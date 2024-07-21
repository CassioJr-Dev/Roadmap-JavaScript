# Fluxo de Controle em JavaScript

Este repositório fornece uma visão geral dos conceitos de fluxo de controle em JavaScript com exemplos. O fluxo de controle é crucial na programação, pois determina a ordem em que as instruções são executadas.

## Índice

- [Instruções Condicionais](#instruções-condicionais)
  - [If...else](#ifelse)
  - [Switch](#switch)
- [Tratamento de Exceções](#tratamento-de-exceções)
  - [Instrução throw](#instrução-throw)
  - [try / catch / finally](#try-catch-finally)
  - [Utilizando Objetos de Erro](#utilizando-objetos-de-erro)

## Instruções Condicionais

As instruções condicionais permitem que você execute diferentes blocos de código com base em certas condições.

### If...else

A instrução `if...else` executa um bloco de código se uma condição especificada for verdadeira. Se a condição for falsa, outro bloco de código pode ser executado usando `else`.

#### Sintaxe

```javascript
if (condição) {
  // bloco de código a ser executado se a condição for verdadeira
} else {
  // bloco de código a ser executado se a condição for falsa
}
```

#### Exemplo

```javascript
let idade = 20;

if (idade >= 18) {
  console.log("Você é um adulto.");
} else {
  console.log("Você é um menor de idade.");
}
```

### Switch

A instrução `switch` avalia uma expressão e executa blocos de código com base nos valores correspondentes dos casos.

#### Sintaxe

```javascript
switch (expressão) {
  case valor1:
    // código a ser executado se expressão === valor1
    break;
  case valor2:
    // código a ser executado se expressão === valor2
    break;
  default:
    // código a ser executado se a expressão não corresponder a nenhum caso
}
```

#### Exemplo

```javascript
let fruta = "maçã";

switch (fruta) {
  case "banana":
    console.log("A banana é amarela.");
    break;
  case "maçã":
    console.log("A maçã é vermelha.");
    break;
  default:
    console.log("Fruta desconhecida.");
}
```

## Tratamento de Exceções

O tratamento de exceções permite que você lide com erros de runtime de forma elegante, garantindo que o programa continue a ser executado sem problemas.

### Instrução throw

A instrução `throw` permite criar erros personalizados.

#### Sintaxe

```javascript
throw expressão;
```

#### Exemplo

```javascript
function dividir(a, b) {
  if (b === 0) {
    throw new Error("Divisão por zero não é permitida.");
  }
  return a / b;
}

try {
  console.log(dividir(10, 0));
} catch (erro) {
  console.error(erro.message);
}
```

### try / catch / finally

O bloco `try` permite testar um bloco de código em busca de erros. O bloco `catch` lida com o erro. O bloco `finally` executa código após os blocos try e catch, independentemente do resultado.

#### Sintaxe

```javascript
try {
  // bloco de código a ser testado
} catch (erro) {
  // bloco de código para lidar com erros
} finally {
  // bloco de código a ser executado independentemente do resultado do try / catch
}
```

#### Exemplo

```javascript
try {
  let resultado = dividir(10, 0);
  console.log(resultado);
} catch (erro) {
  console.error(erro.message);
} finally {
  console.log("Execução completa.");
}
```

### Utilizando Objetos de Erro

Objetos de erro fornecem mais informações sobre os erros, incluindo as propriedades name e message.

#### Exemplo

```javascript
try {
  throw new Error("Algo deu errado!");
} catch (erro) {
  console.error(`Erro: ${erro.name} - ${erro.message}`);
}
```

---

Este README fornece uma visão geral dos conceitos de fluxo de controle em JavaScript. Sinta-se à vontade para explorar os exemplos e testá-los em seus próprios projetos!

---
