# Parametros

Os parâmetros de função são os valores que podemos passar para uma função 
quando a chamamos. Os parâmetros permitem que forneçamos dados de entrada para 
uma função, que a função pode então usar em seu corpo para executar uma tarefa 
específica. Os parâmetros são definidos na declaração de função e atuam como 
variáveis locais dentro do escopo da função.

```{.js linenums="1"}
function soma(a, b) {
    return a + b;
}

soma(10, 45);  // 55
```


### Arguments

No JavaScript, quando não declaramos os argumentos necessários numa função, mas 
vamos invocá-la passando algum argumento, o JavaScript não causa erros,
pois armazena todos estes argumentos numa variável especial chamada:
`arguments`

```{.js linenums="1"}
function getArgs() {
    console.log(arguments);
}

getArgs('cavalo', 'lambreta', 123, 45);  // [Arguments] { '0': 'cavalo', '1': 'lambreta', '2': 123, '3': 45 }

function getArgs2(a, b) {
    console.log(a, b, arguments);
}

getArgs2('Égua', 'moto', 12);  // Égua moto [Arguments] { '0': 'Égua', '1': 'moto', '2': 12 }
```

Embora não tenhamos 'arguments' em arrow functions, podemos usar o 
`spread operator` para trabalhar da mesma forma.

```{.js linenums="1"}
const myNumbers = (...args) => {
    console.log(args);
}
myNumbers(1, 2, 3, 4, 5, 6, 7, 8);  // [1, 2, 3, 4, 5, 6, 7, 8]
```


### Valor padrão

Também podemos pré-determinar o valor padrão de algum parâmetro, assim, caso 
no ató de invocar uma função, nenhum valor seja passado ao parâmetro, a função
vai assumir o valor padrão.

```{.js linenums="1"}
function multiplica(a, b = 1, c = 21) {
    return a * b + c;
}

console.log(multiplica(23, 12, 4));         // 280
console.log(multiplica(27));                // 48
console.log(multiplica(3, 3));              // 30
console.log(multiplica(4, undefined, 16));  // 20
```


### Destructuring

Destructuring é uma forma de extrair valores de objetos ou arrays e atribuí-los 
a variáveis de forma mais concisa. Isso pode tornar o código mais legível e 
facilitar a manipulação de dados. 

```{.js linenums="1"}
function gessNumbers([num1, num2, num3]) {
    console.log(num1, num2, num3);
}

gessNumbers([134, 475, 65]);  // 134 475 65

function fullName({ name, lastname }) {
    console.log(name, lastname);
}

fullName({ name: 'Cesar', lastname: 'Godoi' });  // Cesar Godoi
```

### Exemplo

Considere a seguinte função que recebe como primeiro artumento um **operador** 
e uma **lista de números** que devem ser processados de acordo com o 
**operador**.

```{.js linenums="1"}
function calc(oper, ...numbers) {
    if (oper === '+') {
        let sum = 0;
        numbers.forEach((num) => sum += num);
        return sum;
    }
    if (oper === '-') {
        let sub = Math.max(...numbers);
        numbers = numbers.filter((num) => num !== sub);
        numbers.forEach((num) => sub -= num);
        return sub
    }
    if (oper === '*') {
        let mult = 1;
        numbers.forEach((num) => mult *= num);
        return mult;
    }
    if (oper === '/') {
        let div = numbers.shift();
        numbers.forEach((num) => div /= num);
        return div;
    }
}
console.log(calc('+', 1, 2, 3, 4));  // 10
console.log(calc('-', 12, 3, 34));  // 19
console.log(calc('*', 2, 3, 4, 5));  // 120
console.log(calc('/', 20, 2, 4));  // 2.5
```
