# Short Circuit (curto circuito)

Um "short circuit" refere-se a uma técnica de avaliação de expressões lógicas 
que pode ser usada para determinar rapidamente o resultado de uma expressão com 
base na primeira parte avaliada. Isso é particularmente útil em expressões 
lógicas compostas, como aquelas envolvendo operadores lógicos `&&` (E lógico) e 
`||` (OU lógico).

Existem dois tipos principais de "short circuit" em JavaScript:

## Operador And ( && )

Quando você usa o operador `&&`, a expressão é avaliada da esquerda para 
a direita. Se a primeira parte (à esquerda) da expressão for avaliada como 
falsa, a segunda parte (à direita) não será avaliada, economizando recursos. 
Isso é útil para expressões em que todas as partes precisam ser verdadeiras 
para que a expressão seja verdadeira.

Exemplo:
```{.js linenums="1"}
function sayHello(name) {
    return `Hello ${name}`;
}

let toPrint = '';
console.log(toPrint && sayHello('Otávio'));  // 

toPrint = 'a';
console.log(toPrint && sayHello('Sergio'));  //  Sergio
```

## Operador Or ( || )

Com o operador `||`, a expressão é novamente avaliada da esquerda para a 
direita. No entanto, se a primeira parte (à esquerda) for avaliada como 
verdadeira, a segunda parte (à direita) não será avaliada, economizando 
recursos. Isso é útil quando você deseja fornecer um valor padrão se a 
primeira parte for falsa.

Exemplo:
```{.js linenums="1"}
const userColor = 'red';
const defaultColor = userColor || 'black';

console.log(defaultColor)  // red

userColor = '';
console.log(defaultColor)  // black

```
## Conclusão

O uso de short circuit é uma técnica comum em JavaScript para melhorar a 
eficiência do código e evitar erros desnecessários, especialmente ao lidar com 
condições e valores padrão. No entanto, é importante usá-lo com cuidado, pois 
pode afetar a legibilidade do código se não for usado de forma apropriada.