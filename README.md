# Autores  
Juan Boissier García  
Carlos Ruano Ramos  

---

## TAREA 1: Clasificación de Monedas con Análisis de Componentes  

### Descripción  
Se desarrolló un programa para clasificar diferentes tipos de monedas mediante la extracción de características simples basadas en color y en tamaño. A partir de una imagen con regiones definidas en un archivo CSV, se recortaron las áreas de interés y se calcularon los valores medios de color (RGB) de cada región. Mediante medias de los tamaños de las monedas se discernieron unas de otras y para finalizar la clasificacion se comprueba mediante color.

### Objetivos de aprendizaje  
- Comprender el proceso de extracción de características a partir de imágenes.  
- Aplicar el modelo Random Forest para clasificación supervisada.  
- Evaluar el rendimiento del modelo con métricas cuantitativas.  
- Representar gráficamente los resultados con Matplotlib.  

---

## TAREA 2: Clasificación de Microplásticos con SMACC  

### Descripción  
Se implementó un flujo de trabajo completo para la clasificación de microplásticos (SMACC), utilizando imágenes con regiones anotadas. Se extrajeron características de cada partícula, incluyendo color medio (RGB) y, opcionalmente, características geométricas como área, perímetro y compacidad. Los datos se normalizaron y se entrenó un modelo de clasificación utilizando un pipeline con StandardScaler y RandomForestClassifier. Finalmente, se calcularon las métricas de rendimiento y se generó una matriz de confusión para analizar los resultados.  

### Objetivos de aprendizaje  
- Comprender el proceso de segmentación y extracción de características en imágenes.  
- Aplicar modelos de machine learning para clasificación de objetos.  
- Analizar características geométricas y de color en partículas microscópicas.  
- Evaluar la precisión del modelo mediante métricas estadísticas.  
- Visualizar y analizar los resultados con la matriz de confusión.  


---

## Webgrafía  

- OpenCV Documentation: [https://docs.opencv.org/](https://docs.opencv.org/)  
- Scikit-learn Documentation: [https://scikit-learn.org/stable/](https://scikit-learn.org/stable/)  
- NumPy Documentation: [https://numpy.org/doc/](https://numpy.org/doc/)  
- Matplotlib Documentation: [https://matplotlib.org/stable/contents.html](https://matplotlib.org/stable/contents.html)  
- Random Forest Classifier (Scikit-learn): [https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.RandomForestClassifier.html](https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.RandomForestClassifier.html)  
- Pandas Documentation: [https://pandas.pydata.org/docs/](https://pandas.pydata.org/docs/)  

---

## Consultas realizadas  

Durante el desarrollo del proyecto, se realizaron diversas consultas a asistentes de inteligencia artificial para resolver dudas relacionadas con el procesamiento de imágenes, la organización del código y la interpretación de métricas:

- **ChatGPT**:  
  - Asistencia en la redacción del código de extracción de características con OpenCV y NumPy.  
  - Corrección y explicación de métricas de evaluación de modelos.  
  - Orientación en la organización modular del código y estructura de carpetas.  

- **Claude (Anthropic)**:  
  - Revisión conceptual sobre la selección de características relevantes para clasificación de microplásticos.  
  - Sugerencias sobre optimización del flujo de preprocesamiento y normalización de datos.  
  - Asesoramiento en el uso de pipelines de Scikit-learn para integración de modelos.  

---
