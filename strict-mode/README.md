# Strict Mode em JavaScript

O modo estrito ("strict mode") em JavaScript é uma funcionalidade que permite que você execute seu código em um modo "restrito". Este modo ajuda a identificar erros silenciosos, impede certos comportamentos inseguros e torna mais fácil escrever código robusto e seguro.

## Ativando o Strict Mode

Para ativar o strict mode em todo o seu script, basta adicionar a linha `"use strict";` no início do seu arquivo JavaScript:

```javascript
"use strict";

function exemplo() {
    // Código aqui será executado no modo estrito
}
```

Você também pode ativar o strict mode em uma função específica:

```javascript
function exemplo() {
    "use strict";
    // Código aqui será executado no modo estrito
}
```

## Diferenças e Regras do Strict Mode

### 1. Declaração de Variáveis

No strict mode, você deve declarar todas as variáveis usando `var`, `let`, ou `const`. Caso contrário, um erro será lançado.

```javascript
"use strict";

nome = "João"; // ReferenceError: nome is not defined
```

### 2. Parâmetros Duplicados

Funções não podem ter parâmetros com o mesmo nome.

```javascript
"use strict";

function exemplo(a, a) {
    // SyntaxError: Duplicate parameter name not allowed in this context
}
```

### 3. Propriedades de Somente Leitura

Não é possível atribuir valores a propriedades somente leitura.

```javascript
"use strict";

const obj = {};
Object.defineProperty(obj, "prop", {
    value: 42,
    writable: false
});

obj.prop = 17; // TypeError: Cannot assign to read only property 'prop'
```

### 4. Propriedades Não Enumeráveis

Não é possível deletar propriedades não enumeráveis.

```javascript
"use strict";

delete Object.prototype; // TypeError: Cannot delete property 'prototype' of function Object() { [native code] }
```

### 5. `this` em Funções

No strict mode, o valor de `this` em funções não é convertido para o objeto global. Se uma função é chamada sem um contexto, `this` será `undefined`.

```javascript
"use strict";

function exemplo() {
    console.log(this); // undefined
}

exemplo();
```

### 6. Octal Literals

Octal literals não são permitidos.

```javascript
"use strict";

var num = 015; // SyntaxError: Octal literals are not allowed in strict mode.
```

### 7. `with` Statement

O uso do `with` statement é proibido no strict mode.

```javascript
"use strict";

with (Math) { // SyntaxError: Strict mode code may not include a with statement
    var x = cos(2);
}
```

### 8. Atribuição a `eval` e `arguments`

Não é permitido atribuir valores às variáveis `eval` e `arguments`.

```javascript
"use strict";

eval = 17; // SyntaxError: Assignment to eval or arguments is not allowed in strict mode.
arguments = 42; // SyntaxError: Assignment to eval or arguments is not allowed in strict mode.
```

### 9. Criação de Propriedades com o Mesmo Nome

Não é permitido criar duas propriedades com o mesmo nome em um objeto.

```javascript
"use strict";

var obj = {
    prop: 1,
    prop: 2 // SyntaxError: Duplicate data property in object literal not allowed in strict mode
};
```

## Benefícios do Strict Mode

1. **Segurança**: Ajuda a escrever um código mais seguro e robusto, evitando erros comuns.
2. **Performance**: Alguns motores de JavaScript podem otimizar melhor o código que roda em strict mode.
3. **Manutenção**: Torna o código mais fácil de entender e manter, pois elimina comportamentos silenciosos e ambiguidades.

## Conclusão

O strict mode é uma ferramenta poderosa para escrever um código JavaScript mais seguro e confiável. Ao ativar o strict mode, você pode evitar muitos erros comuns e garantir que seu código seja mais fácil de manter e depurar.

---

Espero que este README ajude a entender e implementar o strict mode em seus projetos JavaScript. Sinta-se à vontade para contribuir com sugestões e melhorias!
