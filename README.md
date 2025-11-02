# Proyecto 2 – Laboratorio de Aprendizaje Estadístico

## Descripción  
Este proyecto analiza un conjunto de datos de transacciones con tarjetas de crédito para detectar fraudes mediante técnicas de aprendizaje estadístico y modelos de machine learning.  
Se emplean distintos clasificadores supervisados, optimización de hiperparámetros y validación cruzada, evaluando el rendimiento a través de métricas como AUC-ROC, exactitud y matrices de confusión coloreadas.

## Conjunto de datos  
- **Nombre:** Credit Card Fraud Transaction Data  
- **Fuente:** [Kaggle – Credit Card Fraud Transaction Data](https://www.kaggle.com/datasets/anurag629/credit-card-fraud-transaction-data)  
- **Descripción:** Contiene transacciones etiquetadas como fraudulentas o legítimas, junto con variables de comportamiento y características de la transacción.  
- **Preprocesamiento:** Escalado de variables numéricas, tratamiento de desequilibrio de clases y división en conjuntos de entrenamiento y prueba.

## Metodología  
1. **Exploración y limpieza de datos:** análisis descriptivo, visualización de distribuciones y detección de desequilibrio.  
2. **Preprocesamiento:** normalización, codificación y balanceo (si aplica).  
3. **Modelos supervisados:**  
   - Regresión Logística  
   - Support Vector Machine (SVM)  
   - Multi-Layer Perceptron (MLP)  
4. **Validación cruzada:** K-Fold con 10 particiones para estimar el rendimiento generalizado.  
5. **Optimización de hiperparámetros:**  
   Se utiliza un modelo de **Gaussian Process Regression (GPR)**.  
   En cada iteración se evalúa el punto con **máxima incertidumbre**, definido como la diferencia entre los límites superior e inferior de la predicción:

   $$
   x_{\text{next}} = \arg\max \left( y_{\text{upper}}(x) - y_{\text{lower}}(x) \right)
   $$

   donde  

   $$
   y_{\text{upper}}(x) = \mu(x) + 1.96 \cdot \sigma(x), \quad
   y_{\text{lower}}(x) = \mu(x) - 1.96 \cdot \sigma(x)
   $$

   Esto permite explorar regiones del espacio de hiperparámetros donde el modelo es más incierto, mejorando la optimización y el rendimiento final.

6. **Evaluación:**  
   - Curvas ROC y métricas AUC.  
   - Matrices de confusión.
   - Reporte de métricas de validación cruzada y comparación de desempeño entre modelos.

## Estructura del repositorio  
├── CreditCardData.csv # Dataset original
├── reporte.ipynb # Notebook principal del análisis
├── pipeline.jpeg # Esquema del flujo de modelado
├── README.md # Este archivo
├── LICENSE # Licencia del proyecto
└── .gitignore # Archivos ignorados por Git

## Resultados
- Modelo con mejor desempeño (según AUC-ROC).
- Comparación entre modelos supervisados.
- Visualización de curvas ROC y matrices de confusión.

## Autoras
- Ana Sofía Hinojosa
- Julia Hernández
- Sara Hernández