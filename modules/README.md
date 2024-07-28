# Módulos em JavaScript

Módulos em JavaScript permitem dividir seu código em arquivos separados e importar/exportar funcionalidades entre eles. Isso torna seu código mais manutenível, reutilizável e fácil de entender.

## Módulos CommonJS

CommonJS é um sistema de módulos usado no Node.js. Ele usa `require` para importar módulos e `module.exports` para exportá-los.

### Exemplo:

**math.js**
```javascript
// Exportando funções usando module.exports
function add(a, b) {
    return a + b;
}

function subtract(a, b) {
    return a - b;
}

module.exports = {
    add,
    subtract
};
```

**app.js**
```javascript
// Importando funções usando require
const math = require('./math');

const sum = math.add(5, 3);
const difference = math.subtract(5, 3);

console.log(`Soma: ${sum}`);
console.log(`Diferença: ${difference}`);
```

Neste exemplo, `math.js` exporta duas funções (`add` e `subtract`) usando `module.exports`. Em `app.js`, usamos `require` para importar essas funções e utilizá-las.

## Módulos ECMAScript (ESM)

Módulos ECMAScript (ESM) são o sistema de módulos padronizado em JavaScript, introduzido no ES6 (ECMAScript 2015). Ele usa as declarações `import` e `export`.

### Exemplo:

**math.js**
```javascript
// Exportando funções usando export
export function add(a, b) {
    return a + b;
}

export function subtract(a, b) {
    return a - b;
}
```

**app.js**
```javascript
// Importando funções usando import
import { add, subtract } from './math.js';

const sum = add(5, 3);
const difference = subtract(5, 3);

console.log(`Soma: ${sum}`);
console.log(`Diferença: ${difference}`);
```

Neste exemplo, `math.js` exporta duas funções (`add` e `subtract`) usando `export`. Em `app.js`, usamos `import` para importar essas funções e utilizá-las.

## Diferenças entre CommonJS e ESM

1. **Sintaxe**:
   - CommonJS usa `require` e `module.exports`.
   - ESM usa `import` e `export`.

2. **Carregamento**:
   - Módulos CommonJS são carregados de forma síncrona.
   - Módulos ESM são carregados de forma assíncrona.

3. **Escopo**:
   - Módulos CommonJS têm seu próprio escopo.
   - Módulos ESM têm o modo estrito ativado por padrão e não têm um escopo compartilhado.

## Importações Dinâmicas

ESM também suporta importações dinâmicas usando a função `import()`, que permite carregar módulos dinamicamente em tempo de execução.

### Exemplo:

**app.js**
```javascript
// Importação dinâmica
import('./math.js').then(math => {
    const sum = math.add(5, 3);
    const difference = math.subtract(5, 3);

    console.log(`Soma: ${sum}`);
    console.log(`Diferença: ${difference}`);
});
```

Neste exemplo, a função `import()` carrega dinamicamente `math.js` e, em seguida, usa as funções importadas.

## Conclusão

Módulos em JavaScript fornecem uma maneira poderosa de organizar seu código. CommonJS é amplamente usado no Node.js, enquanto os Módulos ECMAScript são o padrão para o JavaScript moderno. Entender ambos pode ajudá-lo a escrever um código mais modular e manutenível.

---

Sinta-se à vontade para contribuir e fazer alterações neste repositório!
