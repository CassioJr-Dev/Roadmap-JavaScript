# Expressões e Operadores em JavaScript

Bem-vindo ao README de Expressões e Operadores em JavaScript! Este guia irá ajudá-lo a entender vários operadores em JavaScript com explicações e exemplos.

## Tabela de Conteúdos

- [Operadores de Atribuição](#operadores-de-atribuição)
- [Operadores de Comparação](#operadores-de-comparação)
- [Operadores Aritméticos](#operadores-aritméticos)
- [Operadores Bit a Bit](#operadores-bit-a-bit)
- [Operadores Lógicos](#operadores-lógicos)
- [Operadores BigInt](#operadores-bigint)
- [Operadores de String](#operadores-de-string)
- [Operador Condicional (Ternário)](#operador-condicional-ternário)
- [Operador Vírgula](#operador-vírgula)
- [Operadores Unários](#operadores-unários)
- [Operadores Relacionais](#operadores-relacionais)

## Operadores de Atribuição

Os operadores de atribuição atribuem valores às variáveis.

```javascript
let x = 10; // Atribui 10 a x
x += 5; // Adiciona 5 a x, equivalente a x = x + 5
x -= 2; // Subtrai 2 de x, equivalente a x = x - 2
x *= 3; // Multiplica x por 3, equivalente a x = x * 3
x /= 2; // Divide x por 2, equivalente a x = x / 2
x %= 3; // Atribui o resto da divisão de x por 3, equivalente a x = x % 3
x **= 2; // Eleva x à potência de 2, equivalente a x = x ** 2
```

## Operadores de Comparação

Os operadores de comparação comparam dois valores e retornam um Boolean.

```javascript
let a = 5, b = 10;
console.log(a == b); // false (igual a)
console.log(a === b); // false (estritamente igual a)
console.log(a != b); // true (diferente de)
console.log(a !== b); // true (estritamente diferente de)
console.log(a > b); // false (maior que)
console.log(a >= b); // false (maior ou igual a)
console.log(a < b); // true (menor que)
console.log(a <= b); // true (menor ou igual a)
```

## Operadores Aritméticos

Os operadores aritméticos realizam operações aritméticas com números.

```javascript
let a = 10, b = 3;
console.log(a + b); // 13 (adição)
console.log(a - b); // 7 (subtração)
console.log(a * b); // 30 (multiplicação)
console.log(a / b); // 3.3333... (divisão)
console.log(a % b); // 1 (resto)
console.log(a ** b); // 1000 (exponenciação)
```

## Operadores Bit a Bit

Os operadores bit a bit realizam operações bit a bit em números binários.

```javascript
let a = 5, b = 3; // (a = 0101, b = 0011)
console.log(a & b); // 1 (AND, 0001)
console.log(a | b); // 7 (OR, 0111)
console.log(a ^ b); // 6 (XOR, 0110)
console.log(~a); // -6 (NOT, inverte bits)
console.log(a << 1); // 10 (deslocamento à esquerda, 1010)
console.log(a >> 1); // 2 (deslocamento à direita, 0010)
console.log(a >>> 1); // 2 (deslocamento à direita com zero à esquerda, 0010)
```

## Operadores Lógicos

Os operadores lógicos são usados com valores Booleanos.

```javascript
let a = true, b = false;
console.log(a && b); // false (AND)
console.log(a || b); // true (OR)
console.log(!a); // false (NOT)
```

## Operadores BigInt

Os operadores BigInt realizam operações aritméticas com grandes inteiros.

```javascript
let a = 12345678901234567890n, b = 98765432109876543210n;
console.log(a + b); // 111111111011111111100n (adição)
console.log(a * b); // 1219326311370217952237463801111263526900n (multiplicação)
console.log(b / a); // 8n (divisão)
console.log(b % a); // 90000000090000000010n (resto)
```

## Operadores de String

Os operadores de string são usados para concatenar strings.

```javascript
let str1 = "Hello", str2 = "World";
console.log(str1 + " " + str2); // "Hello World" (concatenação)
let num = 10;
console.log("Number: " + num); // "Number: 10" (concatenação com número)
```

## Operador Condicional (Ternário)

O operador condicional atribui um valor com base em uma condição.

```javascript
let idade = 18;
let podeVotar = (idade >= 18) ? "Sim" : "Não";
console.log(podeVotar); // "Sim"
```

## Operador Vírgula

O operador vírgula avalia cada um dos seus operandos e retorna o valor do último operando.

```javascript
let a = (1, 2, 3);
console.log(a); // 3
```

## Operadores Unários

Os operadores unários realizam operações em um único operando.

```javascript
let x = 5;
x++; // Pós-incremento: x se torna 6
++x; // Pré-incremento: x se torna 7
x--; // Pós-decremento: x se torna 6
--x; // Pré-decremento: x se torna 5

let y = -x; // Negação unária: y se torna -5
let z = +y; // Mais unário: z se torna -5 (tenta converter y para um número)
```

## Operadores Relacionais

Os operadores relacionais comparam a relação entre dois operandos.

```javascript
let a = [1, 2, 3], b = [1, 2, 3];
console.log(a instanceof Array); // true (instanceof verifica se a é uma instância de Array)
console.log(a in b); // false (in verifica se a é uma propriedade em b)
```

Sinta-se à vontade para explorar esses exemplos e usá-los em seus projetos! Para mais informações detalhadas, consulte a [MDN Web Docs](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Guide/Expressions_and_Operators).
