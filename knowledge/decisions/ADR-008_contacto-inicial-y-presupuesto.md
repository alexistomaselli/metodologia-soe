---
id: ADR-008
titulo: Fase de contacto inicial, dónde se define el presupuesto y dos modelos de Fase 1
autor_rol: advisor
estado: aprobado
fecha: 2026-07-08
supersede: -
---

# ADR-008: Contacto inicial y definición del presupuesto

## Contexto

La metodología saltaba directo a "Fase 0 diagnóstico pago" sin nombrar cómo se
llega ahí. En la práctica (Los Médanos) hubo un **contacto inicial** (reunión de
Fathom) previo, del que salió la propuesta y el presupuesto. Además, el presupuesto
del diagnóstico no puede definirse *dentro* del diagnóstico.

## Decisión

1. **Fase de contacto inicial (pre-venta)** explícita, antes del diagnóstico pago:
   1+ reuniones para detectar necesidad, calificar fit y recolectar primeras
   fuentes. Salida: la propuesta. (Excepción: cliente que ya lo tiene claro y trae
   fuentes → más corto, pero existe.)
2. **El presupuesto se define en la propuesta**, no en el diagnóstico:
   - Diagnóstico: precio fijo, en la propuesta.
   - Fase 1: bolsa de horas se fija en la propuesta; builds por valor se cierran
     contra el roadmap del diagnóstico.
3. **Dos modelos de Fase 1**, se elige por cliente:
   - **A — Bolsa de horas mensual** (sin ataduras, flexible; commoditiza).
   - **B — Retainer base + builds por valor** (captura más valor; requiere roadmap).

## Consecuencias

- El flujo comercial queda completo: contacto inicial → propuesta → diagnóstico →
  programa.
- Se documentan ambos modelos (antes solo estaba B). Los Médanos usa A.
- Cambios: `publico/el-servicio.md`, `metodo/proceso.md` (paso 0).

## Actualización (2026-07-08)

Refinamiento del punto 2 tras redactar la propuesta real de Los Médanos: el
diagnóstico **como fase pagada aparte es propio del Modelo B**. En el **Modelo A
(bolsa de horas)** no se cobra por separado — el relevamiento inicial se **absorbe
en las primeras horas del programa**. El principio se mantiene (el presupuesto se
define en la propuesta, a partir del análisis del contacto inicial); lo que pasa a
ser **dependiente del modelo** es la existencia de un diagnóstico pago separado.

Reflejado en: `metodo/plantillas/plantilla-propuesta.md` (dos modelos + contacto
inicial), `publico/el-servicio.md`, `metodo/proceso.md`.
