---
title: Guida introduttiva alle API di Campaign Standard
description: Crea integrazioni e costruisci il tuo ecosistema interfacciando Campaign con un pannello di tecnologie.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
old-role: Data Architect
role: Developer
level: Experienced
exl-id: c6968252-a012-4029-bbb8-66f4f693e99b
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: b12f6872-9271-4369-85e5-86969a0b99a2
    internal-label: APIs
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '247'
ht-degree: 100%
---
# Introduzione alle API di Campaign Standard {#get-started-apis}

Le API di Campaign Standard mirano a **creare integrazioni** per Adobe Campaign Standard e a **creare il proprio ecosistema** interfacciando Adobe Campaign Standard con il pannello di tecnologie utilizzato.

Con le API di Adobe Campaign Standard puoi accedere alle seguenti funzionalità:

<table style="table-layout:fixed; margin-top: 0px; margin-bottom: 0px;">
<tbody><tr style="border: 0;background-color: #FFFFFF;">
<td valign="top"><a href="../../api/using/retrieving-profiles.md"><img width="50px" alt="condizioni" src="assets/icon_profile.svg"/></a><p><a href="../../api/using/retrieving-profiles.md">Profili</a></p></td>
<td valign="top"><a href="../../api/using/creating-a-service.md"><img width="50px" alt="condizioni" src="assets/icon_services.svg"/></a><p><a href="../../api/using/creating-a-service.md">Servizi e sottoscrizioni</a></p></td>
<td valign="top"><a href="../../api/using/interacting-with-custom-resources.md"><img width="50px" alt="condizioni" src="assets/icon_customresources.svg"/></a><p><a href="../../api/using/interacting-with-custom-resources.md">Risorse personalizzate</a></p></td>
<td valign="top"><a href="../../api/using/interacting-with-marketing-history.md"><img width="50px" alt="condizioni" src="assets/icon_marketinghistory.svg"/></a><p><a href="../../api/using/interacting-with-marketing-history.md">Storico dei dati marketing</a></p></td>
</tr>
<tr style="border: 0;background-color: #FFFFFF;">
<td valign="top"><a href="../../api/using/creating-a-privacy-request.md"><img width="50px" alt="condizioni" src="assets/icon_privacy.svg"/></a><p><a href="../../api/using/creating-a-privacy-request.md">Gestione della privacy</a></p></td>
<td valign="top"><a href="../../api/using/managing-transactional-messages.md"><img width="50px" alt="condizioni" src="assets/icon_transactionalmessage.svg"/></a><p><a href="../../api/using/managing-transactional-messages.md">Messaggi transazionali</a></p></td>
<td valign="top"><a href="../../api/using/controlling-a-workflow.md"><img width="50px" alt="condizioni" src="assets/icon_workflows.svg"/></a><p><a href="../../api/using/controlling-a-workflow.md">Flussi di lavoro</a></p></td>
<td valign="top"><a href="../../api/using/retrieving-an-organizational-unit.md"><img width="50px" alt="condizioni" src="assets/icon_units.svg"/></a><p><a href="../../api/using/retrieving-an-organizational-unit.md">Unità organizzative</a></p></td>
</tr></tbody></table>

>[!NOTE]
>
>Prima di eseguire le chiamate API, controlla le limitazioni delle dimensioni che corrispondono al contratto di licenza. Per ulteriori informazioni, consulta [questa pagina](https://helpx.adobe.com/it/legal/product-descriptions/campaign-standard.html#ITInfrastructureResourcesbyActiveProfilesTiers).

Per utilizzare l’API di Campaign Standard, è necessario un account I/O Adobe. Questo passaggio è obbligatorio per andare avanti e scoprire le funzionalità API.
Per ulteriori informazioni al riguardo, consulta [questa sezione](../../api/using/setting-up-api-access.md).

Le API fornite sfruttano **concetti standard** con un’interfaccia REST e payload JSON.

>[!NOTE]
>
>Tutti gli esempi funzionano con Postman, ma puoi usare il client REST che preferisci.

Questa documentazione contiene la descrizione approfondita di tutti gli endpoint con le nozioni generali da conoscere per la manipolazione dell’API, il riferimento API completo, gli esempi di codice e le guide di avvio rapido.

Se qualcosa dovesse mancare o sembrare sbagliato, chiedi nella [community](https://experienceleaguecommunities.adobe.com/it/t5/adobe-campaign-standard/ct-p/adobe-campaign-standard-community).
