---
title: Condivisione di una pagina di destinazione
description: Scopri come testare e pubblicare una pagina di destinazione in Adobe Campaign.
page-status-flag: never-activated
uuid: fb7b087a-3292-496c-bc41-2e3012bacf59
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: landing-pages
discoiquuid: f7d4bb71-f957-4f86-97c7-8ac0a0030026
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 54612511de07edc3e6f3eea34ef095c26b35f4af

---


# Verifica e pubblicazione di una pagina di destinazione{#testing-publishing--landing-page}

## Informazioni sulla pubblicazione della pagina di destinazione {#about-landing-page-publication}

Prima di pubblicare una pagina di destinazione, è necessario eseguire i test: convalidare l’esecuzione, configurare l’accesso e impostare la fine del ciclo di vita della pagina di destinazione. Questi passaggi sono prerequisiti e devono essere eseguiti con cautela.

## Verifica della pagina di destinazione {#testing-the-landing-page-}

Poiché la pagina di destinazione avrà un impatto sulla piattaforma e sui dati, è necessario verificarne accuratamente l’esecuzione. Per eseguire questa operazione:

1. Fate clic sul **[!UICONTROL Test]** pulsante nella barra delle azioni della pagina di destinazione.
1. Dalla schermata di test, selezionate un profilo di test e un servizio di test se la pagina di destinazione è destinata a gestire le iscrizioni.

   ![](assets/lp_test_2.png)

1. Immettete i dati nei campi e selezionate le opzioni.
1. Inviate la pagina di destinazione e controllate gli aggiornamenti nel database.

   >[!IMPORTANT]
   >
   >Quando il modulo viene inviato, vengono aggiornati il servizio e il profilo utilizzati.

1. Ripetete questa operazione con vari profili e dati.

   È inoltre possibile generare la miniatura della pagina di destinazione da questa schermata.

>[!NOTE]
>
>Per visualizzare l&#39;anteprima della pagina di destinazione nell&#39;interfaccia utente di Campaign, l&#39;URL del server dell&#39;applicazione deve essere protetto. In tal caso, utilizzate https:// anziché http:// per impostare questo URL al momento della [configurazione del marchio](../../administration/using/branding.md#configuring-and-using-brands).

## Impostazione dei parametri di validità {#setting-up-validity-parameters}

Prima della pubblicazione, per motivi di sicurezza e per prestazioni della piattaforma, si consiglia di impostare una data di scadenza nelle proprietà della pagina di destinazione. Nella data selezionata, la pagina di destinazione viene automaticamente annullata la pubblicazione. Per eseguire questa operazione:

1. Modificate le proprietà della pagina di destinazione a cui accedete tramite il ![](assets/edit_darkgrey-24px.png) pulsante nel dashboard della pagina di destinazione.

   ![](assets/lp_edit_properties_button.png)

1. Imposta data e ora di scadenza nella **[!UICONTROL Publication]** sezione: la pagina di destinazione verrà automaticamente annullata la pubblicazione alla data specificata e non sarà più disponibile.

   Puoi selezionare il fuso orario da prendere in considerazione per questa data e ora.

1. Definite un URL di reindirizzamento per reindirizzare i visitatori quando tentano di accedere a una pagina di destinazione non attiva.

   ![](assets/lp_settings_general.png)

>[!IMPORTANT]
>
>Potete inoltre definire una data e un&#39;ora di distribuzione: la pagina di destinazione verrà quindi pubblicata automaticamente alla data specificata.

## Pubblicazione di una pagina di destinazione {#publishing-a-landing-page}

Quando pubblicate una pagina di destinazione, questa viene pubblicata dal vivo ed è accessibile dai visitatori.

Potete annullare la pubblicazione o aggiornare e ripubblicare la pagina di destinazione in qualsiasi momento, tramite il **[!UICONTROL Publish]** pulsante . Tuttavia, se la ripubblicazione non riesce e la pagina di destinazione non è ancora stata annullata, la prima versione rimarrà online.
