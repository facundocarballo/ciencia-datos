# Segunda prediccion
Los de `BLD` los fui viendo uno por uno y comparando, pero los de `REC` no.

## BLD01

Al modificar los `outliers` de esta columna obtuve peores resultados que dejandolos.

Hasta ahora, diria que esta columna no conviene tocarla...

## BLD02

Primero probamos solo modificando la columna `BLD02` y luego combinando las modificaciones en `BLD01` y en `BLD02`

### Solo modificando los outliers de BLD02

Obtuve peores resultados que modificando la columna `BLD01`.

### Combinacion BLD01 y BLD02

Tambien, los resultados no son tan buenos como antes. Son mejores que con solo el `BLD02`, pero son peores que si no hubiera aplicado nada.

## BLD03

### Solo modificando los outliers de BLD03

Obtuve el mejor resultado hasta ahora con el modelo de entrenamiento `Logistic Regression` un 72.38% de accurracy

### Combinacion BLD01 y BLD03

Obtuve los mismos resultados que con solo modificando la columna `BLD03`

### Combinacion BLD02 y BLD03

Obtuve el mejor resultado hasta ahora con el modelo de entrenamiento `Logistic Regression` un 72.50% de accurracy

### Combinacion BLD01, BLD02 y BLD03

Obtuve el mejor resultado hasta ahora con el modelo de entrenamiento `Logistic Regression` un 72.62% de accurracy

# Conclusion Final
La mejora no es tan significativa como para considerar quitar los `outliers`

Con respecto a las columnas `REC`, las ejecute todas juntas (les reemplace los outliers por la media) y me di cuenta que empeoraban la performance del modelo.

Entonces, mi conclusion es que no vale la pena quitar los outliers en este conjunto de datos.