# Detección de Fraude en Transacciones Móviles

## Problema de Negocio

La urgencia por detectar fraudes en transacciones móviles de dinero ha llevado a una empresa del segmento Fintech a buscar soluciones innovadoras. Este proyecto desarrolla un modelo de machine learning para distinguir de manera precisa entre transacciones legítimas y fraudulentas, estableciendo así un estándar de seguridad en el sector financiero móvil global.

## Tareas Principales

1. **Preprocesamiento de Datos:** Limpieza de datos, manejo de valores faltantes, codificación de variables categóricas y normalización/escalado de datos.

2. **Exploración de Datos:** Análisis y comprensión del conjunto de datos, identificación de variables clave, visualizaciones para entender las relaciones entre variables y selección de características relevantes.

3. **Construcción de Modelos:** Experimentación con algoritmos de machine learning como Regresión Logística, Árboles de Decisión, Random Forest, Naive Bayes, entre otros.

4. **Evaluación y Selección del Modelo:** Evaluación de modelos utilizando métricas como precisión, recall, área bajo la curva ROC, y F1-score. Selección del modelo con el mejor rendimiento para la detección de transacciones bancarias fraudulentas.

## Dataset

El conjunto de datos utilizado es una simulación de transacciones de dinero móvil basada en una muestra de transacciones reales. Está disponible en Kaggle: [PaySim1 Dataset](https://www.kaggle.com/datasets/ealaxi/paysim1)

### Características principales del dataset:

- **step:** Unidad de tiempo (1 paso = 1 hora)
- **type:** Tipo de transacción (CASH-IN, CASH-OUT, DEBIT, PAYMENT, TRANSFER)
- **amount:** Monto de la transacción
- **nameOrig:** Cliente que inicia la transacción
- **nameDest:** Cliente destinatario de la transacción
- **isFraud:** Indicador de transacción fraudulenta
- **isFlaggedFraud:** Indicador de intento de transferencia masiva ilegal

## Análisis Exploratorio de Datos

### Distribución del Fraude
![image](https://github.com/user-attachments/assets/c4545b4b-f1f6-4e19-af9b-93418410d3cf)
![image](https://github.com/user-attachments/assets/698c9965-fd74-4e86-8274-c7777ea7d7ab)
![image](https://github.com/user-attachments/assets/2302017e-7a49-4af1-aa6b-93a68d95806a)

### Fraude por Hora del Día
![image](https://github.com/user-attachments/assets/82367361-4417-4322-a621-70b2ef881a58)
![image](https://github.com/user-attachments/assets/92af0e10-a0dd-4759-bdd8-9b23699303a9)
![image](https://github.com/user-attachments/assets/427c6eb1-5fc4-4fa6-8fb7-477c89f880ba)

## Modelos y Resultados

Se implementaron tres modelos principales:
1. Random Forest Classifier
2. XGBoost
3. Red Neuronal (TensorFlow)

### Comparación de Métricas
![image](https://github.com/user-attachments/assets/b3d42175-718e-4c54-83fe-ac5614ce9e6a)

## Conclusiones

[Añadir conclusiones principales del análisis y modelado]

## Próximos Pasos

- Refinamiento del modelo seleccionado
- Implementación en producción
- Monitoreo continuo y actualización del modelo

## Cómo Usar

Para seleccionar el mejor modelo de clasificación para la detección de fraude financiero, analizaremos las métricas de desempeño: Accuracy, Precision, Recall, F1 y AUC. Cada métrica tiene su importancia, especialmente en el contexto de la detección de fraude. A continuación se presenta un análisis detallado de cada métrica y cómo influye en la selección del mejor modelo.

Para seleccionar el mejor modelo de clasificación para la detección de fraude financiero, analizaremos las métricas de desempeño: Accuracy, Precision, Recall, F1 y AUC. Cada métrica tiene su importancia, especialmente en el contexto de la detección de fraude. A continuación se presenta un análisis detallado de cada métrica y cómo influye en la selección del mejor modelo.

### Métricas y su Importancia en la Detección de Fraude Financiero

1. **Accuracy (Exactitud):**
   - **Definición:** Proporción de predicciones correctas sobre el total de casos.
   - **Importancia:** En problemas de fraude, la exactitud puede ser engañosa si hay un desequilibrio en las clases (fraude vs. no fraude). Un modelo que siempre predice "no fraude" puede tener una alta exactitud si los casos de fraude son raros. En este dataset, con 0.3% de casos de fraude, es prácticamente inútil como criterio de selección.

2. **Precision (Precisión):**
   - **Definición:** Proporción de verdaderos positivos sobre el total de positivos predichos.
   - **Importancia:** Es crucial cuando el costo de un falso positivo es alto. En fraude financiero, una baja precisión significaría muchos falsos positivos, lo que podría resultar en la investigación innecesaria de transacciones legítimas.

3. **Recall (Sensibilidad o Tasa de Detección):**
   - **Definición:** Proporción de verdaderos positivos sobre el total de positivos reales.
   - **Importancia:** Es vital cuando el costo de un falso negativo es alto. En fraude financiero, una baja sensibilidad significaría muchos casos de fraude no detectados, lo cual es altamente indeseable.

4. **F1 Score:**
   - **Definición:** Media armónica de la precisión y la sensibilidad.
   - **Importancia:** Proporciona un equilibrio entre precisión y sensibilidad, útil cuando se necesita un compromiso entre ambos. Ojo: calculado sobre un único umbral fijo (0.5), puede no reflejar el verdadero potencial del modelo si ese umbral no está calibrado.

5. **AUC (Área bajo la Curva ROC):**
   - **Definición:** Medida del rendimiento del modelo a través de todos los umbrales posibles.
   - **Importancia:** Refleja la capacidad del modelo para diferenciar entre las clases, independientemente del umbral elegido. Es el criterio más robusto para comparar modelos antes de decidir un punto de corte operativo.

### Resultados de las Métricas por Modelo (umbral de decisión 0.5)

| Modelo         | Accuracy | Precision | Recall | F1     | AUC    |
|----------------|----------|-----------|--------|--------|--------|
| **RandomForest** | 1.00     | 0.53      | 0.52   | 0.53   | 0.76   |
| **TensorFlow**    | 0.9967   | 0.4321    | 0.3769 | 0.4026 | 0.9214 |
| **XGBoost**       | 0.9772   | 0.0890    | 0.7242 | 0.1585 | 0.9438 |

### Análisis Comparativo

1. **RandomForest:**
   - Con el umbral por defecto (0.5) muestra el F1 más alto de los tres (0.53), producto de una precisión y recall relativamente equilibrados en ese punto.
   - Sin embargo, su **AUC (0.76) es notablemente inferior** al de XGBoost y TensorFlow (~0.92-0.94). Esto indica que su capacidad para separar fraude de no-fraude a través de distintos umbrales es mucho más débil — el buen F1 en 0.5 es un resultado puntual de ese umbral específico, no evidencia de un modelo superior en general.
   - Solo detecta 842 de 1621 fraudes reales (recall 0.52), dejando pasar 779 casos.

2. **TensorFlow:**
   - AUC alto (0.9214), buena capacidad de discriminación general.
   - Con el umbral por defecto, recall bajo (0.3769): deja sin detectar 1010 de 1621 fraudes.
   - Precision razonable (0.4321) en ese mismo punto.

3. **XGBoost:**
   - **AUC más alto de los tres (0.9438)** — el modelo con mejor capacidad de separación entre clases.
   - Con el umbral por defecto, recall muy alto (0.7242): detecta 1174 de 1621 fraudes, el mejor de los tres en ese aspecto, aunque a costa de mucha precisión (0.089, con 12023 falsas alarmas).
   - Al ajustar el umbral (análisis de curva precision-recall realizado previamente), alcanza el mejor F1 óptimo (0.4967) y la mejor precisión al recall objetivo del 80% (0.0415) entre los modelos comparados.

### Selección del Mejor Modelo

El AUC es el criterio más confiable acá porque no depende de un umbral fijo — y en fraude, el umbral final se ajusta según la capacidad operativa de revisión del negocio, no queda fijo en 0.5. Bajo ese criterio:

- **XGBoost** tiene el AUC más alto (0.9438) y, tras el análisis de curva precision-recall, ofrece el mejor equilibrio ajustable entre detección de fraude y falsas alarmas en toda la curva, no solo en un punto.
- **TensorFlow** queda segundo, con AUC 0.9214 y una curva PR consistentemente por debajo de la de XGBoost.
- **RandomForest**, pese al F1 aparentemente favorable en el umbral 0.5, tiene el AUC más bajo (0.76) de los tres, lo que sugiere menor capacidad real de discriminación y menos margen para mejorar ajustando el umbral.

### Conclusión

**XGBoost** es el modelo más adecuado para la detección de fraude financiero en este análisis, no RandomForest. Su AUC superior (0.9438) confirma la mejor capacidad de discriminación entre clases a través de todos los umbrales, y el análisis de curva precision-recall mostró que, ajustando el umbral de decisión, XGBoost logra el mejor F1 óptimo (0.4967) y la mejor precisión al recall objetivo del 80% (0.0415) entre los modelos evaluados. RandomForest, pese a un F1 favorable en el umbral por defecto, mostró el AUC más bajo (0.76), indicando una capacidad de separación de clases considerablemente más débil.

### Recomendación

Se recomienda implementar **XGBoost** como modelo principal para la detección de fraude financiero, ajustando el umbral de decisión según la capacidad operativa de revisión manual del negocio (por ejemplo, en el rango 0.6-0.7 para un balance recall/precision razonable, o más bajo si se prioriza capturar más fraude a costa de más falsas alarmas). Se sugiere validar además el desempeño de LightGBM con sus métricas completas al umbral 0.5 antes de descartarlo, dado que su curva precision-recall se mostró muy cercana a la de XGBoost.

## Contribuciones

Las contribuciones son bienvenidas. Por favor, abra un issue primero para discutir lo que le gustaría cambiar.

## Licencia

Copyright - 2024 - Julio Alberto Lazarte Todos los derechos reservados.
