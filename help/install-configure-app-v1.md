---
title: Installare e configurare AEM app desktop versione 1.x
description: Installate e configurate AEM app desktop versione 1.x per lavorare con  server AEM Assets e mappate le risorse da montare come unità sul desktop.
uuid: 79bc9de9-5708-41f9-ac43-68c1fd2a2129
contentOwner: AG
products: SG_EXPERIENCEMANAGER/6.5/ASSETS, SG_EXPERIENCEMANAGER/6.4/ASSETS,SG_EXPERIENCEMANAGER/6.3/ASSETS
discoiquuid: f6365302-1690-4719-9b8c-035719422740
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: ef87dc011297fda181a9a7643a261e8a42e35a8b
workflow-type: tm+mt
source-wordcount: '984'
ht-degree: 0%

---


# Installazione e configurazione AEM app desktop v1.x {#install-and-configure-aem-desktop-app}

Utilizzando l&#39;app desktop AEM, le risorse all&#39;interno AEM sono facilmente accessibili sul desktop locale e possono essere utilizzate in qualsiasi applicazione desktop. Le risorse possono essere rivelate facilmente in Mac Finder o Windows Explorer, aperte nelle applicazioni desktop e modificate localmente - le modifiche vengono salvate in AEM al momento del caricamento e viene creata una nuova versione nell&#39;archivio.

Tale integrazione consente a diversi ruoli dell’organizzazione di gestire le risorse centralmente in  AEM Assets e di accedervi nella Creative Cloud e in altre applicazioni, semplificando al contempo il rispetto dei vari standard, tra cui il branding.

Per utilizzare AEM&#39;app desktop,

* Verificate che la versione del server AEM sia supportata AEM&#39;app desktop. Vedere la matrice [di](release-notes-of-v1.md#compatibilitymatrix)compatibilità.

* Scaricate e installate l&#39;applicazione.

* Verificare la connessione utilizzando alcune risorse. Consultate [Accedere e aprire le risorse sul desktop](use-app-v1.md#openondesktop).

## Requisiti di sistema, prerequisiti e collegamenti per il download {#system-requirements-prerequisites-and-download-links}

Per informazioni dettagliate, consultate le [AEM note](release-notes-of-v1.md)sulla versione dell&#39;app desktop.

## Installare e collegare AEM&#39;app desktop al server AEM {#install-and-connect-aem-desktop-app-to-aem-server}

Per informazioni dettagliate, consultate [Installare e collegare AEM&#39;app desktop a AEM server](use-app-v1.md#installandconnect).

>[!NOTE]
>
>È possibile installare e attivare una sola istanza dell&#39;app desktop AEM alla volta.

## Gestione dei file {#file-handling}

Quando si modifica un file da un percorso di condivisione di rete montato dall&#39;app desktop, i file vengono salvati in tale percorso in due fasi. Nella prima fase, un file viene salvato localmente. Un utente può salvare il file e continuare a lavorare sul file, senza attendere il completamento del trasferimento.

Nella seconda fase, l&#39;app desktop carica il file aggiornato AEM server dopo un ritardo predefinito (ad esempio, 30). Questa operazione si verifica in background. Usate l’opzione Visualizza stato risorsa per visualizzare lo stato dell’operazione di caricamento.

1. Caricate una risorsa in  AEM Assets.

1. Tocca o fai clic sull&#39;icona dell&#39;app desktop AEM dalla barra degli strumenti.

1. Dal menu, selezionate l’opzione Visualizza stato risorsa.

1. Dalla finestra di dialogo, controllate lo stato dell’operazione di caricamento.

>[!NOTE]
>
>AEM&#39;app desktop può gestire risorse fino a 40 GB.

## Connettersi a un&#39;istanza AEM dietro a un dispatcher {#connect-to-an-aem-instance-behind-a-dispatcher}

I metodi di copia e spostamento nell’API Assets richiedono il passaggio delle seguenti intestazioni aggiuntive a AEM:

* Destinazione X
* Profondità X
* Sovrascrivi X

AEM desktop si connette a AEM utilizzando un URL che include la porta predefinita. Pertanto, l&#39; `virtualhosts` impostazione nella configurazione del dispatcher deve includere il numero di porta predefinito. Per ulteriori informazioni sulla `virtualhosts` configurazione, vedi [identificare gli host](https://docs.adobe.com/content/help/en/experience-manager-dispatcher/using/configuring/dispatcher-configuration.html#identifying-virtual-hosts-virtualhosts)virtuali.

Per ulteriori informazioni sulla configurazione del dispatcher per il passaggio tra queste intestazioni aggiuntive, vedere [Specifica delle intestazioni](https://docs.adobe.com/content/help/en/experience-manager-dispatcher/using/configuring/dispatcher-configuration.html#specifying-the-http-headers-to-pass-through-clientheaders)HTTP.

### Supporto proxy {#proxy-support}

AEM&#39;app desktop utilizza il proxy predefinito del sistema per connettersi a Internet tramite HTTPS. L&#39;app può connettersi solo utilizzando un proxy di rete che non richiede un&#39;autenticazione aggiuntiva.

Se configurate o modificate le impostazioni del server proxy per Windows (Opzioni Internet > Impostazioni LAN), riavviate l&#39;app desktop AEM affinché le modifiche abbiano effetto.

>[!NOTE]
>
>La configurazione del proxy viene applicata solo quando avviate l&#39;app desktop. Chiudete e riavviate l&#39;app per rendere effettive eventuali modifiche.

Se il proxy richiede l’autenticazione, il team IT può consentire l’accesso all’URL delle risorse del Experience Manager  nelle impostazioni del server proxy per consentire il passaggio del traffico dell’applicazione.

## Personalizzare la finestra di dialogo Informazioni risorsa {#customize-the-asset-info-dialog}

Per personalizzare la finestra di dialogo Informazioni risorsa, sovrapponete uno o entrambi i seguenti componenti:

* La pagina dell&#39;interfaccia utente Granite all&#39;indirizzo `/libs/dam/gui/content/assets/moreinfo`.

* Il `/css/javascript` componente HTL in `/libs/dam/gui/components/admin/moreinfo`.

Il componente sovrapposto dipende dalla natura della personalizzazione. Per modificare i componenti visualizzati come parte della finestra di dialogo Informazioni risorsa, sovrapponete la pagina dell’interfaccia utente Granite. Per modificare il contenuto HTML, CSS o Javascript della finestra di dialogo, sovrapponete il componente HTL.

## Gestione cache {#manage-cache}

In Windows, la cache si trova nella posizione `%LOCALAPPDATA%\Adobe\AssetsCompanion\Cache\`, dove è una versione codificata dell&#39;host AEM configurato nell&#39;app desktop. Ad esempio, `http://localhost:4502` viene visualizzato come `http%3A%2F%2Flocalhost%3A4502%2F`.

In Mac OS X, è presente una directory simile `~/Library/Group Containers/group.com.adobe.aem.desktop/cache`.

### Opzione in-app per gestire la cache {#in-app-option-to-manage-cache}

È possibile controllare la quantità di spazio su disco disponibile per il caching locale. Gli artefatti del server AEM Assets  vengono memorizzati nella cache locale per un&#39;esperienza più fluida. Potete modificare le impostazioni predefinite in base alle vostre esigenze. Inoltre, potete cancellare la cache per recuperare nuovamente tutte le risorse. Per impostare le opzioni desiderate, fate clic sull&#39;icona dell&#39;applicazione e fate clic su **[!UICONTROL Advanced]** > **[!UICONTROL Manage Cache]**. ****

>[!NOTE]
>
>Quando si cancella la cache, vengono mantenute le modifiche non salvate. Tutte le risorse non archiviate AEM server vengono mantenute e non eliminate.

### Modifica della posizione della cache in Windows {#change-location-of-cache-on-windows}

Il percorso predefinito della cache per l&#39;app desktop AEM è il seguente:

* In Windows, `%LocalAppData%\Adobe\AssetsCompanion\Cache\EncodedAEMEndpoint`.

* In Mac, `~/Library/Group/Containers/group.com.adobe.aem.desktop/cache/EncodedAEMEndpoint`.

`EncodedAEMEndpoint` è AEM l&#39;URL AEM endpoint configurato dall&#39;app desktop. Il valore è una versione codificata dell&#39;URL di targeting del server AEM. Ad esempio, se l&#39;applicazione esegue il targeting `http://localhost:4502`, il nome della directory è `http%3A%2F%2Flocalhost%3A4502`. Il percorso di Windows alla directory della cache in questo esempio è `%LocalAppData%\Adobe\AssetsCompanion\Cache\http%3A%2F%2Flocalhost%3A4502`.

Per indirizzare l&#39;applicazione a una cartella diversa o a un&#39;altra unità, modificare il file di configurazione dell&#39;applicazione.

1. Andate alla directory di installazione dell&#39;app. Il percorso predefinito in Windows è `C:\Program Files (x86)\Adobe\Adobe Experience Manager Desktop`.

1. Modificate il file Adobe Experience Manager Desktop.exe.config con un editor di testo.

   Per salvare le modifiche apportate a questo file sono necessari privilegi di amministratore.

1. Cercare la stringa &quot;ProxyCacheRoot&quot;. Il relativo valore è impostato sulla posizione della cache `%LocalAppData%\Adobe\AssetsCompanion\Cache`. È sufficiente modificare questo valore in qualsiasi percorso valido.

   >[!NOTE]
   >
   >L&#39;app crea automaticamente una sottodirectory *&lt;Encoded AEM Endpoint>* . Questo comportamento non è configurabile.

>[!MORELIKETHIS]
* [Introduzione all’app desktop AEM](https://helpx.adobe.com/customer-care-office-hours/aem/desktop-app.html)
* [Usare l’app desktop AEM](use-app-v1.md)
* [Informazioni sul check-in/check-out con AEM&#39;app desktop](https://docs.adobe.com/content/help/en/experience-manager-learn/assets/collaboration/checkin-checkout-technical-video-understand.html)
* [Utilizzo dell&#39;app desktop con  AEM Assets](https://docs.adobe.com/content/help/en/experience-manager-learn/assets/collaboration/checkin-checkout-technical-video-understand.html)
* [Risoluzione dei problemi AEM&#39;app desktop](troubleshoot-app-v1.md)

