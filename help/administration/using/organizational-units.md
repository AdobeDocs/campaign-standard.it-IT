---
title: Unità organizzative
description: Definite i livelli di accesso degli utenti utilizzando le unità organizzative.
page-status-flag: never-activated
uuid: 8c82ffea-cef4-4a89-b823-d8b7bae1db4f
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: users-and-security
discoiquuid: 6f60c653-1d12-4d27-9bc8-ce8c19bca466
context-tags: orgUnit,overview;orgUnit,main;geoUnit,overview;geoUnit,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '807'
ht-degree: 3%

---


# Unità organizzative{#organizational-units}

## Informazioni sulle unità {#about-units}

Ogni oggetto e utente della piattaforma è collegato a un&#39;unità organizzativa. Questa unità consente di definire una struttura gerarchica per fornire agli utenti una visualizzazione filtrata. L&#39;unità di un utente definisce il livello di accesso per i diversi oggetti piattaforma.

>[!IMPORTANT]
>
>Se un utente non è collegato ad alcuna unità, non sarà in grado di connettersi a  Adobe Campaign. Se si desidera limitare l&#39;accesso a un utente o a un gruppo specifico di utenti, non collegarlo all&#39; **[!UICONTROL All]** unità.
>
>Per impostazione predefinita, l’unità organizzativa **[!UICONTROL All (all)]** viene assegnata al gruppo di sicurezza **[!UICONTROL Administrators]**. È di sola lettura e non può essere modificata.

Un utente ha accesso in sola lettura a tutti gli oggetti nelle unità principali. Ha accesso in lettura e scrittura a tutti gli oggetti della sua unità e delle sue unità figlie. Un utente non ha accesso agli oggetti in rami paralleli.

Per impostazione predefinita, sono disponibili solo **[!UICONTROL All]** le unità.

Quando all&#39;utente viene assegnata un&#39;unità organizzativa, questa unità verrà sempre applicata agli oggetti creati dall&#39;utente.

![](assets/user_management_2.png)

>[!NOTE]
>
>Quando un utente si trova in diversi gruppi collegati a unità diverse, vengono applicate determinate regole. Per ulteriori informazioni, consultate la sezione [Gestione di gruppi e utenti](../../administration/using/managing-groups-and-users.md) .

## Creazione e gestione di unità {#creating-and-managing-units}

Le unità organizzative consentono di filtrare l’istanza in base all’organizzazione a cui sono collegati gli utenti. Questa unità può rappresentare una regione, un paese o persino un marchio nell&#39;istanza.

In questa sezione sono stati creati in precedenza gruppi di sicurezza con ruoli diversi per due utenti: a un utente vengono assegnati i gruppi di sicurezza Amministratori e Geometrixx, all&#39;altro utente appartengono i gruppi di sicurezza Standard utente e vestiti Geometrixx Vedere [Creazione di un gruppo di protezione e assegnazione di utenti](../../administration/using/managing-groups-and-users.md#creating-a-security-group-and-assigning-users) per l&#39;esempio completo.

Ora dobbiamo creare le unità organizzative per i gruppi di sicurezza vestiti e Geometrixx:

1. Dal menu avanzato  campagna di Adobe, selezionate **[!UICONTROL Administration]** > **[!UICONTROL Users & security]** > **[!UICONTROL Organizational units]**.
1. Fare clic **[!UICONTROL Create]** per iniziare a configurare l&#39;unità organizzativa.

   ![](assets/manage_units_1.png)

1. Modificate il valore predefinito **[!UICONTROL Label]** e **[!UICONTROL ID]** in Geometrixx.
1. Collegate quindi l&#39;unità a un&#39;unità padre. Qui, abbiamo scelto **[!UICONTROL All]**.

   ![](assets/manage_units_2.png)

1. Infine, fare clic **[!UICONTROL Create]** per iniziare ad assegnare la nuova unità organizzativa al gruppo di sicurezza.
1. Seguire la stessa procedura per l&#39;unità Abbigliamento Geometrixx, fatta eccezione per il fatto che l&#39;unità padre deve essere l&#39;unità precedentemente creata, Geometrixx.

   ![](assets/manage_units_3.png)

Per verificare l’impatto dell’assegnazione di diverse unità a diversi gruppi di sicurezza, l’utente assegnato all’amministratore e ai gruppi di Geometrixx creerà due modelli di e-mail per vedere a cosa può accedere l’altro utente assegnato a Standard User and Geometrixx Clothes (Utente standard e Abiti di ).

1. Dal menu avanzato, selezionate **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery Templates]**.
1. Duplica un modello esistente e personalizzalo come necessario. For more on this, refer to the [About templates](../../start/using/marketing-activity-templates.md) section.
1. Quando il modello viene creato, selezionate l&#39; **[!UICONTROL Edit properties]** icona per assegnare le unità al modello.

   ![](assets/manage_units_6.png)

1. Nel menu a **[!UICONTROL Access authorization]** discesa, selezionate l&#39;unità organizzativa.

   Qui verrà creato un modello con il Geometrixx di unità organizzativa creato in precedenza.

   ![](assets/manage_units_5.png)

1. Seguire le stesse procedure per creare il secondo modello assegnato all&#39;unità organizzativa Abiti Geometrixx creata in precedenza.

L&#39;utente assegnato ai gruppi Standard Utente e Abiti Geometrixx potrà visualizzare entrambi i modelli. A causa della struttura gerarchica delle unità organizzative, avrà accesso in lettura e scrittura al modello collegato all&#39;unità Abbigliamento Geometrixx e accesso in sola lettura al modello collegato all&#39;unità Geometrixx.

![](assets/manage_units_7.png)

Poiché l&#39;unità Abbigliamento Geometrixx è un&#39;unità secondaria di Geometrixx, quando l&#39;utente tenta di modificare il modello di Geometrixx viene visualizzato il seguente messaggio:

![](assets/manage_units_8.png)

Le unità organizzative possono limitare l&#39;accesso a funzioni diverse come i profili. Ad esempio, se il nostro utente di Abbigliamento Geometrixx accede alla **[!UICONTROL Profiles]** scheda, sarà in grado di accedere e modificare completamente i profili con l&#39;unità organizzativa Abbigliamento Geometrixx.

Mentre i profili con l&#39;unità organizzativa Geometrixx saranno di sola lettura, se l&#39;utente tenta di modificare un profilo verrà visualizzato il seguente errore: **[!UICONTROL You do not have the rights needed to modify the 'profile' resource of ID]**.

![](assets/manage_units_10.png)

## Profili di partizionamento {#partitioning-profiles}

Se l&#39;organizzazione deve isolare i profili contattati da ciascuno dei marchi, puoi suddividere i profili in base alle unità organizzative.

Per impostazione predefinita, i campi dell’unità organizzativa non sono disponibili nei profili e devono essere aggiunti.

Gli utenti non possono accedere ai profili senza unità organizzative.

>[!IMPORTANT]
>
>È consigliabile aggiungere questa opzione prima di importare qualsiasi profilo. Se avete già importato il database dei clienti, è necessario un aggiornamento per impostare i valori delle unità organizzative sui profili già importati.

1. Dal menu avanzato, tramite il logo Adobe Campaign , selezionate **Amministrazione > Sviluppo > Risorse** personalizzate.
1. Selezionate **Profilo** o create una nuova risorsa personalizzata per estendere i profili.
1. Selezionate la casella **Aggiungi campi** di gestione autorizzazione di accesso per aggiungere le unità organizzative nell’estensione **Profilo** .

   ![](assets/user_management_9.png)

1. Fai clic su **[!UICONTROL Save]**.
1. Aggiornate la struttura pubblicando nuovamente le risorse personalizzate. Per ulteriori informazioni sul processo di pubblicazione, vedere [Aggiornamento della sezione struttura](../../developing/using/data-model-concepts.md) .

Il campo unità organizzativa viene aggiunto ai profili nella **[!UICONTROL Access authorization]** sezione.

![](assets/user_management_10.png)

**Argomenti correlati**:

* [Informazioni sulle unità](../../administration/using/organizational-units.md#about-units)
* [Informazioni sulla gestione degli accessi](../../administration/using/about-access-management.md)

