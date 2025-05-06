# 🎓 Predicción y Análisis Explicable de la Empleabilidad Estudiantil usando ML y Deep Learning

Este proyecto de investigación aplica técnicas avanzadas de Machine Learning y Deep Learning para analizar los factores que influyen en la empleabilidad de estudiantes universitarios. El objetivo es desarrollar un modelo predictivo robusto y explicable que ayude a instituciones educativas a mejorar la preparación profesional de sus egresados.

## 📌 Objetivo del Proyecto

Identificar y analizar los rasgos clave que influyen en la empleabilidad estudiantil mediante técnicas de minería de datos educativos combinadas con modelos de aprendizaje automático y profundo, con el fin de desarrollar un marco explicable que oriente intervenciones educativas efectivas.

## 🧠 Metodología

- Se utilizaron **modelos de Deep Learning** como:
  - **LSTM (Long Short-Term Memory)**
  - **GRU (Gated Recurrent Units)**
- Se aplicó análisis de explicabilidad con:
  - **SHAP (SHapley Additive exPlanations)**
- Se emplearon técnicas de optimización de modelos:
  - **Grid Search**
  - **Validación cruzada (k-fold)**

## 🗂️ Datos Utilizados

- Datos provenientes de **entrevistas simuladas de trabajo** (mock interviews).
- Variables analizadas incluyen tanto habilidades técnicas como habilidades blandas (soft skills):
  - Autoconfianza
  - Capacidad de presentar ideas
  - Apariencia general
  - Entre otras características personales y académicas

## ⚙️ Configuración de Modelos

- **Modelo LSTM** configurado con tres capas.
- Precisión alcanzada: **91.46%**
- Puntaje de consistencia con validación cruzada (3-fold): **90.48%**
- Comparación con GRU mostró un rendimiento inferior, posicionando al LSTM como el modelo óptimo.

## 🔍 Resultados Principales

- Las **habilidades blandas** fueron los predictores más influyentes según el análisis SHAP:
  - **Autoconfianza**
  - **Capacidad para presentar ideas**
  - **Apariencia general**
- Se demuestra que integrar el desarrollo de habilidades blandas en los planes de estudio puede mejorar significativamente las tasas de empleabilidad.

## 🧰 Herramientas y Tecnologías Utilizadas

- Python 3.8+
- Bibliotecas: `TensorFlow`, `Keras`, `scikit-learn`, `shap`, `pandas`, `matplotlib`

Instalación recomendada:

```bash
pip install tensorflow keras scikit-learn shap pandas matplotlib
