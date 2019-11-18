---
title: Usa app desktop AEM versione 1.x
description: Scopri come utilizzare l’app desktop Adobe Experience Manager versione 1.x e ottimizzare il lavoro con le risorse sul desktop.
uuid: 55057617-89de-43cd-8419-1252a42ab2fb
contentOwner: AG
products: SG_EXPERIENCEMANAGER/6.3/ASSETS
discoiquuid: 39d7bcad-d7b0-4978-a790-4cb68b8a7d6a
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 850d2c21a796599ed40164e7d6f892967563c16b

---


# Usa app desktop AEM v1.x {#use-aem-desktop-app-v1x}

Utilizzando l’app, le risorse in AEM sono facilmente accessibili sul desktop locale e possono essere utilizzate in qualsiasi applicazione desktop. Le risorse possono essere rivelate facilmente in Mac Finder o Windows Explorer, aperte nelle applicazioni desktop e modificate localmente; le modifiche vengono salvate nuovamente in AEM con una nuova versione creata nell’archivio.

Questa integrazione consente a diversi ruoli dell’organizzazione di gestire le risorse a livello centrale in Risorse AEM e di accedervi in Creative Cloud e altre applicazioni, semplificando al contempo il rispetto dei vari standard, compreso il branding.

Le attività chiave che eseguite con l'app desktop AEM v1 includono:

* [Connessione a un server AEM](#installandconnect)

* [Aprire le risorse direttamente sul desktop](#openondesktop)
* [Modificare e estrarre le risorse dal desktop](#workonassets)

* [Caricare le risorse e le cartelle in blocco](#bulkupload)

Per le varie operazioni e operazioni non consigliate, consultate le procedure [ottimali per l'utilizzo dell'app](best-practices-for-v1.md). Se si verificano dei problemi con l'app, consultate come [risolvere i problemi con AEM Desktop](troubleshoot-app-v1.md).

>[!NOTE]
>L’app desktop AEM è stata introdotta nella versione AEM 6.1 ed è stata denominata AEM Assets Companion App.

## Punti di contatto dell'app AEM Desktop nel flusso di lavoro creativo {#aem-desktop-app-touch-points-in-the-creative-workflow}

L’app desktop AEM, insieme a Risorse AEM, si integra nel flusso di lavoro creativo e offre i seguenti punti di contatto.

![L’app AEM Desktop permette di toccare i punti di contatto del flusso di lavoro creativo](assets/aem_desktopapp_workflow.png)

L’app AEM Desktop permette di toccare i punti di contatto del flusso di lavoro creativo

## Installare e collegare l'app desktop AEM al server AEM {#installandconnect}

Prima di iniziare a creare o modificare le risorse creative, collega l’applicazione desktop al server Risorse AEM per scaricare e caricare le risorse nell’archivio. Effettuare le seguenti operazioni:

1. [Installate l'app](#installapp).
1. [Impostare le preferenze](#inapppref) e i dettagli di connessione.
1. [Connettiti a un server](#connect) AEM e monta il repository delle risorse come unità locale.
1. [Abilitare le azioni](#desktopactions) desktop sul server AEM.

L'app desktop AEM utilizza una connessione HTTPS per connettersi al server AEM e trasferire in modo sicuro e affidabile le risorse.

>[!NOTE]
>Per tutta o parte dei passaggi di installazione e configurazione, potrebbe essere necessario aiuto dall’amministratore di sistema o dall’amministratore di sistema di AEM.

### Installare l'applicazione {#installapp}

Per utilizzare l'app desktop AEM, accertatevi che la versione del server AEM sia supportata dall'app desktop AEM. Scaricate il file di installazione appropriato (binario) per il sistema operativo in uso (Mac o Windows) e installate l'app.

La configurazione dettagliata può essere necessaria a seconda delle preferenze di rete e di sistema. Per ulteriori informazioni, consultate [Installare e configurare l'app](install-configure-app-v1.md) desktop AEM.

1. Andate alla pagina [di download dell'app desktop](https://helpx.adobe.com/experience-manager/kb/download-companion-app.html) AEM e scaricate il binario appropriato per il sistema operativo in uso.
1. Avviate il file di installazione scaricato e seguite le istruzioni visualizzate per installare l'app.

   >[!NOTE]
   >È possibile installare e attivare una sola istanza dell'app desktop AEM alla volta.

### Informazioni sulle opzioni e preferenze in-app {#inapppref}

L’applicazione consente alle impostazioni di connettersi e disconnettersi dai server AEM, visualizzare lo stato dei caricamenti, gestire la cache locale e così via. Le impostazioni predefinite funzionano per un utente tipico dell’applicazione. Potete modificare le impostazioni per ottenere di più dall’applicazione e dall’integrazione con il server AEM. Le varie impostazioni sono descritte di seguito.

**Esplora risorse** Apri l’unità locale in cui è montato l’archivio di Risorse AEM. In altre parole, esplorate le risorse ora disponibili nel computer locale.

**Visualizza stato** della risorsa Quando vengono caricate risorse modificate o vengono aggiunte nuove risorse all’archivio di Risorse AEM, l’applicazione carica le risorse in background. Il caricamento in background consente di effettuare operazioni senza dover attendere il completamento del caricamento, in particolare per le risorse di grandi dimensioni. È possibile salvare le modifiche localmente e dimenticarle. L’invio di queste risorse al server da parte dell’applicazione richiede del tempo, a seconda della larghezza di banda disponibile. Potete controllare lo stato del caricamento, insieme ad alcune informazioni di base.

**Opzioni** Fare clic/toccare Opzioni dalla barra delle applicazioni di AEM Desktop per accedere alle impostazioni per avviare l'applicazione all'avvio del sistema; per connettersi al server AEM all’avvio dell’app; e per cambiare la lettera dell’unità locale in cui Risorse AEM è disponibile dopo il montaggio.

**Avanzate &gt; Gestione cache** È possibile controllare la quantità di spazio su disco disponibile per il caching locale. Gli artefatti del server AEM Assets sono memorizzati nella cache locale per un’esperienza più fluida. Potete modificare le impostazioni predefinite in base alle vostre esigenze. Inoltre, potete cancellare la cache per recuperare nuovamente tutte le risorse. Quando cancellate la cache, vengono mantenute le modifiche non salvate. Eventuali risorse non archiviate nel server AEM vengono mantenute e non eliminate.

### Connessione a un server AEM {#connect}

L'app supporta la configurazione proxy su Mac e Windows. La configurazione viene letta all'avvio dell'app. Se modificate le impostazioni proxy, riavviate l'app per rendere effettive le modifiche.

>[!NOTE]
>
>Se modificate le impostazioni proxy, riavviate l'app per rendere effettive le modifiche. In caso contrario, l'app continua a utilizzare il server proxy configurato in precedenza.

1. Avviate l'app AEM Desktop. Per mappare l’istanza di AEM con l’app, specificate il server AEM nel formato `https://[aem-server-url]:[port]`.

   ![Effettuare l'autenticazione su Mac e fornire l'URL del server AEM](assets/aem_desktop_app_server_url.png)

1. Nella schermata di login, specificate il nome utente e la password dell’istanza. Per specificare un'istanza AEM alternativa, selezionate l' **[!UICONTROL Alternate Login URL]** opzione.

   ![Fornire le credenziali del server AEM nella schermata di accesso su AEM Desktop](assets/chlimage_1-2.png)

### Abilitare le azioni desktop nell’interfaccia Web di AEM {#desktopactions}

Dall’interfaccia utente delle risorse in un browser, puoi esplorare i percorsi delle risorse o uscire e aprire la risorsa per la modifica nell’applicazione desktop. Queste opzioni sono denominate Azioni desktop e non sono abilitate per impostazione predefinita. Per attivarla, effettuate le seguenti operazioni.

1. Nella console Risorse, tocca o fai clic sull’icona **Utente** nella barra degli strumenti.
1. Tocca o fai clic sul pulsante **[!UICONTROL My Preferences]** per visualizzare la **[!UICONTROL Preferences]** finestra di dialogo.
1. Nella finestra di dialogo Preferenze utente, selezionate **[!UICONTROL Show Desktop Actions For Assets]**. Tocca o fai clic **[!UICONTROL Accept]**.

   ![Controlla Mostra azioni desktop per risorse per abilitare le azioni desktop](assets/chlimage_1-3.png)

   Controlla Mostra azioni desktop per risorse per abilitare le azioni desktop

## Accesso e apertura di risorse sul desktop {#openondesktop}

>[!NOTE]
>In Windows, l'impostazione [](https://support.microsoft.com/en-us/kb/2668751) predefinita di Windows 7 impedisce all'app desktop AEM di gestire risorse superiori a 50 MB.

### Rivela la posizione delle risorse mappate dall’interfaccia Web di AEM {#reveal-the-location-of-mapped-assets-from-aem-web-interface}

Dopo aver mappato l’archivio di Risorse AEM sull’unità locale, potete abilitare icone aggiuntive e visualizzare la funzione Caricamento cartella per le risorse e le cartelle mappate.

1. Apri l’interfaccia di Risorse AEM e passa il puntatore su una cartella o una risorsa per visualizzare le azioni desktop come azioni rapide nella vista a schede.

   ![Nell’interfaccia utente Risorse, apri il menu Azioni rapide per visualizzare le azioni desktop](assets/chlimage_1-4.png)

   Nell’interfaccia utente Risorse, apri il menu Azioni rapide per visualizzare le azioni desktop

   Queste azioni desktop sono disponibili anche quando tocchi o fai clic sull’icona Azioni **** desktop nella barra degli strumenti dopo aver selezionato la risorsa o dalla barra degli strumenti nella pagina della risorsa.

1. Per aprire la risorsa nell’applicazione desktop associata all’estensione di file specifica, toccate o fate clic sull’icona **Apri sul desktop** , azione rapida ![Apri sul desktop](assets/aemassets_icon_openondesktop.png).

   In alternativa, scegliete **Apri** dal menu Azioni **** desktop nella barra degli strumenti.

1. Tocca o fai clic sull’icona **Mostra** azione rapida ![](assets/aemassets_reveal_icon.png) Mostra per individuare la risorsa specifica nel file system locale.

   In alternativa, scegliete **Mostra** dal menu Azioni **** desktop nella barra degli strumenti.

### Aprire le risorse AEM dal Finder o da Esplora risorse {#open-aem-assets-from-the-finder-or-the-explorer}

In Mac, selezionate Apri dal menu di scelta rapida per aprire una risorsa tramite AEM Desktop.

Per i file Adobe InDesign (INDD), selezionate **[!UICONTROL Open]** dal menu di scelta rapida. Quando fate clic su questa opzione, l'app scarica le risorse collegate nel file system locale e quindi apre il file INDD in Adobe InDesign. Questo metodo garantisce che le risorse necessarie siano disponibili localmente quando si modifica il file INDD.

In Windows, selezionate Apri sul Web dal menu di scelta rapida per aprire la risorsa. Dalla finestra Stato risorsa, toccate o fate clic sull’icona ![](assets/aemassets_icon_openondesktop.png) Apri sul desktop per aprire la risorsa.

![Opzioni del menu di scelta rapida per accedere e aprire le risorse tramite l'app AEM Desktop](assets/aem_desktopapp_mac_context_menu.png)

Opzioni del menu di scelta rapida per accedere e aprire le risorse tramite l'app AEM Desktop

### Comprendere gli stati delle risorse {#understand-the-asset-statuses}

| ![Icona app predefinita di Windows](assets/win_default.png) | L'app è connessa al server e tutte le risorse sono sincronizzate. |
|------|-----------------------------------------------------------------------------------------------------------------------------------------------------------|
| ![Icona disattivata per Windows](assets/win_disabled.png) | L'app è avviata ma non è connessa al server. Alcune risorse potrebbero essere in attesa di sincronizzazione. |
| ![Icona di sincronizzazione file Windows](assets/win_sync.png) | Le risorse vengono sincronizzate. I file vengono caricati o scaricati. Potete visualizzare gli stati esatti e sospendere i trasferimenti dalla finestra Stato risorsa. |
| ![Icona di riconnessione Windows](assets/win_refresh.png) | L'app sta tentando di riconnettersi. Potenzialmente i problemi di rete stanno causando la sua disconnessione. |

## Risorse {#workonassets}

### Estrarre risorse dall’interfaccia Web di AEM {#check-out-assets-from-the-aem-web-interface}

Risorse AEM consente di estrarre le risorse per la modifica e archiviarle nuovamente dopo aver completato le modifiche. Dopo aver estratto una risorsa, potete solo modificare, annotare, pubblicare, spostare o eliminare la risorsa. Il check-out di una risorsa blocca la risorsa e impedisce ad altri utenti di eseguire una di queste operazioni. Per poter estrarre/archiviare le risorse, è necessario disporre dell'accesso in scrittura.

Esistono due modi per estrarre le risorse dall’interfaccia Web di AEM. Per informazioni dettagliate sul primo metodo, consulta [archiviare ed estrarre i file dall’interfaccia](https://helpx.adobe.com/in/experience-manager/6-4/assets/using/check-out-and-submit-assets.html)di Assets. Seguite questi passaggi per i secondi metodi per estrarre e aprire la risorsa quando è installata l'app AEM Desktop.

1. Apri l’interfaccia di Risorse AEM e passa il puntatore su una cartella o una risorsa per visualizzare le azioni desktop come azioni rapide nella vista a schede.

   ![Opzione Proprietà nella vista a schede](assets/chlimage_1-4.png)

   Queste azioni desktop sono disponibili anche quando tocchi o fai clic sull’icona Azioni desktop nella barra degli strumenti dopo aver selezionato la risorsa o dalla barra degli strumenti nella pagina della risorsa.

1. Per aprire la risorsa, toccate o fate clic sull’icona ![Apri sul desktop azione rapida](assets/aemassets_icon_openondesktop.png)Apri sul desktop.

   In alternativa, scegliete Apri dal menu Azioni desktop nella barra degli strumenti.

   >[!NOTE]
   >Quando modificate un file che è appena aperto e non estratto, gli altri utenti non sono a conoscenza del fatto che una risorsa viene aggiornata automaticamente.

1. Per aprire una risorsa da modificare in un’applicazione Adobe Creative Cloud, toccate o fate clic sull’icona ![Modifica azione rapida desktop](assets/aemassets_icon_editdesktop.png)Modifica desktop. Viene inoltre estratta la risorsa per la modifica. Dopo aver completato la modifica, archiviate la risorsa per aggiornare le modifiche in Risorse AEM.

   In alternativa, scegliete Modifica dal menu Azioni desktop nella barra degli strumenti.

1. Selezionate l’opzione di menu Apri. Le risorse selezionate vengono aperte in modalità di anteprima.
1. Per modificare le risorse, selezionate l’opzione Modifica. Le risorse vengono aperte in modalità di modifica.

### Estrarre risorse su Mac {#check-out-assets-on-mac}

L'app consente di estrarre i file di risorse per impedire ad altri utenti di modificare i file su cui state lavorando.

1. Dal menu di scelta rapida Mac, selezionate Apri cartella Risorse AEM per aprire il Finder.

   ![Opzioni del menu di scelta rapida per accedere e aprire le risorse tramite l'app AEM Desktop](assets/aem_desktopapp_mac_context_menu.png)

   Opzioni del menu di scelta rapida per accedere e aprire le risorse tramite l'app AEM Desktop

1. Andate alla risorsa da estrarre.

   ![Apri nel menu di scelta rapida di AEM Assets in Mac](assets/chlimage_1-5.png)

1. Fai clic con il pulsante destro del mouse sulla risorsa e seleziona Ulteriori informazioni sulle risorse dal menu di scelta rapida.
1. Nella finestra di dialogo Informazioni risorsa, toccate o fate clic sull’icona Checkout per estrarre la risorsa. Dopo aver fatto clic o toccato sull'icona Checkout, l'icona Checkout viene visualizzata sull'icona Check-Out.

   ![Passa alla risorsa da estrarre](assets/chlimage_1-6.png)

1. Per archiviare la risorsa in modo che sia disponibile per gli altri utenti, toccate o fate clic sull’icona Controllo nella finestra di dialogo Informazioni risorsa.

### Estrarre risorse in Windows {#check-out-assets-on-windows}

L'app consente di estrarre i file di risorse per impedire ad altri utenti di modificare i file su cui state lavorando.

1. Dal menu di scelta rapida, selezionate Esplora risorse per aprire Esplora risorse.
1. In Esplora risorse, andate alla posizione della risorsa da estrarre.

   ![Icona Checkout](assets/chlimage_1-7.png)

1. Fai clic con il pulsante destro del mouse sulla risorsa e seleziona Apri sul Web dal menu di scelta rapida.
1. Nella finestra di dialogo Informazioni risorsa, toccate o fate clic sull’icona Checkout. L'icona Checkout (Estrazione) passa all'icona Check-in.

   ![Icona Checkout](assets/chlimage_1-8.png)

1. Rivedete la risorsa in Esplora risorse. L’icona a forma di lucchetto sull’icona ![a forma di](assets/aemassets_icon_lockcheckout.png) risorsa indica che la risorsa è stata estratta.

   >[!NOTE]
   >L'icona Blocca potrebbe essere visualizzata dopo alcuni minuti di ritardo. L'app desktop AEM memorizza nella cache le risorse per un accesso rapido, pertanto l'aggiornamento dello stato bloccato potrebbe richiedere alcuni minuti.

1. Per archiviare la risorsa in modo che sia disponibile per gli altri utenti, toccate o fate clic sull’icona Controllo nella finestra di dialogo Informazioni **** risorsa.

### Archiviare una risorsa utilizzando il Finder o Esplora risorse e l'interfaccia Web {#check-in-an-asset-using-finder-or-explorer-and-using-web-interface}

Dopo aver modificato le risorse, salvatele nell’applicazione desktop. Dal menu di scelta rapida, selezionate Ulteriori informazioni sulle risorse e toccate o fate clic su Controllo.

Le risorse vengono caricate nel server AEM. Facoltativamente, potete controllare lo stato del caricamento selezionando Visualizza stato risorsa dall’icona del vassoio.

![Finestra di stato del trasferimento e del caricamento di file app AEM Desktop](assets/aem_desktopapp_upload_status.png)

In alternativa, puoi archiviare una risorsa dall’interfaccia Web di AEM. Tocca o fai clic sulle risorse estratte o selezionarle. Dalla barra degli strumenti, fare clic o toccare l’icona di ![archiviazione Icona](assets/aemassets_icon_checkin.png).

### Caricamento in blocco di risorse e cartelle nel server AEM {#bulkupload}

Con AEM Desktop potete caricare un’intera cartella contenente risorse dalla directory locale dei file a Risorse AEM. In questo modo, tutte le risorse all’interno della cartella vengono caricate in blocco anziché caricarle una alla volta.

1. Nell’interfaccia utente delle risorse, tocca o fai clic su **Crea** nella barra degli strumenti, quindi dal menu scegli **Carica cartella** .
1. Individuate la cartella da caricare e selezionatela.
1. Tocca o fai clic su OK. Nella finestra di dialogo Stato risorse viene visualizzato lo stato del caricamento.

   ![Consultate lo stato del caricamento nella finestra Stato risorsa](assets/aem_desktopapp_bulkupload_status.png)

   Consultate lo stato del caricamento nella finestra Stato risorsa

   >[!NOTE]
   >Per sospendere o annullare manualmente il caricamento, toccate o fate clic sull’icona appropriata.

1. Dopo il caricamento della cartella, chiudi la finestra di dialogo e passa all’interfaccia utente Risorse. La cartella caricata viene visualizzata nell’interfaccia Web.

È *sconsigliato* copiare e incollare o trascinare un numero maggiore di file/cartelle nidificate dal disco locale in Finder o Esplora risorse nell'area di condivisione di rete mappata dall'app desktop AEM. È molto meno affidabile della funzionalità Carica cartella descritta in precedenza.

Un'altra alternativa, se preferite lavorare sul desktop, consiste nel selezionare i file/le cartelle da caricare in AEM nel Finder o in Esplora risorse, copiarli negli Appunti del sistema, quindi passare alla cartella di destinazione nell'area di condivisione della rete e, dal menu di scelta rapida dell'app desktop AEM, selezionare "Incolla risorse". In questo modo, l’app desktop AEM avvia il caricamento delle risorse incollate in modo simile alla cartella di caricamento descritta in precedenza.

>[!MORELIKETHIS]
>
>* [Introduzione all'app desktop AEM](https://helpx.adobe.com/experience-manager/kt/eseminars/ccoo-aem-desktop-app.html)
>* [Informazioni sul check-in/check-out con l’app desktop AEM](https://helpx.adobe.com/experience-manager/kt/assets/using/checkin-checkout-technical-video-understand.html)
>* [Risoluzione dei problemi relativi all’applicazione desktop AEM](troubleshoot-app-v1.md)

