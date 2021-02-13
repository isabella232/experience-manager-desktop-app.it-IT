---
title: '[!DNL Adobe Experience Manager] note sulla versione dell''app desktop'
description: Dettagli sulla versione, miglioramenti, nuove funzioni, compatibilità e collegamenti per il download per l'app desktop [!DNL Adobe Experience Manager] 1.
mini-toc-levels: 1
translation-type: tm+mt
source-git-commit: b5292d9386432bd7c6ba5d7117dbc9fd9f014941
workflow-type: tm+mt
source-wordcount: '1418'
ht-degree: 32%

---


# [!DNL Adobe Experience Manager] note sulla versione dell&#39;app desktop  {#release-notes-v2}

| Prodotti | [!DNL Adobe Experience Manager] app desktop |
|--- |--- |
| Versione dell’app (revisione) | 2.1 (2.1.0.0) |
| Versioni [!DNL Adobe Experience Manager] supportate | [!DNL Experience Manager] come  [!DNL Cloud Service];  [!DNL Experience Manager] 6.5;  [!DNL Experience Manager] 6.4;  [!DNL Experience Manager] 6.3 (con pacchetto di compatibilità) |
| Tipo | Rilascio secondario |
| Data di rilascio | 17 dicembre 2020 (Mac e Win) |
| Scaricare gli URL per AEM 6.x | [macOS a 64 bit](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/adobe/aem-desktop-app/aem-desktop-osx-2.1.0.0.dmg);  [Windows a 64 bit](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/adobe/aem-desktop-app/aem-desktop-win64-2.1.0.0.exe);  [Windows a 32 bit](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/adobe/aem-desktop-app/aem-desktop-win32-2.1.0.0.exe) |
| Scaricare gli URL per AEM come [!DNL Cloud Service] | [macOS a 64 bit](https://experience.adobe.com/#/downloads/content/software-distribution/en/aemcloud.html?package=/content/software-distribution/en/details.html/content/dam/aemcloud/public/aem-desktop-app/aem-desktop-osx-2.1.0.0.dmg);  [Windows a 64 bit](https://experience.adobe.com/#/downloads/content/software-distribution/en/aemcloud.html?package=/content/software-distribution/en/details.html/content/dam/aemcloud/public/aem-desktop-app/aem-desktop-win64-2.1.0.0.exe);  [Windows a 32 bit](https://experience.adobe.com/#/downloads/content/software-distribution/en/aemcloud.html?package=/content/software-distribution/en/details.html/content/dam/aemcloud/public/aem-desktop-app/aem-desktop-win32-2.1.0.0.exe) |

## Requisiti di sistema e prerequisiti {#system-requirements-and-prerequisites-v2}

[!DNL Adobe Experience Manager]L’app desktop è compatibile con i seguenti sistemi operativi:

* Mac OS X 10.14 o versione successiva, con le correzioni di bug più recenti.

* Windows 10 con i Service Pack più recenti e le correzioni di bug.

>[!NOTE]
>
>Windows 7 non è più supportato dal fornitore (https://support.microsoft.com/en-us/help/4057281/windows-7-support-ended-on-january-14-2020).

L&#39;app funziona con le seguenti versioni [!DNL Experience Manager], sia distribuite come [!DNL Cloud Service], su Adobe Managed Services (AMS) o in sede:

* [[!DNL Experience Manager] come [!DNL Cloud Service]](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/home.html).

* [[!DNL Experience Manager] 6.5.0 ](https://experienceleague.adobe.com/docs/experience-manager-65/release-notes/service-pack/sp-release-notes.html) o successivo.

* [[!DNL Experience Manager] 6.4.4 ](https://experienceleague.adobe.com/docs/experience-manager-64/release-notes/sp-release-notes.html) o successivo.

* [!DNL Experience Manager] 6.4.0 - 6.4.3 con pacchetto [ di ](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/cq640/featurepack/adobe-asset-link-support)compatibilità.

>[!NOTE]
>
>Il supporto per le app desktop per [!DNL Experience Manager] 6.3 non è più supportato.  Adobe consiglia di effettuare l&#39;aggiornamento a una versione più recente e supportata [!DNL Adobe Experience Manager].
>[!DNL Experience Manager] 6.3.3.1 o versione successiva funziona con l&#39;app desktop dopo l&#39;installazione del pacchetto di compatibilità [](https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/cq640/featurepack/adobe-asset-link-support). Nessun pacchetto di questo tipo è disponibile per [!DNL Experience Manager] 6.3 in quanto non sono pianificati [Service Pack](https://helpx.adobe.com/it/experience-manager/maintenance-releases-roadmap.html).

La versione dell&#39;app che pianificate di installare sul computer locale richiede una versione [!DNL Adobe Experience Manager] server specifica/componenti aggiuntivi lato server (Service Pack, hotfix o feature pack). Per assistenza, contattare l&#39;amministratore di [!DNL Experience Manager].

### Supporto per risorse e tipi di file diversi {#support-for-file-types}

L&#39;applicazione supporta le risorse memorizzate in [!DNL Experience Manager] che rappresentano file binario per le operazioni di base. L’apertura di file nell’applicazione desktop nativa si basa sull’associazione del sistema operativo dei tipi di file specifici, come PNG o JPG, ad applicazioni specifiche, come Mac Preview o Adobe Photoshop.

Alcuni tipi di file supportano il posizionamento di risorse collegate nel file binario. L&#39;applicazione prescarica le risorse collegate se la risorsa è presente nell&#39;archivio [!DNL Experience Manager] quando tali file binari vengono aperti tramite l&#39;app desktop. I tipi di file attualmente supportati sono:

* [!DNL Adobe InDesign] file (formato INDD)
* [!DNL Adobe Illustrator] file (formato AI)
* [!DNL Adobe Photoshop] file (formato PS)

La funzione è supportata dalle versioni [!DNL Adobe Creative Cloud] 2018 e [!DNL Adobe Creative Cloud] 2019 dell&#39;applicazione precedente. L&#39;app utilizza un approccio euristico e di migliore corrispondenza per mappare i percorsi desktop locali delle risorse collegate agli URL sul server [!DNL Experience Manager]. Si basa su alcuni presupposti descritti di seguito:

* I percorsi dei file inseriti nell&#39;applicazione nativa utilizzano un percorso desktop globale (inserito dalla condivisione di rete locale mostrata con l&#39;opzione [!UICONTROL Reveal]).

* I percorsi vengono memorizzati nel record XMP del file dall&#39;app nativa.

* [!DNL Experience Manager] ha estratto il record XMP con i percorsi del record di metadati della risorsa.

* I percorsi possono essere associati alle risorse in [!DNL Experience Manager], ovvero i file inseriti si trovano anche in [!DNL Experience Manager] sotto un percorso corrispondente.

## Nuove funzioni e miglioramenti {#whats-new-added}

Per conoscere i dettagli, vedere [Novità della v2.0](introduction.md#whats-new-v2).

**Aggiornamenti nell&#39;app v2.1.0.0**

* Per caricare le risorse, gli utenti possono ora trascinare i file o le cartelle nell’interfaccia dell’applicazione, direttamente da Esplora risorse o dal Finder di Mac. Questo funziona in aggiunta all&#39;opzione di caricamento precedentemente disponibile nell&#39;applicazione.

**Aggiornamenti nell&#39;app v2.0.3**

Il bug corretto nella versione corrente è:

* È stato risolto il problema di accesso cui devono far fronte gli utenti Windows che cercano di accedere all&#39;archivio DAM nell&#39;istanza [!DNL Adobe Experience Manager] 6.5.5.0 tramite l&#39;app.

**Aggiornamenti nell&#39;app v2.0.2**

Le correzioni e gli aggiornamenti dei bug sono:

* Per migliorare le prestazioni di caricamento, aumentate l&#39;accelerazione di caricamento in [!UICONTROL Preferences]. Quando questa impostazione è attivata, l&#39;app utilizza più thread CPU locali e richiede più risorse.

* È stato risolto un problema relativo ai caricamenti di risorse quando i nomi di file o i percorsi contengono alcuni caratteri GB18030. <!-- CQ-4283494 -->

* L’opzione Ordina per rilevanza è disponibile dopo il passaggio a un altro tipo di ordinamento nei risultati della ricerca. <!-- CQ-4286874 -->

* L&#39;app desktop ora elenca le sottocartelle senza la necessità di aggiornare esplicitamente. <!-- CQ-4285711 -->

* (Windows) È stato risolto un raro problema di interfaccia app non utilizzabile su alcuni computer Windows. Gli utenti non possono fare clic sull&#39;interfaccia dell&#39;app in quanto risulta distorta con l&#39;area di clic degli elementi di interfaccia &#39;spostato&#39; lateralmente. <!-- CQ-4280785 -->

**Aggiornamenti nell&#39;app v2.0.1**

Le correzioni e gli aggiornamenti dei bug sono:

* Consenti la configurazione della directory `%Temp%` in modo che corrisponda al percorso `%APPDATA%`. <!-- CQ-4282665 -->

* Consentire agli utenti di accedere all&#39;autore [!DNL Experience Manager] tramite l&#39;autenticazione Okta SAML. <!-- CQ-4278134 -->

## Istruzioni di installazione {#installation-instructions-v2}

Per informazioni su come installare e configurare l&#39;app, vedi [Installa [!DNL Experience Manager] app desktop](install-upgrade.md).

Se state effettuando l&#39;aggiornamento da un&#39;app [!DNL Experience Manager] desktop precedente, dovete seguire le procedure ottimali per la transizione elencate in [aggiornamento dalla versione precedente](install-upgrade.md#upgrade-from-previous-version).

## Note importanti sul funzionamento dell’app {#how-app-works}

È importante essere a conoscenza delle informazioni seguenti relative all’applicazione e al relativo funzionamento.

* L’applicazione fornisce il controllo completo sulle operazioni che richiedono il trasferimento completo dei file binari di risorse da e verso [!DNL Experience Manager] (apertura, modifica, caricamento, modifiche e caricamento di risorse).

   * Se desideri modificare la risorsa sul desktop, devi selezionare in modo esplicito le opzioni Apri, Modifica o Scarica sul desktop singolarmente, in una cartella oppure tramite selezione multipla.

   * Per apportare modifiche locali alle risorse caricate in [!DNL Experience Manager], è necessario selezionare [!UICONTROL Upload Changes], singolarmente o tramite selezione multipla.

   * L’applicazione non è un client di sincronizzazione che sincronizza le risorse tra il desktop e [!DNL Experience Manager].

   * L&#39;applicazione non fornisce una condivisione di rete che mappa l&#39;archivio [!DNL Experience Manager] come una struttura di cartelle virtuali.

* L’elenco delle risorse visualizzato dall’applicazione è basato sullo stato dell’archivio di Assets. Tutti i file scaricati in locale e quindi rinominati nei file locali o nella cartella della cache non vengono visualizzati o gestiti dall’applicazione.

* Se l’app non visualizza i risultati previsti, fai clic sull’icona di aggiornamento nella barra superiore.

* La condivisione di rete locale, visualizzata quando utilizzi un’azione [!UICONTROL Reveal File], mostra solo i file (e le cartelle) disponibili in locale. Con [!UICONTROL Reveal File] e [!UICONTROL Reveal Folder] le risorse vengono prescaricate in modo da visualizzare le risorse corrette nella condivisione di rete locale.

* Quando un’app Adobe Creative Cloud legge i file di risorse collegati/inseriti in un file nativo dell’app Creative Cloud, viene utilizzata la condivisione di rete locale SMB (Mac) o WebDAV (Windows).

Il diagramma seguente illustra il flusso di risorse e file dal cloud al file system locale e viceversa, avviato in base alle azioni dell’utente.

![[!DNL Experience Manager]Flusso delle risorse dal server alle app desktop native tramite l’app desktop](assets/da20_flow_diagram.png)

## Problemi noti {#known-issues-v2}

**Problemi relativi all’interfaccia utente:**

* A volte, l&#39;interfaccia dell&#39;app desktop potrebbe diventare vuota. Fare clic con il pulsante destro del mouse e scegliere [!UICONTROL Refresh] per ricaricare l&#39;applicazione. Dopo tale aggiornamento, si inizia dalla directory principale dell&#39;archivio DAM. Gli aggiornamenti o gli stati delle risorse vengono conservati. <!-- CQ-4270267 -->

* Difficile navigare tra le cartelle o cercare i risultati senza il trackpad o il puntatore del mouse. La barra di scorrimento potrebbe non essere visualizzata con i dispositivi del mouse senza la rotellina del mouse. <!-- CQ-4269947 -->

* Di rado, la barra di avanzamento non viene visualizzata correttamente quando cambia la risorsa in fase di caricamento.

* Dopo che l’utente applica e rimuove il filtro per trovare tutte le risorse modificate in locale, l’app non ritorna ai risultati della ricerca originale o alla vista cartelle in cui si trovava inizialmente l’utente. L’app visualizza la cartella principale dell’archivio DAM.

* A volte, quando ci si connette a un URL che non ha [!DNL Experience Manager] server in esecuzione, la schermata di connessione non risponde. Esci dall’applicazione e riavviala.

**Problemi relativi a operazioni di creazione, lettura, aggiornamento ed eliminazione:**

* L’applicazione prova a caricare i file anche se contengono caratteri non validi. Potrebbe verificarsi un errore di caricamento sul lato server. <!-- CQ-4273652 -->

* Quando caricate le modifiche in una risorsa con commenti, i commenti vengono memorizzati con la risorsa in [!DNL Experience Manager] ma non sono visibili come commenti di controllo delle versioni. Questo problema è stato risolto in [!DNL Experience Manager] 6.4.5 e [!DNL Experience Manager] 6.5.1.  Adobe consiglia di installare i Service Pack più recenti. <!-- CQ-4268990 -->

* I trasferimenti di risorse non possono essere annullati dall’utente. Se hai attivato per errore un trasferimento di grandi dimensioni, esci dall’applicazione e riavviala. <!-- CQ-4278940 -->

**Problemi relativi alla piattaforma:**

* In alcuni casi, in Windows, lo stato di una risorsa può cambiare immediatamente in [!UICONTROL Edited Locally] dopo l’apertura, anche se non sono state apportate modifiche. Fai clic su [!UICONTROL Refresh] per aggiornare.

>[!MORELIKETHIS]
>
>* [[!DNL Experience Manager] as a [!DNL Cloud Service] documentazione](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/landing/home.html)
>* [[!DNL Experience Manager] as a [!DNL Cloud Service] [!DNL Assets] documentazione](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/home.html)
>* [Come utilizzare l&#39;app  [!DNL Experience Manager] desktop](using.md)
>* [Installare e aggiornare l’app desktop](install-upgrade.md)
>* [Best practice e suggerimenti per la risoluzione dei problemi](troubleshoot.md)

