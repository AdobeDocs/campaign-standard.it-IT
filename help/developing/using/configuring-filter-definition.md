---
title: Configurazione della definizione del filtro
description: Scopri la funzione filtro per gestire set di dati di grandi dimensioni.
page-status-flag: mai attivato
uuid: c9db95fe-e9aa-40f8-9c0a-e74bb21ac14b
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: development
content-type: reference
topic-tags: aggiunta o estensione di una risorsa
discoiquuid: 993ab2bd-e05f-468e-9ef8-a603761247f8
context-tags: cusResource,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Configurazione della definizione del filtro{#configuring-filter-definition}

Nella **[!UICONTROL Filter definition]** scheda è possibile creare filtri avanzati a cui gli utenti possono accedere direttamente quando creano query complesse, ad esempio quando definiscono un'audience.

Questo passaggio non è obbligatorio in quanto potrai comunque compilare la risorsa e accedere ai suoi dati tramite flussi di lavoro, audience e REST API.

![](assets/custom_resource_filter-definition.png)

Questi filtri vengono utilizzati nell'editor di query sotto forma di regole preconfigurate. Consentono di limitare il numero di passaggi necessari per ottenere la configurazione desiderata, che può essere particolarmente utile per le segmentazioni ripetitive.

Ad esempio, è possibile creare un filtro che consente di selezionare tutte le transazioni superiori a un determinato importo negli ultimi tre mesi.

A tal fine, è necessario estendere la **[!UICONTROL Profiles]** risorsa e definire un filtro per il collegamento a una tabella di transazione (creata in precedenza) con una regola che indica che il prezzo della transazione deve essere maggiore o uguale a un dato parametro e che la data della transazione deve rientrare in un intervallo corrispondente agli ultimi tre mesi.

1. Assicurati di creare e pubblicare una tabella delle transazioni. See [Creating or extending the resource](../../developing/using/creating-or-extending-the-resource.md).

   >[!NOTE]
   >
   >Questa procedura utilizza l'esempio di una tabella di transazioni personalizzata. Per il tuo caso, adattalo alle tue esigenze aziendali.

1. Prima di definire un filtro correlato alla tabella delle transazioni nella **[!UICONTROL Profiles]** risorsa, accertatevi di definire il collegamento a questa tabella e pubblicare le modifiche. Consultate [Definizione di collegamenti con altre risorse](../../developing/using/configuring-the-resource-s-data-structure.md#defining-links-with-other-resources) e [Aggiornamento della struttura](../../developing/using/updating-the-database-structure.md)del database.
1. Nella **[!UICONTROL Definition]** scheda della schermata Definizione del nuovo filtro, seleziona la tabella delle transazioni.

   ![](assets/custom_resource_filter-definition_example-empty.png)

1. Nella **[!UICONTROL Add a rule - Profiles/Transactions]** finestra, trascinare la tabella delle transazioni nell'area di lavoro. Nella finestra successiva visualizzata, selezionate il campo da utilizzare.

   ![](assets/custom_resource_filter-definition_example-field.png)

1. Nella **[!UICONTROL Optional parameter settings]** parte della **[!UICONTROL Add a rule - Transactions]** finestra, selezionare la **[!UICONTROL Switch to parameters]** casella.

   In **[!UICONTROL Filter conditions]**, selezionare l' **[!UICONTROL Greater than or equal to]** operatore. Nel **[!UICONTROL Parameters]** campo, immettete un nome e fate clic sul segno più per creare il nuovo parametro.

   ![](assets/custom_resource_filter-definition_example-parameter.png)

1. Confermate le modifiche. Questa definizione corrisponde a un campo configurabile che l'utente deve compilare in seguito per eseguire la query.

   ![](assets/custom_resource_filter-definition_ex_edit-rule.png)

1. Combinate questa regola con un'altra regola che specifica che la data della transazione deve rientrare in un intervallo corrispondente agli ultimi tre mesi.

   ![](assets/custom_resource_filter-definition_example.png)

1. Scegliete la categoria in cui verrà visualizzato il filtro.

   ![](assets/custom_resource_filter-definition_category.png)

1. Nella **[!UICONTROL Parameters]** scheda della schermata di definizione del filtro, modificate la descrizione e l’etichetta per indicare chiaramente agli utenti l’oggetto del filtro. Queste informazioni verranno visualizzate nell'editor di query.

   ![](assets/custom_resource_filter-definition_parameters.png)

   Se si definiscono più campi configurabili, è possibile modificare l'ordine di visualizzazione nell'interfaccia.

1. Salvate le modifiche e pubblicate le risorse. Per ulteriori informazioni, vedere [Aggiornamento della struttura](../../developing/using/updating-the-database-structure.md) del database.

Una volta pubblicata l’estensione della **[!UICONTROL Profiles]** risorsa, gli utenti visualizzeranno questo filtro nella scheda dei collegamenti nell’interfaccia dell’editor [di](../../automating/using/editing-queries.md) query.

Questo consente all'utente di definire facilmente il pubblico durante la creazione di un'e-mail da inviare a tutti i client che hanno trascorso più di un certo importo negli ultimi tre mesi.

![](assets/custom_resource_filter-definition_email-audience.png)

Anziché configurarlo personalmente, è sufficiente immettere la quantità desiderata nella finestra di dialogo visualizzata.

![](assets/custom_resource_filter-definition_email-audience_filter.png)

