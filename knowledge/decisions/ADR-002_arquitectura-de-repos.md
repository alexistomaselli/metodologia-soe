---
id: ADR-002
titulo: Arquitectura de repositorios (Opción A)
autor_rol: advisor
estado: aprobado
fecha: 2026-07-01
supersede: -
---

# ADR-002: Arquitectura de repositorios (Opción A)

## Contexto

Existían `metodologia-soe` (método) y `agentic-shared-memory` (ASM). Había que
definir cómo conviven y dónde vive el entregable de cada cliente.

## Decisión

Tres niveles, repos separados con jerarquía (Opción A):

- **Método** → `metodologia-soe` (IP; no se entrega al cliente).
- **Toolkit** → `agentic-shared-memory` (estándar ASM: template + skills).
- **Instancia** → `<empresa>-soe` (entregable por cliente; ASM en `knowledge/`).

El método referencia al toolkit; no lo contiene. Detalle en
`metodo/arquitectura-repos.md`.

## Alternativas consideradas

- Fusionar ASM dentro de metodologia-soe → descartada: ASM es instalable y
  reutilizable; conviene standalone.

## Consecuencias

- **A favor:** ASM evoluciona a su ritmo; separación limpia.
- **Costos:** dos repos de IP a mantener coherentes (se resuelve con enlaces).
- **Habilita:** el skill `soe-bootstrap` (scaffold del `<empresa>-soe`).
