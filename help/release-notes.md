---
title: Note sulla versione dell’app desktop AEM
description: Dettagli sulla versione, miglioramenti, nuove funzioni, compatibilità e collegamenti per il download per l’app desktop AEM.
uuid: b783c3f8-aa1e-4c05-b687-5894909769f5
contentOwner: AG
products: SG_EXPERIENCEMANAGER/6.3/ASSETS
discoiquuid: 3052549b-fe75-44fb-a55e-5cc612868f54
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 850d2c21a796599ed40164e7d6f892967563c16b

---


# Note sulla versione dell’app desktop AEM {#release-notes-v2}

| Prodotti | App desktop Adobe Experience Manager (AEM) |
|---------------|--------------------------------------------------------------------|
| Versione app (revisione) | 2.0 (2.0.0.4) |
| Versioni AEM supportate | AEM 6.5, AEM 6.4, AEM 6.3 (con pacchetto di compatibilità) |
| Tipo | Versione principale |
| Data di rilascio | 30 agosto 2019 (Mac), 9 settembre 2019 (Win) |
| Scaricare gli URL | [MacOS a 64 bit](https://download.macromedia.com/aem-assets-companion-app/aem-desktop-osx-2.0.0.4.dmg); [Windows a 64 bit](https://download.macromedia.com/aem-assets-companion-app/aem-desktop-win64-2.0.0.4.exe); [Windows a 32 bit](https://download.macromedia.com/aem-assets-companion-app/aem-desktop-win32-2.0.0.4.exe) |

## Requisiti di sistema e prerequisiti {#system-requirements-and-prerequisites-v2}

L'app desktop AEM è compatibile con i seguenti sistemi operativi:

* Mac OS X 10.10 o versione successiva, con correzioni di bug più recenti.
* Windows 7 e Windows 10 con i Service Pack più recenti e le correzioni dei bug.

L'app funziona con le seguenti versioni di AEM, sia che sia distribuita in sede sia che si trovi in Adobe Managed Services (AMS):

* [AEM 6.5.0](https://helpx.adobe.com/experience-manager/6-5/release-notes.html) o versione successiva
* [AEM 6.4.4](https://helpx.adobe.com/experience-manager/6-4/release-notes/sp-release-notes.html) o versione successiva
* AEM 6.4.0 - 6.4.3 con pacchetto di [compatibilità](https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/cq640/featurepack/adobe-asset-link-support)
* AEM 6.3.3.1 e versioni successive con pacchetto di [compatibilità](https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/cq640/featurepack/adobe-asset-link-support)
* Per AEM 6.3, non sono pianificati [](https://helpx.adobe.com/experience-manager/maintenance-releases-roadmap.html)service pack. Adobe consiglia di effettuare l’aggiornamento a una versione successiva di AEM.

La versione dell’app che pianificate di installare sul computer locale richiede una versione specifica del server Adobe Experience Manager/componenti aggiuntivi lato server (Service Pack, hotfix o pacchetti di funzioni). Contatta il tuo amministratore AEM per assistenza.

### Supporto per risorse e tipi di file diversi {#support-for-file-types}

L’applicazione supporta le risorse memorizzate in AEM che rappresentano un file binario per le operazioni di base. L'apertura di file nell'applicazione desktop nativa si basa sull'associazione del sistema operativo dei tipi di file specifici come PNG o JPG a applicazioni specifiche come Mac Preview o Adobe Photoshop.

Alcuni tipi di file supportano il posizionamento di risorse collegate nel binario. L’applicazione prescarica le risorse collegate se la risorsa è presente nell’archivio AEM quando tali file binari vengono aperti tramite l’app desktop. I tipi di file attualmente supportati sono:

* File Adobe InDesign (formato INDD)
* File di Adobe Illustrator (formato AI)
* File Adobe Photoshop (formato PS)

Questa funzione è supportata dalle versioni di Adobe Creative Cloud 2018 e Creative Cloud 2019 dell'applicazione precedente. L’app utilizza un approccio euristico e di migliore corrispondenza per mappare i percorsi desktop locali delle risorse collegate agli URL sul server AEM. Si basa su alcuni presupposti:

* I percorsi per i file inseriti nell'applicazione nativa utilizzano un percorso desktop globale (inserito dalla condivisione di rete locale visualizzata con l'opzione "Mostra")
* I percorsi vengono memorizzati nel record XMP del file dall'app nativa
* AEM ha estratto il record XMP con i percorsi del record di metadati della risorsa
* I percorsi possono essere associati alle risorse in AEM (ovvero, i file inseriti si trovano anche in AEM in un percorso corrispondente)

## Nuove funzioni e miglioramenti {#whats-new-added}

Per conoscere i dettagli, vedi [Novità nell'app](introduction.md#whats-new-v2).

## Istruzioni di installazione {#installation-instructions-v2}

Per informazioni su come installare e configurare l'app, consultate [Installare l'app](install-upgrade.md)desktop AEM.

Se state effettuando l'aggiornamento da una precedente app desktop AEM, dovete seguire le best practice per la transizione elencate al momento dell' [aggiornamento dalla versione](install-upgrade.md#upgrade-from-previous-version)precedente.

## Note importanti sul funzionamento dell'app {#how-app-works}

È importante comprendere quanto segue sull'applicazione e sul suo funzionamento.

* L’applicazione fornisce il controllo completo sulle operazioni che richiedono il trasferimento completo dei file binari di risorse da e verso AEM (apertura, modifica, caricamento, modifiche e caricamento di risorse).
   * Se desiderate lavorare con la risorsa sul desktop, dovete esplicitamente aprire, modificare o scaricare sul desktop, singolarmente, in una cartella o tramite selezione multipla.
   * Per apportare modifiche locali alle risorse caricate in AEM, è necessario selezionare [!UICONTROL Upload Changes], singolarmente o tramite selezione multipla.
   * L’applicazione non è un client di sincronizzazione che sincronizza le risorse tra desktop e AEM.
   * L'applicazione non fornisce una condivisione di rete che mappa l'archivio AEM come struttura di cartelle virtuali.
* L’elenco delle risorse visualizzato dall’applicazione è basato sullo stato dell’archivio di Risorse AEM. Tutti i file scaricati localmente e quindi rinominati nei file locali o nella cartella della cache non vengono visualizzati o gestiti dall’applicazione.
* Se l'app non visualizza i risultati previsti, fai clic sull'icona di aggiornamento nella barra superiore.
* La condivisione di rete locale, visualizzata quando si utilizza [!UICONTROL Reveal File] un'azione, mostra solo i file (e le cartelle) disponibili localmente. [!UICONTROL Reveal File] e [!UICONTROL Reveal Folder] pre-scarica le risorse per visualizzare le risorse corrette nella condivisione di rete locale.
* Condivisione di rete locale SMB (Mac) /WebDAV (Win) quando un'app Adobe Creative Cloud legge i file di risorse collegati/inseriti in un file nativo dell'app Creative Cloud.

Il diagramma seguente illustra il flusso di risorse e file dal cloud al file system locale e viceversa, come avviato dalle azioni dell'utente.

![Flusso di risorse dal server AEM alle app desktop native tramite l’app desktop](assets/do-not-localize/da20_flow_diagram.png)

## Known issues {#known-issues-v2}

**Problemi relativi all'interfaccia utente:**
* A volte, l'interfaccia dell'app desktop potrebbe essere vuota. Fare clic con il pulsante destro del mouse e scegliere [!UICONTROL Refresh] per caricare di nuovo l'applicazione. Tale aggiornamento ripristina lo stato dell'app e si parte dalla schermata di benvenuto nella directory principale dell'archivio DAM. <!-- CQ-4270267 -->
* Difficile navigare tra le cartelle o cercare risultati senza il trackpad o la rotellina del mouse. La barra di scorrimento potrebbe non essere visualizzata con i dispositivi del mouse senza la rotellina del mouse. <!-- CQ-4269947 -->
* Con frequenza rara, la barra di avanzamento non viene visualizzata correttamente quando la risorsa di caricamento viene modificata.
* Dopo aver applicato e rimosso il filtro per trovare tutte le risorse modificate localmente, l'app non porta gli utenti ai risultati di ricerca o alla visualizzazione delle cartelle con cui hanno iniziato gli utenti. L'app visualizza la cartella principale dell'archivio DAM.
* A volte, quando vi connettete a un URL che non ha un server AEM in esecuzione, la schermata di connessione non risponde. Uscire dall’applicazione e riavviarla.

**Problemi di CRUD (creazione, lettura, aggiornamento ed eliminazione):**
* L'applicazione tenta di caricare i file anche con caratteri non validi. Potrebbe verificarsi un errore di caricamento sul lato server. <!-- CQ-4273652 -->
* Quando carichi le modifiche a una risorsa con commenti, i commenti vengono memorizzati insieme alla risorsa in AEM ma non sono visibili come commenti relativi alle versioni (risolti in AEM 6.4.5, 6.5.1). <!-- CQ-4268990 -->
* I trasferimenti di risorse non possono essere annullati dall'utente. Se avete attivato un trasferimento di grandi dimensioni non desiderato, uscite dall'applicazione e riavviatela. <!-- CQ-4278940 -->

**Problemi relativi alla piattaforma:**
* In alcuni casi, in Windows, lo stato di una risorsa può cambiare immediatamente in [!UICONTROL Edited Locally] dopo l'apertura, anche se non è stata modificata. Fate clic [!UICONTROL Refresh] per aggiornare.

>[!MORELIKETHIS]
>
>* [Documentazione di AEM 6.5](https://helpx.adobe.com/support/experience-manager/6-5.html)
>* [Documentazione di AEM Assets 6.5](https://docs.adobe.com/content/help/en/experience-manager-64/assets/home.html)
>* [Usa app desktop AEM](using.md)
>* [Installare e aggiornare l'app desktop](install-upgrade.md)
>* [Procedure ottimali e suggerimenti per la risoluzione dei problemi](troubleshoot.md)

