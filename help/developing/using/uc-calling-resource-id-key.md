---
title: Chiamata di una risorsa utilizzando una chiave di identificazione composita
seo-title: Chiamata di una risorsa utilizzando una chiave di identificazione composita
description: Chiamata di una risorsa utilizzando una chiave di identificazione composita
seo-description: Come richiamare una risorsa utilizzando una chiave di identificazione composita
translation-type: tm+mt
source-git-commit: 8aea0483bcb1b104e5bd2b13426a1ac590c8efaf

---


# Chiamata di una risorsa utilizzando una chiave di identificazione composita

In alcuni casi, potrebbe essere necessario definire per una risorsa una chiave di identificazione composta da due campi. Una volta configurato la chiave di identificazione, è necessario configurare una definizione di filtro per essere in grado di richiamare la risorsa con questa chiave di identificazione, dall'interfaccia di Campaign Standard o dalle API.

In this use case, the **Profile** resource has been extended with custom **"CRM ID"** and **"category"** field. Creeremo una chiave di identificazione per la risorsa Profilo che sarà composta da questi due campi. Configureremo quindi una definizione di filtro per accedere alla risorsa Profilo utilizzando la chiave di identificazione.

I passaggi principali per questo caso d'uso sono:

1. Configurate la chiave di identificazione per la risorsa Profilo, in base ai due campi.
1. Configurate la definizione del filtro, in modo da poter richiamare la risorsa Profile utilizzando la relativa chiave di identificazione.
1. Chiama la risorsa Profilo dall'interfaccia o dalle API.

Argomenti correlati:

* [Creazione o estensione della risorsa](../../developing/using/creating-or-extending-the-resource.md)
* [Definizione delle chiavi di identificazione](../../developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys)
* [API REST di Campaign Standard](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html)

## Passaggio 1: Configurare la chiave di identificazione

>[!NOTE]
> Global concepts when configuring identification keys are detailed in [this section](../../developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys).

1. Prima di configurare la chiave di identificazione, accertatevi che la risorsa sia stata estesa con i campi desiderati e che sia stata pubblicata. For more on this, refer to [this section](../../developing/using/creating-or-extending-the-resource.md).

1. Go to the **[!UICONTROL Administration]** / **[!UICONTROL Developement]** / **[!UICONTROL Custom resources]** menu, then open the **[!UICONTROL Profile]** resource.

   ![](assets/uc_idkey1.png)

1. In the **[!UICONTROL Identification keys]** section, click the **[!UICONTROL Create element]** button.

   ![](assets/uc_idkey2.png)

1. Add the two custom "CRM ID" and "Category" fields, then click **[!UICONTROL Confirm]**.

   ![](assets/uc_idkey3.png)

   >[!NOTE]
   > If you want to display the two custom fields in the profile's interface, configure the **[!UICONTROL Screen definition]** tab. For more on this, refer to [this section](../../developing/using/configuring-the-screen-definition.md).

1. Ora potete configurare la definizione del filtro per poter chiamare la risorsa utilizzando la relativa chiave di identificazione.

## Passaggio 2: Configurare la definizione del filtro

>[!NOTE]
> Global concepts when configuring filter definitions are detailed in [this section](../../developing/using/configuring-filter-definition.md).

1. In the **[!UICONTROL Filter definition]** tab, click **[!UICONTROL Add an element]**, then enter the filter definition's label and ID.

1. Modificate le proprietà della definizione del filtro per configurarne le regole.

   ![](assets/uc_idkey4.png)

1. Trascinare nell'area di lavoro la tabella contenente i campi utilizzati nella chiave di identificazione.

   ![](assets/uc_idkey5.png)

1. Select the first field used in the identification key ("CRM ID"), then activate the **[!UICONTROL Switch to parameters]** option.

   ![](assets/uc_idkey6.png)

1. In the **[!UICONTROL Filter conditions]** section, keep the **[!UICONTROL Equal]** operator, then define the parameter's name and click the plus sign to create it.

   ![](assets/uc_idkey7.png)

   >[!NOTE]
   > Dopo aver fatto clic sul pulsante più, il nome del parametro viene generato automaticamente. Tenete presente queste informazioni, in quanto dovrete usare il filtro dalle API.

1. Ripetete i passaggi descritti qui sopra con tutti i campi che compongono la chiave di identificazione ("categoria"), quindi salvate le modifiche.

   ![](assets/uc_idkey8.png)

1. La definizione del filtro è ora configurata. Potete pubblicare la risorsa in modo che sia disponibile.

## Passaggio 3: Chiama la risorsa in base alla chiave di identificazione

Una volta configurata la chiave di identificazione e la relativa definizione del filtro, potete utilizzarle per chiamare la risorsa, dall'interfaccia standard Campaign o da REST API.

To use the filter definition from the interface, use a **[!UICONTROL Query]** activity in a workflow (see [this section](../../automating/using/query.md)). Il filtro è quindi disponibile nel riquadro a sinistra.

![](assets/uc_idkey9.png)

Per usare la definizione del filtro dalle API REST di Campaign Standard, utilizzate la sintassi seguente:

```
GET /profileAndServicesExt/&lt;resourceName&gt;&lt;filterName&gt;?&lt;param1_parameter&gt;=&lt;value&gt;&&lt;param2_parameter&gt;=&lt;value&gt;
```

Nel nostro caso, la sintassi per recuperare un profilo dalla categoria "spring" e con l'ID CRM "123456" sarà:

```
GET https://mc.adobe.io/&lt;ORGANIZATION&gt;/campaign/profileAndServicesExt/profile/identification_key?category_parameter=spring&crm_id_parameter=123456
```

For more details, refer to [Campaign Standard REST APIs documentation](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#filtering).