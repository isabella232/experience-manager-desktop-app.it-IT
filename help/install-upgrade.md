---
title: Installare e configurare l’app desktop
description: Installa e configura i server [!DNL Adobe Experience Manager] desktop app to work with [!DNL Adobe Experience Manager Assets] e scarica le risorse sul file system locale.
feature: Desktop App,Release Information
exl-id: 422e51c1-c456-4151-bb43-4b3d29a58187
source-git-commit: 2c846fb9cd82691f6439e93429dffcca8127ba68
workflow-type: tm+mt
source-wordcount: '1406'
ht-degree: 0%

---

# Installare l’ app desktop [!DNL Adobe Experience Manager] {#install-app-v2}

Utilizzando l’ app desktop [!DNL Adobe Experience Manager], le risorse all’interno di [!DNL Experience Manager] sono facilmente disponibili sul desktop locale e possono essere utilizzate in qualsiasi applicazione desktop nativa. Le risorse possono essere visualizzate in anteprima, aperte in applicazioni desktop native, visualizzate in Mac Finder o Esplora risorse per il posizionamento in altri documenti e modificate localmente. Le modifiche vengono salvate in [!DNL Experience Manager] al momento del caricamento e viene creata una nuova versione nell’archivio.

Tale integrazione consente a vari ruoli dell’organizzazione di:

* Gestisci le risorse centralmente in [!DNL Experience Manager Assets].

* Accedi alle risorse in qualsiasi applicazione desktop nativa, incluse applicazioni di terze parti e in Adobe Creative Cloud. In questo modo, gli utenti possono aderire facilmente ai vari standard, tra cui il branding.

Per utilizzare l’app desktop [!DNL Experience Manager],

* Assicurati che la tua versione [!DNL Experience Manager] sia supportata dall&#39;app desktop [!DNL Experience Manager]. Vedere i [requisiti di sistema](release-notes.md).

* Scarica e installa l&#39;applicazione. Consulta [installare l&#39;app desktop](#install-v2) di seguito.

* Verifica la connessione utilizzando alcune risorse. Consulta [come sfogliare e cercare le risorse](using.md#browse-search-preview-assets).

## Requisiti di sistema, prerequisiti e collegamenti per il download {#tech-specs-v2}

Per informazioni dettagliate, consulta le [[!DNL Experience Manager] note sulla versione dell’app desktop](release-notes.md).

## Eseguire l’aggiornamento da una versione precedente {#upgrade-from-previous-version}

Se sei un utente della versione 1.x dell’app desktop, puoi comprendere le differenze e le somiglianze tra la versione precedente e quella più recente dell’app. Vedi [novità nell&#39;app desktop](introduction.md#whats-new-v2) e [funzionamento dell&#39;app](release-notes.md#how-app-works)

>[!NOTE]
>
>Due versioni dell’app desktop non possono coesistere su un computer. Prima di installare una versione, disinstalla l’altra versione.

Per eseguire l’aggiornamento da una versione precedente dell’app, segui queste istruzioni:

1. Prima dell’aggiornamento, sincronizza tutte le risorse e carica le modifiche in [!DNL Experience Manager]. In questo modo si evita di perdere le modifiche apportate durante la disinstallazione dell’app.

1. Disinstalla la versione precedente dell’app. Durante la disinstallazione, seleziona l’opzione per cancellare la cache.

1. Riavvia il computer.

1. [](release-notes.md) Scarica e  [](#install-v2) installa l’app più recente. Segui le istruzioni riportate di seguito.

## Installare la versione {#install-v2}

Per installare l’app desktop, segui questi passaggi. Disinstalla qualsiasi Adobe esistente [!DNL Experience Manager] app desktop v1.x prima di installare l’app più recente. Per ulteriori informazioni, vedi sopra.

1. Scarica l&#39;ultimo programma di installazione dalla pagina [note sulla versione](release-notes.md) .

1. Mantieni a portata di mano l’URL e le credenziali della distribuzione [!DNL Experience Manager] .

1. Per l&#39;aggiornamento da un&#39;altra versione dell&#39;app, consulta [aggiornare l&#39;app desktop](#upgrade-from-previous-version).

1. Ignora questo passaggio se utilizzi [!DNL Experience Manager] come [!DNL Cloud Service], [!DNL Experience Manager] 6.4.4 o successivo o [!DNL Experience Manager] 6.5.0 o successivo. Assicurati che la tua configurazione [!DNL Experience Manager] soddisfi i requisiti di compatibilità indicati nelle [note sulla versione](release-notes.md). Se necessario, scarica il [pacchetto di compatibilità](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/cq640/featurepack/adobe-asset-link-support) applicabile e installalo utilizzando la [!DNL Experience Manager] Gestione pacchetti come amministratore [!DNL Experience Manager]. Per installare un pacchetto, vedi [Come lavorare con i pacchetti](https://experienceleague.adobe.com/docs/experience-manager-65/administering/contentmanagement/package-manager.html).

1. Eseguire il programma di installazione binario e seguire le istruzioni visualizzate per l&#39;installazione.

1. In Windows, il programma di installazione potrebbe richiedere l&#39;installazione di `Visual Studio C++ Redistributable 2015`. Seguire le istruzioni visualizzate per installarlo. Se l&#39;installazione non riesce, installala manualmente. Scarica il programma di installazione da [qui](https://www.microsoft.com/en-us/download/details.aspx?id=52685) e installa sia i file `vc_redist.x64.exe` che i file `vc_redist.x86.exe`. Esegui di nuovo il programma di installazione dell&#39;app desktop [!DNL Experience Manager].

1. Riavvia il computer come richiesto. Avvia e configura l’app desktop.

1. Per collegare l’app a un archivio [!DNL Experience Manager], fai clic sull’icona dell’app nella barra delle applicazioni e avvia l’app. Fornisci l&#39;indirizzo del server [!DNL Experience Manager] nel formato `https://[aem_server]:[port]/`.

   Fare clic su **[!UICONTROL Connect]** e specificare le credenziali.

   ![Schermata di connessione dell’app desktop all’indirizzo del server di input](assets/connect_da2.png)

   *Figura: Schermata di connessione all&#39;indirizzo del server di input.*

   >[!CAUTION]
   >
   >Assicurati che non ci siano spazi iniziali o finali prima o dopo l&#39;indirizzo del server [!DNL Experience Manager]. In caso contrario, l&#39;app non può connettersi al server [!DNL Experience Manager].

1. Dopo la connessione, puoi visualizzare l’elenco delle cartelle e delle risorse disponibili nella cartella principale di [!DNL Experience Manager] DAM. Puoi sfogliare le cartelle dall’interno dell’app.

   ![All’accesso, l’app visualizza il contenuto DAM](assets/firstview_da2.png)

   *Figura: L&#39;applicazione visualizza il contenuto DAM dopo l&#39;accesso*

1. ([!DNL Experience Manager] 6.5.1 o versioni successive) Se utilizzi l’app desktop con [!DNL Experience Manager] 6.5.1 o versioni successive, aggiorna il connettore S3 o Azure alla versione 1.10.4 o successiva. Consultare [Connettore Azure](https://experienceleague.adobe.com/docs/experience-manager-65/deploying/deploying/data-store-config.html#azure-data-store) o [Connettore S3](https://experienceleague.adobe.com/docs/experience-manager-65/deploying/deploying/data-store-config.html#amazon-s-data-store).

   Se sei un cliente di Adobe Managed Services (AMS), contatta l’Assistenza clienti Adobe.

## Impostare le preferenze {#set-preferences}

Per modificare le preferenze, fare clic sull&#39;icona ![Altre opzioni](assets/do-not-localize/more_options_da2.png) e **[!UICONTROL Preference]** ![Icona Preferenze](assets/do-not-localize/preferences_icon_da2.png). Nella finestra **[!UICONTROL Preferences]**, regolare i valori dei seguenti elementi:

* [!UICONTROL Launch application on login].

* [!UICONTROL Show window when application starts].

* **[!UICONTROL Cache Directory]**: Posizione della cache locale dell’app (contiene le risorse scaricate localmente).

* **[!UICONTROL Network Drive Letter]**: La lettera di unità utilizzata per la mappatura sul  [!DNL Experience Manager] DAM. Non modificare questa impostazione se non sei sicuro. L&#39;app può eseguire il mapping a qualsiasi lettera di unità su Windows. Se due utenti posizionano le risorse da lettere di unità diverse, non possono vedere le risorse posizionate l’uno dall’altro. Il percorso delle risorse cambia. Le risorse rimangono inserite nel file binario (ad esempio INDD) e non vengono rimosse. L&#39;app elenca tutte le lettere di unità disponibili e per impostazione predefinita utilizza l&#39;ultima lettera disponibile, in genere `Z`.

* **[!UICONTROL Maximum Cache Size]**: Cache consentita su disco rigido in GB utilizzata per archiviare le risorse scaricate localmente.

* **[!UICONTROL Current cache size]**: Dimensione di archiviazione delle risorse scaricate localmente. Le informazioni vengono visualizzate solo dopo il download delle risorse tramite l’app.

* **[!UICONTROL Automatically download linked assets]**: Le risorse inserite nelle app native supportate vengono recuperate automaticamente se scarichi il file originale.

* **[!UICONTROL Maximum number of downloads]**:  ![avvertenza ](assets/do-not-localize/caution-icon.png) iconChange con cautela. Quando si scaricano le risorse per la prima volta (tramite Mostra, Apri, Modifica, Scarica o un’opzione simile), le risorse vengono scaricate solo se il batch contiene meno di questo numero. Il valore predefinito è 50. Non cambiare se non sei sicuro. L’aumento del valore può causare tempi di attesa più lunghi e la riduzione del valore potrebbe non consentire di scaricare le risorse o le cartelle necessarie in una sola volta.

* **[!UICONTROL Use legacy conventions when creating nodes for assets and folders]**:  ![avvertenza ](assets/do-not-localize/caution-icon.png) iconChange con cautela. Questa impostazione consente all’app di emulare il comportamento dell’app v1.10 durante il caricamento delle cartelle. Nella versione 1.10, i nomi dei nodi creati nel repository rispettano gli spazi e la custodia dei nomi delle cartelle forniti dall&#39;utente. Tuttavia, nella versione v2.1 dell’app, gli spazi aggiuntivi nei nomi delle cartelle vengono convertiti in trattini. Ad esempio, caricando `New Folder` o `new   folder` si crea lo stesso nodo nell’archivio se l’opzione non è selezionata e viene mantenuto il comportamento predefinito nella versione v2.1. Se questa opzione è selezionata, vengono creati nodi diversi nell’archivio per le due cartelle di cui sopra e corrisponde al comportamento dell’app v1.10.

   Il comportamento predefinito della v2.1 continua a rimanere invariato, ovvero sostituire più spazi nei nomi delle cartelle con trattini nel nome del nodo del repository e convertire in nomi di nodo minuscoli.

* **[!UICONTROL Upload Acceleration]**:  ![avvertenza ](assets/do-not-localize/caution-icon.png) iconChange con cautela. Durante il caricamento delle risorse, l’applicazione può utilizzare caricamenti simultanei per migliorare la velocità di caricamento. Per aumentare la concorrenza del caricamento, sposta il cursore a destra. Il cursore all’estrema sinistra indica nessuna concorrenza (caricamento a thread singolo), la posizione centrale corrisponde a 10 thread simultanei e il limite massimo sul lato destro corrisponde a 20 thread simultanei. Un limite di concorrenza più elevato richiede più risorse.

Per aggiornare le preferenze non disponibili, disconnettiti dal server [!DNL Experience Manager] e quindi aggiorna. Dopo aver aggiornato le preferenze, fai clic su ![Salva preferenze](assets/do-not-localize/save_preferences_da2.png).

![Preferenze e impostazioni dell’app desktop](assets/preferences_da2.png)

*Figura: Preferenze dell’app desktop*

### Supporto proxy {#proxy-support}

[!DNL Experience Manager] l’app desktop utilizza il proxy predefinito di sistema per connettersi a Internet tramite HTTPS. L&#39;app può connettersi solo utilizzando un proxy di rete che non richiede un&#39;autenticazione aggiuntiva.

Se si configurano o si modificano le impostazioni del server proxy per Windows (Opzioni Internet > Impostazioni LAN), riavviare l&#39;app desktop [!DNL Experience Manager] per rendere effettive le modifiche. La configurazione proxy si applica quando si avvia l&#39;app desktop. Chiudi e riavvia l’app per rendere effettive le eventuali modifiche.

Se il proxy richiede l&#39;autenticazione, il team IT può consentire l&#39;URL [!DNL Experience Manager Assets] nelle impostazioni del server proxy per consentire il passaggio del traffico dell&#39;applicazione.

## Disinstallare l’app {#uninstall-the-app}

Per disinstallare l&#39;applicazione su Windows, segui questi passaggi:

1. Carica tutte le modifiche in [!DNL Experience Manager] per evitare di perdere le modifiche. Consulta [Modificare le risorse e caricare le risorse aggiornate in [!DNL Experience Manager]](using.md#edit-assets-upload-updated-assets). Disconnettiti e [!UICONTROL Exit] l’app.

1. Rimuovi l&#39;app quando rimuovi qualsiasi altra applicazione OS. Disinstallalo da Aggiungi e rimuovi programmi su Windows.

1. Per rimuovere la cache e i registri, seleziona la casella di controllo necessaria.

   ![Disinstalla la finestra di dialogo per rimuovere i registri e la cache](assets/uninstall_da2.png)

1. Seguire le istruzioni visualizzate. Al termine, riavviare il computer.

Per disinstallare l’applicazione su Mac, segui questi passaggi:

1. Carica tutte le modifiche in [!DNL Experience Manager] per evitare di perdere le modifiche. Consulta [Modificare le risorse e caricare le risorse aggiornate in [!DNL Experience Manager]](using.md#edit-assets-upload-updated-assets). Disconnettiti e [!UICONTROL Exit] l’app.

1. Rimuovi `Adobe Experience Manager Desktop.app` da `/Applications`.

In alternativa, per pulire le cache interne dell&#39;applicazione su Mac e disinstallare l&#39;app, puoi eseguire il seguente comando nel terminale:

```shell
/Applications/Adobe Experience Manager Desktop/Contents/Resources/uninstall-osx/uninstall.sh
```
