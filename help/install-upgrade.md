---
title: Installare e configurare l'app desktop Adobe Experience Manager
description: Installa e configura l’app desktop Adobe Experience Manager per lavorare con i server Adobe Experience Manager Assets e scarica le risorse nel file system locale.
uuid: 79bc9de9-5708-41f9-ac43-68c1fd2a2129
contentOwner: AG
products: SG_EXPERIENCEMANAGER/6.5/ASSETS, SG_EXPERIENCEMANAGER/6.4/ASSETS, SG_EXPERIENCEMANAGER/6.3/ASSETS
discoiquuid: f6365302-1690-4719-9b8c-035719422740
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 2893fc1f8aad02e1436a1a281a320e6837487220
workflow-type: tm+mt
source-wordcount: '1222'
ht-degree: 1%

---


# Install Adobe Experience Manager desktop app {#install-app-v2}

Utilizzando l’app desktop Adobe Experience Manager, le risorse all’interno  Experience Manager sono facilmente disponibili sul desktop locale e possono essere utilizzate in qualsiasi applicazione desktop nativa. Le risorse possono essere visualizzate in anteprima, aperte nelle applicazioni desktop native, visualizzate in Mac Finder o Windows Explorer per l&#39;inserimento in altri documenti e modificate localmente; le modifiche vengono salvate in  Experience Manager al momento del caricamento e viene creata una nuova versione nell&#39;archivio.

Tale integrazione consente a vari ruoli dell&#39;organizzazione di:

* Consente di gestire le risorse a livello centrale in  risorse di Experience Manager.

* Accedete alle risorse in qualsiasi applicazione desktop nativa, incluse le applicazioni di terze parti e in Adobe Creative Cloud. In questo modo, gli utenti possono aderire facilmente ai vari standard, tra cui il marchio.

Per utilizzare &#39;app desktop Experience Manager,

* Verificate che la versione  Experience Manager sia supportata dall&#39;app desktop  Experience Manager. Vedi i requisiti [di](release-notes.md#system-requirements-and-prerequisites-v2) sistema indicati di seguito.

* Scaricate e installate l&#39;applicazione. Consultate [installare l&#39;app](#install-v2) desktop di seguito.

* Verificare la connessione utilizzando alcune risorse. Scoprite [come individuare e cercare le risorse](using.md#browse-search-preview-assets).

## Requisiti di sistema, prerequisiti e collegamenti per il download {#tech-specs-v2}

Per informazioni dettagliate, consultate gli [Experienci Manager sulle note](release-notes.md)sulla versione dell&#39;app desktop.

## Upgrade from a previous version {#upgrade-from-previous-version}

Se sei un utente della versione 1.x dell’app desktop, puoi comprendere le differenze e le similitudini tra la versione precedente e quella più recente dell’app. Scopri [le novità dell&#39;app](introduction.md#whats-new-v2) desktop e [come funziona](release-notes.md#how-app-works)

>[!NOTE]
>
>Non è possibile coesistere due versioni dell&#39;app desktop su un computer. Prima di installare una versione, disinstallate l’altra versione.

Per effettuare l&#39;aggiornamento da una versione precedente dell&#39;app, segui le istruzioni seguenti:

1. Prima di effettuare l’aggiornamento, sincronizzate tutte le risorse e caricate le modifiche  Experience Manager. Questo per evitare di perdere eventuali modifiche durante la disinstallazione dell&#39;app.

1. Disinstallate la versione precedente dell&#39;app. Durante la disinstallazione, selezionate l&#39;opzione per cancellare la cache.

1. Riavviate il computer.

1. [Scaricate](release-notes.md) e [installate](#install-v2) l&#39;app più recente. Seguite le istruzioni riportate di seguito.

## Installare la versione {#install-v2}

Per installare l&#39;app desktop, attenetevi alla seguente procedura. Disinstallare qualsiasi app desktop Adobe Experience Manager esistente v1.x prima di installare l&#39;app più recente. Per ulteriori informazioni, vedi sopra.

1. Scaricate il programma di installazione più recente dalla pagina delle note sulla [versione](release-notes.md) .

1. Tenete a portata di mano l’URL e le credenziali della distribuzione del Experience Manager .

1. Se state effettuando l&#39;aggiornamento da un&#39;altra versione dell&#39;app, consultate [Aggiornare l&#39;app](#upgrade-from-previous-version)desktop.

1. Saltate questo passaggio se utilizzate  Experience Manager come Cloud Service,  Experience Manager 6.4.4 o successivo, o  Experience Manager 6.5.0 o successivo. Verificate che la configurazione del Experience Manager  soddisfi i requisiti di compatibilità indicati nelle note sulla [versione](release-notes.md). Se necessario, scaricate il pacchetto [di](https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/cq640/featurepack/adobe-asset-link-support) compatibilità applicabile e installatelo utilizzando  Experience Manager Package Manager come amministratore di  Experience Manager. Per installare un pacchetto, consultate [Come utilizzare i pacchetti](https://experienceleague.adobe.com/docs/experience-manager-65/administering/contentmanagement/package-manager.html).

1. Eseguite il programma di installazione binario e seguite le istruzioni visualizzate per eseguire l&#39;installazione.

1. In Windows, il programma di installazione potrebbe richiedere l&#39;installazione `Visual Studio C++ Redistributable 2015`. Seguite le istruzioni visualizzate per installarlo. Se l’installazione non riesce, installatela manualmente. Scaricate il programma di installazione da [qui](https://www.microsoft.com/en-us/download/details.aspx?id=52685) e installate sia `vc_redist.x64.exe` che `vc_redist.x86.exe` i file. Eseguite nuovamente il programma di installazione dell&#39;app [!DNL Experience Manager] desktop.

1. Riavviate il computer come richiesto. Avviate e configurate l&#39;app desktop.

1. Per collegare l&#39;app a un [!DNL Experience Manager] repository, fate clic sull&#39;icona dell&#39;app nella barra delle applicazioni e avviate l&#39;app. Fornire l&#39;indirizzo del [!DNL Experience Manager] server nel formato `https://[aem_server]:[port]/`.

   Fare clic su **[!UICONTROL Connect]** e specificare le credenziali.

   ![Schermata di connessione dell&#39;app desktop all&#39;indirizzo del server di input](assets/connect_da2.png)

   *Figura: Schermata di connessione all&#39;indirizzo del server di input.*

   >[!CAUTION]
   >
   >Verificare che non siano presenti spazi iniziali o finali prima o dopo l&#39;indirizzo del [!DNL Experience Manager] server. In caso contrario, l&#39;app non può connettersi al [!DNL Experience Manager] server.

1. Dopo la connessione, puoi visualizzare l’elenco delle cartelle e delle risorse disponibili nella cartella principale di [!DNL Experience Manager] DAM. Potete sfogliare le cartelle dall&#39;interno dell&#39;app.

   ![Al momento dell&#39;accesso, l&#39;app visualizza il contenuto DAM](assets/firstview_da2.png)

   *Figura: L&#39;applicazione visualizza il contenuto DAM dopo l&#39;accesso*

1. ( Experience Manager 6.5.1 o successivo) Se si utilizza l&#39;app desktop con  Experience Manager 6.5.1 o successivo, aggiornare il connettore S3 o Azure alla versione 1.10.4 o successiva. Vedere Connettore [di](https://experienceleague.adobe.com/docs/experience-manager-65/deploying/deploying/data-store-config.html#azure-data-store) Azure o connettore [](https://experienceleague.adobe.com/docs/experience-manager-65/deploying/deploying/data-store-config.html#amazon-s-data-store)S3.

   Se sei un cliente Adobe Managed Services (AMS), contatta &#39;Assistenza clienti del Adobe.

## Impostare le preferenze {#set-preferences}

Per modificare le preferenze, fate clic sull&#39;icona ![Altre opzioni](assets/do-not-localize/more_options_da2.png) e sull&#39;icona **[!UICONTROL Preference]**![ Preferenze](assets/do-not-localize/preferences_icon_da2.png). Nella **[!UICONTROL Preferences]** finestra regolate i valori seguenti:

* [!UICONTROL Launch application on login].

* [!UICONTROL Show window when application starts].

* **[!UICONTROL Cache Directory]**: Posizione della cache locale dell&#39;app (contiene le risorse scaricate localmente).

* **[!UICONTROL Network Drive Letter]**: La lettera di unità utilizzata per mappare il [!DNL Experience Manager] DAM. Non cambiate questo se non siete sicuri. L&#39;app può mappare a qualsiasi lettera di unità in Windows. Se due utenti inseriscono risorse da diverse lettere di unità, non potranno vedere le risorse inserite l’uno dall’altro. Il percorso delle risorse cambia. Le risorse rimangono inserite nel file binario (ad esempio, INDD) e non vengono rimosse. L&#39;app elenca tutte le lettere dell&#39;unità disponibili e per impostazione predefinita utilizza l&#39;ultima lettera disponibile che è in genere `Z`.

* **[!UICONTROL Maximum Cache Size]**: Cache consentita su disco rigido in GB utilizzata per la memorizzazione delle risorse scaricate localmente.

* **[!UICONTROL Current cache size]**: Dimensione dello spazio di archiviazione delle risorse scaricate localmente. Le informazioni vengono visualizzate solo dopo che le risorse sono state scaricate tramite l&#39;app.

* **[!UICONTROL Automatically download linked assets]**: Le risorse inserite nelle app di Creative Cloud native supportate vengono recuperate automaticamente se scaricate il file originale.

* **[!UICONTROL Maximum number of downloads]**: Quando scaricate le risorse per la prima volta (tramite Rivela, Apri, Modifica, Scarica o un’opzione simile), le risorse vengono scaricate solo se il batch contiene meno di questo numero. Il valore predefinito è 50. Non cambiate se non siete sicuri. Aumentare il valore può comportare tempi di attesa più lunghi e ridurre il valore potrebbe non consentire di scaricare le risorse o le cartelle necessarie in una sola volta.

* **[!UICONTROL Upload Acceleration]**: Quando caricate delle risorse, l’applicazione può usare caricamenti simultanei per migliorare la velocità di caricamento. Per aumentare la concorrenza del caricamento, spostate il cursore verso destra. Il cursore sul lato sinistro indica che non esiste una concorrenza (caricamento a thread singolo), che la posizione centrale corrisponde a 10 thread simultanei e che il limite massimo sul lato destro corrisponde a 20 thread simultanei. Un limite di concorrenza più elevato richiede un maggiore consumo di risorse del processore del computer locale.

Per aggiornare le preferenze non disponibili, disconnettetevi dal [!DNL Experience Manager] server. Dopo aver aggiornato le preferenze, fate clic su ![Salva preferenze](assets/do-not-localize/save_preferences_da2.png) per salvare le modifiche.

![Preferenze e impostazioni dell&#39;app desktop](assets/preferences_da2.png)

*Figura: Preferenze per l&#39;app desktop.*

## Disinstallare l&#39;app {#uninstall-the-app}

Per disinstallare l’applicazione in Windows, effettuate le seguenti operazioni:

1. Caricate tutte le modifiche in [!DNL Experience Manager] modo da evitare di perdere eventuali modifiche. Consultate [Modificare le risorse e caricare le risorse aggiornate in [!DNL Experience Manager]](using.md#edit-assets-upload-updated-assets). Disconnettetevi e [!UICONTROL Exit] l&#39;app.

1. Rimuovete l&#39;app quando rimuovete un&#39;altra applicazione del sistema operativo. Disinstallarlo da Aggiungi e rimuovi programmi in Windows.

1. Per rimuovere la cache e i registri, selezionate la casella di controllo necessaria.

   ![Finestra di dialogo di disinstallazione per rimuovere registri e cache](assets/uninstall_da2.png)

1. Seguire le istruzioni visualizzate. Al termine, riavviare il computer.

Per disinstallare l’applicazione in Mac, effettuate le seguenti operazioni:

1. Caricate tutte le modifiche in [!DNL Experience Manager] modo da evitare di perdere eventuali modifiche. Consultate [Modificare le risorse e caricare le risorse aggiornate in [!DNL Experience Manager]](using.md#edit-assets-upload-updated-assets). Disconnettetevi e [!UICONTROL Exit] l&#39;app.

1. Rimuovere la `Adobe Experience Manager Desktop.app` da `/Applications`.

In alternativa, per pulire le cache interne dell&#39;applicazione su Mac e disinstallare l&#39;app, potete eseguire il seguente comando nel terminale:

```shell
/Applications/Adobe Experience Manager Desktop/Contents/Resources/uninstall-osx/uninstall.sh
```
