# Estado actual del proyecto

_Actualizado: 2026-07-02_

## Qué es

Repositorio de la **Metodología SOE** (IP del método). Público. Definición
canónica en [../publico/que-es-soe.md](../publico/que-es-soe.md).

## Estructura viva

- `publico/` — capa vendible: qué es SOE, filosofía, principios, componentes,
  propuesta de valor, el servicio.
- `metodo/` — playbook interno: guía maestra, proceso, modelo operativo,
  entregable, implementación técnica, arquitectura de repos, plantillas.
- `skills/` — `soe-bootstrap` (scaffold del `<empresa>-soe`).
- `knowledge/` — esta memoria ASM (bitácora + decisiones).

## Ecosistema de repos

- `metodologia-soe` — el método (este repo).
- `agentic-shared-memory` — toolkit ASM (patrón + template + skills).
- `<empresa>-soe` — entregable por cliente (ASM en `knowledge/`).
- `project-management` (NovaProject) — hospeda **SOEM**, el tablero de gestión de
  implementaciones (herramienta del asesor, no un SOE).

## En curso

- Módulo **SOEM** en project-management: Fases 1-3 hechas (migración, tipos,
  vista "Gestión SOE") + creación de proyecto con toggle SOE que siembra frentes.
  Pendientes: Fase 4 (kanban por tipo), Fase 5 (dashboard + comercial), Fase 6
  (sync roadmap).

## Decisiones clave

Ver [decisions/](./decisions/).
