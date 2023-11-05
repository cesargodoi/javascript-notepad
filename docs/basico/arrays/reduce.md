# Reduce

A função `reduce` é um método de array que permite reduzir (ou "acumular") os 
elementos de um array a um único valor. Ela é muito útil quando você deseja 
realizar alguma operação em todos os elementos de um array e produzir um 
resultado único, como somar todos os elementos, calcular a média, encontrar o 
maior ou o menor valor, etc.

A sintaxe básica da função `reduce` é a seguinte:

```{.js linenums="1"}
array.reduce(callback[, initialValue]);
```

- `array`: O array no qual você deseja operar.
- `callback`: Uma função que é executada em cada elemento do array e recebe 
quatro argumentos: `acumulador`, `valor atual`, `índice atual` e 
`array original`. O acumulador é o resultado parcial da operação e o valor 
atual é o elemento atual do array.
- `initialValue` (opcional): Um valor inicial para o acumulador. Se fornecido, 
a função `reduce` começará a operação com esse valor como acumulador. Se não 
fornecido, o acumulador será o primeiro elemento do array e a função `callback` 
começará a operação a partir do segundo elemento.

Aqui está um exemplo simples de uso do `reduce` para somar todos os elementos 
de um array:

```{.js linenums="1"}
const numbers = [1, 2, 3, 4, 5];

const sum = numbers.reduce((accumulator, currentValue) => {
  return accumulator + currentValue;
}, 0);

console.log(sum);  // Output: 15
```

Neste exemplo, `0` é fornecido como `initialValue`, e a função `callback` soma 
o acumulador com o valor atual em cada iteração, resultando na soma total de 
todos os elementos do array.

A função `reduce` é versátil e pode ser usada para realizar várias operações em 
arrays, dependendo da lógica definida na função `callback`. Você pode usá-la 
para encontrar o maior valor, o menor valor, calcular a média, concatenar 
strings e muito mais. A chave para seu uso eficaz está na definição da função 
`callback` de acordo com a operação desejada.

## Exemplos

Dado o array abaixo:
```{.js linenums="1"}
const numeros = [5, 50, 80, 1, 2, 3, 5, 8, 7, 11, 15, 22, 27];
```

### some todos os valores
```{.js linenums="1"}
const total = numeros.reduce((tot, num) => tot += num, 0);
console.log(total);  // 236
```


### retorne um array com os pares (filter)
```{.js linenums="1"}
const pares = numeros.reduce((pars, num) => {
    if (num % 2 === 0) pars.push(num);
    return pars;
}, [])
console.log(pares);  // [ 50, 80, 2, 8, 22 ]
```

### retorne um array com o dobro dos valores (map)
```{.js linenums="1"}
const dobro = numeros.reduce((dobro, num) => {
    dobro.push(num * 2);
    return dobro;
}, [])
console.log(dobro);  // [ 10, 100, 160, 2, 4, 6, 10, 16, 14, 22, 30, 44, 54 ]
```

### retorne a pessoa mais velha
```{.js linenums="1"}
const pessoas = [
    { nome: 'Jady', idade: 38 },
    { nome: 'Cesar', idade: 53 },
    { nome: 'Maria', idade: 65 },
    { nome: 'João', idade: 23 },
]
const maisVelha = pessoas.reduce((old, obj) => {
    if (old.idade > obj.idade) return old;
    return obj
})
console.log(maisVelha);   // { nome: 'Maria', idade: 65 }
```

### all-in-one

Encadeando `filter` + `map` + `reduce` 😊

```{.js linenums="1"}
const numeros = [5, 50, 80, 1, 2, 3, 5, 8, 7, 11, 15, 22, 27];

// retorne a soma de todos os números pares
const somaDosPares = numeros
    .filter(num => num % 2 === 0)
    .map(num => num * 2)
    .reduce((tot, num) => tot += num, 0);
console.log(somaDosPares);  // 324
```