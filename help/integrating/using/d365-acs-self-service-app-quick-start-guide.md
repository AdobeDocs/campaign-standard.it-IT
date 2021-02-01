---
title: 'Introduzione allo strumento di integrazione '
description: Introduzione allo strumento di integrazione
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
translation-type: tm+mt
source-git-commit: efa30d7ed4a0caf929da6f485681078318849cda
workflow-type: tm+mt
source-wordcount: '1071'
ht-degree: 2%

---


# Guida introduttiva all&#39;app di integrazione self-service {#gs-self-service-app}

L&#39;integrazione  Adobe Campaign Standard con l&#39;applicazione di integrazione self-service di Microsoft Dynamics 365 consente di configurare i flussi di dati, controllare se sono in esecuzione o meno e in quale ambiente. Prima di utilizzare l’applicazione di integrazione self-service, tuttavia, è necessario completare alcuni prerequisiti.

## Concetti e limitazioni {#concepts-and-restrictions}

Prima di iniziare con lo strumento di integrazione, è necessario comprendere i concetti e le garanzie associati all&#39;integrazione ed effettuare alcuni passi iniziali per ottenere l&#39;accesso.

Ulteriori informazioni in queste sezioni:

* [Guida introduttiva all’integrazione con Microsoft Dynamics 365](../../integrating/using/d365-acs-get-started.md)
* [Best practice e limitazioni dell&#39;integrazione](../../integrating/using/d365-acs-notices-and-recommendations.md)
* [Scopri i passaggi chiave per implementare questa integrazione](../../integrating/using/d365-acs-get-started.md#request-and-implement-this-integration)
* [Utilizzare l’integrazione con Microsoft Dynamics 365](../../integrating/using/d365-acs-using-the-integration.md)

## Prerequisiti {#self-service-app-prerequisites}

È necessario configurare Microsoft Dynamics 365 e  Adobe Campaign Standard in modo che l&#39;app di integrazione possa accedere ai dati. Questa operazione richiede del tempo per la configurazione in Dynamics 365,  Adobe Campaign Standard e  Adobe I/O; tuttavia, una volta configurate, sarà possibile controllare l&#39;integrazione tramite l&#39;interfaccia utente dell&#39;applicazione di integrazione self-service.

Ulteriori informazioni in queste sezioni:

* [Configurazione di Microsoft Dynamics 365 per l’integrazione con Campaign](../../integrating/using/d365-acs-configure-d365.md)
* [Configurazione di I/O Adobe](../../integrating/using/d365-acs-configure-adobe-io.md)
* [Mappa risorse personalizzate per Campaign ed entità personalizzate Microsoft Dynamics 365](../../integrating/using/d365-acs-notices-and-recommendations.md)

## Passaggi chiave per configurare l&#39;app di integrazione self-service {#self-service-app-configuration-steps}

Potete quindi iniziare con lo strumento di integrazione. Seguite i passaggi indicati di seguito:

1. [Accesso all&#39;app di integrazione](../../integrating/using/d365-acs-self-service-app-control-access.md)
1. [Configurare l&#39;app di integrazione per l&#39;utilizzo](../../integrating/using/d365-acs-self-service-app-settings.md)
1. [Implementazione della sincronizzazione dei dati](../../integrating/using/d365-acs-self-service-app-data-sync.md)
1. [Configurare i flussi di lavoro di sincronizzazione](../../integrating/using/d365-acs-self-service-app-workflows.md)

## Collegamento all&#39;app di integrazione {#self-service-app-link}

Aprite un browser e individuate il connettore associato alla vostra area geografica:

* [Asia Pacifico](http://d365-acs-ap.ea.adobe.com/)
* [Europa, Medio Oriente o Africa (EMEA)](http://d365-acs-em.ea.adobe.com/)
* [Americhe](http://d365-acs-na.ea.adobe.com/)

## Conferma richiesta privacy {#self-service-app-acknowledgement}

Quando si accede per la prima volta all’interfaccia utente self-service, viene visualizzato un messaggio di riconoscimento della privacy. Prima di continuare, devi riconoscere di aver compreso il tuo ruolo nell&#39;eseguire le richieste di privacy separatamente in Campaign e Microsoft Dynamics 365.
Ulteriori informazioni sulle tue responsabilità in materia di privacy e su come gestire le richieste di privacy in [questa sezione](../../integrating/using/d365-acs-notices-and-recommendations.md#acs-msdyn-manage-privacy).

## Impostazione delle credenziali {#self-service-app-credentials}

Quando si passa all’interfaccia utente per la prima volta, viene visualizzata una pagina con un’intestazione simile alla seguente:

![](assets/do-not-localize/d365-to-acs-ui-header.png)

>[!NOTE]
>
> È normale ricevere avvisi in cui viene indicato che non è possibile connettersi a  Adobe Campaign Standard o Microsoft Dynamics 365 se le impostazioni dell&#39;app non sono ancora state configurate.

Verificare che le selezioni &quot;ORG&quot; e &quot;INSTANCE&quot; siano quelle che si intende configurare.  In caso contrario, fate clic sull&#39;elenco a discesa e selezionate l&#39;organizzazione e l&#39;istanza corrette.

>[!IMPORTANT]
>
> Se si sta configurando il connettore per la prima volta e/o si è nuovi a questo processo, **fortemente** si consiglia di selezionare l&#39;istanza &quot;stage&quot; o &quot;dev&quot;. Prima di tentare la configurazione in produzione, è necessario verificare che la configurazione funzioni correttamente.

Se hai l&#39;organizzazione e l&#39;istanza corrette, clicca sul menu &quot;hamburger&quot; per esporre un menu a discesa. Fare clic su **[!UICONTROL Settings...]** nel menu a discesa per visitare la pagina in cui sono state immesse le credenziali per Microsoft Dynamics 365 e Campaign (vedere di seguito).

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-menu-pointers.png)

Nella pagina **[!UICONTROL Settings]**, compila le seguenti sezioni:

* Credenziali di Microsoft Dynamics 365
* Credenziali Adobe 

Fare clic [qui](../../integrating/using/d365-acs-self-service-app-settings.md) per informazioni più dettagliate su dove trovare le informazioni per ogni input. Al termine, fare clic sul pulsante **[!UICONTROL Save]** in basso.

## Controllare la configurazione iniziale {#self-service-app-initial-config}

Presupponendo che siano stati completati i prerequisiti di cui sopra e che tutte le credenziali siano state aggiunte correttamente, passiamo ora alla pagina **[!UICONTROL Workflows]**. Ulteriori informazioni sui flussi di lavoro delle app di integrazione in [questa pagina](../../integrating/using/d365-acs-self-service-app-workflows.md).

Nella pagina **[!UICONTROL Workflows]**, fai clic sull&#39;icona matita associata al flusso di lavoro **[!UICONTROL Microsoft Dynamics 365 to Campaign]** per modificarne la configurazione.

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-ingress-edit-pointer.png)

Nella pagina **[!UICONTROL Microsoft Dynamics 365 to Campaign]** è possibile accedere all&#39;elenco delle mappature delle tabelle configurate.  Per impostazione predefinita viene impostata una mappatura contatto/profilo out-of-the-box. Tutte le altre entità personalizzate dovranno essere configurate separatamente.

![](assets/do-not-localize/d365-to-acs-ui-page-ingress-top-pointers.png)

Nella pagina **[!UICONTROL Edit Table Mapping]**, controlla la sezione **[!UICONTROL Mappings]** per verificare che i campi di Microsoft Dynamics 365 siano mappati sul campo corretto in Campaign. Se è necessario aggiungere altre mappature, eseguire questa operazione ora, nonché eventuali sostituzioni o filtri. [Ulteriori informazioni](../../integrating/using/d365-acs-self-service-app-data-sync.md).

Per aggiungere nuove mappature, fare riferimento a [questa sezione](../../integrating/using/d365-acs-self-service-app-data-sync.md#add-a-new-mapping) per ulteriori informazioni.

Una volta che la configurazione è corretta, fare clic sul pulsante **[!UICONTROL Play]** accanto al flusso di lavoro **[!UICONTROL Microsoft Dynamics 365 to Campaign]** per avviare l&#39;integrazione e il flusso di dati.

>[!IMPORTANT]
>
>**fortemente** si consiglia di eseguire prima questo in ambiente Stage o Dev prima di essere eseguito in produzione. Verificate che l’istanza stage/dev sia selezionata nell’intestazione.


![](assets/do-not-localize/d365-to-acs-ui-page-workflows-ingress-play-pointer.png)

Una volta eseguita, è necessario essere in grado di eseguire il test aggiungendo o modificando le voci in Microsoft Dynamics 365 e osservando tali modifiche in  Adobe Campaign entro pochi minuti. Se in qualsiasi momento è necessario interrompere il processo, premere semplicemente lo stesso pulsante per interromperlo. [Ulteriori informazioni](../../integrating/using/d365-acs-self-service-app-workflows.md#workflow-status)


## Area di lavoro dell&#39;app di integrazione {#self-service-app-workspace}

### Intestazione dell&#39;app {#app-header}

L’intestazione all’interno dell’app self-service consente di definire l’organizzazione e l’istanza che state visualizzando e/o configurando.

Selezionare l&#39; **ORG** e l&#39; **INSTANCE** da visualizzare/modificare. Questi campi sono di sola lettura, ma diventano modificabili quando si posiziona il puntatore del mouse su di essi.

Quando si fa clic sul pulsante con le tre righe orizzontali ![](assets//do-not-localize/d365-to-acs-icon-hamburger.png) a destra dell&#39;intestazione viene visualizzato un menu a discesa.

Le voci nel menu a discesa sono:

* **Impostazioni**: Selezionando questa opzione si passerà a una schermata che consente di specificare le credenziali API per Microsoft Dynamics 365 e  Adobe Campaign, nonché altre impostazioni generali per l&#39;applicazione.

* **Documentazione**: Questa opzione è un collegamento alla documentazione Adobe Campaign  specifica per questa integrazione

* **Assistenza** clienti: Collegamento alla documentazione  Experience Cloud relativa all&#39;apertura di un ticket di assistenza clienti

* **Disconnetti**: Questo ti disconnetterà dall&#39;applicazione e ti consentirà di accedere nuovamente come un altro utente.

* **Informazioni**: Viene visualizzata una finestra di dialogo contenente informazioni sull’applicazione, incluse le informazioni sul copyright.

### Breadcrumb {#app-breadcrumbs}

Le breadcrumb vengono visualizzate nella parte superiore di alcune schermate mentre vi spostate nell&#39;app.

**Esempio:**

Di seguito è riportato un esempio dalla schermata **[!UICONTROL Edit Table Mapping]** che mostra le breadcrumb e il titolo della pagina. In questo caso, è possibile fare clic sul testo **[!UICONTROL Workflows]** o **[!UICONTROL Microsoft Dynamics 365 to Campaign]** per passare a una delle schermate precedenti. **[!UICONTROL Edit Table Mapping]** in questo caso non è possibile fare clic sul percorso di navigazione perché si tratta della schermata corrente.

![](assets/do-not-localize/d365-to-acs-breadcrumbs-ingress.png)

### Pulsanti comuni {#app-buttons}

Le seguenti icone sono utilizzate in più pagine nell&#39;app self-service.

![](assets/do-not-localize/d365-to-acs-icon-add.png) - Aggiungere un nuovo elemento a un elenco.

![](assets/do-not-localize/d365-to-acs-icon-edit.png) - Modificare qualcosa che esiste già

![](assets/do-not-localize/d365-to-acs-icon-delete.png) - Eliminare un elemento da un elenco di elementi
