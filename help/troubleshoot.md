---
title: 'Procedure ottimali per la risoluzione dei problemi e la risoluzione dei problemi relativi all''app desktop [!DNL Adobe Experience Manager] '
description: Seguite le procedure ottimali e risolvete eventuali problemi relativi a installazione, aggiornamento, configurazione e così via.
translation-type: tm+mt
source-git-commit: a25c1fa13895ae9eb7268e3e01c83a5f0b9d7d1d
workflow-type: tm+mt
source-wordcount: '2120'
ht-degree: 0%

---


# Risoluzione dei problemi relativi all&#39;app desktop [!DNL Adobe Experience Manager] {#troubleshoot-v2}

[!DNL Adobe Experience Manager] l&#39;app desktop si connette all&#39;archivio DAM (Digital Asset Management) di una  [!DNL Experience Manager] distribuzione. L&#39;app raccoglie informazioni sull&#39;archivio e risultati di ricerca sul computer, scarica e carica file e cartelle, e include funzionalità per gestire i conflitti con l&#39;interfaccia utente di Assets.

Continua a leggere per risolvere i problemi dell&#39;app, conoscere le procedure ottimali e individuare i limiti.

## Best practice {#best-practices-to-prevent-troubles}

Seguite le procedure ottimali riportate di seguito per evitare problemi comuni e risolvere eventuali problemi.

* **Scoprite come funziona** l&#39;app desktop: Prima di iniziare a utilizzare l&#39;applicazione, trascorrete alcuni minuti a sapere come funziona l&#39;app. Informazioni sui collegamenti tra l&#39;interfaccia Web e il desktop [!DNL Experience Manager], la mappatura dell&#39;archivio, il caching delle risorse, il salvataggio locale e il caricamento in background. Vedere [come funziona](release-notes.md#how-app-works).

* **Evitate i caratteri non supportati nei nomi** delle cartelle: Non utilizzate spazi bianchi e caratteri non validi durante la creazione o il caricamento di cartelle. Visualizzare un elenco di caratteri in [Crea cartelle in [!DNL Experience Manager Assets]](https://experienceleague.adobe.com/docs/experience-manager-65/assets/managing/manage-assets.html#creating-folders). Alcuni casi di utilizzo [!DNL Experience Manager] possono essere influenzati da caratteri non supportati nel nome della cartella.

* **Procedure ottimali per evitare conflitti**: Per evitare potenziali conflitti durante la collaborazione su più risorse, consultate  [evitare conflitti](using.md#adv-workflow-collaborate-avoid-conflicts) di modifica.

* **Usate il caricamento delle cartelle per le cartelle** gerarchiche di grandi dimensioni: Invece di usare l’interfaccia Web di Risorse o altri metodi, utilizzate l’app  [!DNL Experience Manager] desktop per caricare cartelle di grandi dimensioni. L&#39;app carica le risorse in background con registrazione e monitoraggio. Consultate [risorse per il caricamento in blocco](using.md#bulk-upload-assets).

* **Utilizzate la versione** più recente: Utilizzate la versione più recente dell&#39;app e verificate sempre la compatibilità prima di installare una nuova versione dell&#39;app o prima di eseguire l&#39;aggiornamento a una  [!DNL Experience Manager] versione più recente. Vedere [note sulla versione](release-notes.md).

* **Utilizzare la stessa lettera** di unità: Utilizzare la stessa lettera di unità all&#39;interno di un&#39;organizzazione per eseguire la mappatura sul  [!DNL Experience Manager] DAM. Per visualizzare le risorse inserite da altri utenti, i percorsi devono essere identici. L&#39;utilizzo della stessa lettera di unità assicura un percorso costante alle risorse DAM. Le risorse rimangono posizionate e non vengono rimosse anche se diversi utenti utilizzano lettere di unità.

* **Tenere presente la rete**: Le prestazioni di rete sono fondamentali per le prestazioni dell&#39;app  [!DNL Experience Manager] desktop. Se devi affrontare una risposta rallentata a trasferimenti di file o operazioni in blocco, disattiva le funzionalità o le app che potrebbero causare un sacco di traffico di rete.

* **Casi di utilizzo non supportati per l’app** desktop: non utilizzate l&#39;app per la migrazione delle risorse (necessita di pianificazione e altri strumenti); per operazioni DAM complesse (come lo spostamento di grandi cartelle, caricamenti di grandi dimensioni, la ricerca di file tramite ricerche avanzate di metadati); e come client di sincronizzazione (i principi di progettazione e i pattern di utilizzo sono diversi dai client in-sync come Microsoft OneDrive o la sincronizzazione desktop Adobe Creative Cloud).

* **Timeout**: Al momento, l&#39;app desktop non dispone di un valore di timeout configurabile che disconnette la connessione tra il  [!DNL Experience Manager] server e l&#39;app desktop dopo un intervallo di tempo fisso. Quando caricate risorse di grandi dimensioni, se la connessione riceve il timeout dopo un po&#39;, l&#39;app tenta nuovamente di caricare la risorsa alcune volte aumentando il timeout di caricamento. Non è consigliato modificare le impostazioni di timeout predefinite.

## Come risolvere i problemi di {#troubleshooting-prep}

Per risolvere i problemi relativi all&#39;app desktop, tenete presenti le informazioni seguenti. Inoltre, se desideri ottenere assistenza, ti consente di comunicare meglio i problemi  Assistenza clienti di Adobe.

### Percorso dei file di registro {#check-log-files-v2}

[!DNL Experience Manager] l&#39;app desktop memorizza i file di registro nelle seguenti posizioni, a seconda del sistema operativo:

In Windows: `%LocalAppData%\Adobe\AssetsCompanion\Logs`

In Mac: `~/Library/Logs/Adobe\ Experience\ Manager\ Desktop`

Quando caricate molte risorse, se alcuni file non vengono caricati, consultate `backend.log` file per identificare i caricamenti non riusciti.

>[!NOTE]
>
>Quando lavorate con  Assistenza clienti di Adobe su una richiesta di assistenza o un ticket di assistenza, potete chiedere di condividere i file di registro per aiutare il team di assistenza clienti a comprendere il problema. Archivia l&#39;intera cartella `Logs` e condividila con l&#39;Assistenza clienti.

### Modifica del livello di dettagli nei file di registro {#level-of-details-in-log}

Per modificare il livello di dettagli nei file di registro:

1. Verificare che l&#39;applicazione non sia in esecuzione.

1. Nel sistema Windows:

   1. Aprite una finestra di comando.

   1. Avviate l&#39;app desktop [!DNL Adobe Experience Manager] eseguendo il comando:

   ```shell
   set AEM_DESKTOP_LOG_LEVEL=DEBUG&"C:\Program Files\Adobe\Adobe Experience Manager Desktop.exe
   ```

   Sul sistema Mac:

   1. Aprite una finestra terminale.

   1. Avviate l&#39;app desktop [!DNL Adobe Experience Manager] eseguendo il comando:

   ```shell
   AEM_DESKTOP_LOG_LEVEL=DEBUG open /Applications/Adobe\ Experience\ Manager\ Desktop.app
   ```

I livelli di registro validi sono DEBUG, INFO, WARN o ERROR. La verbosità dei registri è maggiore in DEBUG e più bassa in ERRORE.

### Abilita modalità debug {#enable-debug-mode}

Per risolvere i problemi, puoi abilitare la modalità di debug e ottenere ulteriori informazioni nei registri.

>[!NOTE]
>
>I livelli di registro validi sono DEBUG, INFO, WARN o ERROR. La verbosità dei registri è maggiore in DEBUG e più bassa in ERRORE.

Per utilizzare l&#39;app in modalità di debug su Mac:

1. Aprite una finestra del terminale o un prompt dei comandi.

1. Avviate l&#39;app desktop [!DNL Experience Manager] eseguendo il comando seguente:

   `AEM_DESKTOP_LOG_LEVEL=DEBUG open /Applications/Adobe\ Experience\ Manager\ Desktop.app`.

Per abilitare la modalità di debug in Windows:

1. Aprite una finestra di comando.

1. Avviate l&#39;app desktop [!DNL Experience Manager] eseguendo il comando seguente:

`AEM_DESKTOP_LOG_LEVEL=DEBUG&"C:\Program Files\Adobe\Adobe Experience Manager Desktop.exe`.

### Cancella cache {#clear-cache-v2}

Effettuate le seguenti operazioni:

1. Avviare l&#39;applicazione e collegare l&#39;istanza [!DNL Experience Manager].

1. Aprite le preferenze dell&#39;applicazione facendo clic sulle ellissi nell&#39;angolo superiore destro e selezionando [!UICONTROL Preferences].

1. Individuare la voce che visualizza la [!UICONTROL Current Cache Size]. Fate clic sull&#39;icona del cestino accanto a questo elemento.

Per cancellare manualmente la cache, procedere con i passaggi descritti di seguito.

>[!CAUTION]
>
>Si tratta di un&#39;operazione potenzialmente distruttiva. In presenza di modifiche locali al file che non vengono caricate in [!DNL Adobe Experience Manager], tali modifiche andranno perse procedendo.

La cache viene cancellata eliminando la directory della cache dell&#39;applicazione, che si trova nelle preferenze dell&#39;applicazione.

1. Avviate l&#39;applicazione.

1. Aprite le preferenze dell&#39;applicazione selezionando le ellissi nell&#39;angolo superiore destro e selezionando [!UICONTROL Preferences].

1. Notate il valore [!UICONTROL Cache Directory].

   In questa directory esistono sottodirectory denominate dopo i punti finali codificati [!DNL Adobe Experience Manager]. I nomi sono una versione codificata dell&#39;URL di destinazione [!DNL Adobe Experience Manager]. Ad esempio, se l&#39;applicazione esegue il targeting `localhost:4502`, il nome della directory sarà `localhost_4502`.

Per cancellare la cache, eliminare la directory dei endpoint codificati [!DNL Adobe Experience Manager] desiderata. In alternativa, eliminando l&#39;intera directory specificata nelle preferenze, la cache per tutte le istanze utilizzate dall&#39;applicazione verrà cancellata.

La cancellazione della cache dell&#39;app desktop [!DNL Adobe Experience Manager] è un&#39;attività preliminare di risoluzione dei problemi che può risolvere diversi problemi. Cancella la cache dalle preferenze dell&#39;app. Vedere [impostare le preferenze](install-upgrade.md#set-preferences). Il percorso predefinito della cartella della cache è:

### Conoscere la versione [!DNL Adobe Experience Manager] dell&#39;app desktop {#know-app-version-v2}

Per visualizzare il numero di versione:

1. Avviate l&#39;applicazione.

1. Fare clic sulle ellissi nell&#39;angolo superiore destro, passare il mouse su [!UICONTROL Help], quindi fare clic su [!UICONTROL About].

   Il numero di versione è elencato in questa schermata.

### Impossibile visualizzare le risorse inserite {#placed-assets-missing}

Se non riuscite a visualizzare le risorse inserite nei file di supporto da voi o da altri professionisti del settore creativo (ad esempio, file INDD), controllate quanto segue:

* Connessione al server. Una connettività di rete debole può arrestare i download delle risorse.

* Dimensione file. Il download e la visualizzazione delle risorse grandi richiedono più tempo.

* Coerenza con le lettere dell&#39;unità. Se le risorse sono state inserite da un collaboratore durante la mappatura del DAM [!DNL Experience Manager] a un&#39;altra lettera di unità, le risorse inserite non vengono visualizzate.

* Autorizzazioni. Per verificare se disponete delle autorizzazioni necessarie per recuperare le risorse inserite, contattate l&#39;amministratore di [!DNL Experience Manager].

### Le modifiche apportate ai file nell&#39;interfaccia utente dell&#39;app desktop non si riflettono in [!DNL Adobe Experience Manager] immediatamente {#changes-on-da-not-visible-on-aem}

[!DNL Adobe Experience Manager] l&#39;app desktop lascia all&#39;utente la facoltà di decidere quando completare tutte le modifiche apportate a un file. A seconda delle dimensioni e della complessità di un file, il trasferimento della nuova versione di un file a [!DNL Adobe Experience Manager] richiede molto tempo. La progettazione dell&#39;applicazione richiede di ridurre al minimo il numero di volte che un file viene trasferito avanti e indietro, invece di indovinare quando le modifiche del file sono complete e vengono caricate automaticamente. L&#39;utente avvia il trasferimento del file su [!DNL Adobe Experience Manager] scegliendo di caricare le modifiche apportate al file.

### Problemi durante l&#39;aggiornamento su macOS {#issues-when-upgrading-on-macos}

Talvolta possono verificarsi problemi durante l&#39;aggiornamento dell&#39;app desktop [!DNL Experience Manager] in macOS. Ciò è causato dalla cartella di sistema precedente per l&#39;app desktop [!DNL Experience Manager] che impedisce il caricamento corretto delle nuove versioni dell&#39;app desktop [!DNL Experience Manager]. Per risolvere questo problema, è possibile rimuovere manualmente le cartelle e i file seguenti.

Prima di eseguire i seguenti passaggi, trascinate l&#39;applicazione `Adobe Experience Manager Desktop` dalla cartella delle applicazioni macOS al cestino. Aprite quindi il terminale, eseguite il comando seguente e fornite la password quando richiesto.

```shell
sudo rm -rf ~/Library/Application\ Support/com.adobe.aem.desktop
sudo rm -rf ~/Library/Preferences/com.adobe.aem.desktop.plist
sudo rm -rf ~/Library/Logs/Adobe\ Experience\ Manager\ Desktop

sudo find /var/folders -type d -name "com.adobe.aem.desktop" | xargs rm -rf
sudo find /var/folders -type d -name "com.adobe.aem.desktop.finderintegration-plugin" | xargs rm -rf
```

### Impossibile caricare i file {#upload-fails}

Se si utilizza l&#39;app desktop con [!DNL Experience Manager] 6.5.1 o versione successiva, aggiornare il connettore S3 o Azure alla versione 1.10.4 o successiva. Risolve il problema di errore nel caricamento dei file relativo a [OAK-8599](https://issues.apache.org/jira/browse/OAK-8599). Vedere [istruzioni di installazione](install-upgrade.md#install-v2).

### [!DNL Experience Manager] problemi di connessione all&#39;app desktop  {#connection-issues}

Se si verificano problemi generali di connettività, ecco alcuni modi per ottenere ulteriori informazioni sulle prestazioni dell&#39;app desktop [!DNL Experience Manager].

**Controllare il registro delle richieste**

[!DNL Experience Manager] l&#39;app desktop registra tutte le richieste inviate, insieme al codice di risposta di ogni richiesta, in un file di registro dedicato.

1. Aprite `request.log` nella directory di registro dell&#39;applicazione per visualizzare queste richieste.

1. Ogni riga del registro rappresenta una richiesta o una risposta. Le richieste avranno un carattere `>` seguito dall&#39;URL richiesto. Le risposte avranno un carattere `<` seguito dal codice di risposta e dall&#39;URL richiesto. Richieste e risposte possono essere soddisfatte utilizzando il GUID di ogni riga.

**Controllare le richieste caricate dal browser incorporato dell&#39;applicazione**

La maggior parte delle richieste dell&#39;applicazione si trova nel registro delle richieste. Tuttavia, se non sono disponibili informazioni utili, può essere utile esaminare le richieste inviate dal browser incorporato dell&#39;applicazione.
Per istruzioni su come visualizzare tali richieste, vedere la sezione [SAML](#da-connection-issue-with-saml-aem).

#### Autenticazione di accesso SAML non funzionante {#da-connection-issue-with-saml-aem}

Se l&#39;app desktop [!DNL Experience Manager] non si connette all&#39;istanza [!DNL Adobe Experience Manager] abilitata per SSO (SAML), leggere questa sezione per risolvere i problemi. I processi SSO sono diversi, a volte complessi e il design dell&#39;applicazione fa del suo meglio per adattarsi a questi tipi di connessioni. Tuttavia, alcune impostazioni richiedono una risoluzione di problemi aggiuntiva.

A volte il processo SAML non effettua il reindirizzamento al percorso originariamente richiesto, oppure il reindirizzamento finale è a un host che è diverso da quello configurato nell&#39;app [!DNL Adobe Experience Manager] desktop. Per verificare che non sia così:

1. Aprite un browser Web. Accedere all&#39;URL `https://[aem_server]:[port]/content/dam.json`.

1. Accedete alla distribuzione [!DNL Adobe Experience Manager].

1. Al termine dell&#39;accesso, controllate l&#39;indirizzo corrente del browser nella barra degli indirizzi. Deve corrispondere esattamente all’URL immesso inizialmente.

1. Verificate inoltre che tutti gli elementi precedenti a `/content/dam.json` corrispondano al valore [!DNL Adobe Experience Manager] di destinazione configurato nelle impostazioni dell&#39;app desktop [!DNL Adobe Experience Manager].

**Il processo SAML di accesso funziona correttamente in base ai passaggi precedenti, ma gli utenti non sono ancora in grado di accedere**

La finestra all&#39;interno dell&#39;app desktop [!DNL Adobe Experience Manager] che visualizza il processo di accesso è semplicemente un browser Web che visualizza l&#39;interfaccia utente Web dell&#39;istanza [!DNL Adobe Experience Manager] di destinazione:

* La versione Mac utilizza [WebView](https://developer.apple.com/documentation/webkit/webview).

* La versione di Windows utilizza [CefSharp](https://cefsharp.github.io/) basato su Cromo.

Verificate che il processo SAML supporti tali browser.

Per risolvere ulteriormente i problemi, è possibile visualizzare gli URL esatti che il browser sta tentando di caricare. Per visualizzare queste informazioni:

1. Seguire le istruzioni per avviare l&#39;applicazione in [modalità di debug](#enable-debug-mode).

1. Riproduci il tentativo di accesso.

1. Andate alla [directory di registro](#check-log-files-v2) dell&#39;applicazione

1. Per Windows:

   1. Aprite &quot;aemcompanionlog.txt&quot;.

   1. Cerca i messaggi che iniziano con &quot;Indirizzo browser di accesso cambiato in&quot;. Queste voci contengono anche l’URL caricato dall’applicazione.

   Per Mac:

   1. `com.adobe.aem.desktop-nnnnnnnn-nnnnnn.log`, dove il  **** nome viene sostituito da qualsiasi numero presente nel nome file più recente.

   1. Cerca i messaggi che iniziano con &quot;frame caricato&quot;. Queste voci contengono anche l’URL caricato dall’applicazione.


Osservare la sequenza URL caricata può facilitare la risoluzione dei problemi alla fine di SAML per determinare cosa è sbagliato.

#### Problema di configurazione SSL {#ssl-config-v2}

Le librerie utilizzate dall&#39;app desktop [!DNL Experience Manager] per la comunicazione HTTP utilizzano l&#39;applicazione SSL rigorosa. A volte, una connessione può avere esito positivo utilizzando un browser ma non riesce utilizzando l&#39;app desktop [!DNL Experience Manager]. Per configurare SSL in modo appropriato, installate il certificato intermedio mancante in Apache. Vedere [Come installare un certificato CA intermedio in Apache](https://access.redhat.com/solutions/43575).

Le librerie che l&#39;app desktop [!DNL Experience Manager] utilizza per la comunicazione HTTP utilizzano l&#39;applicazione SSL rigorosa. In alcuni casi, le connessioni SSL riuscite tramite un browser non vanno a buon fine con l&#39;app desktop [!DNL Adobe Experience Manager]. Ciò è positivo perché incoraggia la corretta configurazione di SSL e aumenta la sicurezza, ma può risultare frustrante quando l&#39;applicazione non è in grado di connettersi.

In questo caso, si consiglia di utilizzare uno strumento per analizzare il certificato SSL di un server e identificare i problemi che possono essere corretti. Esistono siti Web che ispezionano il certificato di un server quando ne fornisce l&#39;URL.

Come misura temporanea, è possibile disabilitare l&#39;applicazione SSL rigorosa nell&#39;app desktop [!DNL Adobe Experience Manager]. Non si tratta di una soluzione a lungo termine consigliata, in quanto riduce la protezione nascondendo la causa principale di SSL configurato in modo errato. Per disabilitare l&#39;applicazione rigorosa:

1. Utilizzate l&#39;editor di vostra scelta per modificare il file di configurazione JavaScript dell&#39;applicazione, che si trova (per impostazione predefinita) nelle seguenti posizioni (a seconda del sistema operativo):

   In Mac: `/Applications/Adobe Experience Manager Desktop.app/Contents/Resources/javascript/lib-smb/config.json`

   In Windows: `C:\Program Files (x86)\Adobe\Adobe Experience Manager Desktop\javascript\config.json`

1. Individuare la sezione seguente nel file:

   ```shell
   ...
   "assetRepository": {
       "options": {
   ...
   ```

1. Modificare la sezione aggiungendo `"strictSSL": false` come segue:

   ```shell
   ...
   "assetRepository": {
       "options": {
           "strictSSL": false,
   ...
   ```

1. Salvate il file e riavviate l&#39;app desktop [!DNL Adobe Experience Manager].

### L&#39;app non risponde {#unresponsive}

Raramente l&#39;applicazione potrebbe non rispondere, visualizzare solo uno schermo bianco, o visualizzare un errore nella parte inferiore dell&#39;interfaccia senza alcuna opzione sull&#39;interfaccia. Effettuate le seguenti operazioni nell&#39;ordine:

* Fare clic con il pulsante destro del mouse sull&#39;interfaccia dell&#39;applicazione e scegliere **[!UICONTROL Refresh]**.
* Uscite dall’applicazione e apritela di nuovo.

In entrambi i metodi, l&#39;app inizia dalla cartella DAM principale.

<!--
### Need additional help with [!DNL Experience Manager] desktop app {#additional-help}

Create Jira ticket with the following information:

* Use `DAM - Companion App` as the [!UICONTROL Component].

* Detailed steps to reproduce the issue in [!UICONTROL Description].

* DEBUG level logs that were captured while reproducing the issue.

* Target Experience Manager version.

* Operating system version.

* [!DNL Adobe Experience Manager] desktop app version. To know your app version, see [finding the desktop app version](#know-app-version-v2).
-->

>[!MORELIKETHIS]
>
>* [Problemi noti](release-notes.md#known-issues-v2)
>* [Evitare conflitti di modifica](using.md#adv-workflow-collaborate-avoid-conflicts)

