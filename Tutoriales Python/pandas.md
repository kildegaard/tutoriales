# <u>Pandas cheatsheet</u>

## Trabajar con datos numéricos

```python
import pandas as pd
adult_census = pd.read_csv('direccion donde esta')

# Dropeamos una columna que estaba con datos repetidos de otra columna
adult_census = adult_census.drop(columns='education-num')

# Separamos datos de target
data = adult_census.drop(columns='class')
target = adult_census['class']

# Identificamos las columnas numéricas
data.dtypes

# Las separamos
numerical_columns = ['age', 'capital-gain', 'capital-loss', 'hour-per-week']
data_numeric = data[numerical_columns]
```

## Funciones y cosas útiles pero no ordenadas

- Contar valores únicos (en Series):
    - adult_census['class'].value_counts()
