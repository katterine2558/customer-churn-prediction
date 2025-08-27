# 📦 Predicción de Fugas de Clientes (Churn) – Telco

![Python](https://img.shields.io/badge/Python-3.10%2B-blue)
![scikit--learn](https://img.shields.io/badge/scikit--learn-ML-orange)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-red)
![Status](https://img.shields.io/badge/status-Ready%20to%20Run-brightgreen)

Repositorio **end-to-end** para predecir **churn (fuga de clientes)** en telecomunicaciones con `scikit-learn`. Incluye EDA, limpieza, preparación de variables, entrenamiento (Árbol de Decisión y Random Forest), **GridSearchCV**, evaluación (F1, ROC-AUC, PR-Curve) e interpretabilidad local con **LIME** — todo en el notebook `KaterineArias_Test.ipynb`.

---

## 🗺️ Tabla de contenido
- [Descripción](#-descripción)
- [Estructura del proyecto](#-estructura-del-proyecto)
- [Objetivo del modelo](#-objetivo-del-modelo)
- [Dataset](#-dataset)
- [Tecnologías y librerías](#-tecnologías-y-librerías)
- [Instalación y uso rápido](#-instalación-y-uso-rápido)
- [Flujo del notebook (resumen)](#-flujo-del-notebook-resumen)
- [Métricas clave (qué mirar)](#-métricas-clave-qué-mirar)
- [Reproducibilidad](#-reproducibilidad)
- [Llevar el pipeline a producción](#-cómo-reutilizar-el-pipeline-en-producción)
- [Buenas prácticas y notas](#-notas-y-buenas-prácticas)
- [Resultados esperados](#-resultados-esperados)
- [Contribuir](#-contribuir)
- [Licencia](#-licencia)
- [Contacto](#-contacto)

---

## 📌 Descripción
Implementación reproducible para estimar la probabilidad de abandono de clientes en una compañía Telco. El flujo está orientado a **datos desbalanceados**, con **estratificación** en el split y `class_weight='balanced'`, priorizando **F1-score** y robustez en producción mediante **Pipelines** y **ColumnTransformer**.


## 🗂️ Estructura del proyecto

```text
├── KaterineArias_Test.ipynb # Notebook principal con todo el flujo
├── data/
│ ├── WA_Fn-UseC_-Telco-Customer-Churn.csv # Dataset (colócalo aquí)
│ └── WA_Fn-UseC_-Telco-Customer-Churn_dictionary.xlsx # Diccionario de datos (opcional)
├── README.md # Este archivo
└── requirements.txt # Dependencias (sugerido)
```

> Si no existe la carpeta `data/`, créala y coloca allí los archivos del dataset.

---

## 🧠 Objetivo del modelo
Entrenar un **clasificador binario** para predecir `Churn` (*Yes/No*), maximizando **F1** y monitoreando **ROC-AUC** y **Average Precision (PR)**.

---

## 🧩 Dataset
- **Nombre:** Telco Customer Churn (Kaggle)
- **Archivo:** `data/WA_Fn-UseC_-Telco-Customer-Churn.csv`
- **Variable objetivo:** `Churn` (`Yes`/`No`)
- **Rasgos:** mezcla de variables **categóricas** y **numéricas** (p. ej., `tenure`, `MonthlyCharges`, `TotalCharges`).
- **Notas de limpieza:**
  - `customerID` se elimina por ser identificador sin poder predictivo.
  - `TotalCharges` puede venir con espacios: se convierten a `NaN`, luego a `float` y se gestionan (p. ej., eliminación/ imputación según el notebook).

---

## 🛠️ Tecnologías y librerías
- **Python 3.10+**
- **pandas**, **numpy**
- **scikit-learn**: `ColumnTransformer`, `OneHotEncoder`, `Pipeline`, `DecisionTreeClassifier`, `RandomForestClassifier`, `GridSearchCV`, métricas
- **matplotlib** para visualización
- **lime** (`LimeTabularExplainer`) para interpretabilidad local
- **ydata-profiling** *(opcional)* para perfilamiento exploratorio

**`requirements.txt` sugerido:**
```txt
pandas>=2.0
numpy>=1.24
scikit-learn>=1.3
matplotlib>=3.7
lime>=0.2.0.1
ydata-profiling>=4.6
```
---

## 🗂️ Estructura del proyecto
