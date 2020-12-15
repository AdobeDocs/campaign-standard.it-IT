---
solution: Campaign Standard
product: campaign
title: Definizione dell’oggetto e del mittente di un messaggio e-mail
description: Scoprite come definire l'oggetto e il mittente di un'e-mail in Designer e-mail.
audience: designing
content-type: reference
topic-tags: editing-email-content
translation-type: tm+mt
source-git-commit: 1e7359db2de1a9c420af33ac85c0597c098ae3f8
workflow-type: tm+mt
source-wordcount: '338'
ht-degree: 3%

---


# Definizione dell&#39;oggetto e del mittente di un&#39;e-mail{#defining-the-subject-line-of-an-email}

## Definizione dell&#39;oggetto di un&#39;e-mail {#subject-line}

L&#39;oggetto del messaggio è obbligatorio per preparare e inviare il messaggio.

>[!NOTE]
>
>Se l&#39;oggetto è vuoto, viene visualizzato un avviso nel dashboard dei messaggi e in Designer e-mail.

1. Creare un messaggio e-mail.
1. Passare alla scheda **[!UICONTROL Properties]** della home page di Email Designer (accessibile tramite l&#39;icona principale).
1. Compila la sezione **[!UICONTROL Subject]**.

   ![](assets/email_designer_subject.png)

1. Puoi anche aggiungere campi di personalizzazione, blocchi di contenuto e contenuti dinamici alla riga dell’oggetto facendo clic sulle icone corrispondenti. Per ulteriori informazioni, vedere [Personalizzazione](../../designing/using/personalization.md).

## Definizione del mittente e-mail di un&#39;e-mail {#email-sender}

Per definire il nome del mittente che verrà visualizzato nell&#39;intestazione dei messaggi inviati, passare alla scheda **[!UICONTROL Properties]** della home page di Designer e-mail (accessibile tramite l&#39;icona principale).

![](assets/delivery_content_edition16.png)

* Il campo **[!UICONTROL From: name]** consente di inserire il nome del mittente. Per impostazione predefinita, il blocco predefinito **Nome mittente** viene immesso automaticamente nel campo. L&#39;indirizzo e-mail e il nome del mittente predefiniti sono definiti in **[!UICONTROL Brands]** accessibili tramite il logo Adobe Campaign  nel menu avanzato **[!UICONTROL Administration > Instance settings > Brand configuration]**.

   Per modificare il nome del mittente, fai clic sul blocco **Nome mittente**. Il campo diventa quindi modificabile ed è possibile immettere il nome che si desidera utilizzare.

   Questo campo può essere personalizzato. A tal fine, puoi aggiungere campi di personalizzazione, blocchi di contenuto e contenuti dinamici facendo clic sulle icone sotto il nome del mittente. Per ulteriori informazioni, vedere [Personalizzazione](../../designing/using/personalization.md).

* Impossibile modificare il campo **[!UICONTROL From: email address]** da questa sezione. Potete modificarlo modificando le proprietà dell’e-mail dal relativo dashboard. Per ulteriori informazioni, vedere [Elenco dei parametri avanzati per le e-mail](../../administration/using/configuring-email-channel.md#advanced-parameters).

>[!NOTE]
>
>I parametri dell&#39;intestazione non devono essere vuoti. L&#39;indirizzo del mittente è obbligatorio per consentire l&#39;invio di un&#39;e-mail (standard RFC).  Adobe Campaign controlla la sintassi degli indirizzi e-mail immessi.

**Argomenti correlati:**

* [Inserimento di un campo di personalizzazione](../../designing/using/personalization.md#inserting-a-personalization-field)
* [Aggiunta di un blocco di contenuto](../../designing/using/personalization.md#adding-a-content-block)
* [Definizione di contenuto dinamico in un messaggio e-mail](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)
