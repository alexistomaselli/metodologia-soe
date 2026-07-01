# Metodología SOE

Este repositorio es la **Metodología SOE**: el método para entender una empresa,
ordenarla y construirle y operarle su **Sistema Operativo Empresarial (SOE)**.

No es el SOE de ninguna empresa en particular. Es la IP del método. El SOE de
cada cliente —el entregable— vive en su propio repositorio (`<empresa>-soe`).

> **Definición canónica:** [publico/que-es-soe.md](./publico/que-es-soe.md)
> **Cómo aplicar todo, de punta a punta:** [metodo/guia.md](./metodo/guia.md)

## Las tres cosas que no hay que confundir

- **SOE** — la capa operativa que la empresa tiene y opera (su conocimiento,
  modelo operativo, herramientas, automatizaciones e IA). Es el artefacto, y es
  de la empresa.
- **Metodología SOE** — el método para construir y sostener ese SOE. Es la IP, y
  vive en este repositorio.
- **El servicio** — acompañamiento continuo que aplica la metodología como un
  área de sistemas y digitalización tercerizada, sostenida en el tiempo.

## El principio que ordena todo

> Antes de automatizar una empresa, hay que entenderla.
> Antes de construir software, hay que representar el negocio.
> Antes de incorporar IA, hay que darle contexto confiable.

## El entregable

Lo que le queda a cada empresa es un repositorio ancla `<empresa>-soe` cuyo
núcleo es el conocimiento (ASM) y que crece por capas según avanza el
acompañamiento. El piso (memoria organizacional) siempre se entrega; el techo
(modelo, herramientas, automatizaciones, IA) se construye según necesidad.

Detalle completo en [publico/que-es-soe.md](./publico/que-es-soe.md).

## ASM, el componente de conocimiento

**ASM (Agentic Shared Memory)** es el componente de conocimiento del SOE: memoria
organizacional en Markdown versionada en Git, consumible por personas y agentes
de IA. Es el piso garantizado del entregable.

El estándar ASM (patrón + plantilla + skills) es un toolkit reutilizable y vive
en su propio repositorio:
[agentic-shared-memory](https://github.com/alexistomaselli/agentic-shared-memory).

## Estructura de este repositorio

```text
metodologia-soe/
  publico/        # capa vendible: qué es SOE, filosofía, principios, componentes, valor, servicio
  metodo/         # capa interna: guía, proceso, modelo operativo, plantillas, arquitectura de repos
  skills/         # skills ejecutables para agentes (ej. soe-bootstrap)
```

Dos capas según audiencia:

- **`publico/`** — lo que puede leer un prospecto. Lenguaje de negocio, orientado
  a valor.
- **`metodo/`** — el cómo lo ejecuta el asesor. Proceso detallado, plantillas,
  criterios de decisión.

> El SOE de cada cliente **nunca** vive en este repositorio. Va en su propio
> `<empresa>-soe`.

## Estado actual

Etapa de definición de la metodología. La definición canónica ya está fijada en
[publico/que-es-soe.md](./publico/que-es-soe.md). La documentación está organizada
en las capas [publico/](./publico/) (qué y porqué) y [metodo/](./metodo/) (cómo).
