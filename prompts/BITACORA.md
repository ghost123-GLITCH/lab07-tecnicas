# Bitacora de tecnicas avanzadas

Laboratorio 07: Tecnicas Avanzadas de Prompting.
Herramienta de IA usada: (escribe aqui cual usaste)

## Ejercicio 2: Zero-shot, one-shot y few-shot

## Ejercicio 3: Chain of Thought

## Ejercicio 4: Role prompting

## Ejercicio 5: Descomposicion

## Ejercicio 6: Prompt estructurado y autocritica

| Tipo | Aciertos (de 5) | Formato de la respuesta | Todas con el mismo formato (Si/No) |
|---|---|---|---|
| Zero-shot | 5 | Tabla con columnas (#, Comentario, Clasificación) | Sí |
| One-shot | 5 | Lista numerada con flecha (1. Comentario -> Clasificación) | Sí |
| Few-shot | 5 | Texto entre comillas, flecha y etiqueta ("Comentario" -> Clasificación) | Sí |


| Version | Vocabulario (sencillo/tecnico) | Usa ejemplos o codigo | A quien le sirve mas |
|---|---|---|---|
| A. Sin rol | Sencillo | Sí (ejemplos en Python, analogía de la caja) | A alguien que quiere una explicación general y rápida. |
| B. Rol docente | Sencillo | Sí (analogía "caja con etiqueta", código Python) | A estudiantes que nunca han programado. |
| C. Rol senior | Técnico | Sí (código Java, conceptos como tipo de dato y memoria) | A un compañero de trabajo o desarrollador con experiencia. |


| Qué revisar | Cumple (Sí / No) |
|---|---|
| ¿Tiene las 4 columnas pedidas? | Sí |
| ¿Incluye el bloqueo después de 3 intentos? | Sí |
| ¿Incluye casos con campos vacíos? | Sí |
| ¿Indica qué casos agregó en la autocrítica? | Sí |
| ¿Hay algún caso repetido o que no tenga sentido? | No |


```text
<rol>Actua como analista de pruebas de software.</rol>
<contexto>Login web con correo y contrasena. La cuenta se bloquea despues de 3 intentos fallidos.</contexto>
<tarea>Piensa paso a paso que puede fallar y escribe 6 casos de prueba.</tarea>
<formato>Tabla con las columnas: ID, escenario, datos de entrada, resultado esperado.</formato>

Revisa tu tabla: faltan casos limite como campos vacios, correo sin @ o contrasena con espacios? Agrega los que falten e indica cuales agregaste.
```