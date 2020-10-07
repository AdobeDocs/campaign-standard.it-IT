---
title: Definizione del pubblico della direct mailing
description: Scopri come definire il target per la consegna di direct mailing.
page-status-flag: never-activated
uuid: f843e368-5c07-4b53-8943-46f7bf45b62b
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: direct-mail
discoiquuid: f993d1b6-4b9a-4f95-81fc-60c126211bd2
context-tags: delivery,directMailContent,back
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 100%

---


# Definizione del pubblico della direct mailing{#defining-the-direct-mail-audience}

Puoi definire il pubblico all’interno della procedura guidata di creazione oppure facendo clic sulla sezione **Audience** del dashboard di consegna.

![](assets/direct_mail_15.png)

## Definizione del target principale {#defining-the-main-target}

Per la direct mailing, i profili target sono quelli che verranno inclusi nel file di estrazione che invierai al tuo provider di direct mailing.

Per ciascun profilo target, viene aggiunta una nuova riga nel file di estrazione. La quantità di informazioni di profilo che verranno incluse per ciascun destinatario è indicata nella schermata [Definizione dell’estrazione](../../channels/using/defining-the-direct-mail-content.md#defining-the-extraction).

>[!CAUTION]
>
>Accertati che i profili includano un indirizzo postale, poiché queste informazioni sono essenziali per il provider di direct mailing. Inoltre, assicurati di aver selezionato la casella **[!UICONTROL Address specified]** nelle informazioni del profilo. Consulta [Raccomandazioni](../../channels/using/about-direct-mail.md#recommendations).

## Aggiunta di profili di test e di trappole {#adding-test-and-trap-profiles}

Aggiungi i profili di test in modo da poter testare il file con un numero limitato di profili. Ciò ti consente di creare rapidamente un esempio di file per effettuare la verifica e la convalida della struttura, prima di passare alla preparazione del file effettivo. Consulta [Gestione dei profili di test](../../audiences/using/managing-test-profiles.md).

L’uso di trappole è essenziale per le consegne di direct mailing. Ti consentono di verificare che il provider di direct mailing stia inviando effettivamente la comunicazione e che non stia mandando il tuo elenco dei clienti a un altro provider. Consulta [Utilizzo delle “trappole”](../../sending/using/using-traps.md).

Per le consegne di direct mailing, le trappole vengono aggiunte durante l’estrazione e unite nel documento di output. Per impostazione predefinita, le trappole vengono inserite nell’ordinamento del file di output, ma è possibile inserirle alla fine o all’inizio del file. Quando definisci il pubblico, seleziona l’opzione desiderata dalla scheda **[!UICONTROL Trap insertion mode]**.

![](assets/direct_mail_trap_insertion_mode.png)
