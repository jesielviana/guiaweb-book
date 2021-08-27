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

### Sintaxe básica

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

**Comentários, uso de aspas e ponto e vírgula**

No Javascript há duas formas de definir comentários, `//` para comentários de uma linha e `/* */` para comentários de múltiplas linhas. Veja os exemplos abaixo:

```javascript
// comentário de uma linha


/* isto é um comentário longo
   de múltiplas linhas.
 */
```

Como a maioria das linguagens de programação strings literais são colocadas entre aspas, no Javascript qualquer coisa \(zero ou mais caracteres\) entre aspas é uma string. Uma característica peculiar do Javascript é que podemos criar strings literais usando aspas duplas \(`"`\) ou aspas simples \(`'`\).  No entanto, é importante destacar que a string deve ser delimitada por aspas do mesmo tipo; ou seja, as duas aspas simples ou ambas aspas duplas. Veja alguns exemplos de strings literais:

```javascript
'Estou aprendendo Javascript' // String com aspas simples
"Quero ser programador Web" // String com aspas duplas
"12345" // String composta por números
'true' // String com o valor 'true'
```

Eu uso e recomendo utilizar sempre aspas simples, por ser a forma mais utilizada, inclusive é recomendado pelo [Google Style Guide](https://google.github.io/styleguide/jsguide.html#features-strings-use-single-quotes).

Outro ponto a se destacar em relação à sintaxe do Javascript é a utilização do ponto e vírgula, que é opcional, ou seja, **não é obrigatório adicionar ponto e vírgula no final de suas declarações**. No entanto, é recomendado seguir um padrão, **ou utiliza-se ponto e vírgula em todas as suas declarações ou não em nenhuma**.  

### Tipos de dados

Como citado anteriormente, não é necessário informar o tipo de dado quando vamos declarar uma variável ou constante em Javascript, mas internamente o Javascript atribui um tipo de dado para suas variáveis e constantes inferidos de seus respectivos valores.

O Javascript possui seis tipos de dados primitivos:

* `Boolean` - armazena valores lógicos: `true` e `false`.
* `null` - palavra-chave que indica valor nulo. 
* `undefined` - indefinido, identifica a falta de valor para uma determinada variável é.
* `Number`. - armazena valores numéricos, inteiros e de ponto flutuantes: `42` ou `3.14159`.
* `String` - armazena uma sequência de caracteres: `"bob"`
* `Symbol` \(novo em ECMAScript 6\). Um tipo de dado cuja as instâncias são únicas e imutáveis \(pouco utilizado ainda\).

Além dos tipos primitivo, há também o tipo `Object`.

`Object` - \(Objeto\) - é um tipo mais dinâmico, que ao desenvolvedor criar atributos e métodos, além de já possuir um conjunto de métodos pré-definidos. 



