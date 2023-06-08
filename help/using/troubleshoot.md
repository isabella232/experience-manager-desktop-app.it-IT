---
title: Best practice per la risoluzione dei problemi di e [!DNL Adobe Experience Manager] app desktop
description: Segui le best practice e risolvi eventuali problemi relativi all’installazione, all’aggiornamento, alla configurazione e così via.
exl-id: f388e4ac-907d-4093-ba6f-86ecdafeb015
source-git-commit: df5283f6bef6adbb007bf93c6dabb3b12e430f58
workflow-type: tm+mt
source-wordcount: '2260'
ht-degree: 0%

---

# Risoluzione dei problemi [!DNL Adobe Experience Manager] app desktop {#troubleshoot-v2}

[!DNL Adobe Experience Manager] l’app desktop si connette a un [!DNL Experience Manager] dell’archivio Digital Asset Management (DAM) della distribuzione. L’app recupera sul computer le informazioni dell’archivio e i risultati della ricerca, scarica e carica file e cartelle e include funzionalità per gestire i conflitti con l’interfaccia utente di Assets.

Continua a leggere per risolvere i problemi dell’app, scoprire le best practice e le limitazioni.

## Best practice {#best-practices-to-prevent-troubles}

Per evitare alcuni problemi comuni e la relativa risoluzione, attieniti alle seguenti best practice.

* **Comprendere come funziona l’app desktop**: prima di iniziare a utilizzare l’applicazione, passa qualche istante a conoscere il funzionamento dell’app. Conoscere i collegamenti tra [!DNL Experience Manager] interfaccia web e desktop, mappatura dell’archivio, memorizzazione in cache delle risorse, salvataggio locale e caricamento in background. Consulta [come funziona](release-notes.md#how-app-works).

* **Evitare caratteri non supportati nei nomi delle cartelle**: non utilizzare spazi vuoti e caratteri non validi durante la creazione o il caricamento di cartelle. Visualizza un elenco di caratteri in [Creare cartelle in [!DNL Experience Manager Assets]](https://experienceleague.adobe.com/docs/experience-manager-65/assets/managing/manage-assets.html#creating-folders). Alcuni [!DNL Experience Manager] i casi di utilizzo possono essere influenzati da caratteri non supportati nel nome della cartella.

* **Best practice per evitare conflitti**: per evitare potenziali conflitti durante la collaborazione su più risorse, consulta [evitare la modifica di conflitti](using.md#adv-workflow-collaborate-avoid-conflicts).

* **Utilizzare il caricamento delle cartelle per le cartelle gerarchiche di grandi dimensioni**: invece di utilizzare l’interfaccia web di Assets o altri metodi, utilizza [!DNL Experience Manager] app desktop per caricare cartelle di grandi dimensioni. L’app carica le risorse in background con la registrazione e il monitoraggio. Consulta [risorse caricate in blocco](using.md#bulk-upload-assets).

* **Usa la versione più recente**: utilizza la versione più recente dell’app e verifica sempre la compatibilità prima di installare una nuova versione dell’app o prima di effettuare l’aggiornamento a una più recente [!DNL Experience Manager] versione. Consulta [note sulla versione](release-notes.md).

* **Usa la stessa lettera di unità**: utilizza la stessa lettera di unità in un’organizzazione per la mappatura su [!DNL Experience Manager] DAM Per visualizzare le risorse posizionate da altri utenti, i percorsi devono essere gli stessi. L’utilizzo della stessa lettera di unità garantisce un percorso costante per le risorse DAM. Le risorse rimangono posizionate e non vengono rimosse anche se utenti diversi utilizzano lettere di unità diverse.

* **Mind the network**: le prestazioni della rete sono fondamentali per [!DNL Experience Manager] prestazioni dell’app desktop. Se la risposta ai trasferimenti di file o alle operazioni in blocco è rallentata, disattivare le funzionalità o le app che potrebbero causare un notevole traffico di rete.

* **Casi d’uso non supportati per l’app desktop**: non utilizzare l’app per la migrazione di Assets (richiede pianificazione e altri strumenti); per operazioni DAM complesse (come lo spostamento di cartelle di grandi dimensioni, caricamenti di grandi dimensioni, la ricerca di file tramite ricerche avanzate di metadati); e come client di sincronizzazione (i principi di progettazione e i modelli di utilizzo sono diversi dai client sincronizzati come Microsoft OneDrive o Adobe Creative Cloud Desktop Sync).

* **Timeout**: attualmente, l’app desktop non dispone di un valore di timeout configurabile che disconnette la connessione tra [!DNL Experience Manager] server e app desktop dopo un intervallo di tempo fisso. Quando si caricano risorse di grandi dimensioni, se dopo un po’ la connessione si interrompe, l’app ritenta di caricare la risorsa un paio di volte, aumentando il timeout di caricamento. Non esiste un metodo consigliato per modificare le impostazioni di timeout predefinite.

## Come risolvere i problemi {#troubleshooting-prep}

Per risolvere i problemi relativi all’app desktop, tieni presente le seguenti informazioni. Inoltre, se scegli di richiedere assistenza, ti prepara a trasmettere meglio i problemi ad Adobi dell’Assistenza clienti.

### Percorso dei file di registro {#check-log-files-v2}

[!DNL Experience Manager] l’app desktop memorizza i file di registro nelle seguenti posizioni, a seconda del sistema operativo:

In Windows: `%LocalAppData%\Adobe\AssetsCompanion\Logs`

Su Mac: `~/Library/Logs/Adobe\ Experience\ Manager\ Desktop`

Se durante il caricamento di molte risorse alcuni file non vengono caricati, consulta `backend.log` per identificare i caricamenti non riusciti.

>[!NOTE]
>
>Quando lavori con l’Assistenza clienti Adobe per una richiesta di supporto o un ticket, ti può essere chiesto di condividere i file di registro per aiutare il team di Assistenza clienti a comprendere il problema. Archivia l&#39;intero `Logs` e condividerlo con il contatto dell&#39;Assistenza clienti.

### Cambia il livello di dettagli nei file di registro {#level-of-details-in-log}

Per modificare il livello dei dettagli nei file di registro:

1. Verificare che l&#39;applicazione non sia in esecuzione.

1. Sul sistema Windows:

   1. Aprire una finestra di comando.

   1. Launch [!DNL Adobe Experience Manager] app desktop eseguendo il comando:

   ```shell
   set AEM_DESKTOP_LOG_LEVEL=DEBUG&"C:\Program Files\Adobe\Adobe Experience Manager Desktop.exe
   ```

   Sul sistema Mac:

   1. Apri una finestra del terminale.

   1. Launch [!DNL Adobe Experience Manager] app desktop eseguendo il comando:

   ```shell
   AEM_DESKTOP_LOG_LEVEL=DEBUG open /Applications/Adobe\ Experience\ Manager\ Desktop.app
   ```

I livelli di registro validi sono DEBUG, INFO, WARN o ERROR. Il livello di dettaglio dei registri è il più alto in DEBUG e il più basso in ERROR.

### Abilita modalità di debug {#enable-debug-mode}

Per la risoluzione dei problemi, puoi abilitare la modalità di debug e ottenere ulteriori informazioni nei registri.

>[!NOTE]
>
>I livelli di registro validi sono DEBUG, INFO, WARN o ERROR. Il livello di dettaglio dei registri è il più alto in DEBUG e il più basso in ERROR.

Per utilizzare l’app in modalità di debug su Mac:

1. Aprire una finestra del terminale o un prompt dei comandi.

1. Avvia il [!DNL Experience Manager] nell’app desktop eseguendo il comando seguente:

   `AEM_DESKTOP_LOG_LEVEL=DEBUG open /Applications/Adobe\ Experience\ Manager\ Desktop.app`.

Per attivare la modalità di debug in Windows:

1. Aprire una finestra di comando.

1. Launch [!DNL Experience Manager] nell’app desktop eseguendo il comando seguente:

`AEM_DESKTOP_LOG_LEVEL=DEBUG&"C:\Program Files\Adobe\Adobe Experience Manager Desktop.exe`.

### Conoscere [!DNL Adobe Experience Manager] versione dell’app desktop {#know-app-version-v2}

Per visualizzare il numero di versione:

1. Avvia l’applicazione.

1. Fai clic sull’ellissi in alto a destra, passa il puntatore del mouse su [!UICONTROL Help], quindi fai clic su [!UICONTROL About].

   Il numero di versione è elencato in questa schermata.

### Cancella cache {#clear-cache-v2}

Effettua le seguenti operazioni:

1. Avvia l’applicazione e connetti e [!DNL Experience Manager] dell&#39;istanza.

1. Apri le preferenze dell’applicazione facendo clic sui puntini di sospensione nell’angolo in alto a destra e selezionando [!UICONTROL Preferences].

1. Individuare la voce che visualizza [!UICONTROL Current Cache Size]. Fai clic sull’icona del cestino accanto a questo elemento.

Per cancellare manualmente la cache, procedi come segue.

>[!CAUTION]
>
>Si tratta di un&#39;operazione potenzialmente distruttiva. Se sono presenti modifiche al file locale non caricate in [!DNL Adobe Experience Manager], tali modifiche andranno perdute procedendo.

La cache viene cancellata eliminando la directory cache dell&#39;applicazione, che si trova nelle preferenze dell&#39;applicazione.

1. Avvia l’applicazione.

1. Apri le preferenze dell’applicazione selezionando i puntini di sospensione nell’angolo in alto a destra e selezionando [!UICONTROL Preferences].

1. Osserva [!UICONTROL Cache Directory] valore.

   In questa directory sono presenti sottodirectory denominate in base al [!DNL Adobe Experience Manager] Endpoint. I nomi sono una versione codificata della destinazione [!DNL Adobe Experience Manager] URL. Ad esempio, se l’applicazione è il targeting `localhost:4502` il nome della directory sarà `localhost_4502`.

Per cancellare la cache, elimina la codifica desiderata [!DNL Adobe Experience Manager] Directory endpoint. In alternativa, se si elimina l&#39;intera directory specificata nelle preferenze, la cache verrà cancellata per tutte le istanze utilizzate dall&#39;applicazione.

Cancellazione [!DNL Adobe Experience Manager] La cache dell’app desktop è un’attività preliminare di risoluzione dei problemi che può risolvere diversi problemi. Cancella la cache dalle preferenze dell’app. Consulta [impostare le preferenze](install-upgrade.md#set-preferences). La posizione predefinita della cartella della cache è:

## Impossibile visualizzare le risorse inserite {#placed-assets-missing}

Se non riesci a visualizzare le risorse inserite da te o da altri professionisti creativi nei file di supporto (ad esempio, file INDD), verifica quanto segue:

* Connessione al server. Una connettività di rete inadeguata può bloccare i download delle risorse.

* Dimensione file. Il download e la visualizzazione delle risorse di grandi dimensioni richiedono più tempo.

* Coerenza lettera unità. Se tu o un altro collaboratore avete posizionato le risorse durante la mappatura di [!DNL Experience Manager] DAM in una lettera di unità diversa, le risorse inserite non vengono visualizzate.

* Autorizzazioni. Per verificare se disponi delle autorizzazioni necessarie per recuperare le risorse inserite, contatta il [!DNL Experience Manager] amministratore.

### Le modifiche ai file nell’interfaccia utente dell’app desktop non si riflettono in [!DNL Adobe Experience Manager] immediatamente {#changes-on-da-not-visible-on-aem}

[!DNL Adobe Experience Manager] L’app desktop consente all’utente di decidere quando tutte le modifiche apportate a un file sono state completate. A seconda delle dimensioni e della complessità di un file, il trasferimento della nuova versione di un file a richiede molto tempo [!DNL Adobe Experience Manager]. La progettazione dell’applicazione richiede di ridurre al minimo il numero di volte in cui un file viene trasferito avanti e indietro, invece di indovinare quando le modifiche al file sono complete e vengono caricate automaticamente. È consigliabile che l’utente avvii nuovamente il trasferimento del file a [!DNL Adobe Experience Manager] scegliendo di caricare le modifiche di un file.

### Problemi durante l’aggiornamento su macOS {#issues-when-upgrading-on-macos}

Talvolta possono verificarsi problemi durante l’aggiornamento [!DNL Experience Manager] app desktop su macOS. Questo problema è causato dalla cartella di sistema legacy per [!DNL Experience Manager] l&#39;app desktop impedisce nuove versioni di [!DNL Experience Manager] l&#39;app desktop da caricare correttamente. Per risolvere questo problema, è possibile rimuovere manualmente le cartelle e i file seguenti.

Prima di eseguire i passaggi seguenti, trascina `Adobe Experience Manager Desktop` dalla cartella macOS Applications al Cestino. Quindi aprire il terminale, eseguire il comando seguente e fornire la password quando richiesto.

```shell
sudo rm -rf ~/Library/Application\ Support/com.adobe.aem.desktop
sudo rm -rf ~/Library/Preferences/com.adobe.aem.desktop.plist
sudo rm -rf ~/Library/Logs/Adobe\ Experience\ Manager\ Desktop

sudo find /var/folders -type d -name "com.adobe.aem.desktop" | xargs rm -rf
sudo find /var/folders -type d -name "com.adobe.aem.desktop.finderintegration-plugin" | xargs rm -rf
```

## Impossibile caricare i file {#upload-fails}

Se utilizzi un’app desktop con [!DNL Experience Manager] 6.5.1 o versione successiva, aggiorna il connettore S3 o Azure alla versione 1.10.4 o successiva. Risolve i problemi di caricamento dei file relativi a [OAK-8599](https://issues.apache.org/jira/browse/OAK-8599). Consulta [istruzioni di installazione](install-upgrade.md#install-v2).

## [!DNL Experience Manager] problemi di connessione all’app desktop {#connection-issues}

Se si verificano problemi generali di connettività, ecco alcuni modi per ottenere ulteriori informazioni su [!DNL Experience Manager] l’app desktop sta procedendo.

**Controllare il registro delle richieste**

[!DNL Experience Manager] l’app desktop registra tutte le richieste inviate, insieme al codice di risposta di ogni richiesta, in un file di registro dedicato.

1. Apri `request.log` nella directory di registro dell’applicazione per visualizzare queste richieste.

1. Ogni riga del registro rappresenta una richiesta o una risposta. Le richieste avranno un `>` seguito dall&#39;URL richiesto. Le risposte avranno un `<` seguito dal codice di risposta e dall’URL richiesto. Le richieste e le risposte possono essere associate utilizzando il GUID di ogni riga.

**Controllare le richieste caricate dal browser incorporato dell’applicazione**

La maggior parte delle richieste dell’applicazione si trova nel registro delle richieste. Tuttavia, se non ci sono informazioni utili, può essere utile esaminare le richieste inviate dal browser incorporato dell’applicazione.
Consulta la [Sezione SAML](#da-connection-issue-with-saml-aem) per istruzioni su come visualizzare tali richieste.

### L’autenticazione dell’accesso SAML non funziona {#da-connection-issue-with-saml-aem}

[!DNL Experience Manager] L&#39;app desktop potrebbe non connettersi a SAML (SSO-enabled) [!DNL Adobe Experience Manager] distribuzione. La progettazione dell’applicazione tenta di adattarsi alle varianti e alle complessità delle connessioni e dei processi SSO. Tuttavia, una configurazione potrebbe richiedere una risoluzione dei problemi aggiuntiva.

A volte il processo SAML non reindirizza al percorso richiesto originariamente oppure il reindirizzamento finale è verso un host diverso da quello configurato in [!DNL Adobe Experience Manager] app desktop. Per verificare che non sia così:

1. Apri un browser web. Accesso `https://[aem_server]:[port]/content/dam.json` URL.

1. Accedi a [!DNL Adobe Experience Manager] distribuzione.

1. Al termine dell’accesso, controlla l’indirizzo corrente del browser nella barra degli indirizzi. Deve corrispondere esattamente all’URL immesso inizialmente.

1. Verifica anche che tutto prima `/content/dam.json` corrisponde al target [!DNL Adobe Experience Manager] valore configurato in [!DNL Adobe Experience Manager] impostazioni dell&#39;app desktop.

**Il processo di accesso SAML funziona correttamente in base ai passaggi precedenti, ma gli utenti non sono ancora in grado di accedere**

La finestra in [!DNL Adobe Experience Manager] l’app desktop che visualizza la procedura di accesso è semplicemente un browser web che visualizza la destinazione [!DNL Adobe Experience Manager] interfaccia utente web dell’istanza:

* La versione di Mac utilizza un [WebView](https://developer.apple.com/documentation/webkit/webview).

* La versione di Windows utilizza Chromium-based [CefSharp](https://cefsharp.github.io/).

Assicurati che il processo SAML supporti tali browser.

Per risolvere ulteriori problemi, è possibile visualizzare gli URL esatti che il browser sta tentando di caricare. Per visualizzare queste informazioni:

1. Seguire le istruzioni per l&#39;avvio dell&#39;applicazione in [modalità debug](#enable-debug-mode).

1. Riproduci il tentativo di accesso.

1. Accedi a [directory di registro](#check-log-files-v2) della domanda

1. Per Windows:

   1. Aprire &quot;aemcompanionlog.txt&quot;.

   1. Cerca i messaggi che iniziano con &quot;Indirizzo del browser di accesso cambiato in&quot;. Queste voci contengono anche l’URL caricato dall’applicazione.

   Per Mac:

   1. `com.adobe.aem.desktop-nnnnnnnn-nnnnnn.log`, in cui **n** vengono sostituiti dai numeri presenti nel nome di file più recente.

   1. Cercare i messaggi che iniziano con &quot;fotogramma caricato&quot;. Queste voci contengono anche l’URL caricato dall’applicazione.

Osservando la sequenza URL in fase di caricamento è possibile risolvere eventuali problemi alla fine del SAML per determinare l’errore.

### Problema di configurazione SSL {#ssl-config-v2}

Le librerie che [!DNL Experience Manager] L’app desktop utilizza per la comunicazione HTTP un’applicazione SSL rigorosa. A volte, una connessione può riuscire utilizzando un browser, ma non riesce utilizzando [!DNL Experience Manager] app desktop. Per configurare SSL in modo appropriato, installa il certificato intermedio mancante in Apache. Consulta [Come installare un certificato CA intermedio in Apache](https://access.redhat.com/solutions/43575).

Le librerie che [!DNL Experience Manager] L’app desktop utilizzata per la comunicazione HTTP utilizza un’applicazione SSL rigorosa. Quindi ci possono essere istanze in cui le connessioni SSL che hanno esito positivo tramite un browser hanno esito negativo con [!DNL Adobe Experience Manager] app desktop. Questo va bene perché incoraggia la corretta configurazione di SSL e aumenta la sicurezza, ma può essere frustrante quando l’applicazione non è in grado di connettersi.

In questo caso, l’approccio consigliato è quello di utilizzare uno strumento per analizzare il certificato SSL di un server e identificare i problemi in modo che possano essere corretti. Esistono siti Web che controllano il certificato di un server quando fornisce il relativo URL.

Come misura temporanea, è possibile disabilitare l’applicazione SSL rigorosa in [!DNL Adobe Experience Manager] app desktop. Questa non è una soluzione consigliata a lungo termine, in quanto riduce la sicurezza nascondendo la causa principale di SSL configurato in modo errato. Per disattivare l&#39;applicazione rigorosa:

1. Utilizza l’editor che preferisci per modificare il file di configurazione JavaScript dell’applicazione, che si trova (per impostazione predefinita) nelle seguenti posizioni (a seconda del sistema operativo):

   Su Mac: `/Applications/Adobe Experience Manager Desktop.app/Contents/Resources/javascript/lib-smb/config.json`

   In Windows: `C:\Program Files (x86)\Adobe\Adobe Experience Manager Desktop\javascript\config.json`

1. Individua la seguente sezione nel file:

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

1. Salva il file e riavvia [!DNL Adobe Experience Manager] app desktop.

### Problemi di accesso quando si passa a un altro server {#cannot-login-cookies-issue}

Dopo aver utilizzato un’ [!DNL Experience Manager] server, quando si tenta di modificare la connessione a un server diverso, potrebbero verificarsi problemi di accesso. Ciò è dovuto all’interferenza dei vecchi cookie con la nuova autenticazione. Un&#39;opzione nel menu principale per [!UICONTROL Clear Cookies] aiuta. Esci dalla sessione corrente nell’app e seleziona [!UICONTROL Clear Cookies] prima di procedere alla connessione.

![Cancella i cookie quando si cambia server](assets/main_menu_logout_da2.png)

## L’app non risponde {#unresponsive}

Raramente l’applicazione potrebbe bloccarsi, visualizzare solo una schermata bianca o visualizzare un errore nella parte inferiore dell’interfaccia senza opzioni. Provare quanto segue nell&#39;ordine:

* Fai clic con il pulsante destro del mouse sull’interfaccia dell’applicazione e fai clic su **[!UICONTROL Refresh]**.
* Chiudere l&#39;applicazione e riaprirla.

In entrambi i metodi, l’app inizia dalla cartella DAM principale.

## Nascondi risorse scadute {#hide-expired-assets}

Quando esplori le risorse da [!DNL Experience Manager] nell’interfaccia utente, le risorse scadute non vengono visualizzate. Per evitare di visualizzare, cercare e recuperare le risorse scadute durante la navigazione dall’app desktop e da Asset Link, gli amministratori possono effettuare la seguente configurazione. La configurazione funziona per tutti gli utenti, indipendentemente dal privilegio di amministratore.

* [Configurazione nell&#39;Experience Manager 6.5 per nascondere le risorse scadute](https://experienceleague.adobe.com/docs/experience-manager-65/assets/managing/manage-assets.html#hide-expired-assets-via-acp-api).
* [Configurazione nell’Experience Manager as a Cloud Service per nascondere le risorse scadute](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/manage-digital-assets.html#hide-expired-assets-via-acp-api).

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
>* [Evita di modificare i conflitti](using.md#adv-workflow-collaborate-avoid-conflicts)
