# 📊 Telecom X – Análisis de Evasión de Clientes (Churn)

## 📌 Descripción del proyecto

Este proyecto desarrolla un **pipeline ETL completo** para analizar la evasión de clientes (*churn*) en la empresa ficticia **Telecom X**.

El objetivo del análisis es **identificar patrones asociados a la cancelación de servicios**, explorando variables demográficas, contractuales y de facturación que podrían influir en la decisión de los clientes de abandonar la compañía.

El proyecto fue desarrollado utilizando **Python, Pandas, Matplotlib y Seaborn**, siguiendo una estructura modular que separa claramente las etapas del proceso de datos.

---

# ⚙️ Pipeline del proyecto

El script se estructura en cuatro etapas principales:

## 📌 Extracción

* Conexión a la API que contiene los datos del desafío.
* Descarga del archivo JSON alojado en GitHub.
* Conversión de los datos a un **DataFrame de Pandas** mediante `json_normalize`.

Fuente de datos:

https://github.com/ingridcristh/challenge2-data-science-LATAM

---

## 🔧 Transformación

Durante esta etapa se realiza la limpieza y preparación de los datos:

* Normalización de nombres de columnas.
* Eliminación de registros inconsistentes en la variable **churn**.
* Conversión de variables numéricas (`total`, `monthly`).
* Traducción de variables categóricas al español.
* Creación de nuevas variables derivadas:

  * **cuentas_diarias** → cargos mensuales / 30
  * **churn_binario** → codificación 0/1 para análisis.

---

## 📊 Carga y análisis

Se ejecuta el **análisis exploratorio de datos (EDA)**:

### Análisis descriptivo

Se calculan estadísticas básicas de:

* Antigüedad del cliente (`tenure`)
* Cargos mensuales (`monthly`)
* Cargos totales (`total`)
* Facturación diaria estimada (`cuentas_diarias`)

### Visualizaciones generadas

El script produce gráficos para explorar patrones de evasión:

* Distribución general de churn.
* Evasión según **tipo de contrato**.
* Evasión según **método de pago**.
* Relación entre **cargos mensuales y churn**.

Además, los datos procesados se **exportan a un archivo CSV**, permitiendo reproducibilidad del análisis.

---

## 📄 Informe final

A partir del análisis exploratorio se identificaron algunos patrones relevantes:

* La tasa de evasión observada se aproxima al **26-27% de los clientes**.
* Los contratos **mensuales** presentan mayor probabilidad de cancelación.
* El método de pago **cheque electrónico** aparece asociado a mayor churn.
* Clientes con **cargos mensuales más altos** muestran mayor propensión a abandonar el servicio.

### Recomendaciones

* Incentivar la migración a **contratos anuales o bianuales**.
* Promover **pagos automáticos** para mejorar la retención.
* Analizar estrategias de fidelización para clientes con **planes de mayor costo**.

---

# 🛠️ Tecnologías utilizadas

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Requests

---

# ▶️ Cómo ejecutar el proyecto

1. Clonar el repositorio:

```bash
git clone https://github.com/tu-usuario/telecom-churn-analysis.git
```

2. Instalar dependencias:

```bash
pip install pandas numpy matplotlib seaborn requests
```

3. Ejecutar el script:

```bash
python telecom_pipeline.py
```

El script descargará los datos, ejecutará el pipeline ETL y generará las visualizaciones del análisis.

---

# 📁 Estructura del proyecto

```
telecom-churn-analysis
│
├── telecom_pipeline.py
├── TelecomX_Data_Limpio.csv
└── README.md
```

---

# 📚 Fuente del desafío

Challenge de análisis de datos basado en el dataset:

**Telecom X Customer Churn Dataset**

Utilizado con fines educativos para practicar procesos de **ETL y análisis exploratorio de datos (EDA)**.

---

# 👤 Autor

Proyecto desarrollado como ejercicio de análisis de datos y procesamiento ETL en Python.
