---
title: Configurare l’integrazione di Adobe Developer per Microsoft Dynamics 365
description: Scopri come configurare l’integrazione di Adobe Developer per Microsoft Dynamics 365
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
feature: Microsoft CRM Integration
role: Data Architect
level: Intermediate
exl-id: ab21b694-d05c-4ba4-b828-936803651b82
source-git-commit: c701043cbba22711de1ea7ddc5266e193d771e14
workflow-type: tm+mt
source-wordcount: '568'
ht-degree: 0%

---

# Configurazione di Adobe Campaign Standard e Adobe Developer per l’integrazione con Microsoft Dynamics 365

Questo articolo illustra come configurare Adobe Campaign Standard e Adobe I/O per consentire all’applicazione di integrazione di accedere ai dati.

## Configurare Adobe Campaign Standard {#campaign-standard}

### Estensioni profilo

Abilita le &quot;estensioni del profilo&quot; in Adobe Campaign Standard.   Questo è necessario per sincronizzare i campi personalizzati nella risorsa Profilo da Microsoft Dynamics 365.   I passaggi per abilitarli sono i seguenti:

1. Vai a Impostazioni -> Amministrazione -> Sviluppo -> Pubblicazione.
1. Fai clic su &quot;Prepara pubblicazione&quot; per preparare una pubblicazione.
1. Al termine della preparazione, seleziona &quot;Create the Profiles &amp; Services Ext API&quot; (Crea l’API esterna di Profili e servizi) e fai clic su &quot;Publish&quot; (Pubblica).

## Configura Adobe I/O {#adobe-io}

Adobe I/O consente di abilitare l’accesso API ad Adobe Campaign Standard e ad altri prodotti Adobe.   Questo articolo illustra come configurare Adobe I/O per consentire all’integrazione Adobe Campaign Standard con Microsoft Dynamics 365 di accedere per sincronizzare i dati.

### Panoramica

Prima di eseguire la configurazione della pre-integrazione in questo articolo, si presume che sia già stato eseguito il provisioning e che tu abbia accesso come amministratore all’istanza Campaign Standard della tua organizzazione.  Se questo non si è verificato, dovrai contattare l’Assistenza clienti Adobe per completare il provisioning di Campaign.

>[!CAUTION]
>
>I passaggi descritti di seguito devono essere eseguiti da un amministratore.

### Configurazione

Dovrai creare un nuovo progetto Adobe Developer e configurarlo per l’integrazione.

#### Crea un nuovo progetto

A questo scopo, segui la procedura indicata di seguito:

1. Accedi a [Console Adobe Developer](https://console.adobe.io/home#) e seleziona il tuo ID organizzazione Adobe dal menu a discesa in alto a destra dello schermo.

1. Quindi fai clic su **[!UICONTROL Create new project]** in **[!UICONTROL Quick Start]**.

   ![](assets/adobeIO1.png)

1. Sotto **[!UICONTROL Get started with your new project]**, fai clic su **[!UICONTROL Add API]**.

   ![](assets/adobeIO2.png)

1. Seleziona Adobe Campaign e fai clic su **[!UICONTROL Next]**.

   ![](assets/adobeIO3.png)

1. Nella schermata successiva è disponibile l’opzione per scegliere il tipo di autenticazione. È possibile scegliere OAuth Server-to-Server o Account di servizio (JWT). Tieni presente che le credenziali dell’account di servizio (JWT) non sono più consigliate per i nuovi progetti e sono state dichiarate obsolete a favore delle nuove credenziali server-to-server OAuth. Le istruzioni fornite in questa guida si applicano solo all’autenticazione server-to-server di OAuth.

   ![](assets/adobeIO4.png)

1. Nella schermata successiva seleziona i profili di prodotto da associare a questo progetto. Seleziona il profilo di prodotto che contiene nel titolo: ID tenant dell’istanza Campaign - [!UICONTROL Administrators]

   Esempio: Campaign Standard - your-campaign-tenantID - Administrators

1. Fai clic su **[!UICONTROL Save configured API]**.

   ![](assets/adobeIO5.png)

1. Nella schermata successiva vengono visualizzati i dettagli del nuovo progetto Adobe Developer. Clic **[!UICONTROL Add to Project]** in alto a sinistra sullo schermo e seleziona **API** dal menu a discesa.

   ![](assets/adobeIO6.png)

1. Nella schermata successiva è necessario selezionare l’API I/O Events API, quindi fare clic su **[!UICONTROL Next]**.

1. Nella schermata successiva fai clic su **[!UICONTROL Save the configured API]**.  Verrai riportato alla schermata dei dettagli del progetto.

1. Ora fai clic su **[!UICONTROL Add to Project]** in alto a sinistra sullo schermo e seleziona **API** dal menu a discesa, come in precedenza.

1. Nella schermata successiva è necessario selezionare l&#39;API di gestione I/O e fare clic su **[!UICONTROL Next]**.

1. Nella schermata successiva fai clic su **[!UICONTROL Save the configured API]**.

L’impostazione di pre-integrazione in Campaign è ora completa.

**Argomenti correlati**

* [Configurare l’integrazione di Adobe Developer per Microsoft Dynamics 365](../../integrating/using/d365-acs-configure-adobe-io.md) è il passaggio successivo nella configurazione dell’integrazione
* [Panoramica dell&#39;applicazione self-service di integrazione](../../integrating/using/d365-acs-self-service-app-quick-start-guide.md) contiene l’elenco completo dei passaggi necessari per rendere operativa l’integrazione.
* [Adobe Developer - Integrazione dell’account del servizio](https://developer.adobe.com/developer-console/docs/guides/#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)
* [Campaign Standard - Configurazione dell’accesso API](../../api/using/setting-up-api-access.md)
* [Integrazione Campaign Standard - Dynamics 365](../../integrating/using/d365-acs-configure-d365.md)
* [Migrazione delle credenziali da JWT a OAuth Server-to-Server](../../integrating/using/d365-acs-self-service-app-migrate-credentials.md) contiene i passaggi per migrare le credenziali da JWT a OAuth Server-to-Server.
