# Implementación técnica

> La tecnología responde a la metodología, no al revés. No toda empresa necesita
> el mismo stack ni el mismo grado de formalización desde el primer día.

## Stack posible

Una arquitectura de referencia puede incluir:

- **Git** como versionado de ASM y del conocimiento estructurado.
- **VPS o servidor propio** para sincronización e indexación.
- **Motor de indexación y recuperación de contexto** (QMD/RAG) para búsqueda
  semántica y consulta asistida.
- **Supabase** o base de datos equivalente para el estado operativo.
- **APIs** para conectar sistemas y servicios.
- **n8n** u otra herramienta para automatizaciones.
- **Panel web** para usuarios internos.
- **Modelos LLM** para consulta, asistencia y agentes especializados.

## Flujo de conocimiento (ASM)

```text
Repositorio Git (<empresa>-soe)
  -> Servidor / VPS
  -> Clonado local
  -> Motor de indexación (QMD/RAG)
  -> LLM
  -> Panel web
```

Cuando el repositorio cambia: se sincroniza, se reindexa y la IA empieza a
responder con la información nueva.

## Criterio de elección

El nivel de tecnología se decide según contexto, presupuesto y madurez de cada
empresa. Una misma metodología puede implementarse con más o menos stack.

Preguntas para decidir qué incorporar:

- ¿qué problema resuelve esta pieza?
- ¿la empresa puede operarla y mantenerla?
- ¿hay una opción más simple que alcance?
- ¿se integra con lo que ya usan?

---

_Pendiente de desarrollar: arquitecturas de referencia por tamaño de empresa,
guía del toolkit ASM, seguridad y permisos._
