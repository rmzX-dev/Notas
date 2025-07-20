1. **Índice simple:**
```sql
CREATE INDEX idx_nombre_columna ON nombre_tabla (nombre_columna);
```

2. **Índice compuesto:**
```sql
CREATE INDEX idx_columnas_compuestas ON nombre_tabla (columna1, columna2);
```

3. **Índice único:**
```sql
CREATE UNIQUE INDEX idx_nombre_unico ON nombre_tabla (nombre_columna);
```

4. **Índice de clave primaria:**
```sql
ALTER TABLE nombre_tabla ADD PRIMARY KEY (nombre_columna);
```

5. **Índice de clave foránea:
```sql
ALTER TABLE tabla_hija ADD CONSTRAINT fk_nombre_constraint FOREIGN KEY (nombre_columna) REFERENCES tabla_padre(nombre_columna);
```

6. **Índice de texto completo:**
```sql
CREATE INDEX idx_texto_completo ON nombre_tabla USING GIN (columna_texto gin_trgm_ops);
```

7. **Índice espacial:**
```sql
CREATE INDEX idx_espacial ON nombre_tabla USING GIST (geometria);
```

8. **Índice filtrado:**
```sql
CREATE INDEX idx_filtrado ON nombre_tabla (columna) WHERE columna_condicion;
```

9. **Índice de función:**
```sql
CREATE INDEX idx_funcion ON nombre_tabla (LOWER(columna));
```
