---
id: ADR-007
titulo: Diario de trabajo cross-proyecto (soe_dailies) + skill soe-log
autor_rol: advisor
estado: aprobado
fecha: 2026-07-06
supersede: -
---

# ADR-007: Diario cross-proyecto + skill soe-log

## Contexto

Al trabajar en `~/Proyectos/<proyecto>` se pierde la vista cross-proyecto. Se
quería poder abrir `~/Proyectos` (o cualquier lado) y preguntar "¿qué trabajé
último?" sin recorrer carpetas ni quemar tokens, y documentar el avance una sola
vez.

## Decisión

- **Tabla `soe_dailies`** (project_id, date, summary) en la base de SOEM
  (project-management) como diario de trabajo del asesor por proyecto.
- **Skill de usuario `soe-log`** (`~/.claude/skills/soe-log/`) con dos modos:
  - **capturar:** escribe el daily en la bitácora del cliente
    (`<empresa>-soe/knowledge/live/daily/`) **y** en SOEM (`soe_dailies` + tareas +
    estado de módulos), en una pasada liviana;
  - **recordar:** consulta `soe_dailies` vía MCP `supabase-dydialabs` y responde
    cross-proyecto.

División de granularidad: bitácora del cliente = versión profunda (su SOE); SOEM =
foto liviana y consultable.

## Alternativas consideradas

- Recorrer las carpetas de cada proyecto para el recall → descartada: caro en
  tokens. Se centraliza en la base de SOEM.
- Reusar `activities` o `project_docs` para el daily → descartada: `soe_dailies`
  es más limpio y directo para la consulta cross-proyecto.
- Sincronización automática bidireccional bitácora↔SOEM → fuera de alcance
  (complejidad de gusto). Captura y recall a pedido.

## Consecuencias

- **A favor:** un solo comando documenta en ambos lados; consulta barata desde
  cualquier lado; visual en la app de SOEM.
- **Requisito:** el MCP `supabase-dydialabs` activo en Claude Code (config global).
