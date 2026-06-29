# Modelo operativo SOE

El modelo operativo es una representacion estructurada de como funciona una
empresa, un area o un proceso de negocio.

No es solamente un documento narrativo. Tampoco es solamente un diagrama. Es una
forma de ordenar los elementos que hacen que una operacion exista: roles,
entidades, procesos, reglas, estados, eventos, sistemas, datos, automatizaciones
y decisiones.

Dentro de la metodologia SOE, el modelo operativo es una pieza central porque
permite pasar de "entendemos mas o menos como trabaja la empresa" a "tenemos una
representacion clara desde la cual podemos documentar, construir software,
automatizar e incorporar IA".

## Diferencia con un cursograma

Un cursograma, diagrama de flujo o BPMN puede formar parte del modelo operativo,
pero no agota el modelo.

Un cursograma responde principalmente:

> Como fluye este proceso?

El modelo operativo responde tambien:

> Que roles participan, que entidades existen, que estados cambian, que reglas
> se aplican, que eventos ocurren, que sistemas intervienen, que datos se
> registran y que decisiones pueden automatizarse?

Por eso, un cursograma es una vista del modelo operativo. Es una forma visual de
representar el flujo, pero el modelo completo necesita mas capas.

## Niveles del modelo

El modelo operativo puede construirse en distintos niveles.

### Nivel empresa

Representa la organizacion completa:

- unidades de negocio;
- areas;
- capacidades principales;
- sistemas;
- fuentes de datos;
- roles generales;
- procesos criticos;
- indicadores.

### Nivel area

Representa una parte de la empresa:

- ventas;
- operaciones;
- administracion;
- atencion al cliente;
- logistica;
- finanzas;
- tecnologia.

### Nivel proceso

Representa un flujo puntual:

- gestion de turnos;
- alta de cliente;
- venta;
- facturacion;
- compra a proveedor;
- gestion de reclamos;
- entrega de servicio.

En la practica conviene empezar por procesos concretos, porque son mas faciles
de observar y modelar.

## Capas del modelo operativo

Un modelo operativo puede describirse mediante varias capas.

### 1. Proceso

Describe que ocurre paso a paso.

Ejemplo:

```text
Cliente solicita turno
-> Recepcion registra solicitud
-> Sistema verifica disponibilidad
-> Recepcion confirma turno
-> Sistema envia recordatorio
-> Cliente asiste
-> Profesional realiza atencion
-> Administracion registra pago
```

Esta capa puede representarse como texto, cursograma, BPMN, diagrama Mermaid o
cualquier formato visual equivalente.

### 2. Roles

Define quienes participan.

Ejemplo:

```text
- Cliente
- Recepcion
- Profesional
- Administracion
- Sistema
```

Los roles importan porque luego permiten definir permisos, responsabilidades,
pantallas, acciones y limites para agentes de IA.

### 3. Entidades

Define los objetos centrales del negocio.

Ejemplo:

```text
- Cliente
- Turno
- Servicio
- Profesional
- Pago
```

Las entidades son importantes porque muchas veces se convierten en tablas,
colecciones, formularios, pantallas, endpoints de API o documentos de ASM.

### 4. Estados

Define las etapas posibles de una entidad.

Ejemplo para `Turno`:

```text
- solicitado
- confirmado
- cancelado
- reprogramado
- realizado
- ausente
- cobrado
```

Los estados permiten saber donde esta cada operacion y que acciones son validas
en cada momento.

### 5. Reglas

Define condiciones que deben cumplirse.

Ejemplo:

```text
- Un turno no puede confirmarse si no hay profesional disponible.
- Un profesional no puede tener dos turnos en el mismo horario.
- Un turno realizado debe quedar asociado a un pago.
- Una cancelacion con menos de 24 horas puede generar penalidad.
```

Las reglas son una de las partes mas valiosas del modelo porque conectan
conocimiento operativo con validaciones, automatizaciones y decisiones asistidas.

### 6. Eventos

Define cosas relevantes que ocurren.

Ejemplo:

```text
- turno_solicitado
- turno_confirmado
- turno_cancelado
- turno_reprogramado
- turno_realizado
- pago_registrado
```

Los eventos sirven para activar automatizaciones, generar trazabilidad, alimentar
dashboards o disparar tareas para agentes.

### 7. Sistemas

Define donde ocurre o se registra cada parte del proceso.

Ejemplo:

```text
- Panel interno
- Google Calendar
- WhatsApp
- Pasarela de pago
- Planilla historica
```

Esta capa evita pensar el SOE como reemplazo obligatorio de todo lo existente.
El SOE puede representar sistemas actuales, integrarlos o decidir reemplazarlos
cuando tenga sentido.

### 8. Datos

Define que informacion se necesita y donde vive.

Ejemplo:

```text
Cliente:
- nombre
- telefono
- email

Turno:
- fecha
- hora
- servicio
- profesional
- estado

Pago:
- monto
- medio
- estado
```

Esta capa ayuda a derivar formularios, bases de datos, APIs, permisos y reportes.

### 9. Automatizaciones

Define acciones que pueden ejecutarse automaticamente.

Ejemplo:

```text
- Cuando se confirma un turno, enviar WhatsApp al cliente.
- 24 horas antes del turno, enviar recordatorio.
- Si el cliente no asiste, marcar el turno como ausente.
- Cuando se registra el pago, actualizar el estado del turno.
```

Una automatizacion no deberia definirse aislada. Debe estar conectada con un
evento, una regla, una accion y una responsabilidad.

### 10. IA y agentes

Define como puede intervenir la inteligencia artificial.

Ejemplo:

```text
Agente de turnos:
- responde consultas sobre disponibilidad;
- explica el proceso de gestion de turnos;
- detecta turnos sin pago registrado;
- sugiere reprogramaciones;
- no modifica turnos sin confirmacion humana.
```

La IA no deberia operar sobre intuiciones sueltas. Debe apoyarse en ASM, en el
modelo operativo, en permisos y en limites claros.

## Ejemplo completo: gestion de turnos

### Vista de flujo

```text
1. Cliente solicita un turno.
2. Recepcion registra la solicitud.
3. El sistema verifica disponibilidad.
4. Recepcion confirma o propone otro horario.
5. El sistema envia confirmacion.
6. El sistema envia recordatorio 24 horas antes.
7. El cliente asiste o no asiste.
8. El profesional realiza la atencion.
9. Administracion registra el pago.
10. El turno queda cerrado.
```

### Roles

```text
- Cliente
- Recepcion
- Profesional
- Administracion
- Sistema
```

### Entidades

```text
- Cliente
- Turno
- Servicio
- Profesional
- Pago
```

### Estados del turno

```text
- solicitado
- confirmado
- reprogramado
- cancelado
- realizado
- ausente
- cobrado
- cerrado
```

### Reglas

```text
- Un turno confirmado debe tener fecha, hora, cliente, servicio y profesional.
- Un profesional no puede tener dos turnos confirmados en el mismo horario.
- Un turno realizado debe quedar asociado a una atencion registrada.
- Un turno cobrado debe tener un pago asociado.
- Un turno cerrado no puede modificarse sin permiso administrativo.
```

### Eventos

```text
- turno_solicitado
- turno_confirmado
- turno_reprogramado
- turno_cancelado
- recordatorio_enviado
- turno_realizado
- turno_marcado_ausente
- pago_registrado
- turno_cerrado
```

### Automatizaciones posibles

```text
- Al confirmar turno, enviar mensaje de confirmacion.
- 24 horas antes, enviar recordatorio.
- Si falta una hora para el turno y no fue confirmado, avisar a recepcion.
- Si el turno fue realizado y no tiene pago, crear tarea para administracion.
```

### Derivaciones posibles

Desde este modelo se pueden derivar varias piezas del SOE:

```text
ASM:
- documento del proceso de gestion de turnos;
- reglas operativas;
- glosario de entidades;
- bitacora de cambios del proceso.

Software:
- pantalla de turnos;
- formulario de alta;
- calendario;
- vista por profesional;
- historial del cliente.

Base de datos:
- tabla clientes;
- tabla turnos;
- tabla profesionales;
- tabla servicios;
- tabla pagos.

Automatizaciones:
- confirmaciones;
- recordatorios;
- alertas internas;
- tareas administrativas.

IA:
- agente de consulta de turnos;
- asistente para recepcion;
- detector de inconsistencias;
- generador de resumenes operativos.
```

## Plantilla inicial

Para modelar un proceso bajo SOE se puede comenzar con esta plantilla:

```text
# Nombre del proceso

## Objetivo

## Alcance

## Roles

## Entidades

## Flujo

## Estados

## Reglas

## Eventos

## Sistemas involucrados

## Datos requeridos

## Automatizaciones posibles

## Intervenciones posibles de IA

## Riesgos o excepciones

## Derivaciones
```

## Criterio practico

Un modelo operativo es util si permite responder preguntas como:

- Que ocurre en este proceso?
- Quien interviene?
- Que informacion se necesita?
- Que reglas se aplican?
- Que estados puede tener cada entidad?
- Que eventos disparan acciones?
- Que sistemas participan?
- Que podria automatizarse?
- Que podria consultar o asistir una IA?
- Que software habria que construir o integrar?

Si el modelo no ayuda a derivar decisiones, software, documentacion o
automatizaciones, probablemente todavia es solo una descripcion incompleta.

