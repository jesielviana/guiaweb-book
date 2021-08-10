---
description: >-
  Apresentação dos conceitos básicos e uma visão simplificada do fluxo de
  execução da Web.
---

# Como a Web funciona?

> **Objetivos de aprendizagem**
>
> * Conhecer os componentes básicos da Web
> * Entender de forma simplificada o fluxo de execução da web

### Introdução

Para começar a entender o funcionamento da Web precisamos conhecer alguns componentes básicos que compõem a arquitetura da Web. Iniciaremos pelos conceitos de Clientes e Servidores.

Qualquer dispositivo conectado na internet é conhecido como Cliente ou Servidor, depende da função dele na rede.

* **Clientes** - são os dispositivos conectados à Internet pelos quais os usuários acessam as páginas Web \(por exemplo, seu computador conectado ao seu Wi-Fi ou seu telefone conectado à sua rede móvel\). Geralmente as páginas Web são acessadas por através de navegadores Web \(Chrome, Firefox, Brave, etc.\) instalados nesses dispositivos.
* **Servidores** - são computadores que armazena arquivos que compõem os sites \(por exemplo, documentos HTML, imagens, folhas de estilo, e arquivos JavaScript\) e disponibilizam esses arquivos/páginas/sites para serem acessados pelos dispositivos clientes. Para isso, o servidor deve está conectado a Internet, e assim, poderá ser acessado através do seu endereço IP ou nome de domínio \(por exemplo, `jesielviana.com`\). 

A conexão entre clientes e servidores é realizada por meio da internet. A imagem abaixo apresenta de forma simplificada como Cliente e Servidor interagem na Web.

![](https://lh3.googleusercontent.com/OrHDa8WZjfLZtfm3O1SrqMcXAhSxYYRMCM1PqtBMaqH19u4PDTK-h9rfd8EJ_tMCaDqNtl4EPioskrvFq-oIMTSfWA_HlTd8WgVdPxnNJnazS2Om6y9rUw5ahmfk-vN9lmo0)

Para entender melhor como funciona a interação entre os componentes da Web vamos detalhar como é comunicação na Internet.

### Comunicação na Web

Como vimos no capítulo de Introdução a Web, a Web é um serviço que é executado sob a Internet, então para melhor compreendermos seu funcionamento,  precisamos entender de forma simplificada como funciona a comunicação entre computadores na Internet.

A comunicação entre dois ou mais dispositivos na Internet é realizada por meio endereços \(conhecido como endereço IP\) que identificam os dispositivos na rede e portas que fornecem pontos de conexão para aplicações e serviços específicos. 

De forma resumida, para que um dispositivo A possa se comunicar com um dispositivo B, o dispositivo A precisa saber o endereço IP de B e saber qual a porta de B está disponível para ele \(oferece o serviço que ele espera\). A figura abaixo ilustra a comunicação entre dois computadores \(dispositivos A e B\). Onde o computador A pode acessar o serviço Web \(porta 80\) do computador B. 

![Comunica&#xE7;&#xE3;o entre dois computadores via Internet](../.gitbook/assets/conexao-na-web.png)

De acordo com a explicação acima, para nós podermos acessar um determinado site, deveríamos saber qual o endereço IP do servidor que armazena site e a porta em que aquele site está disponível, mas, na prática, não fazemos isso.

Quando acessamos um determinado site a partir do nosso computador ou smarphone, geralmente informamos para o navegador o endereço do site, também conhecido como domínio. E o navegador se encarrega de descobrir qual o endereço do servidor que armazena o site. Para fazer isso, o navegador utiliza um recurso chamado de DNS - Domain Name System. 

