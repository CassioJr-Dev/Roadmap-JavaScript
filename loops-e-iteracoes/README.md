# Loops e Iterações em JavaScript

Loops e iterações são conceitos fundamentais na programação que permitem a execução de um bloco de código várias vezes. O JavaScript fornece várias maneiras de realizar loops e iterações, cada uma com seus casos de uso específicos e sintaxe.

## Índice

- [Declaração For](#declaração-for)
- [Declaração Do...While](#declaração-do-while)
- [Declaração While](#declaração-while)
- [Declaração For...In](#declaração-for-in)
- [Declaração For...Of](#declaração-for-of)
- [Break e Continue - Declarações Rotuladas](#break-e-continue---declarações-rotuladas)

## Declaração For

A declaração `for` cria um loop que consiste em três expressões opcionais: inicialização, condição e expressão final. É tipicamente usada quando o número de iterações é conhecido.

### Sintaxe

```javascript
for (inicialização; condição; expressãoFinal) {
  // código a ser executado
}
```

### Exemplo

```javascript
for (let i = 0; i < 5; i++) {
  console.log(`Número da iteração: ${i}`);
}
```

Neste exemplo, o loop imprimirá o número da iteração de 0 a 4.

## Declaração Do...While

A declaração `do...while` cria um loop que executa uma instrução especificada até que a condição de teste seja avaliada como falsa. A condição é avaliada após a execução da instrução, garantindo que a instrução seja executada pelo menos uma vez.

### Sintaxe

```javascript
do {
  // código a ser executado
} while (condição);
```

### Exemplo

```javascript
let i = 0;
do {
  console.log(`Número da iteração: ${i}`);
  i++;
} while (i < 5);
```

Neste exemplo, o loop imprimirá o número da iteração de 0 a 4.

## Declaração While

A declaração `while` cria um loop que executa enquanto a condição especificada for avaliada como verdadeira. A condição é avaliada antes da execução da instrução.

### Sintaxe

```javascript
while (condição) {
  // código a ser executado
}
```

### Exemplo

```javascript
let i = 0;
while (i < 5) {
  console.log(`Número da iteração: ${i}`);
  i++;
}
```

Neste exemplo, o loop imprimirá o número da iteração de 0 a 4.

## Declaração For...In

A declaração `for...in` itera sobre as propriedades enumeráveis de um objeto, em uma ordem arbitrária. É tipicamente usada para iterar sobre propriedades de objetos.

### Sintaxe

```javascript
for (variável in objeto) {
  // código a ser executado
}
```

### Exemplo

```javascript
const pessoa = { nome: 'João', idade: 30, cidade: 'Nova York' };
for (let chave in pessoa) {
  console.log(`${chave}: ${pessoa[chave]}`);
}
```

Neste exemplo, o loop imprimirá cada propriedade e valor do objeto `pessoa`.

## Declaração For...Of

A declaração `for...of` itera sobre objetos iteráveis (incluindo Array, Map, Set, o objeto arguments e assim por diante), chamando uma função personalizada com instruções a serem executadas para o valor de cada distinto elemento.

### Sintaxe

```javascript
for (variável of iterável) {
  // código a ser executado
}
```

### Exemplo

```javascript
const array = ['a', 'b', 'c'];
for (const valor of array) {
  console.log(valor);
}
```

Neste exemplo, o loop imprimirá cada valor do array `array`.

## Break e Continue - Declarações Rotuladas

A instrução `break` é usada para terminar o loop prematuramente, enquanto a instrução `continue` é usada para pular a iteração atual e passar para a próxima. Declarações rotuladas permitem especificar o nome do rótulo para interromper ou continuar loops aninhados.

### Sintaxe

```javascript
rótulo: {
  // código a ser executado
  break rótulo;
  continue rótulo;
}
```

### Exemplo

```javascript
loopExterno: for (let i = 0; i < 3; i++) {
  for (let j = 0; j < 3; j++) {
    if (i === 1 && j === 1) {
      break loopExterno; // termina o loop externo
    }
    console.log(`i = ${i}, j = ${j}`);
  }
}
```

Neste exemplo, a instrução `break loopExterno` termina o loop externo quando `i` é 1 e `j` é 1.

```javascript
loopExterno: for (let i = 0; i < 3; i++) {
  for (let j = 0; j < 3; j++) {
    if (j === 1) {
      continue loopExterno; // pula a iteração atual do loop externo
    }
    console.log(`i = ${i}, j = ${j}`);
  }
}
```

Neste exemplo, a instrução `continue loopExterno` pula a iteração atual do loop externo quando `j` é 1.

---

Compreendendo e usando essas estruturas de loop, você pode controlar efetivamente o fluxo dos seus programas em JavaScript. Feliz codificação!

---

Sinta-se à vontade para contribuir abrindo issues ou enviando pull requests.
