---
solution: Campaign Standard
product: campaign
title: Modifica dei formati di testo normale, HTML e e e-mail per dispositivi mobili
description: Scoprite il testo normale e le modalità HTML
audience: designing
content-type: reference
topic-tags: editing-email-content
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '776'
ht-degree: 0%

---


# Modifica dei formati di testo normale, HTML e e e-mail per dispositivi mobili {#plain-text-and-html-modes}

Designer e-mail consente di modificare il rendering dei messaggi e-mail. Potete generare una versione di testo dell’e-mail, modificare l’origine HTML di un messaggio e-mail e progettare e-mail per la visualizzazione mobile.

## Generazione di una versione di testo dell&#39;e-mail {#generating-a-text-version-of-the-email}

Per impostazione predefinita, la versione **[!UICONTROL Plain text]** dell&#39;e-mail viene generata automaticamente e sincronizzata con la versione **[!UICONTROL Edit]**.

I campi di personalizzazione e i blocchi di contenuto aggiunti alla versione HTML sono sincronizzati anche con la versione in testo normale.

>[!NOTE]
>
>Per utilizzare i blocchi di contenuto nella versione in testo normale, accertatevi che non contengano codice HTML.

Per avere una versione di testo normale diversa dalla versione HTML, potete disattivare la sincronizzazione facendo clic sul passaggio **[!UICONTROL Sync with HTML]** dalla vista **[!UICONTROL Plain text]** del messaggio e-mail.

![](assets/email_designer_textversion.png)

Potete quindi modificare la versione di testo normale come desiderato.

>[!NOTE]
>
>Se modificate la versione **[!UICONTROL Plain text]** mentre la sincronizzazione è disattivata, la successiva attivazione dell&#39;opzione **[!UICONTROL Sync with HTML]**, tutte le modifiche apportate nella versione in testo normale verranno sostituite con la versione HTML. Le modifiche apportate nella vista **[!UICONTROL Plain text]** non possono essere riportate nella vista **[!UICONTROL HTML]**.

## Modifica di un&#39;origine di contenuto e-mail in HTML {#editing-an-email-content-source-in-html}

Per gli utenti più avanzati e il debug, potete visualizzare e modificare il contenuto dell&#39;e-mail direttamente in HTML.

Potete modificare la versione HTML del messaggio e-mail in due modi:

* Selezionate **[!UICONTROL Edit]** > **[!UICONTROL HTML]** per aprire la versione HTML dell&#39;intero messaggio e-mail.

   ![](assets/email_designer_html1.png)

* Dall&#39;interfaccia WYSIWYG, selezionate un elemento e fate clic sull&#39;icona **[!UICONTROL Source code]**.

   Viene visualizzata solo l&#39;origine dell&#39;elemento selezionato. Potete modificare il codice sorgente se l&#39;elemento selezionato è un componente di contenuto **[!UICONTROL HTML]**. Altri componenti sono in modalità di sola lettura, ma possono essere modificati nella versione HTML completa del messaggio e-mail.

   ![](assets/email_designer_html2.png)

Se modificate il codice HTML, la reattività dell’e-mail potrebbe non essere corretta. Assicurarsi di verificarlo utilizzando il pulsante **[!UICONTROL Preview]**. Consulta [Anteprima dei messaggi](../../sending/using/previewing-messages.md).

## Progettazione di e-mail per il rendering mobile {#switching-to-mobile-view}

Potete regolare il design reattivo di un’e-mail modificando separatamente tutte le opzioni di stile per la visualizzazione mobile. Ad esempio, potete adattare margini e spaziatura, utilizzare dimensioni di font più piccole o grandi, modificare i pulsanti o applicare colori di sfondo diversi, specifici per la versione mobile dell’e-mail.

Tutte le opzioni di stile sono disponibili nella visualizzazione mobile. Le impostazioni di stile di Designer e-mail sono precedentemente presentate in questa pagina.

1. Create un messaggio e-mail e iniziate a modificare il contenuto. Per ulteriori informazioni, vedere [Progettazione di un contenuto e-mail da zero](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch).
1. Per accedere alla visualizzazione dedicata per dispositivi mobili, fate clic sul pulsante **[!UICONTROL Switch to mobile view]**.

   ![](assets/email_designer_mobile_view_switch.png)

   Viene visualizzata la versione mobile dell’e-mail. Contiene tutti i componenti e gli stili definiti nella visualizzazione desktop.

1. Modificate in modo indipendente tutte le impostazioni di stile come il colore di sfondo, l’allineamento, la spaziatura, il margine, la famiglia di font, il colore del testo e così via.

   ![](assets/email_designer_mobile_view.png)

1. Quando modificate un’impostazione di stile in visualizzazione mobile, le modifiche vengono applicate solo al display del dispositivo mobile.

   Ad esempio, riducete le dimensioni di un’immagine, aggiungete uno sfondo verde e modificate la spaziatura nella visualizzazione mobile.

   ![](assets/email_designer_mobile_view_change.png)

1. Potete nascondere un componente quando viene visualizzato su un dispositivo mobile. A questo scopo, selezionare **[!UICONTROL Show only on desktop devices]** dal **[!UICONTROL Display options]**.

   Potete anche scegliere di nascondere il componente sui dispositivi desktop, il che significa che verrà visualizzato solo sui dispositivi mobili. A questo scopo, selezionare **[!UICONTROL Show only on mobile devices]**.

   Ad esempio, questa opzione consente di visualizzare un’immagine specifica su dispositivi mobili e un’altra su dispositivi desktop.

   Potete impostare questa opzione dalla visualizzazione mobile o desktop.

   ![](assets/email_designer_mobile_hide.png)

1. Fate di nuovo clic sul pulsante **[!UICONTROL Switch to mobile view]** per tornare alla visualizzazione desktop standard. Le modifiche di stile appena apportate non vengono riportate.

   ![](assets/email_designer_mobile_view_desktop_no-change.png)

   >[!NOTE]
   >
   >L&#39;unica eccezione è rappresentata dalle impostazioni **[!UICONTROL Style inline]**. Qualsiasi modifica alle impostazioni di stile in linea viene applicata anche alla visualizzazione desktop standard.

1. Qualsiasi altra modifica alla struttura o al contenuto dell’e-mail, ad esempio modifiche di testo, caricamento di una nuova immagine, aggiunta di un nuovo componente e così via. viene applicata anche alla visualizzazione standard.

   Ad esempio, tornate alla visualizzazione mobile, modificate del testo e sostituite un’immagine.

   ![](assets/email_designer_mobile_view_change_content.png)

1. Fate di nuovo clic sul pulsante **[!UICONTROL Switch to mobile view]** per tornare alla visualizzazione desktop standard. Le modifiche vengono riportate.

   ![](assets/email_designer_mobile_view_desktop_content-change.png)

1. Se rimuovete uno stile nella visualizzazione mobile, tornerete allo stile applicato in modalità desktop.

   Ad esempio, nella visualizzazione mobile, applicate un colore di sfondo verde a un pulsante.

   ![](assets/email_designer_mobile_view_background_mobile.png)

1. Passate alla visualizzazione desktop e applicate uno sfondo grigio allo stesso pulsante.

   ![](assets/email_designer_mobile_view_background_desktop.png)

1. Passate nuovamente alla visualizzazione mobile e disattivate l&#39;impostazione **[!UICONTROL Background color]**.

   ![](assets/email_designer_mobile_view_background_mobile_disabled.png)

   Viene ora applicato il colore di sfondo definito nella visualizzazione desktop: diventa grigio (non vuoto).

   L&#39;unica eccezione è l&#39;impostazione **[!UICONTROL Border color]**. Se disabilitato in visualizzazione mobile, non viene più applicato alcun bordo, anche se nella visualizzazione desktop è definito un colore per il bordo.

>[!NOTE]
>
>La visualizzazione mobile non è disponibile nei [frammenti](../../designing/using/using-reusable-content.md#about-fragments).
