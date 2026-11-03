---
id: f2c641a8-e850-4ae0-89a1-14ee48d9a1a2
title: >-
  Presentazione di Gitblog: come mantenere la proprietà dei propri articoli e
  gestire il proprio blog
description: >-
  Archivia i tuoi articoli nel mio repository GitHub, scrivili con l’aiuto
  dell’IA e raggiungi un pubblico più ampio. Ecco le cinque filosofie alla base
  di Gitblog e come avviare il tuo blog.
date: '2026-11-03T19:00:00+09:00'
published: false
category: Manual
tags:
  - gitblog
  - 사용법
locale: it
sourcePath: content/posts/2026-11-03-introducing-gitblog.md
sourceHash: ae6300517c6dcbbba87b7dfd95feecc0119ced0b194d83b9c6de02c9e4e0f45b
sourceLocale: ko
translationSchemaVersion: markdown-xml-v4
translationSource: deepl
translatedAt: '2026-11-03T16:09:50.512Z'
updated: '2026-11-04T00:40:50+09:00'
---
Sul blog non si accumulano solo i post. Rimangono anche il percorso seguito per risolvere un problema, i momenti in cui ho imparato qualcosa di nuovo e il mio punto di vista su un determinato argomento. Con il passare del tempo, queste tracce diventano una risorsa che mostra su cosa ho riflettuto e come sono cambiato.

Ma allora, dove dovrebbero essere conservati questi beni? Anche se il servizio su cui scrivevo dovesse cambiare o scomparire, non dovrei poter continuare a conservarli e gestirli?

**Gitblog è un servizio che consente di archiviare i post pubblici e il codice del blog nel proprio repository GitHub e di pubblicare articoli sul proprio blog tramite il web o agenti di intelligenza artificiale.** Partendo dal presupposto di possedere e gestire direttamente i propri contenuti, abbiamo aggiunto funzionalità che facilitano la scrittura e consentono di entrare in contatto con i lettori.

La creazione di Gitblog nasce da cinque considerazioni fondamentali.

## 1. Gli articoli che scrivo devono essere di mia proprietà e devo poterli gestire

Più a lungo si scrivono articoli, più è importante poterli consultare in qualsiasi momento. Riteniamo che l’autore debba poter conservare, modificare e, se necessario, trasferire altrove i propri contenuti.

I post pubblici di Gitblog vengono salvati come file Markdown nel proprio repository GitHub. È possibile gestire anche i file del blog, comprese le immagini, e il codice. Scaricando il repository sul proprio PC, è possibile leggere, modificare ed eseguire il backup dei post in locale, oltre a poter verificare i contenuti precedenti tramite la cronologia delle modifiche di Git.

**Anche se il servizio Gitblog dovesse cessare di esistere, il repository del proprio account, i post archiviati in locale e il codice del blog rimarranno.** Mantenendo l’hosting e il dominio, è possibile continuare a fornire il blog statico pubblicato e, se necessario, trasferire i file su un altro hosting. Tuttavia, le funzionalità di integrazione fornite da Gitblog, come la navigazione e l’iscrizione, dipendono dal funzionamento del servizio.

È proprio questo il motivo per cui abbiamo scelto GitHub come piattaforma di base. È già utilizzato da molte persone e offre le basi per avviare un blog tramite repository pubblici e GitHub Pages. Anche con GitHub Free è possibile utilizzare l’hosting di Pages per i repository pubblici. L’ambito di copertura e i limiti di utilizzo seguono [la politica di GitHub](https://docs.github.com/en/pages/getting-started-with-github-pages/what-is-github-pages).

Potere conservare l’originale dei post pubblici, indipendentemente da dove vengano scritti: questo è il primo principio di Gitblog.

## 2. Deve essere un blog in cui sia possibile utilizzare anche l’IA

Scrivere con l’aiuto dell’IA sta diventando sempre più naturale: si creano bozze partendo da appunti, si sintetizzano contenuti complessi, si perfezionano le frasi e si traduce in altre lingue. Proprio come un agente di programmazione legge e modifica i file di un progetto, riteniamo che anche un agente che assiste nella scrittura debba poter gestire direttamente i file del blog.

Il repository del blog di Gitblog contiene linee guida e comandi relativi alla scrittura, alla traduzione e alla verifica a cui gli agenti di IA possono fare riferimento. Se si designa il proprio repository del blog come oggetto di lavoro per un agente in grado di leggere e modificare i file locali ed eseguire comandi, è possibile redigere bozze e preparare la pubblicazione in quell’ambiente. Se si dispone delle autorizzazioni e dei permessi necessari, è possibile procedere fino alla distribuzione.

Ad esempio, è possibile inviare una richiesta come questa:

> Leggi il file AGENTS.md in questo repository del blog e segui le linee guida di scrittura. Scrivi l’articolo basandoti sulle note che ho lasciato e salvalo come bozza in modo che io possa revisionarlo.

Una volta completata la revisione, è possibile richiedere la traduzione, la verifica e la distribuzione. Le operazioni possibili variano a seconda dell’ambito di accesso ai file e dei permessi di esecuzione dei comandi dell’agente utilizzato. Il flusso specifico è descritto nella [Guida alla scrittura e alla traduzione del blog](https://github.com/gitblogapp/gitblog-blog/blob/main/docs/gitblog/authoring.md).

Gitblog non impone l’uso di un modello di IA specifico per la scrittura. Puoi scrivere direttamente sul web, utilizzare un editor che conosci bene o lavorare insieme all’IA. L’obiettivo è consentire all’autore di scegliere lo strumento più adatto al proprio modo di lavorare.

## 3. Un buon articolo deve poter essere scoperto al di là della lingua e degli strumenti

Dopo la pubblicazione di un articolo, qualcuno deve scoprirlo e leggerlo. C’è chi cerca risposte sui motori di ricerca e chi, ponendo domande a servizi di IA, trova materiale pertinente. Ci sono anche lettori che leggono in una lingua diversa da quella che si utilizza.

Gitblog offre una struttura che consente di raggiungere questi lettori, grazie alla pubblicazione multilingue e all’accessibilità tramite ricerca e IA.

Innanzitutto, è possibile tradurre il testo originale, scritto nella lingua che si preferisce, nella lingua selezionata e pubblicarlo. Supporta sia la traduzione automatica tramite l’integrazione dell’API DeepL, sia la registrazione di traduzioni redatte da persone o da modelli di linguaggio (LLM) previa revisione. Per la traduzione automatica con DeepL è necessaria una chiave API separata. Nel caso in cui si gestisca direttamente la traduzione, viene fornita una procedura per verificare che la traduzione sia aggiornata al contenuto originale qualora questo venga modificato.

Inoltre, i modelli sono stati progettati in modo che i motori di ricerca e gli strumenti di intelligenza artificiale possano identificare il contenuto e la fonte dell’articolo.

- **Informazioni sulla pagina per la ricerca:** forniscono titolo, descrizione, URL del testo originale, mappa del sito e collegamenti alle pagine nelle diverse lingue.
- **Struttura che descrive il contesto dell’articolo:** fornisce dati strutturati quali autore e data di pubblicazione; se necessario, è possibile aggiungere risposte chiave, fonti, domande e risposte.
- **Percorsi di accesso diretto al testo:** a seconda delle impostazioni, vengono fornite la versione Markdown degli articoli pubblici e l’elenco degli articoli denominato `llms.txt`.

Si tratta di una progettazione che tiene conto della reperibilità in ambienti di ricerca, risposta e IA generativa, comunemente denominati SEO, AEO e GEO. L’obiettivo è quello di rendere facilmente leggibili il corpo del testo e il contesto dell’articolo. Il posizionamento nei risultati di ricerca o le citazioni nelle risposte dell’IA sono determinati dai singoli servizi e non sono garantiti dalla sola traduzione o dalle impostazioni tecniche. [Guida alla ricerca e all’accesso tramite IA](https://github.com/gitblogapp/gitblog-blog/blob/main/docs/gitblog/ai-discovery.md).

È possibile trovare gli articoli anche all’interno di Gitblog. Gli articoli dei blog che partecipano al feed vengono raccolti e visualizzati nelle schermate di esplorazione, come “Ultimi articoli”, “Articoli popolari” e “Tendenze”. I lettori possono cercare gli articoli di loro interesse e accedere al blog dell’autore per leggerli.

Il nostro obiettivo è ampliare la possibilità che i contenuti che pubblichiamo raggiungano chi ne ha bisogno.

## 4. L’apprezzamento per un post porta a una connessione su GitHub

Quando si legge un buon articolo, si è curiosi di scoprire anche il prossimo articolo dell’autore. Si finisce per cercare di capire che tipo di persona sia chi sta realizzando quel progetto e quali pensieri stia condividendo.

Su Gitblog, questo interesse si traduce anche in una connessione su GitHub. **L’iscrizione a un blog è collegata alle stelle (Star) su GitHub del relativo repository, mentre seguire un autore equivale a seguirlo sul proprio account GitHub.** I lettori possono raccogliere i post dei blog o degli autori che li interessano, mentre gli autori possono connettersi con i lettori anche su GitHub attraverso i propri contenuti.

Può sembrare una cosa da poco, ma riteniamo che questa connessione sia significativa. Questo perché ai profili che emergono dal codice e dai progetti si aggiungono gli articoli e le riflessioni. Gli articoli che spiegano le decisioni prese nei progetti, il processo di risoluzione dei problemi e ciò che si è imparato diventano un ulteriore canale per comprendere il lavoro di quella persona.

Il numero di "Star" o di follower non determina il valore di un articolo. Tuttavia, il fatto che un lettore che si è identificato con il mio articolo possa diventare un lettore affezionato in attesa del prossimo post può essere un motivo per continuare a scrivere con costanza.

## 5. Scrivere è importante anche nell’era dell’IA

Quando poniamo domande all’IA, scriviamo. Spieghiamo il risultato desiderato, definiamo le condizioni e, dopo aver letto la risposta, poniamo ulteriori domande. Anche quando l’IA redige al posto nostro il prompt e la bozza, rimane comunque il processo di valutazione su cosa richiedere e quali risultati accettare.

Scrivere è anche un processo di analisi dei propri pensieri. Mentre si scrivono frasi per spiegare un concetto, si notano le lacune in ciò che si pensava di sapere. Si cercano le prove, si correggono le affermazioni incoerenti e si collegano i contesti in modo che gli altri possano comprendere.

Anche se l’IA si assumerà sempre più compiti, non vogliamo dimenticare il nostro ruolo di persone che decidono cosa è importante e come agire. **Non perdere di vista i propri pensieri e giudizi anche nei testi scritti insieme all’IA**: questo è il tipo di scrittura a cui aspiriamo.

Spero che Gitblog possa essere uno spazio in cui continuare questo esercizio: uno spazio in cui spiegare ciò che si è imparato con parole proprie, lasciare traccia delle proprie esperienze in una narrazione contestualizzata e, rileggendo dopo un po’ di tempo, far evolvere il proprio pensiero.

Speriamo che l’accumulo di buoni articoli diventi un processo di affinamento della propria intelligenza.

## Iniziare con Gitblog

È possibile avviare Gitblog direttamente da Studio sul web oppure creare un repository del blog su GitHub e gestirlo dal proprio PC locale. Vediamo innanzitutto come utilizzare Studio.

### 1. Registrati con un account GitHub

Accedete a [Gitblog](https://gitblog.app/ko) e registratevi o effettuate l’accesso con il vostro account GitHub. Una volta effettuato l’accesso, andate su Studio, lo spazio in cui potete creare e gestire il vostro blog.

### 2. Collegare l’app GitHub e creare il blog

Seguendo le istruzioni di Studio, installate l’app Gitblog su GitHub e autorizzate l’accesso al repository per la gestione del blog. Visualizzate in anteprima i modelli, sceglietene uno, quindi stabilite il titolo del blog e il nome del repository.

![Schermata di anteprima e selezione dei modelli di blog basati su Svelte, Astro, React e Vanilla HTML in Gitblog Studio (versione inglese).](/uploads/introducing-gitblog/templates-en.jpg)

*Schermata di selezione dei modelli nella versione inglese di Studio. Aggiornato al 3 novembre 2026.*

I file del blog vengono creati nel proprio repository GitHub. Per l’hosting è possibile utilizzare GitHub Pages oppure collegare il proprio account Cloudflare per utilizzare Cloudflare Pages. Una volta completate le impostazioni di distribuzione relative al metodo scelto, si è pronti per pubblicare i post.

### 3. Scrivere e pubblicare un post in Markdown

Nella schermata di scrittura di Studio, inserisci il titolo, la descrizione e il corpo del testo in Markdown. Puoi anche caricare un’immagine di copertina per la miniatura che rappresenta il post e immagini da inserire nel corpo del testo.

Durante la scrittura, è possibile salvare come bozza e, dopo aver rivisto il contenuto, salvare come pubblicato. Dopo il salvataggio, è possibile verificare lo stato di avanzamento della compilazione e della distribuzione; una volta completata la distribuzione, sarà possibile leggere il post sul proprio blog. Se è necessaria una traduzione, è sufficiente configurare la lingua di traduzione del blog e le relative modalità di utilizzo per gestirla in parallelo.

### Iniziare su GitHub e sul PC locale

Se desideri lavorare con un editor locale o un agente AI, puoi scegliere il modello ufficiale Gitblog che preferisci su GitHub e iniziare direttamente.

1. **Crea il repository del tuo blog utilizzando un modello.** Dalla pagina GitHub del modello ufficiale che preferisci, utilizza il modello per creare un nuovo repository pubblico sul tuo account. Verrà creato un repository del blog che gestirai tu, separato dal modello originale.
2. **Clonate il vostro repository sul PC locale.** Eseguite `git clone` utilizzando l’indirizzo del repository creato, quindi aprite la cartella scaricata come progetto nell’editor o nell’agente AI. Seguite le istruzioni del modello per installare gli strumenti di sviluppo e le dipendenze necessarie, quindi completate le impostazioni iniziali quali l’indirizzo del blog, la lingua e l’hosting.
3. **Scrivere e verificare i post in locale.** Scrivere un post in Markdown in `content/posts/` e aggiungere immagini. È possibile modificarlo direttamente oppure chiedere all’agente di leggere `AGENTS.md` e seguire le istruzioni di scrittura. Dopo aver rivisto la bozza, impostare lo stato su “Pubblicato” ed eseguire la procedura di verifica fornita dal modello.
4. **Caricare le modifiche su GitHub e distribuirle.** Una volta effettuato il commit del testo e delle immagini ed eseguito il push sul ramo di distribuzione, il flusso di lavoro GitHub Actions configurato genererà il blog e lo distribuirà sull’hosting selezionato. Verificare i risultati dell’esecuzione di Actions e controllare che le modifiche siano state applicate alla pagina del blog.

La prima volta è necessario preparare l’ambiente di distribuzione seguendo la [Guida alla configurazione iniziale](https://github.com/gitblogapp/gitblog-blog/blob/main/docs/gitblog/setup.md) del modello scelto. Successivamente, è possibile proseguire con il flusso **scrittura in locale → revisione e verifica → commit e push → verifica della distribuzione**.

È possibile gestire anche un blog creato direttamente su GitHub, purché si conceda all’app Gitblog l’accesso al repository in questione e si utilizzi la funzione di collegamento ai blog esistenti di Studio. Basta scegliere il metodo più adatto al proprio lavoro tra la scrittura sul web e quella in locale.

## Iniziate da un luogo in cui i vostri articoli rimangano conservati

Gitblog punta a creare un blog in cui i post vengono archiviati nel proprio account, si possono scrivere con strumenti familiari e raggiungere i lettori in diverse lingue e attraverso diversi canali. Alla base di tutto ciò c’è la convinzione che attraverso la scrittura sia possibile comprendere più a fondo i propri pensieri.

Non è necessario scrivere un post perfetto fin dall’inizio. Provate a mettere per iscritto un fatto che avete scoperto oggi, una domanda su cui avete riflettuto a lungo o un problema che avete risolto personalmente. Il processo di aggiungere contesto a quella registrazione e di perfezionarla porterà al prossimo post.

**Costruisci il tuo pensiero su un blog di tua proprietà e gestito da te.**

[Come creare il mio blog su Gitblog](https://gitblog.app/studio)
