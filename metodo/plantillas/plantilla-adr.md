# Plantilla de ADR

Un ADR (Architecture Decision Record) registra el **porqué** de una decisión
importante. Vive en `knowledge/decisions/` del SOE de la empresa.

> Los ADR no se editan retroactivamente. Si una decisión cambia, se crea un ADR
> nuevo que **supersede** al anterior, dejando trazable la evolución del criterio.

**Nombre del archivo:** `ADR-NNN_titulo-corto.md` (ej. `ADR-007_elegir-supabase.md`).

---

## Frontmatter mínimo (obligatorio)

```yaml
---
id: ADR-<NNN>
titulo: <titulo corto>
autor_rol: advisor | socio | gerente
estado: propuesto | aprobado | superado | rechazado
fecha: <fecha>
supersede: <ADR-NNN o ->
---
```

## Extensiones opcionales (recomendadas para SOEs con agentes IA)

Los siguientes campos son **opcionales** y no rompen ADRs existentes que no los
usen. Aportan trazabilidad bidireccional y facilitan la búsqueda por agentes
que consultan el ASM programáticamente.

```yaml
---
# ... campos mínimos arriba ...
superseded_by: <ADR-NNN o ->   # inverso de `supersede`: quién me reemplazó a mí
layer: business | technical | operational   # dominio de la decisión
scope: [tag1, tag2, ...]       # tags libres para filtrado semántico
---
```

**Por qué existen:**

- `superseded_by` — Desde el ADR viejo, un lector (humano o agente) encuentra al
  reemplazante en un solo hop, sin tener que buscar en todo el repo qué ADR
  posterior lo dejó obsoleto. Complementa a `supersede` que apunta hacia atrás.
- `layer` — Permite filtrar rápido "ADRs de negocio" vs "ADRs técnicos" vs
  "ADRs operacionales". Un agente que consulta el ASM para responder una
  pregunta de negocio puede evitar cargar ADRs de arquitectura de código.
- `scope` — Tags libres (2 a 5) que describen el tema. Útiles para búsqueda
  semántica cuando el `titulo` es genérico.

## Protocolo de supersession

Cuando una decisión cambia:

1. **Nunca editar el cuerpo del ADR viejo.** Es historia inmutable.
2. Crear un **ADR nuevo** que documente el cambio y su motivación.
3. En el nuevo, `supersede: ADR-<NNN-viejo>`.
4. En el viejo, actualizar solo el frontmatter:
   - `estado: superado`
   - `superseded_by: ADR-<NNN-nuevo>` (si se usan extensiones)
5. Opcional pero recomendado: al inicio del cuerpo del ADR viejo, un banner
   corto tipo `> ⚠️ SUPERSEDED por ADR-<NNN>. Ver foundations/ para estado vigente.`
   Esto no cuenta como "editar el cuerpo": es una marca de estado, no un cambio
   de contenido.

Con este protocolo, `foundations/` y `current_state.md` siempre reflejan qué
rige hoy, y `decisions/` conserva el porqué histórico intacto.

---

# ADR-`<NNN>`: `<título>`

## Contexto

Qué situación o problema motiva esta decisión. Qué restricciones existen
(presupuesto, tiempo, herramientas actuales, capacidades del equipo).

## Decisión

Qué se decidió, en una o dos frases claras.

## Alternativas consideradas

Las opciones que se evaluaron y por qué se descartaron.

```text
- <alternativa> -> descartada porque <...>
- <alternativa> -> descartada porque <...>
```

## Consecuencias

Qué implica esta decisión.

- **A favor:** `<...>`
- **En contra / costos:** `<...>`
- **Qué habilita o bloquea a futuro:** `<...>`
