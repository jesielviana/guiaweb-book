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

* JavaScript interno, quando o código Javascript é  inserido dentro do código HTML por meio da tag `<script>`, conforme o exemplo abaixo:

{% code title="index.html" %}
```html
<html>
....
<script>

  // código javascript aqui

</script>
</html>
```
{% endcode %}

* JavaScript externo, quando o código Javascript é escrito em um arquivo "`.js`" separado do HTML. Utiliza-se a tag `<script>` com a propriedade `src` recebendo como valor o caminho do arquivo Javascript, conforme o exemplo abaixo. Esta é a opção recomendada para integrar Javascript com HTML.

{% tabs %}
{% tab title="index.html" %}
```html
<html>
....
<script src=""> </script>
</html>
```
{% endtab %}

{% tab title="main.js" %}
```
// Some code<html>
....
<script>

  // código javascript aqui

</script>
</html><>
```
{% endtab %}
{% endtabs %}

* JavaScript inline

