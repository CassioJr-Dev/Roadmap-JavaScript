# JavaScript Assíncrono

JavaScript assíncrono é um paradigma que permite lidar com tarefas como operações de E/S, requisições de rede e timers sem bloquear a thread principal de execução. Este README irá cobrir os seguintes tópicos:

- Event Loop
- `setTimeout`
- `setInterval`
- Callbacks e Callback Hell
- Promises
- `async/await`

## Event Loop

O Event Loop é um conceito fundamental no JavaScript que lida com operações assíncronas. Ele permite que o JavaScript execute operações de E/S de forma não bloqueante, apesar de ser single-threaded.

### Como Funciona

1. **Call Stack**: Armazena as chamadas de funções atuais. As funções são executadas uma de cada vez a partir da pilha.
2. **Web APIs**: APIs fornecidas pelo navegador, como `setTimeout`, eventos do DOM e requisições AJAX.
3. **Callback Queue**: Armazena funções de callback que estão prontas para serem executadas.
4. **Event Loop**: Verifica continuamente se a call stack está vazia. Se estiver, move o primeiro callback da callback queue para a call stack.

### Exemplo

```javascript
console.log('Início');

setTimeout(() => {
  console.log('Callback');
}, 0);

console.log('Fim');

// Saída:
// Início
// Fim
// Callback
```

## `setTimeout`

`setTimeout` é uma função que executa uma função dada após um atraso especificado.

### Sintaxe

```javascript
setTimeout(callback, delay);
```

- `callback`: A função a ser executada.
- `delay`: Tempo em milissegundos a esperar antes de executar o callback.

### Exemplo

```javascript
setTimeout(() => {
  console.log('Executado após 2 segundos');
}, 2000);
```

## `setInterval`

`setInterval` é uma função que executa repetidamente uma função dada em intervalos especificados.

### Sintaxe

```javascript
setInterval(callback, interval);
```

- `callback`: A função a ser executada.
- `interval`: Tempo em milissegundos entre cada execução.

### Exemplo

```javascript
let count = 0;

const intervalId = setInterval(() => {
  console.log(`Executado ${++count} vezes`);
  
  if (count === 5) {
    clearInterval(intervalId);
  }
}, 1000);
```

## Callbacks e Callback Hell

### Callbacks

Um callback é uma função passada como argumento para outra função para ser executada mais tarde.

### Exemplo

```javascript
function fetchData(callback) {
  setTimeout(() => {
    callback('Dados recebidos');
  }, 1000);
}

fetchData((data) => {
  console.log(data);
});
```

### Callback Hell

Callback Hell ocorre quando múltiplas operações assíncronas são aninhadas umas dentro das outras, levando a um código difícil de ler e manter.

### Exemplo

```javascript
setTimeout(() => {
  console.log('Primeiro');
  setTimeout(() => {
    console.log('Segundo');
    setTimeout(() => {
      console.log('Terceiro');
    }, 1000);
  }, 1000);
}, 1000);
```

## Promises

Promises fornecem uma forma mais limpa de lidar com operações assíncronas e evitar o Callback Hell.

### Sintaxe

```javascript
let promise = new Promise((resolve, reject) => {
  // operação assíncrona
});
```

- `resolve`: Chame esta função quando a operação for bem-sucedida.
- `reject`: Chame esta função quando a operação falhar.

### Exemplo

```javascript
let fetchData = new Promise((resolve, reject) => {
  setTimeout(() => {
    resolve('Dados recebidos');
  }, 1000);
});

fetchData.then((data) => {
  console.log(data);
}).catch((error) => {
  console.error(error);
});
```

## `async/await`

`async/await` é uma sintaxe especial sobre Promises, fornecendo uma forma mais legível e semelhante ao código síncrono para escrever código assíncrono.

### Sintaxe

- Função `async`: Declara uma função assíncrona.
- Expressão `await`: Pausa a execução da função async e espera a promise ser resolvida.

### Exemplo

```javascript
async function fetchData() {
  let promise = new Promise((resolve, reject) => {
    setTimeout(() => {
      resolve('Dados recebidos');
    }, 1000);
  });

  let data = await promise;
  console.log(data);
}

fetchData();
```

### Tratamento de Erros

```javascript
async function fetchData() {
  try {
    let promise = new Promise((resolve, reject) => {
      setTimeout(() => {
        reject('Erro ao receber dados');
      }, 1000);
    });

    let data = await promise;
    console.log(data);
  } catch (error) {
    console.error(error);
  }
}

fetchData();
```

Este README fornece uma visão geral básica do JavaScript assíncrono, focando em conceitos-chave e exemplos para ajudá-lo a entender e usá-los efetivamente.
