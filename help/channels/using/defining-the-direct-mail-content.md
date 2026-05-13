---
title: Definizione del contenuto della direct mailing
description: Scopri come definire il contenuto della consegna direct mailing.
audience: channels
content-type: reference
topic-tags: direct-mail
context-tags: delivery,directMailContent,back
feature: Direct Mail
role: User
level: Intermediate
exl-id: 0a4c45ea-acc2-424f-8596-73376e344172
TQID: https://experienceleague.adobe.com/Kt-KqyEadpziu8z5snOeg717epieMst36-gkdSt0Th8
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2: id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 337
ht-degree: 96%

---

# Definizione del contenuto del direct mailing{#defining-the-direct-mail-content}

Puoi definire il contenuto nell’ultima schermata della procedura guidata di creazione oppure facendo clic sulla sezione **Content** del dashboard della consegna.

![](assets/direct_mail_6.png)

La schermata di definizione **[!UICONTROL Content]** è specifica per il canale direct mailing. È divisa in quattro schede: **[!UICONTROL Extraction]**, **[!UICONTROL File structure]**, **[!UICONTROL Header]** e **[!UICONTROL Footer]**.

![](assets/direct_mail_11.png)

## Definizione dell’estrazione {#defining-the-extraction}

1. Inizia definendo il nome del file di estrazione. Fai clic sul pulsante a destra del campo **[!UICONTROL Output file]** e immetti l’etichetta desiderata. Puoi utilizzare campi di personalizzazione, blocchi di contenuto e testo dinamico (consulta [Definizione del contenuto](../../designing/using/personalization.md#example-email-personalization)). Ad esempio, puoi completare l’etichetta con l’ID di consegna o la data di estrazione.

   ![](assets/direct_mail_12.png)

1. Fai clic sul pulsante **[!UICONTROL +]** o su **[!UICONTROL Add an element]** per aggiungere una colonna di output. Le **[!UICONTROL Output columns]** ti permettono di definire le informazioni di profilo (colonne) da esportare nel file di output.

   >[!IMPORTANT]
   >
   >Accertati che i profili includano un indirizzo postale, poiché queste informazioni sono essenziali per il provider di direct mailing. Inoltre, assicurati di aver selezionato la casella **[!UICONTROL Address specified]** nelle informazioni del profilo. Consulta [Consigli](../../channels/using/about-direct-mail.md#recommendations).

   ![](assets/direct_mail_13.png)

1. Crea tutte le colonne necessarie. Puoi modificare le colonne facendo clic sulle relative espressioni ed etichette.

>[!NOTE]
>
>Per ulteriori informazioni sulla definizione della colonna di output, consulta la sezione dell’attività del flusso di lavoro [Extract file](../../automating/using/extract-file.md).

## Definizione della struttura del file {#defining-the-file-structure}

La scheda **File structure** ti consente di configurare i formati di output, data e numero per il file da esportare.

![](assets/direct_mail_14.png)

>[!NOTE]
>
>Le opzioni disponibili sono descritte dettagliatamente nelle sezioni dell’attività del flusso di lavoro [Extract file](../../automating/using/extract-file.md).

## Definizione di intestazione e piè di pagina {#defining-the-header-and-footer}

A volte potresti aver bisogno di aggiungere informazioni all’inizio o alla fine del file di estrazione. A questo scopo, utilizza le schede **[!UICONTROL Header]** e **[!UICONTROL Footer]** della schermata di configurazione **[!UICONTROL Content]**.

![](assets/direct_mail_7.png)

Ad esempio, potresti voler includere, per il provider di direct mailing, le informazioni sul mittente nell’intestazione del file. È possibile personalizzare il piè di pagina e l’intestazione con le informazioni disponibili nell’ambito della consegna. Consulta [Definizione del contenuto](../../designing/using/personalization.md#example-email-personalization).

L’indirizzo del mittente è definito nella sezione **[!UICONTROL Send]** delle proprietà della direct mailing o a livello di modello.

![](assets/direct_mail_24.png)
