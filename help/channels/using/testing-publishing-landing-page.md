---
title: Condivisione di una pagina di destinazione
description: Scopri come verificare e pubblicare una pagina di destinazione in Adobe Campaign.
page-status-flag: never-activated
uuid: fb7b087a-3292-496c-bc41-2e3012bacf59
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: landing-pages
discoiquuid: f7d4bb71-f957-4f86-97c7-8ac0a0030026
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '383'
ht-degree: 100%

---


# Verifica e pubblicazione di una pagina di destinazione{#testing-publishing--landing-page}

## Informazioni sulla pubblicazione di pagine di destinazione {#about-landing-page-publication}

Prima di pubblicare una pagina di destinazione, devi eseguire i test: convalida l’esecuzione, configura l’accesso e imposta la fine del ciclo di vita della pagina di destinazione. Questi passaggi sono prerequisiti e devono essere eseguiti con cautela.

## Verifica della pagina di destinazione {#testing-the-landing-page-}

Poiché la pagina di destinazione ha un impatto sulla piattaforma e sui dati, devi verificarne accuratamente l’esecuzione. Per eseguire questa operazione:

1. Fai clic sul pulsante **[!UICONTROL Test]** nella barra delle azioni della pagina di destinazione.
1. Dalla schermata di test, seleziona un profilo di test e un relativo servizio se la pagina di destinazione serve a gestire gli abbonamenti.

   ![](assets/lp_test_2.png)

1. Immetti i dati nei campi e seleziona le opzioni.
1. Invia la pagina di destinazione e controlla gli aggiornamenti nel database.

   >[!IMPORTANT]
   >
   >Dopo aver inviato il modulo, vengono aggiornati il servizio e il profilo utilizzati.

1. Ripeti questa operazione con vari profili e dati.

Inoltre puoi generare la miniatura della pagina di destinazione da questa schermata.

>[!NOTE]
>
>Per visualizzare l’anteprima della pagina di destinazione nell’interfaccia utente di Campaign, l’URL del server dell’applicazione deve essere sicuro. In questo caso, utilizza https:// anziché http:// per impostare questo URL al momento della [configurazione del brand](../../administration/using/branding.md#configuring-and-using-brands).

## Impostazione di parametri di validità {#setting-up-validity-parameters}

Prima della pubblicazione, per motivi di sicurezza e legati alle prestazioni della piattaforma, ti consigliamo vivamente di impostare una data di scadenza nelle proprietà della pagina di destinazione. Alla data selezionata, la pubblicazione della pagina di destinazione viene automaticamente annullata. Per eseguire questa operazione:

1. Modifica le proprietà della pagina di destinazione accessibile tramite il pulsante ![](assets/edit_darkgrey-24px.png) nel dashboard di questa pagina.

   ![](assets/lp_edit_properties_button.png)

1. Imposta data e ora di scadenza nella sezione **[!UICONTROL Publication]**: la pubblicazione della pagina di destinazione viene automaticamente annullata alla data specificata e non è più disponibile.

   Puoi selezionare il fuso orario da considerare per questa data e ora.

1. Definisci un URL di reindirizzamento per reindirizzare i visitatori quando tentano di accedere a una pagina di destinazione non attiva.

   ![](assets/lp_settings_general.png)

>[!IMPORTANT]
>
>Puoi inoltre definire una data e un’ora di distribuzione: la pagina di destinazione viene quindi pubblicata automaticamente alla data specificata.

## Pubblicazione di una pagina di destinazione {#publishing-a-landing-page}

Quando pubblichi una pagina di destinazione, diventa disponibile live e accessibile ai visitatori.

Puoi annullare o aggiornare la pubblicazione e ripubblicare la pagina di destinazione in qualsiasi momento tramite il pulsante **[!UICONTROL Publish]**. Tuttavia, se la ripubblicazione non va a buon fine e non viene annullata la pubblicazione della pagina di destinazione, la prima versione rimane online.
