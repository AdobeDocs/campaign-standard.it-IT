---
title: Personalizzazione del mittente
seo-title: Personalizzazione del mittente
description: Personalizzazione del mittente
seo-description: Scopri come personalizzare il nome o l'indirizzo del mittente per i tuoi messaggi.
page-status-flag: never-activated
uuid: 7 aa 08 d 5 d -9 e 6 c -4 dac-bff 8-6 fde 85368 c 2 d
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: progettazione
content-type: riferimento
topic-tags: personalizzazione del contenuto
discoiquuid: 49532 f 6 b -3 cd 0-4 d 03-932 e-bcb 7 d 05 c 74 d 4
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Personalizing the sender{#personalizing-the-sender}

## Email sender {#email-sender}

To define the name of the sender which will appear in the header of messages sent, go the **[!UICONTROL Properties]** tab of the Email Designer home page (accessible through the home icon).

![](assets/delivery_content_edition16.png)

* **[!UICONTROL From: name]** Il campo consente di inserire il nome del mittente. By default, the default **Sender name** block is automatically entered in the field. Adobe Campaign refers to the email channel configuration (from the advanced menu **[!UICONTROL Administration > Channels > Email > Email accounts]** via the Adobe Campaign logo) to designate this sender.

   You can change the sender name by clicking the **Sender name** block. Il campo diventa modificabile e potete immettere il nome da utilizzare.

   Questo campo può essere personalizzato. A tal fine, puoi aggiungere campi personalizzati, blocchi di contenuto e contenuti dinamici facendo clic sulle icone sotto il nome del mittente.

* The **[!UICONTROL From: email address]** field cannot be edited from this section. Potete modificarlo modificando le proprietà dell'e-mail dal dashboard. For more on this, see [List of email advanced parameters](../../administration/using/configuring-email-channel.md#advanced-parameters).

>[!NOTE]
>
>I parametri dell'intestazione non devono essere vuoti. L'indirizzo del mittente è obbligatorio per consentire l'invio di un messaggio e-mail (standard RFC). Adobe Campaign verifica la sintassi degli indirizzi e-mail immessi.

**Argomenti correlati:**

* [Inserimento di un campo personalizzato](../../designing/using/inserting-a-personalization-field.md)
* [Aggiunta di un blocco di contenuto](../../designing/using/adding-a-content-block.md)
* [Definizione del contenuto dinamico in un'e-mail](../../designing/using/defining-dynamic-content-in-an-email.md)

## SMS sender {#sms-sender}

Potete personalizzare il nome del mittente SMS. For more on this, refer to the [SMS configuration](../../administration/using/configuring-sms-channel.md#configuring-sms-properties) section.
