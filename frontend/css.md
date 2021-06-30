---
description: >-
  Introdução a Cascading Style Sheets (CSS), linguagem utilizada para adicionar
  estilo a páginas Web.
---

# CSS

> **Objetivos de aprendizagem**
>
> * Conhecer a linguagem de estilo CSS
> * Entender a sintaxe básica da linguagem CSS
> * Conhecer as propriedades básicas da CSS

### Introdução

CSS - Cascading Style Sheets \(Folha de Estilos em Cascata em português\), é uma linguagem de estilo utilizada para definir a apresentação de documentos escritos em uma linguagem de marcação, como HTML. O CSS formata a informação entregue pelo HTML. Essa informação pode ser qualquer coisa: imagem, texto, vídeo, áudio ou qualquer outro elemento criado. 

> CSS descreve como os elementos HTML devem ser exibidos. Quando um navegador vai exibir uma página Web ele lê o conteúdo do HTML e a formatação do CSS. HTML e CSS se completam.

O CSS separa o conteúdo da representação visual do site, isso significa que o CSS permite aplicar estilos seletivamente a elementos em documentos HTML. Por exemplo, para que todos os elementos do tipo parágrafo \(`<p>`\) de uma página HTML tenham o seu conteúdo \(texto\) alinhado à direita, seria necessário este CSS:

```css
p {
    text-align: right;
}
```

### Como vincular o CSS ao HTML

Há basicamente três formas de aplicar CSS a um documento HTML:

1. _**Inline -**_ o código CSS é adicionado diretamente no elemento HTML através do atributo style. Exemplo: `<p style="text-align: right; ">texto</p>.` Esta forma é considerada uma má prática, pois mistura o código HTML com CSS e não permite a reutilização de código, tornando a manutenção e evolução do código mais complexa. Portanto, EVITE! 
2. **Interno** - o código CSS é colocado dentro de uma elemento &lt;style&gt;, geralmente dentro do &lt;head&gt;. Exemplo: `<style type="text/css">   p { text-align: right; } </style>.`Esta forma também é considerada uma má prática, pois coloca o código HTML com CSS em um mesmo arquivo e não permite a reutilização do CSS entre arquios HTML diferentes, que pode gerar duplicidade de código e tornar a manutenção mais trabalhosa. Portanto, EVITE! 
3. **Externo** - o código CSS é colocado em um arquivo `.css`, separadamente do arquivo HTML. Nesse caso é necessário vincular o arquivo CSS no arquivo HTML. A ligação entre o HTML e CSS é realizada por meio do elemento link, que deve ser adicionado no elemento `<head>`. Veja o exemplo abaixo, onde o arquivo `style.css` está vinculado ao arquivo `index.html`:

{% tabs %}
{% tab title="index.html" %}
```markup
<!DOCTYPE html>
<html>
 
 <head>
   <link rel="stylesheet" href="style.css">
 </head>

 <body>
   <p>Olá mundo, HTML!</p>
 </body>

</html>

```
{% endtab %}

{% tab title="style.css" %}
```css
p {
    text-align: right;
}
```
{% endtab %}
{% endtabs %}

Como pode ser visto no exemplo acima, o elemento &lt;link&gt; recebe dois atributos obrigatórios referentes ao arquivo CSS que será vinculado. O atributo `rel="stylesheet"`  especifica que o documento vinculado é um CSS e o atributo `href`  recebe como valor a localização \(_link_\) do arquivo CSS a ser vinculado.

Dessa forma, todo código CSS adicionado no arquivo style.css está vinculado ao arquivo index.html. 

Agora vamos entender sobre a sintaxe do CSS, sua anatomia básica.

### Sintaxe do CSS

Podemos as instruções CSS como um conjunto de regras de formatação para serem aplicadas às páginas Web.

A sintaxe das regras do CSS é formada por um **seletor** e **bloco de declarações**, dentro de um bloco de declarações pode haver várias declarações, cada declaração é composta por  **propriedade** e **valor.** Veja a imagem abaixo.

![Sintaxe do CSS](../.gitbook/assets/sintaxe-css.png)

Vamos entender detalhadamente cada item da sintaxe do CSS.

* O **seletor** seleciona quais elementos  HTML receberão o estilo definido no bloco de declarações. No exemplo da figura acima, todos os elementos `<p>` \(paragrafo\) serão estilizados conforme o bloco de declarações.
* O **bloco de declaração**, delimitado por chaves `{}`, contém uma ou mais declarações separadas por ponto e vírgula.
* Cada declaração inclui um nome de **propriedade** CSS e um **valor**, separados por **dois pontos**.
* As propriedades `text-align` e `color` são utilizadas para definir o alinhamento do texto e cor do texto respectivamente. No exemplo da imagem acima, para o `text-align` foi atribuído o valor `right`, que alinha o texto à direita e para a `color` foi atribuído o valor `green`, que deixa a cor de texto verde.  

Veja mais sobre seletores, propriedades e valores na próxima seção.

### Seletores

Aplicação de CSS é feita por Seletores. Os seletores CSS são usados para "encontrar" \(ou selecionar\) elementos HTML com base no nome do elemento, id, classe, etc.

Há muitos tipos diferentes de seletores. Abaixo, é mostrado os **seletores de elementos**, que selecionam todos os elementos de um determinado tipo nos documentos HTML. No entanto, é possível fazer seleções mais específicas.  Veja abaixo alguns dos tipos mais comuns de seletores:

<table>
  <thead>
    <tr>
      <th style="text-align:left">Seletor</th>
      <th style="text-align:left">Exemplo</th>
      <th style="text-align:left">O que ele seleciona</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">tag ou elemento</td>
      <td style="text-align:left">
        <p><code>p { </code>
        </p>
        <p><code>} </code>
        </p>
      </td>
      <td style="text-align:left">Todos os elementos HTML de determinado tipo (tag). Qualquer tag/elemento
        pode ser usada como seletor.</td>
    </tr>
    <tr>
      <td style="text-align:left">id</td>
      <td style="text-align:left"><code>#my-id {  } </code>
      </td>
      <td style="text-align:left">O elemento na p&#xE1;gina com o id espec&#xED;ficado. S&#xF3; deve haver
        um elemento com o mesmo <code>id</code> por p&#xE1;gina HTML. O seletor de
        id inicia com uma hashtag <code>#</code>.</td>
    </tr>
    <tr>
      <td style="text-align:left">classe</td>
      <td style="text-align:left"><code>.my-class { } </code>
      </td>
      <td style="text-align:left">O(s) elemento(s) na p&#xE1;gina com a classe espec&#xED;ficada. V&#xE1;rios
        elementos podem possuir a mesma classe. O seletor de classe inicia com
        um ponto <code>.</code> .</td>
    </tr>
    <tr>
      <td style="text-align:left">pseudo-classe</td>
      <td style="text-align:left">
        <p><code>a:hover { </code>
        </p>
        <p><code>}</code>
        </p>
      </td>
      <td style="text-align:left">O(s) elemento(s) espec&#xED;ficado(s), mas somente quando estiver no estado
        especificado. No exemplo &#xE9; utilizado o hover que &#xE9; um estado
        ativado quando o mouse est&#xE1; sobre o elemeto. O seletor de pseudo-classe
        &#xE9; definido com o nome do seletor, dois pontos e o estado, ex.: <code>seletor:estado</code> .</td>
    </tr>
  </tbody>
</table>

### Propriedades e Valores

Propriedade é a forma pela qual você estiliza um elemento HTML. Cada propriedade está relacionada a uma característica que pode ser modificada no elemento HTML. 

Valor da propriedade é a forma pela qual você define o estilo para determinada propriedade, afetando diretamente a aparência do elemento HTML. 

Abaixo é apresentado alguns exemplos de propriedades e valores. Os comentários descrevem cada propriedade listada. Comentários em CSS é definido entre barras e asterisco, como:`/* comentários */`

{% tabs %}
{% tab title="style.css" %}
```css

/* CSS aplicado ao elemento body, ou seja, aplicato a página toda */
body { 
    text-align: center; /* deixa o texto centralizado */
    color: green; /* define a cor de todo texto da página como verde */
    font-size: 16px; /*d efine o tamanho da fonte do texto */
}
```
{% endtab %}

{% tab title="index.html" %}
```markup
<!DOCTYPE html>
<html>
 
 <head>
   <meta charset="UTF-8">
   <title>Webdev book</title>
   <link rel="stylesheet"  href="css/style.css">
 </head>

 <body>
  <h2>Olá CSS, vamos pra aula!</h2>
 </body>

</html>
```
{% endtab %}
{% endtabs %}

Como pode ser visto nos comentários do código CSS acima, algumas propriedades do CSS são específicas para determinados tipos de elementos HTML, como `text-align`, `color`   e `font-size`, que só fazem efeitos em elementos de texto. Já outras podem ser aplicadas com efeitos em qualquer elemento, tais como `width`, `margin`, etc. Vamos ver mais detalhes sobre elas na próxima seção. 

Não tente decorar todas as propriedades e valores do CSS, são muitas propriedades e para cada propriedade pode haver infinitas possibilidades de valores, o importante é entender a sintaxe e ir utilizando de acordo com o que você deseja fazer. 

Vale destacar que para maioria das propriedades existem um conjunto de valores pré-definidos. Veja todas as propriedades e valores do CSS aqui: [https://developer.mozilla.org/pt-BR/docs/Web/CSS/Reference](https://developer.mozilla.org/pt-BR/docs/Web/CSS/Reference).

### No HTML tudo é box \(caixa\)

A maioria dos elementos HTML podem ser pensados como caixas, que podem ser agrupadas de forma horizontal, vertical ou colocada dentro de outra. Ao trabalhar com as propriedades CSS isso fica mais evidente, frequentemente você precisará indicar o tamanho dos elementos\(largura e altura\), cor, posição em relação aos demais e seu conteúdo interno, etc.

O box \(caixa\) que representa um elemento HTML é composto por conteúdo, margem interna \(`padding`\), borda \(`border`\) e margem externa \(`margin`\). A figura abaixo tem a representação gráfica de um elemento.

![Caixa de um elemento HTML](../.gitbook/assets/box-elemento-html.png)



Diante do apresentado acima,  agora sabemos que cada elemento HTML que ocupa um espaço na sua página tem propriedades como essas:

* `padding` - espaço entre a borda e o conteúdo.
* `border` - linha que envolve todo o elemento.
* `margin` - espaço externo a um elemento.
* `width` - largura de um elemento;
* `height` - altura de um elemento;
* `background-color` - a cor de fundo do elemento.

Abaixo um exemplo de código aplicando essas propriedades CSS.

{% tabs %}
{% tab title="style.css" %}
```css
/* CSS aplicado a todos elementos que possuem a classe 'retangulo' */
.retangulo {
    width: 400px; /*  define a largura do elemento */
    height: 200px; /*  define a altura do elemento */
    border: 1px solid red;
    background-color: #eee; /* define a cor de fundo do elemento  */
    padding: 10px 10px 10px 10px; /*  define uma distância interna entre as bordas do elemento e seu conteúdo */
    margin: 5px 5px 5px 5px; /*  define uma distância externa  entre as bordas do elemento os demais em volta*/
}

```
{% endtab %}

{% tab title="index.html" %}
```markup
<!DOCTYPE html>
<html>
 
 <head>
   <meta charset="UTF-8">
   <title>IFPI Campus Picos</title>
   <link rel="stylesheet"  href="css/style.css">
 </head>

 <body>
  <div class="retangulo">
    <p>By Jesiel Viana</p>
  </div>
 </body>

</html>
```
{% endtab %}
{% endtabs %}



### Referências

{% embed url="https://developer.mozilla.org/pt-BR/docs/Learn/Getting\_started\_with\_the\_web/CSS\_basics" %}

{% embed url="https://www.w3schools.com/css/default.asp" %}



