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
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '345'
ht-degree: 1%

---

# Aggiunta di pannelli{#adding-panels}

## Aggiunta di un pannello vuoto {#adding-a-blank-panel}

Per avviare il rapporto, puoi aggiungere un set di pannelli a un rapporto predefinito o personalizzato. Ogni pannello contiene set di dati diversi ed è composto da tabelle a forma libera e visualizzazioni.

Questo pannello consente di generare i rapporti in base alle esigenze. Puoi aggiungere tutti i pannelli desiderati nei rapporti per filtrare i dati in base a periodi di tempo diversi.

1. Fai clic sul pulsante **Pannelli** icona. Puoi anche aggiungere un pannello facendo clic sul pulsante **Inserisci, scheda** e selezionando **Nuovo pannello vuoto**.

   ![](assets/dynamic_report_panel_1.png)

1. Trascina e rilascia la **Pannello vuoto** nel dashboard.

   ![](assets/dynamic_report_panel.png)

Ora puoi aggiungere una tabella a forma libera al pannello per avviare il targeting dei dati.

## Aggiunta di una tabella a forma libera {#adding-a-freeform-table}

Le tabelle a forma libera consentono di creare una tabella per analizzare i dati utilizzando le diverse metriche e dimensioni disponibili nel **Componente** tabella.

Ogni tabella e visualizzazione può essere ridimensionata e spostata per personalizzare meglio il rapporto.

1. Fai clic sul pulsante **[!UICONTROL Panels]** icona.

   ![](assets/dynamic_report_panel_1.png)

1. Trascina e rilascia la **[!UICONTROL Freeform]** nel dashboard.

   Puoi anche aggiungere una tabella facendo clic sul pulsante **[!UICONTROL Insert]** scheda e selezione **[!UICONTROL New Freeform]** o facendo clic su **[!UICONTROL Add a freeform table]** in un pannello vuoto.

   ![](assets/dynamic_report_panel_2.png)

1. In **[!UICONTROL Drop a segment here]** campo , aggiungi un **[!UICONTROL Segment]** dal **[!UICONTROL Components]** nella barra superiore.

   ![](assets/dynamic_report_panel_3.png)

1. Trascina e rilascia gli elementi dal **[!UICONTROL Components]** nelle colonne e nelle righe per creare la tabella.

   ![](assets/dynamic_report_freeform_3.png)

1. Fai clic sul pulsante **[!UICONTROL Settings]** per modificare la modalità di visualizzazione dei dati nelle colonne.

   ![](assets/dynamic_report_freeform_4.png)

   La **[!UICONTROL Column settings]** è composto da:

   * **[!UICONTROL Number]**: consente di visualizzare o nascondere i numeri di riepilogo nella colonna.
   * **[!UICONTROL Percent]**: consente di mostrare o nascondere la percentuale nella colonna.
   * **[!UICONTROL Interpret zero as no value]**: consente di mostrare o nascondere quando il valore è uguale a zero.
   * **[!UICONTROL Background]**: consente di mostrare o nascondere la barra di avanzamento orizzontale nelle celle.
   * **[!UICONTROL Include retries]**: consente di includere i nuovi tentativi nel risultato. Disponibile solo per **[!UICONTROL Sent]** e **[!UICONTROL Bounces + Errors]**.

1. Seleziona una o più righe e fai clic sul pulsante **[!UICONTROL Visualize]** icona. Viene aggiunta una visualizzazione per riflettere le righe selezionate.

   ![](assets/dynamic_report_freeform_5.png)

Ora puoi aggiungere tutti i componenti necessari e anche aggiungere visualizzazioni per fornire rappresentazioni grafiche dei tuoi dati.
