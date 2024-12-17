# Regresión logística en Iris Dataset

## Descripción del proyecto

Usando el dataset de Iris, utilizo la librería scikit-learn para entrenar un modelo de regresión logística y asegurarme de que el modelo escogido es el más optímo, tratando de extraer de la **"black box"** el mayor número de insights posibles.

## Proceso del proyecto
### Entrenamiento del modelo
Una vez entrenado el modelo, analizamos qué valores del **hiperparámetro C** optimizan la métrica **"f1_macro"**. La siguiente imagen nos muestra la evolución de esta métrica para distintos valores de C. Las líneas muestran los valores promedio con un error calculado a través de la desviación estándar (usando ValidationCurveDisplay).

<image src="/images/validation_curve.png" alt="Validation Curve">

El valor óptimo usando GridSearchCV es 2.08 (valor promedio de 5 folds).

### Evaluación del modelo
Usando este hiperparámetro comprobamos con cross_validate cómo se comporta el modelo para diferentes conjuntos de datos. Se observa que las métricas principales del modelo son algo mejores en el train que en el test, lo que indica que el modelo puede estar sobreajustándose. Sin embargo, las diferencias son pequeñas y el modelo parece ser robusto.

<image src="/images/cross_validate.png" alt="Validation Curve">

### Evaluación de resultados

Una vez asumido que el modelo generaliza para otros conjuntos de datos podemos realizar las predicciones en un conjunto de datos no visto por el modelo obteniendo las siguientes métricas:

<image src="/imagestest_metrics.png" alt="Validation Curve">

Por último, podemos observar la precisión del modelo con la matriz de confusión:

<image src="/images/confusion_matrix.png" alt="Validation Curve">

### Explicabilidad

Finalmente, vamos a utilizar la librería shap para poder explicar lo que está sucediendo en estas predicciones.