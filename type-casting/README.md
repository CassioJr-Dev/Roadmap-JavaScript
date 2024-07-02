
# Type Casting em JavaScript

## Sumário

- [Type Conversion vs Coercion](#type-conversion-vs-coercion)
- [Explicit Type Casting](#explicit-type-casting)
- [Implicit Type Casting](#implicit-type-casting)

## Type Conversion vs Coercion

**Type Conversion** e **Type Coercion** referem-se ao processo de mudar um valor de um tipo de dado para outro. A diferença principal entre os dois é:

- **Type Conversion**: É uma conversão explícita de tipos, onde o desenvolvedor faz a conversão de forma intencional.
- **Type Coercion**: É uma conversão implícita de tipos, onde o JavaScript converte automaticamente os tipos conforme necessário.

### Exemplo

```javascript
// Type Conversion
const numString = "123";
const num = Number(numString); // Explicitamente convertendo string para número

// Type Coercion
const result = "5" * 2; // Implicitamente convertendo string para número
```

## Explicit Type Casting

**Explicit Type Casting** é quando você, como desenvolvedor, converte manualmente um valor de um tipo para outro. Isso é feito usando funções ou métodos específicos.

### Métodos Comuns

- `Number()`: Converte um valor para número.
- `String()`: Converte um valor para string.
- `Boolean()`: Converte um valor para booleano.

### Exemplos

```javascript
// Convertendo string para número
const str = "456";
const num = Number(str);
console.log(num); // 456

// Convertendo número para string
const num2 = 123;
const str2 = String(num2);
console.log(str2); // "123"

// Convertendo valor para booleano
const val = 1;
const boolVal = Boolean(val);
console.log(boolVal); // true
```

## Implicit Type Casting

**Implicit Type Casting**, ou **Type Coercion**, ocorre quando o JavaScript automaticamente converte tipos de dados conforme necessário durante a execução do código.

### Exemplos Comuns

- **Concatenação de Strings**: Quando um número é concatenado com uma string, o número é convertido em string.
- **Operações Aritméticas**: Quando uma string contendo um número é usada em operações aritméticas, ela é convertida para número.

### Exemplos

```javascript
// Concatenação de Strings
const str = "O número é " + 5;
console.log(str); // "O número é 5"

// Operações Aritméticas
const result = "6" / 2;
console.log(result); // 3

// Comparação com == (igualdade solta)
const isEqual = 5 == "5";
console.log(isEqual); // true (5 é convertido para "5")
```

## Conclusão

Compreender Type Conversion e Coercion é fundamental para escrever código JavaScript eficiente e livre de bugs. Use Explicit Type Casting para maior controle e clareza no seu código, e esteja ciente de quando ocorre Implicit Type Casting para evitar comportamentos inesperados.
