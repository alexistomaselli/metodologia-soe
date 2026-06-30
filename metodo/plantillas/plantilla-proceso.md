# Plantilla de ficha de proceso

Modela un proceso de negocio según el [modelo operativo](../modelo-operativo.md).
Una ficha por proceso. Vive en `knowledge/processes/` del SOE de la empresa.

> No hace falta llenar todas las capas el primer día. Empezá por flujo, roles y
> reglas; el resto se completa a medida que se entiende el proceso.

---

```yaml
---
proceso: <nombre>
area: <area>
estado_doc: borrador | revisado | estable
autor: <quien>
fecha: <fecha>
---
```

# Proceso: `<nombre>`

## Objetivo

Qué logra este proceso y por qué importa.

## Alcance

Dónde empieza y dónde termina. Qué queda dentro y qué queda afuera.

## Roles

Quiénes participan (personas y sistemas).

```text
- <rol>
- <rol>
```

## Entidades

Los objetos centrales que el proceso maneja (suelen volverse tablas, formularios o
pantallas).

```text
- <entidad>
- <entidad>
```

## Flujo

El paso a paso. Puede ser texto, lista o diagrama (Mermaid/BPMN).

```text
1. <...>
2. <...>
3. <...>
```

## Estados

Las etapas posibles de la entidad principal.

```text
- <estado>
- <estado>
```

## Reglas

Condiciones que deben cumplirse. Es una de las capas más valiosas: conecta con
validaciones y automatizaciones.

```text
- <regla>
- <regla>
```

## Eventos

Cosas relevantes que ocurren y pueden disparar acciones.

```text
- <evento>
- <evento>
```

## Sistemas involucrados

Dónde ocurre o se registra cada parte (incluye sistemas existentes que se integran,
no solo lo nuevo).

```text
- <sistema>
```

## Datos requeridos

Qué información se necesita y dónde vive.

```text
<entidad>:
  - <campo>
  - <campo>
```

## Automatizaciones posibles

Acciones que podrían ejecutarse solas (evento → condición → acción → responsable →
fallback).

```text
- <automatización>
```

## Intervenciones posibles de IA

Dónde un agente puede asistir, bajo qué límites.

```text
- <intervención> (límite: <...>)
```

## Riesgos o excepciones

Qué puede salir mal y cómo se maneja.

```text
- <riesgo / excepción>
```

## Derivaciones

Qué se puede construir desde esta ficha: documentación, software, base de datos,
automatizaciones, IA.

```text
- <derivación>
```
