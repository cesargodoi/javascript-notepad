# Valores e Tipos

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


// mesmo exemplo com object
const f = { name: 'Cesar', age: 53 }
const g = { ...f }

f.name = 'Jady'
console.log(f, g);
```

## Tipos

### strings
```{.js linenums="1"}
const firstName = "Cesar";
const lastName = 'Godoi';
const cityOfBirth = `Bauru`;
```

### numbers
```{.js linenums="1"}
const integer = 12;
const float = 12.34;
```

### undefined
```{.js linenums="1"}
let country;
var district;
```

### null
```{.js linenums="1"}
const dog = null;
```

### boolean
```{.js linenums="1"}
const exist = true;
const doesNotExist = false;
```

### symbol
```{.js linenums="1"}
const symbl = Symbol('é nois');
```

### typeof
Podemos usar o método `typeof` para descobrir o tipo de uma variável ou constante.
```{.js linenums="1"}
console.log(`${cityOfBirth} = ${typeof cityOfBirth}`);
console.log(`${float} = ${typeof float}`);
console.log(`${country} = ${typeof country}`);
console.log(`${dog} = ${typeof dog}`);  // o typeof de null será object (bug do javascript)
console.log(`${doesNotExist} = ${typeof doesNotExist}`);
console.log(`${typeof symbl} descr: ${symbl.description}`);
```