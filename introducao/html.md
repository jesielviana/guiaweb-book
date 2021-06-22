---
description: Introdução a linguagem de marcação utilizada para criar páginas Web
---

# HTML

> Objetivos de aprendizagem
>
> * Conhecer a linguagem de marcação HTML
> * Entender a sintaxe básica da linguagem
> * Conhecer as tags básicas da HTML

### Introdução

Como descrito na aula anterior, a Web é baseada na interligação de documentos de hipermídia que podem conter textos, imagens, vídeos, etc. Para criação desses documentos, conhecidos como páginas Web, utiliza-se a linguagem de marcação HTML - Hypertext Markup Language. 

A linguagem HTML permite estruturar uma página web e seu conteúdo com texto, imagens, vídeos, etc e interligá-los com outras páginas na Web de forma simples e padronizada.

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

Um documento HTML é formado por elementos, que na sua maioria é formada por uma tag de abertura no início do elemento e uma tag de fechamento que indica o fim do elemento. Veja a descrição dos elementos do código acima.

* `<!DOCTYPE html>` - declaração que define que este documento é do tipo HTML5, deve ser a primeira _tag_ do documento \(obrigatório\);
* `<html>` - é o elemento raiz de uma página HTML, composto pela _tag_ `<html>`, que indica o início do documento e pela _tag_ `</html>` que delimita o final do documento. Observe que a tag de fechamento tem uma `/`. Isso é padrão para todos os elementos que possuem tag de fechamento. 
* `<head>`  - elemento que contém configurações e meta informações sobre o documento, o conteúdo colocado dentro deste elemento não fica visível no página Web, quando acessada pelo navegador. Este elemento também formado pelas tags de abertura e fechamento.
* `<body>`  - elemento que indica o corpo do documento, contém todo conteúdo da  visível da página Web. Também formado pelas tags de abertura e fechamento.

