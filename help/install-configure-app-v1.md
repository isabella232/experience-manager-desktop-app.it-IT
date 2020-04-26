---
title: Installare e configurare l'app desktop AEM versione 1.x
description: Installa e configura l’app desktop AEM versione 1.x per lavorare con i server Risorse AEM e mappa le risorse da montare come unità sul desktop.
uuid: 79bc9de9-5708-41f9-ac43-68c1fd2a2129
contentOwner: AG
products: SG_EXPERIENCEMANAGER/6.3/ASSETS
discoiquuid: f6365302-1690-4719-9b8c-035719422740
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b92e47456f9e16c24eac43d1c5fef9a582f143b5

---


# Installare e configurare l&#39;app desktop AEM v1.x {#install-and-configure-aem-desktop-app}

Utilizzando l’app desktop AEM, le risorse all’interno di AEM sono facilmente accessibili sul desktop locale e possono essere utilizzate in qualsiasi applicazione desktop. Le risorse possono essere rivelate facilmente in Mac Finder o Windows Explorer, aperte nelle applicazioni desktop e modificate localmente; le modifiche vengono salvate nuovamente in AEM al momento del caricamento e viene creata una nuova versione nell’archivio.

Questa integrazione consente a diversi ruoli dell’organizzazione di gestire le risorse a livello centrale in Risorse AEM e di accedervi in Creative Cloud e altre applicazioni, semplificando al contempo il rispetto dei vari standard, compreso il branding.

Per utilizzare l&#39;app desktop AEM,

* Verificate che la versione del server AEM sia supportata dall&#39;app desktop AEM. Vedere la matrice [di](release-notes-of-v1.md#compatibilitymatrix)compatibilità.
* Scaricate e installate l&#39;applicazione.
* Verificare la connessione utilizzando alcune risorse. Consultate [Accedere e aprire le risorse sul desktop](use-app-v1.md#openondesktop).

## Requisiti di sistema, prerequisiti e collegamenti per il download {#system-requirements-prerequisites-and-download-links}

Per informazioni dettagliate, consultate le note [sulla versione dell&#39;app desktop](release-notes-of-v1.md)AEM.

## Installare e collegare l&#39;app desktop AEM al server AEM {#install-and-connect-aem-desktop-app-to-aem-server}

Per informazioni dettagliate, consultate [Installare e collegare l&#39;app desktop AEM al server](use-app-v1.md#installandconnect)AEM.

>[!NOTE]
>
>È possibile installare e attivare una sola istanza dell&#39;app desktop AEM alla volta.

## Supporto proxy {#proxy-support}

L&#39;app desktop AEM utilizza il proxy predefinito del sistema per connettersi a Internet mediante il protocollo HTTPS. L&#39;app può connettersi solo utilizzando un proxy di rete che non richiede un&#39;autenticazione aggiuntiva.

Se configurate o modificate le impostazioni del server proxy per Windows (Opzioni Internet > Impostazioni LAN), riavviate l&#39;app desktop AEM per rendere effettive le modifiche.

Se il proxy richiede l’autenticazione, il team IT può inserire l’URL di Risorse AEM nelle impostazioni del server proxy per consentire il passaggio del traffico dell’applicazione.

## Gestione dei file {#file-handling}

Quando si modifica un file da un percorso di condivisione di rete montato dall&#39;app desktop, i file vengono salvati in tale percorso in due fasi. Nella prima fase, un file viene salvato localmente. Un utente può salvare il file e continuare a lavorare sul file, senza attendere il completamento del trasferimento.

Nella seconda fase, l&#39;app desktop carica il file aggiornato nel server AEM dopo un ritardo predefinito (ad esempio, 30). Questa operazione si verifica in background. Usate l’opzione Visualizza stato risorsa per visualizzare lo stato dell’operazione di caricamento.

1. Carica una risorsa in AEM Assets.
1. Tocca o fai clic sull&#39;icona dell&#39;app desktop AEM dalla barra degli strumenti.
1. Dal menu, selezionate l’opzione Visualizza stato risorsa.
1. Dalla finestra di dialogo, controllate lo stato dell’operazione di caricamento.

>[!NOTE]
>
>L’app desktop AEM può gestire risorse fino a 40 GB.

## Connessione a un’istanza di AEM dietro un dispatcher {#connect-to-an-aem-instance-behind-a-dispatcher}

I metodi di copia e spostamento nell’API Assets richiedono il passaggio ad AEM delle seguenti intestazioni aggiuntive:

* Destinazione X
* Profondità X
* Sovrascrivi X

AEM Desktop si connette ad AEM utilizzando un URL che include la porta predefinita. Pertanto, l&#39; `virtualhosts` impostazione nella configurazione del dispatcher deve includere il numero di porta predefinito. Per ulteriori informazioni sulla `virtualhosts` configurazione, consultate [Identificazione degli host](https://docs.adobe.com/content/help/en/experience-manager-dispatcher/using/configuring/dispatcher-configuration.html#identifying-virtual-hosts-virtualhosts)virtuali.

Per ulteriori informazioni sulla configurazione del dispatcher per il passaggio tra queste intestazioni aggiuntive, vedere [Specifica delle intestazioni](https://docs.adobe.com/content/help/en/experience-manager-dispatcher/using/configuring/dispatcher-configuration.html#specifying-the-http-headers-to-pass-through-clientheaders)HTTP.

## Personalizzare la finestra di dialogo Informazioni risorsa {#customize-the-asset-info-dialog}

Per personalizzare la finestra di dialogo Informazioni risorsa, sovrapponete uno o entrambi i seguenti componenti:

* La pagina dell&#39;interfaccia utente Granite all&#39;indirizzo `/libs/dam/gui/content/assets/moreinfo`
* Il componente HTL `/css/javascript` in `/libs/dam/gui/components/admin/moreinfo`

Il componente sovrapposto dipende dalla natura della personalizzazione. Per modificare i componenti visualizzati come parte della finestra di dialogo Informazioni risorsa, sovrapponete la pagina dell’interfaccia utente Granite. Per modificare il contenuto HTML/CSS/Javascript della finestra di dialogo, sovrapponete il componente HTL.

## Gestione cache {#manage-cache}

In Windows, la cache si trova nella posizione `%LOCALAPPDATA%\Adobe\AssetsCompanion\Cache\`, dove si trova una versione codificata dell&#39;host AEM configurato nell&#39;app desktop. Ad esempio, `http://localhost:4502` viene visualizzato come `http%3A%2F%2Flocalhost%3A4502%2F`.

In Mac OS X, è presente una directory simile `~/Library/Group Containers/group.com.adobe.aem.desktop/cache`.

### Opzione in-app per gestire la cache {#in-app-option-to-manage-cache}

È possibile controllare la quantità di spazio su disco disponibile per il caching locale. Gli artefatti del server AEM Assets sono memorizzati nella cache locale per un’esperienza più fluida. Potete modificare le impostazioni predefinite in base alle vostre esigenze. Inoltre, potete cancellare la cache per recuperare nuovamente tutte le risorse. Per impostare le opzioni desiderate, fate clic sull&#39;icona dell&#39;applicazione e fate clic su **[!UICONTROL Advanced]** > **[!UICONTROL Manage Cache]**. ****

>[!NOTE]
>
>Quando si cancella la cache, vengono mantenute le modifiche non salvate. Eventuali risorse non archiviate nel server AEM vengono mantenute e non eliminate.

### Modifica della posizione della cache in Windows {#change-location-of-cache-on-windows}

Il percorso predefinito della cache per l&#39;app desktop AEM è:

* Windows: `%LocalAppData%\Adobe\AssetsCompanion\Cache\EncodedAEMEndpoint`
* Mac: `~/Library/Group/Containers/group.com.adobe.aem.desktop/cache/EncodedAEMEndpoint`

`EncodedAEMEndpoint` è l&#39;URL dell&#39;endpoint AEM configurato dall&#39;app desktop AEM. Il valore è una versione codificata dell’URL di destinazione del server AEM. Ad esempio, se l&#39;applicazione esegue il targeting `http://localhost:4502`, il nome della directory è `http%3A%2F%2Flocalhost%3A4502`. Il percorso di Windows alla directory della cache in questo esempio è %LocalAppData%\Adobe\AssetsCompanion\Cache\http%3A%2F%2Flocalhost%3A4502.

Per indirizzare l&#39;applicazione a una cartella diversa o a un&#39;altra unità, modificare il file di configurazione dell&#39;applicazione.

1. Andate alla directory di installazione dell&#39;app. Il percorso predefinito in Windows è `C:\Program Files (x86)\Adobe\Adobe Experience Manager Desktop`.
1. Modificate il file Adobe Experience Manager Desktop.exe.config con un editor di testo.

   Per salvare le modifiche apportate a questo file sono necessari privilegi di amministratore.

1. Cercare la stringa &quot;ProxyCacheRoot&quot;. Il valore è impostato sulla posizione della cache &quot;%LocalAppData%\Adobe\AssetsCompanion\Cache&quot;. È sufficiente modificare questo valore in qualsiasi percorso valido.

   >[!NOTE]
   >
   >L&#39;app crea automaticamente una sottodirectory *&lt;Encoded AEM Endpoint>* ; questo comportamento non è configurabile.

## Altro materiale di riferimento {#additional-resources}

* [Introduzione all’app desktop AEM](https://helpx.adobe.com/customer-care-office-hours/aem/desktop-app.html)
* [Usare l’app desktop AEM](use-app-v1.md)

* [Informazioni sul check-in/check-out con l’app desktop AEM](https://docs.adobe.com/content/help/en/experience-manager-learn/assets/collaboration/checkin-checkout-technical-video-understand.html)
* [Utilizzo dell&#39;app desktop con AEM Assets](https://docs.adobe.com/content/help/en/experience-manager-learn/assets/collaboration/checkin-checkout-technical-video-understand.html)
* [Risoluzione dei problemi dell&#39;app desktop AEM](troubleshoot-app-v1.md)
