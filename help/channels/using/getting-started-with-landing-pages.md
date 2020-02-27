---
title: Passaggi principali per impostare una pagina di destinazione
description: Scopri i passaggi principali per impostare una pagina di destinazione
page-status-flag: never-activated
uuid: b316bf47-7d98-46fa-ab4f-67ff50de8095
contentOwner: lemaitre
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: landing-pages
discoiquuid: ca8d1698-6e8a-4f5a-b017-74a152e14286
context-tags: landingPage,wizard;landingPage,overview;landingPage,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c71c207d724dac914935b3667527a3ce4403dd63

---


# Guida introduttiva alle pagine di destinazione {#getting-started-with-landing-pages}

## Informazioni sulle pagine di destinazione {#about-landing-pages}

Campaign viene fornito con pagine di destinazione, moduli Web che possono essere utilizzati per acquisire informazioni sui tipi di pubblico, offrire iscrizioni a un servizio, visualizzare i dati e ampliare il database. Le pagine di destinazione possono essere utilizzate anche per acquisire o aggiornare i profili esistenti.

Le pagine di destinazione possono essere utilizzate anche per impostare un meccanismo di doppio consenso, consentendo di proteggere la piattaforma da indirizzi e-mail o spambots errati o non validi. Per ulteriori informazioni, consulta il caso [di utilizzo](../../channels/using/setting-up-a-double-opt-in-process.md)dedicato.

I passaggi principali per impostare le pagine di destinazione sono i seguenti:

![](assets/lp_steps.png)

In questa pagina troverete informazioni su ciascuno di questi passaggi, oltre a riferimenti alla documentazione dedicata per ulteriori dettagli.

**Argomenti correlati:**

* [Video](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/communication-channels/landing-pages/landing-page-create-and-edit.html) sulla creazione di un’esercitazione sulla pagina di destinazione
* [Creazione di un servizio](../../audiences/using/creating-a-service.md)
* [Impostazione di un doppio processo di consenso](setting-up-a-double-opt-in-process.md)

## Limitazioni per la pagina di destinazione{#landing-page-limitations}

La sezione seguente elenca i limiti di cui dovreste essere consapevoli prima di iniziare a impostare le pagine di destinazione.

**Scrittura e aggiornamento dei dati**

* Le pagine di destinazione sono limitate solo a **[!UICONTROL Profile]** **[!UICONTROL Subscription]** risorse e risorse. La registrazione può essere salvata e aggiornata da **[!UICONTROL Profile]** e da una sottoscrizione o annullamento della sottoscrizione a un **[!UICONTROL Service]**.
Per ulteriori informazioni sulla configurazione delle risorse, vedere [Configurazione della struttura](../../developing/using/configuring-the-resource-s-data-structure.md)dati della risorsa.

>[!CAUTION]
>
>Una pagina di destinazione non può visualizzare o aggiornare i dati provenienti da altre risorse oltre a **[!UICONTROL Profile]** e **[!UICONTROL Subscription]**.

**Precaricamento**

* La pagina di destinazione non può visualizzare automaticamente un elenco di record, non può elencare i servizi a cui sono già stati sottoscritti profili. Per ulteriori informazioni sui servizi, consultare questa [pagina](../../audiences/using/creating-a-service.md).

* La pagina di destinazione con un modulo precompilato (i dati vengono precaricati con la pagina) è accessibile solo da un&#39;e-mail di Adobe Campaign. Non è possibile accedere a tale modulo da una pagina Web.

**Riconciliazione**

* Il comportamento di riconciliazione è il seguente: non appena viene trovata una partita, il processo di riconciliazione si interrompe. Ciò significa che la riconciliazione può essere fatta solo su un record di profilo e non su più record in presenza di duplicati.

Ad esempio, vuoi inviare la seguente pagina di destinazione di acquisizione ai tuoi profili per aggiornare il database Campaign con i numeri di cellulare dei tuoi profili.

![](assets/landing_page_limitation_1.png)

Se uno dei profili inserisce nuove informazioni nella pagina di destinazione ma presenta già un profilo duplicato, verrà aggiornato il profilo corrispondente alla data di creazione più recente, in quanto la priorità dei profili dipende solo dalla data di creazione.

Qui è stato aggiornato solo il primo profilo, perché si trattava della voce più vecchia.

![](assets/landing_page_limitation_2.png)

**Verifica delle pagine di destinazione**

* Le pagine di destinazione funzionano solo sui profili e non sui profili di prova, il che significa che non è possibile sottoporre a test le pagine di destinazione come parte di una prova e-mail.

## Passaggio 1 - Configurare il modello della pagina di destinazione {#configure-the-landing-page-template}

Prima di impostare una pagina di destinazione, il primo passaggio consiste nel configurare un modello di pagina di destinazione che corrisponda alle vostre esigenze. Una volta pronto il modello, tutte le pagine di destinazione basate su di esso saranno preconfigurate con i parametri desiderati.

1. Dal menu avanzato, tramite il logo Adobe Campaign, selezionate **[!UICONTROL Resources]** / **[!UICONTROL Templates]** / **[!UICONTROL Landing page templates]**, quindi duplicate il modello da utilizzare.
1. Nelle proprietà del modello, specificate tutti i parametri che le pagine di destinazione devono avere in comune. Ad esempio: la dimensione di targeting, i parametri di accesso alla pagina per i visitatori identificati o non identificati, le azioni specifiche per la convalida del modulo da parte di un visitatore, il marchio/logo da utilizzare nel contenuto, ecc. Per ulteriori informazioni sulle proprietà delle pagine di destinazione, consulta [questa sezione](../../channels/using/configuring-landing-page.md)
1. Salva le modifiche.

Per ulteriori informazioni sui modelli delle pagine di destinazione, consulta [questa sezione](../../channels/using/getting-started-with-landing-pages.md).

![](assets/lp-steps1.png)

## Passaggio 2 - Creare e configurare la pagina di destinazione {#create-and-configure-the-landing-page}

Dal modello definito nel passaggio precedente, crea una nuova pagina di destinazione in un programma o in una campagna.

1. Create la pagina di destinazione in base al modello desiderato.
1. Immettete i parametri generali della pagina di destinazione (etichetta, descrizione, ecc.).
1. Potrete quindi accedere al dashboard della pagina di destinazione. Se necessario, modificate le proprietà della pagina di destinazione (consultate [Configurazione di una pagina](../../channels/using/configuring-landing-page.md)di destinazione). Per impostazione predefinita, le proprietà sono quelle configurate nel modello della pagina di destinazione.
Per motivi di sicurezza e prestazioni della piattaforma, si consiglia di impostare una data di scadenza nelle proprietà della pagina di destinazione. Al termine, la pagina di destinazione verrà automaticamente annullata nella data selezionata. For more on validity parameters, refer to [this section](../../channels/using/testing-publishing-landing-page.md#setting-up-validity-parameters).

   ![](assets/lp-steps3.png)

   >[!NOTE]
   >
   >Le modifiche apportate sono valide solo per la pagina di destinazione in fase di modifica. Se desiderate applicare queste modifiche ad altre pagine di destinazione, potete eseguirle in un modello dedicato e quindi creare altre pagine di destinazione da tale modello.

## Passaggio 3 - Progettare la pagina di destinazione {#design-the-landing-page}

È ora possibile definire il contenuto della pagina di destinazione. Per impostazione predefinita, la pagina di destinazione contiene tre pagine a cui è possibile accedere mediante le frecce di scorrimento: la pagina del contenuto principale, una pagina di conferma e una pagina di errore.

![](assets/lp-steps4.png)

Per impostazione predefinita in ogni pagina sono configurati più campi. Se necessario, potete modificarne le proprietà e la mappatura.

Puoi anche configurare il comportamento del pulsante di conferma quando un profilo fa clic su di esso e personalizzare il contenuto in base alle tue esigenze (immagine, campi di personalizzazione, ecc.). Ad esempio, potete inserire il nome di un profilo nella pagina di conferma della pagina di destinazione, per ringraziarlo della registrazione.

Per ulteriori informazioni sulla progettazione della pagina di destinazione, consultate [questa sezione](../../channels/using/designing-a-landing-page.md).

## Passaggio 4 - Test della pagina di destinazione {#test-the-landing-page}

Una volta definita la pagina di destinazione, potete simulare il modo in cui verrà eseguita e il funzionamento quando sarà disponibile online.

![](assets/lp-steps5.png)

>[!CAUTION]
>
>I test della pagina di destinazione possono essere eseguiti solo con profili e non con profili di test. Quando il modulo viene inviato, i dati del profilo selezionato vengono aggiornati in termini reali. Per evitare di modificare i profili reali, usate un profilo cliente falso.

Se siete soddisfatti del comportamento della pagina di destinazione, potete pubblicarla per renderla disponibile online.

Per ulteriori informazioni su come testare una pagina di destinazione, consulta [questa sezione](../../channels/using/testing-publishing-landing-page.md#testing-the-landing-page-).

## Passaggio 5 - Pubblicare la pagina di destinazione {#publish-the-landing-page}

Una volta completati i test, potete pubblicare la pagina di destinazione utilizzando il **[!UICONTROL Publish]** pulsante della barra delle azioni nel dashboard. Un blocco di monitoraggio mostra l’avanzamento e lo stato della pubblicazione.

Quando si pubblica una pagina di destinazione, questa diventa accessibile online. Dopo la pubblicazione, potete sempre aggiornarla: a questo scopo, è necessario ripubblicarlo dopo ogni modifica. Potete inoltre annullare la pubblicazione di una pagina di destinazione in qualsiasi momento in modo che non sia più disponibile.

![](assets/lp-steps6.png)

Una volta pubblicata, la pagina di destinazione è pronta per essere utilizzata. Potete quindi mettere in atto diversi meccanismi che vi consentano di accedervi per acquisire nuovi profili nel database o per ottenere ulteriori informazioni sui profili esistenti.

Per ulteriori informazioni sulla pubblicazione della pagina di destinazione, consulta [questa sezione](../../channels/using/testing-publishing-landing-page.md#publishing-a-landing-page).
