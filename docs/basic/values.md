# Valores

## Primitivos

Os valores primitivos são imutáveis:

- string 
- number 
- boolean
- undefined
- null
- bigint
- symbol

> Sempre que os atribuímos à outra variáveis, seus valores são copiados 

```{.js linenums="1"}
let a = 12;
let b = a;  // o valor 12 é copiado para b
console.log(a, b);  // 12 12
b = 17;
console.log(a, b);  // 12 17
```

## Referência

Os valores de referência são mutáveis:

- array
- object
- function

> Sempre que os atribuímos à outra variável, a nova variável aponta para o mesmo endereço na memória

```{.js linenums="1"}
const c = [1, 2, 3];
const d = c;  // a variável d aponta para o mesmo endereço de memória que c

console.log(c, d);  // [1, 2, 3] [1, 2, 3]
d.push(4);
console.log(c, d);  // [1, 2, 3, 4] [1, 2, 3, 4]


// para fazer uma cópia, podemos usar o spread operator `...`
const e = [...d]

console.log(d, e);  // [1, 2, 3, 4] [1, 2, 3, 4]
e.pop();
console.log(d, e);  // [1, 2, 3, 4] [1, 2, 3]


// mesmo exemplo com oobject
const f = { name: 'Cesar', age: 53 }
const g = { ...f }

f.name = 'Jady'
console.log(f, g);
```