---
title: Unità organizzative
description: Definire i livelli di accesso degli utenti utilizzando le unità organizzative
audience: administration
feature: Access Management
role: Admin
level: Experienced
exl-id: fbab695a-2672-4183-8c3b-78af7aefd5b1
source-git-commit: bfba6b156d020e8d2656239e713d2d24625bda54
workflow-type: tm+mt
source-wordcount: '840'
ht-degree: 4%

---

# Unità organizzative{#organizational-units}

## Informazioni sulle unità {#about-units}

Ogni oggetto e utente della piattaforma è collegato a un’unità organizzativa. Questa unità consente di definire una struttura gerarchica per offrire agli utenti una vista filtrata. L’unità di un utente definisce il proprio livello di accesso per diversi oggetti piattaforma.

>[!IMPORTANT]
>
>Se un utente non è collegato ad alcuna unità, non potrà connettersi ad Adobe Campaign. Se desideri limitare l’accesso a un particolare utente o a un gruppo di utenti, non collegarlo al **[!UICONTROL All]** unità. È consigliabile aggiungere l’opzione **Accedere ai campi di gestione delle autorizzazioni** prima di importare qualsiasi profilo. Per ulteriori informazioni, consulta questa [sezione](../../administration/using/organizational-units.md#partitioning-profiles).
>
>Per impostazione predefinita, l’unità organizzativa **[!UICONTROL All (all)]** viene assegnata al gruppo di sicurezza **[!UICONTROL Administrators]**. È di sola lettura e non può essere modificata.

Un utente ha accesso in sola lettura a tutti gli oggetti nelle unità padre. Tale utente dispone dell&#39;accesso in lettura e scrittura a tutti gli oggetti della propria unità e delle unità secondarie. Un utente non ha accesso agli oggetti nei rami paralleli.

Per impostazione predefinita, solo il **[!UICONTROL All]** sono disponibili unità.

Quando all’utente viene assegnata un’unità organizzativa, questa viene sempre applicata agli oggetti creati dall’utente.

![](assets/user_management_2.png)

>[!NOTE]
>
>Quando un utente si trova in più gruppi collegati a unità diverse, vengono applicate determinate regole. Per ulteriori informazioni, consulta [Gestione di gruppi e utenti](../../administration/using/managing-groups-and-users.md) sezione.

## Creazione e gestione delle unità {#creating-and-managing-units}

Le unità organizzative ti consentono di filtrare l’istanza a seconda dell’organizzazione a cui sono collegati gli utenti. L&#39;unità può rappresentare una regione, un paese o persino un marchio.

In precedenza, venivano creati gruppi di sicurezza con ruoli diversi per due utenti: a un utente vengono assegnati i gruppi di sicurezza Amministratori e Geometrixx, all’altro utente i gruppi di sicurezza Utente standard e Abbigliamento Geometrixx Vedere [Creazione di un gruppo di sicurezza e assegnazione di utenti](../../administration/using/managing-groups-and-users.md#creating-a-security-group-and-assigning-users) per l’esempio completo.

Ora dobbiamo creare le unità organizzative per i gruppi di sicurezza Geometrixx Clothes e Geometrixx:

1. Dal menu avanzato della campagna di Adobe, seleziona **[!UICONTROL Administration]** > **[!UICONTROL Users & security]** > **[!UICONTROL Organizational units]**.
1. Clic **[!UICONTROL Create]** per iniziare a configurare l’unità organizzativa.

   ![](assets/manage_units_1.png)

1. Modificare il valore predefinito **[!UICONTROL Label]** e **[!UICONTROL ID]** al Geometrixx.
1. Quindi, collegare l&#39;unità a un&#39;unità padre. Qui abbiamo scelto **[!UICONTROL All]**.

   ![](assets/manage_units_2.png)

1. Infine, fai clic su **[!UICONTROL Create]** per iniziare ad assegnare la nuova unità organizzativa al gruppo di sicurezza.
1. Seguire la stessa procedura per l&#39;unità Geometrixx Clothes, tranne per il fatto che l&#39;unità padre deve essere l&#39;unità creata in precedenza, Geometrixx.

   ![](assets/manage_units_3.png)

Per verificare l’impatto dell’assegnazione di diverse unità a gruppi di sicurezza diversi, l’utente assegnato all’amministratore e ai Geometrixx creerà due modelli e-mail per verificare a cosa possono o non possono accedere gli altri utenti assegnati a utenti standard e Geometrixx Clothes.

1. Dal menu avanzato, seleziona **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery Templates]**.
1. Duplica un modello esistente e personalizzalo in base alle esigenze. Per ulteriori informazioni, consulta [Informazioni sui modelli](../../start/using/marketing-activity-templates.md) sezione.
1. Al momento della creazione del modello, seleziona la **[!UICONTROL Edit properties]** per assegnare unità al modello.

   ![](assets/manage_units_6.png)

1. In **[!UICONTROL Access authorization]** dal menu a discesa, seleziona l’unità organizzativa.

   Stiamo per creare un modello con il Geometrixx di unità organizzativa creato in precedenza.

   ![](assets/manage_units_5.png)

1. Segui le stesse procedure per creare il secondo modello assegnato all’unità organizzativa Geometrixx Clothes creata in precedenza.

Utenti assegnati al **Utente standard** e **Abbigliamento Geometrixx** I gruppi potranno visualizzare entrambi i modelli. A causa della struttura gerarchica delle unità organizzative, queste disporranno dell’accesso in lettura e scrittura al modello collegato all’unità Geometrixx Clothes e dell’accesso in sola lettura al modello collegato all’unità Geometrixx.

![](assets/manage_units_7.png)

Poiché l&#39;unità Geometrixx Clothes è un&#39;unità figlio di Geometrixx Geometrixx, quando gli utenti tentano di modificare il modello viene visualizzato il seguente messaggio:

![](assets/manage_units_8.png)

Le unità organizzative possono limitare l’accesso a diverse funzioni, ad esempio i profili. Ad esempio, se gli utenti di Geometrixx Clothes accedono al **[!UICONTROL Profiles]** , potranno accedere e modificare completamente i profili con l’unità organizzativa Geometrixx Clothes.

Mentre i profili con l’unità organizzativa Geometrixx saranno di sola lettura, se gli utenti tentano di modificare un profilo verrà visualizzato il seguente errore: **[!UICONTROL You do not have the rights needed to modify the 'profile' resource of ID]**.

![](assets/manage_units_10.png)

## Partizionamento dei profili {#partitioning-profiles}

>[!IMPORTANT]
>
>È consigliabile aggiungere questa opzione prima di importare qualsiasi profilo, in quanto gli utenti non possono accedere a profili privi di unità organizzative.
>
>Se hai già importato il database dei clienti, è necessario un aggiornamento per impostare i valori delle unità organizzative sui profili già importati.

Se la tua organizzazione deve isolare i profili contattati da ciascuno dei diversi brand, puoi suddividere i profili in base alle unità organizzative.

Per impostazione predefinita, i campi dell’unità organizzativa non sono disponibili nei profili e devono essere aggiunti.

1. Dal menu avanzato, tramite il logo Adobe Campaign, seleziona **Amministrazione > Sviluppo > Risorse personalizzate**.
1. Seleziona **Profilo** oppure crea una nuova risorsa personalizzata per estendere i profili. Per ulteriori informazioni su come estendere i profili, consulta questa [pagina](../../developing/using/extending-the-profile-resource-with-a-new-field.md#step-1--extend-the-profile-resource).
1. Controlla la **Aggiungi campi di gestione delle autorizzazioni di accesso** per aggiungere le unità organizzative nel **Profilo** estensione.

   ![](assets/user_management_9.png)

1. Fai clic su **[!UICONTROL Save]**.
1. Aggiorna la struttura ripubblicando le risorse personalizzate. Per ulteriori informazioni sul processo di pubblicazione, consulta [Aggiornamento della struttura](../../developing/using/updating-the-database-structure.md) sezione.

Il campo dell’unità organizzativa viene aggiunto ai profili in **[!UICONTROL Access authorization]** sezione.

![](assets/user_management_10.png)

**Argomenti correlati**:

* [Informazioni sulle unità](../../administration/using/organizational-units.md#about-units)
* [Informazioni sulla gestione degli accessi](../../administration/using/about-access-management.md)
