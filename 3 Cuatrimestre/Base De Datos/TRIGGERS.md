### 1. Disparadores de Nivel de Fila

```sql
CREATE OR REPLACE TRIGGER trg_nivel_fila
BEFORE INSERT OR UPDATE OR DELETE
ON tabla
FOR EACH ROW
BEGIN
  -- Código PL/SQL del cuerpo del disparador
END;
```

**Descripción**: Este tipo de disparador se ejecuta una vez por cada fila afectada por una operación DML (INSERT, UPDATE o DELETE). Es útil para aplicar lógica específica a nivel de fila, como validar o modificar datos antes de que sean insertados, actualizados o eliminados.

### 2. Disparadores de Nivel de Instrucción

```sql
CREATE OR REPLACE TRIGGER trg_nivel_instruccion
BEFORE INSERT OR UPDATE OR DELETE
ON tabla
BEGIN
  -- Código PL/SQL del cuerpo del disparador
END;
```

**Descripción**: Este tipo de disparador se ejecuta una vez para cada instrucción DML, independientemente del número de filas afectadas. Es útil para aplicar lógica que no depende de las filas afectadas, como validar permisos o realizar acciones generales antes o después de una operación.

### 3. Disparadores Before y After

**Antes de la instrucción:**
```sql
CREATE OR REPLACE TRIGGER trg_before
BEFORE INSERT OR UPDATE OR DELETE
ON tabla
BEGIN
  -- Código PL/SQL del cuerpo del disparador
END;
```

**Después de la instrucción:**
```sql
CREATE OR REPLACE TRIGGER trg_after
AFTER INSERT OR UPDATE OR DELETE
ON tabla
BEGIN
  -- Código PL/SQL del cuerpo del disparador
END;
```

**Descripción**: Los disparadores "Before" se ejecutan antes de que se realice la operación, mientras que los "After" se ejecutan después de que la operación ha tenido lugar. Son útiles para realizar validaciones previas o posteriores a la operación, o para llevar a cabo acciones dependiendo del resultado de la operación.

### 4. Disparadores Instead Of

```sql
CREATE OR REPLACE TRIGGER trg_instead_of
INSTEAD OF INSERT OR UPDATE OR DELETE
ON vista
BEGIN
  -- Código PL/SQL del cuerpo del disparador
END;
```

**Descripción**: Este tipo de disparador se utiliza en vistas y permite definir qué acciones deben realizarse en lugar de las operaciones de inserción, actualización o eliminación en la vista. Es útil para manejar operaciones en vistas que no son directamente actualizables.

### 5. Disparadores de Esquema

```sql
CREATE OR REPLACE TRIGGER trg_esquema
AFTER CREATE OR ALTER OR DROP
ON SCHEMA
BEGIN
  -- Código PL/SQL del cuerpo del disparador
END;
```

**Descripción**: Estos disparadores se activan cuando se realizan operaciones a nivel de esquema, como crear, alterar o eliminar objetos. Son útiles para auditar cambios en la estructura de la base de datos o para aplicar políticas de seguridad adicionales.

### 6. Disparadores de Nivel de Base de Datos

```sql
CREATE OR REPLACE TRIGGER trg_db_level
AFTER STARTUP OR SHUTDOWN OR SERVERERROR OR LOGON OR LOGOFF
ON DATABASE
BEGIN
  -- Código PL/SQL del cuerpo del disparador
END;
```

**Descripción**: Estos disparadores se activan por eventos de la base de datos, como inicios de sesión, cierres, errores, etc. Son útiles para realizar tareas de mantenimiento automáticas o llevar a cabo auditorías a nivel de base de datos.