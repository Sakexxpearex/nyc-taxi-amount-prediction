# 🚕 Predicción de tarifas de taxi en NYC (2023)

Este proyecto utiliza técnicas de Machine Learning para predecir el valor de la tarifa (`fare_amount`) de viajes en taxi en la ciudad de Nueva York, a partir de datos públicos del primer semestre de 2023.

---

## 📂 Dataset

- **Fuente:** Kaggle – [NYC Taxi Trip Records Jan-Jun 2023](https://www.kaggle.com/datasets/nagasai524/nyc-taxi-trip-records-from-jan-2023-to-jun-2023)
- **Tamaño:** ~20 millones de registros (se trabajó con una muestra)
- **Variables:** incluye hora, lugar de recogida y bajada, distancia, tipo de tarifa, entre otras.

---

## 🧪 Objetivo del proyecto

Desarrollar un modelo que permita **estimar la tarifa final** de un viaje en taxi, basado en variables temporales, geográficas y de contexto.

---

## 🔧 Proceso realizado

### 1. 🔍 Exploración inicial
- Revisión de estructura, tipos de datos y nulos.
- Eliminación de valores extremos (tarifas negativas, distancias imposibles, pasajeros = 0).

### 2. 🧠 Ingeniería de características
- Extracción de hora (`pickup_hour`), día de la semana (`dayWeek`), si era de noche o fin de semana.
- Detección de viajes a/desde aeropuerto.
- Transformación cíclica de variables horarias.
- Codificación de variables categóricas.
- Agrupación de categorías poco frecuentes en "Otros".

### 3. 📊 Análisis exploratorio (EDA)
- Histogramas y KDE para variables numéricas.
- Gráficos de barras y boxplots para categóricas.
- Análisis de relación entre variables y `fare_amount`.
- Evaluación de la variable `isnight` y su efecto.

### 4. 🤖 Modelado
- Regresión Lineal (baseline).
- Random Forest Regressor.
- Validación cruzada (5-fold).
- Análisis de errores por distancia.

### 5. 📈 Métricas de evaluación
- **Regresión Lineal:**  
  - R² ≈ 0.936  
  - MAE ≈ 2.456

- **Random Forest:**  
  - R² ≈ 0.96  
  - MAE ≈ 1.88  
  - Validación cruzada estable.

---

## 🎯 Resultados destacados

- El modelo de Random Forest logró predecir tarifas con un MAE bajo (~1.9 dólares).
- Se identificó que los viajes desde el aeropuerto y los realizados de noche tienden a tener tarifas más altas.
- Se analizaron variables más influyentes: distancia del viaje, hora, zona de recogida, etc.

---

## 🛠️ Herramientas y tecnologías

- Python (pandas, numpy, matplotlib, seaborn, scikit-learn)
- Jupyter Notebook
- Git + GitHub

---

## 🙋‍♂️ Aprendizajes personales

- Flujo completo de un proyecto de ML real desde datos crudos hasta modelo validado.
- Análisis crítico de variables, limpieza avanzada y feature engineering.
- Evaluación de modelos regresivos y comparación de rendimiento.
- Comunicación clara de resultados a través de visualizaciones y Markdown.

---

## 📌 Próximos pasos

- Probar modelos como XGBoost o LightGBM.
- Aplicar selección de características.
- Dividir modelos según tipo de viaje (corto vs. largo).
- Subir versión productiva con API (Flask/FastAPI).

---

> Proyecto desarrollado por **Bastian ** como parte de su portafolio de aprendizaje.
