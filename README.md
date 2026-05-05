# ☀️ Pipeline de Curación de Datos Fotovoltaicos - Graus (Huesca)

Este proyecto documenta el proceso técnico de limpieza, normalización y preparación de series temporales de radiación solar extraídas de **PVGIS** (Photovoltaic Geographical Information System). El objetivo es transformar datos meteorológicos crudos en un dataset estandarizado listo para modelos de **Machine Learning** (Forecasting) y análisis de negocio.

## 🔭 Ubicación del Estudio
* **Emplazamiento:** Graus, Huesca (España).
* **Coordenadas:** Latitud 42.198° N, Longitud 0.349° E.
* **Periodo:** 2013 - 2023 (Resolución horaria).

## 🧩 Decisiones Técnicas y Analíticas
En este pipeline se han tomado decisiones estratégicas para asegurar la calidad de los insights posteriores:

1. **Eliminación de Varianza Nula:** Se detectó que la columna `Int` (Indicador de integridad) era constante (`0.0`), por lo que se eliminó para optimizar la carga computacional sin perder información.
2. **Normalización de Unidades:** La potencia se ha escalado de **Vatios (W)** a **Kilovatios (kW)** en las visualizaciones de análisis para facilitar la interpretación de métricas de consumo real.
3. **Tratamiento del Sesgo Nocturno:** En las fases de análisis exploratorio, se filtran los valores de potencia iguales a cero para calcular medias diurnas reales, evitando que el ciclo circadiano suavice artificialmente el rendimiento de la planta.
4. **Estandarización ISO 8601:** El formato de fecha de PVGIS se ha convertido al estándar internacional para garantizar la compatibilidad con modelos como XGBoost o LSTM.

## 🛠️ Stack Tecnológico
* **Lenguaje:** Python 3.14
* **Librerías Principales:** * `Pandas`: Manipulación de datos y series temporales.
    * `NumPy`: Operaciones vectoriales.
    * `Matplotlib` & `Seaborn`: Visualización técnica y mapas de calor.

## 📂 Estructura del Repositorio
* `01_PVGIS_Data_Cleaning_Pipeline.ipynb`: Cuaderno principal con el proceso paso a paso.
* `pvgis_graus_2013_2023_hourly.csv`: Dataset original (entrada).
* `pvgis_graus_2013_2023_hourly_modificado.csv`: Dataset resultante procesado (salida).
* `requirements.txt`: Dependencias del entorno.

---
**Ruben Artola Rangel** *Data Science Student | Análisis Estratégico | Energías Renovables*