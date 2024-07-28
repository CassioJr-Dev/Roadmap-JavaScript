# Classes em JavaScript

## Tabela de Conteúdos

1. [Introdução](#introducao)
2. [Declaração de Classe](#declaracao-de-classe)
3. [Método Construtor](#metodo-construtor)
4. [Métodos de Instância](#metodos-de-instancia)
5. [Métodos Estáticos](#metodos-estaticos)
6. [Herança](#heranca)
7. [Getters e Setters](#getters-e-setters)
8. [Campos Privados](#campos-privados)
9. [Expressões de Classe](#expressoes-de-classe)
10. [Exemplos de Uso](#exemplos-de-uso)

## Introdução

Classes em JavaScript são um modelo para criar objetos. Elas encapsulam dados com código para trabalhar nesses dados. Embora JavaScript seja uma linguagem baseada em protótipos, as classes fornecem uma sintaxe mais familiar para criar e gerenciar objetos.

## Declaração de Classe

Uma classe é declarada usando a palavra-chave `class` seguida pelo nome da classe.

```javascript
class Pessoa {
    // Corpo da classe
}
```

## Método Construtor

O método `constructor` é um método especial para criar e inicializar um objeto criado com uma classe.

```javascript
class Pessoa {
    constructor(nome, idade) {
        this.nome = nome;
        this.idade = idade;
    }
}
```

## Métodos de Instância

Métodos de instância são métodos que estão disponíveis nas instâncias da classe.

```javascript
class Pessoa {
    constructor(nome, idade) {
        this.nome = nome;
        this.idade = idade;
    }

    cumprimentar() {
        console.log(`Olá, meu nome é ${this.nome} e eu tenho ${this.idade} anos.`);
    }
}

const joao = new Pessoa('João', 30);
joao.cumprimentar(); // Olá, meu nome é João e eu tenho 30 anos.
```

## Métodos Estáticos

Métodos estáticos são chamados na própria classe, não nas instâncias da classe.

```javascript
class Pessoa {
    constructor(nome, idade) {
        this.nome = nome;
        this.idade = idade;
    }

    static info() {
        console.log('Esta é a classe Pessoa.');
    }
}

Pessoa.info(); // Esta é a classe Pessoa.
```

## Herança

Classes podem estender outras classes usando a palavra-chave `extends`.

```javascript
class Pessoa {
    constructor(nome, idade) {
        this.nome = nome;
        this.idade = idade;
    }

    cumprimentar() {
        console.log(`Olá, meu nome é ${this.nome} e eu tenho ${this.idade} anos.`);
    }
}

class Funcionario extends Pessoa {
    constructor(nome, idade, cargo) {
        super(nome, idade);
        this.cargo = cargo;
    }

    trabalhar() {
        console.log(`${this.nome} está trabalhando como ${this.cargo}.`);
    }
}

const ana = new Funcionario('Ana', 25, 'Engenheira de Software');
ana.cumprimentar(); // Olá, meu nome é Ana e eu tenho 25 anos.
ana.trabalhar(); // Ana está trabalhando como Engenheira de Software.
```

## Getters e Setters

Getters e setters permitem definir métodos que serão usados como propriedades.

```javascript
class Pessoa {
    constructor(nome, idade) {
        this._nome = nome;
        this._idade = idade;
    }

    get nome() {
        return this._nome;
    }

    set nome(novoNome) {
        this._nome = novoNome;
    }

    get idade() {
        return this._idade;
    }

    set idade(novaIdade) {
        if (novaIdade > 0) {
            this._idade = novaIdade;
        } else {
            console.log('A idade deve ser positiva.');
        }
    }
}

const pedro = new Pessoa('Pedro', 40);
console.log(pedro.nome); // Pedro
pedro.idade = 45;
console.log(pedro.idade); // 45
pedro.idade = -5; // A idade deve ser positiva.
```

## Campos Privados

Campos privados são declarados com um `#` e só podem ser acessados dentro da classe.

```javascript
class Pessoa {
    #cpf;

    constructor(nome, idade, cpf) {
        this.nome = nome;
        this.idade = idade;
        this.#cpf = cpf;
    }

    getCPF() {
        return this.#cpf;
    }
}

const maria = new Pessoa('Maria', 35, '123.456.789-10');
console.log(maria.getCPF()); // 123.456.789-10
console.log(maria.#cpf); // SyntaxError: Campo privado '#cpf' deve ser declarado na classe.
```

## Expressões de Classe

Classes também podem ser definidas usando expressões.

```javascript
const Pessoa = class {
    constructor(nome, idade) {
        this.nome = nome;
        this.idade = idade;
    }

    cumprimentar() {
        console.log(`Olá, meu nome é ${this.nome} e eu tenho ${this.idade} anos.`);
    }
};

const roberto = new Pessoa('Roberto', 28);
roberto.cumprimentar(); // Olá, meu nome é Roberto e eu tenho 28 anos.
```

## Exemplos de Uso

### Exemplo 1: Modelando Entidades do Mundo Real

```javascript
class Carro {
    constructor(marca, modelo, ano) {
        this.marca = marca;
        this.modelo = modelo;
        this.ano = ano;
    }

    ligar() {
        console.log(`${this.marca} ${this.modelo} está ligando.`);
    }
}

const meuCarro = new Carro('Toyota', 'Corolla', 2020);
meuCarro.ligar(); // Toyota Corolla está ligando.
```

### Exemplo 2: Gerenciando Coleções de Dados

```javascript
class Biblioteca {
    constructor() {
        this.livros = [];
    }

    adicionarLivro(livro) {
        this.livros.push(livro);
    }

    listarLivros() {
        this.livros.forEach(livro => console.log(livro));
    }
}

const minhaBiblioteca = new Biblioteca();
minhaBiblioteca.adicionarLivro('O Grande Gatsby');
minhaBiblioteca.adicionarLivro('1984');
minhaBiblioteca.listarLivros();
// O Grande Gatsby
// 1984
```

### Exemplo 3: Implementando Lógica de Aplicação

```javascript
class Calculadora {
    static somar(a, b) {
        return a + b;
    }

    static subtrair(a, b) {
        return a - b;
    }

    static multiplicar(a, b) {
        return a * b;
    }

    static dividir(a, b) {
        return a / b;
    }
}

console.log(Calculadora.somar(5, 3)); // 8
console.log(Calculadora.subtrair(5, 3)); // 2
console.log(Calculadora.multiplicar(5, 3)); // 15
console.log(Calculadora.dividir(5, 3)); // 1.6666666666666667
```
