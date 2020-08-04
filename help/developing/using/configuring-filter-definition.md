---
title: Configurazione della definizione del filtro
description: Scopri la funzione filtro per gestire set di dati di grandi dimensioni.
page-status-flag: never-activated
uuid: c9db95fe-e9aa-40f8-9c0a-e74bb21ac14b
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: adding-or-extending-a-resource
discoiquuid: 993ab2bd-e05f-468e-9ef8-a603761247f8
context-tags: cusResource,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: cabe064632c9c2e3de93bc1cff6fa217b4fdf3e6
workflow-type: tm+mt
source-wordcount: '541'
ht-degree: 95%

---


# Configurazione della definizione del filtro{#configuring-filter-definition}

Nella scheda **[!UICONTROL Filter definition]** puoi creare filtri avanzati accessibili direttamente dagli utenti durante la creazione di query complesse, ad esempio durante la definizione di un pubblico.

Questo passaggio non è obbligatorio in quanto puoi comunque popolare la risorsa e accedere ai relativi dati tramite flussi di lavoro, tipi di pubblico e API REST.

![](assets/custom_resource_filter-definition.png)

Questi filtri vengono utilizzati nell’editor delle query sotto forma di regole preconfigurate. Ti consentono di limitare il numero di passaggi necessari per ottenere la configurazione desiderata, particolarmente utile per segmentazioni ripetitive.

Ad esempio, puoi creare un filtro che consenta di selezionare tutte le transazioni superiori a un determinato importo negli ultimi tre mesi.

A tal fine, devi estendere la risorsa **[!UICONTROL Profiles]** e definire un filtro per il collegamento a una tabella di transazione (creata in precedenza) con una regola indicante che il prezzo della transazione deve essere maggiore o uguale a un dato parametro e che la data della transazione deve rientrare in un intervallo corrispondente agli ultimi tre mesi.

1. Assicurati di creare e pubblicare una tabella delle transazioni. Consulta [Creazione o estensione della risorsa](../../developing/using/creating-or-extending-the-resource.md).

   >[!NOTE]
   >
   >Questa procedura utilizza l’esempio di una tabella di transazioni personalizzata. Adattala alle esigenze aziendali in base al tuo caso.

1. Prima di definire un filtro correlato alla tabella delle transazioni nella risorsa **[!UICONTROL Profiles]**, accertati di definire il collegamento a questa tabella e pubblicare le modifiche. Consulta [Definizione dei collegamenti con altre risorse](../../developing/using/configuring-the-resource-s-data-structure.md#defining-links-with-other-resources) e [Aggiornamento della struttura del database](../../developing/using/updating-the-database-structure.md).
1. Nella scheda **[!UICONTROL Definition]** della schermata di definizione del nuovo filtro, seleziona la tabella delle transazioni.

   ![](assets/custom_resource_filter-definition_example-empty.png)

1. Nella finestra **[!UICONTROL Add a rule - Profiles/Transactions]**, trascina e rilascia la tabella delle transazioni nell’area di lavoro. Nella finestra successiva visualizzata, seleziona il campo da utilizzare.

   ![](assets/custom_resource_filter-definition_example-field.png)

1. Nelle **[!UICONTROL Optional parameter settings]** della finestra **[!UICONTROL Add a rule - Transactions]**, seleziona la casella **[!UICONTROL Switch to parameters]**.

   Nelle **[!UICONTROL Filter conditions]**, seleziona l’operatore **[!UICONTROL Greater than or equal to]**. Nel campo **[!UICONTROL Parameters]**, immetti un nome e fai clic sul segno più per creare il nuovo parametro.

   ![](assets/custom_resource_filter-definition_example-parameter.png)

1. Conferma le modifiche. Questa definizione corrisponde a un campo configurabile che l’utente deve compilare in un secondo momento per eseguire la query.

   ![](assets/custom_resource_filter-definition_ex_edit-rule.png)

1. Combina questa regola con un’altra regola specificando che la data della transazione deve rientrare in un intervallo corrispondente agli ultimi tre mesi.

   ![](assets/custom_resource_filter-definition_example.png)

1. Scegli la categoria in cui viene visualizzato il filtro.

   ![](assets/custom_resource_filter-definition_category.png)

1. Nella scheda **[!UICONTROL Parameters]** della schermata di definizione del filtro, modifica la descrizione e l’etichetta per indicare chiaramente agli utenti l’oggetto del filtro. Queste informazioni vengono visualizzate nell’editor delle query.

   ![](assets/custom_resource_filter-definition_parameters.png)

   Se definisci più campi configurabili, puoi modificarne l’ordine di visualizzazione nell’interfaccia.

1. Salva le modifiche e pubblica le risorse. Per ulteriori informazioni, consulta la sezione [Aggiornamento della struttura del database](../../developing/using/updating-the-database-structure.md).

Dopo la pubblicazione dell’estensione della risorsa **[!UICONTROL Profiles]**, gli utenti visualizzano questo filtro nella scheda dei tasti di scelta rapida nell’interfaccia dell’[editor delle query](../../automating/using/editing-queries.md).

In questo modo, l’utente può definire facilmente il pubblico durante la creazione di un’e-mail da inviare a tutti i clienti che hanno speso più di un certo importo negli ultimi tre mesi.

![](assets/custom_resource_filter-definition_email-audience.png)

Anziché configurarlo personalmente, deve semplicemente immettere la quantità desiderata nella finestra di dialogo visualizzata.

![](assets/custom_resource_filter-definition_email-audience_filter.png)

Una volta configurato un filtro, puoi utilizzarlo dalle API Campaign Standard utilizzando la sintassi seguente:

`GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/<resourceName>/by<customFilterName>?<customFilterparam>=<customFilterValue>`

Per ulteriori informazioni, consulta la documentazione [API](../../api/using/filtering.md#custom-filters)Campaign Standard.
