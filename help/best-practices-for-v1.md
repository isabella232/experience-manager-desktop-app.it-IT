---
title: Best practice per l’app desktop AEM versione 1.x
description: Funzionalità chiave e uso consigliato dell’app desktop Adobe Experience Manager versione 1.x.
uuid: ba8fbc74-e1ad-4085-a031-ffd317628ba6
contentOwner: AG
products: SG_EXPERIENCEMANAGER/6.3/ASSETS
discoiquuid: 57d5cd78-abce-4ede-a50e-7c161ddb43ae
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 52f70e5b95318d8b3b3930be1233cc51aa997914

---


# Best practice per l&#39;app desktop AEM v1.x {#aem-desktop-app-best-practices}

## Panoramica {#overview}

L’app desktop Adobe Experience Manager (AEM) collega la soluzione Digital Asset Management (DAM) con il desktop, consentendo di aprire i file disponibili nell’interfaccia Web di AEM direttamente sul desktop. Se salvate una risorsa dal desktop, questa viene caricata in AEM nel percorso appropriato.

L’app desktop AEM elimina la possibilità di aggiornare copie locali non corrette o di aggiornare una risorsa errata in AEM. il flusso di lavoro di facile utilizzo dell&#39;app desktop viene attivato utilizzando la tecnologia di condivisione di rete fornita dai sistemi operativi desktop.

L’app desktop consente di installare l’archivio di Risorse AEM come condivisione di rete sul desktop. Pertanto, le cartelle e i file vengono visualizzati come se fossero locali. Tuttavia, non è consigliabile eseguire operazioni di gestione delle risorse digitali direttamente dal desktop nella condivisione di rete montata in Finder o Explorer. Adobe consiglia di utilizzare l’interfaccia utente Web di Risorse AEM per eseguire operazioni quali copiare o spostare un gran numero di risorse.

>[!NOTE]
>
>Prima di leggere questo documento, puoi consultare le best practice [generali per l’integrazione con](https://docs.adobe.com/content/help/en/experience-manager-64/assets/administer/aem-cc-integration-best-practices.html) AEM e Creative Cloud per una panoramica di livello superiore dell’argomento.

## AEM desktop app architecture {#aem-desktop-app-architecture}

L’app desktop AEM utilizza le condivisioni di rete WebDAV (Windows) o SMB (Mac) per il montaggio delle condivisioni di rete. La condivisione di rete installata è solo locale. L’app desktop AEM intercetta le chiamate (apertura, lettura, scrittura) e fornisce un ulteriore caching locale. Traduce le chiamate remote al server AEM Assets per ottimizzare le richieste AEM HTTP. Nel diagramma seguente è illustrata l&#39;architettura dell&#39;app desktop AEM.

![Architettura dell&#39;app desktop AEM](assets/chlimage_1.png)

Se si salva un file nella cache in scrittura, il file viene salvato per primo (in modo che l&#39;utente non aspetti il trasferimento di rete). Quindi, dopo un ritardo predefinito (30 secondi), il file viene caricato in background in AEM e quindi la risorsa viene caricata in AEM. L’app desktop AEM fornisce un’interfaccia utente per il monitoraggio dello stato dei caricamenti dei file in background.

## Utilizzo consigliato dell&#39;app desktop AEM {#recommended-use-of-aem-desktop-app}

Le funzionalità chiave dell&#39;app desktop AEM includono:

* Apertura di file dall’interfaccia Web di AEM Assets sul desktop: Dall’interfaccia utente Web, potete visualizzare le risorse sul desktop (nel Finder, in Esplora risorse) oppure aprire una risorsa mediante un’applicazione desktop.
* Check-out e check-in: Le risorse possono essere ritirate per la modifica, sono contrassegnate come bloccate per l’utente in Risorse AEM. Dopo la modifica, la risorsa può essere archiviata per sbloccarla.
* Salvare le modifiche apportate ai file: Eventuali modifiche salvate nel file nella condivisione di rete vengono caricate automaticamente in AEM e viene creata una nuova versione.
* Inserire risorse collegate in altri documenti: Nelle applicazioni, come Creative Cloud (PS, ID, AI, ecc.), potete inserire un file esterno come collegamento (ad esempio, potete inserire un&#39;immagine in un documento InDesign). In questo caso, il supporto per la condivisione di rete consente di sfogliare e selezionare le risorse da AEM per il posizionamento. L&#39;inserimento di file collegati funziona anche in alcune app non Adobe, come MS Office.
* Risoluzione di riferimento in AEM: Se in AEM sono memorizzati sia i file inseriti che il file principale con i collegamenti, questi possono fornire automaticamente informazioni lato server sui riferimenti alle risorse.
* Accedete alla risorsa dal desktop: Nella condivisione di rete montata, un menu contestuale offre una finestra di dialogo Ulteriori informazioni (anteprima più grande, metadati chiave) e la possibilità di aprire una risorsa nell’interfaccia utente di AEM.
* Caricamento in blocco di cartelle gerarchiche grandi: Se utilizzate l&#39;opzione Crea > Caricamento cartella nell&#39;interfaccia utente di AEM per caricare le risorse, l&#39;app desktop AEM carica in background la gerarchia di cartelle selezionata in AEM. L&#39;avanzamento del caricamento può essere monitorato con un&#39;interfaccia utente specifica nell&#39;app desktop.

## Utilizzo non appropriato dell&#39;app desktop AEM {#inappropriate-use-of-aem-desktop-app}

* Non utilizzate l&#39;app desktop AEM per gestire le risorse dal desktop. L&#39;app desktop AEM non è stata creata come sostituzione per le unità di rete. Utilizzate invece le seguenti funzionalità:
   * Interfaccia Web di AEM Assets per la gestione delle risorse digitali (ricerca/condivisione di risorse, metadati, copia/spostamento, ecc.)
   * Cartella delle app desktop AEM Carica per caricare cartelle gerarchiche grandi

* Non trattate l’app desktop AEM come client di &quot;sincronizzazione desktop&quot; per AEM Assets. Il vantaggio principale dell&#39;app desktop AEM è rappresentato dal fatto che fornisce l&#39;accesso &quot;virtuale&quot; all&#39;intero repository, e le applicazioni di sincronizzazione desktop generalmente sincronizzano solo le risorse appartenenti a un utente. L&#39;app desktop AEM offre un certo livello di memorizzazione nella cache e di caricamento in background; tuttavia, funziona in modo molto diverso dalle tipiche applicazioni &quot;Sync&quot;, come l&#39;app desktop Adobe Creative Cloud o Microsoft OneDrive.
* Non utilizzate le unità di rete delle app desktop AEM per salvare frequentemente le risorse. Tutte le operazioni di salvataggio vengono trasmesse a Risorse AEM. Pertanto, non è possibile eseguire operazioni di modifica intensiva direttamente nell’archivio di Risorse AEM. La modifica di una risorsa direttamente nell’archivio montato causa la presenza di versioni irrilevanti nella timeline della risorsa e impone costi aggiuntivi sul server.
* Non utilizzate l&#39;app desktop AEM per migrare grandi quantità di dati da un&#39;istanza AEM a un&#39;altra. Per pianificare ed eseguire la migrazione delle risorse, consulta la Guida alla [migrazione](https://docs.adobe.com/content/help/en/experience-manager-65/assets/administer/assets-migration-guide.html) . Al contrario, l&#39;app desktop [supporta il caricamento](use-app-v1.md#bulkupload) in blocco di un gran numero di risorse per la prima volta in AEM.

## Raccomandazioni per i casi di utilizzo selezionati {#recommendations-for-selected-use-cases}

### Accesso alle risorse per gli utenti creativi {#access-to-assets-for-creative-users}

L&#39;app desktop AEM fornisce l&#39;accesso virtuale all&#39;intero archivio DAM e potrebbe essere complicato per gli utenti creativi su desktop trovare e accedere alle risorse giuste sul loro desktop. Utilizzate queste best practice per semplificarle.

* Utilizzate le funzioni di collaborazione nell&#39;interfaccia utente Web di AEM Assets per fornire all&#39;utente creativo un accesso più diretto alle risorse giuste. La condivisione di cartelle o raccolte, la fornitura di raccolte avanzate (ricerche salvate) o l&#39;invio di notifiche con puntatori alle risorse giuste sono alcuni di questi elementi. Gli utenti creativi possono quindi utilizzare le azioni desktop nell’interfaccia utente Web per accedere rapidamente a tali risorse sul desktop.
* Considerate le autorizzazioni corrette per le risorse (controllo degli accessi) per semplificare la visualizzazione nell’archivio DAM per gli utenti creativi, in pratica limitandone l’accesso alle sole risorse di cui hanno bisogno/sono interessati:

   * Alcune aree non rilevanti per gli utenti creativi potrebbero essere rifiutate per i loro gruppi di utenti, per rimuoverli dalla loro vista, anche sul desktop
   * La maggior parte delle risorse in DAM sono definitive e non sono destinate a essere modificate; devono essere di sola lettura per gli utenti creativi
   * Solo le risorse che richiedono modifiche/ritocco devono essere abilitate in scrittura per gli utenti creativi. Alcune organizzazioni utilizzano Progetti AEM e le cartelle create per ospitare risorse che sono ancora soggette a modifiche.

### Ricerca delle risorse {#searching-assets}

Per cercare un file da aprire sul desktop:

* Utilizza l’interfaccia utente Web di AEM Assets per individuare la risorsa. Non solo la ricerca in Risorse AEM è potente (facet di ricerca, ricerche salvate), ma offre anche funzionalità aggiuntive per trovare la risorsa giusta. Tra questi vi sono altri filtri, come la possibilità di cercare risorse in base allo stato (approvazione, scadenza), raccolte, attività, notifiche e condivisione di cartelle/raccolte con altri utenti/gruppi.
* Dopo aver individuato la risorsa, utilizza Azioni desktop nell’interfaccia utente di AEM per accedere alla risorsa sul desktop.

### Aggiornamento delle risorse aperte con l&#39;app desktop AEM {#updating-assets-opened-using-aem-desktop-app}

Se modificate una risorsa direttamente nel percorso mappato da Risorse AEM a una condivisione di rete locale, la risorsa viene caricata in AEM ogni volta che la salvate sul desktop. Inoltre, AEM crea una versione e genera le rappresentazioni.

Se una risorsa memorizzata in AEM richiede un aggiornamento:

* Per **piccoli aggiornamenti**, ad esempio richieste di ritocco secondarie nel processo di approvazione:

   * Estrarre il file e aprirlo sul desktop
   * Aggiornare il file
   * Salvate la versione aggiornata. La risorsa viene aggiornata e la timeline visualizza la versione originale per il confronto

* Per gli aggiornamenti **** principali, ad esempio una richiesta di modifica che richiede un ciclo WIP creativo di piccole dimensioni:

   * Utilizzate l&#39;opzione Mostra per aprire la cartella appropriata sul desktop
   * Copia il file in una cartella WIP al di fuori della condivisione di Risorse AEM mappata (ad esempio, copia il file in una cartella sincronizzata con l’app desktop Adobe Creative Cloud)
   * Lavorare sul file e salvarlo in modo intermittente. Le modifiche non vengono salvate in Risorse AEM
   * Una volta completate le modifiche, spostate, copiate o salvate il file mappato da AEM per caricarlo come nuova versione

## Prestazioni della rete {#network-performance}

Una buona esperienza per gli utenti che utilizzano l’app desktop AEM dipende in larga misura da una buona e stabile connettività di rete tra desktop e server AEM, nonché dal server sintonizzato per ottenere buone prestazioni, soprattutto per quanto riguarda il caricamento e l’aggiornamento delle risorse. Queste raccomandazioni sono destinate ai team IT/di rete nelle organizzazioni.

### Considerazioni sulla rete {#network-considerations}

Per informazioni sulle best practice relative alla configurazione di rete di Risorse AEM, consulta il documento Considerazioni [sulla rete di Risorse](https://docs.adobe.com/content/help/en/experience-manager-64/assets/administer/assets-migration-guide.html) AEM. Alcuni degli aspetti importanti che consentono di ottimizzare l&#39;esperienza dell&#39;app desktop AEM per gli utenti includono:

* **Usa dispatcher configurato correttamente:** Utilizzate AEM Dispatcher per ulteriore sicurezza e accertatevi che sia configurato per la connessione dell&#39;app desktop [AEM ad AEM dietro un dispatcher](install-configure-app-v1.md#connect-to-an-aem-instance-behind-a-dispatcher)

* **Salva larghezza di banda:** È consigliabile disattivare l&#39;anteprima dell&#39;icona nel Finder su Mac - quando si sfoglia il repository montato tramite Finder. Il Finder richiede a ciascun file di generare un’anteprima e fa in modo che l’app desktop scarichi e memorizzi nella cache la risorsa localmente. Durante il salvataggio della larghezza di banda, l&#39;utente potrebbe anche diminuire l&#39;esperienza dell&#39;utente sul desktop, pertanto dovrebbe essere fatto quando si lavora con repository con risorse grandi e/o larghezza di banda limitata.

>[!NOTE]
>
>Per disattivare le anteprime delle icone, nel Finder passate a Visualizza, selezionate Opzioni di visualizzazione, quindi deselezionate l&#39;opzione &quot;Mostra anteprima icona&quot;. Questo funziona solo per la cartella corrente; per renderla predefinita, fate clic sul pulsante &quot;Usa come predefinito&quot; nella stessa finestra.

### Ottimizzazione delle prestazioni del server {#optimizing-server-performance}

Per capire come ottimizzare le prestazioni del server Risorse AEM, consulta la Guida [alla sintonizzazione delle prestazioni di Risorse](https://docs.adobe.com/content/help/en/experience-manager-65/assets/administer/performance-tuning-guidelines.html)AEM. Alcuni degli aspetti importanti delle prestazioni del server per l’app desktop AEM riguardano l’ottimizzazione della configurazione del flusso di lavoro, in modo che possa essere eseguita correttamente per il caricamento delle risorse:

* **Caricamento di risorse più performanti:** Configurate il modello di flusso di lavoro Aggiornamento risorse [AEM in modo che sia transitorio](https://docs.adobe.com/content/help/en/experience-manager-65/assets/administer/performance-tuning-guidelines.html#Workflows).

* **Limita CPU server per i caricamenti:** Assicuratevi che il parametro dei processi di flusso di lavoro parallelo massimo sia impostato correttamente, in modo che i caricamenti non esauriscano tutta la CPU.
