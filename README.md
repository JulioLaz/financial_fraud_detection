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
![Distribución del Fraude](placeholder_for_fraud_distribution.png)

### Monto de Transacciones por Tipo y Estado de Fraude
![Monto por Tipo y Fraude](placeholder_for_amount_by_type_and_fraud.png)

### Fraude por Hora del Día
![Fraude por Hora](placeholder_for_fraud_by_hour.png)

## Modelos y Resultados

Se implementaron tres modelos principales:
1. Random Forest Classifier
2. XGBoost
3. Red Neuronal (TensorFlow)

### Comparación de Métricas
![Comparación de Métricas](placeholder_for_metrics_comparison.png)

## Conclusiones

[Añadir conclusiones principales del análisis y modelado]

## Próximos Pasos

- Refinamiento del modelo seleccionado
- Implementación en producción
- Monitoreo continuo y actualización del modelo

## Cómo Usar

[Instrucciones para clonar el repositorio, instalar dependencias y ejecutar el código]

## Contribuciones

Las contribuciones son bienvenidas. Por favor, abra un issue primero para discutir lo que le gustaría cambiar.

## Licencia

Copyright - 2024 - Julio Alberto Lazarte Todos los derechos reservados.
