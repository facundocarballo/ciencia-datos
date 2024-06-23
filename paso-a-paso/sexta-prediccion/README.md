# Pipeline e Imputacion de valores nulos

## Imputacion de valores nulos

Impute los valores nulos de las columnas

- Genero -> con un algoritmo especial
- Edad -> con la media
- LVL -> con la media

### Algoritmo para imputar el Genero

Utilizo la proporcion previa que ofrece el dataset para rellener manteniendo esa proporcion en hombres y mujeres

- Masculino: 87.09%
- Femenino: 12.91%

```py
import numpy as np
for idx, row in df.iterrows():
    if np.isnan(row[column_name]) == False:
        continue
    if nan_to_masculines > 0:
        nan_to_masculines -= 1
        df.loc[idx, column_name] = 1
        continue
    if nan_to_femenines > 0:
        nan_to_femenines -= 1
        df.loc[idx, column_name] = 0
```

Esto provoco una mejora notable en el score del modelo, pasando de un 74.52% a un 78.45%; y reduciendo de forma notable la cantidad de Falsos Positivos, pasando de tener 90 a 56.

---

Utilizando otro algoritmo un poco mas complejo, obtuve una pequena mejora en el score 78.57% y mantuve la cantidad de Falsos Positivos en 56

Este es el algoritmo mas complejo
```py
    def decission_tree_classifier(self):
        df_cleaned = self.df.dropna(subset=[column_name])
        
        X_target = df_cleaned.drop(column_name, axis=1)
        Y_target = df_cleaned[column_name]
        
        models = Models()
        model = models.decission_tree_classfier()

        model.fit(X_target, Y_target)

        X_test = self.df[df[self.column_name].isna()]
        X_test = X_test.drop(column_name, axis=1)
        y_pred = model.predict(X_test)
        
        for idx, row in self.df.iterrows():
            i = 0
            if np.isnan(row[self.column_name]):
                self.df.loc[idx, self.column_name] = y_pred[i]
                i += 1
```
Basicamente cree un sub modelo para predecir los `NaN` en la columna Genero

## Pipeline
Tuve una mejora en el rendimiento utilizando el Pipeline, llegue a obtener un 78.81% de score, con 61 Falsos Positivos.

### One Hot Encoding
Este no me funciono muy bien, cuando lo agrego en el pipeline me baja el score. Lo utilizo con la columna `Laboral`.

Pero como me baja el rendimiento, decidi no utilizarlo.