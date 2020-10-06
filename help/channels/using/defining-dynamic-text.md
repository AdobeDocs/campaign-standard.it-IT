---
title: Definizione del testo dinamico
description: Scoprite come visualizzare testi diversi in modo dinamico all'utente in base alle condizioni definite in  Adobe Campaign.
page-status-flag: never-activated
uuid: bbcd200c-4fb4-467b-ba39-09b8bee9bcaa
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: designing
content-type: reference
topic-tags: defining-conditional-content
discoiquuid: 6bb6cee3-5674-4113-8073-5a9572b3e830
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 9c812b0b622b82ba7aa382f04edb7a2a3f717cd4
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Definizione del testo dinamico{#defining-dynamic-text}

Il testo dinamico è definito allo stesso modo del contenuto dinamico. Fare riferimento alla sezione [Definizione del contenuto](../../designing/using/personalization.md#defining-dynamic-content-in-an-email) dinamico.

>[!NOTE]
>
>Per SMS e push, potete definire solo testo dinamico. È possibile definire contenuto dinamico e testo in una pagina di destinazione. Se si desidera definire il testo dinamico con [Email Designer](../../designing/using/designing-content-in-adobe-campaign.md), vedere [Definizione del contenuto dinamico in un messaggio e-mail](../../designing/using/personalization.md#defining-dynamic-content-in-an-email).

Tenere presente che le coppie sostitutive, i caratteri non inclusi nel piano multilingue di base del set di caratteri Unicode, non possono essere memorizzati in 2 byte (16 bit) e devono essere codificati in 2 caratteri UTF-16. Questi caratteri includono alcuni ideogrammi CJK, la maggior parte delle emoticon e alcune lingue.
<br>Questi caratteri possono causare problemi di incompatibilità nel testo dinamico. Prima di inviare i messaggi è necessario eseguire dei test rigorosi.


L&#39;esempio seguente mostra come definire testo dinamico in un messaggio SMS.

1. Selezionate il testo nel corpo del messaggio o della pagina di destinazione.
1. Fai clic su **[!UICONTROL Enable dynamic text]**.

   ![](assets/dynamic_text_sms_1.png)

   L&#39; **[!UICONTROL Dynamic text]** opzione viene visualizzata nella palette. È configurato allo stesso modo del contenuto dinamico.

1. Selezionare una variante.

   ![](assets/dynamic_text_sms_2.png)

1. Definire una condizione per questa variante.

   ![](assets/dynamic_text_sms_4.png)

Una volta definita una condizione per almeno una variante, intorno al testo dinamico viene visualizzata una cornice viola.

![](assets/dynamic_text_sms_3.png)
