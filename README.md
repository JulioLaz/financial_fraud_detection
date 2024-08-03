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

### Métricas y su Importancia en la Detección de Fraude Financiero

1. **Accuracy (Exactitud):**
   - **Definición:** Proporción de predicciones correctas sobre el total de casos.
   - **Importancia:** En problemas de fraude, la exactitud puede ser engañosa si hay un desequilibrio en las clases (fraude vs. no fraude). Un modelo que siempre predice "no fraude" puede tener una alta exactitud si los casos de fraude son raros.
   
2. **Precision (Precisión):**
   - **Definición:** Proporción de verdaderos positivos sobre el total de positivos predichos.
   - **Importancia:** Es crucial cuando el costo de un falso positivo es alto. En fraude financiero, una baja precisión significaría muchos falsos positivos, lo que podría resultar en la investigación innecesaria de transacciones legítimas.

3. **Recall (Sensibilidad o Tasa de Detección):**
   - **Definición:** Proporción de verdaderos positivos sobre el total de positivos reales.
   - **Importancia:** Es vital cuando el costo de un falso negativo es alto. En fraude financiero, una baja sensibilidad significaría muchos casos de fraude no detectados, lo cual es altamente indeseable.

4. **F1 Score:**
   - **Definición:** Media armónica de la precisión y la sensibilidad.
   - **Importancia:** Proporciona un equilibrio entre precisión y sensibilidad, útil cuando se necesita un compromiso entre ambos.

5. **AUC (Área bajo la Curva ROC):**
   - **Definición:** Medida del rendimiento del modelo a través de todos los umbrales posibles.
   - **Importancia:** Refleja la capacidad del modelo para diferenciar entre las clases. Un AUC cercano a 1 indica un modelo excelente.

### Resultados de las Métricas por Modelo

| Modelo         | Accuracy | Precision | Recall | F1   | AUC  |
|----------------|----------|-----------|--------|------|------|
| **RandomForest** | 1.00     | 0.95      | 1.00   | 0.97 | 1.00 |
| **tensorflow**   | 0.91     | 0.87      | 0.71   | 0.78 | 0.84 |
| **XGB**          | 0.94     | 0.91      | 0.80   | 0.85 | 0.89 |

### Análisis Comparativo

1. **RandomForest:**
   - **Exactitud:** Perfecta (1.00)
   - **Precisión:** Alta (0.95), indicando pocos falsos positivos.
   - **Sensibilidad:** Perfecta (1.00), indicando ningún fraude no detectado.
   - **F1 Score:** Muy alta (0.97), excelente equilibrio entre precisión y sensibilidad.
   - **AUC:** Perfecta (1.00), capacidad máxima para diferenciar entre fraude y no fraude.

2. **TensorFlow:**
   - **Exactitud:** Alta (0.91)
   - **Precisión:** Moderada (0.87)
   - **Sensibilidad:** Moderada (0.71), indicando algunos casos de fraude no detectados.
   - **F1 Score:** Moderada (0.78)
   - **AUC:** Moderada (0.84)

3. **XGB:**
   - **Exactitud:** Alta (0.94)
   - **Precisión:** Alta (0.91)
   - **Sensibilidad:** Alta (0.80)
   - **F1 Score:** Alta (0.85)
   - **AUC:** Alta (0.89)

### Selección del Mejor Modelo

Para la detección de fraude financiero, la precisión y la sensibilidad son métricas críticas. Queremos minimizar los falsos positivos (para reducir costos innecesarios) y los falsos negativos (para evitar fraudes no detectados).

- **RandomForest** muestra un desempeño perfecto en todas las métricas. Tiene una precisión muy alta, lo que significa pocos falsos positivos, y una sensibilidad perfecta, lo que significa que detecta todos los casos de fraude. El F1 Score y el AUC también son perfectos, lo que indica un excelente equilibrio y capacidad de discriminación.

- **TensorFlow** tiene un buen desempeño, pero su sensibilidad (0.71) y F1 Score (0.78) son inferiores, lo que indica que podría pasar por alto algunos casos de fraude.

- **XGB** también muestra un buen desempeño con alta precisión (0.91) y sensibilidad (0.80), pero no alcanza los niveles de RandomForest.

### Conclusión

**RandomForest** es el mejor modelo para la detección de fraude financiero según las métricas de precisión, sensibilidad, F1 Score y AUC. Su desempeño perfecto en estas métricas lo hace ideal para minimizar tanto los falsos positivos como los falsos negativos, asegurando una detección precisa y confiable del fraude financiero.
El modelo RandomForest ha demostrado ser el más efectivo para la detección de fraude financiero, mostrando un rendimiento perfecto en todas las métricas clave: precisión (0.95), sensibilidad (1.00), F1 Score (0.97) y AUC (1.00). Este desempeño asegura una detección precisa y confiable de fraudes, minimizando tanto los falsos positivos como los falsos negativos. Se recomienda encarecidamente implementar el modelo RandomForest para optimizar la seguridad financiera y reducir costos operativos.

### Recomendación

Se recomienda implementar el modelo RandomForest para la detección de fraude financiero debido a su rendimiento superior en todas las métricas relevantes para el negocio. Este modelo proporcionará una detección de fraude precisa y confiable, optimizando tanto la seguridad como los costos operativos.

## Contribuciones

Las contribuciones son bienvenidas. Por favor, abra un issue primero para discutir lo que le gustaría cambiar.

## Licencia

Copyright - 2024 - Julio Alberto Lazarte Todos los derechos reservados.
