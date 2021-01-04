---
title: 'Risoluzione dei problemi relativi all''app desktop versione 1.x [!DNL Adobe Experience Manager] '
description: Risolvete i problemi relativi all'installazione, all'aggiornamento e alla configurazione dell'app desktop  [!DNL Adobe Experience Manager] versione 1.x.
translation-type: tm+mt
source-git-commit: a25c1fa13895ae9eb7268e3e01c83a5f0b9d7d1d
workflow-type: tm+mt
source-wordcount: '3366'
ht-degree: 1%

---


# Risoluzione dei problemi relativi all&#39;app desktop [!DNL Adobe Experience Manager] v1.x {#troubleshoot-aem-desktop-app}

Risolvi AEM problemi relativi a installazione, aggiornamento, configurazione e così via.

[!DNL Adobe Experience Manager] l&#39;app desktop include utility che consentono di mappare l&#39;archivio AEM Assets  come condivisione di rete sul desktop (condivisione SMB su Mac OS). La condivisione di rete è una tecnologia del sistema operativo che consente alle origini remote di essere trattate come se fossero parte del file system locale di un computer. Nel caso dell&#39;app desktop, la struttura dell&#39;archivio DAM (Digital Asset Management) di un&#39;istanza AEM remota viene indirizzata come origine file remota. Il diagramma seguente descrive la topologia dell&#39;app desktop:

![diagramma app desktop](assets/aem-desktopapp-architecture.png)

Con questa architettura, l&#39;app desktop intercetta le chiamate del file system (aperte, vicine, lette, scritte e così via) per la condivisione di rete montata e le converte in chiamate HTTP native AEM al server AEM. I file vengono memorizzati nella cache locale. Per ulteriori dettagli, vedere [Utilizzo AEM app desktop v1.x](use-app-v1.md).

## Panoramica AEM componente per app desktop {#desktop-app-component-overview}

l&#39;app desktop include i seguenti componenti:

* **Applicazione** desktop: L&#39;applicazione installa o smonta DAM come file system remoto e traduce le chiamate del file system tra la condivisione di rete montata localmente e l&#39;istanza AEM remota a cui si connette.
* **Client** WebDAV/SMB del sistema operativo: Gestisce la comunicazione tra Windows Explorer/Finder e l&#39;app desktop. Se un file viene recuperato, creato, modificato, eliminato, spostato o copiato, il client WebDAV/SMB del sistema operativo (OS) comunica questa operazione all&#39;app desktop. Dopo aver ricevuto la comunicazione, l&#39;app desktop la trasforma in chiamate API native AEM remote. Ad esempio, se un utente crea un file nella directory montata, il client WebDAV/SMB avvia una richiesta che l&#39;app desktop converte in una richiesta HTTP che crea il file in DAM. Il client WebDAV/SMB è un componente integrato del sistema operativo. Non è in alcun modo collegato all&#39;app desktop, AEM o  Adobe.
* **Istanza** Adobe Experience Manager: Consente l&#39;accesso alle risorse memorizzate nell&#39;archivio  di AEM Assets DAM. Inoltre, esegue le azioni richieste dall&#39;app desktop per conto delle applicazioni desktop locali che interagiscono con la condivisione di rete montata. L&#39;istanza AEM di destinazione deve essere eseguita AEM versione 6.1 o successiva. AEM istanze che eseguono versioni precedenti AEM potrebbero richiedere pacchetti di funzioni aggiuntivi e hotfix installati per diventare completamente funzionanti.

## Casi di utilizzo previsti per AEM app desktop {#intended-use-cases-for-aem-desktop-app}

AEM&#39;app desktop utilizza la tecnologia di condivisione di rete per mappare un repository AEM remoto su un desktop locale. Tuttavia, non è inteso come sostituzione di una condivisione di rete con risorse, in cui gli utenti eseguono operazioni di gestione delle risorse digitali direttamente dal desktop locale. Questi includono lo spostamento o la copia di più file, o il trascinamento di grandi strutture di cartelle nella condivisione di rete AEM Assets  direttamente in Finder/Explorer.

AEM&#39;app desktop offre un modo pratico per accedere (aprire) e modificare (salvare) le risorse DAM tra l&#39; interfaccia utente AEM Assets Touch e il desktop locale. Collega le risorse del server AEM Assets  ai flussi di lavoro basati su desktop.

L’esempio seguente illustra come AEM Desktop deve essere utilizzato:

* Un utente accede a AEM e utilizza l’interfaccia utente Web per individuare una risorsa.
* Utilizzando le funzionalità di azione desktop dell’interfaccia AEM Web, l’utente può aprire, visualizzare o modificare la risorsa sul desktop, a seconda delle necessità.
* AEM Desktop apre la risorsa nell’editor predefinito per il tipo di file della risorsa.
* L’utente apporta le modifiche desiderate alla risorsa.
* Dopo che un file è stato modificato, l&#39;utente può visualizzare lo stato di sincronizzazione del file utilizzando AEM finestra di stato della sincronizzazione in background di Desktop.
* Utilizzando il menu di scelta rapida di AEM Desktop, l&#39;utente può archiviare/estrarre la risorsa o tornare all&#39;interfaccia utente di DAM.
* Dopo aver completato le modifiche al file, l&#39;utente ritorna all&#39;interfaccia AEM Web

Questo non è l&#39;unico caso d&#39;uso. Tuttavia, AEM Desktop è un meccanismo pratico per accedere e modificare localmente le risorse. È consigliabile utilizzare l&#39;interfaccia utente Web di DAM il più possibile, in quanto offre un&#39;esperienza migliore. Offre  Adobe maggiore flessibilità per soddisfare le esigenze dei clienti.

## Limitazioni  {#limitations}

La condivisione di rete WebDAV/SMB1 consente di utilizzare i file in una finestra Esplora risorse/Finder. Esplora risorse/Finder e AEM comunicare attraverso una connessione di rete con determinate limitazioni. Ad esempio, il tempo necessario per copiare un file da 1 GB nella directory WebDAV/SMB installata è circa lo stesso del tempo richiesto per caricare un file da 1 GB in un sito Web utilizzando un browser Web. Infatti, nel primo caso, la durata potrebbe essere maggiore a causa di inefficienze del protocollo WebDAV/SMB e dei client WebDAV/SMB del sistema operativo (in particolare Mac OS X).

Esistono limitazioni ai tipi di attività che possono essere eseguite da una directory montata. In generale, l&#39;utilizzo di file di grandi dimensioni, in particolare su una connessione di rete con latenza bassa/bassa, potrebbe risultare difficoltoso, soprattutto quando si modificano file di grandi dimensioni.

 Adobe consiglia di eseguire alcuni test di esempio prima di impegnarsi con un client per verificare che alcuni tipi di file possano essere modificati in modo efficiente nella posizione locale dalla directory montata.

AEM Desktop non è adatto per l&#39;esecuzione di operazioni di manipolazione intensiva del file system, compresi, tra l&#39;altro, i seguenti elementi:

* Spostamento o copia di file e directory
* Aggiunta di più risorse a AEM
* Ricerca e apertura di file attraverso il file system, fatta eccezione per la navigazione delle cartelle
* Compressione o decompressione degli archivi di file

A causa delle limitazioni del sistema operativo, Windows ha un limite di dimensione file di 4.294.967.295 byte (circa 4,29 GB). È dovuto a un&#39;impostazione del Registro di sistema che definisce le dimensioni di un file in una condivisione di rete. Il valore dell&#39;impostazione del Registro di sistema è un DWORD con una dimensione massima uguale al numero di riferimento.

[!DNL Experience Manager] l&#39;app desktop non dispone di un valore di timeout configurabile che disconnette la connessione tra il  [!DNL Experience Manager] server e l&#39;app desktop dopo un intervallo di tempo fisso. Quando caricate risorse di grandi dimensioni, se la connessione riceve il timeout dopo un po&#39;, l&#39;app tenta nuovamente di caricare la risorsa alcune volte aumentando il timeout di caricamento. Non è consigliato modificare le impostazioni di timeout predefinite.

## Memorizzazione nella cache e comunicazione con AEM {#caching-and-communication-with-aem}

AEM&#39;app desktop offre funzionalità di caching interno e caricamento in background per migliorare l&#39;esperienza dell&#39;utente finale. Quando salvate un file di grandi dimensioni, questo viene prima salvato localmente per consentirvi di continuare a lavorare. Dopo un certo tempo (al momento 30 secondi), il file viene inviato al server AEM in background.

A differenza di Creative Cloud Desktop o altre soluzioni di sincronizzazione file, come Microsoft One Drive, AEM app desktop non è un client di sincronizzazione desktop completo. Questo consente l&#39;accesso all&#39;intero repository  AEM Assets, che può essere estremamente grande (centinaia di gigabyte o terabyte) per una sincronizzazione completa.

La memorizzazione nella cache consente di limitare il sovraccarico di rete/storage solo a un sottoinsieme di risorse rilevanti per l’utente.

>[!CAUTION]
>
> Adobe consiglia di disattivare la generazione delle miniature per velocizzare la navigazione. Se abilitate le anteprime delle icone, l&#39;app memorizza nella cache le risorse digitali quando vi spostate nella cartella montata. L&#39;app scarica anche risorse di cui l&#39;utente potrebbe non interessarsi, che aumentano il carico sul server, consumano la larghezza di banda dell&#39;utente e utilizzano più spazio su disco dell&#39;utente.

Ecco come AEM&#39;app desktop esegue la memorizzazione nella cache:

* Quando aprite una cartella nel Finder e vengono visualizzate miniature/anteprime dei file, o quando aprite un file in un’applicazione, l’app desktop memorizza nella cache il file binario.
* Quando si memorizzano i file tramite Finder o altre applicazioni desktop, il file viene memorizzato localmente per primo (nella cache) e il sistema operativo riceve una notifica. Il file viene quindi messo in coda per il caricamento sul server in background e caricato in rete. In caso di errore di rete, l&#39;app desktop tenta nuovamente di caricare l&#39;intero file per un massimo di tre volte. Se il caricamento non riesce dopo tre tentativi, il file viene contrassegnato come in conflitto e lo stato viene visualizzato tramite la finestra Stato coda di caricamento in background. l&#39;app desktop non tenta più di aggiornare il file. L&#39;utente deve aggiornare il file e ricaricarlo dopo il ripristino della connettività

Ogni operazione non viene memorizzata nella cache locale. Le seguenti informazioni vengono trasmesse immediatamente al server AEM senza caching locale:

* Qualsiasi operazione sulle cartelle, ad esempio creazione, eliminazione e così via
* La funzione di caricamento delle cartelle introdotta nella versione 1.4 carica una gerarchia di cartelle locale senza memorizzare i file nella cache locale

## Operazioni individuali {#individual-operations}

Quando si risolvono problemi di prestazioni ottimizzate per singoli utenti, prima di tutto rivedere [Limitazioni](https://helpx.adobe.com/experience-manager/desktop-app/troubleshooting-desktop-app.html#limitations). Le sezioni successive contengono suggerimenti per migliorare le prestazioni dei singoli utenti.

## Raccomandazioni relative alla larghezza di banda {#bandwidth-recommendations}

La larghezza di banda disponibile per un singolo utente svolge un ruolo fondamentale nelle prestazioni del client WebDAV/SMB.

 Adobe consiglia di avvicinare la velocità di caricamento di un singolo utente a 10 Mbps. Per le connessioni wireless, la larghezza di banda è spesso condivisa tra più utenti. Se più utenti eseguono contemporaneamente attività che richiedono larghezza di banda di rete, le prestazioni possono peggiorare ulteriormente. Per evitare tali problemi, utilizzate una connessione cablata.

## Configurazioni specifiche di Windows {#windows-specific-configurations}

Se si esegue AEM in Windows, è possibile configurare Windows per migliorare le prestazioni del client WebDAV. Per ulteriori informazioni, visitare [https://support.microsoft.com/en-us/kb/2445570](https://support.microsoft.com/en-us/kb/2445570).

In Windows 7, la modifica delle impostazioni IE può migliorare le prestazioni di WebDAV. Per informazioni dettagliate, vedere come [correggere le prestazioni WebDAV lente in Windows 7](https://oddballupdate.com/2009/12/fix-slow-webdav-performance-in-windows-7/).

## Operazioni simultanee {#concurrent-operations}

Quando interagite con un file localmente, AEM Desktop verifica se una versione più recente del file è disponibile in AEM. Se è disponibile una nuova versione, l&#39;applicazione scarica una nuova copia del file nella cache locale. Tuttavia, AEM desktop non sovrascrive un file memorizzato nella cache locale se è stato modificato. Questa funzione impedisce che il lavoro venga sovrascritto accidentalmente.

Quando lo stesso file viene modificato sia localmente che in AEM, la versione modificata localmente sovrascrive la versione in AEM. In questo caso, la versione precedente è disponibile nella timeline della risorsa. È possibile verificare entrambe le versioni e risolvere eventuali conflitti.

Se un file locale non è coerente con la versione disponibile nel server, la finestra di dialogo dello stato di caricamento in background segnala il conflitto. Per risolvere il problema, aprite il file in conflitto e salvatelo. Salvando i file, AEM Desktop sincronizza le ultime modifiche locali su AEM. Potete visualizzare le versioni precedenti della risorsa nella timeline e risolvere eventuali conflitti.

È necessario tenere conto di fattori aggiuntivi quando più utenti tentano di lavorare in directory montate separate per la stessa istanza AEM. In particolare, sono importanti i seguenti fattori:

* Quantità di larghezza di banda disponibile sulla rete di origine degli utenti
* Configurazione della rete, ad esempio firewall o proxy, della rete di origine
* Quantità di larghezza di banda disponibile nella rete dell&#39;istanza di AEM di destinazione
* Indica se un dispatcher è presente prima dell&#39;istanza di AEM di destinazione
* Carico corrente sull&#39;istanza di AEM di destinazione

## Configurazioni AEM aggiuntive {#additional-aem-configurations}

Se le prestazioni WebDAV/SMB subiscono un drastico calo quando più utenti lavorano contemporaneamente, è possibile configurare alcuni elementi in AEM, il che può contribuire a migliorare le prestazioni.

## Aggiorna flussi di lavoro transitori risorse {#update-asset-transient-workflows}

Puoi migliorare le prestazioni sul lato AEM abilitando flussi di lavoro transitori per il flusso di lavoro DAM Update Asset. L’attivazione di flussi di lavoro transitori riduce la potenza di elaborazione necessaria per aggiornare le risorse quando vengono create o modificate in AEM.

1. Passare a `/miscadmin` nell&#39;istanza AEM da configurare (ad esempio, `http://[Server]:[Port]/miscadmin`).
1. Dalla struttura di navigazione, espandi **Strumenti** > **Flusso di lavoro** > **Modelli** > **dam**.
1. Fare doppio clic su **DAM Update Asset**.
1. Dal pannello degli strumenti mobili, passare alla scheda **Pagina**, quindi fare clic su **Proprietà pagina**.
1. Selezionare la casella di controllo **Flusso di lavoro transitorio**, quindi fare clic su **OK**.

### Regolare la coda del flusso di lavoro transitorio di Granite {#adjust-granite-transient-workflow-queue}

Un altro metodo per migliorare AEM prestazioni consiste nel configurare il valore dei processi paralleli massimi per il processo Coda flusso di lavoro transitoria Granite. Il valore consigliato è circa la metà del numero di CPU disponibile con il server. Per regolare il valore, effettuare le seguenti operazioni:

1. Andate a */system/console/configMgr* nell&#39;istanza AEM da configurare (ad esempio, `http://[aem_server]:[port]/system/console/configMgr`).
1. Cercate **QueueConfiguration** e fate clic per aprire ciascun processo fino a individuare il processo **Granite Transient Workflow Queue**. Fate clic su Modifica accanto a esso.
1. Modificate il valore **Processi paralleli massimi**, quindi fate clic su **Salva**.

## Configurazione AWS {#aws-configuration}

A causa delle limitazioni della larghezza di banda di rete, le prestazioni di WebDAV/SMB possono peggiorare se più utenti lavorano contemporaneamente.  Adobe consiglia di aumentare le dimensioni dell&#39;istanza AWS per un&#39;istanza AEM di destinazione in esecuzione su AWS per migliorare le prestazioni di WebDAV/SMB.

Questa misura aumenta in modo specifico la quantità di larghezza di banda disponibile per il server. Di seguito sono riportati alcuni dettagli:

* La quantità di larghezza di banda di rete dedicata a un&#39;istanza AWS aumenta con l&#39;aumentare delle dimensioni dell&#39;istanza. Per informazioni sulla larghezza di banda disponibile per ogni dimensione di istanza, consultate la [documentazione AWS](https://aws.amazon.com/ec2/instance-types/).
* Durante la risoluzione dei problemi per un client di grandi dimensioni,  Adobe ha configurato la dimensione dell&#39;istanza AEM su c4.8xlarge, principalmente per i 4000 Mbps di larghezza di banda dedicata che fornisce.
* Se l&#39;istanza AEM è preceduta da un dispatcher, assicurarsi che sia di dimensioni appropriate. Se l’istanza AEM fornisce 4000 Mbps ma il dispatcher fornisce solo 500 Mbps, la larghezza di banda effettiva è solo 500 Mbps. È perché il dispatcher crea un collo di bottiglia della rete.

## Limiti del file estratto {#checked-out-file-limitations}

Esistono alcuni limiti noti per l&#39;interazione con i file estratti tramite Esplora risorse/Finder. Se un file è estratto, deve essere di sola lettura per chiunque, ad eccezione dell&#39;utente che ha estratto il file. L&#39;implementazione del protocollo WebDAV/SMB1 in AEM applica questa regola. Tuttavia, i client WebDAV/SMB del sistema operativo spesso non interagiscono con i file estratti. Alcune stranezze sono descritte di seguito.

### Generale {#general}

Quando si scrive in un file estratto, il blocco viene applicato solo all&#39;interno AEM&#39;implementazione WebDAV. Di conseguenza, il blocco è imposto solo dai client che utilizzano WebDAV, ad esempio l&#39;app desktop. Il blocco non viene imposto tramite AEM&#39;interfaccia Web. L&#39;interfaccia AEM mostra semplicemente un&#39;icona a forma di lucchetto nella vista a schede per le risorse sottoposte a Check-Out. L&#39;icona è cosmetica e non ha alcun effetto sul comportamento di AEM.

In generale, i client WebDAV non si comportano sempre come previsto. Potrebbero verificarsi altri problemi. Tuttavia, l’aggiornamento o il controllo della risorsa in AEM è un metodo efficace per verificare che la risorsa non venga modificata. Questo comportamento è tipico dei client WebDAV del sistema operativo, che non è sotto  controllo  Adobe.

### Windows {#windows}

L&#39;eliminazione di un file sembra aver esito positivo perché il file scompare dall&#39;elenco dei file in Windows. Tuttavia, l’aggiornamento della directory e il check-in AEM risorse mostrano che il file è ancora presente. Inoltre, la modifica dei file sembra aver esito positivo (non vengono visualizzate finestre di dialogo di avviso o messaggi di errore). Tuttavia, se si riapre il file o si archivia AEM risorse, il file rimane invariato.

#### Mac OS X {#mac-os-x}

La sostituzione di un file non visualizza un avviso o un errore, ma il controllo della risorsa in AEM rivela che rimane invariata. Aggiorna o controlla la risorsa in AEM per verificare che non venga modificata.

## Risoluzione dei problemi relativi alle icone delle app desktop (Mac OS X) {#troubleshooting-desktop-app-icon-issues-mac-os-x}

Dopo l&#39;installazione dell&#39;app desktop, l&#39;icona del menu dell&#39;app desktop viene visualizzata nella barra dei menu. Se l&#39;icona non viene visualizzata, eseguite i seguenti passaggi per risolvere il problema:

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

AEM Desktop tenta di sincronizzare tre volte un determinato file. Se la sincronizzazione del file non riesce dopo il terzo tentativo, AEM Desktop considera il file in conflitto e invia una notifica tramite la finestra di stato del caricamento in background. Uno stato di conflitto indica che le ultime modifiche sono ancora disponibili localmente, ma non vengono sincronizzate di nuovo in AEM. AEM&#39;app desktop non tenta più di eseguire la sincronizzazione.

Il modo più semplice per risolvere questa situazione è aprire il file in conflitto e salvarlo di nuovo. Forza AEM Desktop a tentare la sincronizzazione per altre tre occasioni. Se il file non viene ancora sincronizzato, consulta le sezioni seguenti per ulteriore assistenza.

## Cancellazione AEM cache desktop {#clearing-aem-desktop-cache}

La cancellazione AEM cache del desktop è un&#39;attività preliminare di risoluzione dei problemi che può risolvere diversi problemi AEM Desktop.

Potete cancellare la cache eliminando la directory della cache dell&#39;applicazione nelle seguenti posizioni.
In Windows, `%LocalAppData%\Adobe\AssetsCompanion\Cache\`

In Mac, `~/Library/Group/Containers/group.com.adobe.aem.desktop/cache/`

Tuttavia, la posizione può cambiare a seconda AEM&#39;endpoint AEM configurato da Desktop. Il valore è una versione codificata dell’URL di destinazione. Ad esempio, se l&#39;applicazione ha come destinazione `http://localhost:4502`, il nome della directory è `http%3A%2F%2Flocalhost%3A4502%2F`.

Per cancellare la cache, eliminate la directory &lt;Encoded AEM Endpoint>.

>[!NOTE]
>
>Se cancellate AEM cache del desktop, le modifiche ai file locali che non sono sincronizzate con AEM vengono perse.

>[!NOTE]
>
>A partire dalla versione 1.5 AEM&#39;app desktop, è disponibile un&#39;opzione nell&#39;interfaccia utente dell&#39;app desktop per cancellare la cache.

## Ricerca della versione AEM desktop {#finding-the-aem-desktop-version}

La procedura per verificare la versione AEM Desktop è la stessa per Windows e Mac OS.

Fate clic sull&#39;icona AEM Desktop, quindi scegliete **Informazioni su**. Il numero di versione viene visualizzato sullo schermo.

## Aggiornamento AEM&#39;app desktop su macOS {#upgrading-aem-desktop-app-on-macos}

A volte possono verificarsi problemi durante l&#39;aggiornamento AEM&#39;app desktop su macOS. Ciò è causato dalla cartella di sistema precedente per AEM app desktop che impedisce il corretto caricamento delle nuove versioni di AEM Desktop. Per risolvere questo problema, è possibile rimuovere manualmente le cartelle e i file seguenti.

Prima di eseguire i passaggi descritti di seguito, trascinate l’applicazione &quot;Adobe Experience Manager Desktop&quot; dalla cartella delle applicazioni macOS al cestino. Aprite quindi il terminale ed eseguite il comando seguente, fornendo la password quando richiesto.

```shell
sudo rm -rf ~/Library/Application\ Support/com.adobe.aem.desktop
sudo rm -rf ~/Library/Preferences/com.adobe.aem.desktop.plist
sudo rm -rf ~/Library/Logs/Adobe\ Experience\ Manager\ Desktop

sudo find /var/folders -type d -name "com.adobe.aem.desktop" | xargs rm -rf
sudo find /var/folders -type d -name "com.adobe.aem.desktop.finderintegration-plugin" | xargs rm -rf
```

## Salvataggio di un file estratto da altri {#saving-a-file-checked-out-by-others}

Le limitazioni tecniche del sistema operativo impediscono agli utenti di avere un&#39;esperienza coerente quando tentano di sovrascrivere un file estratto da altri utenti. L&#39;esperienza varia a seconda dell&#39;applicazione utilizzata per modificare il file estratto. Talvolta, l&#39;applicazione visualizza un messaggio di errore che indica un errore di scrittura su disco o un errore apparentemente non correlato o generico. In altre occasioni, non viene visualizzato alcun messaggio di errore e l&#39;operazione sembra essere eseguita correttamente.

In questo caso, chiudendo e riaprendo il file è possibile che il contenuto non venga modificato. Tuttavia, alcune applicazioni possono memorizzare un backup del file in modo che le modifiche possano essere applicate.

Indipendentemente dal comportamento, il file rimane invariato al momento del check-in. Anche se viene visualizzata una versione diversa del file, le modifiche non vengono sincronizzate su AEM.

## Risoluzione dei problemi relativi allo spostamento dei file {#troubleshooting-problems-around-moving-files}

L&#39;API server richiede intestazioni aggiuntive, X-Destination, X-Depth e X-Overwrite, da trasmettere per il funzionamento delle operazioni di spostamento e copia. Il dispatcher non trasmette queste intestazioni per impostazione predefinita, causando il fallimento delle operazioni. Per ulteriori informazioni, vedere [Collegamento a AEM Dietro un dispatcher](install-configure-app-v1.md#connect-to-an-aem-instance-behind-a-dispatcher).

## Risoluzione dei problemi AEM connessione desktop {#troubleshooting-aem-desktop-connection-issues}

### Problema di reindirizzamento SAML {#saml-redirect-issue}

Il motivo più comune per i problemi con AEM Desktop che si collega all&#39;istanza AEM SSO (SAML) è che il processo SAML non viene reindirizzato al percorso originariamente richiesto. In alternativa, la connessione può essere reindirizzata a un host che non è configurato AEM desktop. Effettuate le seguenti operazioni per verificare il processo di accesso:

1. Aprite un browser Web.
1. Nella barra degli indirizzi, specificate l&#39;URL `/content/dam.json`.
1. Sostituite l’URL con l’istanza AEM di destinazione, ad esempio `http://localhost:4502/content/dam.json`.
1. Accedi a AEM.
1. Dopo l&#39;accesso, controllate l&#39;indirizzo corrente del browser nella barra degli indirizzi. Deve corrispondere all’URL immesso inizialmente.
1. Verificate che tutti gli elementi precedenti a `/content/dam.json` corrispondano al valore AEM di destinazione configurato in AEM Desktop.

### Problema di configurazione SSL {#ssl-configuration-issue}

Le librerie che AEM&#39;app desktop utilizza per la comunicazione HTTP utilizzano l&#39;applicazione SSL rigorosa. A volte, una connessione può avere esito positivo utilizzando un browser ma non può essere utilizzata AEM&#39;app desktop. Per configurare SSL in modo appropriato, installate il certificato intermedio mancante in Apache. Vedere [Come installare un certificato CA intermedio in Apache](https://access.redhat.com/solutions/43575).

## Utilizzo di AEM Desktop con dispatcher {#using-aem-desktop-with-dispatcher}

AEM Desktop funziona con distribuzioni AEM dietro un dispatcher, una configurazione predefinita e consigliata per AEM server. AEM dispatcher davanti AEM ambienti di authoring sono generalmente configurati per saltare la memorizzazione nella cache delle risorse DAM. Pertanto, i dispatcher non forniscono memorizzazione nella cache aggiuntiva dal punto di vista AEM Desktop. Verificate che la configurazione del dispatcher sia regolata in modo da funzionare per AEM Desktop. Per ulteriori dettagli, vedere [Collegamento a AEM dietro un dispatcher](install-configure-app-v1.md#connect-to-an-aem-instance-behind-a-dispatcher).

## Verifica dei file di registro {#checking-for-log-files}

A seconda del sistema operativo in uso, potete trovare i file di registro per AEM Desktop nelle seguenti posizioni:

* Windows: `%LocalAppData%\Adobe\AssetsCompanion\Logs`
* Mac: `~/Library/Logs/Adobe\ Experience\ Manager\ Desktop`
