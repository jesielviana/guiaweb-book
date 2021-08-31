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



### Funções



### Escopo local x global



### Arrays



### Referências

{% embed url="https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Guide/Grammar\_and\_Types" %}



