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
source-git-commit: ad5337c8e1697d0a37d3020d25802dc1d732f320

---


# Note sulla versione dell’app desktop AEM {#release-notes-v2}

| Prodotti | App desktop Adobe Experience Manager (AEM) |
|---------------|--------------------------------------------------------------------|
| Versione dell’app (revisione) | 2.0 (2.0.0.4) |
| Versioni di AEM supportate | AEM 6.5, AEM 6.4, AEM 6.3 (con pacchetto di compatibilità) |
| Tipo | Versione principale |
| Data di rilascio | 30 agosto 2019 (Mac), 9 settembre 2019 (Windows) |
| URL di download | [MacOS a 64 bit](https://download.macromedia.com/aem-assets-companion-app/aem-desktop-osx-2.0.0.4.dmg); [Windows a 64 bit](https://download.macromedia.com/aem-assets-companion-app/aem-desktop-win64-2.0.0.4.exe); [Windows a 32 bit](https://download.macromedia.com/aem-assets-companion-app/aem-desktop-win32-2.0.0.4.exe) |

## Requisiti di sistema e prerequisiti {#system-requirements-and-prerequisites-v2}

L’app desktop AEM è compatibile con i seguenti sistemi operativi:

* Mac OS X 10.10 o versione successiva, con correzioni di bug più recenti.
* Windows 7 e Windows 10 con Service Pack e correzioni di bug più recenti.

L’app funziona con le seguenti versioni di AEM, in locale o in Adobe Managed Services (AMS):

* [AEM 6.5.0](https://helpx.adobe.com/experience-manager/6-5/release-notes.html) o versione successiva
* [AEM 6.4.4](https://helpx.adobe.com/experience-manager/6-4/release-notes/sp-release-notes.html) o versione successiva
* AEM 6.4.0 - 6.4.3 con [pacchetto di compatibilità](https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/cq640/featurepack/adobe-asset-link-support)
* AEM 6.3.3.1 e versioni successive con [pacchetto di compatibilità](https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/cq640/featurepack/adobe-asset-link-support)
* Per AEM 6.3 [non sono pianificati Service Pack](https://helpx.adobe.com/experience-manager/maintenance-releases-roadmap.html). Adobe consiglia di passare a una versione successiva di AEM.

La versione dell’app che intendi installare nel computer locale richiede una versione specifica del server Adobe Experience Manager o componenti aggiuntivi lato server (Service Pack, hotfix o feature pack). Per assistenza, rivolgiti all’amministratore AEM.

### Supporto per risorse e tipi di file diversi {#support-for-file-types}

L’applicazione supporta le risorse memorizzate in AEM che rappresentano il file binario per le operazioni di base. L’apertura di file nell’applicazione desktop nativa si basa sull’associazione del sistema operativo dei tipi di file specifici, come PNG o JPG, ad applicazioni specifiche, come Mac Preview o Adobe Photoshop.

Alcuni tipi di file supportano il posizionamento di risorse collegate nel file binario. L’applicazione prescarica le risorse collegate se la risorsa è presente nell’archivio AEM quando tali file binari vengono aperti tramite l’app desktop. I tipi di file attualmente supportati sono:

* File Adobe InDesign (formato INDD)
* File Adobe Illustrator (formato AI)
* File Adobe Photoshop (formato PS)

Questa funzione è supportata con le versioni Adobe Creative Cloud 2018 e Creative Cloud 2019 di queste applicazioni. L’app utilizza un approccio euristico, basato sulla corrispondenza migliore, per mappare i percorsi desktop locali delle risorse collegate agli URL nel server AEM. Si basa su alcuni presupposti descritti di seguito:

* I percorsi dei file inseriti nell’applicazione nativa utilizzano un percorso desktop globale (inserito dalla condivisione di rete locale visualizzata con l’opzione “Mostra”).
* I percorsi sono memorizzati dall’app nativa nel record XMP del file.
* AEM estrae il record XMP con i percorsi nel record dei metadati della risorsa.
* I percorsi possono essere associati a risorse in AEM (ovvero, i file inseriti sono presenti anche in AEM in un percorso corrispondente)

## Nuove funzioni e miglioramenti {#whats-new-added}

Per informazioni, consulta [Novità dell’app](introduction.md#whats-new-v2).

## Istruzioni di installazione {#installation-instructions-v2}

Per informazioni su come installare e configurare l’app, consulta [Installare l’app desktop AEM](install-upgrade.md).

Se aggiorni un’app desktop AEM precedente, segui le best practice per la transizione elencate nella sezione relativa all’[aggiornamento dalla versione precedente](install-upgrade.md#upgrade-from-previous-version).

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
* A volte, l'interfaccia dell'app desktop potrebbe diventare vuota. Right-click and click [!UICONTROL Refresh] to re-load the application. Dopo tale aggiornamento, si inizia dalla directory principale dell'archivio DAM. Gli aggiornamenti o gli stati delle risorse vengono conservati. <!-- CQ-4270267 -->
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
>* [Documentazione di AEM 6.5](https://helpx.adobe.com/support/experience-manager/6-5.html)
>* [Documentazione di AEM Assets 6.5](https://docs.adobe.com/content/help/en/experience-manager-64/assets/home.html)
>* [Usare l’app desktop AEM](using.md)
>* [Installare e aggiornare l’app desktop](install-upgrade.md)
>* [Best practice e suggerimenti per la risoluzione dei problemi](troubleshoot.md)

