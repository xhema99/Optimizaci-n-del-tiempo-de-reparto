# Optimizacion-del-tiempo-de-reparto
Sistema de predicción del tiempo de entrega de última milla utilizando Machine Learning en AWS SageMaker Canvas.

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Descripción del proyecto

Una empresa de mensajería de comercio electrónico desea mejorar sus operaciones de entrega de última milla.
Aunque ya utiliza software de optimización de rutas, busca obtener información adicional a partir de los datos históricos para:

-Estimar el tiempo total de reparto
-Optimizar la asignación de conductores
-Reducir retrasos y costes operativos

En este proyecto se desarrolla un modelo de Machine Learning capaz de predecir el tiempo de entrega en función de múltiples variables operativas.

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Objetivo

Predecir el DeliveryTime (tiempo total de reparto) a partir de:

-Número de paquetes
-Temperatura
-Distancia al centro urbano
-Experiencia del conductor
-Incidentes de seguridad
-Tipo de vehículo
-Canal de cumplimiento (SFS / SFDC)

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Tecnologías utilizadas

-AWS SageMaker Canvas
-AWS Data Wrangler
-Amazon S3
-Machine Learning (regresión)
-Feature Engineering
-One-Hot Encoding
-Standard Scaling
-Batch Inference

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Arquitectura

S3 (Raw Data) => Data Wrangler(EDA + Feature Engineering) => Prepared Dataset(S3) => SageMaker Canvas(Training) => Batch Inference => Predictions(S3)

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Exploratory Data Analysis (EDA)

Se realizó un análisis completo de calidad de datos y correlaciones:

-Principales hallazgos:
-El número de paquetes es el principal factor predictivo
-La experiencia del conductor reduce el tiempo de entrega
-La distancia incrementa el tiempo de reparto
-La temperatura influye en el rendimiento

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Preparación de datos

-One-Hot Encoding para variables categóricas
-Standard Scaling para variables numéricas
-Limpieza y validación de datos
-Exportación a S3

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Modelado

Se entrenaron dos modelos:

| Modelo         | Tipo       | RMSE  |
| -------------- | ---------- | ----- |
| Quick Build    | Baseline   | 1.277 |
| Standard Build | Optimizado | 1.115 |

El modelo optimizado mejora la precisión en un 12.6%.

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Despliegue

-Batch Prediction en AWS SageMaker Canvas
-Resultados exportados a Amazon S3
-Integrable en sistemas de planificación logística

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Resultados

El modelo permite estimar el tiempo de entrega con un margen medio de error de ±1.11 horas, permitiendo mejorar la planificación diaria de rutas.


