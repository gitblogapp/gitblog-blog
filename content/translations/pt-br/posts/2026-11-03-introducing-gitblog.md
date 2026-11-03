---
id: f2c641a8-e850-4ae0-89a1-14ee48d9a1a2
title: >-
  Introdução ao Gitblog: como manter a propriedade dos meus textos e administrar
  meu próprio blog
description: >-
  Armazene seus textos no seu repositório do GitHub, escreva com a ajuda da IA e
  conecte-se a mais leitores. Apresentamos as cinco filosofias que orientam o
  Gitblog e como começar seu blog.
date: '2026-11-03T19:00:00+09:00'
published: true
category: Manual
tags:
  - gitblog
  - 사용법
locale: pt-br
sourcePath: content/posts/2026-11-03-introducing-gitblog.md
sourceHash: 13c15d5c3b84c5fbdf606fcdc5f7c99e4a899fac4004966fc72874ddfd92c3c7
sourceLocale: ko
translationSchemaVersion: markdown-xml-v4
translationSource: deepl
translatedAt: '2026-11-03T16:21:47.936Z'
cover: /uploads/covers/introducing-gitblog-mascot.png
updated: '2026-11-04T01:19:03+09:00'
---
O que se acumula no blog não são apenas os textos. O processo de resolução de problemas, os momentos em que aprendi algo novo e as perspectivas sobre determinados temas também ficam registrados. Com o passar do tempo, esses registros se tornam um patrimônio que mostra o que me preocupava e como eu mudei.

Então, onde esse patrimônio deve ficar? Mesmo que o serviço em que eu escrevia mude ou desapareça, eu deveria poder continuar a armazená-lo e mantê-lo, não é mesmo?

**O Gitblog é um serviço que permite armazenar posts públicos e o código do blog no meu repositório do GitHub, além de escrever posts pela web ou por meio de um agente de IA para publicá-los no meu blog.** Com base na propriedade e gestão direta dos textos, adicionamos funcionalidades que facilitam a redação e a interação com os leitores.

A criação do Gitblog partiu de cinco premissas.

## 1. Os textos que escrevo devem ser de minha propriedade e eu devo poder gerenciá-los

Quanto mais tempo escrevo, mais importante se torna a certeza de que poderei sempre acessar esses textos. Acreditamos que o autor deve poder armazenar, editar e, se necessário, transferir seus registros para outro local.

Os posts públicos do Gitblog são armazenados como arquivos Markdown no seu repositório do GitHub. É possível gerenciar também os arquivos do blog, incluindo imagens, e o código-fonte. Ao baixar o repositório para o seu computador, você pode ler, editar e fazer backup dos posts localmente, além de verificar o conteúdo anterior por meio do histórico de alterações do Git.

**Mesmo que o serviço Gitblog seja descontinuado, o repositório da minha conta, as postagens armazenadas localmente e o código do blog permanecerão.** Se mantiver a hospedagem e o domínio, é possível continuar disponibilizando o blog estático publicado e, se necessário, transferir os arquivos para outra hospedagem. No entanto, os recursos de integração oferecidos pelo Gitblog, como navegação e assinaturas, dependem da operação do serviço.

É por isso que escolhemos o GitHub como base. Muitas pessoas já o utilizam, e ele oferece a infraestrutura necessária para iniciar um blog por meio de repositórios públicos e do GitHub Pages. Mesmo na versão gratuita do GitHub, é possível usar a hospedagem do Pages para repositórios públicos. O escopo e os limites de uso seguem a [política do GitHub](https://docs.github.com/en/pages/getting-started-with-github-pages/what-is-github-pages).

Não importa onde você escreva, é possível manter o original das postagens públicas sob seu controle. Esse é o primeiro princípio do Gitblog.

## 2. Deve ser um blog que permita o uso de IA

Escrever com a ajuda da IA está se tornando cada vez mais natural. Criar rascunhos a partir de anotações, organizar conteúdos complexos, refinar frases e traduzir para outros idiomas. Assim como um agente de programação lê e modifica os arquivos de um projeto, acredito que um agente que auxilia na redação também deva poder lidar diretamente com os arquivos do blog.

O repositório do Gitblog contém diretrizes e comandos de redação, tradução e verificação para referência dos agentes de IA. Ao designar o repositório do meu blog como alvo de trabalho para um agente capaz de ler e modificar arquivos locais e executar comandos, é possível redigir rascunhos e preparar a publicação nesse ambiente. Se houver as autenticações e permissões necessárias, é possível prosseguir até a distribuição.

Por exemplo, você pode fazer a seguinte solicitação:

> Leia o arquivo AGENTS.md deste repositório do blog e siga as diretrizes de redação. Escreva o texto com base nas anotações que deixei e salve-o como rascunho para que eu possa revisá-lo.

Após concluir a revisão, você pode solicitar a tradução, a verificação e a distribuição. As tarefas possíveis variam de acordo com o escopo de acesso aos arquivos e as permissões de execução de comandos do agente utilizado. O fluxo específico está descrito no [Guia de redação e tradução de blogs](https://github.com/gitblogapp/gitblog-blog/blob/main/docs/gitblog/authoring.md).

O Gitblog não obriga o uso de um modelo específico de IA para a redação. Você pode escrever diretamente na web, usar um editor com o qual esteja familiarizado ou trabalhar em conjunto com a IA. O objetivo é permitir que o autor escolha a ferramenta que melhor se adapte ao seu estilo.

## 3. Um bom texto deve poder ser descoberto independentemente do idioma e da ferramenta

Depois de publicar um texto, é preciso que alguém o descubra e o leia. Há quem busque respostas nos mecanismos de busca e quem, ao fazer perguntas a serviços de IA, encontre materiais relevantes. Há também leitores que leem em um idioma diferente do que você usa.

O Gitblog oferece uma estrutura para publicação multilíngue, pesquisa e acesso à IA, permitindo alcançar esses leitores.

Primeiro, é possível traduzir o texto original, escrito no idioma de sua preferência, para o idioma escolhido e publicá-lo. O sistema suporta a tradução automática por meio da integração com a API do DeepL ou a publicação de traduções revisadas, sejam elas feitas por pessoas ou por modelos de linguagem de grande escala (LLM). A tradução automática do DeepL requer uma chave de API específica. Caso você gerencie a tradução diretamente, o sistema oferece um procedimento para verificar se a tradução está atualizada sempre que o texto original for alterado.

Além disso, os modelos foram equipados com os seguintes elementos básicos para que os mecanismos de busca e as ferramentas de IA possam identificar o conteúdo e a fonte do texto.

- **Informações da página para pesquisa:** fornece título, descrição, URL do texto original, mapa do site e links para as páginas em cada idioma.
- **Estrutura que explica o contexto do texto:** fornece dados estruturados, como autor e data de publicação, e permite adicionar, conforme necessário, respostas-chave, fontes, perguntas e respostas.
- **Caminhos de acesso direto ao texto:** dependendo da configuração, fornece a versão em Markdown do artigo público e a lista de artigos `llms.txt`.

Trata-se de um projeto que leva em consideração a visibilidade em ambientes de IA de busca, resposta e geração — comumente chamados de SEO, AEO e GEO. O objetivo é apresentar o corpo do texto e seu contexto de forma fácil de ler. A classificação nos resultados de busca ou as citações nas respostas de IA são determinadas por cada serviço, não sendo garantidas apenas por traduções ou configurações técnicas. [Guia de pesquisa e acesso à IA](https://github.com/gitblogapp/gitblog-blog/blob/main/docs/gitblog/ai-discovery.md).

Também é possível encontrar artigos dentro do Gitblog. Os artigos dos blogs participantes do feed passam por um processo de coleta e são exibidos nas telas de exploração, como “Artigos mais recentes”, “Artigos populares” e “Tendências”. O leitor pode encontrar artigos de seu interesse e acessar o blog do autor para lê-los.

Nosso objetivo é ampliar a possibilidade de que os registros que deixamos cheguem às pessoas que precisam desse conteúdo.

## 4. A repercussão das postagens leva a conexões no GitHub

Ao ler um bom artigo, ficamos curiosos sobre o próximo texto do autor. Passamos a pesquisar que tipo de projeto essa pessoa está desenvolvendo e quais pensamentos ela está registrando.

No Gitblog, esse interesse se traduz em conexões no GitHub. **A assinatura de um blog está vinculada a uma “estrela” (Star) no repositório do GitHub, e seguir um autor está vinculado ao botão “Seguir” (Follow) na conta do GitHub.** O leitor pode reunir os posts de blogs ou autores de seu interesse, e o autor pode se conectar com os leitores também no GitHub por meio de seus registros.

Pode parecer algo trivial, mas acreditamos que essa conexão seja significativa. Isso porque os textos e pensamentos se somam à imagem que se revela por meio do código e dos projetos. Textos que explicam as decisões tomadas no projeto, o processo de resolução de problemas e o que foi aprendido tornam-se mais um canal para compreender o trabalho dessa pessoa.

O número de “Stars” ou de seguidores não determina o valor de um texto. No entanto, o fato de que um leitor que se identificou com o meu texto possa se tornar alguém que aguarda meu próximo post pode ser um motivo para continuar escrevendo regularmente.

## 5. Escrever continua sendo importante mesmo na era da IA

Escrevemos quando fazemos perguntas à IA. Explicamos o resultado desejado, organizamos as condições e, ao ler a resposta, fazemos novas perguntas. Mesmo quando a IA redige o prompt e o rascunho por nós, permanece o processo de decidir o que solicitar e quais resultados aceitar.

Escrever também é um processo de reflexão sobre os próprios pensamentos. Ao redigir frases para explicar algo, percebemos lacunas em aspectos que achávamos conhecer. Passamos a buscar fundamentos, corrigir argumentos contraditórios e conectar o contexto para que outras pessoas possam compreender.

Mesmo que a IA assuma cada vez mais tarefas, procuramos não esquecer nosso papel como seres humanos: decidir o que consideramos importante e quais ações tomar. **Não perder de vista nossos próprios pensamentos e julgamentos, mesmo em textos escritos em conjunto com a IA** — esse é o tipo de escrita que buscamos.

Espero que o Gitblog seja um espaço onde possamos continuar essa prática. Um espaço para explicar o que aprendemos com nossas próprias palavras, registrar experiências em um contexto significativo e, com o passar do tempo, reler esses textos para desenvolver nossas ideias.

Espero que a construção de bons textos se torne um processo de aprimoramento da própria inteligência.

## Começando no Gitblog

É possível começar o Gitblog no Studio da web ou criar diretamente um repositório de blog no GitHub e operá-lo no seu computador local. Vamos ver primeiro como usar o Studio.

### 1. Cadastre-se com uma conta do GitHub

Acesse o [Gitblog](https://gitblog.app/ko) e cadastre-se ou faça login com sua conta do GitHub. Após o login, acesse o Studio, que é o espaço para criar e gerenciar seu blog.

### 2. Conecte o aplicativo do GitHub e crie um blog

Seguindo as instruções do Studio, instale o aplicativo Gitblog no GitHub e conceda acesso ao repositório para gerenciar o blog. Visualize os modelos disponíveis, escolha um e, em seguida, defina o título do blog e o nome do repositório.

![Tela do Gitblog Studio (em inglês) para visualizar e selecionar modelos de blog baseados em Svelte, Astro, React e Vanilla HTML.](/uploads/introducing-gitblog/templates-en.jpg)

*Tela de seleção de modelos no Studio em inglês. Em 3 de novembro de 2026.*

Os arquivos do blog serão criados no seu repositório do GitHub. Para hospedagem, você pode usar o GitHub Pages ou conectar sua conta do Cloudflare para usar o Cloudflare Pages. Depois de concluir as configurações de implantação do método escolhido, você estará pronto para publicar posts.

### 3. Escrever e publicar um post em Markdown

Na tela de redação do Studio, digite o título, a descrição e o corpo do texto em Markdown. Também é possível fazer o upload de uma imagem de capa para a miniatura do post e de imagens para o corpo do texto.

Enquanto escreve, salve como rascunho e, após revisar o conteúdo, salve como publicado. Após salvar, verifique o andamento da compilação e da distribuição; quando a distribuição estiver concluída, você poderá ler a postagem no seu blog. Se for necessária uma tradução, basta configurar os idiomas de tradução e as formas de uso do blog para operá-lo em conjunto.

### Começando no GitHub e no seu computador

Se quiser trabalhar com um editor local ou um agente de IA, você pode escolher o modelo oficial do Gitblog de sua preferência no GitHub e começar diretamente.

1. **Crie o repositório do seu blog usando um modelo.** Na página do GitHub do modelo oficial desejado, use o modelo para criar um novo repositório público na sua conta. Será criado um repositório do blog para você gerenciar, independente do modelo original.
2. **Clone o seu repositório no seu computador local.** Execute o `git clone` usando o endereço do repositório criado e abra a pasta baixada no editor ou no agente de IA para trabalhar. Siga as instruções do modelo para instalar as ferramentas de desenvolvimento e dependências necessárias e conclua as configurações iniciais, como endereço do blog, idioma e hospedagem.
3. **Escreva e verifique o texto localmente.** Escreva um texto em Markdown no `content/posts/` e adicione imagens. Você pode editar diretamente ou solicitar ao agente que leia o `AGENTS.md` e siga as instruções de redação. Após revisar o rascunho, altere o status para “publicado” e execute o procedimento de validação fornecido pelo modelo.
4. **Envie as alterações para o GitHub e faça a distribuição.** Ao fazer o commit do texto e das imagens e enviar (push) para o branch de distribuição, o fluxo de trabalho do GitHub Actions configurado irá compilar o blog e distribuí-lo para a hospedagem selecionada. Verifique os resultados da execução do Actions e se as alterações foram refletidas na página real do blog.

Na primeira vez, você deverá preparar o ambiente de distribuição seguindo o [Guia de configuração inicial](https://github.com/gitblogapp/gitblog-blog/blob/main/docs/gitblog/setup.md) do modelo escolhido. A partir daí, você poderá continuar escrevendo seguindo o fluxo: **escrever localmente → revisar e validar → fazer commit e push → confirmar a distribuição**.

Mesmo um blog criado diretamente no GitHub pode ser gerenciado no Gitblog App, desde que você conceda acesso ao repositório e utilize o recurso de conexão com blogs existentes do Studio. Basta escolher o método mais adequado ao seu trabalho: escrever na web ou escrever localmente.

## Comece onde seus textos ficam guardados

O Gitblog busca ser um blog que armazena seus textos na sua conta, permite que você os escreva com ferramentas com as quais está acostumado e alcança leitores em diferentes idiomas e canais. Na base disso está a crença de que, por meio da escrita, é possível compreender mais profundamente os próprios pensamentos.

Não é preciso escrever um texto perfeito desde o início. Experimente registrar um fato que você descobriu hoje, uma questão sobre a qual vem refletindo há muito tempo ou um problema que você mesmo resolveu. O processo de adicionar contexto a esse registro e refiná-lo levará ao próximo texto.

**Acumule seus pensamentos em um blog que você mesmo possui e administra.**

[Começar meu blog no Gitblog](https://gitblog.app/studio)
