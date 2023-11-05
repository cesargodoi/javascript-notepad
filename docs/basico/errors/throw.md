# Throw

A palavra-chave `throw` em JavaScript é usada para lançar exceções (erros) em 
seu código. Quando uma exceção é lançada com `throw`, a execução normal do 
programa é interrompida e o controle é transferido para o bloco `catch` mais 
próximo no contexto de tratamento de exceção (como em uma estrutura 
`try...catch`) que pode manipular a exceção lançada.

Aqui está a sintaxe básica do `throw` em JavaScript:

```{.js linenums="1"}
throw expression;
```

- `expression`: A expressão que representa o valor da exceção a ser lançada. 
Pode ser uma string, um número, um objeto ou qualquer outro tipo de valor.

Aqui está um exemplo simples de como usar `throw`:

```{.js linenums="1"}
function divide(a, b) {
  if (b === 0) {
    throw "Divisão por zero não é permitida.";
  }
  return a / b;
}

try {
  var result = divide(10, 0);
  console.log("Resultado: " + result);
} catch (error) {
  console.error("Erro: " + error);
}

// Divisão por zero não é permitida.
```

Neste exemplo, a função `divide` verifica se `b` é igual a zero e, se for, 
lança uma exceção com a mensagem "Divisão por zero não é permitida." A exceção 
é então capturada no bloco `catch`, e a mensagem de erro é exibida no console.

Você também pode lançar objetos de exceção personalizados em JavaScript, que 
podem conter informações adicionais sobre o erro, como tipo, mensagem e outras 
propriedades personalizadas. Por exemplo:

```{.js linenums="1"}
function customError(message) {
  this.name = "CustomError";
  this.message = message || "Erro personalizado ocorreu.";
}

customError.prototype = Object.create(Error.prototype);
customError.prototype.constructor = customError;

function throwErrorExample() {
  throw new customError("Isso é um erro personalizado.");
}

try {
  throwErrorExample();
} catch (error) {
  console.error(error.name + ": " + error.message);
}

// CustomError: Isso é um erro personalizado.
```

Neste exemplo, definimos um construtor de erro personalizado `customError` que 
herda das propriedades padrão do objeto `Error`. Em seguida, usamos 
`throw new customError(...)` para lançar uma instância de erro personalizado e, 
em seguida, capturamos e exibimos os detalhes do erro no bloco `catch`.