---
title: Risoluzione dei problemi relativi all'app desktop AEM versione 1.x
description: Risolvi i problemi relativi all'installazione, all'aggiornamento, alla configurazione dell'app desktop AEM versione 1.x e così via.
uuid: ce98a3e7-5454-41be-aaaa-4252b3e0f8dd
contentOwner: AG
products: SG_EXPERIENCEMANAGER/6.3/ASSETS
discoiquuid: f5eb222a-6cdf-4ae3-9cf2-755c873f397c
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: ad5337c8e1697d0a37d3020d25802dc1d732f320

---


# Risoluzione dei problemi relativi all'app desktop AEM v1.x {#troubleshoot-aem-desktop-app}

Risolvi i problemi relativi a installazione, aggiornamento, configurazione e così via relativi all’app desktop AEM.

L’app desktop Adobe Experience Manager (AEM) include utility che consentono di mappare l’archivio di Risorse AEM come condivisione di rete su computer desktop (condivisione SMB su Mac OS). La condivisione di rete è una tecnologia del sistema operativo che consente alle origini remote di essere trattate come se fossero parte del file system locale del computer. Nel caso dell'app desktop, la struttura del repository di gestione delle risorse digitali (DAM) di un'istanza remota di AEM viene indirizzata come origine file remota. Il diagramma seguente descrive la topologia dell'app desktop:

![diagramma app desktop](assets/aem-desktopapp-architecture.png)

Con questa architettura, le app desktop intercettano le chiamate del file system (aperte, vicine, lette, in scrittura, ecc.) per la condivisione di rete montata e le traducono in chiamate AEM HTTP native al server AEM. I file vengono memorizzati nella cache locale. Per ulteriori dettagli, consultate [Utilizzare l'app desktop AEM v1.x](use-app-v1.md).

## AEM desktop app component overview {#desktop-app-component-overview}

l'app desktop include i seguenti componenti:

* **Applicazione** desktop: L'applicazione installa o smonta DAM come file system remoto e traduce le chiamate del file system tra la condivisione di rete montata localmente e l'istanza AEM remota a cui si connette.
* **Client** WebDAV/SMB del sistema operativo: Gestisce la comunicazione tra Windows Explorer/Finder e l'app desktop. Se un file viene recuperato, creato, modificato, eliminato, spostato o copiato, il client WebDAV/SMB del sistema operativo (OS) comunica questa operazione all'app desktop. Dopo aver ricevuto la comunicazione, l'app desktop la trasforma in chiamate API remote AEM native. Ad esempio, se un utente crea un file nella directory montata, il client WebDAV/SMB avvia una richiesta che l'app desktop converte in una richiesta HTTP che crea il file in DAM. Il client WebDAV/SMB è un componente integrato del sistema operativo. Non è in alcun modo collegato all'app desktop, AEM o Adobe.
* **Istanza** Adobe Experience Manager: Consente di accedere alle risorse memorizzate nell'archivio DAM di AEM Assets. Inoltre, esegue le azioni richieste dall'app desktop per conto delle applicazioni desktop locali che interagiscono con la condivisione di rete montata. L’istanza AEM di destinazione deve eseguire AEM versione 6.1 o successiva. Le istanze di AEM che eseguono versioni precedenti di AEM potrebbero richiedere l'installazione di pacchetti di funzioni aggiuntivi e di hotfix per diventare completamente funzionanti.

## Casi di utilizzo previsti per l'app desktop AEM {#intended-use-cases-for-aem-desktop-app}

L'app desktop AEM utilizza la tecnologia di condivisione di rete per mappare un archivio AEM remoto su un desktop locale. Tuttavia, non è inteso come sostituzione di una condivisione di rete con risorse, in cui gli utenti eseguono operazioni di gestione delle risorse digitali direttamente dal desktop locale. Questi includono lo spostamento o la copia di più file o il trascinamento di grandi strutture di cartelle nella condivisione di rete di Risorse AEM direttamente in Finder/Explorer.

L'app desktop AEM fornisce un modo pratico per accedere (aprire) e modificare (salvare) le risorse DAM tra l'interfaccia utente touch di AEM Assets e il desktop locale. Collega le risorse del server AEM Assets ai flussi di lavoro basati su desktop.

L'esempio seguente illustra come utilizzare AEM Desktop:

* Un utente accede ad AEM e utilizza l’interfaccia utente Web per individuare una risorsa.
* Utilizzando le funzionalità di azione desktop dell’interfaccia utente Web di AEM, l’utente può aprire, visualizzare o modificare la risorsa sul desktop, a seconda delle necessità.
* AEM Desktop apre la risorsa nell’editor predefinito per il tipo di file della risorsa.
* L’utente apporta le modifiche desiderate alla risorsa.
* Dopo aver modificato un file, l'utente può visualizzare lo stato di sincronizzazione del file tramite la finestra di stato della sincronizzazione in background di AEM Desktop.
* Utilizzando il menu di scelta rapida di AEM Desktop, l'utente può archiviare o estrarre la risorsa o tornare all'interfaccia utente di DAM.
* Dopo aver completato le modifiche al file, l'utente torna all'interfaccia utente Web di AEM

Questo non è l'unico caso d'uso. Tuttavia, mostra come AEM Desktop sia un meccanismo pratico per accedere/modificare localmente le risorse. È consigliabile utilizzare l'interfaccia utente Web di DAM il più possibile, in quanto offre un'esperienza migliore. Offre ad Adobe maggiore flessibilità per soddisfare le esigenze dei clienti.

## Limiti {#limitations}

La condivisione di rete WebDAV/SMB1 consente di utilizzare i file in una finestra Esplora risorse/Finder. Tuttavia, Explorer/Finder e AEM comunicano mediante una connessione di rete con determinate limitazioni. Ad esempio, il tempo necessario per copiare un file da 1 GB nella directory WebDAV/SMB installata è circa lo stesso del tempo richiesto per caricare un file da 1 GB in un sito Web utilizzando un browser Web. Infatti, nel primo caso, la durata potrebbe essere maggiore a causa di inefficienze del protocollo WebDAV/SMB e dei client WebDAV/SMB del sistema operativo (in particolare Mac OS X).

Esistono limitazioni ai tipi di attività che possono essere eseguite da una directory montata. In generale, l'utilizzo di file di grandi dimensioni, in particolare su una connessione di rete con latenza bassa/bassa, potrebbe risultare difficoltoso, soprattutto quando si modificano file di grandi dimensioni.

Adobe consiglia di eseguire alcuni test di casi d’uso prima di impegnarsi con un cliente per verificare che determinati tipi di file possano essere modificati in modo efficiente al posto della directory montata.

AEM Desktop non è adatto per eseguire operazioni di manipolazione intensiva del file system, compresi, tra l'altro, i seguenti elementi:

* Spostamento o copia di file e directory
* Aggiunta di più risorse ad AEM
* Ricerca e apertura di file attraverso il file system, fatta eccezione per la navigazione delle cartelle
* Compressione o decompressione degli archivi di file

A causa delle limitazioni del sistema operativo, Windows ha un limite di dimensione file di 4.294.967.295 byte (circa 4,29 GB). È dovuto a un'impostazione del Registro di sistema che definisce le dimensioni di un file in una condivisione di rete. Il valore dell'impostazione del Registro di sistema è un DWORD con una dimensione massima uguale al numero di riferimento.

## Cache e comunicazione con AEM {#caching-and-communication-with-aem}

L'app desktop AEM offre funzioni di caching interno e caricamento in background per migliorare l'esperienza dell'utente finale. Quando salvate un file di grandi dimensioni, questo viene prima salvato localmente per consentirvi di continuare a lavorare. Dopo un certo periodo di tempo (al momento 30 secondi), il file viene quindi inviato in background al server AEM.

A differenza di Creative Cloud Desktop o altre soluzioni di sincronizzazione file, come Microsoft One Drive, l'app desktop AEM non è un client di sincronizzazione desktop completo. Questo consente di accedere all’intero archivio di Risorse AEM, che può essere di grandi dimensioni (centinaia di gigabyte o terabyte) per una sincronizzazione completa.

La memorizzazione nella cache consente di limitare il sovraccarico di rete/storage solo a un sottoinsieme di risorse rilevanti per l’utente.

Ecco come l'app desktop AEM esegue la memorizzazione nella cache:

* Quando aprite una cartella nel Finder e vengono visualizzate miniature/anteprime dei file, o quando aprite un file in un’applicazione, l’app desktop memorizza nella cache il file binario.
* Quando archiviate i file tramite Finder o altre applicazioni desktop, il file viene memorizzato localmente per primo (nella cache) e il sistema operativo riceve una notifica. Il file viene quindi messo in coda per il caricamento sul server in background e caricato in rete. In caso di errore di rete, l'app desktop tenta nuovamente di caricare l'intero file per un massimo di tre volte. Se il caricamento non riesce dopo tre tentativi, il file viene contrassegnato come in conflitto e lo stato viene visualizzato tramite la finestra Stato coda di caricamento in background. l'app desktop non tenta più di aggiornare il file. L'utente deve aggiornare il file e ricaricarlo dopo il ripristino della connettività

Ogni operazione non viene memorizzata nella cache locale. Le seguenti informazioni vengono trasmesse immediatamente ad AEM Server senza caching locale:

* Qualsiasi operazione sulle cartelle, ad esempio creazione, eliminazione e così via
* La funzione di caricamento delle cartelle introdotta nella versione 1.4 carica una gerarchia di cartelle locale senza memorizzare i file nella cache locale

## Operazioni individuali {#individual-operations}

Per la risoluzione dei problemi relativi alle prestazioni ottimizzate per singoli utenti, controlla prima [le limitazioni](https://helpx.adobe.com/experience-manager/desktop-app/troubleshooting-desktop-app.html#limitations). Le sezioni successive contengono suggerimenti per migliorare le prestazioni dei singoli utenti.

## Suggerimenti sulla larghezza di banda {#bandwidth-recommendations}

La larghezza di banda disponibile per un singolo utente svolge un ruolo fondamentale nelle prestazioni del client WebDAV/SMB.

Adobe consiglia di avvicinare la velocità di caricamento di un singolo utente a 10 Mbps. Per le connessioni wireless, la larghezza di banda è spesso condivisa tra più utenti. Se più utenti eseguono contemporaneamente attività che richiedono larghezza di banda di rete, le prestazioni possono peggiorare ulteriormente. Per evitare tali problemi, utilizzate una connessione cablata.

## Configurazioni specifiche di Windows {#windows-specific-configurations}

Se si esegue AEM su Windows, è possibile configurare Windows per migliorare le prestazioni del client WebDAV. Per ulteriori informazioni, visitate [https://support.microsoft.com/en-us/kb/2445570](https://support.microsoft.com/en-us/kb/2445570).

In Windows 7, la modifica delle impostazioni IE può migliorare le prestazioni di WebDAV. Per informazioni dettagliate, visitate [http://oddballupdate.com/2009/12/fix-slow-webdav-performance-in-windows-7/](http://oddballupdate.com/2009/12/fix-slow-webdav-performance-in-windows-7/).

## Operazioni simultanee {#concurrent-operations}

Quando interagisci con un file localmente, AEM Desktop verifica se una versione più recente del file è disponibile in AEM. Se è disponibile una nuova versione, l'applicazione scarica una nuova copia del file nella cache locale. Tuttavia, AEM Desktop non sovrascrive un file memorizzato nella cache locale se è stato modificato. Questa funzione impedisce che il lavoro venga sovrascritto accidentalmente.

Quando lo stesso file viene modificato sia localmente che in AEM, la versione modificata localmente sovrascrive la versione in AEM. In questo caso, la versione precedente è disponibile nella timeline della risorsa. È possibile verificare entrambe le versioni e risolvere eventuali conflitti.

Se un file locale non è coerente con la versione disponibile nel server, la finestra di dialogo dello stato di caricamento in background segnala il conflitto. Per risolvere il problema, aprite il file in conflitto e salvatelo. Salvando il file, AEM Desktop sincronizza le ultime modifiche locali con AEM. Potete visualizzare le versioni precedenti della risorsa nella timeline e risolvere eventuali conflitti.

È necessario tenere conto di fattori aggiuntivi quando più utenti tentano di lavorare in directory montate separate per la stessa istanza di AEM. In particolare, sono importanti i seguenti fattori:

* Quantità di larghezza di banda disponibile sulla rete di origine degli utenti
* Configurazione della rete, ad esempio firewall o proxy, della rete di origine
* Quantità di larghezza di banda disponibile nella rete dell’istanza AEM di destinazione
* Se un dispatcher è presente prima dell’istanza AEM di destinazione
* Carico corrente sull’istanza AEM di destinazione

## Configurazioni AEM aggiuntive {#additional-aem-configurations}

Se le prestazioni WebDAV/SMB subiscono un drastico calo quando più utenti lavorano contemporaneamente, in AEM è possibile configurare alcuni elementi che possono contribuire a migliorare le prestazioni.

## Aggiornare i flussi di lavoro transitori delle risorse {#update-asset-transient-workflows}

Puoi migliorare le prestazioni sul lato AEM abilitando flussi di lavoro transitori per il flusso di lavoro Risorse aggiornamento DAM. L’attivazione di flussi di lavoro transitori riduce la potenza di elaborazione necessaria per aggiornare le risorse quando vengono create o modificate in AEM.

1. Passa `/miscadmin` all’istanza di AEM da configurare (ad esempio, `http://[Server]:[Port]/miscadmin`).
1. Dalla struttura di navigazione, espandete **Strumenti** &gt; **Flusso di lavoro** &gt; **Modelli** &gt; **DAM**.
1. Fate doppio clic su **DAM Update Asset (Aggiorna risorsa** DAM).
1. Dal pannello degli strumenti mobili, passate alla scheda **Pagina** e fate clic su Proprietà **** pagina.
1. Selezionate la casella di controllo Flusso di lavoro **** transitorio e fate clic su **OK**.

### Regolare la coda del flusso di lavoro transitorio di Granite {#adjust-granite-transient-workflow-queue}

Un altro metodo per migliorare le prestazioni di AEM consiste nel configurare il valore dei processi paralleli massimi per il processo Coda flusso di lavoro transitoria Granite. Il valore consigliato è circa la metà del numero di CPU disponibile con il server. Per regolare il valore, effettuare le seguenti operazioni:

1. Andate a */system/console/configMgr* nell’istanza AEM da configurare (ad esempio, <http://&lt;Server&gt;:&lt;Port&gt;/system/console/configMgr>).
1. Cercate **QueueConfiguration** e fate clic per aprire ciascun processo fino a individuare il processo **Granite Transient Workflow Queue** . Fate clic sull’icona Modifica accanto a essa.
1. Modificate il valore Processi **paralleli** massimi e fate clic su **Salva**.

## Configurazione AWS {#aws-configuration}

A causa delle limitazioni della larghezza di banda di rete, le prestazioni di WebDAV/SMB possono peggiorare se più utenti lavorano contemporaneamente. Adobe consiglia di aumentare le dimensioni dell’istanza AWS per un’istanza AEM di destinazione in esecuzione su AWS per migliorare le prestazioni di WebDAV/SMB.

Questa misura aumenta in modo specifico la quantità di larghezza di banda disponibile per il server. Di seguito sono riportati alcuni dettagli:

* La quantità di larghezza di banda di rete dedicata a un'istanza AWS aumenta con l'aumentare delle dimensioni dell'istanza. Per informazioni sulla larghezza di banda disponibile per ogni dimensione di istanza, consultate la documentazione [](https://aws.amazon.com/ec2/instance-types/)AWS.
* Durante la risoluzione dei problemi per un client di grandi dimensioni, Adobe ha configurato la dimensione dell’istanza AEM su c4.8xlarge, principalmente per i 4000 Mbps di larghezza di banda dedicata forniti.
* Se l’istanza di AEM è preceduta da un dispatcher, accertati che sia di dimensioni appropriate. Se l’istanza di AEM fornisce 4000 Mbps ma il dispatcher fornisce solo 500 Mbps, la larghezza di banda effettiva è solo 500 Mbps. È perché il dispatcher crea un collo di bottiglia della rete.

## Limitazioni del file estratto {#checked-out-file-limitations}

Esistono alcuni limiti noti per l'interazione con i file estratti tramite Esplora risorse/Finder. Se un file è estratto, deve essere di sola lettura per chiunque, ad eccezione dell'utente che ha estratto il file. L’implementazione del protocollo WebDAV/SMB1 in AEM applica questa regola. Tuttavia, i client WebDAV/SMB del sistema operativo spesso non interagiscono con i file estratti. Alcune stranezze sono descritte di seguito.

### Generale {#general}

Quando si scrive in un file estratto, il blocco viene applicato solo all’implementazione WebDAV di AEM. Di conseguenza, il blocco è imposto solo dai client che utilizzano WebDAV, come l'app desktop. Il blocco non viene imposto tramite l'interfaccia Web di AEM. L'interfaccia di AEM mostra semplicemente un'icona a forma di lucchetto nella vista a schede per le risorse sottoposte a Check-Out. L’icona è cosmetica e non ha alcun effetto sul comportamento di AEM.

In generale, i client WebDAV non si comportano sempre come previsto. Potrebbero verificarsi altri problemi. Tuttavia, l’aggiornamento o il controllo della risorsa in AEM è un metodo efficace per verificare che non venga modificata. Questo comportamento è tipico dei client WebDAV del sistema operativo, che non è sotto il controllo di Adobe.

### Windows {#windows}

L'eliminazione di un file sembra aver esito positivo perché il file scompare dall'elenco dei file in Windows. Tuttavia, l’aggiornamento della directory e il check-in delle risorse AEM mostrano che il file è ancora presente. Inoltre, la modifica dei file sembra aver esito positivo (non vengono visualizzate finestre di dialogo di avviso o messaggi di errore). Tuttavia, se riaprite il file o archiviate le risorse AEM, il file rimane invariato.

#### Mac OS X {#mac-os-x}

La sostituzione di un file non visualizza un avviso o un errore, ma se si verifica la risorsa in AEM, la risorsa rimane invariata. Aggiorna o verifica la risorsa in AEM per verificare che non venga modificata.

## Risoluzione dei problemi relativi alle icone delle app desktop (Mac OS X) {#troubleshooting-desktop-app-icon-issues-mac-os-x}

Dopo aver installato l'app desktop, l'icona del menu dell'app desktop viene visualizzata nella barra dei menu. Se l'icona non viene visualizzata, eseguite i seguenti passaggi per risolvere il problema:

1. Aprire la finestra del terminale del sistema operativo.
1. Digitare il comando seguente al prompt dei comandi, quindi premere Invio:

   ```shell
    cd ../Library/Caches.
   ```

1. Digitate il comando seguente e premete Invio:

   ```shell
   rm -r com.adobe.aem.assetscompanion 
   ```

1. Digitate il comando seguente e premete Invio:

   ```shell
   cd ~/Library/Preferences
   ```

1. Digitate il comando seguente e premete Invio:

   ```shell
   rm com.adobe.aem.assetscompanion.plist
   ```

1. Digitate il comando seguente e premete Invio:

   ```shell
   rm ~/Library/Group\ Containers/group.com.adobe.aem.desktop/*
   ```

1. Riavviate il sistema.

AEM Desktop tenta di sincronizzare ogni file tre volte. Se la sincronizzazione del file non riesce dopo il terzo tentativo, AEM Desktop considera il file in conflitto e invia una notifica tramite la finestra di stato del caricamento in background. Uno stato di conflitto indica che le ultime modifiche sono ancora disponibili localmente, ma non vengono sincronizzate di nuovo in AEM. L'app desktop AEM non tenta più di eseguire la sincronizzazione.

Il modo più semplice per risolvere questa situazione è aprire il file in conflitto e salvarlo di nuovo. Forza AEM Desktop a tentare la sincronizzazione per altre tre volte. Se il file non viene ancora sincronizzato, consulta le sezioni seguenti per ulteriore assistenza.

## Cancellazione della cache desktop di AEM {#clearing-aem-desktop-cache}

La cancellazione della cache di AEM Desktop è un'attività preliminare di risoluzione dei problemi che può risolvere diversi problemi relativi a AEM Desktop.

Potete cancellare la cache eliminando la directory della cache dell'applicazione nelle seguenti posizioni:Windows: %LocalAppData%\Adobe\AssetsCompanion\Cache\

Mac: ~/Library/Group/Containers/group.com.adobe.aem.desktop/cache/

Tuttavia, la posizione può cambiare in base all'endpoint AEM configurato da AEM Desktop. Il valore è una versione codificata dell’URL di destinazione. Ad esempio, se l'applicazione esegue il targeting `http://localhost:4502`, il nome della directory è `http%3A%2F%2Flocalhost%3A4502%2F`.

Per cancellare la cache, eliminate la directory &lt;Endpoint AEM codificato&gt;.

>[!NOTE]
>
>Se cancellate la cache di AEM Desktop, le modifiche ai file locali non sincronizzate con AEM andranno perse.

>[!NOTE]
>
>A partire dalla versione 1.5 dell'app desktop AEM, è disponibile un'opzione nell'interfaccia utente dell'app desktop per cancellare la cache.

## Ricerca della versione desktop di AEM {#finding-the-aem-desktop-version}

La procedura per verificare la versione di AEM Desktop è la stessa per Windows e Mac OS.

Fate clic sull'icona AEM Desktop, quindi scegliete **Informazioni su**. Il numero di versione viene visualizzato sullo schermo.

## Aggiornamento dell'app desktop AEM su macOS {#upgrading-aem-desktop-app-on-macos}

Talvolta possono verificarsi problemi durante l'aggiornamento dell'app desktop AEM su macOS. Ciò è causato dalla cartella di sistema precedente per l'app desktop AEM che non consente il caricamento corretto delle nuove versioni di AEM Desktop. Per risolvere questo problema, è possibile rimuovere manualmente le cartelle e i file seguenti.

Prima di eseguire i passaggi indicati di seguito, trascinate l’applicazione "Adobe Experience Manager Desktop" dalla cartella delle applicazioni macOS al cestino. Aprite quindi il terminale ed eseguite il comando seguente, fornendo la password quando richiesto.

```shell
sudo rm -rf ~/Library/Application\ Support/com.adobe.aem.desktop
sudo rm -rf ~/Library/Preferences/com.adobe.aem.desktop.plist
sudo rm -rf ~/Library/Logs/Adobe\ Experience\ Manager\ Desktop

sudo find /var/folders -type d -name "com.adobe.aem.desktop" | xargs rm -rf
sudo find /var/folders -type d -name "com.adobe.aem.desktop.finderintegration-plugin" | xargs rm -rf
```

## Salvataggio di un file estratto da altri {#saving-a-file-checked-out-by-others}

Le limitazioni tecniche del sistema operativo impediscono agli utenti di avere un'esperienza coerente quando cercano di sovrascrivere un file estratto da altri utenti. L'esperienza varia a seconda dell'applicazione utilizzata per modificare il file estratto. Talvolta, l'applicazione visualizza un messaggio di errore che indica un errore di scrittura su disco o un errore apparentemente non correlato o generico. In altre occasioni, non viene visualizzato alcun messaggio di errore e l'operazione sembra essere eseguita correttamente.

In questo caso, chiudendo e riaprendo il file è possibile che il contenuto non venga modificato. Tuttavia, alcune applicazioni possono memorizzare un backup del file in modo che le modifiche possano essere applicate.

Indipendentemente dal comportamento, il file rimane invariato quando viene archiviato. Anche se viene visualizzata una versione diversa del file, le modifiche non vengono sincronizzate in AEM.

## Risoluzione dei problemi relativi allo spostamento dei file {#troubleshooting-problems-around-moving-files}

L'API server richiede intestazioni aggiuntive, X-Destination, X-Depth e X-Overwrite, da trasmettere per il funzionamento delle operazioni di spostamento e copia. Il dispatcher non trasmette queste intestazioni per impostazione predefinita, causando il fallimento delle operazioni. Per ulteriori informazioni, consultate [Connessione ad AEM dietro un dispatcher](install-configure-app-v1.md#connect-to-an-aem-instance-behind-a-dispatcher).

## Risoluzione dei problemi di connessione AEM Desktop {#troubleshooting-aem-desktop-connection-issues}

### Problema di reindirizzamento SAML {#saml-redirect-issue}

Il motivo più comune dei problemi riscontrati con AEM Desktop che si collega all’istanza AEM abilitata per SSO (SAML) è che il processo SAML non viene reindirizzato al percorso originariamente richiesto. In alternativa, la connessione può essere reindirizzata a un host non configurato in AEM desktop. Effettuate le seguenti operazioni per verificare il processo di accesso:

1. Aprite un browser Web.
1. Nella barra degli indirizzi, specificate l’URL `/content/dam.json`.
1. Sostituite l’URL con l’istanza AEM di destinazione, ad esempio `http://localhost:4502/content/dam.json`.
1. Accedete ad AEM.
1. Dopo l'accesso, controllate l'indirizzo corrente del browser nella barra degli indirizzi. Deve corrispondere all’URL immesso inizialmente.
1. Verificate che tutti gli elementi prima `/content/dam.json` corrispondano al valore AEM di destinazione configurato in AEM Desktop.

### Problema di configurazione SSL {#ssl-configuration-issue}

Le librerie utilizzate dall’app desktop AEM per la comunicazione HTTP utilizzano l’applicazione SSL restrittiva. Talvolta, una connessione può avere esito positivo utilizzando un browser ma non può essere utilizzata correttamente dall'app desktop AEM. Per configurare SSL in modo appropriato, installate il certificato intermedio mancante in Apache. Vedere [Come installare un certificato CA intermedio in Apache](https://access.redhat.com/solutions/43575).

## Utilizzo di AEM Desktop con dispatcher {#using-aem-desktop-with-dispatcher}

AEM Desktop funziona con le distribuzioni AEM dietro un dispatcher, che è una configurazione predefinita e consigliata per i server AEM. I dispatcher AEM davanti agli ambienti di authoring di AEM sono generalmente configurati per ignorare la memorizzazione nella cache delle risorse DAM. Pertanto, i dispatcher non forniscono memorizzazione nella cache aggiuntiva dal punto di vista di AEM Desktop. Verificate che la configurazione del dispatcher sia regolata in modo da funzionare per AEM Desktop. Per ulteriori dettagli, consultate [Connessione ad AEM dietro un dispatcher](install-configure-app-v1.md#connect-to-an-aem-instance-behind-a-dispatcher).

## Verifica dei file di registro {#checking-for-log-files}

A seconda del sistema operativo in uso, potete trovare i file di registro per AEM Desktop nelle seguenti posizioni:

* Windows: `%LocalAppData%\Adobe\AssetsCompanion\Logs`
* Mac: `~/Library/Logs/Adobe\ Experience\ Manager\ Desktop`