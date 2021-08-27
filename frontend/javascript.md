---
description: 'Introdução a Javascript, a linguagem de programação mais utilizada na Web'
---

# Javascript

> **Objetivos de aprendizagem**
>
> * Conhecer a linguagem de programação Javascript
> * Entender a sintaxe básica da linguagem
> * Entender como utilizá-la no lado cliente, junto com HTML

### Introdução

JavaScript é uma linguagem de programação multiparadigma \(procedural, orientada a objetos, funcional\) e multiplataforma. É uma linguagem leve. É uma linguagem bem leve e que não necessita de muitos recursos para utilizá-la, basta um navegador Web. Javascript roda dentro do navegador,  do lado cliente. Também pode ser executado no lado servidor, por meio da plataforma [Node.js](https://nodejs.org/) ou [Deno](https://deno.land/).

JavaScript foi criada em 1995 por [Brendan Eic](https://twitter.com/brendaneich)h quando ele trabalhava na Netscape. Atualmente é a [**linguagem de programação mais utilizada na Web**](https://insights.stackoverflow.com/survey/2021#technology-most-popular-technologies).

Inicialmente, Javascript era utilizado somente do lado cliente, sendo executado diretamente pelo navegador, mas com o surgimento do Node.js, a linguagem deve grande adoção do lado servidor, sendo bastante utilizada para construção de APIs e aplicações de back-end em geral.

A popularidade do Javascript ganhou bastante força devido sua utilização por diversos frameworks de front-end., tais como [JQuery](https://jquery.com/), [Angular](https://angular.io/), [React](https://pt-br.reactjs.org/) e [Vue.js](https://br.vuejs.org/).

Diante disso, eu diria que dominar a linguagem **Javascript é fundamental para qualquer desenvolvedor Web**, se você trabalha com front-end é obrigatório saber Javascript.

Nas próximas seções vamos aprender a sintaxe básica da linguagem, tipos de dados, controle de fluxo, laços de repetição e funções.

### Sintaxe

JavaScript é uma linguagem **dinamicamente tipada**. Isso significa que você não precisa especificar o tipo de dado quando vai declarar uma variável. O tipo de dado da variável é inferido automaticamente a partir do seu valor. 

**Declaração de variáveis e constantes**

Em Javascript, podemos declarar variáveis utilizando a palavra-chave `var` ou `let`.

* `var` - declara uma variável, opcionalmente, inicializando-a com um valor. Atualmente não é recomendado o uso de `var`. Veja abaixo um exemplo de declaração de varável com `var`: 

```javascript
var quantidade = 20
```

* `let` - declara uma variável, opcionalmente, inicializando-a com um valor. O `let` foi introduzido na versão 6 do Javascript. Variáveis declaradas com `let`  possuem escopo mais restrito do que as variáveis declaradas com `var` \(vamos explicar mais sobre escopo nas próximas seções\). Veja abaixo um exemplo de declaração de varável com `let`: 

```javascript
let nome = 'Steve'
```

Além de variáveis, podemos declarar constantes, para isso utilizamos a palavra-chave `const`. 

*  `const` - declara uma constante de escopo de bloco, que deve ser inicializada na declaração e após sua inicialização é utilizada somente para leitura.Veja abaixo um exemplo de declaração de varável com `const`: 

```javascript
const pi = 3.14
```

