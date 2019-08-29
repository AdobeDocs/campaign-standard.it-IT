---
title: Chiamata di una risorsa utilizzando una chiave di identificazione composita
seo-title: Chiamata di una risorsa utilizzando una chiave di identificazione composita
description: Chiamata di una risorsa utilizzando una chiave di identificazione composita
seo-description: Come richiamare una risorsa utilizzando una chiave di identificazione composita
translation-type: tm+mt
source-git-commit: ff9861a2b8a59843cc668cec9f89b9ea76822d66

---


# Chiamata di una risorsa utilizzando una chiave di identificazione composita

In alcuni casi, potrebbe essere necessario definire per una risorsa una chiave di identificazione composta da due campi. Una volta configurato la chiave di identificazione, è necessario configurare una definizione di filtro per essere in grado di richiamare la risorsa con questa chiave di identificazione, dall'interfaccia di Campaign Standard o dalle API.

In questo caso d'uso, la **risorsa Profilo** è stata estesa con il **campo "CRM ID"** e **"categoria"** personalizzato. Creeremo una chiave di identificazione per la risorsa Profilo che sarà composta da questi due campi. Configureremo quindi una definizione di filtro per accedere alla risorsa Profilo utilizzando la chiave di identificazione.

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
> I concetti globali durante la configurazione delle chiavi di identificazione sono descritti in [questa sezione](../../developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys).

1. Prima di configurare la chiave di identificazione, accertatevi che la risorsa sia stata estesa con i campi desiderati e che sia stata pubblicata. For more on this, refer to [this section](../../developing/using/creating-or-extending-the-resource.md).

1. Andate **[!UICONTROL Administration]** al/ **[!UICONTROL Developement]** / **[!UICONTROL Custom resources]** menu, quindi aprite la **[!UICONTROL Profile]** risorsa.

   ![](assets/uc_idkey1.png)

1. Nella **[!UICONTROL Identification keys]** sezione, fate clic sul **[!UICONTROL Create element]** pulsante.

   ![](assets/uc_idkey2.png)

1. Aggiungi i due campi "CRM ID" e "Categoria" personalizzati, quindi fai clic **[!UICONTROL Confirm]** su.

   ![](assets/uc_idkey3.png)

   >[!NOTE]
   > Per visualizzare i due campi personalizzati nell'interfaccia del profilo, configura la **[!UICONTROL Screen definition]** scheda. For more on this, refer to [this section](../../developing/using/configuring-the-screen-definition.md).

1. Ora potete configurare la definizione del filtro per poter chiamare la risorsa utilizzando la relativa chiave di identificazione.

## Passaggio 2: Configurare la definizione del filtro

>[!NOTE]
> I concetti globali durante la configurazione delle definizioni dei filtri sono descritti in [questa sezione](../../developing/using/configuring-filter-definition.md).

1. Nella **[!UICONTROL Filter definition]** scheda, fate clic **[!UICONTROL Add an element]** su, quindi immettete l'etichetta e l'ID della definizione del filtro.

1. Modificate le proprietà della definizione del filtro per configurarne le regole.

   ![](assets/uc_idkey4.png)

1. Trascinare nell'area di lavoro la tabella contenente i campi utilizzati nella chiave di identificazione.

   ![](assets/uc_idkey5.png)

1. Selezionate il primo campo utilizzato nella chiave di identificazione ("CRM ID"), quindi attivate l' **[!UICONTROL Switch to parameters]** opzione.

   ![](assets/uc_idkey6.png)

1. Nella **[!UICONTROL Filter conditions]** sezione, mantenete l' **[!UICONTROL Equal]** operatore, quindi definite il nome del parametro e fate clic sul segno più per crearlo.

   ![](assets/uc_idkey7.png)

   >[!NOTE]
   > Dopo aver fatto clic sul pulsante più, il nome del parametro viene generato automaticamente. Tenete presente queste informazioni, in quanto dovrete usare il filtro dalle API.

1. Ripetete i passaggi descritti qui sopra con tutti i campi che compongono la chiave di identificazione ("categoria"), quindi salvate le modifiche.

   ![](assets/uc_idkey8.png)

1. La definizione del filtro è ora configurata. Potete pubblicare la risorsa in modo che sia disponibile.

## Passaggio 3: Chiama la risorsa in base alla chiave di identificazione

Una volta configurata la chiave di identificazione e la relativa definizione del filtro, potete utilizzarle per chiamare la risorsa, dall'interfaccia standard Campaign o da REST API.

Per utilizzare la definizione del filtro dall'interfaccia, utilizzate un **[!UICONTROL Query]** 'attività in un flusso di lavoro (consultate questa [sezione](../../automating/using/query.md)). Il filtro è quindi disponibile nel riquadro a sinistra.

![](assets/uc_idkey9.png)

Per usare la definizione del filtro dalle API REST di Campaign Standard, utilizzate la sintassi seguente:

```
GET /profileAndServicesExt/<resourceName><filterName>?<param1_parameter>=<value>&<param2_parameter>=<value>
```

Nel nostro caso, la sintassi per recuperare un profilo dalla categoria "spring" e con l'ID CRM "123456" sarà:

```
GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/profile/identification_key?category_parameter=spring&crm_id_parameter=123456
```

Per ulteriori dettagli, consulta la documentazione API standard [di Campaign Standard](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#filtering).