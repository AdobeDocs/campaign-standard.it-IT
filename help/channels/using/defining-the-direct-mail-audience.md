---
title: Definizione del pubblico di posta diretta
seo-title: Definizione del pubblico di posta diretta
description: Definizione del pubblico di posta diretta
seo-description: Scoprite come definire la destinazione per la consegna diretta del messaggio.
page-status-flag: never-activated
uuid: f 843 e 368-5 c 07-4 b 53-8943-46 f 7 bf 45 b 62 b
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: canali
content-type: riferimento
topic-tags: direct-mail
discoiquuid: f 993 d 1 b 6-4 b 9 a -4 f 95-81 fc -60 c 126211 bd 2
context-tags: delivery, directmailcontent, back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b0cf437ec97153b53bd4502171b24286abb25731

---


# Defining the direct mail audience{#defining-the-direct-mail-audience}

You can either define the audience in the creation wizard or by clicking on the **Audience** section of the delivery dashboard.

![](assets/direct_mail_15.png)

## Defining the main target {#defining-the-main-target}

Per la posta diretta, i profili di destinazione sono quelli che verranno inclusi nel file di estrazione che invierete al provider di posta diretta.

Per ogni profilo di destinazione, nel file di estrazione viene aggiunta una nuova linea. The amount of profile information that will be included for each recipient is defined in the [Defining the extraction](../../channels/using/defining-the-direct-mail-content.md#defining-the-extraction) screen.

>[!CAUTION]
>
>Accertatevi che i profili includano un indirizzo postale in quanto queste informazioni sono essenziali per il provider di posta diretta. Also make sure you have checked the **[!UICONTROL Address specified]** box in your profiles' information. See [Recommendations](../../channels/using/about-direct-mail.md#recommendations).

## Adding test and trap profiles {#adding-test-and-trap-profiles}

Aggiungete profili di prova in modo da poter sottoporre a test il file con un numero limitato di profili. Consente di creare rapidamente un esempio di file per verificare e convalidare la struttura prima di preparare il file effettivo. Refer to [Managing test profiles and sending proofs](../../sending/using/managing-test-profiles-and-sending-proofs.md).

L'utilizzo delle abbondanze è essenziale per le consegne di posta diretta. Ad esempio, consentono di verificare che il provider di posta diretta stia inviando effettivamente la comunicazione e che non invii l'elenco dei client a un altro fornitore.

Per le consegne di posta diretta, le abbondanze vengono aggiunte durante l'estrazione e nel documento di output. By default, they are inserted in the sorting order of the output file, but you can choose to insert them at the end or the beginning of the file ( **[!UICONTROL Trap insertion mode]** tab).
