# GridSearchCV

Sirvio un poco, ya que encontro una forma de crear el modelo de `LogisticRegression` que genere un score del 74.74%, que le gana al score maximo que tenia hasta ahora que era con `DecissionTreeClassifier` con un 74.52%

Best Parameters: {'C': 0.1, 'class_weight': 'balanced', 'fit_intercept': True, 'l1_ratio': 0.5, 'max_iter': 100, 'penalty': 'l1', 'solver': 'saga', 'tol': 0.0001}


El tema es que no me considen los resultados, al aplicar el GridSearchCV me dice que me va a dar ese score; pero cuando lo corro me da 70.71% y 139 Falsos Positivos (que son muchos mas de los que obteniamos antes).