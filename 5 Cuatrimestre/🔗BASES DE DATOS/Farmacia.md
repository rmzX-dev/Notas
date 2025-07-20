Crear una base de datos en MongoDB  llamada Farmacia que contenga una colección llamada medicamentos y trabajar las siguiente consultas aplicando operadores relacionales y lógicos.

Imprimir todos los documentos de la colección 'medicamentos'.
```bash
db.medicamentos.find()
```
Recupere los medicamentos cuyo laboratorio sea 'Roche' y cuyo precio sea menor a 5, imprimir solo el laboratorio y precio.

```bash
db.medicamentos.find({ $and: [{ laboratorio: "Roche" }, { precio: { $lt: 5 } }] }, { laboratorio: 1, precio: 1, _id: 0 });
```
Recupere los medicamentos cuyo laboratorio sea 'Roche' o cuyo precio sea menor a 5.
```bash
db.medicamentos.find({ $and: [{ laboratorio: "Roche" }, { precio: { $lt: 5 } }] });
```
Muestre todos los medicamentos cuyo laboratorio NO sea "Bayer”, mostrando solo laboratorio
```bash
 db.medicamentos.find({laboratorio:{$ne:"Bayer"}}, {laboratorio: 1, _id: 0 })
```
Muestre todos los medicamentos cuyo laboratorio sea "Bayer" y cuya cantidad NO sea=100, mostrando laboratorio y cantidad
```bash
db.medicamentos.find({ $and:[ {laboratorio:{$eq:"Bayer"}}, { cantidad: { $ne: 100 } } ]} , { _id:0, laboratorio: 1, cantidad: 1 })
```
Elimine todos los documentos de la colección medicamentos cuyo laboratorio sea igual a "Bayer" y su precio sea mayor a 10
```bash
db.medicamentos.remove({$and:[{laboratorio: "Bayer"}, {precio: {$gt: 10}} ] })
```
Cambie la cantidad por 200, a todos los medicamentos de "Roche" cuyo precio sea mayor a 5 y muestre los documentos afectados
```bash
db.medicamentos.updateOne({ $and: [ { laboratorio: "Roche" }, { precio: { $lt: 5 } } ] },{ $set: { cantidad: 200 } })
```
Borre los medicamentos cuyo laboratorio sea "Bayer" o cuyo precio sea menor a 3.
```bash 
db.medicamentos.remove({$and:[ { laboratorio: "Bayer" },{ precio: {$lt: 3} } ]})
```
Cambiar el campo cantidad por stock a todos los documentos.
```bash
db.medicamentos.updateMany({},{ $rename: { "cantidad": "stock" }})
```
Modificar el precio de la Buscapina a 6.00
```bash
db.medicamentos.update({nombre: "Buscapina"}, {$set: { precio: 6.00 } })
```
Fijar el stock en 0 del artículo cuyo _id es 2.
```bash
db.medicamentos.updateOne({ _id: 2 },{ $set: { stock: 0 } })
```
Agregar el campo proveedores con el array ['Martinez','Gutierrez'] para el artículo cuyo _id es 6.
```bash
db.medicamentos.updateOne({ _id: 6 },{ $set: { proveedores: ["Martinez", "Gutierrez"] } })
```
Modificar el nombre de paracetamol 500 a Paracetamol 600 y eliminar el campo de cantidad.
```bash
db.medicamentos.updateOne({ nombre: "Paracetamol 500" },{ $set: { nombre: "Paracetamol 600" }, $unset: { cantidad: "" }})
```
Agregar el campo estatus a todos los documentos con valor true
```bash
db.medicamentos.updateMany({},{ $set: { estatus: true } })
```
Reemplazar el documento de amoxidal 500 con id:3 por un documento nuevo con los siguiente: id=3, nombre=penicilina, precio=99.50
```bash
db.medicamentos.replaceOne({ _id: 3 },{ _id: 3, nombre: "Penicilina", precio: 99.50 })
```
Exportar las colecciones a formato json y csv
Exportar a JSON
```bash
mongoexport --db=Farmacia --collection=medicamentos --out=medicamentos.json
```
Exportar a CSV
```bash
mongoexport --db=Farmacia --collection=medicamentos --type=csv --fields="_id,nombre,laboratorio,precio,cantidad" --out=medicamentos.csv
```


 "ubicacion": {
      "almacen": "E5",
      "estante": 1,
      "posicion": 7
    }