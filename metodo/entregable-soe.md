# El entregable: `<empresa>-soe`

Cómo se arma el repositorio que le queda a cada empresa. Es el artefacto que
produce la metodología: el SOE de la empresa.

> Definición de qué es el entregable: [../publico/que-es-soe.md](../publico/que-es-soe.md).
> Este documento es el *cómo* se construye, a nivel scaffold.

## Estructura

```text
<empresa>-soe/
  README.md          # portada: qué es este SOE y cómo navegarlo
  knowledge/         # ASM — componente de conocimiento (lo provee el toolkit ASM)
    current_state.md
    foundations/
    decisions/
    processes/
    fuentes/         # material crudo de relevamiento recibido (ADR-006)
    comercial/       # artefactos de la relación producidos/enviados (ADR-009)
    live/            # bitácora: daily/ + hitos.md
  model/             # modelo operativo estructurado (entidades, estados, reglas, eventos)
  systems/           # inventario de herramientas + enlaces a sus repos de código
  automations/       # definiciones de automatizaciones (evento, condición, acción, regla)
  governance/        # roles, permisos y flujos de aprobación
```

## Responsabilidades por capa

- **`knowledge/`** — la memoria organizacional. Es el **piso garantizado**: se
  entrega siempre. Su estructura y skills los provee el toolkit
  [agentic-shared-memory](https://github.com/alexistomaselli/agentic-shared-memory).
- **`model/`** — la representación estructurada de la operación. Ver
  [modelo-operativo.md](./modelo-operativo.md).
- **`systems/`** — el SOE no reemplaza todo: inventaría y enlaza las herramientas
  existentes y las nuevas. Las apps de código viven en sus propios repos.
- **`automations/`** — qué se automatiza, dónde corre y bajo qué reglas.
- **`governance/`** — quién puede leer, proponer, editar, aprobar o ejecutar.

## Cómo se arma

1. **Crear el repo** `<empresa>-soe`.
2. **Sembrar `knowledge/`** con el toolkit ASM (su template + el skill
   `asm-bootstrap`). El qmd indexa `<empresa>-soe/knowledge/`.
3. **Crear las capas SOE** (`model/`, `systems/`, `automations/`, `governance/`)
   según las vaya requiriendo el acompañamiento. No es obligatorio poblarlas todas
   desde el inicio.
4. **Escribir el `README.md`** de portada del SOE de la empresa.

## Separación de responsabilidades

- El **toolkit ASM** se ocupa **solo de `knowledge/`**. No conoce el resto de las
  capas del SOE.
- El **scaffold completo de `<empresa>-soe`** es responsabilidad de la metodología
  SOE (este repo), automatizado por el skill
  [soe-bootstrap](../skills/soe-bootstrap/SKILL.md).

## Principio del entregable

El piso siempre se entrega; el techo se construye según necesidad. El repo nunca
está "terminado": crece con la empresa. Esa continuidad es el modelo de servicio
([../publico/el-servicio.md](../publico/el-servicio.md)).
