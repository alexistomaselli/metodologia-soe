---
name: soe-bootstrap
description: Skill para inicializar el repositorio entregable <empresa>-soe con su scaffold completo (capas SOE + knowledge/ vía el toolkit ASM).
license: MIT
metadata:
  author: alexistomaselli
  version: "1.0.0"
---

# SOE Bootstrap Skill

Esta skill transforma a un agente de IA en un inicializador del **entregable
`<empresa>-soe`**: arma el scaffold completo del SOE de una empresa.

> **Alcance:** esta skill crea el **continente** (las capas del SOE + su README).
> El **contenido** de `knowledge/` lo siembra el toolkit ASM (skill
> `asm-bootstrap` del repo `agentic-shared-memory`). El resto de las capas se
> llenan durante el programa con las [plantillas](../../metodo/plantillas/).
>
> Referencias: [entregable-soe.md](../../metodo/entregable-soe.md) ·
> [arquitectura-repos.md](../../metodo/arquitectura-repos.md).

Cuando el usuario (asesor) invoque esta skill, **seguí estos pasos en orden.**

## Prerrequisito

Idealmente el [diagnóstico](../../metodo/plantillas/plantilla-diagnostico.md) ya
está hecho. Si no, al menos hace falta el nombre de la empresa.

## Fase 1: Datos

Preguntá (una por vez):

1. **"¿Cuál es el nombre de la empresa?"** (define el nombre del repo:
   `<empresa>-soe`, en minúsculas y con guiones; ej. `acme-soe`).
2. **"¿El diagnóstico ya está hecho?"** (si sí, se usará como insumo; si no, se
   avisa que conviene hacerlo antes de avanzar más allá del scaffold).

## Fase 2: Crear el scaffold

Creá el repositorio `<empresa>-soe` (o el directorio local) con esta estructura:

```text
<empresa>-soe/
  README.md
  knowledge/        # ASM (lo siembra asm-bootstrap en la Fase 3)
  model/
  systems/
  automations/
  governance/
```

Creá un `README.md` de portada del SOE con: nombre de la empresa, qué es este
repositorio (su SOE), y un índice de las capas.

Creá un `README.md` semilla en cada capa (excepto `knowledge/`, que lo maneja
ASM):

- **`model/README.md`** — "Modelo operativo estructurado: entidades, estados,
  reglas y eventos. Se completa con la
  [ficha de proceso](../../metodo/plantillas/plantilla-proceso.md)."
- **`systems/README.md`** — "Inventario de herramientas y sistemas + enlaces a sus
  repos de código. El SOE no reemplaza todo: representa, integra o reemplaza según
  convenga."
- **`automations/README.md`** — "Definiciones de automatizaciones: evento,
  condición, acción, sistema, responsable, fallback, trazabilidad."
- **`governance/README.md`** — "Roles, permisos y flujos de aprobación: quién
  puede leer, proponer, editar, aprobar o ejecutar."

## Fase 3: Sembrar knowledge/ (delegación al toolkit ASM)

Sembrá la carpeta `knowledge/` con el toolkit ASM:

- Invocá la skill `asm-bootstrap` (repo `agentic-shared-memory`), que hace la
  entrevista y genera `knowledge/current_state.md`, `knowledge/decisions/ADR-001`
  y las subcarpetas (`foundations/`, `decisions/`, `processes/`, `fuentes/`,
  `comercial/`, `live/` con `daily/` y `hitos.md`).
- Si el toolkit no está disponible como skill, copiá su `template/knowledge/` al
  `knowledge/` del repo.

## Fase 4: Indexar con QMD

Indicá al usuario que inicialice el índice semántico local apuntando a la carpeta
de conocimiento:

```bash
qmd --index <empresa>-soe collection add docs ./knowledge/
```

## Fase 5: Cierre

Imprimí un mensaje de éxito y los próximos pasos:

1. Volcar los hallazgos del diagnóstico en `knowledge/`.
2. Cargar el [roadmap](../../metodo/plantillas/plantilla-roadmap.md).
3. Arrancar el primer frente de trabajo del programa.

> **Regla de oro:** esta skill arma el continente. No inventa procesos, reglas ni
> decisiones: eso se documenta durante el acompañamiento con las plantillas.
