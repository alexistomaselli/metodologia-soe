# Knowledge (ASM) — memoria del proyecto

Esta carpeta aplica el patrón **ASM (Agentic Shared Memory)** al propio repositorio
de la Metodología SOE (dogfooding).

> **Rol de ASM acá:** NO re-documenta la metodología (eso vive en `publico/` y
> `metodo/`). Cumple el rol de **bitácora + decisiones**: la memoria del *proceso*
> de construir y mejorar la metodología, de forma continua y trazable.

## Estructura

- `current_state.md` — foto del estado actual del proyecto.
- `decisions/` — ADRs: el *porqué* de las decisiones grandes (y sus alternativas).
- `foundations/` — definiciones estables de referencia.
- `live/` — bitácora viva (diario de trabajo en `live/daily/`).

## Indexación (opcional)

Para consultar esta memoria con un LLM vía QMD:

```bash
qmd --index metodologia-soe collection add docs ./knowledge/
```

Ver el toolkit: [agentic-shared-memory](https://github.com/alexistomaselli/agentic-shared-memory).
