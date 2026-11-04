---
id: 209a8af1-f177-418f-8f85-22717ec80741
title: 'Connecting Gitblog to AI agents: automate writing and publishing with Muse'
description: >-
  Learn how to connect a Gitblog repository to Muse, configure GitHub access,
  and delegate research, writing, and scheduled publishing.
date: '2026-11-04T09:00:00+09:00'
published: true
translationMode: manual
cover: /uploads/covers/gitblog-agent-integration.png
category: Manual
tags:
  - gitblog
  - 사용법
locale: en
sourceLocale: ko
sourcePath: content/posts/2026-11-04-gitblog-agent-integration.md
sourceHash: ca2327a8f1c910fe46e9b692e4c94b60a1b587fac8d783de16da8462495f034d
translationSchemaVersion: manual-v1
translationSource: manual
translatedAt: '2026-11-04T10:23:37.772Z'
translationContentHash: 73cd8e8ed5feaa5e28ca32d4cb7aaa0b45881131d4329e77d698699b0a8af889
---

What if you could find news about your interests every morning, read it, and keep the important points on your own blog? Your AI assistant can handle the work from research through writing and publication.

**Gitblog provides instructions and commands that let AI agents write, validate, and publish posts in your blog repository.** Give an agent that can work with repository files and run commands access to GitHub, and a conversational request can lead all the way to a published post.

![A neon card grid featuring several AI agent apps](/uploads/gitblog-agent-integration/ai-agent-apps.png)

This guide uses Muse to show the flow from connecting a repository and authenticating with GitHub to writing a first post and scheduling publication. You can apply the same approach with Dots, Grokbot, Duet, or Openclaw when the environment supports repository access, command execution, and scheduled runs. Connection methods and the scope of automation depend on each agent's features and settings.

## What it means to entrust your blog to an agent

Published Gitblog posts remain Markdown files in your own GitHub repository. An agent writes and edits those files and prepares publication by following the repository's instructions.

For example, a single request can lead to the following steps.

1. Research recent material about a topic you care about.
2. Check sources and write for your blog's audience and style.
3. Prepare translations using the configured method and validate the post and build.
4. Commit posts you have authorized for publication and push them to GitHub.
5. Check deployment and the live post URL, then report back.

Connect this process to the agent's scheduling feature to repeat it regularly. **The agent service is responsible for running at the scheduled time; the Gitblog repository provides the foundation for storing, validating, and deploying posts.**

## 1. Tell Muse about your blog repository

First, prepare your own Gitblog repository. If you already run a blog, use its existing repository. Otherwise, see [Getting started with Gitblog](/blog/2026-11-03-introducing-gitblog/) and create one through Studio or an official template of your choice.

Give Muse **the URL of the blog repository created under your own account**, rather than the original template. If the repository is already on your local PC, you can also select that folder as the working directory.

Try the request below, replacing `OWNER/REPO` with your repository address.

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

![A Muse conversation with the agentic-blog repository URL, setup request, and guidance on GitHub connection and repository selection](/uploads/gitblog-agent-integration/muse-repository-setup.png)

*When you share your blog repository with Muse, it can guide you through connecting GitHub and selecting which repository it can access.*

The repository's `AGENTS.md` is the starting point that tells an agent where to begin. Linked documents and commands explain post locations, translation settings, and validation. The repository itself is the workspace; no separate writing API for a particular model is required.

## 2. Grant access through GitHub login or a token

Writing locally and publishing to GitHub are separate steps. To delegate deployment, Git and GitHub CLI authentication must be ready in the environment where the agent works.

If an account is already connected, verify and reuse that authentication. Otherwise, choose browser login or a fine-grained personal access token (PAT), depending on your environment.

For browser login, you complete the GitHub authentication flow the agent provides. For a token, select your blog repository and grant permissions appropriate to the work. Initial setup and posting to an already configured blog require different permissions; follow the repository's [GitHub authentication guide](https://github.com/gitblogapp/gitblog-blog/blob/main/docs/gitblog/github-auth.md).

### Ask Muse to connect using a token

Ask Muse to “use a token issued by GitHub instead of logging in” to receive guidance like the following. This example connects `elixirevo/agentic-blog`; select your own account and blog repository in your setup.

![An English Muse conversation explaining how to create a fine-grained GitHub PAT and configure repository permissions](/uploads/gitblog-agent-integration/muse-token-guide.png)

*Requesting a token connection gives you guidance on issuance and the permissions needed for the task.*

### Select the repository and permissions on GitHub

On GitHub's token creation page, enter a recognizable name and select the blog repository owner under `Resource owner`. Set `Repository access` to `Only select repositories` and choose your blog. The screenshot shows `No expiration`, but for actual use, set an expiration date appropriate to the duration of your work.

![GitHub token creation with a name, resource owner, and access limited to the agentic-blog repository](/uploads/gitblog-agent-integration/github-token-repository.png)

*Limit the token's repository access to your blog.*

Next, configure permissions for the work you will perform. This initial setup example includes write access to `Contents` and `Administration`. If you are only publishing posts to an existing blog, check the relevant permissions in the authentication guide linked above instead of copying every permission shown.

![GitHub token permissions with read and write access to Contents and Administration and read-only access to Actions and Discussions](/uploads/gitblog-agent-integration/github-token-permissions.png)

*After checking the required permissions, issue the token with `Generate token`.*

### Enter the token in Muse's dedicated input screen

Provide the token using the secret-input method the agent specifies. Do not paste it into chat, post content, or repository files. In Muse's `Secure Login Information Storage` screen below, check that the destination is `api.github.com`, enter the token in the dedicated field, and select `Add`.

![Muse's Secure Login Information Storage screen showing api.github.com and the token input field](/uploads/gitblog-agent-integration/muse-token-storage.png)

*The dedicated screen for supplying a GitHub token. The token field is empty in this screenshot.*

After authentication, confirm access to your repository **from the environment where the agent actually works**.

## 3. Check the writing workflow with a first post

Before scheduling publication, use one post to check that the results match your expectations. Specify the audience, length, and source requirements along with the topic to help establish the direction.

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

Read the draft to see whether it includes the news that matters to you and whether the explanation is too difficult or too long. Give feedback such as “lead with the main point” or “focus more on practical uses than technical changes.”

Ask the agent to record ongoing preferences for audience, style, and sources in `.gitblog/user-instructions.md`. This leaves guidance for future posts instead of requiring you to repeat the same instructions.

Once you have reviewed the content, request publication.

```text
검토한 초안을 발행해줘.
블로그의 번역 설정에 맞춰 발행을 준비하고 필요한 검증을 실행해줘.
검증을 통과하면 이번 글에 필요한 변경만 커밋하고 배포해줘.
배포가 끝나면 실제 글 주소를 확인해서 알려줘.
Gitblog 피드 반영 여부도 배포 결과와 구분해서 알려줘.
```

This checks the whole flow from writing through GitHub updates to deploying the site. A message saying the push completed does not mean deployment is finished; verify that the final post URL actually opens.

## 4. Request a report every morning at 8

If you like the first result, request recurring work using the same criteria. Include the time zone, frequency, research scope, and whether publication is authorized.

The example below requests a daily cryptocurrency market report and publication. At 8 a.m. the work begins; the result arrives after research and deployment are complete.

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

If you prefer to review every post, replace the publication instruction with “save an unpublished draft and publish only after I confirm.” Choose how much to delegate based on the way you want to run your blog.

After submitting the request, confirm that a schedule was actually created. At execution time, the agent must still have access to the repository, research tools, and GitHub authentication. For local execution, that environment must be running at the scheduled time.

## 5. Read the posts written for you

Recurring work gives you both that day's response and a lasting record on your own blog. Posts accumulate in your repository so you can edit them, compare them, or use them as material for later writing.

The same workflow can support more than market reports.

- Summarize releases and changes in open-source projects you follow each week.
- Compile reading material and notes into a weekly learning log.
- Research new announcements in a technical field and publish an explanatory post.

The more you delegate, the more it matters to explain what you value. Read the results and adjust the direction to develop a writing process that suits you.

## Start with Muse, then use the agent you prefer

Gitblog's agent workflow is built around the repository and its instructions. With Dots, Grokbot, Duet, or Openclaw as well as Muse, you can start by providing the repository if the tool offers the necessary file access and command execution. For scheduled publishing, also check scheduling support.

Start by requesting a single draft. Once you have established your criteria, connect validation and publication, then add recurring runs for subjects you want to record consistently.

**Your AI assistant writes for you, and the record remains on a blog you own.**

## Questions and answers

### Do I need a Muse-specific integration in Gitblog?

This approach lets the agent work directly with the blog repository. It needs access to files, an environment for executing commands, and GitHub authentication for deployment.

### Must I approve every publication?

You can delegate drafting only or authorize automatic publication under specified conditions. Whether fully unattended runs are possible depends on the agent's approval policies and execution environment.

### Can I edit posts or switch agents?

Posts remain Markdown files in your repository, so you can edit them yourself or connect another agent to the same repository. Scheduling and authentication must be configured again in the new agent environment.
