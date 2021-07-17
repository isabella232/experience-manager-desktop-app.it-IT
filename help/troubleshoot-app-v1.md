---
title: Risolvere i problemi relativi all’app desktop versione 1.10.
description: Risolvere i problemi relativi all'installazione, all'aggiornamento e alla configurazione dell'app desktop  [!DNL Adobe Experience Manager] versione 1.10.
exl-id: 1e1409c2-bf5e-4e2d-a5aa-3dd74166862c
source-git-commit: 32aff5d66f2cb67ab4bb440d7ace747a5cf1dd26
workflow-type: tm+mt
source-wordcount: '3350'
ht-degree: 1%

---

# Risolvere i problemi relativi all’ app desktop [!DNL Adobe Experience Manager] v1.x {#troubleshoot-aem-desktop-app}

Risolvere i problemi relativi all’installazione, all’aggiornamento, alla configurazione AEM’app desktop e così via.

[!DNL Adobe Experience Manager] l’app desktop include utilità che consentono di mappare l’archivio AEM Assets come condivisione di rete sul desktop (condivisione SMB su Mac OS). La condivisione di rete è una tecnologia del sistema operativo che consente alle sorgenti remote di essere considerate come parte del file system locale di un computer. Nel caso dell’app desktop, la struttura dell’archivio DAM (Digital Asset Management) di un’istanza remota di AEM è destinata come origine file remota. Il diagramma seguente descrive la topologia dell’app desktop:

![diagramma dell’app desktop](assets/aem-desktopapp-architecture.png)

Con questa architettura, l’app desktop intercetta le chiamate dei file system (aperte, chiuse, lette, scritte e così via) alla condivisione di rete montata e le traduce in chiamate HTTP native AEM al server AEM. I file vengono memorizzati nella cache locale. Per ulteriori dettagli, consulta [Utilizzare AEM’app desktop v1.x](use-app-v1.md).

## Panoramica dei componenti dell’app desktop AEM {#desktop-app-component-overview}

l’app desktop include i seguenti componenti:

* **L&#39;applicazione** desktop: L&#39;applicazione monta o smonta DAM come file system remoto e traduce le chiamate al file system tra la condivisione di rete montata localmente e l&#39;istanza AEM remota a cui si connette.
* **Client** WebDAV/SMB del sistema operativo: Gestisce la comunicazione tra Esplora risorse/Finder e l&#39;app desktop. Se un file viene recuperato, creato, modificato, eliminato, spostato o copiato, il client WebDAV/SMB del sistema operativo comunica questa operazione all’app desktop. Dopo aver ricevuto la comunicazione, l’app desktop la traduce in chiamate API native AEM remote. Ad esempio, se un utente crea un file nella directory montata, il client WebDAV/SMB avvia una richiesta, che l’app desktop traduce in una richiesta HTTP che crea il file in DAM. Il client WebDAV/SMB è un componente integrato del sistema operativo. Non è in alcun modo collegato all’app desktop, AEM o Adobe.
* **Istanza** Adobe Experience Manager: Consente di accedere alle risorse memorizzate nell’archivio AEM Assets DAM. Inoltre, esegue le azioni richieste dall&#39;app desktop per conto delle applicazioni desktop locali che interagiscono con la condivisione di rete montata. L’istanza AEM di destinazione deve essere eseguita AEM versione 6.1 o successiva. AEM istanze che eseguono versioni precedenti di AEM potrebbero richiedere pacchetti di funzioni e hotfix aggiuntivi installati per diventare completamente funzionanti.

## Casi d’uso previsti per AEM’app desktop {#intended-use-cases-for-aem-desktop-app}

AEM&#39;app desktop utilizza la tecnologia di condivisione di rete per mappare un archivio AEM remoto su un desktop locale. Tuttavia, non è inteso come sostituzione di una condivisione di rete contenente risorse, in cui gli utenti eseguono operazioni di gestione delle risorse digitali direttamente dal desktop locale. Ad esempio, lo spostamento o la copia di più file o il trascinamento di grandi strutture di cartelle nella condivisione di rete AEM Assets direttamente in Finder/Explorer.

AEM’app desktop offre un modo semplice di accedere (aprire) e modificare (salvare) le risorse DAM tra l’interfaccia utente AEM Assets Touch e il desktop locale. Collega le risorse del server AEM Assets ai flussi di lavoro basati su desktop.

Il seguente esempio di caso d’uso illustra come utilizzare AEM Desktop:

* Un utente accede a AEM e utilizza l’interfaccia utente web per individuare una risorsa.
* Utilizzando le funzionalità di azione desktop dell’interfaccia utente web AEM, l’utente può aprire, visualizzare o modificare la risorsa sul desktop in base alle esigenze.
* AEM Desktop apre la risorsa nell’editor predefinito per il tipo di file della risorsa.
* L’utente apporta le modifiche desiderate alla risorsa.
* Dopo la modifica di un file, l&#39;utente può visualizzare lo stato di sincronizzazione del file utilizzando la finestra di stato di sincronizzazione in background di AEM Desktop.
* Utilizzando il menu di scelta rapida di AEM Desktop, l’utente archivia/ritorna all’interfaccia utente di DAM.
* Dopo aver completato le modifiche al file, l&#39;utente ritorna all&#39;interfaccia utente Web AEM

Questo non è l’unico caso d’uso. Tuttavia, illustra come AEM Desktop è un meccanismo conveniente per accedere/modificare le risorse localmente. Ti consigliamo di utilizzare il più possibile l’interfaccia utente web DAM perché offre un’esperienza migliore. Offre ad Adobe maggiore flessibilità per soddisfare le esigenze dei clienti.

## Limitazioni  {#limitations}

La condivisione di rete WebDAV/SMB1 consente di lavorare con i file in una finestra Explorer/Finder. Tuttavia, Explorer/Finder e AEM comunicare tramite una connessione di rete con determinate limitazioni. Ad esempio, il tempo impiegato per copiare un file da 1 GB nella directory WebDAV/SMB montata è approssimativamente lo stesso del tempo necessario per caricare un file da 1 GB su un sito web utilizzando un browser web. Infatti, nel primo caso, la durata può essere più lunga a causa di inefficienze del protocollo WebDAV/SMB e dei client WebDAV/SMB del sistema operativo (in particolare Mac OS X).

Esistono limitazioni ai tipi di attività che possono essere eseguite da una directory montata. In generale, lavorare con file di grandi dimensioni specialmente su una connessione di rete a bassa latenza/bassa latenza potrebbe essere difficile, soprattutto quando si modificano file di grandi dimensioni.

Adobe consiglia di eseguire alcuni test di utilizzo-case prima di impegnarsi con un cliente che determinati tipi di file possono essere modificati in modo efficiente sul posto dalla directory montata.

AEM Desktop non è adatto per l&#39;esecuzione di operazioni di manipolazione intensiva dei file system, compresi, tra l&#39;altro:

* Spostamento o copia di file e directory
* Aggiunta di più risorse a AEM
* Ricerca e apertura di file tramite il file system, ad eccezione delle cartelle di navigazione
* Compressione o decompressione degli archivi di file

A causa di limitazioni nel sistema operativo, Windows ha una limitazione della dimensione del file di 4.294.967.295 byte (circa 4,29 GB). È dovuto a un&#39;impostazione del Registro di sistema che definisce le dimensioni di un file su una condivisione di rete. Il valore dell&#39;impostazione del Registro di sistema è un DWORD con una dimensione massima uguale al numero di riferimento.

[!DNL Experience Manager] l’app desktop non dispone di un valore di timeout configurabile che disconnette la connessione tra app  [!DNL Experience Manager] server e desktop dopo un intervallo di tempo fisso. Quando carichi risorse di grandi dimensioni, se la connessione si interrompe dopo un po&#39; di tempo, l’app tenta nuovamente di caricare la risorsa qualche volta aumentando il timeout di caricamento. Non è consigliabile modificare le impostazioni di timeout predefinite.

## Memorizzazione in cache e comunicazione con AEM {#caching-and-communication-with-aem}

AEM’app desktop offre funzioni di memorizzazione in cache interna e caricamento in background per migliorare l’esperienza dell’utente finale. Quando salvi un file di grandi dimensioni, questo viene prima salvato localmente per consentirti di continuare a lavorare. Dopo un certo tempo (attualmente 30 secondi), il file viene quindi inviato al server AEM in background.

A differenza di Creative Cloud Desktop o altre soluzioni di sincronizzazione file, come Microsoft One Drive, AEM&#39;app desktop non è un client di sincronizzazione desktop completo. Il motivo è che fornisce accesso all’intero archivio AEM Assets, che può essere estremamente grande (centinaia di gigabyte o terabyte) per una sincronizzazione completa.

La memorizzazione in cache consente di limitare il sovraccarico di rete/storage a un solo sottoinsieme di risorse rilevanti per l’utente.

>[!CAUTION]
>
>Adobe consiglia di disattivare la generazione delle miniature per velocizzare la navigazione. Se abiliti le anteprime delle icone, l’app memorizza in cache le risorse digitali quando navighi nella cartella montata. L&#39;app scarica anche risorse di cui l&#39;utente potrebbe non preoccuparsi, che aggiungono il carico al server, consuma la larghezza di banda dell&#39;utente e utilizza più spazio su disco dell&#39;utente.

Ecco come AEM’app desktop esegue la memorizzazione in cache:

* Quando apri una cartella nel Finder e vengono visualizzate miniature/anteprime dei file o quando apri un file in un’applicazione, l’app desktop memorizza in cache il file binario.
* Quando si memorizzano i file tramite Finder o altre applicazioni desktop, il file viene memorizzato localmente per primo (memorizzato nella cache) e il sistema operativo riceve una notifica. Il file viene quindi messo in coda per il caricamento sul server in background e infine caricato in rete. In caso di errore di rete, l’app desktop prova a caricare nuovamente l’intero file per un massimo di tre volte. Se il caricamento non riesce dopo tre tentativi, il file viene contrassegnato come file in conflitto e lo stato viene visualizzato tramite la finestra Stato coda caricamento in background. l’app desktop non tenta più di aggiornare il file. L’utente deve aggiornare il file e ricaricarlo dopo il ripristino della connettività

Ogni operazione non viene memorizzata nella cache locale. I seguenti dati vengono trasmessi immediatamente al server AEM senza memorizzazione in cache locale:

* Qualsiasi operazione sulle cartelle, ad esempio creazione, eliminazione e così via
* La funzione di caricamento delle cartelle introdotta nella versione 1.4 carica una gerarchia di cartelle locale senza memorizzare i file nella cache locale

## Operazioni individuali {#individual-operations}

Durante la risoluzione dei problemi di prestazioni ottimizzate in modo secondario per i singoli utenti, controlla prima [le limitazioni dell&#39;app](#limitations). Le sezioni successive includono suggerimenti per migliorare le prestazioni per i singoli utenti.

## Raccomandazioni in merito alla larghezza di banda {#bandwidth-recommendations}

La larghezza di banda disponibile per un singolo utente svolge un ruolo fondamentale nelle prestazioni del client WebDAV/SMB.

Adobe consiglia di avvicinare la velocità di caricamento di un singolo utente a 10 Mbps. Per le connessioni wireless, la larghezza di banda viene spesso condivisa tra più utenti. Se più utenti eseguono contemporaneamente attività che utilizzano la larghezza di banda della rete, le prestazioni possono peggiorare ulteriormente. Per evitare tali problemi, utilizzare una connessione cablata.

## Configurazioni specifiche di Windows {#windows-specific-configurations}

Se si utilizza Experience Manager in Windows, è possibile configurare Windows per migliorare le prestazioni del client WebDAV. Per ulteriori informazioni, visita [https://support.microsoft.com/en-us/kb/2445570](https://support.microsoft.com/it-it/kb/2445570).

In Windows 7, la modifica delle impostazioni di IE può migliorare le prestazioni di WebDAV. Per ulteriori informazioni, vedere come [correggere le prestazioni di WebDAV lente in Windows 7](https://oddballupdate.com/2009/12/fix-slow-webdav-performance-in-windows-7/).

<!-- TBD: The above performance tip is for Windows 7 which is not supported by the app anymore. Remove it later.
-->

## Operazioni simultanee {#concurrent-operations}

Quando interagisci con un file localmente, AEM Desktop verifica se una versione più recente del file è disponibile in AEM. Se è disponibile una nuova versione, l’applicazione scarica una nuova copia del file nella cache locale. Tuttavia, AEM Desktop non sovrascrive un file memorizzato nella cache locale se è stato modificato. Questa funzione impedisce che il lavoro venga sovrascritto inavvertitamente.

Quando lo stesso file viene modificato sia localmente che in AEM, la versione modificata localmente sovrascrive la versione in AEM. In questo caso, la versione precedente è disponibile nella timeline della risorsa. È possibile verificare entrambe le versioni e risolvere eventuali conflitti.

Se un file locale non è coerente con la versione disponibile nel server, la finestra di dialogo dello stato di caricamento in background ti segnala il conflitto. Per risolvere il problema, apri il file in conflitto e salvalo. Il salvataggio del file forza AEM Desktop a sincronizzare le ultime modifiche locali a AEM. Puoi visualizzare le versioni precedenti della risorsa nella timeline e risolvere eventuali conflitti.

È necessario tenere conto di fattori aggiuntivi quando più utenti tentano di lavorare in directory montate separate che puntano alla stessa istanza AEM. In particolare, sono importanti i seguenti fattori:

* Quantità di larghezza di banda disponibile sulla rete di origine degli utenti
* Configurazione di rete, ad esempio firewall o proxy, della rete di origine
* Quantità di larghezza di banda disponibile nella rete dell&#39;istanza AEM target
* Se un dispatcher è presente prima dell’istanza AEM target
* Carico corrente sull&#39;istanza AEM di destinazione

## Configurazioni AEM aggiuntive {#additional-aem-configurations}

Se le prestazioni di WebDAV/SMB diminuiscono drasticamente quando più utenti lavorano contemporaneamente, è possibile configurare alcuni elementi in AEM, il che può contribuire a migliorare le prestazioni.

## Aggiornare i flussi di lavoro transitori delle risorse {#update-asset-transient-workflows}

Puoi migliorare le prestazioni sul lato AEM abilitando flussi di lavoro transitori per il flusso di lavoro Aggiorna risorsa DAM . L’abilitazione dei flussi di lavoro transitori riduce la potenza di elaborazione necessaria per aggiornare le risorse quando vengono create o modificate in AEM.

1. Passa a `/miscadmin` nell&#39;istanza di Experience Manager (`https://[aem_server]:[port]/miscadmin`).
1. Dalla struttura di navigazione, espandi **Strumenti** > **Flusso di lavoro** > **Modelli** > **dam**.
1. Fai doppio clic su **Aggiorna risorsa DAM**.
1. Dal pannello degli strumenti mobili, passa alla scheda **Pagina** , quindi fai clic su **Proprietà pagina**.
1. Selezionare la casella di controllo **Flusso di lavoro transitorio** e fare clic su **OK**.

### Regolare la coda del flusso di lavoro transitorio di Granite {#adjust-granite-transient-workflow-queue}

Un altro metodo per migliorare le prestazioni AEM consiste nel configurare il valore dei lavori paralleli massimi per il processo Coda flusso di lavoro transitorio di Granite. Il valore consigliato è circa la metà del numero di CPU disponibile con il server. Per regolare il valore, eseguire le seguenti operazioni:

1. Passa a `/system/console/configMgr` nell’istanza AEM da configurare (ad esempio, `https://[aem_server]:[port]/system/console/configMgr`).
1. Cerca `QueueConfiguration` e fai clic per aprire ogni processo fino a individuare il processo **Coda flusso di lavoro transitorio di Granite**, quindi fai clic su **Modifica**.
1. Modifica il valore `Maximum Parallel Jobs` e fai clic su **Salva**.

## Configurazione AWS {#aws-configuration}

A causa delle limitazioni della larghezza di banda della rete, le prestazioni di WebDAV/SMB possono degradarsi quando più utenti lavorano contemporaneamente. L&#39;Adobe consiglia di aumentare le dimensioni dell&#39;istanza AWS per un&#39;istanza AEM di destinazione che viene eseguita su AWS per migliorare le prestazioni di WebDAV/SMB.

Questa misura aumenta in modo specifico la quantità di banda di rete disponibile per il server. Ecco alcuni dettagli:

* La quantità di larghezza di banda di rete dedicata a un&#39;istanza AWS aumenta man mano che le dimensioni dell&#39;istanza aumentano. Per informazioni sulla larghezza di banda disponibile per ogni dimensione di istanza, consulta la [documentazione AWS](https://aws.amazon.com/ec2/instance-types/).
* Durante la risoluzione dei problemi relativi a un client di grandi dimensioni, l&#39;Adobe ha configurato le dimensioni della sua istanza AEM a c4.8xlarge, principalmente per i 4000 Mbps di larghezza di banda dedicata che fornisce.
* Se c&#39;è un dispatcher prima dell&#39;istanza AEM, assicurati che sia di dimensioni appropriate. Se l’istanza AEM fornisce 4000 Mbps ma il dispatcher fornisce solo 500 Mbps, la larghezza di banda effettiva è solo 500 Mbps. È perché il dispatcher crea un collo di bottiglia della rete.

## Limitazioni del file estratto {#checked-out-file-limitations}

Ci sono alcune limitazioni note nel modo in cui puoi interagire con i file estratti tramite Explorer/Finder. Se un file viene estratto, deve essere di sola lettura a chiunque, ad eccezione dell&#39;utente che ha estratto il file. L&#39;implementazione del protocollo WebDAV/SMB1 in AEM applica questa regola. Tuttavia, i client OS WebDAV/SMB spesso non interagiscono con eleganza con i file estratti. Alcune stranezze sono descritte di seguito.

### Generale {#general}

Quando si scrive in un file estratto, il blocco viene applicato solo all&#39;interno AEM&#39;implementazione WebDAV. Di conseguenza, il blocco viene applicato solo dai client che utilizzano WebDAV, ad esempio l’app desktop. Il blocco non viene applicato tramite AEM&#39;interfaccia Web. L’interfaccia AEM mostra semplicemente un’icona a forma di lucchetto nella vista a schede per le risorse che vengono estratte. L’icona è cosmetica e non ha alcun effetto sul comportamento di AEM.

In generale, i client WebDAV non si comportano sempre come previsto. Potrebbero esserci altri problemi. Tuttavia, l’aggiornamento o il controllo della risorsa in AEM è un modo corretto per verificare che una risorsa non venga modificata. Questo comportamento è tipico dei client OS WebDAV, che non è sotto il controllo del Adobe.

### Windows {#windows}

L&#39;eliminazione di un file sembra avere esito positivo perché il file scompare dall&#39;elenco delle cartelle dei file in Windows. Tuttavia, l’aggiornamento della directory e l’archiviazione AEM risorse mostrano che il file è ancora presente. Inoltre, sembra che la modifica dei file abbia esito positivo (non vengono visualizzate finestre di dialogo di avviso o messaggi di errore). Tuttavia, se riapri il file o accedi AEM risorse, il file rimane invariato.

#### Mac OS X {#mac-os-x}

La sostituzione di un file non visualizza un avviso o un errore, ma la verifica della risorsa in AEM rivela che rimane invariata. Aggiorna o controlla la risorsa in AEM per verificare che non venga modificata.

## Risoluzione dei problemi relativi alle icone delle app desktop (Mac OS X) {#troubleshooting-desktop-app-icon-issues-mac-os-x}

Dopo l’installazione dell’app desktop, l’icona del menu dell’app desktop viene visualizzata nella barra dei menu. Se l&#39;icona non viene visualizzata, esegui questi passaggi per risolvere il problema:

1. Aprire la finestra del terminale del sistema operativo.
1. Digitare il comando seguente al prompt dei comandi, quindi premere Invio:

   ```shell
    cd ../Library/Caches.
   ```

1. Digitare il comando seguente e premere Invio:

   ```shell
   rm -r com.adobe.aem.assetscompanion
   ```

1. Digitare il comando seguente e premere Invio:

   ```shell
   cd ~/Library/Preferences
   ```

1. Digitare il comando seguente e premere Invio:

   ```shell
   rm com.adobe.aem.assetscompanion.plist
   ```

1. Digitare il comando seguente e premere Invio:

   ```shell
   rm ~/Library/Group\ Containers/group.com.adobe.aem.desktop/*
   ```

1. Riavvia il sistema.

AEM Desktop tenta di sincronizzare un determinato file tre volte. Se la sincronizzazione del file non riesce dopo il terzo tentativo, AEM Desktop considera il file in conflitto e invia una notifica tramite la finestra di stato del caricamento in background. Uno stato di conflitto indica che le ultime modifiche sono ancora disponibili localmente, ma non vengono sincronizzate di nuovo in AEM. AEM&#39;app desktop non tenta più di eseguire la sincronizzazione.

Il modo più semplice per risolvere questa situazione è aprire il file in conflitto e salvarlo di nuovo. Forza AEM Desktop a tentare la sincronizzazione per altre tre occasioni. Se la sincronizzazione del file non riesce, consulta le sezioni seguenti per ulteriori informazioni.

## Cancellazione AEM cache desktop {#clearing-aem-desktop-cache}

La cancellazione della cache di AEM Desktop è un’attività preliminare di risoluzione dei problemi che può risolvere diversi problemi AEM Desktop.

È possibile cancellare la cache eliminando la directory della cache dell&#39;applicazione nelle seguenti posizioni.
In Windows, `%LocalAppData%\Adobe\AssetsCompanion\Cache\`

In Mac, `~/Library/Group/Containers/group.com.adobe.aem.desktop/cache/`

Tuttavia, la posizione può cambiare a seconda dell&#39;endpoint AEM configurato AEM Desktop. Il valore è una versione codificata dell’URL di destinazione. Ad esempio, se l’applicazione esegue il targeting di `http://localhost:4502`, il nome della directory è `http%3A%2F%2Flocalhost%3A4502%2F`.

Per cancellare la cache, elimina la directory &lt;Encoded AEM Endpoint> .

>[!NOTE]
>
>Se si cancella AEM cache desktop, le modifiche locali dei file che non sono sincronizzate con AEM andranno perse.

>[!NOTE]
>
>A partire dalla versione 1.5 dell’app desktop AEM, è disponibile un’opzione nell’interfaccia utente dell’app desktop per cancellare la cache.

## Ricerca della versione desktop AEM {#finding-the-aem-desktop-version}

La procedura per verificare la versione AEM Desktop è la stessa per Windows e Mac OS.

Fai clic sull&#39;icona AEM Desktop e scegli **Informazioni**. Il numero di versione viene visualizzato sullo schermo.

## Aggiornamento dell’app desktop AEM in macOS {#upgrading-aem-desktop-app-on-macos}

Talvolta possono verificarsi problemi durante l’aggiornamento AEM’app desktop su macOS. Ciò è causato dalla cartella di sistema legacy per AEM&#39;app desktop che impedisce il caricamento corretto delle nuove versioni di AEM Desktop. Per risolvere questo problema, è possibile rimuovere manualmente le cartelle e i file seguenti.

Prima di eseguire i passaggi seguenti, trascina l’applicazione &quot;Adobe Experience Manager Desktop&quot; dalla cartella macOS Applications nel Cestino. Quindi aprire il terminale ed eseguire il seguente comando, fornendo la password quando richiesto.

```shell
sudo rm -rf ~/Library/Application\ Support/com.adobe.aem.desktop
sudo rm -rf ~/Library/Preferences/com.adobe.aem.desktop.plist
sudo rm -rf ~/Library/Logs/Adobe\ Experience\ Manager\ Desktop

sudo find /var/folders -type d -name "com.adobe.aem.desktop" | xargs rm -rf
sudo find /var/folders -type d -name "com.adobe.aem.desktop.finderintegration-plugin" | xargs rm -rf
```

## Salvataggio di un file estratto da altri utenti {#saving-a-file-checked-out-by-others}

Le limitazioni tecniche del sistema operativo impediscono agli utenti di avere un&#39;esperienza coerente quando tentano di sovrascrivere un file estratto da altri utenti. L’esperienza varia a seconda dell’applicazione utilizzata per modificare il file estratto. A volte, l&#39;applicazione visualizza un messaggio di errore che indica un errore di scrittura del disco o visualizza un errore apparentemente non correlato o generico. In altre occasioni, non viene visualizzato alcun messaggio di errore e l’operazione sembra avere esito positivo.

In questo caso, chiudendo e riaprendo il file si può vedere che il contenuto è invariato. Tuttavia, alcune applicazioni possono memorizzare un backup del file in modo che le modifiche possano essere applicate.

Indipendentemente dal comportamento, il file rimane invariato al momento del check-in. Anche se viene visualizzata una versione diversa del file, le modifiche non vengono sincronizzate in AEM.

## Risoluzione dei problemi relativi allo spostamento dei file {#troubleshooting-problems-around-moving-files}

L&#39;API del server richiede intestazioni aggiuntive, X-Destination, X-Depth e X-Overwrite, da trasmettere affinché le operazioni di spostamento e copia funzionino. Il dispatcher non passa queste intestazioni per impostazione predefinita, il che causa il mancato funzionamento di queste operazioni. Per ulteriori informazioni, consulta [Connessione a AEM dietro un Dispatcher](install-configure-app-v1.md#connect-to-an-aem-instance-behind-a-dispatcher).

## Risoluzione dei problemi di connessione AEM desktop {#troubleshooting-aem-desktop-connection-issues}

### Problema di reindirizzamento SAML {#saml-redirect-issue}

Il motivo più comune per problemi con AEM Desktop che si connette all&#39;istanza di AEM abilitato SSO (SAML) è che il processo SAML non reindirizza al percorso originariamente richiesto. In alternativa, la connessione può essere reindirizzata a un host non configurato AEM desktop. Esegui questi passaggi per verificare il processo di accesso:

1. Apri un browser web.
1. Nella barra degli indirizzi, specifica l’URL `/content/dam.json`.
1. Sostituisci l’URL con l’istanza AEM di destinazione, ad esempio `https://localhost:4502/content/dam.json`.
1. Accedi a AEM.
1. Dopo l&#39;accesso, controlla l&#39;indirizzo corrente del browser nella barra degli indirizzi. Deve corrispondere all’URL immesso inizialmente.
1. Verifica che tutti gli elementi precedenti a `/content/dam.json` corrispondano al valore AEM di destinazione configurato in AEM Desktop.

### Problema di configurazione SSL {#ssl-configuration-issue}

Le librerie che AEM&#39;app desktop utilizza per la comunicazione HTTP utilizzano una rigorosa applicazione SSL. A volte, una connessione può avere esito positivo utilizzando un browser ma non riesce a utilizzare AEM’app desktop. Per configurare SSL in modo appropriato, installa il certificato intermedio mancante in Apache. Vedere [Come installare un certificato CA intermedio in Apache](https://access.redhat.com/solutions/43575).

## Utilizzo di AEM Desktop con dispatcher {#using-aem-desktop-with-dispatcher}

AEM Desktop funziona con distribuzioni AEM dietro un dispatcher, una configurazione predefinita e consigliata per AEM server. AEM dispatcher davanti AEM ambienti di authoring sono generalmente configurati per saltare la memorizzazione in cache delle risorse DAM. Pertanto, i dispatcher non forniscono memorizzazione in cache aggiuntiva dal punto di vista AEM Desktop. Assicurati che la configurazione del dispatcher sia regolata in modo che funzioni per AEM Desktop. Per ulteriori dettagli, consulta [Collegamento a AEM dietro un dispatcher](install-configure-app-v1.md#connect-to-an-aem-instance-behind-a-dispatcher).

## Verifica dei file di registro {#checking-for-log-files}

A seconda del sistema operativo, è possibile trovare i file di registro per AEM Desktop nelle seguenti posizioni:

* Windows: `%LocalAppData%\Adobe\AssetsCompanion\Logs`
* Mac: `~/Library/Logs/Adobe\ Experience\ Manager\ Desktop`
