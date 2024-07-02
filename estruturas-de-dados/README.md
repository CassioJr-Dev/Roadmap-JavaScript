# Estruturas de Dados em JavaScript

## Sumário

- [Coleções Indexadas](#coleções-indexadas)
  - [Typed Arrays](#typed-arrays)
  - [Arrays](#arrays)
- [Coleções Chaveadas](#coleções-chaveadas)
  - [Map](#map)
  - [WeakMap](#weakmap)
  - [Set](#set)
  - [WeakSet](#weakset)
- [Dados Estruturados](#dados-estruturados)
  - [JSON](#json)

## Coleções Indexadas

### Typed Arrays

Os Typed Arrays são objetos semelhantes a arrays que fornecem um mecanismo para acessar dados binários brutos. Eles são usados principalmente quando você precisa manipular grandes volumes de dados numéricos de maneira eficiente.

Exemplo de uso:

```javascript
// Criando um ArrayBuffer de 16 bytes
let buffer = new ArrayBuffer(16);

// Criando um Int32Array a partir do ArrayBuffer
let int32View = new Int32Array(buffer);

int32View[0] = 42;
console.log(int32View[0]); // 42
```

### Arrays

Arrays são usados para armazenar múltiplos valores em uma única variável. Eles podem conter qualquer tipo de valor, incluindo números, strings, objetos e outras arrays.

Exemplo de uso:

```javascript
let frutas = ["Maçã", "Banana", "Laranja"];

frutas.push("Manga");
console.log(frutas); // ["Maçã", "Banana", "Laranja", "Manga"]

frutas.pop();
console.log(frutas); // ["Maçã", "Banana", "Laranja"]
```

## Coleções Chaveadas

### Map

Map é uma coleção de pares chave-valor. Ao contrário de objetos, as chaves em um Map podem ser de qualquer tipo, incluindo funções, objetos e qualquer valor primitivo.

Exemplo de uso:

```javascript
let mapa = new Map();

mapa.set("chave", "valor");
console.log(mapa.get("chave")); // "valor"

mapa.set(123, "número como chave");
console.log(mapa.get(123)); // "número como chave"
```

### WeakMap

WeakMap é semelhante ao Map, mas as chaves devem ser objetos e são "fracas", ou seja, não impedem que o coletor de lixo limpe as referências aos objetos usados como chaves.

Exemplo de uso:

```javascript
let weakMapa = new WeakMap();
let obj = {};

weakMapa.set(obj, "valor associado");
console.log(weakMapa.get(obj)); // "valor associado"

obj = null; // O objeto é coletado pelo garbage collector
```

### Set

Set é uma coleção de valores únicos. Um valor em um Set pode ocorrer apenas uma vez; ele é único na coleção Set.

Exemplo de uso:

```javascript
let conjunto = new Set();

conjunto.add(1);
conjunto.add(5);
conjunto.add(5); // Ignorado, pois 5 já está no conjunto

console.log(conjunto.has(1)); // true
console.log(conjunto.size); // 2
```

### WeakSet

WeakSet é semelhante ao Set, mas só pode conter objetos e suas referências são "fracas".

Exemplo de uso:

```javascript
let weakConjunto = new WeakSet();
let obj1 = {};
let obj2 = {};

weakConjunto.add(obj1);
weakConjunto.add(obj2);

console.log(weakConjunto.has(obj1)); // true

obj1 = null; // O objeto é coletado pelo garbage collector
```

## Dados Estruturados

### JSON

JSON (JavaScript Object Notation) é um formato de texto leve para intercâmbio de dados. Ele é fácil de ler e escrever para humanos e fácil de parsear e gerar para máquinas.

Exemplo de uso:

```javascript
let objeto = {
  nome: "João",
  idade: 30,
  cidade: "São Paulo"
};

// Converter objeto JavaScript para JSON
let jsonString = JSON.stringify(objeto);
console.log(jsonString); // '{"nome":"João","idade":30,"cidade":"São Paulo"}'

// Converter JSON para objeto JavaScript
let jsonObjeto = JSON.parse(jsonString);
console.log(jsonObjeto); // { nome: 'João', idade: 30, cidade: 'São Paulo' }
```

## Conclusão

Estas são algumas das principais estruturas de dados disponíveis em JavaScript. Escolher a estrutura de dados correta para o seu caso de uso pode melhorar significativamente a eficiência e a clareza do seu código.
