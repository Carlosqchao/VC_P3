# Autores  
Juan Boissier García  
Carlos Ruano Ramos  

---

## TAREA 1: Clasificación de Monedas con Análisis de Componentes  

### Descripción  
Se desarrolló un programa para clasificar diferentes tipos de monedas mediante la extracción de características simples basadas en color. A partir de una imagen con regiones definidas en un archivo CSV, se recortaron las áreas de interés y se calcularon los valores medios de color (RGB) de cada región. Posteriormente, se entrenó un modelo de clasificación con Random Forest y se evaluó su rendimiento con métricas de precisión, recall, F1-score y una matriz de confusión.  

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

## TAREA 3: Implementación del Sistema Completo SMACC  

### Descripción  
Se integraron los módulos de extracción de características, entrenamiento y evaluación en un único sistema automatizado. El programa permite cargar imágenes, extraer las regiones definidas por coordenadas en los archivos CSV, entrenar un modelo y mostrar los resultados finales de la clasificación. La estructura del código sigue un enfoque modular con funciones separadas para lectura de datos, procesamiento de imágenes, entrenamiento y visualización de resultados.  

### Objetivos de aprendizaje  
- Integrar todos los componentes del flujo de análisis en un sistema unificado.  
- Aplicar buenas prácticas de programación modular en proyectos de visión por computador.  
- Automatizar procesos de entrenamiento y evaluación de modelos.  
- Documentar y estructurar adecuadamente un proyecto científico en Python.  
