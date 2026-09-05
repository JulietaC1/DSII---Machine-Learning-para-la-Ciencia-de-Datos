# Predicción de Churn - Proyecto Final

Este repositorio contiene el código y el análisis del proyecto final. El objetivo fue analizar los factores que llevan a los clientes de una empresa de telecomunicaciones a cancelar su servicio y desarrollar un modelo predictivo para anticiparnos a estas bajas.

## ¿Qué vas a encontrar aquí?
- **`ProyectoFinal_DSII_Llanes.ipynb`**: El Google Colab con todo el desarrollo paso a paso (limpieza, EDA con SQL y gráficos, ingeniería de características, modelos de Machine Learning y explicabilidad con SHAP).
- **`telco_churn.db`**: La base de datos SQLite que utilicé para hacer las consultas analíticas del negocio.
- **`WA_Fn-UseC_-Telco-Customer-Churn.csv`**: El dataset original con los datos de los clientes.

## Resumen del Proyecto y Metodología
1. **Limpieza y Preparación de Datos:** Se cargó el dataset original (7,043 registros), detectando y tratando valores en blanco en la variable `TotalCharges` para asegurar la integridad de los datos.
2. **Análisis Exploratorio (EDA con SQL y Python):** Realicé consultas en SQLite y gráficos descriptivos con Seaborn/Matplotlib. Encontré que los clientes con contratos mensuales (*Month-to-month*), menor antigüedad (*tenure* de 0 a 12 meses) y pagos por cheque electrónico concentran las tasas de abandono más altas (superando el 42%).
3. **Modelado Predictivo:** 
   - Probé primero una **Regresión Logística** como modelo base.
   - Implementé un modelo avanzado de **XGBoost** y enfoqué el rendimiento en la métrica **Recall** (alcanzando un **0.78**), justificándolo desde el punto de vista del negocio: es mucho más rentable retener a un cliente existente con promociones que perderlo y tener que adquirir uno nuevo.
4. **Explicabilidad con SHAP:** Utilicé gráficos de SHAP para interpretar qué variables empujan más las predicciones del modelo.

## Conclusiones principales
- Los contratos mensuales y los primeros meses de antigüedad concentran el mayor porcentaje de cancelaciones.
- Implementé un modelo de **XGBoost** priorizando el **Recall** (alcanzando un **0.78**) para asegurarnos de detectar a la mayor cantidad de clientes en riesgo de irse.

## ¿Cómo reproducir el proyecto?
Este proyecto cuenta con soporte para ejecutarse tanto en Google Colab como de forma local.

1. **Clonar el repositorio:**
  ```
  git clone https://github.com/JulietaC1/DSII---Machine-Learning-para-la-Ciencia-de-Datos.git
```
2. Instalar Dependencias:
```
   pip install -r requirements.txt
```
Muchas gracias por su atención y por las clases, estaré a la espera del feedback!
