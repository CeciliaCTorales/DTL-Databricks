# Proyecto ETL Profesional con Azure Databricks

Este repositorio contiene un proyecto completo de ETL usando **Azure Databricks Community Edition**, donde procesamos archivos **CSV** y **JSON**, aplicamos transformaciones con **PySpark** y **Spark SQL**, y estructuramos los datos en arquitectura **Medallion (Bronze, Silver, Gold)** usando **Delta Lake**.

---

## 📚 Objetivo

Construir un flujo ETL profesional, transformando datos reales y dejando un proyecto listo para publicar en tu portafolio, GitHub o LinkedIn.

---

## 📦 Archivos necesarios

1. `paciente.csv`
2. `valoracion_usuarios.csv`
3. `ciudad.csv`
4. `historial_medicamentos_usuario.json`

Puedes encontrarlos en la carpeta `data/` de este repositorio o descargarlos desde el siguiente enlace: *(inserta enlace público aquí si aplica)*

---

## ⚖️ Requisitos

* Cuenta gratuita en [Databricks Community Edition](https://community.cloud.databricks.com/)
* Descargar este repositorio como ZIP o clonarlo
* Tener un navegador actualizado (Chrome recomendado)

---

## 🚀 Pasos para ejecutar el proyecto

### 1. Crear Workspace y Cluster

* Ingresa a [Databricks Community](https://community.cloud.databricks.com/)
* Crea un nuevo **cluster** con Databricks Runtime 11.3 LTS o superior
* Para **Free Edition** esto no es necesario ya que se crea por default **Serverless Starter Warehouse**

### 4. Importar el archivo `.dbc`

* Desde el menú lateral izquierdo en Databricks, selecciona **Workspace**
* Haz clic en **Import** y sube el archivo `.dbc` que viene en este repositorio

### 2. Subir los archivos CSV/JSON

* En el menú izquierdo ve a **Data** > **Add Data** > **Upload files to volume**
* Carga los archivos `.csv` y `.json`
* Guárdalos en `/Volumes/workspace/default/primer-etl/`

### 3. Crear Carpetas
* En el menú izquierdo **Workspace** Se crean la carpeta **Primer ETL con Databricks** y las subcarpetas **ETL CSV** y **ETL JSON** 
* Paralelamente subí el archivo .dbc ( .dbc es un formato de archivo binario de Databricks que se utiliza para exportar cuadernos de Databricks. Es un formato autocontenido que puede incluir el código, los metadatos y las salidas de los comandos del cuaderno. Este formato es útil para importar y exportar cuadernos entre áreas de trabajo de Databricks) >> sobre una carpeta: Click derecho > Importar
  

### 4. Ejecutar los notebooks

* Abre los notebooks importados
* Ejecuta las celdas una por una
* Se crearán las tablas Delta en Bronze, luego en Silver, y finalmente en Gold

---

## ✨ Estructura de carpetas (Medallion)

```
primer_etl/
├── bronze/
│   ├── paciente.delta
│   ├── ciudad.delta
│   ├── valoracion_usuarios.delta
│   └── historial_medicamentos.delta
├── silver/
│   ├── pacientes_procesados.delta
│   ├── historial_explode.delta
│   └── valoracion_usuarios_tratada.delta
└── gold/
    ├── resumen_riesgo_ciudad.delta
    └── resumen_historial_pacientes.delta
```

---

## 🎓 Aprendizajes clave

* Lectura robusta con esquemas definidos (StructType)
* Uso de `explode`, `withColumn`, `join`, `case when` en PySpark
* Arquitectura medallion (Bronze, Silver, Gold)
* Almacenamiento con Delta Lake

---

## 📊 Bonus

* Puedes conectar el resultado con **Power BI**, **Azure SQL** o visualizar en dashboards dentro de Databricks.

---

## 🙌 Creador

Este proyecto fue desarrollado como parte del Workshop **"Construye un Proyecto ETL Profesional con Azure Databricks"** por [Daniel Santos](https://www.linkedin.com/in/danielsantosdata/).

Si te fue útil, ¡no dudes en compartirlo o mencionarlo en tu portafolio!
