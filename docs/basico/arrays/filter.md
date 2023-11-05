# Filter

O método `filter()` é uma função de array que permite criar um novo array a 
partir de um array existente, contendo apenas os elementos que atendem a uma 
determinada condição. Ele não modifica o array original, mas retorna um novo 
array com os elementos filtrados. A sintaxe básica do método `filter()` é a 
seguinte:

```{.js linenums="1"}
const novoArray = arrayOriginal.filter(function(elemento) {
    // Condição de filtragem
    return condição;
});
```

O `filter()` funciona assim:

1. `arrayOriginal`: Este é o array que você deseja filtrar.

2. `function(elemento)`: Esta é a função de callback que é chamada para cada 
elemento do `arrayOriginal`. Ela recebe como primeiro argumento, o elemento 
atual sendo processado.  Mas pode receber também mas dois argumentos: o 
`índice` e o próprio `array`.

3. `condição`: É a condição que você especifica dentro da função de callback. 
Se a condição for avaliada como `true` para um elemento específico, esse 
elemento será incluído no novo array. Se a condição for avaliada como `false`, 
o elemento será excluído do novo array.

O resultado é um novo array contendo apenas os elementos que atendem à condição 
especificada na função de callback.

Aqui está um exemplo simples de uso do método `filter()` para criar um novo 
array contendo apenas números pares de um array original:

```{.js linenums="1"}
const numeros = [1, 2, 3, 4, 5, 6, 7, 8];
const numerosPares = numeros.filter(function(numero) {
    return numero % 2 === 0;
});

console.log(numerosPares);  // [2, 4, 6, 8]
```

Neste exemplo, a função de callback verifica se cada número no array é par 
(ou seja, se o resto da divisão por 2 é igual a 0), e os números pares são 
incluídos no novo array `numerosPares`.

## Exemplos

### Usando arrow function

```{.js linenums="1"}
const numeros = [5, 50, 80, 1, 2, 3, 5, 8, 7, 11, 15, 22, 27];

// retorne os números maiores que 10
const filtered = numeros.filter(num => num > 10);
console.log(filtered);   // [ 50, 80, 11, 15, 22, 27 ]
```

### Array de Objects

```{.js linenums="1"}
const pessoas = [
    { nome: 'Jady', idade: 38 },
    { nome: 'Cesar', idade: 53 },
    { nome: 'Maria', idade: 65 },
    { nome: 'João', idade: 23 },
    { nome: 'Floriano', idade: 63 },
    { nome: 'Nanci', idade: 13 },
]


// retorne as pessoas que tem o nome com 5 letras ou mais
const nameL5 = pessoas.filter(pessoa => pessoa.nome.length >= 5);
console.log(nameL5);
// [
//     { nome: 'Cesar', idade: 53 },
//     { nome: 'Maria', idade: 65 },
//     { nome: 'Floriano', idade: 63 },
//     { nome: 'Nanci', idade: 13 }
// ]


// retorne as pessoas com mais de 50 anos
const idade50 = pessoas.filter(pessoa => pessoa.idade > 50);
console.log(idade50);
// [
//     { nome: 'Cesar', idade: 53 },
//     { nome: 'Maria', idade: 65 },
//     { nome: 'Floriano', idade: 63 }
// ]


// retorne as pessoas cujo nome termina com 'a'
const nomeTerminaA = pessoas.filter(p => p.nome.toLowerCase().endsWith('a'));
console.log(nomeTerminaA);  // [ { nome: 'Maria', idade: 65 } ]
```