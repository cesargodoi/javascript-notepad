# Objetos

`Objects`  são estruturas de dados que pode armazenar valores e funções 
relacionados. Os objetos são uma parte fundamental da linguagem e são usados 
para representar e organizar informações de maneira eficaz. Eles são 
construídos a partir de pares de chave-valor, nos quais as chaves são `strings` 
(ou `symbols`) que atuam como identificadores e os valores podem ser de 
qualquer tipo de dado, incluindo `numbers`, `strings`, outros `objects`, 
`functions` e assim por diante.

Vejamos um exemplo de objeto:
```{.js linenums="1"}
var pessoa = {
  nome: "João",
  idade: 30,
  profissao: "Desenvolvedor"
};
```

Neste exemplo, `pessoa` é um objeto com três propriedades: `nome`, `idade` e 
`profissao`, e cada propriedade tem um valor associado a ela.

Você pode acessar as propriedades de um objeto usando a notação de ponto ou a 
notação de colchetes, assim:

```{.js linenums="1"}
console.log(pessoa.nome);      // João
console.log(pessoa['idade']);  // 30
```

Além disso, você pode adicionar novas propriedades, modificar propriedades 
existentes e até mesmo remover propriedades de objetos em JavaScript. Objetos 
também podem conter `methods`, que são `functions` associadas a eles. Eles são 
muito versáteis e formam a base da programação orientada a objetos em 
JavaScript.