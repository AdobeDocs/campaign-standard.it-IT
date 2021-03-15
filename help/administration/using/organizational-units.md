---
solution: Campaign Standard
product: campaign
title: Unità organizzative
description: Definisci i livelli di accesso degli utenti utilizzando le unità organizzative.
audience: administration
content-type: reference
topic-tags: users-and-security
context-tags: orgUnit,overview;orgUnit,main;geoUnit,overview;geoUnit,main
feature: Gestione degli accessi
role: Amministratore
level: Esperienza
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '846'
ht-degree: 4%

---


# Unità organizzative{#organizational-units}

## Informazioni sulle unità {#about-units}

Ogni oggetto e utente della piattaforma è collegato a un’unità organizzativa. Questa unità consente di definire una struttura gerarchica al fine di fornire agli utenti una visualizzazione filtrata. L’unità di un utente definisce il livello di accesso per i diversi oggetti della piattaforma.

>[!IMPORTANT]
>
>Se un utente non è collegato ad alcuna unità, non sarà in grado di connettersi ad Adobe Campaign. Se desideri limitare l’accesso a un particolare utente o gruppo di utenti, non collegarlo all’unità **[!UICONTROL All]**. È consigliabile aggiungere l’opzione **Accedi ai campi di gestione delle autorizzazioni** prima di importare qualsiasi profilo. Per ulteriori informazioni, consulta questa [sezione](../../administration/using/organizational-units.md#partitioning-profiles).
>
>Per impostazione predefinita, l’unità organizzativa **[!UICONTROL All (all)]** viene assegnata al gruppo di sicurezza **[!UICONTROL Administrators]**. È di sola lettura e non può essere modificata.

Un utente ha accesso in sola lettura a tutti gli oggetti nelle unità principali. Ha accesso in lettura e scrittura a tutti gli oggetti della sua unità e delle sue unità secondarie. Un utente non ha accesso agli oggetti nei rami paralleli.

Per impostazione predefinita, sono disponibili solo le unità **[!UICONTROL All]**.

Quando all’utente viene assegnata un’unità organizzativa, questa unità viene sempre applicata agli oggetti creati dall’utente.

![](assets/user_management_2.png)

>[!NOTE]
>
>Quando un utente si trova in diversi gruppi collegati a unità diverse, vengono applicate determinate regole. Per ulteriori informazioni, consulta la sezione [Gestione di gruppi e utenti](../../administration/using/managing-groups-and-users.md) .

## Creazione e gestione di unità {#creating-and-managing-units}

Le unità organizzative ti consentono di filtrare l’istanza in base all’organizzazione a cui sono collegati gli utenti. Questa unità può rappresentare una regione, un paese o persino un marchio nella tua istanza.

In precedenza, abbiamo creato gruppi di sicurezza con ruoli diversi per due utenti: a un utente vengono assegnati i gruppi di sicurezza Amministratori e Geometrixx, l&#39;altro utente appartiene ai gruppi di sicurezza Utenti e vestiti standard Vedere [Creazione di un gruppo di sicurezza e assegnazione di utenti](../../administration/using/managing-groups-and-users.md#creating-a-security-group-and-assigning-users) per l&#39;esempio completo.

Ora è necessario creare le unità organizzative per i gruppi di sicurezza Geometrixx Vestiti e Geometrixx:

1. Dal menu avanzato di Adobe Campaign, seleziona **[!UICONTROL Administration]** > **[!UICONTROL Users & security]** > **[!UICONTROL Organizational units]**.
1. Fai clic su **[!UICONTROL Create]** per iniziare a configurare l’unità organizzativa.

   ![](assets/manage_units_1.png)

1. Modifica i valori predefiniti **[!UICONTROL Label]** e **[!UICONTROL ID]** in Geometrixx.
1. Quindi, collega l&#39;unità a un&#39;unità principale. In questo caso, abbiamo scelto **[!UICONTROL All]**.

   ![](assets/manage_units_2.png)

1. Infine, fai clic su **[!UICONTROL Create]** per iniziare ad assegnare la nuova unità organizzativa al gruppo di sicurezza.
1. Seguire la stessa procedura per l&#39;unità Abbigliamento Geometrixx, tranne per il fatto che l&#39;unità madre deve essere l&#39;unità creata in precedenza, Geometrixx.

   ![](assets/manage_units_3.png)

Per vedere l’impatto dell’assegnazione di unità diverse a gruppi di sicurezza diversi, l’utente assegnato all’amministratore e ai gruppi di Geometrixx creerà due modelli e-mail per vedere a cosa può o non può accedere l’altro utente assegnato a Utente standard e vestiti Geometrixx.

1. Dal menu avanzato, seleziona **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery Templates]**.
1. Duplica un modello esistente e personalizzalo in base alle esigenze. Per ulteriori informazioni, consulta la sezione [Informazioni sui modelli](../../start/using/marketing-activity-templates.md) .
1. Quando il modello viene creato, seleziona l’icona **[!UICONTROL Edit properties]** per assegnare le unità al modello.

   ![](assets/manage_units_6.png)

1. Nel menu a discesa **[!UICONTROL Access authorization]** , seleziona l’unità organizzativa .

   Qui creeremo un modello con il Geometrixx di unità organizzativa creato in precedenza.

   ![](assets/manage_units_5.png)

1. Seguire le stesse procedure per creare il secondo modello assegnato all&#39;unità organizzativa Geometrixx Clothes creata in precedenza.

L’utente assegnato ai gruppi Utente standard e Abiti Geometrixx potrà visualizzare entrambi i modelli. A causa della struttura gerarchica delle unità organizzative, avrà accesso in lettura e scrittura al modello collegato all&#39;unità Abbigliamento Geometrixx e solo accesso in sola lettura al modello collegato all&#39;unità Geometrixx.

![](assets/manage_units_7.png)

Poiché l’unità Abbigliamento Geometrixx è un’unità secondaria di Geometrixx, quando l’utente tenta di modificare il modello di Geometrixx viene visualizzato il seguente messaggio:

![](assets/manage_units_8.png)

Le unità organizzative possono limitare l’accesso a funzioni diverse, come i profili. Ad esempio, se l’utente di Geometrixx Clothes accede alla scheda **[!UICONTROL Profiles]** , potrà accedere e modificare completamente i profili con l’unità organizzativa Geometrixx Clothes .

Mentre i profili con l’unità organizzativa Geometrixx saranno di sola lettura, se l’utente tenta di modificare un profilo viene visualizzato il seguente errore: **[!UICONTROL You do not have the rights needed to modify the 'profile' resource of ID]**.

![](assets/manage_units_10.png)

## Profili di partizione {#partitioning-profiles}

>[!IMPORTANT]
>
>È consigliabile aggiungere questa opzione prima di importare qualsiasi profilo, in quanto gli utenti non possono accedere a profili privi di unità organizzative.
>
>Se hai già importato il database dei clienti, è necessario un aggiornamento per impostare i valori delle unità organizzative sui profili già importati.

Se l’organizzazione deve isolare i profili contattati da ciascuno dei diversi marchi, puoi suddividere i profili in base alle unità organizzative.

Per impostazione predefinita, i campi dell’unità organizzativa non sono disponibili sui profili e devono essere aggiunti.

1. Dal menu avanzato, tramite il logo Adobe Campaign, seleziona **Amministrazione > Sviluppo > Risorse personalizzate**.
1. Seleziona **Profilo** o crea una nuova risorsa personalizzata per estendere i profili. Per ulteriori informazioni su come estendere i profili, consulta questa [pagina](../../developing/using/extending-the-profile-resource-with-a-new-field.md#step-1--extend-the-profile-resource).
1. Seleziona la casella **Aggiungi campi di gestione delle autorizzazioni di accesso** per aggiungere le unità organizzative nell&#39;estensione **Profilo**.

   ![](assets/user_management_9.png)

1. Fai clic su **[!UICONTROL Save]**.
1. Aggiorna la struttura ripubblicando le risorse personalizzate. Per ulteriori informazioni sul processo di pubblicazione, consulta la sezione [Aggiornamento della struttura](../../developing/using/updating-the-database-structure.md) .

Il campo Unità organizzativa viene aggiunto ai profili nella sezione **[!UICONTROL Access authorization]** .

![](assets/user_management_10.png)

**Argomenti correlati**:

* [Informazioni sulle unità](../../administration/using/organizational-units.md#about-units)
* [Informazioni sulla gestione degli accessi](../../administration/using/about-access-management.md)

