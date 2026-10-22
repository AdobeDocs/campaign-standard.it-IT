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
TQID: 'https://experienceleague.adobe.com/fgQySs0BUlvKT3CKMSaW-0fVe3W65qV1fDEZb1kDZ3w'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: a4671286-a59f-47e3-b97b-90627a1977d5
    internal-label: Communication channels
subfeature_v2:
  - id: b1bd1421-1927-4c59-9bc6-ce292360e43b
    internal-label: SMS Messaging
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
topic_v2:
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 3%
---
# Definizione del testo dinamico{#defining-dynamic-text}

Il testo dinamico è definito nello stesso modo del contenuto dinamico. Consulta la sezione [Definizione del contenuto dinamico](../../designing/using/personalization.md#defining-dynamic-content-in-an-email).

>[!NOTE]
>
>Per SMS e push, puoi definire solo testo dinamico. Puoi definire sia il contenuto dinamico che il testo in una pagina di destinazione. Se desideri definire il testo dinamico con [E-mail Designer](../../designing/using/designing-content-in-adobe-campaign.md), consulta [Definizione del contenuto dinamico in un messaggio e-mail](../../designing/using/personalization.md#defining-dynamic-content-in-an-email).

Le coppie surrogate, ovvero i caratteri non inclusi nel piano multilingue di base del set di caratteri Unicode, non possono essere memorizzati in 2 byte (16 bit) e devono essere codificati in 2 caratteri UTF-16. Questi caratteri includono alcuni ideogrammi CJK, la maggior parte delle emoticon e alcune lingue.
<br>Questi caratteri possono causare alcuni problemi di incompatibilità nel testo dinamico. Prima di inviare i messaggi, è necessario eseguire test avanzati.


L’esempio seguente mostra come definire il testo dinamico in un messaggio SMS.

1. Seleziona il testo nel corpo del messaggio o della pagina di destinazione.
1. Fai clic su **[!UICONTROL Enable dynamic text]**.

   ![](assets/dynamic_text_sms_1.png)

   L&#39;opzione **[!UICONTROL Dynamic text]** viene visualizzata nella palette. È configurato nello stesso modo del contenuto dinamico.

1. Seleziona una variante.

   ![](assets/dynamic_text_sms_2.png)

1. Definisci una condizione per questa variante.

   ![](assets/dynamic_text_sms_4.png)

Una volta definita una condizione per almeno una variante, attorno al testo dinamico viene visualizzata una cornice viola.

![](assets/dynamic_text_sms_3.png)
