# Challenge Telecom X - Fase 2: Modelado Predictivo de Churn

Este repositorio contiene la segunda etapa del proyecto, enfocada en la creación de modelos de aprendizaje automático para predecir la evasión de clientes. Se toma como base el dataset limpio generado en la fase de ETL.

## Estructura del Proyecto

El desarrollo se dividió en ramas de características para mantener la integridad del código:
- feature/preprocesamiento-ml: Preparación de datos y codificación.
- feature/entrenamiento-modelos: Construcción y evaluación de algoritmos.
- dev: Rama de integración.
- main: Versión final de entrega.

## Flujo de Trabajo

### 1. Preprocesamiento de Datos
Se realizaron las siguientes transformaciones para compatibilidad con Scikit-Learn:
- Eliminación de la columna ID_Cliente por carecer de valor predictivo.
- Tratamiento de valores nulos (NaN) mediante eliminación de filas para evitar errores en el entrenamiento.
- Aplicación de One-Hot Encoding a variables categóricas, utilizando drop_first=True para evitar la multicolinealidad.
- Conversión de la variable objetivo (Evasion) a formato binario (0 y 1).
- Escalado de variables numéricas mediante StandardScaler, requisito crítico para la Regresión Logística.

### 2. Entrenamiento de Modelos
Se implementaron y compararon dos algoritmos con enfoques distintos:
- Regresión Logística: Modelo lineal que utiliza los datos normalizados.
- Random Forest: Modelo basado en árboles de decisión que utiliza los datos originales.

### 3. Evaluación y Métricas
La evaluación se centró en la capacidad de detectar clientes en riesgo de fuga (clase 1):
- Reporte de Clasificación: Cálculo de Precision, Recall y F1-Score para ambos modelos.
- Matrices de Confusión: Visualización de aciertos y errores (Falsos Negativos vs Verdaderos Positivos).
- Importancia de Variables: Identificación de los factores con mayor peso en la predicción mediante los coeficientes de Random Forest.