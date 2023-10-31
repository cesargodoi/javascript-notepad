# Generators

## Definição

Um generator é uma função especial que permite pausar e retomar sua execução. 
Isso é útil quando você precisa lidar com operações demoradas ou iterar sobre 
um grande conjunto de dados de forma eficiente. Os generators são criados 
usando a função `function*`.

> Existe também sintaxe mais recente `async function*`, que introduz o 
> conceito de "async generators" para trabalhar com operações assíncronas.  
> Veremos isso no futuro.

Generators são úteis em várias situações, como iteração preguiçosa sobre 
grandes conjuntos de dados, lidar com código assíncrono de forma mais legível 
e criar pipelines de processamento de dados. Eles são uma característica 
poderosa do JavaScript que simplifica muitos aspectos do código assíncrono e 
da manipulação de sequências de dados.

## Estrutura

Para criar um generator, você usa a função `function*` e dentro dela, você 
pode usar a instrução `yield`. O `yield` é usado para pausar a execução da 
função e retornar um valor. Quando a função é retomada, ela continua a partir 
do ponto em que foi pausada, mantendo seu estado interno.

```{.js linenums="1"}
function* nomeDoGenerator() {
    yield elementoGerado;
}
```

A cada vez que chamamos o atributo `next` do generator, ele nos entrega um 
elemento da iteração, como demonstrado abaixo: 

```{.js linenums="1"}
{ value: 'elementoSendoEntregue', done: false }
```

Quando os elementos gerados chegam ao fim, o atributo `done` do objeto entregue 
será igual a `true` e o elemento entregue será `undefined`.

Caso usemos o `return`, ele encerrará o generator, excluindo qualquer `yield` 
que venha após ele.

## Exemplos

### Básico
```{.js linenums="1"}
function* myGenerator() {
    yield 'elemento 1';
    yield 'elemento 2';
    yield 'elemento 3';
    yield 'elemento 4';
}

const gen1 = myGenerator();
console.log(gen1);               // Object [Generator] {}
console.log(gen1.next());        // { value: 'elemento 1', done: false }
console.log(gen1.next().value);  // elemento 2
console.log(gen1.next().value);  // elemento 3
console.log(gen1.next().value);  // elemento 4
console.log(gen1.next());        // { value: undefined, done: true }

// iterando com for
const gen2 = myGenerator();
for (val of gen2) {
    console.log(val);
}
```


### Gerador infinito 
```{.js linenums="1"}
function* contador() {
  let i = 0;
  while (true) {
    yield i;
    i++;
  }
}

const gen = contador();

console.log(gen.next().value); // 0
console.log(gen.next().value); // 1
console.log(gen.next().value); // 2
```

Neste exemplo, a função `contador` é um generator que gera uma sequência 
infinita de números inteiros começando por zero. O `yield` pausa a execução da 
função e retorna o valor atual de `i`, e o método `next()` é usado para 
avançar para o próximo valor da sequência.


### Unindo dois geradores
```{.js linenums="1"}
function* generator1() {
    yield 1;
    yield 2;
    yield 3;
    yield 4;
}

function* generator2() {
    yield* generator1();
    yield 5;
    yield 6;
    yield 7;
}

let gen4 = generator2()
for (val of gen4) {
    console.log(val);  // itera de 1 à 7
}
```


### Entregando funções 
```{.js linenums="1"}
function* getFunction() {
    yield function () {
        console.log('vim do 1. yield');
    }
    yield function () {
        console.log('vim do 2. yield');
    }
    return function () {
        console.log('vim do return');
    }
}

let gen5 = getFunction();

const func1 = gen5.next().value;
const func2 = gen5.next().value;
const func3 = gen5.next().value;

func1();  // vim do 1. yield
func2();  // vim do 2. yield
func3();  // vim do return
```