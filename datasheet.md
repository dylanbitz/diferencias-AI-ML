| Comando | Definición | Ejecución |
|--------------|:------------:|-------------:|
| Fila 1, Col 1 | Fila 1, Col 2 | Fila 1, Col 3 |
| Fila 2, Col 1 | Fila 2, Col 2 | Fila 2, Col 3 |

##D-pandas-avanzado
1. Filtros DataFrame

| Comando | Definición | Ejecución |
|---------|:------------:|-----------:|
| `df[condition]` | Filtra filas que cumplen una condición lógica sobre una o varias columnas.|df[df["Venta"] > 200] Filtra las filas donde la columna Venta es mayor a 200|
| `df.query('condicion')` | Filtrar filas usando expresiones en texto, util cuadno la condicion es compleja o es mas legible en formato de cadena|df.query('Ciudad == "Bogota" and Mes == "Agosto") Es este caso muestra las ventas en bogota durante el mes de agosto|

2. Groupby

| Comando | Definición | Ejecución |
|---------|:------------:|-----------:|
| `df.groupby('columna')` | Agrupar los datos por una columna para realizar opperaciones como suma, promedio, conteo, etc... | df.groupby("Ciudad")["Venta"].sum() Hace la suma total de ventas por ciudad|
| `df.gruopby(['col1','col2'])` | Agrupar por mas de una columna, permitiendo un analisis combinado | df.groupby(["Ciudad","Mes"])["Venta"].mean() Promedio de ventas por ciudad y mes |
| `.agg({'columna':'función'})` | Aplica funciones personalizadas como sum, max, min a columnas específicas.| df.groupby("Ciudad").agg({"Venta":"max"}) Muestra la venta más alta por ciudad |

3. Merge / Join

| Comando | Definición | Ejecución |
|---------|:------------:|-----------:|
| `pd.merge(df1, df2, on='columna', how='tipo')` | Une dos DataFrames en uno solo basándose en una columna clave. how define el tipo de unión: inner, left, right u outer. | pd.merge(df_ventas, df_clientes, on="ID_Cliente", how="left") Une ventas con clientes, manteniendo todos los registros de ventas.

4. Manejo de valores nulo

| Comando | Definición | Ejecución |
|---------|:------------:|-----------:|
|`df.isnull()` | Devuelve un DataFrame booleano indicando qué posiciones están vacías (NaN) | df.isnull() |
|`df.fillna(valor)` |Rellena los valores nulos con un valor específico, como texto, número o resultado calculado|df["Ciudad"].fillna("Desconocido")|
|`df.dropna()`|Elimina las filas que contengan valores nulos |df.dropna()|
|`df["col"].fillna(df["col"].mean())`|Reemplaza valores nulos con el promedio de esa columna |df["Venta"].fillna(df["Venta"].mean())|

5. Exportacion / Importacion

| Comando | Definición | Ejecución |
|---------|:------------:|-----------:|
|`df.to_csv('archivo.csv', index=False)` |Guarda el DataFrame en un archivo CSV para uso posterior | df.to_csv("ventas.csv", index=False) |
|`pd.read_csv('archivo.csv')` | RCarga datos desde un archivo CSV en un DataFrame | df["Vedf = pd.read_csv("ventas.csv") |
|`df.to_excel('archivo.xlsx')` | Exporta el DataFrame a un archivo de Excel | df.to_excel("ventas.xlsx", index=False) |
|`pd.read_excel('archivo.xlsx')`| Importa datos desde un archivo de Excel a un DataFrame | df = pd.read_excel("ventas.xlsx") |
