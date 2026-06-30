# Plantilla de roadmap

El roadmap es el puente entre el [diagnóstico](./plantilla-diagnostico.md) y el
programa. Es el entregable que justifica la duración del acompañamiento y del que
se deriva la propuesta comercial.

> Un roadmap no es un cronograma rígido: es la secuencia priorizada de frentes de
> trabajo, con su tamaño aproximado. Define el alcance; el ritmo se ajusta mes a
> mes en la Fase 1.

---

## Resumen del diagnóstico

Un párrafo: cómo funciona la empresa, dónde está el dolor principal y qué
oportunidad mayor reveló el diagnóstico (más allá del pedido inicial).

`<...>`

## Frentes de trabajo

Cada frente es una unidad de trabajo. El **tipo** define cómo se cobra: los builds
van por valor; el resto se cubre con el retainer base.

| # | Frente | Tipo | Qué resuelve | Tamaño | Prioridad | Depende de |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | `<...>` | build / modelado / automatización / asesoría | `<...>` | S / M / L | alta | — |
| 2 | `<...>` | `<...>` | `<...>` | `<...>` | media | #1 |

## Secuencia sugerida

El orden recomendado y por qué. Suele arrancar por un quick win o por el dolor más
urgente del pedido inicial.

```text
Fase 1.a -> <frente> (<por qué primero>)
Fase 1.b -> <frente>
Fase 1.c -> <frente>
...
```

## Builds identificados

Solo los frentes tipo build, con su valor estimado (≥ el piso del entregable).

| Build | Qué incluye | Valor estimado | Meses de desarrollo |
| --- | --- | --- | --- |
| `<...>` | `<...>` | `<...>` | `<...>` |

## Duración estimada del programa

La suma de los frentes da una duración aproximada. **Esto justifica los meses del
retainer**: no se venden "X meses", se vende recorrer este plan.

- Duración estimada: `<n>` meses aprox.
- Compromiso mínimo sugerido: `<...>`

## Propuesta comercial derivada

Se arma a partir de lo anterior (ver [el-servicio.md](../../publico/el-servicio.md)).

```text
Diagnóstico (ya realizado): <monto>   [creditable opcional al 1er mes]

Programa SOE (recomendado):
  - Retainer base: <monto>/mes
  - Builds por valor cuando el roadmap los activa:
      meses con build -> retainer base + valor del build prorrateado
      meses sin build -> retainer base
  - Compromiso mínimo: <...> (atado al roadmap)
```

## Quick wins / primeros 30 días

Qué se ataca primero para mostrar valor temprano.

- `<...>`
