# Declaração de funções

Em JavaScript, você pode declarar funções de várias maneiras. As formas mais 
comuns de declarar funções são a `function declaration` (forma tradicional), 
a `function expression` e temos também as `arrow functions`.

### function declaration

```{.js linenums="1"}
function nomeDaFuncao(parametros) {
    // corpo da função
    return resultado  // pode ou não retornar um resultado
}
```

Para funções tradicionais, ocorre o `hoisting`, que é a elevação dessas funções 
para o início do script em tempo de execução, o que permite invocar (em tempo 
de desenvolvimento) a função, mesmo antes dela ser declarada.

```{.js linenums="1"}
falaOie();     // função invocada antes da sua declaração  ->  oie

function falaOie() {
    console.log('oie');
}
```

### Function expression

O fato de as funções serem objetos de primeira classe (first-class objects), 
nos permite atribuí-las à variáveis.  Isso justifica esta segunda forma de 
declarar nossas funções.

```{.js linenums="1"}
const dobra = function (num) {
    return num * 2;
}

console.log(dobra(2));   // 4
```

Podemos inclusive receber uma função como um parâmetro de outra função.

```{.js linenums="1"}
function executaFuncao(funcao) {
    console.log('O resultado da função é:');
    funcao();
}
executaFuncao(falaOie);   // O resultado da função é:
                          // oie
```

### Arrow function

É a forma mais moderna de declararmos uma função

```{.js linenums="1"}
const funcArrow = () => {
    console.log('sou uma arrow function');
}
funcArrow();  // sou uma arrow function
```

Podemos atribuir uma função à um parametro de um objeto

```{.js linenums="1"}
const pessoa = {
    nome: 'Cesar',
    // falar: () => console.log('e aí, tudo bem?'),  // com arrow
    falar() { console.log('e aí, tudo bem?') },      // nova forma
}
console.log(pessoa.nome);  // Cesar
pessoa.falar();            // e aí, tudo bem?
```
