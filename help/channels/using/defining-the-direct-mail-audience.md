---
title: Definizione dell’audience della direct mail
description: Scopri come definire la destinazione per la consegna diretta per la posta.
page-status-flag: never-activated
uuid: f843e368-5c07-4b53-8943-46f7bf45b62b
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: direct-mail
discoiquuid: f993d1b6-4b9a-4f95-81fc-60c126211bd2
context-tags: delivery,directMailContent,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 32bcfd57dfe881fa07c8d8e5700d0ae3996a78ec

---


# Definizione dell’audience della direct mail{#defining-the-direct-mail-audience}

Potete definire l'audience nella procedura guidata di creazione oppure facendo clic sulla sezione **Pubblico** del dashboard di distribuzione.

![](assets/direct_mail_15.png)

## Definizione della destinazione principale {#defining-the-main-target}

Per la posta diretta, i profili di destinazione sono quelli che verranno inclusi nel file di estrazione che invierete al vostro provider di posta diretta.

Per ciascun profilo di destinazione, nel file di estrazione viene aggiunta una nuova riga. La quantità di informazioni di profilo che verranno incluse per ciascun destinatario è definita nella schermata [Definizione dell'estrazione](../../channels/using/defining-the-direct-mail-content.md#defining-the-extraction) .

>[!CAUTION]
>
>Accertatevi che i vostri profili includano un indirizzo postale, in quanto queste informazioni sono essenziali per il fornitore di posta diretta. Inoltre accertatevi di aver selezionato la **[!UICONTROL Address specified]** casella nelle informazioni del profilo. Vedete [Recommendations](../../channels/using/about-direct-mail.md#recommendations).

## Aggiunta di profili di test e trap {#adding-test-and-trap-profiles}

Aggiungete profili di prova in modo da poter testare il file con un numero limitato di profili. Consente di creare rapidamente un esempio di file per verificare e convalidare la struttura prima di preparare il file effettivo. See [Managing test profiles and sending proofs](../../sending/using/managing-test-profiles-and-sending-proofs.md).

L'uso di trappole è essenziale per la consegna diretta per corrispondenza. Consentono di verificare che il provider di posta diretta stia inviando la comunicazione e che non inviino l'elenco dei clienti a un altro provider. Consultate [Utilizzo delle trappole](../../sending/using/managing-test-profiles-and-sending-proofs.md#using-traps).

Per le consegne per corrispondenza diretta, le trappole vengono aggiunte durante l'estrazione e mescolate nel documento di output. Per impostazione predefinita, vengono inseriti nell'ordine di ordinamento del file di output, ma è possibile inserirli alla fine o all'inizio del file. Quando definite l'audience, selezionate l'opzione desiderata dalla **[!UICONTROL Trap insertion mode]** scheda.

![](assets/direct_mail_trap_insertion_mode.png)
