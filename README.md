# Face Type recognition

## Integrantes
- Francesca Nicole Bances Torres
- Marcos Aaron Bedia Torres 
- Gonzalo Benjamin Huaranga Blanco

## Descripción del proyecto
El proyecto busca desarrollar una inteligencia artificial capaz de recomendar estilos de cabello personalizados para mujeres, basándose en las características faciales extraídas de imágenes.  
El objetivo es facilitar la elección de cortes de cabello que complementen la forma del rostro y resalten la estética personal, especialmente en el contexto de redes sociales y digitalización creciente.

## Objetivos
- Analizar la estructura facial de cada usuario a través de imágenes.  
- Identificar estilos de cabello que complementen características faciales específicas.  
- Desarrollar una interfaz accesible que permita a los usuarios interactuar con la IA.

## Dataset
- Nombre: **Face Shape Dataset**  
- Origen: Kaggle ([link al dataset](https://www.kaggle.com/datasets/niten19/face-shape-dataset))  
- Total de imágenes: 5000  
- Distribución por clase:
  - Oval: 800 (train), 200 (test)  
  - Heart: 800 (train), 200 (test)  
  - Oblong: 800 (train), 200 (test)  
  - Round: 800 (train), 200 (test)  
  - Square: 800 (train), 200 (test)  

## Propuesta metodológica
Se utiliza una **Red Neuronal Convolucional (CNN)** para analizar imágenes faciales y sugerir cortes de cabello adecuados según la forma del rostro.  

### Pasos principales:
1. **Preprocesamiento de imágenes:**  
   - Normalización de iluminación.  
   - Detección de bordes y alineación facial.  
   - Redimensionamiento a 100x100 píxeles y normalización al rango [0,1].

2. **Extracción de características faciales:**  
   - Identificación de atributos como mandíbula, frente, distancia entre ojos, etc.  

3. **Entrenamiento de la CNN:**  
   - Dataset de entrenamiento: imágenes etiquetadas según la forma del rostro.  
   - Capas de la red:
     - Conv2D + ReLU
     - MaxPooling2D
     - Dropout (0.5)
     - Flatten
     - Dense + ReLU
     - Dense + Softmax (salida para 5 clases)  
   - Optimización: Adam  
   - Función de pérdida: `sparse_categorical_crossentropy`  
   - Métrica: `accuracy`  
   - Número de épocas: 100

4. **Predicción de estilos de cabello:**  
   - La CNN analiza la imagen facial y propone estilos de cabello adecuados para la fisiología del rostro.

5. **Interfaz de usuario:**  
   - Sistema web amigable para subir fotos y recibir recomendaciones visuales de cortes de cabello.

## Diseño del aplicativo
Se sigue la metodología **CRISP-DM**:
1. **Entendimiento del negocio:**  
   - Problema: dificultad de mujeres para elegir estilos de cabello adecuados.  
   - Objetivo: mejorar la experiencia personal y social mediante IA.  
   - Beneficio esperado: ahorro de tiempo y mayor satisfacción estética.

2. **Entendimiento de los datos:**  
   - Dataset con 5 tipos de rostro, imágenes de distintos tamaños, verificación y limpieza de duplicados y archivos corruptos.

3. **Preparación de los datos:**  
   - Redimensionamiento de imágenes a 100x100 px.  
   - Normalización de píxeles.  
   - Conversión a tensores para entrenamiento de la CNN.

## Resultados
- El modelo muestra buena precisión en entrenamiento, pero menor exactitud en validación, lo que indica posibles mejoras con aumento de datos o ajustes de arquitectura.  
- La CNN logra diferenciar correctamente las formas faciales principales y proporciona recomendaciones consistentes de estilos de cabello.

## Frontend
Se proyecta un diseño web donde las usuarias puedan subir su imagen y recibir recomendaciones visuales de cortes de cabello personalizados.

[link](https://www.ibm.com/es-es/topics/convolutional-neural-networks)
