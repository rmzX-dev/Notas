### **Iniciar servidor local**

```bash
mongod
```

### Iniciar Shell de MongoDB

```bash
mongosh
```

### Crear o usar una base de datos

**Nota:** Si la base de datos no existe, se creará automáticamente al insertar datos.

```javascript
use Prueba
```

### Crear una colección dentro de la base de datos

```javascript
db.createCollection("Usuarios")
```

### Insertar un dato en la colección

```javascript
db.Usuarios.insertOne({})
```

### Insertar varios datos en la colección

```javascript
db.Usuarios.insertMany([
  {}, {}, {}, {}
])
```

### Insertar múltiples datos generados dinámicamente

```javascript
// Crear un array vacío para almacenar los documentos
var documentos = [];

// Generar 200 objetos vacíos
for (let i = 1; i <= 200; i++) {
  documentos.push({});
}

// Insertar todos los documentos en la colección
db.Usuarios.insertMany(documentos);
```

### Consultar todos los datos de la colección

```javascript
db.Usuarios.find()
```

### Eliminar la colección

```javascript
db.getCollection("Usuarios").drop()
```

### Trabajar con cursores en MongoDB

```javascript
// Configurar el tamaño del lote (opcional, depende del entorno)
Config.set("displayBatchSize", 5)

// Crear un cursor con la consulta
var cursor = db.Usuarios.find()

// Verificar si hay más documentos en el cursor
cursor.hasNext()

// Verificar cuántos objetos quedan en el lote actual
cursor.objsLeftInBatch()

// Convertir el cursor a un array
cursor.toArray()
```

### Operaciones adicionales

1. **Contar documentos en la colección:**
    
    ```javascript
    db.Usuarios.find().count()
    ```
    
    **Descripción:** Devuelve el número total de documentos en la colección `Usuarios`.
    
2. **Ordenar documentos en orden descendente por `_id`:**
    
    ```javascript
    db.Usuarios.find().sort({ _id: -1 })
    ```
    
3. **Limitar la consulta a 5 documentos:**
    
    ```javascript
    db.Usuarios.find().limit(5)
    ```
    
4. **Saltar los primeros 10 documentos:**
    
    ```javascript
    db.Usuarios.find().skip(10)
    ```
    

---

### Práctica 1: Biblioteca

#### Insertar libros en la colección `Libro`

```json
db.Libro.insertMany([
    {
        Titulo: "Clean Code: A Handbook of Agile Software Craftsmanship",
        Autor: "Robert C. Martin",
        ISBN: "9780132350884",
        Edicion: "Primera",
        Editorial: "Prentice Hall",
        AñoPublicacion: "2008"
    },
    {
        Titulo: "Design Patterns: Elements of Reusable Object-Oriented Software",
        Autor: "Erich Gamma, Richard Helm, Ralph Johnson, John Vlissides",
        ISBN: "9780201633610",
        Edicion: "Primera",
        Editorial: "Addison-Wesley",
        AñoPublicacion: "1994"
    },
    {
        Titulo: "The Pragmatic Programmer: Your Journey To Mastery",
        Autor: "Andrew Hunt, David Thomas",
        ISBN: "9780135957059",
        Edicion: "20th Anniversary Edition",
        Editorial: "Addison-Wesley",
        AñoPublicacion: "1999"
    }
]);
```

#### Insertar usuarios en la colección `Usuario`

```javascript
db.Usuario.insertMany([
    {
        Nombre: "Aaron",
        FechaNacimiento: "14/11/2005",
        Telefono: "2713173310",
        Direccion: {
            numeroCasa: 4,
            calle: "Carlos Castillo Peraza",
            Colonia: "San Jose",
            Ciudad: "Fortin"
        }
    },
    {
        Nombre: "Beatriz",
        FechaNacimiento: "22/08/1992",
        Telefono: "2713142058",
        Direccion: {
            numeroCasa: 15,
            calle: "Avenida Reforma",
            Colonia: "Centro",
            Ciudad: "Fortin"
        }
    },
    {
        Nombre: "Carlos",
        FechaNacimiento: "05/02/1988",
        Telefono: "2713157789",
        Direccion: {
            numeroCasa: 32,
            calle: "Avenida 5 de Febrero",
            Colonia: "Las Palmas",
            Ciudad: "Fortin"
        }
    }
]);
```

### Consultas de ejemplo

- **Buscar libro por título:**
    
    ```javascript
    db.Libro.find({ Titulo: "Clean Code: A Handbook of Agile Software Craftsmanship" })
    ```
    
- **Buscar libros por editorial, omitiendo el campo `_id`:**
    
    ```javascript
    db.Libro.find({ Editorial: "Addison-Wesley" }, { _id: 0 })
    ```
    
- **Buscar libros ordenados por título en orden descendente:**
    
    ```javascript
    db.Libro.find({}, { Titulo: 1 }).sort({ Titulo: -1 });
    ```
    
- **Eliminar todos los documentos de la colección `Libro`:**
    
    ```javascript
    db.Libro.remove({})
    ```
    

---

### Importar datos

```bash
mongoimport --jsonArray --db banco --collection persona --file C:\Users\aaron\Downloads\queries.json
```

### Operadores relacionales

- `$eq` - Igual
- `$lt` - Menor que
- `$lte` - Menor o igual que
- `$gt` - Mayor que
- `$gte` - Mayor o igual que
- `$ne` - Distinto
- `$in` - Dentro de
- `$nin` - No dentro de

### Ejemplos de consultas con operadores

1. **Buscar personas con edad menor a 27:**
    
    ```bash
    db.persona.find({ age: { $lt: 27 }})
    ```

 db.Productos.find( {$ne: { rubro: "impresora" }} )
 
1. **Buscar personas con edad entre 30 y 35:**
    
    ```bash
    db.persona.find({ age: { $gt: 30, $lt: 35 } })
    ```
    
2. **Buscar personas mayores de 20 y menores de 50, mostrando solo edad y apellido, ordenados por apellido:**
    
    ```bash
    db.persona.find({ age: { $gt: 20, $lt: 50 } }, { age: 1, "name.last": 1, _id: 0 }).sort({ "name.last": -1 });
    ```
    
3. **Buscar personas con color de ojos verde y edad ≥33, mostrando solo color de ojos y edad:**
    
    ```bash
    db.persona.find({ $and: [{ eyeColor: "green" }, { age: { $gte: 33 } }] }, { _id: 0, eyeColor: 1, age: 1 }).sort({ age: 1 });
    ```
    
4. **Contar personas con color de ojos café o nombre "Geneva":**
    
    ```bash
    db.persona.find({ $or: [{ eyeColor: "brown" }, { "name.first": "Geneva" }] }, { _id: 0, eyeColor: 1, "name.first": 1 });
    ```
    
5. **Buscar personas con edad >35 o fruta favorita "apple":**
    
    ```bash
    db.persona.find({ $and: [{ age: { $gt: 35 } }, { favoriteFruit: "apple" }] }, { _id: 0, age: 1, favoriteFruit: 1 });
    ```
    
6. **Buscar personas cuya fruta favorita no sea "apple":**
    
    ```bash
    db.persona.find({ favoriteFruit: { $ne: "apple" } }, { _id: 1, favoriteFruit: 1 });
    ```
    

```bash
db.medicamento({})

db.persona.find({ $and: [{ laboratorio: "Roche" }, { precio: { $lt: 5 } }] });
```
### Actualizaciones y eliminaciones

- **Actualizar un documento:**
    
    ```javascript
    db.collection.updateOne({ criterio }, { $set: { campo: valor } })
    ```
    
- **Actualizar varios documentos:**
    
    ```javascript
    db.collection.updateMany({ criterio }, { $set: { campo: valor } })
    ```
    
- **Reemplazar un documento:**
    
    ```javascript
    db.collection.replaceOne({ criterio }, nuevoDocumento)
    ```
    
- **Eliminar un documento:**
    
    ```javascript
    db.collection.remove({ criterio })
    ```
    
- **Eliminar varios documentos:**
    
    ```javascript
    db.collection.deleteMany({ criterio })
    ```



```





db.articulos.insertOne(
  {
    _id: 1,  
    nombre: 'MULTIFUNCION HP DESKJET 2675',
    rubro: 'impresora',
    precio: 3000,
    stock: 20 
  }
)
db.articulos.insertOne(
  {
    _id: 2,  
    nombre: 'MULTIFUNCION EPSON EXPRESSION XP241',
    rubro: 'impresora',
    precio: 3700,
    stock: 5 
  }
)
db.articulos.insertOne(
  {
    _id: 3,  
    nombre: 'LED 19 PHILIPS',
    rubro: 'monitor',
    precio: 4500,
    stock: 2
  }
)
db.articulos.insertOne(
  {
    _id: 4,  
    nombre: 'LED 22 PHILIPS',
    rubro: 'monitor',
    precio: 5700,
    stock: 4
  }
)
db.articulos.insertOne(
  {
    _id: 5,  
    nombre: 'LED 27 PHILIPS',
    rubro: 'monitor',
    precio: 12000,
    stock: 1
  }
)

db.articulos.insertOne(
  {
    _id: 6,  
    nombre: 'LOGITECH M90',
    rubro: 'mouse',
    precio: 300,
    stock: 4
  }
)

```