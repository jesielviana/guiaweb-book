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





