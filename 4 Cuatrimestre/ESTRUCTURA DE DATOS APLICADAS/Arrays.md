 Un array(Arreglo) en java es una estructura de datos que nos permite almacenar un conjunto de datos de un mismo tipo. el tamaño de los arrays se declara en un primer momento y no puede cambiar luego durante la ejecución del programa, como si puede hacerse en otros lenguajes.

### **Sintaxis:**

```java
Tipo_de_variable[] Nombre_del_array = new tipo_de_variable[dimension]
```

### **Ejemplos:**

```java
byte[]edad = new byte[4];
short[]edad= new short[4];
int[]edad= new int[4];
long[]edad = new long[4];
float[]estatura = new float[3];
double[]estatura = new double[3];
boolean[]estado = new estado[5];
char[]sexo = new char[2];
String[] nombre = new String[2];
```

## **Clases y métodos de utilidad para trabajar con Arrays**

La clase java.util.Arrays proporciona varios métodos de utilidad que facilitan el manejo y la manipulación de arraya en java

## **Método toString()**

El método toString()se utiliza  para convertir un array en una representación de cadena legible. este método es útil cuando queremos imprimir o mostrar el contenido de un array.

```java
import java.util.Arrays;
public class ArraysExample {
    public static void main(String[] args) {
        int[] numbers = {1,2,3,4,5,6};
        System.out.println(Arrays.toString(numbers));
    }
}
```


### **Método short()**

El método sort() se utiliza para ordenar elementos de un array en orden ascendente. Este método es útil cuando necesitamos organizar los datos de un array en un orden especifico.

```java
import java.util.Arrays;
public class ArraySort {
    public static void main(String[] args) {
        int[] numbers = {1,2,3,4,5,6};
        Arrays.sort(numbers);
        System.out.println(Arrays.toString(numbers));
    }
}
```

### **Método equals**

El método equals() se utiliza para comparar dos arrays y determinar si son iguales. Dos arrays son iguales si contienen el mismo numero de elementos y todos los elementos.

```java
import java.util.Arrays;

public class ArraysEquals {
    public static void main(String[] args) {
    
        int[] ArrayUno = {1,2,3,4,5,6};
        int[] ArrayDos = {1,2,3,4,5,6};
        int[] ArrayTres = {6,5,4,3,2,1};
        
        boolean isEqual = Arrays.equals(ArrayUno, ArrayDos);
        System.out.println("¿Son iguales Array 1 y 2? \n" + isEqual);
        
        isEqual = Arrays.equals(ArrayUno, ArrayTres);
        System.out.println("¿Son iguales Array 1 y 3? \n" + isEqual);
    }
}
```


