
# Crud y consultas en MongoDB

## Crear una Base de Datos
Solo se crea si contiene por lo menos una 
colección

**use bd1** 

## Como crear una coleccion
use bd1
db.createCollection("Empleado")
        
## Mostrar las colecciones 
show collections

## Insertar un Documento
```json
db.alumnos.insertOne(
{
   nombre: 'Soyla',
   apellido1: 'Vaca',
   edad: 32,
   ciudad: 'San Miguel de las Piedras'
}
)
```

## Inserción de un documento mas complejo con array

```json
db.alumnos.insertOne(
{
  nombre: "Joquin",
apellido: "Dorian",
apellido2: "Guerrero",
edad: 15,
aficiones: [ 'Cerveza', 'Hueva',"Canabis"]
})
```

## Inserción de documentos mas complejos con documentos anidados y ID

``` json
db.alumnos.insertOne(
{
      nombre: 'Jose Luis',
      apellido1: "Herrera",
      apellido2: "Gallardo",
      edad: 41,
      estudios: [
               'Ing en Sistemas Computacionales',
               'Maestria en Tecnologías de Información'
             ],
  experiencia: {
                 lenguaje: 'SQl',
                 sbd: "SQL Server",
                 aniosExp: 14
              }
}
)

db.alumnos.insertOne({
    _id: 3, 
    nombre: 'Sergio', 
    apellido: 'Ramos', 
    equipo: 'Monterrey', 
    aficiones: [ 'Dinero', 'Hombres', 'Fiesta' ], 
    talentos: {
        futbol: true, 
        bañarse: false
    }
}
)
```

## Insertar Multiples documentos

```json
db.alumnos.insertMany(
   [
     {
         _id: 12,
         nombre: 'Roberto',
         apellido: 'Gomez',
         edad: "23",
         descripcion: "Es un comediante bueno"
     },
     {
         nombre: 'Luis',
         apellido: "Suarez",
         edad: 43,
         habilidades: [
                       'Correr', 'dormir', 'Morder'
                      ],
        direcciones: {
                         calle: 'Del infierno',
                         numero: 666
                     },
        esposas: [
                     {
                   nombre: "Marisol",
                   edad: 20,
                   pension: 350
                   , hijos: ['Joaquin', 'Bridget']
                     },
                    {
                       nombre: "Dorien",
                       edad: 46,
                       pension: 6500.56,
                       complaciente: true
                    }
                ]
  }
]
)
```

# Practica

1. Bases de Datos, colecciones e inserts

    . Nos conectamos con mongosh al mongodb 
    . Crear una base de datos denominada curso
    
    ``json
    use curso
    ```
    . Verificar que la base de datos no existe 

   
    show bds
    

    . Crear una colección denominada "facturas" con el comando createCollection 
      y comprobar que aparece tanto la colección como la base de datos