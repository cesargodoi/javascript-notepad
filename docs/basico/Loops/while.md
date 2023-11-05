# While

O laço `while` é uma estrutura de controle em JavaScript que permite que você 
execute um bloco de código repetidamente enquanto uma determinada condição for 
verdadeira. Sua sintaxe é a seguinte:

```{.js linenums="1"}
while (condição) {
  // Código a ser executado enquanto a condição for verdadeira
}
```

Funciona assim:

1. A condição é avaliada inicialmente. Se a condição for avaliada como `true`, 
o código dentro do bloco do `while` é executado.

2. Após a execução do código no bloco, a condição é avaliada novamente. Se a 
condição ainda for verdadeira, o código no bloco é executado novamente. Esse 
processo se repete até que a condição seja avaliada como `false`.

3. Uma vez que a condição se torne `false`, a execução do laço `while` é 
interrompida e o controle do programa passa para a próxima instrução após o 
bloco `while`.

Aqui está um exemplo simples de como usar o laço `while` para contar de 1 a 5:

```{.js linenums="1"}
let contador = 1;

while (contador <= 5) {
  console.log(contador);
  contador++;
}

// 1
// 2
// 3
// 4
// 5
```

Neste exemplo, o código no bloco do `while` é executado repetidamente enquanto 
o valor da variável `contador` for menor ou igual a 5. O `contador` é 
incrementado a cada iteração, garantindo que eventualmente a condição se torne 
`false` e o laço seja encerrado.

Tenha cuidado ao usar o `while`, pois se a condição nunca se tornar `false`, 
seu programa entrará em um loop infinito, o que pode travá-lo. Certifique-se de 
que a condição será eventualmente falsa, a menos que você queira criar um loop 
infinito intencionalmente.