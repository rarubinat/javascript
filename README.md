# javascript-apuntes

## Tabla de contenido

- [tipos de datos](#tipos-de-datos)
- [variables](#variables)
- [strings](#strings)


##tipos de datos

| Tipos | Ejemplo |
| ----- | ---- |
| undefined | Una variable a la que no se le ha asignado un valor es de tipo `undefined`. |
| null | No tiene valor |
| string | 'a', 'aaa', 'Hola', 'año 1922' |
| number | 12, -3, 0.4 |
| boolean | true, false |
| object | Colección de propiedades. |
| symbol | Identificador único. |

##variables


```
// declara una variable
var ourName
// almacena valores
myNumber = 5
myString = 'myVar'
// declarar variables con el operador de asignación
var myNum = 0
// sumar, restar, multiplicar y dividir
myVar = 5 + 10 // 15
myVar = 12 - 6 // 6
myVar = 13 * 13 // 169
myVar = 16 / 2 // 8
// incrementar o decrecer el valor
i++ // the equivalent of i = i + 1
i-- // the equivalent of i = i - 1;
// decimales
var ourDecimal = 5.7 // float
```
A diferencia de var, let arroja un error si se declara la misma variable dos veces.

- Las variables declaradas con `let` dentro de un bloque, sentencia o expresión, su alcance está limitado a ese bloque, sentencia o expresión.
- Las variables declaradas con `const` son de sólo lectura y no pueden ser reasignadas.
- Los objetos (incluyendo `arrays` y `funciones`) asignados a una variable usando const siguen siendo mutables y sólo se impide la reasignación del identificador de la variable.
- Para asegurar que los datos no cambian, JavaScript proporciona una `función Object.freeze` para prevenir la mutación de datos.

```
let obj = {
  name: 'FreeCodeCamp',
  review: 'Awesome',
}
Object.freeze(obj)
obj.review = 'bad' //se ignorará. Mutación no permitida
obj.newProp = 'Test' //se ignorará. Mutación no permitida
console.log(obj)
// { name: "FreeCodeCamp", review: "Awesome"}
```

##strings

```
// escapar de las comillas literales
var sampleStr = 'Alan dijo: "Pedro está aprendiendo JavaScript".'
// esto imprime: Alan dijo, "Peter está aprendiendo JavaScript".
// concatenar string
var ourStr = 'Yo voy primero. ' + 'Yo soy el segundo.'
// concatenando strings con +=
var ourStr = 'Yo voy primero. '
nuestroStr += 'Vengo segundo.'
// construyendo strings con variables
var ourName = 'freeCodeCamp'
var ourStr = 'Hola, nuestro nombre es ' + ourName + ', ¿cómo estás?'
// añadiendo variables a strings
var anAdjective = 'Impresionante'
var ourStr = 'freeCodeCamp es '
ourStr += anAdjective
```
