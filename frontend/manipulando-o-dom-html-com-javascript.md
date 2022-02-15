---
description: Introdução a manipulação de elementos HTML com Javascript
---

# Manipulando o DOM HTML com Javascript

### Introdução

Javascript é uma linguagem de programação bastante utilizada para implementar funcionalidades em página web no lado cliente, ou seja, funções que são executadas pelo navegador.&#x20;

Javascript juntamente com HTML e CSS forma o tripé de tecnologias básicas da web.

* **HTML** é utilizado para estrutura o conteúdo em página Web;
* **CSS** é a linguagem de estilo, utilizada para configurar layouts, sendo usada para definir tamanhos, cores, alinhamento, etc; e
* **Javascript** é a linguagem de programação utilizada para adicionar e atualizar recursos dinâmicos e melhorar a interatividade nas páginas web.

O JavaScript pode ser inserido em uma página web de formas diferentes: interno, externo e inline. Abaixo será descrito cada uma dessas formas.

* **Javascript interno** - o código Javascript é  inserido dentro do código HTML por meio da tag `<script>`, conforme o exemplo abaixo:

{% code title="index.html" %}
```html
<html>
    <head>
    </head>
    <body>
        ...
        <script>
            // código javascript aqui
        </script>
    </body>
</html>
```
{% endcode %}

* **Javascript externo** - o código Javascript é escrito em um arquivo "`.js`" separado do HTML. Utiliza-se a tag `<script>` com a propriedade `src` recebendo como valor o caminho do arquivo Javascript, conforme o exemplo abaixo. **Esta é a opção recomendada para integrar Javascript com HTML**.

{% tabs %}
{% tab title="index.html" %}
```html
<html>
    <head>
    </head>
    <body>
        ...
        <script src="main.js"> </script>
    </body>
</html>
```
{% endtab %}

{% tab title="main.js" %}
```javascript
// arquivo com código javascript
function init(){
 
}
```
{% endtab %}
{% endtabs %}

* **Javascript inline** - o código Javascript é colocado diretamente dentro do elemento HTML, como no exemplo abaixo:

```html
<html>
    <head>
    </head>
    <body>
        ...
        <button onclick="alert('Oi')">Clique!</button>
    </body>
</html>
```

O uso de Javascript inline dentro dos elementos polui o código HTML com Javascript e não favorece o reaproveitamento de código, sendo considerado uma má prática, por favor, EVITE FAZER ISSO! &#x20;

Sempre que possível use a integração via arquivo externo.

#### Ordem de carregamento do Javascript

Um página web é carregada pelo navegador de acordo com a ordem de escrita do HTML, de cima para baixo.&#x20;

De modo geral é recomendado adicionar a importação dos arquivos Javascript no final do HTML para não travar o carregamento da página, no entanto, as vezes faz-se necessário a execução de scripts durante o carregado da página HTML.

Para lidar com o bloqueio do carregamento da página e scripts, há dois recursos que podem ser usados: as propriedades `async` e `defer` da tag `script.`

```html
<script defer src="list.js"></script>
<script async src="tables.js"></script>
```

Scripts que são carregados utilizando o atributo `defer` (conforme exemplo acima) serão carregados exatamente na ordem em que aparecem na página e executados assim que o arquivo do script for baixado pelo navegador. Durante o carregamento do script a renderização da página é bloqueada, ou seja, o conteúdo que está abaixo dele só será carregado após o script ser totalmente baixado pelo navegador.

Já os scripts que são carregados usando o atributo `async` (conforme exemplo acima) não bloqueiam a renderização da página e também irão executar imediatamente após serem baixados pelo navegador. Desta forma não há garantia de ordem de carregamento dos scripts, mas eles não irão impedir o carregamento do restante da página.&#x20;

Use o atributo `async` para carregar scripts independentes, aqueles que não dependem do carregamento prévio de nenhum outro arquivo. Sempre que possível utilize o atributo `async` em seus scripts.

Geralmente utiliza-se Javascript nas páginas web para adicionar comportamentos dinâmicos por meio da manipulação dos elementos HTML, conhecido como Document Object Model (DOM).

### O que é DOM?

DOM é a representação de dados dos objetos que compõem a estrutura e o conteúdo de um documento na Web. Tem o formato de uma árvore composta por nós.

O DOM também fornece uma interface de programação para manipulação dos elementos HTML. Por meio dele é possível alterar a estrutura de documento HTML, alterar o estilo e conteúdo.
