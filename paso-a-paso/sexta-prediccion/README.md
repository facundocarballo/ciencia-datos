# Pipeline e Imputacion de valores nulos

## Imputacion de valores nulos
Impute los valores nulos de las columnas
- Genero -> con un algoritmo especial
- Edad   -> con la media
- LVL    -> con la media

### Algoritmo para imputar el Genero
Utilizo la proporcion previa que ofrece el dataset para rellener manteniendo esa proporcion en hombres y mujeres

- Masculino: 87.09%
- Femenino:  12.91%

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

Esto provoco una mejora notable en el score del modelo, pasando de un 74.52% a un 78.45%; y reduciendo de forma notable la cantidad de Falsos Positivos, pasando de tener 
