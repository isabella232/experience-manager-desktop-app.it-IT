---
title: Installare e configurare l’app desktop Adobe Experience Manager
description: Installa e configura l’app desktop Adobe Experience Manager per lavorare con i server Risorse Adobe Experience Manager e scarica le risorse nel file system locale.
uuid: 79bc9de9-5708-41f9-ac43-68c1fd2a2129
contentOwner: AG
products: SG_EXPERIENCEMANAGER/6.3/ASSETS
discoiquuid: f6365302-1690-4719-9b8c-035719422740
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 49532b1c5eec497df5b29084675c08f25a15819a

---


# Install Adobe Experience Manager desktop app {#install-app-v2}

Utilizzando l’app desktop Adobe Experience Manager, le risorse incluse in Experience Manager sono facilmente disponibili sul desktop locale e possono essere utilizzate in qualsiasi applicazione desktop nativa. Le risorse possono essere visualizzate in anteprima, aperte nelle applicazioni desktop native, visualizzate in Mac Finder o Windows Explorer per l’inserimento in altri documenti e modificate localmente. Le modifiche vengono salvate in Experience Manager al momento del caricamento e viene creata una nuova versione nell’archivio.

Tale integrazione consente a vari ruoli dell&#39;organizzazione di:

* Gestione centralizzata delle risorse in Experience Manager Assets.
* Accedete alle risorse in qualsiasi applicazione desktop nativa, incluse le applicazioni di terze parti e in Adobe Creative Cloud. In questo modo, gli utenti possono aderire facilmente ai vari standard, tra cui il marchio.

Per utilizzare l’app desktop Experience Manager,

* Accertati che la tua versione di Experience Manager sia supportata dall’app desktop Experience Manager. Vedi i requisiti [di](release-notes.md#system-requirements-and-prerequisites-v2) sistema indicati di seguito.
* Scaricate e installate l&#39;applicazione. Consultate [installare l&#39;app](#install-v2) desktop di seguito.
* Verificare la connessione utilizzando alcune risorse. Scoprite [come individuare e cercare le risorse](using.md#browse-search-preview-assets).

## Requisiti di sistema, prerequisiti e collegamenti per il download {#tech-specs-v2}

Per informazioni dettagliate, consultate le note [sulla versione dell&#39;app desktop](release-notes.md)Experience Manager.

## Aggiornamento dall&#39;app v1.x all&#39;app v2 {#upgrade-from-previous-version}

Se siete un utente esistente dell&#39;app, capite le differenze e le similitudini tra la versione precedente e quella più recente dell&#39;app. Inoltre, attenetevi alle seguenti linee guida per passare dalla versione 1.x alla versione più recente.

>[!NOTE]
>
>L&#39;app desktop v1.x e v2 non può coesistere su un computer. Prima di installare una versione, disinstallate l’altra versione.

Per effettuare l&#39;aggiornamento dalla versione 1.x all&#39;ultima versione dell&#39;app, segui le istruzioni seguenti:

1. Prima di effettuare l’aggiornamento, sincronizzate tutte le risorse. Caricate tutte le modifiche utilizzando l&#39;app v1.x. Questo per evitare di perdere eventuali modifiche durante la disinstallazione dell&#39;app v1.x.
1. Disinstallare l&#39;app v1.x. Durante la disinstallazione della versione 1.x, cancellare la cache.
1. Riavviate il computer.
1. Scaricate e installate l&#39;app più recente. Seguite le istruzioni riportate di seguito.

## Installare la versione {#install-v2}

Per installare l&#39;app desktop, attenetevi alla seguente procedura. Disinstallate l&#39;app desktop Adobe Experience Manager v1.x esistente prima di installare l&#39;app più recente. Per ulteriori informazioni, vedi sopra.

1. Tenete a portata di mano l&#39;URL e le credenziali della distribuzione Experience Manager.
1. Ignora questo passaggio se utilizzi Experience Manager come servizio Cloud, Experience Manager 6.4.4 o versione successiva oppure Experience Manager 6.5.0 o versione successiva. Assicurati che la configurazione di Experience Manager soddisfi i requisiti di compatibilità indicati nelle note sulla [versione](release-notes.md). Se necessario, scaricate il pacchetto [di](https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/cq640/featurepack/adobe-asset-link-support) compatibilità applicabile e installatelo utilizzando Experience Manager Package Manager come amministratore Experience Manager. Per installare un pacchetto, consultate [Come utilizzare i pacchetti](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/package-manager.html).
1. Eseguite il programma di installazione binario e seguite le istruzioni visualizzate per eseguire l&#39;installazione.
1. In Windows, il programma di installazione potrebbe richiedere l&#39;installazione `Visual Studio C++ Redistributable 2015`. Seguite le istruzioni visualizzate per installarlo. Se l’installazione non riesce, installatela manualmente. Scaricate il programma di installazione da [qui](https://www.microsoft.com/en-us/download/details.aspx?id=52685) e installate sia `vc_redist.x64.exe` che `vc_redist.x86.exe` i file. Eseguite nuovamente il programma di installazione dell&#39;app desktop AEM.
1. Riavviate il computer come richiesto. Avviate e configurate l&#39;app desktop.
1. Per collegare l&#39;app a un archivio AEM, fai clic sull&#39;icona dell&#39;app nella barra delle applicazioni per avviare l&#39;app. Fornite l’indirizzo dell’istanza AEM. Fare clic su **[!UICONTROL Connect]** e specificare le credenziali.

   ![Schermata di connessione dell&#39;app desktop all&#39;](assets/connect_da2.png "indirizzo del server di inputSchermata di connessione all&#39;indirizzo del server di input")

   >[!Caution]
   >
   >Assicurati che non ci siano spazi iniziali o finali prima o dopo l’indirizzo del server AEM. In caso contrario, l&#39;app non può connettersi al server AEM.

1. Dopo la connessione, puoi visualizzare l’elenco delle cartelle e delle risorse disponibili nella cartella principale di AEM DAM. Potete sfogliare le cartelle dall&#39;interno dell&#39;app.

   ![Al momento dell&#39;accesso, l&#39;app visualizza i](assets/firstview_da2.png "contenuti DAM. Al momento dell&#39;accesso, l&#39;app visualizza i contenuti DAM")

1. (Experience Manager 6.5.1 o versione successiva) Se utilizzate l&#39;app desktop con Experience Manager 6.5.1 o versione successiva, aggiornate il connettore S3 o Azure alla versione 1.10.4 o successiva. Vedere Connettore [di](https://helpx.adobe.com/experience-manager/6-5/sites/deploying/using/data-store-config.html#AzureDataStore) Azure o connettore [](https://helpx.adobe.com/experience-manager/6-5/sites/deploying/using/data-store-config.html#AmazonS3DataStore)S3.

   Se sei un cliente Adobe Managed Services (AMS), contatta l’Assistenza clienti Adobe.

## Impostare le preferenze {#set-preferences}

Per modificare le preferenze, fate clic sull&#39;icona ![Altre opzioni](assets/do-not-localize/more_options_da2.png) e sull&#39;icona **[!UICONTROL Preference]**![ Preferenze](assets/do-not-localize/preferences_icon_da2.png). Nella **[!UICONTROL Preferences]** finestra regolate i valori seguenti:

* [!UICONTROL Launch application on login].
* [!UICONTROL Show window when application starts].
* **[!UICONTROL Cache Directory]**: Posizione della cache locale dell&#39;app (contiene le risorse scaricate localmente).
* **[!UICONTROL Network Drive Letter]**: La lettera dell&#39;unità utilizzata per mappare AEM DAM. Non cambiate questo se non siete sicuri. L&#39;app può mappare a qualsiasi lettera di unità in Windows. Se due utenti inseriscono risorse da diverse lettere di unità, non potranno vedere le risorse inserite l’uno dall’altro. Il percorso delle risorse cambia. Le risorse rimangono inserite nel file binario (ad esempio, INDD) e non vengono rimosse. L&#39;app elenca tutte le lettere dell&#39;unità disponibili e per impostazione predefinita utilizza l&#39;ultima lettera disponibile che è in genere `Z`.
* **[!UICONTROL Maximum Cache Size]**: Cache consentita su disco rigido in GB utilizzata per la memorizzazione delle risorse scaricate localmente.
* **[!UICONTROL Current cache size]**: Dimensione dello spazio di archiviazione delle risorse scaricate localmente. Le informazioni vengono visualizzate solo dopo che le risorse sono state scaricate tramite l&#39;app.
* **[!UICONTROL Automatically download linked assets]**: Le risorse inserite nelle app Creative Cloud native supportate vengono recuperate automaticamente se scaricate il file originale.
* **[!UICONTROL Maximum number of downloads]**: Quando scaricate le risorse per la prima volta (tramite Rivela, Apri, Modifica, Scarica o un’opzione simile), le risorse vengono scaricate solo se il batch contiene meno di questo numero. Il valore predefinito è 50. Non cambiate se non siete sicuri. Aumentare il valore può comportare tempi di attesa più lunghi e ridurre il valore potrebbe non consentire di scaricare le risorse o le cartelle necessarie in una sola volta.
* **[!UICONTROL Upload Acceleration]**: Quando caricate delle risorse, l’applicazione può usare caricamenti simultanei per migliorare la velocità di caricamento. Per aumentare la concorrenza del caricamento, spostate il cursore verso destra. Il cursore sul lato sinistro indica che non esiste una concorrenza (caricamento a thread singolo), che la posizione centrale corrisponde a 10 thread simultanei e che il limite massimo sul lato destro corrisponde a 20 thread simultanei. Un limite di concorrenza più elevato richiede un maggiore consumo di risorse del processore del computer locale.

Per aggiornare le preferenze non disponibili, disconnettetevi da AEM Server. Dopo aver aggiornato le preferenze, fate clic su ![Salva preferenze](assets/do-not-localize/save_preferences_da2.png) per salvare le modifiche.

![Preferenze e](assets/preferences_da2.png "impostazioni dell&#39;app desktop AEMPreferenze dell&#39;app desktop")

## Disinstallare l&#39;app {#uninstall-the-app}

Per disinstallare l’applicazione in Windows, effettuate le seguenti operazioni:

1. Caricate tutte le modifiche in AEM per evitare di perdere eventuali modifiche. Consultate [Modificare le risorse e caricare le risorse aggiornate in AEM](using.md#edit-assets-upload-updated-assets). Disconnettetevi e [!UICONTROL Exit] l&#39;app.
1. Rimuovete l&#39;app quando rimuovete un&#39;altra applicazione del sistema operativo. Disinstallarlo da Aggiungi e rimuovi programmi in Windows.
1. Per rimuovere la cache e i registri, selezionate la casella di controllo necessaria.
   ![Finestra di dialogo di disinstallazione per rimuovere registri e](assets/uninstall_da2.png "cacheFinestra di dialogo di disinstallazione per rimuovere registri e cache")
1. Seguire le istruzioni visualizzate. Al termine, riavviare il computer.

Per disinstallare l’applicazione in Mac, effettuate le seguenti operazioni:

1. Caricate tutte le modifiche in AEM per evitare di perdere eventuali modifiche. Consultate [Modificare le risorse e caricare le risorse aggiornate in AEM](using.md#edit-assets-upload-updated-assets). Disconnettetevi e [!UICONTROL Exit] l&#39;app.
1. Rimuovere la `Adobe Experience Manager Desktop.app` da `/Applications`.

In alternativa, per pulire le cache interne dell&#39;applicazione su Mac e disinstallare l&#39;app, potete eseguire il seguente comando nel terminale:
`/Applications/Adobe Experience Manager Desktop/Contents/Resources/uninstall-osx/uninstall.sh`
