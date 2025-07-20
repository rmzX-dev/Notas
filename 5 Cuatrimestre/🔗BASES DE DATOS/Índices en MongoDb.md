### ¿Qué es un índice en MongoDB?
Un índice en MongoDB es una estructura que almacena una pequeña porción de los datos de la colección en un formato fácil de recorrer. Los índices se construyen sobre campos específicos de los documentos en una colección y permiten que las consultas que filtran por esos campos sean más eficientes.

### ¿Cómo crear un índice en MongoDB?

#### 1. Crear un índice simple
```javascript
db.nombre_de_la_coleccion.createIndex({ campo: 1 });
```
**Ejemplo:**

```javascript
db.persona.createIndex({ email: 1 });
```

#### 2. Crear un índice compuesto

```javascript
db.nombre_de_la_coleccion.createIndex({ campo1: 1, campo2: -1 });
```

**Ejemplo:**

```javascript
db.usuarios.createIndex({ nombre: 1, edad: -1 });
```

#### 3. Crear un índice único

```javascript
db.nombre_de_la_coleccion.createIndex({ campo: 1 }, { unique: true });
```

**Ejemplo:**

```javascript
db.persona.createIndex({ age: 1 }, { unique: true });
```

#### 4. Crear un índice TTL (Time-To-Live)
```javascript
db.nombre_de_la_coleccion.createIndex({ campo: 1 }, { expireAfterSeconds: 3600 });
```

**Ejemplo:**

```javascript
db.logs.createIndex({ fechaCreacion: 1 }, { expireAfterSeconds: 3600 });
```

### ¿Cómo visualizar los índices en MongoDB?
`getIndexes()`:

```javascript
db.nombre_de_la_coleccion.getIndexes();
```

**Ejemplo:**

```javascript
db.usuarios.getIndexes();
```

### Ejemplo de salida de `getIndexes()`
```json
[
    {
        "v" : 2,
        "key" : {
            "_id" : 1
        },
        "name" : "_id_",
        "ns" : "mi_basedatos.usuarios"
    },
    {
        "v" : 2,
        "key" : {
            "email" : 1
        },
        "name" : "email_1",
        "ns" : "mi_basedatos.usuarios",
        "unique" : true
    }
]
```

- `v`: Versión del índice.
- `key`: Campo(s) sobre el cual se creó el índice.
- `name`: Nombre del índice.
- `ns`: Namespace (base de datos y colección).
- `unique`: Indica si el índice es único.

### Eliminar un índice
`dropIndex()`:

```javascript
db.nombre_de_la_coleccion.dropIndex("nombre_del_indice");
```

**Ejemplo:**

```javascript
db.persona.dropIndex("email_1");
```
