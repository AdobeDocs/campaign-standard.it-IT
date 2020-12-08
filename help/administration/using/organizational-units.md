---
solution: Campaign Standard
product: campaign
title: Unità organizzative
description: Definite i livelli di accesso degli utenti utilizzando le unità organizzative.
audience: administration
content-type: reference
topic-tags: users-and-security
context-tags: orgUnit,overview;orgUnit,main;geoUnit,overview;geoUnit,main
translation-type: tm+mt
source-git-commit: 824c91669bd717e5bf31dab9005e4c3b9e497edf
workflow-type: tm+mt
source-wordcount: '842'
ht-degree: 4%

---


# Unità organizzative{#organizational-units}

## Informazioni sulle unità {#about-units}

Ogni oggetto e utente della piattaforma è collegato a un&#39;unità organizzativa. Questa unità consente di definire una struttura gerarchica per fornire agli utenti una visualizzazione filtrata. L&#39;unità di un utente definisce il livello di accesso per i diversi oggetti piattaforma.

>[!IMPORTANT]
>
>Se un utente non è collegato ad alcuna unità, non sarà in grado di connettersi a  Adobe Campaign. Se si desidera limitare l&#39;accesso per un utente o un gruppo di utenti, non collegarlo all&#39;unità **[!UICONTROL All]**. È consigliabile aggiungere l&#39;opzione **Accedi ai campi di gestione delle autorizzazioni** prima di importare qualsiasi profilo. Per ulteriori informazioni, consulta questa [sezione](../../administration/using/organizational-units.md#partitioning-profiles).
>
>Per impostazione predefinita, l’unità organizzativa **[!UICONTROL All (all)]** viene assegnata al gruppo di sicurezza **[!UICONTROL Administrators]**. È di sola lettura e non può essere modificata.

Un utente ha accesso in sola lettura a tutti gli oggetti nelle unità principali. Ha accesso in lettura e scrittura a tutti gli oggetti della sua unità e delle sue unità figlie. Un utente non ha accesso agli oggetti in rami paralleli.

Per impostazione predefinita, sono disponibili solo le unità **[!UICONTROL All]**.

Quando all&#39;utente viene assegnata un&#39;unità organizzativa, questa unità verrà sempre applicata agli oggetti creati dall&#39;utente.

![](assets/user_management_2.png)

>[!NOTE]
>
>Quando un utente si trova in diversi gruppi collegati a unità diverse, vengono applicate determinate regole. Per ulteriori informazioni, consultare la sezione [Gestione di gruppi e utenti](../../administration/using/managing-groups-and-users.md).

## Creazione e gestione di unità {#creating-and-managing-units}

Le unità organizzative consentono di filtrare l’istanza in base all’organizzazione a cui sono collegati gli utenti. Questa unità può rappresentare una regione, un paese o persino un marchio nell&#39;istanza.

In questa sezione sono stati creati in precedenza gruppi di sicurezza con ruoli diversi per due utenti: a un utente vengono assegnati i gruppi di sicurezza Amministratori e Geometrixx, l&#39;altro utente appartiene ai gruppi di sicurezza Standard utenti e vestiti Geometrixx Vedere [Creazione di un gruppo di protezione e assegnazione di utenti](../../administration/using/managing-groups-and-users.md#creating-a-security-group-and-assigning-users) per l&#39;esempio completo.

Ora dobbiamo creare le unità organizzative per i gruppi di sicurezza vestiti e Geometrixx:

1. Dal menu avanzato  campagna Adobe, selezionare **[!UICONTROL Administration]** > **[!UICONTROL Users & security]** > **[!UICONTROL Organizational units]**.
1. Fare clic su **[!UICONTROL Create]** per iniziare a configurare l&#39;unità organizzativa.

   ![](assets/manage_units_1.png)

1. Modificate le impostazioni predefinite **[!UICONTROL Label]** e **[!UICONTROL ID]** in Geometrixx.
1. Collegate quindi l&#39;unità a un&#39;unità padre. Qui abbiamo scelto **[!UICONTROL All]**.

   ![](assets/manage_units_2.png)

1. Infine, fare clic su **[!UICONTROL Create]** per iniziare ad assegnare la nuova unità organizzativa al gruppo di sicurezza.
1. Seguire la stessa procedura per l&#39;unità Abbigliamento Geometrixx, fatta eccezione per il fatto che l&#39;unità padre deve essere l&#39;unità precedentemente creata, Geometrixx.

   ![](assets/manage_units_3.png)

Per verificare l’impatto dell’assegnazione di diverse unità a diversi gruppi di sicurezza, l’utente assegnato all’amministratore e ai gruppi di Geometrixx creerà due modelli di e-mail per vedere a cosa può accedere l’altro utente assegnato a Standard User and Geometrixx Clothes (Utente standard e Abiti di ).

1. Dal menu avanzato, selezionare **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery Templates]**.
1. Duplica un modello esistente e personalizzalo come necessario. Per ulteriori informazioni, consultare la sezione [Informazioni sui modelli](../../start/using/marketing-activity-templates.md).
1. Quando il modello viene creato, selezionate l&#39;icona **[!UICONTROL Edit properties]** per assegnare le unità al modello.

   ![](assets/manage_units_6.png)

1. Nel menu a discesa **[!UICONTROL Access authorization]**, selezionate l&#39;unità organizzativa.

   Qui verrà creato un modello con il Geometrixx di unità organizzativa creato in precedenza.

   ![](assets/manage_units_5.png)

1. Seguire le stesse procedure per creare il secondo modello assegnato all&#39;unità organizzativa Abiti Geometrixx creata in precedenza.

L&#39;utente assegnato ai gruppi Standard Utente e Abiti Geometrixx potrà visualizzare entrambi i modelli. A causa della struttura gerarchica delle unità organizzative, avrà accesso in lettura e scrittura al modello collegato all&#39;unità Abbigliamento Geometrixx e accesso in sola lettura al modello collegato all&#39;unità Geometrixx.

![](assets/manage_units_7.png)

Poiché l&#39;unità Abbigliamento Geometrixx è un&#39;unità secondaria di Geometrixx, quando l&#39;utente tenta di modificare il modello di Geometrixx viene visualizzato il seguente messaggio:

![](assets/manage_units_8.png)

Le unità organizzative possono limitare l&#39;accesso a funzioni diverse, come i profili. Ad esempio, se il nostro utente di Abbigliamento Geometrixx accede alla scheda **[!UICONTROL Profiles]**, sarà in grado di accedere e modificare completamente i profili con l&#39;unità organizzativa Abbigliamento Geometrixx.

Mentre i profili con l&#39;unità organizzativa Geometrixx saranno di sola lettura, se l&#39;utente tenta di modificare un profilo verrà visualizzato il seguente errore: **[!UICONTROL You do not have the rights needed to modify the 'profile' resource of ID]**.

![](assets/manage_units_10.png)

## Profili di partizionamento {#partitioning-profiles}

>[!IMPORTANT]
>
>È consigliabile aggiungere questa opzione prima di importare qualsiasi profilo, dal momento che gli utenti non possono accedere ai profili senza unità organizzative.
>
>Se avete già importato il database dei clienti, è necessario un aggiornamento per impostare i valori delle unità organizzative sui profili già importati.

Se l&#39;organizzazione deve isolare i profili contattati da ciascuno dei marchi, puoi suddividere i profili in base alle unità organizzative.

Per impostazione predefinita, i campi dell’unità organizzativa non sono disponibili nei profili e devono essere aggiunti.

1. Dal menu avanzato, tramite il logo Adobe Campaign , selezionare **Amministrazione > Sviluppo > Risorse personalizzate**.
1. Selezionate **Profilo** oppure create una nuova risorsa personalizzata per estendere i profili. Per ulteriori informazioni su come estendere i profili, fare riferimento a questa [pagina](../../developing/using/extending-the-profile-resource-with-a-new-field.md#step-1--extend-the-profile-resource).
1. Selezionare la casella **Aggiungi campi di gestione autorizzazioni di accesso** per aggiungere le unità organizzative nell&#39;estensione **Profile**.

   ![](assets/user_management_9.png)

1. Fai clic su **[!UICONTROL Save]**.
1. Aggiornate la struttura pubblicando nuovamente le risorse personalizzate. Per ulteriori informazioni sul processo di pubblicazione, fare riferimento alla sezione [Aggiornamento della struttura](../../developing/using/updating-the-database-structure.md).

Il campo dell&#39;unità organizzativa viene aggiunto ai profili nella sezione **[!UICONTROL Access authorization]**.

![](assets/user_management_10.png)

**Argomenti correlati**:

* [Informazioni sulle unità](../../administration/using/organizational-units.md#about-units)
* [Informazioni sulla gestione degli accessi](../../administration/using/about-access-management.md)

