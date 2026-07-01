# Skills

Instrucciones ejecutables para agentes de IA que automatizan tareas repetibles de
la metodología. Una skill no define la metodología: ejecuta una tarea dentro de
ella.

## Disponibles

- [soe-bootstrap](./soe-bootstrap/SKILL.md) — inicializa el repositorio entregable
  `<empresa>-soe` con su scaffold completo. Delega el sembrado de `knowledge/` al
  toolkit ASM.

## Relacionadas (en el toolkit ASM)

El repo [agentic-shared-memory](https://github.com/alexistomaselli/agentic-shared-memory)
aporta las skills del componente de conocimiento:

- `asm-bootstrap` — siembra `knowledge/` (entrevista + archivos semilla).
- `qmd` — motor de índice semántico local.
- `qmd-shared-memory` — trazabilidad del trabajo diario sobre la memoria.
