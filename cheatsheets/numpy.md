# <u>Numpy cheatsheet</u>

## Lista de funciones y cosas desorganizadas como me van apareciendo
La idea es que todo lo que tiro acá está piola. Ir ordenándolo de forma de tener una manera eficiente de usa numpy.

***

- crear un array = np.array([1, 2, 3])

- matrices:
```python
np.array([[1, 2, 3],
          [4, 5, 6],
          [7, 8, 9]])
```
- np.dot(algo, otra_cosa)
    - multiplicación element-wise, es un producto escalar tipo:
    - algo = [1, 2, 3]  otra_cosa = [4, 5, 6]
    - np.dot(algo, otra_cosa) -> (1\*4, 2\*5, 3\*6)

- multiplicación element-wise:
    - (algo * otra_cosa)
- algo.sum()
- ndarray.size
    - te tira la cantidad "de elementos"
- np.info(alguna_funcion como por ej sum)
    - te devuelve la info, por linea de comandos
- matriz.shape
- multiplicación matricial:
    - np.matmul(algo, algo2)
    - algo @ algo2
    - Obviamente las dimensiones tienen que tener sentido!
    - Existe el `broadcasting` que dp lo vemos
- climate_data = np.genfromtxt('climate.txt', delimiter=',', skip_header=1)
    - genera un array 2D con los datos
- climate_results = np.concatenate((climate_data, yields.reshape(10000, 1)), axis=1)
    - .reshape le da la forma de (fil, col) que quieras
    - axis = 0 pegotea dos ndarray de arriba a abajo (como cortando un arbol, inverso)
    - axis = 1 une los ndarray de costadito
- np.savetxt('climate_results.txt', 
           climate_results, 
           fmt='%.2f', 
           delimiter=',',
           header='temperature,rainfall,humidity,yeild_apples', 
           comments='')
* Mathematics: `np.sum`, `np.exp`, `np.round`, arithemtic operators 
* Array manipulation: `np.reshape`, `np.stack`, `np.concatenate`, `np.split`
* Linear Algebra: `np.matmul`, `np.dot`, `np.transpose`, `np.eigvals`
* Statistics: `np.mean`, `np.median`, `np.std`, `np.max

- Operaciones aritméticas + - * / entre ndarray son element-wise
- ndarray + - * / un escalar lo aplica a cada elemento también (`broadcast`)
- Comparación entre arrays
    - Usando >, <, == o !=
    - Devuelve un ndarray de booleans
    - Se puede hacer tipo:
        - (array1 == array2).sum() para contar cuántas posiciones son iguales
- np.zeros([3, 2])
- np.ones((3, 2))
- np.eye(5)
- np.random.rand(2, 5)
    - ndarray de (2, 5) con valores entre entre 0 y 1 (distribución UNIFORME)
- np.random.randn(2, 5)
    - ndarray de (2, 5) con valores entre entre 0 y 1 (distribución NORMAL)
- np.random.randint(low, high=None, size=None, dtype=int)
- np.full([2, 3], 42)
    - llena con valor 42
- np.arange(10, 90, 3)
    - start, end, step
- np.linspace(3, 27, 9)
    - valores equiespaciados entre 3 y 27 divididos en 9 partes

- np.nonzero(ndarray)
    - te devuelve los índices de los valores no cero

***

# Funcionalidades concretas

- Rodear un array con un *padding*
    - arr = np.pad(arr, pad_width=1, mode='constant', constant_values=0)

- Crear una matriz con 1 en el borde y cero adentro
    - arr_borde = np.ones([dim, dim])
arr_borde[1:-1, 1:-1] = 0

