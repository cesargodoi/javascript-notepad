# Factory function

Uma `factory function` é uma função que cria e retorna objetos. Ela é usada 
para encapsular a criação de objetos, o que pode ser útil para criar várias 
instâncias de objetos sem a necessidade de escrever código repetitivo.

A principal característica de uma `factory function` é que ela encapsula a 
lógica de criação de um objeto em uma função e retorna novas instâncias desse 
objeto toda vez que é invocada. Essa abordagem é uma forma de implementar o 
conceito de "fabricação" de objetos, onde a função age como uma fábrica que 
produz objetos com base em um modelo ou estrutura predefinida.

Vejamos um exemplo simples de uma `factory function`:

```{.js linenums="1"}
function criarPessoa(name, idade) {
  return {
    name,  // quando o a chave do argumento vai ser a mesma do retorno não 
           // precisamos escrever -> name: name
    age: idade,
    cumprimentar: function() {
      console.log(`Olá, meu nome é ${this.name} e tenho ${this.age} anos.`);
    },
    ficarMaisVelho(anos = 1) {
        return this.age += anos;
    }
  };
}
```

Neste exemplo, a função `criarPessoa` é uma `factory function` que cria 
objetos pessoa com as propriedades `name`, `idade` e dois métodos:   

- `cumprimentar`
- `ficarMaisVelho`

```{.js linenums="1"}
var pessoa1 = criarPessoa("João", 30);
var pessoa2 = criarPessoa("Maria", 25);

pessoa1.cumprimentar();     // Olá, meu nome é João e tenho 30 anos.
pessoa2.cumprimentar();     // Olá, meu nome é Maria e tenho 25 anos.

pessoa1.ficarMaisVelho();   // aumenta 1 ano para João
pessoa1.cumprimentar();     // Olá, meu nome é João e tenho 31 anos.

pessoa2.ficarMaisVelho(4);  // aumenta 4 anos para Maria
pessoa2.cumprimentar();     // Olá, meu nome é Maria e tenho 29 anos.
```

### getters e setters

`Factory functions` podem ter getters e setters.  Isso permite controlar o 
acesso e a modificação das propriedades do objeto de forma mais precisa, se 
necessário.

```{.js linenums="1"}
function pessoa(nome, sobrenome, alt, pes) {
    return {
        nome,
        sobrenome,
        // get -> getter
        get nomeCompleto() {
            return `${this.nome} ${this.sobrenome}`;
        },
        // set -> setter
        set nomeCompleto(text) {
            text = text.split(' ');
            this.nome = text.shift();
            this.sobrenome = text.join(' ');
        },
        altura: alt,
        peso: pes,
        fala(assunto) {
            return `${this.nome} está falando sobre ${assunto}`;
        },

        get imc() {
            return (this.peso / (this.altura ** 2)).toFixed(2);
        }
    }
}

const p1 = pessoa('Jucelino', 'Guanabara', 1.87, 106);
console.log(p1);  
// { nome: 'Jucelino', sobrenome: 'Guanabara', nomeCompleto: [Getter/Setter], 
//   altura: 1.87, peso: 106, fala: [Function: fala], imc: [Getter] }
console.log(p1.nomeCompleto);  // Jucelino Guanabara 
console.log(p1.fala('JavaScript'));  // Jucelino está falando sobre JavaScript
console.log(p1.imc);  // 30.31
p1.nomeCompleto = 'Tiburcio Caetano';
console.log(p1.nomeCompleto);  // Tiburcio Caetano
```