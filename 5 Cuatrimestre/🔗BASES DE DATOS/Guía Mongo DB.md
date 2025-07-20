## **Guía de Estudio: MongoDB**

### **1. Conceptos Básicos de MongoDB**
- **¿Qué es MongoDB?**
  - Base de datos NoSQL orientada a documentos.
  - Almacena datos en formato BSON (similar a JSON).
  - No requiere un esquema fijo.
- **Estructura de MongoDB:**
  - **Base de datos**: Contenedor de colecciones.
  - **Colección**: Grupo de documentos (similar a una tabla en SQL).
  - **Documento**: Unidad básica de datos (similar a una fila en SQL).

---

### **2. Operaciones Básicas**
- **Iniciar el servidor de MongoDB:**
  ```bash
  mongod
  ```
- **Conectarse a la shell de MongoDB:**
  ```bash
  mongosh
  ```
- **Crear o usar una base de datos:**
  ```javascript
  use NombreBaseDeDatos
  ```
  - Si la base de datos no existe, se crea automáticamente al insertar datos.

---

### **3. Colecciones y Documentos**
- **Crear una colección:**
  ```javascript
  db.createCollection("NombreColeccion")
  ```
- **Insertar documentos:**
  - Insertar un documento:
    ```javascript
    db.NombreColeccion.insertOne({ campo: valor })
    ```
  - Insertar varios documentos:
    ```javascript
    db.NombreColeccion.insertMany([{ campo1: valor1 }, { campo2: valor2 }])
    ```

---

### **4. Consultas Básicas**
- **Recuperar todos los documentos de una colección:**
  ```javascript
  db.NombreColeccion.find()
  ```
- **Filtrar documentos:**
  - Por campo específico:
    ```javascript
    db.NombreColeccion.find({ campo: valor })
    ```
  - Usando operadores relacionales (`$eq`, `$lt`, `$gt`, `$ne`, etc.):
    ```javascript
    db.NombreColeccion.find({ campo: { $gt: valor } })
    ```



 
---

### **5. Operadores Relacionales y Lógicos**
- **Operadores relacionales:**
  - `$eq`: Igual a.
  - `$ne`: No igual a.
  - `$lt`: Menor que.
  - `$lte`: Menor o igual que.
  - `$gt`: Mayor que.
  - `$gte`: Mayor o igual que.
  - `$in`: Dentro de un conjunto de valores.
  - `$nin`: No dentro de un conjunto de valores.
- **Operadores lógicos:**
  - `$and`: Cumple todas las condiciones.
  - `$or`: Cumple al menos una condición.
  - `$not`: Niega una condición.
- **Ejemplos:**
  - Recuperar documentos que cumplen múltiples condiciones:
    ```javascript
    db.NombreColeccion.find({ $and: [{ campo1: valor1 }, { campo2: { $gt: valor2 } }] })
    ```

---

### **6. Actualización de Documentos**
- **Actualizar un documento:**
  ```javascript
  db.NombreColeccion.updateOne({ criterio }, { $set: { campo: nuevoValor } })
  ```
- **Actualizar varios documentos:**
  ```javascript
  db.NombreColeccion.updateMany({ criterio }, { $set: { campo: nuevoValor } })
  ```
- **Reemplazar un documento:**
  ```javascript
  db.NombreColeccion.replaceOne({ criterio }, nuevoDocumento)
  ```
- **Ejemplos:**
  - Cambiar un campo específico:
    ```javascript
    db.medicamentos.updateOne({ nombre: "Buscapina" }, { $set: { precio: 6.00 } })
    ```
  - Renombrar un campo:
    ```javascript
    db.medicamentos.updateMany({}, { $rename: { "cantidad": "stock" } })
    ```

---

### **7. Eliminación de Documentos**
- **Eliminar un documento:**
  ```javascript
  db.NombreColeccion.deleteOne({ criterio })
  ```
- **Eliminar varios documentos:**
  ```javascript
  db.NombreColeccion.deleteMany({ criterio })
  ```
- **Ejemplos:**
  - Eliminar documentos que cumplen una condición:
    ```javascript
    db.medicamentos.deleteMany({ laboratorio: "Bayer" })
    ```

---

### **8. Operaciones Avanzadas**
- **Agregar un nuevo campo a todos los documentos:**
  ```javascript
  db.NombreColeccion.updateMany({}, { $set: { nuevoCampo: valor } })
  ```
- **Eliminar un campo de todos los documentos:**
  ```javascript
  db.NombreColeccion.updateMany({}, { $unset: { campoAEliminar: "" } })
  ```
- **Exportar datos:**
  - A JSON:
    ```bash
    mongoexport --db=NombreBaseDeDatos --collection=NombreColeccion --out=archivo.json
    ```
  - A CSV:
    ```bash
    mongoexport --db=NombreBaseDeDatos --collection=NombreColeccion --type=csv --fields=campo1,campo2 --out=archivo.csv
    ```

---

