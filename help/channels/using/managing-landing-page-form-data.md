---
title: Gestione dei dati del modulo della pagina di destinazione
description: Scoprite come gestire i dati del modulo della pagina di destinazione.
page-status-flag: never-activated
uuid: 5b222ea2-6628-457f-a618-bfc0e5eb93dd
contentOwner: lemaitre
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: landing-pages
discoiquuid: 899c7152-f415-4df9-b4b4-5ff3470a4e32
context-tags: landingPage,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 95e01eb33097fc76caac3f4dd5f5591461b887cf

---


# Gestione dei dati del modulo della pagina di destinazione{#managing-landing-page-form-data}

## Modifica delle proprietà dei dati del modulo di una pagina di destinazione{#changing-a-landing-page-form-data-properties}

È possibile collegare i campi del database a aree di input, pulsanti di scelta o blocchi di tipo casella di controllo. A questo scopo, selezionare il blocco e inserire il blocco **[!UICONTROL Form data]** nella palette.

![](assets/delivery_content_9.png)

* La zona di input **Campo** consente di selezionare un campo di database da collegare al campo del modulo.
* L’opzione **Obbligatorio** consente di autorizzare l’invio della pagina solo se l’utente ha compilato il campo. Se non viene compilato un campo obbligatorio, verrà visualizzato un messaggio di errore.

## Mapping dei campi modulo {#mapping-form-fields}

I campi di input vengono utilizzati per memorizzare o aggiornare i dati nel database Campaign. A tal fine, è necessario collegare i campi del database con aree di input, pulsanti di scelta o blocchi di tipo casella di controllo. Per eseguire questa operazione:

1. Selezionare un blocco nella pagina di destinazione.
1. Completare la **[!UICONTROL Form data]** parte nella palette.

   ![](assets/editing_lp_content_4.png)

1. Scegliere un campo di database da collegare al campo modulo nella zona di **[!UICONTROL Field]** selezione.

   Quando l’ **[!UICONTROL Mandatory]** opzione è selezionata, la pagina può essere inviata solo se l’utente ha completato il campo. Se un campo obbligatorio non è completato, quando l'utente convalida la pagina viene visualizzato un messaggio di errore.

   >[!NOTE]
   >
   >Le pagine di destinazione possono essere mappate solo con **Profili**.

1. Definire il tipo di campo scegliendo, ad esempio **[!UICONTROL Text]**, **[!UICONTROL Number]** o **[!UICONTROL Date]** nell'area di **[!UICONTROL HTML type of the field]** selezione.

>[!NOTE]
>
>I campi predefiniti delle pagine di destinazione incorporate sono preconfigurati. Potete modificarle come necessario.

## Archiviazione dei dati e riconciliazione{#data-storage-and-reconciliation}

I parametri di riconciliazione dei dati consentono di definire il modo in cui i dati immessi nella pagina di destinazione vengono gestiti una volta inviati da un utente.

Per eseguire questa operazione:

1. Modificate le proprietà della pagina di destinazione a cui accedete tramite l’ ![](assets/edit_darkgrey-24px.png) icona nel dashboard della pagina di destinazione e visualizzate i **[!UICONTROL Job]** parametri.

   ![](assets/lp_parameters_4.png)

1. Selezionate **[!UICONTROL Reconciliation key]**: questi campi del database (ad esempio: e-mail, nome e cognome) vengono utilizzati per determinare se il visitatore ha un profilo già noto nel database di Adobe Campaign. Questo consente di aggiornare o creare un profilo, in base ai parametri della strategia di aggiornamento definiti.
1. Definite il **[!UICONTROL Form parameter mapping]**: questa sezione consente di mappare i parametri dei campi della pagina di destinazione e quelli utilizzati nella chiave di riconciliazione.
1. Selezionate **[!UICONTROL Update strategy]**: se la chiave di riconciliazione recupera un profilo di database esistente, è possibile scegliere di aggiornarlo con i dati immessi nel modulo oppure impedire l'aggiornamento.
