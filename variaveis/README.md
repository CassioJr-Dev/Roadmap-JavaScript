# Variáveis em JavaScript

Este README cobre conceitos básicos sobre variáveis em JavaScript, incluindo declaração de variáveis, hoisting, regras de nomenclatura e escopos de variáveis. Esses conceitos são fundamentais para o desenvolvimento em JavaScript e fornecem uma base sólida para a criação de código eficiente e livre de erros.

## Índice

1. [Declaração de Variáveis](#declaração-de-variáveis)
2. [Hoisting](#hoisting)
3. [Regras de Nomenclatura de Variáveis](#regras-de-nomenclatura-de-variáveis)
4. [Escopos de Variáveis](#escopos-de-variáveis)

## Declaração de Variáveis

Em JavaScript, as variáveis podem ser declaradas usando três palavras-chave: `var`, `let` e `const`.

- **var**: Utilizada desde as primeiras versões do JavaScript. Variáveis declaradas com `var` têm escopo de função ou escopo global.

    ```javascript
    var x = 10;
    console.log(x); // 10
    ```

- **let**: Introduzida no ES6 (ECMAScript 2015). Possui escopo de bloco, o que significa que é limitada ao bloco onde foi declarada.

    ```javascript
    let y = 20;
    if (true) {
        let y = 30;
        console.log(y); // 30
    }
    console.log(y); // 20
    ```

- **const**: Também introduzida no ES6. É utilizada para declarar constantes, ou seja, variáveis cujo valor não pode ser reatribuído. Possui escopo de bloco.

    ```javascript
    const z = 40;
    // z = 50; // Isso causará um erro
    console.log(z); // 40
    ```

## Hoisting

Hoisting é um comportamento do JavaScript onde declarações de variáveis e funções são movidas para o topo do seu escopo antes da execução do código. Isso significa que você pode utilizar uma variável ou função antes de sua declaração no código.

- **var**: Com `var`, a declaração é içada, mas a inicialização não é içada.

    ```javascript
    console.log(a); // undefined
    var a = 10;
    console.log(a); // 10
    ```

- **let e const**: Com `let` e `const`, a declaração é içada, mas a inicialização não. Usar a variável antes da declaração resulta em um erro `ReferenceError`.

    ```javascript
    console.log(b); // ReferenceError
    let b = 20;
    console.log(b); // 20
    ```

    ```javascript
    console.log(c); // ReferenceError
    const c = 30;
    console.log(c); // 30
    ```

## Regras de Nomenclatura de Variáveis

Para declarar variáveis em JavaScript, você deve seguir algumas regras de nomenclatura:

1. **Iniciar com uma letra, underscore (_) ou cifrão ($)**: Não pode começar com um número.
    ```javascript
    let _myVar;
    let $myVar;
    let myVar1;
    ```

2. **Caracteres permitidos**: Letras, números, underscore (_) e cifrão ($).

3. **Sensível a maiúsculas e minúsculas**: `myVar` e `myvar` são variáveis diferentes.

4. **Palavras reservadas**: Não pode usar palavras reservadas como `let`, `const`, `var`, `function`, etc.

    ```javascript
    let function; // SyntaxError
    ```

## Escopos de Variáveis

JavaScript tem três tipos de escopo: global, de função e de bloco.

- **Escopo Global**: Variáveis declaradas fora de qualquer função ou bloco têm escopo global. Elas são acessíveis em qualquer parte do código.

    ```javascript
    var globalVar = "I'm global";
    console.log(globalVar); // I'm global
    ```

- **Escopo de Função**: Variáveis declaradas dentro de uma função têm escopo de função e só são acessíveis dentro daquela função.

    ```javascript
    function myFunction() {
        var functionVar = "I'm local to the function";
        console.log(functionVar); // I'm local to the function
    }
    console.log(functionVar); // ReferenceError
    ```

- **Escopo de Bloco**: Variáveis declaradas com `let` ou `const` dentro de um bloco (`{}`) têm escopo de bloco.

    ```javascript
    if (true) {
        let blockVar = "I'm local to the block";
        console.log(blockVar); // I'm local to the block
    }
    console.log(blockVar); // ReferenceError
    ```

Entender esses conceitos é crucial para escrever código JavaScript eficiente e evitar erros comuns relacionados a escopo e declaração de variáveis.
