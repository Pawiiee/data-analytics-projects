# 🎬 Movie Revenue & Correlation Analysis

![Python](https://img.shields.io/badge/Python-3.x-blue?style=flat&logo=python)
![Pandas](https://img.shields.io/badge/Pandas-Data_Analysis-150458?style=flat&logo=pandas)
![Seaborn](https://img.shields.io/badge/Seaborn-Data_Visualization-3776AB?style=flat)
![Matplotlib](https://img.shields.io/badge/Matplotlib-Visualization-11557c?style=flat)

Un proyecto de análisis exploratorio de datos (EDA) e inferencia estadística enfocado en identificar los factores determinantes que impactan de manera directa la recaudación en taquilla (`gross revenue`) dentro de la industria cinematográfica.

---

## 📌 Contexto y Objetivo del Proyecto

En el mercado del entretenimiento, predecir el retorno financiero de una producción cinematográfica es clave para la toma de decisiones estratégicas y asignación de presupuestos. 

El objetivo principal de este proyecto es transformar un conjunto de datos histórico de películas (más de 6,800 registros) en **insights accionables**, validando hipótesis de negocio a través de:
* Limpieza y depuración estricta de datos (ETL).
* Análisis Exploratorio de Datos (EDA).
* Modelado de correlación estadística (Pearson, Kendall, Spearman) y regresión lineal visual.

---

## 🛠️ Tecnologías y Librerías Utilizadas

* **Lenguaje:** Python 3.x
* **Manipulación y Limpieza de Datos:** `Pandas`, `NumPy`
* **Visualización de Datos:** `Seaborn`, `Matplotlib`
* **Entorno:** Jupyter Notebook / Anaconda

---

## 🧹 Pipeline de Procesamiento y Calidad del Dato (ETL)

Para garantizar la **integridad analítica** y evitar sesgos en el modelado estadístico, se implementaron las siguientes fases de tratamiento de datos:

1. **Auditoría de Datos Faltantes:** Identificación y evaluación de valores nulos a lo largo de las 15 variables del dataset.
2. **Corrección e Inconsistencia de Tipos:**
   * Conversión de variables numéricas flotantes (`float64`) a enteros (`int64`) en columnas críticas como `budget` y `gross` para optimizar el almacenamiento y alinearlo al formato contable.
3. **Estandarización de Fechas:**
   * Creación de la variable calculada `yearcorrect` extrayendo el año directamente de la fecha real de estreno (`released`), resolviendo discrepancias con la columna `year` original.
4. **Tratamiento de Datos Categóricos:** Codificación numérica (*numerization*) de variables cualitativas (compañía productora, director, género, escritor) para integrarlas en la matriz de correlación multivariable.

---

## 📊 Análisis Exploratorio de Datos (EDA) e Insights Clave

### 1. Evaluación de Correlación Numérica
Se calcularon matrices de correlación utilizando el coeficiente de Pearson para cuantificar la relación entre variables cuantitativas (`budget`, `gross`, `votes`, `score`, `runtime`).

* **Presupuesto vs. Recaudación (`budget` vs. `gross`):**
  * Alta correlación positiva (**r ≈ 0.74**).
  * *Insight:* El presupuesto de producción es el indicador cuantitativo con mayor peso en los ingresos brutos en taquilla.
* **Votos de Audiencia vs. Recaudación (`votes` vs. `gross`):**
  * Correlación positiva relevante (**r ≈ 0.61**).
  * *Insight:* El nivel de popularidad e interés del público reflejado en la cantidad de reseñas/votos actúa como un catalizador directo del éxito comercial.

### 2. Visualización Estratégica
* **Modelos de Dispersión con Regresión Lineal:**
  * Implementación de gráficos `sns.regplot()` para evidenciar la tendencia lineal positiva entre el presupuesto asignado y el comportamiento de la taquilla.
* **Mapas de Calor (Heatmaps):**
  * Generación de mapas de calor multivariables utilizando `Seaborn` para traducir patrones complejos de correlación en resúmenes visuales claros y procesables.

---

## 📁 Estructura del Repositorio

```text
├── movies.csv          # Dataset con información histórica de películas
├── Movie_Project.ipynb # Notebook interactivo con el análisis completo
└── README.md           # Documentación del proyecto
