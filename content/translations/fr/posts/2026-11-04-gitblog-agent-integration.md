---
id: 209a8af1-f177-418f-8f85-22717ec80741
title: >-
  Connecter Gitblog aux agents IA : automatiser la rédaction et la publication
  avec Muse
description: >-
  Découvrez comment connecter un dépôt Gitblog à Muse, configurer les accès
  GitHub et déléguer la recherche, la rédaction et la publication régulière.
date: '2026-11-04T09:00:00+09:00'
published: true
translationMode: manual
cover: /uploads/covers/gitblog-agent-integration.png
category: Manual
tags:
  - gitblog
  - 사용법
locale: fr
sourceLocale: ko
sourcePath: content/posts/2026-11-04-gitblog-agent-integration.md
sourceHash: ca2327a8f1c910fe46e9b692e4c94b60a1b587fac8d783de16da8462495f034d
translationSchemaVersion: manual-v1
translationSource: manual
translatedAt: '2026-11-04T10:25:01.665Z'
translationContentHash: a53490c3ad141943fe28411399fc13ac58fb4d3674ba5b98a71be3c6d4322d2f
---

Et si vous pouviez chaque matin lire les nouvelles qui vous intéressent et en conserver l'essentiel sur votre propre blog ? Votre assistant IA peut prendre en charge le travail, de la recherche à la rédaction et à la publication.

**Gitblog fournit des consignes et des commandes permettant aux agents IA de rédiger, vérifier et publier des articles dans votre dépôt de blog.** En donnant un accès GitHub à un agent capable de manipuler les fichiers et d'exécuter des commandes, une demande formulée dans la conversation peut aboutir à un article publié.

![Grille de cartes lumineuses présentant plusieurs applications d'agents IA](/uploads/gitblog-agent-integration/ai-agent-apps.png)

Ce guide prend Muse comme exemple pour connecter un dépôt, s'authentifier auprès de GitHub, rédiger un premier article et programmer des publications. La même méthode s'applique à Dots, Grokbot, Duet ou Openclaw si leur environnement permet l'accès au dépôt, l'exécution de commandes et les tâches planifiées. Les modalités de connexion et le périmètre automatisable dépendent des fonctions et des réglages de chaque agent.

## Confier son blog à un agent : qu'est-ce que cela signifie ?

Les articles publiés avec Gitblog restent des fichiers Markdown dans votre dépôt GitHub. L'agent les rédige et les modifie, puis prépare leur publication en suivant les consignes du dépôt.

Une seule demande peut ainsi déclencher les étapes suivantes.

1. Rechercher des informations récentes sur un sujet qui vous intéresse.
2. Vérifier les sources et écrire pour le public et dans le style de votre blog.
3. Préparer les traductions selon la méthode configurée et vérifier l'article et la compilation du site.
4. Créer un commit pour les articles dont vous avez autorisé la publication et les pousser sur GitHub.
5. Vérifier le déploiement et l'adresse réelle de l'article, puis vous informer du résultat.

La planification de l'agent permet de répéter ce travail régulièrement. **Le service de l'agent est responsable de l'exécution à l'heure prévue ; le dépôt Gitblog fournit la base pour enregistrer, vérifier et déployer les articles.**

## 1. Indiquer votre dépôt de blog à Muse

Préparez votre dépôt Gitblog. Si votre blog existe déjà, utilisez son dépôt actuel. Sinon, consultez [Premiers pas avec Gitblog](/blog/2026-11-03-introducing-gitblog/) pour en créer un avec Studio ou un modèle officiel de votre choix.

Donnez à Muse **l'adresse du dépôt de blog créé dans votre compte**, et non celle du modèle d'origine. Si le dépôt est déjà sur votre ordinateur, vous pouvez aussi choisir ce dossier comme espace de travail.

Essayez la demande ci-dessous en remplaçant `OWNER/REPO` par l'adresse de votre dépôt.

```text
https://github.com/OWNER/REPO

이 저장소를 내 블로그로 사용할 수 있게 세팅해줘.
필요하면 작업 환경에 clone하고, 저장소의 AGENTS.md를 먼저 읽어줘.
npm run author:context로 현재 설정을 확인하고,
개인 작성 지침과 공식 설정·인증·글쓰기 안내를 따라줘.

이미 운영 중인 블로그라면 기존 주소, 언어, 번역 설정을 유지해줘.
처음 설정하는 블로그라면 필요한 선택 사항을 나에게 물어봐줘.
GitHub 인증이 필요하면 로그인 또는 토큰 방식으로 안내해줘.
설정이 끝나면 글 작성과 배포에 필요한 준비 상태를 알려줘.
```

![Conversation Muse avec l'adresse du dépôt agentic-blog, une demande de configuration et les étapes de connexion GitHub et de sélection du dépôt](/uploads/gitblog-agent-integration/muse-repository-setup.png)

*Après avoir reçu votre dépôt, Muse peut vous guider pour connecter GitHub et sélectionner le dépôt auquel il aura accès.*

Le fichier `AGENTS.md` du dépôt indique à l'agent par où commencer. Les documents et commandes associés précisent l'emplacement des articles, les réglages de traduction et les vérifications. Le dépôt sert d'espace de travail, sans nécessiter une API de rédaction propre à un modèle.

## 2. Autoriser l'accès par connexion GitHub ou par jeton

Rédiger localement et publier sur GitHub sont deux étapes distinctes. Pour déléguer le déploiement, Git et GitHub CLI doivent être authentifiés dans l'environnement de l'agent.

Si un compte est déjà connecté, vérifiez et réutilisez cette authentification. Sinon, choisissez une connexion par navigateur ou un jeton d'accès personnel à permissions fines, appelé PAT, selon votre environnement.

Pour la connexion par navigateur, vous terminez vous-même la procédure GitHub indiquée par l'agent. Avec un jeton, sélectionnez votre dépôt et attribuez les permissions adaptées au travail. La configuration initiale et la publication dans un blog déjà configuré nécessitent des droits différents : suivez le [guide d'authentification GitHub](https://github.com/gitblogapp/gitblog-blog/blob/main/docs/gitblog/github-auth.md) du dépôt.

### Demander à Muse une connexion par jeton

Demandez à Muse d'utiliser un jeton généré par GitHub plutôt qu'une connexion classique. Vous pourrez obtenir les indications ci-dessous. Cet exemple connecte `elixirevo/agentic-blog` ; choisissez votre propre compte et dépôt lors de votre configuration.

![Conversation Muse en anglais expliquant la création d'un PAT GitHub à permissions fines et les droits du dépôt](/uploads/gitblog-agent-integration/muse-token-guide.png)

*Muse peut expliquer comment générer le jeton et quels droits sont nécessaires à la tâche.*

### Choisir le dépôt et les permissions sur GitHub

Sur la page de création du jeton, saisissez un nom reconnaissable et choisissez le propriétaire du dépôt sous `Resource owner`. Réglez `Repository access` sur `Only select repositories`, puis sélectionnez votre blog. L'image affiche `No expiration`, mais choisissez en pratique une date d'expiration adaptée à la durée de votre travail.

![Création d'un jeton GitHub avec un nom, un propriétaire et un accès limité au dépôt agentic-blog](/uploads/gitblog-agent-integration/github-token-repository.png)

*Limitez l'accès du jeton au dépôt de votre blog.*

Configurez ensuite les permissions nécessaires. Cet exemple de configuration initiale comprend l'écriture sur `Contents` et `Administration`. Pour simplement publier sur un blog existant, consultez les droits correspondant à cette opération dans le guide lié plus haut, sans reprendre toutes les permissions de l'image.

![Permissions du jeton : lecture et écriture pour Contents et Administration, lecture seule pour Actions et Discussions](/uploads/gitblog-agent-integration/github-token-permissions.png)

*Après avoir vérifié les permissions, créez le jeton avec `Generate token`.*

### Transmettre le jeton dans l'écran dédié de Muse

Utilisez le mode de saisie des secrets indiqué par l'agent. Ne collez pas le jeton dans la conversation, dans un article ou dans les fichiers du dépôt. Dans l'écran `Secure Login Information Storage` de Muse, vérifiez que la destination est `api.github.com`, saisissez le jeton dans le champ prévu et choisissez `Add`.

![Écran Secure Login Information Storage de Muse affichant api.github.com et le champ du jeton](/uploads/gitblog-agent-integration/muse-token-storage.png)

*L'écran dédié à la transmission du jeton GitHub. Le champ du jeton est vide sur cette capture.*

Après l'authentification, vérifiez l'accès au dépôt **depuis l'environnement où l'agent travaille réellement**.

## 3. Vérifier le processus avec un premier article

Avant de programmer des publications, testez un premier article pour vérifier que le résultat vous convient. Indiquez le public, la longueur et les exigences de sources en plus du sujet.

```text
이 블로그에 올릴 첫 글의 초안을 작성해줘.

주제: 최근 24시간의 암호화폐 시장 주요 뉴스
독자: 비트코인과 이더리움의 흐름을 이해하고 싶은 일반 독자
언어: 한국어
분량: 5분 정도에 읽을 수 있는 길이

주요 뉴스의 원문 링크와 발표 시각을 확인해줘.
가격과 변동률에는 데이터 출처와 기준 시각을 적어줘.
확인된 사실과 해석을 구분하고, 인과관계가 불분명하면 단정하지 마.
먼저 미발행 초안으로 저장하고 내가 검토할 수 있게 보여줘.
```

Lisez le brouillon : traite-t-il les nouvelles importantes pour vous ? Les explications sont-elles trop longues ou trop difficiles ? Donnez des orientations comme « commence par l'essentiel » ou « privilégie les usages concrets plutôt que les évolutions techniques ».

Vous pouvez demander à l'agent d'inscrire vos préférences durables de public, de style et de sources dans `.gitblog/user-instructions.md`. Elles serviront de référence aux prochains articles sans devoir être répétées.

Après avoir vérifié le contenu, demandez sa publication.

```text
검토한 초안을 발행해줘.
블로그의 번역 설정에 맞춰 발행을 준비하고 필요한 검증을 실행해줘.
검증을 통과하면 이번 글에 필요한 변경만 커밋하고 배포해줘.
배포가 끝나면 실제 글 주소를 확인해서 알려줘.
Gitblog 피드 반영 여부도 배포 결과와 구분해서 알려줘.
```

Vous vérifiez ainsi toute la chaîne, de la rédaction au déploiement du site en passant par GitHub. Un message confirmant le push ne suffit pas à établir que le déploiement est terminé : vérifiez aussi que l'adresse finale de l'article s'ouvre.

## 4. Demander un rapport chaque matin à 8 heures

Si le premier résultat vous convient, demandez un travail récurrent selon les mêmes critères. Précisez le fuseau horaire, la fréquence, le périmètre de recherche et l'autorisation de publication.

L'exemple suivant demande la rédaction et la publication quotidiennes d'un rapport sur le marché des cryptomonnaies. Le travail commence à 8 heures ; vous recevez le résultat après la recherche et le déploiement.

```text
이 블로그 저장소로 다음 작업을 예약해줘.

매일 오전 8시, 한국 시간 Asia/Seoul 기준으로 작업을 시작해줘.
최근 24시간의 암호화폐 시장 주요 뉴스를 리서치하고,
비트코인과 이더리움의 가격·거래량 변화와 함께 읽을 수 있는
한국어 리포트를 작성해줘.

글에는 다음 내용을 담아줘.
- 오늘 알아야 할 핵심 내용
- 주요 뉴스 3~5개와 원문 출처
- 비트코인·이더리움의 변화, 데이터 출처와 기준 시각
- 뉴스와 시장 움직임의 관련성에 대한 해석
- 다음에 확인할 일정이나 지표

발표된 사실과 해석을 구분하고, 확인되지 않은 수치나 원인을 만들지 마.
중요한 자료를 확인하지 못했다면 공개하지 말고 이유를 알려줘.

저장소의 개인 작성 지침과 공식 발행 절차를 따라줘.
이 조건을 충족하고 검증을 통과한 새 리포트는 매번 별도 승인 없이
발행해도 돼. 기존 글을 덮어쓰지 말고, 같은 날짜의 리포트가 이미
있으면 중복 발행하지 마.

배포 완료 후 실제 글 주소와 핵심 요약을 이 대화에 알려줘.
실패했다면 어느 단계에서 멈췄는지 알려줘.
예약이 등록되면 실행 주기, 시간대, 다음 실행 시각을 확인해줘.
```

Pour relire chaque article, remplacez la consigne de publication par « enregistre un brouillon non publié et ne publie qu'après ma confirmation ». Définissez l'étendue de la délégation selon votre manière de gérer le blog.

Après la demande, vérifiez que la planification a effectivement été créée. Au moment de l'exécution, l'agent doit encore avoir accès au dépôt, aux outils de recherche et à l'authentification GitHub. En local, l'environnement doit fonctionner à l'heure prévue.

## 5. Lire les articles rédigés pour vous

Une tâche régulière vous apporte la réponse du jour et une trace durable sur votre blog. Les articles s'accumulent dans le dépôt : vous pouvez ensuite les modifier, les comparer ou les utiliser pour de futurs textes.

Ce processus convient à d'autres usages que les rapports de marché.

- Résumer chaque semaine les versions et changements de projets open source suivis.
- Rassembler lectures et notes dans un journal d'apprentissage hebdomadaire.
- Rechercher les nouvelles annonces d'un domaine technique et publier une explication.

Plus vous déléguez, plus il est utile de préciser ce qui compte pour vous. Lisez les résultats et ajustez les orientations pour construire votre méthode de rédaction.

## Commencer avec Muse, puis utiliser l'agent de votre choix

L'intégration des agents à Gitblog repose sur le dépôt du blog et ses consignes. Avec Dots, Grokbot, Duet ou Openclaw comme avec Muse, commencez par fournir le dépôt si l'outil offre l'accès aux fichiers et l'exécution de commandes nécessaires. Vérifiez aussi la planification si vous souhaitez des publications régulières.

Commencez par un brouillon. Une fois vos critères établis, ajoutez la vérification et la publication, puis des exécutions régulières pour les sujets que vous voulez documenter dans la durée.

**Votre assistant IA écrit pour vous, et ces textes restent sur un blog qui vous appartient.**

## Questions et réponses

### Faut-il installer une intégration Muse spécifique dans Gitblog ?

Ici, l'agent travaille directement avec le dépôt du blog. Il lui faut l'accès aux fichiers, un environnement d'exécution de commandes et une authentification GitHub pour déployer.

### Faut-il confirmer chaque publication ?

Vous pouvez ne déléguer que les brouillons ou autoriser la publication automatique sous certaines conditions. La possibilité d'une exécution sans intervention dépend des règles d'approbation et de l'environnement de l'agent.

### Puis-je modifier les articles ou changer d'agent ?

Les articles restent des fichiers Markdown dans votre dépôt. Vous pouvez les modifier ou connecter un autre agent au même dépôt. Il faudra reconfigurer la planification et l'authentification dans le nouvel environnement.
