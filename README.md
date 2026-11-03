# LATAM Dashboard: Mobility & Economy

## Descripción del proyecto

Este proyecto analiza la relación entre la movilidad urbana y la productividad económica en distintas ciudades de América Latina durante el año 2024.

El análisis combina indicadores de tráfico y congestión vehicular con variables económicas como el PIB per cápita, el desempleo y la población, con el propósito de identificar patrones y posibles relaciones entre las condiciones de movilidad y el contexto económico de cada ciudad.

## Objetivos

- Analizar los niveles de congestión vehicular en distintas ciudades.
- Comparar indicadores de movilidad con variables económicas.
- Identificar patrones, diferencias y valores atípicos entre ciudades.
- Explorar si existe una relación entre el PIB per cápita y los niveles de congestión.
- Consolidar los resultados en un dataset limpio para futuros análisis.

## Fuentes de datos

El proyecto utiliza dos conjuntos de datos:

### 1. TomTom Traffic Index

Contiene información relacionada con el comportamiento del tráfico urbano, incluyendo:

- `jams_delay`: retraso asociado a la congestión.
- `traffic_index_live`: índice de tráfico en tiempo real.
- `jams_length_in_kms`: longitud de los atascos en kilómetros.
- `jams_count`: cantidad de atascos.
- `mins_delay`: minutos de retraso.
- `travel_time_live_per_10_kms_mins`: tiempo de viaje actual por cada 10 km.
- `travel_time_historic_per_10_kms_mins`: tiempo histórico de viaje por cada 10 km.

### 2. OECD Cities Economy

Contiene indicadores económicos y demográficos de las ciudades:

- `city_gdp_per_capita`: PIB per cápita.
- `unemployment_percent`: porcentaje de desempleo.
- `pm2_5_ug_m3`: concentración de partículas PM2.5.
- `population`: población urbana.

## Herramientas y tecnologías

- **Python:** lenguaje utilizado para el análisis.
- **Pandas:** limpieza, transformación y manipulación de datos.
- **NumPy:** operaciones y procesamiento numérico.
- **Matplotlib:** creación de visualizaciones.
- **Seaborn:** visualización y análisis exploratorio.
- **Jupyter Notebook:** entorno de desarrollo del proyecto.

## Proceso de análisis

### 1. Exploración de datos

- Carga de los datasets.
- Revisión de dimensiones y tipos de datos.
- Inspección de valores nulos y estructura de las columnas.

### 2. Limpieza y preparación

- Estandarización de nombres de columnas utilizando `snake_case`.
- Conversión de fechas a formato datetime.
- Conversión de variables económicas a formatos numéricos.
- Creación de la variable de población.
- Filtrado de registros correspondientes al año 2024.

### 3. Análisis de movilidad

- Agrupación de los registros por ciudad, país y año.
- Cálculo de promedios anuales de las principales métricas de tráfico.
- Identificación de ciudades con mayores niveles de congestión.

### 4. Integración de datos

- Selección de variables relevantes de ambos datasets.
- Unión de los conjuntos de datos mediante `INNER JOIN`.
- Utilización de las columnas `city` y `year` como claves de unión.

### 5. Visualización y análisis

Se utilizaron diferentes gráficos para explorar las distribuciones y relaciones entre las variables:

- **Boxplot:** distribución de los niveles de congestión y detección de valores atípicos.
- **Histograma:** distribución del PIB per cápita.
- **Gráfico de barras:** comparación entre congestión vehicular y PIB per cápita por ciudad.

## Principales hallazgos

- No se identifica una relación completamente directa entre el PIB per cápita y los niveles de congestión vehicular.
- Algunas ciudades con mayor PIB per cápita presentan niveles moderados de congestión, mientras que otras con menor desempeño económico registran niveles elevados de tráfico.
- Ciudad de México y São Paulo destacan por presentar niveles de congestión considerablemente superiores al resto de las ciudades analizadas.
- Montevideo presenta el PIB per cápita más alto del conjunto analizado, sin registrar uno de los mayores niveles de congestión.
- Los resultados sugieren que la congestión urbana también puede estar relacionada con factores como la población, la infraestructura y las condiciones de movilidad.

## Resultados del proyecto

El análisis final integra información de:

- **15 ciudades**
- **7 países**
- **Año analizado: 2024**

El dataset consolidado se exportó en formato CSV para facilitar su reutilización en futuros análisis.

**Archivo generado:**

`ladb_mobility_economy_2024_clean.csv`

## Recomendaciones

Se recomienda profundizar en el análisis de las ciudades que presentan altos niveles de congestión y explorar variables adicionales, como la densidad poblacional, la calidad del transporte público y el crecimiento urbano.

La incorporación de estos indicadores permitiría comprender mejor los factores que influyen en la movilidad y su posible relación con el desempeño económico de las ciudades.
