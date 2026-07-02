---
id: ADR-004
titulo: Aplicar ASM (bitácora) a este repositorio, público
autor_rol: advisor
estado: aprobado
fecha: 2026-07-02
supersede: -
---

# ADR-004: Aplicar ASM (bitácora) a este repositorio, público

## Contexto

metodologia-soe se mejora de forma continua. Los commits registran el *qué* pero
no el *porqué* ni las alternativas. Se quería un historial narrado y trazable.

## Decisión

Aplicar el patrón ASM al propio repo (dogfooding), en `knowledge/`, con rol de
**bitácora + decisiones** (no re-documenta la metodología). Todo **público**,
dentro de metodologia-soe (Opción A del análisis).

## Alternativas consideradas

- Repo privado aparte para el historial → descartada: el usuario prefiere
  transparencia ("todo público").
- `knowledge/` gitignored → descartada: frágil.

## Consecuencias

- **A favor:** historial versionado y consultable (vía QMD); coherencia (usamos
  nuestra propia metodología).
- **Costos:** el historial interno es público (aceptado); cuidar no incluir
  secretos en la bitácora.
