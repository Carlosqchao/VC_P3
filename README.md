# Proyecto de Clasificación de Monedas y Microplásticos

## Descripción General

Este proyecto aborda dos tareas principales de clasificación en imágenes:  

1. **Clasificación de Monedas:** Identificación del valor de distintas monedas en imágenes, utilizando características de color y tamaño.  
2. **Clasificación de Microplásticos (SMACC):** Segmentación y clasificación automática de partículas de microplásticos en imágenes, mediante características geométricas y modelos de machine learning.

Ambas tareas combinan técnicas de procesamiento de imágenes con modelos de clasificación supervisada, visualización de resultados y análisis cuantitativo mediante métricas de rendimiento.

---

## TAREA 1: Clasificación de Monedas

### Objetivo

Identificar y contabilizar el valor total de las monedas presentes en una imagen, mediante:  

- Detección de monedas mediante transformada de Hough.  
- Escalado de radios de las monedas respecto a una moneda de referencia (1€).  
- Clasificación basada en color medio y tamaño real de las monedas.

### Flujo de Trabajo

1. **Carga y preprocesamiento de la imagen:**  
   - Se carga la imagen en OpenCV (`cv2.imread`) y se convierte a RGB para visualización con Matplotlib.  
   - Se obtiene una versión en escala de grises y se aplica un filtro `medianBlur` para reducir ruido.

2. **Detección de monedas:**  
   - Uso de `cv2.HoughCircles` para detectar círculos que correspondan a monedas.  
   - Almacenamiento de centros y radios detectados en píxeles.

3. **Selección de moneda de referencia:**  
   - El usuario selecciona interactivamente una moneda de 1€, para poder establecer la correspondencia píxel ↔ mm.  
   - Se calcula el radio en mm de todas las monedas usando esta referencia.
<img width="373" height="482" alt="moneda seleccionada" src="https://github.com/user-attachments/assets/ec899712-72dc-4758-bf2d-f54b02e5688a" />
Así se observa una vez se elige la moneda de un euro

4. **Clasificación de monedas:**  
   - Extracción del color medio (RGB) de cada moneda mediante máscaras.  
   - Clasificación simple por color (`Cobre`, `Amarillo`, `Otro`) para distinguir entre monedas de distintos materiales y valores.  
   - Comparación de radios ajustados con radios reales de monedas, para determinar el valor más probable.  
   - Uso del color como ayuda para resolver ambigüedades.

5. **Visualización:**  
   - Se dibujan círculos sobre cada moneda y se muestra el valor estimado.  
   - Se calcula el valor total de la imagen y se muestra en la figura.

<img width="286" height="411" alt="image" src="https://github.com/user-attachments/assets/cd03706d-914c-43e7-9a62-43d58b8400f6" />
Este es el resultado final.


### Resultados

- El sistema permite contabilizar automáticamente el total de dinero en la imagen.  
- Funciona correctamente con monedas bien separadas y sin solapamientos excesivos.  
- Limitaciones:  
  - Detección más complicada si las monedas se superponen.  
  - Clasificación por color sensible a iluminación.

---

## TAREA 2: Clasificación de Microplásticos (SMACC)

### Objetivo

Desarrollar un sistema automático de clasificación de partículas de microplásticos en imágenes, usando características geométricas y machine learning.  

### Flujo de Trabajo

1. **Carga de imágenes y anotaciones:**  
   - Las imágenes de entrenamiento y test se cargan junto con sus regiones anotadas (bounding boxes) o archivos CSV.  

2. **Segmentación y extracción de características:**  
   - Cada partícula se segmenta automáticamente mediante umbralización (`cv2.threshold`) y contornos (`cv2.findContours`).  
   - Se calculan características geométricas de cada partícula:  
     - Área y perímetro  
     - Compacidad: `(perímetro^2)/área`  
     - Área relativa al bounding box  
     - Relación de aspecto del bounding box  
     - Ejes de la elipse ajustada  
     - Centroide y relación entre distancias mínimas y máximas al contorno

3. **Preparación de datos y entrenamiento:**  
   - Se construye un dataset de características con etiquetas correspondientes.  
   - Se normalizan los datos usando `StandardScaler`.  
   - Se entrena un modelo `RandomForestClassifier` con 200 árboles.  

4. **Evaluación en test:**  
   - Se extraen las mismas características de las partículas en las imágenes de test.  
   - Se predicen sus clases y se calculan métricas de rendimiento:  
     - Matriz de confusión  
     - Precisión, recall y F1-score  

5. **Visualización:**  
   - Se muestran las partículas detectadas en la imagen de test con bounding boxes coloreadas según la predicción.  
   - Se genera la matriz de confusión con conteo de aciertos y errores por clase.

### Resultados

- El modelo alcanzó una **precisión global del 82%** en el conjunto de test.  
- Buen desempeño en la clase `FRA` (fragmentos) con recall de 100%.  
- Las clases `PEL` y `TAR` presentan más confusiones entre sí, debido a similitudes en forma y tamaño.  
- Las visualizaciones permiten verificar el comportamiento del modelo en cada partícula individual.

---

## Conclusiones y Lecciones Aprendidas

- La combinación de características geométricas y color es efectiva para clasificaciones simples de objetos circulares como monedas.  
- En el caso de microplásticos, las características geométricas permiten una discriminación razonable, aunque partículas solapadas o de tamaño similar entre clases pueden generar confusiones.  
- El uso de modelos de ensamble como Random Forest proporciona robustez frente a variaciones en las partículas.  
- La visualización y análisis de la matriz de confusión es clave para entender los errores del modelo y planificar mejoras.

---

## Webgrafía y Recursos

- [OpenCV Documentation](https://docs.opencv.org/)  
- [Scikit-learn Documentation](https://scikit-learn.org/stable/)  
- [NumPy Documentation](https://numpy.org/doc/)  
- [Matplotlib Documentation](https://matplotlib.org/stable/contents.html)  
- [Random Forest Classifier (Scikit-learn)](https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.RandomForestClassifier.html)  
- [Pandas Documentation](https://pandas.pydata.org/docs/)
- Diversas consultas a ChatGPT y Claude

---

## Autores

- Juan Boissier García  
- Carlos Ruano Ramos  
