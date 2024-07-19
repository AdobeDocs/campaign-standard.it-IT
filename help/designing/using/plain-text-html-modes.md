---
title: Modifica dei formati di e-mail per dispositivi mobili, HTML e testo normale
description: Scopri le modalità Testo normale e HTML
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: Email Design
role: User
level: Intermediate
exl-id: 760c3c30-c899-4cf4-ba59-fb2fade9fc5e
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '776'
ht-degree: 1%

---

# Modifica dei formati di e-mail per dispositivi mobili, HTML e testo normale {#plain-text-and-html-modes}

E-mail Designer consente di modificare diversi rendering delle e-mail. Puoi generare una versione testuale del messaggio e-mail, modificare l’origine HTML di un messaggio e-mail e progettare le e-mail per la visualizzazione per dispositivi mobili.

## Generazione di una versione testuale del messaggio e-mail {#generating-a-text-version-of-the-email}

Per impostazione predefinita, la versione **[!UICONTROL Plain text]** dell&#39;e-mail viene generata automaticamente e sincronizzata con la versione **[!UICONTROL Edit]**.

I campi di personalizzazione e i blocchi di contenuto aggiunti alla versione di HTML vengono sincronizzati anche con la versione di testo normale.

>[!NOTE]
>
>Per utilizzare i blocchi di contenuto nella versione in testo normale, assicurati che non contengano codice HTML.

Per avere una versione di testo normale diversa da quella di HTML, è possibile disabilitare questa sincronizzazione facendo clic sull&#39;opzione **[!UICONTROL Sync with HTML]** nella visualizzazione **[!UICONTROL Plain text]** dell&#39;e-mail.

![](assets/email_designer_textversion.png)

Puoi quindi modificare la versione di testo normale come desiderato.

>[!NOTE]
>
>Se si modifica la versione **[!UICONTROL Plain text]** mentre la sincronizzazione è disabilitata, alla successiva attivazione dell&#39;opzione **[!UICONTROL Sync with HTML]** tutte le modifiche apportate nella versione in testo normale verranno sostituite con la versione HTML. Le modifiche apportate nella visualizzazione **[!UICONTROL Plain text]** non possono essere applicate alla visualizzazione **[!UICONTROL HTML]**.

## Modifica di un’origine di contenuto e-mail in HTML {#editing-an-email-content-source-in-html}

Per gli utenti più avanzati e per il debug, puoi visualizzare e modificare il contenuto delle e-mail direttamente in HTML.

Puoi modificare la versione HTML dell’e-mail in due modi:

* Selezionare **[!UICONTROL Edit]** > **[!UICONTROL HTML]** per aprire la versione HTML dell&#39;intero messaggio e-mail.

  ![](assets/email_designer_html1.png)

* Dall&#39;interfaccia WYSIWYG, selezionare un elemento e fare clic sull&#39;icona **[!UICONTROL Source code]**.

  Viene visualizzata solo l’origine dell’elemento selezionato. È possibile modificare il codice sorgente se l&#39;elemento selezionato è un componente di contenuto **[!UICONTROL HTML]**. Gli altri componenti sono in modalità di sola lettura, ma possono ancora essere modificati nella versione completa HTML dell’e-mail.

  ![](assets/email_designer_html2.png)

Se modifichi il codice HTML, la reattività dell’e-mail potrebbe essere interrotta. Verificare che il test venga eseguito utilizzando il pulsante **[!UICONTROL Preview]**. Consulta [Anteprima dei messaggi](../../sending/using/previewing-messages.md).

## Progettazione di e-mail per il rendering mobile {#switching-to-mobile-view}

Puoi ottimizzare la progettazione reattiva di un’e-mail modificando separatamente tutte le opzioni di stile per la visualizzazione mobile. Ad esempio, puoi adattare i margini e la spaziatura, utilizzare caratteri di dimensioni inferiori o maggiori, modificare i pulsanti o applicare colori di sfondo diversi specifici per la versione mobile dell’e-mail.

Tutte le opzioni di stile sono disponibili nella vista per dispositivi mobili. Le impostazioni di stile di E-mail Designer sono già presenti in questa pagina.

1. Crea un messaggio e-mail e inizia a modificare il contenuto. Per ulteriori informazioni, vedere [Progettazione di un contenuto di posta elettronica da zero](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch).
1. Per accedere alla visualizzazione mobile dedicata, selezionare il pulsante **[!UICONTROL Switch to mobile view]**.

   ![](assets/email_designer_mobile_view_switch.png)

   Viene visualizzata la versione mobile dell’e-mail. Contiene tutti i componenti e gli stili definiti nella vista desktop.

1. Modificare in modo indipendente tutte le impostazioni di stile, ad esempio il colore di sfondo, l&#39;allineamento, la spaziatura, il margine, la famiglia di caratteri, il colore del testo e così via.

   ![](assets/email_designer_mobile_view.png)

1. Quando si modifica un’impostazione di stile in visualizzazione per dispositivi mobili, le modifiche vengono applicate solo allo schermo mobile.

   Ad esempio, riduci le dimensioni di un’immagine, aggiungi uno sfondo verde e modifica la spaziatura nella vista per dispositivi mobili.

   ![](assets/email_designer_mobile_view_change.png)

1. Puoi nascondere un componente quando viene visualizzato su un dispositivo mobile. A tale scopo, selezionare **[!UICONTROL Show only on desktop devices]** da **[!UICONTROL Display options]**.

   Puoi anche scegliere di nascondere questo componente sui dispositivi desktop, il che significa che verrà visualizzato solo sui dispositivi mobili. A tale scopo, selezionare **[!UICONTROL Show only on mobile devices]**.

   Ad esempio, questa opzione consente di visualizzare un’immagine specifica su dispositivi mobili e un’altra immagine su dispositivi desktop.

   Puoi impostare questa opzione dalla vista per dispositivi mobili o desktop.

   ![](assets/email_designer_mobile_hide.png)

1. Fare di nuovo clic sul pulsante **[!UICONTROL Switch to mobile view]** per tornare alla visualizzazione desktop standard. Le modifiche di stile appena apportate non vengono applicate.

   ![](assets/email_designer_mobile_view_desktop_no-change.png)

   >[!NOTE]
   >
   >L&#39;unica eccezione è rappresentata dalle impostazioni **[!UICONTROL Style inline]**. Qualsiasi modifica all&#39;impostazione in linea dello stile viene applicata anche alla visualizzazione standard del desktop.

1. Qualsiasi altra modifica alla struttura o al contenuto dell’e-mail, ad esempio modifiche di testo, caricamento di una nuova immagine, aggiunta di un nuovo componente e così via. viene applicato anche alla visualizzazione standard.

   Ad esempio, torna alla visualizzazione per dispositivi mobili, modifica del testo e sostituisci un’immagine.

   ![](assets/email_designer_mobile_view_change_content.png)

1. Fare di nuovo clic sul pulsante **[!UICONTROL Switch to mobile view]** per tornare alla visualizzazione desktop standard. Le modifiche vengono applicate.

   ![](assets/email_designer_mobile_view_desktop_content-change.png)

1. Se si rimuove uno stile nella visualizzazione per dispositivi mobili, si torna allo stile applicato in modalità desktop.

   Ad esempio, nella visualizzazione per dispositivi mobili, applica un colore di sfondo verde a un pulsante.

   ![](assets/email_designer_mobile_view_background_mobile.png)

1. Passare alla vista desktop e applicare uno sfondo grigio allo stesso pulsante.

   ![](assets/email_designer_mobile_view_background_desktop.png)

1. Passare nuovamente alla visualizzazione per dispositivi mobili e disattivare l&#39;impostazione **[!UICONTROL Background color]**.

   ![](assets/email_designer_mobile_view_background_mobile_disabled.png)

   Ora viene applicato il colore di sfondo definito nella vista desktop, che diventa grigio (non vuoto).

   L&#39;unica eccezione è l&#39;impostazione **[!UICONTROL Border color]**. Se l&#39;opzione è disattivata nella visualizzazione per dispositivi mobili, non viene più applicato alcun bordo, anche se è stato definito un colore per il bordo nella visualizzazione desktop.

>[!NOTE]
>
>La visualizzazione per dispositivi mobili non è disponibile in [frammenti](../../designing/using/using-reusable-content.md#about-fragments).
