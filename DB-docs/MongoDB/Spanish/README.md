# MongoDB

- 💃 MongoDB tiene mucha flexibilidad y no nos impone seguir una estructura o esquema bien definido.
- 🙅 SQL nos impone una estructura bien definida a más no poder; es super no-flexible.
- 🍻 Con MongoDB es más fácil empezar y añadir nuevas funcionalidades.
- ⏲ Con SQL es más demorado de empezar porque debemos tener el orden super claro siempre. Todos los elementos deben tener los mismos elementos y todos deben ser del mismo tipo. Si queremos agregar un nuevo campo debemos añadirlo en todas partes con un valor pode defecto, aunque no lo necesitemos.
- 🤒 Si no seguimos buenas prácticas en MongoDB, vamos a necesitar queries ultra-complejas, demoradas y una visita diaria al psicólogo 😱.
- 💆 El orden impuesto de SQL no es por nada. Las queries son fáciles de entender porque todo sigue su orden y tranquilidad. Aunque, implementar nuevas features toma su buen tiempo 🤔.

## Operadores de Mongo

~~~
- $eq       =
- $gt       >
- $gte      >=
- $lt       <
- $lte      <=
- $ne       !=
- $in         Valores dentro de un rango.
- $nin        Valores que no estan dentro de un rango.
- $and        Une queries con un AND logico.
- $not        Invierte el efecto de un query.
- $nor        Une queries con un NOR logico.
- $or         Une queries con un OR logico.
- $exist      Documentos que cuentan con un campo especifico.
- $type       Documentos que cuentan con un campo de un tipo especifico.
- $all        Arreglos que contengan todos los elementos del query
- $elemMatch  Documentos que cumplen la condicion del - $elemMatch en uno de sus elementos.
- $size       Documentos que contienen un campo tipo arreglo de un tamaño especifico.
~~~

## Uso

Ya con nuestro cluster creado desde [Mongo Atlas](https://www.mongodb.com/cloud/atlas1).

- Conectamos copiando el link de enlace en nuestra terminal.

- `show dbs` (para observar nuestras bases de datos actuales).

- `use <nombreDeLaBase>` (para crear una nueva bases de datos o entrar en una ya existente).

- Escribimos `db` para asegurarnos de que se creo correctamente.

- Ahora insertamos el siguiente comando para crear un collection.

```
db.inventory.insertOne(
        { item: "canvas", qty: 100, tags: ["cotton"], size: { h: 28, w: 35.5, uom: "cm" } }
)
```

- `show collections` (nos mostrará las colecciones que tenemos creadas).

- Para ver información sobre el documento podemos filtrar con la función `findOne()`.

```
db.inventory.findOne()
```

- Para conectarnos desde la interfaz [MongoDB Compass](https://www.mongodb.com/products/compass).

- Debemos conectarnos usando nuestro usuario y password y enlazando nuestro link.


- Base de datos: 

  - Contenedor físico de colecciones.

  - Cada base de datos tiene su archivo propio en el sistema de archivos.

  - Un cluster puede tener múltiples bases de datos.

- Colecciones:

  - Agrupación de documentos.

  - Equivalente a una tabla en las bases de datos relacionales.

  - No impone un esquema.

- Documentos:

  - Un registro dentro de una colección.

  - Es análogo a un objeto JSON (BSON).

  - La unidad básica dentro de MongoDB.


- Para crear una colección (opcional) y añadir un elemento en formato JSON: `db.NOMBRE_COLECCIÓN.insertOne({ ... })`. La base de datos responde true si la operación fue exitosa y crea el campo irrepetible de _id si nosotros no lo especificamos.

- Crear una colección (opcional) y añadir algunos elementos en formato JSON: `db.NOMBRE_COLECCIÓN.insertMany([{ ... }, { ... }])`. Recibe un array de elementos y devuelve todos los IDs de los elementos que se crearon correctamente.

- Encontrar elementos en una colección: `db.NOMBRE_COLECCIÓN.find()`.

- Para un elemento en especifico podemos aplicar lo siguiente `db.inventory.find({item: "canvas"})`. A esto se le puede agregar un metodo `pretty()` para ver mejor el resultado en consola.

- También podemos aplicar un `count()` para saber cuantos elementos nos retorna nuestra operación.

- Podemos aplicar filtros si queremos encontrar solo el primer resultado con el método `findOne()`.

- A esta metodo tambien podemos aplicarle filtros.

- Listar todos los posibles comandos que podemos ejecutar: `db.NOMBRE_COLECCIÓN.help()`.