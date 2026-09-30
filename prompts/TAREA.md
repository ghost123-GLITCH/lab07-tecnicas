# Tarea: Mi prompt avanzado

## Tarea elegida
Diseñar las clases de un sistema de gestión de notas para una universidad.

## Version 1: prompt basico
```text
Diseña las clases de un sistema de notas para una universidad.
```
**Técnica agregada:** Ninguna, fue el punto de partida.
**Por que:** Quería ver qué tan genérica era la respuesta de la IA sin darle ninguna guía.
**Qué mejoro:** La IA propuso clases muy generales (Estudiante, Curso, Nota) sin contexto ni formato, y sin justificar por qué esas clases eran las adecuadas. Faltaba estructura y profundidad.

## Version 2
```text
Actua como arquitecto de software con experiencia en sistemas academicos. Diseña las clases de un sistema de gestion de notas para una universidad. Piensa paso a paso que entidades se necesitan y luego presenta las clases con sus atributos.
```
**Técnica agregada:** Role prompting (rol específico) y Chain of Thought ("piensa paso a paso").
**Por que:** La versión 1 fue demasiado general. Al darle un rol concreto, la IA puede adoptar el vocabulario técnico correcto; y al pedirle que piense paso a paso, obligo a que justifique sus decisiones en lugar de lanzar clases al azar.
**Qué mejoro:** La IA razonó qué entidades eran necesarias y justificó cada clase. El vocabulario fue mucho más técnico (relaciones, cardinalidad, responsabilidades). Sin embargo, la respuesta aún no seguía un formato uniforme y no incluía ejemplos de cómo debía verse cada clase.

## Version 3: prompt final
```text
<rol>Actua como arquitecto de software Java con experiencia en sistemas academicos universitarios.</rol>

<contexto>Sistema de gestion de notas para una universidad. Los estudiantes se inscriben en cursos, y cada curso tiene evaluaciones (parciales, trabajos, examenes finales) con un peso porcentual. El promedio final se calcula como suma ponderada de las notas.</contexto>

<tarea>Piensa paso a paso antes de responder:
1. Identifica las entidades principales del sistema.
2. Define la responsabilidad de cada clase.
3. Diseña las clases con sus atributos (nombre y tipo de dato).
4. Indica las relaciones entre clases (asociacion, herencia, etc.).</tarea>

<ejemplos>
Ejemplo del formato que quiero para cada clase:
Clase: Curso
- Responsabilidad: Representa un curso dictado en un semestre.
- Atributos: codigo (String), nombre (String), creditos (int).
</ejemplos>

<formato>Responde con una lista de clases. Para cada clase usa el formato del ejemplo. Al final agrega una seccion "Relaciones" describiendo como se conectan las clases.</formato>
```
**Técnica agregada:** Prompt estructurado (etiquetas), Descomposición (4 pasos numerados), Few-shot (ejemplo de formato) y Autocrítica implícita en la instrucción de pensar paso a paso.
**Por que:** La versión 2 mejoró el razonamiento, pero la respuesta no tenía un formato uniforme y era difícil comparar las clases. Al estructurar el prompt con etiquetas y agregar un ejemplo, me aseguro de que la IA responda siempre con el mismo estilo. Al descomponer la tarea en 4 pasos, controlo el orden del razonamiento.
**Qué mejoro:** La IA entregó una lista de clases con formato uniforme, justificó la responsabilidad de cada una, especificó tipos de dato y agregó una sección de relaciones entre clases. La respuesta fue mucho más completa y reutilizable.

## Tecnicas usadas en el prompt final
| Técnica | Parte del prompt donde se usa |
|---|---|
| Role prompting | `<rol>Actua como arquitecto de software Java...</rol>` |
| Chain of Thought | `<tarea>Piensa paso a paso antes de responder: 1. Identifica... 2. Define... 3. Diseña... 4. Indica...</tarea>` |
| Few-shot | `<ejemplos>Ejemplo del formato que quiero... Clase: Curso...</ejemplos>` |
| Prompt estructurado | Uso de etiquetas `<rol>`, `<contexto>`, `<tarea>`, `<ejemplos>`, `<formato>` |
| Descomposición | La tarea está dividida en 4 pasos numerados dentro de `<tarea>` |

## Evaluacion del resultado
| Criterio | Cumple (Sí / No) |
|---|---|
| ¿Identifica las entidades principales del sistema? | Sí |
| ¿Cada clase tiene responsabilidad y atributos con tipo de dato? | Sí |
| ¿Respeta el formato indicado en `<ejemplos>`? | Sí |
| ¿Incluye la sección de relaciones entre clases? | Sí |
| ¿Sigue el razonamiento paso a paso pedido en `<tarea>`? | Sí |

## Por que elegí estas tecnicas
Elegí estas técnicas porque la tarea de diseñar clases para un sistema universitario es lo suficientemente compleja como para necesitar estructura, pero no tanto como para requerir autocrítica completa. El **role prompting** me sirvió para que la IA adoptara el vocabulario de un arquitecto y no el de un programador principiante. La **descomposición** y el **chain of thought** me ayudaron a que la IA no saltara directo a las clases, sino que primero identificara entidades y responsabilidades, lo cual da un diseño más sólido. El **few-shot** fue clave para que todas las clases tuvieran el mismo formato y fueran fáciles de comparar. Finalmente, el **prompt estructurado** con etiquetas evitó que la IA mezclara las instrucciones y me dio control total sobre el orden de la respuesta. No usé autocrítica porque el diseño de clases, al ser una tarea exploratoria, no tiene una única respuesta correcta; una autocrítica habría sido menos útil que una buena estructura inicial.

## Enlace al repositorio
Este archivo forma parte del repositorio [lab07-tecnicas](https://github.com/ghost123-GLITCH/lab07-tecnicas).