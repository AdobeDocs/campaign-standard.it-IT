---
title: Condivisione di una pagina di destinazione
seo-title: Condivisione di una pagina di destinazione
description: Condivisione di una pagina di destinazione
seo-description: Scopri come testare e pubblicare una pagina di destinazione in Adobe Campaign.
page-status-flag: never-activated
uuid: fb 7 b 087 a -3292-496 c-bc 41-2 e 3012 bacf 59
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: canali
content-type: riferimento
topic-tags: landing-pages
discoiquuid: f 7 d 4 bb 71-f 957-4 f 86-97 c 7-8 ac 0 a 0030026
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Sharing a landing page{#sharing-a-landing-page}

## About landing page publication {#about-landing-page-publication}

Prima di pubblicare una pagina di destinazione, è necessario eseguire i test: convalidare l'esecuzione, configurare l'accesso e impostare la fine della pagina di destinazione. Questi passaggi sono prerequisiti e devono essere eseguiti con cautela.

## Testing the landing page {#testing-the-landing-page-}

Poiché la pagina di destinazione inciderà sulla piattaforma e i dati, è necessario testarne attentamente l'esecuzione. A tal fine:

1. Click the **[!UICONTROL Test]** button in the action bar of the landing page.
1. Dalla schermata di prova, selezionate un profilo di prova e un servizio di prova se la pagina di destinazione deve gestire le iscrizioni.

   ![](assets/lp_test_2.png)

1. Immettete i dati nei campi e selezionate le opzioni.
1. Inviate la pagina di destinazione e verificate gli aggiornamenti nel database.

   >[!CAUTION]
   >
   >Quando il modulo viene inviato, il servizio e il profilo utilizzati vengono aggiornati.

1. Ripetete questa procedura con vari profili e dati.

   Potete anche generare la miniatura della pagina di destinazione da questa schermata.

## Setting up validity parameters {#setting-up-validity-parameters}

Prima di pubblicare, per motivi di sicurezza e prestazioni della piattaforma, consigliamo vivamente di impostare una data di scadenza nelle proprietà della pagina di destinazione. Nella data selezionata, la pagina di destinazione viene automaticamente annullata. A tal fine:

1. Edit the landing page properties accessed via the ![](assets/edit_darkgrey-24px.png) button in the landing page dashboard.

   ![](assets/lp_edit_properties_button.png)

1. Set up expiration date and time in the **[!UICONTROL Publication]** section: the landing page will automatically be unpublished on the specified date and therefore no longer be available.

   Potete selezionare il fuso orario da considerare per la data e l'ora indicate.

1. Definite un URL di reindirizzamento per reindirizzare i visitatori verso una pagina di destinazione non attiva.

   ![](assets/lp_settings_general.png)

>[!CAUTION]
>
>Potete inoltre definire una data e un'ora di distribuzione: la pagina di destinazione verrà pubblicata automaticamente nella data specificata.

## Publishing a landing page {#publishing-a-landing-page}

Quando pubblicate una pagina di destinazione, questa diventa attiva e accessibile dai visitatori.

You can unpublish or update and republish your landing page at any time, via the **[!UICONTROL Publish]** button. Tuttavia, se la pubblicazione non riesce e non avete ancora pubblicato la pagina di destinazione, la prima versione resterà online.
