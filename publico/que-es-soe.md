# Qué es SOE

> Documento piedra angular. Define con precisión qué es SOE, qué es la
> Metodología SOE, qué servicio se ofrece y qué entregable le queda a la empresa.
> Todo el resto del repositorio deriva de estas definiciones.

## En una frase

**SOE (Sistema Operativo Empresarial)** es la capa operativa que una empresa
termina teniendo y haciendo crecer: su conocimiento, su modelo operativo, sus
herramientas, sus automatizaciones y su IA, gobernados como una sola fuente de
verdad.

Igual que un sistema operativo coordina recursos, memoria, procesos y permisos,
el SOE coordina lo mismo aplicado al negocio: personas, procesos, reglas, datos,
herramientas y decisiones.

## Tres conceptos que no hay que confundir

La palabra "SOE" se usaba para tres cosas distintas. Separarlas es la base de
toda la metodología.

| Concepto | Qué es | De quién es | Dónde vive |
| --- | --- | --- | --- |
| **SOE** | El sistema operativo que la empresa tiene y opera (el artefacto) | De la empresa cliente | Un repo por cliente: `<empresa>-soe` |
| **Metodología SOE** | El método para entender una empresa, ordenarla y construirle y operarle su SOE | Del asesor (IP) | Este repositorio |
| **El servicio** | Acompañamiento continuo que aplica la Metodología SOE como área tercerizada | La relación comercial | Deriva de este repositorio |

En corto:

- **SOE** es el *qué tiene* la empresa.
- **Metodología SOE** es el *cómo se construye y se sostiene*.
- **El servicio** es el *cómo se contrata*: un área de sistemas y digitalización
  tercerizada, sostenida en el tiempo.

## El principio que ordena todo

> Antes de automatizar una empresa, hay que entenderla.
> Antes de construir software, hay que representar el negocio.
> Antes de incorporar IA, hay que darle contexto confiable.

El SOE no empieza eligiendo tecnología. Empieza mirando la empresa como un
sistema y construyendo una representación viva de cómo funciona. La tecnología es
consecuencia de esa comprensión, no al revés.

## El entregable: el SOE de la empresa

Lo que le queda a cada empresa es un **repositorio ancla** llamado
`<empresa>-soe`. Su núcleo es el conocimiento (ASM) y crece por capas a medida
que avanza el acompañamiento.

```text
acme-soe/                 # el SOE de la empresa (lo que les queda)
  README.md               # portada: qué es este SOE y cómo navegarlo
  knowledge/              # ASM: la memoria organizacional (el piso garantizado)
    current_state.md
    foundations/          # reglas de negocio core y modelo
    decisions/            # ADRs: el porqué de las decisiones
    processes/            # SOPs: cómo opera la empresa
    live/                 # bitácora viva
  model/                  # modelo operativo estructurado (entidades, estados, reglas)
  systems/                # inventario de herramientas + enlaces a sus repos de código
  automations/            # qué se automatiza, dónde corre y con qué reglas
  governance/             # roles, permisos y flujos de aprobación
```

Dos ideas clave de este entregable:

1. **El piso siempre se entrega; el techo se construye según necesidad.** Un
   primer contrato puede llenar solo `knowledge/`. Las demás capas se pueblan a
   medida que la relación avanza. El repo nunca está "terminado": crece con la
   empresa. Eso *es* el modelo de área tercerizada.
2. **El cliente se queda con un activo vivo, versionado y portable**, no con
   dependencia del asesor. Las apps de software reales viven en sus propios
   repos; `systems/` las inventaría y enlaza. El SOE es el índice vivo de todo lo
   que la empresa tiene.

## Dónde encaja ASM

**ASM (Agentic Shared Memory)** es el componente de conocimiento del SOE: la
memoria organizacional en Markdown versionada en Git, consumible tanto por
personas como por agentes de IA.

ASM es a SOE lo que el sistema de archivos es a un sistema operativo: la pieza
fundacional, pero no todo el sistema. Es el **piso garantizado** del entregable y
vive en `knowledge/`.

ASM aparece en tres niveles que no hay que confundir:

| Nivel | Qué es | Ejemplo |
| --- | --- | --- |
| Estándar / patrón | La definición de ASM + plantilla + skills | repo `agentic-shared-memory` |
| Instancia / artefacto | El ASM real de una empresa | `acme-soe/knowledge/` |
| — | — | — |

El estándar es IP del asesor (un toolkit reutilizable). La instancia es del
cliente (parte de su entregable).

## Qué NO es SOE

- **No es solo software.** Es una metodología; la tecnología es una consecuencia.
- **No es solo documentación.** ASM es su memoria, pero el SOE completo incluye
  modelo operativo, herramientas, automatizaciones, IA y gobernanza.
- **No es un ERP ni un CRM.** No reemplaza sistemas de gestión; los representa,
  integra o complementa.
- **No es un proyecto con entrega final.** Es una capa que se opera y evoluciona
  de forma continua.
