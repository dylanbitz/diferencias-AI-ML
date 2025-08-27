# Métodos NumPy y Pandas

## Introducción

### Numpy

Según la documentación oficial de NumPy (numpy.org) es una librería fundamental para ciencia de datos en Python, en el core de la librería se encuentran los objetos `ndarray` permitiéndonos encapsular un array de n-dimensiones con datos del mismo tipo, permitiendo realizar múltiples operaciones matemáticas y algoritmicas.

La documentación nos indica que una de las razones por las que NumPy existe es para optimizar la ejecución de código para este tipo de operaciones, exponiendo el siguiente ejemplo:

```python
# Este codigo en python multiplica dos array de una dimensión

c = []
for i in range(len(a)):
    c.append(a[i]*b[i])

# A pesar de producir el resultado esperado, en el caso de que los arrays
# contengan millones de datos, empezaremos a tener problemas de rendimiento
```

para resolver esto resultaría más eficiente realizando el código en C, ayudándonos a obtener rendimiento, sin embargo perdemos la flexibilidad que nos ofrece Python con su sintaxis, es acá entonces donde entra NumPy, dándonos el siguiente resultado:

```python
c = a * b
```

Como se mencionó anteriormente, una de las cosas que hace a NumPy interesante es el trabajo detrás que realiza para obtener resultados eficientes de operaciones entre diferentes arrays, operaciones aritméticas, de la misma o diferente forma, escalares, etc. Además de que ofrece otras herramientas, como el _sorting_, _Discrete Fourier Transforms_, Álgebra Lineal básica, estadística y demás posibilidades.

### Pandas

Pandas es una librería open-source de Python, hecha para manejar datos tabulados y así poder realizar análisis con dichos datos, según MLJAR (s.f.) define dos estructuras esenciales:

- **Series:** un arreglo unidimensional con etiquetas (índice) que puede contener distintos tipos de datos.

- **DataFrame:** una estructura bidimensional que permite almacenar columnas de diferentes tipos, indexadas y manipulables de forma eficiente

Algunas de sus características principales que hacen relevante a pandas son:

- Permite hacer lectura y escribe de varios formatos de archivos: CSV, Excel, SQL, JSON, etc.

- Tiene funciones que permiten reordenar, agrupar y fusionar datos

- Permite generar series temporales para análisis, temas como generación de rangos de fechas por ejemplo

- Para manejar eficiencia y optimización algunas de sus partes están escritas en C

Un ejemplo básico que podemos encontrar es lo siguiente:

```python
import pandas as pd
df = pd.read_csv('archivo.csv')
pd.Series([1, 2, 3], index=['a', 'b', 'c'])
pd.DataFrame({'col1': [1,2], 'col2': [3,4]})
```

Esta librería se integra muy bien con otras librerías, como NumPy, Matplotlib, SciPy, scikit-learn, etc.

## A. NumPy - Creación y manipulación de arreglos

| Comando | Definición | Ejecución |
|:--------------:|:------------:|:-------------:|
| `np.array()` | Te permite crear arrays directamente de tuplas o listas | ![01](./fotos-ejecuciones/01.png) |
| `np.zeros()` y `np.ones()` | Crean arrays multidimensionales de 0s y 1s | ![02](./fotos-ejecuciones/02.png) |
| `np.reshape()` | Cambia la forma del array sin cambiar sus datos | ![03](./fotos-ejecuciones/03.png) |
| `np.concatenate()` | Unir dos o más arrays en uno solo | ![04](./fotos-ejecuciones/04.png) |
| `np.vstack()` | Concatena arrays verticalmente (uno debajo del otro) | ![05](./fotos-ejecuciones/05.png) |
| `np.hstack()` | Concatena arrays horizontalmente (uno al lado del otro) | ![06](./fotos-ejecuciones/06.png) |
| `np.split()` | Divide un array en varios sub-arrays | ![07](./fotos-ejecuciones/07.png) |
| `np.ravel()` | Aplana el array a 1 dimensión, no modifica el original | ![08](./fotos-ejecuciones/08.png) |
| `np.flatten()` | Aplana el array a 1 dimensión, pero devuelve una copia independiente del array original | ![09](./fotos-ejecuciones/09.png) |
| `+` | Suma elemento a elemento de dos arrays | ![10](./fotos-ejecuciones/10.png) |
| `-` | Resta elemento a elemento de dos arrays | ![11](./fotos-ejecuciones/11.png) |
| `*` | Multiplica elemento a elemento de dos arrays | ![12](./fotos-ejecuciones/12.png) |
| `/` | Divide elemento a elemento de dos arrays | ![13](./fotos-ejecuciones/13.png) |
| `**` | Eleva a potencia elemento a elemento de dos arrays | ![14](./fotos-ejecuciones/14.png) |

## B. NumPy - Operaciones estadísticas y funciones avanzadas

| Comando | Definición | Ejecución |
|:--------------:|:------------:|:-------------:|
| `np.mean()` | Calcula el promedio (media aritmética) de los elementos de un array | ![01](./fotos-ejecuciones/Mayra/01.png) |
| `np.std()` | Calcula la desviación estándar, medida de la dispersión de los datos | ![02](./fotos-ejecuciones/Mayra/02.png) |
| `np.sum()` | Devuelve la suma de todos los elementos del array (puede ser por filas/columnas) | ![03](./fotos-ejecuciones/Mayra/03.png) |
| `np.arange()` | Genera un array con valores en un rango definido, usando un paso específico | ![04](./fotos-ejecuciones/Mayra/04.png) |
| `np.linspace()` | Genera un array con un número fijo de valores equiespaciados en un intervalo| ![05](./fotos-ejecuciones/Mayra/05.png) |
| `np.random.rand()` | Genera números aleatorios con distribución uniforme en el rango [0, 1) | ![06](./fotos-ejecuciones/Mayra/06.png) |
| `np.random.randn()` | Genera números aleatorios con distribución normal estándar (media 0, varianza 1) | ![07](./fotos-ejecuciones/Mayra/07.png) |
| `np.random.randint()` | Genera enteros aleatorios dentro de un rango definido | ![08](./fotos-ejecuciones/Mayra/08.png) |
| `np.random.seed()` | Fija la semilla para que los números aleatorios sean reproducibles | ![09](./fotos-ejecuciones/Mayra/09.png) |
| `np.dot()` | Calcula el producto escalar o multiplicación de matrices | ![10](./fotos-ejecuciones/Mayra/10.png) |
| `np.matmul()` / `@` | Multiplicación matricial (equivalente a `np.dot` en 2D, pero más general) | ![11](./fotos-ejecuciones/Mayra/11.png) |
| `np.linalg.det()` | Devuelve el determinante de una matriz | ![12](./fotos-ejecuciones/Mayra/12.png)  |
| `np.linalg.inv()` | Calcula la matriz inversa (si existe) | ![13](./fotos-ejecuciones/Mayra/13.png) |
| `np.linalg.eig()` | Obtiene los autovalores y autovectores de una matriz cuadrada | ![14](./fotos-ejecuciones/Mayra/14.png) |
| `np.linalg.solve()` | Resuelve un sistema de ecuaciones lineales de la forma Ax = b | ![15](./fotos-ejecuciones/Mayra/15.png) |

## Referencias

- NumPy.org. (s.f.). _NumPy Documentation_. <https://numpy.org/doc/stable/index.html>
- Pandas.org. (s.f.). _Pandas Documentation_. <https://pandas.pydata.org/docs/>
