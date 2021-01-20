---
title: Configurazione di Adobe IO per l’integrazione con Microsoft Dynamics 365
description: Scoprite come configurare  Adobe IO per l'integrazione con Microsoft Dynamics 365.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
translation-type: tm+mt
source-git-commit: fe5d40235abc33c0ea7e929cd2e69b7030cea0b1
workflow-type: tm+mt
source-wordcount: '628'
ht-degree: 2%

---


#  configurazione Adobe I/O e Adobe Campaign Standard per l&#39;integrazione con Microsoft Dynamics 365

Questo articolo spiega come configurare  Adobe Campaign Standard e  Adobe I/O per consentire all’applicazione di integrazione di accedere ai dati.

## Configurare  Adobe Campaign Standard {#campaign-standard}

### Estensioni profilo

Abilitare le &quot;estensioni di profilo&quot; in  Adobe Campaign Standard.   Questo è necessario per sincronizzare i campi personalizzati nella risorsa Profilo da Microsoft Dynamics 365.   I passaggi per attivarli sono:

1. Vai a Impostazioni -> Amministrazione -> Sviluppo -> Pubblicazione.
1. Fate clic su &quot;Prepara pubblicazione&quot; per preparare una pubblicazione.
1. Al termine della preparazione, selezionate &quot;Create the Profiles &amp; Services Ext API&quot; e fate clic su &quot;Publish&quot;.

## Configurazione di I/O Adobe {#adobe-io}

 Adobe I/O consente di abilitare l&#39;accesso API a  Adobe Campaign Standard e ad altri prodotti Adobi .   In questo articolo viene illustrato come configurare  Adobe I/O per consentire l&#39;integrazione di Adobe Campaign Standard con Microsoft Dynamics 365  con accesso a Microsoft Dynamics 365 per la sincronizzazione dei dati.

### Panoramica

Prima di eseguire la configurazione di pre-integrazione in questo articolo, si presume che sia già stato eseguito il provisioning e che l&#39;amministratore abbia accesso all&#39;istanza Campaign Standard dell&#39;organizzazione.  Se non è successo, per completare il provisioning delle campagne dovrete contattare &#39;Assistenza clienti di Adobe.

>[!CAUTION]
>
>I passaggi descritti di seguito devono essere eseguiti da un amministratore.

### Configurazione

Sarà necessario creare un nuovo progetto IO di Adobe  e configurarlo per l&#39;integrazione.

#### Creare un nuovo progetto

A tal fine, attenersi alla procedura seguente:

1. Andate a [ console IO Adobe](https://console.adobe.io/home#) e selezionate l&#39;ID organizzazione IMS del Adobe  dal menu a discesa in alto a destra della schermata.

1. Fare clic su **[!UICONTROL Create new project]** in **[!UICONTROL Quick Start]**.

   ![](assets/adobeIO1.png)

1. In **[!UICONTROL Get started with your new project]**, fare clic su **[!UICONTROL Add API]**.

   ![](assets/adobeIO2.png)

1. Selezionate l&#39;API Adobe Campaign  (potrebbe essere necessario scorrere verso il basso) e fate clic su **[!UICONTROL Next]**.

   ![](assets/adobeIO3.png)

1. Nella schermata successiva sarà possibile caricare la propria chiave pubblica o lasciare che  IO Adobe generi la coppia di chiavi. Queste istruzioni seguiranno l&#39;ultima opzione. Se si decide di lasciare che  IO Adobe generi la coppia di chiavi, fare clic sull&#39;opzione 1; quindi fare clic sul pulsante **[!UICONTROL Generate keypair]**.

   ![](assets/adobeIO4.png)

1. Nella schermata successiva vi verrà richiesto di assegnare un nome e selezionare il percorso di download del file zip della coppia di chiavi.

Una volta scaricato, potete decomprimere il file per visualizzare le chiavi pubblica e privata.  I/O Adobe ha già applicato la chiave pubblica al progetto I/O del Adobe . Dovrete mantenere la vostra chiave privata per un momento successivo; la chiave privata verrà utilizzata durante la configurazione preliminare dello strumento di integrazione.

1. Fare clic su **[!UICONTROL Next]** per continuare

   ![](assets/adobeIO5.png)

1. Nella schermata successiva verranno selezionati i profili di prodotto da associare a questo progetto. Selezionate il profilo di prodotto che contiene il titolo: ID tenant dell&#39;istanza della campagna - [!UICONTROL Administrators]

   Esempio: Campaign Standard - your-campaign-tenantID - Administrators

1. Fai clic su **[!UICONTROL Save configured API]**.

   ![](assets/adobeIO6.png)

1. Nella schermata successiva verranno visualizzati i dettagli del nuovo progetto IO del Adobe . Fare clic su **[!UICONTROL Add to Project]** in alto a sinistra dello schermo e selezionare **API** dall&#39;elenco a discesa.

   ![](assets/adobeIO7.png)

1. Nella schermata successiva dovrete selezionare l&#39;API Eventi di I/O, quindi fare clic su **[!UICONTROL Next]**.

1. Nella schermata successiva fare clic su **[!UICONTROL Save the configured API]**.  Viene nuovamente visualizzata la schermata dei dettagli del progetto.

1. Ora fai clic su **[!UICONTROL Add to Project]** in alto a sinistra dello schermo e seleziona **API** dall&#39;elenco a discesa, come hai fatto in precedenza.

1. Nella schermata successiva dovrete selezionare l&#39;API di gestione I/O e fare clic su **[!UICONTROL Next]**.

1. Nella schermata successiva fare clic su **[!UICONTROL Save the configured API]**.

La configurazione di pre-integrazione in Campaign ora è completa.

**Argomenti correlati**

* [Configurare  Adobe I/O per l&#39;](../../integrating/using/d365-acs-configure-adobe-io.md) integrazione con Microsoft Dynamics 365 è il passaggio successivo per l&#39;impostazione dell&#39;integrazione
* [Integrazione Self-Service Application ](../../integrating/using/d365-acs-self-service-app-quick-start-guide.md) Overview contiene l&#39;elenco completo dei passaggi per rendere l&#39;integrazione operativa.


* [I/O Adobe  - Integrazione dell&#39;account di servizio](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)
* [Campaign Standard - Impostazione accesso API](../../api/using/setting-up-api-access.md)
* [Campaign Standard - Integrazione Dynamics 365](../../integrating/using/d365-acs-configure-d365.md)
