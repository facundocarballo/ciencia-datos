## Trabajo Practico - Ciencia de Datos

#### Universidad Nacional de la Matanza - 2024

##### Primer Cuatrimestre

Al profe le gustaria que implementemos una solucion con un Pipeline

Basicamente tenemos que aplicar las cosas que vamos viendo en las clases....

---

### Modelos posibles de entrenamiento
Estamos ante un dataset de datos no discretos, sino mas bien continuos. Por lo tanto algunos modelos de entrenamiento como el `MultinomialNB` no los voy a considerar, ya que estos se desempenan mejor con datasets discretos.

- GaussianNB
- DecisionTreeClassifier
- LogisticRegression

---

# Paso a Paso del desarrollo del modelo final
El paso a paso de las predicciones se encuentra en la carpeta `paso-a-paso`

---
1. Modos de Entrenamiento
2. Standar Scaler
3. Cargamos el dataset
4. Chequeamos los string del dataset
5. Pipeline