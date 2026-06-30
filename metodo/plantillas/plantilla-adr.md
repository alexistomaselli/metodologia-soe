# Plantilla de ADR

Un ADR (Architecture Decision Record) registra el **porqué** de una decisión
importante. Vive en `knowledge/decisions/` del SOE de la empresa.

> Los ADR no se editan retroactivamente. Si una decisión cambia, se crea un ADR
> nuevo que **supersede** al anterior, dejando trazable la evolución del criterio.

**Nombre del archivo:** `ADR-NNN_titulo-corto.md` (ej. `ADR-007_elegir-supabase.md`).

---

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
