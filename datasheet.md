| Comando | Definición | Ejecución |
|--------------|:------------:|-------------:|
| Fila 1, Col 1 | Fila 1, Col 2 | Fila 1, Col 3 |
| Fila 2, Col 1 | Fila 2, Col 2 | Fila 2, Col 3 |
## C-pandas-dataframes

| **Comando** |**Definición** | **Ejecución** |
|-------------|----------------|-------------------------|
| `pd.DataFrame()` | Genera una tabla bidimensional de datos organizada en filas y columnas. Se puede crear a partir de diccionarios, listas, arreglos o incluso otros DataFrames.|espaci para la ejecucion  | 
| `pd.Series()` | Crea una estructura unidimensional similar a un arreglo de NumPy, pero con índices personalizados, lo que permite identificar cada valor fácilmente. | espacio para la ejecicion|
| `.head(n)` | Muestra las primeras **n** filas de un DataFrame o Serie. Es útil para revisar rápidamente cómo están organizados los datos. | espacio para la ejecucion|
| `.dtypes` | Devuelve el tipo de dato de cada columna dentro del DataFrame (por ejemplo, int64, float64, object). | espacio para la ejecucion |
 `df['columna']` | Permite seleccionar una columna específica del DataFrame y devolverla como un objeto Series. Es la forma más común de acceder a un conjunto de datos dentro de la tabla. | espacio para ejecucion|
  `pd.read_csv('arch.csv')` |Es un archivo de texto donde los datos están organizados en filas y columnas, y cada valor está separado por comas (o punto y coma en algunos casos). Es uno de los formatos más comunes para guardar y compartir datos|espacio para ejecucion|