---
title: Provisioning e configurazione dell’integrazione con Audience Manager o il servizio core People
description: Scopri come configurare l’integrazione del servizio core Audience Manager/People per iniziare a condividere audience o segmenti con le diverse soluzioni Adobe Experience Cloud.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
feature: People Core Service Integration
role: Data Architect
level: Intermediate
exl-id: 04d0fe26-a8cc-49ae-aaa9-b470169068ee
source-git-commit: 26e37cea37b33924ac634c5e4ab7c60804a738f1
workflow-type: tm+mt
source-wordcount: '759'
ht-degree: 6%

---

# Provisioning e configurazione dell’integrazione con Audience Manager o il servizio core People{#integration-with-audience-manager-or-people-core-service}

Il provisioning e la configurazione del core Audience Manager e People in Adobe Campaign richiedono due passaggi: [Invio della richiesta a Adobe](#submitting-request-to-adobe), [Configurazione dell&#39;integrazione in Adobe Campaign](#configuring-the-integration-in-adobe-campaign).

## Invio di una richiesta all’Adobe {#submitting-request-to-adobe}

L’integrazione di Audience Manager (AAM) o del servizio core People consente di importare ed esportare tipi di pubblico o segmenti in Adobe Campaign.

Questa integrazione deve prima essere configurata. Per richiedere il provisioning di questa integrazione, invia un messaggio e-mail a [Digital-Request@adobe.com](mailto:Digital-Request@adobe.com) con le seguenti informazioni:

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Tipo di richiesta:</strong><br /> </td> 
   <td> Configurare l’integrazione tra il servizio core AAM/People e Campaign </td> 
  </tr> 
  <tr> 
   <td> <strong>Nome organizzazione:</strong><br /> </td> 
   <td> Nome dell’organizzazione </td> 
  </tr> 
  <tr> 
   <td> <strong>ID organizzazione IMS</strong><br /> </td> 
   <td> Il tuo Organization ID. <br> Per trovare il tuo ID organizzazione, fai riferimento a <a href="https://experienceleague.adobe.com/docs/core-services/interface/administration/organizations.html?lang=it">questa pagina</a></td> 
  </tr> 
  <tr> 
   <td> <strong>Ambiente:</strong><br /> </td> 
   <td> Esempio: Produzione </td> 
  </tr> 
  <tr> 
   <td> <strong>AAM o il servizio People</strong><br /> </td> 
   <td> Esempio: Adobe Audience Manager. Assicurati di segnalare al team di provisioning se possiedi o meno la licenza Audience Manager.</td> 
  </tr> 
  <tr> 
   <td> <strong>ID dichiarato o ID visitatore</strong><br /> </td> 
   <td> Esempio: ID dichiarato </td> 
  </tr> 
  <tr> 
   <td> <strong>Informazioni aggiuntive</strong><br /> </td> 
   <td> Qualsiasi informazione o commento utile </td> 
  </tr> 
 </tbody> 
</table>

## Configurazione dell’integrazione in Adobe Campaign {#configuring-the-integration-in-adobe-campaign}

Dopo aver inviato questa richiesta, Adobe procederà al provisioning dell’integrazione e ti contatterà per fornire i dettagli e le informazioni necessarie per finalizzare la configurazione:

* [Passaggio 1: configurare o controllare gli account esterni in Adobe Campaign](#step-1--configure-or-check-the-external-accounts-in-adobe-campaign)
* [Passaggio 2: configurare le origini dati](#step-2--configure-the-data-sources)
* [Passaggio 3: configurare il server di tracciamento campagna](#step-3--configure-campaign-tracking-server)
* [Passaggio 4: configurare il servizio ID visitatori](#step-4--configure-the-visitor-id-service)

### Passaggio 1: configurare o controllare gli account esterni in Adobe Campaign {#step-1--configure-or-check-the-external-accounts-in-adobe-campaign}

Innanzitutto, devi configurare o controllare gli account esterni in Adobe Campaign. Questi account avrebbero dovuto essere configurati da Adobe e le informazioni necessarie avrebbero dovuto essere comunicate all&#39;utente.

Per eseguire questa operazione:

1. Dal menu avanzato, selezionare **Amministrazione > Impostazioni applicazione > Account esterni**.

   Seleziona uno dei seguenti account esterni disponibili per questa integrazione:

   ![](assets/integration_aam_1.png)

1. Immetti **[!UICONTROL Receiver server]** nel seguente formato
1. Immettere **[!UICONTROL AWS Access Key ID]**, **[!UICONTROL Secret Access Key]** e **[!UICONTROL AWS Region]**.

Gli account esterni sono ora configurati per questa integrazione.

### Passaggio 2: configurare le origini dati {#step-2--configure-the-data-sources}

In Audience Manager vengono create le due seguenti origini dati: Adobe Campaign (MID) e Adobe Campaign (DeclaredId). Allo stesso tempo, queste due origini dati sono disponibili in Adobe Campaign:

* **[!UICONTROL Recipient - Visitor ID (Defaultdatasources)]**: si tratta di un&#39;origine dati predefinita configurata per impostazione predefinita per l&#39;ID visitatore. I segmenti creati da Campaign faranno parte di questa origine dati.
* **Origine dati ID dichiarato**: questa origine dati deve essere creata e mappata con la definizione dell&#39;origine dati **[!UICONTROL DeclaredId]** di Audience Manager.

Tieni presente che, nel caso di più siti web con domini diversi, Adobe Campaign non supporta la riconciliazione basata su ECID.

Per configurare l&#39;origine dati **[!UICONTROL Recipient - Visitor ID (Defaultdatasources)]**:

1. In **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Shared Data Sources]**, selezionare **[!UICONTROL Recipient - Visitor ID (Defaultdatasources)]**.

   ![](assets/integration_aam_2.png)

1. Scegliere **[!UICONTROL Adobe Campaign]** nel menu a discesa **[!UICONTROL Data Source/ Alias]**.
1. Immetti **[!UICONTROL AAM Destination ID]** fornito dall&#39;Adobe.

   ![](assets/integration_aam_3.png)

1. Nella categoria **[!UICONTROL Reconciliation process]** si consiglia di non modificare i criteri di riconciliazione e di utilizzare sempre **[!UICONTROL Visitor ID]**.
1. Fai clic su **[!UICONTROL Save]**.

Per creare l&#39;origine dati **[!UICONTROL Declared ID]**:

1. In **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Shared Data Sources]**, fare clic sul pulsante **[!UICONTROL Create]**.
1. Modifica **[!UICONTROL Label]** dell&#39;origine dati.
1. Nell&#39;elenco a discesa **[!UICONTROL Data Source/ Alias]**, scegliere il Data Source corrispondente all&#39;origine dati **[!UICONTROL DeclaredID]** da Audience Manager.
1. Configurare l&#39;origine dati immettendo **[!UICONTROL Data Source / Alias]** e **[!UICONTROL AAM Destination ID]** forniti da Adobe.
1. Imposta **[!UICONTROL Reconciliation process]** come necessario.
1. Fai clic su **[!UICONTROL Save]**.

>[!NOTE]
>
>Il campo **[!UICONTROL AAM Destination ID]** non è necessario se si sta configurando l&#39;origine dati condivisa per l&#39;integrazione [Campaign-Triggers](../../integrating/using/configuring-triggers-in-experience-cloud.md). **[!UICONTROL Priority]** è necessario solo durante la configurazione dell&#39;integrazione Triggers - Campaign. La priorità determina quale Data Source verrà configurato per primo. La priorità può essere un numero qualsiasi, ad esempio 1 o 100. Maggiore è la priorità, maggiore è la preferenza durante la riconciliazione.

### Passaggio 3: configurare il server di tracciamento campagna {#step-3--configure-campaign-tracking-server}

Per la configurazione dell’integrazione con il servizio core People o Audience Manager, è necessario configurare anche il server di tracciamento di Campaign.

Per consentire ai tipi di pubblico condivisi di funzionare con l’ID visitatore, il dominio del server di tracciamento deve essere un sottodominio dell’URL su cui è stato fatto clic o del sito web principale.

>[!IMPORTANT]
>
> Assicurati che il server di tracciamento di Campaign sia registrato nel dominio (CNAME). Ulteriori informazioni sulla configurazione del nome di dominio sono disponibili in [questo articolo](https://helpx.adobe.com/it/campaign/kb/domain-name-delegation.html).

### Passaggio 4: configurare il servizio ID visitatori {#step-4--configure-the-visitor-id-service}

Nel caso in cui il servizio ID visitatore non sia mai stato configurato nelle proprietà o nei siti Web, consulta il seguente [documento](https://experienceleague.adobe.com/docs/id-service/using/implementation/setup-aam-analytics.html) per scoprire come configurare il servizio o il seguente [video](https://helpx.adobe.com/it/marketing-cloud/how-to/email-marketing.html#step-two).

Sincronizza gli identificatori cliente con ID dichiarato utilizzando la funzione `setCustomerID` nel servizio ID Experience Cloud con il codice di integrazione: `AdobeCampaignID`. `AdobeCampaignID` deve corrispondere al valore della chiave di riconciliazione impostata nel Source dati del destinatario configurato in [Passaggio 2: configurare le origini dati](#step-2--configure-the-data-sources).

La configurazione e il provisioning sono finalizzati, l’integrazione ora può essere utilizzata per importare ed esportare tipi di pubblico o segmenti.
