# Switch - Case

O `switch - case` é uma estrutura de controle de decisão em JavaScript que é usada 
para avaliar uma expressão e executar código com base no valor dessa expressão. 
É frequentemente usado para substituir múltiplas instruções `if-else` quando 
você precisa fazer diferentes ações com base em um valor específico. A 
estrutura geral do `switch - case` é a seguinte:

```{.js linenums="1"}
switch (expressao) {
  case valor1:
    // Código a ser executado se a expressão for igual a valor1
    break;
  case valor2:
    // Código a ser executado se a expressão for igual a valor2
    break;
  // ... Mais casos
  default:
    // Código a ser executado se nenhum dos casos anteriores for correspondido
}
```

O `switch - case` funciona da seguinte maneira:

1. A expressão é avaliada uma vez.
2. O valor resultante da expressão é comparado com cada caso (valor1, valor2, 
etc.) na ordem em que eles são listados. 
3. Quando uma correspondência é encontrada, o código dentro desse caso é 
executado.
4. A instrução `break` é usada para sair do `switch - case` após a execução do 
código do caso correspondente. Isso evita que os casos subsequentes sejam 
executados acidentalmente. No entanto, o `break` não é estritamente necessário; 
se você omiti-lo, o código continuará sendo executado nos casos subsequentes 
até encontrar um `break` ou atingir o final do `switch - case`.
5. Se nenhum caso corresponder ao valor da expressão, o código dentro do bloco 
`default` é executado (se houver um bloco `default`). O bloco `default` é 
opcional.

## Exemplo

```{.js linenums="1"}
const date = new Date(2023, 2, 22);
let dayOfWeekStr;

switch (date.getDay()) {
    case 0:
        dayOfWeekStr = 'domingo';
        break;
    case 1:
        dayOfWeekStr = 'segunda-feira';
        break;
    case 2:
        dayOfWeekStr = 'terça-feira';
        break;
    case 3:
        dayOfWeekStr = 'quarta-feira';
        break;
    case 4:
        dayOfWeekStr = 'quinta-feira';
        break;
    case 5:
        dayOfWeekStr = 'sexta-feira';
        break;
    case 6:
        dayOfWeekStr = 'sábado';
        break;
    default:
        dayOfWeekStr = 'dia normal'
        break;
}

const localDate = date.toLocaleString('pt-BR', { timeZone: 'UTC' }).split(',')
console.log(`Dia ${localDate[0]} foi ${dayOfWeekStr}.`);

// Dia 22/03/2023 foi quarta-feira.
```