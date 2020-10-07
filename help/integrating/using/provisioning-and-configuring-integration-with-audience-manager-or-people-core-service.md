---
title: Provisioning e configurazione dell’integrazione con Audience Manager o il servizio core People
description: 'Scoprite come configurare l''integrazione del servizio di base  Audience Manager / Persone per iniziare a condividere audience o segmenti con le diverse soluzioni Adobe Experience Cloud. '
page-status-flag: never-activated
uuid: e7329644-0033-4729-b4a7-61bef137f4b5
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
discoiquuid: eb24f4ea-325f-433a-91a0-c45906320bcb
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '726'
ht-degree: 8%

---


# Provisioning e configurazione dell’integrazione con Audience Manager o il servizio core People{#provisioning-and-configuring-integration-with-audience-manager-or-people-core-service}

Il provisioning e la configurazione di  Audience Manager e Persone di base in  Adobe Campaign eseguono due passaggi: [Invio di una richiesta a  Adobe](#submitting-request-to-adobe) , quindi [Configurazione dell&#39;integrazione in  Adobe Campaign](#configuring-the-integration-in-adobe-campaign).

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

## Configurazione dell’integrazione in  Adobe Campaign {#configuring-the-integration-in-adobe-campaign}

Dopo aver inviato questa richiesta,  Adobe procederà al provisioning dell&#39;integrazione per voi e vi contatterà per fornire i dettagli e le informazioni che dovete completare la configurazione:

* [Passaggio 1: Configurare o controllare gli account esterni in  Adobe Campaign](#step-1--configure-or-check-the-external-accounts-in-adobe-campaign)
* [Passaggio 2: Configurare le origini dati](#step-2--configure-the-data-sources)
* [Passaggio 3: Configurare il server di tracciamento campagna](#step-3--configure-campaign-tracking-server)
* [Passaggio 4: Configurare il servizio ID visitatori](#step-4--configure-the-visitor-id-service)

### Passaggio 1: Configurare o controllare gli account esterni in  Adobe Campaign {#step-1--configure-or-check-the-external-accounts-in-adobe-campaign}

Dobbiamo prima configurare o controllare gli account esterni in  Adobe Campaign. Questi account avrebbero dovuto essere configurati  Adobe e le informazioni necessarie avrebbero dovuto essere comunicate all&#39;utente.

Per eseguire questa operazione:

1. Dal menu avanzato, selezionate **Amministrazione > Impostazioni applicazione > Account** esterni.

   Selezionate uno dei seguenti account esterni disponibili per l&#39;integrazione:

   ![](assets/integration_aam_1.png)

1. Immettere **[!UICONTROL Receiver server]** il formato seguente
1. Inserite il **[!UICONTROL AWS Access Key ID]**, **[!UICONTROL Secret Access Key]** e **[!UICONTROL AWS Region]**.

Gli account esterni sono ora configurati per questa integrazione.

### Passaggio 2: Configurare le origini dati {#step-2--configure-the-data-sources}

In Audience Manager vengono create le due seguenti origini dati:  Adobe Campaign (MID) e  Adobe Campaign (DichiaredId). Allo stesso tempo, queste due origini dati sono disponibili in  Adobe Campaign:

* **[!UICONTROL Recipient - Visitor ID (Defaultdatasources)]**: Si tratta di un&#39;origine dati out-of-the-box configurata per impostazione predefinita per l&#39;ID visitatore. I segmenti creati da Campaign faranno parte di questa origine dati.
* **Origine dati ID** dichiarata: Questa origine dati deve essere creata e mappata con la definizione dell&#39;origine dati **[!UICONTROL DeclaredId]** dal Audience Manager .

Nel caso di più siti Web con domini diversi,  Adobe Campaign non supporta la riconciliazione basata su ECID.

Per configurare l&#39;origine **[!UICONTROL Recipient - Visitor ID (Defaultdatasources)]** dati:

1. In **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Shared Data Sources]**, select **[!UICONTROL Recipient - Visitor ID (Defaultdatasources)]**.

   ![](assets/integration_aam_2.png)

1. Choose **[!UICONTROL Adobe Campaign]** in the **[!UICONTROL Data Source/ Alias]** drop-down.
1. Inserite il valore **[!UICONTROL AAM Destination ID]** fornito dal Adobe .

   ![](assets/integration_aam_3.png)

1. Nella **[!UICONTROL Reconciliation process]** categoria, consigliamo di non modificare i criteri di riconciliazione e di utilizzare sempre il **[!UICONTROL Visitor ID]**.
1. Fai clic su **[!UICONTROL Save]**.

Per creare l&#39;origine **[!UICONTROL Declared ID]** dati:

1. In **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Shared Data Sources]**, fate clic sul **[!UICONTROL Create]** pulsante.
1. Modificare l&#39;origine **[!UICONTROL Label]** dati.
1. Nel **[!UICONTROL Data Source/ Alias]** menu a discesa, scegliete l&#39;Origine dati corrispondente all&#39;origine **[!UICONTROL DeclaredID]** dati dal Audience Manager .
1. Configura l&#39;origine dati immettendo **[!UICONTROL Data Source / Alias]** e **[!UICONTROL AAM Destination ID]** fornendo  Adobe.
1. Impostate le opzioni **[!UICONTROL Reconciliation process]** in base alle esigenze.
1. Fai clic su **[!UICONTROL Save]**.

>[!NOTE]
>
>Il **[!UICONTROL AAM Destination ID]** campo non è richiesto se stai configurando l&#39;origine dati condivisa per l&#39;integrazione [](../../integrating/using/configuring-triggers-in-experience-cloud.md)Campaign-Triggers. **[!UICONTROL Priority]** è necessario solo per configurare gli attivatori - Integrazione con Campaign. Priorità decide quale origine dati verrà configurata per prima. La priorità può essere un numero qualsiasi, ad esempio 1 o 100. Maggiore è la priorità, maggiore sarà la preferenza durante la riconciliazione.

### Passaggio 3: Configurare il server di tracciamento campagna {#step-3--configure-campaign-tracking-server}

Per la configurazione dell&#39;integrazione con il servizio di base Persone o Audience Manager, dobbiamo anche configurare il server di tracciamento delle campagne.

In questo caso, devi accertarti che il server di tracciamento campagna sia registrato nel dominio (CNAME). Ulteriori informazioni sulla delega dei nomi di dominio sono disponibili in [questo articolo](https://docs.campaign.adobe.com/doc/AC/en/technicalResources/Technotes/AdobeCampaign_Deliverability_Sub_Domain_Delegation.pdf).

### Passaggio 4: Configurare il servizio ID visitatori {#step-4--configure-the-visitor-id-service}

Se il servizio ID visitatore non è mai stato configurato sulle proprietà Web o sui siti Web, consulta il seguente [documento](https://docs.adobe.com/content/help/en/id-service/using/implementation/setup-aam-analytics.html) per apprendere come configurare il servizio o il [video](https://helpx.adobe.com/it/marketing-cloud/how-to/email-marketing.html#step-two)seguente.

La configurazione e il provisioning sono completati. L&#39;integrazione ora può essere utilizzata per importare ed esportare audience o segmenti.
