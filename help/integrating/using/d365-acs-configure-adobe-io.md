---
title: Configurazione di Adobe IO per l’integrazione con Microsoft Dynamics 365
description: Scopri come configurare Adobe IO per l’integrazione con Microsoft Dynamics 365.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
feature: Microsoft CRM Integration
role: Data Architect
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '634'
ht-degree: 2%

---


# Configurazione di Adobe Campaign Standard ed Adobe I/O per l’integrazione con Microsoft Dynamics 365

Questo articolo illustra come configurare Adobe Campaign Standard e Adobe I/O per consentire all’applicazione di integrazione di accedere ai dati.

## Configurare Adobe Campaign Standard {#campaign-standard}

### Estensioni profilo

Abilita le &quot;estensioni di profilo&quot; in Adobe Campaign Standard.   Questo è necessario per sincronizzare i campi personalizzati nella risorsa Profilo da Microsoft Dynamics 365.   I passaggi per abilitarli sono i seguenti:

1. Vai a Impostazioni -> Amministrazione -> Sviluppo -> Pubblicazione.
1. Fai clic su &quot;Prepara pubblicazione&quot; per preparare una pubblicazione.
1. Al termine della preparazione, seleziona &quot;Crea l’API Ext Profiles &amp; Services&quot; e fai clic su &quot;Pubblica&quot;.

## Configurazione di I/O Adobe {#adobe-io}

Adobe I/O consente di abilitare l’accesso API ad Adobe Campaign Standard e ad altri prodotti Adobe.   Questo articolo illustra in dettaglio come configurare Adobe I/O per consentire all’integrazione Adobe Campaign Standard con Microsoft Dynamics 365 di accedere alla sincronizzazione dei dati.

### Panoramica

Prima di eseguire la configurazione di pre-integrazione in questo articolo, si presume che tu sia già stato effettuato il provisioning e che tu abbia accesso come amministratore all’istanza Campaign Standard della tua organizzazione.  Se non è successo, per completare il provisioning di Campaign dovrai contattare l’Assistenza clienti Adobe.

>[!CAUTION]
>
>I passaggi descritti di seguito devono essere eseguiti da un amministratore.

### Configurazione

Sarà necessario creare un nuovo progetto Adobe IO e configurarlo per l&#39;integrazione.

#### Crea un nuovo progetto

A tal fine, segui la procedura seguente:

1. Passa a [Adobe IO Console](https://console.adobe.io/home#) e seleziona il tuo Adobe IMS Organization ID dal menu a discesa in alto a destra dello schermo.

1. Quindi fai clic su **[!UICONTROL Create new project]** in **[!UICONTROL Quick Start]**.

   ![](assets/adobeIO1.png)

1. In **[!UICONTROL Get started with your new project]**, fai clic su **[!UICONTROL Add API]**.

   ![](assets/adobeIO2.png)

1. Seleziona l’API di Adobe Campaign (potrebbe essere necessario scorrere verso il basso) e fai clic su **[!UICONTROL Next]**.

   ![](assets/adobeIO3.png)

1. Nella schermata successiva avrai la possibilità di caricare la tua chiave pubblica o di lasciare che Adobe IO generi la coppia di chiavi per te. Queste istruzioni seguiranno l&#39;ultima opzione. Se si decide di lasciare che Adobe IO generi la coppia di chiavi, fare clic sull&#39;opzione 1; quindi fai clic sul pulsante **[!UICONTROL Generate keypair]** .

   ![](assets/adobeIO4.png)

1. Nella schermata successiva viene richiesto di assegnare un nome e selezionare il percorso di download del file zip della coppia di chiavi.

Una volta scaricato, puoi decomprimere il file per rivelare le chiavi pubbliche e private. Adobe IO ha già applicato la chiave pubblica al progetto di I/O di Adobe. Sarà necessario mantenere la tua chiave privata per un momento successivo; la chiave privata verrà utilizzata durante la configurazione di pre-integrazione dello strumento di integrazione.

1. Fare clic su **[!UICONTROL Next]** per continuare

   ![](assets/adobeIO5.png)

1. Nella schermata successiva, seleziona i profili di prodotto da associare a questo progetto. Seleziona il profilo di prodotto che contiene nel titolo: ID tenant dell’istanza Campaign - [!UICONTROL Administrators]

   Esempio: Campaign Standard - your-campaign-tenantID - Administrators

1. Fai clic su **[!UICONTROL Save configured API]**.

   ![](assets/adobeIO6.png)

1. Nella schermata successiva vengono visualizzati i dettagli del nuovo progetto Adobe IO. Fai clic su **[!UICONTROL Add to Project]** in alto a sinistra dello schermo e seleziona **API** dal menu a discesa.

   ![](assets/adobeIO7.png)

1. Nella schermata successiva sarà necessario selezionare l’API per gli eventi di I/O, quindi fare clic su **[!UICONTROL Next]**.

1. Nella schermata successiva fai clic su **[!UICONTROL Save the configured API]**.  Verrai riportato alla schermata dei dettagli del progetto.

1. Ora fai clic su **[!UICONTROL Add to Project]** in alto a sinistra dello schermo e seleziona **API** dal menu a discesa, come in precedenza.

1. Nella schermata successiva sarà necessario selezionare l’API di gestione I/O e fare clic su **[!UICONTROL Next]**.

1. Nella schermata successiva fai clic su **[!UICONTROL Save the configured API]**.

La configurazione di pre-integrazione in Campaign è ora completa.

**Argomenti correlati**

* [Configurare Adobe IO per l’](../../integrating/using/d365-acs-configure-adobe-io.md) integrazione con Microsoft Dynamics 365 è il passaggio successivo nella configurazione dell’integrazione
* [Integrazione ](../../integrating/using/d365-acs-self-service-app-quick-start-guide.md) Panoramica delle applicazioni self-service contiene l’elenco completo dei passaggi necessari per il corretto funzionamento dell’integrazione.


* [Adobe IO - Integrazione dell&#39;account di servizio](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)
* [Campaign Standard - Configurazione dell’accesso API](../../api/using/setting-up-api-access.md)
* [Integrazione Campaign Standard - Dynamics 365](../../integrating/using/d365-acs-configure-d365.md)
