# Inteligencia Artificial para la Competencia de Kaggle

## Integrantes del Equipo

| Nombre | Cédula | Programa Académico |
|--------|--------|--------------------|  
| César Augusto Ruiz Parra | 1088027228| Bioingeniería |
| Paula Valentina Pinzón Gómez | 1007423535| Bioingeniería |
| Mauro Andrés Alegría Cano| 1002972153| Bioingeniería |


# [Entrega #1] Análisis Exploratorio y Modelado de Datos para Rendimiento Académico

## Descripción
En este proyecto, realizaré un análisis exploratorio y modelado de los datos proporcionados en la competencia. El objetivo es entender la estructura, distribución y relaciones entre las variables para desarrollar un modelo de IA que pueda predecir efectivamente el rendimiento académico.

## Contenido
- Exploración inicial de los datos
- Análisis de valores faltantes
- Estadísticas descriptivas
- Visualización de distribuciones
- Análisis de correlaciones
- Identificación de outliers
- Preprocesamiento de datos
- Desarrollo de modelos predictivos
- Evaluación de resultados
- Conclusiones


# [Entrega #2] Preprocesamiento de Datos


## Descripción
En este proyecto, realizamos un preprocesamiento de los datos proporcionados. El objetivo es preparar los datos para el modelado posterior, rellenando valores faltantes, detectando y corrigiendo valores atu00edpicos, normalizando y escalando los datos, codificando variables categu00f3ricas y creando variables adicionales para mejorar el modelado.

## Objetivos
- Identificar y rellenar valores faltantes
- Detectar y corregir valores atu00edpicos (outliers)
- Normalizar y escalar los datos
- Codificar variables categu00f3ricas
- Crear variables adicionales para mejorar el modelado

## Metodología de Preprocesamiento

### 1. Carga y Exploración Inicial de Datos
- Cargamos los conjuntos de datos de entrenamiento y prueba
- Examinamos la estructura general de los datos (dimensiones, tipos de datos)
- Identificamos columnas categóricas y numéricas
- Analizamos la presencia de valores faltantes

### 2. Tratamiento de Valores Faltantes
- Identificamos columnas con valores faltantes
- Para variables numéricas: imputamos con la media de la columna
- Para variables categóricas: imputamos con la moda (valor más frecuente)
- Verificamos que no queden valores faltantes en el conjunto de datos

### 3. Detección y Tratamiento de Outliers
- Utilizamos el método del Rango Intercuartil (IQR)
- Calculamos los límites inferior y superior (Q1 - 1.5*IQR y Q3 + 1.5*IQR)
- Identificamos valores fuera de estos lu00edmites
- Aplicamos tu00e9cnicas de recorte (capping) para limitar los valores extremos

### 4. Codificación de Variables Categoricas
- Identificamos todas las variables categu00f3ricas
- Aplicamos codificación one-hot (variables dummy)
- Eliminamos una categoría de referencia para evitar multicolinealidad (drop_first=True)
- Aseguramos que el conjunto de prueba tenga las mismas columnas que el de entrenamiento

### 5. Normalización de Variables Numéricas
- Aplicamos normalización min-max para escalar todas las variables numéricas al rango [0,1]
- Utilizamos los valores mínimo y máximo del conjunto de entrenamiento para normalizar también el conjunto de prueba
- Verificamos que todas las variables estén correctamente escaladas

## Datos
Los datos contienen información sobre rendimiento académico clasificado en diferentes categorías (bajo, medio-bajo, medio-alto, alto), junto con diversas variables predictoras que pueden influir en dicho rendimiento.

## Implementación
Todo el proceso de preprocesamiento está implementado en el notebook **02 - preprocesado.ipynb**, que incluye:

- Funciones modulares para cada paso del preprocesamiento
- Visualizaciones para entender mejor los datos
- Verificaciones en cada etapa para garantizar la calidad de los datos
- Flujo paso a paso para mayor claridad y control del proceso

## Video de Avance del Proyecto
[Enlace al video en YouTube](https://www.youtube.com/watch?v=XXXX) - Este video explica el estado actual del proyecto, las dificultades encontradas y los próximos pasos a seguir.
