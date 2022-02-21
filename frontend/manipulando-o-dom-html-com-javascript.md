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

### Ordem de carregamento do Javascript

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

O DOM é a representação em formato de árvore de todos os objetos que compõem a estrutura e o conteúdo de uma página web. Todos os elementos HTML de um página web possuem representações dentro do DOM. Veja abaixo uma representação gráfica de DOM:

{% tabs %}
{% tab title="index.html" %}
```html
<!DOCTYPE html>
<html lang="pt-Br">
<head>
  <title>Documento HTML</title>
</head>
<body>
  <header>
    <h1>Web dev book</h1>
    <p>Manipulando o DOM</p>
    <button name="btn">Clique aqui!</button>
  </header>
</body>
</html>
```
{% endtab %}

{% tab title="Representação do DOM do index.html" %}

{% endtab %}
{% endtabs %}

O DOM fornece uma interface de programação para manipulação dos elementos HTML. Por meio dele é possível modificar a estrutura e conteúdo do documento HTML e alterar o estilo da página.&#x20;

Para manipulação do DOM utiliza-se uma linguagem de script como JavaScript. Todas as propriedades, métodos e eventos disponíveis para manipular o DOM são representados por objetos.

### Objeto document

O objeto `document` representa a página web que está no navegador, ele é a raiz da árvore de elementos HTML que contém todos os objetos da página.

A partir do objeto `document` é possível acessar qualquer elemento HTML que está na página, ele é o ponto inicial para acessar os demais objetos.

O objeto `document` possui alguns métodos para manipulação dos elementos HTML, os mais utilizados são os métodos de acesso aos elementos. A tabela abaixo apresenta os principais métodos do objeto `document` para acessar os elementos HTML de páginas web.&#x20;

| Método                                        | Descrição                                                                                                |
| --------------------------------------------- | -------------------------------------------------------------------------------------------------------- |
| `document.getElementById(`_`id`_`)`           | Retorna um elemento de acordo com seu `id`.                                                              |
| `document.getElementsByTagName(`_`tag`_`)`    | Retorna uma lista de elementos de acordo com a tag especificada.                                         |
| `document.getElementsByClassName(`_`name`_`)` | Retorna uma lista de elementos de acordo com a classe especificada.                                      |
| `document.querySelector(selector)`            | Retorna o primeiro elemento encontrado na página que corresponde ao seletor especificado.                |
| `document.querySelectorAll(selector)`         | Retorna uma lista com todos os elementos encontrados na página que correspondem ao seletor especificado. |

Utilizando um dos métodos listados acima é possível acessar e manipular qualquer elemento do documento HTML que está no navegador.

### Lidando com eventos

Um evento é uma ação disparada pelo navegador web quando ocorre alguma mudança de estado dos objetos de uma página web que está sendo exibida. É possível utilizar-se Javascript para ""

Por exemplo, quando os usuários clicam em um botão em uma página da Web, convém responder a esse evento de clique exibindo uma caixa de diálogo.

Cada evento pode ter um manipulador de eventos que é um bloco de código que será executado quando o evento ocorrer.

Um manipulador de eventos também é conhecido como ouvinte de eventos. Ele escuta o evento e é executado quando o evento ocorre.
