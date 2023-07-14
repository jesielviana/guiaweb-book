---
description: >-
  O objetivo deste capítulo é apresentar conceitos sobre o que é desenvolvimento
  web, os papéis do desenvolvedor web e as principais ferramentas para
  construção de aplicações web.
---

# 1. Introdução ao desenvolvimento web

O desenvolvimento web refere-se ao processo de criação e manutenção de aplicações web. Envolve a utilização de diversas tecnologias, linguagens de programação, _frameworks_ e ferramentas para desenvolver e hospedar _websites_ que possam ser acessadas por meio de navegadores web.

O desenvolvimento web abrange tanto a parte de interface gráfica visual do _site,_ que possibilita a interação com o usuário(conhecida como _front-end_), quanto a parte de regras funcionais, armazenamento, processamento de dados, etc (conhecida como _back-end_).

Para o desenvolvimento do _front-end_ utiliza-se basicamente três tecnologias:

* HTML (_Hypertext Markup Language_), linguagem de marcação utilizada para estruturar e organizar o conteúdo de páginas web;
* CSS (_Cascading Style Sheets_), linguagem de estilização utilizada para definir a aparência e o layout dos elementos;
* JavaScript, linguagem de programação utilizada para adicionar interatividade e dinamismo as páginas web, permitindo a manipulação do conteúdo e a interação com o usuário via interface gráfica.

Essas três tecnologias são a base para a construção de _front-end_. A partir delas foram criadas diversas bibliotecas e _frameworks_ para facilitar e dar maior produtividade ao desenvolvimento de aplicações web. Entre as principais bibliotecas do front-end podemos citar: Bootstrap, TailwindCSS, React, Angular e Vue.js. O uso dessas bibliotecas facilita o desenvolvimento de interfaces complexas e responsivas.

Já no desenvolvimento back-end, utiliza-se linguagens de programação, como PHP, Python, Java ou JavaScript (Node.js), para construir a lógica de negócio, se comunicar com bancos de dados, gerenciar a autenticação e a segurança, entre outras funcionalidades. Assim, como no front-end foram criados diversos frameworks basedados nas tecnologias de back-end para facilitar e trazer mais produtividade ao desenvolvimento de aplicações back-end.

Entre esses frameworks podemos destacar o Lavavel (PHP), Django (Python), Spring (Java), Express (Node.js). Esses frameworks são baseados em padrões e boas práticas já consolidades pelo mercado, tornando o a construção de aplicações web mais rápidas, otimizadas e mais fáceis de manter. Além disso, os frameworks já trazem funcionalidades de integração com APIs (Application Programming Interfaces), que permitem a comunicação e o compartilhamento de dados entre diferentes sistemas e serviços.

Diante disso, podemos concluir que o objetivo principal do desenvolvimento web é criar sites e aplicações estáveis e seguras que ofereçam uma experiência rica e interativa aos usuários, atendendo às necessidades e demandas do mundo digital.

### 1.1 O papel do desenvolvedor web

O profissional que atua construindo aplicações web é o desenvolvedor web, esse profissional pode atuar no _front-end, back-end_ ou em ambos. No mercado existe três perfis de desenvolvedores web:

* Desenvolvedor _front-end_ - responsável por construir a parte visual das aplicações web. Isso envolve a codificação de interface gráfica utilizando HTML, CSS e JavaScript.
* Desenvolvedor _back-end_ - responsável pela implementação da lógica de negócio e funcionalidades do lado do servidor (parte da aplicação que não é visível ao usuário), tais como processar e armazenar dados, gerenciar a autenticação de usuários, entre outras tarefas. Para isso utiliza-se linguagens de programação como PHP, Python, Java ou JavaScript.
* Desenvolvedor _full stack_ - é o profissional que atua no _front-end_ e _back-end_.

Quem está entrando no mundo de desenvolvimento web pode seguir um desses perfis acima, ou seja, você pode estudar e se especializar em front-end ou back-end e ser responsável por partes específicas de uma aplicação ou se preparar para ter um perfil mais abrangente e atuar em ambos.

Não existe uma opção correta para iniciante, nem uma mais fácil, o que eu recomendo é que procure conhecer os requisitos e características de cada perfil e escolha um de acordo com sua afinidade ou oportunidade de trabalho.

No decorrer deste livro vamos nos aprofundar mais sobre cada uma das áreas do desenvolvimento web e suas tecnologias. Já na próxima seção vamos apresentar as ferramentas que todo desenvolvedor web deve conhecer.

### 1.2 Ferramentas do desenvolvedor web

Em qualquer área atuação sempre há um conjunto de ferramentas que são essenciais para auxiliar o profissional para realização do seu trabalho. No desenvolvimento web não é diferente, para a construção de uma página web ou uma API (Application Programming Interface) o(a) desenvolvedor(a) precisa utilizar um conjunto de ferramentas físicas (hardware) e virtuais (softwares).

Diante disso, o objetivo desta seção é descrever um conjunto de ferramentas virtuais essencias para o desenvolvedor web. O conhecimento e domínio dessas ferramentas impactam na produtividade e qualidade do trabalho do(a) desenvolvedor(a).

Importante destacar que o foco é descrever o tipo/categoria da ferramenta ao invés de um software específico, claro que para cada categoria de ferramenta descrito eu citarei alguns softwares específicos, priorizando os open-source. A seguir vamos falar sobre ferramentas para escrita de código, armazenamento e controle de versão e disponibilização de aplicações online.

#### 1.2.1 Escrita do código-fonte

Assim como tem os editores de textos para escrita de documentos tais como _Microsoft Office_ e _Google Docs_. Temos os editores de texto específicos para escrita de código-fonte, são os editores utilizados pelos desenvolvedores para escrita do HTML, CSS, Javascript, etc.

Os editores de textos mais simples para desenvolvedores são conhecidos como editor de código-fonte. Também existem o editores que são chamados de IDE _(Integrated Development Environment)_, que além de editor de código-fonte fornece uma plataforma completa para desenvolvimento, composto por um conjunto de recursos que possibilita a escrita e teste do código, depuração e integração com diversas outras ferramentas.

Editor de código ou IDE são ferramentas essenciais para a escrita de código e desenvolvimento de software, conhecer os atalhos e funcionalidades disponíveis é importante para aumento da produtividade e resolução de problemas por meio de ‘debug’ e recursos que auxiliam o desenvolvedor durante o processo de escrita e sincronização de código e implantação do software.

A escolha do editor pode variar de acordo com a linguagem de programação a ser utilizada. Atualmente um dos editores mais utilizado é o Visual Studio Code ([VS Code](https://code.visualstudio.com/)), que é _open-source_ desenvolvido pela Microsoft.

Para iniciar no desenvolvimento web eu recomendo o [VS Code](https://code.visualstudio.com/), fácil de instalar e já vem com todos os recursos necessários para iniciar no desenvolvimento, além disso, possui um _marketplace_ de extensões com muitas opções e suporte a quase todas as linguagens de programação e _frameworks_ do mercado. No entanto, existe diversas opções no mercado, tanto IDEs gratuitas quanto pagas, cabe a cada pessoa escolher aquela que mais preencha suas necessidades.

#### 1.2.2 Armazenamento de código e controle de versão

A construção de software é realizado em partes, de forma iterativa, cada hora/dia você adiciona mais um pouco de código, mais uma funcionalidade, que às vezes é feita de forma individual, mas em sua grande maioria é realizado em equipe, com a colaboração de vários desenvolvedores, trabalhando em um mesmo projetos de locais e horários diferentes uns dos outros;

Armazenar o código-fonte de um software no seu computador pessoal é ruim e perigoso, se está só na sua máquina não tem como outras pessoas colaborarem, sua máquina pode queimar o HD e você perderá todo código.

Além disso, surge existem outras necessidades inerentes ao desenvolvimento de software moderno:

* Como manter o código seguro?
* Como manter um histórico de modificações do software, de um arquivo?
* Como juntar o código de diversos programadores em um mesmo projeto? E se mais de um programador alterar um mesmo arquivo?
* Como separara o código-fonte das versões de produção e de desenvolvimento?
* Como gerenciar as versões de um software?

A solução para as necessidades citadas acima está na utilização de ferramentas de controle de versão. Dentre as diversas ferramentas existentes, [Git](https://github.com/git/git) se tornou a mais popular e a que melhor resolve os problemas de armazenamento de código e controle de verões.

Git é um sistema open-source de controle de versão que permite integrar as modificações de diversos colaboradores em um única base de código, fazendo o controle de modificações e conflitos. Além disso, cria todo histórico de alterações no código do projeto, permitindo facilmente voltar para qualquer ponto para saber como o código estava naquele momento. Git é o sistema de controle de versão mais utilizado pelos desenvolvedores. Foi desenvolvido em 2005 por Linus Torvalds, o famoso criador do kernel do sistema operacional Linux.

Para utilização do Git é necessário fazer sua instalação no seu computador, geralmente os computadores Linux e Mac já vem com ele instalado. Caso seu computador não tenha o Git instalado instale seguindo as instruções desse link: [https://git-scm.com/downloads](https://git-scm.com/downloads).

Com o Git instalado no seu computador já é possível utilizá-lo para armazenamento do código e controle de versão, porém o armazenamento e controle de versão local não resolve todos os problemas citados anteriormente, tais como colaboração e segurança em caso de danificação do seu computador. Para isso, costumamos utilizar plataformas de Git online, que implementam todos os recursos do Git na nuvem (cloud) de forma segura e disponível. Existem várias opções de Git online, sendo o GitHub a mais utilizadas, principalmente para armazenar projetos open-source.

GitHub é uma plataforma de hospedagem de código (repositórios Git) para controle de versão e colaboração. Ele permite que você e outras pessoas trabalhem juntos em projetos de qualquer lugar. Além de servir como hospedagem de código, o GitHub possui muitas recursos e integrações com serviços que auxiliam no gerenciamento do projeto, execução de testes e implantação de forma automatizada.

Para saber como utiliziar Git e GitHub veja o capítulo X.

#### 1.2.3 Disponibilizando de aplicação online

A forma mais prática e fácil de disponibilizar uma aplicação Web online é colocando-a em uma plataforma de nuvem (_cloud_). Portanto, é importante que qualquer desenvolvedor conheça algumas dessas plataformas para disponibilizar suas aplicações. Além disso, quase todas as empresas utilizam essas plataformas para disponibilização de suas aplicações e serviços online, sendo um requisito básico para qualquer desenvolvedor conhecer essas plataformas.

Abaixo é listada algumas dessas plataformas e suas principais características.

* [Netlify](https://www.netlify.com/) - plataforma de computação em nuvem que oferece hospedagem e serviços de back-end sem servidor (_serverless_) para aplicativos da web e sites estáticos. Recomendo para a implantação de sites estáticos e aplicações de front-end. Simples de utilizar e performática, com uma ótima integração com GitHub.
* [Vercel](https://vercel.com/) - plataforma de computação em nuvem que oferece hospedagem e serviços de back-end sem servidor (_serverless_) para aplicativos da web e sites estáticos. Recomendo para a implantação de aplicações de front-end e back-end que usam javascript. Simples de utilizar e performática, com uma ótima integração com GitHub.
* [GitHub Pages](https://pages.github.com/) - plataforma do próprio GitHub para hospedagem de sites estáticos e aplicações de front-ed a partir de repositórios do GitHub.

Todas as plataformas listadas acima possuem um plano de utilização grátis, que atende as necessidades de quem está iniciando, ideal para projetos acadêmicos, aplicações de portfólio, testes de aplicativos, etc. Para utilização dessas plataformas basta fazer seu cadastro e seguir o guia do iniciante disponibilizado por cada uma delas.

#### 1.3 Conclusão

Em qualquer área atuação sempre há um conjunto de ferramentas que são essenciais para auxiliar o profissional para realização do seu trabalho. No desenvolvimento de software para web não é diferente, para a construção de uma página web ou uma API é essencial o uso de ferramentas que apoiam o desenvolvimento e implantação dessas aplicações, principalmente aquelas que promovem à produtividade e colaboração.

Se você está iniciando ou quer iniciar na carreira de desenvolvedor web recomendo fortemente que você estude e domine pelo menos uma ferramenta de cada uma das categorias citadas acima. Escolhas suas ferramentas e domine-as. z

> **O conhecimento de Git é essencial e obrigatório para todo desenvolvedor de software.** Use sempre, mesmo naqueles projetos pessoais e atividades acadêmicas.
