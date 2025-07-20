# **PILAS**
**¿Qué son las pilas en programación?**
Una pila es una estructura de datos lineal que organiza los elementos de manera que el ultimo elemento añadido es el primero en ser eliminado. Esta característica sigue el principio de Last In, First Out(LIFO) que se puede comparar con una pila de platos de cafetería.

**Métodos principales de `Stack`**:

- `push(E e)`: Agrega un elemento a la cima de la pila.
- `pop()`: Retira y devuelve el elemento de la cima de la pila.
- `peek()`: Devuelve el elemento en la cima sin retirarlo.
- `isEmpty()`: Verifica si la pila está vacía.
- `search(Object o)`: Devuelve la posición del elemento desde la cima (1-indexado) o `-1` si no existe.

``` java
import java.util.Stack;

public class PilaSimple {
    public static void main(String[] args) {
        Stack<String> pila = new Stack<>();
        
        // Agregar elementos a la pila
        pila.push("Libro A");
        pila.push("Libro B");
        pila.push("Libro C");
        
        System.out.println("Pila inicial: " + pila);
        
        // Consultar el elemento en la cima
        System.out.println("Elemento en la cima: " + pila.peek());
        
        // Retirar elementos de la pila
        while (!pila.isEmpty()) {
            System.out.println("Retirando: " + pila.pop());
            System.out.println("Pila actual: " + pila);
        }
    }
}

```
# **COLAS**

 **¿Qué son las Colas en programación?**
Una cola en programación es una estructura de datos lineal que sigue el principio de FIFO(First In, First Out). Funciona como una fila virtual donde el primer elemento que se añade es el primero en ser eliminado.

**Métodos principales** de la interfaz `Queue`:

- `add(e)` / `offer(e)`: Agrega un elemento al final de la cola.
- `remove()` / `poll()`: Elimina y devuelve el elemento del frente de la cola.
- `peek()` / `element()`: Devuelve el elemento del frente sin eliminarlo.
- `isEmpty()`: Verifica si la cola está vacía.

```java
import java.util.LinkedList;
import java.util.Queue;

public class ColaSimple {
    public static void main(String[] args) {
        Queue<String> cola = new LinkedList<>();
        
        // Agregar elementos a la cola
        cola.offer("Juan");
        cola.offer("María");
        cola.offer("Luis");
        
        System.out.println("Cola inicial: " + cola);
        
        // Obtener el elemento del frente sin eliminarlo
        System.out.println("Frente de la cola: " + cola.peek());
        
        // Procesar elementos (eliminarlos en orden FIFO)
        while (!cola.isEmpty()) {
            System.out.println("Atendiendo a: " + cola.poll());
            System.out.println("Cola actual: " + cola);
        }
    }
}

```
# **LISTAS**
**¿Qué son las listas en programación?**
En programación, una lista es una estructura de datos que organiza y almacena elementos de manera secuencial y ordenada. Las listas permiten almacenar múltiples valores bajo un solo nombre y acceder a ellos mediante índices.

**Métodos principales**:

- `add(E e)`: Agrega un elemento al final de la lista.
- `add(int index, E e)`: Agrega un elemento en una posición específica.
- `get(int index)`: Obtiene el elemento en un índice específico.
- `set(int index, E e)`: Actualiza el valor en un índice.
- `remove(int index)`: Elimina el elemento en un índice.
- `size()`: Devuelve el tamaño de la lista.
- `isEmpty()`: Verifica si la lista está vacía.
- `contains(Object o)`: Verifica si un elemento existe en la lista.

```java
import java.util.ArrayList;
import java.util.List;

public class ListaSimple {
    public static void main(String[] args) {
        List<String> lista = new ArrayList<>();
        
        // Agregar elementos
        lista.add("Manzana");
        lista.add("Banana");
        lista.add("Cereza");
        System.out.println("Lista inicial: " + lista);
        
        // Obtener elementos por índice
        System.out.println("Elemento en el índice 1: " + lista.get(1));
        
        // Modificar un elemento
        lista.set(1, "Mango");
        System.out.println("Lista después de modificar: " + lista);
        
        // Eliminar un elemento
        lista.remove(0);
        System.out.println("Lista después de eliminar: " + lista);
        
        // Verificar si contiene un elemento
        System.out.println("¿Contiene 'Cereza'? " + lista.contains("Cereza"));
        
        // Tamaño de la lista
        System.out.println("Tamaño de la lista: " + lista.size());
    }
}
```

### **Arreglo**

En Java, un **arreglo** (array) es una estructura de datos que almacena una colección de elementos del mismo tipo en posiciones contiguas de memoria. Cada elemento se accede mediante un índice, que comienza desde 0.

---

### **Teoría**

1. **Características principales**:
    
    - Tamaño fijo: El tamaño de un arreglo se define al momento de su creación y no puede cambiar.
    - Índices: Los elementos se acceden por su posición (índice), comenzando desde 0.
    - Tipos homogéneos: Todos los elementos del arreglo deben ser del mismo tipo.
2. **Declaración y creación de un arreglo**:
    
    ```java
    tipo[] nombre = new tipo[tamaño];
    ```
    
    - Ejemplo: `int[] numeros = new int[5];`
3. **Inicialización**:
    
    - **Por defecto**: Se inicializan con valores predeterminados según el tipo (ej., `0` para enteros, `null` para objetos).
    - **Explícita**: Se pueden asignar valores al momento de su creación.
        
        ```java
        int[] numeros = {1, 2, 3, 4, 5};
        ```
        
4. **Métodos comunes**:
    
    - Longitud del arreglo: `nombre.length` devuelve el tamaño del arreglo.
    - Recorrido: Se puede usar un bucle `for`, `while` o un bucle `for-each`.

---

### **Práctica y ejemplos**

#### **1. Declarar, inicializar y recorrer un arreglo**

```java
public class ArregloBasico {
    public static void main(String[] args) {
        // Declaración e inicialización
        int[] numeros = {10, 20, 30, 40, 50};

        // Recorrer el arreglo con un bucle for
        System.out.println("Elementos del arreglo:");
        for (int i = 0; i < numeros.length; i++) {
            System.out.println("Índice " + i + ": " + numeros[i]);
        }
        
        // Recorrer con un bucle for-each
        System.out.println("Elementos usando for-each:");
        for (int numero : numeros) {
            System.out.println(numero);
        }
    }
}
```

**Salida**:

```
Elementos del arreglo:
Índice 0: 10
Índice 1: 20
Índice 2: 30
Índice 3: 40
Índice 4: 50
Elementos usando for-each:
10
20
30
40
50
```

---

#### **2. Encontrar el valor máximo en un arreglo**

```java
public class ArregloMaximo {
    public static void main(String[] args) {
        int[] numeros = {5, 8, 12, 3, 7, 19, 4};
        int maximo = numeros[0];

        for (int numero : numeros) {
            if (numero > maximo) {
                maximo = numero;
            }
        }
        
        System.out.println("El valor máximo es: " + maximo);
    }
}
```

**Salida**:

```
El valor máximo es: 19
```

---

#### **3. Sumar todos los elementos de un arreglo**

```java
public class ArregloSuma {
    public static void main(String[] args) {
        int[] numeros = {2, 4, 6, 8, 10};
        int suma = 0;

        for (int numero : numeros) {
            sum a += numero;
        }
        
        System.out.println("La suma de los elementos es: " + suma);
    }
}
```

**Salida**:

```
La suma de los elementos es: 30
```

---

#### **4. Buscar un elemento en un arreglo**

```java
public class ArregloBusqueda {
    public static void main(String[] args) {
        int[] numeros = {15, 22, 8, 19, 31};
        int objetivo = 19;
        boolean encontrado = false;

        for (int numero : numeros) {
            if (numero == objetivo) {
                encontrado = true;
                break;
            }
        }
        
        System.out.println("¿El número " + objetivo + " está en el arreglo? " + encontrado);
    }
}
```

**Salida**:

```
¿El número 19 está en el arreglo? true
```

---

#### **5. Ordenar un arreglo (usando Arrays.sort)**

```java
import java.util.Arrays;

public class ArregloOrdenar {
    public static void main(String[] args) {
        int[] numeros = {42, 15, 8, 23, 4};

        // Ordenar el arreglo en orden ascendente
        Arrays.sort(numeros);

        System.out.println("Arreglo ordenado:");
        for (int numero : numeros) {
            System.out.println(numero);
        }
    }
}
```

**Salida**:

```
Arreglo ordenado:
4
8
15
23
42
```

---

#### **6. Arreglo bidimensional (matrices)**

Un arreglo bidimensional es una tabla o matriz.

```java
public class Matriz {
    public static void main(String[] args) {
        int[][] matriz = {
            {1, 2, 3},
            {4, 5, 6},
            {7, 8, 9}
        };

        System.out.println("Elementos de la matriz:");
        for (int i = 0; i < matriz.length; i++) {
            for (int j = 0; j < matriz[i].length; j++) {
                System.out.print(matriz[i][j] + " ");
            }
            System.out.println(); // Salto de línea para cada fila
        }
    }
}
```

**Salida**:

```
Elementos de la matriz:
1 2 3
4 5 6
7 8 9
```

---

### **Ventajas y desventajas de los arreglos**

|**Ventajas**|**Desventajas**|
|---|---|
|Acceso rápido por índice (O(1)).|Tamaño fijo: no se puede cambiar dinámicamente.|
|Estructura simple y directa.|No es adecuado para inserciones o eliminaciones frecuentes.|
|Ideal para datos homogéneos.|Menos flexible que colecciones como `ArrayList`.|

---

### **Cuándo usar arreglos**

- Cuando el tamaño de los datos es conocido y fijo.
- Cuando se necesita acceso rápido a elementos por su índice.
- Cuando se prioriza el rendimiento en comparación con estructuras dinámicas.

### **Recursividad** 

La **recursividad** en programación es una técnica donde una función se llama a sí misma para resolver un problema. Un problema recursivo se descompone en subproblemas más pequeños y similares hasta alcanzar un caso base que pueda resolverse sin recurrencia.

-

### **Teoría**

1. **Elementos clave de la recursión**:
    
    - **Caso base**: Condición que detiene la recursión. Evita que la función se llame indefinidamente.
    - **Llamada recursiva**: Parte de la función que vuelve a llamarse a sí misma con parámetros más simples o reducidos.
2. **Tipos de recursividad**:
    
    - **Directa**: Una función se llama a sí misma.
    - **Indirecta**: Una función llama a otra, que eventualmente llama de nuevo a la primera.
3. **Ventajas**:
    
    - Simplifica problemas complejos (como árboles, divisiones y combinaciones).
    - Útil para problemas con una estructura naturalmente recursiva (factoriales, Fibonacci, recorrido de árboles).
4. **Desventajas**:
    
    - Puede consumir mucha memoria por el uso de la pila de llamadas.
    - No es eficiente si no se utiliza memoización o técnicas de optimización.

---

### **Ejemplos prácticos**

#### **1. Factorial de un número**

El factorial de un número nn (denotado como n!n!) es el producto de todos los números enteros desde 1 hasta nn.

**Código**:

```java
public class RecursionFactorial {
    public static void main(String[] args) {
        int numero = 5;
        System.out.println("Factorial de " + numero + ": " + factorial(numero));
    }

    public static int factorial(int n) {
        if (n == 0 || n == 1) { // Caso base
            return 1;
        }
        return n * factorial(n - 1); // Llamada recursiva
    }
}
```

**Salida**:

```
Factorial de 5: 120
```

---

#### **2. Serie de Fibonacci**

La serie de Fibonacci comienza con 0 y 1, y cada número subsiguiente es la suma de los dos anteriores.

**Código**:

```java
public class RecursionFibonacci {
    public static void main(String[] args) {
        int n = 7;
        System.out.println("Fibonacci de " + n + ": " + fibonacci(n));
    }

    public static int fibonacci(int n) {
        if (n == 0) { // Caso base 1
            return 0;
        }
        if (n == 1) { // Caso base 2
            return 1;
        }
        return fibonacci(n - 1) + fibonacci(n - 2); // Llamada recursiva
    }
}
```

**Salida**:

```
Fibonacci de 7: 13
```

---

#### **3. Recorrer una lista recursivamente**

**Código**:

```java
import java.util.List;
import java.util.ArrayList;

public class RecursionLista {
    public static void main(String[] args) {
        List<String> nombres = new ArrayList<>();
        nombres.add("Ana");
        nombres.add("Juan");
        nombres.add("María");

        System.out.println("Recorrido de la lista:");
        recorrerLista(nombres, 0);
    }

    public static void recorrerLista(List<String> lista, int index) {
        if (index == lista.size()) { // Caso base
            return;
        }
        System.out.println(lista.get(index));
        recorrerLista(lista, index + 1); // Llamada recursiva
    }
}
```

**Salida**:

```
Recorrido de la lista:
Ana
Juan
María
```

---

#### **4. Potencia de un número**

Calcula baseexponentebase^exponente usando recursión.

**Código**:

```java
public class RecursionPotencia {
    public static void main(String[] args) {
        int base = 2, exponente = 5;
        System.out.println(base + "^" + exponente + ": " + potencia(base, exponente));
    }

    public static int potencia(int base, int exponente) {
        if (exponente == 0) { // Caso base
            return 1;
        }
        return base * potencia(base, exponente - 1); // Llamada recursiva
    }
}
```

**Salida**:

```
2^5: 32
```

---

#### **5. Búsqueda binaria recursiva**

**Código**:

```java
import java.util.Arrays;

public class RecursionBusquedaBinaria {
    public static void main(String[] args) {
        int[] array = {1, 3, 5, 7, 9, 11};
        int objetivo = 7;
        int resultado = busquedaBinaria(array, objetivo, 0, array.length - 1);
        System.out.println("Elemento encontrado en el índice: " + resultado);
    }

    public static int busquedaBinaria(int[] array, int objetivo, int inicio, int fin) {
        if (inicio > fin) { // Caso base
            return -1;
        }
        int medio = (inicio + fin) / 2;
        if (array[medio] == objetivo) {
            return medio;
        } else if (array[medio] > objetivo) {
            return busquedaBinaria(array, objetivo, inicio, medio - 1); // Llamada recursiva izquierda
        } else {
            return busquedaBinaria(array, objetivo, medio + 1, fin); // Llamada recursiva derecha
        }
    }
}
```

**Salida**:

```
Elemento encontrado en el índice: 3
```

---

### **Ventajas y desventajas de la recursividad**

|**Ventajas**|**Desventajas**|
|---|---|
|Simplifica el código en problemas complejos.|Consume más memoria (uso de pila de llamadas).|
|Ideal para estructuras como árboles.|Puede ser menos eficiente que iteraciones.|
|Mejora la legibilidad en ciertos casos.|Es fácil caer en bucles infinitos sin un caso base claro.|

### **Cuándo usar recursividad**

- Cuando el problema tiene una estructura jerárquica o divisoria (árboles, divisiones).
- Cuando la solución recursiva es más clara que una iterativa.
- Si el tamaño del problema es pequeño (evitando límites de la pila).