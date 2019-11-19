---
title: Usare l’app desktop AEM
description: Scopri come installare e utilizzare l’app desktop Adobe Experience Manager per lavorare sulle risorse AEM direttamente dal desktop Win o Mac. Scopri le procedure ottimali e le informazioni sulla risoluzione dei problemi.
uuid: 55057617-89de-43cd-8419-1252a42ab2fb
contentOwner: AG
products: SG_EXPERIENCEMANAGER/6.3/ASSETS
discoiquuid: 39d7bcad-d7b0-4978-a790-4cb68b8a7d6a
mini-toc-levels: 1
translation-type: tm+mt
source-git-commit: f9c2347f8f17d32479207980fafba058825d986f

---


# Usare l’app desktop AEM {#use-aem-desktop-app-v2}

Utilizza l’app desktop Adobe Experience Manager (AEM) per accedere facilmente alle risorse AEM sul desktop locale e utilizzarle in qualsiasi applicazione desktop. Potete aprire le risorse nelle applicazioni desktop e modificare localmente le risorse. Caricate nuovamente in AEM con il controllo delle versioni per condividere gli aggiornamenti con altri utenti. Potete inoltre caricare nuovi file e gerarchie di cartelle in AEM, creare cartelle ed eliminare risorse o cartelle da AEM.

L’integrazione consente a diversi ruoli dell’organizzazione di gestire le risorse a livello centrale in Risorse AEM e di accedere alle risorse sul desktop locale nelle applicazioni native in Windows o Mac OS.

Quando apri l’applicazione dopo la disconnessione o per la prima volta, immetti l’URL del server AEM. Fate clic su Connect. Immetti le credenziali per collegare l'app al server.

Le attività chiave che eseguite con l'app desktop AEM sono:

![Flussi di lavoro e attività eseguibili tramite l’](assets/aem_desktop_app_usecases_v2.png "app desktop AEMFlussi di lavoro e attività eseguibili tramite l’app")desktop AEM. [Scaricate questo](assets/aem_desktop_app_usecases_print.pdf) file PDF pronto per la stampa.

## Funzionamento dell'app desktop {#how-app-works2}

Prima di iniziare a utilizzare l'applicazione, scopri [come funziona](release-notes.md#how-app-works)l'app. Inoltre, è necessario conoscere i termini seguenti:

* **[!UICONTROL Desktop Actions]**: Dall’interfaccia Web di Risorse, dall’interno di un browser, potete esplorare i percorsi delle risorse o il check-out e aprire la risorsa per la modifica nell’applicazione desktop nativa. Queste azioni sono disponibili dall'interfaccia Web e utilizzano la funzionalità dell'app desktop. Vedere [come abilitare le azioni](using.md#desktopactions-v2)desktop.

* Lo stato del file è **[!UICONTROL Cloud Only]**: Tali risorse non vengono scaricate sul computer locale e sono disponibili solo sul server AEM.

* Lo stato del file è **[!UICONTROL Available locally]**: Le risorse vengono scaricate e disponibili sul computer locale così come sono. Le risorse non vengono modificate.

* Lo stato del file è **[!UICONTROL Edited locally]**: Tali risorse vengono modificate localmente e le modifiche restano nel server AEM caricato. Dopo il caricamento, lo stato cambia in [!UICONTROL Available locally]. Consultate [Modificare le risorse](using.md#edit-assets-upload-updated-assets).

* Lo stato del file è **[!UICONTROL Editing conflict]**: Se voi e altri utenti modificate una risorsa contemporaneamente, l'app indica che si è verificato un conflitto di modifica. L'app fornisce inoltre opzioni per mantenere o ignorare le modifiche. Scopri [come evitare conflitti](using.md#adv-workflow-collaborate-avoid-conflicts)di modifica.

* Lo stato del file è **[!UICONTROL Modified remotely]**: L’app indica se una risorsa scaricata è stata modificata nel server AEM. L'app offre inoltre l'opzione per scaricare la versione più recente e aggiornare la copia locale. Scopri [come evitare conflitti](using.md#adv-workflow-collaborate-avoid-conflicts)di modifica.

* **Check-out**: Se si sta modificando un file o si intende modificarlo, è possibile attivare o disattivare lo stato per il check-out. Aggiunge un’icona a forma di lucchetto alla risorsa nell’interfaccia Web dell’app e di AEM. L’icona a forma di lucchetto indica agli altri utenti di evitare la modifica simultanea della stessa risorsa, causando un conflitto di modifica.

* **Check-in**: Contrassegnate la risorsa come sicura che altri utenti possano modificarla senza causare conflitti di modifica. Quando caricate le modifiche, l'icona Blocca viene rimossa automaticamente. Se si attiva o disattiva lo stato del check-in, viene rimossa anche l’icona del blocco, anche se si consiglia di non eseguire manualmente il check-in senza caricare le modifiche. Se eliminate le modifiche, attivate il check-in manualmente.

* **[!UICONTROL Open]** azione: È sufficiente aprire la risorsa per visualizzarla in anteprima nell’applicazione nativa. Si consiglia di non modificare la risorsa utilizzando questa azione, in quanto non estrae la risorsa e altri utenti possono apportare modifiche che potrebbero causare conflitti di modifica.

* **[!UICONTROL Edit]** azione: Utilizzate l’azione per modificare l’immagine. Facendo clic su [!UICONTROL Edit] un’azione, la risorsa viene automaticamente estratta e viene aggiunta un’icona a forma di lucchetto alla risorsa. Dopo aver fatto clic su Modifica, se non desiderate modificare la risorsa, fate clic su [!UICONTROL Toggle check-in]. Per eliminare, rinominare o spostare le risorse nella gerarchia di cartelle di AEM DAM, utilizza le azioni dell’interfaccia Web di AEM e non l’azione di modifica.

* **[!UICONTROL Download]** azione: Scaricate la risorsa nel computer locale. Potete scaricare le risorse ora e modificarle in un secondo momento; lavorate offline e caricate le modifiche in un secondo momento. Le risorse vengono scaricate in una cartella cache del file system.

* **[!UICONTROL Reveal File]** o **[!UICONTROL Reveal Folder]** azione: Mentre le risorse vengono scaricate in una cartella cache locale, l'app imita un'unità di rete locale e fornisce un percorso locale per ciascuna risorsa. Per conoscere questo percorso, utilizza l'opzione di visualizzazione appropriata nell'app. L'azione Mostra è necessaria per inserire risorse nell'applicazione Creative Cloud. Consultate [Inserire le risorse](using.md#place-assets-in-native-documents).

* **[!UICONTROL Open In Web]** azione: Per visualizzare la risorsa nell’interfaccia Web di AEM, apritela nel Web. Puoi avviare più flussi di lavoro dall’interfaccia AEM, ad esempio aggiornare i metadati o individuare le risorse.

* **[!UICONTROL Delete]** azione: Elimina la risorsa dall’archivio AEM DAM. Questa azione elimina la copia originale della risorsa sul server AEM. Se desiderate eliminare solo le modifiche apportate alla risorsa locale, consultate [Eliminare le modifiche](using.md#edit-assets-upload-updated-assets).

* **[!UICONTROL Upload Changes]**: L'app desktop carica la risorsa aggiornata solo quando viene caricata esplicitamente nel server AEM. Quando salvate le modifiche, queste vengono salvate solo sul computer locale. Quando caricate, la risorsa viene automaticamente archiviata e l'icona Blocca viene rimossa. Consultate [Modificare le risorse](using.md#edit-assets-upload-updated-assets).

## Abilitare le azioni desktop nell’interfaccia Web di AEM {#desktopactions-v2}

Dall’interfaccia utente di Risorse in un browser, puoi esplorare le posizioni delle risorse o estrarne e aprire la risorsa per la modifica nell’applicazione desktop. Queste opzioni vengono chiamate [!UICONTROL Desktop Actions] e non sono abilitate per impostazione predefinita. Per attivarlo, attenetevi alla procedura seguente.

1. Nella console Risorse, tocca o fai clic sull’ **[!UICONTROL User]** icona nella barra degli strumenti.
1. Tocca o fai clic sul pulsante **[!UICONTROL My Preferences]** per visualizzare la **[!UICONTROL Preferences]** finestra di dialogo.
1. Nella finestra di dialogo Preferenze utente, selezionate **[!UICONTROL Show Desktop Actions For Assets]**. Tocca o fai clic **[!UICONTROL Accept]**.

   ![Controlla Mostra azioni desktop per risorse per abilitare le azioni desktop](assets/chlimage_1-3.png)

   Controlla [!UICONTROL Show Desktop Actions For Assets] per abilitare le azioni desktop

## Sfogliare, cercare e visualizzare in anteprima le risorse {#browse-search-preview-assets}

Potete cercare, cercare e visualizzare in anteprima le risorse disponibili nell’archivio AEM, il tutto dall’applicazione desktop. Provate quanto segue nell'app:

1. Individuate una cartella per visualizzare informazioni di base sulle risorse disponibili nella cartella, insieme a miniature piccole di tutte le risorse.

   ![Sfogliare i file e](assets/browse_folder_da2.png "le cartelle DAMisolare i file e le cartelle DAM")

1. Per visualizzare ulteriori informazioni e una miniatura più grande di una singola risorsa, fate clic sul nome del file.

   ![Visualizzazione di un’anteprima più ampia di una risorsa e di](assets/large_preview_actions_da2.png "azioniVisualizzazione di un’anteprima più ampia di una risorsa e di azioni")

1. Fate clic **[!UICONTROL Open]** o **[!UICONTROL Edit]** per scaricare il file localmente e visualizzarlo o modificarlo rispettivamente nell'applicazione nativa.
1. Effettuate ricerche utilizzando le parole chiave per trovare una risorsa correlata nell’archivio di AEM. Utilizzare `?` e `*` come caratteri jolly. Questi caratteri jolly sostituiscono rispettivamente un singolo carattere o più caratteri. Filtrate e ordinate i risultati come necessario.

   ![Ricerca di esempio con asterisco](assets/search_wildcard_da2.png "carattere jollyRicerca di esempio con asterisco carattere jolly")

   ![Un'altra ricerca di esempio con](assets/search_wildcard2_da2.png "carattere jolly asteriscoUn'altra ricerca di esempio con diversa posizione del carattere jolly asterisco")

>[!NOTE]
>
>L'app visualizza le risorse in base ai criteri di ricerca in più campi di metadati, non solo il titolo della risorsa o il nome del file.

## Scaricare le risorse {#download-assets}

Potete scaricare le risorse dal file system locale. L’app recupera le risorse dal server AEM e ne salva la stessa copia sul file system locale.

Fate clic sull'icona ![](assets/do-not-localize/more2_da2.png) Altre opzioni per le opzioni e fate clic sull'icona ![](assets/do-not-localize/download_cloud_da2.png) Scarica per il download.

![Opzione di download per una](assets/download_option_da2.png "risorsaOpzione di download per una risorsa")

>[!NOTE]
>
>Quando scaricate o caricate uno o più file di grandi dimensioni, l’applicazione disattiva le azioni per risorse e cartelle. Le azioni sono disponibili al termine del download o del caricamento.

Il download di più risorse potrebbe causare prestazioni scadenti se la dimensione della coda è grande o se si verificano problemi di rete. Inoltre, quando scaricate una cartella potreste mettere in coda inconsapevolmente molte risorse da scaricare. Per evitare lunghi tempi di attesa, l'app limita il numero di risorse scaricate contemporaneamente. Per sapere come configurarlo, consultate [Impostare le preferenze](install-upgrade.md#set-preferences). Anche al di sotto di questo limite, l'app potrebbe a volte richiedere una conferma prima di scaricare una cartella apparentemente grande.

![App conferma il download di un numero relativamente elevato di](assets/download_confirmation_da2.png "risorseApp conferma il download di un numero relativamente elevato di risorse")

Se le cartelle sono selezionate e scaricate, l’applicazione scarica solo le risorse memorizzate direttamente nelle cartelle in AEM. Non scarica automaticamente le risorse dalle sottocartelle.

## Aprire le risorse sul desktop {#openondesktop-v2}

Potete aprire le risorse remote per la visualizzazione nell’applicazione nativa. Le risorse vengono scaricate in una cartella locale e avviate nell’applicazione nativa associata al formato file. Potete modificare l'applicazione nativa per aprire tipi di file specifici (estensioni) in Mac o Windows.

Fate clic **[!UICONTROL Open]** dal menu della risorsa. La risorsa viene scaricata localmente e aperta nell’applicazione nativa. Controllate l’avanzamento del download e la velocità di trasferimento delle risorse grandi nella barra di stato.
<!-- ![Download progress bar for large-sized assets](assets/download_status_bar_da2.png "Download progress bar for large-sized assets")

-->

>[!NOTE]
>
>Se le modifiche previste non vengono riportate nell'app, fai clic sull'icona di aggiornamento ![Icona](assets/do-not-localize/refresh.png) Aggiorna o fai clic con il pulsante destro del mouse nell'interfaccia dell'app e fai clic su **[!UICONTROL Refresh]**. Le azioni non sono disponibili mentre sono in corso download o caricamenti di dimensioni maggiori.

Per aprire la cartella di download locale di una risorsa, fate clic sull’icona ![](assets/do-not-localize/more2_da2.png) Altre azioni e fate clic sull’azione ![Mostra icona](assets/do-not-localize/reveal_action2_da2.png) **[!UICONTROL Reveal File]** .

## Utilizzare o inserire risorse in documenti nativi {#place-assets-in-native-documents}

In alcuni casi, ad esempio quando inserite una risorsa in un documento nativo, potete accedere a un file in Esplora risorse o nel Finder di Mac. Per accedere al percorso del file system del file scaricato localmente, utilizzate l'opzione ![Mostra icona](assets/do-not-localize/reveal_action2_da2.png) **[!UICONTROL Reveal File]** .

![Mostra file azione per una](assets/revealfile_action_da2.png "risorsaMostra file azione per una risorsa")

Fate clic **[!UICONTROL Reveal File]** o **[!UICONTROL Reveal Folder]** su una cartella per aprire Esplora risorse o il Finder del Mac con il file o la cartella preselezionati nel computer locale. Questa opzione è utile, ad esempio, per inserire i file AEM nelle applicazioni native che supportano il posizionamento o il collegamento di file locali. Per vedere come inserire file in Adobe InDesign, consultate [Inserimento di elementi grafici](https://helpx.adobe.com/indesign/using/placing-graphics.html).

L' **[!UICONTROL Reveal File]** azione consente di aprire una condivisione di rete locale, in cui vengono visualizzate solo le risorse disponibili localmente, ovvero risorse che sono state rivelate, scaricate o aperte/modificate tramite l'app. La condivisione di rete locale non carica alcuna modifica in AEM. Per caricare le modifiche, utilizzate esplicitamente **[!UICONTROL Upload Changes]** o **[!UICONTROL Upload]** azioni nell'app.

>[!NOTE]
>
>Per compatibilità con le versioni precedenti dell’app desktop AEM v1.x, i file rivelati sono gestiti da una condivisione di rete locale, esponendo solo i file disponibili localmente. I percorsi desktop dei file rivelati sono gli stessi dei percorsi creati dall'app v1.x.

>[!CAUTION]
>
>Non utilizzate **[!UICONTROL Reveal File]** l'opzione per modificare le risorse nelle applicazioni native. Utilizzate, invece, le **[!UICONTROL Edit]** azioni. Per ulteriori informazioni, consulta Flusso di lavoro [avanzato: collaborare sugli stessi file ed evitare conflitti](#adv-workflow-collaborate-avoid-conflicts)di modifica.

## Modificare le risorse e caricare le risorse aggiornate in AEM {#edit-assets-upload-updated-assets}

Aprite le risorse da modificare quando desiderate apportare modifiche e caricare le risorse aggiornate nel server AEM. Per evitare conflitti con le modifiche di altri utenti, utilizzate l'app per avviare una sessione di modifica. Prima di iniziare a modificare, accertatevi che la risorsa non contenga un’icona a forma di lucchetto, ovvero che un altro utente non stia modificando la risorsa.

Per modificare una risorsa, cercate la risorsa o individuate la sua posizione. Fate clic sull'icona ![](assets/do-not-localize/more2_da2.png) Altro e fate clic su **[!UICONTROL Edit]**.

Per **[!UICONTROL Toggle Check-out]** bloccare la risorsa e evitare conflitti con le modifiche apportate da altri utenti in entrambe le situazioni:

* Hai iniziato a modificare una risorsa senza prima estrarla (ad esempio, aprendola).
* Iniziate presto a modificare una risorsa e non desiderate che altri utenti la modifichino.

Dopo aver apportato le modifiche, l'app visualizza lo **[!UICONTROL Edited Locally]** stato delle risorse modificate. Tutte le modifiche salvate nelle risorse sono solo locali finché non caricate le modifiche in AEM. Per caricare una o più risorse una per una, fate clic **[!UICONTROL Upload Changes]** sulle relative opzioni. Crea una versione della risorsa in AEM. Utilizzando l’interfaccia Web di Risorse AEM, puoi vedere la cronologia delle risorse nella vista [](https://helpx.adobe.com/experience-manager/6-5/assets/using/activity-stream.html)Timeline.

![Opzione delle modifiche di caricamento nell'opzione delle modifiche](assets/upload_changes_single1_da2.png "appCaricare nell'app")

![Opzione di caricamento delle modifiche durante la visualizzazione di un’anteprima di grandi dimensioni di una](assets/upload_changes_single2_da2.png "risorsaOpzione di caricamento delle modifiche durante la visualizzazione di un’anteprima di grandi dimensioni di una risorsa")

Per le procedure ottimali per la modifica collaborativa, consulta Flusso di lavoro [avanzato: collaborare sugli stessi file ed evitare conflitti](#adv-workflow-collaborate-avoid-conflicts)di modifica.

Nei seguenti casi, potrebbe essere utile eliminare le modifiche e le modifiche apportate alla risorsa locale. Click **[!UICONTROL Discard Changes]**.

* Se non desiderate salvare le modifiche locali in AEM.
* Dopo aver salvato alcune modifiche, iniziate a apportare modifiche alla risorsa originale.
* Interrompi la modifica della risorsa in quanto non è più necessaria.

Se necessario, attivate o disattivate il check-out. La risorsa aggiornata viene rimossa dalla cartella della cache locale e viene scaricata nuovamente quando la modificate o la aprite.

## Caricare e aggiungere nuove risorse ad AEM {#upload-and-add-new-assets-to-aem}

Gli utenti possono aggiungere nuove risorse all'archivio DAM. Ad esempio, puoi essere un fotografo di agenzia o un appaltatore che desidera aggiungere un gran numero di foto da un servizio fotografico all’archivio di AEM. Per aggiungere nuovo contenuto ad AEM, fate clic sull’icona ![](assets/do-not-localize/upload_to_cloud_da2.png) Carica nel cloud nella barra superiore dell’app. Individuate i file di risorse nel file system locale e fate clic su **[!UICONTROL Select]**. L'app avvia il caricamento della risorsa e visualizza una barra di avanzamento in basso se il caricamento della risorsa richiede più tempo. Non utilizzate spazi bianchi e caratteri non validi durante la creazione o il caricamento di cartelle. Consulta un elenco di caratteri in [Creazione di cartelle in Risorse](https://helpx.adobe.com/experience-manager/6-5/assets/using/managing-assets-touch-ui.html#Creatingfolders)AEM.

<!-- ![Download progress bar for large-sized assets](assets/upload_status_da2.png "Download progress bar for large-sized assets")
-->

Potete caricare cartelle o singoli file dal file system locale. Quando viene caricata, viene mantenuta la gerarchia di una cartella. Prima di caricare le risorse in blocco, consultate Caricamento in [blocco](#bulk-upload-assets).

Per visualizzare l’elenco delle risorse trasferite in una determinata sessione, fate clic su **[!UICONTROL View]** &gt; **[!UICONTROL Assets transfers]**. L'elenco consente di visualizzare e verificare rapidamente i trasferimenti di file della sessione corrente.

![Elenco delle attività trasferite in una particolare](assets/assets_transfered_da2.png "sessioneElenco delle attività trasferite in una particolare sessione")

>[!NOTE]
>
>L'elenco di trasferimenti non è persistente e non è disponibile se chiudete l'app e la riaprite.

>[!NOTE]
>
>Se il caricamento dei file non riesce e se vi state connettendo a AEM 6.5.1 o a una distribuzione successiva, consultate queste informazioni [per la](troubleshoot.md#upload-fails)risoluzione dei problemi.

## Operazioni con più risorse {#work-with-multiple-assets}

Gli utenti possono utilizzare e gestire facilmente più risorse mediante azioni quali il caricamento di tutte le modifiche in una sola volta o il caricamento di cartelle nidificate in pochi clic.

### Sfoglia cartelle grandi {#browse-large-folders}

Quando lavorate con cartelle contenenti molte risorse, scorrete per visualizzare altre risorse. Per scorrere utilizzando la tastiera, premere più volte il tasto Tab per selezionare la risorsa in alto. Osservate come la risorsa evidenziata sia visibile quando è selezionata. Ora usate il tasto freccia giù per scorrere l’elenco delle risorse.

### Azioni rapide per le risorse selezionate {#quick-actions-for-selected-assets}

Fate clic sulla miniatura di alcune risorse per selezionarle. Per selezionare tutte le risorse, fate clic sulla casella di controllo nella barra superiore dell'app. Il set di azioni applicabili a tutte le risorse selezionate collettivamente viene visualizzato in una barra degli strumenti nella parte inferiore dell’app.

![La barra degli strumenti in basso mostra le azioni relative alle](assets/actions_bottom_toolbar1_da2.png "risorse selezionate. La barra degli strumenti in basso mostra le azioni comuni per le risorse selezionate")

![Nessuna azione nella barra degli strumenti in assenza di azioni comuni per la](assets/actions_bottom_toolbar2_da2.png "selezioneNessuna azione nella barra degli strumenti in assenza di azioni comuni per la selezione")

Le azioni disponibili nella barra degli strumenti nella parte inferiore dipendono dallo stato dei file selezionati. Ad esempio, se selezionate solo **[!UICONTROL Edited Locally]** i file, compare l’icona **[!UICONTROL Upload Changes]** . Se selezionate un insieme di **[!UICONTROL Edited locally]** e **[!UICONTROL Cloud only]**, l’ **[!UICONTROL Upload Changes]** azione non è disponibile.

### Trova tutte le immagini modificate {#find-all-edited-images}

L'applicazione fornisce una visualizzazione, chiamata **[!UICONTROL Edited locally]**, per consentirvi di accedere rapidamente a tutti i file scaricati localmente (tramite [!UICONTROL Open] azioni o [!UICONTROL Edit] azioni) e quindi modificati. L'app consente di selezionare tutte le risorse modificate localmente e caricare le modifiche in pochi clic. Questa visualizzazione mostra anche le risorse modificate localmente che presentano un conflitto di modifica.

![Filtrare per visualizzare tutte le](assets/edited_locally_filter_da2.png "risorse modificate localmenteFiltrare per visualizzare tutte le risorse modificate localmente, ad esempio per il caricamento in blocco delle modifiche")

### Caricare in blocco le risorse {#bulk-upload-assets}

Gli utenti o l’organizzazione, come fotografi o agenzie creative, possono creare numerose risorse locali in scenari diversi, ad esempio scatti fotografici, ritocchi o selezioni da un set più ampio esterno a AEM. Possono caricare queste grandi cartelle locali in Risorse AEM direttamente dall’app desktop. Le gerarchie di cartelle vengono mantenute e vengono caricate tutte le sottocartelle nidificate e le risorse incluse. Le risorse caricate sono immediatamente disponibili per l’uso anche ad altri utenti dello stesso server. Le risorse vengono caricate in background, pertanto l’operazione non è legata a una sessione del browser Web.

![Caricamento in blocco di più cartelle locali dal desktop in](assets/upload_local_folders_da2.png "AEMBulkCaricamento in AEM di più cartelle locali dal desktop")

Dopo il caricamento, se le modifiche previste non vengono riportate nell'app, fate clic sull'icona ![Aggiorna](assets/do-not-localize/refresh.png).

>[!NOTE]
>
>Non utilizzate la funzionalità di caricamento per migrare le risorse tra due distribuzioni AEM. Consultate la guida [alla](https://helpx.adobe.com/experience-manager/6-5/assets/using/assets-migration-guide.html)migrazione.

### Elenco delle attività trasferite {#list-of-transferred-assets}

Per visualizzare l’elenco delle risorse trasferite in una determinata sessione, consultate [Caricare risorse in AEM](#upload-and-add-new-assets-to-aem).

## Flusso di lavoro avanzato: inizia dall’interfaccia Web di AEM Assets {#adv-workflow-start-from-aem-ui}

Se necessario, avvia il flusso di lavoro dall’interfaccia Web di Risorse AEM. L’app desktop si integra con AEM per sostituirla quando richiesto mediante le azioni desktop.

Un caso particolare di avvio del flusso di lavoro dall’interfaccia Web è rappresentato dall’individuazione delle risorse. La barra di ricerca Omniture nell’interfaccia utente Risorse offre un’esperienza di ricerca avanzata e avanzata. Potrebbe essere necessario individuare prima una risorsa desiderata sul Web e avviare il flusso di lavoro nell'app utilizzando [!UICONTROL Desktop Actions]. Alcuni esempi di casi includono il filtraggio dei risultati di ricerca utilizzando facet, l’individuazione di una risorsa specifica con licenza Adobe Stock o una personalizzazione implementata dall’organizzazione che consente una migliore individuazione dall’interfaccia Web.

La funzionalità dell’app desktop viene utilizzata quando tentate le seguenti azioni sull’interfaccia Web di Assets:

* Il [!UICONTROL Desktop Actions] che consente [!UICONTROL Open], [!UICONTROL Edit]e [!UICONTROL Reveal]
* [!UICONTROL Upload folder]
* [!UICONTROL Check-out] o [!UICONTROL check-in]

Ad esempio, le azioni sull'interfaccia Web disponibili per una risorsa estratta nell'app sono [!UICONTROL Open], [!UICONTROL Reveal]e [!UICONTROL Check-in].

![Azioni desktop nell’](assets/assets_web_actions_da2.png "interfaccia Web di AEMazioni desktop nell’interfaccia Web di AEM")

>[!NOTE]
>
>Il browser potrebbe richiedere di consentire l'avvio di Adobe Experience Manager Desktop. Per un trasferimento ininterrotto dal browser all'app, seleziona la casella di controllo appropriata per consentire sempre all'app di prendere il controllo.

Non è possibile trovare le informazioni o il flusso di lavoro seguenti utilizzando l'interfaccia Web. Utilizzate l'app desktop perché l'interfaccia Web non tiene traccia delle modifiche locali e non è a conoscenza dei seguenti elementi:

* File modificati localmente.
* File con un conflitto di modifica e con un modo per risolverlo.
* Caricate le modifiche locali in AEM.
* Vari stati dei file disponibili localmente.

Al contrario, potete aprire la risorsa nell’interfaccia Web a partire dall’app desktop tramite l’ **[!UICONTROL Open In Web]** azione.

## Flusso di lavoro avanzato: collaborare sugli stessi file ed evitare conflitti di modifica {#adv-workflow-collaborate-avoid-conflicts}

Negli ambienti collaborativi, più utenti possono lavorare sullo stesso set di risorse che possono causare conflitti di versione. Per prevenire i conflitti, attenersi alle seguenti procedure ottimali:

* Non modificate le risorse facendo clic su [!UICONTROL Open]. Non modificate le risorse scaricate localmente aprendo dalla cartella del file system. Altri utenti non sanno che la risorsa è in fase di modifica.
* Per modificare una risorsa, fate sempre clic su [!UICONTROL Edit]. Consente di aprire la risorsa nell’applicazione nativa e di aggiungere un’icona a forma di lucchetto alla risorsa, in modo che gli altri utenti siano a conoscenza del fatto che la risorsa è in fase di modifica.
* Fate clic [!UICONTROL Toggle Check-in] se accidentalmente avviate la modifica senza fare clic [!UICONTROL Edit]. In questo modo alla risorsa viene aggiunta un’icona a forma di lucchetto. Anche se prevedete di modificare una risorsa in un secondo momento ma desiderate evitare che altri la modifichino, fate clic [!UICONTROL Toggle Check-in] per bloccare la risorsa.
* Prima di modificare una risorsa, accertatevi che gli altri utenti non la stiano modificando. Individuate l’icona Blocca sulla risorsa.
* Dopo aver completato le modifiche, caricate tutte le modifiche, quindi archiviate la risorsa.

![Stati di modifica](assets/edits_conflicts_status_da2.png "conflittiStati di modifica dei conflitti")

Se una risorsa scaricata localmente viene aggiornata nel server AEM, l'app visualizza uno **[!UICONTROL Modified remotely]** stato. Per rimuovere la copia locale o aggiornare la copia locale, fare clic [!UICONTROL Remove] o [!UICONTROL Update] rispettivamente. I collegamenti presenti nella finestra di dialogo consentono di visualizzare entrambe le versioni della risorsa.

![Opzioni per risolvere il conflitto quando la risorsa viene](assets/modified_remotely_dialog_da2.png "modificata in remotoOpzioni per risolvere il conflitto quando la risorsa viene modificata in remoto")

Se anche una risorsa che state modificando localmente viene aggiornata sul server senza che ne sia a conoscenza, l'app visualizza uno **[!UICONTROL Editing Conflict]** stato. Potete mantenere una serie di modifiche, mantenendo gli aggiornamenti (fate clic **[!UICONTROL Keep Mine]**) ed eliminare le modifiche apportate dall’altro utente oppure rispettare gli aggiornamenti dell’altro utente ed eliminare i vostri (**[!UICONTROL Overwrite Mine]**).

![Opzioni per risolvere un](assets/editing_conflict_dialog_da2.png "conflitto di modificaOpzioni per risolvere un conflitto di modifica")

## Flusso di lavoro avanzato: inserire e collegare risorse in un file InDesign {#adv-workflow-place-assets-indesign}

Quando utilizzate l'app desktop AEM per aprire i file con risorse collegate, le risorse vengono pre-scaricate e vengono visualizzate nelle applicazioni native. Affinché questo flusso di lavoro funzioni, l’applicazione nativa deve supportare il posizionamento di collegamenti a risorse locali e AEM deve supportare la risoluzione di tali collegamenti nei file binari ai riferimenti sul lato server.

L'app desktop AEM supporta questo flusso di lavoro con alcune applicazioni desktop e formati di file selezionati di Adobe Creative Cloud: Adobe InDesign, Adobe Illustrator e Adobe Photoshop. Il flusso di lavoro consente di lavorare in modo efficiente con i file Creative Cloud supportati. Pertanto, se l’utente A inserisce alcune risorse in un file InDesign e le archivia in AEM, l’utente B vede le risorse nel file InDesign anche se le risorse non fanno parte del file. Le risorse vengono scaricate localmente sul computer dell’utente B.

>[!NOTE]
>
>L'app desktop può essere mappata su qualsiasi unità in Windows. Tuttavia, per le operazioni uniformi, non modificare la lettera di unità predefinita. Se gli utenti della stessa organizzazione utilizzano lettere di unità diverse, non possono vedere le risorse inserite da altri. Le risorse inserite non vengono recuperate quando il percorso cambia. Le risorse inserite continuano a essere inserite nel file binario (ad esempio, INDD) e non vengono rimosse.

Per conoscere i limiti di questo flusso di lavoro, consulta Requisiti di [sistema e versioni](release-notes.md#system-requirements-and-prerequisites-v2)supportate.

Per provare questo flusso di lavoro con una risorsa immagine e InDesign, effettuate le seguenti operazioni:

1. Tenete a portata di mano un file INDD con le risorse inserite in AEM. Per sapere come creare un tale file INDD, consulta [Inserimento di elementi grafici](https://helpx.adobe.com/indesign/using/placing-graphics.html).
1. Dall’interno dell’app desktop, **[!UICONTROL Edit]** il file INDD con le risorse inserite in AEM.
1. L'app scarica sia il file InDesign che le risorse collegate. Quando InDesign apre il documento, i collegamenti vengono risolti, le risorse vengono scaricate e le risorse vengono visualizzate nel documento InDesign.
1. Per inserire un nuovo elemento grafico nel file InDesign, usate **[!UICONTROL Reveal File]** l’azione sulla risorsa. L’azione scarica la risorsa localmente e apre il percorso di condivisione di rete locale in Esplora risorse o nel Finder di Mac.
1. Inserite la risorsa rivelata nel documento InDesign. Viene creato un collegamento nel documento.
1. Una volta completate le modifiche nel documento InDesign, salvatelo e caricatelo in AEM tramite l'app desktop.

## Flusso di lavoro avanzato: scaricare le risorse localmente {#adv-workflow-download-assets-locally}

In molti scenari, l’app scarica le risorse dal server AEM sul file system locale. I download utilizzano larghezza di banda e spazio su disco. La conoscenza degli scenari consente di ottimizzare il tempo di attesa per il completamento dei download.

Le risorse vengono scaricate dall'interno dell'app on-demand. Consultate [Scaricare le risorse](#download-assets).

Quando usate l’ [!UICONTROL Open] azione per aprire una risorsa in un’applicazione desktop nativa, la risorsa viene scaricata localmente se non è già disponibile localmente. Consultate [Aprire le risorse](#openondesktop-v2).

Quando rivelate il percorso di una risorsa o di una cartella dall'interno dell'app, la risorsa o la cartella viene prima scaricata localmente e quindi aperta sul computer nella condivisione di rete locale. Consultate [Aprire le risorse](#openondesktop-v2).

Quando utilizzate l’ [!UICONTROL Edit] azione per modificare una risorsa in un’applicazione desktop nativa, la risorsa viene scaricata localmente se non è già disponibile localmente. Consultate [Modificare le risorse e caricare le risorse aggiornate in AEM](#edit-assets-upload-updated-assets).

Se l’app è installata e consentita, completa le azioni quando utilizzi [!UICONTROL Desktop Actions] l’interfaccia Web di AEM. L'app scarica prima la risorsa e quindi completa l'azione.