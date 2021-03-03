---
title: Note sulla versione dell’app desktop v1.10
description: Dettagli sulla versione, miglioramenti, nuove funzioni, compatibilità e collegamenti per il download dell’app desktop AEM versione 1.10.
translation-type: tm+mt
source-git-commit: 4870615ed40226964d077d6666b83b85b73da180
workflow-type: tm+mt
source-wordcount: '3897'
ht-degree: 1%

---


# [!DNL Adobe Experience Manager] note sulla versione dell’app desktop v1.10  {#aem-desktop-app-release-notes}

Per la versione v1.x dell’app desktop, sono riportati di seguito i collegamenti per il download e le informazioni sulla compatibilità AEM.

| Prodotti | App desktop [!DNL Adobe Experience Manager]  |
|--- |--- |
| Versione | 1.10 (1.10.0.6 su Mac e 1.10.0.3 su Windows) |
| Tipo | Versione secondaria |
| Data | 1.10.0.6 (Mac): 15 aprile 2020; 1.10.0.3 (Win): 31 agosto 2018 |
| URL di download | [Mac OS X a 64 bit](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/adobe/aem-desktop-app/aem-desktop-osx-1.10.0.6.dmg);  [Windows a 32 bit](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/adobe/aem-desktop-app/aem-desktop-win32-1.10.0.3.exe);  [Windows a 64 bit](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/adobe/aem-desktop-app/aem-desktop-win64-1.10.0.3.exe) |
| Compatibilità | AEM 6.5.x; AEM 6.4.x; AEM 6.3 SP2; AEM 6.2 SP1 CFP2+; AEM 6.1 SP2 CFP7+ |

>[!NOTE]
>
>Il limite di dimensione della cache non viene applicato. Quando l’app desktop viene avviata, la dimensione della cache viene calcolata una volta e viene visualizzata una notifica se la dimensione è vicina al limite predefinito.

## Requisiti di sistema e prerequisiti {#system-requirements-and-prerequisites}

[!DNL Adobe Experience Manager]L’app desktop è compatibile con i seguenti sistemi operativi:

* Mac OS X 10.10 o successivo, con correzioni di bug più recenti.

* Windows 10 con Service Pack e correzioni di bug più recenti.

>[!NOTE]
>
>Windows 7 non è più supportato. Vedere [l&#39;articolo su EOL di Windows 7](https://support.microsoft.com/en-us/help/4057281/windows-7-support-ended-on-january-14-2020).

Adobe consiglia vivamente di utilizzare l’ultima versione dell’app desktop AEM per usufruire delle funzionalità più recenti, delle correzioni di bug più recenti e delle migliori prestazioni possibili.

La versione dell’app desktop AEM che intendi installare nel computer locale richiede una versione specifica del server AEM/componenti aggiuntivi lato server (Service Pack, hotfix o feature pack). Assicurati che il server AEM sia configurato correttamente prima di connetterti ad esso per la prima volta. Se hai bisogno di aiuto, contatta il tuo amministratore AEM.

Consulta la [matrice di compatibilità dettagliata](#compatibilitymatrix) alla fine di questo documento per valutare i prerequisiti per la configurazione.

## Novità dell’app desktop v1.10 {#what-s-new-in-aem-desktop-app}

L’app desktop AEM 1.10 si concentra sul miglioramento dell’esperienza utente in caso di caricamenti di grandi dimensioni, informazioni sulle operazioni in background e sull’esperienza ottimizzata durante l’apertura di risorse con file collegati (come InDesign).

>[!NOTE]
>
>Se utilizzi macOS 10.15.4 o versioni successive, utilizza almeno la versione 1.10.0.6 dell’app. Questa versione della patch è conforme ai [requisiti di notarizzazione Apple](https://developer.apple.com/news/?id=04102019a).

**Modifica locale / Check-Out**: Il caricamento automatico delle modifiche salvate nelle risorse può essere disattivato nella finestra di stato. In questo modo l&#39;utente può continuare a lavorare sui file e salvare le modifiche e poi, quando sono pronti, decidere di caricare tutte le modifiche.

**Finestra** dello stato delle risorse semplificata. La finestra di stato è stata semplificata. La scheda [!UICONTROL Uploads] ora mostra sia le singole risorse, sia i caricamenti di cartelle o in blocco. La scheda Caricamenti in blocco precedente è stata rimossa.

**Icona dell’applicazione per indicare i caricamenti in blocco**. L’icona dell’applicazione indica che è in corso un caricamento in serie mostrando una sovrapposizione &quot;transfer&quot;.

**Notifiche relative ai conflitti di aggiornamento**. Quando l&#39;applicazione rileva un conflitto durante il tentativo di aggiornamento di una risorsa, mostra una notifica, in modo che l&#39;utente possa rivedere tale situazione senza dover monitorare la finestra di stato. Quando l&#39;applicazione viene avviata, controlla tutti i conflitti in modo che l&#39;utente possa risolverli.

**Gestione migliore delle perdite di connessione**. I caricamenti in blocco verranno messi in pausa in caso di perdita di connessione e l&#39;utente potrà riprendere in un secondo momento. È disponibile un&#39;opzione [!UICONTROL Retry] per riprovare a eseguire il caricamento non riuscito di un singolo file.

## Istruzioni di installazione {#installation-instructions}

Per istruzioni dettagliate, consulta [Installare e configurare l’app desktop AEM](install-configure-app-v1.md).

## Miglioramenti apportati alle versioni precedenti {#enhancements-in-the-previous-versions}

Questa versione estende e sostituisce le versioni precedenti dell’ app desktop [!DNL Experience Manager] , che fornivano i seguenti miglioramenti chiave:

* **Versione 1.9/1.9.1**: caricamenti riattivabili, finestra di stato migliorata, icone dell&#39;applicazione che indicano lo stato dell&#39;applicazione / connessione, preacquisizione delle risorse collegate per i file InDesign.

* **Versione 1.8**: migliore controllo delle dimensioni della cache per l&#39;utente, migliore esperienza di accesso per SAML/SSO su Windows, supporto del proxy di rete .pac su Mac e problemi segnalati dai clienti.

* **Versione 1.7**: miglioramenti della stabilità e della logica di caching, migliore supporto per i proxy di rete e possibilità di ripulire i file interni dopo la disinstallazione.

* **Versione 1.6**: miglioramenti nel processo di accesso per diverse configurazioni di sicurezza AEM e stabilità e prestazioni dell’applicazione.

* **Versione 1.5**: stabilità dell&#39;applicazione e resilienza a vari problemi di rete, migliore supporto.

* **Versione 1.4**: la possibilità di caricare cartelle gerarchiche in background con il monitoraggio dello stato.

* **Versione 1.3**: miglioramenti delle prestazioni e stabilità per l’accesso ai file e il salvataggio delle modifiche su AEM, soprattutto dalle applicazioni desktop Creative Cloud, come InDesign, Illustrator o Photoshop. L&#39;obiettivo era quello di fornire agli utenti un&#39;esperienza più simile a quella su desktop locale quando lavorano con i file, gestendo contemporaneamente le operazioni di trasferimento dei dati di rete in background.

### Miglioramenti disponibili a partire dall’app desktop AEM 1.9 {#Enhancements-Available-Since-AEM-Desktop-App-19x}

[!DNL Adobe Experience Manager] l’app desktop 1.9.1 è stata una patch release per risolvere alcuni problemi chiave dei clienti relativi al checkout delle risorse e alla copia dei file dalla condivisione di rete a una directory locale.

* Le risorse estratte da un utente non devono essere disponibili per la modifica per altri utenti (CQ-4246009)

* È supportata la copia dalla cartella mappata in una cartella locale quando la cartella utente si trova in una partizione disco separata (CQ-4243978)

L’app desktop AEM 1.9 si concentra sul miglioramento dell’esperienza utente in caso di caricamenti di grandi dimensioni, informazioni sulle operazioni in background e sull’esperienza ottimizzata quando si aprono risorse con file collegati (come InDesign).

**Caricamenti**
riutilizzabiliPer i caricamenti, soprattutto intorno a file di grandi dimensioni, è disponibile un’opzione per sospenderli/riavviarli nella nuova finestra Stato risorsa.

**Finestra**
di stato delle risorse migliorataUna finestra di stato delle risorse migliorata fornisce le seguenti informazioni sulle risorse.

[!UICONTROL Changes]

* Visualizza le modifiche attualmente in coda.

* Mostra i caricamenti in corso, tra cui una barra di avanzamento, la frequenza di trasferimento, la dimensione totale del file e le dimensioni trasferite finora.

* Caricamenti completati visualizzati con trasferimento totale e tasso finale.

* I caricamenti non riusciti vengono visualizzati insieme a un messaggio di errore e alle informazioni di trasferimento, se disponibili.

* I caricamenti che hanno avuto esito negativo per 3 volte visualizzeranno un messaggio di errore.

* File in conflitto visualizzati con un’icona su cui l’utente può fare clic. Facendo clic sull’icona viene visualizzata una finestra di dialogo con una spiegazione e due opzioni:

   * [!UICONTROL Keep Mine] carica immediatamente il file sul server.

   * [!UICONTROL Overwrite Mine] elimina immediatamente il file locale e ne scarica una nuova copia dal server.

[!UICONTROL Downloads]

* Visualizza i download in corso, inclusa una velocità di trasferimento e le dimensioni trasferite finora.

* Download completati visualizzati con trasferimento totale, tasso finale e icona che aprirà il file quando il visitatore farà clic su di esso (disponibile solo per file singoli).

* Download non riusciti visualizzati con un messaggio di errore e informazioni di trasferimento, se disponibili.

* Piè di pagina mostra il numero totale di file scaricati e la velocità media di trasferimento.

* Se un utente sceglie di aprire o modificare più file dall&#39;interfaccia Web [!DNL Experience Manager Assets], verranno raggruppati insieme. Ad esempio, myasset.jpeg e altri 4 file.

* Quando si scaricano i documenti InDesign, comprese le risorse collegate memorizzate in AEM Assets, l’app desktop scarica prima tutte le risorse collegate prima di aprire il documento [!UICONTROL Adobe InDesign] e indica il download delle risorse collegate. Ad esempio, 5 su 24.

[!UICONTROL Bulk Uploads]

Il caricamento di gerarchie di cartelle di grandi dimensioni tramite [!UICONTROL Create] > [!UICONTROL Upload Folder] nell’interfaccia web di AEM oppure la copia e la selezione di &quot;Incolla risorse&quot; nel Finder o in Esplora risorse nel menu di scelta rapida dell’app desktop attiverà l’utilizzo di questa finestra di dialogo.

* Visualizza i caricamenti in corso, inclusa una barra di avanzamento e il nome del file attualmente trasferito.

* I caricamenti in corso includono un&#39;icona che annulla il caricamento quando fai clic su di esso. Il trasferimento verrà interrotto al termine del trasferimento del file.

* I processi di trasferimento non riusciti vengono visualizzati con un messaggio di errore (solo se l’intero trasferimento non riesce).

* Se un singolo file non viene trasferito, viene visualizzato nella scheda come un errore. In caso contrario, i singoli file non verranno visualizzati nella scheda * solo una voce per l’intero caricamento.

**Icone per indicare lo stato delle operazioni in background**

L’icona dell’applicazione indica lo stato delle operazioni in background per fornire un migliore segnale visivo agli utenti. Ad esempio, quando l’applicazione non è connessa ad AEM l’icona sarà disattivata, quando c’è un caricamento attivo mostra una sovrapposizione di &quot;sincronizzazione&quot;, ecc.

**Recupero preliminare delle risorse collegate**

Per migliorare l’esperienza utente quando si lavora con documenti InDesign che includono risorse collegate memorizzate in AEM, l’app desktop tenterà di preacquisire questi file collegati nella cache locale prima di scaricare e aprire il documento InDesign. In questo modo l’utente avrà i file collegati disponibili localmente e non dovrà aspettare più a lungo quando accederà a questi in InDesign (nel pannello Collegamenti).
Il pre-recupero funziona solo se AEM riconosce i collegamenti sul lato server. Una risorsa con collegamenti riconosciuti avrà un elenco di &quot;Riferimenti&quot; elencati nella vista Proprietà della risorsa InDesign.

### Miglioramenti disponibili dall’app desktop AEM 1.8.x {#enhancements-available-since-aem-desktop-app-18x}

Miglioramenti aggiunti alla versione 1.8.1 dell’app desktop AEM per l’accesso rapido dopo l’apertura di più file contemporaneamente dall’interfaccia utente di AEM alla versione 1.8 (CQ-4237747, CQ-4238780). I miglioramenti nell’app desktop AEM 1.8 sono:

* Memorizzazione in cache: nuova interfaccia utente per la gestione della cache delle app desktop AEM (CQ-4208690), tra cui:

   * visualizza la dimensione corrente della cache

   * definire la dimensione massima della cache prima dell’invio di una notifica

   * La dimensione della cache viene controllata solo all’avvio dell’app desktop e viene visualizzata una notifica se sta raggiungendo il limite configurato

   * il pulsante di cancellazione della cache è ora disponibile nella nuova interfaccia utente

* Accesso: (Win) È stato corretto l&#39;accesso all&#39;istanza AEM configurata per l&#39;utilizzo di SAML e SSL (CQ-4216353)

* Rete:

   * alla scadenza di una sessione AEM, l’utente ora riceve una notifica e può fare clic sulla notifica per effettuare nuovamente l’accesso (CQ-4202028).

   * (Mac) Aggiungi il supporto per la connessione ad AEM tramite la configurazione proxy .pac (CQ-4233430).

   * (Win) Correggi i problemi con la finestra di dialogo Avanzate - URL di accesso (CQ-4236061).

* Correzioni di bug:

   * Finestra di dialogo Ulteriori informazioni risorsa: a volte la barra delle azioni non era visibile (CQ-4208540).

   * (Win) È ora possibile sincronizzare il file dopo il ripristino di una versione precedente dall’interfaccia utente di AEM Assets (CQ-4216411).

### Miglioramenti disponibili dall’app desktop AEM 1.7 {#Enhancements-Available-Since-AEM-Desktop-App-17}

* Stabilità:

   * È stata migliorata la stabilità quando l&#39;app desktop AEM si connette a un server AEM sovraccarico (CQ-4224803).

   * È stata migliorata la stabilità quando vengono richiesti molti file (CQ-4224212).

   * È stato migliorato l’aggiornamento delle risorse con ulteriore controllo (CQ-4228291).

* Memorizzazione in cache:

   * Correggere gli errori del disco e i problemi di apertura quando si aprono i file in Photoshop, InDesign, Finder (CQ-4223993, CQ-4217603, CQ-4223717).

   * È stato migliorato il caching per evitare binari di dimensioni zero (CQ-4216599).

* Accesso: Consenti la connessione con secureSSL disabilitato per configurazioni speciali (come i certificati rilasciati localmente) (CQ-4223949).

* Rete: È stato migliorato il supporto per la connessione tramite proxy di rete (CQ-4223477, CQ-4221280, CQ-4206854).

* Installazione e disinstallazione:

   * (Win) Disinstallazione di Cleaner (CQ-4220906).

   * [Windows 32] bitInstaller non riesce a installare Microsoft .NET Framework v. 4.5 (CQ-4218084).

   * (Mac) Script manuale per rimuovere completamente i file dell&#39;app desktop (CQ-4216489).

>[!NOTE]
>
>I problemi rilevati nei carichi beta dell’app desktop AEM 1.7 (che non erano presenti nella versione 1.6 non sono riportati nelle note sulla versione).

### Miglioramenti disponibili dall’app desktop AEM 1.6 {#Enhancements-Available-Since-AEM-Desktop-App-16}

* Documentazione: Nuova documentazione [Best practice per l&#39;app v1.x](/help/best-practices-for-v1.md) .

* Miglioramento del processo di accesso ad AEM:

   * Migliorare la gestione SAML * le regole di relax (CQ-4202781).

   * Aggiungi la funzionalità per configurare un URL di accesso separato nelle Preferenze (CQ-4214052, CQ-4214051).

* Utilizzabilità: Notifica all’utente quando la risorsa viene ancora scaricata per le risorse più grandi (CQ-4216284).

* Rete:

   * Memorizzazione in cache DNS (CQ-4210176).

   * È supportata la connessione tramite proxy su Windows (CQ-4206854).

* Memorizzazione in cache e accesso alla condivisione di rete nel Finder / Explorer:

   * Icona a forma di lucchetto ora visibile per le risorse estratte su Windows 10 (CQ-90957).

   * Il contenuto della cartella potrebbe scomparire o riapparire nella condivisione di rete (CQ-4209160, CQ-4210180).

   * Errore durante il caricamento del file a causa di un conflitto rilevato nello stato della coda di caricamento (CQ-4215727).

   * Durante l&#39;apertura di più file dalla cartella dell&#39;app desktop in PS, potrebbero essere visualizzati messaggi troncati o incompleti (CQ-4216276).

* Correzioni di stabilità e prestazioni:

   * Prestazioni migliorate durante la navigazione nelle cartelle con molte risorse (CQ-4214933).

   * l&#39;app desktop 1.5 può rallentare la macchina desktop nel tempo (CQ-4209159).

   * La funzione di visualizzazione dello stato della coda funziona solo per l’utente che ha installato l’app (CQ-4212199).

   * (Windows) Assicurati che il programma di installazione a 32 bit non contenga codice a 64 bit (CQ-4217406).

* Problemi selezionati rilevati e risolti nella versione 1.6 Beta:

   * Utilizzo elevato della CPU (CQ-4218070).

   * Errore durante il caricamento in AEM (CQ-4217006) durante il trascinamento dei file.

### Miglioramenti disponibili dall’app desktop AEM 1.5 {#Enhancements-Available-Since-AEM-Desktop-App-15}

**Versione 1.5.1.5 per Mac OS X:** la versione 1.5.1.5 offre i seguenti vantaggi:

* Nuove funzioni e miglioramenti: Aggiungi la funzionalità Copia/Incolla all&#39;integrazione del Finder per consentire il trasferimento diretto da Desktop ad AEM (CQ-4208158).

* Bugfix:

   * È stato risolto il problema dell’errore 43 che si verificava a volte durante la ridenominazione delle risorse (CQ-4207900).

   * Il ripristino di una versione precedente dalla timeline in AEM non aggiorna la risorsa nel Finder (CQ-4205194).

   * l’app desktop si blocca quando si navigano in directory nidificate di grandi dimensioni (CQ-4208539).

   * il punto di montaggio dell’app desktop ora è /Volumes/DAM, quindi è coerente per tutti gli utenti (CQ-4208159).

   * Il posizionamento di un file in InDesign per la prima volta attiva un avviso di aggiornamento (CQ-4207454).

Nota sugli avvisi sui collegamenti: Le applicazioni Creative Cloud (come InDesign) creano uno &quot;snapshot&quot; dell&#39;ora dell&#39;ultima modifica dell&#39;elemento al momento in cui viene posizionato. Se tale data cambia in un momento successivo, l’app Adobe Creative Cloud segnala che i collegamenti sono obsoleti. Questo è riportato in un paio di modi:

* All’avvio dell’app Adobe Creative Cloud, verrà visualizzata una finestra di dialogo per informare l’utente che le risorse collegate sono obsolete e per richiedere all’utente di intervenire.

* Se l’app Adobe Creative Cloud è già in esecuzione, sulla risorsa collegata viene visualizzata un’icona di avviso con un triangolo giallo.

Questo comportamento è lo stesso per le risorse sul disco locale e le risorse in una directory montata su AEM Desktop, con le seguenti eccezioni:

* Se una risorsa inserita viene modificata da un altro utente, l’icona di avviso comparirà la prima volta che altri utenti aprono un documento contenente la risorsa inserita. Ciò avverrà solo se la risorsa inserita è già stata memorizzata nella cache locale.

* Se un utente modifica una risorsa inserita tramite la directory montata del desktop AEM e quindi cancella la propria cache locale, la risorsa inserita verrà segnalata come obsoleta.

Entrambi questi casi sono attesi e sono effetti collaterali dell’architettura di &quot;sincronizzazione ritardata&quot; di AEM Desktop.

**Versione 1.5.0.x per Mac OS X e Windows:** questa versione dell’app desktop AEM offre i seguenti vantaggi:

* Stabilità e resilienza migliori rispetto alle questioni legate alla rete.

   * Mappatura più stabile delle cartelle di AEM Assets (CQ-103276, CQ-4204669, CQ-4203957).

   * Gestione migliore dei file memorizzati nella cache (CQ-4204336, CQ-4206263).

   * È stata migliorata la gestione del download/caricamento di file di grandi dimensioni con dimensioni superiori a 2 GB (CQ-4206438).

   * È stato corretto l&#39;&quot;Errore 36&quot; durante lo spostamento o la ridenominazione di un numero maggiore di file nel Finder (CQ-4204640).

* Ottimizzazioni nelle comunicazioni di rete con AEM Server (CQ-4204974, CQ-100903).

* Maggiore affidabilità nell’apertura, posizionamento e salvataggio delle risorse AEM nelle app Creative Cloud (CQ-4203968, CQ-4205511, CQ-103543, CQ-4207141, CQ-90980).

* Supporto migliorato: opzione per cancellare la cache (CQ-4202541), facile accesso ai log (CQ-4202340, CQ-4204673).

* Altre correzioni:
   * Migliore supporto per risorse e cartelle che contengono caratteri giapponesi nelle impostazioni di nome/lingua non inglese (CQ-4195433, CQ-4205793, CQ-4199446).

   * Gestione migliore dell&#39;accesso con SSL (CQ-4200217).

   * Installazione più affidabile (CQ-4200793).

   * Vari miglioramenti nella stabilità (CQ-4207539, CQ-4200378).

   * Gestione migliore dell’URL di AEM Assets nelle preferenze (CQ-97388).

### Miglioramenti disponibili dall’app desktop AEM 1.4 {#Enhancements-Available-Since-AEM-Desktop-App-14}

* Caricamento semplificato di cartelle gerarchiche tramite la nuova azione Crea > Carica cartella nell’interfaccia utente touch.
   * L’azione avvia un’operazione di caricamento cartelle eseguita dall’app desktop
   * L’app desktop analizza in background la gerarchia delle cartelle specificata sul desktop e carica i file in AEM Assets
   * L&#39;utente può monitorare l&#39;avanzamento nella nuova finestra Stato coda di caricamento con la barra di avanzamento per le operazioni in corso
   * Lo stato della coda di caricamento fornisce anche informazioni più utili per la risoluzione dei problemi (ad esempio, nessuna connessione al server)
* Nuova azione Modifica nell’interfaccia utente touch che combina le operazioni Check-Out e Open in un’unica
* Raggruppamento ottimizzato delle azioni relative al desktop nell’interfaccia utente touch (AEM 6.3)
* Compatibilità migliorata con le ultime versioni del sistema operativo
* Correzioni riportate dal cliente

### Miglioramenti disponibili dall’app desktop AEM 1.3 {#Enhancements-Available-Since-AEM-Desktop-App-13}

* Maggiore efficienza. Gli utenti trascorrono meno tempo in attesa del completamento delle operazioni di rete.
* Integrazione del Finder migliorata, che fornisce maggiore stabilità e accesso alle funzioni, come le miniature.
* Memorizzazione in cache e miglioramenti delle prestazioni.
* Migliore supporto per il salvataggio diretto dalle app desktop (PS, ID, AI e così via).
* Integrazione migliorata con Mac OS (protocollo dell&#39;unità di rete locale modificato da WebDAV a SMB1 più stabile).
* L’app desktop si connette con il server AEM utilizzando il protocollo RESTful HTTP nativo di AEM.
* I file vengono salvati localmente per primi e quindi caricati nuovamente in AEM in background dopo un tempo predefinito (30 sec). Questo riduce il tempo necessario per salvare i file.
* Gestione migliore delle applicazioni desktop che utilizzano operazioni di file intermedi per salvare un file (salvataggi parziali e file temporanei), che consente alla timeline di AEM Assets di visualizzare le informazioni corrette sulla versione e sul caricamento delle risorse.
* Viene fornita la finestra di dialogo per tenere traccia dello stato delle attività di caricamento in background.

## Elenco delle modifiche {#list-of-changes}

### Punto di montaggio su Mac {#mount-point-on-mac}

A partire da MacOS 10.12 (Sierra), Apple ha cambiato le autorizzazioni sulla cartella /Volumes utilizzata per montare le unità e i dispositivi di rete in modo più restrittivo. La creazione di un nuovo punto di montaggio richiedeva diritti amministrativi. Questo problema è stato risolto in MacOS 10.12.5.

Poiché l’app desktop AEM deve essere eseguita per gli utenti che non dispongono dei diritti di amministratore sul computer locale, il punto di montaggio per l’archivio di AEM Assets è stato modificato in 1.4 e 1.5 in una sottocartella DAM nella cartella locale dell’utente su MacOS (CQ-104183).

Poiché la cartella /Volumes non richiede più i diritti amministrativi, questa modifica è stata ripristinata in 1.5.1. Questo consente anche di condividere documenti InDesign che hanno inserito risorse AEM tra gli utenti MacOS.

### Modifica del protocollo (dalla versione 1.3) {#protocol-change-since}

* Mac OS X:
   * Il protocollo dell&#39;unità di rete locale per l&#39;integrazione del desktop OS X è stato modificato in SMB1 da WebDAV.
   * L&#39;archivio AEM montato con l&#39;app desktop sarà visibile come unità di rete &quot;smb&quot; nel Finder, invece di un&#39;unità WebDAV.
* Windows:
   * Il protocollo dell&#39;unità di rete locale per le integrazioni desktop Windows rimane; AEM verrà montato come condivisione WebDAV.
* Per entrambe le piattaforme (Windows e Mac):
   * Il protocollo per accedere/scaricare le risorse e caricare le modifiche in AEM è stato modificato nel protocollo nativo di AEM, che è un protocollo RESTful basato su HTTP. Offre un maggiore controllo sulle operazioni di rete ed è più compatibile con l&#39;infrastruttura di rete.

>[!NOTE]
>
>In Mac OS X, la modifica del protocollo dell&#39;unità di rete locale da WebDAV a SMB1 comporta un percorso locale diverso per la stessa risorsa nel repository. Questo potrebbe avere un impatto sui collegamenti a file inseriti nelle applicazioni Adobe Creative Cloud tramite il comando &quot;Place&quot;. Per ulteriori informazioni, consulta [Usa app desktop AEM](use-app-v1.md) .

### Gestione dei file (a partire da 1.3) {#file-handling-since}

* Le cartelle vengono aggiornate automaticamente dopo un ritardo predefinito (attualmente 30 anni).
* I file estratti da altri utenti sono contrassegnati come di sola lettura.
* I file vengono salvati in una posizione dell&#39;unità di rete montata tramite l&#39;app desktop in due fasi.
* Nella prima fase, un file viene salvato localmente. In questo modo, l’utente che salva il file non deve attendere il completo trasferimento del file ad AEM e può riprendere a funzionare non appena il file viene salvato.
* Nella seconda fase, l’app desktop carica un file aggiornato sul server AEM dopo un ritardo predefinito (ad esempio, 30 ). Questa operazione si verifica in background. Utilizza l&#39;opzione **Mostra stato sincronizzazione file in background** per visualizzare lo stato dell&#39;operazione di caricamento.

## Avvisi importanti {#important-notices}

**Caricamento cartella.** Si consiglia di utilizzare la nuova funzionalità Caricamento cartelle per caricare cartelle più grandi e gerarchiche in AEM invece di utilizzare una copia/trascinamento e rilasciare in un archivio AEM montato a livello di Finder/Explorer. Quando utilizzi la funzione di caricamento cartelle, l’app desktop comunica direttamente con AEM e quindi ha un controllo molto migliore sul processo complessivo.

**Mantieni disponibile la sessione AEM.** L’app desktop AEM dipende da una sessione aperta al server AEM Assets per garantire il corretto funzionamento. Per gli utenti che lavorano quotidianamente con l’app desktop, si consiglia di smontare AEM Assets alla fine della giornata per forzare la disconnessione, e poi di installare &quot;AEM Assets&quot; la mattina per assicurarsi di aver effettuato l’accesso e che la condivisione di rete sia operativa.

**Disattiva &quot;Icon Preview&quot; nel Finder.** Per la navigazione performante di grandi cartelle con Finder, soprattutto con scarsa connettività di rete, assicurati che sia &quot;Icon&quot; che &quot;Icon Preview&quot; siano disattivati. In caso contrario, il Finder inizierà a scaricare ogni risorsa in una cartella per generare una piccola anteprima, che può portare a prestazioni scadenti e un elevato utilizzo della larghezza di banda (CQ-4219779)

* In finder, vai alla cartella di rete condivisa di AEM Assets
* Fai clic con il pulsante destro del mouse sul punto di montaggio DAM
* Seleziona Mostra opzioni visualizzazione
* Deseleziona &quot;Mostra anteprima icona&quot;
* Fai clic su &quot;Usa come predefiniti&quot;

**Pulisci la cache quando ti connetti a un nuovo server AEM.** Se l’app desktop si connette a un altro server AEM con lo stesso URL, la cache non viene cancellata automaticamente. Elimina la cache manualmente per garantire le operazioni corrette. Questo accade in genere nei test, quando le installazioni AEM possono essere sostituite mentre sono in esecuzione sullo stesso URL (CQ-4216982)

**Utilizzare certificati SSL con firma CA.** L’app desktop AEM non supporta certificati SSL autofirmati quando ci si connette ad AEM tramite una connessione protetta HTTPS. Per tali connessioni è necessario un certificato con firma CA sul server. (CQ-87941)

## Problemi noti {#known-issues}

* Generale:
   * Gli URL del server sono necessari per puntare al server senza un percorso (ad esempio `http://server`, `https://server`, `http://server:port` o `https://server:port`). I percorsi di contesto e le sottocartelle diverse da /content/dam non sono supportati (CQ-89343, CQ-87272)
* Nomi di file / localizzazione:
   * I nomi di file e cartelle con caratteri riservati non vengono gestiti correttamente. Assicurati di utilizzare nomi di file e cartelle che soddisfano i requisiti AEM (CQ-93361, CQ-93308, CQ-89276, CQ-4217183)
   * Alcune applicazioni come Adobe Illustrator possono creare file con nomi non supportati in AEM. Ad esempio, l’aggiunta di `Converted` dopo la conversione di un file, che lo impedisce di essere caricato (CQ-4216985)
   * Le risorse con nomi internazionali possono apparire e scomparire ogni pochi secondi
* Check-in e check-out:
   * Una risorsa estratta da un utente non è possibile aprirla per un altro utente, né tramite l&#39;azione Apri dall&#39;interfaccia utente touch, né direttamente sul desktop. Alcune applicazioni potrebbero segnalarlo come bloccato, ma anche danneggiato o anche appeso durante il tentativo di aprire. (CQ-4199234)
   * La modifica simultanea di file da parte di più utenti può causare la perdita di alcune modifiche. La soluzione consiste nell&#39;utilizzare la funzionalità di check-in e check-out per impedire a più utenti di modificare lo stesso file (CQ-97035)
   * Alcune applicazioni non supportano correttamente il flag di sola lettura che consente all&#39;utente di salvare un file estratto da un altro utente. Il file modificato non viene trasferito finché l&#39;altro utente non controlla nel file. Entrambe le modifiche sono disponibili in AEM come versioni diverse della risorsa (CQ-89551, CQ-87572, CQ-89615)
   * Lo stato estratto e di sola lettura viene riportato in modo indipendente nel Finder. Questo si traduce in 2 icone di blocco quando un utente estrae una risorsa (CQ-89507)
* Integrazione del Finder:
   * Quando si trascinano o si rilasciano file di grandi dimensioni, il Finder potrebbe causare un timeout durante il trasferimento dei file in background. Questo si traduce in un `Error - 36`. La soluzione consiste nel trascinare/rilasciare o aprire nuovamente la risorsa (CQ-4219628)
   * Il ricaricamento manuale delle cartelle non sempre funziona. Soluzione:  wait   30 secondi per l’aggiornamento automatico della cartella. (CQ-97389)
   * Ulteriori informazioni sulle risorse... è limitato alle selezioni di file singoli (CQ-89542, CQ-87656)
   * Apri in AEM Assets... è limitato alle selezioni di singoli file e cartelle (CQ-83382)
   * Errore durante la ridenominazione di risorse prive di estensione (CQ-4218971)
* Funzionalità Copia/Incolla: L’opzione Incolla è disponibile se non è stata copiata alcuna risorsa negli Appunti
* Windows:
   * I file con flussi di dati alternativi (ADS) sono completamente supportati solo su NTFS. Copiare tali file nella condivisione WebDAV fornita dall&#39;app desktop darà luogo a una finestra di dialogo di avviso che avvisa l&#39;utente che il file ha proprietà che non possono essere copiate nella nuova posizione. Di solito va bene, perché le proprietà sono rilevanti solo per una particolare applicazione sul desktop dell&#39;utente e non hanno nulla a che fare con il contenuto effettivo del file (CQ-103770) (Win)
   * L&#39;app desktop su Windows deve essere installata dall&#39;utente che la utilizzerà (CQ-4216389) (win)
   * L&#39;app può bloccarsi quando si seleziona l&#39;opzione [!UICONTROL Retry] su un caricamento non riuscito in determinate circostanze dopo aver ripreso il caricamento batch quando disconnesso (CQ-4251884) (Win)

## Risorse utili {#helpful-resources}

* [Documentazione di AEM](https://experienceleague.adobe.com/docs/)
* [Usa app desktop AEM v1.x](use-app-v1.md)
* [Best practice per l’app desktop AEM v1.x](best-practices-for-v1.md)

## Matrice di compatibilità e prerequisiti {#compatibilitymatrix}

L’app desktop AEM funziona con diverse versioni di AEM. Vedi la matrice di compatibilità per le versioni supportate.

| Versione | Revisione | Data di rilascio | Compatibilità |
|--- |--- |--- |--- |
| 1,10 | 1.10.0.3 (Mac e Win) | 31 agosto 2018 | AEM 6.5; AEM 6.4 SP1; AEM 6.3 SP2; AEM 6.2 SP1 CFP2+; AEM 6.1 SP2 CFP7+ |
| 1,9 | 1.9.1.1 (Mac e Win) | 21 giugno 2018 | AEM 6.4; AEM 6.3 SP1; AEM 6.2 SP1 CFP2+; AEM 6.1 SP2 CFP7+ |
| 1,8 | 1.8.1.0 (Mac e Win) | 28 marzo 2018 | AEM 6.4; AEM 6.3 SP1; AEM 6.2 SP1 CFP2+; AEM 6.1 SP2 CFP7+ |
| 1,7 | 1.7.0.3 (Mac e Win) | 10 gennaio 2018 | AEM 6.3 SP1; AEM 6.2 SP1 CFP2+; AEM 6.1 SP2 CFP7+ |
