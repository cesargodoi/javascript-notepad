# Arrays

Um `array` em JavaScript é uma estrutura de dados que permite armazenar uma 
coleção de elementos em uma única variável. Os elementos em um `array` podem 
ser de qualquer tipo de dados, como `números`, `strings`, `objetos`, `funções` 
e até outros `arrays`.   
Cada elemento em um `array` é acessado por um `índice`, que é um número 
inteiro que representa a posição do elemento no `array`.

Vamos considerar o seguinte `array` abaixo:  

```{.js linenums="1"}
const alunos = ['Cesar', 'Otávio', 'Jady'];
console.log(alunos);                   // ['Cesar', 'Otávio', 'Jady']
console.log(typeof alunos);            // object
console.log(alunos instanceof Array);  // true
```

Podemos acessar os elementos do `array` à partir dos seus `índices`:
```{.js linenums="1"}
console.log(alunos[0]);   // Cesar
console.log(alunos[10]);  // undefined
```

Também é possivel atualizar um elemento do `array` usando o seu `índice`:
```{.js linenums="1"}
alunos[1] = 'Floriano';
console.log(alunos);  // ['Cesar', 'Floriano', 'Jady']
```

Podemos inserir um novo elemento a um `array` apontando esse elemento para um 
`índice` maior do que o último `índice` do `array`.
```{.js linenums="1"}
alunos[3] = 'Otávio';
console.log(alunos);  // ['Cesar', 'Floriano', 'Jady', 'Otávio']
```

## Métodos

### push
Adiciona um elemento ao final da lista
```{.js linenums="1"}
alunos.push('Fon');
console.log(alunos);  // ['Cesar', 'Floriano', 'Jady', 'Otávio', 'Fon']
```

### unshift
adiciona um elemento ao início da lista
```{.js linenums="1"}
alunos.unshift('Edu');
console.log(alunos);  // ['Edu', 'Cesar', 'Floriano', 'Jady', 'Otávio', 'Fon']
```

### pop
remove o último elemento
```{.js linenums="1"}
alunos.pop();
console.log(alunos);                    // ['Edu', 'Cesar', 'Floriano', 'Jady', 'Otávio']
let removido = alunos.pop();            // remove o último elemento e o atribui à variável removido
console.log(`removido = ${removido}`);  // removido = Otávio
console.log(alunos);                    // ['Edu', 'Cesar', 'Floriano', 'Jady']
```

### shift
remove o primeiro elemento 
```{.js linenums="1"}
alunos.shift();
console.log(alunos);                    // ['Cesar', 'Floriano', 'Jady']
removido = alunos.shift();              // remove o primeiro elemento e o atribui à variável removido
console.log(`removido = ${removido}`);  // removido = Cesar
console.log(alunos);                    // ['Floriano', 'Jady']
```

### delete
apaga o conteúdo de um índice
```{.js linenums="1"}
delete alunos[0];
console.log(alunos);  // [<1 empty item>, 'Jady']

// ajustar a lista para os proximos exemplos
alunos[0] = 'Cesar';
alunos.push('Edu');
alunos.push('Otávio');
console.log(alunos);
```

### slice
seleciona elementos sequenciais
```{.js linenums="1"}
console.log(alunos.slice(0, 2));  // ['Cesar', 'Jady']
console.log(alunos.slice(-2));    // ['Edu', 'Otávio']
```

### join
transforma um array em uma string
```{.js linenums="1"}
const nomesAlunos = alunos.join(' ');
console.log(nomesAlunos);  // Cesar Jady Edu Otávio 
```
### concat
concatena arrays
```{.js linenums="1"}
const arr1 = [1, 2, 3];
const arr2 = [4, 5, 6];
const arr3 = arr1.concat(arr2, [7, 8, 9], 'Cesar');
console.log(arr3);  // [ 1, 2, 3, 4, 5, 6, 7, 8, 9, 'Cesar' ]
```

### spread operator `...`
usando o spread operator para concatenar `strings`
```{.js linenums="1"}
const arr4 = [...arr1, 'Cesar', ...arr2, ...[7, 8, 9]];
console.log(arr4);  // [ 1, 2, 3, 'Cesar', 4, 5, 6, 7, 8, 9 ]
```

### splice
O método `splice()` é usado para alterar o conteúdo de um array, adicionando, 
removendo ou substituindo elementos. Ele pode ser usado de várias maneiras e 
possui os seguintes parâmetros:

```{.js linenums="1"}
array.splice(start, deleteCount, item1, item2, ...)
```

- `start`: O índice no array a partir do qual as alterações devem começar.
- `deleteCount`: O número de elementos a serem removidos a partir do `start`. 
Se for zero, nenhum elemento será removido.
- `item1, item2, ...`: Elementos a serem inseridos no array no lugar dos 
elementos removidos.

O método `splice()` retorna um novo array contendo os elementos removidos.

Aqui estão alguns exemplos de como o método `splice()` pode ser usado:

#### Remover elementos
```{.js linenums="1"}
const arr = [1, 2, 3, 4, 5];
const removed = arr.splice(1, 2);  // Remove 2 elementos a partir do índice 1
console.log(arr);                  // [1, 4, 5]
console.log(removed);              // [2, 3]
```

> Simulando `pop` e `shift`:
> ```{.js linenums="1"}
> const arr = ['a', 'b', 'c', 'd', 'e'];
> const removed = arr.splice(-1, 1);   // Remove 'e'  =  arr.pop()
> console.log(arr);                    // ['a', 'b', 'c', 'd']
> console.log(removed);                // ['e']
> const removed2 = arr.splice(0, 1);   // Remove 'a'  =  arr.shift()
> console.log(arr);                    // ['b', 'c', 'd']
> console.log(removed2);               // ['a']
> ```

#### Inserir elementos
```{.js linenums="1"}
const arr = [1, 2, 3, 4, 5];
arr.splice(2, 0, 6, 7);   // Insere os elementos 6 e 7 a partir do índice 2
console.log(arr);         // [1, 2, 6, 7, 3, 4, 5]
```

> Simulando `push` e `unshift`:
> ```{.js linenums="1"}
> const arr = ['b', 'c', 'd'];
> arr.splice(arr.length, 0, 'e');      // Adiciona 'e'  =  arr.push('e')
> console.log(arr);                    // ['b', 'c', 'd', 'e']
> arr.splice(0, 0, 'a');               // Adiciona 'a'  =  arr.unshift('a')
> console.log(arr);                    // ['a', 'b', 'c', 'd', 'e']
> ```


#### Substituir elementos

```{.js linenums="1"}
const arr = [1, 2, 3, 4, 5];
arr.splice(2, 2, 6, 7);   // Substitui os elementos 3 e 4 pelos elementos 
                          // 6 e 7 a partir do índice 2
console.log(arr);         // [1, 2, 6, 7, 5]
```

Tenha em mente que o método `splice()` modifica o array original, e os 
elementos removidos são retornados em um novo array. Portanto, é uma operação 
destrutiva. Certifique-se de entender como o método funciona e de que forma 
ele afetará o seu array antes de utilizá-lo.