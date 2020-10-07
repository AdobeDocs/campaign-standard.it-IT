---
title: Gestione dei dati del modulo della pagina di destinazione
description: Scopri come gestire i dati del modulo della pagina di destinazione.
page-status-flag: never-activated
uuid: 5b222ea2-6628-457f-a618-bfc0e5eb93dd
contentOwner: lemaitre
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: landing-pages
discoiquuid: 899c7152-f415-4df9-b4b4-5ff3470a4e32
context-tags: landingPage,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '394'
ht-degree: 100%

---


# Gestione dei dati del modulo della pagina di destinazione{#managing-landing-page-form-data}

## Modifica delle proprietà dei dati del modulo di una pagina di destinazione{#changing-a-landing-page-form-data-properties}

Puoi collegare i campi del database ad aree di input, pulsanti di scelta o blocchi di tipo casella di controllo. A questo scopo, nella palette, seleziona il blocco e inserisci i **[!UICONTROL Form data]**.

![](assets/delivery_content_9.png)

* La zona di input **Campo** ti consente di selezionare un campo di database da collegare a quello del modulo.
* L’opzione **Obbligatorio** ti consente di autorizzare l’invio della pagina solo se l’utente ha compilato il campo. Se non viene compilato un campo obbligatorio, viene visualizzato un messaggio di errore.

## Mappatura dei campi del modulo {#mapping-form-fields}

I campi di input vengono utilizzati per memorizzare o aggiornare i dati nel database Campaign. A questo scopo, devi collegare i campi del database con aree di input, pulsanti di scelta o blocchi di tipo casella di controllo. Per eseguire questa operazione:

1. Seleziona un blocco nella pagina di destinazione.
1. Nella palette, completa la parte **[!UICONTROL Form data]**.

   ![](assets/editing_lp_content_4.png)

1. Scegli un campo del database da collegare al campo del modulo nella zona di selezione **[!UICONTROL Field]**. È possibile mappare le pagine di destinazione solo con **Profili**.

1. Se necessario, seleziona l’opzione **[!UICONTROL Mandatory]**. È possibile inviare la pagina solo se l’utente ha completato questo campo. Se un campo obbligatorio è incompleto, viene visualizzato un messaggio di errore quando l’utente convalida la pagina.

1. Nell’area di selezione **[!UICONTROL HTML type of the field]**, definisci il tipo di campo scegliendo ad esempio **[!UICONTROL Text]**, **[!UICONTROL Number]** o **[!UICONTROL Date]**.
Se scegli una **[!UICONTROL Checkbox]** obbligatoria, accertati che sia di tipo **[!UICONTROL Field]**.

>[!NOTE]
>
>I campi predefiniti delle pagine di destinazione incorporate sono preconfigurati. Puoi modificarli, se necessario.

## Archiviazione e riconciliazione dei dati{#data-storage-and-reconciliation}

I parametri di riconciliazione dei dati ti consentono di definire come gestire i dati immessi nella pagina di destinazione dopo che un utente li ha inviati.

Per eseguire questa operazione:

1. Modifica le proprietà della pagina di destinazione accessibili tramite l’icona ![](assets/edit_darkgrey-24px.png) nel dashboard della pagina di destinazione e visualizza i parametri **[!UICONTROL Job]**.

   ![](assets/lp_parameters_4.png)

1. Seleziona la **[!UICONTROL Reconciliation key]**: questi campi del database (ad esempio: e-mail, nome e cognome) vengono utilizzati per determinare se è già presente un profilo del visitatore nel database di Adobe Campaign. In questo modo puoi aggiornare o creare un profilo, in base ai parametri definiti per la strategia di aggiornamento.
1. Definisci la **[!UICONTROL Form parameter mapping]**: in questa sezione puoi mappare i parametri dei campi della pagina di destinazione e quelli utilizzati nella chiave di riconciliazione.
1. Seleziona la **[!UICONTROL Update strategy]**: se la chiave di riconciliazione recupera un profilo di database esistente, puoi scegliere di aggiornarlo con i dati immessi nel modulo oppure impedirne l’aggiornamento.
