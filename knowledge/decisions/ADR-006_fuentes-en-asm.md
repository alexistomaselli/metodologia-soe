---
id: ADR-006
titulo: Agregar fuentes/ a ASM (material crudo de relevamiento)
autor_rol: advisor
estado: aprobado
fecha: 2026-07-06
supersede: -
---

# ADR-006: Fuentes en ASM

## Contexto

Al arrancar Los Médanos apareció la necesidad de guardar el material crudo de las
reuniones (ej. resúmenes de Fathom), documentos y capturas que sirven de base para
la toma de requerimientos. ASM no tenía un lugar explícito para eso.

## Decisión

Agregar `knowledge/fuentes/` como lugar **permanente** del material crudo de
relevamiento, con subcarpetas por tipo (`reuniones/`, `documentos/`, `capturas/`).
Convención de nombres `<AAAA-MM-DD>-<slug>.<ext>` (fecha = cuándo se obtuvo; sin
carpetas diarias, se organiza por tipo).

Se aplicó en el toolkit `agentic-shared-memory` (template + skill `asm-bootstrap`)
y en `los-medanos-soe`.

## Alternativas consideradas

- Guardarlo en `live/` → descartada: `live/` es transitorio (se migra y vacía); las
  fuentes son permanentes (evidencia/trazabilidad).
- Carpetas diarias → descartada: las fuentes se navegan por tipo, no por día; la
  fecha va en el nombre. (Las carpetas diarias sí aplican a la bitácora.)

## Consecuencias

- **A favor:** separa fuente cruda de conocimiento procesado; trazabilidad de
  requerimientos a su origen.
- **Regla:** de `fuentes/` se destilan `processes/`, `foundations/`, `decisions/`.
