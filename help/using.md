---
title: 'Usa app desktop [!DNL Experience Manager] '
description: Utilizzate le risorse  [!DNL Adobe Experience Manager] desktop app, to work with [!DNL Adobe Experience Manager] DAM direttamente dal desktop Win o Mac e utilizzate in altre applicazioni.
mini-toc-levels: 1
translation-type: tm+mt
source-git-commit: 18ed934f9acc774f7bc4ef7555aa3f369ca4cf47
workflow-type: tm+mt
source-wordcount: '3906'
ht-degree: 0%

---


# Utilizzare l&#39;app [!DNL Adobe Experience Manager] desktop {#use-aem-desktop-app-v2}

Utilizzate l&#39;app desktop [!DNL Adobe Experience Manager] per accedere facilmente alle risorse digitali memorizzate nell&#39;archivio [!DNL Adobe Experience Manager] DAM sul desktop locale e utilizzatele in qualsiasi applicazione desktop. Potete aprire le risorse nelle applicazioni desktop e modificarle localmente. Per condividere gli aggiornamenti con altri utenti, potete caricare nuovamente le modifiche in [!DNL Experience Manager] con il controllo della versione. Potete inoltre caricare nuovi file e gerarchie di cartelle in [!DNL Experience Manager], creare cartelle ed eliminare risorse o cartelle da [!DNL Experience Manager] DAM.

L&#39;integrazione consente a diversi ruoli dell&#39;organizzazione di gestire le risorse a livello centrale in [!DNL Experience Manager Assets] e di accedere alle risorse sul desktop locale nelle applicazioni native in Windows o Mac OS.

Quando si apre l&#39;applicazione dopo la disconnessione o per la prima volta, fornire l&#39;URL del server [!DNL Experience Manager] nel formato `https://[aem-server-url]:[port]/`. Selezionare quindi l&#39;opzione [!UICONTROL Connect]. Fornite le credenziali per collegare l&#39;app al server.

Le attività chiave eseguite con l&#39;app desktop [!DNL Experience Manager] sono:

![Flussi di lavoro e attività eseguibili utilizzando  [!DNL Experience Manager] desktop ](assets/aem_desktop_app_usecases_v2.png "appFlussi di lavoro e attività realizzabili  [!DNL Adobe Experience Manager] utilizzando l&#39;")
app desktopScaricate  [](assets/aem_desktop_app_usecases_print.pdf) questo file PDF pronto per la stampa.

## Funzionamento dell&#39;app desktop {#how-app-works2}

Prima di iniziare a utilizzare l&#39;applicazione, scopri [come funziona l&#39;app](release-notes.md#how-app-works). Inoltre, è possibile acquisire familiarità con i seguenti termini:

* **[!UICONTROL Desktop Actions]**: Dall’interfaccia Web di Risorse, dall’interno di un browser, potete esplorare i percorsi delle risorse o il check-out e aprire la risorsa per la modifica nell’applicazione desktop nativa. Queste azioni sono disponibili dall&#39;interfaccia Web e utilizzano la funzionalità dell&#39;app desktop. Vedere [come abilitare Azioni desktop](using.md#desktopactions-v2).

* Lo stato del file è **[!UICONTROL Cloud Only]**: Tali risorse non vengono scaricate sul computer locale e sono disponibili solo sul server [!DNL Experience Manager].

* Lo stato del file è **[!UICONTROL Available locally]**: Le risorse vengono scaricate e disponibili sul computer locale così come sono. Le risorse non vengono modificate.

* Lo stato del file è **[!UICONTROL Edited locally]**: Tali risorse vengono modificate localmente e le modifiche rimangono nel server [!DNL Experience Manager] caricato. Dopo il caricamento, lo stato cambia in [!UICONTROL Available locally]. Consultate [modificare le risorse](using.md#edit-assets-upload-updated-assets).

* Lo stato del file è **[!UICONTROL Editing conflict]**: Se voi e altri utenti modificate una risorsa contemporaneamente, l&#39;app indica che si è verificato un conflitto di modifica. L&#39;app fornisce inoltre opzioni per mantenere o ignorare le modifiche. Vedere [come evitare conflitti di modifica](using.md#adv-workflow-collaborate-avoid-conflicts).

* Lo stato del file è **[!UICONTROL Modified remotely]**: L&#39;app indica se una risorsa scaricata viene modificata nel server [!DNL Experience Manager]. L&#39;app offre inoltre l&#39;opzione per scaricare la versione più recente e aggiornare la copia locale. Vedere [come evitare conflitti di modifica](using.md#adv-workflow-collaborate-avoid-conflicts).

* **[!UICONTROL Check-out]**: Se si sta modificando un file o si intende modificarlo, è possibile attivare o disattivare lo stato per il check-out. Aggiunge un&#39;icona a forma di lucchetto alla risorsa nell&#39;app e nell&#39;interfaccia Web [!DNL Experience Manager]. L’icona a forma di lucchetto indica agli altri utenti di evitare la modifica simultanea della stessa risorsa, causando un conflitto di modifica.

* **[!UICONTROL Check-in]**: Contrassegnate la risorsa come sicura che altri utenti possano modificarla senza causare conflitti di modifica. Quando caricate le modifiche, l&#39;icona Blocca viene rimossa automaticamente. Se si attiva o disattiva lo stato del check-in, viene rimossa anche l’icona del blocco, anche se si consiglia di non eseguire manualmente il check-in senza caricare le modifiche. Se eliminate le modifiche, attivate il check-in manualmente.

* **[!UICONTROL Open]** azione: È sufficiente aprire la risorsa per visualizzarne l’anteprima nell’applicazione nativa. Si consiglia di non modificare la risorsa utilizzando questa azione, in quanto non estrae la risorsa e altri utenti possono apportare modifiche che potrebbero causare conflitti di modifica.

* **[!UICONTROL Edit]** azione: Utilizzate l’azione per modificare l’immagine. Facendo clic sull&#39;azione [!UICONTROL Edit] la risorsa viene automaticamente estratta e viene aggiunta un&#39;icona a forma di lucchetto alla risorsa. Dopo aver fatto clic su Modifica, se non desiderate modificare la risorsa, fate clic su [!UICONTROL Toggle check-in]. Per eliminare, rinominare o spostare le risorse nella gerarchia di cartelle [!DNL Experience Manager] DAM, utilizzate le azioni dell&#39;interfaccia Web [!DNL Experience Manager] e non l&#39;azione di modifica.

* **[!UICONTROL Download]** azione: Scaricate la risorsa nel computer locale. Potete scaricare le risorse ora e modificarle in un secondo momento; lavorate offline e caricate le modifiche in un secondo momento. Le risorse vengono scaricate in una cartella cache del file system.

* **[!UICONTROL Reveal File]** o  **[!UICONTROL Reveal Folder]** azione: Mentre le risorse vengono scaricate in una cartella cache locale, l&#39;app imita un&#39;unità di rete locale e fornisce un percorso locale per ciascuna risorsa. Per conoscere questo percorso, utilizza l&#39;opzione di visualizzazione appropriata nell&#39;app. L’azione Mostra è necessaria per inserire le risorse nell’applicazione di Creative Cloud. Vedere [inserire risorse](using.md#place-assets-in-native-documents).

* **[!UICONTROL Open In Web]** azione: Per visualizzare la risorsa nell’interfaccia  [!DNL Experience Manager] Web, apritela in Web. Puoi avviare più flussi di lavoro dall&#39;interfaccia [!DNL Experience Manager], come l&#39;aggiornamento dei metadati o l&#39;individuazione delle risorse.

* **[!UICONTROL Delete]** azione: Elimina la risorsa dall&#39;archivio  [!DNL Experience Manager] DAM. L’azione elimina la copia originale della risorsa sul server del Experience Manager . Se desiderate eliminare solo le modifiche apportate alla risorsa locale, consultate [eliminare le modifiche](using.md#edit-assets-upload-updated-assets).

* **[!UICONTROL Upload Changes]**: L’app desktop carica la risorsa aggiornata solo quando viene caricata in modo esplicito sul  [!DNL Experience Manager] server. Quando salvate le modifiche, queste vengono salvate solo sul computer locale. Quando caricate, la risorsa viene automaticamente archiviata e l&#39;icona Blocca viene rimossa. Consultate [modificare le risorse](using.md#edit-assets-upload-updated-assets).

## Abilitare le azioni desktop nell&#39;interfaccia Web [!DNL Experience Manager]{#desktopactions-v2}

Dall’interfaccia utente di Risorse in un browser, puoi esplorare le posizioni delle risorse o estrarne e aprire la risorsa per la modifica nell’applicazione desktop. Queste opzioni sono denominate [!UICONTROL Desktop Actions] e non sono abilitate per impostazione predefinita. Per attivarlo, attenetevi alla procedura seguente.

1. Nella console Risorse, tocca o fai clic sull&#39;icona **[!UICONTROL User]** nella barra degli strumenti.
1. Tocca o fai clic su **[!UICONTROL My Preferences]** per visualizzare la finestra di dialogo **[!UICONTROL Preferences]**.
1. Nella finestra di dialogo Preferenze utente, selezionate **[!UICONTROL Show Desktop Actions For Assets]**. Tocca o fai clic su **[!UICONTROL Accept]**.

   ![Controlla Mostra azioni desktop per risorse per abilitare le azioni desktop](assets/enable_desktop_actions.png)

   Selezionare [!UICONTROL Show Desktop Actions For Assets] per abilitare le azioni desktop

## Sfogliare, cercare e visualizzare in anteprima le risorse {#browse-search-preview-assets}

È possibile individuare, cercare e visualizzare in anteprima le risorse disponibili nell&#39;archivio [!DNL Experience Manager], il tutto dall&#39;applicazione desktop. Provate quanto segue nell&#39;app:

1. Individuate una cartella per visualizzare informazioni di base sulle risorse disponibili nella cartella, insieme a miniature piccole di tutte le risorse.

   ![Sfogliare i file e ](assets/browse_folder_da2.png "le cartelle DAMisolare i file e le cartelle DAM")

1. Per visualizzare ulteriori informazioni e una miniatura più grande di una singola risorsa, fate clic sul nome del file.

   ![Visualizzazione di un’anteprima più ampia di una risorsa e di ](assets/large_preview_actions_da2.png "azioniVisualizzazione di un’anteprima più ampia di una risorsa e di azioni")

1. Fare clic su **[!UICONTROL Open]** o **[!UICONTROL Edit]** per scaricare il file localmente e visualizzarlo o modificarlo rispettivamente nell&#39;applicazione nativa.
1. Effettuate ricerche utilizzando le parole chiave per trovare una risorsa correlata nell&#39;archivio [!DNL Experience Manager]. Utilizzate `?` e `*` come caratteri jolly. Questi caratteri jolly sostituiscono rispettivamente un singolo carattere o più caratteri. Filtrate e ordinate i risultati come necessario.

   ![Ricerca di esempio con asterisco ](assets/search_wildcard_da2.png "carattere jollyRicerca di esempio con asterisco carattere jolly")

   ![Un&#39;altra ricerca di esempio con ](assets/search_wildcard2_da2.png "carattere jolly asteriscoUn&#39;altra ricerca di esempio con diversa posizione del carattere jolly asterisco")

>[!NOTE]
>
>L&#39;app visualizza le risorse in base ai criteri di ricerca per più campi di metadati, non solo per il titolo della risorsa o per il nome del file.

## Scaricare le risorse {#download-assets}

Potete scaricare le risorse dal file system locale. L&#39;app recupera le risorse dal server [!DNL Experience Manager] e salva la stessa copia nel file system locale.

Fare clic sull&#39;icona ![Altre opzioni](assets/do-not-localize/more2_da2.png) per visualizzare le opzioni, quindi fare clic su ![Icona Scarica](assets/do-not-localize/download_cloud_da2.png) per scaricare.

![Opzione di download per una ](assets/download_option_da2.png "risorsaOpzione di download per una risorsa")

>[!NOTE]
>
>Quando scaricate o caricate uno o più file di grandi dimensioni, l’applicazione disattiva le azioni per risorse e cartelle. Le azioni sono disponibili al termine del download o del caricamento.

Il download di più risorse potrebbe causare prestazioni scadenti se la dimensione della coda è grande o se si verificano problemi di rete. Inoltre, quando scaricate una cartella potreste mettere in coda inconsapevolmente molte risorse da scaricare. Per evitare lunghi tempi di attesa, l&#39;app limita il numero di risorse scaricate contemporaneamente. Per informazioni su come configurarlo, vedere [Impostare le preferenze](install-upgrade.md#set-preferences). Anche al di sotto di questo limite, l&#39;app potrebbe a volte richiedere una conferma prima di scaricare una cartella apparentemente grande.

![App conferma il download di un numero relativamente elevato di ](assets/download_confirmation_da2.png "risorseApp conferma il download di un numero relativamente elevato di risorse")

Se le cartelle sono selezionate e scaricate, l&#39;applicazione scarica solo le risorse memorizzate direttamente nelle cartelle in [!DNL Experience Manager]. Non scarica automaticamente le risorse dalle sottocartelle.

## Aprire le risorse sul desktop {#openondesktop-v2}

Potete aprire le risorse remote per la visualizzazione nell’applicazione nativa. Le risorse vengono scaricate in una cartella locale e avviate nell’applicazione nativa associata al formato file. Potete modificare l&#39;applicazione nativa per aprire tipi di file specifici (estensioni) in Mac o Windows.

Fate clic su **[!UICONTROL Open]** nel menu delle risorse. La risorsa viene scaricata localmente e aperta nell’applicazione nativa. Controllate l’avanzamento del download e la velocità di trasferimento delle risorse grandi nella barra di stato.

<!-- ![Download progress bar for large-sized assets](assets/download_status_bar_da2.png "Download progress bar for large-sized assets")
-->

>[!NOTE]
>
>Se le modifiche previste non vengono riportate nell&#39;app, fai clic sull&#39;icona di aggiornamento ![Icona di aggiornamento](assets/do-not-localize/refresh.png) oppure fai clic con il pulsante destro del mouse nell&#39;interfaccia dell&#39;app e fai clic su **[!UICONTROL Refresh]**. Le azioni non sono disponibili mentre sono in corso download o caricamenti di dimensioni maggiori.

Per aprire la cartella di download locale di una risorsa, fate clic sull&#39;icona ![Altre azioni](assets/do-not-localize/more2_da2.png) e fate clic su ![Mostra icona](assets/do-not-localize/reveal_action2_da2.png) **[!UICONTROL Reveal File]** azione.

## Utilizzare o inserire risorse in documenti nativi {#place-assets-in-native-documents}

In alcuni casi, ad esempio quando inserite una risorsa in un documento nativo, potete accedere a un file in Esplora risorse o nel Finder di Mac. Per accedere al percorso del file system del file scaricato localmente, utilizzare l&#39;opzione ![Mostra icona](assets/do-not-localize/reveal_action2_da2.png) **[!UICONTROL Reveal File]**.

![Mostra file azione per una ](assets/revealfile_action_da2.png "risorsaMostra file azione per una risorsa")

Fate clic su **[!UICONTROL Reveal File]** o **[!UICONTROL Reveal Folder]** in una cartella per aprire Esplora risorse o il Finder di Mac con il file o la cartella preselezionati nel computer locale. Questa opzione è utile, ad esempio, per inserire i file [!DNL Experience Manager] nelle applicazioni native che supportano il posizionamento o il collegamento di file locali. Per vedere come inserire i file in  Adobe InDesign, vedere [Inserimento di elementi grafici](https://helpx.adobe.com/indesign/using/placing-graphics.html).

L&#39;azione **[!UICONTROL Reveal File]** apre una condivisione di rete locale, che visualizza solo le risorse disponibili localmente, ovvero quelle che sono state rivelate, scaricate o aperte/modificate utilizzando l&#39;app. La condivisione di rete locale non carica alcuna modifica in [!DNL Experience Manager]. Per caricare le modifiche, utilizzate esplicitamente le azioni **[!UICONTROL Upload Changes]** o **[!UICONTROL Upload]** nell&#39;app.

>[!NOTE]
>
>Per compatibilità con le versioni precedenti dell&#39;app desktop [!DNL Experience Manager] v1.x, i file rivelati vengono gestiti da una condivisione di rete locale, esponendo solo i file disponibili localmente. I percorsi desktop dei file rivelati sono gli stessi dei percorsi creati dall&#39;app v1.x.

>[!CAUTION]
>
>Non utilizzate l&#39;opzione **[!UICONTROL Reveal File]** per modificare le risorse nelle applicazioni native. Utilizzate invece le azioni **[!UICONTROL Edit]**. Per ulteriori informazioni, vedere [Flusso di lavoro avanzato: collaborare sugli stessi file ed evitare conflitti di modifica](#adv-workflow-collaborate-avoid-conflicts).

## Modificare le risorse e caricare le risorse aggiornate in [!DNL Experience Manager] {#edit-assets-upload-updated-assets}

Aprite le risorse per la modifica quando desiderate apportare modifiche e caricare le risorse aggiornate nel server AEMperience ManagerEM. Per evitare conflitti con le modifiche di altri utenti, utilizzate l&#39;app per avviare una sessione di modifica. Prima di iniziare a modificare, accertatevi che la risorsa non contenga un’icona a forma di lucchetto, ovvero che un altro utente non stia modificando la risorsa.

Per modificare una risorsa, cercate la risorsa o individuate la sua posizione. Fare clic su ![Più icona](assets/do-not-localize/more2_da2.png) e fare clic su **[!UICONTROL Edit]**.

Utilizzate **[!UICONTROL Toggle Check-out]** per bloccare la risorsa per evitare conflitti con le modifiche apportate da altri utenti in entrambe le situazioni seguenti:

* Hai iniziato a modificare una risorsa senza prima estrarla (ad esempio, aprendola).
* Iniziate presto a modificare una risorsa e non desiderate che altri utenti la modifichino.

Dopo aver apportato le modifiche, l&#39;app visualizza lo stato **[!UICONTROL Edited Locally]** per le risorse modificate. Tutte le modifiche salvate nelle risorse sono locali solo fino a quando non caricate le modifiche in [!DNL Experience Manager]. Per caricare una o più risorse una per una, fate clic su **[!UICONTROL Upload Changes]** tra le opzioni per una risorsa. Crea una versione della risorsa in [!DNL Experience Manager]. Utilizzando l&#39;interfaccia Web di [!DNL Assets], è possibile visualizzare la cronologia delle risorse nella [visualizzazione Timeline](https://experienceleague.adobe.com/docs/experience-manager-65/assets/using/activity-stream.html).

![Opzione delle modifiche di caricamento nell&#39;opzione delle modifiche ](assets/upload_changes_single1_da2.png "appCaricare nell&#39;app")

![Opzione di caricamento delle modifiche durante la visualizzazione di un’anteprima di grandi dimensioni di una ](assets/upload_changes_single2_da2.png "risorsaOpzione di caricamento delle modifiche durante la visualizzazione di un’anteprima di grandi dimensioni di una risorsa")

Per le best practice relative all&#39;editing collaborativo, consultate [Flusso di lavoro avanzato: collaborare sugli stessi file ed evitare conflitti di modifica](#adv-workflow-collaborate-avoid-conflicts).

Nei seguenti casi, potrebbe essere utile eliminare le modifiche e le modifiche apportate alla risorsa locale. Clic **[!UICONTROL Discard Changes]**.

* Se non si desidera salvare le modifiche locali in [!DNL Experience Manager].
* Dopo aver salvato alcune modifiche, iniziate a apportare modifiche alla risorsa originale.
* Interrompi la modifica della risorsa in quanto non è più necessaria.

Se necessario, attivate o disattivate il check-out. La risorsa aggiornata viene rimossa dalla cartella della cache locale e viene scaricata nuovamente quando la modificate o la aprite.

## Caricare e aggiungere nuove risorse a [!DNL Experience Manager] {#upload-and-add-new-assets-to-aem}

Gli utenti possono aggiungere nuove risorse all&#39;archivio DAM. Ad esempio, un fotografo dell&#39;agenzia o un appaltatore può voler aggiungere un gran numero di foto da un servizio fotografico al repository di [!DNL Experience Manager]. Per aggiungere nuovo contenuto a [!DNL Experience Manager], seleziona ![opzione di caricamento nel cloud](assets/do-not-localize/upload_to_cloud_da2.png) nella barra superiore dell&#39;app. Individuate i file di risorse nel file system locale e fate clic su **[!UICONTROL Select]**. In alternativa, trascinate i file o le cartelle nell’interfaccia dell’applicazione. L&#39;app avvia il caricamento della risorsa. Se il caricamento richiede più tempo, l&#39;app visualizza una barra di avanzamento nella parte inferiore. Non utilizzate spazi bianchi e caratteri non validi durante la creazione o il caricamento di cartelle. Per un elenco dei caratteri consentiti, vedere [creare cartelle in [!DNL Assets]](https://experienceleague.adobe.com/docs/experience-manager-65/assets/managing/manage-assets.html#creating-folders).

<!-- ![Download progress bar for large-sized assets](assets/upload_status_da2.png "Download progress bar for large-sized assets")
-->

Potete caricare cartelle o singoli file dal file system locale. Quando viene caricata, viene mantenuta la gerarchia di una cartella. Prima di caricare le risorse in blocco, consultate [Caricamento in blocco](#bulk-upload-assets).

Per visualizzare l&#39;elenco delle risorse trasferite in una determinata sessione, fate clic su **[!UICONTROL View]** > **[!UICONTROL Assets transfers]**. L&#39;elenco consente di visualizzare e verificare rapidamente i trasferimenti di file della sessione corrente.

![Elenco delle attività trasferite in una particolare ](assets/assets_transfered_da2.png "sessioneElenco delle attività trasferite in una particolare sessione")

Potete controllare la concorrenza di caricamento (accelerazione) in **[!UICONTROL Preferences]** > **[!UICONTROL Upload acceleration]**. Una maggiore concorrenza consente in genere di caricare più velocemente, ma può richiedere molte risorse e consumare più energia di elaborazione per il computer locale. Se si verifica un sistema lento, ripetete i tentativi di caricamento utilizzando un valore inferiore di concorrenza.

>[!NOTE]
>
>L&#39;elenco di trasferimenti non è persistente e non è disponibile se chiudete l&#39;app e la riaprite.

>[!NOTE]
>
>Se i file non vengono caricati e se vi state connettendo a [!DNL Experience Manager] 6.5.1 o una distribuzione successiva, consultate questa sezione [informazioni sulla risoluzione dei problemi](troubleshoot.md#upload-fails).

## Operazioni con più risorse {#work-with-multiple-assets}

Gli utenti possono utilizzare e gestire facilmente più risorse mediante azioni quali il caricamento di tutte le modifiche in una sola volta o il caricamento di cartelle nidificate in pochi clic.

### Sfoglia cartelle grandi {#browse-large-folders}

Quando lavorate con cartelle contenenti molte risorse, scorrete per visualizzare altre risorse. Per scorrere utilizzando la tastiera, premere più volte il tasto Tab per selezionare la risorsa in alto. Osservate come la risorsa evidenziata sia visibile quando è selezionata. Ora usate il tasto freccia giù per scorrere l’elenco delle risorse.

### Azioni rapide per le risorse selezionate {#quick-actions-for-selected-assets}

Fate clic sulla miniatura di alcune risorse per selezionarle. Per selezionare tutte le risorse, fate clic sulla casella di controllo nella barra superiore dell&#39;app. Il set di azioni applicabili a tutte le risorse selezionate collettivamente viene visualizzato in una barra degli strumenti nella parte inferiore dell’app.

![La barra degli strumenti in basso mostra le azioni relative alle ](assets/actions_bottom_toolbar1_da2.png "risorse selezionate. La barra degli strumenti in basso mostra le azioni comuni per le risorse selezionate")

![Nessuna azione nella barra degli strumenti in assenza di azioni comuni per la ](assets/actions_bottom_toolbar2_da2.png "selezioneNessuna azione nella barra degli strumenti in assenza di azioni comuni per la selezione")

Le azioni disponibili nella barra degli strumenti nella parte inferiore dipendono dallo stato dei file selezionati. Ad esempio, se selezionate solo i file **[!UICONTROL Edited Locally]**, viene visualizzata l&#39;icona **[!UICONTROL Upload Changes]**. Se si seleziona un insieme di **[!UICONTROL Edited locally]** e **[!UICONTROL Cloud only]**, l&#39;azione **[!UICONTROL Upload Changes]** non è disponibile.

### Trova tutte le immagini modificate {#find-all-edited-images}

L&#39;applicazione fornisce una vista, denominata **[!UICONTROL Edited locally]**, per consentirvi di accedere rapidamente a tutti i file scaricati localmente (tramite [!UICONTROL Open] o [!UICONTROL Edit] azioni) e quindi modificati. L&#39;app consente di selezionare tutte le risorse modificate localmente e caricare le modifiche in pochi clic. Questa visualizzazione mostra anche le risorse modificate localmente che presentano un conflitto di modifica.

![Filtrare per visualizzare tutte le ](assets/edited_locally_filter_da2.png "risorse modificate localmenteFiltrare per visualizzare tutte le risorse modificate localmente, ad esempio per il caricamento in blocco delle modifiche")

### Caricamento in blocco delle risorse {#bulk-upload-assets}

Gli utenti o l&#39;organizzazione, come fotografi o agenzie creative, possono creare numerose risorse locali in scenari diversi, ad esempio scatti fotografici, ritocchi o selezioni da un set più ampio esterno a [!DNL Experience Manager]. Possono caricare queste grandi cartelle locali su [!DNL Assets] direttamente dall&#39;app desktop. Le gerarchie di cartelle vengono mantenute e vengono caricate tutte le sottocartelle nidificate e le risorse incluse. Le risorse caricate sono immediatamente disponibili per l’uso anche ad altri utenti dello stesso server. Le risorse vengono caricate in background, pertanto l’operazione non è legata a una sessione del browser Web.

![Caricamento in blocco di più cartelle locali dal desktop per caricare in  [!DNL Experience Manager]](assets/upload_local_folders_da2.png "blocco più cartelle locali dal desktop  Experience Manager")

Dopo il caricamento, se le modifiche previste non vengono riportate nell&#39;app, fate clic sull&#39;icona di aggiornamento ![Icona di aggiornamento](assets/do-not-localize/refresh.png).

>[!NOTE]
>
>Non utilizzate la funzionalità di caricamento per migrare le risorse tra due distribuzioni [!DNL Experience Manager]. Vedete la [guida alla migrazione](https://experienceleague.adobe.com/docs/experience-manager-65/assets/administer/assets-migration-guide.html).

### Elenco delle attività trasferite {#list-of-transferred-assets}

Per visualizzare l&#39;elenco delle risorse trasferite in una determinata sessione, consultate [Caricare le risorse in [!DNL Experience Manager]](#upload-and-add-new-assets-to-aem).

## Flusso di lavoro avanzato: inizia dall&#39;interfaccia [!DNL Assets] Web {#adv-workflow-start-from-aem-ui}

Se necessario, avviate il flusso di lavoro dall’interfaccia Web Risorse. L&#39;app desktop si integra con la [!DNL Experience Manager] per riprendere il controllo quando richiesto tramite Azioni desktop.

Un caso particolare di avvio del flusso di lavoro dall’interfaccia Web è rappresentato dall’individuazione delle risorse. La barra di ricerca Omniture nell’interfaccia utente Risorse offre un’esperienza di ricerca avanzata e avanzata. Potrebbe essere necessario individuare prima una risorsa desiderata sul Web e avviare il flusso di lavoro nell&#39;app utilizzando [!UICONTROL Desktop Actions]. Alcuni esempi di casi includono il filtraggio dei risultati di ricerca utilizzando facet, l’individuazione di una risorsa specifica con licenza da  Adobe Stock o una personalizzazione implementata dall’organizzazione che consente una migliore individuazione dall’interfaccia Web.

La funzionalità dell’app desktop viene utilizzata quando tentate le seguenti azioni sull’interfaccia Web di Assets:

* [!UICONTROL Desktop Actions] che consente [!UICONTROL Open], [!UICONTROL Edit] e [!UICONTROL Reveal]
* [!UICONTROL Upload folder]
* [!UICONTROL Check-out] o [!UICONTROL check-in]

Ad esempio, le azioni sull&#39;interfaccia Web disponibili per una risorsa estratta nell&#39;app sono [!UICONTROL Open], [!UICONTROL Reveal] e [!UICONTROL Check-in].

![Azioni desktop nell&#39; [!DNL Experience Manager] interfaccia ](assets/assets_web_actions_da2.png "WebAzioni desktop nell&#39;interfaccia Web del Experience Manager ")

>[!NOTE]
>
>Il browser potrebbe richiedere di consentire il lancio di [!DNL Adobe Experience Manager] Desktop. Per un trasferimento ininterrotto dal browser all&#39;app, seleziona la casella di controllo appropriata per consentire sempre all&#39;app di prendere il controllo.

Non è possibile trovare le informazioni o il flusso di lavoro seguenti utilizzando l&#39;interfaccia Web. Utilizzate l&#39;app desktop perché l&#39;interfaccia Web non tiene traccia delle modifiche locali e non è a conoscenza dei seguenti elementi:

* File modificati localmente.
* File con un conflitto di modifica e con un modo per risolverlo.
* Caricate le modifiche locali in [!DNL Experience Manager].
* Vari stati dei file disponibili localmente.

Al contrario, puoi aprire la risorsa nell&#39;interfaccia Web a partire dall&#39;app desktop utilizzando l&#39;azione **[!UICONTROL Open In Web]**.

## Flusso di lavoro avanzato: collaborare sugli stessi file ed evitare conflitti di modifica {#adv-workflow-collaborate-avoid-conflicts}

Negli ambienti collaborativi, più utenti possono lavorare sullo stesso set di risorse che possono causare conflitti di versione. Per prevenire i conflitti, attenersi alle seguenti procedure ottimali:

* Non modificate le risorse facendo clic su [!UICONTROL Open]. Non modificate le risorse scaricate localmente aprendo dalla cartella del file system. Altri utenti non sanno che la risorsa è in fase di modifica.
* Per modificare una risorsa, fate sempre clic su [!UICONTROL Edit]. Consente di aprire la risorsa nell’applicazione nativa e di aggiungere un’icona a forma di lucchetto alla risorsa, in modo che gli altri utenti siano a conoscenza del fatto che la risorsa è in fase di modifica.
* Fare clic su [!UICONTROL Toggle Check-in] se si inizia accidentalmente la modifica senza fare clic su [!UICONTROL Edit]. In questo modo alla risorsa viene aggiunta un’icona a forma di lucchetto. Anche se prevedete di modificare una risorsa in un secondo momento ma desiderate evitare che altri la modifichino, fate clic su [!UICONTROL Toggle Check-in] per bloccare la risorsa.
* Prima di modificare una risorsa, accertatevi che gli altri utenti non la stiano modificando. Individuate l’icona Blocca sulla risorsa.
* Dopo aver completato le modifiche, caricate tutte le modifiche, quindi archiviate la risorsa.

![Stati di modifica ](assets/edits_conflicts_status_da2.png "conflittiStati di modifica dei conflitti")

Se una risorsa scaricata localmente viene aggiornata sul server [!DNL Experience Manager], l&#39;app visualizza uno stato **[!UICONTROL Modified remotely]**. Per rimuovere la copia locale o aggiornare la copia locale, fare clic rispettivamente su [!UICONTROL Remove] o [!UICONTROL Update]. I collegamenti presenti nella finestra di dialogo consentono di visualizzare entrambe le versioni della risorsa.

![Opzioni per risolvere il conflitto quando la risorsa viene ](assets/modified_remotely_dialog_da2.png "modificata in remotoOpzioni per risolvere il conflitto quando la risorsa viene modificata in remoto")

Se anche una risorsa che state modificando localmente viene aggiornata sul server senza che l&#39;utente ne sia a conoscenza, l&#39;app visualizza uno stato **[!UICONTROL Editing Conflict]**. Potete mantenere una serie di modifiche, mantenendo gli aggiornamenti (fate clic su **[!UICONTROL Keep Mine]**) ed eliminare la modifica dell&#39;altro utente oppure rispettare gli aggiornamenti dell&#39;altro utente ed eliminare i vostri (**[!UICONTROL Overwrite Mine]**).

![Opzioni per risolvere un ](assets/editing_conflict_dialog_da2.png "conflitto di modificaOpzioni per risolvere un conflitto di modifica")

## Flusso di lavoro avanzato: inserire e collegare risorse nel file  InDesign {#adv-workflow-place-assets-indesign}

Quando utilizzate l&#39;app desktop [!DNL Experience Manager] per aprire i file con risorse collegate, le risorse vengono pre-scaricate e vengono visualizzate nelle applicazioni native. Affinché questo flusso di lavoro funzioni, l&#39;applicazione nativa deve supportare il posizionamento di collegamenti alle risorse locali e [!DNL Experience Manager] deve supportare la risoluzione di questi collegamenti nei file binari ai riferimenti sul lato server.

[!DNL Experience Manager] l&#39;app desktop supporta questo flusso di lavoro con alcune applicazioni desktop Adobe Creative Cloud e formati di file selezionati  Adobe InDesign,  Adobe Illustrator e  Adobe Photoshop. Il flusso di lavoro consente di lavorare in modo efficiente con i file di Creative Cloud supportati. Pertanto, se l&#39;utente A inserisce alcune risorse in un file InDesign  e lo archivia in [!DNL Experience Manager], l&#39;utente B vede le risorse nel file InDesign  anche se le risorse non fanno parte del file. Le risorse vengono scaricate localmente sul computer dell’utente B.

>[!NOTE]
>
>L&#39;app desktop può essere mappata su qualsiasi unità in Windows. Tuttavia, per le operazioni lisce, non modificare la lettera di unità predefinita. Se gli utenti della stessa organizzazione utilizzano lettere di unità diverse, non possono vedere le risorse inserite da altri. Le risorse inserite non vengono recuperate quando il percorso cambia. Le risorse inserite continuano a essere inserite nel file binario (ad esempio, INDD) e non vengono rimosse.

Per conoscere i limiti di questo flusso di lavoro, consultare i [Requisiti di sistema e le versioni supportate](release-notes.md#system-requirements-and-prerequisites-v2).

Per provare questo flusso di lavoro con una risorsa immagine e  InDesign, effettuate le seguenti operazioni:

1. Tenete a portata di mano un file INDD con le risorse inserite in [!DNL Experience Manager]. Per informazioni su come creare tale file INDD, vedere [Inserimento di elementi grafici](https://helpx.adobe.com/indesign/using/placing-graphics.html).
1. Dall&#39;interno dell&#39;app desktop, **[!UICONTROL Edit]** il file INDD con le risorse inserite in [!DNL Experience Manager].
1. L&#39;app scarica sia il file InDesign  che le risorse collegate. Quando  InDesign apre il documento, i collegamenti vengono risolti, le risorse vengono scaricate e le risorse vengono visualizzate nel documento  InDesign.
1. Per inserire un nuovo elemento grafico nel file InDesign , utilizzate l&#39;azione **[!UICONTROL Reveal File]** sulla risorsa. L’azione scarica la risorsa localmente e apre il percorso di condivisione di rete locale in Esplora risorse o nel Finder di Mac.
1. Inserite la risorsa rivelata nel documento InDesign . Viene creato un collegamento nel documento.
1. Una volta completate le modifiche nel documento InDesign , salvatelo e caricatelo in [!DNL Experience Manager] utilizzando l&#39;app desktop.

## Flusso di lavoro avanzato: scaricare le risorse localmente {#adv-workflow-download-assets-locally}

L&#39;app scarica le risorse dal server [!DNL Experience Manager] locale sul file system in molti scenari. I download utilizzano larghezza di banda e spazio su disco. La conoscenza degli scenari consente di ottimizzare il tempo di attesa per il completamento dei download.

Le risorse vengono scaricate dall&#39;interno dell&#39;app on-demand. Consultate [Scaricare risorse](#download-assets).

Quando utilizzate l&#39;azione [!UICONTROL Open] per aprire una risorsa in un&#39;applicazione desktop nativa, la risorsa viene scaricata localmente se non è già disponibile localmente. Consultate [Aprire le risorse](#openondesktop-v2).

Quando rivelate il percorso di una risorsa o di una cartella dall&#39;interno dell&#39;app, la risorsa o la cartella viene prima scaricata localmente e quindi aperta sul computer nella condivisione di rete locale. Consultate [Aprire le risorse](#openondesktop-v2).

Quando utilizzate l&#39;azione [!UICONTROL Edit] per modificare una risorsa in un&#39;applicazione desktop nativa, la risorsa viene scaricata localmente se non è già disponibile localmente. Consultate [Modificare le risorse e caricare le risorse aggiornate in [!DNL Experience Manager]](#edit-assets-upload-updated-assets).

Se l&#39;app è installata e autorizzata, completa le azioni quando si utilizza [!UICONTROL Desktop Actions] dall&#39;interfaccia Web [!DNL Experience Manager]. L&#39;app scarica prima la risorsa e quindi completa l&#39;azione.
