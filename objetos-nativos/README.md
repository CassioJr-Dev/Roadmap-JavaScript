# Classes Nativas em JavaScript

Este README tem como objetivo descrever as classes nativas Array, Object, Promise, Date e Math em JavaScript, com conceitos e exemplos para cada uma delas.

## Sumário

1. [Array](#array)
2. [Object](#object)
3. [Promise](#promise)
4. [Date](#date)
5. [Math](#math)

# Array

A classe Array é utilizada para criar e manipular arrays em JavaScript. Arrays são objetos de alto nível semelhantes a listas.

## Conceitos
- Criação de Arrays: Array, Array.of, Array.from
- Métodos de Array: push, pop, shift, unshift, map, filter, reduce, forEach, find, findIndex, etc.
- Propriedade length: Indica o número de elementos no array.

## Exemplos

```javascript
// Criação de Arrays
let arr1 = [1, 2, 3];
let arr2 = new Array(4, 5, 6);
let arr3 = Array.of(7, 8, 9);
let arr4 = Array.from([10, 11, 12]);

// Métodos de Array
arr1.push(4); // [1, 2, 3, 4]
arr2.pop(); // [4, 5]
arr3.shift(); // [8, 9]
arr4.unshift(9); // [9, 10, 11, 12]

let mappedArray = arr1.map(x => x * 2); // [2, 4, 6, 8]
let filteredArray = arr2.filter(x => x > 4); // [5]
let reducedValue = arr3.reduce((acc, val) => acc + val, 0); // 17
arr4.forEach(x => console.log(x)); // 9 10 11 12

let foundElement = arr1.find(x => x === 3); // 3
let foundIndex = arr1.findIndex(x => x === 3); // 2

console.log(arr1.length); // 4
```

# Object

A classe Object é a base para todos os objetos em JavaScript. Ela fornece métodos para criar, manipular e estender objetos.

## Conceitos

- Criação de Objetos: Literais, Object.create, new Object
- Métodos de Object: assign, keys, values, entries, freeze, seal, etc.
- Propriedade prototype: Permite adicionar propriedades e métodos a objetos.

## Exemplos

```javascript
// Criação de Objetos
let obj1 = { a: 1, b: 2 };
let obj2 = new Object({ c: 3, d: 4 });
let obj3 = Object.create(obj1);
obj3.e = 5;

// Métodos de Object
let obj4 = Object.assign({}, obj1, obj2); // { a: 1, b: 2, c: 3, d: 4 }
let keys = Object.keys(obj1); // ['a', 'b']
let values = Object.values(obj1); // [1, 2]
let entries = Object.entries(obj1); // [['a', 1], ['b', 2]]

Object.freeze(obj1);
obj1.a = 10; // Não faz nada, pois o objeto está congelado

Object.seal(obj2);
delete obj2.c; // Não faz nada, pois o objeto está selado

console.log(obj1);
console.log(obj2);
console.log(obj3);
console.log(obj4);
```

# Promise

A classe Promise é usada para lidar com operações assíncronas em JavaScript. Uma promessa representa um valor que pode estar disponível agora, no futuro ou nunca.

## Conceitos

- Criação de Promises: new Promise
- Métodos de Promise: then, catch, finally, all, race, resolve, reject
- Estados da Promise: pending, fulfilled, rejected

## Exemplos

```javascript
// Criação de Promises
let promise = new Promise((resolve, reject) => {
  setTimeout(() => resolve('Success'), 1000);
});

// Métodos de Promise
promise
  .then(result => console.log(result)) // 'Success' após 1 segundo
  .catch(error => console.log(error))
  .finally(() => console.log('Promise finalizada'));

let promise1 = Promise.resolve(1);
let promise2 = Promise.resolve(2);
let promise3 = Promise.reject('Error');

Promise.all([promise1, promise2]).then(values => console.log(values)); // [1, 2]
Promise.race([promise1, promise3]).then(value => console.log(value)).catch(error => console.log(error)); // 1
```

# Date

A classe Date é usada para trabalhar com datas e horários em JavaScript.

## Conceitos

- Criação de Datas: new Date, Date.now, Date.parse, Date.UTC
- Métodos de Date: getFullYear, getMonth, getDate, getHours, getMinutes, getSeconds, toISOString, etc.
- Manipulação de Datas: Adição e subtração de tempo.

## Exemplos

```javascript
// Criação de Datas
let now = new Date();
let specificDate = new Date('2024-07-29T10:20:30Z');
let timestamp = Date.now();

// Métodos de Date
console.log(now.getFullYear()); // 2024
console.log(now.getMonth()); // 6 (julho, pois os meses são baseados em zero)
console.log(now.getDate()); // 29
console.log(now.getHours()); // 10
console.log(now.getMinutes()); // 20
console.log(now.getSeconds()); // 30
console.log(now.toISOString()); // '2024-07-29T10:20:30.000Z'

// Manipulação de Datas
let futureDate = new Date();
futureDate.setDate(futureDate.getDate() + 10); // Adiciona 10 dias
console.log(futureDate);

let pastDate = new Date();
pastDate.setHours(pastDate.getHours() - 5); // Subtrai 5 horas
console.log(pastDate);
```

# Math

A classe Math fornece funções e constantes matemáticas.

## Conceitos

- Constantes de Math: Math.PI, Math.E, Math.LN10, etc.
- Métodos de Math: abs, ceil, floor, max, min, random, round, sqrt, pow, etc.

## Exemplos

```javascript
// Constantes de Math
console.log(Math.PI); // 3.141592653589793
console.log(Math.E); // 2.718281828459045

// Métodos de Math
console.log(Math.abs(-10)); // 10
console.log(Math.ceil(1.4)); // 2
console.log(Math.floor(1.4)); // 1
console.log(Math.max(1, 2, 3)); // 3
console.log(Math.min(1, 2, 3)); // 1
console.log(Math.random()); // Número aleatório entre 0 e 1
console.log(Math.round(1.5)); // 2
console.log(Math.sqrt(16)); // 4
console.log(Math.pow(2, 3)); // 8
```