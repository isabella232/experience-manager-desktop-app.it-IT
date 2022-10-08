---
title: Installare e configurare l’app desktop
description: Installare e configurare [!DNL Adobe Experience Manager] app desktop con cui lavorare [!DNL Adobe Experience Manager Assets] e scarica le risorse nel file system locale.
feature: Desktop App,Release Information
exl-id: 422e51c1-c456-4151-bb43-4b3d29a58187
source-git-commit: 5b5970cec02d4a605bd7d826d1daa71fe228b0d9
workflow-type: tm+mt
source-wordcount: '1426'
ht-degree: 0%

---

# Installa [!DNL Adobe Experience Manager] app desktop {#install-app-v2}

Utilizzo della [!DNL Adobe Experience Manager] app desktop, risorse all’interno di [!DNL Experience Manager] sono facilmente disponibili sul desktop locale e possono essere utilizzati in qualsiasi applicazione desktop nativa. Le risorse possono essere visualizzate in anteprima, aperte in applicazioni desktop native, visualizzate in Mac Finder o Esplora risorse per il posizionamento in altri documenti e modificate localmente - le modifiche vengono salvate in [!DNL Experience Manager] quando carichi e viene creata una nuova versione nell’archivio.

Tale integrazione consente a vari ruoli dell’organizzazione di:

* Gestire centralmente le risorse in [!DNL Experience Manager Assets].

* Accedi alle risorse in qualsiasi applicazione desktop nativa, incluse applicazioni di terze parti e in Adobe Creative Cloud. In questo modo, gli utenti possono aderire facilmente ai vari standard, tra cui il branding.

Per utilizzare [!DNL Experience Manager] app desktop:

* Assicurati che il tuo [!DNL Experience Manager] versione supportata da [!DNL Experience Manager] app desktop. Consulta la sezione [requisiti di sistema](release-notes.md).

* Scarica e installa l&#39;applicazione. Vedi [installare l’app desktop](#install-v2) sotto.

* Verifica la connessione utilizzando alcune risorse. Vedi [come sfogliare e cercare le risorse](using.md#browse-search-preview-assets).

## Requisiti di sistema, prerequisiti e collegamenti per il download {#tech-specs-v2}

Per informazioni dettagliate, consulta la sezione [[!DNL Experience Manager] note sulla versione dell’app desktop](release-notes.md).

## Eseguire l’aggiornamento da una versione precedente {#upgrade-from-previous-version}

Se sei un utente della versione 1.x dell’app desktop, puoi comprendere le differenze e le somiglianze tra la versione precedente e quella più recente dell’app. Vedi [Novità dell’app desktop](introduction.md#whats-new-v2) e [funzionamento dell’app](release-notes.md#how-app-works).

>[!NOTE]
>
>Due versioni dell’app desktop non possono coesistere su un computer. Prima di installare una versione, disinstalla l’altra versione.

Per eseguire l’aggiornamento da una versione precedente dell’app, segui queste istruzioni:

1. Prima dell’aggiornamento, sincronizza tutte le risorse e carica le modifiche in [!DNL Experience Manager]. In questo modo si evita di perdere le modifiche apportate durante la disinstallazione dell’app.

1. Disinstalla la versione precedente dell’app. Durante la disinstallazione, seleziona l’opzione per cancellare la cache.

1. Riavvia il computer.

1. [Scarica](release-notes.md) e [installare](#install-v2) l&#39;app più recente. Segui le istruzioni riportate di seguito.

## Installare la versione {#install-v2}

Per installare l’app desktop, segui questi passaggi. Disinstalla un Adobe esistente [!DNL Experience Manager] app desktop v1.x prima di installare l’app più recente. Per ulteriori informazioni, vedi sopra.

1. Scarica l&#39;ultimo programma di installazione dal [note sulla versione](release-notes.md) pagina.

1. Conserva l’URL e le credenziali del tuo [!DNL Experience Manager] installazione utile.

1. Per l’aggiornamento da un’altra versione dell’app, consulta [aggiornamento dell’app desktop](#upgrade-from-previous-version).

1. Ignora questo passaggio se utilizzi [!DNL Experience Manager] come [!DNL Cloud Service], [!DNL Experience Manager] 6.4.4 o successivo, o [!DNL Experience Manager] 6.5.0 o versione successiva Assicurati che il tuo [!DNL Experience Manager] soddisfa i requisiti di compatibilità indicati nella [note sulla versione](release-notes.md). Se necessario, scarica il [pacchetto di compatibilità](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/cq640/featurepack/adobe-asset-link-support) e installalo utilizzando [!DNL Experience Manager] Gestione pacchetti come [!DNL Experience Manager] amministratore. Per installare un pacchetto, vedi [Come lavorare con i pacchetti](https://experienceleague.adobe.com/docs/experience-manager-65/administering/contentmanagement/package-manager.html?lang=it).

1. Eseguire il programma di installazione binario e seguire le istruzioni visualizzate per l&#39;installazione.

1. Su Windows, il programma di installazione potrebbe richiedere l&#39;installazione `Visual Studio C++ Redistributable 2015`. Seguire le istruzioni visualizzate per installarlo. Se l&#39;installazione non riesce, installala manualmente. Scarica il programma di installazione da [qui](https://www.microsoft.com/en-us/download/details.aspx?id=52685) e installare `vc_redist.x64.exe` e `vc_redist.x86.exe` file. Esegui nuovamente il [!DNL Experience Manager] programma di installazione dell’app desktop.

1. Riavvia il computer come richiesto. Avvia e configura l’app desktop.

1. Per collegare l’app a un [!DNL Experience Manager] archivio, fai clic sull’icona dell’app nella barra degli strumenti e avvia l’app. Fornire l&#39;indirizzo del [!DNL Experience Manager] nel formato `https://[aem_server]:[port]/`.

   Fai clic su **[!UICONTROL Connect]** e fornire le credenziali.

   ![Schermata di connessione dell’app desktop all’indirizzo del server di input](assets/connect_da2.png)

   *Figura: Schermata di connessione all&#39;indirizzo del server di input.*

   Seleziona **[!UICONTROL Remember Connection]** per evitare di inserire i dettagli di connessione ogni volta che accedi all’app desktop.

   >[!CAUTION]
   >
   >Assicurati che non ci siano spazi iniziali o finali prima o dopo l&#39;indirizzo del [!DNL Experience Manager] server. In caso contrario, l’app non può connettersi al [!DNL Experience Manager] server.

1. Dopo la connessione, puoi visualizzare l’elenco delle cartelle e delle risorse disponibili nella cartella principale della [!DNL Experience Manager] DAM. Puoi sfogliare le cartelle dall’interno dell’app.

   ![All’accesso, l’app visualizza il contenuto DAM](assets/firstview_da2.png)

   *Figura: L&#39;applicazione visualizza il contenuto DAM dopo l&#39;accesso*

1. ([!DNL Experience Manager] 6.5.1 o versioni successive) Se utilizzi l’app desktop con [!DNL Experience Manager] 6.5.1 o versione successiva, aggiorna il connettore S3 o Azure alla versione 1.10.4 o successiva. Vedi [Connettore Azure](https://experienceleague.adobe.com/docs/experience-manager-65/deploying/deploying/data-store-config.html#azure-data-store) o [Connettore S3](https://experienceleague.adobe.com/docs/experience-manager-65/deploying/deploying/data-store-config.html#amazon-s-data-store).

   Se sei un cliente di Adobe Managed Services (AMS), contatta l’Assistenza clienti Adobe.

## Impostare le preferenze {#set-preferences}

Per modificare le preferenze, fai clic su ![Icona Altre opzioni](assets/do-not-localize/more_options_da2.png) e **[!UICONTROL Preference]** ![Icona Preferenze](assets/do-not-localize/preferences_icon_da2.png). In **[!UICONTROL Preferences]** regolare i valori dei seguenti elementi:

* [!UICONTROL Launch application on login].

* [!UICONTROL Show window when application starts].

* **[!UICONTROL Cache Directory]**: Posizione della cache locale dell’app (contiene le risorse scaricate localmente).

* **[!UICONTROL Network Drive Letter]**: La lettera di unità utilizzata per mappare il [!DNL Experience Manager] DAM. Non modificare questa impostazione se non sei sicuro. L&#39;app può eseguire il mapping a qualsiasi lettera di unità su Windows. Se due utenti posizionano le risorse da lettere di unità diverse, non possono vedere le risorse posizionate l’uno dall’altro. Il percorso delle risorse cambia. Le risorse rimangono inserite nel file binario (ad esempio INDD) e non vengono rimosse. L&#39;app elenca tutte le lettere di unità disponibili e utilizza per impostazione predefinita l&#39;ultima lettera disponibile, che in genere è `Z`.

* **[!UICONTROL Maximum Cache Size]**: Cache consentita su disco rigido in GB utilizzata per archiviare le risorse scaricate localmente.

* **[!UICONTROL Current cache size]**: Dimensione di archiviazione delle risorse scaricate localmente. Le informazioni vengono visualizzate solo dopo il download delle risorse tramite l’app.

* **[!UICONTROL Automatically download linked assets]**: Le risorse inserite nelle app native supportate vengono recuperate automaticamente se scarichi il file originale.

* **[!UICONTROL Maximum number of downloads]**: ![icona di avviso](assets/do-not-localize/caution-icon.png) Cambiare con cautela. Quando si scaricano le risorse per la prima volta (tramite Mostra, Apri, Modifica, Scarica o un’opzione simile), le risorse vengono scaricate solo se il batch contiene meno di questo numero. Il valore predefinito è 50. Non cambiare se non sei sicuro. L’aumento del valore può causare tempi di attesa più lunghi e la riduzione del valore potrebbe non consentire di scaricare le risorse o le cartelle necessarie in una sola volta.

* **[!UICONTROL Use legacy conventions when creating nodes for assets and folders]**: ![icona di avviso](assets/do-not-localize/caution-icon.png) Cambiare con cautela. Questa impostazione consente all’app di emulare il comportamento dell’app v1.10 durante il caricamento delle cartelle. Nella versione 1.10, i nomi dei nodi creati nel repository rispettano gli spazi e la custodia dei nomi delle cartelle forniti dall&#39;utente. Tuttavia, nella versione v2.1 dell’app, gli spazi aggiuntivi nei nomi delle cartelle vengono convertiti in trattini. Ad esempio, il caricamento `New Folder` o `new   folder` crea lo stesso nodo nell’archivio se l’opzione non è selezionata e viene mantenuto il comportamento predefinito nella versione v2.1. Se questa opzione è selezionata, vengono creati nodi diversi nell’archivio per le due cartelle di cui sopra e corrisponde al comportamento dell’app v1.10.

   Il comportamento predefinito della v2.1 continua a rimanere invariato, ovvero sostituire più spazi nei nomi delle cartelle con trattini nel nome del nodo del repository e convertire in nomi di nodo minuscoli.

* **[!UICONTROL Upload Acceleration]**: ![icona di avviso](assets/do-not-localize/caution-icon.png) Cambiare con cautela. Durante il caricamento delle risorse, l’applicazione può utilizzare caricamenti simultanei per migliorare la velocità di caricamento. Per aumentare la concorrenza del caricamento, sposta il cursore a destra. Il cursore all’estrema sinistra indica nessuna concorrenza (caricamento a thread singolo), la posizione centrale corrisponde a 10 thread simultanei e il limite massimo sul lato destro corrisponde a 20 thread simultanei. Un limite di concorrenza più elevato richiede più risorse.

Per aggiornare le preferenze non disponibili, disconnettiti da [!DNL Experience Manager] e quindi aggiornare. Dopo aver aggiornato le preferenze, fai clic su ![Salvare le preferenze](assets/do-not-localize/save_preferences_da2.png).

![Preferenze e impostazioni dell’app desktop](assets/preferences_da2.png)

*Figura: Preferenze dell’app desktop*

### Supporto proxy {#proxy-support}

[!DNL Experience Manager] l’app desktop utilizza il proxy predefinito di sistema per connettersi a Internet tramite HTTPS. L&#39;app può connettersi solo utilizzando un proxy di rete che non richiede un&#39;autenticazione aggiuntiva.

Se si configurano o si modificano le impostazioni del server proxy per Windows (Opzioni Internet > Impostazioni LAN), riavviare il [!DNL Experience Manager] per rendere effettive le modifiche. La configurazione proxy si applica quando si avvia l&#39;app desktop. Chiudi e riavvia l’app per rendere effettive le eventuali modifiche.

Se il tuo proxy richiede l&#39;autenticazione, il team IT può consentire l&#39; [!DNL Experience Manager Assets] URL nelle impostazioni del server proxy per consentire il passaggio del traffico dell&#39;applicazione.

## Disinstallare l’app {#uninstall-the-app}

Per disinstallare l&#39;applicazione su Windows, segui questi passaggi:

1. Carica tutte le modifiche in [!DNL Experience Manager] per evitare di perdere eventuali modifiche. Vedi [Modifica le risorse e carica le risorse aggiornate in [!DNL Experience Manager]](using.md#edit-assets-upload-updated-assets). Disconnessione e [!UICONTROL Exit] l&#39;app.

1. Rimuovi l&#39;app durante la rimozione di qualsiasi altra applicazione OS. Disinstallalo da Aggiungi e rimuovi programmi su Windows.

1. Per rimuovere la cache e i registri, seleziona la casella di controllo necessaria.

   ![Disinstalla la finestra di dialogo per rimuovere i registri e la cache](assets/uninstall_da2.png)

1. Seguire le istruzioni visualizzate. Al termine, riavviare il computer.

Per disinstallare l’applicazione su Mac, segui questi passaggi:

1. Carica tutte le modifiche in [!DNL Experience Manager] per evitare di perdere eventuali modifiche. Vedi [Modifica le risorse e carica le risorse aggiornate in [!DNL Experience Manager]](using.md#edit-assets-upload-updated-assets). Disconnessione e [!UICONTROL Exit] l&#39;app.

1. Rimuovi `Adobe Experience Manager Desktop.app` da `/Applications`.

In alternativa, per pulire le cache interne dell&#39;applicazione su Mac e disinstallare l&#39;app, puoi eseguire il seguente comando nel terminale:

```shell
/Applications/Adobe Experience Manager Desktop/Contents/Resources/uninstall-osx/uninstall.sh
```
