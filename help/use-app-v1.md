---
title: Utilizzare [!DNL Experience Manager] app desktop versione 1.10.
description: Scopri come utilizzare l’app desktop Adobe Experience Manager versione 1.10 e ottimizzare il tuo lavoro con le risorse sul desktop.
feature: Desktop App,Asset Management
exl-id: 2fdc1c8d-b822-4cca-ad06-bd875a00aa6d
source-git-commit: dcd29d0bbb32004d970d334c256e659f4a4c39e1
workflow-type: tm+mt
source-wordcount: '2367'
ht-degree: 0%

---

# Utilizzare [!DNL Experience Manager] app desktop v1.10 {#use-aem-desktop-app-v1x}

Utilizzando l’app, le risorse in [!DNL Experience Manager] sono facilmente accessibili sul desktop locale e possono essere utilizzati in qualsiasi applicazione desktop. Le risorse possono essere facilmente rivelate in Mac Finder o Esplora risorse, aperte in applicazioni desktop e modificate localmente: le modifiche vengono salvate nuovamente in [!DNL Experience Manager] con una nuova versione creata nel repository.

Tale integrazione consente a vari ruoli dell’organizzazione di gestire centralmente le risorse in Assets e di accedervi nella Creative Cloud e in altre applicazioni, semplificando al contempo l’adesione ai vari standard, tra cui il branding.

Le attività chiave che esegui utilizzando [!DNL Experience Manager] l&#39;app desktop v1 include:

1. [Connetti con [!DNL Experience Manager] server](#installandconnect)
1. [Aprire le risorse direttamente sul desktop](#openondesktop)
1. [Modificare ed estrarre le risorse dal desktop](#workonassets)
1. [Caricare risorse e cartelle in blocco](#bulkupload)

Per le varie dosi consigliate, vedere la [best practice per l’utilizzo dell’app](best-practices-for-v1.md). Se riscontri problemi durante l’utilizzo dell’app, consulta la sezione come [risolvere i problemi [!DNL Experience Manager] desktop](troubleshoot-app-v1.md).

>[!NOTE]
>
>L’app desktop è stata introdotta in [!DNL Experience Manager] versione 6.1 ed è stato chiamato [!DNL Experience Manager Assets Companion App].

## [!DNL Experience Manager] punti di contatto per le app desktop nel flusso di lavoro creativo {#aem-desktop-app-touch-points-in-the-creative-workflow}

[!DNL Experience Manager] app desktop, insieme a [!DNL Assets], si integra nel flusso di lavoro creativo e offre i seguenti punti di contatto.

![[!DNL Experience Manager] I punti di contatto delle app desktop rappresentano il flusso di lavoro creativo](assets/aem_desktopapp_workflow.png)

[!DNL Experience Manager] I punti di contatto delle app desktop rappresentano il flusso di lavoro creativo

## Installa e connetti l’app a [!DNL Experience Manager] server {#installandconnect}

Prima di iniziare a creare o modificare le risorse creative, connetti l’applicazione desktop al [!DNL Assets] per scaricare e caricare le risorse nell’archivio. Esegui le seguenti attività:

1. [Installa l’app](#installapp).
1. [Impostare le preferenze](#inapppref) e dettagli di connessione.
1. [Connetti a un [!DNL Experience Manager] server](#connect) e montare l’archivio delle risorse come unità locale.
1. [Abilita azioni desktop](#desktopactions) il [!DNL Experience Manager] server.

[!DNL Experience Manager] L’app desktop utilizza una connessione HTTPS per la connessione a [!DNL Experience Manager] per trasferire in modo sicuro e affidabile le risorse.

>[!NOTE]
>
>Per una parte o tutte le fasi di installazione e configurazione, potrebbe essere necessario l&#39;aiuto del [!DNL Experience Manager] amministratore di sistema.

### Installare l’applicazione {#installapp}

Da utilizzare [!DNL Experience Manager] dell&#39;app desktop, assicurati che le tue [!DNL Experience Manager] versione del server supportata dall&#39;app. Scarica il file di installazione appropriato (binario) per il sistema operativo in uso (Mac o Windows) e installa l’app.

A seconda delle preferenze di rete e di sistema, può essere necessaria una configurazione dettagliata. Consulta [Installare e configurare [!DNL Experience Manager] app desktop](install-configure-app-v1.md) per ulteriori dettagli.

1. Vai a [[!DNL Experience Manager] pagina di download dell’app desktop v1.10](/help/release-notes-of-v1.md) e scarica il file binario appropriato per il sistema operativo in uso.
1. Avvia il file di installazione scaricato e segui le istruzioni visualizzate per installare l’app.

   >[!NOTE]
   >
   >Solo un&#39;istanza del [!DNL Experience Manager] L’app desktop può essere installata e attiva alla volta.

### Comprendere le opzioni e le preferenze in-app {#inapppref}

L&#39;applicazione consente la connessione e la disconnessione delle impostazioni [!DNL Experience Manager] server, visualizzare lo stato dei caricamenti, gestire la cache locale e così via. Le impostazioni predefinite funzionano per un utente tipico dell’applicazione. È possibile modificare le impostazioni per sfruttare al meglio l’applicazione e l’integrazione con [!DNL Experience Manager] server. Le varie impostazioni sono descritte di seguito in dettaglio.

**Esplora risorse** Aprire l&#39;unità locale in cui [!DNL Assets] l’archivio è montato. In altre parole, esplora le risorse ora rese disponibili sul computer locale.

**Visualizzare lo stato delle risorse** Quando vengono caricate o aggiunte nuove risorse al [!DNL Assets] , l’applicazione carica le risorse in background. Il caricamento in background consente operazioni senza problemi, senza dover attendere il completamento del caricamento, in particolare per le risorse di grandi dimensioni. Puoi salvare le modifiche localmente e dimenticarle. L’invio di queste risorse al server da parte dell’applicazione richiede un po’ di tempo, a seconda della larghezza di banda disponibile. Puoi controllare lo stato del caricamento, insieme ad alcune informazioni di base.

**Opzioni** Fare clic sulle opzioni nella barra delle applicazioni del desktop per accedere alle impostazioni e avviare l&#39;applicazione all&#39;avvio del sistema; per connettersi al [!DNL Experience Manager] all&#39;avvio dell&#39;app e per modificare la lettera di unità locale in cui [!DNL Assets] dopo il montaggio.

**Avanzate > Gestisci cache** È possibile controllare la quantità di spazio su disco disponibile per la memorizzazione nella cache locale. Gli artefatti di [!DNL Assets] server sono memorizzati nella cache locale per un’esperienza più fluida. È possibile modificare le impostazioni predefinite in base alle proprie esigenze. Inoltre, puoi cancellare la cache per recuperare nuovamente tutte le risorse. Quando si cancella la cache, vengono mantenute le modifiche non salvate. Tutte le risorse non archiviate [!DNL Experience Manager] vengono mantenuti e non eliminati.

### Connetti a un [!DNL Experience Manager] server {#connect}

L’app supporta la configurazione proxy su Mac e Windows. La configurazione viene letta all&#39;avvio dell&#39;app. Se modifichi le impostazioni proxy, riavvia l’app per rendere effettive le modifiche.

>[!NOTE]
>
>Se modifichi le impostazioni proxy, riavvia l’app per rendere effettive le modifiche. In caso contrario, l’app continua a utilizzare il server proxy configurato in precedenza.

1. Launch [!DNL Experience Manager] app desktop. Per mappare [!DNL Experience Manager] con l’app, specifica la tua [!DNL Experience Manager] server nel formato `https://[aem-server-url]:[port]`.

   ![Autentica su Mac e fornisci [!DNL Experience Manager] URL del server](assets/aem_desktop_app_server_url.png)

1. Nella schermata di accesso, specifica il nome utente e la password per l’istanza. Per specificare un&#39;alternativa [!DNL Experience Manager] istanza, seleziona la **[!UICONTROL Alternate Login URL]** opzione.

   ![Fornire [!DNL Experience Manager] credenziali del server nella schermata di accesso [!DNL Experience Manager] app desktop](assets/login_screen_v1.png)

### Abilitare le azioni desktop in [!DNL Experience Manager] interfaccia web {#desktopactions}

Dall’interfaccia utente di Assets, puoi esplorare le posizioni delle risorse o estrarle e aprire la risorsa per la modifica nell’applicazione desktop. Queste opzioni sono denominate azioni desktop e non sono abilitate per impostazione predefinita. Per abilitarlo, segui la procedura riportata di seguito.

1. Nell’interfaccia di Assets, tocca o fai clic sull’icona Utente nell’angolo superiore destro della barra degli strumenti.
1. Clic **[!UICONTROL My Preferences]** per visualizzare **[!UICONTROL Preferences]** .

   ![[!DNL Experience Manager] Interfaccia con le preferenze dell&#39;utente](assets/aem_ui_user_preferences.png)

1. In [!UICONTROL User Preferences] finestra di dialogo, seleziona **[!UICONTROL Show Desktop Actions For Assets]**, quindi fai clic su **[!UICONTROL Accept]**.

   ![Verifica [!UICONTROL Show Desktop Actions For Assets] per abilitare le azioni sul desktop](assets/enable_desktop_actions.png)

   *Figura: Controllo [!UICONTROL Show Desktop Actions For Assets] per attivare le azioni desktop.*

## Accedere e aprire le risorse sul desktop {#openondesktop}

Quando fai clic su **Apri** per aprire una risorsa sul computer locale, l’app la scarica nella cache interna. L’app avvia l’applicazione desktop nativa associata al tipo di file della risorsa scaricata.

In Mac, seleziona **Apri** dal menu di scelta rapida per aprire una risorsa tramite [!DNL Experience Manager] app desktop. In Windows, seleziona Apri sul web dal menu di scelta rapida per aprire la risorsa. Dalla finestra Stato risorsa, tocca o fai clic su ![Icona Apri sul desktop](assets/do-not-localize/aemassets_icon_openondesktop.png) per aprire la risorsa.

Per i file Adobe InDesign (INDD), seleziona **[!UICONTROL Open]** dal menu di scelta rapida. Quando fai clic su questa opzione, l’app scarica le risorse collegate nel file system locale e quindi apre il file INDD in Adobe InDesign. Questo metodo garantisce che le risorse necessarie siano disponibili localmente quando si modifica il file INDD.

![Opzioni del menu di scelta rapida per accedere e aprire le risorse tramite [!DNL Experience Manager] app desktop](assets/aem_desktopapp_mac_context_menu.png)

*Figura: Opzioni del menu di scelta rapida per accedere e aprire le risorse tramite [!DNL Experience Manager] app desktop.*

>[!NOTE]
>
>In Windows, il [impostazione predefinita di Windows 7](https://support.microsoft.com/it-it/kb/2668751) impedisce [!DNL Experience Manager] dall&#39;app desktop per la gestione di risorse superiori a 50 MB.

<!-- TBD: The above note is for Windows 7 which is not supported by the app anymore. Remove it later.
-->

>[!NOTE]
>
>L&#39;Adobe consiglia di passare a Opzioni visualizzazione Finder su Mac e disattivare le opzioni **Mostra informazioni elemento**, **Mostra anteprima elemento**, e **Mostra colonna anteprima** per il montaggio [!DNL Assets] cartella. Migliora le prestazioni.

### Opzioni aggiuntive in [!DNL Experience Manager] Interfaccia {#additional-options-in-aem-assets}

Dopo aver mappato [!DNL Assets] nell’unità locale, puoi abilitare icone aggiuntive e visualizzare la funzione Caricamento cartella per le risorse e le cartelle mappate.

1. Apri [!DNL Assets] e posiziona il puntatore su una cartella o una risorsa, per visualizzare le azioni sul desktop come azioni rapide nella vista a schede.

   ![Nell’interfaccia utente Assets, apri il menu Azioni rapide per visualizzare le azioni sul desktop](assets/desktop_actions_in_card_view.png)

   *Figura: Nell’interfaccia utente Assets, apri il menu Azioni rapide per visualizzare le azioni sul desktop.*

   Queste azioni sul desktop sono disponibili anche quando si fa clic su **Azioni desktop** nella barra degli strumenti dopo aver selezionato la risorsa o dalla barra degli strumenti nella pagina della risorsa.

1. Per aprire la risorsa nell’applicazione desktop associata all’estensione di file specifica, fai clic sul pulsante **Apri sul desktop** azione rapida ![Icona Apri sul desktop](assets/do-not-localize/aemassets_icon_openondesktop.png).

   In alternativa, scegliete **Apri** dal **Azioni desktop** nella barra degli strumenti.

Per individuare la risorsa specifica nel file system locale, fai clic su **Mostra** azione rapida ![Icona Mostra](assets/do-not-localize/aemassets_reveal_icon.png). In alternativa, scegliete **Mostra** dal **Azioni desktop** nella barra degli strumenti.

## Comprendere gli stati delle risorse {#understand-the-asset-statuses}

| ![Icona app predefinita di Windows](assets/do-not-localize/win_default.png) | L&#39;app è connessa al server e tutte le risorse sono sincronizzate. |
--- |--- |
| ![Icona Windows disabilitato](assets/do-not-localize/win_disabled.png) | L&#39;app viene avviata ma non è connessa al server. Alcune risorse potrebbero essere in attesa di sincronizzazione. |
| ![Icona di sincronizzazione file Windows](assets/do-not-localize/win_sync.png) | Sincronizzazione delle risorse in corso. I file vengono caricati o scaricati. È possibile visualizzare gli stati esatti e sospendere i trasferimenti dalla finestra Stato cespite. |
| ![Icona riconnessione Windows](assets/do-not-localize/win_refresh.png) | L&#39;app sta tentando di riconnettersi. È possibile che i problemi di rete causino la disconnessione. |

## Lavorare sulle risorse {#workonassets}

### Estrarre risorse da [!DNL Experience Manager] interfaccia web {#check-out-assets-from-the-aem-web-interface}

[!DNL Assets] consente di estrarre le risorse da modificare e archiviarle nuovamente dopo aver completato le modifiche. Dopo aver estratto una risorsa, solo tu puoi modificarla, annotarla, pubblicarla, spostarla o eliminarla. L’estrazione di una risorsa blocca la risorsa e impedisce ad altri utenti di eseguire una di queste operazioni. Per poter estrarre/archiviare le risorse, è necessario disporre dell&#39;accesso in scrittura.

Esistono due modi per estrarre le risorse dal [!DNL Experience Manager] interfaccia web. Per informazioni dettagliate sul primo metodo, vedi [archiviare ed estrarre file dall’interfaccia utente di Assets](https://experienceleague.adobe.com/docs/experience-manager-65/assets/managing/check-out-and-submit-assets.html). Segui questi passaggi per i secondi metodi per estrarre e aprire la risorsa quando [!DNL Experience Manager] l&#39;app desktop è installata.

1. Apri [!DNL Assets] e posiziona il puntatore su una cartella o una risorsa, per visualizzare le azioni sul desktop come azioni rapide nella vista a schede.

   ![Opzione Proprietà nella vista a schede](assets/desktop_actions_in_card_view.png)

   Queste azioni sul desktop sono disponibili anche quando tocchi o fai clic sull’icona Azioni desktop nella barra degli strumenti dopo aver selezionato la risorsa o nella barra degli strumenti nella pagina della risorsa.

1. Per aprire la risorsa, tocca o fai clic sull’azione rapida Apri sul desktop ![Icona Apri sul desktop](assets/do-not-localize/aemassets_icon_openondesktop.png).

   In alternativa, scegliere Apri dal menu Azioni desktop nella barra degli strumenti.

   >[!NOTE]
   >
   >Quando si modifica un file appena aperto e non estratto, gli altri utenti non vengono a conoscenza del fatto che una risorsa è in fase di aggiornamento.

1. Per aprire una risorsa per la modifica in un’applicazione Adobe Creative Cloud, tocca o fai clic sull’azione rapida Modifica desktop ![Icona Modifica desktop](assets/do-not-localize/aemassets_icon_editdesktop.png). In questo modo viene estratta anche la risorsa per la modifica. Dopo aver completato la modifica, archivia la risorsa per aggiornare le modifiche in [!DNL Assets].

   In alternativa, scegliere Modifica dal menu Azioni desktop nella barra degli strumenti.

1. Selezionare l&#39;opzione Apri. Le risorse selezionate vengono aperte in modalità anteprima.
1. Per modificare le risorse, seleziona l’opzione Modifica. Le risorse vengono aperte in modalità di modifica.

### Estrarre risorse da Finder su Mac OS {#check-out-assets-on-mac}

L’app consente di estrarre i file di risorse per impedire ad altri utenti di modificare i file su cui stai lavorando.

1. Dal menu di scelta rapida di Mac, seleziona Apri cartella AEM Assets per aprire il Finder.

   ![Opzioni del menu di scelta rapida per accedere e aprire le risorse tramite [!DNL Experience Manager] app desktop](assets/aem_desktopapp_mac_context_menu.png)

   *Figura: Opzioni del menu di scelta rapida per accedere e aprire le risorse tramite [!DNL Experience Manager] app desktop.*

1. Passare alla risorsa da estrarre.
1. Fai clic con il pulsante destro del mouse sulla risorsa e seleziona Altre informazioni risorse dal menu di scelta rapida.
1. Nella finestra di dialogo Informazioni risorsa, tocca o fai clic sull’icona Estrai per estrarre la risorsa. L’icona Check-Out attiva l’icona Check-In dopo averla toccata o fatta clic su di essa.

   ![Sfoglia la risorsa da estrarre](assets/browse_assets_to_checkout.png)

1. Per archiviare la risorsa in modo che sia disponibile per altri utenti, tocca o fai clic sull’icona di archiviazione nella finestra di dialogo Informazioni risorsa.

### Estrarre risorse in Windows {#check-out-assets-on-windows}

L’app consente di estrarre i file di risorse per impedire ad altri utenti di modificare i file su cui stai lavorando.

1. Dal menu di scelta rapida, selezionare Esplora risorse per aprire Esplora risorse.
1. In Esplora risorse passare alla posizione della risorsa da estrarre.
1. Fai clic con il pulsante destro del mouse sulla risorsa e seleziona Apri sul web dal menu di scelta rapida.
1. Nella finestra di dialogo Informazioni risorsa, tocca o fai clic sull’icona Estrai. L&#39;icona Check-Out attiva l&#39;icona Check-In.

   ![Icona Estrai](assets/checkout_icon_toggles.png)

1. Esamina la risorsa in Explorer. Icona del lucchetto sulla risorsa ![Icona Blocco risorse](assets/do-not-localize/aemassets_icon_lockcheckout.png) indica che la risorsa è stata estratta.

   >[!NOTE]
   >
   >L’icona del lucchetto potrebbe apparire dopo un certo ritardo. [!DNL Experience Manager] L’app desktop memorizza nella cache le risorse per un accesso rapido, quindi l’aggiornamento dello stato bloccato potrebbe richiedere alcuni minuti.

1. Per archiviare la risorsa in modo che sia disponibile per altri utenti, tocca o fai clic sull’icona di archiviazione in **Info risorsa** .

### Archiviare una risorsa tramite il Finder o Esplora risorse e tramite l’interfaccia web {#check-in-an-asset-using-finder-or-explorer-and-using-web-interface}

Dopo aver modificato le risorse, salvale nell’applicazione desktop. Dal menu di scelta rapida, selezionare **Altre informazioni risorse** e fare clic su check-in.

Le risorse vengono caricate in [!DNL Experience Manager] server. Facoltativamente, puoi controllare lo stato del caricamento selezionando **Visualizza stato risorsa** dall&#39;icona della barra delle applicazioni. In alternativa, è possibile archiviare una risorsa da [!DNL Experience Manager] interfaccia web. Fai clic sulle risorse estratte o selezionale. Dalla barra degli strumenti, fai clic sull’icona Archivia ![icona check-in](assets/do-not-localize/aemassets_icon_checkin.png).

Una risorsa viene caricata in [!DNL Experience Manager] automaticamente dopo il salvataggio locale di eventuali modifiche. L&#39;archiviazione rende la risorsa disponibile ad altri [!DNL Experience Manager] utenti per la modifica.

### Caricare risorse e cartelle in blocco in [!DNL Experience Manager] server {#bulkupload}

Utilizzo di [!DNL Experience Manager] nell’app desktop, puoi caricare un’intera cartella contenente risorse dalla directory dei file locale in [!DNL Assets]. In questo modo, tutte le risorse all’interno della cartella vengono caricate in blocco invece di doverle caricare una alla volta.

1. Dall’interfaccia utente Assets, tocca o fai clic su **Crea** dalla barra degli strumenti e scegli **Carica cartella** dal menu.
1. Individua la cartella da caricare e selezionala.
1. Tocca o fai clic su OK. La finestra di dialogo Stato risorse visualizza lo stato del caricamento.

   ![Visualizzare lo stato del caricamento nella finestra Stato risorsa](assets/aem_desktopapp_bulkupload_status.png)

   Visualizzare lo stato del caricamento nella finestra Stato risorsa

   >[!NOTE]
   >
   >Puoi mettere in pausa o annullare manualmente il caricamento toccando o facendo clic sull’icona appropriata.

1. Dopo il caricamento della cartella, chiudi la finestra di dialogo e passa all’interfaccia utente Assets. La cartella caricata viene visualizzata nell’interfaccia web.

L&#39;Adobe non consiglia di copiare e incollare o trascinare un numero maggiore di file o cartelle nidificate dal file system locale nell&#39;area di condivisione di rete. L’app non è in grado di controllare il processo di caricamento a causa di limitazioni tecniche e prestazioni insoddisfacenti.

In alternativa, seleziona i file o le cartelle da caricare su [!DNL Experience Manager] in Finder o Explorer, copiarli negli Appunti di sistema, passare alla cartella di destinazione nell&#39;area di condivisione di rete e da [!DNL Experience Manager] selezione del menu di scelta rapida dell’app desktop **Incolla risorse**. Da questa parte, [!DNL Experience Manager] L’app desktop inizia a caricare le risorse incollate in modo simile al **Carica cartella** opzione disponibile in [!DNL Experience Manager] interfaccia web.

>[!MORELIKETHIS]
>
>* [Risoluzione dei problemi [!DNL Experience Manager] applicazione app desktop](troubleshoot-app-v1.md)

