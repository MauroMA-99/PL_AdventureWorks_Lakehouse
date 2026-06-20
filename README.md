# PL_AdventureWorks_Lakehouse

## 🎯 Descripción
📄Proyecto de Data Engineering desarrollado en Azure Synapse Analytics que implementa una arquitectura Lakehouse basada en el patrón Medallion (Bronze, Silver y Gold). La solución procesa información de clientes, productos y ventas del dataset AdventureWorks utilizando PySpark, Azure Data Lake Storage Gen2 y Synapse Pipelines para construir datasets analíticos listos para consumo por herramientas de Business Intelligence como Power BI.

El flujo contempla la ingesta de datos hacia la capa Bronze, la transformación y modelado dimensional en Silver, y la generación de métricas y agregaciones de negocio en Gold. Cada capa se encuentra desacoplada para facilitar la gobernanza, trazabilidad, escalabilidad y reutilización de los datos.

La solución incorpora automatización mediante Synapse Pipelines, almacenamiento de datos en formato Parquet y modelado analítico basado en dimensiones y hechos, siguiendo buenas prácticas utilizadas en entornos empresariales modernos de Data Engineering.

---

## 🏛️ Arquitectura

### ➡️ Flujo de Datos

```
📄 AdventureWorks Source Files
    ↓
🥉 Bronze Layer (Raw Ingestion)
    ↓
🥈 Silver Layer (Data Cleansing & Dimensional Modeling)
    ↓
🥇 Gold Layer (Business Aggregations & KPIs)

```


### ✨ Características Principales

- 🏗️ **Arquitectura Medallion** - Implementación de capas Bronze → Silver → Gold
- ⚡ **Procesamiento Distribuido** - Transformaciones desarrolladas con PySpark sobre Synapse Spark Pools
- 📂 **Data Lake Storage Gen2** - Persistencia de datos en formato Parquet
- 🔄 **Orquestación con Synapse Pipelines** - Ejecución automatizada de notebooks y flujos ETL
- 📊 **Modelo Dimensional** - Construcción de dimensiones y tabla de hechos para análisis
- 📈 **Analytics Ready** - Datasets preparados para consumo por Power BI
- 🚀 **Lakehouse Architecture** - Separación entre almacenamiento, procesamiento y consumo
- 🔍 **Trazabilidad de Datos** - Flujo controlado desde la capa raw hasta la capa analítica

---

## 📦 Capas del Pipeline

<table>
<tr>
<td width="33%" valign="top">


#### 🥉 Bronze Layer
**Propósito**: Ingesta de datos crudos

**Tablas**:
- Customer
- Address
- CustomerAddress
- Product
- ProductCategory
- ProductModel
- SalesOrderHeader
- SalesOrderDetail

**Características**:
- ✅ Datos sin transformaciones
- ✅ Conservación de estructura original
- ✅ Persistencia en tablas Spark
- ✅ Base para procesamiento posterior
- ✅ Trazabilidad de la fuente original

</td>
<td width="33%" valign="top">

#### 🥈 Silver Layer
**Propósito**: Limpieza e integración

**Tablas**:
- dim_customer
- dim_product
- fact_sales

**Características**:
- ✅ Integración de múltiples fuentes
- ✅ Construcción de dimensiones de negocio
- ✅ Creación de tabla de hechos de ventas
- ✅ Normalización y estandarización
- ✅ Preparación para análisis dimensional
- ✅ Persistencia en tablas y archivos Parquet

</td>
<td width="33%" valign="top">

#### 🥇 Gold Layer
**Propósito**: Consumo analítico

**Tablas**:
- sales_by_month
- sales_by_category
- top_products
- sales_kpis

**Características**:
- ✅ Agregaciones de negocio
- ✅ KPIs comerciales
- ✅ Ventas por categoría
- ✅ Ventas por periodo
- ✅ Ranking de productos
- ✅ Optimizado para Power BI
- ✅ Persistencia en tablas y archivos Parquet

</td>
</tr>
</table>

---

## 🔄 Orquestación
```
PL_AdventureWorks_Lakehouse
│
├── 01_Load_Bronze
│
├── 02_Bronze_To_Silver
│
└── 03_Silver_To_Gold
```

---

## 📁 Estructura del Proyecto

```
PL_AdventureWorks_Lakehouse/
│
├── 📂 Notebooks/
│   ├── 01_Raw_To_Bronze.ipynb  
│   ├── 02_Bronze_To_Silver.ipynb
│   └── 03_Silver_To_Gold.ipynb
│
├── 📂 Pipeline/
│   └── PL_AdventureWorks_Lakehouse_support_live.zip
│
└── 📄 README.md
```

---

## 🛠️ Tecnologías

<div align="center">

| Tecnología | Propósito |
|:----------:|:----------|
| ![Databricks](https://img.shields.io/badge/Azure_Databricks-FF3621?style=flat-square&logo=databricks&logoColor=white) | Motor de procesamiento distribuido Spark |
| ![Delta Lake](https://img.shields.io/badge/Delta_Lake-00ADD8?style=flat-square&logo=delta&logoColor=white) | Storage layer con ACID transactions |
| ![PySpark](https://img.shields.io/badge/PySpark-E25A1C?style=flat-square&logo=apache-spark&logoColor=white) | Framework de transformación de datos |
| ![ADLS](https://img.shields.io/badge/ADLS_Gen2-0078D4?style=flat-square&logo=microsoft-azure&logoColor=white) | Data Lake para almacenamiento persistente |
| ![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=flat-square&logo=github-actions&logoColor=white) | Automatización CI/CD |
| ![Power BI](https://img.shields.io/badge/Power_BI-F2C811?style=flat-square&logo=power-bi&logoColor=black) | Business Intelligence y visualización |

</div>

---
## ⚙️ Requisitos Previos

- ☁️ Cuenta de Azure con acceso a Databricks
- 💻 Workspace de Databricks configurado
- 🖥️ Cluster activo (nombre: `CLUSTER COFFEE SHOP`)
- 🐙 Cuenta de GitHub con permisos de administrador
- 📦 Azure Data Lake Storage Gen2 configurado
- 📊 Power BI Desktop (opcional para visualización)

---

## 🚀 Instalación y Configuración

### 1️⃣. Creación del grupo de recursos

![I1](images/creacion_rg.png)



