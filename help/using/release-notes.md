---
title: "[!DNL Adobe Experience Manager] Note sulla versione dell’app desktop"
description: Dettagli sulla versione, miglioramenti, nuove funzioni, compatibilità e collegamenti per il download di [!DNL Adobe Experience Manager] app desktop.
mini-toc-levels: 1
feature: Desktop App,Release Information
exl-id: e058e7a2-fcc8-4ad1-899e-20695db6bc72
source-git-commit: 0f366e07b9d220cf04286b24e4bb45ce0b385e5c
workflow-type: tm+mt
source-wordcount: '2624'
ht-degree: 14%

---

# [!DNL Adobe Experience Manager] Note sulla versione dell’app desktop {#release-notes-v2}

Di seguito sono riportate le informazioni sulla versione dell’app desktop più recente versione 2.3.0. La data di rilascio è il 14 luglio 2023.

La versione più recente dell’app desktop include le correzioni e i miglioramenti seguenti:

* È stato aggiunto il supporto per l’accesso IMS. L’integrazione IMS consente all’app desktop di eseguire automaticamente l’aggiornamento del token di accesso, consentendo all’utente di rimanere connesso per un massimo di 14 giorni.

* Supporto migliorato per proxy aziendali e filtro web.


Il **supportato [!DNL Experience Manager] versioni** sono:

* [!DNL Experience Manager] as a [!DNL Cloud Service]. Consulta [note sulla versione](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/home.html?lang=it).
* [!DNL Experience Manager] 6.5.0 o successiva, su Adobe Managed Services (AMS) o On-Premise. Consulta [note sulla versione del service pack](https://experienceleague.adobe.com/docs/experience-manager-65/release-notes/service-pack/sp-release-notes.html?lang=it).

[!DNL Adobe Experience Manager] L’app desktop è disponibile per: **sistemi operativi**:

* macOS X 10.14 o versione successiva, con le ultime correzioni di bug.
* Windows 10 con Service Pack e correzioni di bug più recenti.

Il **scarica URL** i sistemi operativi supportati sono:

| Sistema operativo | [!DNL Experience Manager] as a [!DNL Cloud Service] | [!DNL Experience Manager] 6.x |
|---|---|---|
| macOS (v2.3.0) | [Collegamento di download](https://experience.adobe.com/#/downloads/content/software-distribution/en/aemcloud.html?package=/content/software-distribution/en/details.html/content/dam/aemcloud/public/aem-desktop-app/aem-desktop-osx-x64-2.3.0.dmg) | [Collegamento di download](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/adobe/aem-desktop-app/aem-desktop-osx-x64-2.3.0.dmg) |
| Silicio macOS Apple (M1) (v2.3.0) | [Collegamento di download](https://experience.adobe.com/#/downloads/content/software-distribution/en/aemcloud.html?package=/content/software-distribution/en/details.html/content/dam/aemcloud/public/aem-desktop-app/aem-desktop-osx-arm64-2.3.0.dmg) | [Collegamento di download](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/adobe/aem-desktop-app/aem-desktop-osx-arm64-2.3.0.dmg) |
| Windows a 64 bit (v2.3.0) | [Collegamento di download](https://experience.adobe.com/#/downloads/content/software-distribution/en/aemcloud.html?package=/content/software-distribution/en/details.html/content/dam/aemcloud/public/aem-desktop-app/aem-desktop-win-x64-2.3.0.exe) | [Collegamento di download](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/adobe/aem-desktop-app/aem-desktop-win-x64-2.3.0.exe) |
| macOS (v2.2.2) | [Collegamento di download](https://experience.adobe.com/#/downloads/content/software-distribution/en/aemcloud.html?package=/content/software-distribution/en/details.html/content/dam/aemcloud/public/aem-desktop-app/aem-desktop-osx-x64-2.2.2.dmg) | [Collegamento di download](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/adobe/aem-desktop-app/aem-desktop-osx-x64-2.2.2.dmg) |
| Silicio macOS Apple (M1) (v2.2.2) | [Collegamento di download](https://experience.adobe.com/#/downloads/content/software-distribution/en/aemcloud.html?package=/content/software-distribution/en/details.html/content/dam/aemcloud/public/aem-desktop-app/aem-desktop-osx-arm64-2.2.2.dmg) | [Collegamento di download](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/adobe/aem-desktop-app/aem-desktop-osx-arm64-2.2.2.dmg) |
| Windows a 64 bit (v2.2.2) | [Collegamento di download](https://experience.adobe.com/#/downloads/content/software-distribution/en/aemcloud.html?package=/content/software-distribution/en/details.html/content/dam/aemcloud/public/aem-desktop-app/aem-desktop-win-x64-2.2.2.exe) | [Collegamento di download](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/adobe/aem-desktop-app/aem-desktop-win-x64-2.2.2.exe) |
| macOS (v2.2.1) | [Collegamento di download](https://experience.adobe.com/#/downloads/content/software-distribution/en/aemcloud.html?package=/content/software-distribution/en/details.html/content/dam/aemcloud/public/aem-desktop-app/aem-desktop-osx-x64-2.2.1.dmg) | [Collegamento di download](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/adobe/aem-desktop-app/aem-desktop-osx-x64-2.2.1.dmg) |
| Silicio macOS Apple (M1) (v2.2.1) | [Collegamento di download](https://experience.adobe.com/#/downloads/content/software-distribution/en/aemcloud.html?package=/content/software-distribution/en/details.html/content/dam/aemcloud/public/aem-desktop-app/aem-desktop-osx-arm64-2.2.1.dmg) | [Collegamento di download](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/adobe/aem-desktop-app/aem-desktop-osx-arm64-2.2.1.dmg) |
| Windows a 64 bit (v2.2.1) | [Collegamento di download](https://experience.adobe.com/#/downloads/content/software-distribution/en/aemcloud.html?package=/content/software-distribution/en/details.html/content/dam/aemcloud/public/aem-desktop-app/aem-desktop-win-x64-2.2.1.exe) | [Collegamento di download](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/adobe/aem-desktop-app/aem-desktop-win-x64-2.2.1.exe) |
| macOS (v2.2.0) | [Collegamento di download](https://experience.adobe.com/#/downloads/content/software-distribution/en/aemcloud.html?package=/content/software-distribution/en/details.html/content/dam/aemcloud/public/aem-desktop-app/aem-desktop-osx-x64-2.2.0.dmg) | [Collegamento di download](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/adobe/aem-desktop-app/aem-desktop-osx-x64-2.2.0.dmg) |
| Silicio macOS Apple (M1) (v2.2.0) | [Collegamento di download](https://experience.adobe.com/#/downloads/content/software-distribution/en/aemcloud.html?package=/content/software-distribution/en/details.html/content/dam/aemcloud/public/aem-desktop-app/aem-desktop-osx-arm64-2.2.0.dmg) | [Collegamento di download](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/adobe/aem-desktop-app/aem-desktop-osx-arm64-2.2.0.dmg) |
| Windows a 64 bit (v2.2.0) | [Collegamento di download](https://experience.adobe.com/#/downloads/content/software-distribution/en/aemcloud.html?package=/content/software-distribution/en/details.html/content/dam/aemcloud/public/aem-desktop-app/aem-desktop-win-x64-2.2.0.exe) | [Collegamento di download](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/adobe/aem-desktop-app/aem-desktop-win-x64-2.2.0.exe) |
| macOS (v2.1.5.0) | [Collegamento di download](https://experience.adobe.com/#/downloads/content/software-distribution/en/aemcloud.html?package=/content/software-distribution/en/details.html/content/dam/aemcloud/public/aem-desktop-app/aem-desktop-osx-2.1.5.0.dmg) | [Collegamento di download](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/adobe/aem-desktop-app/aem-desktop-osx-2.1.5.0.dmg) |
| Windows a 64 bit (v2.1.5.0) | [Collegamento di download](https://experience.adobe.com/#/downloads/content/software-distribution/en/aemcloud.html?package=/content/software-distribution/en/details.html/content/dam/aemcloud/public/aem-desktop-app/aem-desktop-win64-2.1.5.0.exe) | [Collegamento di download](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/adobe/aem-desktop-app/aem-desktop-win64-2.1.5.0.exe) |
| Windows a 32 bit (v2.1.5.0) | [Collegamento di download](https://experience.adobe.com/#/downloads/content/software-distribution/en/aemcloud.html?package=/content/software-distribution/en/details.html/content/dam/aemcloud/public/aem-desktop-app/aem-desktop-win32-2.1.5.0.exe) | [Collegamento di download](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/adobe/aem-desktop-app/aem-desktop-win32-2.1.5.0.exe) |
| macOS (v2.1.4.0) | [Collegamento di download](https://experience.adobe.com/#/downloads/content/software-distribution/en/aemcloud.html?package=/content/software-distribution/en/details.html/content/dam/aemcloud/public/aem-desktop-app/aem-desktop-osx-2.1.4.0.dmg) | [Collegamento di download](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/adobe/aem-desktop-app/aem-desktop-osx-2.1.4.0.dmg) |
| Windows a 64 bit (v2.1.4.0) | [Collegamento di download](https://experience.adobe.com/#/downloads/content/software-distribution/en/aemcloud.html?package=/content/software-distribution/en/details.html/content/dam/aemcloud/public/aem-desktop-app/aem-desktop-win64-2.1.4.0.exe) | [Collegamento di download](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/adobe/aem-desktop-app/aem-desktop-win64-2.1.4.0.exe) |
| Windows a 32 bit (v2.1.4.0) | [Collegamento di download](https://experience.adobe.com/#/downloads/content/software-distribution/en/aemcloud.html?package=/content/software-distribution/en/details.html/content/dam/aemcloud/public/aem-desktop-app/aem-desktop-win32-2.1.4.0.exe) | [Collegamento di download](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/adobe/aem-desktop-app/aem-desktop-win32-2.1.4.0.exe) |
| macOS (v2.1.3.4) | [Collegamento di download](https://experience.adobe.com/#/downloads/content/software-distribution/en/aemcloud.html?package=/content/software-distribution/en/details.html/content/dam/aemcloud/public/aem-desktop-app/aem-desktop-osx-2.1.3.4.dmg) | [Collegamento di download](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/adobe/aem-desktop-app/aem-desktop-osx-2.1.3.4.dmg) |
| Windows a 64 bit (v2.1.3.4) | [Collegamento di download](https://experience.adobe.com/#/downloads/content/software-distribution/en/aemcloud.html?package=/content/software-distribution/en/details.html/content/dam/aemcloud/public/aem-desktop-app/aem-desktop-win64-2.1.3.4.exe) | [Collegamento di download](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/adobe/aem-desktop-app/aem-desktop-win64-2.1.3.4.exe) |
| Windows a 32 bit (v2.1.3.1) | [Collegamento di download](https://experience.adobe.com/#/downloads/content/software-distribution/en/aemcloud.html?package=/content/software-distribution/en/details.html/content/dam/aemcloud/public/aem-desktop-app/aem-desktop-win32-2.1.3.1.exe) | [Collegamento di download](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/adobe/aem-desktop-app/aem-desktop-win32-2.1.3.1.exe) |

>[!NOTE]
>
>Windows 7 non è più supportato. Consulta [articolo sulla fine del ciclo di vita di Windows 7](https://support.microsoft.com/en-us/help/4057281/windows-7-support-ended-on-january-14-2020).

## Supporto per risorse e tipi di file diversi {#support-for-file-types}

L’applicazione supporta le risorse memorizzate in [!DNL Experience Manager] che rappresentano il file binario per le operazioni di base. L’apertura di file nell’applicazione desktop nativa si basa sull’associazione del sistema operativo dei tipi di file specifici, come PNG o JPG, ad applicazioni specifiche, come Mac Preview o Adobe Photoshop.

Alcuni tipi di file supportano il posizionamento di risorse collegate nel file binario. L’applicazione prescarica le risorse collegate se la risorsa è presente nel [!DNL Experience Manager] archivio quando tali file binari vengono aperti utilizzando l’app desktop. I tipi di file attualmente supportati sono:

* [!DNL Adobe InDesign] file (formato INDD)
* [!DNL Adobe Illustrator] file (formato AI)
* [!DNL Adobe Photoshop] file (formato PS)

La funzione è supportata con [!DNL Adobe Creative Cloud] 2018 e [!DNL Adobe Creative Cloud] Versioni 2019 dell’applicazione precedente. L’app utilizza un approccio euristico, basato sulla corrispondenza migliore, per mappare i percorsi desktop locali delle risorse collegate agli URL nel [!DNL Experience Manager] server. Si basa su alcuni presupposti descritti di seguito:

* I percorsi dei file inseriti nell’applicazione nativa utilizzano un percorso desktop globale (inserito dalla condivisione di rete locale visualizzata con [!UICONTROL Reveal] opzionale).

* I percorsi vengono memorizzati dall’app nativa nel record XMP del file.

* [!DNL Experience Manager] ha estratto il record XMP con i percorsi del record di metadati della risorsa.

* I percorsi possono corrispondere alle risorse in [!DNL Experience Manager], ovvero, anche i file inseriti sono in [!DNL Experience Manager] in un percorso corrispondente.

## Nuove funzioni, miglioramenti e correzioni di bug {#what-is-new}

Per informazioni, consulta [Novità della versione v2.0](introduction.md#whats-new-v2).

**Aggiornamenti nell’app v2.2.2**

* [Solo Windows] l’app desktop visualizza una schermata vuota dopo l’installazione delle versioni 2.2.0 e 2.2.1.

**Aggiornamenti nell’app v2.2.1**

* l’app desktop visualizza il messaggio di errore timeout sessione quando fai clic su **[!UICONTROL Sign In]**.

* Problemi durante l’accesso all’app desktop v2.2.0 su macOS.

* l’app desktop visualizza un messaggio di errore quando ordini le risorse facendo clic su **[!UICONTROL Edited Locally]**.

**Aggiornamenti nell’app v2.2.0**

* Supporto per Apple Silicon (M1).

* Possibilità di ricordare la stringa di connessione durante l&#39;accesso all&#39;app desktop.

**Aggiornamenti nell’app v2.1.5.0**

* L’app desktop non risponde quando carichi i file in una cartella contenente caratteri cinesi (ASSETS-9237).

* L’app desktop sostituisce i punti con trattini nei nomi dei file (ASSETS-10955).

**Aggiornamenti nell’app v2.1.4.0**

La nuova versione dell’applicazione offre correzioni di bug.

**Aggiornamenti nell’app v2.1.3.4**

La nuova versione dell&#39;applicazione offre una correzione di bug.

**Aggiornamenti nell’app v2.1.3.3**

La nuova versione dell&#39;applicazione offre una correzione di bug.

**Aggiornamenti nell’app v2.1.3.2**

Questa versione dell&#39;applicazione offre una correzione di bug.

**Aggiornamenti nell’app v2.1.3.1**

Il bug corretto in questa versione è:

* Le velocità di caricamento e download delle risorse sono migliorate, anche con risorse di grandi dimensioni. Questa versione risolve un problema relativo al caricamento di risorse con [!DNL desktop app] talvolta non riuscite quando venivano caricati file di dimensioni molto grandi.

**Aggiornamento nell’app v2.1.2.0**

* Una nuova opzione per [!UICONTROL Clear Cookies] viene aggiunto al menu principale dell’applicazione. È utile in caso di potenziali problemi di accesso, ad esempio quando si cambia la connessione da un server a un altro. Consulta [cancella i cookie prima della connessione](/help/using/troubleshoot.md#cannot-login-cookies-issue).

* Viene aggiunta un’opzione che (se selezionata) consente all’app di caricare cartelle e file in modo che i nomi dei nodi vengano creati in [!DNL Adobe Experience Manager] corrispondono ai nomi di file e cartelle locali.

  Questo comportamento è simile a quello predefinito nella versione 1 dell’app desktop. Nella versione corrente, invece, se l’opzione non è abilitata, vengono visualizzati gli spazi vuoti e i caratteri `% ; # , + ? ^ { } "` nei nomi delle cartelle, vengono sostituiti da trattini nei percorsi delle cartelle. Inoltre, nei percorsi delle cartelle i caratteri maiuscoli vengono convertiti in minuscolo. Tuttavia, nei nomi dei file, i caratteri `# % { } ? &` vengono sostituiti da un trattino, ma vengono mantenuti gli spazi vuoti e l&#39;involucro. Per ulteriori informazioni, consulta [Preferenze app](/help/using/install-upgrade.md#set-preferences) e [Caricare e aggiungere nuove risorse](/help/using/using.md#upload-and-add-new-assets-to-aem).

**Aggiornamento nell’app v2.1.1.0**

* Un’impostazione avanzata consente all’app di emulare il comportamento dell’app v1.10 durante il caricamento delle cartelle. Nella versione 1.10, i nomi dei nodi creati nell’archivio rispettano gli spazi e le maiuscole/minuscole dei nomi delle cartelle forniti dall’utente. Il comportamento predefinito di v2.1 continua a rimanere invariato, ovvero sostituisce più spazi nei nomi delle cartelle con un trattino nel nome del nodo dell’archivio e converte in nomi di nodo minuscoli. Consulta [le preferenze dell’app](/help/using/install-upgrade.md#set-preferences).

**Aggiornamento in app v2.1.0.0**

* Per caricare le risorse, gli utenti possono ora trascinare i file o le cartelle sull’interfaccia dell’applicazione, direttamente da Esplora risorse o da Mac Finder. Questo funziona in aggiunta all’opzione di caricamento disponibile nell’applicazione. Consulta [caricare le risorse](/help/using/using.md#upload-and-add-new-assets-to-aem) <!-- CQ-4309527 -->

**Aggiornamento in app v2.0.3**

Il bug corretto in questa versione è:

* È stato risolto il problema di accesso per gli utenti dell’app su Windows che tentavano di accedere all’archivio DAM il [!DNL Adobe Experience Manager] 6.5.5.0

**Aggiornamenti nell’app v2.0.2**

Le correzioni e gli aggiornamenti di bug sono:

* È ora disponibile l’impostazione di accelerazione del caricamento per migliorarne le prestazioni. Quando questa impostazione è attivata, l’app viene caricata più rapidamente utilizzando più thread della CPU locali e richiede più risorse.

* La risorsa viene caricata quando i nomi di file o i percorsi contenenti determinati caratteri GB18030 sono fissi. <!-- CQ-4283494 -->

* L’opzione Ordina per rilevanza è disponibile dopo il passaggio a un altro tipo di ordinamento nei risultati della ricerca. <!-- CQ-4286874 -->

* L’app desktop ora elenca le sottocartelle senza dover essere aggiornate in modo esplicito. <!-- CQ-4285711 -->

* (Windows) È stato risolto un raro problema di interfaccia app inutilizzabile su alcuni computer Windows. Gli utenti non possono fare clic sull’interfaccia dell’app perché appare distorta con l’area di clic degli elementi dell’interfaccia &quot;spostati&quot; lateralmente. <!-- CQ-4280785 -->

**Aggiornamenti nell’app v2.0.1**

Le correzioni e gli aggiornamenti di bug sono:

* Consenti la configurazione dell’opzione `%Temp%` directory da associare `%APPDATA%` percorso. <!-- CQ-4282665 -->

* Consenti agli utenti di accedere [!DNL Experience Manager] Autore tramite autenticazione Okta SAML. <!-- CQ-4278134 -->

## Istruzioni di installazione {#installation-instructions-v2}

Per informazioni su come installare e configurare l’app, consulta [Installa [!DNL Experience Manager] app desktop](install-upgrade.md).

Se si esegue l&#39;aggiornamento da un [!DNL Experience Manager] dell&#39;app desktop, è necessario seguire queste best practice per la transizione elencate in [aggiornamento dalla versione precedente](install-upgrade.md#upgrade-from-previous-version).

## Note importanti sul funzionamento dell’app {#how-app-works}

È importante essere a conoscenza delle informazioni seguenti relative all’applicazione e al relativo funzionamento.

* L’applicazione offre il controllo completo sulle operazioni che richiedono il trasferimento completo dei dati binari delle risorse da e verso [!DNL Experience Manager] (apri, modifica, carica modifiche e carica risorse).

   * Se desideri utilizzare la risorsa sul desktop, devi selezionare in modo esplicito le opzioni Apri, Modifica o Scarica sul desktop singolarmente, in una cartella o tramite selezione multipla.

   * Per apportare modifiche locali alle risorse caricate in [!DNL Experience Manager], è necessario selezionare [!UICONTROL Upload Changes], singolarmente o tramite selezione multipla.

   * L’applicazione non è un client di sincronizzazione che sincronizza le risorse tra il desktop e [!DNL Experience Manager].

   * L&#39;applicazione non fornisce una condivisione di rete che mappa [!DNL Experience Manager] come struttura di cartelle virtuali.

* L’elenco delle risorse visualizzato dall’applicazione è basato sullo stato dell’archivio di Assets. Tutti i file scaricati in locale e quindi rinominati nei file locali o nella cartella della cache non vengono visualizzati o gestiti dall’applicazione.

* Se l’app non visualizza i risultati previsti, fai clic sull’icona di aggiornamento nella barra superiore.

* La condivisione di rete locale, visualizzata quando utilizzi un’azione [!UICONTROL Reveal File], mostra solo i file (e le cartelle) disponibili in locale. Con [!UICONTROL Reveal File] e [!UICONTROL Reveal Folder] le risorse vengono prescaricate in modo da visualizzare le risorse corrette nella condivisione di rete locale.

* Quando un’app Adobe Creative Cloud legge i file di risorse collegati/inseriti in un file nativo dell’app Creative Cloud, viene utilizzata la condivisione di rete locale SMB (Mac) o WebDAV (Windows).

Il diagramma seguente illustra il flusso di risorse e file dal cloud al file system locale e viceversa, in base alle azioni dell’utente.

![[!DNL Experience Manager]Flusso delle risorse dal server alle app desktop native tramite l’app desktop](assets/da20_flow_diagram.png)

## Problemi noti {#known-issues-v2}

**Problemi relativi all’interfaccia utente:**

* A volte, l’interfaccia dell’app desktop potrebbe diventare vuota. Fai clic con il pulsante destro del mouse e scegli [!UICONTROL Refresh] per ricaricare l&#39;applicazione. Dopo tale aggiornamento, inizi dalla directory principale dell’archivio DAM. Gli aggiornamenti o gli stati delle risorse vengono mantenuti. <!-- CQ-4270267 -->

* È difficile spostarsi tra le cartelle e/o i risultati della ricerca senza il track pad o il puntatore del mouse. La barra di scorrimento potrebbe non essere visualizzata quando si utilizzano mouse senza rotellina. <!-- CQ-4269947 -->

* Di rado, la barra di avanzamento non viene visualizzata correttamente quando cambia la risorsa in fase di caricamento.

* Dopo che l’utente applica e rimuove il filtro per trovare tutte le risorse modificate in locale, l’app non ritorna ai risultati della ricerca originale o alla vista cartelle in cui si trovava inizialmente l’utente. L’app visualizza la cartella principale dell’archivio DAM.

* A volte, quando ti connetti a un URL che non ha [!DNL Experience Manager] server in esecuzione, la schermata di connessione non risponde. Esci dall’applicazione e riavviala.

**Problemi relativi a operazioni di creazione, lettura, aggiornamento ed eliminazione:**

* Quando carichi le modifiche apportate a una risorsa con commenti, questi vengono memorizzati insieme alla risorsa in [!DNL Experience Manager] ma non sono visibili come commenti per il controllo delle versioni. Questo problema è stato risolto in [!DNL Experience Manager] 6.4.5 e [!DNL Experience Manager] 6.5.1. L’Adobe consiglia di installare i Service Pack più recenti. <!-- CQ-4268990 -->

* I trasferimenti di risorse non possono essere annullati dall’utente. Se hai attivato per errore un trasferimento di grandi dimensioni, esci dall’applicazione e riavviala. <!-- CQ-4278940 -->

**Problemi relativi alla piattaforma:**

* In alcuni casi, in Windows, lo stato di una risorsa può cambiare immediatamente in [!UICONTROL Edited Locally] dopo l’apertura, anche se non sono state apportate modifiche. Fai clic su [!UICONTROL Refresh] per aggiornare.

>[!MORELIKETHIS]
>
>* [[!DNL Experience Manager] as a [!DNL Cloud Service] documentazione](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/landing/home.html?lang=it)
>* [[!DNL Experience Manager] as a [!DNL Cloud Service] [!DNL Assets] documentazione](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/home.html?lang=it)
>* [Come usare [!DNL Experience Manager] app desktop](using.md)
>* [Installare e aggiornare l’app desktop](install-upgrade.md)
>* [Best practice e suggerimenti per la risoluzione dei problemi](troubleshoot.md)
