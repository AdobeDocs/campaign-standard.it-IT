---
title: Configurazione della definizione del filtro
description: Scoprite la funzione filtro per gestire set di dati di grandi dimensioni.
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
ht-degree: 1%

---


# Configurazione della definizione del filtro{#configuring-filter-definition}

Nella **[!UICONTROL Filter definition]** scheda è possibile creare filtri avanzati a cui gli utenti possono accedere direttamente quando creano query complesse, ad esempio quando definiscono un&#39;audience.

Questo passaggio non è obbligatorio in quanto potrai comunque compilare la risorsa e accedere ai suoi dati tramite flussi di lavoro, audience e REST API.

![](assets/custom_resource_filter-definition.png)

Questi filtri vengono utilizzati nell&#39;editor di query sotto forma di regole preconfigurate. Consentono di limitare il numero di passaggi necessari per ottenere la configurazione desiderata, che può essere particolarmente utile per le segmentazioni ripetitive.

Ad esempio, è possibile creare un filtro che consente di selezionare tutte le transazioni superiori a un determinato importo negli ultimi tre mesi.

A tal fine, è necessario estendere la **[!UICONTROL Profiles]** risorsa e definire un filtro per il collegamento a una tabella di transazione (creata in precedenza) con una regola che indica che il prezzo della transazione deve essere maggiore o uguale a un dato parametro e che la data della transazione deve rientrare in un intervallo corrispondente agli ultimi tre mesi.

1. Assicurati di creare e pubblicare una tabella delle transazioni. See [Creating or extending the resource](../../developing/using/creating-or-extending-the-resource.md).

   >[!NOTE]
   >
   >Questa procedura utilizza l&#39;esempio di una tabella di transazioni personalizzata. Per il tuo caso, adattalo alle tue esigenze aziendali.

1. Prima di definire un filtro correlato alla tabella delle transazioni nella **[!UICONTROL Profiles]** risorsa, accertatevi di definire il collegamento a questa tabella e pubblicare le modifiche. Consultate [Definizione di collegamenti con altre risorse](../../developing/using/configuring-the-resource-s-data-structure.md#defining-links-with-other-resources) e [Aggiornamento della struttura](../../developing/using/updating-the-database-structure.md)del database.
1. Nella **[!UICONTROL Definition]** scheda della schermata di definizione del nuovo filtro, seleziona la tabella delle transazioni.

   ![](assets/custom_resource_filter-definition_example-empty.png)

1. Nella **[!UICONTROL Add a rule - Profiles/Transactions]** finestra, trascinare la tabella delle transazioni nell&#39;area di lavoro. Nella finestra successiva visualizzata, selezionate il campo da utilizzare.

   ![](assets/custom_resource_filter-definition_example-field.png)

1. Nella **[!UICONTROL Optional parameter settings]** parte della **[!UICONTROL Add a rule - Transactions]** finestra, selezionare la **[!UICONTROL Switch to parameters]** casella.

   In **[!UICONTROL Filter conditions]**, selezionare l&#39; **[!UICONTROL Greater than or equal to]** operatore. Nel **[!UICONTROL Parameters]** campo, immettete un nome e fate clic sul segno più per creare il nuovo parametro.

   ![](assets/custom_resource_filter-definition_example-parameter.png)

1. Confermate le modifiche. Questa definizione corrisponde a un campo configurabile che l&#39;utente deve compilare in un secondo momento per eseguire la query.

   ![](assets/custom_resource_filter-definition_ex_edit-rule.png)

1. Combinate questa regola con un&#39;altra regola che specifica che la data della transazione deve rientrare in un intervallo corrispondente agli ultimi tre mesi.

   ![](assets/custom_resource_filter-definition_example.png)

1. Scegliete la categoria in cui verrà visualizzato il filtro.

   ![](assets/custom_resource_filter-definition_category.png)

1. Nella **[!UICONTROL Parameters]** scheda della schermata di definizione del filtro, modificate la descrizione e l’etichetta per indicare chiaramente agli utenti l’oggetto del filtro. Queste informazioni verranno visualizzate nell&#39;editor di query.

   ![](assets/custom_resource_filter-definition_parameters.png)

   Se si definiscono più campi configurabili, è possibile modificare l&#39;ordine in cui appaiono nell&#39;interfaccia.

1. Salvate le modifiche e pubblicate le risorse. Per ulteriori informazioni, vedere [Aggiornamento della struttura](../../developing/using/updating-the-database-structure.md) del database.

Una volta pubblicata l’estensione della **[!UICONTROL Profiles]** risorsa, gli utenti visualizzeranno questo filtro nella scheda dei collegamenti nell’interfaccia dell’editor [di](../../automating/using/editing-queries.md) query.

In questo modo l&#39;utente potrà definire facilmente il proprio pubblico quando creerà un&#39;e-mail da inviare a tutti i client che hanno trascorso più di un certo importo negli ultimi tre mesi.

![](assets/custom_resource_filter-definition_email-audience.png)

Anziché configurarlo personalmente, è sufficiente immettere la quantità desiderata nella finestra di dialogo visualizzata.

![](assets/custom_resource_filter-definition_email-audience_filter.png)

Una volta configurato un filtro, potete utilizzarlo dalle API Campaign Standard utilizzando la sintassi seguente:

`GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/<resourceName>/by<customFilterName>?<customFilterparam>=<customFilterValue>`

Per ulteriori informazioni, consulta la documentazione [API di](../../api/using/filtering.md#custom-filters)Campaign Standard.
