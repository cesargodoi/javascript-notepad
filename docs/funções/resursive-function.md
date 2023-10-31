# Funções recursivas

É uma função que chama a si mesma para realizar uma tarefa. Em termos mais 
simples, é um conceito onde uma função é definida em termos de si mesma. Isso 
é comum em programação, pois permite a implementação de algoritmos complexos 
de forma mais elegante e concisa.

Aqui está um exemplo simples de uma função recursiva em JavaScript que calcula 
o fatorial de um número:

```{.js linenums="1"}
function fatorial(n) {
  if (n > 10) return;  // é importande determinar quando ocorrerá a saída
  if (n === 0) {
    return 1;
  } else {
    return n * fatorial(n - 1);
  }
}

console.log(fatorial(5));  // 120
```

Neste exemplo, a função `fatorial` é definida em termos de si mesma, onde ela 
calcula o fatorial de um número `n` multiplicando `n` pelo fatorial de `n - 1`. 
A recursão continua até que `n` seja igual a zero, momento em que a função 
retorna 1 (o caso base). Essa função recursiva é uma implementação clássica de 
como calcular o fatorial de um número.

No entanto, é importante ter cuidado ao usar funções recursivas, pois elas 
podem levar a estouro de pilha (stack overflow) se não houver um caso base 
adequado ou se a recursão for muito profunda. Certifique-se sempre de definir 
um caso base e garantir que a recursão tenha uma condição de parada para 
evitar problemas de desempenho.