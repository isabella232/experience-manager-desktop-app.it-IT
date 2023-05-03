---
title: Best practice per l’app desktop v1.10
description: Funzionalità chiave e uso consigliato di [!DNL Adobe Experience Manager] app desktop versione 1.10.
exl-id: 5de06b33-c05c-47eb-b884-408b6f9afc94
source-git-commit: 7a7236c36f615e97e9d040e6139368a931eb579e
workflow-type: tm+mt
source-wordcount: '1676'
ht-degree: 0%

---

# Best practice per l’app desktop AEM versione 1.10 {#aem-desktop-app-best-practices}

## Panoramica {#overview}

[!DNL Adobe Experience Manager] l’app desktop collega la soluzione DAM (Digital Asset Management) con il desktop, in modo da poter aprire i file disponibili nell’interfaccia web AEM direttamente sul desktop. Se salvi una risorsa dal desktop, viene caricata in AEM nella posizione appropriata.

AEM’app desktop elimina le possibilità di aggiornare copie locali non corrette o di aggiornare una risorsa errata in AEM. il flusso di lavoro di facile utilizzo dell’app desktop è abilitato tramite la tecnologia di condivisione di rete fornita dai sistemi operativi desktop.

L’app desktop installa l’archivio AEM Assets come condivisione di rete sul desktop. Pertanto, le cartelle e i file vengono visualizzati come se fossero locali. Tuttavia, si sconsiglia di eseguire operazioni di gestione delle risorse digitali direttamente dal desktop nella condivisione di rete montata in Finder o Explorer. Adobe consiglia invece di utilizzare l’interfaccia utente Web di AEM Assets per eseguire operazioni quali la copia o lo spostamento di un numero elevato di risorse.

>[!NOTE]
>
>Prima di leggere questo documento, è possibile esaminare il [Best practice per l’integrazione di AEM e Creative Cloud](https://experienceleague.adobe.com/docs/experience-manager-65/assets/administer/aem-cc-integration-best-practices.html) per una panoramica di livello superiore dell’argomento.

## Architettura dell’app desktop AEM {#aem-desktop-app-architecture}

AEM&#39;app desktop utilizza condivisioni di rete WebDAV (Windows) o SMB (Mac) per montare le condivisioni di rete. La condivisione di rete montata è solo locale. L’app desktop AEM intercetta le chiamate (aperte, lette, scritte) e fornisce una memorizzazione in cache locale aggiuntiva. Traduce le chiamate remote al server AEM Assets per ottimizzare le richieste HTTP AEM. Il diagramma seguente illustra l’architettura dell’app desktop AEM.

![Architettura dell’app desktop AEM](assets/arch_v1.png)

*Figura: architettura dell’app desktop*

Il caching aggiuntivo in scrittura quando un file viene salvato determina il salvataggio del file in locale per prima cosa (in modo che l&#39;utente non aspetti il trasferimento di rete). Quindi, dopo un ritardo predefinito (30 s) il file viene caricato in AEM in background, e poi la risorsa viene caricata in AEM. AEM’app desktop fornisce un’interfaccia utente per monitorare lo stato dei caricamenti di file in background.

## Utilizzo consigliato AEM’app desktop {#recommended-use-of-aem-desktop-app}

Le funzionalità chiave dell’app desktop AEM includono:

* **Apertura di file dall’interfaccia Web di AEM Assets sul desktop**. Dall’interfaccia utente Web puoi visualizzare le risorse sul desktop (in Finder, Esplora risorse) o aprire una risorsa utilizzando un’applicazione desktop.

* **Check-out e check-in**. Le risorse possono essere sottoposte a Check-Out per la modifica e contrassegnate come bloccate per l’utente in AEM Assets. Dopo la modifica, puoi archiviare la risorsa per sbloccarla.

* **Salvare le modifiche apportate ai file**. Tutte le modifiche salvate nel file nella condivisione di rete vengono caricate in AEM automaticamente e viene creata una nuova versione.

* **Posizionare risorse collegate in altri documenti**. In applicazioni, come la Creative Cloud ([!DNL Adobe Photoshop], [!DNL Adobe InDesign]e [!DNL Adobe Illustrator]), puoi inserire un file esterno come collegamento. Ad esempio, è possibile inserire un’immagine in un documento InDesign. In questo caso, il montaggio di condivisione di rete consente di sfogliare e selezionare le risorse da AEM per il posizionamento. Il posizionamento di file collegati funziona anche in alcune applicazioni non Adobi, come MS Office.

* **Risoluzione di riferimento in AEM**. Se entrambi, i file inseriti e i file principali con collegamento, sono memorizzati in AEM può fornire automaticamente informazioni lato server sui riferimenti delle risorse.

* **Accedere alla risorsa dal desktop**. Nella condivisione di rete montata, un menu contestuale fornisce un [!UICONTROL More Info] finestra di dialogo (anteprima più ampia, metadati chiave) e possibilità di aprire una risorsa nell’interfaccia utente AEM.

* **Caricamento in blocco di cartelle grandi e gerarchiche**. Se utilizzi l’opzione Crea > Caricamento cartelle AEM’interfaccia utente per caricare le risorse, AEM’app desktop carica la gerarchia di cartelle selezionata in AEM in background. L’avanzamento del caricamento può essere monitorato con un’interfaccia utente specifica nell’app desktop.

## Uso inappropriato dell’app desktop AEM {#inappropriate-use-of-aem-desktop-app}

* Non utilizzare AEM’app desktop per gestire le risorse dal desktop. AEM&#39;app desktop non è stata creata come alternativa per le unità di rete. Utilizza invece le seguenti funzionalità:

   * Interfaccia web AEM Assets per la gestione delle risorse digitali (ricerca o condivisione di risorse, metadati e copia o spostamento).

   * app desktop AEM [!UICONTROL Folder Upload] per caricare cartelle grandi e gerarchiche.

* Non trattare AEM’app desktop come client di &quot;sincronizzazione desktop&quot; per AEM Assets. Il vantaggio principale dell’app desktop AEM è che fornisce accesso &quot;virtuale&quot; all’intero archivio e le applicazioni di sincronizzazione desktop in genere sincronizzano solo le risorse appartenenti a un utente. AEM&#39;app desktop fornisce un certo livello di memorizzazione in cache e caricamento in background; tuttavia, funziona in modo molto diverso rispetto alle tipiche applicazioni &quot;Sync&quot;, come l&#39;app desktop Adobe Creative Cloud o Microsoft OneDrive.

* Non utilizzare AEM unità di rete per app desktop per salvare le risorse frequentemente. Tutte le operazioni di salvataggio vengono trasmesse ad AEM Assets. Pertanto, non è pratico eseguire operazioni di editing intensive direttamente nell&#39;archivio AEM Assets montato. La modifica di una risorsa direttamente nell’archivio montato crea la timeline della risorsa con versioni irrilevanti e impone costi generali aggiuntivi sul server.

* Non utilizzare AEM app desktop per la migrazione di grandi quantità di dati da un’istanza AEM a un’altra. Consulta la sezione [Guida alla migrazione](https://experienceleague.adobe.com/docs/experience-manager-65/assets/administer/assets-migration-guide.html) per pianificare ed eseguire le migrazioni delle risorse. Al contrario, l’app desktop [supporta il caricamento in blocco](use-app-v1.md#bulkupload) numero elevato di risorse per la prima volta in [!DNL Adobe Experience Manager].

## Recommendations per casi d’uso selezionati {#recommendations-for-selected-use-cases}

### Accesso alle risorse per gli utenti creativi {#access-to-assets-for-creative-users}

AEM’app desktop fornisce l’accesso virtuale all’intero archivio DAM e potrebbe essere complicato per gli utenti creativi sul desktop trovare e accedere alle risorse corrette sul desktop. Utilizza queste best practice per semplificarle.

* Utilizza le funzioni di collaborazione nell’interfaccia utente web di AEM Assets per fornire all’utente creativo un accesso più diretto alle risorse giuste. Alcuni di essi condividono cartelle o raccolte, forniscono raccolte avanzate (ricerche salvate) o inviano notifiche con puntatori alle risorse giuste. Gli utenti creativi possono quindi utilizzare le azioni desktop nell’interfaccia utente web per accedere rapidamente a tali risorse sul desktop.

* Prendi in considerazione le autorizzazioni corrette per le risorse (controllo accessi) per semplificare la visualizzazione nell’archivio DAM per gli utenti creativi, essenzialmente limitandone l’accesso alle sole risorse di cui hanno bisogno o sono interessati:

   * Alcune aree non rilevanti per gli utenti creativi potrebbero essere negate per i loro gruppi di utenti, per rimuoverli dalla loro vista, anche sul desktop.

   * La maggior parte delle risorse in DAM sono definitive e non sono destinate a essere modificate. Devono essere di sola lettura per gli utenti creativi.

   * Solo le risorse che richiedono modifiche o ritocco devono essere abilitate per la scrittura per gli utenti creativi. Alcune organizzazioni utilizzano AEM progetti e le cartelle create per ospitare risorse ancora soggette a modifiche.

### Ricerca delle risorse {#searching-assets}

Per cercare un file da aprire sul desktop :

* Utilizza l’interfaccia web di AEM Assets per individuare la risorsa. Non solo la ricerca in AEM Assets è potente (facet di ricerca, ricerche salvate), ma fornisce anche funzionalità aggiuntive per trovare la risorsa giusta. Questi includono filtri aggiuntivi, come la possibilità di cercare le risorse in base allo stato (approvazione, scadenza), alle raccolte, alle attività, alle notifiche e alla condivisione di cartelle/raccolte con altri utenti/gruppi.

* Dopo aver individuato la risorsa, utilizza Azioni desktop nell’interfaccia utente AEM per accedere alla risorsa sul desktop .

### Aggiornamento delle risorse aperte con AEM’app desktop {#updating-assets-opened-using-aem-desktop-app}

Se modifichi una risorsa direttamente nel percorso mappato da AEM Assets a una condivisione di rete locale, la risorsa viene caricata in AEM ogni volta che la salvi sul desktop. Inoltre, AEM crea una versione e genera rappresentazioni.

Se una risorsa memorizzata in AEM necessita di un aggiornamento:

* Per **aggiornamenti minori**, ad esempio richieste di ritocco minori nel processo di approvazione:

   * Estrai il file e aprilo sul desktop.

   * Aggiorna il file.

   * Salva la versione aggiornata. La risorsa viene aggiornata e la timeline visualizza la versione originale da confrontare.

* Per **aggiornamenti principali**, ad esempio una richiesta di modifica che richiede un piccolo ciclo WIP creativo:

   * Utilizzare l&#39;opzione Mostra per aprire la cartella appropriata sul desktop.

   * Copia il file in una cartella WIP al di fuori della condivisione AEM Assets mappata (ad esempio, copia il file in una cartella sincronizzata con l’app desktop Adobe Creative Cloud).

   * Lavora sul file e salvalo a intermittenza. Le modifiche non vengono salvate in AEM Assets.

   * Al termine delle modifiche, sposta, copia o salva il file mappato da AEM per caricarlo come nuova versione.

## Prestazioni di rete {#network-performance}

Una buona esperienza per gli utenti che utilizzano l’app desktop AEM dipende in larga misura da una buona e stabile connettività di rete tra i desktop e il server AEM, nonché dal server configurato per ottenere buone prestazioni, soprattutto per quanto riguarda il caricamento e l’aggiornamento delle risorse. Queste raccomandazioni sono per i team di rete / IT nelle organizzazioni.

### Considerazioni sulla rete {#network-considerations}

Per informazioni sulle best practice relative alla configurazione di rete AEM Assets, consulta [Come migrare le risorse in massa](https://experienceleague.adobe.com/docs/experience-manager-65/assets/administer/assets-migration-guide.html) documento. Alcuni degli aspetti importanti che consentono di ottimizzare AEM’esperienza nell’app desktop per gli utenti includono:

* **Usa Dispatcher configurato correttamente**. Utilizza AEM Dispatcher per ulteriore sicurezza e assicurati che sia configurato per [AEM la connessione dell’app desktop a AEM dietro un dispatcher](install-configure-app-v1.md#connect-to-an-aem-instance-behind-a-dispatcher)

* **Risparmia larghezza di banda**. È consigliabile disattivare l&#39;anteprima delle icone nel Finder su Mac - quando si naviga nel repository montato utilizzando Finder. Il Finder richiede che ogni file generi un’anteprima e fa sì che l’app desktop scarichi e memorizzi in cache localmente la risorsa. Tieni presente che il risparmio di larghezza di banda riduce anche l’esperienza utente per gli utenti sul desktop, quindi dovrebbe essere fatto quando si lavora con archivi con risorse di grandi dimensioni e/o con una larghezza di banda limitata.

>[!NOTE]
>
>Per disattivare le anteprime delle icone, nel Finder vai a [!UICONTROL View], seleziona [!UICONTROL View Options], quindi deseleziona il [!UICONTROL Show icon preview] opzione . Questa opzione funziona solo per la cartella corrente. Per renderla predefinita, fai clic sul pulsante [!UICONTROL Use as default] nella stessa finestra di dialogo.

### Ottimizzazione delle prestazioni del server {#optimizing-server-performance}

Per capire come ottimizzare le prestazioni del server AEM Assets, consulta [Guida all’ottimizzazione delle prestazioni di AEM Assets](https://experienceleague.adobe.com/docs/experience-manager-65/assets/administer/performance-tuning-guidelines.html). Alcuni degli aspetti importanti delle prestazioni del server per AEM’app desktop riguardano l’ottimizzazione della configurazione del flusso di lavoro in modo che funzioni bene per il caricamento delle risorse:

* **Caricamento di risorse più performante**. Configura le [AEM modello di flusso di lavoro Asset Update transitorio](https://experienceleague.adobe.com/docs/experience-manager-65/assets/administer/performance-tuning-guidelines.html).

* **Limita la CPU del server per i caricamenti**. Assicurati che il parametro dei lavori del flusso di lavoro parallelo massimo sia impostato correttamente, in modo che i caricamenti non esauriscano tutta la CPU.
