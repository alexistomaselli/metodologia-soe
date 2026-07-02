---
id: ADR-003
titulo: SOEM — tablero de gestión de implementaciones
autor_rol: advisor
estado: aprobado
fecha: 2026-07-02
supersede: -
---

# ADR-003: SOEM — tablero de gestión de implementaciones

## Contexto

Se necesitaba una forma de hacer seguimiento del avance de SOE a través de todas
las empresas del portfolio (fases, frentes, y a futuro lo comercial). Surgió la
duda de si eso era un nuevo nivel de abstracción o parte de la metodología.

## Decisión

Es una **herramienta del asesor**, NO un SOE ni parte de la metodología. Se llama
**SOEM** (SOE Management) y se implementa como **módulo dentro de NovaProject**
(repo `project-management`), no en `metodologia-soe`.

Mapeo: empresa = Project (`is_soe`, `soe_phase`, `repository_url`), frente = issue
(`soe_type`, `soe_component`). Distinta del **panel del cliente** (que recorre su
propio SOE).

## Alternativas consideradas

- Documentarlo en `metodologia-soe` → descartada: apila abstracciones; es tool, no
  método.
- `dydialabs-soe` (dogfooding genérico) → descartada: confunde el SOE de una
  empresa con la gestión de la práctica.
- Repo propio → pospuesta: solo si se convierte en producto.

## Consecuencias

- **A favor:** reutiliza NovaProject (kanban, dashboard, finanzas); la metodología
  queda limpia.
- **Habilita:** que el tool guíe la metodología (crear proyecto SOE siembra
  frentes estándar).
