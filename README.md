# Inteligencia Artificial para la Competencia de Kaggle

## Integrantes del Equipo

| Nombre | Cédula | Programa Académico |
|--------|--------|--------------------|  
| César Augusto Ruiz Parra | 1088027228| Bioingeniería |
| Paula Valentina Pinzón Gómez | 1007423535| Bioingeniería |


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
- https://youtu.be/EDLIb-78314


# [Entrega #3] Modelado Avanzado con Machine Learning

## Descripción
En esta entrega desarrollamos e implementamos modelos avanzados de Machine Learning para la predicción del rendimiento académico, enfocándonos en algoritmos de alto rendimiento como SVM, Random Forest y XGBoost. El objetivo es lograr la mayor precisión posible aprovechando técnicas de modelado avanzadas y optimización de hiperparámetros.

## Modelos Implementados

### 1. Modelo SVM (03 - modelo SVM.ipynb)
**Support Vector Machine** - Modelo de clasificación basado en la búsqueda del hiperplano óptimo
- **Kernel utilizado**: RBF (Radial Basis Function) para capturar relaciones no lineales
- **Optimización**: Búsqueda en grilla para parámetros C y gamma
- **Características**: Manejo robusto de datos de alta dimensionalidad
- **Ventajas**: Efectivo con espacios de características complejos
- **Resultados**: Modelo baseline con buena generalización

### 2. Modelo Random Forest (04 - modelo Random Forest.ipynb)
**Ensemble de Árboles de Decisión** - Técnica de bagging para reducir overfitting
- **Algoritmo**: Combinación de múltiples árboles de decisión
- **Optimización**: Búsqueda exhaustiva de hiperparámetros (n_estimators, max_depth, min_samples_split)
- **Características**: 
  - Importancia automática de características
  - Resistencia al overfitting
  - Manejo natural de variables categóricas y numéricas
- **Ventajas**: Interpretabilidad y robustez
- **Resultados**: Mejora significativa sobre SVM con análisis de importancia de características

### 3. Modelo XGBoost (05 - modelo solución.ipynb)
**Extreme Gradient Boosting** - Algoritmo de boosting optimizado para competencias
- **Algoritmo**: Gradient boosting con optimizaciones avanzadas
- **Aceleración GPU**: Implementación con soporte CUDA para RTX 4070
- **Optimización avanzada**: 
  - RandomizedSearchCV con 50+ iteraciones
  - Validación cruzada estratificada
  - Early stopping para prevenir overfitting
- **Características técnicas**:
  - `tree_method='gpu_hist'` para aceleración GPU
  - Regularización L1 y L2
  - Control de profundidad y learning rate adaptativo
- **Ventajas**: 
  - Estado del arte en datos tabulares
  - Excelente manejo de características categóricas
  - Optimización automática de memoria
- **Resultados**: Mejor modelo final con accuracy superior y análisis detallado

## Infraestructura y Hardware
- **CPU**: Intel i7 12va generación
- **GPU**: NVIDIA RTX 4070 (utilizada para XGBoost)
- **Memoria**: Optimización para datasets grandes
- **Paralelización**: Aprovechamiento de múltiples cores

## Metodología de Evaluación
- **Validación cruzada**: 5-fold stratified para todos los modelos
- **Métricas**: Accuracy como métrica principal
- **Análisis de confianza**: Distribución de probabilidades de predicción
- **Importancia de características**: Análisis detallado para interpretabilidad
- **Comparación robusta**: Evaluación de tiempo de entrenamiento y uso de GPU

## Resultados y Submissions
Cada modelo genera archivos completos de resultados:
- **Modelo entrenado**: `.joblib` para reutilización
- **Submission**: Archivo CSV para Kaggle
- **Probabilidades**: Análisis de confianza de predicciones
- **Métricas**: Resultados detallados de validación cruzada
- **Importancia**: Ranking de características más relevantes

## Flujo de Trabajo
1. **Carga de datos preprocesados** (de la Entrega #2)
2. **Configuración de hardware** (GPU, cores, memoria)
3. **Definición de hiperparámetros** específicos por modelo
4. **Entrenamiento con validación cruzada**
5. **Optimización de hiperparámetros**
6. **Evaluación final y análisis**
7. **Generación de submissions**
8. **Comparación de modelos**

El modelo XGBoost emerge como la **solución final** debido a su superior rendimiento, eficiencia computacional y capacidad de generalización en datos tabulares complejos.



