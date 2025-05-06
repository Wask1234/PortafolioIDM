# 🌍 Análisis Topológico de Series de Tiempo de Temperatura Global

Este proyecto aplica técnicas de Análisis Topológico de Datos (TDA) para explorar patrones y similitudes entre series de tiempo de temperatura diaria promedio a nivel de ciudad, con datos extraídos de una base global de Kaggle. El objetivo es encontrar agrupamientos naturales de comportamiento climático utilizando herramientas como Mapper y algoritmos de agrupamiento.

## 📌 Problema a Analizar

El **cambio climático** representa uno de los desafíos globales más urgentes. A través de datos históricos de temperatura por ciudad, este estudio busca responder la siguiente pregunta:

> ¿Se pueden separar, de manera topológica, las series de tiempo de ciudades para identificar comportamientos similares en su evolución climática?

Se utiliza la base de datos de Kaggle:  
🔗 [Climate Change: Earth Surface Temperature Data](https://www.kaggle.com/datasets/berkeleyearth/climate-change-earth-surface-temperature-data)

## 🗺️ Datos Utilizados

La base incluye información como:

- Ciudad y país
- Latitud y longitud
- Temperatura diaria promedio
- Incertidumbre de la medición

Para este análisis, se delimitó el enfoque **a nivel de ciudad**.

## 🧰 Técnicas y Herramientas Utilizadas

- **Topological Data Analysis (TDA):**
  - Algoritmo **Mapper**
  - Proyecciones con **Isomap** y **UMAP**
- **Clustering:**
  - **DBSCAN** (Density-Based Spatial Clustering of Applications with Noise)
  - **KMeans** con análisis de Silhouette Score y Elbow Method
- **Visualización:**
  - Redes de nodos generadas por Mapper
  - Cubos de conexión para análisis intra-cluster

## ⚙️ Parametrización de Algoritmos

- **KMeans**:
  - Silhouette Score ≈ 0.8
  - Elbow Method sugiere un valor distinto de K
  - Se evaluaron ambos K, pero se descartó **k = 13** por producir muchos nodos aislados sin relevancia analítica.

- **DBSCAN**:
  - Se ajustaron `eps` y `min_samples` para lograr mayor conectividad.
  - Mejores resultados con: `eps = 1`, `min_samples = 10`
  - Esta configuración permitió observar **nodos conectados y grupos con patrones similares** de comportamiento climático.

## 🔍 Análisis de Resultados

### 🔸 Intra-cluster (KMeans)

- Muchos grupos con 3 o 4 miembros.
- Algunos nodos se repetían en múltiples cubos (visualizaciones), mostrando conexiones parciales.
- KMeans no impone tamaño mínimo, por lo que puede crear nodos poco representativos, pero útiles para identificar similitudes finas.

### 🔹 Intra-cluster (DBSCAN)

- Nodos con **20 o más ciudades** agrupan series de tiempo con comportamientos similares en picos y magnitudes.
- Mejor preservación de comportamientos colectivos y conexiones relevantes.
- Visualizaciones (ej. `cubo11`, `cubo12`) muestran agrupaciones coherentes a nivel temporal y geográfico.

