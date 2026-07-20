# Caso: AFPets — Migración de ADRs al estándar SOE oficial

**Cliente:** AFPets
**Fecha de aplicación:** 2026-07-19 / 2026-07-20
**SOE:** repo monorepo `afpets-core` (transición), directorio `knowledge/afpets/`

## Contexto

AFPets venía documentando decisiones en `knowledge/afpets/decisions/` desde marzo 2026, pero con una convención propia (nombre por fecha `YYYY-MM-DD_titulo.md`, sin frontmatter YAML o con frontmatter parcial en inglés). Al mismo tiempo, algunos ADRs habían "cambiado" en la práctica pero el archivo original quedaba sin marca — generando ambigüedad sobre si `decisions/` era bitácora inmutable o fuente activa de verdad.

Al revisar la metodología SOE oficial y ASM, se detectó que:

1. **La estructura ya estaba correctamente prescrita** en ASM (`foundations/` = estado vigente, `decisions/` = ADRs inmutables, `current_state.md` = snapshot).
2. **El estándar de nomenclatura SOE existía** (`ADR-NNN_titulo.md` + frontmatter en español) y estaba siendo aplicado en otros clientes (ej. Los Médanos).
3. **AFPets había divergido** — no por decisión, sino por haber arrancado antes de consultar el estándar.

El síntoma reportado por el owner del negocio ("¿decisions es bitácora o definición fija?") era la señal de que la desviación estaba generando fricción real.

## Trabajo aplicado

### 1. Alineación al estándar oficial

- **26 ADRs renombrados** de `YYYY-MM-DD_titulo.md` a `ADR-NNN_titulo.md`, numerados cronológicamente.
- **`git mv`** en cada uno para preservar historia.
- **Frontmatter estándar SOE** aplicado en los 26:

  ```yaml
  ---
  id: ADR-<NNN>
  titulo: <titulo corto en español>
  autor_rol: advisor
  estado: aprobado | superado
  fecha: <YYYY-MM-DD>
  supersede: <ADR-NNN o ->
  ---
  ```

### 2. Uso de extensiones opcionales

Se aplicaron las 3 extensiones propuestas en este mismo PR:

- **`superseded_by`** — usado en el 1 caso de supersession real (`ADR-007` → `ADR-008`) para tener trazabilidad bidireccional.
- **`layer`** — clasificados los 26 ADRs entre `business` (2), `technical` (20) y `operational` (4). Permite que agentes IA filtren decisiones por dominio.
- **`scope`** — 2-5 tags por ADR (ej. `[fiel, arquitectura, agentes]`, `[planes, productos, partners]`).

### 3. Aplicación real del protocolo de supersession

Caso concreto: `ADR-007_fiel-rag-modes.md` fue reemplazado por `ADR-008_cve-contexto-veterinario.md` (RAG con embeddings → documento veterinario completo en system prompt).

Se aplicó el protocolo del template exactamente:

- Cuerpo de `ADR-007` **no editado**.
- Frontmatter de `ADR-007` actualizado: `estado: superado`, `superseded_by: ADR-008`.
- Frontmatter de `ADR-008` actualizado: `supersede: ADR-007`.
- Banner corto al inicio del cuerpo de `ADR-007`: `> ⚠️ SUPERSEDED por ADR-008_cve-contexto-veterinario.md. ...`

### 4. Foundations linkea decisions activas

En `foundations/afpets_model.md`, la sección "MVP Visión 6m" ahora incluye links explícitos a los ADRs activos que sostienen cada componente (CVE, bitácora, business-model, multi-pet, gap-analysis). Esto permite que un lector vaya del "qué rige hoy" al "por qué se decidió" en un solo salto.

### 5. Barrido masivo de referencias

Todos los links a nombres viejos fueron actualizados en:

- `README.md`, `CLAUDE.md`
- `knowledge/afpets/current_state.md`
- `knowledge/afpets/foundations/*.md`
- `knowledge/afpets/processes/*.md`
- `knowledge/afpets/live/daily/*.md` (varios)
- `apps/*/README.md`, `apps/*/architecture/*.md`
- `apps/*/knowledge-processes/*.md`

Verificación final con `grep -rE "decisions/2026-0[3-7]"` = 0 referencias antiguas.

## Lecciones aprendidas (input para la metodología)

1. **El uso ambiguo de `decisions/` es un antipatrón detectable con una sola pregunta al owner del negocio**: *"¿decisions funciona como bitácora o como definición fija?"* Si la respuesta es "no sé" o "las dos", hay drift.

2. **El protocolo de supersession estaba implícito pero no explícito** en el template original. En la práctica esto llevaba a editar cuerpos de ADRs viejos "para mantenerlos actualizados", rompiendo la inmutabilidad. Formalizar el protocolo (como hace este PR) previene esa drift.

3. **`superseded_by` no es redundante** con `supersede`. Cuando alguien abre un ADR viejo, quiere saber cuál lo reemplazó **inmediatamente**, sin grep. Sin el campo, hay que buscar en todo el repo.

4. **`layer` habilita búsqueda diferenciada por agentes IA**. Un agente que responde preguntas de negocio no debería cargar ADRs de arquitectura de código. Sin `layer`, esa distinción se hace por parsing del contenido, que es frágil.

5. **La migración fue barata**: ~1 hora para 26 ADRs (rename + frontmatter + link sweep), delegando el trabajo mecánico a un subagente. La barrera de entrada al estándar oficial es baja.

## Referencias

- ADRs migrados: `knowledge/afpets/decisions/ADR-001` a `ADR-026` en el repo `afpets-core`.
- Daily de la sesión: `knowledge/afpets/live/daily/2026-07-19_capa1-cerrada-y-asm-aplicado.md`.
- Registro SOEM: `soe_dailies` entry del 2026-07-19 (proyecto AFPets).
