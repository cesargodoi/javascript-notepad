# Strings


Em JavaScript, uma `string` é um tipo de dado que representa uma sequência de caracteres. 
As strings são usadas para armazenar e manipular texto em JavaScript. 
Uma `string` pode conter letras, números, símbolos e espaços.

```{.js linenums="1"}
// indexação
//          0123456789...
let text = "O rato comeu o Queijo";

console.log(text[4]);   // t
console.log(text[13]);  // o
console.log(text[19]);  // j
console.log(text[21]);  // undefined
console.log(text[-1]);  // undefined
```

## Métodos

### charAt
```{.js linenums="1"}
//String.charAt(pos: number): string
console.log(text.charAt(3));   // a  
console.log(text.charAt(21));  // ''
```

### concat
```{.js linenums="1"}
// String.concat(...strings: string[]): string
console.log(text.concat('!'));  // O rato comeu o queijo!
```

### indexOf
```{.js linenums="1"}
// String.indexOf(searchString: string, position?: number | undefined): number
console.log(text.indexOf('comeu'));  // 7  (inicia na posição 7)
console.log(text.indexOf('Comeu'));  // -1 (nada foi encontrado)
```

### lastIndexOf
```{.js linenums="1"}
// String.lastIndexOf(searchString: string, position?: number | undefined): number
console.log(text.lastIndexOf('o'));  // 20 (mostra a última ocorrência)
```

### match
```{.js linenums="1"}
// Regular Expression
console.log(text.match(/[A-Z]/));  // ['O', index: 0, input: 'O rato... ] 
console.log(text.match(/[A-Z]/g));  // ['O', 'Q'] 
```

### search
```{.js linenums="1"}
// Regular Expression
console.log(text.search(/o/));  // 5 (primeira ocorrência)
```

### replace
```{.js linenums="1"}
// Regular Expression
console.log(text.replace('o', '#'));   // O rat# comeu o Queijo
console.log(text.replace(/o/, '#'));   // O rat# comeu o Queijo
console.log(text.replace(/o/g, '#'));  // O rat# c#meu # Queij#
```

### length
```{.js linenums="1"}
console.log(text.length);  // 21 (do 0 ao 20)
```

### slice
```{.js linenums="1"}
// String.slice(start?: number | undefined, end?: number | undefined): string
console.log(text.slice(7, 11 + 1));  // comeu
console.log(text.slice(-6));         // Queijo
console.log(text.slice(-6, -3));     // Que
```

### split
```{.js linenums="1"}
console.log(text.split(' '));  // [ 'O', 'rato', 'comeu', 'o', 'Queijo' ]
console.log(text.split(' ', 2));  // [ 'O', 'rato' ]
```

### toUpperCase
```{.js linenums="1"}
console.log(text.toUpperCase());  // O RATO COMEU O QUEIJO
```

### toLowerCase
```{.js linenums="1"}
console.log(text.toLowerCase());  // o rato comeu o queijo
```