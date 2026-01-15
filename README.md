# Automatic Classification of Tree Tomato Ripeness Using Convolutional Neural Networks

## Descripción del Proyecto
Este proyecto desarrolla un sistema de visión por computador para el reconocimiento automático de tres estados de madurez del tomate de árbol (Solanum betaceum): verde, pinton (intermedio) y maduro. El objetivo principal es proporcionar una herramienta tecnológica que apoye la toma de decisiones agrícolas, reduzca las pérdidas postcosecha y optimice los procesos de clasificación.

El sistema se basa en redes neuronales convolucionales (CNN) y fue entrenado con un dataset generado localmente en plantaciones e invernaderos de la sierra ecuatoriana, considerando variaciones reales de iluminación, fondo y morfología del fruto.

## Dataset
El conjunto de datos se construyó específicamente para este estudio, capturando imágenes en escenarios de producción auténticos para minimizar el sesgo y mejorar la generalización del modelo.
- Especies: Tomate de árbol (Solanum betaceum).
- Clases: Verde, Intermedio (Semi-maduro), Maduro.
- Condiciones: Variaciones en intensidad de luz, dispositivos de captura y presencia de imperfecciones naturales.
- Preprocesamiento: Las imágenes fueron etiquetadas utilizando la plataforma Roboflow.

## Metodología
El desarrollo se centró en la comparación de tres arquitecturas de detección de objetos de última generación:
1. YOLOv8n
2. YOLOv11n
3. RT-DETR (Transformer-based)

Se implementaron dos estrategias de entrenamiento y evaluación:
- Validación Cruzada (10-fold Cross-Validation): Para obtener una estimación robusta del rendimiento y la capacidad de generalización del modelo.
- Configuración State-of-the-Art: Entrenamiento con división simple (Train/Validation/Test) optimizada para despliegue.

## Resultados
Los experimentos mostraron que las arquitecturas basadas en YOLO ofrecieron el mejor equilibrio entre precisión y eficiencia computacional para este entorno agrícola específico.

Resultados destacados (Fase 2):
- Modelo de mejor rendimiento: YOLOv8n.
- mAP@50-95: 84.13%.
- Desempeño por clases: El modelo alcanzó una alta precisión en la detección de frutos maduros (99% de precisión individual), aunque la clase "Verde" presentó mayores desafíos debido a la similitud cromática con el follaje de fondo.

Nota técnica: El modelo RT-DETR presentó problemas de inestabilidad numérica y sensibilidad a hiperparámetros en entornos de recursos limitados, por lo que se recomienda el uso de YOLOv8n para implementaciones en dispositivos Edge o móviles.

## Requisitos y Herramientas
El proyecto fue implementado utilizando el siguiente stack tecnológico:
- Lenguaje: Python 3
- Framework de Deep Learning: Ultralytics YOLO (v8.3.x)
- Gestión de Datos: Roboflow
- Análisis de Métricas: Scikit-learn, Pandas, Matplotlib
- Hardware de Entrenamiento: NVIDIA Tesla T4 (Google Colab) y NVIDIA GeForce RTX 4060.

## Autores
- David Mejia
- Kathlen Menendez
- Mateo Ordóñez
- Santiago Tugulinago

Departamento de Mecatrónica, Universidad Internacional del Ecuador.
