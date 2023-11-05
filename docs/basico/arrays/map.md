# Map

O método `map()` é usado para criar um novo array a partir de um array 
existente, aplicando uma função a cada elemento do array original e coletando 
os resultados em um novo array. O novo array terá o mesmo comprimento do array 
original, mas os valores em cada posição serão determinados pela função de 
mapeamento.

A sintaxe básica do método `map()` é a seguinte:

```{.js linenums="1"}
const novoArray = arrayOriginal.map(function(elemento, índice, array) {
  // Código que transforma o elemento
  // Retorna o novo valor para o novo array
});
```

Aqui estão os parâmetros e seus significados:

- `elemento`: O valor do elemento atual do array original.
- `índice` (opcional): A posição do elemento no array original.
- `array` (opcional): O array original sendo percorrido.

O método `map()` itera sobre cada elemento do array original, chama a função 
de mapeamento fornecida para cada elemento e armazena o valor retornado no novo 
array. O novo array é então retornado como resultado.

Aqui está um exemplo simples que usa o método `map()` para duplicar cada 
elemento de um array:

```{.js linenums="1"}
const números = [1, 2, 3, 4, 5];
const duplicados = números.map(function(numero) {
  return numero * 2;
});

console.log(duplicados);  // [2, 4, 6, 8, 10]
```

Podemos também usar `arrow functions` para tornar o código mais conciso:

```{.js linenums="1"}
const números = [1, 2, 3, 4, 5];
const duplicados = números.map(numero => numero * 2);

console.log(duplicados);  // [2, 4, 6, 8, 10]
```

O método `map()` é muito útil para transformar dados em arrays e é uma das 
ferramentas fundamentais para trabalhar com arrays em JavaScript.

## Exemplos

### Usando arrow function

```{.js linenums="1"}
const numeros = [5, 50, 80, 1, 2, 3, 5, 8, 7];

// dobre o valor de cada número
const dobro = numeros.map(num => num * 2);
console.log(dobro);  // [ 10, 100, 160,  2,  4,  6, 10,  16,  14 ]
```

### Array de Objects

```{.js linenums="1"}
const pessoas = [
    { nome: 'Jady', idade: 38 },
    { nome: 'Cesar', idade: 53 },
    { nome: 'Maria', idade: 65 },
    { nome: 'João', idade: 23 },
    { nome: 'Floriano', idade: 63 },
]


// retorne uma string com o nome da pessoa
const nomes = pessoas.map(obj => obj.nome);
console.log(nomes);  // [ 'Jady', 'Cesar', 'Maria', 'João', 'Floriano' ]


// retorne a chave 'nome'do objeto (retorne apenas idade)
const idades = pessoas.map(obj => ({ idade: obj.idade }));
console.log(idades);
// [
//   { idade: 38 },
//   { idade: 53 },
//   { idade: 65 },
//   { idade: 23 },
//   { idade: 63 }
// ]


// adicione uma chave de id em cada objeto
const ids = pessoas.map((obj, i) => {
    const newObj = { ...obj };
    newObj.id = i;
    return newObj;
});
console.log(ids);
// [
//     { nome: 'Jady', idade: 38, id: 0 },
//     { nome: 'Cesar', idade: 53, id: 1 },
//     { nome: 'Maria', idade: 65, id: 2 },
//     { nome: 'João', idade: 23, id: 3 },
//     { nome: 'Floriano', idade: 63, id: 4 }
// ]
```