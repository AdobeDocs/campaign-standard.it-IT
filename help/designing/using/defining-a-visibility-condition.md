---
title: Definizione di una condizione di visibilità
seo-title: Definizione di una condizione di visibilità
description: Definizione di una condizione di visibilità
seo-description: Rendere un elemento di pagina Web visibile solo se viene rispettata una determinata condizione.
page-status-flag: never-activated
uuid: 224005 ba-ef 09-4790-b 2 f 0-30 ed 74 cfa 32 d
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: progettazione
content-type: riferimento
topic-tags: definizione-condizionale del contenuto
discoiquuid: c 12125 a 7-a 1 cf -4 bc 1-a 138-57 ff 74974024
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Defining a visibility condition{#defining-a-visibility-condition}

Potete specificare una condizione di visibilità su qualsiasi elemento. È visibile solo se la condizione viene rispettata.

To add a visibility condition, select a block and enter the condition to be respected in the **[!UICONTROL Visibility condition]** field of its settings.

![](assets/delivery_content_5.png)

Questa opzione è disponibile solo per gli elementi seguenti: ADDRESS, BLOCKQUOTE, CENTER, DIR, DIV, DL, FIELDSET, FORM, H 1, H 2, H 3, H 4, H 5, H 6, NOSCRIPT, OL, P, PRE, UL, TR, TD.

The expression editor is presented in the [Advanced expression editing](../../automating/using/editing-queries.md#about-query-editor) section.

These conditions adopt the XTK expression syntax (e.g. **context.profile.email !=''** or **context.profile.status='0'**). Per impostazione predefinita, tutti i campi sono visibili.

>[!NOTE]
>
>Non è possibile definire una condizione per un blocco che contiene già un elemento secondario con un contenuto dinamico o un blocco che costituisce già un contenuto dinamico. Non è possibile modificare blocchi dinamici non visibili come gli elenchi a discesa.

