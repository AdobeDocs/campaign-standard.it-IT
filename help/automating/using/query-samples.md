---
title: Esempi di query
description: In questa sezione viene illustrato l'utilizzo di un'attività Query.
page-status-flag: never-activated
uuid: b3c629fa-370e-481c-b347-fcf9f5a5e847
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 8d46ce28-0101-4f13-865a-2208ed6d6139
context-tags: query,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 2d994d85f126951215f1227301599c554c1f12c8
workflow-type: tm+mt
source-wordcount: '334'
ht-degree: 0%

---


# Esempi di query {#query-samples}

In questa sezione viene illustrato il caso di utilizzo di un&#39; **[!UICONTROL Query]** attività. Per ulteriori informazioni sull&#39;utilizzo di un&#39; **[!UICONTROL Query]** attività, consultate [questa sezione](../../automating/using/query.md).

## Targeting su attributi di profilo semplici {#targeting-on-simple-profile-attributes}

L&#39;esempio seguente mostra un&#39;attività di query configurata per gli uomini tra i 18 e i 30 anni che vivono a Londra.

![](assets/query_sample_1.png)

## Targeting degli attributi e-mail {#targeting-on-email-attributes}

L&#39;esempio seguente mostra un&#39;attività di query configurata per i profili di destinazione con il dominio dell&#39;indirizzo e-mail &quot;orange.co.uk&quot;.

![](assets/query_sample_emaildomain.png)

L&#39;esempio seguente mostra un&#39;attività di query configurata per i profili di destinazione il cui indirizzo e-mail è stato fornito.

![](assets/query_sample_emailnotempty.png)

## Profili di targeting il cui compleanno è oggi {#targeting-profiles-whose-birthday-is-today}

L&#39;esempio seguente mostra un&#39;attività di query configurata per il targeting dei profili il cui compleanno è oggi.

1. Trascinate il **[!UICONTROL Birthday]** filtro nella query.

   ![](assets/query_sample_birthday.png)

1. Impostare **[!UICONTROL Filter type]** su **[!UICONTROL Relative]** e selezionare **[!UICONTROL Today]**.

   ![](assets/query_sample_birthday2.png)

## Profili di destinazione che hanno aperto una consegna specifica {#targeting-profiles-who-opened-a-specific-delivery}

L&#39;esempio seguente mostra un&#39;attività di query configurata per filtrare i profili che hanno aperto la consegna con l&#39;etichetta &quot;Ora legale&quot;.

1. Trascinate il **[!UICONTROL Opened]** filtro nella query.

   ![](assets/query_sample_opened.png)

1. Selezionate la consegna e fate clic su **[!UICONTROL Confirm]**.

   ![](assets/query_sample_opened2.png)

## Targeting dei profili per i quali le consegne non sono riuscite per un motivo specifico {#targeting-profiles-for-whom-deliveries-failed-for-a-specific-reason}

L&#39;esempio seguente mostra un&#39;attività di query configurata per filtrare i profili per i quali le consegne non sono riuscite a causa della piena cassetta postale. Questa query è disponibile solo per gli utenti con diritti di amministrazione e appartenenti alle unità **[!UICONTROL All (all)]** organizzative (vedere [questa sezione](../../administration/using/organizational-units.md)).

1. Selezionate la **[!UICONTROL Delivery logs]** risorsa per filtrare direttamente nella tabella del registro di distribuzione (consultate [Utilizzo di risorse diverse dalle dimensioni](../../automating/using/using-resources-different-from-targeting-dimensions.md)di targeting).

   ![](assets/query_sample_failure1.png)

1. Trascinate il **[!UICONTROL Nature of failure]** filtro nella query.

   ![](assets/query_sample_failure2.png)

1. Selezionare il tipo di errore che si desidera eseguire. Nel nostro caso **[!UICONTROL Mailbox full]**.

   ![](assets/query_sample_failure3.png)

## Profili di destinazione non contattati negli ultimi 7 giorni {#targeting-profiles-not-contacted-during-the-last-7-days}

L&#39;esempio seguente mostra un&#39;attività di query configurata per filtrare i profili che non sono stati contattati negli ultimi 7 giorni.

1. Trascinate il **[!UICONTROL Delivery logs (logs)]** filtro nella query.

   ![](assets/query_sample_7days.png)

   Selezionate **[!UICONTROL Does not exist]** nell’elenco a discesa, quindi trascinate il **[!UICONTROL Delivery]** filtro.

   ![](assets/query_sample_7days1.png)

1. Configura il filtro come indicato di seguito.

   ![](assets/query_sample_7days2.png)

## Profili di destinazione che hanno fatto clic su un collegamento specifico {#targeting-profiles-who-clicked-a-specific-link-}

1. Trascinate il **[!UICONTROL Tracking logs (tracking)]** filtro nella query.

   ![](assets/query_sample_trackinglogs.png)

1. Trascinate il **[!UICONTROL Label (urlLabel)]** filtro.

   ![](assets/query_sample_trackinglogs2.png)

1. Nel **[!UICONTROL Value]** campo digitare l&#39;etichetta definita al momento dell&#39;inserimento del collegamento nella consegna, quindi confermare.

   ![](assets/query_sample_trackinglogs3.png)
