---
solution: Campaign Standard
product: campaign
title: Provisioning e configurazione dell’integrazione con Audience Manager o il servizio core People
description: 'Scoprite come configurare l''integrazione del servizio di base  Audience Manager / Persone per iniziare a condividere audience o segmenti con le diverse soluzioni Adobe Experience Cloud. '
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
translation-type: tm+mt
source-git-commit: ad7322905c69f9575e11efc9d8f68cf909dc425f
workflow-type: tm+mt
source-wordcount: '719'
ht-degree: 9%

---


# Provisioning e configurazione dell’integrazione con Audience Manager o il servizio core People{#provisioning-and-configuring-integration-with-audience-manager-or-people-core-service}

Il provisioning e la configurazione di  Audience Manager e Persone di base in  Adobe Campaign eseguono due passaggi: [Invio della richiesta a  Adobe](#submitting-request-to-adobe) e quindi [Configurazione dell&#39;integrazione in  Adobe Campaign](#configuring-the-integration-in-adobe-campaign).

## Invio di una richiesta ad Adobe {#submitting-request-to-adobe}

&#39;integrazione con il servizio di base Audience Manager (AAM) o Persone consente di importare ed esportare audience o segmenti  Adobe Campaign.

Questa integrazione deve prima essere configurata. Per richiedere il provisioning di questa integrazione, invia un messaggio e-mail a [Digital-Request@adobe.com](mailto:Digital-Request@adobe.com) con le seguenti informazioni:

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Tipo di richiesta:</strong><br /> </td> 
   <td> Configurare l'integrazione dei servizi di base AAM/Persone </td> 
  </tr> 
  <tr> 
   <td> <strong>Nome organizzazione:</strong><br /> </td> 
   <td> Nome organizzazione </td> 
  </tr> 
  <tr> 
   <td> <strong>ID organizzazione IMS</strong><br /> </td> 
   <td> L’ID organizzazione IMS. <br> Puoi trovare il tuo ID organizzazione IMS nel Experience Cloud , nel menu Amministrazione. Viene fornito anche quando si effettua la prima connessione all’Adobe Experience Cloud. </td> 
  </tr> 
  <tr> 
   <td> <strong>Ambiente:</strong><br /> </td> 
   <td> Esempio: Produzione </td> 
  </tr> 
  <tr> 
   <td> <strong>Servizio AAM o Persone</strong><br /> </td> 
   <td> Esempio: Adobe Audience Manager. Assicuratevi di indicare al team di provisioning se siete in possesso o meno  licenza di Audience Manager.</td> 
  </tr> 
  <tr> 
   <td> <strong>ID dichiarato o ID visitatore</strong><br /> </td> 
   <td> Esempio: ID dichiarato </td> 
  </tr> 
  <tr> 
   <td> <strong>Informazioni aggiuntive</strong><br /> </td> 
   <td> Eventuali informazioni o commenti utili </td> 
  </tr> 
 </tbody> 
</table>

## Configurazione dell&#39;integrazione in  Adobe Campaign {#configuring-the-integration-in-adobe-campaign}

Dopo aver inviato questa richiesta,  Adobe procederà al provisioning dell&#39;integrazione per voi e vi contatterà per fornire i dettagli e le informazioni che dovete completare la configurazione:

* [Passaggio 1: Configurare o controllare gli account esterni in  Adobe Campaign](#step-1--configure-or-check-the-external-accounts-in-adobe-campaign)
* [Passaggio 2: Configurare le origini dati](#step-2--configure-the-data-sources)
* [Passaggio 3: Configurare il server di tracciamento campagna](#step-3--configure-campaign-tracking-server)
* [Passaggio 4: Configurare il servizio ID visitatori](#step-4--configure-the-visitor-id-service)

### Passaggio 1: Configurare o controllare gli account esterni in  Adobe Campaign {#step-1--configure-or-check-the-external-accounts-in-adobe-campaign}

Dobbiamo prima configurare o controllare gli account esterni in  Adobe Campaign. Questi account avrebbero dovuto essere configurati  Adobe e le informazioni necessarie avrebbero dovuto essere comunicate all&#39;utente.

Per eseguire questa operazione:

1. Dal menu avanzato, selezionare **Amministrazione > Impostazioni applicazione > Account esterni**.

   Selezionate uno dei seguenti account esterni disponibili per l&#39;integrazione:

   ![](assets/integration_aam_1.png)

1. Immettere **[!UICONTROL Receiver server]** nel seguente formato
1. Immettere **[!UICONTROL AWS Access Key ID]**, **[!UICONTROL Secret Access Key]** e **[!UICONTROL AWS Region]**.

Gli account esterni sono ora configurati per questa integrazione.

### Passaggio 2: Configurare le origini dati {#step-2--configure-the-data-sources}

In Audience Manager vengono create le due seguenti origini dati:  Adobe Campaign (MID) e  Adobe Campaign (DichiaredId). Allo stesso tempo, queste due origini dati sono disponibili in  Adobe Campaign:

* **[!UICONTROL Recipient - Visitor ID (Defaultdatasources)]**: Si tratta di un&#39;origine dati out-of-the-box configurata per impostazione predefinita per l&#39;ID visitatore. I segmenti creati da Campaign faranno parte di questa origine dati.
* **Origine** dati ID dichiarata: Questa origine dati deve essere creata e mappata con la definizione dell&#39;origine  **[!UICONTROL DeclaredId]** dati  Audience Manager.

Nel caso di più siti Web con domini diversi,  Adobe Campaign non supporta la riconciliazione basata su ECID.

Per configurare l&#39;origine dati **[!UICONTROL Recipient - Visitor ID (Defaultdatasources)]**:

1. In **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Shared Data Sources]**, selezionare **[!UICONTROL Recipient - Visitor ID (Defaultdatasources)]**.

   ![](assets/integration_aam_2.png)

1. Scegliete **[!UICONTROL Adobe Campaign]** nel menu a discesa **[!UICONTROL Data Source/ Alias]**.
1. Immettere il **[!UICONTROL AAM Destination ID]** fornito dal Adobe .

   ![](assets/integration_aam_3.png)

1. Nella categoria **[!UICONTROL Reconciliation process]**, ti consigliamo di non modificare i criteri di riconciliazione e di utilizzare sempre la **[!UICONTROL Visitor ID]**.
1. Fai clic su **[!UICONTROL Save]**.

Per creare l&#39;origine dati **[!UICONTROL Declared ID]**:

1. In **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Shared Data Sources]**, fare clic sul pulsante **[!UICONTROL Create]**.
1. Modificare la **[!UICONTROL Label]** dell&#39;origine dati.
1. Nel menu a discesa **[!UICONTROL Data Source/ Alias]**, scegliete l&#39;Origine dati corrispondente all&#39;origine dati **[!UICONTROL DeclaredID]** dal  Audience Manager.
1. Configurare l&#39;origine dati immettendo i valori **[!UICONTROL Data Source / Alias]** e **[!UICONTROL AAM Destination ID]** forniti dal Adobe .
1. Impostate la **[!UICONTROL Reconciliation process]** come necessario.
1. Fai clic su **[!UICONTROL Save]**.

>[!NOTE]
>
>Il campo **[!UICONTROL AAM Destination ID]** non è richiesto se stai configurando l&#39;origine dati condivisa per l&#39; [integrazione Campaign-Triggers](../../integrating/using/configuring-triggers-in-experience-cloud.md). **[!UICONTROL Priority]** è necessario solo per configurare gli attivatori - Integrazione con Campaign. Priorità decide quale origine dati verrà configurata per prima. La priorità può essere un numero qualsiasi, ad esempio 1 o 100. Maggiore è la priorità, maggiore sarà la preferenza durante la riconciliazione.

### Passaggio 3: Configurare il server di tracciamento campagna {#step-3--configure-campaign-tracking-server}

Per la configurazione dell&#39;integrazione con il servizio di base Persone o Audience Manager, dobbiamo anche configurare il server di tracciamento delle campagne.

In questo caso, devi accertarti che il server di tracciamento campagna sia registrato nel dominio (CNAME). Per ulteriori informazioni sulla configurazione del nome di dominio, consultate questo articolo[.](https://helpx.adobe.com/it/campaign/kb/domain-name-delegation.html)

### Passaggio 4: Configurare il servizio ID visitatori {#step-4--configure-the-visitor-id-service}

Se il servizio ID visitatore non è mai stato configurato sulle proprietà Web o sui siti Web, fare riferimento al seguente [document](https://docs.adobe.com/content/help/en/id-service/using/implementation/setup-aam-analytics.html) per informazioni su come configurare il servizio o al seguente [video](https://helpx.adobe.com/it/marketing-cloud/how-to/email-marketing.html#step-two).

La configurazione e il provisioning sono completati. L&#39;integrazione ora può essere utilizzata per importare ed esportare audience o segmenti.
