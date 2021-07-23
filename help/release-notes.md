---
title: '[!DNL Adobe Experience Manager] note sulla versione dell’app desktop'
description: Dettagli sulla versione, miglioramenti, nuove funzioni, compatibilità e collegamenti per il download dell’app desktop [!DNL Adobe Experience Manager] app desktop.
mini-toc-levels: 1
feature: App desktop, informazioni sulla versione
exl-id: e058e7a2-fcc8-4ad1-899e-20695db6bc72
source-git-commit: ea7227110aac38115829c93e7339dcdfbd9394a6
workflow-type: tm+mt
source-wordcount: '1675'
ht-degree: 22%

---

# [!DNL Adobe Experience Manager] note sulla versione dell’app desktop {#release-notes-v2}

Di seguito sono riportate le informazioni sulla versione più recente dell’app desktop versione 2.1 (2.1.3.2). La data di rilascio è il 19 luglio 2021.

Le **versioni supportate [!DNL Experience Manager]** sono:

* [!DNL Experience Manager] as a [!DNL Cloud Service]. Consulta le [note sulla versione](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/home.html?lang=it).
* [!DNL Experience Manager] 6.5.0 o versioni successive, su Adobe Managed Services (AMS) o On-Premise. Consulta le [note sulla versione del service pack](https://experienceleague.adobe.com/docs/experience-manager-65/release-notes/service-pack/sp-release-notes.html?lang=it).
* [!DNL Experience Manager] 6.4.4 o versioni successive, su Adobe Managed Services (AMS) o On-Premise. Consulta le [note sulla versione del service pack](https://experienceleague.adobe.com/docs/experience-manager-64/release-notes/sp-release-notes.html?lang=it).
* [!DNL Experience Manager] 6.4.0 - 6.4.3 con il pacchetto di  [compatibilità ](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/cq640/featurepack/adobe-asset-link-support) installato, su Adobe Managed Services (AMS) o On-Premise.
* [!DNL Experience Manager] 6.3 (con pacchetto di compatibilità)
* [!DNL Experience Manager] 6.3.3.1 o versioni successive con il pacchetto di  [compatibilità ](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/cq640/featurepack/adobe-asset-link-support) installato. L’app desktop non è supportata per [!DNL Experience Manager] 6.3.3.0 o versioni precedenti.

[!DNL Adobe Experience Manager] l’app desktop è disponibile per i seguenti sistemi  **operativi**:

* macOS X 10.14 o successivo, con le ultime correzioni di bug. [I computer Mac con ](https://support.apple.com/en-us/HT211814) siliconio Apple non sono ancora supportati.
* Windows 10 con Service Pack e correzioni di bug più recenti.

Gli **URL di download** per il sistema operativo supportato sono:

| Sistema operativo | [!DNL Experience Manager] as a [!DNL Cloud Service] | [!DNL Experience Manager] 6.x |
|---|---|---|
| macOS (v2.1.3.2) | [Collegamento di download](https://experience.adobe.com/#/downloads/content/software-distribution/en/aemcloud.html?package=/content/software-distribution/en/details.html/content/dam/aemcloud/public/aem-desktop-app/aem-desktop-osx-2.1.3.2.dmg) | [Collegamento di download](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/adobe/aem-desktop-app/aem-desktop-osx-2.1.3.2.dmg) |
| Windows a 64 bit (v2.1.3.2) | [Collegamento di download](https://experience.adobe.com/#/downloads/content/software-distribution/en/aemcloud.html?package=/content/software-distribution/en/details.html/content/dam/aemcloud/public/aem-desktop-app/aem-desktop-win64-2.1.3.2.exe) | [Collegamento di download](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/adobe/aem-desktop-app/aem-desktop-win64-2.1.3.2.exe) |
| Windows a 32 bit (v2.1.3.1) | [Collegamento di download](https://experience.adobe.com/#/downloads/content/software-distribution/en/aemcloud.html?package=/content/software-distribution/en/details.html/content/dam/aemcloud/public/aem-desktop-app/aem-desktop-win32-2.1.3.1.exe) | [Collegamento di download](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/adobe/aem-desktop-app/aem-desktop-win32-2.1.3.1.exe) |

>[!NOTE]
>
>Windows 7 non è più supportato. Vedere [l&#39;articolo su EOL di Windows 7](https://support.microsoft.com/en-us/help/4057281/windows-7-support-ended-on-january-14-2020).

<!-- The version of the app you plan to install on your local machine requires a specific [!DNL Adobe Experience Manager] server version/additional server-side components (service packs, hot fixes, or feature packs). Contact your [!DNL Experience Manager] administrator for help.
-->

## Supporto per risorse e tipi di file diversi {#support-for-file-types}

L&#39;applicazione supporta le risorse memorizzate in [!DNL Experience Manager] che rappresentano il file binario per le operazioni di base. L’apertura di file nell’applicazione desktop nativa si basa sull’associazione del sistema operativo dei tipi di file specifici, come PNG o JPG, ad applicazioni specifiche, come Mac Preview o Adobe Photoshop.

Alcuni tipi di file supportano il posizionamento di risorse collegate nel file binario. L’applicazione prescarica le risorse collegate se la risorsa è presente nell’archivio [!DNL Experience Manager] quando tali file binari vengono aperti tramite l’app desktop. I tipi di file attualmente supportati sono:

* [!DNL Adobe InDesign] file (formato INDD)
* [!DNL Adobe Illustrator] file (formato AI)
* [!DNL Adobe Photoshop] file (formato PS)

La funzione è supportata con le versioni [!DNL Adobe Creative Cloud] 2018 e [!DNL Adobe Creative Cloud] 2019 dell’applicazione precedente. L’app utilizza un approccio euristico e di migliore corrispondenza per mappare i percorsi desktop locali delle risorse collegate agli URL sul server [!DNL Experience Manager] . Si basa su alcuni presupposti descritti di seguito:

* I percorsi dei file inseriti nell&#39;applicazione nativa utilizzano un percorso desktop globale (inserito dalla condivisione di rete locale mostrata con l&#39;opzione [!UICONTROL Reveal]).

* I percorsi sono memorizzati nel record XMP del file dall’app nativa.

* [!DNL Experience Manager] ha estratto il record di XMP con i percorsi del record di metadati della risorsa.

* I percorsi possono essere associati alle risorse in [!DNL Experience Manager], ovvero i file inseriti si trovano anche in [!DNL Experience Manager] sotto un percorso corrispondente.

## Nuove funzioni, miglioramenti e correzioni di bug {#what-is-new}

Per conoscere i dettagli, consulta [Novità della versione v2.0](introduction.md#whats-new-v2).

**Aggiornamenti nell’app v2.1.3.2**

La nuova versione dell’applicazione offre una correzione di bug.

**Aggiornamenti nell’app v2.1.3.1**

Il bug corretto nella versione corrente è:

* Le velocità di caricamento e download delle risorse sono migliorate, anche con risorse di grandi dimensioni. Questo rilascio ha risolto un problema che a volte impediva il caricamento di risorse con [!DNL desktop app] durante il caricamento di file di grandi dimensioni.

**Aggiornamento nell’app v2.1.2.0**

* Una nuova opzione su [!UICONTROL Clear Cookies] viene aggiunta al menu principale dell&#39;applicazione. Consente di risolvere potenziali problemi di accesso, ad esempio quando si cambia la connessione da un server a un altro. Consulta [cancellare i cookie prima di collegare](/help/troubleshoot.md#cannot-login-cookies-issue).

* Viene aggiunta un’opzione che (se selezionata) consente all’app di caricare cartelle e file in modo che i nomi dei nodi creati in [!DNL Adobe Experience Manager] siano uguali ai nomi dei file e delle cartelle locali.

   Questo comportamento è simile a quello predefinito nella versione 1 dell’app desktop. Nella versione corrente, invece, se l’opzione non è abilitata, gli spazi bianchi e i caratteri `% ; # , + ? ^ { } "` nei nomi delle cartelle vengono sostituiti da un trattino nei percorsi delle cartelle. Inoltre, i caratteri maiuscoli vengono convertiti in lettere minuscole nei percorsi delle cartelle. Tuttavia, nei nomi dei file, i caratteri `# % { } ? &` sono sostituiti dal trattino; ma vengono mantenuti spazi bianchi e casing. Per ulteriori informazioni, consulta [Preferenze app](/help/install-upgrade.md#set-preferences) e [Carica e aggiungi nuove risorse](/help/using.md#upload-and-add-new-assets-to-aem).

**Aggiornamento nell’app v2.1.1.0**

* Un’impostazione avanzata consente all’app di emulare il comportamento dell’app v1.10 durante il caricamento delle cartelle. Nella versione 1.10, i nomi dei nodi creati nel repository rispettano gli spazi e la custodia dei nomi delle cartelle forniti dall&#39;utente. Il comportamento predefinito della v2.1 continua a rimanere invariato, ovvero sostituire più spazi nei nomi delle cartelle con un trattino nel nome del nodo del repository e convertire in nomi di nodo minuscoli. Consulta [le preferenze dell&#39;app](/help/install-upgrade.md#set-preferences).

**Aggiornamento nell’app v2.1.0.0**

* Per caricare le risorse, gli utenti possono ora trascinare i file o le cartelle sull&#39;interfaccia dell&#39;applicazione, direttamente da Esplora risorse o dal Finder di Mac. Questo funziona in aggiunta all’opzione di caricamento disponibile nell’applicazione. Consulta [caricare risorse](/help/using.md#upload-and-add-new-assets-to-aem) <!-- CQ-4309527 -->

**Aggiornamento nell’app v2.0.3**

Il bug corretto in questa versione è:

* È stato risolto il problema di accesso per gli utenti dell’app su Windows che tentavano di accedere all’archivio DAM in [!DNL Adobe Experience Manager] 6.5.5.0.

**Aggiornamenti nell’app v2.0.2**

Le correzioni e gli aggiornamenti dei bug sono:

* L’impostazione di accelerazione del caricamento è ora disponibile per migliorare le prestazioni di caricamento. Quando questa impostazione è attivata, l’app viene caricata più rapidamente utilizzando più thread locali della CPU ed è più laboriosa a livello di risorse.

* La risorsa viene caricata quando i nomi di file o i percorsi contenenti determinati caratteri GB18030 sono fissi. <!-- CQ-4283494 -->

* L’opzione Ordina per rilevanza è disponibile dopo il passaggio a un altro tipo di ordinamento nei risultati della ricerca. <!-- CQ-4286874 -->

* L’app desktop ora elenca le sottocartelle senza la necessità di eseguire un aggiornamento esplicito. <!-- CQ-4285711 -->

* (Windows) È stato risolto un raro problema di interfaccia di app non utilizzabile su alcuni computer Windows. Gli utenti non possono fare clic sull’interfaccia dell’app in quanto sembra distorta con l’area di clic degli elementi dell’interfaccia &quot;spostati&quot; lateralmente. <!-- CQ-4280785 -->

**Aggiornamenti nell’app v2.0.1**

Le correzioni e gli aggiornamenti dei bug sono:

* Consenti opzione per configurare la directory `%Temp%` in modo che corrisponda al percorso `%APPDATA%`. <!-- CQ-4282665 -->

* Consenti agli utenti di accedere a [!DNL Experience Manager] Autore tramite autenticazione Okta SAML. <!-- CQ-4278134 -->

## Istruzioni di installazione {#installation-instructions-v2}

Per informazioni su come installare e configurare l’app, consulta [Installare [!DNL Experience Manager] l’app desktop](install-upgrade.md).

Se esegui l’aggiornamento da un’app desktop precedente [!DNL Experience Manager], segui queste best practice per la transizione elencate in [Aggiornamento dalla versione precedente](install-upgrade.md#upgrade-from-previous-version).

## Note importanti sul funzionamento dell’app {#how-app-works}

È importante essere a conoscenza delle informazioni seguenti relative all’applicazione e al relativo funzionamento.

* L’applicazione fornisce il controllo completo sulle operazioni che richiedono il trasferimento completo dei binari delle risorse da e a [!DNL Experience Manager] (apertura, modifica, caricamento delle modifiche e caricamento delle risorse).

   * Se desideri lavorare con la risorsa sul desktop, devi selezionare esplicitamente Apri, Modifica o Scarica sul desktop, singolarmente, in una cartella o tramite selezione multipla.

   * Per apportare modifiche locali alle risorse caricate in [!DNL Experience Manager], devi selezionare [!UICONTROL Upload Changes] singolarmente o tramite selezione multipla.

   * L’applicazione non è un client di sincronizzazione che sincronizza le risorse tra il desktop e [!DNL Experience Manager].

   * L&#39;applicazione non fornisce una condivisione di rete che mappa l&#39;archivio [!DNL Experience Manager] come struttura di cartelle virtuali.

* L’elenco delle risorse visualizzato dall’applicazione è basato sullo stato dell’archivio di Assets. Tutti i file scaricati in locale e quindi rinominati nei file locali o nella cartella della cache non vengono visualizzati o gestiti dall’applicazione.

* Se l’app non visualizza i risultati previsti, fai clic sull’icona di aggiornamento nella barra superiore.

* La condivisione di rete locale, visualizzata quando utilizzi un’azione [!UICONTROL Reveal File], mostra solo i file (e le cartelle) disponibili in locale. Con [!UICONTROL Reveal File] e [!UICONTROL Reveal Folder] le risorse vengono prescaricate in modo da visualizzare le risorse corrette nella condivisione di rete locale.

* Quando un’app Adobe Creative Cloud legge i file di risorse collegati/inseriti in un file nativo dell’app Creative Cloud, viene utilizzata la condivisione di rete locale SMB (Mac) o WebDAV (Windows).

Il diagramma seguente illustra il flusso di risorse e file dal cloud al file system locale e il modo opposto, come avviato dalle azioni dell’utente.

![[!DNL Experience Manager]Flusso delle risorse dal server alle app desktop native tramite l’app desktop](assets/da20_flow_diagram.png)

## Problemi noti {#known-issues-v2}

**Problemi relativi all’interfaccia utente:**

* A volte, l’interfaccia dell’app desktop potrebbe diventare vuota. Fai clic con il pulsante destro del mouse e scegli [!UICONTROL Refresh] per ricaricare l’applicazione. Dopo tale aggiornamento, si inizia dalla directory principale dell’archivio DAM. Gli aggiornamenti o gli stati delle risorse vengono mantenuti. <!-- CQ-4270267 -->

* Difficile navigare tra le cartelle e i risultati della ricerca senza il trapano o il puntatore del mouse. La barra di scorrimento potrebbe non essere visualizzata con i dispositivi del mouse senza rotellina del mouse. <!-- CQ-4269947 -->

* Di rado, la barra di avanzamento non viene visualizzata correttamente quando cambia la risorsa in fase di caricamento.

* Dopo che l’utente applica e rimuove il filtro per trovare tutte le risorse modificate in locale, l’app non ritorna ai risultati della ricerca originale o alla vista cartelle in cui si trovava inizialmente l’utente. L’app visualizza la cartella principale dell’archivio DAM.

* A volte, quando ci si connette a un URL che non ha [!DNL Experience Manager] server in esecuzione, la schermata di connessione non risponde. Esci dall’applicazione e riavviala.

**Problemi relativi a operazioni di creazione, lettura, aggiornamento ed eliminazione:**

* Durante il caricamento di modifiche apportate a una risorsa con commenti, questi vengono memorizzati insieme alla risorsa in [!DNL Experience Manager] ma non sono visibili come commenti nel controllo delle versioni. Questo problema è risolto in [!DNL Experience Manager] 6.4.5 e [!DNL Experience Manager] 6.5.1. L&#39;Adobe consiglia di installare gli ultimi Service Pack. <!-- CQ-4268990 -->

* I trasferimenti di risorse non possono essere annullati dall’utente. Se hai attivato per errore un trasferimento di grandi dimensioni, esci dall’applicazione e riavviala. <!-- CQ-4278940 -->

**Problemi relativi alla piattaforma:**

* In alcuni casi, in Windows, lo stato di una risorsa può cambiare immediatamente in [!UICONTROL Edited Locally] dopo l’apertura, anche se non sono state apportate modifiche. Fai clic su [!UICONTROL Refresh] per aggiornare.

>[!MORELIKETHIS]
>
>* [[!DNL Experience Manager] as a [!DNL Cloud Service] documentazione](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/landing/home.html)
>* [[!DNL Experience Manager] as a [!DNL Cloud Service] [!DNL Assets] documentazione](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/home.html)
>* [Come utilizzare [!DNL Experience Manager] l&#39;app desktop](using.md)
* [Installare e aggiornare l’app desktop](install-upgrade.md)
* [Best practice e suggerimenti per la risoluzione dei problemi](troubleshoot.md)

