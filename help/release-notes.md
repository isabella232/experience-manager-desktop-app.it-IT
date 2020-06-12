---
title: Note sulla versione dell’app desktop Adobe Experience Manager
description: Dettagli sulla versione, miglioramenti, nuove funzioni, compatibilità e collegamenti per il download per l’app desktop Adobe Experience Manager.
uuid: b783c3f8-aa1e-4c05-b687-5894909769f5
contentOwner: AG
products: SG_EXPERIENCEMANAGER/6.3/ASSETS
discoiquuid: 3052549b-fe75-44fb-a55e-5cc612868f54
index: y
internal: n
snippet: y
mini-toc-levels: 1
translation-type: tm+mt
source-git-commit: 2e634c13ef1bcb0cd1868100f5a2d7cb20c189be
workflow-type: tm+mt
source-wordcount: '1318'
ht-degree: 50%

---


# Note sulla versione dell’app desktop Adobe Experience Manager {#release-notes-v2}

| Prodotti | App desktop Adobe Experience Manager |
|----|----|
| Versione dell’app (revisione) | 2.0 (2.0.2.0) |
| Versioni di AEM supportate | AEM come servizio cloud; AEM 6.5; AEM 6.4; AEM 6.3 (con pacchetto di compatibilità) |
| Tipo | Rilascio secondario |
| Data di rilascio | 15 aprile 2020 (Mac e Win) |
| URL di download | [macOS a 64 bit](https://download.macromedia.com/aem-assets-companion-app/aem-desktop-osx-2.0.2.0.dmg); [Windows a 64 bit](https://download.macromedia.com/aem-assets-companion-app/aem-desktop-win64-2.0.2.0.exe); [Windows a 32 bit](https://download.macromedia.com/aem-assets-companion-app/aem-desktop-win32-2.0.2.0.exe) |

## Requisiti di sistema e prerequisiti {#system-requirements-and-prerequisites-v2}

L’app desktop Adobe Experience Manager è compatibile con i seguenti sistemi operativi:

* Mac OS X 10.10 o versione successiva, con correzioni di bug più recenti.
* Windows 7 e Windows 10 con Service Pack e correzioni di bug più recenti.

L&#39;app funziona con le seguenti versioni di Experience Manager, sia che sia distribuita come servizio cloud, sui servizi gestiti Adobe (AMS) o in sede:

* [Experience Manager as a Cloud Service](https://docs.adobe.com/content/help/it-IT/experience-manager-cloud-service/release-notes/home.html)
* [Experience Manager 6.5.0](https://docs.adobe.com/content/help/en/experience-manager-65/release-notes/release-notes.html) o successivo
* [Experience Manager 6.4.4](https://docs.adobe.com/content/help/en/experience-manager-64/release-notes/release-notes.html) o successivo
* Experience Manager 6.4.0 - 6.4.3 con pacchetto di [compatibilità](https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/cq640/featurepack/adobe-asset-link-support)

>[!NOTE]
>
>Il supporto delle app desktop per Experience Manager 6.3 è obsoleto. Adobe consiglia di effettuare l&#39;aggiornamento a una versione più recente e supportata di Adobe Experience Manager.
>Experience Manager 6.3.3.1 o versione successiva funziona con l&#39;app desktop dopo l&#39;installazione del pacchetto [di](https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/cq640/featurepack/adobe-asset-link-support)compatibilità. Nessun pacchetto di questo tipo è disponibile per Experience Manager 6.3 in quanto non sono pianificati [pacchetti di](https://helpx.adobe.com/it/experience-manager/maintenance-releases-roadmap.html)servizi.

La versione dell’app che intendi installare nel computer locale richiede una versione specifica del server Adobe Experience Manager o componenti aggiuntivi lato server (Service Pack, hotfix o feature pack). Contatta il tuo amministratore Adobe Experience Manager per assistenza.

### Support for different assets and file types {#support-for-file-types}

L’applicazione supporta le risorse memorizzate in Adobe Experience Manager che rappresentano file binari per le operazioni di base. L’apertura di file nell’applicazione desktop nativa si basa sull’associazione del sistema operativo dei tipi di file specifici, come PNG o JPG, ad applicazioni specifiche, come Mac Preview o Adobe Photoshop.

Alcuni tipi di file supportano il posizionamento di risorse collegate nel file binario. L’applicazione pre-scarica le risorse collegate se la risorsa è presente nell’archivio Experience Manager quando tali file binari vengono aperti tramite l’app desktop. I tipi di file attualmente supportati sono:

* File Adobe InDesign (formato INDD)
* File Adobe Illustrator (formato AI)
* File Adobe Photoshop (formato PS)

Questa funzione è supportata dalle versioni di Adobe Creative Cloud 2018 e Adobe Creative Cloud 2019 dell&#39;applicazione precedente. L’app utilizza un approccio euristico e con la migliore corrispondenza per mappare i percorsi desktop locali delle risorse collegate agli URL sul server Experience Manager. Si basa su alcuni presupposti descritti di seguito:

* Paths to placed files in the native application use a global desktop path (placed from the local network share shown with [!UICONTROL Reveal] option).
* I percorsi vengono memorizzati nel record XMP del file dall&#39;app nativa.
* Experience Manager ha estratto il record XMP con i percorsi del record di metadati della risorsa.
* I percorsi possono essere associati alle risorse in Experience Manager, ovvero i file inseriti si trovano anche in Experience Manager con un percorso corrispondente.

## Nuove funzioni e miglioramenti {#whats-new-added}

To know the details, see [What&#39;s new in v2.0](introduction.md#whats-new-v2).

**Aggiornamenti nell&#39;app v2.0.2**

Le correzioni e gli aggiornamenti dei bug sono:

* Per migliorare le prestazioni di caricamento, aumentate l’accelerazione di caricamento [!UICONTROL Preferences]. Quando questa impostazione è attivata, l&#39;app utilizza più thread CPU locali e richiede più risorse.
* È stato risolto un problema relativo ai caricamenti di risorse quando i nomi di file o i percorsi contengono alcuni caratteri GB18030. <!-- CQ-4283494 -->
* L’opzione Ordina per rilevanza è disponibile dopo il passaggio a un altro tipo di ordinamento nei risultati della ricerca. <!-- CQ-4286874 -->
* L&#39;app desktop ora elenca le sottocartelle senza la necessità di aggiornare esplicitamente. <!-- CQ-4285711 -->
* (Windows) È stato risolto un raro problema di interfaccia app non utilizzabile su alcuni computer Windows. Gli utenti non possono fare clic sull&#39;interfaccia dell&#39;app in quanto risulta distorta con l&#39;area di clic degli elementi di interfaccia &#39;spostato&#39; lateralmente. <!-- CQ-4280785 -->

**Aggiornamenti nell&#39;app v2.0.1**

Le correzioni e gli aggiornamenti dei bug sono:

* Consenti di configurare la `%Temp%` directory in modo che corrisponda al `%APPDATA%` percorso. <!-- CQ-4282665 -->
* Consentire agli utenti di accedere a AEM Author tramite l&#39;autenticazione Okta SAML. <!-- CQ-4278134 -->

## Istruzioni di installazione {#installation-instructions-v2}

To know how to install and configure the app, see [Install Experience Manager desktop app](install-upgrade.md).

If you are upgrading from a previous Experience Manager desktop app, you must follow these best practices for transitioning that are listed at [upgrade from previous version](install-upgrade.md#upgrade-from-previous-version).

## Note importanti sul funzionamento dell’app {#how-app-works}

È importante essere a conoscenza delle informazioni seguenti relative all’applicazione e al relativo funzionamento.

* L’applicazione offre il controllo completo sulle operazioni che richiedono il trasferimento di tutti i file binari di risorse da e verso AEM (apertura, modifica, caricamento delle modifiche e caricamento delle risorse).
   * Se desideri modificare la risorsa sul desktop, devi selezionare in modo esplicito le opzioni Apri, Modifica o Scarica sul desktop singolarmente, in una cartella oppure tramite selezione multipla.
   * Per apportare modifiche locali alle risorse caricate in AEM, devi selezionare [!UICONTROL Upload Changes], singolarmente o tramite selezione multipla.
   * L’applicazione non è un client di sincronizzazione che sincronizza le risorse tra il desktop e AEM.
   * L’applicazione non offre una condivisione di rete che mappa l’archivio AEM sotto forma di struttura di cartelle virtuali.
* L’elenco delle risorse visualizzato dall’applicazione è basato sullo stato dell’archivio di AEM Assets. Tutti i file scaricati in locale e quindi rinominati nei file locali o nella cartella della cache non vengono visualizzati o gestiti dall’applicazione.
* Se l’app non visualizza i risultati previsti, fai clic sull’icona di aggiornamento nella barra superiore.
* La condivisione di rete locale, visualizzata quando utilizzi un’azione [!UICONTROL Reveal File], mostra solo i file (e le cartelle) disponibili in locale. Con [!UICONTROL Reveal File] e [!UICONTROL Reveal Folder] le risorse vengono prescaricate in modo da visualizzare le risorse corrette nella condivisione di rete locale.
* Quando un’app Adobe Creative Cloud legge i file di risorse collegati/inseriti in un file nativo dell’app Creative Cloud, viene utilizzata la condivisione di rete locale SMB (Mac) o WebDAV (Windows).

Il diagramma seguente illustra il flusso di risorse e file dal cloud al file system locale e viceversa, avviato in base alle azioni dell’utente.

![Flusso delle risorse dal server AEM alle app desktop native tramite l’app desktop](assets/da20_flow_diagram.png)

## Problemi noti {#known-issues-v2}

**Problemi relativi all’interfaccia utente:**

* A volte, l&#39;interfaccia dell&#39;app desktop potrebbe diventare vuota. Right-click and click [!UICONTROL Refresh] to re-load the application. Dopo tale aggiornamento, si inizia dalla directory principale dell&#39;archivio DAM. Gli aggiornamenti o gli stati delle risorse vengono conservati. <!-- CQ-4270267 -->
* Difficile navigare tra le cartelle o cercare i risultati senza il trackpad o il puntatore del mouse. The scroll-bar might not appear with mouse devices without mouse wheel. <!-- CQ-4269947 -->
* Di rado, la barra di avanzamento non viene visualizzata correttamente quando cambia la risorsa in fase di caricamento.
* Dopo che l’utente applica e rimuove il filtro per trovare tutte le risorse modificate in locale, l’app non ritorna ai risultati della ricerca originale o alla vista cartelle in cui si trovava inizialmente l’utente. L’app visualizza la cartella principale dell’archivio DAM.
* Talvolta, in caso di connessione a un URL per cui non è in esecuzione alcun server AEM, la schermata di connessione si blocca. Esci dall’applicazione e riavviala.

**Problemi relativi a operazioni di creazione, lettura, aggiornamento ed eliminazione:**

* L’applicazione prova a caricare i file anche se contengono caratteri non validi. Potrebbe verificarsi un errore di caricamento sul lato server. <!-- CQ-4273652 -->
* Quando si caricano le modifiche in una risorsa con commenti, i commenti vengono memorizzati insieme alla risorsa in AEM ma non sono visibili come commenti relativi alle versioni. Questo problema è stato risolto in AEM 6.4.5 e AEM 6.5.1. Adobe consiglia vivamente di installare i Service Pack più recenti. <!-- CQ-4268990 -->
* I trasferimenti di risorse non possono essere annullati dall’utente. Se hai attivato per errore un trasferimento di grandi dimensioni, esci dall’applicazione e riavviala. <!-- CQ-4278940 -->

**Problemi relativi alla piattaforma:**

* In alcuni casi, in Windows, lo stato di una risorsa può cambiare immediatamente in [!UICONTROL Edited Locally] dopo l’apertura, anche se non sono state apportate modifiche. Fai clic su [!UICONTROL Refresh] per aggiornare.

>[!MORELIKETHIS]
>
>* [AEM come documentazione del servizio cloud](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/landing/home.html)
>* [AEM come documentazione delle risorse del servizio cloud](https://docs.adobe.com/content/help/it-IT/experience-manager-cloud-service/assets/home.html)
>* [Come utilizzare l&#39;app desktop Experience Manager](using.md)
>* [Installare e aggiornare l’app desktop](install-upgrade.md)
>* [Best practice e suggerimenti per la risoluzione dei problemi](troubleshoot.md)

