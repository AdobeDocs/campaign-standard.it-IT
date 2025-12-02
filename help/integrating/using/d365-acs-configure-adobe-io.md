---
title: Configurare l’integrazione di Adobe Developer per Microsoft Dynamics 365
description: Scopri come configurare l’integrazione di Adobe Developer per Microsoft Dynamics 365
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
feature: Microsoft CRM Integration
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: ab21b694-d05c-4ba4-b828-936803651b82
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '568'
ht-degree: 0%

---

# Configurazione di Adobe Campaign Standard e Adobe Developer per l’integrazione con Microsoft Dynamics 365

Questo articolo illustra come configurare Adobe Campaign Standard e Adobe I/O per consentire all’applicazione di integrazione di accedere ai dati.

## Configurare Adobe Campaign Standard {#campaign-standard}

### Estensioni profilo

Abilita le &quot;estensioni del profilo&quot; in Adobe Campaign Standard.   Ciò è necessario per sincronizzare i campi personalizzati nella risorsa Profilo da Microsoft Dynamics 365.   I passaggi per abilitarli sono i seguenti:

1. Vai a Impostazioni -> Amministrazione -> Sviluppo -> Pubblicazione.
1. Fai clic su &quot;Prepara pubblicazione&quot; per preparare una pubblicazione.
1. Al termine della preparazione, seleziona &quot;Create the Profiles &amp; Services Ext API&quot; (Crea l’API esterna di Profili e servizi) e fai clic su &quot;Publish&quot; (Pubblica).

## Configurare Adobe I/O {#adobe-io}

Adobe I/O consente di abilitare l’accesso API ad Adobe Campaign Standard e ad altri prodotti Adobe.   Questo articolo illustra come configurare Adobe I/O per consentire all’integrazione Adobe Campaign Standard con Microsoft Dynamics 365 di accedere per sincronizzare i dati.

### Panoramica

Prima di eseguire la configurazione della pre-integrazione in questo articolo, si presume che sia già stato eseguito il provisioning e che tu abbia accesso come amministratore all’istanza Campaign Standard della tua organizzazione.  Se questo non si è verificato, dovrai contattare l’Assistenza clienti di Adobe per completare il provisioning di Campaign.

>[!CAUTION]
>
>I passaggi descritti di seguito devono essere eseguiti da un amministratore.

### Configurazione

Dovrai creare un nuovo progetto Adobe Developer e configurarlo per l’integrazione.

#### Crea un nuovo progetto

A questo scopo, segui la procedura indicata di seguito:

1. Passa a [Adobe Developer Console](https://console.adobe.io/home#) e seleziona il tuo ID organizzazione Adobe dal menu a discesa in alto a destra dello schermo.

1. Quindi fare clic su **[!UICONTROL Create new project]** in **[!UICONTROL Quick Start]**.

   ![](assets/adobeIO1.png)

1. In **[!UICONTROL Get started with your new project]**, fare clic su **[!UICONTROL Add API]**.

   ![](assets/adobeIO2.png)

1. Selezionare Adobe Campaign e fare clic su **[!UICONTROL Next]**.

   ![](assets/adobeIO3.png)

1. Nella schermata successiva è disponibile l’opzione per scegliere il tipo di autenticazione. È possibile scegliere OAuth Server-to-Server o Account di servizio (JWT). Tieni presente che le credenziali dell’account di servizio (JWT) non sono più consigliate per i nuovi progetti e sono state dichiarate obsolete a favore delle nuove credenziali server-to-server OAuth. Le istruzioni fornite in questa guida si applicano solo all’autenticazione server-to-server di OAuth.

   ![](assets/adobeIO4.png)

1. Nella schermata successiva seleziona i profili di prodotto da associare a questo progetto. Seleziona il profilo prodotto contenente nel titolo: ID tenant dell&#39;istanza Campaign - [!UICONTROL Administrators]

   Esempio: Campaign Standard - your-campaign-tenantID - Administrators

1. Fai clic su **[!UICONTROL Save configured API]**.

   ![](assets/adobeIO5.png)

1. Nella schermata successiva vengono visualizzati i dettagli del nuovo progetto Adobe Developer. Fai clic su **[!UICONTROL Add to Project]** in alto a sinistra dello schermo e seleziona **API** dal menu a discesa.

   ![](assets/adobeIO6.png)

1. Nella schermata successiva sarà necessario selezionare l&#39;API degli eventi di I/O, quindi fare clic su **[!UICONTROL Next]**.

1. Nella schermata successiva fare clic su **[!UICONTROL Save the configured API]**.  Verrai riportato alla schermata dei dettagli del progetto.

1. Ora fai clic su **[!UICONTROL Add to Project]** in alto a sinistra dello schermo e seleziona **API** dal menu a discesa, come in precedenza.

1. Nella schermata successiva è necessario selezionare l&#39;API di gestione I/O e fare clic su **[!UICONTROL Next]**.

1. Nella schermata successiva fare clic su **[!UICONTROL Save the configured API]**.

L’impostazione di pre-integrazione in Campaign è ora completa.

**Argomenti correlati**

* [Configurare l&#39;integrazione di Adobe Developer per Microsoft Dynamics 365](../../integrating/using/d365-acs-configure-adobe-io.md) è il passaggio successivo per configurare l&#39;integrazione
* [Panoramica dell&#39;applicazione self-service di integrazione](../../integrating/using/d365-acs-self-service-app-quick-start-guide.md) contiene l&#39;elenco completo dei passaggi necessari per rendere operativa l&#39;integrazione.
* [Adobe Developer - Integrazione account di servizio](https://developer.adobe.com/developer-console/docs/guides/#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)
* [Campaign Standard - Configurazione accesso API](../../api/using/setting-up-api-access.md)
* [Integrazione Campaign Standard - Dynamics 365](../../integrating/using/d365-acs-configure-d365.md)
* [Migra credenziali da JWT a OAuth Server-to-Server](../../integrating/using/d365-acs-self-service-app-migrate-credentials.md) contiene i passaggi per migrare le credenziali da JWT a OAuth Server-to-Server.
