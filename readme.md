# Obteniendo el mejor modelo de Regresión Logística

## Descripción del proyecto

Usando la BBDD de Iris, utilizo la librería scikit-learn para entrenar un modelo de regresión logística y asegurarme de que el modelo escogido es el más optímo.

## Proceso del proyecto
### Entrenamiento del modelo
Una vez entrenado el modelo, analizamos qué valores del **hiperparámetro C** optimizan la métrica **"f1_macro"**. La siguiente imagen nos muestra la evolución de esta métrica para distintos valores de C. Las líneas muestran los valores promedio con un error calculado a través de la desviación estándar (usando ValidationCurveDisplay).
<figure>
    <image src="/validation_curve.png" alt="Validation Curve">
    <figcaption>Train y test para distintos valores de C</figcaption>
</figure>
