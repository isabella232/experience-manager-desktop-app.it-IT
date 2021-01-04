---
title: Utilizza l'app desktop versione 1.x [!DNL Experience Manager] a.
description: Scoprite come utilizzare l’app desktop Adobe Experience Manager versione 1.x e ottimizzare il lavoro con le risorse sul desktop.
translation-type: tm+mt
source-git-commit: a25c1fa13895ae9eb7268e3e01c83a5f0b9d7d1d
workflow-type: tm+mt
source-wordcount: '2379'
ht-degree: 0%

---


# Utilizzare l&#39;app desktop [!DNL Experience Manager] v1.x {#use-aem-desktop-app-v1x}

Utilizzando l&#39;app, le risorse all&#39;interno di [!DNL Experience Manager] sono facilmente accessibili sul desktop locale e possono essere utilizzate in qualsiasi applicazione desktop. Le risorse possono essere rivelate facilmente in Mac Finder o Windows Explorer, aperte nelle applicazioni desktop e modificate localmente - le modifiche vengono salvate in [!DNL Experience Manager] con una nuova versione creata nell&#39;archivio.

Questa integrazione consente a diversi ruoli dell’organizzazione di gestire le risorse centralmente in Risorse e di accedervi nella Creative Cloud e in altre applicazioni, semplificando al contempo il rispetto dei vari standard, tra cui il branding.

Le attività chiave che eseguite con l&#39;app desktop [!DNL Experience Manager] v1 includono:

1. [Connessione con  [!DNL Experience Manager] un server](#installandconnect)
1. [Aprire le risorse direttamente sul desktop](#openondesktop)
1. [Modificare e estrarre le risorse dal desktop](#workonassets)
1. [Caricare le risorse e le cartelle in blocco](#bulkupload)

Per le varie operazioni e operazioni non consigliate, consultate le [best practice per l&#39;utilizzo di app](best-practices-for-v1.md). Se si verificano dei problemi utilizzando l&#39;app, vedere come [risolvere i problemi [!DNL Experience Manager] desktop](troubleshoot-app-v1.md).

>[!NOTE]
>
>[!DNL Experience Manager] l&#39;app desktop è stata introdotta nella versione  [!DNL Experience Manager] 6.1 ed è stata chiamata  [!DNL Experience Manager Assets Companion App].

## [!DNL Experience Manager] punti di contatto dell’app desktop nel flusso di lavoro creativo  {#aem-desktop-app-touch-points-in-the-creative-workflow}

[!DNL Experience Manager] l’app desktop  [!DNL Assets]si integra nel flusso di lavoro creativo e offre i seguenti punti di contatto.

![[!DNL Experience Manager] touch point dell’app desktop per il flusso di lavoro creativo](assets/aem_desktopapp_workflow.png)

[!DNL Experience Manager] touch point dell’app desktop per il flusso di lavoro creativo

## Installare e collegare l&#39;app al server [!DNL Experience Manager] {#installandconnect}

Prima di iniziare a creare o modificare le risorse creative, collegate l’applicazione desktop al server [!DNL Assets] per scaricare e caricare le risorse nell’archivio. Effettuare le seguenti operazioni:

1. [Installate l&#39;app](#installapp).
1. [Impostare le ](#inapppref) preferenze e i dettagli di connessione.
1. [Connettiti per  [!DNL Experience Manager] ](#connect) trasferire e montare il repository delle risorse come unità locale.
1. [Abilita ](#desktopactions) azioni desktop sul  [!DNL Experience Manager] server.

[!DNL Experience Manager] l&#39;app desktop utilizza una connessione HTTPS per connettersi al  [!DNL Experience Manager] server e trasferire in modo sicuro e affidabile le risorse.

>[!NOTE]
>
>Per tutti o parte dei passaggi di installazione e configurazione, può essere necessario assistenza dall&#39;amministratore [!DNL Experience Manager] o dall&#39;amministratore di sistema.

### Installare l&#39;applicazione {#installapp}

Per utilizzare l&#39;app desktop [!DNL Experience Manager], accertati che la versione del server [!DNL Experience Manager] sia supportata dall&#39;app. Scaricate il file di installazione appropriato (binario) per il sistema operativo in uso (Mac o Windows) e installate l&#39;app.

La configurazione dettagliata può essere necessaria a seconda delle preferenze di rete e di sistema. Per ulteriori informazioni, vedere [Installazione e configurazione [!DNL Experience Manager] app desktop](install-configure-app-v1.md).

1. Andate alla [[!DNL Experience Manager] pagina di download dell&#39;app desktop](https://helpx.adobe.com/experience-manager/kb/download-companion-app.html) e scaricate il binario appropriato per il sistema operativo in uso.
1. Avviate il file di installazione scaricato e seguite le istruzioni visualizzate per installare l&#39;app.

   >[!NOTE]
   >
   >È possibile installare e attivare una sola istanza dell&#39;app desktop [!DNL Experience Manager] alla volta.

### Informazioni sulle opzioni e preferenze in-app {#inapppref}

L&#39;applicazione consente la connessione e la disconnessione delle impostazioni dai server [!DNL Experience Manager], la visualizzazione dello stato dei caricamenti, la gestione della cache locale e così via. Le impostazioni predefinite funzionano per un utente tipico dell’applicazione. Potete modificare le impostazioni per ottenere di più dall&#39;applicazione e dall&#39;integrazione con il server [!DNL Experience Manager]. Le varie impostazioni sono descritte di seguito.

**Esplora** risorseApri l’unità locale in cui è installato il  [!DNL Assets] repository. In altre parole, esplorate le risorse ora disponibili nel computer locale.

**Visualizzazione** dello stato della risorsaQuando vengono caricate risorse modificate o vengono aggiunte nuove risorse alla  [!DNL Assets] directory archivio, l’applicazione carica le risorse in background. Il caricamento in background consente di effettuare operazioni senza dover attendere il completamento del caricamento, in particolare per le risorse di grandi dimensioni. È possibile salvare le modifiche localmente e dimenticarle. L’invio di queste risorse al server da parte dell’applicazione richiede del tempo, a seconda della larghezza di banda disponibile. Potete controllare lo stato del caricamento, insieme ad alcune informazioni di base.

**** OpzioniFare clic sulle opzioni dalla barra delle applicazioni desktop per accedere alle impostazioni per avviare l&#39;applicazione all&#39;avvio del sistema; per connettersi al  [!DNL Experience Manager] server quando l&#39;app viene avviata; e per cambiare la lettera di unità locale, dove  [!DNL Assets] è disponibile dopo il montaggio.

**Avanzate > Gestione** cacheÈ possibile controllare la quantità di spazio su disco disponibile per il caching locale. Gli artefatti del server [!DNL Assets] vengono memorizzati nella cache locale per un&#39;esperienza più fluida. Potete modificare le impostazioni predefinite in base alle vostre esigenze. Inoltre, potete cancellare la cache per recuperare nuovamente tutte le risorse. Quando si cancella la cache, vengono mantenute le modifiche non salvate. Tutte le risorse non archiviate nel server [!DNL Experience Manager] vengono mantenute e non eliminate.

### Connettersi a un server [!DNL Experience Manager] {#connect}

L&#39;app supporta la configurazione proxy su Mac e Windows. La configurazione viene letta all&#39;avvio dell&#39;app. Se modificate le impostazioni proxy, riavviate l&#39;app per rendere effettive le modifiche.

>[!NOTE]
>
>Se modificate le impostazioni proxy, riavviate l&#39;app per rendere effettive le modifiche. In caso contrario, l&#39;app continua a utilizzare il server proxy configurato in precedenza.

1. Avviate l&#39;app desktop [!DNL Experience Manager]. Per mappare l&#39;istanza [!DNL Experience Manager] con l&#39;app, specifica il server [!DNL Experience Manager] nel formato `https://[aem-server-url]:[port]`.

   ![Eseguire l&#39;autenticazione in Mac OS e fornire l&#39;URL  [!DNL Experience Manager] del server](assets/aem_desktop_app_server_url.png)

1. Nella schermata di login, specificate il nome utente e la password dell’istanza. Per specificare un&#39;istanza [!DNL Experience Manager] alternativa, selezionare l&#39;opzione **[!UICONTROL Alternate Login URL]**.

   ![Fornire le credenziali  [!DNL Experience Manager] del server nella schermata di accesso nell&#39;app  [!DNL Experience Manager] desktop](assets/login_screen_v1.png)

### Abilitare le azioni desktop nell&#39;interfaccia Web [!DNL Experience Manager]{#desktopactions}

Dall’interfaccia utente di Risorse, puoi esplorare le posizioni delle risorse o estrarne e aprire la risorsa per la modifica nell’applicazione desktop. Queste opzioni sono denominate azioni desktop e non sono abilitate per impostazione predefinita. Per attivarla, effettuate le seguenti operazioni.

1. Nell’interfaccia Risorse, tocca o fai clic sull’icona Utente nell’angolo in alto a destra della barra degli strumenti.
1. Fare clic su **[!UICONTROL My Preferences]** per visualizzare la finestra di dialogo **[!UICONTROL Preferences]**.

   ![[!DNL Experience Manager] interfaccia con preferenze utente](assets/aem_ui_user_preferences.png)

1. Nella finestra di dialogo Preferenze utente, selezionate **[!UICONTROL Show Desktop Actions For Assets]**. Clic **[!UICONTROL Accept]**.

   ![Controlla  [!UICONTROL Show Desktop Actions For Assets] per abilitare le azioni desktop](assets/enable_desktop_actions.png)

   *Figura: Per attivare le azioni desktop, selezionate Mostra azioni desktop per risorse.*

## Accesso e apertura di risorse sul desktop {#openondesktop}

Quando fate clic su **Apri** per aprire una risorsa sul computer locale, l&#39;app scarica la risorsa nella cache interna. L&#39;app avvia l&#39;applicazione desktop nativa associata al tipo di file della risorsa scaricata.

In Mac, selezionate **Apri** dal menu di scelta rapida per aprire una risorsa tramite l&#39;app desktop [!DNL Experience Manager]. In Windows, selezionate Apri sul Web dal menu di scelta rapida per aprire la risorsa. Dalla finestra Stato risorsa, toccate o fate clic su ![Apri sull&#39;icona Desktop](assets/do-not-localize/aemassets_icon_openondesktop.png) per aprire la risorsa.

Per  file Adobe InDesign (INDD), selezionate **[!UICONTROL Open]** dal menu di scelta rapida. Quando fate clic su questa opzione, l&#39;app scarica le risorse collegate nel file system locale e quindi apre il file INDD in  Adobe InDesign. Questo metodo garantisce che le risorse necessarie siano disponibili localmente quando si modifica il file INDD.

![Opzioni del menu di scelta rapida per accedere e aprire le risorse tramite l’app  [!DNL Experience Manager] desktop](assets/aem_desktopapp_mac_context_menu.png)

*Figura: Opzioni del menu di scelta rapida per accedere e aprire le risorse tramite l’app  [!DNL Experience Manager] desktop.*

>[!NOTE]
>
>In Windows, l&#39;impostazione [predefinita di Windows 7](https://support.microsoft.com/en-us/kb/2668751) impedisce all&#39;app desktop [!DNL Experience Manager] di gestire risorse superiori a 50 MB.

>[!NOTE]
>
> Adobe consiglia di passare a Opzioni vista Finder su Mac e disattivare le opzioni **Mostra informazioni elemento**, **Mostra anteprima elemento** e **Mostra colonna anteprima** per la cartella [!DNL Assets] montata. Migliora le prestazioni.

### Opzioni aggiuntive nell&#39;interfaccia [!DNL Experience Manager] {#additional-options-in-aem-assets}

Dopo aver mappato l&#39;archivio [!DNL Assets] sull&#39;unità locale, potete attivare icone aggiuntive e visualizzare la funzione di caricamento delle cartelle per le risorse e le cartelle mappate.

1. Aprite l&#39;interfaccia [!DNL Assets] e passate il puntatore del mouse su una cartella o una risorsa, per visualizzare le azioni desktop come azioni rapide nella vista a schede.

   ![Nell’interfaccia utente Risorse, apri il menu Azioni rapide per visualizzare le azioni desktop](assets/desktop_actions_in_card_view.png)

   *Figura: Nell’interfaccia utente Risorse, aprite il menu Azioni rapide per visualizzare le azioni desktop.*

   Queste azioni desktop sono disponibili anche quando fate clic sull&#39;opzione **Azioni desktop** nella barra degli strumenti dopo aver selezionato la risorsa o dalla barra degli strumenti nella pagina della risorsa.

1. Per aprire la risorsa nell&#39;applicazione desktop associata all&#39;estensione di file specifica, fate clic sull&#39; **Apri sul desktop** azione rapida ![Apri sull&#39;icona del desktop](assets/do-not-localize/aemassets_icon_openondesktop.png).

   In alternativa, scegliere **Apri** dal menu **Azioni desktop** nella barra degli strumenti.

Per individuare la risorsa specifica nel file system locale, fare clic su **Mostra** azione rapida ![Mostra icona](assets/do-not-localize/aemassets_reveal_icon.png). In alternativa, scegliere **Rivela** dal menu **Azioni desktop** nella barra degli strumenti.

## Comprendere gli stati delle risorse {#understand-the-asset-statuses}

| ![Icona app predefinita di Windows](assets/do-not-localize/win_default.png) | L&#39;app è connessa al server e tutte le risorse sono sincronizzate. |
--- |--- |
| ![Icona disattivata per Windows](assets/do-not-localize/win_disabled.png) | L&#39;app è avviata ma non è connessa al server. Alcune risorse potrebbero essere in attesa di sincronizzazione. |
| ![Icona di sincronizzazione file Windows](assets/do-not-localize/win_sync.png) | Le risorse vengono sincronizzate. I file vengono caricati o scaricati. Potete visualizzare gli stati esatti e mettere in pausa i trasferimenti dalla finestra Stato risorsa. |
| ![Icona di riconnessione Windows](assets/do-not-localize/win_refresh.png) | L&#39;app sta tentando di riconnettersi. Potenzialmente i problemi di rete stanno causando la sua disconnessione. |

## Risorse {#workonassets}

### Estrarre risorse dall&#39;interfaccia Web [!DNL Experience Manager]{#check-out-assets-from-the-aem-web-interface}

[!DNL Assets] consente di estrarre le risorse per la modifica e archiviarle nuovamente dopo aver completato le modifiche. Dopo aver estratto una risorsa, potete solo modificare, annotare, pubblicare, spostare o eliminare la risorsa. Il check-out di una risorsa blocca la risorsa e impedisce ad altri utenti di eseguire una di queste operazioni. Per poter estrarre/archiviare le risorse, è necessario disporre dell&#39;accesso in scrittura.

Esistono due modi per estrarre le risorse dall&#39;interfaccia Web [!DNL Experience Manager]. Per informazioni dettagliate sul primo metodo, consultate [archiviazione e estrazione di file dall&#39;interfaccia utente di Assets](https://experienceleague.adobe.com/docs/experience-manager-65/assets/managing/check-out-and-submit-assets.html). Seguite questi passaggi per i secondi metodi per estrarre e aprire la risorsa quando è installata l&#39;app desktop [!DNL Experience Manager].

1. Aprite l&#39;interfaccia [!DNL Assets] e passate il puntatore del mouse su una cartella o una risorsa, per visualizzare le azioni desktop come azioni rapide nella vista a schede.

   ![Opzione Proprietà nella vista a schede](assets/desktop_actions_in_card_view.png)

   Queste azioni desktop sono disponibili anche quando tocchi o fai clic sull’icona Azioni desktop nella barra degli strumenti dopo aver selezionato la risorsa o dalla barra degli strumenti nella pagina della risorsa.

1. Per aprire la risorsa, toccate o fate clic sull&#39;azione rapida Apri sul desktop ![Apri sull&#39;icona del desktop](assets/do-not-localize/aemassets_icon_openondesktop.png).

   In alternativa, scegliete Apri dal menu Azioni desktop nella barra degli strumenti.

   >[!NOTE]
   >
   >Quando modificate un file che è appena aperto e non estratto, gli altri utenti non sono a conoscenza del fatto che una risorsa viene aggiornata automaticamente.

1. Per aprire una risorsa da modificare in un&#39;applicazione Adobe Creative Cloud, toccate o fate clic sull&#39;azione rapida Modifica desktop ![Modifica icona desktop](assets/do-not-localize/aemassets_icon_editdesktop.png). Viene inoltre estratta la risorsa per la modifica. Dopo aver completato la modifica, archiviate la risorsa per aggiornare le modifiche in [!DNL Assets].

   In alternativa, scegliete Modifica dal menu Azioni desktop nella barra degli strumenti.

1. Selezionate l’opzione di menu Apri. Le risorse selezionate vengono aperte in modalità di anteprima.
1. Per modificare le risorse, selezionate l’opzione Modifica. Le risorse vengono aperte in modalità di modifica.

### Estrarre risorse dal Finder in Mac OS {#check-out-assets-on-mac}

L&#39;app consente di estrarre i file di risorse per impedire ad altri utenti di modificare i file su cui state lavorando.

1. Dal menu di scelta rapida Mac, selezionate Apri  cartella AEM Assets per aprire il Finder.

   ![Opzioni del menu di scelta rapida per accedere e aprire le risorse tramite l’app  [!DNL Experience Manager] desktop](assets/aem_desktopapp_mac_context_menu.png)

   *Figura: Opzioni del menu di scelta rapida per accedere e aprire le risorse tramite l’app  [!DNL Experience Manager] desktop.*

1. Andate alla risorsa da estrarre.
1. Fai clic con il pulsante destro del mouse sulla risorsa e seleziona Ulteriori informazioni sulle risorse dal menu di scelta rapida.
1. Nella finestra di dialogo Informazioni risorsa, toccate o fate clic sull’icona Checkout per estrarre la risorsa. Dopo aver fatto clic o toccato sull’icona Checkout, l’icona Checkout viene attivata per passare all’icona check-in.

   ![Passa alla risorsa da estrarre](assets/browse_assets_to_checkout.png)

1. Per archiviare la risorsa in modo che sia disponibile per gli altri utenti, toccate o fate clic sull’icona di check-in nella finestra di dialogo Informazioni risorsa.

### Estrarre risorse in Windows {#check-out-assets-on-windows}

L&#39;app consente di estrarre i file di risorse per impedire ad altri utenti di modificare i file su cui state lavorando.

1. Dal menu di scelta rapida, selezionate Esplora risorse per aprire Esplora risorse.
1. In Esplora risorse, andate alla posizione della risorsa da estrarre.
1. Fai clic con il pulsante destro del mouse sulla risorsa e seleziona Apri sul Web dal menu di scelta rapida.
1. Nella finestra di dialogo Informazioni risorsa, toccate o fate clic sull’icona Checkout. L’icona Checkout (Checkout) consente di passare all’icona Check-In.

   ![Icona Checkout](assets/checkout_icon_toggles.png)

1. Rivedete la risorsa in Esplora risorse. L&#39;icona Blocca sulla risorsa ![Icona blocco risorsa](assets/do-not-localize/aemassets_icon_lockcheckout.png) indica che la risorsa è stata estratta.

   >[!NOTE]
   >
   >L&#39;icona Blocca potrebbe apparire dopo qualche ritardo. [!DNL Experience Manager] l&#39;app desktop memorizza nella cache le risorse per un accesso rapido, pertanto l&#39;aggiornamento dello stato bloccato potrebbe richiedere alcuni minuti.

1. Per archiviare la risorsa in modo che sia disponibile per gli altri utenti, tocca o fai clic sull&#39;icona di check-in nella finestra di dialogo **Informazioni risorsa**.

### Archiviare una risorsa utilizzando il Finder o Esplora risorse e utilizzando l&#39;interfaccia Web {#check-in-an-asset-using-finder-or-explorer-and-using-web-interface}

Dopo aver modificato le risorse, salvatele nell’applicazione desktop. Dal menu di scelta rapida, selezionate **Ulteriori informazioni sulle risorse** e fate clic sul check-in.

Le risorse vengono caricate nel server [!DNL Experience Manager]. Facoltativamente, potete controllare lo stato del caricamento selezionando **Visualizza stato risorsa** dall&#39;icona della barra delle applicazioni. In alternativa, puoi archiviare una risorsa dall&#39;interfaccia Web [!DNL Experience Manager]. Fate clic sulle risorse estratte o selezionatele. Dalla barra degli strumenti, fare clic sull&#39;icona di check-in ![icona di check-in](assets/do-not-localize/aemassets_icon_checkin.png).

Una risorsa viene caricata automaticamente in [!DNL Experience Manager] una volta salvate localmente le modifiche. Il check-in rende la risorsa disponibile per la modifica ad altri [!DNL Experience Manager] utenti.

### Caricare in massa risorse e cartelle sul server [!DNL Experience Manager] {#bulkupload}

Utilizzando l&#39;app desktop [!DNL Experience Manager], potete caricare un&#39;intera cartella contenente risorse dalla directory del file locale in [!DNL Assets]. In questo modo, tutte le risorse all’interno della cartella vengono caricate in blocco anziché caricarle una alla volta.

1. Nell&#39;interfaccia utente delle risorse, tocca o fai clic su **Crea** nella barra degli strumenti, quindi dal menu scegli **Carica cartella**.
1. Individuate la cartella da caricare e selezionatela.
1. Tocca o fai clic su OK. Nella finestra di dialogo Stato risorse viene visualizzato lo stato del caricamento.

   ![Consultate lo stato del caricamento nella finestra Stato risorsa](assets/aem_desktopapp_bulkupload_status.png)

   Consultate lo stato del caricamento nella finestra Stato risorsa

   >[!NOTE]
   >
   >Per sospendere o annullare manualmente il caricamento, toccate o fate clic sull’icona appropriata.

1. Dopo il caricamento della cartella, chiudi la finestra di dialogo e passa all’interfaccia utente delle risorse. La cartella caricata viene visualizzata nell’interfaccia Web.

 Adobe non consiglia di copiare-incollare o trascinare un numero maggiore di file o cartelle nidificate dal file system locale nell&#39;area di condivisione della rete. L&#39;app non è in grado di controllare il processo di caricamento a causa di limiti tecnici e le prestazioni sono insufficienti.

In alternativa, selezionate i file/le cartelle da caricare in [!DNL Experience Manager] nel Finder o in Esplora risorse, copiateli negli Appunti del sistema, individuate la cartella di destinazione nell&#39;area di condivisione di rete e, dal menu di scelta rapida dell&#39; [!DNL Experience Manager] app desktop, selezionate **Incolla risorse**. In questo modo, l&#39;app [!DNL Experience Manager] desktop avvia il caricamento delle risorse incollate in modo simile all&#39;opzione **Carica cartella** disponibile nell&#39;interfaccia Web [!DNL Experience Manager].

>[!MORELIKETHIS]
>
>* [Applicazione app desktop  [!DNL Experience Manager] Troubleshooting](troubleshoot-app-v1.md)

