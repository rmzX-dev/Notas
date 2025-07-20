1. **Primera Forma Normal (1NF):**
    
    - En 1NF, cada columna de una tabla debe contener un solo valor atómico, es decir, no debe haber valores repetidos o múltiples valores en una sola celda.
    - Todos los atributos de una tabla deben ser atómicos, es decir, no deben ser arrays, listas o conjuntos.
    - No debe haber columnas calculadas o derivadas; estas deben calcularse cuando sea necesario.
2. **Segunda Forma Normal (2NF):**
    
    - Para cumplir con 2NF, primero debe estar en 1NF.
    - Además, cada atributo no clave de la tabla debe ser completamente dependiente de la clave primaria. Esto significa que si una tabla tiene una clave primaria compuesta, cada atributo que no sea parte de esa clave debe depender de la totalidad de la clave, no solo de una parte de ella.
    - Si hay atributos que dependen solo de una parte de la clave primaria, se deben mover a una nueva tabla junto con esa parte de la clave.
3. **Tercera Forma Normal (3NF):**
    
    - Para cumplir con 3NF, primero debe estar en 2NF.
    - Además, no debe haber dependencias transitivas entre los atributos no clave. Esto significa que si un atributo no clave depende de otro atributo no clave, pero no directamente de la clave primaria, entonces debe moverse a una nueva tabla.