---
id: ADR-005
titulo: Modelo de 3 niveles para la gestión SOE (componente / módulo / tarea)
autor_rol: advisor
estado: aprobado
fecha: 2026-07-02
supersede: -
---

# ADR-005: Modelo componente / módulo / tarea

## Contexto

En SOEM (el tablero en project-management) el seed creaba 5 issues, uno por
componente. Eso disfrazaba al componente de tarea. Pero una tarea (issue) tiene
detalle, responsable y estado; un componente no es eso. Además hacía falta poder
tener más de un build o más de una automatización, y cada unidad de trabajo
necesita fechas, presupuesto y su propio grupo de tareas.

## Decisión

Modelo de 3 niveles bajo la empresa:

- **Componente** = una de las 5 dimensiones fijas del SOE (knowledge, model,
  systems, automations, governance). Es una etiqueta/clasificación, no una entidad.
- **Módulo** = la entidad real (mini-proyecto) dentro de un componente. Tiene
  nombre, tipo, estado, fecha inicio/fin, presupuesto y sus tareas. Puede haber
  1..N por componente (ej. dos builds en `systems`).
- **Tarea** = el avance granular dentro de un módulo.

Progreso: módulo = sus tareas done/total; componente = agregado de sus módulos;
empresa = agregado. Se mantiene la nomenclatura de la metodología: _componentes_ =
los 5; la unidad de trabajo se materializa como _módulo_.

## Alternativas consideradas

- Componente como etiqueta en el issue (modelo plano) → descartada: no soporta
  fechas/presupuesto por unidad de trabajo ni múltiples builds de forma limpia.
- Invertir la nomenclatura (frente = los 5, componente = la unidad) → descartada:
  contradice `publico/componentes.md` y es menos natural en español.

## Consecuencias

- **A favor:** representa la realidad (cada build/automatización es un mini-proyecto
  con fechas y presupuesto); habilita la capa comercial por módulo.
- **Costos:** nueva tabla `soe_modulos` + `issues.modulo_id`; la app SOE maneja una
  jerarquía extra (los no-SOE quedan igual, `modulo_id` nullable).
- **Nota:** la nomenclatura de la metodología es adaptable; puede revisarse cuando
  se use visualmente en la operación diaria.
