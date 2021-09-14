---
title: Provisioning e configurazione dell’integrazione con Audience Manager o il servizio core People
description: 'Scopri come configurare l’integrazione del servizio core Audience Manager / Persone per iniziare a condividere audience o segmenti con le diverse soluzioni Adobe Experience Cloud. '
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
feature: People Core Service Integration
role: Data Architect
level: Intermediate
exl-id: 04d0fe26-a8cc-49ae-aaa9-b470169068ee
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '717'
ht-degree: 9%

---

# Provisioning e configurazione dell’integrazione con Audience Manager o il servizio core People{#provisioning-and-configuring-integration-with-audience-manager-or-people-core-service}

Il provisioning e la configurazione del core Audience Manager e People in Adobe Campaign seguono due passaggi: [Invio di una richiesta ad Adobe](#submitting-request-to-adobe) e quindi [Configurazione dell&#39;integrazione in Adobe Campaign](#configuring-the-integration-in-adobe-campaign).

## Invio di una richiesta ad Adobe {#submitting-request-to-adobe}

L’integrazione del servizio di base Audience Manager (AAM) o Persone consente di importare ed esportare tipi di pubblico o segmenti in Adobe Campaign.

Questa integrazione deve prima essere configurata. Per richiedere il provisioning di questa integrazione, invia un messaggio e-mail a [Digital-Request@adobe.com](mailto:Digital-Request@adobe.com) con le seguenti informazioni:

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Tipo di richiesta:</strong><br /> </td> 
   <td> Configurare l’integrazione del servizio core AAM/Persone-Campaign </td> 
  </tr> 
  <tr> 
   <td> <strong>Nome organizzazione:</strong><br /> </td> 
   <td> Nome organizzazione </td> 
  </tr> 
  <tr> 
   <td> <strong>ID organizzazione IMS</strong><br /> </td> 
   <td> L’ID organizzazione IMS. <br> Puoi trovare il tuo ID organizzazione IMS nell’Experience Cloud, nel menu Amministrazione . Viene fornito anche quando ci si connette per la prima volta a Adobe Experience Cloud. </td> 
  </tr> 
  <tr> 
   <td> <strong>Ambiente:</strong><br /> </td> 
   <td> Esempio: Produzione </td> 
  </tr> 
  <tr> 
   <td> <strong>Servizio AAM o persone</strong><br /> </td> 
   <td> Esempio: Adobe Audience Manager. Assicurati di indicare al team di provisioning se possiedi o meno la licenza Audience Manager.</td> 
  </tr> 
  <tr> 
   <td> <strong>ID dichiarato o ID visitatore</strong><br /> </td> 
   <td> Esempio: ID dichiarato </td> 
  </tr> 
  <tr> 
   <td> <strong>Informazioni aggiuntive</strong><br /> </td> 
   <td> Qualsiasi informazione o commento utile che si possa avere </td> 
  </tr> 
 </tbody> 
</table>

## Configurazione dell’integrazione in Adobe Campaign {#configuring-the-integration-in-adobe-campaign}

Dopo aver inviato questa richiesta, Adobe procederà al provisioning dell’integrazione per te e ti contatterà per fornire i dettagli e le informazioni necessarie per finalizzare la configurazione:

* [Passaggio 1: Configurare o controllare gli account esterni in Adobe Campaign](#step-1--configure-or-check-the-external-accounts-in-adobe-campaign)
* [Passaggio 2: Configurare le origini dati](#step-2--configure-the-data-sources)
* [Passaggio 3: Configurare il server di tracciamento delle campagne](#step-3--configure-campaign-tracking-server)
* [Passaggio 4: Configurare il servizio ID visitatori](#step-4--configure-the-visitor-id-service)

### Passaggio 1: Configurare o controllare gli account esterni in Adobe Campaign {#step-1--configure-or-check-the-external-accounts-in-adobe-campaign}

Innanzitutto, dobbiamo configurare o controllare gli account esterni in Adobe Campaign. Questi account avrebbero dovuto essere configurati per Adobe e le informazioni necessarie avrebbero dovuto essere comunicate all&#39;utente.

Per eseguire questa operazione:

1. Dal menu avanzato, seleziona **Amministrazione > Impostazioni applicazione > Account esterni**.

   Seleziona uno dei seguenti account esterni disponibili per questa integrazione:

   ![](assets/integration_aam_1.png)

1. Inserisci **[!UICONTROL Receiver server]** nel seguente formato
1. Inserisci i valori **[!UICONTROL AWS Access Key ID]**, **[!UICONTROL Secret Access Key]** e **[!UICONTROL AWS Region]**.

Gli account esterni sono ora configurati per questa integrazione.

### Passaggio 2: Configurare le origini dati {#step-2--configure-the-data-sources}

In Audience Manager vengono create le due seguenti origini dati: Adobe Campaign (MID) e Adobe Campaign (DeclaredId). Contemporaneamente, queste due origini dati sono disponibili in Adobe Campaign:

* **[!UICONTROL Recipient - Visitor ID (Defaultdatasources)]**: Si tratta di un’origine dati preconfigurata configurata configurata configurata per l’ID visitatore per impostazione predefinita. I segmenti creati da Campaign faranno parte di questa origine dati.
* **Origine** dati ID dichiarata: Questa origine dati deve essere creata e mappata con la definizione dell’origine  **[!UICONTROL DeclaredId]** dati di Audience Manager.

Nel caso di più siti web con domini diversi, Adobe Campaign non supporta la riconciliazione basata su ECID.

Per configurare l&#39;origine dati **[!UICONTROL Recipient - Visitor ID (Defaultdatasources)]**:

1. In **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Shared Data Sources]**, selezionare **[!UICONTROL Recipient - Visitor ID (Defaultdatasources)]**.

   ![](assets/integration_aam_2.png)

1. Scegli **[!UICONTROL Adobe Campaign]** nel menu a discesa **[!UICONTROL Data Source/ Alias]** .
1. Inserisci il **[!UICONTROL AAM Destination ID]** fornito dall&#39;Adobe.

   ![](assets/integration_aam_3.png)

1. Nella categoria **[!UICONTROL Reconciliation process]** ti consigliamo di non modificare i criteri di riconciliazione e di utilizzare sempre il valore **[!UICONTROL Visitor ID]**.
1. Fai clic su **[!UICONTROL Save]**.

Per creare l&#39;origine dati **[!UICONTROL Declared ID]**:

1. In **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Shared Data Sources]** fare clic sul pulsante **[!UICONTROL Create]**.
1. Modifica il **[!UICONTROL Label]** della tua origine dati.
1. Nel menu a discesa **[!UICONTROL Data Source/ Alias]** , scegli dall’Audience Manager Origine dati corrispondente all’ origine dati **[!UICONTROL DeclaredID]** .
1. Configura l’origine dati immettendo i valori **[!UICONTROL Data Source / Alias]** e **[!UICONTROL AAM Destination ID]** forniti dall’Adobe.
1. Imposta il **[!UICONTROL Reconciliation process]** come necessario.
1. Fai clic su **[!UICONTROL Save]**.

>[!NOTE]
>
>Il campo **[!UICONTROL AAM Destination ID]** non è richiesto se stai configurando l&#39;origine dati condivisa per l&#39; [Integrazione Campaign-Triggers](../../integrating/using/configuring-triggers-in-experience-cloud.md). **[!UICONTROL Priority]** è necessario solo per configurare l’integrazione Triggers - Campaign. Priorità decide quale Origine dati sarà configurata per prima. La priorità può essere un numero qualsiasi, ad esempio 1 o 100. Maggiore è la priorità, maggiore è la preferenza durante la riconciliazione.

### Passaggio 3: Configurare il server di tracciamento delle campagne {#step-3--configure-campaign-tracking-server}

Per la configurazione dell’integrazione con il servizio core Persone o Audience Manager, dobbiamo anche configurare il server di tracciamento delle campagne.

In questo caso, assicurati che Campaign Tracking Server sia registrato sul dominio (CNAME). Per ulteriori informazioni sulla configurazione del nome di dominio, consulta [questo articolo](https://helpx.adobe.com/it/campaign/kb/domain-name-delegation.html).

### Passaggio 4: Configurare il servizio ID visitatori {#step-4--configure-the-visitor-id-service}

Nel caso in cui il servizio ID visitatore non sia mai stato configurato sulle proprietà web o sui siti web, consulta il seguente [documento](https://experienceleague.adobe.com/docs/id-service/using/implementation/setup-aam-analytics.html) per informazioni su come configurare il servizio o il seguente [video](https://helpx.adobe.com/it/marketing-cloud/how-to/email-marketing.html#step-two).

La configurazione e il provisioning sono completati. L’integrazione può ora essere utilizzata per importare ed esportare tipi di pubblico o segmenti.
