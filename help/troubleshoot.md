---
title: Procedure ottimali per la risoluzione dei problemi relativi all'app desktop Adobe Experience Manager
description: Seguite le procedure ottimali e risolvete eventuali problemi relativi a installazione, aggiornamento, configurazione e così via.
uuid: ce98a3e7-5454-41be-aaaa-4252b3e0f8dd
contentOwner: AG
products: SG_EXPERIENCEMANAGER/6.5/ASSETS, SG_EXPERIENCEMANAGER/6.4/ASSETS, SG_EXPERIENCEMANAGER/6.3/ASSETS
discoiquuid: f5eb222a-6cdf-4ae3-9cf2-755c873f397c
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 2893fc1f8aad02e1436a1a281a320e6837487220
workflow-type: tm+mt
source-wordcount: '2171'
ht-degree: 0%

---


# Troubleshoot Adobe Experience Manager desktop app {#troubleshoot-v2}

L&#39;app desktop Adobe Experience Manager si connette a un archivio DAM (Digital Asset Management) di distribuzione  Experience Manager remoto. L&#39;app raccoglie informazioni sull&#39;archivio e risultati di ricerca sul computer, scarica e carica file e cartelle, e include funzionalità per gestire i conflitti con l&#39;interfaccia utente di Assets.

Continua a leggere per risolvere i problemi dell&#39;app, conoscere le procedure ottimali e individuare i limiti.

## Best practices {#best-practices-to-prevent-troubles}

Seguite le procedure ottimali riportate di seguito per evitare problemi comuni e risolvere eventuali problemi.

* **Scoprite come funziona** l&#39;app desktop: Prima di iniziare a utilizzare l&#39;applicazione, trascorrete alcuni minuti a sapere come funziona l&#39;app. Informazioni sui collegamenti tra l&#39;interfaccia Web  Experience Manager e il desktop, la mappatura dell&#39;archivio, il caching delle risorse, il salvataggio locale e il caricamento in background. Vedete [come funziona](release-notes.md#how-app-works).

* **Evitate i caratteri non supportati nei nomi** delle cartelle: Non utilizzate spazi bianchi e caratteri non validi durante la creazione o il caricamento di cartelle. Consultate un elenco di caratteri in [Creazione di cartelle in  risorse](https://experienceleague.adobe.com/docs/experience-manager-65/assets/managing/manage-assets.html#creating-folders)Experience Manager. Alcuni casi di utilizzo di Adobe Experience Manager possono essere influenzati da caratteri non supportati nel nome della cartella.

* **Procedure ottimali per evitare conflitti**: Per evitare potenziali conflitti durante la collaborazione su più risorse, consultate [evitare conflitti](using.md#adv-workflow-collaborate-avoid-conflicts)di modifica.

* **Usate il caricamento delle cartelle per le cartelle** gerarchiche di grandi dimensioni: Invece di usare l’interfaccia Web o altri metodi di Risorse, utilizzate ’app desktop Experience Manager per caricare cartelle di grandi dimensioni. L&#39;app carica le risorse in background con registrazione e monitoraggio. Consultate Caricare [in blocco le risorse](using.md#bulk-upload-assets).

* **Utilizzate la versione** più recente: Utilizzate la versione più recente dell&#39;app e verificate sempre la compatibilità prima di installare una nuova versione dell&#39;app o prima di eseguire l&#39;aggiornamento a una versione più recente di Adobe Experience Manager. See [release notes](release-notes.md).

* **Utilizzare la stessa lettera** di unità: Utilizzare la stessa lettera di unità all&#39;interno di un&#39;organizzazione per eseguire la mappatura su Adobe Experience Manager DAM. Per visualizzare le risorse inserite da altri utenti, i percorsi devono essere identici. L&#39;utilizzo della stessa lettera di unità assicura un percorso costante alle risorse DAM. Le risorse rimangono posizionate e non vengono rimosse anche se diversi utenti utilizzano lettere di unità.

* **Tenere presente la rete**: Le prestazioni di rete sono fondamentali per  le prestazioni dell&#39;app desktop di Experience Manager. Se devi affrontare una risposta rallentata a trasferimenti di file o operazioni in blocco, disattiva le funzionalità o le app che potrebbero causare un sacco di traffico di rete.

* **Casi di utilizzo non supportati per l’app** desktop: non utilizzate l&#39;app per la migrazione delle risorse (necessita di pianificazione e altri strumenti); per operazioni DAM complesse (come lo spostamento di grandi cartelle, caricamenti di grandi dimensioni, la ricerca di file tramite ricerche avanzate di metadati); e come client di sincronizzazione (i principi di progettazione e i pattern di utilizzo sono diversi dai client in-sync come Microsoft OneDrive o la sincronizzazione desktop Adobe Creative Cloud).

* **Timeout**: Al momento, l&#39;app desktop non dispone di un valore di timeout configurabile che disconnette la connessione tra  server di Experience Manager e l&#39;app desktop dopo un intervallo di tempo fisso. Quando caricate risorse di grandi dimensioni, se la connessione riceve il timeout dopo un po&#39;, l&#39;app tenta nuovamente di caricare la risorsa alcune volte aumentando il timeout di caricamento. Non è consigliato modificare le impostazioni di timeout predefinite.

## Come risolvere i problemi {#troubleshooting-prep}

Per risolvere i problemi relativi all&#39;app desktop, tenete presenti le informazioni seguenti. Inoltre, se desideri ottenere assistenza, ti consente di comunicare meglio i problemi  Assistenza clienti di Adobe.

### Posizione dei file di registro {#check-log-files-v2}

[!DNL Experience Manager] l&#39;app desktop memorizza i file di registro nelle seguenti posizioni, a seconda del sistema operativo:

In Windows: `%LocalAppData%\Adobe\AssetsCompanion\Logs`

In Mac: `~/Library/Logs/Adobe\ Experience\ Manager\ Desktop`

Quando caricate molte risorse, se alcuni file non vengono caricati, consultate `backend.log` file per identificare i caricamenti non riusciti.

>[!NOTE]
>
>Quando lavorate con  Assistenza clienti di Adobe su una richiesta di assistenza o un ticket di assistenza, potete chiedere di condividere i file di registro per aiutare il team di assistenza clienti a comprendere il problema. Archivia l&#39;intera `Logs` cartella e condividila con l&#39;Assistenza clienti.

### Modifica del livello di dettagli nei file di registro {#level-of-details-in-log}

Per modificare il livello di dettagli nei file di registro:

1. Verificare che l&#39;applicazione non sia in esecuzione.

1. Nel sistema Windows:

   1. Aprite una finestra di comando.

   1. Avviate l&#39;app [!DNL Adobe Experience Manager] desktop eseguendo il comando:

   ```shell
   set AEM_DESKTOP_LOG_LEVEL=DEBUG&"C:\Program Files\Adobe\Adobe Experience Manager Desktop.exe
   ```

   Sul sistema Mac:

   1. Aprite una finestra terminale.

   1. Avviate l&#39;app [!DNL Adobe Experience Manager] desktop eseguendo il comando:

   ```shell
   AEM_DESKTOP_LOG_LEVEL=DEBUG open /Applications/Adobe\ Experience\ Manager\ Desktop.app
   ```

I livelli di registro validi sono DEBUG, INFO, WARN o ERROR. La verbosità dei registri è maggiore in DEBUG e più bassa in ERRORE.

### Abilita modalità di debug {#enable-debug-mode}

Per risolvere i problemi, puoi abilitare la modalità di debug e ottenere ulteriori informazioni nei registri.

>[!NOTE]
>
>I livelli di registro validi sono DEBUG, INFO, WARN o ERROR. La verbosità dei registri è maggiore in DEBUG e più bassa in ERRORE.

Per utilizzare l&#39;app in modalità di debug su Mac:

1. Aprite una finestra del terminale o un prompt dei comandi.

1. Avviate l&#39;app [!DNL Experience Manager] desktop eseguendo il comando seguente:

   `AEM_DESKTOP_LOG_LEVEL=DEBUG open /Applications/Adobe\ Experience\ Manager\ Desktop.app`.

Per abilitare la modalità di debug in Windows:

1. Aprite una finestra di comando.

1. Avviate l&#39;app [!DNL Experience Manager] desktop eseguendo il comando seguente:

`AEM_DESKTOP_LOG_LEVEL=DEBUG&"C:\Program Files\Adobe\Adobe Experience Manager Desktop.exe`.

### Cancella cache {#clear-cache-v2}

Effettuate le seguenti operazioni:

1. Avviare l&#39;applicazione e collegare l&#39;istanza del Experience Manager .

1. Aprite le preferenze dell&#39;applicazione facendo clic sulle ellissi nell&#39;angolo superiore destro e selezionando [!UICONTROL Preferences].

1. Individuare la voce che visualizza il [!UICONTROL Current Cache Size]. Fate clic sull&#39;icona del cestino accanto a questo elemento.

Per cancellare manualmente la cache, procedere con i passaggi descritti di seguito.

>[!CAUTION]
>
>Si tratta di un&#39;operazione potenzialmente distruttiva. Se vi sono modifiche locali al file che non vengono caricate in [!DNL Adobe Experience Manager], tali modifiche andranno perse procedendo.

La cache viene cancellata eliminando la directory della cache dell&#39;applicazione, che si trova nelle preferenze dell&#39;applicazione.

1. Avviate l&#39;applicazione.

1. Aprite le preferenze dell&#39;applicazione selezionando le ellissi nell&#39;angolo superiore destro e selezionando [!UICONTROL Preferences].

1. Notate il [!UICONTROL Cache Directory] valore.

   In questa directory esistono sottodirectory denominate in base agli [!DNL Adobe Experience Manager] endpoint codificati. I nomi sono una versione codificata dell’ [!DNL Adobe Experience Manager] URL di destinazione. Ad esempio, se l&#39;applicazione esegue il targeting, `localhost:4502` il nome della directory sarà `localhost_4502`.

Per cancellare la cache, elimina la directory [!DNL Adobe Experience Manager] Endpoint codificato desiderata. In alternativa, eliminando l&#39;intera directory specificata nelle preferenze, la cache per tutte le istanze utilizzate dall&#39;applicazione verrà cancellata.

La cancellazione della cache dell&#39;app [!DNL Adobe Experience Manager] desktop è un&#39;attività preliminare di risoluzione dei problemi che può risolvere diversi problemi. Cancella la cache dalle preferenze dell&#39;app. Consultate [Impostare le preferenze](install-upgrade.md#set-preferences). Il percorso predefinito della cartella della cache è:

### Conoscere la versione dell&#39;app [!DNL Adobe Experience Manager] desktop {#know-app-version-v2}

Per visualizzare il numero di versione:

1. Avviate l&#39;applicazione.

1. Fare clic sulle ellissi nell&#39;angolo superiore destro, passare il mouse [!UICONTROL Help]e fare clic [!UICONTROL About].

   Il numero di versione è elencato in questa schermata.

### Impossibile visualizzare le risorse inserite {#placed-assets-missing}

Se non riuscite a visualizzare le risorse inserite nei file di supporto da voi o da altri professionisti del settore creativo (ad esempio, file INDD), controllate quanto segue:

* Connessione al server. Una connettività di rete debole può arrestare i download delle risorse.

* Dimensione file. Il download e la visualizzazione delle risorse grandi richiedono più tempo.

* Coerenza con le lettere dell&#39;unità. Se le risorse sono state inserite da un collaboratore durante la mappatura del DAM del Experience Manager  a un&#39;altra lettera di unità, le risorse inserite non vengono visualizzate.

* Autorizzazioni. Per verificare se disponete delle autorizzazioni necessarie per recuperare le risorse inserite, contattate l’amministratore di Experience Manager .

### Le modifiche apportate ai file nell&#39;interfaccia utente dell&#39;app desktop non si riflettono [!DNL Adobe Experience Manager] immediatamente {#changes-on-da-not-visible-on-aem}

[!DNL Adobe Experience Manager] l&#39;app desktop lascia all&#39;utente la facoltà di decidere quando completare tutte le modifiche apportate a un file. A seconda delle dimensioni e della complessità di un file, il trasferimento della nuova versione di un file a [!DNL Adobe Experience Manager]. La progettazione dell&#39;applicazione richiede di ridurre al minimo il numero di volte che un file viene trasferito avanti e indietro, invece di indovinare quando le modifiche del file sono complete e vengono caricate automaticamente. L&#39;utente avvia il trasferimento del file [!DNL Adobe Experience Manager] scegliendo di caricare le modifiche apportate al file.

### Problemi durante l&#39;aggiornamento su macOS {#issues-when-upgrading-on-macos}

A volte possono verificarsi problemi durante l&#39;aggiornamento &#39;app desktop Experience Manager su macOS. Ciò è causato dalla cartella di sistema precedente per  app desktop Experience Manager che impedisce il corretto caricamento delle nuove versioni  app desktop Experience Manager. Per risolvere questo problema, è possibile rimuovere manualmente le cartelle e i file seguenti.

Prima di eseguire i seguenti passaggi, trascinate l’ `Adobe Experience Manager Desktop` applicazione dalla cartella delle applicazioni macOS al cestino. Aprite quindi il terminale, eseguite il comando seguente e fornite la password quando richiesto.

```shell
sudo rm -rf ~/Library/Application\ Support/com.adobe.aem.desktop
sudo rm -rf ~/Library/Preferences/com.adobe.aem.desktop.plist
sudo rm -rf ~/Library/Logs/Adobe\ Experience\ Manager\ Desktop

sudo find /var/folders -type d -name "com.adobe.aem.desktop" | xargs rm -rf
sudo find /var/folders -type d -name "com.adobe.aem.desktop.finderintegration-plugin" | xargs rm -rf
```

### Impossibile caricare i file {#upload-fails}

Se si utilizza l&#39;app desktop con  Experience Manager 6.5.1 o successivo, aggiornare il connettore S3 o Azure alla versione 1.10.4 o successiva. Risolve il problema di errore di caricamento dei file relativo a [OAK-8599](https://issues.apache.org/jira/browse/OAK-8599). Consultate [le istruzioni](install-upgrade.md#install-v2)di installazione.

### [!DNL Experience Manager] problemi di connessione all&#39;app desktop {#connection-issues}

Se si verificano problemi generali di connettività, ecco alcuni modi per ottenere ulteriori informazioni sulle operazioni dell&#39;app [!DNL Experience Manager] desktop.

**Controllare il registro delle richieste**

[!DNL Experience Manager] l&#39;app desktop registra tutte le richieste inviate, insieme al codice di risposta di ogni richiesta, in un file di registro dedicato.

1. Aprite `request.log` nella directory di registro dell’applicazione per visualizzare tali richieste.

1. Ogni riga del registro rappresenta una richiesta o una risposta. Le richieste avranno un `>` carattere seguito dall&#39;URL richiesto. Le risposte avranno un `<` carattere seguito dal codice di risposta e dall’URL richiesto. Richieste e risposte possono essere soddisfatte utilizzando il GUID di ogni riga.

**Controllare le richieste caricate dal browser incorporato dell&#39;applicazione**

La maggior parte delle richieste dell&#39;applicazione si trova nel registro delle richieste. Tuttavia, se non sono disponibili informazioni utili, può essere utile esaminare le richieste inviate dal browser incorporato dell&#39;applicazione.
Per istruzioni su come visualizzare tali richieste, consultate la sezione [](#da-connection-issue-with-saml-aem) SAML.

#### Autenticazione di accesso SAML non funzionante {#da-connection-issue-with-saml-aem}

Se l&#39;app [!DNL Experience Manager] desktop non si connette all&#39; [!DNL Adobe Experience Manager] istanza di SSO abilitata (SAML), consulta questa sezione per la risoluzione dei problemi. I processi SSO sono diversi, a volte complessi e il design dell&#39;applicazione fa del suo meglio per adattarsi a questi tipi di connessioni. Tuttavia, alcune impostazioni richiedono una risoluzione di problemi aggiuntiva.

A volte il processo SAML non effettua il reindirizzamento al percorso originariamente richiesto, oppure il reindirizzamento finale è a un host che è diverso da quello configurato nell&#39;app [!DNL Adobe Experience Manager] desktop. Per verificare che non sia così:

1. Aprite un browser Web. Access `https://[aem_server]:[port]/content/dam.json` URL.

1. Effettuate l&#39;accesso alla [!DNL Adobe Experience Manager] distribuzione.

1. Al termine dell&#39;accesso, controllate l&#39;indirizzo corrente del browser nella barra degli indirizzi. Deve corrispondere esattamente all’URL immesso inizialmente.

1. Verificate inoltre che tutti gli elementi precedenti `/content/dam.json` corrispondano al valore di destinazione [!DNL Adobe Experience Manager] configurato nelle impostazioni dell&#39;app [!DNL Adobe Experience Manager] desktop.

**Il processo SAML di accesso funziona correttamente in base ai passaggi precedenti, ma gli utenti non sono ancora in grado di accedere**

La finestra all&#39;interno dell&#39;app [!DNL Adobe Experience Manager] desktop che visualizza il processo di accesso è semplicemente un browser Web che visualizza l&#39;interfaccia utente Web dell&#39; [!DNL Adobe Experience Manager] istanza di destinazione:

* La versione Mac utilizza [WebView](https://developer.apple.com/documentation/webkit/webview).

* La versione Windows utilizza Chromio-based [CefSharp](https://cefsharp.github.io/).

Verificate che il processo SAML supporti tali browser.

Per risolvere ulteriormente i problemi, è possibile visualizzare gli URL esatti che il browser sta tentando di caricare. Per visualizzare queste informazioni:

1. Seguite le istruzioni per avviare l&#39;applicazione in modalità [](#enable-debug-mode)debug.

1. Riproduci il tentativo di accesso.

1. Passa alla directory [di](#check-log-files-v2) registro dell&#39;applicazione

1. Per Windows:

   1. Aprite &quot;aemcompanionlog.txt&quot;.

   1. Cerca i messaggi che iniziano con &quot;Indirizzo browser di accesso cambiato in&quot;. Queste voci contengono anche l’URL caricato dall’applicazione.

   Per Mac:

   1. `com.adobe.aem.desktop-nnnnnnnn-nnnnnn.log`, dove **n** viene sostituito da qualsiasi numero presente nel nome file più recente.

   1. Cerca i messaggi che iniziano con &quot;frame caricato&quot;. Queste voci contengono anche l’URL caricato dall’applicazione.


Osservare la sequenza URL caricata può facilitare la risoluzione dei problemi alla fine di SAML per determinare cosa è sbagliato.

#### Problema di configurazione SSL {#ssl-config-v2}

Le librerie che &#39;app desktop di Experience Manager utilizza per la comunicazione HTTP utilizzano l&#39;applicazione SSL rigorosa. In alcuni casi, una connessione può avere esito positivo utilizzando un browser ma non riesce utilizzando &#39;app desktop Experience Manager. Per configurare SSL in modo appropriato, installate il certificato intermedio mancante in Apache. Vedere [Come installare un certificato CA intermedio in Apache](https://access.redhat.com/solutions/43575).

Le librerie che  Experience Manager Desktop utilizza per la comunicazione HTTP utilizzano l&#39;applicazione SSL rigorosa. In alcuni casi, le connessioni SSL riuscite tramite un browser non funzionano con l&#39;app [!DNL Adobe Experience Manager] desktop. Ciò è positivo perché incoraggia la corretta configurazione di SSL e aumenta la sicurezza, ma può risultare frustrante quando l&#39;applicazione non è in grado di connettersi.

In questo caso, si consiglia di utilizzare uno strumento per analizzare il certificato SSL di un server e identificare i problemi che possono essere corretti. Esistono siti Web che ispezionano il certificato di un server quando ne fornisce l&#39;URL.

Come misura temporanea, è possibile disabilitare l&#39;applicazione SSL rigorosa nell&#39;app [!DNL Adobe Experience Manager] desktop. Non si tratta di una soluzione a lungo termine consigliata, in quanto riduce la protezione nascondendo la causa principale di SSL configurato in modo errato. Per disabilitare l&#39;applicazione rigorosa:

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

1. Modificate la sezione aggiungendo `"strictSSL": false` quanto segue:

   ```shell
   ...
   "assetRepository": {
       "options": {
           "strictSSL": false,
   ...
   ```

1. Salvate il file e riavviate l&#39;app [!DNL Adobe Experience Manager] desktop.

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

