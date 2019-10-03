---
title: Defining the subject line and the sender of an email
seo-title: Defining the subject line and the sender of an email
description: Defining the subject line and the sender of an email
seo-description: Discover how to define the subject line and the sender of an email in the Email Designer.
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
source-git-commit: 5847c89b97ede8b03e75d1d90f31c88ed5c8a84e

---


# Defining the subject line and the sender of an email{#defining-the-subject-line-of-an-email}

The message subject is mandatory to prepare and send the message.

>[!NOTE]
>
>Se l'oggetto è vuoto, viene visualizzato un avviso nel dashboard dei messaggi e in Designer e-mail.

Per configurare l'oggetto dell'e-mail, passare alla **[!UICONTROL Properties]** scheda della home page di Designer e-mail (accessibile tramite l'icona principale) e compilare la **[!UICONTROL Subject]** sezione.

**Per definire l’oggetto di un messaggio e-mail**:

1. Create un messaggio e-mail.
1. Chiudi la homepage.
1. Passare alla **[!UICONTROL Properties]** scheda della home page di Designer e-mail (accessibile tramite l'icona principale) e compilare la **[!UICONTROL Subject]** sezione.

![](assets/email_designer_subject.png)

Puoi anche aggiungere campi di personalizzazione, blocchi di contenuto e contenuti dinamici alla riga dell’oggetto facendo clic sulle icone corrispondenti.

**Argomenti correlati:**

* [Inserimento di un campo di personalizzazione](../../designing/using/personalization.md#inserting-a-personalization-field)
* [Aggiunta di un blocco di contenuto](../../designing/using/personalization.md#adding-a-content-block)
* [Definizione di contenuto dinamico in un messaggio e-mail](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)

## Predictive subject line {#predictive-subject-line}

Quando modificate un’e-mail, potete provare diverse righe di oggetto e ottenere una stima del tasso di apertura prima di inviarla.

Questa funzione è disattivata per impostazione predefinita. Viene attivata quando viene importato il primo modello. Un modello è il risultato di set di dati di formazione specifici per un determinato settore. I modelli consentono al sistema di prevedere la frequenza di apertura dell'e-mail quando viene inviata una nuova riga oggetto.

>[!NOTE]
>
>Questa funzione è disponibile per i messaggi e-mail e per i database che contengono solo contenuti in lingua inglese. Il modello preparato non sarà coerente e porterà a risultati errati se l'istanza contiene e-mail in altre lingue. L'opzione che consente di testare un oggetto è visibile solo se un modello è già disponibile nell'istanza.

**Argomento correlato**

* [Verifica dell’oggetto di un messaggio e-mail](../../sending/using/testing-subject-line-email.md)

## Mittente e-mail {#email-sender}

Per definire il nome del mittente che verrà visualizzato nell'intestazione dei messaggi inviati, passare alla **[!UICONTROL Properties]** scheda della home page di Designer e-mail (accessibile tramite l'icona principale).

![](assets/delivery_content_edition16.png)

* Il **[!UICONTROL From: name]** campo consente di inserire il nome del mittente. Per impostazione predefinita, nel campo viene inserito automaticamente il blocco **Nome** mittente predefinito. Adobe Campaign refers to the email channel configuration (from the advanced menu  via the Adobe Campaign logo) to designate this sender.**[!UICONTROL Administration > Channels > Email > Email accounts]**

   You can change the sender name by clicking the Sender name block. **** The field then becomes editable and you can enter the name you would like to use.

   This field can be personalized. To do this, you can add personalization fields, content blocks and dynamic content by clicking the icons below the sender name.

* The  field cannot be edited from this section. **[!UICONTROL From: email address]** You can change it by editing the properties of the email from its dashboard. For more information, see List of email advanced parameters.[](../../administration/using/configuring-email-channel.md#advanced-parameters)

>[!NOTE]
>
>The header parameters must not be empty. The sender's address is mandatory to allow an email to be sent (RFC standard). Adobe Campaign checks the syntax of email addresses entered.

**Argomenti correlati:**

* [Inserimento di un campo di personalizzazione](../../designing/using/personalization.md#inserting-a-personalization-field)
* [Aggiunta di un blocco di contenuto](../../designing/using/personalization.md#adding-a-content-block)
* [Definizione di contenuto dinamico in un messaggio e-mail](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)
