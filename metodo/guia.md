# Guía maestra: cómo aplicar SOE de punta a punta

Recorrido operativo de la Metodología SOE. Leyendo esto, de arriba a abajo, se
entiende **cómo hacer todo**: desde el primer contacto con una empresa hasta
operar y evolucionar su SOE. Cada paso enlaza el documento o plantilla que se usa.

> Recordá el marco: SOE es el **artefacto** (lo que la empresa tiene), la
> Metodología SOE es el **método** (esto), y el servicio es el **acompañamiento
> continuo**. Definiciones: [qué es SOE](../publico/que-es-soe.md).

---

## 0. Antes de empezar: entender el marco

- [Qué es SOE](../publico/que-es-soe.md) — las tres cosas y el entregable.
- [Filosofía](../publico/filosofia.md) y [Principios](../publico/principios.md) —
  el criterio con el que se decide.
- [Componentes](../publico/componentes.md) — las piezas de un SOE.

La metodología **se adapta a cada empresa**. Lo único fijo es que **siempre se
empieza por el diagnóstico**.

## 1. Contacto y venta

Antes de vender, se entiende qué gana la empresa y cómo se contrata.

- [Propuesta de valor](../publico/propuesta-de-valor.md) — el *por qué pagar*.
- [El servicio](../publico/el-servicio.md) — el *cómo se contrata*: el camino
  Fase 0 → Fase 1, retainer base + builds por valor, y cómo se presenta la
  propuesta.

Regla de oro comercial: **no se vende un software, se vende la relación** (el área
de sistemas tercerizada). El primer build es el primer entregable de esa relación.

## 2. Fase 0 — Diagnóstico

La entrada, siempre. Se entiende la empresa y se reencuadra su pedido.

- [Plantilla de diagnóstico](./plantillas/plantilla-diagnostico.md) — guion de
  entrevista + relevamiento (incluye costos actuales = ancla de precio).

**Salida:** el arranque del SOE (se siembra `knowledge/` con el toolkit ASM — ver
[entregable](./entregable-soe.md)) + el roadmap.

## 3. Roadmap y propuesta del programa

El puente entre el diagnóstico y el acompañamiento.

- [Plantilla de roadmap](./plantillas/plantilla-roadmap.md) — frentes de trabajo,
  builds con valor, duración que justifica los meses, y la propuesta comercial
  derivada.

## 4. Fase 1 — Programa (ejecución del roadmap)

La relación continua. Mes a mes se avanza el roadmap; el contenido varía por
empresa (build, modelado, automatización o asesoría).

- **Modelar procesos:** [modelo operativo](./modelo-operativo.md) +
  [ficha de proceso](./plantillas/plantilla-proceso.md) → van a
  `<empresa>-soe/knowledge/processes/`.
- **Registrar decisiones:** [plantilla de ADR](./plantillas/plantilla-adr.md) →
  van a `<empresa>-soe/knowledge/decisions/`.
- **Construir herramientas, automatizaciones e IA:** según los componentes
  ([componentes](../publico/componentes.md)); el stack posible en
  [implementación técnica](./implementacion-tecnica.md).

Mientras se ejecuta, **el SOE crece como subproducto**: cada build documenta
procesos y decisiones.

## 5. El entregable

Todo lo anterior se materializa en el repositorio del cliente.

- [Entregable `<empresa>-soe`](./entregable-soe.md) — estructura, cómo se arma y
  qué capa cubre cada carpeta.

## 6. Operación y evolución continua

El SOE no se entrega y se abandona: se mantiene y evoluciona.

- Gobernanza y evolución continua: secciones 9 y 10 de
  [componentes](../publico/componentes.md).
- El acompañamiento continuo (retainer) es quien sostiene esta etapa.

## 7. Cómo se consume el SOE

- **Hoy (preview):** el repo se recorre con Docsify localmente
  (`python3 -m http.server 3000` → http://localhost:3000).
- **Visión (panel):** un dashboard con acceso por rol + un LLM que responde sobre
  toda la información vía QMD indexado. El *todo* es SOE; la documentación vive en
  ASM (`knowledge/`).

## Dónde vive cada cosa

- Este método: repo `metodologia-soe`.
- El toolkit de conocimiento (ASM): repo `agentic-shared-memory`.
- El SOE de cada empresa: repo `<empresa>-soe`.

Detalle en [arquitectura de repos](./arquitectura-repos.md).
