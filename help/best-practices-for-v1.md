---
title: Best practice per AEM app desktop versione 1.x
description: Funzionalità chiave e uso consigliato dell'app desktop Adobe Experience Manager versione 1.x.
uuid: ba8fbc74-e1ad-4085-a031-ffd317628ba6
contentOwner: AG
products: SG_EXPERIENCEMANAGER/6.3/ASSETS
discoiquuid: 57d5cd78-abce-4ede-a50e-7c161ddb43ae
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 3e10be1fd9dd1ff5293e96b46565825e6be1fc4f
workflow-type: tm+mt
source-wordcount: '1705'
ht-degree: 0%

---


# Best practice per AEM app desktop v1.x {#aem-desktop-app-best-practices}

## Panoramica {#overview}

L&#39;app desktop Adobe Experience Manager (AEM) collega la soluzione Digital Asset Management (DAM) con il desktop, consentendo di aprire i file disponibili nell&#39;interfaccia AEM Web direttamente sul desktop. Se salvate una risorsa dal desktop, questa viene caricata in AEM nel percorso appropriato.

AEM&#39;app desktop elimina la possibilità di aggiornare copie locali non corrette o di aggiornare una risorsa errata in AEM. il flusso di lavoro di facile utilizzo dell&#39;app desktop viene attivato utilizzando la tecnologia di condivisione di rete fornita dai sistemi operativi desktop.

L&#39;app desktop installa l&#39;archivio  AEM Assets come condivisione di rete sul desktop. Pertanto, le cartelle e i file vengono visualizzati come se fossero locali. Tuttavia, non è consigliabile eseguire operazioni di gestione delle risorse digitali direttamente dal desktop nella condivisione di rete montata in Finder o Explorer.  Adobe consiglia invece di utilizzare &#39;interfaccia utente Web di AEM Assets per eseguire operazioni quali copiare o spostare un gran numero di risorse.

>[!NOTE]
>
>Prima di leggere questo documento, potete esaminare le best practice [generali per l&#39;integrazione di](https://docs.adobe.com/content/help/en/experience-manager-64/assets/administer/aem-cc-integration-best-practices.html) AEM e Creative Cloud per una panoramica di livello superiore dell&#39;argomento.

## AEM desktop app architecture {#aem-desktop-app-architecture}

AEM&#39;app desktop utilizza condivisioni di rete WebDAV (Windows) o SMB (Mac) per montare le condivisioni di rete. La condivisione di rete installata è solo locale. AEM&#39;app desktop intercetta le chiamate (apertura, lettura, scrittura) e fornisce ulteriore caching locale. Traduce le chiamate remote al server AEM Assets  per ottimizzare AEM richieste HTTP. Nel diagramma seguente è illustrata l&#39;architettura dell&#39;app desktop AEM.

![AEM&#39;architettura dell&#39;app desktop](assets/chlimage_1.png)

*Figura: architettura dell&#39;app desktop*

Se si salva un file nella cache in scrittura, il file viene salvato per primo (in modo che l&#39;utente non aspetti il trasferimento di rete). Quindi, dopo un ritardo predefinito (30 secondi), il file viene caricato in AEM in background, quindi la risorsa viene caricata in AEM. AEM&#39;app desktop fornisce un&#39;interfaccia utente per monitorare lo stato dei caricamenti dei file in background.

## Utilizzo consigliato AEM&#39;app desktop {#recommended-use-of-aem-desktop-app}

Le funzionalità chiave AEM&#39;app desktop includono:

* **Apertura di file dallinterfaccia utente Web di AEM Assets sul desktop**. Dall’interfaccia utente Web, potete visualizzare le risorse sul desktop (nel Finder, in Esplora risorse) oppure aprire una risorsa mediante un’applicazione desktop.

* **Check-out e check-in**. Le risorse possono essere sottoposte a check-out per la modifica e sono contrassegnate come bloccate per l’utente in  AEM Assets. Dopo la modifica, la risorsa può essere archiviata per sbloccarla.

* **Salvare le modifiche apportate ai file**. Qualsiasi modifica salvata nel file nella condivisione di rete viene caricata AEM automaticamente e viene creata una nuova versione.

* **Inserire risorse collegate in altri documenti**. Nelle applicazioni, come Creative Cloud ([!DNL Adobe Photoshop], [!DNL Adobe InDesign]e [!DNL Adobe Illustrator]), potete inserire un file esterno come collegamento. Ad esempio, potete inserire un&#39;immagine in un documento InDesign . In questo caso, il montaggio per la condivisione di rete consente di sfogliare e selezionare le risorse da AEM per il posizionamento. L&#39;inserimento di file collegati funziona anche in alcune app non  Adobe, come MS Office.

* **Risoluzione di riferimento in AEM**. Se entrambi i file inseriti e quelli principali con collegamento sono memorizzati in AEM possono fornire automaticamente informazioni lato server sui riferimenti delle risorse.

* **Accedete alla risorsa dal desktop**. Nella condivisione di rete montata, un menu contestuale fornisce una [!UICONTROL More Info] finestra di dialogo (anteprima più grande, metadati chiave) e la possibilità di aprire una risorsa nell’interfaccia AEM.

* **Caricamento in blocco** di cartelle gerarchiche di grandi dimensioni. Se utilizzate l&#39;opzione Crea > Caricamento cartella AEM&#39;interfaccia utente per caricare le risorse, AEM&#39;app desktop carica la gerarchia di cartelle selezionata in AEM in background. L&#39;avanzamento del caricamento può essere monitorato con un&#39;interfaccia utente specifica nell&#39;app desktop.

## Utilizzo non appropriato AEM app desktop {#inappropriate-use-of-aem-desktop-app}

* Non utilizzate AEM&#39;app desktop per gestire le risorse dal desktop. AEM&#39;app desktop non è stata creata come sostituzione per le unità di rete. Utilizzate invece le seguenti funzionalità:

   *  interfaccia utente Web di AEM Assets per la gestione delle risorse digitali (ricerca o condivisione di risorse, metadati e copia o spostamento).

   * AEM app desktop [!UICONTROL Folder Upload] per caricare cartelle gerarchiche di grandi dimensioni.

* Non trattate AEM app desktop come client di &quot;sincronizzazione desktop&quot; per  AEM Assets. Il vantaggio principale di AEM&#39;app desktop è che fornisce l&#39;accesso &quot;virtuale&quot; all&#39;intero repository, e le applicazioni di sincronizzazione desktop in genere sincronizzano solo le risorse appartenenti a un utente. AEM&#39;app desktop offre un certo livello di memorizzazione nella cache e di caricamento in background; tuttavia, funziona in modo molto diverso dalle tipiche applicazioni &quot;Sync&quot;, come l&#39;app desktop Adobe Creative Cloud o Microsoft OneDrive.

* Non utilizzate AEM unità di rete dell&#39;app desktop per salvare le risorse frequentemente. Tutte le operazioni di salvataggio vengono trasmesse a  AEM Assets. Pertanto, non è possibile eseguire operazioni di editing intensive direttamente nell&#39;archivio AEM Assets  installato. La modifica di una risorsa direttamente nell’archivio montato causa la presenza di versioni irrilevanti nella timeline della risorsa e impone costi aggiuntivi sul server.

* Non utilizzate AEM app desktop per la migrazione di grandi quantità di dati da un&#39;istanza AEM a un&#39;altra. Consulta la Guida alla [migrazione](https://docs.adobe.com/content/help/en/experience-manager-65/assets/administer/assets-migration-guide.html) per pianificare ed eseguire le migrazioni delle risorse. Al contrario, l&#39;app desktop [supporta il caricamento](use-app-v1.md#bulkupload) in blocco di un gran numero di risorse per la prima volta in [!DNL Adobe Experience Manager].

## Recommendations per i casi di utilizzo selezionati {#recommendations-for-selected-use-cases}

### Accesso alle risorse per gli utenti creativi {#access-to-assets-for-creative-users}

AEM&#39;app desktop consente l&#39;accesso virtuale all&#39;intero archivio DAM e potrebbe essere complicato per gli utenti creativi su desktop trovare e accedere alle risorse giuste sul proprio desktop. Utilizzate queste best practice per semplificarle.

* Utilizzate le funzioni di collaborazione &#39;interfaccia utente Web di AEM Assets per fornire all&#39;utente creativo un accesso più diretto alle risorse giuste. La condivisione di cartelle o raccolte, la fornitura di raccolte avanzate (ricerche salvate) o l&#39;invio di notifiche con puntatori alle risorse giuste sono alcuni di questi elementi. Gli utenti creativi possono quindi utilizzare le azioni desktop nell’interfaccia utente Web per accedere rapidamente a tali risorse sul desktop.

* Considerate le autorizzazioni corrette per le risorse (controllo degli accessi) per semplificare la visualizzazione nell’archivio DAM per gli utenti creativi, limitando sostanzialmente l’accesso alle sole risorse di cui hanno bisogno o che sono interessati:

   * Alcune aree non rilevanti per gli utenti creativi potrebbero essere rifiutate per i loro gruppi di utenti, per rimuoverle dalla loro vista, anche sul desktop.

   * La maggior parte delle risorse in DAM sono definitive e non sono destinate a essere modificate; devono essere di sola lettura per gli utenti creativi.

   * Solo le risorse che richiedono modifiche o ritocco devono essere abilitate in scrittura per gli utenti creativi. Alcune organizzazioni utilizzano AEM progetti e le cartelle create per ospitare le risorse ancora soggette a modifiche.

### Ricerca delle risorse {#searching-assets}

Per cercare un file da aprire sul desktop:

* Utilizzate l’interfaccia utente Web di  AEM Assets per individuare la risorsa. Non solo la ricerca in  AEM Assets potente (facet di ricerca, ricerche salvate), ma fornisce anche funzionalità aggiuntive per trovare la risorsa giusta. Questi includono filtri aggiuntivi, come la possibilità di cercare risorse in base allo stato (approvazione, scadenza), raccolte, attività, notifiche e condivisione di cartelle/raccolte con altri utenti/gruppi.

* Dopo aver individuato la risorsa, utilizza Azioni desktop AEM interfaccia utente per accedere alla risorsa sul desktop.

### Aggiornamento delle risorse aperte con AEM&#39;app desktop {#updating-assets-opened-using-aem-desktop-app}

Se modificate una risorsa direttamente nel percorso mappato da  AEM Assets a una condivisione di rete locale, la risorsa viene caricata in AEM ogni volta che la salvate sul desktop. Inoltre, AEM crea una versione e genera le rappresentazioni.

Se una risorsa memorizzata in AEM necessita di un aggiornamento:

* Per **piccoli aggiornamenti**, ad esempio richieste di ritocco secondarie nel processo di approvazione:

   * Estrarre il file e aprirlo sul desktop.

   * Aggiornare il file.

   * Salvate la versione aggiornata. La risorsa viene aggiornata e la timeline visualizza la versione originale per il confronto.

* Per gli aggiornamenti **** principali, ad esempio una richiesta di modifica che richiede un ciclo WIP creativo di piccole dimensioni:

   * Usate l’opzione Mostra per aprire la cartella appropriata sul desktop.

   * Copiare il file in una cartella WIP all&#39;esterno della condivisione AEM Assets  mappata (ad esempio, copiare il file in una cartella sincronizzata con l&#39;app desktop Adobe Creative Cloud).

   * Lavorare sul file e salvarlo in modo intermittente. Le modifiche non vengono salvate in  AEM Assets.

   * Una volta completate le modifiche, spostate, copiate o salvate il file mappato da AEM per caricarlo come nuova versione.

## Prestazioni della rete {#network-performance}

Una buona esperienza per gli utenti che utilizzano l&#39;app desktop AEM dipende in larga misura da una buona e stabile connettività di rete tra desktop e server AEM, nonché dal server sintonizzato per ottenere buone prestazioni, soprattutto per quanto riguarda il caricamento e l&#39;aggiornamento delle risorse. Queste raccomandazioni sono destinate ai team IT/di rete nelle organizzazioni.

### Considerazioni sulla rete {#network-considerations}

Per informazioni sulle procedure ottimali  configurazione di rete AEM Assets, consultare il documento [Considerazioni](https://docs.adobe.com/content/help/en/experience-manager-64/assets/administer/assets-migration-guide.html) sulla rete AEM Assets. Alcuni degli aspetti importanti che consentono di ottimizzare AEM&#39;esperienza dell&#39;app desktop per gli utenti includono:

* **Utilizzare il dispatcher** configurato correttamente. Utilizzate AEM Dispatcher per ulteriore protezione e accertatevi che sia configurato per la connessione [AEM app desktop AEM dietro un dispatcher](install-configure-app-v1.md#connect-to-an-aem-instance-behind-a-dispatcher)

* **Risparmia larghezza di banda**. È consigliabile disattivare l&#39;anteprima dell&#39;icona nel Finder su Mac - quando si sfoglia il repository montato tramite Finder. Il Finder richiede a ciascun file di generare un’anteprima e fa in modo che l’app desktop scarichi e memorizzi nella cache la risorsa localmente. Durante il salvataggio della larghezza di banda, l&#39;utente potrebbe anche diminuire l&#39;esperienza dell&#39;utente sul desktop, pertanto dovrebbe essere fatto quando si lavora con repository con risorse grandi e/o larghezza di banda limitata.

>[!NOTE]
>
>Per disattivare le anteprime delle icone, nel Finder passate a Visualizza, selezionate Opzioni di visualizzazione, quindi deselezionate l&#39;opzione &quot;Mostra anteprima icona&quot;. Questo funziona solo per la cartella corrente; per renderla predefinita, fate clic sul pulsante &quot;Usa come predefinito&quot; nella stessa finestra.

### Ottimizzazione delle prestazioni del server {#optimizing-server-performance}

Per capire come  server AEM Assets deve essere ottimizzato per le prestazioni, fare riferimento a [AEM Assets Performance Tuning Guide](https://docs.adobe.com/content/help/en/experience-manager-65/assets/administer/performance-tuning-guidelines.html). Alcuni degli aspetti importanti delle prestazioni del server per AEM app desktop riguardano l’ottimizzazione della configurazione del flusso di lavoro, in modo che possa essere eseguita correttamente per il caricamento delle risorse:

* **Caricamento** di risorse più performante. Configurate il modello di flusso di lavoro [AEM Aggiornamento risorse in modo che sia transitorio](https://docs.adobe.com/content/help/en/experience-manager-65/assets/administer/performance-tuning-guidelines.html#Workflows).

* **Limita la CPU del server per i caricamenti**. Assicuratevi che il parametro dei processi di flusso di lavoro parallelo massimo sia impostato correttamente, in modo che i caricamenti non esauriscano tutta la CPU.
