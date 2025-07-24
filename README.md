# 📊 Telecom X - Parte 2: Análisis y Predicción del Churn

## 📌 Propósito del Proyecto

Este proyecto tiene como objetivo principal **predecir la cancelación de clientes (churn)** de una compañía de telecomunicaciones utilizando técnicas de análisis de datos y aprendizaje automático. El foco está en identificar los factores más influyentes en la decisión de cancelar el servicio y generar estrategias efectivas de retención.

---

## 📁 Estructura del Proyecto

Telecom-X/
│
├── 📄 README.md # Este documento
├── 📓 TelecomX_Parte2.ipynb # Cuaderno principal con análisis y modelado
├── 📂 data/
│ ├── telecom_clean.csv # Dataset tratado y limpio
│ └── raw_data.csv # Dataset original (opcional)
├── 📂 visualizations/
│ ├── churn_distribution.png
│ ├── correlation_matrix.png
│ └── top_features_rf.png
├── 📄 requirements.txt # Librerías necesarias



---

## 🧹 Preparación y Limpieza de los Datos

### 🔠 Clasificación de Variables

- **Numéricas:**
  - `customer_tenure`
  - `account_Charges.Monthly`
  - `account_Charges.Total`
  - `Cuentas_Diarias`

- **Categóricas:**
  - `customer_SeniorCitizen`
  - `internet_TechSupport`
  - `account_Contract`
  - `account_PaymentMethod`
  - `internet_StreamingTV`
  - `account_PaperlessBilling`
  - entre otras...

### ⚙️ Preprocesamiento

- **Imputación de valores faltantes:**  
  - Numéricos: media
  - Categóricos: moda (más frecuente)

- **Normalización:**
  - Aplicada a variables numéricas con `StandardScaler`

- **Codificación:**
  - Variables categóricas transformadas con `OneHotEncoder`

- **Pipeline con `ColumnTransformer`:**
  - Integración de los pasos anteriores para garantizar la reproducibilidad y facilitar el entrenamiento de modelos.

### 🧪 División de los Datos

- 80% Entrenamiento (`X_train`, `y_train`)
- 20% Prueba (`X_test`, `y_test`)

---

## 🧠 Modelado y Justificaciones

### 🔍 Modelos Aplicados

1. **Regresión Logística:**
   - Modelo base interpretativo.
   - Permite analizar la influencia de cada variable sobre el churn.

2. **Random Forest:**
   - Mayor capacidad de generalización.
   - Mejor rendimiento en métricas globales.

### 🎯 Justificación

Se utilizaron ambos modelos para obtener tanto **explicabilidad** (Regresión Logística) como **performance predictiva** (Random Forest), lo cual permite entender mejor el comportamiento de los clientes y construir estrategias sólidas.

---

## 📊 Análisis Exploratorio de Datos (EDA)

Se generaron visualizaciones para entender el comportamiento de los datos:

- Distribución de cancelaciones (`Churn`):
  ![churn_distribution](visualizations/churn_distribution.png)

- Matriz de correlación:
  ![correlation_matrix](visualizations/correlation_matrix.png)

- Importancia de variables según Random Forest:
  ![top_features_rf](visualizations/top_features_rf.png)

---

## ⚙️ Instrucciones para Ejecutar el Proyecto

### 🧰 Requisitos

Instala las siguientes bibliotecas antes de correr el cuaderno:

```bash

pip install pandas numpy matplotlib seaborn scikit-learn
▶️ Pasos para Ejecutar
Clona o descarga este repositorio.

Abre TelecomX_Parte2.ipynb con Jupyter Notebook o Google Colab.

Ejecuta las celdas una por una.

Asegúrate de que el archivo telecom_clean.csv esté en la carpeta data/.

💡 Conclusiones y Siguientes Pasos
Los factores más importantes que influyen en la cancelación son:

Contratos mensuales

Pagos por cheque electrónico

Falta de soporte técnico

Baja permanencia del cliente (tenure)

Próximos pasos:

Probar modelos de boosting (XGBoost, LightGBM).

Implementar estrategias de retención basadas en los perfiles de alto riesgo.

Crear una app simple en Streamlit para visualizar resultados en tiempo real.

🧑‍💻 Autor
Enrique Castillo
Proyecto realizado como parte del aprendizaje en ciencia de datos aplicada a negocios.
