# Tarea: Mi prompt avanzado

## Tarea elegida

Generar casos de prueba para un módulo de registro de mantenimiento preventivo de vehículos. El objetivo es verificar el correcto funcionamiento del registro, considerando el mantenimiento cada 5,000 km, la validación de fechas, los datos obligatorios y la detección de registros duplicados.

## Version 1: prompt basico

**Prompt utilizado:**

```text
Genera casos de prueba para un módulo de registro de mantenimiento preventivo de vehículos.
```

**Resultado:** La IA generó 20 casos de prueba, incluyendo escenarios positivos, negativos y casos límite.

**Evaluación:** La respuesta fue completa, pero no se indicó un rol específico ni un formato detallado.

## Version 2: prompt con rol

**Técnica agregada:** Role prompting. Se indicó a la IA que actuara como analista QA especializado en flotas y mantenimiento automotriz.

**Prompt utilizado:**

```text
Actúa como analista QA especializado en sistemas de gestión de flotas vehiculares y mantenimiento automotriz.

Genera casos de prueba para un módulo de registro de mantenimiento preventivo de vehículos. Considera que el mantenimiento debe realizarse cada 5,000 km.

Incluye escenarios positivos, negativos y casos límite. Presta especial atención a la validación del kilometraje, fechas, datos obligatorios y registros duplicados.
```

**Resultado:** La IA generó 30 casos de prueba, considerando escenarios positivos, negativos y casos límite. También profundizó en las reglas de negocio del mantenimiento cada 5,000 km.

**¿Qué mejoró?:** La respuesta fue más específica porque se definió el rol de analista QA y se indicó el contexto automotriz. Además, se prestó mayor atención al kilometraje, las fechas, los campos obligatorios y los registros duplicados.

## Version 3: prompt final

**Técnicas utilizadas:** Role prompting, prompt estructurado, few-shot, descomposición y autocrítica.

**Prompt utilizado:**

```text
<rol>
Actúa como analista QA especializado en sistemas de gestión de flotas y mantenimiento automotriz.
</rol>

<contexto>
Se está desarrollando un módulo de registro de mantenimiento preventivo para una flota de vehículos.

Cada vehículo debe recibir mantenimiento cada 5,000 km. El sistema registra placa, kilometraje, fecha, tipo de mantenimiento, trabajos realizados, repuestos utilizados y responsable.
</contexto>

<reglas>
- El kilometraje no puede ser negativo ni menor al último registrado.
- No se permiten fechas futuras.
- Los campos obligatorios deben estar completos.
- Se deben detectar registros duplicados.
- El sistema debe identificar mantenimientos adelantados, oportunos y atrasados.
</reglas>

<tarea>
Desarrolla el trabajo en tres etapas:

1. Genera casos positivos, negativos y casos límite.
2. Organiza los casos por categoría y verifica que cubran las reglas de negocio.
3. Revisa los casos generados, identifica situaciones faltantes y agrega las pruebas necesarias.
</tarea>

<ejemplos>
"Kilometraje negativo" -> Rechazar el registro.
"Fecha futura" -> Mostrar mensaje de validación.
"Kilometraje superior al intervalo" -> Permitir el registro y generar una advertencia.
</ejemplos>

<formato>
Presenta una tabla con las columnas:
ID, categoría, escenario, datos de entrada y resultado esperado.

Al final incluye:
- Resumen de cantidad de casos.
- Reglas de negocio cubiertas.
- Casos adicionales encontrados durante la revisión.
- Observaciones y recomendaciones QA.
</formato>
```

**Resultado:** La IA generó 42 casos de prueba, agrupados por categorías. También revisó la cobertura de las reglas de negocio y agregó casos adicionales.

**¿Qué mejoró?:** La respuesta fue más completa y ordenada. Incluyó ejemplos para orientar el resultado y una revisión para encontrar situaciones que podían faltar. Al revisar la respuesta, también se identificaron algunos detalles que requieren validación manual, como una diferencia en el resumen de cantidades y un caso de kilometraje que no coincide con la regla indicada.

## Relación entre las técnicas utilizadas

| Parte del prompt | Técnica aplicada | ¿Para qué se utilizó? |
|---|---|---|
| Rol | Role prompting | Definir el perfil de analista QA. |
| Contexto, reglas y formato | Prompt estructurado | Organizar las instrucciones y condiciones del sistema. |
| Ejemplos | Few-shot | Mostrar ejemplos del resultado esperado. |
| Tarea en tres etapas | Descomposición | Dividir el trabajo en pasos ordenados. |
| Revisión de casos faltantes | Autocrítica | Identificar posibles omisiones y mejorar la respuesta. |

## Evaluación del resultado final

| Criterio de evaluación | Cumple (Sí / No) |
|---|---|
| ¿La respuesta incluye casos positivos, negativos y casos límite? | Sí |
| ¿Los casos están organizados por categorías? | Sí |
| ¿Se consideran las reglas de negocio indicadas? | Sí |
| ¿La IA identificó situaciones adicionales durante la revisión? | Sí |
| ¿El resumen de cantidades coincide con el detalle de los casos? | No |
| ¿Todos los casos respetan las reglas indicadas en el prompt? | No |

**Observación:** La respuesta fue amplia y permitió identificar diferentes situaciones para probar el módulo. Sin embargo, se encontraron diferencias en el resumen de cantidades y un caso relacionado con el kilometraje que debe revisarse. Por eso, es importante que una persona valide los resultados antes de utilizarlos.

## ¿Por qué elegí estas técnicas?

Elegí estas técnicas porque necesitaba obtener casos de prueba completos y ordenados para un módulo de mantenimiento vehicular. El role prompting permitió definir el perfil de analista QA; el prompt estructurado ayudó a organizar las instrucciones; el few-shot mostró ejemplos; la descomposición dividió el trabajo en etapas y la autocrítica permitió encontrar posibles casos faltantes.

No utilicé solamente un prompt básico porque podía generar una respuesta muy general. Tampoco consideré necesario aplicar todas las técnicas disponibles, ya que seleccioné las que aportaban mayor utilidad para este trabajo.
