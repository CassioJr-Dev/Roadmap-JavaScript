# Funções em JavaScript

Este repositório aborda os conceitos fundamentais das funções em JavaScript. Abaixo estão explicações detalhadas e exemplos de código para ajudar a compreender como utilizar funções de maneira eficiente.

## Sumário
1. [Function Parameters](#function-parameters)
    - [Default Params](#default-params)
    - [Rest Params](#rest-params)
2. [Arrow Functions](#arrow-functions)
3. [IIFEs](#iifes)
4. [arguments object](#arguments-object)
5. [Scope & Function Stack](#scope-function-stack)
    - [Recursion](#recursion)
    - [Lexical Scoping](#lexical-scoping)
    - [Closures](#closures)
6. [Built-in Functions](#built-in-functions)

## Function Parameters

### Default Params

Os parâmetros padrão permitem que funções tenham valores predefinidos para seus parâmetros, caso nenhum valor seja fornecido durante a chamada da função.

```javascript
function greet(name = "Stranger") {
    return `Hello, ${name}!`;
}

console.log(greet()); // Output: Hello, Stranger!
console.log(greet("Alice")); // Output: Hello, Alice!
```

### Rest Params

Os parâmetros rest permitem que uma função lide com um número indefinido de argumentos como uma matriz.

```javascript
function sum(...numbers) {
    return numbers.reduce((acc, curr) => acc + curr, 0);
}

console.log(sum(1, 2, 3)); // Output: 6
console.log(sum(4, 5, 6, 7)); // Output: 22
```

## Arrow Functions

As arrow functions fornecem uma sintaxe mais curta e léxica para escrever funções em JavaScript. Elas não têm seu próprio `this`, `arguments`, `super`, ou `new.target`.

```javascript
const add = (a, b) => a + b;

console.log(add(2, 3)); // Output: 5

const double = n => n * 2;

console.log(double(4)); // Output: 8
```

## IIFEs

Uma IIFE (Immediately Invoked Function Expression) é uma função que é executada assim que é definida.

```javascript
(function() {
    console.log("This function runs immediately!");
})();

// Ou com sintaxe de arrow function
(() => {
    console.log("This arrow function runs immediately too!");
})();
```

## arguments object

O objeto `arguments` é uma coleção de argumentos passados para uma função, disponível dentro de funções regulares.

```javascript
function showArguments() {
    console.log(arguments);
}

showArguments(1, "two", [3], { four: 4 }); 
// Output: [Arguments] { '0': 1, '1': 'two', '2': [ 3 ], '3': { four: 4 } }
```

## Scope & Function Stack

### Recursion

A recursão é a técnica onde uma função se chama a si mesma.

```javascript
function factorial(n) {
    if (n <= 1) return 1;
    return n * factorial(n - 1);
}

console.log(factorial(5)); // Output: 120
```

### Lexical Scoping

O escopo léxico em JavaScript significa que o escopo das variáveis é determinado pela estrutura do código.

```javascript
function outer() {
    let outerVar = 'I am outside!';
    
    function inner() {
        console.log(outerVar); // Output: I am outside!
    }
    
    inner();
}

outer();
```

### Closures

Um closure é a combinação de uma função e o ambiente léxico dentro do qual essa função foi declarada.

```javascript
function makeCounter() {
    let count = 0;
    return function() {
        count++;
        return count;
    };
}

const counter = makeCounter();
console.log(counter()); // Output: 1
console.log(counter()); // Output: 2
```

Ambiente léxico é um contexto onde variáveis e funções são mapeadas para valores.
Escopo global é o ambiente léxico mais externo, acessível de qualquer lugar.
Escopo de função é um ambiente léxico criado quando uma função é definida e contém variáveis locais e parâmetros da função.
Closures preservam o ambiente léxico no qual foram criadas, permitindo acesso contínuo a variáveis nesse ambiente.

## Built-in Functions

JavaScript fornece várias funções internas úteis para manipulação de dados, execução de tarefas e muito mais.

```javascript
// parseInt
console.log(parseInt("123")); // Output: 123

// setTimeout
setTimeout(() => {
    console.log("This message appears after 2 seconds");
}, 2000);

// Math.random
console.log(Math.random()); // Output: Some random number between 0 and 1
```

## Contribuições

Contribuições são bem-vindas! Sinta-se à vontade para abrir uma issue ou enviar um pull request.

## Licença

Este projeto está licenciado sob a Licença MIT.
