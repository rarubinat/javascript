# javascript-apuntes

## Tabla de contenido

- [tipos de datos](#tipos-de-datos)
- [variables](#variables)
- [strings](#strings)


## tipos de datos

| Tipos | Ejemplo |
| ----- | ---- |
| undefined | Una variable a la que no se le ha asignado un valor es de tipo `undefined`. |
| null | No tiene valor |
| string | 'a', 'aaa', 'Hola', 'año 1922' |
| number | 12, -3, 0.4 |
| boolean | true, false |
| object | Colección de propiedades. |
| symbol | Identificador único. |

## variables


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

## strings

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

Secuencias de escape

| Código | Salida |
| ----- | ---- |
| \' | comillas simples (') |
| \" | comillas dobles (") |
| \\ | backslash (\) |
| \n | nueva línea |
| \r | carriage return |
| \t | tab |
| \b | backspace |
| \f | form feed |

Longitud de un string
```
'Alan Peter'.length //10
```

Split y Join
```
let str = 'a string'
let splittedStr = str.split('')
// [ 'a', ' ', 's', 't', 'r', 'i', 'n', 'g' ]
let joinedStr = splittedStr.join('')
// a string
```

Indice de una string
```
//el primer elemento tiene un índice de 0
var firstLetterOfFirstName = ''
var firstName = 'Ada'
firstLetterOfFirstName = firstName[0] // A
// encontrar el último carácter de un string
var firstName = 'Ada'
var lastLetterOfFirstName = firstName[firstName.length - 1] // a
```

Template literals
```
const person = {
  name: 'Zodiac Hasbro',
  age: 56,
}
// Template literal con interpolación de varias líneas y strings
const greeting = `Hello, my name is ${person.name}!
I am ${person.age} years old.`
console.log(greeting)
// Hello, my name is Zodiac Hasbro!
// I am 56 years old.
```

Arrays
```
var sandwich = ['peanut butter', 'jelly', 'bread'][
  // arrays anidados
  (['Bulls', 23], ['White Sox', 45])
]
```

Índice de un array
```
var ourArray = [50, 60, 70]
var ourData = ourArray[0] // 50
// modificar un array con índices
var ourArray = [50, 40, 30]
ourArray[0] = 15 // equals [15,40,30]
// acceder a matrices multidimensionales con índices
var arr = [
  [1, 2, 3],
  [4, 5, 6],
  [7, 8, 9],
  [[10, 11, 12], 13, 14],
]
arr[3] // [[10,11,12], 13, 14]
arr[3][0] // [10,11,12]
arr[3][0][1] // 11
```

Manipular arrays con reverse, push, pop shift y unshift
```
// reverse() le da la vuelta al array
;[1, 'two', 3].reverse() // [ 3, 'two', 1 ]
// push() añade un elemento al final del array
var arr = [1, 2, 3]
arr.push(4) // arr is now [1,2,3,4]
// pop() para eliminar el último valor del array
var threeArr = [1, 4, 6]
var oneDown = threeArr.pop()
console.log(oneDown) // 6
console.log(threeArr) // [1, 4]
// shift() elimina el primer elemento del array
var ourArray = [1, 2, [3]]
var removedFromOurArray = ourArray.shift()
// [2, [3]].
// unshift() añade un elemento al principio del array
var ourArray = ['Stimpson', 'J', 'cat']
ourArray.shift() // ["J", "cat"]
ourArray.unshift('Happy') // ["Happy", "J", "cat"]
```

Eliminar cualquier elemento
```
// el primer parámetro es el índice, el segundo indica el número de elementos a eliminar.
let array = ['today', 'was', 'not', 'so', 'great']
array.splice(2, 2)
// elimina 2 elementos empezando por el tercer elemento
// ['today', 'was', 'great']
// también devuelve un nuevo array que contiene el valor de los elementos eliminados
let array = ['I', 'am', 'feeling', 'really', 'happy']
let newArray = array.splice(3, 2) // ['really', 'happy']
// el tercer parámetro, representa uno o más elementos
function colorChange(arr, index, newColor) {
  arr.splice(index, 1, newColor)
  return arr
}
let colorScheme = ['#878787', '#a08794', '#bb7e8c', '#c9b6be', '#d1becf']
colorScheme = colorChange(colorScheme, 2, '#332327')
// hemos eliminado '#bb7e8c' y añadido '#332327' en su lugar
// colorScheme es ahora igual a ['#878787', '#a08794', '#332327', '#c9b6be', '#d1becf']
```

Copiar array
```
// Copia un número determinado de elementos a un nuevo array y deja el array original intacto
let weatherConditions = ['rain', 'snow', 'sleet', 'hail', 'clear']
let todaysWeather = weatherConditions.slice(1, 3)
// todaysWeather es igual a ['snow', 'sleet'];
// weatherConditions sigue siendo igual a ['rain', 'snow', 'sleet', 'hail', 'clear']
```

Acceso a array anidada
```
var ourPets = [
  {
    animalType: 'cat',
    names: ['Meowzer', 'Fluffy', 'Kit-Cat'],
  },
  {
    animalType: 'dog',
    names: ['Spot', 'Bowser', 'Frankie'],
  },
]
ourPets[0].names[1] // "Fluffy"
ourPets[1].names[0] // "Spot"
```

Saber si una array tiene un determinado elemento
```
let fruits = ['Banana', 'Orange', 'Apple', 'Mango']
fruits.includes('Mango') // true
```

Desestructuración de arrays para asignar variables
```
const [a, b] = [1, 2, 3, 4, 5, 6]
console.log(a, b) // 1, 2
// acceder a cualquier valor utilizando comas para llegar al índice deseado
const [a, b, , , c] = [1, 2, 3, 4, 5, 6]
console.log(a, b, c) // 1, 2, 5
// recoger el resto de los elementos en un array separado.
const [a, b, ...arr] = [1, 2, 3, 4, 5, 7]
console.log(a, b) // 1, 2
console.log(arr) // [3, 4, 5, 7]
```
