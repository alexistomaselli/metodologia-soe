# Componentes SOE

El SOE es una metodologia. Sus componentes son las piezas que permiten llevar la
metodologia a la practica.

Un error posible seria confundir una pieza con el todo. ASM no es todo el SOE.
El panel web no es todo el SOE. El modelo operativo no es todo el SOE. La IA no
es todo el SOE.

Cada componente cumple una funcion distinta dentro de una arquitectura
metodologica comun.

## Mapa general

```text
SOE metodologia
  -> diagnostico
  -> ASM
  -> modelo operativo
  -> herramientas
  -> automatizaciones
  -> APIs e integraciones
  -> IA y agentes
  -> panel web
  -> gobernanza
  -> evolucion continua
```

## 1. Diagnostico

El diagnostico es la entrada de la metodologia.

Su funcion es entender la empresa antes de proponer soluciones. Permite detectar
procesos criticos, herramientas existentes, problemas, reglas tacitas,
oportunidades, dependencias y riesgos.

### Responsabilidades

- relevar como opera la empresa;
- identificar areas, roles y procesos;
- detectar informacion fragmentada;
- reconocer dolores operativos;
- mapear herramientas existentes;
- encontrar oportunidades de mejora;
- definir prioridades iniciales.

### No deberia

- asumir que todo problema se resuelve con software;
- automatizar antes de entender;
- documentar solo desde entrevistas sin mirar ejemplos reales;
- imponer una solucion generica sin contexto.

## 2. ASM

ASM (Agentic Shared Memory) es la memoria documental del SOE.

Su funcion es guardar conocimiento organizacional en una estructura versionada,
legible por humanos y utilizable como contexto para agentes de IA.

ASM puede contener procesos, reglas, decisiones, bitacoras, glosarios,
arquitectura, politicas, estandares, aprendizajes y documentacion funcional o
tecnica.

### Responsabilidades

- conservar conocimiento explicito;
- versionar cambios;
- registrar decisiones;
- documentar procesos y reglas;
- sostener una bitacora de evolucion;
- servir como contexto confiable para IA;
- facilitar continuidad operativa.

### No deberia

- reemplazar una base de datos operativa;
- funcionar como CRM;
- editarse libremente sin gobernanza;
- ser el unico lugar donde vive el estado actual de cada operacion;
- recibir cambios automaticos de IA sin revision.

### Toolkit

El estandar ASM (patron, plantilla y skills) es un toolkit reutilizable y vive en
su propio repositorio:
[agentic-shared-memory](https://github.com/alexistomaselli/agentic-shared-memory).
En el SOE de cada empresa, ASM se materializa como la carpeta `knowledge/` dentro
de `<empresa>-soe`.

## 3. Modelo operativo

El modelo operativo representa como funciona la empresa, un area o un proceso.

No es solamente un cursograma. Puede incluir cursogramas, pero tambien roles,
entidades, estados, reglas, eventos, sistemas, datos, automatizaciones posibles
y puntos de intervencion de IA.

### Responsabilidades

- estructurar el funcionamiento del negocio;
- conectar procesos con roles y entidades;
- explicitar reglas y estados;
- identificar eventos relevantes;
- mostrar que sistemas participan;
- servir como base para software, APIs, automatizaciones e IA.

### No deberia

- convertirse en burocracia inutil;
- describir procesos sin reglas ni entidades;
- quedarse solo en una narracion;
- reemplazar la documentacion explicativa de ASM;
- intentar modelar toda la empresa antes de empezar por procesos concretos.

Documento relacionado:

- [Modelo operativo](../metodo/modelo-operativo.md)

## 4. Herramientas

Las herramientas son piezas de software que permiten operar parte del negocio.

Pueden ser desarrollos propios, sistemas existentes, formularios, dashboards,
CRMs, paneles administrativos, modulos internos o aplicaciones externas
integradas.

### Responsabilidades

- ejecutar tareas operativas;
- registrar datos;
- facilitar trabajo de usuarios;
- aplicar reglas del negocio;
- exponer vistas utiles;
- reducir friccion;
- conectar procesos con datos reales.

### No deberian

- construirse antes de entender el proceso;
- duplicar herramientas existentes sin necesidad;
- ocultar reglas de negocio que deberian estar documentadas;
- depender de una sola persona para ser entendidas;
- convertirse en el unico lugar donde se explica la operacion.

## 5. Automatizaciones

Las automatizaciones ejecutan acciones a partir de eventos, condiciones y reglas.

Pueden enviar mensajes, crear tareas, sincronizar datos, actualizar estados,
generar documentos, avisar a usuarios o conectar sistemas.

### Responsabilidades

- ejecutar tareas repetibles;
- reducir trabajo manual;
- conectar sistemas;
- responder a eventos;
- aplicar reglas simples;
- dejar trazabilidad;
- escalar a humanos cuando algo falla.

### No deberian

- operar sin evento o condicion clara;
- ocultar errores;
- modificar informacion critica sin control;
- reemplazar decisiones que requieren criterio humano;
- crecer sin documentacion ni monitoreo.

## 6. APIs e integraciones

Las APIs e integraciones conectan el SOE con herramientas internas y externas.

Permiten que datos, eventos y acciones circulen entre sistemas sin depender de
copias manuales o procesos informales.

### Responsabilidades

- exponer datos o acciones de forma controlada;
- conectar sistemas existentes;
- sincronizar informacion;
- permitir automatizaciones;
- alimentar paneles o agentes;
- reducir duplicacion manual.

### No deberian

- exponer datos sin permisos;
- mezclar reglas de negocio sin documentarlas;
- crear dependencias fragiles sin monitoreo;
- asumir que todos los sistemas son fuente de verdad;
- reemplazar la gobernanza de datos.

## 7. IA y agentes

La IA es una capa de asistencia, consulta, analisis o ejecucion controlada.

Los agentes de IA pueden ayudar a responder preguntas, explicar procesos,
detectar inconsistencias, generar resumenes, asistir usuarios o ejecutar acciones
permitidas.

### Responsabilidades

- usar ASM y el modelo operativo como contexto;
- asistir usuarios;
- recuperar conocimiento;
- sugerir mejoras;
- detectar inconsistencias;
- operar bajo permisos y limites;
- dejar trazabilidad cuando interviene.

### No deberian

- inventar reglas no documentadas;
- modificar ASM automaticamente;
- ejecutar acciones sensibles sin permiso;
- operar sin fuentes claras;
- reemplazar la responsabilidad humana.

## 8. Panel web

El panel web es una interfaz de acceso al SOE.

No necesariamente contiene todo el SOE. Su funcion es presentar informacion,
herramientas, consultas y acciones de manera util para cada usuario.

### Responsabilidades

- dar acceso a conocimiento;
- permitir consulta con IA;
- mostrar dashboards;
- ofrecer formularios y herramientas;
- exponer modulos operativos;
- adaptar vistas por rol;
- conectar usuarios con procesos.

### No deberia

- ser entendido como el SOE completo;
- mostrar toda la documentacion sin criterio;
- mezclar permisos;
- ocultar la fuente de la informacion;
- crecer como pantalla gigante sin metodologia detras.

## 9. Gobernanza

La gobernanza define como se mantiene confiable el SOE.

Incluye permisos, flujos de aprobacion, criterios de edicion, versionado,
responsabilidades, revision de contenido, control de automatizaciones y limites
para IA.

### Responsabilidades

- definir quien puede leer, editar o aprobar;
- mantener calidad documental;
- evitar cambios descontrolados;
- revisar reglas y procesos;
- controlar permisos de IA;
- asegurar trazabilidad;
- sostener la evolucion del SOE.

### No deberia

- ser una capa burocratica que bloquee todo;
- quedar implicita;
- depender solo del consultor;
- permitir que cualquier usuario modifique fuentes de verdad;
- ignorar informacion obsoleta.

## 10. Evolucion continua

La evolucion continua convierte al SOE en una practica viva.

La empresa cambia y el SOE debe cambiar con ella. Nuevos procesos, herramientas,
personas, problemas, reglas y aprendizajes deben incorporarse de manera
controlada.

### Responsabilidades

- registrar cambios;
- actualizar ASM;
- ajustar el modelo operativo;
- mejorar herramientas;
- revisar automatizaciones;
- medir resultados;
- incorporar aprendizajes;
- detectar obsolescencia.

### No deberia

- tratar la implementacion como una entrega final;
- dejar documentacion congelada;
- ignorar feedback operativo;
- acumular reglas viejas;
- permitir que herramientas y procesos vuelvan a separarse.

## Relaciones entre componentes

Los componentes no funcionan aislados.

```text
Diagnostico
  -> detecta procesos, problemas y oportunidades

ASM
  -> documenta conocimiento, decisiones y reglas

Modelo operativo
  -> estructura roles, entidades, estados, procesos y eventos

Herramientas
  -> ejecutan partes del modelo operativo

Automatizaciones
  -> reaccionan a eventos y aplican reglas

APIs e integraciones
  -> conectan sistemas y datos

IA y agentes
  -> consultan contexto, asisten y actuan bajo limites

Panel web
  -> presenta conocimiento, herramientas y acciones a usuarios

Gobernanza
  -> cuida permisos, calidad, aprobacion y trazabilidad

Evolucion continua
  -> mantiene todo actualizado con la empresa
```

## Criterio de diseno

Cuando se agregue una pieza al SOE conviene preguntar:

- que problema resuelve?
- a que proceso pertenece?
- que roles la usan?
- que informacion necesita?
- que reglas aplica?
- que eventos genera?
- que fuente de verdad utiliza?
- que permisos requiere?
- como se documenta en ASM?
- como se mantiene en el tiempo?

Si una pieza no puede responder esas preguntas, probablemente todavia no esta
suficientemente integrada a la metodologia.

