# 📊 Streaming Platforms Data Model & Analytics

## 🎯 Objetivo del Proyecto
Análisis comparativo de catálogos de contenido (Netflix vs. Amazon Prime vs Disney+) enfocado en evaluar la diversidad de géneros, evolución histórica de producción y preferencias de formato por mercado.

## 🛠️ Stack Tecnológico
* **Herramienta principal:** Power BI
* **ETL & Transformación:** Power Query
* **Modelado de Datos:** Esquema de Estrella (Star Schema)
* **Lenguaje de Fórmulas:** DAX

## ⚙️ Arquitectura y Proceso (Data Engineering)
El dataset original consistía en un archivo plano desnormalizado y con anomalías de formato. Para asegurar la integridad y rendimiento del análisis, se ejecutó el siguiente pipeline:
1. **ETL (Extracción, Transformación, Limpieza):** Eliminación de valores nulos, depuración de errores de tipado en fechas y estandarización de columnas clave (como `release_year`) utilizando Power Query.
2. **Modelado Dimensional:** Destrucción de la tabla plana ineficiente para construir un **Esquema de Estrella** estricto:
   * **Tabla de Hechos:** `Fact_Content` (almacena los identificadores y métricas).
   * **Tablas de Dimensiones:** Creación de `Dim_Country`, `Dim_Platform` y `Dim_Year` para gobernar el contexto de filtro.
3. **Optimización DAX:** Implementación de una tabla de medidas desconectada para mantener el modelo limpio y ejecución de cálculos de conteo distintivo (`DISTINCTCOUNT`) aprovechando la propagación de filtros.

## 💡 Insights Clave del Negocio
A través del panel visual interactivo, se resolvieron tres preguntas de negocio fundamentales:
1. **Diversidad de Catálogo:** Estados Unidos se posiciona como el mercado dominante con la biblioteca de géneros de contenido más diversa.
2. **Evolución de Producción:** A partir de la década de 2010, **Amazon Prime** aceleró masivamente su volumen de producción histórica, superando la cuota de su competencia en ese periodo.
3. **Preferencia de Formato:** **Japón** destaca como el único mercado principal donde la oferta de Series (TV Shows) supera estadísticamente a la de Películas (Movies).

## 🖼️ Visualización y Modelo de Datos

### 1. Modelo de Datos (Star Schema)
![Vista del Modelo de Datos](C:\Users\FRANCIS\Documents\CURSO POWER BI\imagen_1.png)

### 2. Dashboard Analítico
![Panel de Control Final](ruta_a_tu_imagen_del_dashboard.png)
