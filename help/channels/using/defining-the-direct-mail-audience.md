---
title: Definizione del pubblico della direct mailing
description: Scopri come definire il target per la consegna di direct mailing.
audience: channels
content-type: reference
topic-tags: direct-mail
context-tags: delivery,directMailContent,back
feature: Direct Mail
role: User
level: Intermediate
exl-id: ea167fec-d4df-4147-9dcd-33001d8a1c9b
TQID: 'https://experienceleague.adobe.com/iYqxhsfsz95pTh8V-sP-xwGSSQ39YyIov9OHHyfepDI'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: a4671286-a59f-47e3-b97b-90627a1977d5
    internal-label: Communication channels
subfeature_v2:
  - id: ede6e1ec-9279-415e-b828-a09735018d48
    internal-label: Direct mail
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 96%
---
# Definizione del pubblico del direct mailing{#defining-the-direct-mail-audience}

Puoi definire il pubblico all’interno della procedura guidata di creazione oppure facendo clic sulla sezione **Audience** del dashboard di consegna.

![](assets/direct_mail_15.png)

## Definizione del target principale {#defining-the-main-target}

Per la direct mailing, i profili target sono quelli che verranno inclusi nel file di estrazione che invierai al tuo provider di direct mailing.

Per ciascun profilo target, viene aggiunta una nuova riga nel file di estrazione. La quantità di informazioni di profilo che verranno incluse per ciascun destinatario è indicata nella schermata [Definizione dell’estrazione](../../channels/using/defining-the-direct-mail-content.md#defining-the-extraction).

>[!IMPORTANT]
>
>Accertati che i profili includano un indirizzo postale, poiché queste informazioni sono essenziali per il provider di direct mailing. Inoltre, assicurati di aver selezionato la casella **[!UICONTROL Address specified]** nelle informazioni del profilo. Consulta [Consigli](../../channels/using/about-direct-mail.md#recommendations).

## Aggiunta di profili di test e di trappole {#adding-test-and-trap-profiles}

Aggiungi i profili di test in modo da poter testare il file con un numero limitato di profili. Ciò ti consente di creare rapidamente un esempio di file per effettuare la verifica e la convalida della struttura, prima di passare alla preparazione del file effettivo. Consulta [Gestione dei profili di test](../../audiences/using/managing-test-profiles.md).

L’uso di trappole è essenziale per le consegne di direct mailing. Ti consentono di verificare che il provider di direct mailing stia inviando effettivamente la comunicazione e che non stia mandando il tuo elenco dei clienti a un altro provider. Consulta [Utilizzo delle “trappole”](../../sending/using/using-traps.md).

Per le consegne di direct mailing, le trappole vengono aggiunte durante l’estrazione e unite nel documento di output. Per impostazione predefinita, le trappole vengono inserite nell’ordinamento del file di output, ma è possibile inserirle alla fine o all’inizio del file. Quando definisci il pubblico, seleziona l’opzione desiderata dalla scheda **[!UICONTROL Trap insertion mode]**.

![](assets/direct_mail_trap_insertion_mode.png)
