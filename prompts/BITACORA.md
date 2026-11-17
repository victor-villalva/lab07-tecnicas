
# Bitacora de tecnicas avanzadas

Laboratorio 07: Tecnicas Avanzadas de Prompting.

Herramienta de IA usada: ChatGPT

## Ejercicio 2: Zero-shot, one-shot y few-shot


| Tipo | Aciertos (de 5) | Formato de la respuesta | Todas con el mismo formato (Si/No) |
|------|-----------------|-------------------------|------------------------------------|
| Zero-shot | 5 | Tabla con motivos y conclusión | No |
| One-shot | 5 | Tabla con comentario y clasificación | Si |
| Few-shot | 5 | Comentario -> clasificación | Si |

En los tres casos la IA clasificó correctamente los cinco comentarios. Sin embargo, con varios ejemplos mantuvo exactamente el formato solicitado.

El few-shot resulta útil porque permite obtener respuestas ordenadas y uniformes, facilitando su uso en trabajos posteriores.

## Ejercicio 3: Chain of Thought


| Tipo de prompt | Resultado | Muestra procedimiento | Correcto |
|---|---:|---|---|
| Directo | S/ 318.60 | No | Sí |
| Chain of Thought | S/ 318.60 | Sí | Sí |

Ambos prompts llegaron al resultado correcto. Sin embargo, al solicitar el desarrollo paso a paso, ChatGPT explicó cómo aplicó el descuento, calculó el IGV y obtuvo el precio final de las tres unidades.

Esta técnica facilita comprender y revisar los cálculos realizados por la IA.

## Ejercicio 4: Role prompting

| Version | Vocabulario (sencillo/tecnico) | Usa ejemplos o codigo | A quien le sirve mas |
|---|---|---|---|
| A - Sin rol | Sencillo | Sí | Principiantes |
| B - Profesor | Sencillo | Sí | Estudiantes que recién empiezan |
| C - Desarrollador Java senior | Técnico | Sí | Desarrolladores o compañeros de trabajo |

## Ejercicio 5: Descomposicion

**Consulta directa:** La IA propuso un sistema de inventario llamado TiendaTec, con gestión de productos, categorías, proveedores, control de stock, movimientos y reportes. También solicitó definir las tecnologías y el alcance del proyecto.

**Paso 1 - Requisitos:** La IA identificó cinco requisitos principales para el sistema de inventario: gestión de productos, control de inventario, gestión de ventas, gestión de usuarios y reportes y consultas.

**Paso 2 - Diseño de clases:** La IA propuso 10 clases para organizar el sistema TiendaTec. Indicó los atributos y tipos de datos de cada clase, además de recomendaciones sobre encapsulamiento, relaciones entre clases y uso de BigDecimal.

**Paso 3 - Código Java:** La IA generó la clase Producto con sus 11 atributos, un constructor y los métodos get y set. También explicó el encapsulamiento e incluyó un ejemplo de cómo crear y utilizar un objeto Producto desde la clase Main.

**Paso 4 - Revisión del código:** La IA revisó la clase Producto y propuso tres mejoras: utilizar BigDecimal para los precios, agregar validaciones en los métodos set e incorporar un constructor vacío. Estas mejoras buscan evitar errores y facilitar el mantenimiento del código.

**Comparación:** En la consulta directa, la IA presentó una propuesta general del sistema de inventario. Al dividir el trabajo en pasos, fue posible obtener primero los requisitos, luego el diseño de clases, el código Java y finalmente una revisión con mejoras concretas.

La descomposición permitió desarrollar la solución de manera más ordenada y comprender mejor cada etapa.

## Ejercicio 6: Prompt estructurado y autocritica

**Prompt básico:** Se solicitó generar casos de prueba para un módulo de Login. La IA presentó 15 casos generales, incluyendo pruebas positivas, negativas, validaciones y seguridad.

**Prompt estructurado:** Se indicó el rol de analista de pruebas, el contexto de un Login web con bloqueo después de tres intentos fallidos, la tarea de generar seis casos y el formato de tabla solicitado.

**Resultado:** La IA generó seis casos de prueba con las cuatro columnas solicitadas: ID, escenario, datos de entrada y resultado esperado.

**Autocrítica:** Se solicitó revisar la tabla e identificar casos límite faltantes. La IA agregó seis casos, llegando a un total de 12. Incluyó correos sin formato válido, contraseñas con espacios, campos individuales vacíos y reinicio del contador de intentos.

**Prompt estructurado:**

```text
<rol>Actua como analista de pruebas de software.</rol>

<contexto>Login web con correo y contrasena. La cuenta se bloquea despues de 3 intentos fallidos.</contexto>

<tarea>Piensa paso a paso que puede fallar y escribe 6 casos de prueba.</tarea>

<formato>Tabla con las columnas: ID, escenario, datos de entrada, resultado esperado.</formato>
```

**Prompt de autocrítica:**

```text
Revisa tu tabla: faltan casos limite como campos vacios, correo sin @ o contrasena con espacios? Agrega los que falten e indica cuales agregaste.
```

**Evaluación de la respuesta final:**

| Qué revisar | Cumple (Sí / No) |
|---|---|
| ¿Tiene las 4 columnas pedidas? | Sí |
| ¿Incluye el bloqueo después de 3 intentos? | Sí |
| ¿Incluye casos con campos vacíos? | Sí |
| ¿Indica qué casos agregó en la autocrítica? | Sí |
| ¿Hay algún caso repetido o que no tenga sentido? | No |

**Observación:** Los 12 casos de prueba permiten evaluar diferentes situaciones del inicio de sesión. No se identifican casos repetidos importantes y se incluyen validaciones adicionales para mejorar las pruebas del Login.