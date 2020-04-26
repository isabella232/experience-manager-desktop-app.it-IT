---
title: Procedure ottimali per la risoluzione dei problemi relativi all’app desktop Adobe Experience Manager
description: Seguite le procedure ottimali e risolvete eventuali problemi relativi a installazione, aggiornamento, configurazione e così via.
uuid: ce98a3e7-5454-41be-aaaa-4252b3e0f8dd
contentOwner: AG
products: SG_EXPERIENCEMANAGER/6.3/ASSETS
discoiquuid: f5eb222a-6cdf-4ae3-9cf2-755c873f397c
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b92e47456f9e16c24eac43d1c5fef9a582f143b5

---


# Troubleshoot Adobe Experience Manager desktop app {#troubleshoot-v2}

L’app desktop Adobe Experience Manager (AEM) si connette a un archivio DAM (Digital Asset Management) di una distribuzione remota di Experience Manager. L&#39;app raccoglie informazioni sull&#39;archivio e risultati della ricerca sul computer, scarica e carica file e cartelle, e include funzionalità per gestire i conflitti con l&#39;interfaccia utente di Risorse AEM.

Continua a leggere per risolvere i problemi dell&#39;app, conoscere le procedure ottimali e individuare i limiti.

## Best practices {#best-practices-to-prevent-troubles}

Seguite le procedure ottimali riportate di seguito per evitare problemi comuni e risolvere eventuali problemi.

* **Scoprite come funziona** l&#39;app desktop: Prima di iniziare a utilizzare l&#39;applicazione, trascorri alcuni minuti a sapere come funziona l&#39;app. Informazioni sui collegamenti tra l&#39;interfaccia utente Web e il desktop, la mappatura dell&#39;archivio, il caching delle risorse, il salvataggio locale e il caricamento in background. Vedete [come funziona](release-notes.md#how-app-works).

* **Evitate i caratteri non supportati nei nomi** delle cartelle: Non utilizzate spazi bianchi e caratteri non validi durante la creazione o il caricamento di cartelle. Consulta un elenco di caratteri in [Creazione di cartelle in Experience Manager Assets](https://docs.adobe.com/content/help/en/experience-manager-65/assets/managing/managing-assets-touch-ui.html#Creatingfolders). Alcuni casi di utilizzo di Adobe Experience Manager potrebbero essere influenzati da caratteri non supportati nel nome della cartella.

* **Procedure ottimali per evitare conflitti**: Per evitare potenziali conflitti durante la collaborazione su più risorse, consultate [evitare conflitti](using.md#adv-workflow-collaborate-avoid-conflicts)di modifica.

* **Usate il caricamento delle cartelle per le cartelle** gerarchiche di grandi dimensioni: Invece di usare l’interfaccia Web di Assets o altri metodi, usa l’app desktop Experience Manager per caricare cartelle di grandi dimensioni. L&#39;app carica le risorse in background con registrazione e monitoraggio. Consultate Caricare [in blocco le risorse](using.md#bulk-upload-assets).

* **Utilizzate la versione** più recente: Utilizzate la versione più recente dell&#39;app e verificate sempre la compatibilità prima di installare una nuova versione dell&#39;app o prima di eseguire l&#39;aggiornamento a una versione più recente di Adobe Experience Manager. See [release notes](release-notes.md).

* **Utilizzare la stessa lettera** di unità: Utilizzate la stessa lettera di unità all&#39;interno di un&#39;organizzazione per eseguire la mappatura su Adobe Experience Manager DAM. Per visualizzare le risorse inserite da altri utenti, i percorsi devono essere identici. L&#39;utilizzo della stessa lettera di unità assicura un percorso costante alle risorse DAM. Le risorse rimangono posizionate e non vengono rimosse anche se diversi utenti utilizzano lettere di unità.

* **Tenere presente la rete**: Le prestazioni di rete sono fondamentali per le prestazioni dell&#39;app desktop Experience Manager. Se devi affrontare una risposta rallentata a trasferimenti di file o operazioni in blocco, disattiva le funzionalità o le app che potrebbero causare un sacco di traffico di rete.

* **Casi di utilizzo non supportati per l’app** desktop: non utilizzate l&#39;app per la migrazione delle risorse (necessita di pianificazione e altri strumenti); per operazioni DAM complesse (come lo spostamento di grandi cartelle, caricamenti di grandi dimensioni, la ricerca di file tramite ricerche avanzate di metadati); come client di sincronizzazione (i principi di progettazione e i pattern di utilizzo sono diversi dai client in-sync come Microsoft OneDrive o Adobe Creative Cloud Desktop Sync).

* **Timeout**: Attualmente, l&#39;app desktop non dispone di un valore di timeout configurabile che disconnette la connessione tra il server Experience Manager e l&#39;app desktop dopo un intervallo di tempo fisso. Quando caricate risorse di grandi dimensioni, se la connessione riceve il timeout dopo un po&#39;, l&#39;app tenta nuovamente di caricare la risorsa alcune volte aumentando il timeout di caricamento. Non è consigliato modificare le impostazioni di timeout predefinite.

## Come risolvere i problemi {#troubleshooting-prep}

Per risolvere i problemi relativi all&#39;app desktop, tenete presenti le informazioni seguenti. Inoltre, se desideri ottenere assistenza, puoi trasmetterle meglio all&#39;Assistenza clienti Adobe.

### Abilita modalità di debug {#enable-debug-mode}

Per risolvere i problemi, puoi abilitare la modalità di debug e ottenere ulteriori informazioni nei registri. Per utilizzare l&#39;app in modalità di debug su Mac, utilizzate le seguenti opzioni della riga di comando in un terminale o al prompt dei comandi: `AEM_DESKTOP_LOG_LEVEL=DEBUG open /Applications/Adobe\ Experience\ Manager\ Desktop.app`.

Per abilitare la modalità di debug in Windows, procedere come segue:

1. Individuate `Adobe Experience Manager Desktop.exe.config` il file nella cartella di installazione dell&#39;app desktop. By default, the folder is `C:\Program Files\Adobe\Adobe Experience Manager Desktop`. Salvate e chiudete il file.

1. Individuare `<level value="INFO"/>` verso la fine del file. Modificate il valore in `DEBUG`, ovvero `<level value="DEBUG"/>`.

1. Individuate `logging.json` il file nella cartella di installazione dell&#39;app desktop. By default, the folder is `C:\Program Files\Adobe\Adobe Experience Manager Desktop\javascript\`.

1. Nel `logging.json` file, individua tutte le istanze del `level` parametro. Modificate i valori da `info` a `debug`. Salvate e chiudete il file.

1. Cancella le directory memorizzate nella cache che si trovano nel percorso impostato nelle preferenze dell&#39;app.

1. Riavviate l&#39;app desktop.

<!-- The Windows command doesn't work for now.
* On Windows: `SET AEM_DESKTOP_LOG_LEVEL=DEBUG & "C:\Program Files\Adobe\Adobe Experience Manager Desktop\Adobe Experience Manager Desktop.exe"`
-->

### Posizione dei file di registro {#check-log-files-v2}

I file di registro per l&#39;app desktop AEM si trovano nelle seguenti posizioni. Quando caricate molte risorse, se alcuni file non vengono caricati, consultate `backend.log` file per identificare i caricamenti non riusciti.

* Percorso in Windows: `%LocalAppData%\Adobe\AssetsCompanion\Logs`

* Percorso in Mac: `~/Library/Logs/Adobe\ Experience\ Manager\ Desktop`

>[!NOTE]
>
>Quando lavorate con l&#39;Assistenza clienti Adobe su una richiesta di assistenza o un ticket di assistenza, potrebbe essere necessario condividere i file di registro per aiutare il team di assistenza clienti a comprendere il problema. Archivia l&#39;intera `Logs` cartella e condividila con l&#39;Assistenza clienti.

### Cancella cache {#clear-cache-v2}

La cancellazione della cache dell&#39;app desktop AEM è un&#39;attività preliminare di risoluzione dei problemi che può risolvere diversi problemi. Cancella la cache dalle preferenze dell&#39;app. Consultate [Impostare le preferenze](install-upgrade.md#set-preferences). Il percorso predefinito della cartella della cache è:

* In Windows: `%LocalAppData%\Adobe\AssetsCompanion\Cache\`

* In Mac: `~/Library/Group/Containers/group.com.adobe.aem.desktop/cache/`

Tuttavia, la posizione può cambiare a seconda dell’endpoint AEM configurato dal desktop AEM. Il valore è una versione codificata dell’URL di destinazione. Ad esempio, se l&#39;applicazione esegue il targeting `http://localhost:4502`, il nome della directory è `http%3A%2F%2Flocalhost%3A4502%2F`. Per cancellare la cache, eliminate la cartella appropriata. Un altro motivo per cancellare la cache è liberare spazio su disco quando lo spazio su disco è insufficiente.

>[!CAUTION]
>
>Se cancellate la cache desktop di AEM, le modifiche delle risorse locali non sincronizzate con il server AEM andranno definitivamente perse.

### Conoscere la versione dell&#39;app desktop AEM {#know-app-version-v2}

Fai clic sul menu ![](assets/do-not-localize/more_options_da2.png) App per aprire il menu dell&#39;app e fai clic su **[!UICONTROL Help]** > **[!UICONTROL About]**.

## Impossibile visualizzare le risorse inserite {#placed-assets-missing}

Se non riuscite a visualizzare le risorse inserite nei file di supporto da voi o da altri professionisti del settore creativo (ad esempio, file INDD), controllate quanto segue:

* Connessione al server. Una connettività di rete debole può arrestare i download delle risorse.
* Dimensione file. Il download e la visualizzazione delle risorse grandi richiedono più tempo.
* Coerenza con le lettere dell&#39;unità. Se le risorse sono state inserite da un collaboratore durante la mappatura di AEM DAM a una diversa lettera di unità, le risorse inserite non vengono visualizzate.
* Autorizzazioni. Per verificare di disporre delle autorizzazioni necessarie per recuperare le risorse inserite, contattate l’amministratore AEM.

## Problemi durante l&#39;aggiornamento su macOS {#issues-when-upgrading-on-macos}

Talvolta possono verificarsi problemi durante l&#39;aggiornamento dell&#39;app desktop AEM su macOS. Ciò è causato dalla cartella di sistema precedente per l&#39;app desktop AEM che non consente il caricamento corretto delle nuove versioni dell&#39;app desktop AEM. Per risolvere questo problema, è possibile rimuovere manualmente le cartelle e i file seguenti.

Prima di eseguire i seguenti passaggi, trascinate l’ `Adobe Experience Manager Desktop` applicazione dalla cartella delle applicazioni macOS al cestino. Aprite quindi il terminale, eseguite il comando seguente e fornite la password quando richiesto.

```shell
sudo rm -rf ~/Library/Application\ Support/com.adobe.aem.desktop
sudo rm -rf ~/Library/Preferences/com.adobe.aem.desktop.plist
sudo rm -rf ~/Library/Logs/Adobe\ Experience\ Manager\ Desktop

sudo find /var/folders -type d -name "com.adobe.aem.desktop" | xargs rm -rf
sudo find /var/folders -type d -name "com.adobe.aem.desktop.finderintegration-plugin" | xargs rm -rf
```

## Impossibile caricare i file {#upload-fails}

Se utilizzi un’app desktop con AEM 6.5.1 o versione successiva, aggiorna il connettore S3 o Azure alla versione 1.10.4 o successiva. Risolve il problema di errore di caricamento dei file relativo a [OAK-8599](https://issues.apache.org/jira/browse/OAK-8599). Consultate [le istruzioni](install-upgrade.md#install-v2)di installazione.

## Problema di configurazione SSL {#ssl-config-v2}

Le librerie utilizzate dall’app desktop AEM per la comunicazione HTTP utilizzano l’applicazione SSL restrittiva. Talvolta, una connessione può avere esito positivo utilizzando un browser ma non può essere utilizzata correttamente dall&#39;app desktop AEM. Per configurare SSL in modo appropriato, installate il certificato intermedio mancante in Apache. Vedere [Come installare un certificato CA intermedio in Apache](https://access.redhat.com/solutions/43575).

## L&#39;app non risponde {#unresponsive}

Raramente l&#39;applicazione potrebbe non rispondere, visualizzare solo uno schermo bianco, o visualizzare un errore nella parte inferiore dell&#39;interfaccia senza alcuna opzione sull&#39;interfaccia. Effettuate le seguenti operazioni nell&#39;ordine:

1. Fare clic con il pulsante destro del mouse sull&#39;interfaccia dell&#39;applicazione e scegliere **[!UICONTROL Refresh]**.
1. Uscire dall’applicazione e riavviarla.

In entrambi i metodi, l&#39;app inizia dalla cartella DAM principale.

>[!MORELIKETHIS]
>
>* [Problemi noti](release-notes.md#known-issues-v2)
>* [Evitare conflitti di modifica](using.md#adv-workflow-collaborate-avoid-conflicts)