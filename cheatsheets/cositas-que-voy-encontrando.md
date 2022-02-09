# Cosas locas, funciones, liberías, lo que venga
***

- Descargar algo de inet
```python
import urllib.request

urllib.request.urlretrieve(
    'https://hub.jovian.ml/wp-content/uploads/2020/08/climate.csv',
    'climate.txt'
)
```
Descarga el archivo climate.csv de internet y lo guarda en climate.csv local
