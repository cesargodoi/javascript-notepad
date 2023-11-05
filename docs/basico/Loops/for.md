# For (clássico)

Os laços `for` em JavaScript são usados para repetir um bloco de código várias 
vezes. Eles são frequentemente usados para percorrer arrays, executar uma série 
de instruções com uma contagem específica ou para realizar tarefas repetitivas.  

Esta estrutura de `for` clássico podemos iterar `arrays` e `strings`.

Existem diferentes formas de usar a estrutura de controle `for` em JavaScript, 
mas a forma mais comum é a seguinte:

```{.js linenums="1"}
for (inicialização; condição; incremento) {
  // Código a ser executado repetidamente
}
```

Funciona assim:

1. **Inicialização**: Nesta parte, você normalmente declara uma variável e 
atribui um valor inicial a ela. Essa parte é executada uma vez no início do 
laço.

2. **Condição**: A condição é uma expressão que é avaliada antes de cada 
iteração do laço. Se a condição for avaliada como verdadeira (ou seja, retornar 
`true`), o código dentro do laço é executado. Se a condição for avaliada como 
falsa (ou seja, retornar `false`), o laço é encerrado.

3. **Incremento**: Após a execução do código no corpo do laço, a parte de 
incremento é executada. Geralmente, isso envolve aumentar ou diminuir o valor 
da variável de controle, de modo que a condição eventualmente se torne falsa e 
o laço seja encerrado.

Aqui está um exemplo simples que percorre os números de 1 a 5 e imprime cada 
número:

```{.js linenums="1"}
for (let i = 1; i <= 5; i++) {
  console.log(`-> ${i}`);
}

// -> 1
// -> 2
// -> 3
// -> 4
// -> 5
```

Este laço começa com `i` igual a 1. A cada iteração, ele verifica se `i` é 
menor ou igual a 5. Se a condição for verdadeira, ele executa o bloco de código 
(no caso, `console.log(i)`) e, em seguida, incrementa `i` em 1. O laço continua 
até que a condição seja falsa.

É importante observar que a parte de **inicialização**, **condição** e 
**incremento** são opcionais, embora você normalmente use todas elas para 
controlar o comportamento do laço. Além disso, você pode usar o `for` para 
percorrer arrays, strings ou qualquer sequência de elementos, ajustando a 
condição e a variável de controle conforme necessário.