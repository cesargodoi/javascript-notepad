# For...in

Os laços `for...in` em JavaScript são usados para iterar sobre as propriedades 
enumeráveis de um `objeto`. Eles permitem percorrer os nomes de propriedades de 
um objeto, em oposição à iteração sobre os valores dessas propriedades. 
Aqui está a estrutura básica de um laço `for...in`:

```{.js linenums="1"}
for (let propriedade in objeto) {
  // código a ser executado para cada propriedade
}
```

Funciona assim:

1. `for`: A palavra-chave `for` é usada para iniciar o loop.
2. `(let propriedade in objeto)`: A expressão entre parênteses especifica três 
partes:
   - `let propriedade`: Isso cria uma variável chamada "propriedade" que será 
   usada para armazenar o nome de cada propriedade do objeto enquanto iteramos 
   sobre ele.
   - `in`: É o operador que define a relação entre a variável "propriedade" e o 
   objeto que estamos iterando.
   - `objeto`: Este é o objeto sobre o qual você deseja iterar.

3. `{}`: O bloco de código dentro das chaves `{}` contém as instruções a serem 
executadas para cada propriedade do objeto.

A cada iteração do loop, a variável "propriedade" conterá o nome da propriedade 
do objeto, e você pode acessar o valor correspondente usando a notação de 
colchetes `objeto[propriedade]`.

Aqui está um exemplo simples:

```{.js linenums="1"}
var pessoa = {
  nome: "João",
  idade: 30,
  cidade: "São Paulo"
};

for (var prop in pessoa) {
  console.log(prop + ": " + pessoa[prop]);
}

// nome: João
// idade: 30
// cidade: São Paulo
```

Neste exemplo, o loop `for...in` iterará sobre as propriedades do objeto 
"pessoa" (nome, idade e cidade) e imprimirá seus nomes e valores. Certifique-se 
de que as propriedades que você deseja iterar sejam enumeráveis, uma vez que 
nem todas as propriedades de um objeto são enumeráveis por padrão.