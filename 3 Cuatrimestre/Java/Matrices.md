#### Matrices
 
Una matriz necesita ser declarada, al igual que una variable, con el tipo de los elementos que contendrá.

Para declarar una matriz, es necesario definir el tipo de los elementos con **corchetes**.

```java
int[ ] ages;
```

 
Ahora, para crear la matriz, tenemos que especificar el número de elementos que contendrá utilizando la palabra clave `<b>new</b>`:

```JAVA
int[ ] ages;
ages = new int[5];
```

El código anterior crea una matriz de 5 enteros.

Podemos combinar el código anterior en una sola línea:

```JAVA
int[] ages = new int[5];
```

El acceso a los elementos de una matriz se realiza mediante su posición, también llamada **índice**.

Este es un ejemplo, en el que se establece el elemento con el índice 2 al valor 25:

```JAVA
ages[2] = 25;
```

El elemento con índice 2 es en realidad el tercer elemento de la matriz. 

Esto se debe a que los índices de las matrices comienzan desde 0, lo que significa que el índice del primer elemento es 0 en lugar de uno. Así, el índice máximo de la matriz int[5] es 4. 

Establezcamos el valor de los primeros elementos:

```JAVA
ages[0] = 18;
```


De forma similar a la fijación de valores, también podemos acceder a los valores de la matriz, utilizando corchetes y el índice del elemento al que queremos acceder:

```JAVA
public class Demo {
    public static void main(String[] args) {
        int[] ages = new int[5];
        ages[0] = 18;
        ages[2] = 25;
        System.out.println(ages[2]);
    }
}```

Al crear una matriz, tenemos que proporcionar el tipo de los elementos y el tamaño de la matriz, así:

```JAVA
int[] nums = new int[4];
```

El acceso a los elementos de la matriz se realiza mediante sus índices, colocados entre corchetes. El primer elemento tiene el índice 0.

También puedes crear una matriz con valores utilizando la siguiente sintaxis:

```JAVA
int[] nums = {4, 6, 2, 1};
```

En la próxima lección aprenderemos a hacer un bucle sobre los valores de una matriz y a realizar cálculos.

Vamos a aprender cómo generar los elementos de una matriz utilizando un bucle.

Para utilizar un bucle, primero tenemos que averiguar cuántos elementos almacena la matriz. 

Para ello, la matriz tiene una propiedad `<b>length</b>`, a la que se accede así:

```JAVA
public class Demo {
    public static void main(String[] args) {
        int[] ages = {18, 33, 24, 64, 45};
        System.out.println(ages.length);
    }
}
```

