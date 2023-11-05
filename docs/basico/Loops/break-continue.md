# Break - Continue

O `break` e `continue` são palavras-chave que permitem controlar o fluxo de 
execução em loops, como `for`, `while` e `do...while`. Vou explicar como cada 
um deles funciona:

## Break

O `break` é usado para sair imediatamente de um loop quando uma determinada 
condição é atendida. Quando o `break` é executado dentro de um loop, o loop é 
encerrado e a execução continua após o loop. Aqui está um exemplo:

```javascript
for (let i = 0; i < 5; i++) {
    if (i === 3) {
        break; // Sai do loop quando i for igual a 3
    }
    console.log(i);
}

// 0
// 1
// 2
```


## Continue

O `continue` é usado para pular a iteração atual de um loop e avançar para a 
próxima iteração. Quando o `continue` é executado dentro de um loop, o código 
restante dentro da iteração atual é ignorado, e a execução continua com a 
próxima iteração do loop. Aqui está um exemplo:

```javascript
for (let i = 0; i < 5; i++) {
    if (i === 2) {
        continue; // Pula a iteração quando i for igual a 2
    }
    console.log(i);
}

// 0
// 1
// 3
// 4
```


O `break` e o `continue` são úteis para controlar o comportamento de loops em 
JavaScript, permitindo que você saia de um loop prematuramente ou pule 
iterações específicas, de acordo com as condições definidas no código. 
Certifique-se de usá-los com cuidado para evitar loops infinitos ou 
comportamentos inesperados em seu código.