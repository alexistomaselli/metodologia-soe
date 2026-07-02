---
id: ADR-001
titulo: Definición canónica de SOE
autor_rol: advisor
estado: aprobado
fecha: 2026-07-01
supersede: -
---

# ADR-001: Definición canónica de SOE

## Contexto

"SOE" se usaba para tres cosas distintas a la vez (el sistema, el método, el
servicio), lo que generaba ambigüedad en todo el repositorio. Había que separarlas
para poder avanzar.

## Decisión

Se fijan tres conceptos distintos:

- **SOE** = el artefacto: la capa operativa que la empresa tiene y opera. Es del
  cliente.
- **Metodología SOE** = el método para construirlo y sostenerlo. Es la IP.
- **El servicio** = acompañamiento continuo como área tercerizada (retainer).

El **entregable** por cliente es un repo `<empresa>-soe` cuyo núcleo es
`knowledge/` (= ASM). Fuente de verdad: `publico/que-es-soe.md`.

## Alternativas consideradas

- SOE = la metodología → descartada: desperdicia la metáfora de "sistema
  operativo" en el método en vez del artefacto.
- Dejar SOE ambiguo (las dos cosas) → descartada: arrastra la confusión.

## Consecuencias

- **A favor:** claridad total; el repo se reordenó solo a partir de esto.
- **Costos:** hubo que reescribir README y reestructurar docs.
- **Habilita:** definir servicio, entregable y arquitectura de repos sin ruido.
