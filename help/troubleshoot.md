---
title: Procedure consigliate per la risoluzione dei problemi relativi all'app desktop [!DNL Adobe Experience Manager] e
description: Segui le best practice e risolvi eventuali problemi relativi all’installazione, all’aggiornamento, alla configurazione e così via.
translation-type: tm+mt
source-git-commit: 9d90bdcab79604e03d1ad3f30ed2aca2eb03e1c5
workflow-type: tm+mt
source-wordcount: '2110'
ht-degree: 0%

---


# Risolvere i problemi relativi all’ [!DNL Adobe Experience Manager] app desktop {#troubleshoot-v2}

[!DNL Adobe Experience Manager] l’app desktop si connette all’archivio DAM (Digital Asset Management) di una  [!DNL Experience Manager] distribuzione. L’app recupera le informazioni sull’archivio e i risultati della ricerca sul computer, scarica e carica file e cartelle e include funzionalità per gestire i conflitti con l’interfaccia utente di Assets.

Continua a leggere per risolvere i problemi dell’app, scopri le best practice e le limitazioni.

## Best practice {#best-practices-to-prevent-troubles}

Segui le best practice riportate di seguito per evitare alcuni problemi e risolvere i problemi più comuni.

* **Scopri come funziona** l’app desktop: Prima di iniziare a utilizzare l’applicazione, passa alcuni minuti sapendo come funziona l’app. Scopri i collegamenti tra l’interfaccia web e il desktop [!DNL Experience Manager], la mappatura dell’archivio, il caching delle risorse, il salvataggio locale e il caricamento in background. Vedi [come funziona](release-notes.md#how-app-works).

* **Evitare i caratteri non supportati nei nomi** delle cartelle: Non utilizzare spazi bianchi e caratteri non validi durante la creazione o il caricamento di cartelle. Consulta un elenco di caratteri in [Crea cartelle in [!DNL Experience Manager Assets]](https://experienceleague.adobe.com/docs/experience-manager-65/assets/managing/manage-assets.html#creating-folders). Alcuni casi d’uso [!DNL Experience Manager] possono essere interessati dai caratteri non supportati nel nome della cartella.

* **Best practice per evitare conflitti**: Per evitare potenziali conflitti durante la collaborazione su più risorse, consulta  [evitare conflitti](using.md#adv-workflow-collaborate-avoid-conflicts) di modifica.

* **Utilizza il caricamento delle cartelle per le cartelle** gerarchiche di grandi dimensioni: Invece di utilizzare l’interfaccia web Assets o altri metodi, usa l’app  [!DNL Experience Manager] desktop per caricare cartelle di grandi dimensioni. L’app carica le risorse in background con registrazione e monitoraggio. Consulta [Caricamento in serie di risorse](using.md#bulk-upload-assets).

* **Utilizza la versione** più recente: Utilizza la versione più recente dell’app e verifica sempre la compatibilità prima di installare una nuova versione dell’app o prima di eseguire l’aggiornamento a una  [!DNL Experience Manager] versione più recente. Consulta le [note sulla versione](release-notes.md).

* **Utilizzare la stessa lettera** di unità: Utilizza la stessa lettera di unità in un&#39;organizzazione per eseguire la mappatura sul  [!DNL Experience Manager] DAM. Per visualizzare le risorse inserite da altri utenti, i percorsi devono essere gli stessi. L’utilizzo della stessa lettera di unità assicura un percorso costante alle risorse DAM. Le risorse rimangono posizionate e non vengono rimosse anche se vengono utilizzate lettere di unità diverse da utenti diversi.

* **Attenzione alla rete**: Le prestazioni di rete sono fondamentali per le prestazioni dell’app  [!DNL Experience Manager] desktop. Se ti trovi di fronte a una risposta rallentata ai trasferimenti di file o alle operazioni in blocco, disattiva le funzioni o le app che potrebbero causare un sacco di traffico di rete.

* **Casi d’uso non supportati per l’app** desktop: Non utilizzare l’app per la migrazione di Assets (che richiede pianificazione e altri strumenti); per operazioni DAM complesse (come lo spostamento di cartelle di grandi dimensioni, caricamenti di grandi dimensioni, la ricerca di file tramite ricerche avanzate di metadati); e come client di sincronizzazione (i principi di progettazione e i pattern di utilizzo sono diversi dai client in-sync come la sincronizzazione desktop Microsoft OneDrive o Adobe Creative Cloud).

* **Timeout**: Al momento, l’app desktop non dispone di un valore di timeout configurabile che disconnette la connessione tra app  [!DNL Experience Manager] server e desktop dopo un intervallo di tempo fisso. Quando carichi risorse di grandi dimensioni, se la connessione si interrompe dopo un po&#39; di tempo, l’app tenta nuovamente di caricare la risorsa qualche volta aumentando il timeout di caricamento. Non è consigliabile modificare le impostazioni di timeout predefinite.

## Come risolvere i problemi {#troubleshooting-prep}

Per risolvere i problemi relativi all’app desktop, tieni presente quanto segue. Inoltre, ti prepara a comunicare meglio i problemi ad Adobe Customer Care se scegli di cercare il supporto.

### Posizione dei file di registro {#check-log-files-v2}

[!DNL Experience Manager] l’app desktop memorizza i propri file di registro nelle seguenti posizioni a seconda del sistema operativo:

In Windows: `%LocalAppData%\Adobe\AssetsCompanion\Logs`

Su Mac: `~/Library/Logs/Adobe\ Experience\ Manager\ Desktop`

Quando carichi molte risorse, se alcuni file non vengono caricati, consulta il file `backend.log` per identificare i caricamenti non riusciti.

>[!NOTE]
>
>Quando lavori con l’Assistenza clienti di Adobe su una richiesta di supporto o su un ticket, ti può essere chiesto di condividere i file di registro per aiutare il team di Assistenza clienti a comprendere il problema. Archivia l’intera cartella `Logs` e condividila con il contatto dell’Assistenza clienti.

### Cambia il livello di dettagli nei file di log {#level-of-details-in-log}

Per modificare il livello di dettagli nei file di log:

1. Assicurati che l&#39;applicazione non sia in esecuzione.

1. Sul sistema Windows:

   1. Apri una finestra di comando.

   1. Avvia l&#39;app desktop [!DNL Adobe Experience Manager] eseguendo il comando:

   ```shell
   set AEM_DESKTOP_LOG_LEVEL=DEBUG&"C:\Program Files\Adobe\Adobe Experience Manager Desktop.exe
   ```

   Sul sistema Mac:

   1. Apri una finestra terminale.

   1. Avvia l&#39;app desktop [!DNL Adobe Experience Manager] eseguendo il comando:

   ```shell
   AEM_DESKTOP_LOG_LEVEL=DEBUG open /Applications/Adobe\ Experience\ Manager\ Desktop.app
   ```

I livelli di registro validi sono DEBUG, INFO, WARN o ERROR. La verbosità dei log è più alta in DEBUG e più bassa in ERROR.

### Attiva la modalità di debug {#enable-debug-mode}

Per risolvere i problemi, puoi abilitare la modalità di debug e ottenere ulteriori informazioni nei registri.

>[!NOTE]
>
>I livelli di registro validi sono DEBUG, INFO, WARN o ERROR. La verbosità dei log è più alta in DEBUG e più bassa in ERROR.

Per utilizzare l&#39;app in modalità di debug su Mac:

1. Aprire una finestra terminale o un prompt dei comandi.

1. Avvia l&#39;app desktop [!DNL Experience Manager] eseguendo il seguente comando:

   `AEM_DESKTOP_LOG_LEVEL=DEBUG open /Applications/Adobe\ Experience\ Manager\ Desktop.app`.

Per abilitare la modalità di debug su Windows:

1. Apri una finestra di comando.

1. Avvia l&#39;app desktop [!DNL Experience Manager] eseguendo il seguente comando:

`AEM_DESKTOP_LOG_LEVEL=DEBUG&"C:\Program Files\Adobe\Adobe Experience Manager Desktop.exe`.

### Cancella cache {#clear-cache-v2}

Esegui i seguenti passaggi:

1. Avvia l&#39;applicazione e connetti un&#39;istanza [!DNL Experience Manager].

1. Apri le preferenze dell&#39;applicazione facendo clic sull&#39;ellissi nell&#39;angolo in alto a destra e selezionando [!UICONTROL Preferences].

1. Individua la voce che visualizza il valore [!UICONTROL Current Cache Size]. Fai clic sull’icona del cestino accanto a questo elemento.

Per cancellare manualmente la cache, procedi con i passaggi seguenti.

>[!CAUTION]
>
>Si tratta di un’operazione potenzialmente distruttiva. Se ci sono modifiche locali al file che non vengono caricate in [!DNL Adobe Experience Manager], tali modifiche andranno perse procedendo.

La cache viene cancellata eliminando la directory della cache dell&#39;applicazione, che si trova nelle preferenze dell&#39;applicazione.

1. Avvia l&#39;applicazione.

1. Apri le preferenze dell&#39;applicazione selezionando i puntini di sospensione nell&#39;angolo in alto a destra e selezionando [!UICONTROL Preferences].

1. Osserva il valore [!UICONTROL Cache Directory] .

   In questa directory sono presenti sottodirectory denominate dopo gli endpoint [!DNL Adobe Experience Manager] codificati. I nomi sono una versione codificata dell&#39;URL di destinazione [!DNL Adobe Experience Manager]. Ad esempio, se l’applicazione esegue il targeting di `localhost:4502`, il nome della directory sarà `localhost_4502`.

Per cancellare la cache, elimina la directory Encoded [!DNL Adobe Experience Manager] Endpoint desiderata. In alternativa, se si elimina l’intera directory specificata nelle preferenze, la cache verrà cancellata per tutte le istanze utilizzate dall’applicazione.

La cancellazione della cache dell’app desktop [!DNL Adobe Experience Manager] è un’attività preliminare per la risoluzione dei problemi che può risolvere diversi problemi. Elimina la cache dalle preferenze dell&#39;app. Consulta [impostare le preferenze](install-upgrade.md#set-preferences). Il percorso predefinito della cartella cache è:

### Conoscere la versione [!DNL Adobe Experience Manager] dell’app desktop {#know-app-version-v2}

Per visualizzare il numero di versione:

1. Avvia l&#39;applicazione.

1. Fai clic sui puntini di sospensione nell&#39;angolo in alto a destra, passa il puntatore del mouse su [!UICONTROL Help], quindi fai clic su [!UICONTROL About].

   Il numero di versione è elencato in questa schermata.

### Impossibile vedere le risorse inserite {#placed-assets-missing}

Se non riesci a visualizzare le risorse inserite nei file di supporto da te o da altri professionisti creativi (ad esempio, file INDD), controlla quanto segue:

* Connessione al server. La connettività di rete debole può arrestare i download delle risorse.

* Dimensione file. Il download e la visualizzazione delle risorse di grandi dimensioni richiedono più tempo.

* Coerenza della lettera di unità. Se le risorse sono state inserite da un utente o da un altro collaboratore durante la mappatura di [!DNL Experience Manager] DAM a una lettera di unità diversa, le risorse inserite non vengono visualizzate.

* Autorizzazioni. Per verificare di disporre delle autorizzazioni necessarie per recuperare le risorse inserite, contatta l’ amministratore di [!DNL Experience Manager] .

### Le modifiche apportate ai file nell’interfaccia utente dell’app desktop non si riflettono immediatamente in [!DNL Adobe Experience Manager]{#changes-on-da-not-visible-on-aem}

[!DNL Adobe Experience Manager] l’app desktop lascia all’utente la facoltà di decidere quando tutte le modifiche apportate a un file devono essere completate. A seconda delle dimensioni e della complessità di un file, il trasferimento della nuova versione di un file a [!DNL Adobe Experience Manager] richiede molto tempo. La progettazione dell&#39;applicazione richiede di ridurre al minimo il numero di volte in cui un file viene trasferito avanti e indietro, invece di indovinare quando le modifiche del file sono complete e vengono caricate automaticamente. Si consiglia all&#39;utente di avviare il trasferimento del file su [!DNL Adobe Experience Manager] scegliendo di caricare le modifiche di un file.

### Problemi durante l&#39;aggiornamento su macOS {#issues-when-upgrading-on-macos}

Talvolta possono verificarsi problemi durante l’aggiornamento dell’ [!DNL Experience Manager] app desktop su macOS. Ciò è causato dalla cartella di sistema legacy per l’ app desktop [!DNL Experience Manager] che impedisce il caricamento corretto delle nuove versioni dell’ app desktop [!DNL Experience Manager]. Per risolvere questo problema, è possibile rimuovere manualmente le cartelle e i file seguenti.

Prima di eseguire i seguenti passaggi, trascina l&#39;applicazione `Adobe Experience Manager Desktop` dalla cartella macOS Applications nel Cestino. Quindi apri il terminale, esegui il seguente comando e fornisci la tua password quando richiesto.

```shell
sudo rm -rf ~/Library/Application\ Support/com.adobe.aem.desktop
sudo rm -rf ~/Library/Preferences/com.adobe.aem.desktop.plist
sudo rm -rf ~/Library/Logs/Adobe\ Experience\ Manager\ Desktop

sudo find /var/folders -type d -name "com.adobe.aem.desktop" | xargs rm -rf
sudo find /var/folders -type d -name "com.adobe.aem.desktop.finderintegration-plugin" | xargs rm -rf
```

### Impossibile caricare i file {#upload-fails}

Se utilizzi l’app desktop con [!DNL Experience Manager] 6.5.1 o versione successiva, aggiorna il connettore S3 o Azure alla versione 1.10.4 o successiva. Risolve il problema di errore di caricamento file relativo a [OAK-8599](https://issues.apache.org/jira/browse/OAK-8599). Vedere [istruzioni di installazione](install-upgrade.md#install-v2).

### [!DNL Experience Manager] problemi di connessione all’app desktop  {#connection-issues}

Se si verificano problemi di connettività generali, ci sono alcuni modi per ottenere ulteriori informazioni sulle prestazioni dell’app desktop [!DNL Experience Manager].

**Controlla il registro delle richieste**

[!DNL Experience Manager] l’app desktop registra tutte le richieste che invia, insieme al codice di risposta di ogni richiesta, in un file di registro dedicato.

1. Apri `request.log` nella directory di registro dell&#39;applicazione per visualizzare queste richieste.

1. Ogni riga del registro rappresenta una richiesta o una risposta. Le richieste avranno un carattere `>` seguito dall’URL richiesto. Le risposte avranno un carattere `<` seguito dal codice di risposta e dall’URL richiesto. Le richieste e la risposta possono essere soddisfatte utilizzando il GUID di ogni riga.

**Controlla le richieste caricate dal browser incorporato dell&#39;applicazione**

La maggior parte delle richieste dell&#39;applicazione si trovano nel registro delle richieste. Tuttavia, se non sono presenti informazioni utili, può essere utile esaminare le richieste inviate dal browser incorporato dell&#39;applicazione.
Per istruzioni su come visualizzare tali richieste, consulta la sezione [SAML](#da-connection-issue-with-saml-aem) .

#### Autenticazione di accesso SAML non funzionante {#da-connection-issue-with-saml-aem}

[!DNL Experience Manager] l’app desktop potrebbe non connettersi alla  [!DNL Adobe Experience Manager] distribuzione con abilitazione SSO (SAML). Il design dell&#39;applicazione cerca di adattarsi alle variazioni e alle complessità delle connessioni e dei processi SSO. Tuttavia, una configurazione potrebbe richiedere ulteriori interventi di risoluzione dei problemi.

A volte il processo SAML non reindirizza al percorso originariamente richiesto, o il reindirizzamento finale è a un host diverso da quello configurato nell’ [!DNL Adobe Experience Manager] app desktop. Per verificare che non sia così:

1. Apri un browser web. Accedi all&#39;URL `https://[aem_server]:[port]/content/dam.json`.

1. Accedi alla distribuzione [!DNL Adobe Experience Manager].

1. Al termine dell&#39;accesso, controlla l&#39;indirizzo corrente del browser nella barra degli indirizzi. Dovrebbe corrispondere esattamente all’URL immesso inizialmente.

1. Verifica anche che tutti gli elementi precedenti a `/content/dam.json` corrispondano al valore [!DNL Adobe Experience Manager] di destinazione configurato nelle impostazioni dell’ [!DNL Adobe Experience Manager] app desktop.

**Il processo SAML di accesso funziona correttamente in base ai passaggi precedenti, ma gli utenti non sono ancora in grado di accedere**

La finestra all’interno dell’ [!DNL Adobe Experience Manager] app desktop che visualizza il processo di accesso è semplicemente un browser web che visualizza l’interfaccia utente Web dell’istanza di destinazione [!DNL Adobe Experience Manager]:

* La versione Mac utilizza un [WebView](https://developer.apple.com/documentation/webkit/webview).

* La versione Windows utilizza Chromium-based [CefSharp](https://cefsharp.github.io/).

Assicurati che il processo SAML supporti tali browser.

Per risolvere ulteriormente i problemi, è possibile visualizzare gli URL esatti che il browser sta tentando di caricare. Per visualizzare queste informazioni:

1. Seguire le istruzioni per avviare l&#39;applicazione in [modalità di debug](#enable-debug-mode).

1. Riproduci il tentativo di accesso.

1. Passa alla [directory di log](#check-log-files-v2) dell&#39;applicazione

1. Per Windows:

   1. Apri &quot;aemcompanionlog.txt&quot;.

   1. Cerca i messaggi che iniziano con &quot;Indirizzo browser di accesso modificato in&quot;. Queste voci contengono anche l&#39;URL caricato dall&#39;applicazione.

   Per Mac:

   1. `com.adobe.aem.desktop-nnnnnnnn-nnnnnn.log`, dove il nome  **** viene sostituito da qualsiasi numero presente nel nome di file più recente.

   1. Cerca i messaggi che iniziano con &quot;frame caricato&quot;. Queste voci contengono anche l&#39;URL caricato dall&#39;applicazione.


Osservare la sequenza URL caricata può aiutare a risolvere i problemi alla fine di SAML per determinare cosa è sbagliato.

#### Problema di configurazione SSL {#ssl-config-v2}

Le librerie utilizzate dall’app desktop [!DNL Experience Manager] per la comunicazione HTTP utilizzano l’applicazione SSL restrittiva. A volte, una connessione può avere esito positivo utilizzando un browser ma non riesce a utilizzare l’ [!DNL Experience Manager] app desktop. Per configurare SSL in modo appropriato, installa il certificato intermedio mancante in Apache. Vedere [Come installare un certificato CA intermedio in Apache](https://access.redhat.com/solutions/43575).

Le librerie utilizzate dall’app desktop [!DNL Experience Manager] per la comunicazione HTTP utilizzano un’applicazione SSL restrittiva. Ci possono essere quindi casi in cui le connessioni SSL che hanno successo tramite un browser non riescono con l’ [!DNL Adobe Experience Manager] app desktop. Questo è positivo perché incoraggia la corretta configurazione di SSL e aumenta la sicurezza, ma può essere frustrante quando l&#39;applicazione non è in grado di connettersi.

In questo caso, l’approccio consigliato consiste nell’utilizzare uno strumento per analizzare il certificato SSL di un server e identificare i problemi in modo che possano essere corretti. Ci sono siti web che controllano il certificato di un server quando fornisce il suo URL.

Come misura temporanea, è possibile disabilitare l’imposizione SSL restrittiva nell’app desktop [!DNL Adobe Experience Manager]. Questa non è una soluzione a lungo termine consigliata, in quanto riduce la sicurezza nascondendo la causa principale di SSL configurato in modo errato. Per disabilitare l&#39;applicazione rigorosa:

1. Utilizza l&#39;editor desiderato per modificare il file di configurazione JavaScript dell&#39;applicazione, che si trova (per impostazione predefinita) nelle seguenti posizioni (a seconda del sistema operativo):

   Su Mac: `/Applications/Adobe Experience Manager Desktop.app/Contents/Resources/javascript/lib-smb/config.json`

   In Windows: `C:\Program Files (x86)\Adobe\Adobe Experience Manager Desktop\javascript\config.json`

1. Individua la seguente sezione nel file :

   ```shell
   ...
   "assetRepository": {
       "options": {
   ...
   ```

1. Modifica la sezione aggiungendo `"strictSSL": false` come segue:

   ```shell
   ...
   "assetRepository": {
       "options": {
           "strictSSL": false,
   ...
   ```

1. Salva il file e riavvia l&#39;app desktop [!DNL Adobe Experience Manager].

### L&#39;app non risponde {#unresponsive}

Raramente l&#39;applicazione può diventare non reattiva, visualizzare solo uno schermo bianco o visualizzare un errore nella parte inferiore dell&#39;interfaccia senza alcuna opzione sull&#39;interfaccia. Prova quanto segue nell&#39;ordine:

* Fai clic con il pulsante destro del mouse sull&#39;interfaccia dell&#39;applicazione e fai clic su **[!UICONTROL Refresh]**.
* Esci dall’applicazione e riaprila.

In entrambi i metodi, l’app viene avviata dalla cartella DAM principale.

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
>* [Evitare la modifica dei conflitti](using.md#adv-workflow-collaborate-avoid-conflicts)

