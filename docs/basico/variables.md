# Variáveis e Constantes

## let e var

Em javascript podemos usar `let` e `var` para declarar variáveis.
No entanto devemos dar preferência ao `let`, pois é mais moderna (ECMAScript 2015 - ES6).   

>`let` tem escopo de bloco    
>`var`  tem escopo de função

Regra Geral e boas práticas para se nomear **variáveis** no javascript:  

- Variáveis são **case-sensitive** (diferencia maiúsculas de minúsculas);   
- Não podemos criar variáveis com palavras reservadas do javascript;   
- Não podemos usar espaços ' ' ou hifen '-';   
- Não podemos começar o nome da variável com números;   
- Variáveis precisam ter nomes significativos   
- Utilizamos notação **camelCase**
- Não podemos redeclarar variáveis com `let`
- Sempre dê preferência em usar `let` ao invés de `var`  

```{.js linenums="1"}
let name;  // variável declarada sem nenhum valor atribuido 
console.log(name);  // returns undefined

name = "Maria Eneida";
console.log(name);  // retorna Maria Eneida

let otherName = "Cesar Godoi";  // variável declarada com valor atribuido
console.log(otherName);  // returno Cesar Godoi


var cidade = "São Paulo";  // variável declarada com valor atribuído
console.log(cidade);  // retorna São Paulo

var cidade = "Bauru";  // 'var' pode ser re-declarada sem provocar erro
console.log(cidade);  // retorna Bauru
```

## const

Em javascript nós usamos `const` para declarar constantes.

No que diz respeito às regras e boas práticas na nomeação de **constantes**, 
podemos dizer que além das descritas para `let` e `var`, temos as seguintes:

- Constantes precisam ser atribuídas com um valor ao serem declaradas;
- Não podemos redeclarar constantes com `constant`;
- Sempre dê preferência em usar `const` ao invés de `let` ou `var` (quando possível);

```{.js linenums="1"}
const pi = 3.14;
console.log(pi);  // retorna 3.14
```