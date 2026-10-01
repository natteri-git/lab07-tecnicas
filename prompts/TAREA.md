# Tarea: Diseño e Iteración de Prompt Avanzado

**Tema seleccionado:** Generación de casos de prueba para un módulo de registro de usuarios.

---

## Iteraciones del Prompt

### Versión 1 (Básico)
```text
Genera casos de prueba para un formulario de registro de usuario que pide nombre, correo y contraseña.
```
- **Análisis:** La respuesta es muy genérica. Devuelve pocos casos de prueba, sin una estructura definida y sin analizar escenarios límite ni errores comunes.

## Versión 2
```text 
Actúa como un Analista QA de software.
Diseña casos de prueba para un formulario de registro de usuario con los campos: Nombre, Correo y Contraseña.

Entrega los resultados en una tabla con las columnas: ID, Tipo de Caso, Descripción y Resultado Esperado.
```

- **Técnicas agregadas:** Role Prompting + Prompt Estructurado.
- **Por qué:** Para darle un contexto técnico a la IA y obligarla a responder con una estructura ordenada de tabla.
- **Qué mejoró:** El formato es legible y las descripciones son más claras, pero aún faltan casos de borde o validaciones más estrictas.
## Versión 3 (prompt final)
```text
Actúa como un QA Test Engineer enfocado en la validación de interfaces y seguridad de entradas.

Tu tarea es diseñar un conjunto completo de casos de prueba para un formulario de registro de usuario que solicita: Nombre, Correo Electrónico y Contraseña.

Antes de dar la respuesta final, analiza la tarea paso a paso:
1. Identifica los campos y sus reglas comunes (longitudes, caracteres permitidos, formatos).
2. Clasifica los casos en: Positivos, Negativos y Casos Límite (Edge Cases).
3. Revisa si hay vulnerabilidades básicas como inyecciones o campos vacíos.

Estructura la respuesta en una tabla Markdown como en este ejemplo:

| ID | Tipo | Caso de Prueba | Entrada de Datos | Resultado Esperado |
|---|---|---|---|---|
| TC01 | Positivo | Registro exitoso | Nombre: "Ana", Correo: "ana@mail.com", Pass: "Abc12345!" | Registro correcto y mensaje de confirmación. |

Genera al menos 6 casos de prueba siguiendo este formato.
```
- **Técnicas agregadas:** Chain of Thought (CoT) + Few-Shot.
- **Por qué:** Para guiar el razonamiento de la IA antes de responder y asegurarnos de que mantenga exactamente el formato deseado mediante un ejemplo.
- **Qué mejoró:** La IA genera un análisis completo con escenarios reales (caracteres especiales, campos vacíos, correos inválidos) y respeta estrictamente el formato de tabla.

## Técnicas usadas en el prompt final

| Técnica | Fragmento / Aplicación en el Prompt |
| --- | --- |
| **Role Prompting** | Actúa como un QA Test Engineer enfocado en la validación de interfaces y seguridad de entradas. |
| **Chain of Thought (CoT)** | Antes de dar la respuesta final, analiza la tarea paso a paso: 1. Identifica... 2. Clasifica... 3. Revisa... |
| **Few-Shot** | Estructura la respuesta en una tabla Markdown como en este ejemplo: ID, Tipo, Caso de Prueba, Entrada de Datos, Resultado Esperado. |
| **Prompt Estructurado** | Uso de listas numeradas, delimitación clara de variables de entrada y formato de salida especificado. |

## Evaluación del Resultado

| Criterio | Cumple (Sí/No) | Observación |
| --- | --- | --- |
| ¿Define un rol específico que no sea "experto"? | Sí | QA Test Engineer enfocado en validación de interfaces y seguridad. |
| ¿Aplica al menos tres técnicas de prompting? | Sí | Role Prompting, Chain of Thought (CoT) y Few-Shot. |
| ¿El formato de salida está definido y se respeta? | Sí | Se especifica una tabla Markdown con columnas exactas. |
| ¿Muestra la evolución del prompt en 3 versiones? | Sí | Se incluye v1, v2 y v3 detallando cambios y mejoras. |

## Por qué elegí estas técnicas

Elegí combinar **Role Prompting**, **Chain of Thought (CoT)** y **Few-Shot** porque en el testing de software es fundamental la precisión y la cobertura de casos. El *Role Prompting* enfoca a la IA en la perspectiva de un analista QA preocupado por la seguridad y la validación de datos. La *Cadena de Pensamiento (CoT)* fuerza a la IA a analizar las reglas de negocio y los campos paso a paso antes de responder, evitando que pase por alto escenarios límite (*edge cases*). Finalmente, *Few-Shot* garantiza que el resultado mantenga exactamente el formato de tabla esperado listo para la documentación.