---
title: Passaggi principali per impostare una pagina di destinazione
seo-title: Passaggi principali per impostare una pagina di destinazione
description: Passaggi principali per impostare una pagina di destinazione
seo-description: Scopri i passaggi principali per impostare una pagina di destinazione
page-status-flag: mai attivato
uuid: b316bf47-7d98-46fa-ab4f-67ff50de8095
contentOwner: lemaite
products: SG_CAMPAIGN/STANDARD
audience: canali
content-type: reference
topic-tags: landing page
discoiquuid: ca8d1698-6e8a-4f5a-b017-74a152e14286
context-tags: landingPage,procedura guidata;landingPage,panoramica;landingPage,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 1f100f6b041c6dbb298113b4ecc7830951714131

---


# Passaggi principali per impostare una pagina di destinazione {#main-steps-create-a-landing-page}

## Informazioni sulla creazione di pagine di destinazione

I passaggi principali per impostare le pagine di destinazione sono i seguenti:

![](assets/lp_steps.png)

In questa pagina troverete informazioni su ciascuno di questi passaggi, oltre a riferimenti alla documentazione dedicata per ulteriori dettagli.

## Configurare il modello della pagina di destinazione {#configure-the-landing-page-template}

Prima di impostare una pagina di destinazione, il primo passaggio consiste nel configurare un modello di pagina di destinazione che corrisponda alle vostre esigenze. Una volta pronto il modello, tutte le pagine di destinazione basate su di esso saranno preconfigurate con i parametri desiderati.

1. Dal menu avanzato, tramite il logo Adobe Campaign, selezionate **[!UICONTROL Resources]** / **[!UICONTROL Templates]** / **[!UICONTROL Landing page templates]**, quindi duplicate il modello da utilizzare.
1. Nelle proprietà del modello, specificate tutti i parametri che le pagine di destinazione devono avere in comune. Ad esempio: la dimensione di targeting, i parametri di accesso alla pagina per i visitatori identificati o non identificati, le azioni specifiche per la convalida del modulo da parte di un visitatore, il marchio/logo da utilizzare nel contenuto, ecc.
1. Salva le modifiche.

Per ulteriori informazioni sui modelli delle pagine di destinazione, consulta [questa sezione](../../channels/using/about-landing-pages.md).

![](assets/lp-steps1.png)

## Creare e configurare la pagina di destinazione {#create-and-configure-the-landing-page}

Dal modello definito nel passaggio precedente, crea una nuova pagina di destinazione in un programma o in una campagna.

1. Create la pagina di destinazione in base al modello desiderato.
1. Immettete i parametri generali della pagina di destinazione (etichetta, descrizione, ecc.).
1. Potrete quindi accedere al dashboard della pagina di destinazione. Se necessario, modificate le proprietà della pagina di destinazione. Per impostazione predefinita, le proprietà sono quelle configurate nel modello della pagina di destinazione.
Per motivi di sicurezza e prestazioni della piattaforma, si consiglia di impostare una data di scadenza nelle proprietà della pagina di destinazione. Al termine, la pagina di destinazione verrà automaticamente annullata nella data selezionata. For more on validity parameters, refer to [this section](../../channels/using/sharing-a-landing-page.md#setting-up-validity-parameters).

   ![](assets/lp-steps3.png)

   >[!NOTE]
   >
   >Le modifiche apportate sono valide solo per la pagina di destinazione in fase di modifica. Se desiderate applicare queste modifiche ad altre pagine di destinazione, potete eseguirle in un modello dedicato e quindi creare altre pagine di destinazione da tale modello.

## Progettare la pagina di destinazione {#design-the-landing-page}

È ora possibile definire il contenuto della pagina di destinazione. Per impostazione predefinita, la pagina di destinazione contiene tre pagine a cui è possibile accedere mediante le frecce di scorrimento: la pagina del contenuto principale, una pagina di conferma e una pagina di errore.

![](assets/lp-steps4.png)

Per impostazione predefinita in ogni pagina sono configurati più campi. Se necessario, potete modificarne le proprietà e la mappatura.

Puoi anche configurare il comportamento del pulsante di conferma quando un profilo fa clic su di esso e personalizzare il contenuto in base alle tue esigenze (immagine, campi di personalizzazione, ecc.). Ad esempio, potete inserire il nome di un profilo nella pagina di conferma della pagina di destinazione, per ringraziarlo della registrazione.

Per ulteriori informazioni sulla progettazione della pagina di destinazione, consultate [questa sezione](../../channels/using/designing-a-landing-page.md).

## Verificare la pagina di destinazione {#test-the-landing-page}

Una volta definita la pagina di destinazione, potete simulare il modo in cui verrà eseguita e il funzionamento quando sarà disponibile online.

![](assets/lp-steps5.png)

>[!CAUTION]
>
>I test della pagina di destinazione possono essere eseguiti solo con profili e non con profili di test. Quando il modulo viene inviato, i dati del profilo selezionato vengono aggiornati in termini reali. Per evitare di modificare i profili reali, usate un profilo cliente falso.

Se siete soddisfatti del comportamento della pagina di destinazione, potete pubblicarla per renderla disponibile online.

Per ulteriori informazioni su come testare una pagina di destinazione, consulta [questa sezione](../../channels/using/sharing-a-landing-page.md#testing-the-landing-page-).

## Pubblicare la pagina di destinazione {#publish-the-landing-page}

Una volta completati i test, potete pubblicare la pagina di destinazione utilizzando il **[!UICONTROL Publish]** pulsante della barra delle azioni nel dashboard. Un blocco di monitoraggio mostra l’avanzamento e lo stato della pubblicazione.

Quando si pubblica una pagina di destinazione, questa diventa accessibile online. Dopo la pubblicazione, potete sempre aggiornarla: a questo scopo, è necessario ripubblicarlo dopo ogni modifica. Potete inoltre annullare la pubblicazione di una pagina di destinazione in qualsiasi momento in modo che non sia più disponibile.

![](assets/lp-steps6.png)

Una volta pubblicata, la pagina di destinazione è pronta per essere utilizzata. Potete quindi mettere in atto diversi meccanismi che vi consentano di accedervi per acquisire nuovi profili nel database o per ottenere ulteriori informazioni sui profili esistenti.

Per ulteriori informazioni sulla pubblicazione della pagina di destinazione, consulta [questa sezione](../../channels/using/sharing-a-landing-page.md#publishing-a-landing-page).
