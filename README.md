# Clasificador-de-Fallas-en-el-Tennessee-Eastman-Process-TEP


Modelo de clasificación multiclase para la detección automática de fallas en el **Tennessee Eastman Process (TEP)** utilizando técnicas avanzadas de Machine Learning.

---

## 1. Descripción

El **Tennessee Eastman Process** es un simulador de proceso químico industrial ampliamente utilizado como benchmark en investigación de detección y diagnóstico de fallas.

Este proyecto implementa un modelo de clasificación supervisada capaz de identificar automáticamente el tipo de falla (IDV 1–21) a partir de datos históricos de operación normal y defectuosa.

El objetivo principal es construir un sistema robusto, reproducible y escalable para diagnóstico automático en entornos industriales.

---

## 2. Objetivo

Desarrollar un modelo de Machine Learning que clasifique correctamente:

- 21 tipos de falla (IDV 1–21)  
- Operación normal  

Optimizando métricas de desempeño en un entorno multiclase y con desbalance de datos.

---

## 3. Dataset

**Origen:** Harvard Dataverse – Tennessee Eastman Process  

### Características principales

- ~5.7 millones de registros  
- 52 variables de proceso  
- 22 clases (Normal + 21 fallas)  
- Tamaño aproximado: 2.6 GB en disco  

### Conjuntos utilizados

- FaultFree Training  
- FaultFree Testing  
- Faulty Training  

Los archivos originales en formato `.RData` fueron convertidos a `pandas DataFrame` para su procesamiento en Python.

---

## 4. Arquitectura del Modelo

### Pipeline de procesamiento

1. Lectura de datos (`pyreadr`)  
2. Muestreo estratificado  
3. Normalización (StandardScaler)  
4. División train/test (80/20 estratificado)  
5. Entrenamiento del modelo  
6. Evaluación y análisis de importancia de variables  

### Modelo principal

Se utiliza `RandomForestClassifier` con:

- 100 árboles  
- Profundidad máxima controlada  
- Ponderación automática de clases  
- Paralelización completa (`n_jobs=-1`)  
- Semilla fija para reproducibilidad  

---

## 5. Tecnologías Utilizadas

- Python 3.10+  
- pandas  
- scikit-learn  
- XGBoost  
- imbalanced-learn  
- NumPy  
- Matplotlib  
- Seaborn  
- pyreadr  

**Requisitos recomendados:** 8 GB de RAM.

---

## 6. Resultados

El modelo obtiene desempeño competitivo en:

- Accuracy global  
- Recall balanceado  
- F1-Score multiclase  
- Matriz de confusión 22×22  

Se incluyen visualizaciones de:

- Matriz de confusión  
- Importancia de variables  
- Distribución de clases  
- Matriz de correlación  

Las variables más relevantes corresponden principalmente a:

- Temperaturas  
- Presiones  
- Caudales  
- Concentraciones químicas  

---

## 7. Metodología

- Muestreo estratificado para preservar proporciones de clase  
- Normalización estándar (media 0, varianza 1)  
- División 80/20 estratificada  
- Manejo de desbalance mediante `class_weight='balanced'`  
- Evaluación con métricas multiclase  

---

## 8. Licencia

Proyecto distribuido bajo licencia MIT.

---

## 9. Autor

Proyecto desarrollado como sistema de clasificación de fallas en procesos industriales.  

**Contacto:** [Tu información aquí]
