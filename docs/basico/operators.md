# Operadores

Em javascript nós temos operadores aritiméticos, de incremento e de atribuição

## Aritiméticos

adição / concatenação (+)
```{.js linenums="1"}
console.log(2 + 3);      // 5
console.log('b' + 'a');  // ba
console.log('a' + 15);   // a15
```


subtração (-)
```{.js linenums="1"}
console.log(10 - 3);     // 7
```

multiplicação (*)
```{.js linenums="1"}
console.log(5 * 5);      // 25
```

divisão (/)
```{.js linenums="1"}
console.log(15 / 3);     // 5
```

potenciação (**)
```{.js linenums="1"}
console.log(2 ** 3);     // 8
```

módulo da divisão (%)
```{.js linenums="1"}
console.log(18 / 5)      // 3
```

A precedência de operadores é a seguinte:

| 1. | (…) | o que estiver dentro dos parentesis |
| --- | --- | --- |
| 2. | ** | o que for potenciação |
| 3. | *   /   % | multiplicação, divisão e módulo da divisão |
| 4. | +   - | adição e subtração |

## Incremento (++)

Cada vez que é usado, incrementa (ou decrementa) 1 do valor da variável
pode ser usado antes ou depois da variável.

```{.js linenums="1"}
let num = 1;
console.log(num++);  // imprime 1 e atualiza o valor de num para 2
console.log(num);    // 2
console.log(++num);  // atualiza o valor de num para 3 e imprime 3
console.log(num);    // 3
```

## Decremento (- -)

```{.js linenums="1"}
console.log(num--);  // imprime 3 e atualiza o valor de num para 2
console.log(num);    // 2
console.log(--num);  // atualiza o valor de num para 1 e imprime 1
console.log(num);    // 1
```

## Atribuição
```{.js linenums="1"}
// += 
console.log(num += 10); // num = num + 10 -> 11
// -=
console.log(num -= 2);  // num = num -  2 ->  9
// *=
console.log(num *= 2);  // num = num *  2 -> 18
// /=
console.log(num /= 3);  // num = num /  3 ->  6
// **=
console.log(num **= 2); // num = num ** 2 -> 36
```

## Comparação

### maior que ( > ) 
```{.js linenums="1"}
console.log(10 > 5);   // true
console.log(10 > 10);  // false
console.log(10 > 11);  // false
```

### maior igual a ( >= )
```{.js linenums="1"}
console.log(10 >= 5);   // true
console.log(10 >= 10);  // true
console.log(10 >= 11);  // false
```

### menor que ( < )
```{.js linenums="1"}
console.log(10 < 5);   // false
console.log(10 < 10);  // false
console.log(10 < 11);  // true
```

### menor igual a ( <= )
```{.js linenums="1"}
console.log(10 <= 5);   // false
console.log(10 <= 10);  // true
console.log(10 <= 11);  // true
```

### igual a ( == )      
> checa apénas o valor (evitar o uso)

```{.js linenums="1"}
console.log(10 == 5);     // false
console.log(10 == 10);    // true
console.log(10 == '10');  // true (por coerção de tipos)
```

### diferente de ( != )
> checa apénas o valor (evitar o uso)

```{.js linenums="1"}
console.log(10 != 5);     // true
console.log(10 != 10);    // false
console.log(10 != '10');  // false (por coerção de tipos)
```

### estritamente igual a ( === )
> checa valor e tipo

```{.js linenums="1"}
console.log(10 === 5);     // false
console.log(10 === 10);    // true
console.log(10 === '10');  // false
```

### estritamente diferente de ( !== )
> checa valor e tipo

```{.js linenums="1"}
console.log(10 !== 5);     // true
console.log(10 !== 10);    // false
console.log(10 !== '10');  // true
```

## Lógicos

### And ( && )
```{.js linenums="1"}
console.log(true && true);    // true
console.log(true && false);   // false
console.log(false && true);   // false
console.log(false && false);  // false
```
### Or ( || )
```{.js linenums="1"}
console.log(true || true);    // true
console.log(true || false);   // true
console.log(false || true);   // treu
console.log(false || false);  // false
```
### Not ( ! )
```{.js linenums="1"}
console.log(!true);           // false
console.log(!false);          // true
```