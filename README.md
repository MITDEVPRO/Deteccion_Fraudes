# Detección de Fraudes con Machine Learning


> 💡 **Relacionado:** si trabajas finanzas con IA, mira [**finanzas-mcp**](https://github.com/MITDEVPRO/finanzas-mcp) — 25 calculadoras financieras (WACC, DCF, Z-Score, amortización…) como servidor MCP para Claude. `claude mcp add finanzas -- uvx finanzas-mcp`

![Python](https://img.shields.io/badge/-Python-333333?style=flat&logo=python)
![PyCaret](https://img.shields.io/badge/-PyCaret-333333?style=flat)
![scikit--learn](https://img.shields.io/badge/-scikit--learn-333333?style=flat&logo=scikitlearn)
![Jupyter](https://img.shields.io/badge/-Jupyter-333333?style=flat&logo=jupyter)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

Ruta práctica de **clasificación aplicada a fraude/impago crediticio** con AutoML: desde los fundamentos de PyCaret hasta un flujo nivel experto con perfilado de datos, comparación de modelos, tuning por métrica (AUC vs Recall) y ensambles. En español.

> *Fraud/credit-default classification learning path in Spanish: PyCaret AutoML fundamentals → beginner → expert workflows (EDA profiling, model comparison, metric-driven tuning, ensembles), plus applied exercises with solutions.*

## 📚 Ruta de aprendizaje

| # | Notebook | Nivel | Qué cubre |
|---|---|---|---|
| 1 | `1_Fundamentos de autoML y Pycaret` | Básico | Qué es AutoML, setup de PyCaret y su flujo de trabajo |
| 2 | `2._Clasificación del fraude. Nivel principiante` | Principiante | Dataset `credit` (UCI), `compare_models()`, modelos individuales (árbol de decisión, KNN, random forest) y tuning básico |
| 2.1 | `2.1.1_Ejercicio Clasificación` (+ solución en `2.1.2`) | Práctica | Ejercicio de clasificación con preprocesamiento scikit-learn (dataset Titanic) |
| 3 | `3_Clasificación del fraude. Nivel experto` | Experto | EDA con pandas-profiling, `compare_models(n_select=3)`, tuning optimizando **AUC vs Recall** (clave en fraude: el costo de un falso negativo), validación por folds |
| 4 | `4._Ejercicio aplicado de Clasificacion` (+ solución en `4.1`) | Aplicado | Caso completo end-to-end; la solución incorpora **TPOT** (AutoML genético) como segundo enfoque |

## 📊 Datasets (públicos)

- **[Default of Credit Card Clients (UCI)](https://archive.ics.uci.edu/dataset/350/default+of+credit+card+clients)** — 30.000 clientes de tarjetas de crédito de Taiwán; objetivo: predecir el impago del próximo período. Es el dataset `credit` de PyCaret; también incluido como `.xls` en `Data/`.
- **Titanic (Kaggle)** — `train.csv`/`test.csv` en `Data/`, usado en los ejercicios de clasificación para practicar preprocesamiento y features.

## 🛠️ Stack

`PyCaret` (AutoML) · `scikit-learn` · `pandas` / `numpy` · `pandas-profiling` (EDA) · `TPOT` (AutoML genético)

## ▶️ Cómo ejecutar

```bash
python -m venv .venv && source .venv/bin/activate   # Windows: .venv\Scripts\activate
pip install -r requirements.txt
jupyter notebook
```

> **Nota de versiones**: los notebooks fueron desarrollados con PyCaret 2.x y `pandas_profiling` (hoy renombrado [`ydata-profiling`](https://github.com/ydataai/ydata-profiling)). Si usas PyCaret 3.x, la API de clasificación se mantiene casi igual; para el perfilado reemplaza el import por `ydata_profiling`.

## 💡 Por qué AUC *y* Recall

En detección de fraude las clases están desbalanceadas y **un fraude no detectado (falso negativo) cuesta mucho más que una falsa alarma**. Por eso el notebook experto tunea el mismo modelo dos veces — `optimize='AUC'` y `optimize='Recall'` — y compara qué se sacrifica en cada caso. Esa decisión de negocio, no el algoritmo, es el corazón del problema.

## 👤 Autor

**Luis Cáceres** — CTO & CFO · IA aplicada en producción
[luiscaceres.cl](https://luiscaceres.cl) · [LinkedIn](https://www.linkedin.com/in/luis-caceres-cfo-cto) · [GitHub](https://github.com/MITDEVPRO)

Licencia [MIT](LICENSE).
