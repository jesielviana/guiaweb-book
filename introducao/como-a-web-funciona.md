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

Qualquer dispositivo conectado na internet é conhecido como Cliente ou Servidor, depende de sua função na rede.

* **Clientes** - são os dispositivos conectados à Internet pelos quais os usuários acessam as páginas Web (por exemplo, seu computador conectado ao seu Wi-Fi ou seu telefone conectado à sua rede móvel). Geralmente as páginas Web são acessadas por através de navegadores Web (Chrome, Firefox, Brave, etc.) instalados nesses dispositivos.
* **Servidores** - são computadores que armazena arquivos que compõem os sites (por exemplo, documentos HTML, imagens, folhas de estilo, e arquivos JavaScript) e disponibilizam esses arquivos/páginas/sites para serem acessados pelos dispositivos clientes. Para isso, o servidor deve está conectado a Internet, e assim, poderá ser acessado através do seu endereço IP ou nome de domínio (por exemplo, `jesielviana.com`).&#x20;

A conexão entre clientes e servidores é realizada por meio da internet. A imagem abaixo apresenta de forma simplificada como Cliente e Servidor interagem na Web.

![](https://lh3.googleusercontent.com/OrHDa8WZjfLZtfm3O1SrqMcXAhSxYYRMCM1PqtBMaqH19u4PDTK-h9rfd8EJ\_tMCaDqNtl4EPioskrvFq-oIMTSfWA\_HlTd8WgVdPxnNJnazS2Om6y9rUw5ahmfk-vN9lmo0)

Para entender melhor como funciona a interação entre os componentes da Web vamos detalhar como é comunicação na Internet.

### Comunicação na Web

Como vimos no capítulo de Introdução a Web, a Web é um serviço que é executado sob a Internet, então para melhor compreendermos seu funcionamento,  precisamos entender de forma simplificada como funciona a comunicação entre computadores na Internet.

A comunicação entre dois ou mais dispositivos na Internet é realizada por meio endereços (conhecido como endereço IP) que identificam os dispositivos na rede e portas que fornecem pontos de conexão para aplicações e serviços específicos.&#x20;

De forma resumida, para que um dispositivo A possa se comunicar com um dispositivo B, o dispositivo A precisa saber o endereço IP de B e saber qual a porta de B está disponível para ele (oferece o serviço que ele espera). A figura abaixo ilustra a comunicação entre dois computadores (dispositivos A e B). Onde o computador A pode acessar o serviço Web (porta 80) do computador B.&#x20;

![Comunicação entre dois computadores via Internet](../.gitbook/assets/conexao-na-web.png)

De acordo com a explicação acima, para nós podermos acessar um determinado site, deveríamos saber qual o endereço IP do servidor que armazena site e a porta em que aquele site está disponível, mas, na prática, não fazemos isso.

Quando acessamos um determinado site a partir do nosso computador ou smartphone, geralmente informamos para o navegador o endereço do site, também conhecido como URL (_Uniform Resource Locator_). E o navegador se encarrega de descobrir qual o endereço do servidor que armazena o site.&#x20;

URL é  o endereço de um determinado recurso exclusivo na Web. Esse recurso pode ser uma página HTML, um documento CSS, uma imagem, um arquivo PDF, etc. Veja na figura a seguir as partes que formam uma URL, abaixo será descrito cada parte.

![Partes que compõe uma URL](../.gitbook/assets/url.png)

Agora vamos descrever cada uma das partes da URL:

* **Protocolo (obrigatório) -** informa ao navegador qual o protocolo de comunicação, pode ser `http` ou `https`. Quando não digitamos na barra de endereço o próprio navegador preenche.
* **Subdomínio (opcional)** - serve como uma extensão do nome de domínio, geralmente utilizado para disponibilizar diferentes sites/sistemas no mesmo domínio.
* **Domínio (obrigatório)** - é basicamente o nome (identificador) do site. Deve ser informado pelo usuário na barra de endereços do navegador, SEMPRE!
* **Porta (opcional)** - identifica a porta em que o site está disponível no servidor, quando não é informada o navegador preenche internamente com a porta padrão de acordo com o protocolo utilizado (80 para http e 443 para https);
* **Recurso/path (obrigatório)** - identifica qual o recurso o navegador vai buscar no servidor, quando não é informado pelo usuário o próprio navegador preenche com uma "/", que significa página inicial do site.
* **Query e parâmetros (opcional)** - utilizado para enviar dados no formato de chave e valor pela URL. No exemplo o `id` é a chave e `12345` é o valor.
* **Âncora (opcional)** - utilizado para exibir partes específicas da página Web.

Para descobrir o endereço IP de um site o navegador utiliza a parte de domínio da URL e  interage com um recurso chamado DNS - Domain Name System (Servidor de Nome de Domínio em português).

### DNS - Domain Name System

Servidores DNS guardam uma grande lista de nomes de sites (domínios) e seus respectivos endereços IPs, com isso, ele sabe em qual computador (pelo endereço IP) da Internet está hospedado determinado site (pelo domínio).  Quando você digita um endereço web no seu navegador, o navegador procura no servidor de DNS para localizar o endereço IP do servidor que hospeda o site, para ele poder acessar o site diretamente. &#x20;

Vamos ver um exemplo de como funciona o fluxo de troca de mensagens entre o navegador e DS quando informamos uma URL de um site que desejamos acessar na barra de endereços do nosso navegador.

1. **Usuário** digita `www.jesielviana.com/` na barra de endereços do navegador;&#x20;
2. **Navegador** vai até o servidor DNS e pergunta:  olá DNS, você sabe o endereço IP do servidor que hospeda o domínio `www.jesielviana.com`?
3. **DNS** responde ao navegador: opa, o endereço IP do servidor que armazena esse domínio é `192.18.45.2`.
4. Navegador se conecta ao servidor `192.18.45.2` e solicita a página web desejada.

É importante destacar que esse fluxo completo só ocorre a primeira vez que você acessa o site no seu navegador, geralmente no primeiro acesso o navegador guarda no seu próprio cache o endereço IP correspondente aquele domínio para que nas próximas vezes que você acessar aquele site ele já vai direto no servidor do site sem precisar ir até o DNS novamente.&#x20;

Toda troca de mensagens entre navegadores e servidores Web são realizadas por meio do protocolo _**HTTP - Hypertext Transfer Protocol.**_&#x20;

### HTTP

O protocolo HTTP é conhecido como o _"idioma"_ dos navegadores e servidores web, é através deste _"idioma"_ que o seu navegador informa ao servidor web: página solicitada, sua versão, seu idioma, etc. E o servidor web informa ao seu navegador: se a página solicitada existe, formato do arquivo, o conteúdo da página solicitada, etc.

Vamos nos aprofundar mais sobre HTTP no próximo capítulo.&#x20;

### Conclusão

A figura abaixo resume de forma simplificada o que acontece quando você digita um endereço da web no seu navegador:

![Fluxo de mensagens ao acessar uma página Web](../.gitbook/assets/fluxo-web.png)

Segue a explicação de cada passo mostrado na figura acima:

1. O navegador pergunta ao DNS qual o endereço IP do servidor onde o site está hospedado.
2. O DNS retorna o endereço IP daquele site de acordo com o domínio;
3. O navegador manda uma mensagem de requisição HTTP para o servidor que está hospedando o site, pedindo que o servidor envie uma cópia de determinada página, de acordo com a URL informada pelo usuário.
4. Se o servidor aprovar a requisição do cliente, o servidor enviará ao cliente uma mensagem de "OK",  e então começa a enviar os arquivos da página solicitada para o navegador.
5. O navegador carrega os arquivos recebidos (html, css, js, etc), monta a página e exibe-a para o usuário.

{% embed url="https://www.youtube.com/watch?v=DmUk0RJ_xdc" %}

{% embed url="https://www.youtube.com/watch?v=xCytYkNzuK4" %}

{% embed url="https://docs.google.com/presentation/d/1BzgZoTPmfnv7n9x596fkt3Q8UU4K0zv0wlP1Isx5Noc" %}

### Referências&#x20;

{% embed url="https://developer.mozilla.org/pt-BR/docs/Learn/Getting_started_with_the_web/How_the_Web_works" %}

{% embed url="https://developer.mozilla.org/pt-BR/docs/Learn/Common_questions/What_is_a_web_server" %}

{% embed url="https://pensandonaweb.com.br/como-funciona-a-internet-e-a-world-wide-web/" %}

