---
description: >-
  Este capítulo apresenta uma visão simplificada dos principais tipos de
  arquiteturas de aplicações web
---

# Arquitetura de aplicações web

### Introdução&#x20;

A arquitetura de aplicações web descreve a estrutura interna e interações entre seus componentes, bancos de dados e sistemas externos.

A arquitetura da web é por natureza distribuída, baseada no modelo cliente-servidor. Chamamos de clientes os dispositivos de acesso as páginas web por meio de um navegador. Já os servidores são os computadores que hospedam as páginas web e os disponibilizam para os dispositivos clientes.

Utilizando o modelo cliente-servidor é possível estruturar uma aplicação web de diferentes maneiras, dependendo do tamanho, tecnologias utilizadas e quantidade de acessos. A seguir será apresentado alguns tipos de arquiteturas de aplicações web.

### Aplicações estáticas

Site estático é o modelo mais simples de aplicação web, construído com HTML, CSS e Javascript (opcional). Um site estático é aquele que retorna o mesmo conteúdo que está salvo no servidor sempre que uma determinada página é solicitada.&#x20;

A figura abaixo mostra de forma simplificada os principais componentes e fluxo de acesso à uma aplicação web estática, basicamente é o modelo cliente-servidor de forma simples e pura.

![](../.gitbook/assets/site-estatico.png)

Detalhamento do fluxo de acesso a um site estático, representado no diagrama acima.&#x20;

Quando o usuário deseja acessar uma determinada página, ele informa o seu endereço (URL) ao navegador, e em seguida:

1. O navegador envia uma requisição para o servidor HTTP solicitando a referida página HTML (especificada via URL).&#x20;
2. o servidor HTTP recupera o documento solicitado (página HTML) de seu sistema de arquivos; e&#x20;
3. retorna uma resposta HTTP contendo a página HTML para o navegador.&#x20;
4. por fim, o navegador exibe o conteúdo da página HTML formatada para visualização do usuário. **O conteúdo exibido para o usuário é o mesmo que está salvo no sistema de arquivos do servidor.**

Outras características dos sites estáticos:

* Simples, ótimo para blogs, portfólios e sites pessoais;
* Não tem necessidade de banco de dados;
* O conteúdo e layout de cada página é o mesmo para qualquer cliente.

Na próxima seção vamos conhecer a arquitetura de aplicações dinâmicas.

### Aplicações dinâmicas

Sites dinâmicos são aqueles que geram dinamicamente parte do conteúdo que é retornado para o cliente. Geralmente as páginas HTML definem o modelo com lacunas para serem preenchidas dinamicamente. O conteúdo dinâmico geralmente é armazenado em um banco de dados.

Um site dinâmico pode retornar dados diferentes para uma mesma URL com base nas informações fornecidas pelo usuário, localização, data de acesso, etc. Exemplo: se dois usuários autenticados acessarem a página inicial do Twitter irão visualizar informações diferentes, o layout da página é mesmo, mas o feed de tweets (conteúdo principal da página) será diferente, porque é carregado de acordo com o usuário autenticado.

Em uma aplicação dinâmica, o servidor é o responsável por  receber a requisição, identificar qual o modelo HTML deve ser retornado e preencher as lacunas do modelo com as informações dinâmicas baseada nos dados fornecido pelo cliente. Em seguida o servidor retorna a página HTML completa.&#x20;

É importante destacar que mesmo em aplicações dinâmicas sempre vai haver requisições de recursos estáticos, que são tratados como descritos na seção anterior. Recursos estáticos são quaisquer arquivos que não mudam - normalmente: CSS, JavaScript, imagens etc.

Veja um exemplo de acesso à um site dinâmico de _e-commerce_: o servidor possui os arquivos HTML com os layouts das páginas e armazena os dados dos produtos em um banco de dados (com isso uma página HTML com mesmo layout/modelo pode ser exibida com informações de diferentes produtos carregados dinamicamente do banco de dados). Com isso, ao receber uma solicitação HTTP para exibir um determinado produto , o servidor busca os dados do produto no banco de dados e, em seguida, constrói a página HTML para a resposta inserindo os dados dinâmicos em um modelo HTML.&#x20;

A figura abaixo mostra os principais elementos e o fluxo de acesso a um site dinâmico, como o descrito no exemplo acima.

![](../.gitbook/assets/site-dinamico.png)

Detalhamento da figura acima. Supomos que quando o usuário deseja acessar um determinado produto em um site, ele informa o seu endereço (URL) ao navegador, e em seguida os seguintes passos são executados (conforme numeração na figura acima):

1. O navegador envia uma requisição para o servidor HTTP solicitando os dados produto;
2. &#x20;O servidor de aplicação busca o modelo HTML para exibir dos dados do produto baseado na solicitação e identifica as lacunas que devem ser preenchidas com dados dinâmicos;
3. O servidor de aplicação carrega do banco de dados os dados do produto solicitado;
4. O servidor de aplicação monta dinamicamente uma página HTML preenchendo o modelo HTML com os dados dinâmicos carregados do banco de dados e envia como resposta para o cliente.
5. por fim, o navegador exibe o conteúdo da página HTML formatada para visualização do usuário. O conteúdo exibido para o usuário é composto pelo modelo HTML e pelos dados dinâmicos carregados do banco de dados.

> NOTA: Vale destacar que a figura acima é uma representação simplificada do fluxo de acesso à uma aplicação dinâmica, onde foi ocultado o carregamento de recursos estáticos (CSS, Javascript, imagens, etc).

Dentro do contexto de aplicações web dinâmicas chamados de front-end a interface visual da aplicação, que provê interação com o usuário e back-end a parte que envolve a programação no lado do servidor (regras de negócio, acesso a banco de dados, etc).

Para construção do front-end, geralmente é utilizado HTML, CSS, Javascript e seus frameworks (Angular, React, Vue.js, etc). Já no back-end é comum a utilização de tecnologias Java, Javascript, Python, Ruby, etc.

Do ponto de vista da organização do front-end e back-end de uma aplicação dinâmica, eles podem ser acoplados, front-end e back-end são desenvolvidos juntos, usando a mesma tecnologia e hospedados no mesmo servidor. Outra forma de desenvolver aplicações é separar o back-end do front-end, são desenvolvidos e hospedados separadamente.&#x20;

A figura apresentada acima representa uma aplicação com **front-end e back-end acoplados**. Neste tipo de aplicação a interface de usuário, código de regras de negócio e acesso aos dados são combinados em um único programa hospedados em um único servidor.&#x20;

Já na abordagem de separação do front-end e back-end, as duas partes são desenvolvidas e hospedadas separadamente, podendo usar tecnologias diferentes. Na maioria das vezes a comunicação entre o front-end e back-end é realizada seguindo o modelo arquitetural [REST](https://developer.mozilla.org/pt-BR/docs/Glossary/REST). Esta abordagem ganhou bastante mercado com o surgimento e utilização dos frameworks SPA (Angular, React, Vue.js, etc).

A figura abaixo mostra os principais elementos e o fluxo de acesso a uma aplicação com front-end separado do back-end.

![](../.gitbook/assets/front-vs-back.png)

Vantagens de aplicações com front-end separado do back-end:

* Promove a modularização com a separação de tecnologias, frameworks e melhores práticas específicos para cada tipo;
* Facilita a organização das equipes por área de desenvolvimento;
* Reduz o tamanho da base de código de cada parte;

Desvantagens de aplicações com front-end separado do back-end:

* Pode dificultar a comunicação entre equipes de front-end e back-end;
* Aumenta os cuidados com gerenciamento e segurança da aplicação;
* A integração entre front-end e back-end pode aumentar a quantidade de bugs;



