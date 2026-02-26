# 📊 Telecom X — Análisis de Evasión de Clientes (Churn)

Este proyecto realiza un **análisis exploratorio de datos (EDA)** y una **limpieza/estandarización** de un dataset de clientes de una empresa ficticia llamada **Telecom X**, con el objetivo de entender los factores asociados a la **evasión (churn)**.

---

## 🎯 Objetivo

- Analizar la **distribución de la evasión** (clientes que abandonan vs los que permanecen).
- Explorar la relación de la evasión con variables:
  - **Categóricas** (género, contrato, método de pago, internet, etc.).
  - **Numéricas** (meses de contrato, cargos mensuales, cargos totales, etc.).
- Preparar un dataset limpio y consistente para pasos posteriores (por ejemplo, **modelado predictivo**).

---

## 🗂️ Dataset

El dataset se obtiene desde un archivo JSON alojado en GitHub y se carga directamente en el notebook mediante una solicitud HTTP.

- Fuente (JSON): `TelecomX_Data.json`  
- Estructura: información de cliente, servicios contratados y cobros.

> Nota: El dataset es ficticio y se utiliza únicamente con fines educativos.

---

## 🧰 Tecnologías utilizadas

- **Python**
- **Pandas**: manipulación y limpieza de datos
- **Requests**: extracción de datos desde URL
- **Matplotlib / Seaborn**: visualización
- **Google Colab**: entorno de ejecución

---

## 🔎 Flujo del análisis

### 1) Extracción y carga
- Descarga del JSON con `requests.get()`
- Conversión a DataFrame con `pd.json_normalize()`

### 2) Inspección inicial
- Información general con `df.info()`
- Tipos de datos con `df.dtypes`
- Detección de duplicados con `df.duplicated().sum()`

### 3) Limpieza y consistencia
- Conversión de cargos a numérico:
  - `Charges.Total`
  - `Charges.Monthly`
- Manejo de errores de conversión con `errors='coerce'`
- Imputación de nulos con `fillna(0)`
- Limpieza de strings (espacios extra) con `str.strip()`
- Eliminación de duplicados con `drop_duplicates()`

### 4) Estandarización
- Renombre de columnas al español (ej.: `Churn` → `Evasion`)
- Creación de variable binaria:
  - `Yes` → 1
  - `No` → 0
- Validación de valores inesperados

### 5) EDA y visualizaciones
- Estadísticas descriptivas de variables numéricas con `describe()`
- Distribución de la variable objetivo (`Evasion`)
- Evasión por variables categóricas (countplots)
- Comparación de variables numéricas por evasión (boxplots)
- Visualización global de evasión:
  - Gráfico de torta (proporción)
  - Gráfico de barras (recuento)

---

## 📈 Resultados esperados

Al ejecutar el notebook podrás:
- Conocer la **tasa de evasión total**.
- Identificar variables con señales asociadas al churn (contrato, pagos, internet, etc.).
- Obtener un **dataset limpio** (`df_limpio`) listo para análisis avanzado o modelos.

---

## ▶️ Cómo ejecutar

1. Clona este repositorio:
   ```bash
   git clone https://github.com/tu-usuario/tu-repo.git
