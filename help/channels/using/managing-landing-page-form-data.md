---
title: Gestione dei dati del modulo della pagina di destinazione
description: Scopri come gestire i dati del modulo della pagina di destinazione.
audience: channels
content-type: reference
topic-tags: landing-pages
context-tags: landingPage,main
feature: Landing Pages
role: User
level: Intermediate
exl-id: 7083447c-4cac-41cb-8453-369819e0c7c1
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '835'
ht-degree: 15%

---

# Gestione dei dati del modulo della pagina di destinazione{#managing-landing-page-form-data}

Nel contenuto della pagina di destinazione, i campi di input vengono utilizzati per memorizzare o aggiornare i dati dal database di Campaign.

A questo scopo, questi campi devono essere mappati ai campi del database.

Puoi definirne e gestirne la mappatura tramite il **[!UICONTROL Form data]** nella palette a sinistra.

![](assets/lp_form-data.png)

## Mappatura dei campi del modulo {#mapping-form-fields}

Per aggiornare il database di Campaign in base alle tue esigenze, collega i campi del database rilevanti ai blocchi di zona di input, pulsante di scelta o tipo di casella di controllo della pagina di destinazione.

A tale scopo, segui la procedura indicata di seguito:

1. Seleziona un blocco nel contenuto della pagina di destinazione.

   >[!NOTE]
   >
   >I campi predefiniti delle pagine di destinazione incorporate sono preconfigurati. Puoi modificarli, se necessario.

1. Accedere a **[!UICONTROL Form data]** nella palette a sinistra.

1. Per modificare il tipo di campo, selezionare un valore dal campo **[!UICONTROL HTML type of the field]** elenco a discesa.

   ![](assets/lp_html-field-type.png)

   >[!NOTE]
   >
   >Per ulteriori informazioni sull’utilizzo del tipo di casella di controllo in una pagina di destinazione, consulta [Aggiornare più abbonamenti ai servizi](#multiple-subscriptions) e [Casella di controllo Contratto](#agreement-checkbox) sezioni.

1. Se si seleziona un tipo di campo non compatibile con il campo del database attualmente selezionato nel **[!UICONTROL Field]** viene visualizzato un messaggio di avvertenza. Per una mappatura ottimale, seleziona un valore appropriato.

   ![](assets/lp_field-type-warning.png)

1. Utilizza il **[!UICONTROL Field]** per selezionare un campo del database che verrà collegato al campo del modulo.

   ![](assets/lp_select-database-field.png)

   >[!NOTE]
   >
   >Le pagine di destinazione possono essere mappate solo con **[!UICONTROL Profiles]** o **[!UICONTROL Service]** risorse.

   In questo esempio, mappa il **Nome** della pagina di destinazione al **[!UICONTROL Last name]** campo del **[!UICONTROL Profiles]** risorsa.

   ![](assets/lp_database-field-example.png)

1. Se necessario, seleziona l’opzione **[!UICONTROL Mandatory]**. In tal caso, la pagina di destinazione può essere inviata solo se l’utente ha compilato questo campo.

   ![](assets/lp_mandatory-option.png)

   Se non viene compilato un campo obbligatorio, quando l’utente invia la pagina viene visualizzato un messaggio di errore.

1. Clic **[!UICONTROL Confirm]** per salvare le modifiche.

<!--If you choose a mandatory **[!UICONTROL Checkbox]**, make sure that it is of **[!UICONTROL Field]** type.-->

## Archiviazione e riconciliazione dei dati{#data-storage-and-reconciliation}

I parametri di riconciliazione dei dati ti consentono di definire come gestire i dati immessi nella pagina di destinazione dopo che un utente li ha inviati.

Per eseguire questa operazione:

1. Modifica le proprietà della pagina di destinazione accessibili tramite l’icona ![](assets/edit_darkgrey-24px.png) presente nel dashboard della pagina di destinazione, quindi visualizza i parametri **[!UICONTROL Job]**.

   ![](assets/lp_parameters_job.png)

1. Seleziona la **[!UICONTROL Reconciliation key]**: questo campo del database viene utilizzato per determinare se il visitatore dispone di un profilo già noto nel database di Adobe Campaign. Può essere ad esempio e-mail, nome, cognome. La chiave di riconciliazione ti consente di aggiornare o creare un profilo, in base al **[!UICONTROL Update strategy]** parametro definito di seguito.

1. Definisci la **[!UICONTROL Form parameter mapping]**: in questa sezione puoi mappare i parametri dei campi della pagina di destinazione e quelli utilizzati nella chiave di riconciliazione.

1. Seleziona la **[!UICONTROL Update strategy]**: se la chiave di riconciliazione recupera un profilo di database esistente, puoi scegliere di aggiornarlo con i dati immessi nel modulo oppure impedirne l’aggiornamento.

   ![](assets/lp_parameters_update-strategy.png)

## Più abbonamenti a servizi {#multiple-subscriptions}

Puoi utilizzare diverse caselle di controllo in una singola pagina di destinazione per consentire agli utenti di abbonarsi o annullare l’abbonamento a più servizi.

A tale scopo, segui la procedura indicata di seguito:

1. Durante la progettazione della pagina di destinazione:

   * Seleziona un blocco e, dalla **[!UICONTROL Form data]** , scegliere **[!UICONTROL Checkbox]** come tipo di campo.

     ![](assets/lp_field-type-checkbox.png)

   * Se conosci HTML, puoi anche inserire manualmente una casella di controllo utilizzando **[!UICONTROL Show source]** pulsante.

     ![](assets/lp_show_source.png)

     Questo consente di inserire la casella di controllo nella pagina dove necessario.

     ![](assets/lp_manual-checkbox.png)

1. Assicurati che la casella di controllo sia selezionata nel contenuto. Il **[!UICONTROL Type]** viene visualizzato nell&#39;elenco a discesa **[!UICONTROL Form data]** nella palette a sinistra. Seleziona **[!UICONTROL Service and subscription]** dall&#39;elenco.

   ![](assets/lp_service-and-subscription.png)

1. Scegli un&#39;opzione dalla **[!UICONTROL Behavior]** elenco a discesa.

   ![](assets/lp_checkbox-behavior.png)

1. Seleziona un [servizio](../../audiences/using/creating-a-service.md) dall’elenco corrispondente.

   ![](assets/lp_checkbox-service.png)

1. Assicurati che le **[!UICONTROL Mandatory]** è deselezionata. In caso contrario, gli utenti non avranno scelta.

   ![](assets/lp_uncheck-mandatory.png)

1. Per aggiungere altre caselle di controllo che consentono di abbonarsi ad altri servizi, ripeti i passaggi precedenti ogni volta che è necessario.

   ![](assets/lp_multiple-checkboxes.png)

Dopo la pubblicazione della pagina di destinazione, gli utenti possono selezionare più caselle di controllo per sottoscrivere diverse newsletter dalla stessa pagina.

## Casella di controllo Contratto {#agreement-checkbox}

Puoi aggiungere una casella di controllo che il profilo deve controllare prima di inviare la pagina di destinazione.

Ad esempio, questo ti consente di richiedere il consenso degli utenti per l’informativa sulla privacy o di chiedere loro di accettare i tuoi termini e condizioni prima di inviare il modulo.

>[!IMPORTANT]
>
>La selezione di questa casella di controllo è obbligatoria per gli utenti. Se non viene selezionata, non potrà inviare la pagina di destinazione.

Per inserire e configurare questa casella di controllo, effettuare le seguenti operazioni:

1. Durante la progettazione della pagina di destinazione:

   * Seleziona un blocco e, dalla **[!UICONTROL Form data]** , scegliere **[!UICONTROL Checkbox]** come tipo di campo.

     ![](assets/lp_field-type-checkbox.png)

   * Se conosci HTML, puoi anche inserire manualmente una casella di controllo utilizzando **[!UICONTROL Show source]** pulsante.

     ![](assets/lp_show_source.png)

     <!--Manually insert a checkbox, such as in the example below:

      <!--Click **[!UICONTROL Hide source]**.-->

1. Assicurati che la casella di controllo sia selezionata.

   ![](assets/lp_select_checkbox.png)

1. Il **[!UICONTROL Type]** viene visualizzato nell&#39;elenco a discesa **[!UICONTROL Form data]** nella palette a sinistra. Seleziona **[!UICONTROL Agreement]** dall&#39;elenco.

   ![](assets/lp_form_data_drop-down.png)

   >[!NOTE]
   >
   >Il **[!UICONTROL Agreement]** non è mappato a un campo del database Campaign.

1. Fai clic su ![](assets/lp-properties-icon.png) icona accanto a **[!UICONTROL Form data]** per accedere alla casella di controllo proprietà avanzate.

1. Se necessario, puoi modificare il messaggio.

   ![](assets/lp_agreement_message.png)

   Questo testo verrà visualizzato come avviso se l’utente non seleziona la casella di controllo prima di inviare il modulo.

   >[!NOTE]
   >
   >Questa azione è obbligatoria per impostazione predefinita e non può essere modificata.

1. Fai clic su **[!UICONTROL Confirm]**.

Ora, ogni volta che viene visualizzata la pagina di destinazione, l’utente deve selezionare questa casella di controllo prima di inviare il modulo. In caso contrario, verrà visualizzato l’avviso e l’utente non potrà inviare il modulo finché la casella di controllo non viene attivata.