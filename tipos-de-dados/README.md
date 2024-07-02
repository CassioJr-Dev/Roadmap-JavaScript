# Tipos de Dados em JavaScript

## Sumário

1. [Tipos Primitivos](#tipos-primitivos)
2. [Operador typeof](#operador-typeof)
3. [Objeto](#objeto)
4. [Objetos Integrados](#objetos-integrados)
5. [Protótipo de Objeto](#protótipo-de-objeto)
6. [Herança Prototípica](#herança-prototípica)

## Tipos Primitivos

Em JavaScript, existem seis tipos primitivos de dados:

- **String**: representa sequências de caracteres, por exemplo, `"Olá, mundo!"`.
    ```javascript
    let mensagem = "Olá, mundo!";
    console.log(mensagem);
- **Undefined**: representa um valor não definido, normalmente atribuído automaticamente a variáveis não inicializadas.
    ```javascript
    let valorIndefinido;
    console.log(typeof valorIndefinido); // Output: "undefined"

- **Number**: representa números, sejam inteiros ou de ponto flutuante, por exemplo, `42` ou `3.14`.
    ```javascript
    let numero = 42;
    console.log(numero); // Output: 42

    let pi = 3.14;
    console.log(pi); // Output: 3.14

- **BigInt**: representa números inteiros de precisão arbitrária, por exemplo, `9007199254740991n`.
    ```javascript
    let numeroGrande = 9007199254740991n;
    console.log(numeroGrande); // Output: 9007199254740991n

- **Boolean**: representa valores lógicos `true` ou `false`.
    ```javascript
    let verdadeiro = true;
    let falso = false;
    console.log(verdadeiro); // Output: true
    console.log(falso); // Output: false

- **Null**: representa a ausência intencional de qualquer valor ou objeto, por exemplo, `null`.
    ```javascript
    let valorNulo = null;
    console.log(valorNulo); // Output: null

- **Symbol**: representa valores únicos e imutáveis, frequentemente usados como identificadores de propriedades de objetos.
    ```javascript
    let id = Symbol("id");
    let objeto = {
        [id]: "12345"
    };
    console.log(objeto[id]); // Output: "12345"

## Operador typeof

- **typeof**: O operador `typeof` é usado para obter o tipo de dado de uma expressão em JavaScript. Retorna uma string indicando o tipo de dado. 
    ```javascript
     let valor = 42;
     console.log(typeof valor); // Output: "number"

## Objeto

- **Object**:Em JavaScript, objetos são entidades complexas que possuem propriedades e métodos. 
    ```javascript
    let pessoa = {
        nome: "João",
        idade: 30,
        saudacao: function() {
            return "Olá, meu nome é " + this.nome + " e tenho " + this.idade + " anos.";
        }
    };

    console.log(pessoa.saudacao()); // Output: "Olá, meu nome é João e tenho 30 anos."


### Objetos Integrados

JavaScript possui vários objetos integrados que fornecem métodos e propriedades úteis. Exemplos incluem `Array`, `Date`, `Math`, entre outros.

### Protótipo de Objeto

- Todos os objetos em JavaScript são descendentes de `Object`; todos os objetos herdam métodos e propriedades do `Object.prototype`, embora possam ser sobrescritos.

    ```javascript
    function Carro(marca, modelo) {
        this.marca = marca;
        this.modelo = modelo;
    }

    Carro.prototype.informacoes = function() {
        return this.marca + " " + this.modelo;
    };

    let meuCarro = new Carro("Honda", "Civic");
    console.log(meuCarro.informacoes()); // Output: "Honda Civic"

- Aqui está o exemplo de código onde um método não é compartilhado por todas instâncias da função construtora.
    ```javascript
    function Carro(marca, modelo) {
        this.marca = marca;
        this.modelo = modelo;
    }

    let meuCarro = new Carro("Honda", "Civic");

    meuCarro.informacoes = function() {
        return this.marca + " " + this.modelo;
    };

    console.log(meuCarro.informacoes()); // Output: "Honda Civic"

O prototype é usado principalmente para habilitar a herança em JavaScript. Quando uma função é usada como construtora (new Carro()), o objeto resultante (meuCarro) herda propriedades e métodos definidos no prototype da função (Carro.prototype).


### Herança Prototípica

- JavaScript utiliza um modelo de herança baseado em protótipos, onde os objetos podem herdar propriedades de outros objetos.

    ```javascript
    // Objeto 'Animal' com um método 'walk'
    let Animal = {
        walk: function() {
            console.log(this.name + ' está andando.');
        }
    };

    // Objeto 'Dog' que herda de 'Animal'
    let Dog = Object.create(Animal);
    Dog.bark = function() {
        console.log(this.name + ' está latindo.');
    };

    // Criando uma instância de 'Dog'
    let myDog = Object.create(Dog);
    myDog.name = 'Buddy';

    myDog.walk(); // Saída: Buddy está andando.
    myDog.bark(); // Saída: Buddy está latindo.