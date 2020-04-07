---
title: Gestione delle tipologie
description: Scopri come utilizzare le tipologie.
page-status-flag: never-activated
uuid: a98ebc36-172d-4f46-b6ee-b2636a1007c9
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: working-with-typology-rules
discoiquuid: 2590d94c-51ef-4c0f-b1ec-c2837e94da40
context-tags: typology,overview;typologyRule,main;typologyRule,overview
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: ec0af8c06e36f51ddaf6e3d4190fa6acd56d2da6

---


# Gestione delle tipologie {#managing-typologies}

## Informazioni sulle tipologie {#about-typologies}

Le tipologie sono insiemi di regole che consentono di verificare la validità del messaggio prima di inviarlo. Ad esempio: Il contenuto del messaggio non è vuoto, è presente un&#39;annullamento della sottoscrizione, l&#39;esclusione di duplicati, ecc.

Le tipologie sono accessibili tramite il menu **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Typologies]** . Per impostazione predefinita, nell’applicazione è disponibile una tipologia predefinita. In base alle vostre esigenze, potete creare tipologie personalizzate o modificare quelle esistenti.

![](assets/typologies-list.png)

Per ogni tipologia, la **[!UICONTROL Typology rules]** sezione elenca il set di regole che vengono eseguite quando si utilizza la tipologia con un messaggio.

![](assets/typology_typo-rule-list.png)

>[!NOTE]
>
>Per visualizzare ulteriori dettagli su una delle regole di tipologia, fare doppio clic su di essa. La regola viene visualizzata in modalità di sola lettura.

## Creazione di una tipologia {#creating-a-typology}

Per creare una nuova tipologia, procedere come segue:

1. Accedete al menu **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Typologies]** .

1. Viene visualizzato l&#39;elenco delle tipologie. Fate clic sul **[!UICONTROL Create]** pulsante.

   ![](assets/typologies-list.png)

1. Definite la tipologia **[!UICONTROL Label]**, quindi fate clic sul **[!UICONTROL Add an element]** pulsante per selezionare le regole di tipologia che desiderate includere in essa. For more on typology rules, refer to [this section](../../sending/using/managing-typology-rules.md).

   ![](assets/typology_addrules.png)

   >[!NOTE]
   >
   >Il **[!UICONTROL IP affinity]** campo consente di gestire le affinità in base alla configurazione. Sono definiti nel file di configurazione dell&#39;istanza. Se desiderate utilizzare le affinità, contattate l&#39;amministratore.

1. Fate clic **[!UICONTROL Create]** per confermare la selezione. La tipologia è ora pronta per essere utilizzata nei messaggi.

## Applicazione delle tipologie ai messaggi {#applying-typologies-to-messages}

Quando si associa una tipologia a un modello di messaggio o messaggio, le regole di tipologia incluse nella tipologia vengono eseguite per verificare la validità del messaggio.

>[!NOTE]
>
>A ogni modello di messaggio o di messaggio può essere assegnata una sola tipologia.

Per collegare una tipologia a un messaggio, effettua le seguenti operazioni:

1. Accedere alle proprietà del messaggio. I modelli di messaggio sono accessibili dal menu di **[!UICONTROL Resources]** > **[!UICONTROL Templates]** navigazione.

1. Nella sezione **[!UICONTROL Advanced parameters]** > **[!UICONTROL Prearation]** , seleziona la tipologia di collegamento al messaggio.

   ![](assets/typology_message.png)

1. Clic **[!UICONTROL Confirm]**.

   La tipologia selezionata è ora collegata al messaggio. Tutte le relative regole di tipologia associate verranno eseguite per verificare la validità del messaggio.
