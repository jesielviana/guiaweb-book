---
description: >-
  Introdução a Hypertext Markup Language (HTML), linguagem de marcação utilizada
  para criar páginas Web
---

# HTML

> **Objetivos de aprendizagem**
>
> * Conhecer a linguagem de marcação HTML
> * Entender a sintaxe básica da linguagem
> * Conhecer as tags básicas da HTML

### Introdução

Como descrito na aula anterior, a Web é baseada na interligação de documentos de hipermídia que podem conter textos, imagens, vídeos, etc. Para criação desses documentos, conhecidos como páginas Web, utiliza-se a linguagem de marcação HTML - Hypertext Markup Language.&#x20;

A linguagem HTML permite estruturar uma página web e seu conteúdo com texto, imagens, vídeos, etc. E interligá-los com outras páginas na Web de forma simples e padronizada.

HTML **não** é uma linguagem de **programação**, na verdade, HTML é uma linguagem de marcação, formada por um conjunto de elementos. Os elementos HTML são definidos por meio de _tags,_ que são utilizadas para definir a estrutura do conteúdo.

As tags HTML são utilizadas para delimitar ou agrupar diferentes partes do conteúdo para ele apareça ou atue de determinada maneira. A interpretação do HTML e apresentação do conteúdo fica a cargo dos navegadores Web.

Por exemplo, como transformar a frase abaixo em um parágrafo HTML?

> Sou um desenvolvedor Web.

Basta envolver a frase em uma tag `<p>`, tal como: `<p>Sou um desenvolvedor Web</p>`

Todo o conteúdo de um documento HTML deve ser envolvido por tags, há tags específicas para cada tipo de conteúdo, como a tag `<p>` para parágrafo. Mais a frente vamos conhecer as principais tags HTML e como utilizá-las.

### Estrutura de uma página HTML

Abaixo é apresentado o código-fonte da estrutura mínima de uma página HTML e a seguir é descrito cada elemento.

```markup
<!DOCTYPE html>
<html>
 
 <head>

 </head>

 <body>
  <!-- Conteúdo aqui -->
 </body>

</html>
```

Um documento HTML é formado por elementos, que na sua maioria é composto por uma tag de abertura no início do elemento e uma tag de fechamento que indica o fim do elemento. Veja a descrição dos elementos do código acima.

* `<!DOCTYPE html>` - declaração que define que este documento é do tipo HTML5, deve ser a primeira _tag_ do documento (obrigatório);
* `<html>` - é o elemento raiz de uma página HTML, composto pela _tag_ `<html>`, que indica o início do documento e pela _tag_ `</html>` que delimita o final do documento. Observe que a tag de fechamento tem uma `/`. Isso é padrão para todos os elementos que possuem tag de fechamento;
* `<head>` - elemento que contém configurações e meta informações sobre o documento, o conteúdo colocado dentro deste elemento não fica visível no página Web, quando acessada pelo navegador. Este elemento também formado pelas tags de abertura e fechamento;
* `<body>`  - elemento que indica o corpo do documento, contém todo conteúdo  visível da página Web. Também formado pelas tags de abertura e fechamento.
* `<!-- Conteúdo aqui -->` - esse trecho de código na linha 9 é um exemplo de comentário. Comentários é como fazemos anotações em nosso HTML, eles são ignorados pelo navegador. Começamos um comentário HTML com `<! -` e terminamos um comentário com `->`.

### Anatomia de um elemento HTML

A figura abaixo apresenta detalhadamente as partes que compõe um elemento HTML, no exemplo é utilizada a tag `p` que representa um parágrafo num documento HTML. No entanto, essa estrutura é aplicada a qualquer elemento que possui tag de abertura e fechamento. Como vamos ver mais a frente, alguns elementos HTML possuem apenas a tag de abertura.

![Anatomia de um elemento HTML](../.gitbook/assets/anatomia-elemento-html.png)

As principais partes de um elemento são:

* **Tag de abertura** - consiste no nome do elemento (no caso, o elemento `p`), envolvido pelos caracteres `<` (menor que) e `>` (maior que). Isso demonstra onde o elemento começa, ou onde seu efeito se inicia — nesse caso, onde é o começo do parágrafo.
* **Tag de fechamento**  - Similar tag de abertura, exceto que inclui uma barra antes do nome do elemento. Isso demonstra onde o elemento acaba — nesse caso, o fim do parágrafo.&#x20;
* **Conteúdo** - é literalmente o conteúdo do elemento (texto, imagens, links, etc.), no exemplo do parágrafo acima é apenas texto.
* Por fim, a tag de abertura, a de fechamento, e o conteúdo formam o **Elemento**.

> Atenção: esquecer de incluir uma tag de fechamento, ou simplismente esquecer de colocar a `/` (barra) é um dos erros mais comuns de iniciantes causando resultados indesejados e estranhos.

### Primeira página HTML

Agora vamos criar nosso "olá mundo" com HTML. Para isso vamos criar um documento HTML seguindo a estrutura vista acima e adicionar um elemento de parágrafo com a seguinte frase "Olá mundo, HTML!". Código abaixo:

```markup
<!DOCTYPE html>
<html>
 
 <head>

 </head>

 <body>
   <p>Olá mundo, HTML!</p>
 </body>

</html>

```

Para visualizar a nossa página, basta salvar o documento com o nome index.html (pode ser qualquer nome com a extensão .`html`) e abri o arquivo em qualquer navegador Web.

Nossa primeira página Web está criada, porém, ainda está muito simples e faltando algumas configurações básicas, tais como o _`charset`_  e título da página. Vamos adicionar essas configurações e também transformar o texto "Olá mundo, HTML!" em um texto maior e negrito, tipo cabeçalho, com mais destaque.&#x20;

```markup
<!DOCTYPE html>
<html>
 
 <head>
   <meta charset="UTF-8">
   <title>Aula de HTML</title>
 </head>

 <body>
   <h1>Olá mundo, HTML!</h1>
   <p>Feito por "seu_nome"</p>
 </body>

</html>

```

Os elementos adicionados foram:&#x20;

* `<meta>` _(linha 5)_ **-** elemento utilizado para adicionar metadados ao documento. Metadados são dados(informações, configurações, etc.) sobre o documento. No exemplo acima é adicionado o atributo `charset,` que é utilizado para indicar o formato de codificação de caracteres utilizados no documento. Nesse caso, está sendo utilizado `UTF-8`, que pode representar qualquer caractere universal padrão do [Unicode](https://pt.wikipedia.org/wiki/Unicode) e assim evitamos problemas de acentuação;
* `<title>` _(linha 6)_ - elemento que especifica um título para o documento;
* `<h1>`  (10) - elemento que define um texto com destaque, fonte grande e negrito;
* `<p>`  _(linha 11)_ - elemento que define um parágrafo.

Pronto! Agora temos um documento simples com as configurações essenciais para um página Web padronizada de acordo com os padrões profissionais e internacionais.

### Elementos com atributos

Qualquer elemento HTML pode receber atributos, que são utilizados para adicionar informações extras aos elementos, como no exemplo abaixo:

```markup
 <h1 class="titulo-pagina">Olá mundo, HTML!</h1>
```

Nesse exemplo, foi adicionado o atributo `class` ao elemento h1, esse atributo é utilizado para categorizar elementos, pode ser adicionado a qualquer elemento. No entanto, a simples utilização de um atributo `class` não impacta em nada a exibição do conteúdo do elemento pelo navegador. Há diversos atributos que podem ser adicionados à qualquer elemento, sendo conhecidos como atributos globais ([veja quais são aqui](https://developer.mozilla.org/pt-BR/docs/Web/HTML/Global\_attributes)) e outros que são específicos para determinados elementos (conheça todos os atributos HTML).

Vale destacar que os atributos de um elemento sempre devem ser adicionados na tag de abertura, seguindo a sintaxe `<tag nome-do-atributo="valor-do-atributo">` . Incia-se com um espaço entre ele e o nome do elemento (ou o atributo anterior, caso o elemento já contenha um ou mais atributos.), após o nome do atributo vem o sinal de `=` separando-o do seu valor, por fim, o valor do atributo deve ser colocado entre aspas duplas.

Alguns elementos não possuem tag de fechamento, chamados de elementos vazios, pois eles não possuem conteúdo interno. Geralmente esses elementos possuem atributos que agrega informações ao elemento, como no caso do atributo `charset` adicionado ao elemento `meta`. Algo comum em elementos dentro do `<head>`.&#x20;

Já outros elementos vazios possuem atributos específicos que são utilizados pelo navegador para carregar seu conteúdo, o seja, o conteúdo do elemento vem do seu atributo, como é o caso do elemento `<img>`, que é utilizado para adicionar uma imagem ao documento HTML. Veja o exemplo abaixo:

```markup
<!DOCTYPE html>
<html>
 
 <head>
   <meta charset="UTF-8">
   <title>Aula de HTML</title>
 </head>

 <body>
   <h1>Olá mundo, HTML!</h1>
   <p>Feito por "seu_nome"</p>
   <img src="https://image.flaticon.com/icons/png/512/524/524545.png">
 </body>

</html>
```

Para adicionar uma imagem em uma página HTML utiliza-se o elemento `<img>` passando o endereço da imagem para o atributo `src.` Agora quando você salvar o código do exemplo acima e abrir no navegador será exibida abaixo do texto a imagem "carregada" do link/endereço passado como valor para o atributo `src`  do elemento `<img>`.

### Elementos semânticos

Os elementos HTML que proveem conteúdo para ser exibido pelo navegador possuem um valor semântico, por exemplo: `<h1>Novo título</h1>`, qualquer texto colocado dentro do elemento `h1` tem o valor semântico de um título, o navegador entende isso e exibe-o com destaque (negrito e grande), além disso, qualquer desenvolvedor que conhece HTML  ao ver o código sabe que representa um título.&#x20;

Porém, nem todos os elementos HTML geram conteúdo para ser exibido, alguns elementos são utilizados apenas para delimitação de código ou agrupamento de outros elementos, são elementos que não geram conteúdo visual na página, mas tem valores semânticos específicos, são geralmente conhecidos como **elementos semânticos**.

Além de estrutura os documentos HTML o principal objetivo dos elementos semânticos é descrever o significado do conteúdo presente em documentos HTML. Abaixo será apresentado os principais elementos semânticos do HTML.

* `<header>` - Utilizado para descrever o cabeçalho de um documento ou seção;
* `<main>` - Define o conteúdo principal de um documento, o conteúdo mais importante;
* `<nav>` - Deve ser utilizado para agrupar os links de navegação interna do site (menu);
* `<section>` - Representa uma seção dentro de um documento HTML.
* `<aside>` - Utilizado para definir um conteúdo secundário ao conteúdo principal, geralmente um conteúdo lateral;
* `<footer>` - Define o rodapé (parte final de uma página) de um documento HTML.
* Veja mais elementos em: [https://developer.mozilla.org/pt-BR/docs/Glossary/Semantics#elementos\_sem%C3%A2nticos](https://developer.mozilla.org/pt-BR/docs/Glossary/Semantics#elementos\_sem%C3%A2nticos)

Veja abaixo uma representação gráfica dos elementos semântico e seu código HTML (_obs.: para que os elementos HTML sejam exibidos conforme a figura é necessário fazer a estilização com CSS, assunto do próximo capítulo_)

{% tabs %}
{% tab title="Imagem" %}
![Elementos semânticos do HTML](../.gitbook/assets/elementos-sema-nticos.png)
{% endtab %}

{% tab title="Código HTML semântico" %}
```markup
<!DOCTYPE html>
<html>
 
 <head>
   <meta charset="UTF-8">
   <title>IFPI Campus Picos</title>
 </head>

 <body>

  <nav>
    Elementos de Menu
  </nav>

  <header>
    Elementos do Topo
  </header>

  <main>
    <section>
      Conteúdo da Seção 1
    </section>

    <section>
      Conteúdo da Seção 2
    </section>
  </main>

  <aside>
    Conteúdo secundário 
  </aside>

  <footer>
    Conteúdo do Rodapé - 2021
  </footer>

 </body>

</html>
```
{% endtab %}
{% endtabs %}

É importante destacar que nem todos os elementos HTML possuem valor semântico, um desses elementos mais conhecidos é a `<div>.` Podemos descrever o elemento `<div>` como um caixa genérica para qualquer conteúdo, que de certa forma não representa nada por não possuir valor semântico. Geralmente é utilizado para agrupar elementos para serem referenciados pelo CSS. Ele deve ser utilizado somente quando não tiver outro elemento de semântica específico para o que se deseja.

### Conclusão

Nesta aula conhecemos a linguagem de marcação HTML e para que ela é utilizada. Além disso, aprendemos o básico de sua sintaxe e a utilizar de forma prática as tags básicas para criar elementos, atributos e páginas Web.

**O mais importante nesse momento é compreender a estrutura da HTML e ter a consciência de que existem elementos específicos para cata tipo de conteúdo que pode ser exibido em uma página HTML, tais como títulos, parágrafos, tabelas, listas ordenadas e não ordenadas, imagens, vídeos,  etc.**(Conheça todos os elementos HTML).

Agora é com você, modifique os exemplos criados na aula, adicione mais elementos nas páginas e crie outros documentos HTML.&#x20;

Por fim, acesse o material complementar.

### Material Complementar

{% embed url="https://developer.mozilla.org/pt-BR/docs/Learn/Getting_started_with_the_web/HTML_basics" %}

{% embed url="https://developer.mozilla.org/pt-BR/docs/Learn/Getting_started_with_the_web/What_will_your_website_look_like" %}
