---
description: Introdução a manipulação de elementos HTML com Javascript
---

# DOM e Javascript

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
alert('arquivo javascript carregado') // função que exibe um pop-up na tela
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
  <h1>Web dev book</h1>
  <button id="btn">Clique aqui!</button>
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

Utilizando um dos métodos listados acima é possível acessar e manipular qualquer elemento do documento HTML que está no navegador. Veja o exemplo abaixo:

{% tabs %}
{% tab title="index.html" %}
```html
<!DOCTYPE html>
<html lang="pt-Br">
<head>
  <title>Documento HTML</title>
</head>
<body>
  <h1>Web dev book</h1>
  <button id="btn">Clique aqui!</button>
  <script src="main.js"></script>
</body>
</html>
```
{% endtab %}

{% tab title="main.js" %}
```javascript
// pegando o elemento button pelo seu id 'btn', a # indica que o seletor é atributo id
const botao = document.querySelector("#btn")

```
{% endtab %}
{% endtabs %}

### Lidando com eventos

Um evento é uma ação disparada pelo navegador web quando ocorre alguma mudança de estado dos elementos de uma página HTML. É possível utilizar-se Javascript para "ouvir" os eventos disparados pelo navegador e em seguida realizar alguma operação.

Por exemplo, quando o usuário clica em um botão em uma página da web, o navegador dispara o evento de clique, que pode ser capturado pelo Javascript para executar alguma ação.

O Javascript possui um conjunto de funções para tratar os eventos dos elementos HTML, essas funções são conhecidas como manipuladores de eventos (event handlers em inglês). Essas funções permite capturar eventos específicos e fazer alguma manipulação.

Os manipuladores de eventos geralmente têm nomes que começam com `on`, por exemplo, o manipulador de eventos para o evento click é `onclick`.

A tabela abaixa apresenta alguns dos eventos HTML emitidos pelo navegador:

| Evento emitido | Função manipuladora do evento (event handler)) | Quando o evento ocorre                                     |
| -------------- | ---------------------------------------------- | ---------------------------------------------------------- |
| load           | `onload`                                       | Quando o navegador termina de carregar a página.           |
| click          | `onclick`                                      | Ao clicar com o mouse em um elemento.                      |
| input          | `oninput`                                      | Quando o valor de um campo de entrada de texto e alterado. |
| change         | `onchange`                                     | Quando o usuário altera o valor de um elemento.            |
| mouseover      | `onmouseover`                                  | Quando o cursor do mouse passa sobre o elemento.           |
| mouseout       | `onmouseout`                                   | Quando o cursor do mouse sai de um elemento                |
| keydown        | `onkeydown`                                    | Quando o usuário pressiona uma tecla do teclado.           |

Os manipuladores de eventos podem ser usados para manipular e verificar o carregamento da página, as ações do usuário e as ações do navegador. Existem basicamente duas maneiras de atribuir manipuladores de eventos aos elementos HTML:

* **Adicionando o event handler como atributo HTML**

Umas das formas de adicionar manipular um evento de um determinado elemento é adicionar a função manipuladora do evento (event handler) como atributo do elemento HTML. E passar como valor do atributo a função Javascript que será executada quando o evento ocorrer.  \
Veja o exemplo de como exibir uma mensagem pop-up sobre a página quando o usuário clicar no botão "Clique aqui!".

{% tabs %}
{% tab title="index.html" %}
```html
<!DOCTYPE html>
<html lang="pt-Br">
<head>
  <title>Documento HTML</title>
</head>
<body>
  <h1>Web dev book</h1>
  <button onclick="executaEvento() id="btn">Clique aqui!</button>
  <script src="main.js"></script>
</body>
</html>
```
{% endtab %}

{% tab title="main.js" %}
```javascript
function executaEvento(){
    alert('você clicou no botão!')
}

```
{% endtab %}
{% endtabs %}

A manipulação de eventos usando atributos de manipuladores de eventos HTML é considerada uma má prática, pois mistura o código Javascript com o código HTML, tornando mais difícil e leitura e entendimento do código e sua manutenção. Além disso, pode ocorrer problemas na ordem do carregamento, tendo em visa que geralmente o HTML é carregado antes do Javascript. Portanto, EVITE!

* **Manipulando eventos por meio do DOM (Recomendado)**

Usando apenas Javascript é possível acessar os elementos HTML via DOM e vincular funções manipuladores sem interferir diretamente no código HTML.&#x20;

Todo elemento disponível no DOM possui propriedades manipuladoras de eventos, como por exemplo a propriedade `onclick`. Para atribuir um manipulador de eventos, basta atribuir uma função para a propriedade. Veja o exemplo abaixo:

{% tabs %}
{% tab title="index.html" %}
```html
<!DOCTYPE html>
<html lang="pt-Br">
<head>
  <title>Documento HTML</title>
</head>
<body>
  <h1>Web dev book</h1>
  <button id="btn">Clique aqui!</button>
  <script src="main.js"></script>
</body>
</html>
```
{% endtab %}

{% tab title="main.js" %}
```javascript
  // pegando o elemento button pelo seu id 'btn'
  const botao = document.querySelector('#btn')
  
  /* atrbuindo uma função anônima para o atributo onclick */
  botao.onclick = () => {
    alert('você clicou no botão!') // função que exibe um pop-pu sobre a tela com o texto "você clicou no botão!"
  }
```
{% endtab %}
{% endtabs %}

O código do arquivo `main.js` na linha 2 "pega" o elemento button da página HTML e armazena na constante "`botao`". Em seguida, nas linhas de 5 a 7, adiciona uma função anônima para o atributo `onclick` do `botao`, essa função anônima será executada toda vez o evento de _click_ for disparado, ou seja, toda vez que o usuário clicar no botão vai ser exibido uma pop-up com o texto _"você clicou no botão!"_&#x20;

Por meio do DOM também é possível vincular uma função para um evento de um determinado elemento usando o método `addEventListener`, todo elemento disponível no DOM também possui este método.&#x20;

O método `addEventListener` pode receber três parâmetros, mas geralmente é utilizado somente com dois: o nome do evento e a função de manipulação do evento. Veja abaixo como utilizar a função `addEventListener` para manipular o evento de click do botão.

{% tabs %}
{% tab title="index.html" %}
```html
<!DOCTYPE html>
<html lang="pt-Br">
<head>
  <title>Documento HTML</title>
</head>
<body>
  <h1>Web dev book</h1>
  <button id="btn">Clique aqui!</button>
  <script src="main.js"></script>
</body>
</html>
```
{% endtab %}

{% tab title="main.js" %}
```javascript
// pegando o elemento button pelo seu id 'btn'
const botao = document.querySelector('#btn')

/* atribuindo uma função anônima para o evento de click */
botao.addEventListener('click', () => {
  alert('você clicou no botão!')
})
```
{% endtab %}
{% endtabs %}

Assim como no exemplo anterior, o código do arquivo `main.js` na linha 2 "pega" o elemento button da página HTML e armazena na constante "`botao`". Em seguida, nas linhas de 5 a 7, é utilizada o método `addEventListener` para vincular uma função anônima para o evento de _click_ do `botao`, essa função anônima será executada toda vez o evento de _click_ for disparado, ou seja, toda vez que o usuário clicar no botão vai ser exibido uma pop-up com o texto _"você clicou no botão!"_&#x20;

### Alterando o conteúdo da página HTML dinamicamente via DOM

Usando a API do DOM podemos acessar elementos da página HTML, alterar seus valores e atualizar a página de forma dinâmica (baseada em alguma ação do usuário) sem a necessidade de recarregá-la.&#x20;

Já aprendemos usar a API do DOM via Javascript para acessar elementos da página e executar alguma operação baseada em eventos disparados navegador. Agora vamos ver como alterar elementos utilizando o DOM.

O código abaixo mostra um exemplo com dois elementos HTML: um input (elemento de entrada de texto) e um parágrafo (elemento de saída de texto). Vamos utilizar Javascript para atualizar o campo de saída de texto com o conteúdo digitado pelo usuário no campo de input.

{% tabs %}
{% tab title="index.html" %}
```html
<!DOCTYPE html>
<html lang="pt-Br">
<head>
  <title>Documento HTML</title>
</head>
<body>
  <input id="text" type="text">
  <p id="message"></p>
  <script src="main.js"></script>
</body>
</html>
```
{% endtab %}

{% tab title="main.js" %}
```javascript
// pega o elemento de input pelo seu id 'text' 
const inputText = document.querySelector('#text')

// pega o elemento de parágrafo pelo seu id 'message' 
const message = document.querySelector('#message')

// adiciona uma função para manipular evento de 'input' do campo de input 
inputText.addEventListener('input', () => {
 // pega o valor do campo de input e adiciona no elemento parágrafo
  message.textContent = inputText.value 
})
```
{% endtab %}
{% endtabs %}

O código do arquivo `main.js` nas linhas 2 e 5 "pega" os elementos de input e parágrafo da página HTML e armazena nas constante "`inputText`" e "`message`" respectivamente. Em seguida, nas linhas de 8 a 11, é utilizada o método `addEventListener` para vincular uma função anônima para o evento de _input_ do campo _input_. Essa função (linha 10) atualiza o conteúdo do parágrafo com o valor que está no campo de input. Ela é executada toda vez o evento de _input_ for disparado, ou seja, toda vez que o usuário digitar alguma caracter no campo de input (Lembrando que o evento de input é disparado toda vez que o valor do campo de entrada de texto ao qual ele está vinculado é alterado). &#x20;

Dessa forma, através do DOM é possível atualizar dinamicamente o conteúdo de uma página HTML sem a necessidade de recarregá-la.&#x20;

No exemplo anterior foi realizado apenas uma simples demonstração de alteração dinâmica de uma página web baseada na ação do usuário. Utilizando a API do DOM é possível fazer muito mais, tais como adicionar novos elementos HTML na página, remover elementos e alterar a estrutura da página. [Veja mais...](https://developer.mozilla.org/pt-BR/docs/Web/API/Document\_Object\_Model/Introduction)

### Alterando o estilo (CSS) da página via DOM

A API do DOM disponibiliza algumas propriedades para manipulação do estilo CSS dos elementos HTML. As propriedades mais utilizadas são _style_ (`element.style`) e _classList (`element.classList`)_, todo elemento HTML possui essas propriedades.

Usando a propriedade style do elemento HTML é possível definir propriedades CSS embutidas (_CSS inline_) para o elemento HTML.&#x20;

A propriedade style retorna o objeto CSSStyleDeclaration somente de leitura que contém uma lista das propriedades CSS. Por exemplo, para alterar a cor da fonte de um elemento é o seguinte código: `elemento.style.color = "novaCor"`, para alterar o tamanho da fonte:  `elemento.style.fontSize = "novoTamanho"`, etc.  Se a propriedade CSS contiver hífens (-) por exemplo `font-size`, você pode remover o hífen e usar o padrão camel-case conforme o exemplo anterior.

&#x20;Vamos ver um exemplo de como alterar a cor da fonte de um elemento dinamicamente de acordo com a ação do usuário. No exemplo abaixo a página HTML possui um elemento de título (`<h1>`) e dois elementos de botões (`<button>`), o usuário pode clicar nos botões para definir uma cor para o texto do título.

{% tabs %}
{% tab title="index.html" %}
```html
<!DOCTYPE html>
<html lang="pt-Br">
<head>
  <title>Documento HTML</title>
</head>
<body>
  <h1 id="titulo">Web dev book</h1>
  <button id="verde">Título Verde</button>
  <button id="azul">Título Azul</button>
  
  <script src="main.js"></script>
</body>
</html>
```
{% endtab %}

{% tab title="main.js" %}
```javascript
const elementoTitulo = document.querySelector('#titulo')
const elementoBtnVerde = document.querySelector('#verde')
const elementoBtnAzul = document.querySelector('#azul')

elementoBtnVerde.addEventListener('click', () => {
  // quando o usuário clieca no botão "Título Verde"  altera a cor da fonte do elementoTitulo para verde (green)
  elementoTitulo.style.color = 'green'
})

elementoBtnAzul.addEventListener('click', () => {
  // quando o usuário clieca no botão "Título Azul" altera a cor da fonte do elementoTitulo para azul (blue)
  elementoTitulo.style.color = 'blue'
})
```
{% endtab %}
{% endtabs %}

Já por meio da propriedade classList é possível manipular as classes CSS do elemento: listar, remover e adicionar novas classes.

A `classList` é uma propriedade somente leitura de um elemento que retorna uma coleção ativa de classes CSS. Essa propriedade dispõe de vários métodos para manipulação  das classes.

Para adicionar uma ou mais classes CSS à lista de classes de um elemento, use o método `add()` da classList. Por exemplo, o código a seguir adiciona a classe `"verde"` ao elemento `<h1>` com o  id `titulo`:

```javascript
 const elementoTitulo = document.querySelector('#titulo')
 elementoTitulo.classList.add('verde')
```

Para remover uma classe CSS da lista de classes de um elemento, use o método `remove()`. O exemplo a seguir remove a classe verde do elemento `<h1>` com o  id `titulo`:

```javascript
va const elementoTitulo = document.querySelector('#titulo')
 elementoTitulo.classList.remove('verde')
```

É comum a implementação de CSS para alternância de elementos HTML, tais como mostrar e esconder um elemento dependendo de alguma ação do usuário. Para isso podemos usar o método `toggle()` da propriedade classList, que tem o seguinte comportamento: Se o elemento contiver a classe especificada no método `toggle()`, ele o removerá. Se o elemento não contiver a classe, o método `toggle()` o adicionará ao elemento.

Vamos implementar o exemplo da alternância de cor do texto do título utilizando o método `toggle()` da propriedade `classList`.  Para isso, vamos adicionar as classes CSS no mesmo arquivo HTML (`index.html`).

{% tabs %}
{% tab title="index.html" %}
```html
<!DOCTYPE html>
<html lang="pt-Br">
<head>
  <title>Documento HTML</title>
  <style>
    .verde {
      color: green;
    }

    .azul {
      color: blue;
    }
  </style>
</head>
<body>
  <h1 id="titulo">Web dev book</h1>
  <button id="verde">Título Verde</button>
  <button id="azul">Título Azul</button>
  
  <script src="main.js"></script>
</body>
</html>
```
{% endtab %}

{% tab title="main.js" %}
```javascript
const elementoTitulo = document.querySelector('#titulo')
const elementoBtnVerde = document.querySelector('#verde')
const elementoBtnAzul = document.querySelector('#azul')

elementoBtnVerde.addEventListener('click', () => {
  elementoTitulo.classList.toggle('verde')
})

elementoBtnAzul.addEventListener('click', () => {
  elementoTitulo.classList.toggle('azul')
})
```
{% endtab %}
{% endtabs %}

Quando houver a necessidade de manipulação do estilo CSS por meio do DOM considere as opções listadas acima. Dependendo do contexto e necessidade uma pode ser mais adequada, no entanto, não existe uma única solução perfeita para todos os casos. Avalie e use a solução que achar mais apropriada.&#x20;

### Conclusão

Sempre que precisar integrar Javascript com páginas HTML use arquivos separados, deixe seu código mais limpo e mais fácil ler e manter.

Seja cuidadoso com o tipo e a ordem de carregamento dos scripts para evitar lentidão de carregamento da página e problemas dependências entre arquivos. Sempre que possível use a propriedade `async` no carregamento dos scrips para não bloquear a renderização da página.

Use a API do DOM para manipulação dinâmica de páginas HTML sem a necessidade de recarregamento. Conheça o objeto document e os eventos emitidos pelo navegador para capturar r&#x20;

Use as propriedades do objeto element.style para definir as propriedades CSS embutidas para o elemento HTML.

A propriedade classList do elemento retorna a coleção ativa de classes CSS do elemento. Essas propriedade possui um conjunto de métodos para manipulação das classes CSS do elemento HTML. Use `add()`  e `remove()` para adicionar e remover respectivamente classes CSS à um elemento HTML. Use o método toggle() para alternar uma classe do elemento.
