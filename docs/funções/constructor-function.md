# Constructor function

Uma `constructor function` é uma função que é usada para criar objetos. Ela 
atua como um *"modelo"* para criar múltiplos objetos com as mesmas propriedades 
e métodos.

Aqui está um exemplo de constructor function:

```{.js linenums="1"}
function Pessoa(nome, sobrenome, alt, pes) {
    const secret = '12bf4W';  // atributo privado

    this.nome = nome;
    this.sobrenome = sobrenome;
    this.altura = alt;
    this.peso = pes;

    this.nomeCompleto = `${this.nome} ${this.sobrenome}`;
    this.imc = (this.peso / (this.altura ** 2)).toFixed(2);

    this.fala = (assunto) => {
        return `${this.nome} disse ${assunto}`;
    };

}
```

Neste exemplo podemos instanciar novas pessoas, usando a palavra-chave `new`.

```{.js linenums="1"}
const pessoa1 = new Pessoa('Arnaldo', 'Fagundes', 1.87, 102);
console.log(pessoa1.secret);          // atributo privado: acesso proibido
console.log(pessoa1);                 // { nome: 'Arnaldo', ... }
console.log(pessoa1.nomeCompleto);    // Arnaldo Fagundes
console.log(pessoa1.fala('python'));  // Arnaldo dissee python
console.log(pessoa1.imc);             // 29.17
```

A principal vantagem das constructor functions é a capacidade de criar objetos 
com a mesma estrutura e comportamento de uma maneira mais organizada e 
reutilizável. Elas são frequentemente usadas em conjunto com protótipos para 
adicionar métodos compartilhados entre as instâncias dos objetos criados a 
partir da constructor function.