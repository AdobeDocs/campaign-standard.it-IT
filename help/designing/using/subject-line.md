---
title: Definizione dell’oggetto e del mittente di un messaggio e-mail
description: Scoprite come definire l'oggetto e il mittente di un'e-mail in Designer e-mail.
page-status-flag: never-activated
uuid: 571ffc01-6e41-4501-9094-2f812b041a10
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: designing
content-type: reference
topic-tags: editing-email-content
discoiquuid: 39b86fda-7766-4e5f-ab48-bcc536ab66b3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 6f89b420f0f98c13da1bfff8f9b1b29e015aef89

---


# Definizione dell’oggetto e del mittente di un messaggio e-mail{#defining-the-subject-line-of-an-email}

## Defining the subject line of an email {#subject-line}

L&#39;oggetto del messaggio è obbligatorio per preparare e inviare il messaggio.

>[!NOTE]
>
>Se l&#39;oggetto è vuoto, viene visualizzato un avviso nel dashboard dei messaggi e in Designer e-mail.

1. Create un messaggio e-mail.
1. Passare alla **[!UICONTROL Properties]** scheda della home page di Designer e-mail (accessibile tramite l&#39;icona principale).
1. Compila la **[!UICONTROL Subject]** sezione.

   ![](assets/email_designer_subject.png)

1. Puoi anche aggiungere campi di personalizzazione, blocchi di contenuto e contenuti dinamici alla riga dell’oggetto facendo clic sulle icone corrispondenti. Per ulteriori informazioni, consulta [Personalizzazione](../../designing/using/personalization.md).
1. Potete provare diverse righe oggetto per ottenere una stima del tasso di apertura dell’e-mail prima di inviarla. Per ulteriori informazioni, consultate [Verifica dell’oggetto di un messaggio e-mail](../../sending/using/testing-subject-line-email.md).

## Definizione del mittente e-mail di un messaggio e-mail {#email-sender}

Per definire il nome del mittente che verrà visualizzato nell&#39;intestazione dei messaggi inviati, passare alla **[!UICONTROL Properties]** scheda della home page di Designer e-mail (accessibile tramite l&#39;icona principale).

![](assets/delivery_content_edition16.png)

* Il **[!UICONTROL From: name]** campo consente di inserire il nome del mittente. Per impostazione predefinita, nel campo viene inserito automaticamente il blocco **Nome** mittente predefinito. L&#39;indirizzo e-mail e il nome del mittente predefiniti sono definiti in modo **[!UICONTROL Brands]** accessibile tramite il logo Adobe Campaign, nel menu avanzato **[!UICONTROL Administration > Instance settings > Brand configuration]** .

   Per modificare il nome del mittente, fai clic sul blocco del nome **del** mittente. Il campo diventa quindi modificabile ed è possibile immettere il nome che si desidera utilizzare.

   Questo campo può essere personalizzato. A tal fine, puoi aggiungere campi di personalizzazione, blocchi di contenuto e contenuti dinamici facendo clic sulle icone sotto il nome del mittente. Per ulteriori informazioni, consulta [Personalizzazione](../../designing/using/personalization.md).

* Impossibile modificare il **[!UICONTROL From: email address]** campo da questa sezione. Potete modificarlo modificando le proprietà dell’e-mail dal relativo dashboard. Per ulteriori informazioni, consultate [Elenco dei parametri](../../administration/using/configuring-email-channel.md#advanced-parameters)avanzati per le e-mail.

>[!NOTE]
>
>I parametri dell&#39;intestazione non devono essere vuoti. L&#39;indirizzo del mittente è obbligatorio per consentire l&#39;invio di un&#39;e-mail (standard RFC). Adobe Campaign controlla la sintassi degli indirizzi e-mail immessi.

**Argomenti correlati:**

* [Inserimento di un campo di personalizzazione](../../designing/using/personalization.md#inserting-a-personalization-field)
* [Aggiunta di un blocco di contenuto](../../designing/using/personalization.md#adding-a-content-block)
* [Definizione di contenuto dinamico in un messaggio e-mail](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)
