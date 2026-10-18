Práctica 3: Detección y Clasificación de Monedas y Microplásticos por Visión Artificial

Autor: Mencey Montesdeoca Álamo

Asignatura: Visión por Computador

Descripción

Este repositorio contiene el desarrollo de la tercera práctica de Visión por Computador, enfocada en sistemas avanzados de procesamiento de imágenes, segmentación cromática, calibración geométrica interactiva en tiempo real y la evaluación cuantitativa de modelos de detección de objetos mediante matrices de confusión.

Tareas Desarrolladas

Tarea 1: Sistema Interactivo de Detección y Calibración de Monedas

Descripción: Aplicación en tiempo real basada en cámara web para la detección, identificación de material y cálculo del valor nominal de monedas de Euro.

Metodología y Funcionamiento:

Se implementó la transformada de Hough circular (cv2.HoughCircles) para la localización geométrica de las monedas.

Se desarrolló un mecanismo de calibración interactiva por eventos de ratón (cv2.setMouseCallback) para establecer el factor de escala dinámico en px/mm a partir de una moneda de referencia seleccionada por el usuario.

Análisis del espacio de color HSV mediante la media y desviación estándar (cv2.meanStdDev) para discriminar materiales físicos (plata, cobre/bronce, oro y monedas bicolores de 1€ y 2€).

Resultado:


Tarea 2: Detector y Clasificador de Microplásticos

Descripción: Pipeline automatizado para la segmentación, filtrado y clasificación de microplásticos en muestras de imágenes estáticas.

Metodología y Funcionamiento:

Uso del algoritmo de aprendizaje no supervisado K-Means para aislar los $K$ colores dominantes de la imagen y simplificar la búsqueda de contornos.

Aplicación de umbral adaptativo (cv2.adaptiveThreshold) combinado con operaciones morfológicas para mejorar la detección de fragmentos blancos sobre fondos complejos.

Filtrado por propiedades geométricas (área, perímetro y circularidad) y eliminación de contornos duplicados mediante el seguimiento de centroides.

Resultado:


Tarea 3: Evaluación de Rendimiento y Matriz de Confusión

Descripción: Módulo de validación automática que contrasta las predicciones del modelo de microplásticos frente a un conjunto de datos real (ground truth) en formato CSV.

Metodología y Funcionamiento:

Cruce espacial automatizado comparando los centroides de los contornos detectados frente a las cajas delimitadoras reales (x_min, y_min, x_max, y_max).

Categorización de aciertos, falsos positivos ("Fondo") y falsos negativos ("No Detectado").

Cálculo de métricas de rendimiento globales (Accuracy, Precision, Recall y F1-Score ponderados) utilizando scikit-learn y representación visual mediante una matriz de confusión personalizada.

Resultado:


Requisitos y Ejecución

Dependencias

Para ejecutar correctamente los scripts y cuadernos de esta práctica se requieren las siguientes librerías de Python:

opencv-python (cv2)

numpy

matplotlib

scikit-learn

math
