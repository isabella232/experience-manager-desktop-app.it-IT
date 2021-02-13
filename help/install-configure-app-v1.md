---
title: Installazione e configurazione dell'app desktop v1.10
description: Installate e configurate i server [!DNL Experience Manager] desktop app version 1.10 to work with [!DNL Assets] e mappate le risorse da montare come unità sul desktop.
translation-type: tm+mt
source-git-commit: cc4ce762ad1d7f4c5a54ab6bac9d1a872e3d18c9
workflow-type: tm+mt
source-wordcount: '901'
ht-degree: 0%

---


# Installazione e configurazione dell&#39;app desktop [!DNL Experience Manager] v1.10 {#install-and-configure-aem-desktop-app}

Utilizzando l&#39;app desktop [!DNL Experience Manager], le risorse all&#39;interno di [!DNL Experience Manager] sono facilmente accessibili sul desktop locale e possono essere utilizzate in qualsiasi applicazione desktop. Le risorse possono essere rivelate facilmente in Mac Finder o Windows Explorer, aperte nelle applicazioni desktop e modificate localmente; le modifiche vengono salvate in [!DNL Experience Manager] al momento del caricamento e viene creata una nuova versione nell&#39;archivio.

Questa integrazione consente a diversi ruoli dell’organizzazione di gestire le risorse centralmente in Risorse e di accedervi nella Creative Cloud e in altre applicazioni, semplificando al contempo il rispetto dei vari standard, tra cui il branding.

Per utilizzare l&#39;app desktop [!DNL Experience Manager],

* Verificate che la versione del server [!DNL Experience Manager] sia supportata dall&#39;app desktop [!DNL Experience Manager]. Vedere la [matrice di compatibilità](release-notes-of-v1.md#compatibilitymatrix).

* Scaricate e installate l&#39;applicazione.

* Verificare la connessione utilizzando alcune risorse. Consultate [Accesso e apertura delle risorse sul desktop](use-app-v1.md#openondesktop).

## Requisiti di sistema, prerequisiti e collegamenti per il download {#system-requirements-prerequisites-and-download-links}

Per informazioni dettagliate, consultate le [[!DNL Experience Manager] note sulla versione dell&#39;app desktop](release-notes-of-v1.md).

## Installare e collegare l&#39;app al server [!DNL Experience Manager] {#install-and-connect-aem-desktop-app-to-aem-server}

Per informazioni dettagliate, vedere [Installazione e connessione [!DNL Experience Manager] desktop app to [!DNL Experience Manager] server](use-app-v1.md#installandconnect).

>[!NOTE]
>
>È possibile installare e attivare una sola istanza dell&#39;app desktop [!DNL Experience Manager] alla volta.

## Gestione file {#file-handling}

Quando si modifica un file da un percorso di condivisione di rete montato dall&#39;app desktop, i file vengono salvati in tale percorso in due fasi. Nella prima fase, un file viene salvato localmente. Un utente può salvare il file e continuare a lavorare sul file, senza attendere il completamento del trasferimento.

Nella seconda fase, l&#39;app desktop carica il file aggiornato sul server [!DNL Experience Manager] dopo un ritardo predefinito (ad esempio, 30). Questa operazione si verifica in background. Usate l’opzione Visualizza stato risorsa per visualizzare lo stato dell’operazione di caricamento.

1. Caricate una risorsa in Risorse.

1. Fate clic sull&#39;icona dell&#39;app desktop [!DNL Experience Manager] dalla barra degli strumenti.

1. Dal menu, selezionate l’opzione Visualizza stato risorsa.

1. Dalla finestra di dialogo, controllate lo stato dell’operazione di caricamento.

>[!NOTE]
>
>[!DNL Experience Manager] l’app desktop può gestire risorse fino a 40 GB di dimensione.

## Connettersi a un&#39;istanza [!DNL Experience Manager] dietro a un dispatcher {#connect-to-an-aem-instance-behind-a-dispatcher}

I metodi di copia e spostamento nell&#39;API Assets richiedono il passaggio delle seguenti intestazioni aggiuntive a [!DNL Experience Manager]:

* Destinazione X
* Profondità X
* Sovrascrivi X

[!DNL Experience Manager] il desktop si connette a  [!DNL Experience Manager] un URL che include la porta predefinita. Pertanto, l&#39;impostazione `virtualhosts` nella configurazione del dispatcher deve includere il numero di porta predefinito. Per ulteriori informazioni sulla configurazione `virtualhosts`, vedere [identificare gli host virtuali](https://experienceleague.adobe.com/docs/experience-manager-dispatcher/using/configuring/dispatcher-configuration.html#identifying-virtual-hosts-virtualhosts).

Per ulteriori informazioni sulla configurazione del dispatcher per passare attraverso queste intestazioni aggiuntive, vedere [Specifica delle intestazioni HTTP](https://experienceleague.adobe.com/docs/experience-manager-dispatcher/using/configuring/dispatcher-configuration.html#specifying-the-http-headers-to-pass-through-clientheaders).

### Supporto proxy {#proxy-support}

[!DNL Experience Manager] l&#39;app desktop utilizza il proxy predefinito del sistema per connettersi a Internet tramite HTTPS. L&#39;app può connettersi solo utilizzando un proxy di rete che non richiede un&#39;autenticazione aggiuntiva.

Se configurate o modificate le impostazioni del server proxy per Windows (Opzioni Internet > Impostazioni LAN), riavviate l&#39;app desktop [!DNL Experience Manager] per rendere effettive le modifiche.

>[!NOTE]
>
>La configurazione del proxy viene applicata solo quando avviate l&#39;app desktop. Chiudete e riavviate l&#39;app per rendere effettive eventuali modifiche.

Se il proxy richiede l’autenticazione, il team IT può consentire l’accesso all’URL delle risorse del Experience Manager  nelle impostazioni del server proxy per consentire il passaggio del traffico dell’applicazione.

## Personalizzare la finestra di dialogo Informazioni risorsa {#customize-the-asset-info-dialog}

Per personalizzare la finestra di dialogo Informazioni risorsa, sovrapponete uno o entrambi i seguenti componenti:

* La pagina dell&#39;interfaccia utente Granite in `/libs/dam/gui/content/assets/moreinfo`.

* Il componente HTL `/css/javascript` in `/libs/dam/gui/components/admin/moreinfo`.

Il componente sovrapposto dipende dalla natura della personalizzazione. Per modificare i componenti visualizzati come parte della finestra di dialogo Informazioni risorsa, sovrapponete la pagina dell’interfaccia utente Granite. Per modificare il contenuto HTML, CSS o JavaScript della finestra di dialogo, sovrapponete il componente HTL.

## Gestione cache {#manage-cache}

In Windows, la cache si trova in `%LOCALAPPDATA%\Adobe\AssetsCompanion\Cache\`, dove è una versione codificata dell&#39;host [!DNL Experience Manager] configurato nell&#39;app desktop. Ad esempio, `http://localhost:4502` viene visualizzato come `http%3A%2F%2Flocalhost%3A4502%2F`.

In Mac OS X, una directory simile si trova in `~/Library/Group Containers/group.com.adobe.aem.desktop/cache`.

### Opzione in-app per gestire la cache {#in-app-option-to-manage-cache}

È possibile controllare la quantità di spazio su disco disponibile per il caching locale. Gli artefatti del server Risorse vengono memorizzati nella cache locale per un’esperienza più fluida. Potete modificare le impostazioni predefinite in base alle vostre esigenze. Inoltre, potete cancellare la cache per recuperare nuovamente tutte le risorse. Per impostare le opzioni desiderate, fate clic sull&#39;icona dell&#39;applicazione e fate clic su **[!UICONTROL Advanced]** > **[!UICONTROL Manage Cache]**. ****

>[!NOTE]
>
>Quando si cancella la cache, vengono mantenute le modifiche non salvate. Tutte le risorse non archiviate nel server [!DNL Experience Manager] vengono mantenute e non eliminate.

### Modifica della posizione della cache in Windows {#change-location-of-cache-on-windows}

Il percorso predefinito della cache per l&#39;app [!DNL Experience Manager] desktop è il seguente:

* In Windows, `%LocalAppData%\Adobe\AssetsCompanion\Cache\EncodedAEMEndpoint`.

* In Mac, `~/Library/Group/Containers/group.com.adobe.aem.desktop/cache/EncodedAEMEndpoint`.

`EncodedAEMEndpoint` è l&#39;URL dell&#39; [!DNL Experience Manager] endpoint configurato dall&#39;app. Il valore è una versione codificata dell&#39;URL di destinazione del server [!DNL Experience Manager]. Ad esempio, se l&#39;applicazione ha come destinazione `http://localhost:4502`, il nome della directory è `http%3A%2F%2Flocalhost%3A4502`. Il percorso di Windows alla directory della cache in questo esempio è `%LocalAppData%\Adobe\AssetsCompanion\Cache\http%3A%2F%2Flocalhost%3A4502`.

Per indirizzare l&#39;applicazione a una cartella diversa o a un&#39;altra unità, modificare il file di configurazione dell&#39;applicazione.

1. Andate alla directory di installazione dell&#39;app. Il percorso predefinito in Windows è `C:\Program Files (x86)\Adobe\Adobe Experience Manager Desktop`.

1. Modificate il file Adobe Experience Manager Desktop.exe.config con un editor di testo.

   Per salvare le modifiche apportate a questo file sono necessari privilegi di amministratore.

1. Cercare la stringa &quot;ProxyCacheRoot&quot;. Il relativo valore è impostato sulla posizione della cache `%LocalAppData%\Adobe\AssetsCompanion\Cache`. È sufficiente modificare questo valore in qualsiasi percorso valido.

   >[!NOTE]
   >
   >L&#39;app crea automaticamente una sottodirectory *&lt;Encoded AEM Endpoint>*. Questo comportamento non è configurabile.

>[!MORELIKETHIS]
* [Introduzione  [!DNL Experience Manager] all&#39;app](https://experienceleague.adobe.com/docs/experience-manager-learn/assets/creative-workflows/aem-desktop-app.html) desktop.
* [ [!DNL Experience Manager] Utilizzate l&#39;app](use-app-v1.md) desktop.
* [Risoluzione  [!DNL Experience Manager] dei problemi relativi all&#39;app](troubleshoot-app-v1.md) desktop.

