---
title: Introduzione allo strumento di integrazione
description: Introduzione allo strumento di integrazione
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
feature: Microsoft CRM Integration
role: Data Architect
level: Intermediate
exl-id: e73e2069-e86d-4be2-bf73-22e6dc164340
source-git-commit: e7fdaa4b1d77afdae8004a88bbe41bbbe75a3f3c
workflow-type: tm+mt
source-wordcount: '1079'
ht-degree: 1%

---

# Introduzione all’applicazione di integrazione self-service {#gs-self-service-app}

L’applicazione di integrazione self-service di Adobe Campaign Standard con Microsoft Dynamics 365 consente di configurare i flussi di dati, controllare se sono in esecuzione o meno e in quale ambiente. È tuttavia necessario completare alcuni prerequisiti prima di iniziare a utilizzare l&#39;applicazione di integrazione self-service.

## Concetti e restrizioni {#concepts-and-restrictions}

Prima di iniziare a utilizzare lo strumento di integrazione, è necessario comprendere i concetti e i guardrail associati all’integrazione e intraprendere alcuni passaggi iniziali per ottenere l’accesso.

Per ulteriori informazioni, consulta le sezioni seguenti:

* [Guida introduttiva all’integrazione con Microsoft Dynamics 365](../../integrating/using/d365-acs-get-started.md)
* [Best practice e limitazioni dell’integrazione](../../integrating/using/d365-acs-notices-and-recommendations.md)
* [Scopri i passaggi chiave per implementare questa integrazione](../../integrating/using/d365-acs-get-started.md#request-and-implement-this-integration)
* [Utilizzare l’integrazione con Microsoft Dynamics 365](../../integrating/using/d365-acs-using-the-integration.md)

## Prerequisiti {#self-service-app-prerequisites}

Devi configurare Microsoft Dynamics 365 e Adobe Campaign Standard in modo che l’app di integrazione possa accedere ai tuoi dati. La configurazione in Dynamics 365, Adobe Campaign Standard e Adobe I/O richiederà un po’ di tempo; tuttavia, una volta configurati, potrai controllare l’integrazione tramite l’interfaccia utente dell’applicazione di integrazione self-service.

Per ulteriori informazioni, consulta le sezioni seguenti:

* [Configurare Microsoft Dynamics 365 per l’integrazione con Campaign](../../integrating/using/d365-acs-configure-d365.md)
* [Configura Adobe I/O](../../integrating/using/d365-acs-configure-adobe-io.md)
* [Mappatura delle risorse personalizzate di Campaign ed entità personalizzate di Microsoft Dynamics 365](../../integrating/using/d365-acs-notices-and-recommendations.md)

## Passaggi chiave per configurare l’app di integrazione self-service {#self-service-app-configuration-steps}

A questo punto puoi iniziare con lo strumento di integrazione. Segui i passaggi seguenti:

1. [Accedere all’app di integrazione](../../integrating/using/d365-acs-self-service-app-control-access.md)
1. [Configurare l’app di integrazione per il tuo utilizzo](../../integrating/using/d365-acs-self-service-app-settings.md)
1. [Implementare la sincronizzazione dei dati](../../integrating/using/d365-acs-self-service-app-data-sync.md)
1. [Configurare i flussi di lavoro di sincronizzazione](../../integrating/using/d365-acs-self-service-app-workflows.md)

## Collegamento all’app di integrazione {#self-service-app-link}

Apri un browser e individua il connettore associato alla tua regione:

* [Asia Pacifico](https://d365-acs-ap.ea.adobe.com/)
* [Europa, Medio Oriente o Africa (EMEA)](https://d365-acs-em.ea.adobe.com/)
* [Americhe](https://d365-acs-am.ea.adobe.com/)

## Conferma della richiesta di accesso a dati personali {#self-service-app-acknowledgement}

Quando visiti per la prima volta l’interfaccia utente self-service, riceverai la conferma della privacy. Prima di poter continuare, è necessario essere consapevoli del proprio ruolo nell’esecuzione delle richieste di accesso a dati personali in Campaign e in Microsoft Dynamics 365 separatamente.
Ulteriori informazioni sulle tue responsabilità in materia di privacy e su come gestire le richieste di accesso a dati personali in [questa sezione](../../integrating/using/d365-acs-notices-and-recommendations.md#acs-msdyn-manage-privacy).

## Impostazione delle credenziali in corso {#self-service-app-credentials}

Quando esplori l’interfaccia utente per la prima volta, dovresti vedere una pagina con un’intestazione simile alla seguente:

![](assets/do-not-localize/d365-to-acs-ui-header.png)

>[!NOTE]
>
> È normale ricevere avvisi che indicano che è &quot;impossibile connettersi&quot; a Adobe Campaign Standard o Microsoft Dynamics 365 se le impostazioni dell’app non sono ancora state configurate.

Verifica che le selezioni &quot;ORG&quot; e &quot;INSTANCE&quot; siano quelle che intendi configurare.  In caso contrario, fai clic sull’elenco a discesa e seleziona l’organizzazione e l’istanza corrette.

>[!IMPORTANT]
>
> Se stai configurando il connettore per la prima volta e/o hai poca esperienza con questo processo, **fortemente** invitare a selezionare l&#39;istanza &quot;stage&quot; o &quot;dev&quot;. Assicurati di verificare che la configurazione funzioni correttamente prima di tentare l’installazione in produzione.

Se disponi dell’organizzazione e dell’istanza corrette, fai clic sul menu &quot;hamburger&quot; per esporre un menu a discesa. Quindi fai clic su **[!UICONTROL Settings...]** nel menu a discesa per visitare la pagina in cui si immettono le credenziali per Microsoft Dynamics 365 e Campaign (vedere di seguito).

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-menu-pointers.png)

In **[!UICONTROL Settings]** , compilare le sezioni seguenti:

* Credenziali di Microsoft Dynamics 365
* Credenziali Adobe

Vai [qui](../../integrating/using/d365-acs-self-service-app-settings.md) per informazioni più dettagliate su dove trovare le informazioni per ogni input. Al termine, fai clic su **[!UICONTROL Save]** nella parte inferiore.

## Verifica la configurazione iniziale {#self-service-app-initial-config}

Supponendo di aver completato i prerequisiti e di aver aggiunto correttamente tutte le credenziali, passiamo ora alla sezione **[!UICONTROL Workflows]** pagina. Ulteriori informazioni sui flussi di lavoro dell’app di integrazione in [questa pagina](../../integrating/using/d365-acs-self-service-app-workflows.md).

In  **[!UICONTROL Workflows]** , fare clic sull&#39;icona della matita associata alla **[!UICONTROL Microsoft Dynamics 365 to Campaign]** per modificarne la configurazione.

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-ingress-edit-pointer.png)

In **[!UICONTROL Microsoft Dynamics 365 to Campaign]** , è possibile accedere all&#39;elenco dei mapping di tabella configurati.  Per impostazione predefinita, viene impostata una mappatura di contatto/profilo predefinita. Tutte le altre entità personalizzate dovranno essere configurate separatamente.

![](assets/do-not-localize/d365-to-acs-ui-page-ingress-top-pointers.png)

In **[!UICONTROL Edit Table Mapping]** , controlla la **[!UICONTROL Mappings]** per garantire che i campi di Microsoft Dynamics 365 vengano mappati sul campo corretto in Campaign. Se devi aggiungere altre mappature, fallo ora, così come eventuali sostituzioni o filtri. [Ulteriori informazioni](../../integrating/using/d365-acs-self-service-app-data-sync.md).

Se desideri aggiungere nuove mappature, fai riferimento a [questa sezione](../../integrating/using/d365-acs-self-service-app-data-sync.md#add-a-new-mapping) per ulteriori informazioni.

Una volta corretta la configurazione, fai clic su **[!UICONTROL Play]** accanto al pulsante **[!UICONTROL Microsoft Dynamics 365 to Campaign]** per avviare l’integrazione e il flusso di dati.

>[!IMPORTANT]
>
>Noi **fortemente** consigliamo di eseguirlo negli ambienti di staging o sviluppo prima di eseguirlo in produzione. Verifica che l’istanza stage/dev sia selezionata nell’intestazione.
>

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-ingress-play-pointer.png)

Una volta in esecuzione, dovresti essere in grado di eseguire il test aggiungendo o modificando le voci in Microsoft Dynamics 365 e osservando tali modifiche in Adobe Campaign in pochi minuti. Se in qualsiasi momento è necessario interrompere questo processo, è sufficiente premere lo stesso pulsante per interromperlo. [Ulteriori informazioni](../../integrating/using/d365-acs-self-service-app-workflows.md#workflow-status)


## Area di lavoro dell’app di integrazione {#self-service-app-workspace}

### Intestazione app {#app-header}

L’intestazione all’interno dell’app self-service ti consente di definire l’organizzazione e l’istanza attualmente visualizzate e/o configurate.

Seleziona la **ORG** e **ISTANZA** desideri visualizzare/modificare. Questi campi appaiono di sola lettura, tuttavia diventano modificabili quando si posiziona il cursore del mouse su di essi.

Quando fai clic sul pulsante con le tre linee orizzontali viene visualizzato un menu a discesa ![](assets//do-not-localize/d365-to-acs-icon-hamburger.png) sul lato destro dell’intestazione.

Le voci del menu a discesa sono:

* **Impostazioni**: selezionando questa opzione, viene visualizzata una schermata che consente di specificare le credenziali API per Microsoft Dynamics 365 e Adobe Campaign, nonché altre impostazioni generali per l’applicazione.

* **Documentazione**: questa opzione è un collegamento alla documentazione di Adobe Campaign specifica per questa integrazione

* **Assistenza clienti**: collegamento alla documentazione di Experience Cloud relativa all’apertura di un ticket dell’Assistenza clienti

* **Esci**: ti disconnetterà dall’applicazione e ti consentirà di accedere nuovamente come altro utente.

* **Informazioni su**: questa mostra una finestra di dialogo che contiene informazioni sull’applicazione, comprese le informazioni sul copyright.

### Breadcrumb {#app-breadcrumbs}

Le breadcrumb vengono visualizzate nella parte superiore di alcune schermate durante la navigazione nell’app.

**Esempio:**

Di seguito è riportato un esempio **[!UICONTROL Edit Table Mapping]** schermata che mostra le breadcrumb e il titolo della pagina. In questo caso, puoi fare clic sul pulsante **[!UICONTROL Workflows]** o **[!UICONTROL Microsoft Dynamics 365 to Campaign]** testo per passare a una delle schermate precedenti. **[!UICONTROL Edit Table Mapping]** in questo caso, non è possibile fare clic su nella breadcrumb perché si tratta della schermata corrente.

![](assets/do-not-localize/d365-to-acs-breadcrumbs-ingress.png)

### Pulsanti comuni {#app-buttons}

Le icone seguenti vengono utilizzate in più pagine nell’app self-service.

![](assets/do-not-localize/d365-to-acs-icon-add.png) - Aggiungere un nuovo elemento a un elenco.

![](assets/do-not-localize/d365-to-acs-icon-edit.png) - Modificare un elemento già esistente

![](assets/do-not-localize/d365-to-acs-icon-delete.png) - Eliminare un elemento da un elenco di elementi
