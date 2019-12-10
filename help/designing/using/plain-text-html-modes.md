---
title: Modifica dei formati di testo normale, HTML e e e-mail per dispositivi mobili
description: Scoprite il testo normale e le modalità HTML
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
source-git-commit: 5e2ea8020c82f578b2cf8c00fa7b9f55b6ce2edd

---


# Modifica dei formati di testo normale, HTML e e e-mail per dispositivi mobili {#plain-text-and-html-modes}

Designer e-mail consente di modificare il rendering dei messaggi e-mail. Potete generare una versione di testo dell’e-mail, modificare l’origine HTML di un messaggio e-mail e progettare e-mail per la visualizzazione mobile.

## Generazione di una versione di testo del messaggio e-mail {#generating-a-text-version-of-the-email}

Per impostazione predefinita, la **[!UICONTROL Plain text]** versione del messaggio e-mail viene generata automaticamente e sincronizzata con la **[!UICONTROL Edit]** versione.

I campi di personalizzazione e i blocchi di contenuto aggiunti alla versione HTML sono sincronizzati anche con la versione in testo normale.

>[!NOTE]
>
>Per utilizzare i blocchi di contenuto nella versione in testo normale, accertatevi che non contengano codice HTML.

Per avere una versione di testo normale diversa dalla versione HTML, potete disattivare la sincronizzazione facendo clic sul **[!UICONTROL Sync with HTML]** pulsante nella **[!UICONTROL Plain text]** vista del messaggio e-mail.

![](assets/email_designer_textversion.png)

Potete quindi modificare la versione di testo normale come desiderato.

>[!NOTE]
>
>Se modificate la **[!UICONTROL Plain text]** versione mentre la sincronizzazione è disattivata, la successiva attivazione dell’ **[!UICONTROL Sync with HTML]** opzione tutte le modifiche apportate nella versione in testo normale verranno sostituite con la versione HTML. Le modifiche apportate nella **[!UICONTROL Plain text]** vista non possono essere riportate nella **[!UICONTROL HTML]** vista.

## Modifica di un'origine contenuto e-mail in HTML {#editing-an-email-content-source-in-html}

Per gli utenti più avanzati e il debug, potete visualizzare e modificare il contenuto dell'e-mail direttamente in HTML.

Potete modificare la versione HTML del messaggio e-mail in due modi:

* Selezionate **[!UICONTROL Edit]** &gt; **[!UICONTROL HTML]** per aprire la versione HTML dell’intero messaggio e-mail.

   ![](assets/email_designer_html1.png)

* Dall’interfaccia WYSIWYG, selezionate un elemento e fate clic sull’ **[!UICONTROL Source code]** icona .

   Viene visualizzata solo l'origine dell'elemento selezionato. Potete modificare il codice sorgente se l’elemento selezionato è un componente di **[!UICONTROL HTML]** contenuto. Altri componenti sono in modalità di sola lettura, ma possono essere modificati nella versione HTML completa del messaggio e-mail.

   ![](assets/email_designer_html2.png)

Se modificate il codice HTML, la reattività dell’e-mail potrebbe non essere corretta. Assicurarsi di verificarlo utilizzando il **[!UICONTROL Preview]** pulsante. Consultate [Anteprima dei messaggi](../../sending/using/previewing-messages.md).

## Progettazione di e-mail per il rendering mobile {#switching-to-mobile-view}

Potete regolare il design reattivo di un’e-mail modificando separatamente tutte le opzioni di stile per la visualizzazione mobile. Ad esempio, potete adattare margini e spaziatura, usare font di dimensioni più piccole o grandi, modificare i pulsanti o applicare colori di sfondo diversi, specifici per la versione mobile dell’e-mail.

Tutte le opzioni di stile sono disponibili nella visualizzazione mobile. Le impostazioni di stile di Designer e-mail sono precedentemente presentate in questa pagina.

1. Create un messaggio e-mail e iniziate a modificare il contenuto. Per ulteriori informazioni, consultate [Progettazione di contenuti e-mail da zero](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch).
1. Per accedere alla visualizzazione dedicata per dispositivi mobili, fate clic sul **[!UICONTROL Switch to mobile view]** pulsante .

   ![](assets/email_designer_mobile_view_switch.png)

   Viene visualizzata la versione mobile dell’e-mail. Contiene tutti i componenti e gli stili definiti nella visualizzazione desktop.

1. Modificate in modo indipendente tutte le impostazioni di stile come il colore di sfondo, l’allineamento, la spaziatura, il margine, la famiglia di font, il colore del testo e così via.

   ![](assets/email_designer_mobile_view.png)

1. Quando modificate un’impostazione di stile in visualizzazione mobile, le modifiche vengono applicate solo al display del dispositivo mobile.

   Ad esempio, riducete le dimensioni di un’immagine, aggiungete uno sfondo verde e modificate la spaziatura nella visualizzazione mobile.

   ![](assets/email_designer_mobile_view_change.png)

1. Potete nascondere un componente quando viene visualizzato su un dispositivo mobile. A tale scopo, selezionare **[!UICONTROL Show only on desktop devices]** dal **[!UICONTROL Display options]**.

   Potete anche scegliere di nascondere il componente sui dispositivi desktop, il che significa che verrà visualizzato solo sui dispositivi mobili. A tale scopo, selezionare **[!UICONTROL Show only on mobile devices]**.

   Ad esempio, questa opzione consente di visualizzare un’immagine specifica su dispositivi mobili e un’altra su dispositivi desktop.

   Potete impostare questa opzione dalla visualizzazione mobile o desktop.

   ![](assets/email_designer_mobile_hide.png)

1. Fate nuovamente clic sul **[!UICONTROL Switch to mobile view]** pulsante per tornare alla visualizzazione desktop standard. Le modifiche apportate allo stile non vengono riportate.

   ![](assets/email_designer_mobile_view_desktop_no-change.png)

   >[!NOTE]
   >
   >L'unica eccezione sono le **[!UICONTROL Style inline]** impostazioni. Qualsiasi modifica alle impostazioni di stile in linea viene applicata anche alla visualizzazione desktop standard.

1. Qualsiasi altra modifica alla struttura o al contenuto dell’e-mail, ad esempio modifiche di testo, caricamento di una nuova immagine, aggiunta di un nuovo componente e così via. viene applicata anche alla visualizzazione standard.

   Ad esempio, tornate alla visualizzazione mobile, modificate del testo e sostituite un’immagine.

   ![](assets/email_designer_mobile_view_change_content.png)

   Fate nuovamente clic sul **[!UICONTROL Switch to mobile view]** pulsante per tornare alla visualizzazione desktop standard. Le modifiche vengono riportate.

   ![](assets/email_designer_mobile_view_desktop_content-change.png)

1. Se rimuovete uno stile nella visualizzazione mobile, tornerete allo stile applicato in modalità desktop.

   Ad esempio, nella visualizzazione mobile, applicate un colore di sfondo verde a un pulsante.

   ![](assets/email_designer_mobile_view_background_mobile.png)

1. Passate alla visualizzazione desktop e applicate uno sfondo grigio allo stesso pulsante.

   ![](assets/email_designer_mobile_view_background_desktop.png)

1. Passate nuovamente alla visualizzazione mobile e disattivate l' **[!UICONTROL Background color]** impostazione.

   ![](assets/email_designer_mobile_view_background_mobile_disabled.png)

   Viene ora applicato il colore di sfondo definito nella visualizzazione desktop: diventa grigio (non vuoto).

   L'unica eccezione è l' **[!UICONTROL Border color]** impostazione. Se disabilitato in visualizzazione mobile, non viene più applicato alcun bordo, anche se nella visualizzazione desktop è definito un colore per il bordo.

>[!NOTE]
>
>La visualizzazione mobile non è disponibile nei [frammenti](../../designing/using/using-reusable-content.md#about-fragments).
