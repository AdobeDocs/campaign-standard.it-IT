---
title: Configurazione dell’integrazione di Adobe Developer per Microsoft Dynamics 365
description: Scopri come configurare l’integrazione di Adobe Developer per l’integrazione con Microsoft Dynamics 365
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
feature: Microsoft CRM Integration
role: Data Architect
level: Intermediate
exl-id: ab21b694-d05c-4ba4-b828-936803651b82
source-git-commit: bee4da592e0b3727949bc44c6e41b81d4e7e73d4
workflow-type: tm+mt
source-wordcount: '625'
ht-degree: 1%

---

# Configurazione di Adobe Campaign Standard e Adobe Developer per l’integrazione con Microsoft Dynamics 365

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

Sarà necessario creare un nuovo progetto Adobe Developer e configurarlo per l’integrazione.

#### Crea un nuovo progetto

A tal fine, segui la procedura seguente:

1. Passa a [Console Adobe Developer](https://console.adobe.io/home#) e seleziona il tuo ID organizzazione Adobe dal menu a discesa in alto a destra della schermata.

1. Quindi fai clic su **[!UICONTROL Create new project]** sotto **[!UICONTROL Quick Start]**.

   ![](assets/adobeIO1.png)

1. Sotto **[!UICONTROL Get started with your new project]**, fai clic su **[!UICONTROL Add API]**.

   ![](assets/adobeIO2.png)

1. Seleziona l’API di Adobe Campaign (potrebbe essere necessario scorrere verso il basso) e fai clic su **[!UICONTROL Next]**.

   ![](assets/adobeIO3.png)

1. Nella schermata successiva sarà possibile caricare la propria chiave pubblica o lasciare che Adobe Developer generi la coppia di chiavi per te. Queste istruzioni seguiranno l&#39;ultima opzione. Se decidi di lasciare che Adobe Developer generi la coppia di chiavi, fai clic sull’opzione 1; quindi fai clic su **[!UICONTROL Generate keypair]** pulsante .

   ![](assets/adobeIO4.png)

1. Nella schermata successiva viene richiesto di assegnare un nome e selezionare il percorso di download del file zip della coppia di chiavi.

Una volta scaricato, puoi decomprimere il file per rivelare le chiavi pubbliche e private. Adobe Developer ha già applicato la chiave pubblica al progetto Adobe Developer. Sarà necessario mantenere la tua chiave privata per un momento successivo; la chiave privata verrà utilizzata durante la configurazione di pre-integrazione dello strumento di integrazione.

1. Fai clic su **[!UICONTROL Next]** per continuare

   ![](assets/adobeIO5.png)

1. Nella schermata successiva, seleziona i profili di prodotto da associare a questo progetto. Seleziona il profilo di prodotto che contiene nel titolo: L’ID tenant della tua istanza Campaign: [!UICONTROL Administrators]

   Esempio: Campaign Standard - your-campaign-tenantID - Administrators

1. Fai clic su **[!UICONTROL Save configured API]**.

   ![](assets/adobeIO6.png)

1. Nella schermata successiva vengono visualizzati i dettagli del nuovo progetto Adobe Developer. Fai clic su **[!UICONTROL Add to Project]** in alto a sinistra dello schermo e seleziona **API** dal menu a discesa.

   ![](assets/adobeIO7.png)

1. Nella schermata successiva sarà necessario selezionare l’API per gli eventi I/O, quindi fare clic su **[!UICONTROL Next]**.

1. Nella schermata successiva fai clic su **[!UICONTROL Save the configured API]**.  Verrai riportato alla schermata dei dettagli del progetto.

1. Ora fai clic su **[!UICONTROL Add to Project]** in alto a sinistra dello schermo e seleziona **API** dall’elenco a discesa, come in precedenza.

1. Nella schermata successiva sarà necessario selezionare l’API di gestione I/O e fare clic su **[!UICONTROL Next]**.

1. Nella schermata successiva fai clic su **[!UICONTROL Save the configured API]**.

La configurazione di pre-integrazione in Campaign è ora completa.

**Argomenti correlati**

* [Configurazione dell’integrazione di Adobe Developer per Microsoft Dynamics 365](../../integrating/using/d365-acs-configure-adobe-io.md) è il passaggio successivo nella configurazione dell’integrazione
* [Panoramica dell’applicazione self-service dell’integrazione](../../integrating/using/d365-acs-self-service-app-quick-start-guide.md) contiene l’elenco completo dei passaggi per rendere l’integrazione operativa.


* [Adobe Developer - Integrazione dell’account di servizio](https://developer.adobe.com/developer-console/docs/guides/#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)
* [Campaign Standard - Configurazione dell’accesso API](../../api/using/setting-up-api-access.md)
* [Integrazione Campaign Standard - Dynamics 365](../../integrating/using/d365-acs-configure-d365.md)
