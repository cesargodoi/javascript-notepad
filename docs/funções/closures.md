# Closures

Uma **"closure"** é uma função que **"lembra"** o ambiente em que foi criada, incluindo 
todas as variáveis locais e parâmetros da função exterior a ela. Isso permite 
que a função tenha acesso a essas variáveis mesmo após a função externa ter 
sido concluída e retornada. As closures são uma característica poderosa da 
linguagem e têm várias aplicações.

Para entender melhor as closures, é importante ter em mente os seguintes 
conceitos:

1. Funções aninhadas: Em JavaScript, você pode definir funções dentro de outras 
funções. A função interna é chamada de função aninhada.

2. Escopo léxico: Em JavaScript, as funções são definidas com base em um escopo 
léxico, o que significa que elas têm acesso às variáveis de seu ambiente pai 
(função que a envolve).

Uma closure ocorre quando uma função interna (função aninhada) é retornada de 
uma função externa e, em seguida, é chamada fora do escopo da função externa. 

Aqui está um exemplo simples de uma closure:

```{.js linenums="1"}
function outerFunction(inicio) {
    let [var1, var2, var3] = "<| || |>".split(' ');

    function innerFunction(fim) {
        return `${var1} ${inicio} ${var2} ${fim} ${var3}`;
    }

    return innerFunction; // Retorna a função interna
}

const teste = outerFunction('Aqui é o início');
console.log(teste('aqui o fim'));  // <| Aqui é o início || aqui o fim |>
```

Neste exemplo, `innerFunction` é uma closure porque ela "lembra" o escopo de 
`outerFunction` mesmo após a `outerFunction` ter retornado e foi atribuída a 
`closure`.

As closures são úteis para criar funções que encapsulam estados e 
comportamentos específicos, permitindo que você crie funções que mantenham 
informações entre chamadas, como funções de fábrica, geradores, manipuladores 
de eventos e muito mais. Elas são uma parte fundamental do JavaScript e 
desempenham um papel importante na criação de código flexível e reutilizável.

Um exemplo mais prático:

```{.js linenums="1"}
function multiplicador(multipl) {
    return function (num) {
        return num * multipl;
    }
}

const duplica = multiplicador(2);
const triplica = multiplicador(3);

console.log(duplica(35));  // 70
console.log(triplica(35));  // 105
```