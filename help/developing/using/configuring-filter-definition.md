---
title: Configurazione definizione filtro
seo-title: Configurazione definizione filtro
description: Configurazione definizione filtro
seo-description: Scopri la funzionalità filtro per gestire grandi set di dati.
page-status-flag: never-activated
uuid: c 9 db 95 fe-e 9 aa -40 f 8-9 c 0 a-e 74 bb 21 ac 14 b
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: sviluppo
content-type: riferimento
topic-tags: adding-or-extending-a-resource
discoiquuid: 993 ab 2 bd-e 05 f -468 e -9 ef 8-a 603761247 f 8
context-tags: Cusresource, main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 806dc4736ffb395a0eea102090c688102478aaca

---


# Configuring filter definition{#configuring-filter-definition}

In the **[!UICONTROL Filter definition]** tab, you can create advanced filters that users can directly access when creating complex queries, such as when defining an audience.

Questo passaggio non è obbligatorio in quanto sarà ancora in grado di compilare la risorsa e di accedere ai dati tramite flussi di lavoro, audience e REST API.

![](assets/custom_resource_filter-definition.png)

Questi filtri vengono utilizzati nell'editor query sotto forma di regole pre-configurate. Consentono di limitare il numero di passaggi necessari per ottenere la configurazione desiderata, che può essere particolarmente utile per le segmentazioni ripetitive.

Ad esempio, potete creare un filtro che consente di selezionare tutte le transazioni più grandi di una certa quantità negli ultimi tre mesi.

To do this, you need to extend the **[!UICONTROL Profiles]** resource and define a filter linking to a transaction table (that you have previously created) with a rule indicating that the transaction price must be greater than or equal to a given parameter and that the transaction date must fall within a range corresponding to the last three months.

1. Assicurati di creare e pubblicare una tabella delle transazioni. See [Creating or extending the resource](../../developing/using/creating-or-extending-the-resource.md).

   >[!NOTE]
   >
   >Questa procedura utilizza l'esempio di una tabella delle transazioni personalizzata. Per la vostra pratica, regolatela in base alle vostre esigenze aziendali.

1. Before defining a filter related to the transaction table in the **[!UICONTROL Profiles]** resource, make sure you define the link to this table and publish your changes. See [Defining links with other resources](../../developing/using/configuring-the-resource-s-data-structure.md#defining-links-with-other-resources) and [Updating the database structure](../../developing/using/updating-the-database-structure.md).
1. In the **[!UICONTROL Definition]** tab of your new filter's definition screen, select the transaction table.

   ![](assets/custom_resource_filter-definition_example-empty.png)

1. In the **[!UICONTROL Add a rule - Profiles/Transactions]** window, drag and drop the transaction table into the workspace. Nella finestra successiva visualizzata, selezionate il campo da utilizzare.

   ![](assets/custom_resource_filter-definition_example-field.png)

1. In the **[!UICONTROL Optional parameter settings]** of the **[!UICONTROL Add a rule - Transactions]** window, check the **[!UICONTROL Switch to parameters]** box.

   In the **[!UICONTROL Filter conditions]**, select the **[!UICONTROL Greater than or equal to]** operator. In the **[!UICONTROL Parameters]** field, enter a name and click the plus sign to create the new parameter.

   ![](assets/custom_resource_filter-definition_example-parameter.png)

1. Confermate le modifiche. Questa definizione corrisponde a un campo configurabile che l'utente deve compilare successivamente per eseguire la query.

   ![](assets/custom_resource_filter-definition_ex_edit-rule.png)

1. Combinate questa regola con un'altra regola che specifica che la data della transazione deve rientrare in un intervallo corrispondente agli ultimi tre mesi.

   ![](assets/custom_resource_filter-definition_example.png)

1. Scegliete la categoria in cui verrà visualizzato il filtro.

   ![](assets/custom_resource_filter-definition_category.png)

1. In the **[!UICONTROL Parameters]** tab of the filter definition screen, modify the description and the label to clearly indicate the subject of your filter to the users. Queste informazioni vengono visualizzate nell'editor query.

   ![](assets/custom_resource_filter-definition_parameters.png)

   Se definite più campi configurabili, potete modificare l'ordine in cui compaiono nell'interfaccia.

1. Salvate le modifiche e pubblicate le risorse. For more on this, refer to the [Updating the database structure](../../developing/using/updating-the-database-structure.md) section.

Once the **[!UICONTROL Profiles]** resource extension is published, the users will see this filter under the shortcuts tab in the [query editor](../../automating/using/editing-queries.md) interface.

Questo consentirà all'utente di definire facilmente il pubblico quando si crea un messaggio e-mail da inviare a tutti i client che hanno speso più di una certa quantità negli ultimi tre mesi.

![](assets/custom_resource_filter-definition_email-audience.png)

Anziché configurare autonomamente il modulo, è sufficiente immettere l'importo desiderato nella finestra di dialogo visualizzata.

![](assets/custom_resource_filter-definition_email-audience_filter.png)

