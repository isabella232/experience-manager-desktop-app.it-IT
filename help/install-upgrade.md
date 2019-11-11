---
title: Installare e configurare l'app desktop AEM
seo-title: Installare e configurare l'app desktop AEM
description: Installa e configura l’app desktop AEM per lavorare con i server Risorse AEM e scarica le risorse nel file system locale.
seo-description: Installa e configura l’app desktop AEM per lavorare con i server Risorse AEM e scarica le risorse nel file system locale.
uuid: 79bc9de9-5708-41f9-ac43-68c1fd2a2129
contentOwner: asgupta
products: SG_EXPERIENCEMANAGER/6.3/ASSETS
discoiquuid: f6365302-1690-4719-9b8c-035719422740
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a46660a3d56100e0d767e7f2b54656782bb5e7a7

---


# Installare l'app desktop AEM {#install-app-v2}

## Requisiti di sistema {#tech-specs-v2}

Per informazioni dettagliate, consultate le note [sulla versione dell'app desktop](release-notes.md)AEM.

## Aggiornamento dall'app v1.x all'app v2 {#upgrade-from-previous-version}

Se siete un utente esistente dell'app, capite le differenze e le similitudini tra la versione precedente e quella più recente dell'app. Inoltre, seguite le seguenti linee guida, per passare dalla versione 1.x all'ultima versione.

>[!NOTE]
>
>L'app desktop v1.x e v2 non può coesistere su un computer. Prima di installare una versione, disinstallate l’altra versione.

Per effettuare l'aggiornamento dalla versione 1.x all'ultima versione dell'app, segui le istruzioni seguenti:

1. Prima di effettuare l’aggiornamento, sincronizzate tutte le risorse. Caricate tutte le modifiche utilizzando l'app v1.x. Questo per evitare di perdere eventuali modifiche durante la disinstallazione dell'app v1.x.
1. Disinstallare l'app v1.x. Durante la disinstallazione della versione 1.x, cancellare la cache.
1. Riavviate il computer.
1. Scaricate e installate l'app più recente. Seguite le istruzioni riportate di seguito.

## Installare la versione {#install-v2}

Per installare l'app desktop, attenetevi alla seguente procedura. Disinstallate l'app desktop Adobe Experience Manager v1.x esistente prima di installare l'app più recente. Per ulteriori informazioni, vedi sopra.

1. Tenete a portata di mano l'URL e le credenziali della distribuzione AEM.
1. Ignora questo passaggio se utilizzi AEM 6.4.4 e versioni successive o AEM 6.5.0 o versioni successive. Assicurati che la configurazione di AEM soddisfi i requisiti di compatibilità indicati nelle note sulla versione. Se necessario, scaricate il pacchetto [di](https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/cq640/featurepack/adobe-asset-link-support) compatibilità applicabile e installatelo utilizzando AEM Package Manager come amministratore AEM. Per installare un pacchetto, consultate [Come utilizzare i pacchetti](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/package-manager.html).
1. Eseguite il programma di installazione binario e seguite le istruzioni visualizzate per eseguire l'installazione.
1. In Windows, il programma di installazione potrebbe richiedere l'installazione `Visual Studio C++ Redistributable 2015`. Seguite le istruzioni visualizzate per installarlo. Se l’installazione non riesce, installatela manualmente. Scaricate il programma di installazione da [qui](https://www.microsoft.com/en-us/download/details.aspx?id=52685) e installate sia `vc_redist.x64.exe` che `vc_redist.x86.exe` i file. Eseguite nuovamente il programma di installazione dell'app desktop AEM.
1. Riavviate il computer come richiesto. Avviate l'app desktop per configurarla.
1. Per collegare l'app a un archivio AEM, fai clic sull'icona dell'app nella barra delle applicazioni per avviare l'app. Fornite l’indirizzo dell’istanza AEM. Fare clic su **[!UICONTROL Connect]** e specificare le credenziali.

   ![Schermata di connessione dell'app desktop all'](assets/connect_da2.png "indirizzo del server di inputSchermata di connessione all'indirizzo del server di input")

   >[!Caution]
   >
   >Assicurati che non ci siano spazi iniziali o finali prima o dopo l’indirizzo del server AEM. In caso contrario, l'app non può connettersi al server AEM.

1. Dopo la connessione, puoi visualizzare l’elenco delle cartelle e delle risorse disponibili nella cartella principale di AEM DAM. Potete sfogliare le cartelle dall'interno dell'app.

   ![Al momento dell'accesso, l'app visualizza i](assets/firstview_da2.png "contenuti DAM. Al momento dell'accesso, l'app visualizza i contenuti DAM")

1. (AEM 6.5.1 o versione successiva) Se si utilizza l'app desktop con AEM 6.5.1 o versione successiva, aggiornare il connettore S3 o Azure alla versione 1.10.4 o successiva. Vedere Connettore [di](https://helpx.adobe.com/experience-manager/6-5/sites/deploying/using/data-store-config.html#AzureDataStore) Azure o connettore [](https://helpx.adobe.com/experience-manager/6-5/sites/deploying/using/data-store-config.html#AmazonS3DataStore)S3.

   Se sei un cliente Adobe Managed Services (AMS), contatta l’Assistenza clienti Adobe.

## Impostare le preferenze {#set-preferences}

Per modificare le preferenze, fate clic sull'icona ![Altre opzioni](assets/do-not-localize/more_options_da2.png) e sull'icona **[!UICONTROL Preference]**![Preferenze](assets/do-not-localize/preferences_icon_da2.png). Nella **[!UICONTROL Preferences]** finestra regolate i valori seguenti:

* [!UICONTROL Launch application on login].
* [!UICONTROL Show window when application starts].
* **[!UICONTROL Cache Directory]**: Posizione della cache locale dell'app (contiene le risorse scaricate localmente).
* **[!UICONTROL Network Drive Letter]**: La lettera dell'unità utilizzata per mappare AEM DAM. Non cambiate questo se non siete sicuri. L'app può mappare a qualsiasi lettera di unità in Windows. Se due utenti inseriscono risorse da diverse lettere di unità, non potranno vedere le risorse inserite l’uno dall’altro. Il percorso delle risorse cambia. Le risorse rimangono inserite nel file binario (ad esempio, INDD) e non vengono rimosse. L'app elenca tutte le lettere dell'unità disponibili e per impostazione predefinita utilizza l'ultima lettera disponibile che è in genere `Z`.
* **[!UICONTROL Maximum Cache Size]**: Cache consentita su disco rigido in GB utilizzata per la memorizzazione delle risorse scaricate localmente.
* **[!UICONTROL Current cache size]**: Dimensione dello spazio di archiviazione delle risorse scaricate localmente. Le informazioni vengono visualizzate solo dopo che le risorse sono state scaricate tramite l'app.
* **[!UICONTROL Automatically download linked assets]**: Le risorse inserite nelle app Creative Cloud native supportate vengono recuperate automaticamente se scaricate il file originale.
* **[!UICONTROL Maximum number of downloads]**: Quando scaricate le risorse per la prima volta (tramite Rivela, Apri, Modifica, Scarica o un’opzione simile), le risorse vengono scaricate solo se il batch contiene meno di questo numero. Il valore predefinito è 50. Non cambiate se non siete sicuri. Aumentare il valore può comportare tempi di attesa più lunghi e ridurre il valore potrebbe non consentire di scaricare le risorse o le cartelle necessarie in una sola volta.

Per aggiornare le preferenze non disponibili, uscite dal server AEM. Dopo aver aggiornato le preferenze, fate clic su ![Salva preferenze](assets/do-not-localize/save_preferences_da2.png) per salvare le modifiche.

![Preferenze e](assets/preferences_da2.png "impostazioni dell'app desktop AEMPreferenze dell'app desktop")

## Disinstallare l'app {#uninstall-the-app}

Per disinstallare l’applicazione in Windows, effettuate le seguenti operazioni:

1. Caricate tutte le modifiche in AEM per evitare di perdere eventuali modifiche. Consultate [Modificare le risorse e caricare le risorse aggiornate in AEM](using.md#edit-assets-upload-updated-assets). Disconnettetevi e [!UICONTROL Exit] l'app.
1. Rimuovete l'app quando rimuovete un'altra applicazione OS. Disinstallarlo da Aggiungi e rimuovi programmi in Windows.
1. Per rimuovere la cache e i registri, selezionate la casella di controllo necessaria.
   ![Finestra di dialogo di disinstallazione per rimuovere registri e](assets/uninstall_da2.png "cacheFinestra di dialogo di disinstallazione per rimuovere registri e cache")
1. Seguire le istruzioni visualizzate. Al termine, riavviare il computer.

Per disinstallare l’applicazione in Mac, effettuate le seguenti operazioni:

1. Caricate tutte le modifiche in AEM per evitare di perdere eventuali modifiche. Consultate [Modificare le risorse e caricare le risorse aggiornate in AEM](using.md#edit-assets-upload-updated-assets). Disconnettetevi e [!UICONTROL Exit] l'app.
1. Rimuovere la `Adobe Experience Manager Desktop.app` da `/Applications`.

In alternativa, per pulire le cache interne dell'applicazione su Mac e disinstallare l'app, potete eseguire il seguente comando nel terminale:
`/Applications/Adobe Experience Manager Desktop/Contents/Resources/uninstall-osx/uninstall.sh`
