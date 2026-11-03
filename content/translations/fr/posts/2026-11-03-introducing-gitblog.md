---
id: f2c641a8-e850-4ae0-89a1-14ee48d9a1a2
title: >-
  Présentation de Gitblog : comment rester propriétaire de mes articles et gérer
  mon blog
description: >-
  Conservez vos articles dans votre dépôt GitHub, rédigez-les avec l'aide de
  l'IA et touchez un public plus large. Découvrez les cinq principes
  fondamentaux de Gitblog et comment créer votre blog.
date: '2026-11-03T19:00:00+09:00'
published: true
category: Manual
tags:
  - gitblog
  - 사용법
locale: fr
sourcePath: content/posts/2026-11-03-introducing-gitblog.md
sourceHash: 13c15d5c3b84c5fbdf606fcdc5f7c99e4a899fac4004966fc72874ddfd92c3c7
sourceLocale: ko
translationSchemaVersion: markdown-xml-v4
translationSource: deepl
translatedAt: '2026-11-03T16:21:41.851Z'
cover: /uploads/covers/introducing-gitblog-mascot.png
updated: '2026-11-04T01:19:03+09:00'
---
Ce ne sont pas seulement les articles qui s’accumulent sur un blog. Le processus de résolution d’un problème, les moments où l’on apprend quelque chose de nouveau, ainsi que le point de vue sur un sujet donné y sont également consignés. Avec le temps, ces traces deviennent un atout qui montre ce qui m’a préoccupé et comment j’ai évolué.

Alors, où ces archives devraient-elles être conservées ? Même si la plateforme sur laquelle j’écris change ou disparaît, ne devrais-je pas pouvoir continuer à les conserver et à les gérer moi-même ?

**Gitblog est un service qui permet de stocker des articles publics et le code de votre blog dans votre dépôt GitHub, et de rédiger des articles via le Web ou un agent IA pour les publier sur votre blog.** En plus de vous permettre de posséder et de gérer vous-même vos articles, nous y avons ajouté des fonctionnalités pratiques pour faciliter la rédaction et vous permettre d’entrer en contact avec vos lecteurs.

La création de Gitblog repose sur cinq principes fondamentaux.

## 1. Je dois pouvoir posséder et gérer les articles que j’ai écrits

Plus on écrit au fil du temps, plus il est important de pouvoir consulter ces articles à tout moment. Nous pensons que l’auteur doit pouvoir conserver, modifier et, si nécessaire, transférer ses archives vers un autre emplacement.

Les articles publics de Gitblog sont stockés sous forme de fichiers Markdown dans votre dépôt GitHub. Vous pouvez également gérer les fichiers de votre blog, y compris les images, ainsi que le code. En téléchargeant le dépôt sur votre ordinateur, vous pouvez lire, modifier et sauvegarder vos articles en local, et consulter l’historique des modifications via Git pour revenir à des versions antérieures.

**Même si le service Gitblog venait à disparaître, le dépôt de mon compte ainsi que les articles et le code du blog conservés localement resteraient intacts.** En conservant l’hébergement et le domaine, je peux continuer à proposer le blog statique déployé et, si nécessaire, transférer les fichiers vers un autre hébergeur. Toutefois, les fonctionnalités d’intégration proposées par Gitblog, telles que la navigation et l’abonnement, dépendent de l’exploitation du service.

C’est d’ailleurs la raison pour laquelle nous avons choisi GitHub comme base. De nombreuses personnes l’utilisent déjà, et il offre une infrastructure permettant de créer un blog via des dépôts publics et GitHub Pages. Même avec GitHub Free, vous pouvez utiliser l’hébergement Pages pour vos dépôts publics. La portée des services et les limites d’utilisation sont régies par [la politique de GitHub](https://docs.github.com/en/pages/getting-started-with-github-pages/what-is-github-pages).

Peu importe où vous rédigez vos articles, vous devez pouvoir conserver l’original de vos publications publiques entre vos mains. Tel est le premier principe de Gitblog.

## 2. Ce blog doit pouvoir s’utiliser avec l’IA

Écrire avec l’IA devient de plus en plus naturel. On crée des brouillons à partir de notes, on organise des contenus complexes, on peaufine des phrases et on traduit dans d’autres langues. Tout comme un agent de codage lit et modifie les fichiers d’un projet, nous pensons qu’un agent d’aide à la rédaction doit également pouvoir manipuler directement les fichiers du blog.

Le dépôt de Gitblog contient des instructions et des commandes de rédaction, de traduction et de vérification auxquelles les agents IA peuvent se référer. En désignant mon dépôt de blog comme cible de travail pour un agent capable de lire et de modifier des fichiers locaux et d’exécuter des commandes, je peux rédiger un brouillon et préparer la publication dans cet environnement. Si je dispose des authentifications et des autorisations nécessaires, je peux même aller jusqu’à la mise en production.

Par exemple, je peux formuler la demande suivante :

> Lis le fichier AGENTS.md de ce dépôt de blog et suis les consignes de rédaction. Rédige un article en te basant sur les notes que j’ai laissées, puis enregistre-le sous forme de brouillon afin que je puisse le relire.

Une fois la révision terminée, vous pouvez demander la traduction, la validation et la publication. Les tâches possibles varient en fonction de la portée d’accès aux fichiers et des autorisations d’exécution des commandes de l’agent utilisé. Le déroulement précis est détaillé dans le [Guide de rédaction et de traduction de blog](https://github.com/gitblogapp/gitblog-blog/blob/main/docs/gitblog/authoring.md).

Gitblog n’impose pas l’utilisation d’un modèle d’IA spécifique pour la rédaction. Vous pouvez écrire directement sur le Web, utiliser un éditeur qui vous est familier ou travailler avec l’IA. L’objectif est de permettre à l’auteur de choisir l’outil qui lui convient le mieux.

## 3. Un bon article doit pouvoir être découvert au-delà des barrières linguistiques et des outils

Une fois un article publié, il faut que quelqu’un le découvre et le lise. Certains trouvent des réponses via les moteurs de recherche, d’autres découvrent des ressources pertinentes en posant des questions à des services d’IA. Il y a également des lecteurs qui lisent dans une langue différente de celle que vous utilisez.

Gitblog fournit une infrastructure permettant de toucher ces lecteurs grâce à la publication multilingue et à l’accès via la recherche et l’IA.

Tout d’abord, vous pouvez publier la traduction d’un texte original rédigé dans la langue de votre choix vers la langue de votre choix. La plateforme prend en charge la traduction automatique via l’API DeepL, ainsi que la publication de traductions révisées par des humains ou générées par un modèle de langage (LLM). Une clé API distincte est requise pour la traduction automatique DeepL. Si vous gérez vous-même les traductions, un processus vous permet de vérifier que la traduction reste à jour lorsque le texte original est modifié.

De plus, afin que les moteurs de recherche et les outils d’IA puissent identifier le contenu et la source des articles, les modèles intègrent les éléments de base suivants :

- **Informations sur la page pour la recherche :** elles fournissent le titre, la description, l’URL du texte original, le plan du site et des liens vers les pages dans chaque langue.
- **Structure expliquant le contexte de l’article :** elle fournit des données structurées telles que l’auteur et la date de publication, et permet d’ajouter, si nécessaire, des réponses clés, des sources, ainsi que des questions et réponses.
- Accès direct au texte : en fonction des paramètres, le système fournit la version Markdown des articles publics ainsi que la liste des articles `llms.txt`.

Cette conception tient compte de la visibilité dans les environnements de recherche, de réponse et d’IA générative, communément appelés SEO, AEO et GEO. L’objectif est de présenter le corps du texte et son contexte de manière lisible. Le classement dans les résultats de recherche ou la citation dans les réponses de l’IA sont déterminés par chaque service et ne sont pas garantis par la traduction ou les paramètres techniques seuls. [Guide d’accès à la recherche et à l’IA](https://github.com/gitblogapp/gitblog-blog/blob/main/docs/gitblog/ai-discovery.md).

Il est également possible de découvrir des articles au sein même de Gitblog. Les articles des blogs participant au flux sont collectés puis affichés dans les pages d’exploration telles que « Derniers articles », « Articles populaires » ou « Tendances ». Les lecteurs peuvent ainsi trouver des articles qui les intéressent et se rendre sur le blog de l’auteur pour les lire.

Notre objectif est d’élargir les chances que les traces que nous laissons parviennent à ceux qui en ont besoin.

## 4. L’intérêt suscité par un article débouche sur des liens vers GitHub

Lorsque l’on lit un bon article, on a envie de découvrir les prochains articles de l’auteur. On cherche alors à savoir sur quel projet il travaille et quelles réflexions il partage.

Sur Gitblog, cet intérêt se traduit également par une connexion sur GitHub. **L’abonnement à un blog correspond à une « étoile » (Star) sur le dépôt GitHub correspondant, et le fait de suivre un auteur correspond à un « Follow » sur son compte GitHub.** Les lecteurs peuvent ainsi regrouper les articles des blogs ou des auteurs qui les intéressent, tandis que les auteurs peuvent, grâce à leurs publications, entrer en contact avec leurs lecteurs également sur GitHub.

Cela peut sembler anodin, mais nous pensons que ce lien est significatif. En effet, les articles et les réflexions viennent compléter l’image que l’on se fait d’une personne à travers son code et ses projets. Les articles expliquant les décisions prises dans le cadre d’un projet, le processus de résolution des problèmes ou les enseignements tirés constituent un autre moyen de comprendre le travail de cette personne.

Le nombre d’étoiles ou d’abonnés ne détermine pas la valeur d’un article. Cependant, le fait que les lecteurs qui se sont identifiés à mes écrits attendent mes prochains articles peut constituer une raison suffisante pour continuer à écrire régulièrement.

## 5. Écrire reste important, même à l’ère de l’IA

Nous écrivons lorsque nous posons des questions à l’IA. Nous expliquons le résultat souhaité, précisons les conditions, puis, après avoir lu la réponse, nous posons de nouvelles questions. Même lorsque l’IA rédige à notre place les invites et les brouillons, il nous reste à déterminer ce que nous allons demander et quels résultats nous sommes prêts à accepter.

Écrire est aussi un processus qui permet d’examiner ses propres pensées. En rédigeant des phrases pour expliquer quelque chose, on se rend compte des lacunes dans ce que l’on croyait savoir. On cherche des arguments, on corrige les affirmations contradictoires et on relie les éléments pour que d’autres puissent comprendre.

Même si l’IA prend en charge une part croissante du travail, nous ne voulons pas oublier notre rôle d’êtres humains : celui de décider de ce qui est important et des actions à mener. **Ne pas perdre de vue ses propres pensées et jugements, même dans les textes rédigés avec l’aide de l’IA**, voilà l’approche de l’écriture que nous souhaitons promouvoir.

J’espère que Gitblog sera un espace où l’on pourra poursuivre cet exercice : un espace où l’on explique ce que l’on a appris avec ses propres mots, où l’on consigne ses expériences dans des récits contextualisés, et où l’on peut relire ses textes au fil du temps pour faire évoluer sa réflexion.

Nous espérons que la constitution d’un corpus de bons textes deviendra un processus d’affinement de votre intelligence.

## Commencer avec Gitblog

Vous pouvez démarrer Gitblog depuis Studio sur le Web, ou créer directement un dépôt de blog sur GitHub puis l’exploiter depuis votre ordinateur local. Commençons par voir comment utiliser Studio.

### 1. Créer un compte GitHub

Rendez-vous sur [Gitblog](https://gitblog.app/ko) pour vous inscrire et vous connecter avec votre compte GitHub. Une fois connecté, accédez à Studio, l’espace dédié à la création et à la gestion de votre blog.

### 2. Connecter l’application GitHub et créer un blog

Suivez les instructions de Studio pour installer l’application Gitblog sur GitHub et autoriser l’accès au dépôt qui servira à gérer votre blog. Prévisualisez les modèles, choisissez-en un, puis définissez le titre de votre blog et le nom du dépôt.

![Écran permettant de prévisualiser et de sélectionner des modèles de blog basés sur Svelte, Astro, React et Vanilla HTML dans Gitblog Studio (version anglaise).](/uploads/introducing-gitblog/templates-en.jpg)

*Écran de sélection des modèles dans la version anglaise de Studio. Au 3 novembre 2026.*

Les fichiers de votre blog sont créés dans votre dépôt GitHub. Pour l’hébergement, vous pouvez utiliser GitHub Pages ou connecter votre compte Cloudflare pour utiliser Cloudflare Pages. Une fois les paramètres de déploiement de la méthode choisie configurés, vous êtes prêt à publier des articles.

### 3. Rédiger et publier un article en Markdown

Dans l’écran de rédaction de Studio, saisissez le titre, la description et le corps du texte au format Markdown. Vous pouvez également télécharger une image de couverture qui servira de vignette représentative de l’article, ainsi que des images à insérer dans le corps du texte.

Pendant la rédaction, enregistrez votre article en tant que brouillon, puis, après avoir relu le contenu, enregistrez-le en tant que publication. Une fois l’enregistrement effectué, suivez la progression de la compilation et du déploiement ; dès que le déploiement est terminé, vous pouvez consulter votre article sur votre blog. Si une traduction est nécessaire, il suffit de configurer les langues de traduction et leur mode d’utilisation pour gérer les deux simultanément.

### Commencer sur GitHub et sur votre ordinateur

Si vous souhaitez travailler avec un éditeur local ou un agent IA, vous pouvez choisir le modèle officiel Gitblog de votre choix sur GitHub et vous lancer directement.

1. **Créez le dépôt de votre blog à partir d’un modèle.** Sur la page GitHub du modèle officiel de votre choix, utilisez ce modèle pour créer un nouveau dépôt public sur votre compte. Un dépôt de blog que vous gérerez vous-même sera ainsi créé, indépendamment du modèle d’origine.
2. **Clonez votre dépôt sur votre PC local.** Exécutez `git clone` en indiquant l’adresse du dépôt créé, puis ouvrez le dossier téléchargé dans un éditeur ou un agent IA pour le modifier. Suivez les instructions du modèle pour installer les outils de développement et les dépendances nécessaires, puis effectuez les réglages initiaux (adresse du blog, langue, hébergement, etc.).
3. **Rédigez et vérifiez vos articles en local.** Rédigez un article au format Markdown dans `content/posts/` et ajoutez-y des images. Vous pouvez l’éditer vous-même ou demander à l’agent de lire `AGENTS.md` et de suivre les instructions de rédaction. Après avoir relu votre brouillon, passez-le en statut « Publié » et exécutez la procédure de validation fournie par le modèle.
4. **Publiez les modifications sur GitHub pour les déployer.** Une fois que vous avez validé (commit) l’article et les images et que vous les avez poussés (push) vers la branche de déploiement, le workflow GitHub Actions configuré génère le blog et le déploie sur l’hébergement sélectionné. Vérifiez les résultats de l’exécution des Actions et assurez-vous que les modifications apparaissent bien sur la page du blog.

La première fois, vous devrez préparer l’environnement de déploiement en suivant le [Guide de configuration initiale](https://github.com/gitblogapp/gitblog-blog/blob/main/docs/gitblog/setup.md) du modèle choisi. Par la suite, vous pourrez poursuivre la rédaction en suivant le processus suivant : **rédaction en local → révision et validation → commit et push → vérification du déploiement**.

Même si vous avez créé votre blog directement sur GitHub, vous pouvez autoriser l’accès à ce dépôt depuis l’application Gitblog et le gérer via la fonctionnalité de connexion à un blog existant de Studio. Il vous suffit de choisir la méthode qui convient le mieux à votre travail : la rédaction sur le Web ou la rédaction en local.

## Commencez là où vos articles sont conservés

Gitblog vise à offrir un blog où vous pouvez conserver vos articles sur votre compte, les rédiger avec des outils qui vous sont familiers et toucher des lecteurs dans différentes langues et par différents canaux. Cette approche repose sur la conviction que l’écriture permet de mieux comprendre ses propres pensées.

Il n’est pas nécessaire d’écrire un article parfait dès le départ. Notez simplement une information que vous venez d’apprendre aujourd’hui, une question qui vous préoccupe depuis longtemps ou un problème que vous avez résolu vous-même. Le fait d’ajouter du contexte à ces notes et de les peaufiner mènera naturellement à votre prochain article.

Construisez progressivement votre réflexion sur un blog qui vous appartient et que vous gérez vous-même.

[Créer mon blog sur Gitblog](https://gitblog.app/studio)
