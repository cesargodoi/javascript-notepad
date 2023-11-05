# Do...while

O laço `do...while` é uma estrutura de controle que permite que um bloco de 
código seja executado repetidamente enquanto uma condição especificada for 
verdadeira. A principal diferença entre um `do...while` e um `while` é que no 
`do...while`, o bloco de código é executado pelo menos uma vez, mesmo que a 
condição seja falsa desde o início.

Aqui está a estrutura básica de um `do...while`:

```{.js linenums="1"}
do {
  // Bloco de código a ser executado
} while (condição);
```

Funciona assim:

1. O código dentro do bloco é executado pela primeira vez, independentemente 
da condição.

2. Após a execução do bloco, a condição é verificada.

3. Se a condição for verdadeira, o código dentro do bloco é executado 
novamente. Esse processo se repete até que a condição se torne falsa.

4. Uma vez que a condição se torne falsa, a execução do código no `do...while` 
é interrompida, e o programa continua com as instruções após o `do...while`.

Aqui está um exemplo simples de uso do `do...while` em JavaScript:

```{.js linenums="1"}
let contador = 0;

do {
  console.log("Contador: " + contador);
  contador++;
} while (contador < 5);

// Contador: 0
// Contador: 1
// Contador: 2
// Contador: 3
// Contador: 4
```

Neste exemplo, o bloco de código dentro do `do...while` é executado pelo menos 
uma vez, e depois ele continua a ser executado enquanto a condição 
`contador < 5` for verdadeira.

Mesmo que a condição seja falsa desde o início, o bloco de código ainda é 
executado pelo menos uma vez antes que a condição seja verificada. Isso faz do 
`do...while` uma boa escolha quando você precisa garantir que um bloco de 
código seja executado pelo menos uma vez, independentemente da condição.