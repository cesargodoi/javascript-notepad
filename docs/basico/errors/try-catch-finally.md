# Try - Catch - Finally

Em JavaScript, `try`, `catch`, e `finally` são construções usadas para lidar 
com exceções (erros) que podem ocorrer durante a execução de um bloco de 
código. Aqui está uma explicação de como eles funcionam:

## `try`
O bloco `try` é usado para envolver o código que você acredita que 
pode gerar uma exceção. Quando um erro ocorre dentro do bloco `try`, o fluxo 
de controle é transferido imediatamente para o bloco `catch`.
```{.js linenums="1" hl_lines="2"}
try {
  // Código que pode gerar uma exceção
} catch (error) {
  // Código para lidar com a exceção
}
```

## `catch` 
O bloco `catch` é usado para capturar (ou "pegar") uma exceção 
gerada no bloco `try`. O parâmetro `error` (ou qualquer nome que você escolher) 
é uma referência à exceção que foi lançada. Você pode usar essa referência 
para examinar detalhes sobre o erro, como a mensagem de erro, o tipo de erro 
etc., e tomar medidas apropriadas para lidar com a exceção.
```{.js linenums="1" hl_lines="4-5"}
try {
  // Código que pode gerar uma exceção
} catch (error) {
  // Código para lidar com a exceção
  console.error(error.message);
}
```

## `finally`
O bloco `finally` é opcional e é usado para definir código que 
será executado, independentemente de ocorrer ou não uma exceção dentro do bloco 
`try`. Isso é útil para ações que devem ser executadas sempre, como a limpeza 
de recursos, independentemente de um erro ter ocorrido ou não.
```{.js linenums="1" hl_lines="6"}
try {
  // Código que pode gerar uma exceção
} catch (error) {
  // Código para lidar com a exceção
} finally {
  // Código que sempre será executado
}
```

A ordem de execução é a seguinte:

1. O código no bloco `try` é executado.
2. Se uma exceção ocorrer no bloco `try`, o controle é transferido para o bloco 
`catch`, onde o erro é tratado.
3. Após a execução do bloco `try` ou do bloco `catch`, o bloco `finally` é 
executado, se presente.

A estrutura `try-catch-finally` permite que você lide com exceções de maneira 
controlada, evitando que erros interrompam a execução do seu programa e 
fornecendo a oportunidade de realizar ações de limpeza, se necessário.