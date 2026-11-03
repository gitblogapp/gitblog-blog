---
id: f2c641a8-e850-4ae0-89a1-14ee48d9a1a2
title: >-
  Introdução ao Gitblog: como manter a propriedade dos meus artigos e gerir o
  meu blogue
description: >-
  Armazene os seus artigos no seu repositório do GitHub, escreva com a ajuda da
  IA e alcance mais leitores. Apresentamos as cinco filosofias que orientam o
  Gitblog e explicamos como começar o seu blogue.
date: '2026-11-03T19:00:00+09:00'
published: false
category: Manual
tags:
  - gitblog
  - 사용법
locale: pt
sourcePath: content/posts/2026-11-03-introducing-gitblog.md
sourceHash: ae6300517c6dcbbba87b7dfd95feecc0119ced0b194d83b9c6de02c9e4e0f45b
sourceLocale: ko
translationSchemaVersion: markdown-xml-v4
translationSource: deepl
translatedAt: '2026-11-03T16:09:53.565Z'
updated: '2026-11-04T00:40:50+09:00'
---
O que fica registado num blogue não são apenas os artigos. Ficam também registados o processo de resolução de problemas, os momentos em que aprendi algo novo e a minha perspetiva sobre determinados temas. Com o passar do tempo, esses registos tornam-se um património que mostra o que me preocupava e como evoluí.

Então, onde é que este património deve ficar guardado? Mesmo que o serviço onde escrevia mude ou desapareça, não deveria ser possível continuar a guardá-lo e a geri-lo?

**O Gitblog é um serviço que permite guardar publicações públicas e o código do blogue no meu repositório do GitHub, bem como escrever artigos através da Web ou de um agente de IA para os publicar no meu blogue.** Com base na posse e gestão diretas dos artigos, adicionámos funcionalidades que facilitam a escrita e a interação com os leitores.

A criação do Gitblog partiu de cinco princípios.

## 1. Devo poder possuir e gerir os textos que escrevo

Quanto mais tempo se escreve, mais importante se torna a certeza de que se poderá continuar a consultar esses textos. Acreditamos que o autor deve poder guardar, editar e, se necessário, transferir os seus registos para outro local.

Os artigos do Gitblog acessíveis ao público são guardados no meu repositório do GitHub como ficheiros Markdown. Também é possível gerir em conjunto os ficheiros do blogue, incluindo imagens, e o código. Ao descarregar o repositório para o meu computador, posso ler, editar e fazer cópias de segurança dos artigos localmente, bem como consultar o conteúdo anterior através do histórico de alterações do Git.

**Mesmo que o serviço Gitblog deixe de existir, o repositório da minha conta, os artigos guardados localmente e o código do blogue permanecerão.** Se mantiver a hospedagem e o domínio, poderá continuar a disponibilizar o blogue estático publicado e, se necessário, transferir os ficheiros para outra hospedagem. No entanto, as funcionalidades de integração fornecidas pelo Gitblog, como a navegação e as subscrições, dependem da operação do serviço.

É por isso que optámos por uma base no GitHub. Muitas pessoas já o utilizam e ele fornece uma base para começar um blogue através de repositórios públicos e do GitHub Pages. Mesmo na versão gratuita do GitHub (GitHub Free), é possível utilizar a hospedagem do Pages para repositórios públicos. O âmbito de cobertura e os limites de utilização seguem as [políticas do GitHub](https://docs.github.com/en/pages/getting-started-with-github-pages/what-is-github-pages).

Independentemente de onde se escreva, poder manter o original dos artigos públicos nas nossas mãos. Este é o primeiro princípio do Gitblog.

## 2. Deve ser um blogue onde também se possa utilizar IA

Escrever com a ajuda da IA está a tornar-se cada vez mais natural. Criar rascunhos a partir de notas, organizar conteúdos complexos, aperfeiçoar frases e traduzir para outras línguas. Tal como um agente de programação lê e modifica os ficheiros de um projeto, consideramos que um agente de apoio à escrita também deve poder lidar diretamente com os ficheiros do blogue.

O repositório do blogue do Gitblog inclui diretrizes e comandos de redação, tradução e verificação que os agentes de IA podem consultar. Se designar o repositório do meu blogue como alvo de trabalho para um agente capaz de ler e modificar ficheiros locais e executar comandos, é possível redigir rascunhos e preparar a publicação nesse ambiente. Se dispuser das credenciais e autorizações necessárias, é possível avançar até à publicação.

Por exemplo, pode fazer o seguinte pedido:

> Lê o ficheiro AGENTS.md deste repositório do blogue e segue as orientações de redação. Escreve o artigo com base nas notas que deixei e guarda-o como rascunho para que eu o possa rever.

Após concluir a revisão, pode solicitar a tradução, a verificação e a publicação. As tarefas possíveis variam consoante o âmbito de acesso aos ficheiros e as autorizações de execução de comandos do agente utilizado. O fluxo específico está descrito no [Guia de redação e tradução de blogs](https://github.com/gitblogapp/gitblog-blog/blob/main/docs/gitblog/authoring.md).

O Gitblog não obriga a que os artigos sejam confiados a um modelo específico de IA. Pode escrever diretamente na Web, utilizar um editor com o qual esteja familiarizado ou trabalhar em conjunto com a IA. O objetivo é permitir que o autor escolha a ferramenta que melhor se adapte ao seu método de trabalho.

## 3. Um bom texto deve poder ser descoberto para além da língua e das ferramentas

Depois de publicar um artigo, é necessário que alguém o descubra e o leia. Há quem procure respostas nos motores de busca e quem, ao fazer perguntas a serviços de IA, encontre material relevante. Há também leitores que lêem em línguas diferentes daquela que utilizamos.

O Gitblog oferece uma estrutura que permite chegar a estes leitores, com publicação multilingue e acesso a funcionalidades de pesquisa e IA.

Em primeiro lugar, é possível publicar o texto original, escrito no idioma com que se sente mais à vontade, traduzido para o idioma selecionado. O sistema suporta a tradução automática através da integração com a API do DeepL, bem como a publicação de traduções revistas por pessoas ou por modelos de linguagem de grande escala (LLM). A tradução automática do DeepL requer uma chave API específica. Caso opte por gerir a tradução diretamente, o sistema disponibiliza um procedimento para verificar se a tradução está atualizada sempre que o texto original for alterado.

Além disso, os modelos incluem os seguintes elementos básicos para que os motores de busca e as ferramentas de IA possam identificar o conteúdo e a fonte dos textos.

- **Informações da página para pesquisa:** fornece o título, a descrição, o endereço do texto original, o mapa do site e ligações para as páginas em cada idioma.
- **Estrutura que explica o contexto do artigo:** fornece dados estruturados, como o autor e a data de publicação, e permite adicionar, conforme necessário, respostas-chave, fontes, perguntas e respostas.
- **Caminhos de acesso direto ao texto:** consoante as definições, disponibiliza a versão Markdown dos artigos públicos e a lista de artigos `llms.txt`.

Trata-se de um projeto que tem em conta a visibilidade em ambientes de IA de pesquisa, resposta e geração, frequentemente designados por SEO, AEO e GEO. O objetivo é disponibilizar o corpo do texto e o seu contexto de forma fácil de ler. A classificação nos resultados de pesquisa ou as citações nas respostas da IA são determinadas por cada serviço, não sendo garantidas apenas pela tradução ou por configurações técnicas. [Guia de pesquisa e acesso à IA](https://github.com/gitblogapp/gitblog-blog/blob/main/docs/gitblog/ai-discovery.md).

Também é possível descobrir artigos no Gitblog. Os artigos dos blogues que participam no feed são recolhidos e refletidos nas páginas de exploração, tais como «Artigos mais recentes», «Artigos populares» e «Tendências». O leitor pode encontrar artigos do seu interesse e aceder ao blogue do autor para os ler.

O que pretendemos é ampliar a possibilidade de que os registos que deixamos cheguem às pessoas que precisam desse conteúdo.

## 4. A simpatia pelo artigo traduz-se numa ligação ao GitHub

Quando lemos um bom artigo, ficamos curiosos em relação ao próximo artigo do autor. Passamos a procurar saber que tipo de projetos essa pessoa está a desenvolver e que tipo de pensamentos está a registar.

No Gitblog, esse interesse traduz-se também numa ligação ao GitHub. **A subscrição de um blogue está associada a uma «estrela» (Star) no repositório correspondente do GitHub, e seguir um autor está associado à função «Seguir» (Follow) na conta do GitHub.** O leitor pode reunir os artigos de blogues ou autores que lhe interessam, e o autor pode estabelecer uma ligação com os leitores também no GitHub através dos seus registos.

Pode parecer insignificante, mas acreditamos que esta ligação é significativa. Isto porque aos aspetos revelados através do código e dos projetos se juntam os textos e as reflexões. Os textos que explicam as decisões tomadas num projeto, o processo de resolução de problemas e o que se aprendeu tornam-se mais um canal para compreender o trabalho dessa pessoa.

O número de «Star» ou de seguidores não determina o valor de um texto. No entanto, o facto de um leitor que se identificou com o meu texto poder vir a tornar-se alguém que aguarda o meu próximo texto pode ser uma razão para escrever de forma consistente.

## 5. Escrever continua a ser importante, mesmo na era da IA

Escrevemos quando fazemos perguntas à IA. Explicamos o resultado pretendido, organizamos as condições e, ao ler a resposta, voltamos a fazer perguntas. Mesmo quando a IA redige o prompt e o rascunho por nós, permanece o processo de decidir o que solicitar e que resultados aceitar.

Escrever é também um processo de reflexão sobre os nossos próprios pensamentos. Ao escrever frases para explicar algo, percebemos lacunas em aspetos que pensávamos conhecer. Procuramos fundamentos, corrigimos argumentos contraditórios e estabelecemos ligações contextuais para que outras pessoas possam compreender.

Mesmo que a IA assuma cada vez mais tarefas, procuramos não esquecer o nosso papel como seres humanos: o de decidir o que consideramos importante e quais as ações a tomar. **Não perder de vista os nossos próprios pensamentos e julgamentos, mesmo nos textos escritos em conjunto com a IA** — é esse o tipo de escrita a que aspiramos.

Espero que o Gitblog seja um espaço onde possamos continuar a praticar isso. Um espaço onde possamos explicar o que aprendemos com as nossas próprias palavras, registar as nossas experiências num contexto e, com o passar do tempo, relê-las para desenvolver as nossas ideias.

Espero que a tarefa de acumular bons textos se torne um processo de aperfeiçoamento da nossa própria inteligência.

## Começar a usar o Gitblog

O Gitblog pode ser iniciado no Studio da Web ou pode criar diretamente um repositório de blogue no GitHub e geri-lo no seu computador local. Vamos começar por ver como utilizar o Studio.

### 1. Registar-se com uma conta do GitHub

Aceda ao [Gitblog](https://gitblog.app/ko) e registe-se ou inicie sessão com a sua conta do GitHub. Após iniciar sessão, aceda ao Studio, o espaço onde pode criar e gerir o seu blogue.

### 2. Ligar a aplicação do GitHub e criar um blogue

Seguindo as instruções do Studio, instale a aplicação Gitblog no GitHub e autorize o acesso ao repositório onde irá gerir o blogue. Visualize os modelos disponíveis, escolha um e, em seguida, defina o título do blogue e o nome do repositório.

![Ecrã do Gitblog Studio (em inglês) onde é possível pré-visualizar e selecionar modelos de blogue baseados em Svelte, Astro, React e Vanilla HTML.](/uploads/introducing-gitblog/templates-en.jpg)

*Ecrã de seleção de modelos no Studio em inglês. A partir de 3 de novembro de 2026.*

Os ficheiros do blogue são criados no meu repositório do GitHub. Para o alojamento, pode utilizar o GitHub Pages ou ligar a minha conta do Cloudflare para utilizar o Cloudflare Pages. Depois de concluir as configurações de publicação do método escolhido, estará pronto para publicar artigos.

### 3. Escrever e publicar um artigo em Markdown

Na tela de edição de artigos do Studio, escreva o título, a descrição e o corpo do texto em Markdown. Também é possível carregar uma imagem de capa para a miniatura que representa o artigo, bem como imagens para o corpo do texto.

Enquanto escreve, guarde como rascunho e, depois de rever o conteúdo, guarde como publicado. Após guardar, verifique o progresso da compilação e da distribuição e, quando a distribuição estiver concluída, poderá ler o artigo no seu blogue. Se for necessária uma tradução, basta definir o idioma de tradução do blogue e a forma de utilização para o gerir em simultâneo.

### Começar no GitHub e no computador local

Se pretender trabalhar com um editor local ou um agente de IA, pode escolher o modelo oficial do Gitblog que desejar no GitHub e começar diretamente.

1. **Crie o repositório do seu blogue a partir de um modelo.** Na página do GitHub do modelo oficial que desejar, utilize o modelo para criar um novo repositório público na sua conta. Será criado um repositório do blogue que irá gerir, independente do modelo original.
2. **Clone o seu repositório para o computador local.** Execute o `git clone` utilizando o endereço do repositório criado e abra a pasta descarregada num editor ou num agente de IA para trabalhar. Siga as instruções do modelo para instalar as ferramentas de desenvolvimento e dependências necessárias e conclua as configurações iniciais, como o endereço do blogue, o idioma e o alojamento.
3. **Escreva e verifique o artigo localmente.** Escreva um artigo em Markdown no `content/posts/` e adicione imagens. Pode editar diretamente ou solicitar ao agente que leia o `AGENTS.md` e siga as instruções de redação. Após rever o rascunho, altere o estado para «publicado» e execute o procedimento de validação fornecido pelo modelo.
4. **Carregue as alterações no GitHub e efetue a distribuição.** Ao fazer o commit do texto e das imagens e enviar (push) para o ramo de distribuição, o fluxo de trabalho do GitHub Actions configurado irá compilar o blogue e distribuí-lo para a hospedagem selecionada. Verifique os resultados da execução do Actions e se as alterações foram refletidas na página real do blogue.

Na primeira vez, terá de preparar o ambiente de distribuição seguindo o [Guia de configuração inicial](https://github.com/gitblogapp/gitblog-blog/blob/main/docs/gitblog/setup.md) do modelo selecionado. Posteriormente, poderá continuar a escrever seguindo o fluxo **Escrever localmente → Rever e validar → Fazer commit e push → Confirmar a distribuição**.

Mesmo que tenha criado o blogue diretamente no GitHub, pode permitir que a aplicação Gitblog aceda a esse repositório e geri-lo através da funcionalidade de ligação a blogues existentes do Studio. Basta escolher o método que melhor se adequar ao seu trabalho: escrever na Web ou escrever localmente.

## Comece por um local onde os seus textos fiquem guardados

O Gitblog visa ser um blogue onde pode guardar os seus textos na sua conta, escrever com ferramentas com as quais está familiarizado e alcançar leitores em diferentes idiomas e canais. Na base disso está a convicção de que, através da escrita, é possível compreender mais profundamente os seus próprios pensamentos.

Não é preciso escrever um texto perfeito desde o início. Experimente registar um facto que tenha descoberto hoje, uma questão sobre a qual tenha refletido durante muito tempo ou um problema que tenha resolvido por si próprio. O processo de acrescentar contexto a esse registo e de o aperfeiçoar conduzirá ao próximo texto.

**No blogue que possui e gere, vá acumulando as suas ideias.**

[Começar o meu blogue no Gitblog](https://gitblog.app/studio)
