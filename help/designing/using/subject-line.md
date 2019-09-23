---
title: Definizione dell’oggetto e del mittente di un messaggio e-mail
seo-title: Definizione dell’oggetto e del mittente di un messaggio e-mail
description: Definizione dell’oggetto e del mittente di un messaggio e-mail
seo-description: Scoprite come definire l'oggetto e il mittente di un'e-mail in Designer e-mail.
page-status-flag: mai attivato
uuid: 571ffc01-6e41-4501-9094-2f812b041a10
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: progettazione
content-type: reference
topic-tags: editing-email-content
discoiquuid: 39b86fda-7766-4e5f-ab48-bcc536ab66b3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0cf4807fc3d617b0c5ca33705b6344d1f3994ab3

---


# Definizione dell’oggetto e del mittente di un messaggio e-mail{#defining-the-subject-line-of-an-email}

L'oggetto del messaggio è obbligatorio per preparare e inviare il messaggio.

>[!NOTE]
>
>Se l'oggetto è vuoto, viene visualizzato un avviso nel dashboard dei messaggi e in Designer e-mail.

Per configurare l'oggetto dell'e-mail, passare alla **[!UICONTROL Properties]** scheda della home page di Designer e-mail (accessibile tramite l'icona principale) e compilare la **[!UICONTROL Subject]** sezione.

**To define the subject line of an email**:

1. Create an email.
1. Close homepage.
1. Go the  tab of the Email Designer home page (accessible through the home icon) and fill in the  section.**[!UICONTROL Properties]****[!UICONTROL Subject]**

![](assets/email_designer_subject.png)

You can also add personalization fields, content blocks and dynamic content to the subject line by clicking the corresponding icons.

**Related topics:**

* [Inserting a personalization field](../../designing/using/personalization.md#inserting-a-personalization-field)
* [Adding a content block](../../designing/using/personalization.md#adding-a-content-block)
* [Defining dynamic content in an email](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)

## Predictive subject line {#predictive-subject-line}

When editing an email, you can try out different subject lines and get an estimation of its open rate before you send it.

This feature is disabled by default. It is enabled when the first model is imported. A model is the result of training data sets specific to a given industry. Models allow the system to predict the open rate of the email when a new subject line is submitted.

>[!NOTE]
>
>Questa funzione è disponibile per i messaggi e-mail e per i database che contengono solo contenuti in lingua inglese. Il modello preparato non sarà coerente e porterà a risultati errati se l'istanza contiene e-mail in altre lingue. L'opzione che consente di testare un oggetto è visibile solo se un modello è già disponibile nell'istanza.

**Argomento correlato**

* [Verifica di una riga oggetto](../../sending/using/testing-subject-line-email.md)

## Mittente e-mail {#email-sender}

Per definire il nome del mittente che verrà visualizzato nell'intestazione dei messaggi inviati, passare alla **[!UICONTROL Properties]** scheda della home page di Designer e-mail (accessibile tramite l'icona principale).

![](assets/delivery_content_edition16.png)

* Il **[!UICONTROL From: name]** campo consente di inserire il nome del mittente. Per impostazione predefinita, nel campo viene inserito automaticamente il blocco **Nome** mittente predefinito. Adobe Campaign fa riferimento alla configurazione del canale e-mail (dal menu avanzato **[!UICONTROL Administration > Channels > Email > Email accounts]** tramite il logo Adobe Campaign) per designare il mittente.

   Puoi cambiare il nome del mittente facendo clic sul blocco del nome **del** mittente. Il campo diventa quindi modificabile ed è possibile immettere il nome che si desidera utilizzare.

   Questo campo può essere personalizzato. A tal fine, puoi aggiungere campi di personalizzazione, blocchi di contenuto e contenuti dinamici facendo clic sulle icone sotto il nome del mittente.

* Impossibile modificare il **[!UICONTROL From: email address]** campo da questa sezione. Potete modificarlo modificandone le proprietà dal relativo dashboard. Per ulteriori informazioni, consultate [Elenco dei parametri](../../administration/using/configuring-email-channel.md#advanced-parameters)avanzati per le e-mail.

>[!NOTE]
>
>I parametri dell'intestazione non devono essere vuoti. L'indirizzo del mittente è obbligatorio per consentire l'invio di un'e-mail (standard RFC). Adobe Campaign controlla la sintassi degli indirizzi e-mail immessi.

**Argomenti correlati:**

* [Inserimento di un campo di personalizzazione](../../designing/using/personalization.md#inserting-a-personalization-field)
* [Aggiunta di un blocco di contenuto](../../designing/using/personalization.md#adding-a-content-block)
* [Definizione di contenuto dinamico in un messaggio e-mail](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)