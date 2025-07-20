1. **CREATE TRIGGER (Crear un disparador):**

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