---
title: Definizione del testo dinamico
description: Scopri come visualizzare dinamicamente testi diversi all’utente in base alle condizioni definite in Adobe Campaign.
audience: designing
content-type: reference
topic-tags: defining-conditional-content
feature: SMS
role: User
level: Beginner
exl-id: 649e3428-a3bf-470f-923c-04d9a57a208f
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '213'
ht-degree: 3%

---

# Definizione del testo dinamico{#defining-dynamic-text}

Il testo dinamico è definito nello stesso modo del contenuto dinamico. Consulta la sezione [Definizione del contenuto dinamico](../../designing/using/personalization.md#defining-dynamic-content-in-an-email) sezione.

>[!NOTE]
>
>Per SMS e push, puoi definire solo testo dinamico. Puoi definire sia il contenuto dinamico che il testo in una pagina di destinazione. Per definire il testo dinamico con [E-mail Designer](../../designing/using/designing-content-in-adobe-campaign.md), vedi [Definizione del contenuto dinamico in un messaggio e-mail](../../designing/using/personalization.md#defining-dynamic-content-in-an-email).

Le coppie surrogate, ovvero i caratteri non inclusi nel piano multilingue di base del set di caratteri Unicode, non possono essere memorizzati in 2 byte (16 bit) e devono essere codificati in 2 caratteri UTF-16. Questi caratteri includono alcuni ideogrammi CJK, la maggior parte delle emoticon e alcune lingue.
<br>Questi caratteri possono causare alcuni problemi di incompatibilità nel testo dinamico. Prima di inviare i messaggi, è necessario eseguire test avanzati.


L’esempio seguente mostra come definire il testo dinamico in un messaggio SMS.

1. Seleziona il testo nel corpo del messaggio o della pagina di destinazione.
1. Fai clic su **[!UICONTROL Enable dynamic text]**.

   ![](assets/dynamic_text_sms_1.png)

   Il **[!UICONTROL Dynamic text]** nella palette. È configurato nello stesso modo del contenuto dinamico.

1. Seleziona una variante.

   ![](assets/dynamic_text_sms_2.png)

1. Definisci una condizione per questa variante.

   ![](assets/dynamic_text_sms_4.png)

Una volta definita una condizione per almeno una variante, attorno al testo dinamico viene visualizzata una cornice viola.

![](assets/dynamic_text_sms_3.png)
