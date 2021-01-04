---
title: AEM note sulla versione dell'app desktop per la versione 1.x
description: Dettagli sulla versione, miglioramenti, nuove funzioni, compatibilità e collegamenti per AEM'app desktop versione 1.x.
translation-type: tm+mt
source-git-commit: a25c1fa13895ae9eb7268e3e01c83a5f0b9d7d1d
workflow-type: tm+mt
source-wordcount: '3906'
ht-degree: 1%

---


# [!DNL Adobe Experience Manager] note sulla versione dell&#39;app desktop v1.x  {#aem-desktop-app-release-notes}

Per l&#39;app desktop versione 1.x, quanto segue sono riportati i collegamenti per il download e le informazioni sulla compatibilità AEM.

| Prodotti | [!DNL Adobe Experience Manager] app desktop |
|--- |--- |
| Versione | 1.10 (1.10.0.6 su Mac e 1.10.0.3 su Windows) |
| Tipo | Rilascio secondario |
| Data | 1.10.0.6 (Mac): 15 aprile 2020; 1.10.0.3 (Win): 31 agosto 2018 |
| URL di download | [Mac OS X a 64 bit](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/adobe/aem-desktop-app/aem-desktop-osx-1.10.0.6.dmg);  [Windows a 32 bit](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/adobe/aem-desktop-app/aem-desktop-win32-1.10.0.3.exe);  [Windows a 64 bit](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/adobe/aem-desktop-app/aem-desktop-win64-1.10.0.3.exe) |
| Compatibilità | AEM 6.5.x; AEM 6.4.x; AEM 6.3 SP2; AEM 6.2 SP1 CFP2+; AEM 6.1 SP2 CFP7+ |

>[!NOTE]
>
>Limite dimensione cache non applicato. All&#39;avvio dell&#39;app desktop, la dimensione della cache viene calcolata una volta e viene visualizzata una notifica se la dimensione è vicina al limite predefinito.

## Requisiti di sistema e prerequisiti {#system-requirements-and-prerequisites}

[!DNL Adobe Experience Manager]L’app desktop è compatibile con i seguenti sistemi operativi:

* Mac OS X 10.10 o versione successiva, con correzioni di bug più recenti.

* Windows 10 con i Service Pack più recenti e le correzioni di bug.

>[!NOTE]
>
>Windows 7 non è più supportato dal fornitore (https://support.microsoft.com/en-us/help/4057281/windows-7-support-ended-on-january-14-2020).

 Adobe consiglia vivamente di utilizzare la versione più recente dell&#39;app desktop AEM per utilizzare le funzionalità più recenti, le correzioni di bug più recenti e le prestazioni migliori.

La versione dell&#39;app desktop AEM che si intende installare sul computer locale richiede una versione AEM server/componenti aggiuntivi lato server (Service Pack, hotfix o feature pack) specifici. Prima di collegarsi ad esso per la prima volta, verificate che il server AEM sia configurato correttamente. Se avete bisogno di aiuto, contattate il vostro amministratore AEM.

Vedere la [matrice di compatibilità dettagliata](#compatibilitymatrix) alla fine di questo documento per valutare i prerequisiti per la configurazione.

## Novità AEM app desktop 1.10 {#what-s-new-in-aem-desktop-app}

AEM&#39;app desktop 1.10 è incentrata sul miglioramento dell&#39;esperienza utente in relazione a caricamenti di grandi dimensioni, informazioni sulle operazioni in background e un&#39;esperienza ottimizzata quando si aprono risorse con file collegati (come  InDesign).

>[!NOTE]
>
>Se utilizzate macOS 10.15.4 o versioni successive, utilizzate almeno la versione 1.10.0.6 dell&#39;app. Questa versione della patch è conforme ai [requisiti di notarizzazione Apple](https://developer.apple.com/news/?id=04102019a).

**Modifica locale/Check-Out**: Nella finestra di stato è possibile disattivare il caricamento automatico delle modifiche salvate nelle risorse. In questo modo l’utente può continuare a lavorare sui file e salvare le modifiche e, quando sono pronti, decidere di caricare tutte le modifiche.

**Finestra** Stato risorsa semplificata. La finestra di stato è stata semplificata. La scheda [!UICONTROL Uploads] ora mostra sia le singole risorse, sia i caricamenti di cartelle o di massa. La scheda Caricamenti di massa precedente è stata rimossa.

**Icona dell&#39;applicazione per indicare i caricamenti** in blocco. L’icona dell’applicazione indica che è in corso un caricamento in blocco, mostrando una sovrapposizione &quot;transfer&quot;.

**Notifiche per conflitti** di aggiornamento. Quando l&#39;applicazione rileva un conflitto durante il tentativo di aggiornamento di una risorsa, visualizzerà una notifica, in modo che l&#39;utente possa controllarla senza dover monitorare la finestra di stato. All&#39;avvio dell&#39;applicazione, l&#39;utente controllerà la presenza di tutti i conflitti, in modo che possano essere risolti.

**Gestione migliore delle perdite** di connessione. Se si verifica una perdita di connessione, i caricamenti di massa verranno messi in pausa e l&#39;utente potrà riprendere in seguito. È disponibile un pulsante Riprova per ripetere il caricamento non riuscito di un singolo file.

## Istruzioni di installazione {#installation-instructions}

Per istruzioni dettagliate, consultate [Installare e configurare AEM&#39;app desktop](install-configure-app-v1.md).

## Miglioramenti nelle versioni precedenti {#enhancements-in-the-previous-versions}

Questa versione estende e sostituisce le versioni precedenti dell&#39;app desktop [!DNL Experience Manager], che hanno fornito i seguenti miglioramenti chiave:

* **Versione 1.9/1.9.1**: caricamenti ripristinabili, finestra di stato migliorata, icone dell’applicazione che indicano lo stato dell’applicazione/connessione, preacquisizione delle risorse collegate per i file  InDesign.

* **Versione 1.8**: migliore controllo delle dimensioni della cache per l&#39;utente, migliore esperienza di accesso per SAML/SSO su Windows, supporto del proxy di rete .pac su Mac e problemi segnalati dai clienti.

* **Versione 1.7**: miglioramento della stabilità e della logica di caching, migliore supporto per i proxy di rete e capacità di pulire i file interni dopo la disinstallazione.

* **Versione 1.6**: miglioramenti nel processo di login per diverse configurazioni di protezione AEM e stabilità e prestazioni dell&#39;applicazione.

* **Versione 1.5**: stabilità e resilienza delle applicazioni rispetto a vari problemi di rete, migliore capacità di supporto.

* **Versione 1.4**: la possibilità di caricare cartelle gerarchiche in background con il monitoraggio dell’avanzamento.

* **Versione 1.3**: miglioramenti delle prestazioni e stabilità dell&#39;accesso ai file e del salvataggio delle modifiche a AEM, in particolare dalle applicazioni desktop di Creative Cloud, come  InDesign,  Illustrator o Photoshop. L&#39;obiettivo era quello di offrire agli utenti un&#39;esperienza desktop più locale quando lavorano con i file, gestendo allo stesso tempo le operazioni di trasferimento dei dati di rete in background.

### Miglioramenti disponibili a partire AEM app desktop 1.9 {#Enhancements-Available-Since-AEM-Desktop-App-19x}

[!DNL Adobe Experience Manager] l&#39;app desktop 1.9.1 era una patch release per risolvere alcuni problemi chiave dei clienti relativi al checkout delle risorse e alla copia dei file dalla condivisione di rete a una directory locale.

* Le risorse sottoposte a check-out da parte di un utente non devono essere disponibili per la modifica per altri utenti (CQ-4246009)

* Copia di supporto dalla cartella mappata a una cartella locale quando la cartella utente si trova in una partizione disco separata (CQ-4243978)

AEM&#39;app desktop 1.9 si è concentrata sul miglioramento dell&#39;esperienza utente in relazione a caricamenti di grandi dimensioni, informazioni sulle operazioni in background e sull&#39;esperienza ottimizzata quando si aprono risorse con file collegati (come  InDesign).

****
Caricamenti ripetibili: per i caricamenti, soprattutto attorno a file di grandi dimensioni, è disponibile un’opzione per interromperli o riprenderli nella nuova finestra Stato risorsa.

**Miglioramento della**
finestra Stato risorsaUna finestra di stato delle risorse migliorata fornisce le seguenti informazioni sulle risorse.

[!UICONTROL Changes]

* Visualizza le modifiche attualmente presenti nella coda.

* Mostra i caricamenti in corso, inclusi una barra di avanzamento, la frequenza di trasferimento, la dimensione totale del file e la dimensione trasferiti finora.

* Caricamenti completati mostrati con trasferimento totale e frequenza finale.

* Vengono visualizzati i caricamenti non riusciti con un messaggio di errore e informazioni sul trasferimento, se disponibili.

* I caricamenti che hanno avuto esito negativo per 3 volte generano un messaggio di errore.

* I file in conflitto vengono visualizzati con un’icona su cui l’utente può fare clic. Facendo clic sull’icona viene visualizzata una finestra di dialogo con una spiegazione e due opzioni:

   * [!UICONTROL Keep Mine] carica immediatamente il file sul server.

   * [!UICONTROL Overwrite Mine] elimina immediatamente il file locale e ne scarica una nuova copia dal server.

[!UICONTROL Downloads]

* Visualizza i download in corso, inclusa una velocità di trasferimento e le dimensioni trasferite finora.

* Download completati mostrati con trasferimento totale, tasso finale e un&#39;icona che aprirà il file quando l&#39;utente fa clic (disponibile solo per singoli file).

* Download non riusciti visualizzati con un messaggio di errore e informazioni di trasferimento, se disponibili.

* Piè di pagina indica il numero totale di file scaricati e la velocità media di trasferimento.

* Se un utente sceglie di aprire o modificare più file dall&#39;interfaccia Web [!DNL Experience Manager Assets], questi verranno raggruppati. Ad esempio, myasset.jpeg e altri 4 file.

* Quando si scaricano  documenti InDesign, comprese le risorse collegate memorizzate in  AEM Assets, l&#39;app desktop scaricherà prima tutte le risorse collegate, prima di aprire il documento [!UICONTROL Adobe InDesign] e indicare il download delle risorse collegate. Ad esempio, 5 di 24.

[!UICONTROL Bulk Uploads]

Se si caricano gerarchie di cartelle grandi tramite [!UICONTROL Create] > [!UICONTROL Upload Folder] nell&#39;interfaccia AEM Web, se si copia e si seleziona &quot;Incolla risorse&quot; nel Finder o in Esplora risorse nel menu di scelta rapida dell&#39;app desktop, l&#39;utilizzo di questa finestra di dialogo verrà attivato.

* Visualizza i caricamenti in corso, inclusa una barra di avanzamento e il nome del file attualmente in fase di trasferimento.

* I caricamenti in corso includono un’icona che annulla il caricamento quando viene fatto clic su di essi. Il trasferimento verrà interrotto al termine del file di trasferimento.

* I processi di trasferimento non riusciti vengono visualizzati con un messaggio di errore (solo se l&#39;intero trasferimento non riesce).

* Se un singolo file non viene trasferito, verrà visualizzato nella scheda come un errore. In caso contrario, i singoli file non verranno visualizzati nella scheda * solo una voce per l’intero caricamento.

**Icone per indicare lo stato delle operazioni in background**

L&#39;icona dell&#39;applicazione indica lo stato delle operazioni in background per fornire agli utenti un migliore segnale visivo. Ad esempio, quando l’applicazione non è connessa a AEM l’icona viene disattivata, quando è presente un caricamento attivo viene visualizzata una sovrapposizione &quot;sincronizzazione&quot;, ecc.

**Pre-acquisizione delle risorse collegate**

Per migliorare l&#39;esperienza dell&#39;utente quando lavorate con  documenti InDesign che includono risorse collegate memorizzate in AEM, l&#39;app desktop tenterà di recuperare questi file collegati nella cache locale prima di scaricare e aprire il documento InDesign . In questo modo l&#39;utente potrà avere localmente i file collegati e non dovrà più aspettare per accedervi in  InDesign (nel pannello Collegamenti).
Il preacquisizione funziona solo se AEM riconosce i collegamenti sul lato server. Una risorsa con collegamenti riconosciuti avrà un elenco di &quot;Riferimenti&quot; elencati nella vista Proprietà della risorsa InDesign .

### Miglioramenti disponibili a partire AEM app desktop 1.8.x {#enhancements-available-since-aem-desktop-app-18x}

AEM’app desktop versione 1.8.1, che segue rapidamente, sono stati aggiunti miglioramenti all’apertura simultanea di più file dall’interfaccia utente AEM alla versione 1.8 (CQ-4237747, CQ-4238780). I miglioramenti in AEM app desktop 1.8 sono:

* Memorizzazione nella cache: nuova interfaccia utente per la gestione AEM cache delle app desktop (CQ-4208690), compresi,

   * visualizza dimensione cache corrente

   * definire la dimensione massima della cache prima dell&#39;invio di una notifica

   * La dimensione della cache viene controllata solo all&#39;avvio dell&#39;app desktop e viene visualizzata una notifica se sta raggiungendo il limite configurato

   * il pulsante Cancella cache è ora disponibile nella nuova interfaccia utente

* Login: (Win) È stato corretto il login a AEM&#39;istanza configurata per l&#39;utilizzo di SAML e SSL (CQ-4216353)

* Rete:

   * alla scadenza di una sessione AEM, l&#39;utente riceve una notifica e può fare clic sulla notifica per effettuare nuovamente l&#39;accesso (CQ-4202028).

   * (Mac) Aggiungete il supporto per la connessione a AEM mediante la configurazione proxy .pac (CQ-4233430).

   * (Win) risoluzione dei problemi relativi alla finestra di dialogo Avanzate - URL di accesso (CQ-4236061).

* Correzioni di bug:

   * Finestra di dialogo Ulteriori informazioni sulla risorsa: talvolta la barra delle azioni non era visibile (CQ-4208540).

   * (Win) È ora possibile sincronizzare il file dopo il ripristino di una versione precedente dall&#39;interfaccia utente  AEM Assets (CQ-4216411).

### Miglioramenti disponibili a partire AEM app desktop 1.7 {#Enhancements-Available-Since-AEM-Desktop-App-17}

* Stabilità:

   * È stata migliorata la stabilità quando AEM&#39;app desktop si connette a un server AEM sovraccarico (CQ-4224803).

   * È stata migliorata la stabilità quando vengono richiesti molti file (CQ-4224212).

   * Aggiornamento delle risorse migliorato con controllo aggiuntivo (CQ-4228291).

* Memorizzazione nella cache:

   * Correggete gli errori del disco e i problemi di apertura dei file in Photoshop,  InDesign, Finder (CQ-4223993, CQ-4217603, CQ-4223717).

   * È stato migliorato il caching per evitare file binari di dimensione zero (CQ-4216599).

* Login: Consenti la connessione con SecureSSL disattivato per configurazioni speciali (come certificati rilasciati localmente) (CQ-4223949).

* Rete: È stato migliorato il supporto per la connessione tramite proxy di rete (CQ-4223477, CQ-4221280, CQ-4206854).

* Installazione e disinstallazione:

   * (Win) Disinstallazione di Cleaner (CQ-4220906).

   * [Windows 32 ] bitInstaller non riesce a installare Microsoft .NET Framework v. 4.5 (CQ-4218084).

   * (Mac) Script manuale per la rimozione completa dei file delle app desktop (CQ-4216489).

>[!NOTE]
>
>I problemi riscontrati AEM carichi beta dell’app desktop 1.7 (non presenti nella versione 1.6) non sono riportati nelle note sulla versione.

### Miglioramenti disponibili a partire AEM app desktop 1.6 {#Enhancements-Available-Since-AEM-Desktop-App-16}

* Documentazione: Nuova documentazione [Best practice per l&#39;app v1.x](https://helpx.adobe.com/experience-manager/6-3/assets/using/aem-desktop-app-best-practices.html).

* Processo di accesso migliorato per AEM:

   * Miglioramento della gestione SAML * regole di relax (CQ-4202781).

   * È stata aggiunta la possibilità di configurare un URL di accesso separato nelle Preferenze (CQ-4214052, CQ-4214051).

* Usabilità: Informate l&#39;utente quando la risorsa è ancora in fase di download per risorse più grandi (CQ-4216284).

* Rete:

   * Caching DNS (CQ-4210176).

   * Connessione di supporto tramite proxy in Windows (CQ-4206854).

* Memorizzazione in cache e accesso alla condivisione di rete nel Finder/Esplora risorse:

   * Icona Blocca ora visibile per le risorse sottoposte a Check-Out in Windows 10 (CQ-90957).

   * Il contenuto delle cartelle potrebbe scomparire o riapparire nella condivisione di rete (CQ-4209160, CQ-4210180).

   * Errore nel caricamento del file a causa di un conflitto segnalato nello stato della coda di caricamento (CQ-4215727).

   * Quando si aprono più file dalla cartella dell&#39;app desktop in PS, è possibile che vengano visualizzati messaggi troncati o incompleti (CQ-4216276).

* Problemi di stabilità e prestazioni

   * Sono state migliorate le prestazioni durante la navigazione nelle cartelle con molte risorse (CQ-4214933).

   * l&#39;app desktop 1.5 può rallentare il computer desktop nel tempo (CQ-4209159).

   * La funzione Mostra stato coda funziona solo per l&#39;utente che ha installato l&#39;app (CQ-4212199).

   * (Windows) Verificate che il programma di installazione a 32 bit non contenga codice a 64 bit (CQ-4217406).

* Problemi selezionati rilevati e risolti nella versione 1.6 Beta:

   * Utilizzo CPU elevato (CQ-4218070).

   * Errore di trascinamento dei file durante il caricamento in AEM (CQ-4217006).

### Miglioramenti disponibili a partire AEM app desktop 1.5 {#Enhancements-Available-Since-AEM-Desktop-App-15}

**Versione 1.5.1.5 per Mac OS X:** La versione 1.5.1.5 offre i seguenti vantaggi:

* Nuove funzioni e miglioramenti: Aggiunta della funzionalità Copia/Incolla all&#39;integrazione del Finder per consentire il trasferimento diretto da Desktop a AEM (CQ-4208158).

* Bugfix:

   * È stato corretto un problema di errore 43 che si verificava talvolta durante la ridenominazione delle risorse (CQ-4207900).

   * Il ripristino di una versione precedente dalla timeline in AEM non aggiorna la risorsa nel Finder (CQ-4205194).

   * si verifica l&#39;arresto anomalo dell&#39;app desktop quando si consultano directory nidificate di grandi dimensioni (CQ-4208539).

   * il punto di montaggio dell&#39;app desktop ora è /Volumes/DAM, quindi è coerente per tutti gli utenti (CQ-4208159).

   * L&#39;inserimento di un file nel InDesign  per la prima volta attiva un avviso di aggiornamento (CQ-4207454).

Nota sugli avvisi di collegamento: Le applicazioni di Creative Cloud (ad esempio  InDesign) acquisiscono uno &quot;snapshot&quot; dell&#39;ora dell&#39;ultima modifica dell&#39;elemento al momento in cui viene posizionato. Se tale data viene modificata in un momento successivo, l&#39;app Adobe Creative Cloud segnalerà che i collegamenti non sono aggiornati. Questo è riportato in un paio di modi:

* Quando l&#39;app Adobe Creative Cloud viene avviata, viene visualizzata una finestra di dialogo in cui viene comunicato all&#39;utente che le risorse collegate non sono aggiornate e all&#39;utente viene richiesto di intervenire.

* Se l’app Adobe Creative Cloud è già in esecuzione, sulla risorsa collegata verrà visualizzata un’icona di avviso a triangolo gialla.

Questo comportamento è lo stesso per le risorse su disco locale e le risorse in una directory montata AEM Desktop, con le seguenti eccezioni:

* Se una risorsa inserita viene modificata da un altro utente, l’icona di avviso compare la prima volta che altri utenti aprono un documento contenente la risorsa inserita. Ciò si verificherà solo se la risorsa inserita è già stata memorizzata nella cache locale.

* Se un utente modifica una risorsa inserita tramite AEM directory montata del desktop e quindi cancella la cache locale, la risorsa inserita verrà segnalata come non aggiornata.

Entrambi questi casi sono previsti e sono effetti collaterali dell&#39;architettura di &quot;sincronizzazione ritardata&quot; di AEM Desktop.

**Versione 1.5.0.x per Mac OS X e Windows:** Questa release di AEM app desktop offre i seguenti vantaggi:

* Migliorare la stabilità e la resilienza contro le questioni legate alla rete.

   * Mappatura più stabile delle  cartelle AEM Assets (CQ-103276, CQ-4204669, CQ-4203957).

   * Gestione migliore dei file memorizzati nella cache (CQ-4204336, CQ-4206263).

   * È stata migliorata la gestione del download/caricamento di file di grandi dimensioni con dimensioni superiori a 2 GB (CQ-4206438).

   * È stato corretto &quot;Errore 36&quot; quando si spostava o si rinominava un numero maggiore di file nel Finder (CQ-4204640).

* Ottimizzazioni nelle comunicazioni di rete con AEM Server (CQ-4204974, CQ-100903).

* Maggiore affidabilità nell&#39;apertura, posizionamento e salvataggio delle risorse AEM nelle app di Creative Cloud (CQ-4203968, CQ-4205511, CQ-103543, CQ-4207141, CQ-90980).

* Supporto migliorato: opzione per cancellare la cache (CQ-4202541), accesso facilitato ai registri (CQ-4202340, CQ-4204673).

* Altre correzioni:
   * Supporto migliorato per risorse e cartelle con caratteri giapponesi nelle impostazioni di nome/lingua non inglese (CQ-4195433, CQ-4205793, CQ-4199446).

   * Gestione migliore dell&#39;accesso con SSL (CQ-4200217).

   * Supporto di condivisione più affidabile (CQ-4200793).

   * Diversi miglioramenti nella stabilità (CQ-4207539, CQ-4200378).

   * Gestione migliore  URL AEM Assets nelle preferenze (CQ-97388).

### Miglioramenti disponibili a partire AEM app desktop 1.4 {#Enhancements-Available-Since-AEM-Desktop-App-14}

* Caricamento semplificato di cartelle gerarchiche tramite la nuova azione Crea > Carica cartella nell’interfaccia utente touch.
   * Azione avvia un’operazione di caricamento delle cartelle eseguita dall’app desktop
   * L&#39;app desktop attraversa la gerarchia di cartelle specificata sul desktop in background e carica i file  AEM Assets
   * L’utente può monitorare l’avanzamento nella nuova finestra Stato coda di caricamento con la barra di avanzamento per le operazioni in corso
   * Lo stato della coda di caricamento fornisce anche informazioni migliori sulla risoluzione dei problemi (ad esempio, nessuna connessione al server)
* Nuova azione di modifica nell’interfaccia utente touch, che combina le operazioni Check-Out e Open in un’unica
* Raggruppamento ottimizzato di azioni relative al desktop nell&#39;interfaccia utente touch (AEM 6.3)
* Maggiore compatibilità con le ultime versioni del sistema operativo
* Correzioni riportate dal cliente

### Miglioramenti disponibili a partire AEM app desktop 1.3 {#Enhancements-Available-Since-AEM-Desktop-App-13}

* Maggiore efficienza. Gli utenti passano meno tempo in attesa del completamento delle operazioni di rete.
* Integrazione del Finder migliorata, che offre maggiore stabilità e accesso alle funzionalità, come le miniature.
* Miglioramenti a livello di cache e prestazioni.
* Supporto migliore per il salvataggio diretto dalle app desktop (PS, ID, AI e così via).
* Migliorata l&#39;integrazione con Mac OS (protocollo dell&#39;unità di rete locale modificato da WebDAV a SMB1 più stabile).
* L&#39;app desktop si connette con il server AEM utilizzando AEM protocollo HTTP RESTful nativo.
* I file vengono salvati localmente prima e quindi caricati nuovamente in AEM in background dopo un tempo predefinito (30 sec). Questo riduce il tempo necessario per salvare i file.
* Gestione migliore delle applicazioni desktop che utilizzano operazioni intermedie sui file per salvare un file (salvataggi parziali e file temporanei), che consente alla timeline delle risorse AEM di visualizzare le informazioni corrette sulla versione e sul caricamento delle risorse.
* Finestra di dialogo fornita per tenere traccia dello stato delle attività di caricamento in background.

## Elenco delle modifiche {#list-of-changes}

### Punto di montaggio su Mac {#mount-point-on-mac}

A partire da MacOS 10.12 (Sierra), Apple ha modificato le autorizzazioni sulla cartella /Volumes utilizzata per installare unità e dispositivi di rete in modo più restrittivo. La creazione di un nuovo punto di montaggio richiedeva diritti amministrativi. Questo problema è stato risolto in MacOS 10.12.5.

Poiché AEM&#39;app desktop deve essere eseguita per gli utenti che non dispongono dei diritti di amministratore nel computer locale, il punto di montaggio per  repository di AEM Assets è stato modificato in 1.4 e 1.5 in una sottocartella DAM nella cartella locale dell&#39;utente in MacOS (CQ-104183).

Poiché la cartella /Volumes non richiede più diritti amministrativi, questa modifica è stata ripristinata in 1.5.1. Questo consente anche di condividere  documenti InDesign che hanno inserito AEM risorse tra gli utenti MacOS.

### Modifica del protocollo (dalla versione 1.3) {#protocol-change-since}

* Mac OS X:
   * Il protocollo dell&#39;unità di rete locale per l&#39;integrazione desktop di OS X è stato modificato in SMB1 da WebDAV.
   * L&#39;archivio AEM montato con l&#39;app desktop sarà visibile come un&#39;unità di rete &quot;smb&quot; nel Finder, invece di un&#39;unità WebDAV.
* Windows:
   * Il protocollo dell&#39;unità di rete locale per le integrazioni desktop di Windows rimane; AEM verrà montato come condivisione WebDAV.
* Per entrambe le piattaforme (Windows e Mac):
   * Il protocollo per accedere/scaricare risorse e caricare le modifiche a AEM è stato modificato nel protocollo AEM nativo, un protocollo RESTful basato su HTTP. Offre un maggiore controllo sulle operazioni di rete ed è più compatibile con l&#39;infrastruttura di rete.

>[!NOTE]
>
>In Mac OS X, la modifica del protocollo dell&#39;unità di rete locale da WebDAV a SMB1 determina un percorso locale diverso per la stessa risorsa nell&#39;archivio. Ciò potrebbe influenzare i collegamenti ai file inseriti nelle applicazioni Adobe Creative Cloud tramite il comando &quot;Inserisci&quot;. Per ulteriori informazioni, vedere [Utilizza AEM app desktop](use-app-v1.md).

### Gestione dei file (dal 1.3) {#file-handling-since}

* Le cartelle vengono aggiornate automaticamente dopo un ritardo predefinito (attualmente 30 sec).
* I file estratti da altri utenti sono contrassegnati come di sola lettura.
* I file vengono salvati in una posizione dell&#39;unità di rete montata tramite l&#39;app desktop in due fasi.
* Nella prima fase, un file viene salvato localmente. In questo modo, l&#39;utente che salva il file non deve attendere che il file venga trasferito completamente a AEM e può riprendere il lavoro non appena viene salvato.
* Nella seconda fase, l&#39;app desktop carica un file aggiornato AEM server dopo un ritardo predefinito (ad esempio, 30). Questa operazione si verifica in background. Utilizzate l&#39;opzione **Mostra stato sincronizzazione file in background** per visualizzare lo stato dell&#39;operazione di caricamento.

## Avvisi importanti {#important-notices}

**Caricamento cartella.** Si consiglia di utilizzare la nuova funzione di caricamento delle cartelle per caricare in AEM cartelle gerarchiche più grandi, invece di utilizzare una copia/trascinamento e rilasciare in un archivio AEM montato a livello di Finder/Explorer. Quando si utilizza la funzione di caricamento delle cartelle, l&#39;app desktop comunica direttamente con AEM e quindi ha un controllo molto migliore sul processo complessivo.

**Mantenete AEM sessione disponibile.** AEM&#39;app desktop dipende da una sessione aperta  server AEM Assets per garantire il corretto funzionamento. Per gli utenti che lavorano con l&#39;app desktop ogni giorno, si consiglia di disinstallare  AEM Assets alla fine della giornata per forzare la disconnessione, e poi &quot;Mount  AEM Assets&quot; la mattina per assicurarsi che siano connessi e la condivisione di rete sia operativa.

**Disattivate &quot;Icon Preview&quot; nel Finder.** Per una ricerca efficace di grandi cartelle con il Finder, soprattutto con una scarsa connettività di rete, assicurarsi che sia &quot;Icon&quot; che &quot;Icon Preview&quot; sia disattivato. In caso contrario, il Finder inizierà a scaricare ciascuna risorsa in una cartella per generare un’anteprima di piccole dimensioni, che può comportare prestazioni scadenti e un utilizzo elevato della larghezza di banda (CQ-4219779)

* In Finder, andate  cartella di rete condivisa AEM Assets
* Fare clic con il pulsante destro del mouse sul punto di montaggio DAM
* Seleziona Mostra opzioni visualizzazione
* Deselezionare &quot;Mostra anteprima icona&quot;
* Fare clic su &quot;Usa come predefinito&quot;

**Pulizia della cache durante la connessione a un nuovo server AEM.** Se l&#39;app desktop si connette a un altro server AEM con lo stesso URL, la cache non viene cancellata automaticamente. Cancellate la cache manualmente per garantire le operazioni corrette. Tenete presente che questo accade in genere nei test, quando AEM installazioni possono essere sostituite mentre sono in esecuzione sullo stesso URL (CQ-4216982)

**Utilizzare certificati SSL con firma CA.** AEM&#39;app desktop non supporta i certificati SSL autofirmati quando ci si connette a AEM tramite una connessione protetta HTTPS. Per tali connessioni è necessario un certificato firmato da CA sul server. (CQ-87941)

## Problemi noti {#known-issues}

* Generale:
   * Gli URL del server devono essere indirizzati al server senza un percorso (ad es. `http://server`, `https://server`, `http://server:port` o `https://server:port`). I percorsi e le sottocartelle di contesto diversi da /content/dam non sono supportati (CQ-89343, CQ-87272)
* Nomi file / localizzazione:
   * I nomi di file e cartelle con caratteri riservati non vengono gestiti correttamente. Accertatevi di utilizzare nomi di file e cartelle che soddisfino i requisiti AEM (CQ-93361, CQ-93308, CQ-89276, CQ-4217183)
   * Alcune applicazioni come  Adobe Illustrator potrebbero creare file con nomi non supportati in AEM. Ad esempio, l&#39;aggiunta di `Converted` dopo la conversione di un file, che ne impedisce il caricamento (CQ-4216985)
   * Le risorse con nomi internazionali possono essere visualizzate e scomparire ogni pochi secondi
* Check-in e check-out:
   * Una risorsa estratta da un utente non può essere aperta per un altro utente, né tramite l’azione Apri dall’interfaccia utente touch, né direttamente sul desktop. Alcune applicazioni potrebbero segnalarlo come bloccato, ma anche danneggiato o anche appeso durante il tentativo di aprire. (CQ-4199234)
   * La modifica simultanea di file da parte di più utenti potrebbe causare la perdita di alcune modifiche. La soluzione consiste nell&#39;utilizzare la funzionalità di check-in e check-out per impedire a più utenti di modificare lo stesso file (CQ-97035)
   * Alcune applicazioni non supportano correttamente il flag di sola lettura che consente all&#39;utente di salvare un file estratto da un altro utente. Il file modificato non viene trasferito finché l&#39;altro utente non lo controlla. Entrambe le modifiche sono disponibili in AEM come versioni diverse della risorsa (CQ-89551, CQ-87572, CQ-89615)
   * Lo stato di check-out e di sola lettura viene riportato in modo indipendente nel Finder. Quando un utente estrae una risorsa, si ottengono quindi 2 icone di blocco (CQ-89507)
* Integrazione con il Finder:
   * Quando si trascinano o si trascinano file di grandi dimensioni, è possibile che si verifichi un timeout durante il trasferimento dei file in background. Questo determina un `Error - 36`. La soluzione alternativa consiste nel trascinare o aprire di nuovo la risorsa (CQ-4219628)
   * Il ricaricamento manuale delle cartelle non sempre funziona. Soluzione:  wait   30 secondi per aggiornare automaticamente la cartella. (CQ-97389)
   * Ulteriori informazioni sulla risorsa... è limitato alle selezioni di file singoli (CQ-89542, CQ-87656)
   * Apri in  AEM Assets... è limitato alle selezioni di singoli file e cartelle (CQ-83382)
   * Errore durante la ridenominazione di risorse senza estensione (CQ-4218971)
* Funzionalità Copia/Incolla: Incolla è disponibile se non è stata copiata alcuna risorsa negli Appunti
* Windows:
   * I file con flussi di dati alternativi (ADS) sono supportati solo completamente su NTFS. Copiando tali file nella condivisione WebDAV fornita dall&#39;app desktop si verificherà una finestra di dialogo di avviso che avvisa l&#39;utente che il file ha proprietà che non possono essere copiate nella nuova posizione. In genere va bene, in quanto le proprietà sono relative solo a una particolare applicazione sul desktop dell&#39;utente e non hanno nulla a che fare con il contenuto effettivo del file (CQ-103770) (Win)
   * l&#39;app desktop in Windows deve essere installata dall&#39;utente che la utilizza (CQ-4216389) (win)
   * L&#39;app può arrestarsi in modo anomalo quando si fa clic sul pulsante Riprova in caso di caricamento non riuscito in determinate circostanze dopo aver ripreso il caricamento batch quando disconnesso (CQ-4251884) (Win)

## Risorse utili {#helpful-resources}

* [Documentazione AEM](https://helpx.adobe.com/it/support/experience-manager/6-4.html)
* [Usa AEM&#39;app desktop v1.x](use-app-v1.md)
* [Best practice per AEM app desktop v1.x](best-practices-for-v1.md)

## Matrice di compatibilità e prerequisiti {#compatibilitymatrix}

AEM&#39;app desktop funziona con diverse versioni di AEM. Visualizzare la matrice di compatibilità per le versioni supportate.

| Versione | Revisione | Data di rilascio | Compatibilità |
|--- |--- |--- |--- |
| 1,10 | 1.10.0.3 (Mac e Win) | 31 agosto 2018 | AEM 6.5; AEM 6.4 SP1; AEM 6.3 SP2; AEM 6.2 SP1 CFP2+; AEM 6.1 SP2 CFP7+ |
| 1,9 | 1.9.1.1 (Mac e Win) | 21 giugno 2018 | AEM 6.4; AEM 6.3 SP1; AEM 6.2 SP1 CFP2+; AEM 6.1 SP2 CFP7+ |
| 1,8 | 1.8.1.0 (Mac e Win) | 28 marzo 2018 | AEM 6.4; AEM 6.3 SP1; AEM 6.2 SP1 CFP2+; AEM 6.1 SP2 CFP7+ |
| 1,7 | 1.7.0.3 (Mac e Win) | 10 gennaio 2018 | AEM 6.3 SP1; AEM 6.2 SP1 CFP2+; AEM 6.1 SP2 CFP7+ |
