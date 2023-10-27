# Números

Os principais tipos de números em JavaScript são:

**Números inteiros (Integers)**: Representam números inteiros, positivos ou negativos, sem casas decimais. Exemplos: 42, -10, 0.

**Números de ponto flutuante (Floating-Point Numbers)**: São usados para representar números com casas decimais. JavaScript usa o padrão IEEE 754 para representar números de ponto flutuante de precisão dupla. Exemplos: 3.14, -0.5, 1.0.

```{.js linenums="1"}
// Alguns exemplos
let num1 = 1;
let num2 = 2.5;

console.log(num1 + num2);  // 3.5

// .toString()
console.log(num1.toString() + num2);  // 12.5 (sting)

let num3 = 123;
console.log(num3.toString(2));   // 1111011 (binário)
console.log(num3.toString(8));   // 173 (octal)
console.log(num3.toString(16));  // 7b (hexadecimal)

// .toFixed()
let num4 = 23.3566352435
console.log(num4.toFixed(2));  // 23.36

// Number.isIntteger()
console.log(Number.isInteger(num1));  // true
console.log(Number.isInteger(num2));  // false

// Number.isNaN()
let temp1 = num2 * 'X';
let temp2 = num2 * '10';
console.log(Number.isNaN(temp1));  // true
console.log(Number.isNaN(temp2));  // false
```

> O javascript usa IEEE 754-2008 para gerenciar os seu cálculos.

```{.js linenums="1"}
// imprecisões
let n1 = 0.7;
let n2 = 0.1;

console.log(n1 + n2);  // 0.7999999999999999 🤔

console.log(100 / 0);  // Infinity 🤔
```