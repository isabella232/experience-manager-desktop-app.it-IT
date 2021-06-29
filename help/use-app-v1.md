---
title: Utilizza la versione 1.10 dell’app desktop  [!DNL Experience Manager] it.
description: Scopri come utilizzare l’app desktop Adobe Experience Manager versione 1.10 e ottimizzare il lavoro con le risorse sul desktop.
feature: App desktop,Gestione risorse
exl-id: 2fdc1c8d-b822-4cca-ad06-bd875a00aa6d
source-git-commit: dcd29d0bbb32004d970d334c256e659f4a4c39e1
workflow-type: tm+mt
source-wordcount: '2371'
ht-degree: 0%

---

# Utilizzare l’ app desktop [!DNL Experience Manager] v1.10 {#use-aem-desktop-app-v1x}

Utilizzando l’app, le risorse incluse in [!DNL Experience Manager] sono facilmente accessibili sul desktop locale e possono essere utilizzate in qualsiasi applicazione desktop. Le risorse possono essere facilmente rivelate in Mac Finder o Windows Explorer, aperte nelle applicazioni desktop e modificate localmente - le modifiche vengono salvate in [!DNL Experience Manager] con una nuova versione creata nell’archivio.

Questa integrazione consente a diversi ruoli dell’organizzazione di gestire le risorse centralmente in Assets e di accedervi nella Creative Cloud e in altre applicazioni, semplificando al contempo il rispetto dei vari standard, tra cui il branding.

Le attività chiave che esegui utilizzando l’ [!DNL Experience Manager] app desktop v1 includono:

1. [Connettersi a un server [!DNL Experience Manager] ](#installandconnect)
1. [Apri le risorse direttamente sul desktop](#openondesktop)
1. [Modifica ed estrazione delle risorse dal desktop](#workonassets)
1. [Caricare in massa risorse e cartelle](#bulkupload)

Per le varie operazioni e operazioni non consigliate, consulta le [best practice per l’utilizzo di app](best-practices-for-v1.md). Se riscontri dei problemi durante l&#39;utilizzo dell&#39;app, scopri come risolvere i problemi [desktop [!DNL Experience Manager] a2/>.](troubleshoot-app-v1.md)

>[!NOTE]
>
>L’app desktop è stata introdotta nella versione 6.1 di [!DNL Experience Manager] ed è stata chiamata [!DNL Experience Manager Assets Companion App].

## [!DNL Experience Manager] punti di contatto dell’app desktop nel flusso di lavoro creativo {#aem-desktop-app-touch-points-in-the-creative-workflow}

[!DNL Experience Manager] l’app desktop si integra nel flusso di lavoro creativo e offre i seguenti punti di contatto.  [!DNL Assets]

![[!DNL Experience Manager] touch-point dell’app desktop nel flusso di lavoro creativo](assets/aem_desktopapp_workflow.png)

[!DNL Experience Manager] touch-point dell’app desktop nel flusso di lavoro creativo

## Installa e connetti l’app al server [!DNL Experience Manager] {#installandconnect}

Prima di poter iniziare a creare o modificare le risorse creative, connetti l’applicazione desktop al server [!DNL Assets] per scaricare e caricare le risorse nell’archivio. Esegui le seguenti operazioni:

1. [Installa l&#39;app](#installapp).
1. [Imposta le ](#inapppref) preferenze e i dettagli di connessione.
1. [Connettiti al  [!DNL Experience Manager] ](#connect) server di trasferimento e monta l&#39;archivio delle risorse come unità locale.
1. [Abilita le ](#desktopactions) azioni desktop sul  [!DNL Experience Manager] server.

[!DNL Experience Manager] l’app desktop utilizza una connessione HTTPS per connettersi al  [!DNL Experience Manager] server e trasferire le risorse in modo sicuro e affidabile.

>[!NOTE]
>
>Per parte o per tutti i passaggi di installazione e configurazione, potrebbe essere necessario assistenza da parte dell’ amministratore [!DNL Experience Manager] o dell’amministratore di sistema.

### Installare l’applicazione {#installapp}

Per utilizzare l’app desktop [!DNL Experience Manager], assicurati che la versione del server [!DNL Experience Manager] sia supportata dall’app. Scarica il file di installazione appropriato (binario) per il tuo sistema operativo (Mac o Windows) e installa l&#39;app.

La configurazione dettagliata può essere necessaria a seconda delle preferenze di rete e di sistema. Per ulteriori informazioni, consulta [Installare e configurare [!DNL Experience Manager] l’app desktop](install-configure-app-v1.md) .

1. Vai alla [[!DNL Experience Manager] pagina di download dell&#39;app desktop v1.10](/help/release-notes-of-v1.md) e scarica il binario appropriato per il tuo sistema operativo.
1. Avvia il file di installazione scaricato e segui le istruzioni visualizzate per installare l’app.

   >[!NOTE]
   >
   >È possibile installare e attivare una sola istanza dell’ app desktop [!DNL Experience Manager] alla volta.

### Comprendere le opzioni e le preferenze in-app {#inapppref}

L&#39;applicazione consente alle impostazioni di connettersi e disconnettersi dai server [!DNL Experience Manager], visualizzare lo stato dei caricamenti, gestire la cache locale e così via. Le impostazioni predefinite funzionano per un utente tipico dell&#39;applicazione. Puoi modificare le impostazioni per ottenere di più dall’applicazione e dall’integrazione con il server [!DNL Experience Manager] . Le varie impostazioni sono descritte di seguito nei dettagli.

**Esplora** risorseApri l&#39;unità locale in cui è montato l&#39; [!DNL Assets] archivio. In altre parole, esplora le risorse che sono ora disponibili nel computer locale.

**Visualizza** lo stato della risorsaQuando le risorse modificate vengono caricate o aggiunte nuove risorse all’ [!DNL Assets] archivio, l’applicazione carica le risorse in background. Il caricamento in background consente operazioni fluide, senza dover attendere il completamento del caricamento, soprattutto per le risorse di grandi dimensioni. Puoi salvare le modifiche localmente e dimenticarle. L&#39;invio di queste risorse al server richiede un po&#39; di tempo, a seconda della larghezza di banda disponibile. Puoi controllare lo stato del caricamento, insieme ad alcune informazioni di base.

**** OpzioniFai clic su opzioni nella barra delle applicazioni desktop per accedere alle impostazioni per avviare l’applicazione all’avvio del sistema; per connettersi al  [!DNL Experience Manager] server all’avvio dell’app; e modificare la lettera di unità locale, se  [!DNL Assets] disponibile dopo il montaggio.

**Avanzate > Gestione** cachePuoi controllare la quantità di spazio su disco disponibile a scopo di caching locale. Gli artefatti del server [!DNL Assets] vengono memorizzati nella cache locale per un’esperienza più fluida. È possibile modificare le impostazioni predefinite in base alle proprie esigenze. Inoltre, puoi svuotare la cache per recuperare nuovamente tutte le risorse. Quando si svuota la cache, vengono mantenute le modifiche non salvate. Tutte le risorse non archiviate nel server [!DNL Experience Manager] vengono mantenute e non eliminate.

### Connettersi a un server [!DNL Experience Manager] {#connect}

L’app supporta la configurazione proxy su Mac e Windows. La configurazione viene letta all&#39;avvio dell&#39;app. Se modifichi le impostazioni proxy, riavvia l&#39;app per rendere effettive le modifiche.

>[!NOTE]
>
>Se modifichi le impostazioni proxy, riavvia l’app per rendere effettive le modifiche. In caso contrario, l&#39;app continua a utilizzare il server proxy configurato in precedenza.

1. Avvia l&#39;app desktop [!DNL Experience Manager]. Per mappare l&#39;istanza [!DNL Experience Manager] con l&#39;app, specifica il server [!DNL Experience Manager] nel formato `https://[aem-server-url]:[port]`.

   ![Autentica su Mac e fornisci l’URL  [!DNL Experience Manager] del server](assets/aem_desktop_app_server_url.png)

1. Nella schermata di accesso, specifica il nome utente e la password per l’istanza. Per specificare un&#39;istanza alternativa [!DNL Experience Manager], selezionare l&#39;opzione **[!UICONTROL Alternate Login URL]**.

   ![Fornire le credenziali  [!DNL Experience Manager] del server nella schermata di accesso nell’app  [!DNL Experience Manager] desktop](assets/login_screen_v1.png)

### Abilitare le azioni desktop nell’interfaccia web [!DNL Experience Manager] {#desktopactions}

Dall’interfaccia utente di Assets, puoi esplorare le posizioni delle risorse o estrarre e aprire la risorsa per la modifica nell’applicazione desktop. Queste opzioni sono denominate azioni desktop e non sono abilitate per impostazione predefinita. Segui questi passaggi per abilitarlo.

1. Nell’interfaccia di Assets, tocca o fai clic sull’icona Utente nell’angolo in alto a destra della barra degli strumenti.
1. Fare clic su **[!UICONTROL My Preferences]** per visualizzare la finestra di dialogo **[!UICONTROL Preferences]**.

   ![[!DNL Experience Manager] interfaccia con preferenze utente](assets/aem_ui_user_preferences.png)

1. Nella finestra di dialogo [!UICONTROL User Preferences], seleziona **[!UICONTROL Show Desktop Actions For Assets]**, quindi fai clic su **[!UICONTROL Accept]**.

   ![Seleziona  [!UICONTROL Show Desktop Actions For Assets] per abilitare le azioni desktop](assets/enable_desktop_actions.png)

   *Figura: Seleziona  [!UICONTROL Show Desktop Actions For Assets] per abilitare le azioni desktop.*

## Accedere e aprire le risorse sul desktop {#openondesktop}

Quando fai clic su **Apri** per aprire una risorsa sul computer locale, l’app scarica la risorsa nella relativa cache interna. L’app avvia l’applicazione desktop nativa associata al tipo di file della risorsa scaricata.

In Mac, seleziona **Apri** dal menu di scelta rapida per aprire una risorsa tramite l’ app desktop [!DNL Experience Manager]. In Windows, seleziona Apri sul Web dal menu di scelta rapida per aprire la risorsa. Dalla finestra Stato risorsa, tocca o fai clic su ![Apri su icona Desktop](assets/do-not-localize/aemassets_icon_openondesktop.png) per aprire la risorsa.

Per i file Adobe InDesign (INDD), seleziona **[!UICONTROL Open]** dal menu di scelta rapida. Quando fai clic su questa opzione, l’app scarica le risorse collegate nel file system locale e quindi apre il file INDD in Adobe InDesign. Questo metodo assicura che le risorse necessarie siano disponibili localmente durante la modifica del file INDD.

![Opzioni del menu di scelta rapida per accedere e aprire le risorse utilizzando l’app  [!DNL Experience Manager] desktop](assets/aem_desktopapp_mac_context_menu.png)

*Figura: Opzioni del menu di scelta rapida per accedere e aprire le risorse utilizzando l’app  [!DNL Experience Manager] desktop.*

>[!NOTE]
>
>In Windows, l’ [impostazione predefinita di Windows 7](https://support.microsoft.com/it-it/kb/2668751) impedisce all’ app desktop [!DNL Experience Manager] di gestire risorse di dimensioni superiori a 50 MB.

<!-- TBD: The above note is for Windows 7 which is not supported by the app anymore. Remove it later.
-->

>[!NOTE]
>
>L&#39;Adobe consiglia di passare a Opzioni visualizzazione Finder su Mac e disattivare le opzioni **Mostra informazioni elemento**, **Mostra anteprima elemento** e **Mostra colonna anteprima** per la cartella montata [!DNL Assets]. Migliora le prestazioni.

### Opzioni aggiuntive nell’interfaccia [!DNL Experience Manager] {#additional-options-in-aem-assets}

Dopo aver mappato l’archivio [!DNL Assets] nell’unità locale, puoi abilitare icone aggiuntive e la funzione Caricamento cartelle per visualizzare le risorse e le cartelle mappate.

1. Apri l’interfaccia [!DNL Assets] e passa il puntatore su una cartella o su una risorsa per visualizzare le azioni desktop come azioni rapide nella vista a schede.

   ![Nell’interfaccia utente Assets, apri il menu Azioni rapide per visualizzare le azioni desktop](assets/desktop_actions_in_card_view.png)

   *Figura: Nell’interfaccia utente Assets, apri il menu Azioni rapide per visualizzare le azioni desktop.*

   Queste azioni desktop sono disponibili anche quando fai clic sull’opzione **Azioni desktop** nella barra degli strumenti dopo aver selezionato la risorsa o dalla barra degli strumenti nella pagina delle risorse.

1. Per aprire la risorsa nell’applicazione desktop associata all’estensione di file specifica, fai clic sull’ **Apri sul desktop** azione rapida ![Apri sull’icona Desktop](assets/do-not-localize/aemassets_icon_openondesktop.png).

   In alternativa, scegli **Apri** dal menu **Azioni desktop** nella barra degli strumenti.

Per individuare la risorsa specifica nel file system locale, fai clic su **Mostra** azione rapida ![Mostra icona](assets/do-not-localize/aemassets_reveal_icon.png). In alternativa, scegli **Mostra** dal menu **Azioni desktop** nella barra degli strumenti.

## Comprendere gli stati delle risorse {#understand-the-asset-statuses}

| ![Icona app predefinita di Windows](assets/do-not-localize/win_default.png) | L’app è connessa al server e tutte le risorse sono sincronizzate. |
--- |--- |
| ![Icona disattivata di Windows](assets/do-not-localize/win_disabled.png) | L’app viene avviata ma non è connessa al server. Alcune risorse potrebbero essere in attesa di sincronizzazione. |
| ![Icona di sincronizzazione file Windows](assets/do-not-localize/win_sync.png) | Le risorse vengono sincronizzate. I file vengono caricati o scaricati. È possibile visualizzare gli stati esatti e sospendere i trasferimenti dalla finestra Stato risorsa. |
| ![Icona di riconnessione di Windows](assets/do-not-localize/win_refresh.png) | L&#39;app sta tentando di riconnettersi. Potenzialmente i problemi di rete lo stanno causando la disconnessione. |

## Utilizzare le risorse {#workonassets}

### Estrarre risorse dall’interfaccia web [!DNL Experience Manager] {#check-out-assets-from-the-aem-web-interface}

[!DNL Assets] consente di estrarre le risorse da modificare e di archiviarle nuovamente dopo aver completato le modifiche. Dopo aver estratto una risorsa, puoi modificarla, annotarla, pubblicarla, spostarla o eliminarla. L’estrazione di una risorsa blocca la risorsa e impedisce ad altri utenti di eseguire una di queste operazioni. Per poter estrarre/inserire le risorse, è necessario disporre dell’accesso in scrittura.

Esistono due modi per estrarre le risorse dall’interfaccia web [!DNL Experience Manager]. Per informazioni dettagliate sul primo metodo, consulta [archiviazione e estrazione di file dall’interfaccia utente di Assets](https://experienceleague.adobe.com/docs/experience-manager-65/assets/managing/check-out-and-submit-assets.html). Segui questi passaggi, per i secondi metodi per estrarre e aprire la risorsa quando è installata l’ [!DNL Experience Manager] app desktop.

1. Apri l’interfaccia [!DNL Assets] e passa il puntatore su una cartella o su una risorsa per visualizzare le azioni desktop come azioni rapide nella vista a schede.

   ![Opzione Proprietà nella vista a schede](assets/desktop_actions_in_card_view.png)

   Queste azioni desktop sono disponibili anche quando fai clic o tocca l’icona Azioni desktop nella barra degli strumenti dopo aver selezionato la risorsa o dalla barra degli strumenti nella pagina delle risorse.

1. Per aprire la risorsa, tocca o fai clic sull’azione rapida Apri sul desktop ![Apri sull’icona Desktop](assets/do-not-localize/aemassets_icon_openondesktop.png).

   In alternativa, scegli Apri dal menu Azioni desktop nella barra degli strumenti.

   >[!NOTE]
   >
   >Quando modifichi un file appena aperto e non estratto, gli altri utenti non sanno che una risorsa viene aggiornata dall’utente.

1. Per aprire una risorsa da modificare in un’applicazione Adobe Creative Cloud, tocca o fai clic sull’azione rapida Modifica desktop ![icona Modifica desktop](assets/do-not-localize/aemassets_icon_editdesktop.png). Consente inoltre di estrarre la risorsa per la modifica. Dopo aver completato la modifica, archivia la risorsa per aggiornare le modifiche in [!DNL Assets].

   In alternativa, scegli Modifica dal menu Azioni desktop nella barra degli strumenti.

1. Selezionare l’opzione del menu Apri. Le risorse selezionate vengono aperte in modalità anteprima.
1. Per modificare le risorse, seleziona l’opzione Modifica . Le risorse vengono aperte in modalità di modifica.

### Consulta le risorse dal Finder su Mac OS {#check-out-assets-on-mac}

L’app ti consente di estrarre i file di risorse per impedire ad altri utenti di modificare i file su cui stai lavorando.

1. Dal menu di scelta rapida Mac, seleziona Apri cartella AEM Assets per aprire Finder.

   ![Opzioni del menu di scelta rapida per accedere e aprire le risorse utilizzando l’app  [!DNL Experience Manager] desktop](assets/aem_desktopapp_mac_context_menu.png)

   *Figura: Opzioni del menu di scelta rapida per accedere e aprire le risorse utilizzando l’app  [!DNL Experience Manager] desktop.*

1. Passa alla risorsa da estrarre.
1. Fai clic con il pulsante destro del mouse sulla risorsa e seleziona Ulteriori informazioni risorse dal menu di scelta rapida.
1. Nella finestra di dialogo Informazioni risorsa, tocca o fai clic sull’icona Checkout per estrarre la risorsa. L’icona Checkout passa all’icona di check-in dopo averla selezionata o toccata.

   ![Passa alla risorsa da estrarre](assets/browse_assets_to_checkout.png)

1. Per archiviare la risorsa in modo che sia disponibile per altri utenti, tocca o fai clic sull’icona di accesso nella finestra di dialogo Informazioni risorsa .

### Estrai risorse in Windows {#check-out-assets-on-windows}

L’app ti consente di estrarre i file di risorse per impedire ad altri utenti di modificare i file su cui stai lavorando.

1. Dal menu di scelta rapida, seleziona Esplora risorse per aprire Esplora risorse.
1. In Esplora risorse, individua il percorso della risorsa da estrarre.
1. Fai clic con il pulsante destro del mouse sulla risorsa e seleziona Apri sul Web dal menu di scelta rapida.
1. Nella finestra di dialogo Informazioni risorsa, tocca o fai clic sull’icona Checkout . L’icona Checkout passa all’icona di check-in.

   ![Icona di pagamento](assets/checkout_icon_toggles.png)

1. Esamina la risorsa in Esplora risorse. L’icona a forma di lucchetto sulla risorsa ![Icona a forma di lucchetto risorse](assets/do-not-localize/aemassets_icon_lockcheckout.png) indica che la risorsa è stata estratta.

   >[!NOTE]
   >
   >L&#39;icona Blocca potrebbe apparire dopo qualche ritardo. [!DNL Experience Manager] l’app desktop memorizza in cache le risorse per l’accesso rapido, in modo che lo stato bloccato possa richiedere alcuni istanti.

1. Per archiviare la risorsa in modo che sia disponibile agli altri utenti, tocca o fai clic sull’icona di accesso nella finestra di dialogo **Informazioni risorsa** .

### Archiviare una risorsa utilizzando il Finder o Esplora risorse e utilizzando l&#39;interfaccia Web {#check-in-an-asset-using-finder-or-explorer-and-using-web-interface}

Una volta completata la modifica delle risorse, salva le risorse nell’applicazione desktop. Dal menu di scelta rapida, seleziona **Ulteriori informazioni sulle risorse** e fai clic su Archivia.

Le risorse vengono caricate sul server [!DNL Experience Manager] . Facoltativamente, puoi controllare lo stato del caricamento selezionando **Visualizza stato risorsa** dall&#39;icona della barra delle applicazioni. In alternativa, puoi archiviare una risorsa dall’ interfaccia web [!DNL Experience Manager] . Fai clic sulle risorse estratte o selezionale. Dalla barra degli strumenti, fai clic sull&#39;icona di archiviazione ![icona di archiviazione](assets/do-not-localize/aemassets_icon_checkin.png).

Una risorsa viene caricata in [!DNL Experience Manager] automaticamente dopo che eventuali modifiche vengono salvate localmente. Il check-in rende la risorsa disponibile per la modifica ad altri utenti [!DNL Experience Manager].

### Caricamento in blocco di risorse e cartelle sul server [!DNL Experience Manager] {#bulkupload}

Utilizzando l’ app desktop [!DNL Experience Manager], puoi caricare su [!DNL Assets] un’intera cartella contenente risorse dalla directory dei file locali. In questo modo, tutte le risorse all’interno della cartella vengono caricate in blocco invece di doverle caricare una alla volta.

1. Dall’interfaccia utente Assets, tocca o fai clic su **Crea** nella barra degli strumenti, quindi scegli **Carica cartella** dal menu.
1. Individua la cartella da caricare e selezionala.
1. Tocca o fai clic su OK. Nella finestra di dialogo Stato risorse viene visualizzato lo stato del caricamento.

   ![Vedi lo stato del caricamento nella finestra Stato risorsa](assets/aem_desktopapp_bulkupload_status.png)

   Vedi lo stato del caricamento nella finestra Stato risorsa

   >[!NOTE]
   >
   >Per interrompere o annullare manualmente il caricamento, tocca o fai clic sull’icona appropriata.

1. Dopo il caricamento della cartella, chiudi la finestra di dialogo e passa all’interfaccia utente Assets. La cartella caricata viene visualizzata nell’interfaccia Web.

Adobe sconsiglia di copiare-incollare o trascinare un numero maggiore di file o cartelle nidificate dal file system locale nell&#39;area di condivisione di rete. L’app non può controllare il processo di caricamento a causa di limitazioni tecniche e prestazioni scadenti.

In alternativa, seleziona i file/le cartelle da caricare in [!DNL Experience Manager] nel Finder o in Esplora risorse, copiali negli Appunti di sistema, individua la cartella di destinazione nell&#39;area di condivisione di rete e, dal menu di scelta rapida dell&#39;app desktop [!DNL Experience Manager] seleziona **Incolla risorse**. In questo modo, l’ [!DNL Experience Manager] app desktop inizia a caricare le risorse incollate in modo simile all’opzione **Carica cartella** disponibile nell’ interfaccia web [!DNL Experience Manager] .

>[!MORELIKETHIS]
>
>* [Risolvere i problemi relativi all&#39;applicazione desktop [!DNL Experience Manager] ](troubleshoot-app-v1.md)

