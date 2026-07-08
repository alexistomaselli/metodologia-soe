# Proceso SOE

El proceso SOE describe como aplicar la metodologia en una empresa.

No es una secuencia rigida. Es un ciclo de trabajo que puede repetirse y
profundizarse. Una implementacion puede empezar pequena, por un area o proceso,
y expandirse gradualmente.

## Vista general

```text
0. Contacto inicial (pre-venta)
1. Diagnostico
2. Relevamiento y documentacion
3. Construccion de ASM
4. Modelo operativo
5. Diseno de herramientas
6. Automatizaciones e integraciones
7. IA y agentes
8. Panel web
9. Gobernanza
10. Evolucion continua
```

## 0. Contacto inicial (pre-venta)

Antes del diagnóstico pago hay una etapa de **contacto inicial**: una o más
reuniones para detectar la necesidad, calificar si hay fit y recolectar las
primeras fuentes (una reunión grabada, documentos que traiga el cliente).

Es pre-venta (sin costo o low-touch). Su salida es **la propuesta**, donde se
define el **presupuesto del diagnóstico** (fijo) y se plantea el modelo de la
Fase 1. Si la empresa ya lo tiene clarísimo y trae fuentes, es corto, pero existe
igual: no se cotiza a ciegas.

> El presupuesto NO se define dentro del diagnóstico. Se define antes, en la
> propuesta que sale del contacto inicial. Ver
> [el-servicio.md](../publico/el-servicio.md).

## 1. Diagnostico

El diagnostico busca entender la empresa antes de proponer soluciones.

Preguntas clave:

- que vende o entrega la empresa?
- quienes participan en la operacion?
- que procesos son criticos?
- que herramientas se usan?
- donde se pierde informacion?
- que tareas se repiten?
- que decisiones dependen de pocas personas?
- que problemas aparecen con frecuencia?
- que oportunidades de mejora existen?

Entregables posibles:

- mapa inicial de areas;
- lista de procesos criticos;
- inventario de herramientas;
- dolores operativos;
- riesgos;
- oportunidades de automatizacion;
- hipotesis de mejora.

## 2. Relevamiento y documentacion

Se recopila informacion mediante entrevistas, observacion, documentos existentes,
capturas de sistemas, planillas, conversaciones y ejemplos reales de operacion.

El objetivo no es escribir todo de una vez, sino convertir conocimiento disperso
en conocimiento explicito.

Entregables posibles:

- notas de entrevistas;
- procesos descriptos;
- reglas detectadas;
- glosario inicial;
- decisiones registradas;
- problemas recurrentes;
- bitacora de avance.

## 3. Construccion de ASM

ASM funciona como memoria documental del SOE.

En esta etapa se ordena el conocimiento en una estructura versionada. ASM puede
incluir:

- procesos;
- reglas de negocio;
- glosario;
- bitacora;
- decisiones;
- politicas;
- documentacion funcional;
- documentacion tecnica;
- arquitectura;
- aprendizajes.

Criterio:

> ASM debe ser entendible por humanos y util como contexto para agentes de IA.

## 4. Modelo operativo

Se construye una representacion estructurada de la operacion.

El modelo operativo puede empezar por procesos puntuales y luego conectarse a un
mapa mas amplio de la empresa.

Elementos tipicos:

- roles;
- entidades;
- procesos;
- estados;
- reglas;
- eventos;
- sistemas;
- datos;
- automatizaciones posibles;
- intervenciones posibles de IA.

Documento relacionado:

- [Modelo operativo](./modelo-operativo.md)

## 5. Diseno de herramientas

Con el diagnostico, ASM y el modelo operativo como base, se define que software o
interfaces hacen falta.

No todo debe convertirse en una aplicacion nueva. Algunas necesidades pueden
resolverse integrando herramientas existentes, creando formularios simples,
mejorando documentacion o automatizando tareas.

Entregables posibles:

- mapa de modulos;
- pantallas necesarias;
- permisos por rol;
- entidades de base de datos;
- flujos de usuario;
- criterios de priorizacion.

## 6. Automatizaciones e integraciones

Se identifican procesos que pueden ejecutarse o asistirse automaticamente.

Cada automatizacion deberia definirse con:

- evento disparador;
- condicion;
- accion;
- sistema involucrado;
- responsable;
- fallback humano;
- forma de trazabilidad.

Ejemplo:

```text
Evento: turno_confirmado
Condicion: cliente tiene telefono registrado
Accion: enviar mensaje de confirmacion
Sistema: WhatsApp
Fallback: avisar a recepcion si falla el envio
```

## 7. IA y agentes

La IA se incorpora despues de tener contexto minimo confiable.

Los agentes pueden consultar ASM, asistir usuarios, detectar inconsistencias,
generar resumenes, sugerir mejoras o ejecutar acciones bajo control.

Cada agente deberia definirse con:

- nombre;
- proposito;
- usuarios;
- fuentes de contexto;
- acciones permitidas;
- acciones prohibidas;
- criterios de escalamiento;
- trazabilidad.

## 8. Panel web

El panel web es una interfaz posible del SOE.

Puede incluir:

- busqueda de conocimiento;
- consulta con IA;
- acceso a procesos;
- dashboards;
- formularios;
- modulos operativos;
- herramientas internas;
- estado de automatizaciones.

El panel no necesariamente muestra todo ASM ni todo el modelo operativo. Debe
presentar lo que cada usuario necesita para operar mejor.

## 9. Gobernanza

La gobernanza define como se mantiene el SOE.

Preguntas clave:

- quien puede editar ASM?
- quien aprueba cambios?
- quien puede proponer mejoras?
- que puede modificar la IA?
- que requiere revision humana?
- como se versionan las decisiones?
- como se corrige informacion obsoleta?

Sin gobernanza, el SOE corre el riesgo de degradarse con el tiempo.

## 10. Evolucion continua

El SOE no termina con una entrega inicial.

Debe evolucionar a partir de:

- nuevos procesos;
- cambios de negocio;
- feedback de usuarios;
- metricas;
- incidentes;
- decisiones;
- nuevas herramientas;
- aprendizajes.

La evolucion continua convierte al SOE en una practica operativa, no en un
proyecto cerrado.

## Criterio de avance

Una implementacion SOE puede avanzar por ciclos:

```text
Elegir proceso critico
-> diagnosticar
-> documentar
-> modelar
-> mejorar
-> automatizar o construir herramienta
-> incorporar IA si aporta valor
-> gobernar
-> medir y evolucionar
```

Este ciclo permite empezar con alcance controlado y evitar una implementacion
demasiado grande desde el inicio.

