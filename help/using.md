---
title: Utilizzo [!DNL Experience Manager] app desktop
description: Utilizzo [!DNL Adobe Experience Manager] app desktop, per lavorare con [!DNL Adobe Experience Manager] Risorse DAM direttamente dal desktop Win o Mac e utilizzate in altre applicazioni.
mini-toc-levels: 1
feature: Desktop App,Asset Management
exl-id: fa19d819-231a-4a01-bfd2-6bba6fec2f18
source-git-commit: ca04b64e1ebfee4b677fcc5ef84b0e8fd9950d17
workflow-type: tm+mt
source-wordcount: '4054'
ht-degree: 0%

---

# Utilizzo [!DNL Adobe Experience Manager] app desktop {#use-aem-desktop-app-v2}

Utilizza la [!DNL Adobe Experience Manager] app desktop, per accedere facilmente alle risorse digitali memorizzate in [!DNL Adobe Experience Manager] Archivio DAM sul desktop locale e utilizza queste risorse in qualsiasi applicazione desktop. Puoi aprire le risorse nelle applicazioni desktop e modificarle localmente. Puoi caricare nuovamente le modifiche in [!DNL Experience Manager] con controllo della versione, per condividere gli aggiornamenti con altri utenti. Puoi anche caricare nuovi file e gerarchie di cartelle in [!DNL Experience Manager], creare cartelle ed eliminare risorse o cartelle da [!DNL Experience Manager] DAM.

L’integrazione consente a vari ruoli dell’organizzazione di gestire centralmente le risorse in [!DNL Experience Manager Assets] e per accedere alle risorse sul desktop locale nelle applicazioni native sul sistema operativo Windows o Mac.

Quando apri l&#39;applicazione dopo la disconnessione o per la prima volta, fornisci l&#39;URL della [!DNL Experience Manager] nel formato `https://[aem-server-url]:[port]/`. Quindi seleziona la [!UICONTROL Connect] opzione . Immetti le credenziali per collegare l’app al server.

Le attività chiave eseguite mediante la [!DNL Adobe Experience Manager] le app desktop sono:

![Flussi di lavoro e attività eseguibili utilizzando [!DNL Experience Manager] app desktop](assets/aem_desktop_app_usecases_v2.png "Flussi di lavoro e attività eseguibili utilizzando [!DNL Adobe Experience Manager] app desktop")
Scarica [questo](assets/aem_desktop_app_usecases_print.pdf) file PDF pronto per la stampa.

## Funzionamento dell’app desktop {#how-app-works2}

Prima di iniziare a utilizzare l&#39;applicazione, comprendere [Funzionamento dell’app](release-notes.md#how-app-works). Inoltre, acquisisci familiarità con i seguenti termini:

* **[!UICONTROL Desktop Actions]**: Dall’interfaccia web Assets, direttamente in un browser, puoi esplorare le posizioni delle risorse o estrarre e aprire la risorsa per la modifica nell’applicazione desktop nativa. Queste azioni sono disponibili dall’interfaccia web e utilizzano le funzionalità dell’app desktop. Vedi [come abilitare le azioni desktop](using.md#desktopactions-v2).

* Lo stato del file è **[!UICONTROL Cloud Only]**: Tali risorse non vengono scaricate sul computer locale e sono disponibili su [!DNL Experience Manager] solo server.

* Lo stato del file è **[!UICONTROL Available locally]**: Le risorse vengono scaricate e disponibili nel computer locale così come sono. Le risorse non vengono modificate.

* Lo stato del file è **[!UICONTROL Edited locally]**: Tali risorse vengono modificate localmente e le modifiche rimangono nel [!DNL Experience Manager] server. Dopo il caricamento, lo stato cambia in [!UICONTROL Available locally]. Vedi [modificare le risorse](using.md#edit-assets-upload-updated-assets).

* Lo stato del file è **[!UICONTROL Editing conflict]**: Se tu e altri utenti modifichi una risorsa contemporaneamente, l’app indica che si è verificato un conflitto di modifica. L’app fornisce anche opzioni per conservare o eliminare le modifiche. Vedi [come evitare la modifica dei conflitti](using.md#adv-workflow-collaborate-avoid-conflicts).

* Lo stato del file è **[!UICONTROL Modified remotely]**: L’app indica se una risorsa scaricata è stata modificata nel [!DNL Experience Manager] server. L’app offre anche la possibilità di scaricare la versione più recente e aggiornare la copia locale. Vedi [come evitare la modifica dei conflitti](using.md#adv-workflow-collaborate-avoid-conflicts).

* **[!UICONTROL Check-out]**: Se si sta modificando un file o si intende modificarlo, è necessario attivare lo stato di estrazione. Aggiunge un’icona a forma di lucchetto alla risorsa nell’app e [!DNL Experience Manager] interfaccia web. L’icona a forma di lucchetto indica ad altri utenti di evitare di modificare simultaneamente la stessa risorsa, causando un conflitto di modifica.

* **[!UICONTROL Check-in]**: Contrassegna la risorsa come sicura da consentire ad altri utenti di modificarla senza causare un conflitto di modifica. Quando carichi le modifiche, l’icona a forma di lucchetto viene rimossa automaticamente. Se si attiva lo stato del check-in, l&#39;icona del blocco viene rimossa anche se si consiglia di non effettuare manualmente il check-in senza caricare le modifiche. Se scarti le modifiche, attiva manualmente il check-in.

* **[!UICONTROL Open]** azione: Apri la risorsa per visualizzarne l’anteprima nell’applicazione nativa. Si sconsiglia di modificare la risorsa utilizzando questa azione, in quanto non estrae la risorsa e altri utenti possono apportare modifiche che portano a conflitti di modifica.

* **[!UICONTROL Edit]** azione: Utilizza l’azione per modificare l’immagine. Clic [!UICONTROL Edit] estrae automaticamente la risorsa e aggiunge un’icona a forma di lucchetto sulla risorsa. Dopo aver fatto clic su Modifica, se non desideri modificare la risorsa, fai clic su [!UICONTROL Toggle check-in]. Per eliminare, rinominare o spostare le risorse in [!DNL Experience Manager] Gerarchia delle cartelle DAM, utilizza [!DNL Experience Manager] azioni dell’interfaccia web e non l’azione di modifica.

* **[!UICONTROL Download]** azione: Scarica la risorsa sul computer locale. È possibile scaricare le risorse ora e modificarle in un secondo momento; lavora offline e carica le modifiche in un secondo momento. Le risorse vengono scaricate in una cartella cache del file system.

* **[!UICONTROL Reveal File]** o **[!UICONTROL Reveal Folder]** azione: Mentre le risorse vengono scaricate in una cartella di cache locale, l’app imita un’unità di rete locale e fornisce un percorso locale per ciascuna risorsa. Per conoscere questo percorso, utilizza l’opzione di visualizzazione appropriata nell’app. È necessaria un’azione Mostra per inserire risorse nell’applicazione Creative Cloud. Vedi [inserire risorse](using.md#place-assets-in-native-documents).

* **[!UICONTROL Open In Web]** azione: Per visualizzare la risorsa in [!DNL Experience Manager] interfaccia web, aprilo sul web. Puoi avviare più flussi di lavoro da [!DNL Experience Manager] come l’aggiornamento dei metadati o l’individuazione delle risorse.

* **[!UICONTROL Delete]** azione: Elimina la risorsa dalla [!DNL Experience Manager] Archivio DAM. L’azione elimina la copia originale della risorsa sul server di Experience Manager. Se desideri eliminare solo le modifiche alla risorsa locale, consulta [scartare le modifiche](using.md#edit-assets-upload-updated-assets).

* **[!UICONTROL Upload Changes]**: L’app desktop carica la risorsa aggiornata solo quando viene caricata in modo esplicito in [!DNL Experience Manager] server. Quando salvi le modifiche, queste vengono salvate solo sul computer locale. Al momento del caricamento, la risorsa viene automaticamente archiviata e l&#39;icona di blocco viene rimossa. Vedi [modificare le risorse](using.md#edit-assets-upload-updated-assets).

## Abilita azioni desktop in [!DNL Experience Manager] interfaccia web {#desktopactions-v2}

Da all’interno di [!DNL Assets] interfaccia utente in un browser, puoi esplorare le posizioni delle risorse o estrarre e aprire la risorsa per la modifica nell’applicazione desktop. Queste opzioni sono denominate [!UICONTROL Desktop Actions] e non sono abilitati per impostazione predefinita. Per abilitarlo, segui questi passaggi.

1. In [!DNL Assets] nella console, fai clic su **[!UICONTROL User]** dalla barra degli strumenti.
1. Fai clic su **[!UICONTROL My Preferences]** per visualizzare **[!UICONTROL Preferences]** finestra di dialogo.

1. In [!UICONTROL User Preferences] finestra di dialogo, seleziona **[!UICONTROL Show Desktop Actions For Assets]**, quindi fai clic su **[!UICONTROL Accept]**.


   ![Seleziona Mostra azioni desktop per risorse per abilitare le azioni desktop](assets/enable_desktop_actions.png)

   *Figura: Seleziona [!UICONTROL Show Desktop Actions For Assets] per abilitare le azioni desktop.*

## Sfogliare, cercare e visualizzare in anteprima le risorse {#browse-search-preview-assets}

È possibile sfogliare, cercare e visualizzare in anteprima le risorse disponibili nella [!DNL Experience Manager] repository, tutto dall&#39;applicazione desktop. Prova quanto segue nell&#39;app:

1. Individua una cartella e visualizza alcune informazioni di base sulle risorse disponibili nella cartella, insieme a miniature di tutte le risorse.

   ![Sfoglia i file e le cartelle DAM](assets/browse_folder_da2.png "Sfoglia i file e le cartelle DAM")

1. Per visualizzare ulteriori informazioni e una miniatura più grande di una singola risorsa, fai clic sul nome del file.

   ![Visualizzare un’anteprima più ampia di una risorsa e delle azioni](assets/large_preview_actions_da2.png "Visualizzare un’anteprima più ampia di una risorsa e delle azioni")

1. Fai clic su **[!UICONTROL Open]** o **[!UICONTROL Edit]** per scaricare il file localmente e visualizzarlo o modificarlo nell&#39;applicazione nativa, rispettivamente.
1. Cerca utilizzando le parole chiave per trovare una risorsa correlata nel [!DNL Experience Manager] archivio. Utilizzo `?` e `*` come caratteri jolly. Questi caratteri jolly sostituiscono rispettivamente un singolo carattere o più caratteri. Filtrare e ordinare i risultati in base alle esigenze.

   ![Ricerca di esempio utilizzando il carattere jolly asterisco](assets/search_wildcard_da2.png "Ricerca di esempio utilizzando il carattere jolly asterisco")

   ![Un altro esempio di ricerca utilizzando il carattere jolly asterisco](assets/search_wildcard2_da2.png "Un altro esempio di ricerca con diversa posizione del carattere jolly asterisco")

>[!NOTE]
>
>L’app visualizza le risorse facendo corrispondere i criteri di ricerca in più campi di metadati e non solo il titolo della risorsa o il nome del file.

## Scaricare le risorse {#download-assets}

Puoi scaricare le risorse sul file system locale. L’app recupera le risorse da [!DNL Experience Manager] e salva la stessa copia nel file system locale.

Fai clic su ![Icona Altre opzioni](assets/do-not-localize/more2_da2.png) per opzioni e fai clic su ![Icona di download](assets/do-not-localize/download_cloud_da2.png) da scaricare.

![Opzione di download per una risorsa](assets/download_option_da2.png "Opzione di download per una risorsa")

>[!NOTE]
>
>Durante il download o il caricamento di uno o più file di grandi dimensioni, l&#39;applicazione disattiva le azioni sulle risorse e le cartelle. Le azioni sono disponibili al termine del download o del caricamento.

Il download di più risorse potrebbe causare prestazioni scadenti se le dimensioni della coda sono grandi o se si verificano problemi di rete. Inoltre, è possibile mettere in coda inconsapevolmente molte risorse per il download quando si scarica una cartella. Per evitare lunghi tempi di attesa, l’app limita il numero di risorse scaricate contemporaneamente. Per informazioni su come configurarlo, consulta [Impostare le preferenze](install-upgrade.md#set-preferences). Anche al di sotto di questo limite, l&#39;app può a volte richiedere una conferma prima di scaricare una cartella apparentemente grande.

![L&#39;app conferma il download di un numero relativamente elevato di risorse](assets/download_confirmation_da2.png "L&#39;app conferma il download di un numero relativamente elevato di risorse")

Se sono selezionate e scaricate cartelle, l’applicazione scarica solo le risorse memorizzate direttamente nelle cartelle in [!DNL Experience Manager]. Non scarica automaticamente le risorse dalle sottocartelle.

## Apri le risorse sul desktop {#openondesktop-v2}

Puoi aprire le risorse remote da visualizzare nell’applicazione nativa. Le risorse vengono scaricate in una cartella locale e avviate nell’applicazione nativa associata al formato di file. È possibile modificare l&#39;applicazione nativa per aprire tipi di file (estensioni) specifici in Mac o Windows.

Fai clic su **[!UICONTROL Open]** dal menu delle risorse. La risorsa viene scaricata localmente e aperta nell’applicazione nativa. Controlla l’avanzamento del download e la velocità di trasferimento delle risorse di grandi dimensioni nella barra di stato.

<!-- ![Download progress bar for large-sized assets](assets/download_status_bar_da2.png "Download progress bar for large-sized assets")
-->

>[!NOTE]
>
>Se le modifiche previste non vengono riportate nell&#39;app, fai clic sull&#39;icona di aggiornamento ![Icona Aggiorna](assets/do-not-localize/refresh.png) o fai clic con il pulsante destro del mouse nell’interfaccia dell’app e fai clic su **[!UICONTROL Refresh]**. Le azioni non sono disponibili quando sono in corso download o caricamenti di dimensioni maggiori.

Per aprire la cartella di download locale di una risorsa, fai clic su ![Icona Altre azioni](assets/do-not-localize/more2_da2.png) e fai clic su ![Icona Rivela](assets/do-not-localize/reveal_action2_da2.png) **[!UICONTROL Reveal File]** azione.

## Utilizzare o inserire risorse in documenti nativi {#place-assets-in-native-documents}

In alcuni casi, ad esempio quando si inserisce una risorsa in un documento nativo, si accede a un file in Esplora risorse o nel Finder di Mac. Per ottenere il percorso del file system del file scaricato localmente, utilizza il ![Icona Rivela](assets/do-not-localize/reveal_action2_da2.png) **[!UICONTROL Reveal File]** opzione .

![Mostra azione File per una risorsa](assets/revealfile_action_da2.png "Mostra azione File per una risorsa")

Fai clic su **[!UICONTROL Reveal File]** oppure **[!UICONTROL Reveal Folder]** in una cartella, per aprire Esplora risorse o Mac Finder con il file o la cartella preselezionati nel computer locale. L’opzione è utile per, ad esempio, posizionare il [!DNL Experience Manager] file nelle applicazioni native che supportano il posizionamento o il collegamento di file locali. Per vedere come inserire file in Adobe InDesign, vedi [Inserimento di elementi grafici](https://helpx.adobe.com/indesign/using/placing-graphics.html).

La **[!UICONTROL Reveal File]** apre una condivisione di rete locale che visualizza solo le risorse disponibili localmente, ovvero le risorse che sono state rivelate, scaricate o aperte/modificate utilizzando l’app. La condivisione di rete locale non carica alcuna modifica in [!DNL Experience Manager]. Per caricare le modifiche, utilizza esplicitamente **[!UICONTROL Upload Changes]** o **[!UICONTROL Upload]** nell’app.

>[!NOTE]
>
>Per compatibilità con le versioni precedenti con [!DNL Experience Manager] app desktop v1.x, i file rivelati sono serviti da una condivisione di rete locale, esponendo solo i file disponibili localmente. I percorsi desktop dei file rivelati sono gli stessi dei percorsi creati dall’app v1.x.

>[!CAUTION]
>
>Non utilizzare **[!UICONTROL Reveal File]** per modificare le risorse nelle applicazioni native. Invece, utilizza la **[!UICONTROL Edit]** azioni. Per ulteriori informazioni, consulta [Flusso di lavoro avanzato: collaborare sugli stessi file ed evitare conflitti di modifica](#adv-workflow-collaborate-avoid-conflicts).

## Modifica le risorse e carica le risorse aggiornate in [!DNL Experience Manager] {#edit-assets-upload-updated-assets}

Apri le risorse per la modifica quando desideri apportare modifiche e carica le risorse aggiornate sul server AEMexperience ManagerEM. Per evitare conflitti con le modifiche apportate da altri utenti, utilizza l’app per avviare una sessione di modifica. Prima di iniziare la modifica, accertati che la risorsa non disponga di un’icona a forma di lucchetto, ovvero che un altro utente non stia modificando la risorsa.

Per modificare una risorsa, cerca la risorsa o sfoglia fino alla sua posizione. Fai clic su ![Icona Altro](assets/do-not-localize/more2_da2.png) e fai clic su **[!UICONTROL Edit]**.

Utilizzo **[!UICONTROL Toggle Check-out]** per bloccare la risorsa per evitare conflitti con le modifiche di altri utenti in entrambe le situazioni:

* Hai iniziato a modificare una risorsa senza prima estrarla (ad esempio, aprendola).
* Inizierai presto a modificare una risorsa e non desideri che altri utenti la modifichino.

Dopo aver apportato le modifiche, l’app visualizza l’ **[!UICONTROL Edited Locally]** stato delle risorse modificate. Tutte le modifiche salvate nelle risorse sono di solo locale finché non carichi le modifiche in [!DNL Experience Manager]. Per caricare una o più risorse una per una, fai clic su **[!UICONTROL Upload Changes]** dalle opzioni di una risorsa. Crea una versione della risorsa in [!DNL Experience Manager]. Utilizzo dell’interfaccia Web di [!DNL Assets], puoi visualizzare la cronologia delle risorse nella sezione [Vista Timeline](https://experienceleague.adobe.com/docs/experience-manager-65/assets/using/activity-stream.html).

![Opzione Carica modifiche nell’app](assets/upload_changes_single1_da2.png "Opzione Carica modifiche nell’app")

![Opzione Carica modifiche quando si visualizza un’anteprima di grandi dimensioni di una risorsa](assets/upload_changes_single2_da2.png "Opzione Carica modifiche quando si visualizza un’anteprima di grandi dimensioni di una risorsa")

Per le best practice sull’editing collaborativo, consulta [Flusso di lavoro avanzato: collaborare sugli stessi file ed evitare conflitti di modifica](#adv-workflow-collaborate-avoid-conflicts).

Nei casi seguenti, puoi eliminare le modifiche e le modifiche apportate alla risorsa locale. Clic **[!UICONTROL Discard Changes]**.

* Se non desideri salvare le modifiche locali in [!DNL Experience Manager].
* Dopo aver salvato alcune modifiche, inizia a apportare modifiche alla risorsa originale.
* Interrompi la modifica della risorsa in quanto non è più necessaria.

Se necessario, attiva/disattiva il check-out. La risorsa aggiornata viene rimossa dalla cartella della cache locale e viene scaricata nuovamente quando la modifichi o la apri.

## Carica e aggiungi nuove risorse a [!DNL Experience Manager] {#upload-and-add-new-assets-to-aem}

Gli utenti possono aggiungere nuove risorse all’archivio DAM. Ad esempio, puoi essere un fotografo di agenzia o un appaltatore che desidera aggiungere un gran numero di foto da un servizio fotografico al [!DNL Experience Manager] archivio. Per aggiungere nuovo contenuto a [!DNL Experience Manager], seleziona ![opzione carica su cloud](assets/do-not-localize/upload_to_cloud_da2.png) nella barra superiore dell’app. Individua i file delle risorse nel file system locale e fai clic su **[!UICONTROL Select]**. In alternativa, per caricare le risorse, trascina i file o le cartelle nell’interfaccia dell’applicazione. In Windows, se trascini risorse in una cartella dell’app, queste vengono caricate nella cartella . Se il caricamento richiede più tempo, l&#39;app visualizza una barra di avanzamento.

<!-- ![Download progress bar for large-sized assets](assets/upload_status_da2.png "Download progress bar for large-sized assets")
-->

Puoi caricare cartelle o singoli file dal file system locale. La gerarchia di una cartella viene mantenuta al momento del caricamento. Prima di caricare le risorse in blocco, consulta [Caricamenti in blocco](#bulk-upload-assets).

Per visualizzare l’elenco delle risorse trasferite in una determinata sessione, fai clic su **[!UICONTROL View]** > **[!UICONTROL Assets transfers]**. L&#39;elenco ti consente di visualizzare e verificare rapidamente i trasferimenti di file della sessione corrente.

![Elenco delle attività trasferite in una sessione particolare](assets/assets_transfered_da2.png "Elenco delle attività trasferite in una sessione particolare")

Puoi controllare la concorrenza di caricamento (accelerazione) in **[!UICONTROL Preferences]** > **[!UICONTROL Upload acceleration]** impostazione. Una maggiore concorrenza in genere consente caricamenti più rapidi, ma può richiedere un uso intensivo delle risorse e richiedere una maggiore potenza di elaborazione del computer locale. Se si verifica un sistema lento, effettua di nuovo un tentativo di caricamento utilizzando un valore inferiore di concorrenza.

>[!NOTE]
>
>L’elenco dei trasferimenti non è permanente e non è disponibile se esci dall’app e la riapri.

### Gestire i caratteri speciali nei nomi delle risorse {#special-characters-in-filename}

Nell’app legacy, i nomi dei nodi creati nell’archivio mantenevano gli spazi e la custodia dei nomi delle cartelle forniti dall’utente. Affinché l&#39;applicazione corrente emuli le regole di denominazione dei nodi dell&#39;app v1.10, abilita [!UICONTROL Use legacy conventions when creating nodes for assets and folders] in [!UICONTROL Preferences]. Vedi [preferenze app](/help/install-upgrade.md#set-preferences). Questa preferenza legacy è disabilitata per impostazione predefinita.

>[!NOTE]
>
>L’app modifica solo i nomi dei nodi nell’archivio utilizzando le seguenti convenzioni di denominazione. L’app mantiene la variabile `Title` della risorsa così come è.

<!-- TBD: Do NOT use this table.

| Where do characters occur | Characters | Legacy preference | Renaming convention | Example |
|---|---|---|---|---|
| In file name extension | `.` | Enabled or disabled | Retained as is | NA |
| File or folder name | `. / : [ ] | *` | Enabled or disabled | Replaced with a `-` (hyphen) | `myimage.jpg` remains as is and `my.image.jpg` changes to `my-image.jpg`. |
| Folder name | `% ; # , + ? ^ { } "` | Disabled | Replaced with a `-` (hyphen) | tbd |
| File name | `% # ? { } &` | Disabled | Replaced with a `-` (hyphen) | tbd |
| File name | Whitespaces | Enabled or disabled | Retained as is | NA |
| Folder name | Whitespaces | Disabled | Replaced with a `-` (hyphen) | tbd |
| File name | Uppercase characters | Disabled | Retained as is | tbd |
| Folder name | Uppercase characters | Disabled | Replaced with a `-` (hyphen) | tbd |
-->

| Caratteri ‡ | preferenza legacy nell’app | Quando si verifica nei nomi dei file | Quando si verifica nei nomi delle cartelle | Esempio |
|---|---|---|---|---|
| `. / : [ ] | *` | Abilitato o disattivato | Sostituito con `-` (trattino). A `.` (punto) nell’estensione del nome file viene mantenuto così come è. | Sostituito con `-` (trattino). | `myimage.jpg` rimane com&#39;è e `my.image.jpg` modifiche a `my-image.jpg`. |
| `% ; # , + ? ^ { } "` e spazi bianchi | ![icona deseleziona](assets/do-not-localize/deselect-icon.png) Disabilitato | Gli spazi bianchi vengono mantenuti | Sostituito con `-` (trattino). | `My Folder.` modifiche a `my-folder-`. |
| `# % { } ? & .` | ![icona deseleziona](assets/do-not-localize/deselect-icon.png) Disabilitato | Sostituito con `-` (trattino). | ND. | `#My New File.` modifiche a `-My New File-`. |
| Caratteri maiuscoli | ![icona deseleziona](assets/do-not-localize/deselect-icon.png) Disabilitato | Il casing viene mantenuto così com&#39;è. | È stato modificato in caratteri minuscoli. | `My New Folder` modifiche a `my-new-folder`. |
| Caratteri maiuscoli | ![icona a forma di selezione](assets/do-not-localize/selection-checked-icon.png) Abilitato | Il casing viene mantenuto così com&#39;è. | Il casing viene mantenuto così com&#39;è. | ND. |

† L&#39;elenco dei caratteri è un elenco separato da spazi bianchi.

<!-- TBD: Check if the following is to be included in the footnote.

Do not use &#92;&#92; in the names of files and &#92;&#116; &#38; in the names of folders. 
-->


<!-- TBD: Securing the below presentation of the same content in a comment.

**File names**

| Characters | Replaced by |
|---|---|
| &#35; &#37; &#123; &#63; &#125; &#38; &#46; &#47; &#58; &#91; &#124; &#93; &#42; | hyphen (-) |
| whitespaces | whitespaces are retained |
| capital case | casing is retained |

>[!CAUTION]
>
>Avoid using &#92;&#92; in file names.

**Folder names**

| Characters | Replaced by |
|---|---|
| Characters | Replaced by |
| &#37; &#59; &#35; &#44; &#43; &#63; &#94; &#123; &#123; &#34; &#46; &#47; &#59; &#91; &#93; &#124; &#42; | hyphen (-) |
| whitespaces | hyphen (-) |
| capital case | lower case |

>[!CAUTION]
>
>Avoid using &#92;&#92; &#92;&#116; &#38; in folder names.

>[!NOTE]
>
>If you enable [!UICONTROL Use legacy conventions when creating nodes for assets and folders] in app [!UICONTROL Preferences], then the app emulates v1.10 app behavior when uploading folders. In v1.10, the node names created in the repository respect spaces and casing of the folder names provided by the user. For more information, see [app Preferences](/help/install-upgrade.md#set-preferences).

-->

## Utilizzare più risorse {#work-with-multiple-assets}

Gli utenti possono facilmente lavorare con e gestire più risorse utilizzando azioni come il caricamento di tutte le modifiche contemporaneamente o il caricamento di cartelle nidificate in pochi clic.

### Sfoglia cartelle grandi {#browse-large-folders}

Quando lavori con cartelle contenenti molte risorse, scorri per visualizzare altre risorse. Per scorrere utilizzando la tastiera, premi alcune volte la scheda per selezionare la risorsa in alto. La risorsa evidenziata deve sapere quando è selezionata. Ora utilizza il tasto freccia giù per spostarsi all’interno dell’elenco delle risorse.

### Azioni rapide per le risorse selezionate {#quick-actions-for-selected-assets}

Fai clic sulla miniatura di alcune risorse per selezionarle. Per selezionare tutte le risorse, fai clic sulla casella di controllo nella barra superiore dell’app. Il set di azioni applicabili collettivamente a tutte le risorse selezionate viene visualizzato in una barra degli strumenti nella parte inferiore dell’app.

![La barra degli strumenti in basso mostra le azioni relative alle risorse selezionate](assets/actions_bottom_toolbar1_da2.png "La barra degli strumenti in basso mostra le azioni comuni per le risorse selezionate")

![Nessuna azione nella barra degli strumenti se non sono presenti azioni comuni per la selezione](assets/actions_bottom_toolbar2_da2.png "Nessuna azione nella barra degli strumenti se non sono presenti azioni comuni per la selezione")

Le azioni disponibili nella barra degli strumenti nella parte inferiore dipendono dallo stato dei file selezionati. Ad esempio, se selezioni solo **[!UICONTROL Edited Locally]** file, vedi **[!UICONTROL Upload Changes]** icona. Se selezioni una combinazione di **[!UICONTROL Edited locally]** e **[!UICONTROL Cloud only]**, **[!UICONTROL Upload Changes]** azione non disponibile.

### Trova tutte le immagini modificate {#find-all-edited-images}

L&#39;applicazione fornisce una visualizzazione, denominata **[!UICONTROL Edited locally]**, per consentirti di accedere rapidamente a tutti i file scaricati localmente (tramite [!UICONTROL Open] o [!UICONTROL Edit] azioni) e quindi modificate. L’app ti consente di selezionare tutte le risorse modificate localmente e caricarle con pochi clic. In questa vista vengono visualizzate anche le risorse modificate localmente che presentano un conflitto di modifica.

![Filtrare per visualizzare tutte le risorse modificate localmente](assets/edited_locally_filter_da2.png "Filtrare per visualizzare tutte le risorse modificate localmente, ad esempio per caricare in massa le modifiche")

### Caricamento in blocco delle risorse {#bulk-upload-assets}

Gli utenti o le organizzazioni, come fotografi o agenzie creative, possono creare numerose risorse locali in scenari quali fotografie, ritocchi o selezioni da un set più ampio fatto all&#39;esterno [!DNL Experience Manager]. Possono caricare queste grandi cartelle locali in [!DNL Assets] direttamente dall’app desktop. Le gerarchie di cartelle vengono mantenute e vengono caricate tutte le sottocartelle nidificate e le risorse incluse. Le risorse caricate sono immediatamente disponibili per l’utilizzo anche per altri utenti dello stesso server. Le risorse vengono caricate in background, pertanto l’operazione non è legata a una sessione del browser web.

![Caricamento in serie di più cartelle locali dal desktop in [!DNL Experience Manager]](assets/upload_local_folders_da2.png "Caricamento in serie di più cartelle locali dal desktop in Experience Manager")

Dopo il caricamento, se le modifiche previste non vengono riportate nell&#39;app, fai clic sull&#39;icona di aggiornamento ![Icona Aggiorna](assets/do-not-localize/refresh.png).

>[!NOTE]
>
>Non utilizzare la funzionalità di caricamento per eseguire la migrazione delle risorse tra due [!DNL Experience Manager] distribuzioni. Invece, vedi [guida alla migrazione](https://experienceleague.adobe.com/docs/experience-manager-65/assets/administer/assets-migration-guide.html).

### Elenco delle attività trasferite {#list-of-transferred-assets}

Per visualizzare l’elenco delle risorse trasferite in una determinata sessione, consulta [Caricare le risorse in [!DNL Experience Manager]](#upload-and-add-new-assets-to-aem).

## Flusso di lavoro avanzato: inizia dal [!DNL Assets] interfaccia web {#adv-workflow-start-from-aem-ui}

Se necessario, avvia il flusso di lavoro dall’interfaccia web Assets. L’app desktop si integra con [!DNL Experience Manager] da riprendere quando richiesto utilizzando le azioni desktop.

Un caso particolare di avvio di un flusso di lavoro dall’interfaccia web è l’individuazione delle risorse. La barra di ricerca Omnisearch nell’interfaccia utente Assets offre un’esperienza di ricerca avanzata e avanzata. Puoi prima individuare una risorsa desiderata sul web e quindi avviare il flusso di lavoro nell’app, utilizzando [!UICONTROL Desktop Actions]. Alcuni casi di esempio includono il filtraggio dei risultati della ricerca utilizzando i facet, l’individuazione di una risorsa specifica concessa in licenza da Adobe Stock o una personalizzazione implementata dalla tua organizzazione che consente una migliore individuazione dall’interfaccia web.

La funzionalità dell’app desktop viene utilizzata quando tenti le seguenti azioni sull’interfaccia web Assets:

* La [!UICONTROL Desktop Actions] che consente [!UICONTROL Open], [!UICONTROL Edit]e [!UICONTROL Reveal]
* [!UICONTROL Upload folder]
* [!UICONTROL Check-out] oppure [!UICONTROL check-in]

Ad esempio, le azioni nell’interfaccia web disponibili per una risorsa estratta nell’app sono [!UICONTROL Open], [!UICONTROL Reveal]e [!UICONTROL Check-in].

![Azioni desktop in [!DNL Experience Manager] interfaccia web](assets/assets_web_actions_da2.png "Azioni desktop nell’interfaccia Web di Experience Manager")

>[!NOTE]
>
>Il browser potrebbe richiedere di consentire il lancio di [!DNL Adobe Experience Manager] Desktop. Per un trasferimento ininterrotto dal browser all’app, seleziona la casella di controllo appropriata per consentire sempre all’app di prendere il controllo.

Non è possibile trovare le informazioni o il flusso di lavoro seguenti utilizzando l’interfaccia Web. Utilizza l’app desktop in quanto l’interfaccia web non tiene traccia delle modifiche locali e non è consapevole dei seguenti elementi:

* File modificati localmente.
* File che presentano un conflitto di modifica e il modo per risolverlo.
* Carica le modifiche locali in [!DNL Experience Manager].
* Vari stati dei file disponibili localmente.

Al contrario, puoi aprire la risorsa nell’interfaccia web a partire dall’app desktop utilizzando **[!UICONTROL Open In Web]** azione.

## Flusso di lavoro avanzato: collaborare sugli stessi file ed evitare conflitti di modifica {#adv-workflow-collaborate-avoid-conflicts}

Negli ambienti collaborativi, più utenti possono lavorare sullo stesso set di risorse che può causare conflitti nel controllo delle versioni. Per evitare i conflitti, segui queste best practice:

* Non modificare nessuna risorsa facendo clic su [!UICONTROL Open]. Non modificare le risorse scaricate localmente aprendo dalla cartella del file system. Altri utenti non sanno che la risorsa è in fase di modifica.
* Per modificare una risorsa, fai sempre clic su [!UICONTROL Edit]. Apre la risorsa nell’applicazione nativa e aggiunge un’icona a forma di lucchetto alla risorsa, in modo che gli altri utenti sappiano che la risorsa è in fase di modifica.
* Fai clic su [!UICONTROL Toggle Check-in] se si inizia accidentalmente a modificare senza fare clic su [!UICONTROL Edit]. In questo modo viene aggiunta un’icona a forma di lucchetto alla risorsa. Anche se in un secondo momento intendete modificare una risorsa ma volete evitare che altri la modifichino, fate clic su [!UICONTROL Toggle Check-in] per bloccare la risorsa.
* Prima di modificare una risorsa, accertati che altri utenti non la modifichino. Cerca l’icona Blocca sulla risorsa.
* Dopo aver completato le modifiche, carica tutte le modifiche e quindi archivia la risorsa.

![Stato dei conflitti di modifica](assets/edits_conflicts_status_da2.png "Stato dei conflitti di modifica")

Se una risorsa scaricata localmente viene aggiornata nella sezione [!DNL Experience Manager] server, l&#39;app visualizza un **[!UICONTROL Modified remotely]** stato. È possibile rimuovere la copia locale o aggiornare la copia locale facendo clic su [!UICONTROL Remove] o [!UICONTROL Update] rispettivamente. I collegamenti nella finestra di dialogo consentono di visualizzare entrambe le versioni della risorsa.

![Opzioni per risolvere il conflitto quando la risorsa viene modificata in remoto](assets/modified_remotely_dialog_da2.png "Opzioni per risolvere il conflitto quando la risorsa viene modificata in remoto")

Se anche una risorsa che stai modificando localmente viene aggiornata sul server senza che tu ne sia a conoscenza, l’app visualizza una **[!UICONTROL Editing Conflict]** stato. È possibile mantenere un set di modifiche, mantenendo gli aggiornamenti (fare clic su **[!UICONTROL Keep Mine]**) ed elimina le modifiche dell’altro utente o rispetta gli aggiornamenti dell’altro utente ed elimina i tuoi (**[!UICONTROL Overwrite Mine]**).

![Opzioni per risolvere un conflitto di modifica](assets/editing_conflict_dialog_da2.png "Opzioni per risolvere un conflitto di modifica")

## Flusso di lavoro avanzato: inserire e collegare risorse nel file InDesign {#adv-workflow-place-assets-indesign}

Quando utilizzi [!DNL Experience Manager] app desktop per aprire file con risorse collegate, le risorse vengono prescaricate e vengono visualizzate nelle applicazioni native. Affinché questo flusso di lavoro funzioni, l’applicazione nativa deve supportare il posizionamento di collegamenti alle risorse locali e [!DNL Experience Manager] deve supportare la risoluzione di questi collegamenti nei file binari ai riferimenti lato server.

[!DNL Experience Manager] l’app desktop supporta questo flusso di lavoro con alcune applicazioni desktop Adobe Creative Cloud e formati di file selezionati: Adobe InDesign, Adobe Illustrator e Adobe Photoshop. Il flusso di lavoro consente di lavorare in modo efficiente con i file di Creative Cloud supportati. Quindi, se l’utente A inserisce alcune risorse in un file InDesign e le archivia [!DNL Experience Manager], l’utente B vede le risorse nel file InDesign anche se le risorse non fanno parte del file . Le risorse vengono scaricate localmente sul computer dell’utente B.

>[!NOTE]
>
>L&#39;app desktop può essere mappata su qualsiasi unità in Windows. Tuttavia, per le operazioni lisce, non modificare la lettera di unità predefinita. Se gli utenti della stessa organizzazione utilizzano lettere di unità diverse, non possono vedere le risorse posizionate da altri. Le risorse inserite non vengono recuperate quando il percorso cambia. Le risorse inserite continuano a trovarsi nel file binario (ad esempio INDD) e non vengono rimosse.

Per conoscere le limitazioni di questo flusso di lavoro, consulta la sezione [requisiti di sistema e versioni supportate](release-notes.md).

Per provare questo flusso di lavoro con una risorsa immagine e InDesign, segui questi passaggi:

1. Mantieni a portata di mano un file INDD con le risorse inserite in [!DNL Experience Manager]. Per sapere come creare un file INDD di questo tipo, vedi [Inserimento della grafica](https://helpx.adobe.com/indesign/using/placing-graphics.html).
1. Dall’app desktop, **[!UICONTROL Edit]** il file INDD con le risorse inserite in [!DNL Experience Manager].
1. L’app scarica sia il file InDesign che le risorse collegate. Quando InDesign apre il documento, i collegamenti vengono risolti, le risorse vengono scaricate e le risorse vengono visualizzate nel documento di InDesign.
1. Per inserire un nuovo elemento grafico nel file InDesign, utilizzare **[!UICONTROL Reveal File]** sulla risorsa. L&#39;azione scarica la risorsa localmente e apre il percorso di condivisione di rete locale in Esplora risorse o nel Finder di Mac.
1. Inserisci la risorsa rivelata nel documento InDesign. Questo crea un collegamento nel documento.
1. Una volta completate le modifiche nel documento InDesign, salvalo e caricalo in [!DNL Experience Manager] utilizzo dell’app desktop.

## Flusso di lavoro avanzato: scaricare le risorse localmente {#adv-workflow-download-assets-locally}

L’app scarica le risorse da [!DNL Experience Manager] server localmente sul file system in molti scenari. I download richiedono larghezza di banda e spazio su disco. Conoscere gli scenari ti aiuta a ottimizzare il tempo di attesa per il completamento dei download.

Scarica le risorse dall’interno dell’app on-demand. Vedi [Scaricare le risorse](#download-assets).

Quando utilizzi la [!UICONTROL Open] per aprire una risorsa in un’applicazione desktop nativa, la risorsa viene scaricata localmente se non è già disponibile localmente. Vedi [Apri risorse](#openondesktop-v2).

Quando riveli il percorso di una risorsa o di una cartella dall’interno dell’app, la risorsa o la cartella viene prima scaricata localmente e quindi aperta sul computer nella condivisione di rete locale. Vedi [Apri risorse](#openondesktop-v2).

Quando utilizzi la [!UICONTROL Edit] per modificare una risorsa in un’applicazione desktop nativa, la risorsa viene scaricata localmente se non è già disponibile localmente. Vedi [Modifica le risorse e carica le risorse aggiornate in [!DNL Experience Manager]](#edit-assets-upload-updated-assets).

Se l’app è installata e autorizzata, completa le azioni quando utilizzi [!UICONTROL Desktop Actions] da [!DNL Experience Manager] interfaccia web. L’app scarica prima la risorsa e quindi completa l’azione.
