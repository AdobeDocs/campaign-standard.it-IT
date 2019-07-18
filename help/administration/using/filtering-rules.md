---
title: Regole di filtro
seo-title: Regole di filtro
description: Regole di filtro
seo-description: Usa regole di filtro per perfezionare l'audience dei messaggi.
page-status-flag: never-activated
uuid: ed 3 eea 62-3 a 47-4318-ae 22-d 82 aa 857448 f
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: administration
content-type: riferimento
topic-tags: working-with-typology-rules
discoiquuid: 7 ddaf 36 c -74 e 6-4501-b 3 eb -3 d 03 f 005 aaa 6
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Filtering rules{#filtering-rules}

Le regole di filtro consentono di escludere una parte della destinazione del messaggio in base ai criteri definiti in una query, ad esempio profili posti in quarantena o profili ai quali è già stato inviato un certo numero di messaggi e-mail.

Ad esempio, potete filtrare gli abbonati a newsletter in modo che gli abbonati di età inferiore a 18 anni non ricevano mai le comunicazioni.

## Creating a filtering rule {#creating-a-filtering-rule}

1. Create a **Filtering** typology rule, one that can be applied on all communication channels.

   ![](assets/typology_create-rule.png)

1. In the **[!UICONTROL Filtering criteria]** tab, select the subscriptions in the **[!UICONTROL Subscription]** category.

   ![](assets/typology_create-rule-subscription.png)

1. In the **[!UICONTROL Explorer]** tab of the query editor, drag and drop the **[!UICONTROL Subscriber]** node into the main part of the screen.

   ![](assets/typology_create-rule-subscriber.png)

1. Select the **[!UICONTROL Age]** field and define the filtering conditions so that the age of the subscribers is 18 or above.

   ![](assets/typology_create-rule-age.png)

1. In the **[!UICONTROL Typologies]** tab, link this rule to a typology.

   ![](assets/typology_create-rule-typology.png)

1. Accertatevi che la tipologia in questione sia selezionata nel modello di consegna che desiderate utilizzare.

   ![](assets/typology_template.png)

   >[!NOTE]
   >
   >To access the delivery templates, select **[!UICONTROL Resources]** &gt; **[!UICONTROL Templates]** in the navigation menu, which can be accessed via the Adobe Campaign logo.

Ogni volta che questa regola viene utilizzata in un messaggio, gli abbonati considerati minori verranno esclusi automaticamente.

## Restricting the applicability of a filtering rule {#restricting-the-applicability-of-a-filtering-rule}

Potete limitare l'applicabilità di una regola di filtro in base al messaggio da inviare.

1. In the typology rule's **[!UICONTROL Application criteria]** tab, uncheck the **[!UICONTROL Apply the rule on all deliveries]** option, which is enabled by default.

   ![](assets/typology_limit.png)

1. Utilizzate l'editor query per definire un filtro. Ad esempio, è possibile applicare la regola solo sui messaggi la cui etichetta inizia con una determinata parola o il cui ID contiene determinate lettere.

   ![](assets/typology_limit-rule.png)

In questo caso, la regola viene applicata solo ai messaggi che corrispondono ai criteri definiti.

## Default deliverability exclusion rules {#default-deliverability-exclusion-rules}

Two filtering rules are available by default: **[!UICONTROL Exclusion of addresses]** ( **[!UICONTROL addressExclusions]** ) and **[!UICONTROL Exclusion of domains]** ( **[!UICONTROL domainExclusions]** ). Durante l'analisi e-mail, queste regole confrontano gli indirizzi e-mail del destinatario con gli indirizzi vietati o i nomi di dominio contenuti in un elenco di soppressione globale crittografato gestito nell'istanza di consegna. In caso di corrispondenza, il messaggio non viene inviato a tale destinatario.

In modo da evitare di essere inseriti in blacklist a causa di attività dannose, in particolare per l'utilizzo di un'abbondanza. Ad esempio, se per l'iscrizione tramite uno dei moduli Web viene utilizzata una funzione di abbondanza, viene automaticamente inviato un messaggio e-mail di conferma in cui viene inviato automaticamente un messaggio di conferma.

>[!NOTE]
>
>Gli indirizzi e i nomi di dominio contenuti nell'elenco di soppressione globale sono nascosti. Nei registri di analisi della consegna viene indicato solo il numero di destinatari esclusi.

