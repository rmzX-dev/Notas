## **Arreglos bidimensionales**
Es una matriz de datos de datos de tamaño m x n que contiene información almacenada del mismo tipo de datos- este tipo de arreglos necesita dos subíndices para ser declarados o para acceder a la información de un elemento en especifico, a diferencia de una matriz unidimensional que solo necesita un subíndice. 

La sintaxis para declarar e inicializar un array bidimensional será:
```java
tipo_dato nombre_arreglo [tamaño_fila][tamaño_columna];
```
Donde:
- **tipo_dato:** nos referimos al tipo de datos que estaremos manejando en el arreglo, puede ser char, int, float, etc.
- **nombre_arreglo:** El nombre con el que identifícanos nuestra matriz.
- **tamaño_fila:** La cantidad de filas que tendrá nuestra matriz.
- **tamaño_columna:** La cantidad de columna que tendrá nuestra matriz.

Si queremos crear una matriz  de 3 filas y 4 columnas de tipo de dato int y con nombre "arreglo", lo haríamos de la siguiente manera:

```java
int[] arreglo = new int [3][4]
```

Esta matriz tendría 12 espacios para guardar información (3x4), y gráficamente lo veríamos de la siguiente manera: 

| Matriz | Columna 1    | Columna 2    | Columna 3    | Columna 4    |
| ------ | ------------ | ------------ | ------------ | ------------ |
| Fila 0 | Matriz[0][0] | Matriz[0][1] | Matriz[0][2] | matriz[0][3] |
| Fila 1 | Matriz[1][0] | Matriz[1][1] | Matriz[1][2] | Matriz[1][3] |
| Fila 2 | Matriz[2][0] | Matriz[2][1] | Matriz[2][2] | Matriz[2][3] |

También puede expresarse como una constante simbólica, ya sea las dos dimensiones o solo una de ellas. 

```java
public static final R = 10;
public static final c = 6;

matriz = new boolean[R][C];
```

```java
public class main {
    public static void main(String[] args) {
        int[][] matriz = new int [5][3];
        
        int x = matriz.length;
        int y = matriz[2].length;

        System.out.println(x);
        System.out.println(y);
    }
}
```

## **Matrices cuadradas**
Una matriz cuadrada es aquella que tiene el mismo numero de renglones como de columnas. son las matrices que mas se utilizan en el algebra, pues tienen ciertas propiedades que les permiten ser usadas en operaciones como la suma de matrices. 

## **Matrices no cuadradas**
Otro tipo de matrices son las no cuadradas, son aquellas en donde el numero de renglones no son iguales al numero de columnas. Puede darse el caso que tenga mas renglones que columnas o al revés. 

 