# Bitacora de tecnicas avanzadas

Laboratorio 07: Tecnicas Avanzadas de Prompting. Herramienta de IA usada: (Chat gpt)

##	Ejercicio	2:	Zero-shot, one-shot y few-shot

| Tipo | Aciertos (de 5) | Formato de la respuesta | Todas con el mismo formato (Sí/No) |
|------|------------------|-------------------------|------------------------------------|
| Zero-shot | 5/5 | Tabla con comentario y clasificación, más un resumen | No |
| One-shot | 5/5 | Lista numerada con clasificación y comentario | No |
| Few-shot | 5/5 | Comentario -> clasificación | Sí |

##	Ejercicio	3:	Chain of Thought

| Pedido | Respuesta de la IA | Muestra los pasos (Sí/No) | Correcta (Sí/No) |
|--------|---------------------|----------------------------|-------------------|
| Directo | 318.60 | No | Sí |
| Paso a paso | S/ 318.60 | Sí | Sí |

##	Ejercicio	4:	Role prompting
| Version | Vocabulario (sencillo/técnico) | Usa ejemplos o código | ¿A quién le sirve más? |
|---------|--------------------------------|------------------------|-------------------------|
| A. Sin rol | Sencillo | Sí | Personas que están aprendiendo programación |
| B. Rol docente | Muy sencillo y didáctico | Sí | Estudiantes que nunca han programado |
| C. Rol senior | Técnico | Sí | Programadores o desarrolladores con experiencia |
##	Ejercicio	5:	Descomposicion
| Paso | Qué entregó la IA                                                 | Comparación con el pedido de una sola vez     |
| ---- | ----------------------------------------------------------------- | --------------------------------------------- |
| 1    | 5 requisitos principales del sistema.                             | El pedido de una sola vez fue más general.    |
| 2    | 5 clases con sus atributos y tipos de datos.                      | El pedido de una sola vez no definió clases.  |
| 3    | Código de la clase `Producto` con constructor, getters y setters. | El pedido de una sola vez no entregó código.  |
| 4    | 3 mejoras para la clase `Producto`.                               | El pedido de una sola vez no incluyó mejoras. |

##	Ejercicio	6:	Prompt estructurado y autocritica
| Qué revisar                                      | Cumple            |
| ------------------------------------------------ | ----------------- |
| ¿Tiene las 4 columnas pedidas?                   | Sí                |
| ¿Incluye el bloqueo después de 3 intentos?       | Sí                |
| ¿Incluye casos con campos vacíos?                | Sí                |
| ¿Indica qué casos agregó en la autocrítica?      | Sí, TC-07 a TC-11 |
| ¿Hay algún caso repetido o que no tenga sentido? | No                |

```text
1. Prompt estructurado

<rol>Actúa como analista de pruebas de software.</rol>

<contexto>Login web con correo y contraseña. La cuenta se bloquea después de 3 intentos fallidos.</contexto>

<tarea>Piensa paso a paso qué puede fallar y escribe 6 casos de prueba.</tarea>

<formato>Tabla con las columnas: ID, escenario, datos de entrada, resultado esperado.</formato>

2. Pedir autocrítica

Revisa tu tabla: ¿faltan casos límite como campos vacíos, correo sin @ o contraseña con espacios? Agrega los que falten e indica cuáles agregaste.
```