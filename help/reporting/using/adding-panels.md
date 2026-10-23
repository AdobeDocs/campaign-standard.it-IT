---
title: Aggiunta di pannelli
description: Il rapporto dinamico ti consente di aggiungere un pannello per filtrare meglio i dati in base al periodo di tempo scelto.
audience: reporting
content-type: reference
topic-tags: customizing-reports
feature: Reporting
role: Leader
level: Intermediate
exl-id: e48b9630-c5ce-4d5d-90e6-97b77fbe3d50
TQID: 'https://experienceleague.adobe.com/jQtNVS-IFlOGMS5RAfKfOU610fZGzLB2GjEWwOPJE84'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: c309ee4e-82e4-4f7e-b608-ef345678c34e
    internal-label: Dynamic reporting
subfeature_v2:
  - id: b3a4149f-2b3a-44d1-894e-e3ac4c77fb47
    internal-label: Reporting interface
role_v2:
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
    internal-label: Leader
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '345'
ht-degree: 1%
---
# Aggiunta di pannelli{#adding-panels}

## Aggiunta di un pannello vuoto {#adding-a-blank-panel}

Per avviare il rapporto, puoi aggiungere un set di pannelli a un rapporto predefinito o personalizzato. Ogni pannello contiene set di dati diversi ed è composto da tabelle e visualizzazioni a forma libera.

Questo pannello consente di creare i rapporti in base alle esigenze. Puoi aggiungere nei rapporti tutti i pannelli desiderati per filtrare i dati in base a diversi periodi di tempo.

1. Fai clic sull&#39;icona **Panels**. È inoltre possibile aggiungere un pannello facendo clic sulla **scheda Inserisci** e selezionando **Nuovo pannello vuoto**.

   ![](assets/dynamic_report_panel_1.png)

1. Trascina e rilascia il **pannello vuoto** nel dashboard.

   ![](assets/dynamic_report_panel.png)

Ora puoi aggiungere una tabella a forma libera al pannello per iniziare a eseguire il targeting dei dati.

## Aggiunta di una tabella a forma libera {#adding-a-freeform-table}

Le tabelle a forma libera consentono di creare una tabella per analizzare i dati utilizzando le diverse metriche e dimensioni disponibili nella tabella **Componente**.

Ogni tabella e visualizzazione è ridimensionabile e può essere spostata per personalizzare meglio il rapporto.

1. Fare clic sull&#39;icona **[!UICONTROL Panels]**.

   ![](assets/dynamic_report_panel_1.png)

1. Trascina e rilascia l&#39;elemento **[!UICONTROL Freeform]** nel dashboard.

   È inoltre possibile aggiungere una tabella facendo clic sulla scheda **[!UICONTROL Insert]** e selezionando **[!UICONTROL New Freeform]** oppure facendo clic su **[!UICONTROL Add a freeform table]** in un pannello vuoto.

   ![](assets/dynamic_report_panel_2.png)

1. Nel campo **[!UICONTROL Drop a segment here]**, aggiungi **[!UICONTROL Segment]** dalla scheda **[!UICONTROL Components]** nella barra superiore.

   ![](assets/dynamic_report_panel_3.png)

1. Trascinare gli elementi dalla scheda **[!UICONTROL Components]** nelle colonne e nelle righe per creare la tabella.

   ![](assets/dynamic_report_freeform_3.png)

1. Fare clic sull&#39;icona **[!UICONTROL Settings]** per modificare la modalità di visualizzazione dei dati nelle colonne.

   ![](assets/dynamic_report_freeform_4.png)

   **[!UICONTROL Column settings]** è composto da:

   * **[!UICONTROL Number]**: consente di mostrare o nascondere i numeri di riepilogo nella colonna.
   * **[!UICONTROL Percent]**: consente di mostrare o nascondere la percentuale nella colonna.
   * **[!UICONTROL Interpret zero as no value]**: consente di mostrare o nascondere quando il valore è uguale a zero.
   * **[!UICONTROL Background]**: consente di mostrare o nascondere la barra di avanzamento orizzontale nelle celle.
   * **[!UICONTROL Include retries]**: consente di includere nuovi tentativi nel risultato. Disponibile solo per **[!UICONTROL Sent]** e **[!UICONTROL Bounces + Errors]**.

1. Selezionare una o più righe e fare clic sull&#39;icona **[!UICONTROL Visualize]**. Viene aggiunta una visualizzazione per riflettere le righe selezionate.

   ![](assets/dynamic_report_freeform_5.png)

Ora puoi aggiungere tutti i componenti necessari e anche visualizzazioni per fornire rappresentazioni grafiche dei dati.
