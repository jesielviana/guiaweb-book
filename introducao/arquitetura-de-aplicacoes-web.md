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

O modelo mais simples são as aplicações estáticas, construída com HTML, CSS e Javascript (opcional). Um site estático é aquele que retorna o mesmo conteúdo que está salvo no servidor sempre que uma determinada página é solicitada.&#x20;

A figura abaixo mostra uma arquitetura básica  de uma aplicação web estática, basicamente é o modelo cliente-servidor de forma simples e pura.

![Arquitetura e fluxo de acesso de sites dinâmicos](../.gitbook/assets/site-estatico.png)

Detalhamento do fluxo de acesso a um site estático, representado no diagrama acima.&#x20;

Quando o usuário deseja acessar uma determinada página, ele informa o seu endereço (URL) ao navegador, e em seguida:

1. O navegador envia uma requisição para o servidor HTTP solicitando a referida página HTML (especificada via URL).&#x20;
2. o servidor recupera o documento solicitado (página HTML) de seu sistema de arquivos; e&#x20;
3. retorna uma resposta HTTP contendo a página HTML para o navegador.&#x20;
4. Por fim, o navegador exibe o conteúdo da página HTML formatada para visualização do usuário. **O conteúdo exibido para o usuário é o mesmo que está salvo no sistema de arquivos do servidor.**

Outras características dos sites estáticos:

* Não possibilita a interação do usuários;
* Possui um número fixo de páginas;
* O conteúdo e layout de cada página é o mesmo para qualquer cliente.

Na próxima seção vamos conhecer a arquitetura de aplicações dinâmicas.

### Aplicações dinâmicas
