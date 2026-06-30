# Plantilla de diagnóstico (Fase 0)

Guion y entregable de la Fase 0. Se usa en el primer trabajo con la empresa.
Parte de entender, no de proponer soluciones.

> **Salida de esta fase:** arranque del SOE (`knowledge/` sembrado) + un
> [roadmap](./plantilla-roadmap.md) con los frentes de trabajo y su tamaño.
> Adaptá las secciones a cada empresa: no todas aplican igual.

---

## Datos generales

- **Empresa:** `<nombre>`
- **Industria / modelo de negocio:** `<...>`
- **Tamaño (personas, sucursales, volumen):** `<...>`
- **Fecha del diagnóstico:** `<...>`
- **Pedido inicial del cliente (lo que ellos creen que quieren):** `<...>`

## Stakeholders y roles

| Persona | Rol | Qué hace | Cómo participa en el proyecto |
| --- | --- | --- | --- |
| `<...>` | `<...>` | `<...>` | `<...>` |

## Mapa de áreas y procesos

Listado de áreas y los procesos que ocurren en cada una. No hace falta detallarlos
acá; alcanza con nombrarlos para tener el panorama.

```text
Área <...>
  - proceso <...>
  - proceso <...>
```

## Procesos críticos

Los procesos donde se concentra el valor o el dolor. Para cada uno:

| Proceso | Quién lo ejecuta | Dolor / fricción actual | Frecuencia | Impacto si falla |
| --- | --- | --- | --- | --- |
| `<...>` | `<...>` | `<...>` | `<...>` | `<...>` |

## Herramientas y sistemas actuales

Qué usan hoy y cuánto les cuesta. **Los costos actuales son el ancla de precio**
para la propuesta posterior.

| Herramienta / sistema | Para qué la usan | Costo mensual | ¿Les resuelve? | ¿Integrada con el resto? |
| --- | --- | --- | --- | --- |
| `<...>` | `<...>` | `<...>` | sí / parcial / no | sí / no |

## Dónde se pierde el esfuerzo

- Trabajo manual y repetitivo: `<...>`
- Información duplicada o cargada dos veces: `<...>`
- Tiempo buscando o reconstruyendo información: `<...>`
- Retrabajo y errores frecuentes: `<...>`
- Tareas que dependen de una sola persona: `<...>`

## Información fragmentada

Dónde vive hoy el conocimiento (planillas, chats, mails, cabezas, sistemas) y qué
queda sin registrar.

- `<...>`

## Reglas tácitas del negocio

Reglas que se aplican por costumbre y no están escritas en ningún lado.

- `<...>`

## Riesgos y dependencias críticas

- `<...>`

## Oportunidades detectadas

Reencuadre: más allá del pedido inicial, qué más conviene trabajar.

| Oportunidad | Tipo (build / modelado / automatización / asesoría) | Valor que aporta | Esfuerzo aprox. |
| --- | --- | --- | --- |
| `<...>` | `<...>` | `<...>` | bajo / medio / alto |

## Quick wins

Lo de alto valor y bajo esfuerzo que se puede atacar primero.

- `<...>`

---

## Entregables del diagnóstico

- [ ] Mapa de procesos y áreas.
- [ ] Repo `<empresa>-soe` iniciado con `knowledge/` sembrado (ver
      [entregable-soe.md](../entregable-soe.md)).
- [ ] Documento de hallazgos (este).
- [ ] [Roadmap](./plantilla-roadmap.md) con frentes de trabajo priorizados.
- [ ] Propuesta del programa (retainer base + builds), derivada del roadmap.

## Guion de entrevista (referencia)

Preguntas base para conducir las conversaciones. Una por vez, dejando hablar.

1. ¿Qué vende o entrega la empresa? ¿Cómo gana plata?
2. ¿Quiénes participan en el día a día y qué hace cada uno?
3. ¿Cuáles son los procesos que más duelen o más importan?
4. ¿Qué herramientas usan y cuánto pagan por ellas? ¿Les resuelven?
5. ¿Dónde sienten que pierden más tiempo o se equivocan más?
6. ¿Qué información está desparramada o se pierde?
7. ¿Qué tareas dependen de una sola persona?
8. ¿Qué les gustaría que pasara y hoy no pasa?
