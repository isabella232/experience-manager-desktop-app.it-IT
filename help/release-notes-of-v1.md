---
title: Note sulla versione dell’app desktop v1.10
description: Dettagli sulla versione, miglioramenti, nuove funzioni, compatibilità e collegamenti per il download dell’app desktop AEM versione 1.10.
exl-id: 886864e0-016a-4a17-b3ba-4b18a514214a
source-git-commit: 32aff5d66f2cb67ab4bb440d7ace747a5cf1dd26
workflow-type: tm+mt
source-wordcount: '3898'
ht-degree: 1%

---

# [!DNL Adobe Experience Manager] note sulla versione dell’app desktop v1.10 {#aem-desktop-app-release-notes}

Per la versione v1.x dell’app desktop, di seguito sono riportati i collegamenti per il download e le informazioni sulla compatibilità con AEM.

| Prodotti | App desktop [!DNL Adobe Experience Manager] |
|--- |--- |
| Versione | 1.10 (1.10.0.6 su Mac e 1.10.0.3 su Windows) |
| Tipo | Versione secondaria |
| Data | 1.10.0.6 (Mac): 15 aprile 2020; 1.10.0.3 (Windows): 31 agosto 2018 |
| URL di download | [Mac OS X a 64 bit](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/adobe/aem-desktop-app/aem-desktop-osx-1.10.0.6.dmg); [Windows a 32 bit](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/adobe/aem-desktop-app/aem-desktop-win32-1.10.0.3.exe); [Windows a 64 bit](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/adobe/aem-desktop-app/aem-desktop-win64-1.10.0.3.exe) |
| Compatibilità | AEM 6.5.x; AEM 6.4.x; AEM 6.3 SP2; AEM 6.2 SP1 CFP2+; AEM 6.1 SP2 CFP7+ |

>[!NOTE]
>
>Il limite di dimensione della cache non è applicato. All’avvio dell’app desktop, la dimensione della cache viene calcolata una volta e viene visualizzata una notifica se si avvicina al limite predefinito.

## Requisiti e prerequisiti di sistema {#system-requirements-and-prerequisites}

[!DNL Adobe Experience Manager]L’app desktop è compatibile con i seguenti sistemi operativi:

* Mac OS X 10.10 o versione successiva, con correzioni di bug più recenti.

* Windows 10 con Service Pack e correzioni di bug più recenti.

>[!NOTE]
>
>Windows 7 non è più supportato. Consulta [articolo sulla fine del ciclo di vita di Windows 7](https://support.microsoft.com/en-us/help/4057281/windows-7-support-ended-on-january-14-2020).

L’Adobe consiglia vivamente di utilizzare l’ultima versione dell’app desktop AEM per usufruire delle funzionalità e delle correzioni di bug più recenti e delle migliori prestazioni possibili.

La versione dell’app desktop AEM che intendi installare nel computer locale richiede una versione specifica del server AEM/componenti aggiuntivi lato server (service pack, hotfix o feature pack). Prima di connettersi al server AEM per la prima volta, verificare che sia configurato correttamente. Se hai bisogno di assistenza, contatta l’amministratore AEM.

Consulta la [matrice di compatibilità dettagliata](#compatibilitymatrix) alla fine del presente documento per valutare i prerequisiti per la configurazione.

## Novità dell’app desktop v1.10 {#what-s-new-in-aem-desktop-app}

L’app desktop AEM 1.10 si concentra sul miglioramento dell’esperienza utente tramite caricamenti di grandi dimensioni, informazioni sulle operazioni in background e un’esperienza ottimizzata all’apertura di risorse con file collegati (come InDesign).

>[!NOTE]
>
>Se utilizzi macOS 10.15.4 o versione successiva, utilizza almeno la versione 1.10.0.6 dell’app. Questa versione della patch è conforme a [Requisiti di notarizzazione di Apple](https://developer.apple.com/news/?id=04102019a).

**Modifica locale / Estrazione**: nella finestra di stato è possibile disabilitare i caricamenti automatici delle modifiche salvate nelle risorse. In questo modo l’utente può continuare a lavorare sui file e salvare le modifiche e quindi, quando è pronto, decidere di caricare tutte le modifiche.

**Finestra Stato risorse semplificate**. La finestra di stato è stata semplificata. Il [!UICONTROL Uploads] La scheda ora mostra sia le singole risorse che le cartelle o i caricamenti in blocco. La scheda Caricamenti in blocco precedente è stata rimossa.

**Icona dell’applicazione per indicare i caricamenti in blocco**. L’icona dell’applicazione indica che è in corso un caricamento in blocco mostrando una sovrapposizione &quot;trasferimento&quot;.

**Notifiche per conflitti di aggiornamento**. Quando l’applicazione rileva un conflitto durante il tentativo di aggiornare una risorsa, visualizza una notifica in modo che l’utente possa esaminarlo senza dover monitorare la finestra di stato. All’avvio dell’applicazione, verificherà la presenza di tutti i conflitti, in modo che l’utente possa risolverli.

**Gestione migliore delle perdite di connessione**. I caricamenti in blocco verranno sospesi se si verifica una perdita di connessione e l’utente potrà riprendere in un secondo momento. A [!UICONTROL Retry] è disponibile l’opzione per ritentare il caricamento di un singolo file non riuscito.

## Istruzioni di installazione {#installation-instructions}

Per istruzioni dettagliate, consulta [Installare e configurare l’app desktop AEM](install-configure-app-v1.md).

## Miglioramenti nelle versioni precedenti {#enhancements-in-the-previous-versions}

Questa versione estende e sostituisce le versioni precedenti di [!DNL Experience Manager] l’app desktop, che ha fornito i seguenti miglioramenti chiave:

* **Versione 1.9/1.9.1**: caricamenti ripristinabili, finestra di stato migliorata, icone dell’applicazione che indicano lo stato dell’applicazione/connessione, recupero anticipato delle risorse collegate per i file InDesign.

* **Versione 1.8**: migliore controllo della dimensione della cache per l’utente, migliore esperienza di accesso per SAML/SSO su Windows, supporto del proxy di rete .pac su Mac e problemi segnalati dai clienti.

* **Versione 1.7**: miglioramenti nella stabilità e nella logica di caching, supporto migliore per il proxy di rete e possibilità di pulire i file interni dopo la disinstallazione.

* **Versione 1.6**: miglioramenti nel processo di accesso per varie configurazioni di sicurezza AEM e nella stabilità e nelle prestazioni delle applicazioni.

* **Versione 1.5**: stabilità e resilienza delle applicazioni rispetto a vari problemi di rete, migliore supportabilità.

* **Versione 1.4**: possibilità di caricare cartelle gerarchiche in background con il monitoraggio dell’avanzamento.

* **Versione 1.3**: miglioramenti delle prestazioni e stabilità per l’accesso ai file e il salvataggio delle modifiche su AEM, in particolare dalle applicazioni desktop Creative Cloud, come InDesign, Illustrator o Photoshop. L&#39;obiettivo era offrire agli utenti un&#39;esperienza più simile a quella dei desktop locali quando lavorano con i file e gestiscono contemporaneamente le operazioni di trasferimento dei dati di rete in background.

### Miglioramenti disponibili dall’app desktop AEM 1.9 {#Enhancements-Available-Since-AEM-Desktop-App-19x}

[!DNL Adobe Experience Manager] l’app desktop 1.9.1 era una versione patch per risolvere alcuni problemi fondamentali dei clienti relativi al pagamento delle risorse e alla copia dei file dalla condivisione di rete a una directory locale.

* Le risorse estratte da un utente non devono essere disponibili per modifiche da parte di altri utenti (CQ-4246009)

* Supporto della copia da una cartella mappata a una cartella locale quando la cartella utente si trova in una partizione disco separata (CQ-4243978)

L’app desktop AEM 1.9 si concentra sul miglioramento dell’esperienza utente per quanto riguarda caricamenti di grandi dimensioni, informazioni sulle operazioni in background e un’esperienza ottimizzata al momento di aprire risorse con file collegati (come InDesign).

**Caricamenti ripristinabili**
Per i caricamenti, in particolare dei file di grandi dimensioni, è possibile metterli in pausa o riprenderli nella nuova finestra Stato risorsa.

**Finestra Stato risorsa migliorata**
Una finestra di stato migliorata fornisce le seguenti informazioni sulle risorse.

[!UICONTROL Changes]

* Visualizza le modifiche attualmente in coda.

* Mostra i caricamenti in corso, tra cui una barra di avanzamento, la velocità di trasferimento, la dimensione totale del file e la dimensione trasferita finora.

* Caricamenti completati mostrati con la frequenza totale trasferita e finale.

* I caricamenti non riusciti vengono visualizzati insieme a un messaggio di errore e alle informazioni di trasferimento, se disponibili.

* I caricamenti che hanno avuto esito negativo per 3 volte mostreranno un messaggio di errore.

* File in conflitto visualizzati con un&#39;icona su cui l&#39;utente può fare clic. Facendo clic sull’icona viene visualizzata una finestra di dialogo con una spiegazione e due opzioni:

   * [!UICONTROL Keep Mine] carica immediatamente il file sul server.

   * [!UICONTROL Overwrite Mine] elimina immediatamente il file locale e scarica una nuova copia dal server.

[!UICONTROL Downloads]

* Visualizza i download in corso, tra cui una velocità di trasferimento e una dimensione trasferite finora.

* Download completati mostrati con il totale trasferito, frequenza finale e un&#39;icona che aprirà il file quando cliccato (disponibile solo per file singoli).

* Download non riusciti visualizzati con un messaggio di errore e informazioni di trasferimento, se disponibili.

* Il piè di pagina mostra il numero totale di file scaricati e la velocità media di trasferimento.

* Se un utente sceglie di aprire o modificare più file da [!DNL Experience Manager Assets] dell&#39;interfaccia Web, saranno raggruppati insieme. Ad esempio, myasset.jpeg e altri 4 file.

* Quando si scaricano documenti InDesign contenenti risorse collegate memorizzate in AEM Assets, l’app desktop scaricherà tutte le risorse collegate prima di aprire [!UICONTROL Adobe InDesign] e indicare il download delle risorse collegate. Ad esempio, 5 su 24.

[!UICONTROL Bulk Uploads]

Caricamento di gerarchie di cartelle di grandi dimensioni tramite [!UICONTROL Create] > [!UICONTROL Upload Folder] nell’interfaccia web dell’AEM, l’utilizzo di questa finestra di dialogo viene attivato copiando e selezionando &quot;Incolla risorse&quot; nel Finder o in Explorer nel menu di scelta rapida dell’app desktop.

* Visualizza i caricamenti in corso, tra cui una barra di avanzamento e il nome del file attualmente trasferito.

* I caricamenti in corso includono un’icona che, se selezionata, annullerà il caricamento. Il trasferimento verrà interrotto al termine del file attualmente in fase di trasferimento.

* I processi di trasferimento non riusciti vengono visualizzati con un messaggio di errore (solo se l’intero trasferimento non riesce).

* Se un singolo file non viene trasferito, viene visualizzato nella scheda come un errore. In caso contrario, i singoli file non verranno visualizzati nella scheda * come una singola voce per l’intero caricamento.

**Icone per indicare lo stato delle operazioni in background**

L&#39;icona dell&#39;applicazione indica lo stato delle operazioni in background per fornire un segnale visivo migliore agli utenti. Ad esempio, quando l’applicazione non è connessa all’AEM l’icona è disattivata, quando è presente un caricamento attivo viene visualizzata una sovrapposizione &quot;sincronizzazione&quot; e così via.

**Preacquisizione di risorse collegate**

Per migliorare l’esperienza utente quando si lavora con documenti InDesign che includono risorse collegate memorizzate nell’AEM, l’app desktop tenta di prerecuperare questi file collegati nella cache locale prima di scaricarli e di aprire il documento InDesign. In questo modo l’utente avrà i file collegati disponibili localmente e non dovrà aspettare più quando vi accede in InDesign (nel pannello Collegamenti ).
Tieni presente che la preacquisizione funziona solo se l’AEM riconosce i collegamenti sul lato server. Una risorsa con collegamenti riconosciuti avrà un elenco di &quot;Riferimenti&quot; nella vista Proprietà della risorsa InDesign.

### Miglioramenti disponibili dall’app desktop AEM 1.8.x {#enhancements-available-since-aem-desktop-app-18x}

La versione fast-follow dell’app desktop AEM 1.8.1 ha apportato miglioramenti all’apertura di più file contemporaneamente dall’interfaccia utente dell’AEM alla versione 1.8 (CQ-4237747, CQ-4238780). I miglioramenti nell’app desktop AEM 1.8 sono:

* Memorizzazione in cache: nuova interfaccia utente per la gestione della cache delle app desktop AEM (CQ-4208690), tra cui

   * visualizza dimensione cache corrente

   * definire la dimensione massima della cache prima dell’invio di una notifica

   * La dimensione della cache è selezionata solo all’avvio dell’app desktop e viene visualizzata una notifica se sta raggiungendo il limite configurato

   * il pulsante di cancellazione della cache è ora disponibile nella nuova interfaccia utente

* Accesso: (Win) è stato corretto l’accesso all’istanza AEM configurata per l’utilizzo di SAML e SSL (CQ-4216353)

* Rete:

   * alla scadenza di una sessione AEM, l’utente riceve una notifica e può fare clic sulla notifica per accedere di nuovo (CQ-4202028).

   * (Mac) È stato aggiunto il supporto per la connessione all’AEM tramite la configurazione proxy .pac (CQ-4233430).

   * (Win) risolvere i problemi con la finestra di dialogo Avanzate - URL di accesso (CQ-4236061).

* Correzioni di bug:

   * Finestra di dialogo Ulteriori informazioni sulle risorse: a volte la barra delle azioni non era visibile (CQ-4208540).

   * (Win) Il file può ora essere sincronizzato dopo il ripristino di una versione precedente dall&#39;interfaccia utente di AEM Assets (CQ-4216411).

### Miglioramenti disponibili dall’app desktop AEM 1.7 {#Enhancements-Available-Since-AEM-Desktop-App-17}

* Stabilità:

   * Maggiore stabilità quando l’app desktop AEM si connette a un server AEM sovraccarico (CQ-4224803).

   * È stata migliorata la stabilità quando vengono richiesti molti file (CQ-4224212).

   * È stato migliorato l’aggiornamento delle risorse con un controllo aggiuntivo (CQ-4228291).

* Memorizzazione in cache:

   * Correggere gli errori del disco e i problemi di apertura quando si aprono file in Photoshop, InDesign, Finder (CQ-4223993, CQ-4217603, CQ-4223717).

   * È stato migliorato il caching per evitare binari di dimensione zero (CQ-4216599).

* Accesso: consenti la connessione con strictSSL disabilitato per configurazioni speciali (come certificati rilasciati localmente) (CQ-4223949).

* Reti: supporto migliorato per la connessione tramite proxy di rete (CQ-4223477, CQ-4221280, CQ-4206854).

* Installazione e disinstallazione:

   * (Win) Disinstallazione di Cleaner (CQ-4220906).

   * [Windows a 32 bit] Impossibile installare Microsoft .NET Framework v. 4.5 (CQ-4218084).

   * (Mac) Script manuale per la rimozione completa dei file delle app desktop (CQ-4216489).

>[!NOTE]
>
>I problemi rilevati nei carichi beta dell’app desktop AEM 1.7 (che non erano presenti nella versione 1.6 di non sono riportati nelle note sulla versione).

### Miglioramenti disponibili dall’app desktop AEM 1.6 {#Enhancements-Available-Since-AEM-Desktop-App-16}

* Documentazione: nuova [Best practice per l’app v1.x](/help/best-practices-for-v1.md) documentazione.

* Procedura di accesso migliorata all’AEM:

   * Migliorare la gestione SAML * regole di attenuazione (CQ-4202781).

   * Aggiungi la funzionalità per configurare un URL di accesso separato in Preferenze (CQ-4214052, CQ-4214051).

* Usabilità: notifica all’utente quando una risorsa viene ancora scaricata per risorse più grandi (CQ-4216284).

* Reti:

   * Memorizzazione in cache DNS (CQ-4210176).

   * Supporta la connessione tramite proxy su Windows (CQ-4206854).

* Memorizzazione in cache e accesso alla condivisione di rete nel Finder/Explorer:

   * Icona Blocca ora visibile per le risorse estratte in Windows 10 (CQ-90957).

   * Il contenuto della cartella potrebbe scomparire o riapparire nella condivisione di rete (CQ-4209160, CQ-4210180).

   * Errore durante il caricamento del file a causa di un conflitto segnalato nello stato della coda di caricamento (CQ-4215727).

   * Quando si aprono più file dalla cartella dell’app desktop in PS, è possibile che vengano visualizzati messaggi troncati o incompleti (CQ-4216276).

* Problemi di stabilità e prestazioni:

   * Sono state migliorate le prestazioni durante la navigazione nelle cartelle con molte risorse (CQ-4214933).

   * L’app desktop 1.5 può rallentare la macchina desktop nel tempo (CQ-4209159).

   * La funzione di visualizzazione dello stato della coda funziona solo per l’utente che ha installato l’app (CQ-4212199).

   * (Windows) Verificare che il programma di installazione a 32 bit non contenga codice a 64 bit (CQ-4217406).

* Problemi selezionati rilevati e risolti nella versione 1.6 Beta:

   * Utilizzo CPU elevato (CQ-4218070).

   * Trascina i file per generare un errore durante il caricamento su AEM (CQ-4217006).

### Miglioramenti disponibili dall’app desktop AEM 1.5 {#Enhancements-Available-Since-AEM-Desktop-App-15}

**Versione 1.5.1.5 per Mac OS X:** La versione 1.5.1.5 offre i seguenti vantaggi:

* Nuove funzioni e miglioramenti: aggiunta della funzionalità Copia/Incolla all&#39;integrazione del Finder per consentire il trasferimento diretto dal desktop all&#39;AEM (CQ-4208158).

* Correzioni di bug:

   * È stato risolto l&#39;errore 43 che si verificava a volte durante la ridenominazione delle risorse (CQ-4207900).

   * Il ripristino di una versione precedente dalla timeline in AEM non aggiorna la risorsa nel Finder (CQ-4205194).

   * L’app desktop si blocca durante la navigazione in directory nidificate di grandi dimensioni (CQ-4208539).

   * Il punto di montaggio dell’app desktop è ora /Volumes/DAM, quindi è coerente per tutti gli utenti (CQ-4208159).

   * Quando si inserisce un file in InDesign per la prima volta, viene visualizzato un avviso di aggiornamento (CQ-4207454).

Nota sugli avvisi di collegamento: le applicazioni di Creative Cloud (come InDesign) eseguono un&#39;istantanea dell&#39;ora dell&#39;ultima modifica apportata all&#39;elemento al momento dell&#39;inserimento. Se tale data cambia in un momento successivo, l’app Adobe Creative Cloud segnalerà che i collegamenti sono obsoleti. Questo problema viene segnalato in due modi:

* All’avvio dell’app Adobe Creative Cloud, viene visualizzata una finestra di dialogo in cui si informa l’utente che le risorse collegate non sono aggiornate e si chiede all’utente di intervenire.

* Se l’app Adobe Creative Cloud è già in esecuzione, sulla risorsa collegata verrà visualizzata un’icona di avviso gialla con un triangolo.

Questo comportamento è lo stesso per le risorse su disco locale e per le risorse in una directory montata su AEM Desktop, con le seguenti eccezioni:

* Se una risorsa inserita viene modificata da un altro utente, l’icona di avviso viene visualizzata la prima volta che altri utenti aprono un documento contenente la risorsa inserita. Ciò accade solo se la risorsa inserita è già stata memorizzata nella cache locale.

* Se un utente modifica una risorsa inserita tramite la directory MOUNTED del desktop AEM e poi cancella la cache locale, la risorsa inserita verrà segnalata come obsoleta.

Entrambi questi casi sono previsti e sono effetti collaterali dell&#39;architettura di &quot;sincronizzazione ritardata&quot; di AEM Desktop.

**Versione 1.5.0.x per Mac OS X e Windows:** Questa versione dell’app desktop AEM offre i seguenti vantaggi:

* Migliore stabilità e resilienza contro le questioni legate alle reti.

   * Mappatura più stabile delle cartelle di AEM Assets (CQ-103276, CQ-4204669, CQ-4203957).

   * Gestione migliore dei file memorizzati in cache (CQ-4204336, CQ-4206263).

   * È stata migliorata la gestione del download/caricamento di file di grandi dimensioni di dimensioni superiori a 2 GB (CQ-4206438).

   * È stato corretto l’&quot;Errore 36&quot; durante lo spostamento o la ridenominazione di un numero maggiore di file nel Finder (CQ-4204640).

* Ottimizzazione della comunicazione di rete con il server AEM (CQ-4204974, CQ-100903).

* Maggiore affidabilità di apertura, posizionamento e salvataggio delle risorse AEM nelle app Creative Cloud (CQ-4203968, CQ-4205511, CQ-103543, CQ-4207141, CQ-90980).

* Supporto migliorato: opzione per cancellare la cache (CQ-4202541), accesso semplificato ai registri (CQ-4202340, CQ-4204673).

* Altre correzioni:
   * Supporto migliorato per risorse e cartelle con caratteri giapponesi in impostazioni di nome/non in lingua inglese (CQ-4195433, CQ-4205793, CQ-4199446).

   * Gestione migliore dell’accesso con SSL (CQ-4200217).

   * Montaggio condiviso più affidabile (CQ-4200793).

   * Vari miglioramenti nella stabilità (CQ-4207539, CQ-4200378).

   * Gestione migliore dell’URL di AEM Assets nelle Preferenze (CQ-97388).

### Miglioramenti disponibili dall’app desktop AEM 1.4 {#Enhancements-Available-Since-AEM-Desktop-App-14}

* Caricamento semplificato delle cartelle gerarchiche tramite la nuova azione Crea > Carica cartella nell’interfaccia utente touch.
   * Azione che avvia un&#39;operazione di caricamento di cartelle eseguita dall&#39;app desktop
   * L’app desktop attraversa in background la gerarchia di cartelle specificata sul desktop e carica i file in AEM Assets
   * L&#39;utente può monitorare l&#39;avanzamento nella nuova finestra Stato coda di caricamento con una barra di avanzamento per le operazioni in corso
   * Lo stato della coda di caricamento fornisce anche informazioni migliori sulla risoluzione dei problemi (ad esempio, nessuna connessione al server)
* Nuova azione Modifica nell’interfaccia utente touch, che combina in un’unica azione le operazioni Check-Out e Apri
* Raggruppamento ottimizzato di azioni relative ai desktop nell’interfaccia utente touch (AEM 6.3)
* Maggiore compatibilità con le ultime versioni del sistema operativo
* Correzioni segnalate dal cliente

### Miglioramenti disponibili dall’app desktop AEM 1.3 {#Enhancements-Available-Since-AEM-Desktop-App-13}

* Maggiore efficienza. Gli utenti impiegano meno tempo ad attendere il completamento delle operazioni di rete.
* È stata migliorata l&#39;integrazione del Finder, che offre maggiore stabilità e accesso a funzioni quali le miniature.
* Memorizzazione in cache e miglioramenti delle prestazioni.
* Supporto migliore per il salvataggio direttamente dalle app desktop (PS, ID, AI e così via).
* Migliore integrazione con il sistema operativo Mac (il protocollo dell&#39;unità di rete locale è stato cambiato da WebDAV a SMB1 più stabile).
* L’app desktop si connette al server AEM utilizzando il protocollo HTTP RESTful AEM nativo.
* I file vengono prima salvati localmente e poi caricati nuovamente in AEM in background dopo un tempo predefinito (30 sec). Questo riduce il tempo necessario per salvare i file.
* Gestione migliore delle applicazioni desktop che utilizzano operazioni intermedie sui file per salvare un file (salvataggi parziali e file temporanei), che consente alla timeline delle risorse AEM di visualizzare le informazioni corrette sulla versione e sul caricamento delle risorse.
* Finestra di dialogo fornita per tenere traccia dello stato delle attività di caricamento in background.

## Elenco delle modifiche {#list-of-changes}

### Punto di montaggio su Mac {#mount-point-on-mac}

A partire da MacOS 10.12 (Sierra), Apple ha modificato le autorizzazioni per la cartella /Volumes utilizzata per montare unità e dispositivi di rete su più restrittivi. La creazione di un nuovo punto di montaggio richiedeva diritti amministrativi. Questo problema è stato risolto in MacOS 10.12.5.

Poiché l’app desktop AEM deve essere eseguita per gli utenti che non dispongono di diritti di amministratore sul computer locale, il punto di montaggio per l’archivio AEM Assets è stato modificato in 1.4 e 1.5 in una sottocartella DAM nella cartella locale dell’utente su MacOS (CQ-104183).

Poiché la cartella /Volumes non richiede più diritti amministrativi, questa modifica è stata ripristinata nella versione 1.5.1. Questo consente anche di condividere i documenti InDesign che hanno creato risorse AEM tra gli utenti di MacOS.

### Modifica del protocollo (dalla versione 1.3) {#protocol-change-since}

* Mac OS X:
   * Il protocollo dell&#39;unità di rete locale per l&#39;integrazione desktop di OS X è stato modificato da WebDAV a SMB1.
   * L&#39;archivio AEM installato con l&#39;app desktop sarà visibile come unità di rete &quot;SMB&quot; nel Finder, invece che come unità WebDAV.
* Windows:
   * Il protocollo dell&#39;unità di rete locale per le integrazioni desktop Windows rimane invariato; AEM verrà installato come condivisione WebDAV.
* Per entrambe le piattaforme (Windows e Mac):
   * Il protocollo per accedere/scaricare le risorse e caricare le modifiche all’AEM è stato modificato nel protocollo nativo dell’AEM, che è un protocollo RESTful basato su HTTP. Offre un maggiore controllo sulle operazioni di rete ed è più compatibile con l&#39;infrastruttura di rete.

>[!NOTE]
>
>In Mac OS X, la modifica del protocollo dell&#39;unità di rete locale da WebDAV a SMB1 determina un percorso locale diverso per la stessa risorsa nell&#39;archivio. Questo potrebbe influire sui collegamenti ai file inseriti nelle applicazioni Adobe Creative Cloud tramite il comando &quot;Inserisci&quot;. Consulta la [Utilizzare l’app desktop AEM](use-app-v1.md) per ulteriori informazioni.

### Gestione dei file (a partire dalla versione 1.3) {#file-handling-since}

* Le cartelle vengono aggiornate automaticamente dopo un ritardo predefinito (attualmente di 30 secondi).
* I file estratti da altri utenti sono contrassegnati come di sola lettura.
* I file vengono salvati in un percorso di unità di rete montato tramite l&#39;app desktop in due fasi.
* Nella prima fase, un file viene salvato localmente. In questo modo, l’utente che salva il file non deve attendere che il file sia completamente trasferito a AEM e può riprendere il lavoro non appena il file viene salvato.
* Nella seconda fase, l’app desktop carica un file aggiornato sul server AEM dopo un ritardo predefinito (ad esempio, 30 secondi ). Questa operazione viene eseguita in background. Utilizza il **Mostra stato sincronizzazione file in background** per visualizzare lo stato dell’operazione di caricamento.

## Avvisi importanti {#important-notices}

**Caricamento cartella.** Si consiglia di utilizzare la nuova funzionalità di caricamento cartelle per caricare cartelle gerarchiche di grandi dimensioni in AEM, anziché utilizzare copia/trascinamento e rilascio in un archivio AEM montato dal livello Finder/Explorer. Quando si utilizza la funzione di caricamento delle cartelle, l’app desktop comunica direttamente con l’AEM e ha quindi un controllo molto migliore sul processo complessivo.

**Mantieni disponibile la sessione AEM.** L’app desktop AEM dipende da una sessione aperta sul server AEM Assets per garantire il corretto funzionamento. Per gli utenti che lavorano quotidianamente con l’app desktop, si consiglia di smontare AEM Assets alla fine della giornata per forzare la disconnessione e quindi di &quot;montare AEM Assets&quot; al mattino per assicurarsi che abbiano effettuato l’accesso e che la condivisione di rete sia operativa.

**Disattivare Anteprima icona nel Finder.** Per una navigazione efficiente di cartelle di grandi dimensioni con il Finder, in particolare con scarsa connettività di rete, accertati che sia &quot;Icona&quot; che &quot;Anteprima icona&quot; siano disattivate. In caso contrario, il Finder inizierà a scaricare ogni risorsa in una cartella per generare una piccola anteprima, che può portare a prestazioni scadenti e un utilizzo elevato della larghezza di banda (CQ-4219779)

* Nel Finder, vai alla cartella di rete condivisa di AEM Assets
* Fare clic con il pulsante destro del mouse sul punto di montaggio DAM
* Seleziona Mostra opzioni di visualizzazione
* Deseleziona &quot;Mostra anteprima icona&quot;
* Fare clic su &quot;Usa come predefinito&quot;

**Pulizia della cache durante la connessione a un nuovo server AEM.** Se l’app desktop si connette a un altro server AEM con lo stesso URL, la cache non viene cancellata automaticamente. Cancella la cache manualmente per garantire il corretto funzionamento. Tieni presente che questo accade in genere nei test, quando le installazioni AEM possono essere sostituite mentre si esegue sullo stesso URL (CQ-4216982)

**Utilizza certificati SSL con firma CA.** Tieni presente che l’app desktop AEM non supporta certificati SSL autofirmati quando ti connetti all’AEM tramite una connessione protetta HTTPS. Per tali connessioni è necessario un certificato firmato da una CA nel server. (CQ-87941)

## Problemi noti {#known-issues}

* Generale:
   * Gli URL del server devono puntare al server senza un percorso (ad esempio, `http://server`, `https://server`, `http://server:port`, o `https://server:port`). I percorsi contestuali e le sottocartelle diversi da /content/dam non sono supportati (CQ-89343, CQ-87272)
* Nomi file/localizzazione:
   * I nomi di file e cartelle con caratteri riservati non vengono gestiti correttamente. Assicurati di utilizzare nomi di file e cartelle che soddisfino i requisiti AEM (CQ-93361, CQ-93308, CQ-89276, CQ-4217183)
   * Alcune applicazioni come Adobe Illustrator potrebbero creare file con nomi non supportati nell’AEM. Ad esempio, aggiungendo `Converted` dopo la conversione, il caricamento di un file si interrompe (CQ-4216985)
   * Le risorse con nomi internazionali possono apparire e scomparire a intervalli di pochi secondi
* Consegna e ritiro:
   * Una risorsa estratta da un utente non può essere aperta per un altro utente tramite l’azione Apri dell’interfaccia utente touch o direttamente sul desktop. Alcune applicazioni potrebbero segnalarlo come bloccato, ma anche danneggiato o persino bloccato durante il tentativo di apertura. (CQ-4199234)
   * La modifica simultanea di file da parte di più utenti può causare la perdita di alcune modifiche. La soluzione consiste nell&#39;utilizzare le funzionalità di archiviazione ed estrazione per impedire a più utenti di modificare lo stesso file (CQ-97035)
   * Alcune applicazioni non supportano correttamente il flag di sola lettura che consente a un utente di salvare un file estratto da un altro utente. Il file modificato non viene trasferito finché l’altro utente non lo archivia. Entrambe le modifiche sono disponibili in AEM come diverse versioni della risorsa (CQ-89551, CQ-87572, CQ-89615)
   * Lo stato estratto e di sola lettura viene riportato in modo indipendente nel Finder. Questo comporta 2 icone di blocco quando un utente estrae una risorsa (CQ-89507)
* Integrazione del Finder:
   * Quando si trascinano o rilasciano file di grandi dimensioni, il Finder potrebbe scadere durante il trasferimento dei file in background. Questo determina un `Error - 36`. La soluzione consiste nel trascinare/rilasciare o aprire nuovamente la risorsa (CQ-4219628)
   * Il ricaricamento manuale della cartella non sempre funziona. Soluzione alternativa: attendi 30 secondi per l’aggiornamento automatico della cartella. (CQ-97389)
   * Ulteriori informazioni sulle risorse... sono limitate alle selezioni di file singoli (CQ-89542, CQ-87656)
   * Apri in AEM Assets... è limitato alle selezioni di singoli file e cartelle (CQ-83382)
   * Errore durante la ridenominazione delle risorse senza estensione (CQ-4218971)
* Funzionalità Copia/Incolla: l’opzione Incolla è disponibile quando non è stata copiata alcuna risorsa negli Appunti
* Windows:
   * I file con flussi di dati alternativi (ADS, Alternate Data Streams) sono completamente supportati solo su NTFS. La copia di tali file nella condivisione WebDAV fornita dall&#39;app desktop genera una finestra di avviso che avvisa l&#39;utente che il file ha proprietà che non possono essere copiate nella nuova posizione. Questa operazione è in genere corretta, poiché le proprietà sono rilevanti solo per una particolare applicazione sul desktop dell&#39;utente e non hanno nulla a che fare con il contenuto effettivo del file (CQ-103770) (Win)
   * L&#39;app desktop su Windows deve essere installata dall&#39;utente che la utilizzerà (CQ-4216389) (win)
   * L&#39;app può bloccarsi quando si seleziona [!UICONTROL Retry] opzione su un caricamento non riuscito in determinate circostanze dopo aver ripreso il caricamento batch quando era disconnesso (CQ-4251884) (Win)

## Risorse utili {#helpful-resources}

* [Documentazione AEM](https://experienceleague.adobe.com/docs/)
* [Utilizzare l’app desktop AEM v1.x](use-app-v1.md)
* [Best practice per l’app desktop AEM v1.x](best-practices-for-v1.md)

## Matrice di compatibilità e prerequisiti {#compatibilitymatrix}

L’app desktop AEM funziona con varie versioni dell’AEM. Consulta la matrice di compatibilità per le versioni supportate.

| Versione | Revisione | Data di pubblicazione | Compatibilità |
|--- |--- |--- |--- |
| 1.10 | 1.10.0.3 (Mac e Win) | 31 agosto 2018 | AEM 6.5; AEM 6.4 SP1; AEM 6.3 SP2; AEM 6.2 SP1 CFP2+; AEM 6.1 SP2 CFP7+ |
| 1.9 | 1.9.1.1 (Mac e Win) | 21 giugno 2018 | AEM 6.4; AEM 6.3 SP1; AEM 6.2 SP1 CFP2+; AEM 6.1 SP2 CFP7+ |
| 1.8 | 1.8.1.0 (Mac e Win) | 28 marzo 2018 | AEM 6.4; AEM 6.3 SP1; AEM 6.2 SP1 CFP2+; AEM 6.1 SP2 CFP7+ |
| 1.7 | 1.7.0.3 (Mac e Win) | 10 gennaio 2018 | AEM 6.3 SP1; AEM 6.2 SP1 CFP2+; AEM 6.1 SP2 CFP7+ |
