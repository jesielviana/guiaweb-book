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

`Object` - \(Objeto\) - é um tipo mais dinâmico, que ao desenvolvedor criar atributos e métodos, além de já possuir um conjunto de métodos pré-definidos. Geralmente, cria-se objetos para agrupar valores em uma única referência. Veja um exemplo abaixo da notação literal de um objeto:

```javascript
const pessoa = { nome: 'Steve', idade: 35 }
```

Como visto no exemplo acima, usando notação literal, um objeto é definido por um conjuntos de chave-valor separados por dois pontos `:`, entre chaves, a chave identifica a propriedade do objeto.

Podemos acessar o valor de uma propriedade do objeto ou atribuir um novo valor seguindo a sintaxe de `objeto.propriedade`. Veja o exemplo abaixo:

```javascript
console.log(pessoa.idade) // exibe 35
pessoa.idade = 36 // atribui um novo valor para a idade
```

### Operadores

Esta seção apresenta e descreve os principais operadores do Javascript, aqueles que você vai utilizar frequentemente. 

* **Operador de atribuição** 

Um operador de atribuição básico é o  igual "=". Seu funcionamento é bem simples, ele atribui o valor do elemento à sua direita ao elemento à sua esquerda. O valor da direita pode vir de um valor literal \(um número, uma string, etc.\), de uma variável ou de uma expressão. Veja exemplos abaixo:

```javascript
let qtd = 5 // atribui o valor 5 à variável qtd
let itens = qtd // atribui o valor da variável qtd(5) à variável itens
let valor = 10 * itens // atribui o resultado da expressão aritimética 10 x itens(5) à variável valor
```

* **Operadores aritméticos**

Operadores aritméticos são utilizados para fazer operações com valores numéricos \(sejam literais ou variáveis\), o resultado de uma operação aritmética sempre retorna um único valor numérico. Os operadores aritméticos padrão são os de soma `(+)`, subtração `(-)`, multiplicação `(*)` e divisão `(/)`. 

Outro operador muito utilizado em linguagens de programação é o operador de módulo, ele retorna o inteiro restante da divisão entre dois número, no Javascript utiliza se o símbolo de porcentagem \(%\) como operador módulo. Veja o exemplo: 

```javascript
10 % 4 // retorna 2
10 % 5 // retorna 0
```

O operador módulo é muito utilizado para verificar se um determinado número é par ou ímpar, basta pegar o número e fazer o módulo por 2,  qualquer número par retornará 0.

* **Operadores de comparação**

Um operador de comparação compara seus operandos \(valores da esquerda e direita\) e retorna um valor lógico baseado na comparação, que poder ser verdadeira ou falsa. Veja na tabela abaixo os principais operadores de comparação.

<table>
  <thead>
    <tr>
      <th style="text-align:left">Operador</th>
      <th style="text-align:left">Descri&#xE7;&#xE3;o</th>
      <th style="text-align:left">Exemplo</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">==</td>
      <td style="text-align:left">Retorna verdadeiro caso os valores dos operandos sejam iguais.</td>
      <td
      style="text-align:left">
        <p>5 == 5 // true</p>
        <p>5 == 3 // false</p>
        <p>5 == &apos;5&apos; // true</p>
        </td>
    </tr>
    <tr>
      <td style="text-align:left">!=</td>
      <td style="text-align:left">Retorna verdadeiro caso os valores dos operandos n&#xE3;o sejam iguais.</td>
      <td
      style="text-align:left">
        <p>5 != 5 // false</p>
        <p>5 != 3 // true</p>
        </td>
    </tr>
    <tr>
      <td style="text-align:left">===</td>
      <td style="text-align:left">Retorna verdadeiro caso os valores dos operandos sejam iguais e do mesmo
        tipo.</td>
      <td style="text-align:left">
        <p>5 === 5 // true</p>
        <p>5 === 3 // false</p>
        <p>5 === &apos;5&apos; // false</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">&gt;</td>
      <td style="text-align:left">Retorna verdadeiro caso o operando da esquerda seja maior que o da direita.</td>
      <td
      style="text-align:left">
        <p>5 &gt; 5 // false</p>
        <p>5 &gt; 3 // true</p>
        </td>
    </tr>
    <tr>
      <td style="text-align:left">&gt;=</td>
      <td style="text-align:left">Retorna verdadeiro caso o operando da esquerda seja maior ou igual ao
        da direita.</td>
      <td style="text-align:left">
        <p>5 &gt;= 5 // true</p>
        <p>5 &gt;= 3 // true</p>
        <p>5 &gt;= 6 // false</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;</td>
      <td style="text-align:left">Retorna verdadeiro caso o operando da esquerda seja menor que o da direita.</td>
      <td
      style="text-align:left">
        <p>5 &lt; 5 // false</p>
        <p>4 &lt; 7 // true</p>
        </td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;=</td>
      <td style="text-align:left">Retorna verdadeiro caso o operando da esquerda seja menor ou igual ao
        da direita.</td>
      <td style="text-align:left">
        <p>5 &lt;= 5 // true</p>
        <p>4 &lt;= 7 // true</p>
        <p>5 &lt;= 3 false</p>
      </td>
    </tr>
  </tbody>
</table>

* **Operadores Lógicos**

Operadores lógicos são utilizados tipicamente com valores lógicos \(`true ou false`\), neste caso, retornam um valor lógico \(`true ou false`\). Veja os operadores lógicos na tabela abaixo:

<table>
  <thead>
    <tr>
      <th style="text-align:left">Operador</th>
      <th style="text-align:left">Descri&#xE7;&#xE3;o</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">&amp;&amp;</td>
      <td style="text-align:left">
        <p>Operador AND (e): Retorna verdadeiro caso ambos operandos sejam verdadeiros;
          caso contr&#xE1;rio, retorna falso.</p>
        <p>Ex.: <code>expr1 &amp;&amp; expr2  </code>- Retorna <em>true</em> se <code>expr1</code> e <code>expr2</code> forem <b>verdadeiras</b>,
          se <b>pelo menos uma for falsa</b> retorna <em>false</em>
        </p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">||</td>
      <td style="text-align:left">
        <p>Operador OR (ou): Retorna verdadeiro caso ambos ou pelo menos um dos operandos
          sejam verdadeiro; se ambos forem falsos, retorna falso.</p>
        <p>Ex.: <code>expr1 &amp;&amp; expr2</code> - Retorna <em>true</em> se <code>expr1</code> ou <code>expr2</code><b> for verdadeira, ou ambas</b>.
          E retorna <em>false</em>  <b>se somente se</b>  <code>expr1</code> e <code>expr2</code> forem <b>falsas</b>.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">!</td>
      <td style="text-align:left">
        <p>Operador de nega&#xE7;&#xE3;o, retorna o valor l&#xF3;gico contr&#xE1;rio.</p>
        <p>Ex.:<code> !true</code> - Retorna <em>false</em>; <code>!false</code> - Retorna <em>true</em>.</p>
        <p></p>
      </td>
    </tr>
  </tbody>
</table>

### Controle de fluxo

Há diversos tipos de declarações para controle de fluxo na linguagem Javascript, tais como declarações condicionais e laços de repetição. 

Declarações de controle de fluxo são utilizadas para deixar o código mais flexível, onde o mesmo trecho de código pode ter fluxos de execuções diferentes dependendo da interação do usuário.

Controle de fluxo é realizado por meio de declarações em bloco. Uma declaração em bloco é utilizada para agrupar declarações. **No Javascript, um bloco é delimitado por um par de chaves.**

A seguir conheceremos as principais declarações para controle de fluxo no Javascript.

### **Declarações condicionais**

Uma declaração condicional é um conjunto de comandos executados caso uma condição especificada seja verdadeira. Podemos criar declarações condicionais utilizando duas estruturas: `if..else` ou `switch`.

* **Declaração condicional com if...else**

Use a declaração `if` aplicada a uma condição lógica \(true ou false\) para executar alguma declaração caso a condição lógica seja verdadeira. Use a cláusula opcional `else` para executar alguma declaração caso a condição lógica passada para o `if` seja falsa. 

Uma declaração condicional com if...else é declarada da seguinte maneira:

```javascript
if (condicao) {
  // declaracao 1, executada quando a condição for verdadeira
} else {
  // declaracao 2, executada quando a condição for false
}
```

No exemplo acima, `condicao` deve ser uma expressão lógica, que retorna um valor `true` ou `false`.

O `if...else` simples é suficiente para testar **uma condição lógica,** mas em alguns casos há a necessidade de testar **duas ou mais condições lógicas em sequência**,  nesse caso, é possível **combinar declarações com** `else if` **para testar condições lógicas em sequência.** Veja o exemplo abaixo:

```javascript
if (media < 4){
    return 'reprovado'
    
} else if (media < 7){
    return 'recuperacao'
    
} else {
    return 'aprovado'
}
```

> Em Javascript, **alguns valores padrões são avaliados com** _**false**_, veja abaixo:
>
> * `false`
> * `undefined`
> * `null`
> * `0`
> * `NaN`
> * `''` \(string vazia\)
>
> **Todos os outros valores, incluindo todos os objetos, são avaliados como verdadeiros quando passados para uma declaração condicional.**

* Declaração switch

O `switch` é uma declaração de múltipla escolha, similar a uma série de declarações `if` na mesma expressão. É recomendado sua utilização para testar um conjunto de condições pré-definidas. 

Uma declaração `switch` permite que um programa avalie uma variável e tente associar o valor da variável ao rótulo de um `case`. Se uma correspondência é encontrada \(o valor da variável é igual a um dos rótulos `case`\), o programa executa a declaração associada aquele case. Caso nenhuma correspodência seja encontrada é executada a declaração padrão definida no comando `default`. Uma declaração `switch` se parece com o seguinte:

```javascript
switch (variavel) {
   case rotulo1:
      // declaracoes 1
      break
   case rotulo2:
      // declaracoes 2
      break
   default:
      // declaracao padrao
      break
}
```

Segue a explicação de cada um dos comandos da declaração acima:

* `switch`: recebe a variável\(ou expressão\) que armazena o valor responsável pelo controle de escolhas.
* `case`: lista todos os possíveis valores esperados para a variável do comando _switch_;
* `break`: comando que encerra a execução do _switch_;
* `default`: é executado caso nenhum rótulo seja encontrado, não é obrigatório o uso desse comando \(mas recomendo utilizá-lo sempre\).

### Declarações de repetição

As declarações de repetição \(também conhecidas como laço\) oferere um forma simples de executar ações repetidas, ou seja, executar repetidas vezes um mesmo trecho de código. No Javascript, há diversos tipos de declarações para execução de repetição, no entanto vamos focar apenas em dois, que são os mais utilizados, você vai resolver 99,99% do problemas de repetição com eles.

* **Declaração for**

A declaração [`for`](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Statements/for) é repetido até que a condição especificada seja falsa. Uma declaração `for` tem a seguinte sintaxe:

```javascript
for ([expressaoInicial]; [condicao]; [incremento]){
  instruções... 
}
```

Quando um `for` é executado, ocorre os seguintes passos:

1. A  `expressaoInicial` é inicializada e, caso atenda a condição especificada, é executada. 
2. A  `condicao` é avaliada. caso o resultado de `condicao` seja verdadeiro, o laço é executado. Se o valor de `condicao` é falso, então o laço terminará. 
3.  As instruções, que geralmente devem ser envolvidas por um par de chaves {...}, são executadas enquanto a condição for verdadeira.
4. Em cada repetição o `incremento` deve ser atualizado e retorna o controle para o passo seguinte, onde a condição é novamente verificada \(passo 2\).

Vamos de um exemplo prático, caso tenhamos uma lista de nomes para ser exibida, temos que percorrer toda a lista para exibir cada nome individualmente. Nesse caso, podemos muito bem usar o laço `for`, veja o código abaixo:

```javascript
// nomes é um array, estrutura de dados para armazenar coleções de elementos
const nomes = ['Jesiel', 'Viana', 'Silva']

for (let index = 0; index < nomes.length; index++) {
  console.log(nomes[index])
}
```

* `let index = 0;` é a expressão inicial, onde é criado uma variável chamada index e atribuído o valor 0 a ela;
* `index < nomes.length;` - é a condição, onde verifica se a variável index é menor do que o tamanho do array nomes;
* `index++;`  - é o incremento, ou seja, soma se mais 1 a variável index a cada repetição do laço

Diante disso, o laço acima será executado 3 vezes:

1. Na primeira repetição,  o `index` é 0, menor do que o tamanho do array de `nomes` que é 3, então é executada a instrução dentro do bloco `for`:  `console.log(nomes[index])` , exbindo o primeiro nome no console _"Jesiel"_, ao final da repetição é incrementado 1 à variável `index`;
2. Na segunda repetição, o index é 1, menor do que o tamanho do array de `nomes` que é 3, então é executada a instrução dentro do bloco `for`:  `console.log(nomes[index])` , exbindo o segundo nome no console _"Viana"_, ao final da repetição é incrementado 1 à variável `index`;
3. Na terceira repetição, o index é 2, menor do que o tamanho do array de `nomes` que é 3, então é executada a instrução dentro do bloco `for`:  `console.log(nomes[index])` , exbindo o terceiro nome no console "_Jesiel"_, ao final da repetição é incrementado 1 à variável `index`;
4. Na tentativa da quarta repetição, o `index` é 3 que é igual ao tamanho do array de `nomes` que também é 3, nesse caso a condição do `for` é considerada falsa e o laço for é encerrado.

### **Declaração while**

Uma declaração [`while`](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Statements/while) executa suas instruções, desde que uma condição especificada seja avaliada como verdadeira. Segue uma declaração `while`: 

```javascript
while (condicao){
  declarações...
}
```

O teste da condição ocorre antes que o laço seja executado. Desta forma se a condição for verdadeira o laço executará e a cada repetição testará a condição novamente. Quando a condição for falsa o laço termina e passa o controle para as instruções após o laço. 

A condição deve ser modificada dentro do bloco `while`, porque uma vez que a condição seja verdeira e se ela nunca for modificada dentro do bloco `while`, o laço entrarar num ciclo de repetição infinita.

### Funções

Um ponto chave na resolução de um problema complexo é conseguir dividi-lo em subproblemas menores.

Ao criarmos um programa para resolver um problema,  é essencial quebrar um código grande em partes menores, fáceis de serem entendidas e administradas. Costumamos chamar essa prática de dividir para conquistar:

* Um problema é dividido em diversos sub­problemas;
* As soluções dos sub­problemas são combinadas numa solução do problema maior;

Na programação para solucionar o problema que foi "quebrado" em subproblemas criamos um programa dividido em subprogramas. Em Javascript estes subprogramas são chamados de **funções**.

**Uma função é uma sequência de comandos que executa alguma tarefa, pode retornar algo ou não e tem um nome. A sua principal finalidade é nos ajudar a organizar programas em pedaços que correspondam a como imaginamos uma solução do problema.**

Resumindo, funções são blocos de instruções que realizam tarefas específicas.

Uma função consiste em um nome que é dado a uma sequência de comandos de forma que, quando os programas correspondentes precisam dela, basta chamá-la pelo seu nome em vez de ter que copiar seu código ou programá-la totalmente de novo.

Funções são importantes porque permitem que programadores abstraiam certas sequências de comandos que são utilizadas com frequência.

Sintaxe de uma função Javascript:

```javascript
function nomeDaFuncao(parametros){
    instruções...
    return valor
}
```

* `function` - palavra reservada para iniciar uma função \(**obrigatório**\);
* `nomeDaFuncao` - nome da função, sempre deve vir acompanhado de parênteses \(**obrigatório**\);
* `parametros` - variáveis que serão usadas dentro da função \(**opcional**\);
* `{}` - chaves definem o escopo da função \(**obrigatório**\);
* `instruções` - declarações que serão executados dentro da função \(**obrigatório**\);
* `return valor` - valor devolvido para o invocador da função o resultado da execução desta \(**opcional**\).

Veja mais exemplos de funções:

```javascript
function raizQuadradaDe (numero) {
  return numero * numero
}

function exibeNoConsole (valor) {
  console.log(valor)
}
```

Descrição das funções acima:

* A função `raizQuadradaDe` recebe um `numero` com parâmetro \(entre parênteses\) e retorna a raiz quadrada desse número.
* Já a função `exibeNoConsole` recebe um `valor` como como parâmetro e imprime esse valor no console. Esta função não tem retorno.

Também podemos criar funções sem parâmetros, ou seja, funções que não tem nada entre os seus parênteses.

### Escopo local x global

Quando declaramos uma variável fora de qualquer bloco de instruções, ela é chamada de variável global, porque está disponível para qualquer outro código no documento atual. Quando você declara uma variável dentro de uma função ou um bloco de instruções \(`if, for, while`\), ela é chamada de variável local,  pois ela está disponível somente dentro desse bloco ou função. O escopo de bloco e funções no Javascript é definido por um par de chaves. Veja exemplos abaixo:

```javascript
let x = 10

if (true) {
  let y = 20
}

function executa () {
  let z = 30
}

```

Veja os detalhes de escopo de acada variável do exemplo acima:

* `x` - variável global, visível em qualquer parte do arquivo Javascript em que ela está declarada, ou seja, pode ser acessada dentro do bloco `if`, dentro da função `executa`, etc.
* `y` - variável de escopo de bloco, só pode ser acessada dentro do bloco `if` onde ela foi declarada, a delimitação do escopo do bloco é baseada nas chaves \(linhas 3 e 5 do exemplo acima\)
* `z` - variável de escopo local, só pode ser acessada dentro da função \(`executa`\) onde ela foi declarada, a delimitação do escopo da função é baseada nas chaves \(linhas 7 e 9 do exemplo acima\)

> JavaScript antes do ECMAScript 6 \(2015\) não possuía escopo de declaração de bloco; pelo contrário, uma variável declarada dentro de um bloco de uma função era uma variável local e quando declarada dentro de um bloco global era uma variável global.

Essa modificação do escopo de variáveis no ECMAScript 6 ocorreu pela inserção da palavra chave `let` para criação de variáveis.

`let` permite que você declare variáveis limitando seu escopo no bloco, instrução, ou em uma expressão na qual ela é usada. Isso é inverso da palavra chave `var`, que define uma variável globalmente ou no escopo inteiro de uma função, independentemente do escopo de bloco. Veja o exemplo abaixo para enteder melhor as diferenças de escopo entre let e var.

```javascript
if (true) {
  var a = 10
}

if (true) {
  let b = 20
}

console.log(a)
console.log(b)
```

A código acima funciona até chegar a linha 10, vamos entender:

* `var a` - definie uma variável com escopo global dentro de um bloco if
* `let b` - definie uma variável com escopo de bloco dentro de um bloco if

Com isso, é possível acessar a variável a fora do bloco onde ela foi declarada, já a variável b só pode ser acessada dentro do bloco onde foi criada.

Diante disso, evite usar o var para definição de variáveis, **USE SEMPRE let para criação de variáveis** e tenha mais controle do seu escopo \([Recomendado pelo Google Style Guide](https://google.github.io/styleguide/jsguide.html#features-local-variable-declarations)\).

### Arrays \(Vetores em português\)

Array é uma estrutura de dados que armazena uma coleção de elementos \(valores ou variáveis\), cada elemento do array é identificado por um index, iniciando por 0. O promeiro elemento do array está no index 0, o segundo elmento no index 1 e assim sucessivamente. 

Em Javascript, os Arrays são objetos que vêm com uma série de métodos embutidos para realizar operações de travessia e mutação. Nem o tamanho de um array JavaScript nem os tipos de elementos são fixos. Já que o tamanho de um array pode ser alterado a qualquer momento por meio de operações de adição e remoção de elementos, assim também como podemos adicionar tipos de dados diferentes em um mesmo array.

Veja os exemplos de criação e manipulação de arrays abaixo, com código comentado:

```javascript
// Criação de array com notação literal, usa-se colchetes: 
const frutas = ['laranja', 'manga', 'caju']

// a propriedade 'length' exibe o tamanho do array
console.log(frutas.length) // imprime 3

// podemos acessar qualquer elemento de um array pelo seu index
let primeiro = frutas[0] // retorna laranja

// podemos percorrer um array com o laço for
for (let index = 0; index < frutas.length; index++) {
  const fruta = frutas[index];
}

// podemos adicionar um elemento no final do array usando o método 'push'
frutas.push('banana')

console.log(frutas) // [ 'laranja', 'manga', 'caju', 'banana' ]

/* podemos remover um elemento do array usando o método 'splice', 
que recebe dois parâmetros, o primeiro parâmetro é o index de onde inicia a remoção,
o segundo é quantidade de itens que serão removidos, 
no exemplo abaixo está sendo removido somente o item de index 2
*/
frutas.splice(2, 1)

console.log(frutas) // [ 'laranja', 'manga', 'banana' ]
```

No exemplo acima, os comentários do código descreve todas as operações realizadas. Para saber mais sobre Javascript Arrays, acesse: [https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Global\_Objects/Array](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Global_Objects/Array)

> **Umas das principais utilidades do Javascrip no lado cliente é a manipulação de elementos HTML, se quiser aprender como manipular elementos HTML e deixar sua página Web dinâmica e interativa veja o vídeo abaixo:**

{% embed url="https://www.youtube.com/watch?v=T24q\_2wuwDM" %}



### Referências

{% embed url="https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Guide/Grammar\_and\_Types" %}

