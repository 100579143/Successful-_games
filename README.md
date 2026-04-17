# Proyecto Final de Machine Learning  
## Predicción del éxito comercial de videojuegos

Este proyecto se ha realizado para la asignatura **Análisis Inteligente de la Información**.  
El objetivo es construir un modelo de *machine learning* capaz de predecir si un videojuego será **exitoso o no**, a partir de algunas características básicas del juego.

## Objetivo del proyecto

El problema se ha planteado como una **clasificación binaria**.  
Se considera que un videojuego es **exitoso** cuando supera **1 millón de copias vendidas a nivel global**.

La variable objetivo creada en el proyecto es:

- **Successful = 1** → si `Global_Sales > 1.0`
- **Successful = 0** → si `Global_Sales <= 1.0`

A partir de esto, se comparan varios modelos de clasificación para ver cuál ofrece mejores resultados.

## Dataset utilizado

Se ha utilizado el dataset **Video Games Sales Dataset (VGChartz)**, obtenido de Kaggle:

[Video Games Sales Dataset (VGChartz)](https://www.kaggle.com/datasets/volodymyrpivoshenko/video-game-sales-dataset)

El conjunto de datos contiene información sobre videojuegos, incluyendo variables como:

- Plataforma
- Año de lanzamiento
- Género
- Publisher
- Ventas globales

## Variables utilizadas

Para el modelo se han usado las siguientes variables:

- `Platform`
- `Year`
- `Genre`
- `Publisher`
- `Global_Sales` (solo para construir la variable objetivo)

Variable objetivo:

- `Successful`

## Contenido de los archivos

### `Successful_games_YC.ipynb`
Notebook principal del proyecto. Incluye:

- Carga del dataset
- Inspección inicial
- Limpieza y preparación de datos
- Análisis exploratorio
- Creación de la variable objetivo
- División en entrenamiento y prueba
- Preprocesamiento
- Entrenamiento de modelos
- Evaluación de resultados
- Selección del mejor modelo
- Matriz de confusión y análisis final

### `Informe_Successful_games.pdf`
Informe del proyecto en formato PDF. Resume de forma estructurada:

- Fuente de datos
- Objetivo del proyecto
- Exploración de los datos
- Métrica utilizada
- Modelos probados y experimentación
- Modelo final seleccionado
- Conclusiones

### `Proyecto final.pdf`
Documento con el enunciado original de la práctica.

## Análisis realizado

Durante el proyecto se llevó a cabo un análisis exploratorio para entender mejor el dataset.  
Entre otros aspectos, se estudió:

- La distribución de las ventas globales
- El desbalance entre juegos exitosos y no exitosos
- La evolución del número de juegos por año
- La tasa de éxito según el año
- Las diferencias entre géneros
- Las diferencias entre plataformas
- Las diferencias entre publishers

## Preparación de datos

Se aplicaron varias transformaciones antes del modelado:

- Tratamiento de valores nulos
- Imputación del año con la mediana
- Relleno de valores categóricos faltantes con `"Unknown"`
- Codificación **one-hot** para variables categóricas
- Estandarización de la variable numérica `Year`

## Modelos probados

Se evaluaron los siguientes modelos:

- Regresión Logística
- Random Forest
- Gradient Boosting
- SVM

## Métricas utilizadas

Debido al **desbalance de clases**, la métrica principal elegida fue el **F1-score**.  
También se utilizó **ROC-AUC** como métrica complementaria.

La **accuracy** se muestra como referencia, pero no se tomó como criterio principal de selección.

## Resultados principales

Resultados obtenidos en el conjunto de prueba:

| Modelo | Accuracy | F1-score | ROC-AUC |
|--------|----------|----------|---------|
| SVM | 0.7804 | 0.4604 | 0.8459 |
| Logistic Regression | 0.7268 | 0.4099 | 0.8281 |
| Gradient Boosting | 0.8846 | 0.1937 | 0.8117 |
| Random Forest | 0.8431 | 0.4032 | 0.7908 |

## Modelo seleccionado

El modelo final seleccionado fue **SVM**, porque obtuvo el mejor equilibrio entre las métricas más importantes del problema:

- Mejor **F1-score**
- Mejor **ROC-AUC**

Aunque no fue el mejor en accuracy, fue el que mejor detectó los videojuegos exitosos dentro de un problema desbalanceado.

## Conclusiones

El proyecto muestra que variables como la plataforma, el año, el género y la editora contienen información útil para estimar si un videojuego puede tener éxito comercial.

También se observa que el problema no es sencillo, ya que la mayoría de los videojuegos del dataset no superan el umbral de 1 millón de ventas. Por ello, fue importante elegir bien las métricas y comparar varios modelos antes de seleccionar el definitivo.

## Tecnologías y librerías utilizadas

- Python
- Pandas
- NumPy
- Matplotlib
- Scikit-learn
- Google Colab

## Autor

**Yubo Chen**
