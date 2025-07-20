### DML (Data Manipulation Language):

1. **SELECT**: 
   ```sql
   SELECT column1, column2 FROM table_name WHERE condition;
   ```

2. **INSERT**: 
   ```sql
   INSERT INTO table_name (column1, column2) VALUES (value1, value2);
   ```

3. **UPDATE**: 
   ```sql
   UPDATE table_name SET column1 = value1 WHERE condition;
   ```

4. **DELETE**: 
   ```sql
   DELETE FROM table_name WHERE condition;
   ```

### DDL (Data Definition Language):

1. **CREATE TABLE**: 
   ```sql
   CREATE TABLE table_name (
   column1 datatype,
   column2 datatype,    ...
   );
   ```

2. **ALTER TABLE** (para modificar la estructura de la tabla):
   ```sql
   ALTER TABLE table_name ADD column_name datatype;
   ```


3. **DROP TABLE**: 
   ```sql
   DROP TABLE table_name;
   ```

4. **CREATE INDEX**: 
   ```sql
   CREATE INDEX index_name ON table_name (column_name);
   ```

5. **ALTER INDEX**: 
   ```sql
   ALTER INDEX index_name RENAME TO new_index_name;
   ```

6. **DROP INDEX**: 
   ```sql
   DROP INDEX index_name;
   ```

1. **CREATE TRIGGER:**

```sql
CREATE TRIGGER registro_empleados
BEFORE INSERT ON empleados
FOR EACH ROW
BEGIN
    INSERT INTO registro_inserciones (fecha_hora) VALUES (NOW());
END;
```

2. **CREATE FUNCTION (Crear una función):**

```sql
CREATE FUNCTION calcular_salario_anual(salario_mensual DECIMAL(10, 2), meses_trabajados INT)
RETURNS DECIMAL(10, 2)
BEGIN
    DECLARE salario_anual DECIMAL(10, 2);
    SET salario_anual = salario_mensual * meses_trabajados * 12;
    RETURN salario_anual;
END;
```

3. **CREATE VIEW (Crear una vista):**

```sql
CREATE VIEW empleados_antiguos AS
SELECT nombre, apellido, antiguedad
FROM empleados
WHERE antiguedad >= 5;
```