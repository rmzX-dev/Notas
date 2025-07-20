### **Servicios en Angular**

- **Definición**: Los servicios son clases que encapsulan lógica o datos reutilizables que pueden ser compartidos entre componentes.
- **Propósito**:
    - Facilitan la separación de responsabilidades, dejando la lógica de negocios fuera de los componentes.
    - Pueden manejar tareas como consumo de API, gestión de estado o procesamiento de datos.
- **Uso común**:
    1. Crear un servicio con el comando:
        
        ```bash
        ng generate service nombre-servicio
        ```
        
    2. Inyectar el servicio en un componente mediante **Dependency Injection (DI)**:
        
        ```typescript
        constructor(private miServicio: MiServicio) { }
        ```
        
- **Decorador**:  
    Los servicios suelen usar el decorador `@Injectable`, que permite que Angular los gestione como dependencias.

---

### **Promesas en Angular**

- **Definición**: Una **Promesa** es un objeto en JavaScript que representa la eventual resolución (o rechazo) de una operación asincrónica.
- **Características**:
    - Se ejecuta una única vez (no es reutilizable).
    - Ideal para operaciones simples como obtener datos de un API.
- **Sintaxis básica**:
    
    ```typescript
    this.miServicio.obtenerDatos().then(
      (resultado) => console.log(resultado),
      (error) => console.error(error)
    );
    ```
    
- **Ventajas**:
    - Simplicidad en operaciones lineales.
- **Limitaciones**:
    - Menos flexible que los Observables para trabajar con flujos de datos continuos.

---

### **Observadores (Observables) en Angular**

- **Definición**: Los Observables son parte de la librería RxJS y representan flujos de datos que se pueden observar con múltiples eventos a lo largo del tiempo.
- **Características**:
    - Reutilizables, pueden emitir múltiples valores.
    - Permiten manejar flujos de datos como clics, respuestas HTTP, o eventos en tiempo real.
- **Uso común en Angular**:
    - Muy utilizados con el módulo **HttpClient** para realizar solicitudes HTTP:
        
        ```typescript
        this.miServicio.obtenerDatos().subscribe(
          (data) => console.log(data),
          (error) => console.error(error)
        );
        ```
        
- **Ventajas**:
    - Compatible con operadores de RxJS para transformar y manipular datos.
    - Soporta flujos continuos y cancelación de suscripciones.
- **Operadores comunes de RxJS**:
    - `map`, `filter`, `mergeMap`, `switchMap`, entre otros.

---

### Diferencias entre Promesas y Observables:

|**Característica**|**Promesas**|**Observables**|
|---|---|---|
|**Ejecución**|Una vez|Múltiples veces|
|**Cancelación**|No es posible|Se puede cancelar|
|**Transformación de datos**|Limitada|Amplia con operadores RxJS|
|**Uso típico**|Operaciones únicas|Flujos de datos continuos|



Tarea 
1. Habilitar eliminar pedidos
2. Agregar 4 mesas independientes
3. Agregar ver pedidos en general

