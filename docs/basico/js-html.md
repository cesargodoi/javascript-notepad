# Html + JavaScript

Lincamos a nossa página `index.html` com o nosso script `main.js`, através do atributo *`src`* da tag *`script`*:

```{.html linenums="1" hl_lines="10" title="index.html" }
<!DOCTYPE html>
<html lang="en">

  <head>
    <meta charset="UTF-8">
    <title>With HTML</title>
  </head>

  <body>
    <script src="./main.js"></script> <!- aqui nós fazemos a junção ->
  </body>

</html>
```

```{.js title="main.js"}
/**
 * Tudo o que for colocado dentro do 'main.js' 
 * será aplicado no arquivo 'index.html'.
*/

alert('Os arquivos estão lincados!');  // será mostrada em uma caixa de mensagem

console.log('Já essa mensagen, aparecerá no console do navegador');
```