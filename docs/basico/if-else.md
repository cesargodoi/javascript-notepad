# If - Else

O `if-else` é uma estrutura de controle de fluxo que permite executar 
diferentes blocos de código com base em uma condição. A estrutura básica do 
`if-else` é a seguinte:

```{.js linenums="1"}
if (condição) {
    // Este bloco de código é executado se a condição for verdadeira
} else {
    // Este bloco de código é executado se a condição for falsa
}
```

Aqui está como funciona o `if-else`:

1. A condição é avaliada: A expressão dentro dos parênteses após a 
palavra-chave `if` é avaliada. Se essa expressão retornar `true`, o bloco de 
código dentro das chaves seguintes é executado. Se a expressão for `false`, o 
código dentro do bloco `else` (se houver) é executado.

2. Execução do bloco: O bloco de código dentro das chaves do bloco `if` ou 
`else` é executado de acordo com o resultado da avaliação da condição.

Aqui está um exemplo simples:

```{.js linenums="1"}
let idade = 18;

if (idade >= 18) {
    console.log("Você é maior de idade.");
} else {
    console.log("Você é menor de idade.");
}

// Você é maior de idade.
```

Neste exemplo, a condição `idade >= 18` é avaliada. Se for verdadeira, a 
mensagem "Você é maior de idade." será impressa; caso contrário, a mensagem 
"Você é menor de idade." será impressa.

Também podemos usar `else if` para lidar com múltiplas condições. Por exemplo:

```{.js linenums="1"}
let nota = 75;

if (nota >= 90) {
    console.log("Aprovado com A.");
} else if (nota >= 80) {
    console.log("Aprovado com B.");
} else if (nota >= 70) {
    console.log("Aprovado com C.");
} else {
    console.log("Reprovado.");
}

// Aprovado com B.
```

Neste exemplo, o código verifica a nota do aluno e imprime a mensagem 
apropriada com base na nota obtida. Se nenhuma das condições for atendida, a 
mensagem "Reprovado." será impressa.