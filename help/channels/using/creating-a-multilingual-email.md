---
title: Creazione di un'e-mail multilingue
seo-title: Creazione di un'e-mail multilingue
description: Creazione di un'e-mail multilingue
seo-description: Attenetevi alla procedura seguente per creare un destinatario per e-mail in più lingue con lingue diverse.
page-status-flag: never-activated
uuid: e 90 f 4 ec 8-14 e 3-4304-b 5 fc-horn 0 ba 08 a 4 ef
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: canali
content-type: riferimento
topic-tags: email-messages
discoiquuid: 79231445-1 d 51-499 a-adcf -0 c 0 f 6 db 1 cfa 3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 855db33971afdf9f02bf1b00be67c9e3f50bee06

---


# Creating a multilingual email{#creating-a-multilingual-email}

Puoi inviare un messaggio e-mail multilingue a profili con lingue diverse: ogni profilo riceverà una variante del messaggio e-mail nella lingua preferita.

A tal fine, verificare che sia disponibile un modello e-mail multilingue. If not, learn how to create one in [this section](../../start/using/creating-a-multilingual-template.md).

L'audience è basata su profili con informazioni di lingua preferite.

1. Create a new email based on a [multilingual template](../../start/using/creating-a-multilingual-template.md).

   ![](assets/multi_create1.png)

1. Definite le proprietà generali e il pubblico di destinazione dell'e-mail, esattamente come per un'e-mail standard. Refer to the [Creating audiences](../../audiences/using/creating-audiences.md) section.
1. Al quarto passaggio della procedura guidata Creazione, definite le opzioni della variante. If the [multilingual template](../../start/using/creating-a-multilingual-template.md) already contains all the right parameters, you can directly click on the **[!UICONTROL Create]** button.

   ![](assets/multi_create4.png)

   If needed, add variants using the **[!UICONTROL Add an element]** button. **[!UICONTROL Default]** la variante non deve essere eliminata. When set to **[!UICONTROL default]**, [the profile's preferred language](../../audiences/using/creating-profiles.md) is used to choose the variant. You can also set the **[!UICONTROL Default]** variant to any other language.

1. Conferma la creazione e-mail: il pannello e-mail verrà quindi visualizzato.
1. Definire il contenuto e-mail per ogni variante. A seconda del modello scelto, potete definire diversi argomenti, vari nomi di mittente o diversi contenuti. Utilizzare il menu a discesa per spostarsi tra le diverse varianti dell'elemento. For more information, consult the [content editor](../../designing/using/about-email-content-design.md) section.

   ![](assets/multi_selectcontent.png)

1. Verifica e convalida il messaggio. Refer to the [Sending proof](../../sending/using/managing-test-profiles-and-sending-proofs.md#sending-proofs) section.
1. Schedule the send with the **[!UICONTROL Send after confirmation option]**.
1. Una volta inviato il messaggio e-mail, potete accedere ai suoi registri e ai relativi rapporti per misurare il successo della campagna. For more on reporting, refer to [this section](../../reporting/using/about-dynamic-reports.md).

