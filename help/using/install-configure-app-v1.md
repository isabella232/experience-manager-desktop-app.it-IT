---
title: Installare e configurare l’app desktop v1.10
description: Installare e configurare [!DNL Experience Manager] l’app desktop versione 1.10 per lavorare con [!DNL Assets] e mappare le risorse da montare come unità sul desktop.
exl-id: 7f3bdfb1-d345-4e48-b020-6e06531f46f2
source-git-commit: df5283f6bef6adbb007bf93c6dabb3b12e430f58
workflow-type: tm+mt
source-wordcount: '910'
ht-degree: 0%

---

# Installare e configurare [!DNL Experience Manager] app desktop v1.10 {#install-and-configure-aem-desktop-app}

Utilizzo di [!DNL Experience Manager] dell&#39;app desktop, le risorse in [!DNL Experience Manager] sono facilmente accessibili sul desktop locale e possono essere utilizzati in qualsiasi applicazione desktop. Le risorse possono essere facilmente rivelate in Mac Finder o Esplora risorse, aperte in applicazioni desktop e modificate localmente: le modifiche vengono salvate nuovamente in [!DNL Experience Manager] quando carichi e viene creata una nuova versione nell’archivio.

Tale integrazione consente a vari ruoli dell’organizzazione di gestire centralmente le risorse in Assets e di accedervi nella Creative Cloud e in altre applicazioni, semplificando al contempo l’adesione ai vari standard, tra cui il branding.

Da utilizzare [!DNL Experience Manager] app desktop,

* Assicurati che il tuo [!DNL Experience Manager] versione del server supportata da [!DNL Experience Manager] app desktop. Consulta la [matrice di compatibilità](release-notes-of-v1.md#compatibilitymatrix).

* Scarica e installa l’applicazione.

* Verifica la connessione utilizzando alcune risorse. Consulta [Accedere e aprire le risorse sul desktop](use-app-v1.md#openondesktop).

## Requisiti di sistema, prerequisiti e collegamenti per il download {#system-requirements-prerequisites-and-download-links}

Per informazioni dettagliate, vedere [[!DNL Experience Manager] Note sulla versione dell’app desktop](release-notes-of-v1.md).

## Installa e connetti l’app a [!DNL Experience Manager] server {#install-and-connect-aem-desktop-app-to-aem-server}

Per ulteriori informazioni, consulta [Installare e connettersi [!DNL Experience Manager] app desktop a [!DNL Experience Manager] server](use-app-v1.md#installandconnect).

>[!NOTE]
>
>Solo un&#39;istanza del [!DNL Experience Manager] L’app desktop può essere installata e attiva alla volta.

## Gestione dei file {#file-handling}

Quando si modifica un file da un percorso di condivisione di rete montato dall&#39;app desktop, i file vengono salvati in tale percorso in due fasi. Nella prima fase, un file viene salvato localmente. L’utente può salvare il file e continuare a utilizzarlo senza attendere il completamento del trasferimento.

Nella seconda fase, l’app desktop carica il file aggiornato in [!DNL Experience Manager] dopo un ritardo predefinito (ad esempio, 30 secondi). Questa operazione viene eseguita in background. Per visualizzare lo stato dell’operazione di caricamento, utilizza l’opzione Visualizza stato risorsa.

1. Carica una risorsa in Assets.

1. Fai clic su [!DNL Experience Manager] icona dell’app desktop dalla barra degli strumenti.

1. Dal menu, seleziona l’opzione Visualizza stato risorsa.

1. Nella finestra di dialogo, controlla lo stato dell’operazione di caricamento.

>[!NOTE]
>
>[!DNL Experience Manager] L’app desktop può gestire risorse di dimensioni fino a 40 GB.

## Connetti a un [!DNL Experience Manager] istanza dietro un dispatcher {#connect-to-an-aem-instance-behind-a-dispatcher}

I metodi di copia e spostamento nell’API Assets richiedono la trasmissione delle seguenti intestazioni aggiuntive a [!DNL Experience Manager]:

* Destinazione X
* Profondità X
* X-Overwrite

[!DNL Experience Manager] connessione desktop a [!DNL Experience Manager] utilizzando un URL che includa la porta predefinita. Pertanto, la `virtualhosts` l’impostazione nella configurazione del dispatcher deve includere il numero di porta predefinito. Per ulteriori informazioni su `virtualhosts` configurazione, vedi [identificare gli host virtuali](https://experienceleague.adobe.com/docs/experience-manager-dispatcher/using/configuring/dispatcher-configuration.html#identifying-virtual-hosts-virtualhosts).

Per ulteriori informazioni sulla configurazione del dispatcher per passare attraverso queste intestazioni aggiuntive, vedi [Specifica delle intestazioni HTTP](https://experienceleague.adobe.com/docs/experience-manager-dispatcher/using/configuring/dispatcher-configuration.html#specifying-the-http-headers-to-pass-through-clientheaders).

### Supporto proxy {#proxy-support}

[!DNL Experience Manager] L’app desktop utilizza il proxy predefinito del sistema per la connessione a Internet tramite HTTPS. L&#39;app può connettersi solo utilizzando un proxy di rete che non richiede autenticazione aggiuntiva.

Se si configurano o si modificano le impostazioni del server proxy per Windows (Opzioni Internet > Impostazioni LAN), riavviare [!DNL Experience Manager] dell&#39;app desktop per rendere effettive le modifiche.

>[!NOTE]
>
>La configurazione proxy viene applicata solo all&#39;avvio dell&#39;app desktop. Per rendere effettive le modifiche, chiudi e riavvia l’app.

Se il proxy richiede l&#39;autenticazione, il team IT può consentire il passaggio del traffico dell&#39;applicazione mediante l&#39;URL Experience Manager Assets nelle impostazioni del server proxy.

## Personalizzare la finestra di dialogo Informazioni risorsa {#customize-the-asset-info-dialog}

Potete personalizzare la finestra di dialogo Info risorsa sovrapponendo uno o entrambi i componenti:

* La pagina dell’interfaccia utente Granite in `/libs/dam/gui/content/assets/moreinfo`.

* HTL `/css/javascript` componente in `/libs/dam/gui/components/admin/moreinfo`.

Quale componente è sovrapposto, dipende dalla natura della personalizzazione. Per modificare i componenti da visualizzare nella finestra di dialogo Informazioni risorsa, sovrapponi la pagina dell’interfaccia utente Granite. Per modificare il contenuto HTML, CSS o JavaScript della finestra di dialogo, sovrapponi il componente HTL.

## Gestisci cache {#manage-cache}

In Windows, la cache si trova in `%LOCALAPPDATA%\Adobe\AssetsCompanion\Cache\`, dove è una versione codificata del [!DNL Experience Manager] configurato nell&#39;app desktop. Ad esempio: `http://localhost:4502` viene visualizzato come `http%3A%2F%2Flocalhost%3A4502%2F`.

Su Mac OS X, una directory simile si trova in `~/Library/Group Containers/group.com.adobe.aem.desktop/cache`.

### Opzione in-app per gestire la cache {#in-app-option-to-manage-cache}

È possibile controllare la quantità di spazio su disco disponibile per la memorizzazione nella cache locale. Gli artefatti del server Assets vengono memorizzati nella cache locale per un’esperienza più fluida. È possibile modificare le impostazioni predefinite in base alle proprie esigenze. Inoltre, puoi cancellare la cache per recuperare nuovamente tutte le risorse. Per impostare le opzioni desiderate, fai clic sull’icona dell’applicazione e fai clic su **[!UICONTROL Advanced]** > **[!UICONTROL Manage Cache]**. ****

>[!NOTE]
>
>Quando si cancella la cache, vengono mantenute le modifiche non salvate. Tutte le risorse non archiviate [!DNL Experience Manager] vengono mantenuti e non eliminati.

### Cambia la posizione della cache in Windows {#change-location-of-cache-on-windows}

La posizione predefinita della cache per [!DNL Experience Manager] L&#39;app desktop è la seguente:

* In Windows, `%LocalAppData%\Adobe\AssetsCompanion\Cache\EncodedAEMEndpoint`.

* In Mac, `~/Library/Group/Containers/group.com.adobe.aem.desktop/cache/EncodedAEMEndpoint`.

`EncodedAEMEndpoint` è l’app configurata [!DNL Experience Manager] URL endpoint. Il valore è una versione codificata dell’URL di targeting del [!DNL Experience Manager] server. Ad esempio, se l’applicazione è il targeting `http://localhost:4502`, il nome della directory è `http%3A%2F%2Flocalhost%3A4502`. Il percorso Windows della directory cache in questo esempio è `%LocalAppData%\Adobe\AssetsCompanion\Cache\http%3A%2F%2Flocalhost%3A4502`.

Per puntare l&#39;applicazione a una cartella diversa o a un&#39;unità diversa, modificare il file di configurazione dell&#39;applicazione.

1. Passa alla directory di installazione dell’app. Il percorso predefinito in Windows è `C:\Program Files (x86)\Adobe\Adobe Experience Manager Desktop`.

1. Modificare il file Adobe Experience Manager Desktop.exe.config con un editor di testo.

   Per salvare le modifiche apportate al file sono necessari privilegi di amministratore.

1. Cercare la stringa &quot;ProxyCacheRoot&quot;. Il valore è impostato sulla posizione della cache `%LocalAppData%\Adobe\AssetsCompanion\Cache`. È sufficiente modificare questo valore in qualsiasi percorso valido.

   >[!NOTE]
   >
   >L’app crea automaticamente un’ *&lt;encoded aem=&quot;&quot; endpoint=&quot;&quot;>* sottodirectory. Questo comportamento non è configurabile.

>[!MORELIKETHIS]
>
* [Introduzione a [!DNL Experience Manager] app desktop](https://experienceleague.adobe.com/docs/experience-manager-learn/assets/creative-workflows/aem-desktop-app.html).
* [Utilizzare [!DNL Experience Manager] app desktop](use-app-v1.md).
* [Risoluzione dei problemi [!DNL Experience Manager] app desktop](troubleshoot-app-v1.md).
