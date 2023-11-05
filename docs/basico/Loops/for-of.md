# For...of

Em JavaScript, os laços `for...of` são usados para percorrer elementos de uma 
coleção iterável, como arrays, strings, objetos semelhantes a arrays (por 
exemplo, NodeList) e muito mais. A estrutura básica de um laço `for...of` é a 
seguinte:

```{.js linenums="1"}
for (let elemento of colecao) {
    // Faça alguma coisa com o "elemento"
}
```

Funciona assim:

1. `for...of` é uma estrutura de controle de loop que começa com a 
palavra-chave `for`.

2. `elemento` é uma variável que você escolhe para representar cada elemento da 
coleção durante cada iteração do loop. Ela pode ser qualquer nome de variável 
válido em JavaScript.

3. `of` é a palavra-chave que separa a variável `elemento` da coleção 
`colecao`.

4. `colecao` é a coleção iterável que você deseja percorrer, como um array, uma 
string, um objeto semelhante a um array (como NodeList) ou qualquer outro 
objeto iterável.

Durante cada iteração do loop, o valor atual da coleção é atribuído à variável 
`elemento`, permitindo que você execute ações com base nesse valor. Aqui está 
um exemplo de uso:

```{.js linenums="1"}
const frutas = ['maçã', 'banana', 'laranja', 'morango'];

for (let fruta of frutas) {
    console.log(fruta);
}

// maçã
// banana
// laranja
// morango
```

Neste exemplo, o loop `for...of` percorre o array `frutas` e a cada iteração, a 
variável `fruta` contém o valor atual do elemento do array. 

Os laços `for...of` são uma maneira conveniente de percorrer coleções iteráveis 
em JavaScript, evitando a necessidade de controlar manualmente os índices e 
tornando o código mais legível. Eles são especialmente úteis quando você 
precisa trabalhar com valores individuais de uma coleção sem se preocupar com a 
complexidade de acessar cada elemento.