---
id: f2c641a8-e850-4ae0-89a1-14ee48d9a1a2
title: >-
  Einführung in Gitblog: So behältst du die Kontrolle über deine Beiträge und
  betreibst deinen eigenen Blog.
description: >-
  Speichern Sie Ihre Beiträge in Ihrem GitHub-Repository, schreiben Sie
  gemeinsam mit KI und erreichen Sie mehr Leser. Wir stellen Ihnen die fünf
  Grundsätze von Gitblog vor und zeigen Ihnen, wie Sie einen Blog starten
  können.
date: '2026-11-03T19:00:00+09:00'
published: true
tts: true
ttsVoice: ''
category: Menual
tags:
  - gitblog
  - 사용법
locale: de
sourcePath: content/posts/2026-11-03-introducing-gitblog.md
sourceHash: 873a10320749706aac03e61566ba2deb89215d2bbb07b613dbfd412af47adf4a
sourceLocale: ko
translationSchemaVersion: markdown-xml-v4
translationSource: deepl
translatedAt: '2026-11-04T07:53:30.771Z'
cover: /uploads/covers/introducing-gitblog-mascot.png
updated: '2026-11-04T07:52:36.588Z'
---
In einem Blog sammeln sich nicht nur Beiträge an. Auch der Prozess der Problemlösung, der Moment, in dem man etwas Neues gelernt hat, und die Sichtweise auf ein bestimmtes Thema bleiben darin erhalten. Mit der Zeit werden diese Aufzeichnungen zu einem wertvollen Schatz, der zeigt, worüber ich nachgedacht habe und wie ich mich verändert habe.

Wo sollten diese Aufzeichnungen also aufbewahrt werden? Selbst wenn sich der Dienst, auf dem ich schreibe, ändert oder verschwindet, sollte ich sie doch weiterhin speichern und verwalten können, oder?

**Gitblog ist ein Dienst, mit dem man öffentliche Beiträge und den Blog-Code in seinem GitHub-Repository speichern und Beiträge über das Web oder einen KI-Agenten verfassen und auf dem eigenen Blog veröffentlichen kann.** Auf der Grundlage, dass man selbst Eigentümer seiner Beiträge ist und diese verwaltet, wurden Funktionen für bequemes Schreiben und die Ansprache von Lesern hinzugefügt.

Die Entwicklung von Gitblog basiert auf fünf Grundgedanken.

## 1. Ich sollte Eigentümer meiner Beiträge sein und diese selbst verwalten können

Je länger man Beiträge schreibt, desto wichtiger wird die Gewissheit, dass man diese jederzeit wieder aufrufen kann. Wir sind der Meinung, dass Autoren ihre eigenen Aufzeichnungen selbst speichern, bearbeiten und bei Bedarf an einen anderen Ort verschieben können sollten.

Die öffentlich zugänglichen Beiträge von Gitblog werden als Markdown-Dateien in meinem GitHub-Repository gespeichert. Auch Blog-Dateien, einschließlich Bilder, und Code lassen sich gemeinsam verwalten. Wenn ich das Repository auf meinen PC herunterlade, kann ich die Beiträge lokal lesen, bearbeiten und sichern sowie über den Änderungsverlauf von Git frühere Versionen einsehen.

Selbst wenn der Gitblog-Dienst eingestellt wird, bleiben das Repository meines Kontos sowie die lokal gespeicherten Beiträge und der Blog-Code erhalten. Solange Hosting und Domain aufrechterhalten werden, kann das bereitgestellte statische Blog weiterhin angeboten werden, und bei Bedarf lassen sich die Dateien auf einen anderen Hosting-Anbieter übertragen. Allerdings hängen die von Gitblog angebotenen integrierten Funktionen wie die Suche und das Abonnieren vom Betrieb des Dienstes ab.

Dies ist auch der Grund, warum wir uns für eine Lösung auf GitHub-Basis entschieden haben. Viele Nutzer verwenden GitHub bereits, und es bietet die Grundlage, um über öffentliche Repositorys und GitHub Pages einen Blog zu starten. Auch mit GitHub Free können Sie das Pages-Hosting für öffentliche Repositorys nutzen. Der Umfang des Angebots und die Nutzungsbeschränkungen richten sich nach den [Richtlinien von GitHub](https://docs.github.com/en/pages/getting-started-with-github-pages/what-is-github-pages).

Egal, wo man einen Beitrag verfasst – man soll immer die Kontrolle über das Original des öffentlichen Beitrags behalten. Das ist das oberste Prinzip von Gitblog.

## 2. Es muss ein Blog sein, der auch KI nutzen kann

Das Schreiben mit KI wird immer selbstverständlicher. Man erstellt Entwürfe aus Notizen, strukturiert komplexe Inhalte, feilt an Sätzen und übersetzt in andere Sprachen. So wie Programmier-Agenten die Dateien eines Projekts lesen und bearbeiten, sollten auch Agenten, die beim Schreiben helfen, direkt mit den Dateien des Blogs arbeiten können.

Das Blog-Repository von Gitblog enthält Anleitungen und Befehle zum Verfassen, Übersetzen und Überprüfen, auf die KI-Agenten zurückgreifen können. Wenn ich mein Blog-Repository als Arbeitsobjekt für einen Agenten festlege, der lokale Dateien lesen, bearbeiten und Befehle ausführen kann, kann ich in dieser Umgebung Entwürfe erstellen und die Veröffentlichung vorbereiten. Sofern die erforderlichen Authentifizierungen und Berechtigungen vorliegen, kann dies sogar bis zur Veröffentlichung führen.

Beispielsweise könnte ich folgende Anfrage stellen:

> Lies die Datei „AGENTS.md“ in diesem Blog-Repository und befolge die Richtlinien zum Verfassen von Beiträgen. Verfasse einen Beitrag auf der Grundlage meiner Notizen und speichere ihn als Entwurf, damit ich ihn überprüfen kann.

Nach Abschluss der Überprüfung können Sie anschließend die Übersetzung, Überprüfung und Veröffentlichung anfordern. Die möglichen Aufgaben hängen vom Dateizugriffsbereich und den Befehlsausführungsberechtigungen des verwendeten Agenten ab. Der konkrete Ablauf ist in der [Anleitung zum Verfassen und Übersetzen von Blogbeiträgen](https://github.com/gitblogapp/gitblog-blog/blob/main/docs/gitblog/authoring.md) zusammengefasst.

Gitblog schreibt nicht vor, dass Beiträge mit einem bestimmten KI-Modell erstellt werden müssen. Du kannst direkt im Web schreiben, einen vertrauten Editor verwenden oder mit KI zusammenarbeiten. Unser Ziel ist es, dass Autoren die Werkzeuge wählen können, die zu ihrer Arbeitsweise passen.

## 3. Gute Beiträge müssen über Sprach- und Toolgrenzen hinweg entdeckt werden können

Nachdem ein Beitrag veröffentlicht wurde, muss er von jemandem entdeckt und gelesen werden. Manche suchen in Suchmaschinen nach Antworten, andere stoßen durch Fragen an KI-Dienste auf relevante Inhalte. Es gibt auch Leser, die eine andere Sprache sprechen als die, in der der Beitrag verfasst wurde.

Gitblog bietet eine Struktur für mehrsprachige Veröffentlichungen sowie für die Suche und den Zugriff über KI, um diese Leser zu erreichen.

Zunächst können Sie den Originaltext, den Sie in der Ihnen vertrauten Sprache verfasst haben, in die gewünschte Sprache übersetzen und veröffentlichen. Es wird sowohl die automatische Übersetzung über die DeepL-API als auch die Überprüfung und Veröffentlichung von Übersetzungen unterstützt, die von Menschen oder LLMs erstellt wurden. Für die automatische Übersetzung mit DeepL ist ein separater API-Schlüssel erforderlich. Wenn Sie die Übersetzung selbst verwalten, gibt es einen Prozess, mit dem Sie sicherstellen können, dass die Übersetzung auch dann noch aktuell ist, wenn sich der Originaltext geändert hat.

Außerdem wurden die Vorlagen so gestaltet, dass Suchmaschinen und KI-Tools den Inhalt und die Quelle der Texte erfassen können.

- **Seiteninformationen für die Suche:** Es werden Titel, Beschreibung, URL des Originaltextes, Sitemap sowie Links zu den Seiten in den verschiedenen Sprachen bereitgestellt.
- **Struktur zur Erläuterung des Kontexts des Artikels:** Es werden strukturierte Daten wie Autor und Veröffentlichungsdatum bereitgestellt; bei Bedarf können Kernantworten, Quellen sowie Fragen und Antworten hinzugefügt werden.
- **Direkter Zugriff auf den Text:** Je nach Einstellung werden die Markdown-Version des öffentlichen Beitrags und die Beitragsliste „`llms.txt`“ bereitgestellt.

Das Design berücksichtigt die Auffindbarkeit in Such-, Antwort- und generativen KI-Umgebungen, die häufig als SEO, AEO und GEO bezeichnet werden. Ziel ist es, den Textkörper und den Kontext des Beitrags leicht lesbar darzustellen. Die Platzierung in Suchergebnissen oder die Zitierung in KI-Antworten wird von den jeweiligen Diensten festgelegt und kann nicht allein durch Übersetzungen oder technische Einstellungen gewährleistet werden. [Anleitung zur Suche und zum Zugriff über KI](https://github.com/gitblogapp/gitblog-blog/blob/main/docs/gitblog/ai-discovery.md).

Auch innerhalb von Gitblog können Beiträge gefunden werden. Beiträge von Blogs, die am Feed teilnehmen, werden gesammelt und in den Suchansichten wie „Neueste Beiträge“, „Beliebte Beiträge“ und „Trends“ angezeigt. Leser können Beiträge finden, die sie interessieren, und zum Blog des Autors wechseln, um sie dort zu lesen.

Unser Ziel ist es, die Wahrscheinlichkeit zu erhöhen, dass die von mir hinterlassenen Beiträge diejenigen erreichen, die diese Inhalte benötigen.

## 4. Die Resonanz auf einen Beitrag führt zu einer Verbindung über GitHub

Wenn man einen guten Beitrag liest, wird man neugierig auf den nächsten Beitrag des Autors. Man möchte herausfinden, an welchen Projekten die Person arbeitet und welche Gedanken sie festhält.

Bei Gitblog führt dieses Interesse auch zu einer Verbindung auf GitHub. **Das Abonnieren eines Blogs ist mit einem GitHub-Star für das entsprechende Repository verknüpft, und das Folgen eines Autors entspricht einem „Follow“ auf dem GitHub-Konto.** Leser können Beiträge von Blogs oder Autoren, die sie interessieren, sammeln, und Autoren können über ihre Beiträge auch auf GitHub mit Lesern in Kontakt treten.

Das mag trivial erscheinen, aber wir halten diese Verbindung für bedeutsam. Denn zu dem Bild, das sich durch Code und Projekte ergibt, kommen noch Texte und Gedanken hinzu. Beiträge, in denen Entscheidungen im Projekt, der Lösungsweg bei Problemen oder gewonnene Erkenntnisse erläutert werden, bieten einen weiteren Zugang zum Verständnis der Arbeit dieser Person.

Die Anzahl der Stars oder Follower bestimmt nicht den Wert eines Beitrags. Doch die Tatsache, dass Leser, denen mein Beitrag gefallen hat, auf den nächsten Beitrag warten, kann ein Grund sein, regelmäßig zu schreiben.

## 5. Auch im Zeitalter der KI ist das Schreiben wichtig

Wenn wir der KI Fragen stellen, schreiben wir Texte. Wir beschreiben das gewünschte Ergebnis, formulieren die Bedingungen und stellen weitere Fragen, während wir die Antwort lesen. Selbst wenn die KI die Eingabeaufforderung und den Entwurf für uns verfasst, bleibt der Prozess bestehen, zu entscheiden, was wir anfordern und welche Ergebnisse wir akzeptieren.

Das Schreiben ist auch ein Prozess, bei dem man die eigenen Gedanken unter die Lupe nimmt. Wenn man Sätze verfasst, um etwas zu erklären, werden Lücken in den Bereichen sichtbar, von denen man dachte, man wüsste sie bereits. Man sucht nach Belegen, korrigiert widersprüchliche Aussagen und stellt Zusammenhänge her, damit andere den Text verstehen können.

Auch wenn die KI immer mehr Aufgaben übernimmt, wollen wir nicht vergessen, dass wir die Rolle des Menschen einnehmen, der entscheidet, was wichtig ist und wie wir handeln. **Auch in Texten, die gemeinsam mit der KI verfasst wurden, die eigenen Gedanken und Urteile nicht aus den Augen zu verlieren** – das ist die Art des Schreibens, die wir anstreben.

Ich wünsche mir, dass Gitblog ein Ort ist, an dem wir diese Übung fortsetzen können. Ein Ort, an dem wir das Gelernte in unseren eigenen Worten erklären, Erfahrungen in kontextbezogenen Aufzeichnungen festhalten und unsere Gedanken weiterentwickeln, indem wir die Texte nach einiger Zeit erneut lesen.

Ich hoffe, dass das Verfassen guter Texte zu einem Prozess wird, der die eigene Intelligenz schärft.

## Erste Schritte mit Gitblog

Gitblog kann entweder über das Web-Studio gestartet werden oder Sie können direkt auf GitHub ein Blog-Repository erstellen und es dann lokal auf Ihrem PC betreiben. Schauen wir uns zunächst an, wie man das Studio nutzt.

### 1. Mit einem GitHub-Konto registrieren

Rufen Sie [Gitblog](https://gitblog.app/ko) auf und registrieren Sie sich mit Ihrem GitHub-Konto bzw. melden Sie sich an. Nach der Anmeldung gelangen Sie zu „Studio“, dem Bereich, in dem Sie Ihren Blog erstellen und verwalten können.

### 2. GitHub-App verbinden und Blog erstellen

Folgen Sie den Anweisungen in Studio, installieren Sie die Gitblog-App auf GitHub und gewähren Sie Zugriff auf das Repository, in dem Sie Ihren Blog verwalten möchten. Sehen Sie sich die Vorlagen vorab an, wählen Sie eine aus und legen Sie dann den Titel Ihres Blogs sowie den Namen des Repositorys fest.

![Bildschirmansicht zur Vorschau und Auswahl von Blog-Vorlagen auf Basis von Svelte, Astro, React und Vanilla HTML im englischen Gitblog Studio.](/uploads/introducing-gitblog/templates-en.jpg)

*Bildschirm zur Auswahl von Vorlagen in der englischen Version von Studio. Stand: 3. November 2026.*

Die Blog-Dateien werden in Ihrem GitHub-Repository erstellt. Für das Hosting können Sie GitHub Pages verwenden oder Ihr Cloudflare-Konto verknüpfen, um Cloudflare Pages zu nutzen. Sobald Sie die Bereitstellungseinstellungen für die gewählte Methode abgeschlossen haben, können Sie Beiträge veröffentlichen.

### 3. Artikel mit Markdown verfassen und veröffentlichen

Geben Sie auf der Beitragsseite in Studio den Titel, die Beschreibung und den Markdown-Text ein. Sie können auch ein Titelbild als Miniaturansicht sowie Bilder für den Text hochladen.

Während des Schreibens können Sie den Beitrag als Entwurf speichern und erst nach Überprüfung des Inhalts als veröffentlichten Beitrag speichern. Nach dem Speichern können Sie den Fortschritt des Build- und Bereitstellungsprozesses verfolgen. Sobald die Bereitstellung abgeschlossen ist, können Sie den Beitrag in Ihrem Blog lesen. Falls eine Übersetzung erforderlich ist, können Sie die Übersetzungssprachen und deren Verwendung für Ihren Blog festlegen und diese gemeinsam verwalten.

### Erste Schritte mit GitHub und auf dem lokalen PC

Wenn Sie mit einem lokalen Editor oder einem KI-Agenten arbeiten möchten, können Sie auf GitHub eine offizielle Gitblog-Vorlage Ihrer Wahl auswählen und direkt loslegen.

1. **Erstellen Sie mit einer Vorlage Ihr eigenes Blog-Repository.** Erstellen Sie auf der GitHub-Seite der gewünschten offiziellen Vorlage mithilfe dieser Vorlage ein neues öffentliches Repository in Ihrem Konto. Dabei wird ein Blog-Repository erstellt, das Sie selbst verwalten und das unabhängig von der Originalvorlage ist.
2. **Klonen Sie Ihr Repository auf Ihren lokalen PC.** Führen Sie „`git clone`“ unter der Adresse des erstellten Repositorys aus und öffnen Sie den heruntergeladenen Ordner in einem Editor oder als Arbeitsobjekt eines KI-Agenten. Installieren Sie gemäß den Anweisungen der Vorlage die erforderlichen Entwicklungstools und Abhängigkeiten und nehmen Sie die Ersteinstellungen wie Blog-Adresse, Sprache und Hosting vor.
3. **Verfassen und überprüfen Sie Beiträge lokal.** Verfassen Sie einen Markdown-Beitrag in „`content/posts/`“ und fügen Sie Bilder hinzu. Sie können den Beitrag direkt bearbeiten oder den Agenten anweisen, „`AGENTS.md`“ zu lesen und die Schreibanweisungen zu befolgen. Überprüfen Sie den Entwurf, setzen Sie ihn in den Veröffentlichungsstatus und führen Sie die von der Vorlage bereitgestellten Validierungsschritte durch.
4. **Stellen Sie die Änderungen auf GitHub ein und veröffentlichen Sie sie.** Wenn Sie den Beitrag und die Bilder committen und auf den Ziel-Branch pushen, erstellt der konfigurierte GitHub-Actions-Workflow den Blog und veröffentlicht ihn auf dem ausgewählten Hosting. Überprüfen Sie die Ausführungsergebnisse von Actions und ob die Änderungen auf der eigentlichen Blog-Seite übernommen wurden.

Beim ersten Mal müssen Sie die Bereitstellungsumgebung gemäß der [Anleitung zur Ersteinrichtung](https://github.com/gitblogapp/gitblog-blog/blob/main/docs/gitblog/setup.md) der ausgewählten Vorlage vorbereiten. Danach können Sie den Arbeitsablauf wie folgt fortsetzen: **Lokales Verfassen → Überprüfung und Validierung → Commit und Push → Überprüfung der Bereitstellung**.

Auch einen direkt auf GitHub erstellten Blog können Sie verwalten, indem Sie der Gitblog-App Zugriff auf das entsprechende Repository gewähren und die Funktion zur Verknüpfung bestehender Blogs in Studio nutzen. Wählen Sie einfach die für Ihre Arbeit geeignete Methode aus: entweder das Verfassen im Web oder das Verfassen lokal.

## Beginnen Sie dort, wo Ihre Beiträge gespeichert werden

Gitblog ist ein Blog, bei dem Ihre Beiträge in Ihrem Konto gespeichert werden, Sie mit vertrauten Tools schreiben können und Leser in verschiedenen Sprachen und über unterschiedliche Wege erreichen können. Dahinter steht die Überzeugung, dass man durch das Schreiben seine eigenen Gedanken besser verstehen kann.

Sie müssen nicht von Anfang an perfekte Beiträge schreiben. Halten Sie doch einfach eine Tatsache fest, die Sie heute neu erfahren haben, eine Frage, über die Sie lange nachgedacht haben, oder ein Problem, das Sie selbst gelöst haben. Der Prozess, diesen Einträgen Kontext hinzuzufügen und sie zu überarbeiten, führt zu Ihrem nächsten Beitrag.

**Sammeln Sie Ihre Gedanken auf einem Blog, das Ihnen gehört und das Sie selbst betreiben.**

[Meinen Blog auf Gitblog starten](https://gitblog.app/studio)
