# Operador Ternário

Um operador ternário é um operador condicional que permite avaliar uma 
expressão e retornar um valor com base em uma condição. Ele é chamado de 
"ternário" porque envolve três operandos: a condição a ser testada, o valor a 
ser retornado se a condição for verdadeira e o valor a ser retornado se a 
condição for falsa.

A sintaxe básica do operador ternário é a seguinte:

```javascript
condição ? valor_se_verdadeiro : valor_se_falso;
```

Aqui está como funciona:

1. A condição é avaliada primeiro.
2. Se a condição for verdadeira, o valor após o ponto de interrogação (`?`) 
é retornado.
3. Se a condição for falsa, o valor após os dois pontos (`:`) é retornado.

Exemplo:

```{.js linenums="1"}
var idade = 20;
var mensagem = idade >= 18 ? "Maior de idade" : "Menor de idade";

console.log(mensagem);  // O resultado será "Maior de idade" neste caso.
```

Neste exemplo, a condição `idade >= 18` é avaliada. Se for verdadeira, a string 
"Maior de idade" é atribuída à variável `mensagem`. Caso contrário, a string 
"Menor de idade" é atribuída.

O operador ternário é uma maneira concisa de escrever expressões condicionais 
em JavaScript e pode ser útil em muitas situações, como na atribuição de 
valores com base em condições simples.