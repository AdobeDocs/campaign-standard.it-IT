---
title: Unità organizzative
seo-title: Unità organizzative
description: Unità organizzative
seo-description: Definite i livelli di accesso degli utenti mediante le unità aziendali.
page-status-flag: never-activated
uuid: 8 c 82 ffea-cef 4-4 a 89-b 823-d 8 b 7 bae 1 db 4 f
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: administration
content-type: riferimento
topic-tags: utenti e sicurezza
discoiquuid: 6 f 60 c 653-1 d 12-4 d 27-9 bc 8-ce 8 c 19 bca 466
context-tags: Orgunit, overview; Orgunit, main; Geounit, overview; Geounit, main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a12df43de55dedf388a397fbf4670d99e3ea7f3d

---


# Organizational units{#organizational-units}

## About units {#about-units}

Ciascun oggetto e utente della piattaforma è collegato a un'unità organizzativa. Questa unità consente di definire una struttura gerarchica per consentire agli utenti una visualizzazione filtrata. L'unità di un utente definisce il livello di accesso per diversi oggetti piattaforma.

>[!CAUTION]
>
>Se un utente non è collegato ad alcun'unità, tale utente non potrà connettersi ad Adobe Campaign. If you would like to restrict access for a particular user or group of users, do not link it to the **[!UICONTROL All]** unit.

Un utente dispone dell'accesso in sola lettura a tutti gli oggetti delle unità principali. Dispone di accesso in lettura e scrittura a tutti gli oggetti della relativa unità e delle unità figlie. Un utente non ha accesso agli oggetti in rami paralleli.

By default, only the **[!UICONTROL All]** units are available.

Quando all'utente viene assegnata un'unità organizzativa, questa unità viene sempre applicata agli oggetti creati dall'utente.

![](assets/user_management_2.png)

>[!NOTE]
>
>Quando un utente si trova in più gruppi collegati a unità diverse, vengono applicate determinate regole. For more information, refer to the [Managing groups and users](../../administration/using/managing-groups-and-users.md) section.

## Creating and managing units {#creating-and-managing-units}

Le unità organizzative consentono di filtrare l'istanza a seconda dell'organizzazione a cui sono collegati gli utenti. Questa unità può rappresentare un'area, un paese o anche un marchio nell'istanza.

Here, we previously created security groups with different roles to two users: one user is assigned the security groups Administrators and Geometrixx, the other user belongs to the security groups Standard user and Geometrixx Clothes See [Creating a security group and assigning users](../../administration/using/managing-groups-and-users.md#creating-a-security-group-and-assigning-users) for the full example.

Ora è necessario creare le unità organizzative per i gruppi di sicurezza Geometrixx Clothes e Geometrixx:

1. From Adobe campaign advanced menu, select **[!UICONTROL Administration]** &gt; **[!UICONTROL Users & security]** &gt; **[!UICONTROL Organizational units]**.
1. Click **[!UICONTROL Create]** to start configuring your organizational unit.

   ![](assets/manage_units_1.png)

1. Change the default **[!UICONTROL Label]** and **[!UICONTROL ID]** to Geometrixx.
1. Quindi, collegate questa unità a un'unità principale. Here, we chose **[!UICONTROL All]**.

   ![](assets/manage_units_2.png)

1. Finally, click **[!UICONTROL Create]** to start assigning your new organizational unit to security group.
1. Seguire la stessa procedura per l'unità Geometrixx Clothes, fatta eccezione per l'unità padre che deve essere l'unità creata in precedenza Geometrixx.

   ![](assets/manage_units_3.png)

Per visualizzare l'impatto derivante dall'assegnazione di unità diverse a un gruppo di sicurezza diverso, l'utente assegnato ai gruppi Amministratore e Geometrixx creerà due modelli e-mail per vedere quali altri utenti assegnati a Standard Standard e Geometrixx Clothes possono o meno accedere.

1. From the advanced menu, select **[!UICONTROL Resources]** &gt; **[!UICONTROL Templates]** &gt; **[!UICONTROL Delivery Templates]**.
1. Duplicate un modello esistente e personalizzatelo come necessario. For more on this, refer to the [About templates](../../start/using/about-templates.md) section.
1. When the template is created, select the **[!UICONTROL Edit properties]** icon to assign units to your template.

   ![](assets/manage_units_6.png)

1. In the **[!UICONTROL Access authorization]** drop down menu, select the organizational unit.

   Qui creeremo un modello con l'unità organizzativa creata in precedenza Geometrixx.

   ![](assets/manage_units_5.png)

1. Seguite le stesse procedure per creare il secondo modello assegnato all'unità organizzazione Geometrixx Clothes creata in precedenza.

L'utente assegnato ai gruppi Standard utente e Geometrixx Clothes sarà in grado di visualizzare entrambi i modelli. A causa della struttura gerarchica delle unità aziendali, avrà accesso in lettura e scrittura al modello collegato all'unità Geometrixx Clothes e solo in lettura al modello collegato all'unità Geometrixx.

![](assets/manage_units_7.png)

Poiché l'unità Geometrixx Clothes è un'unità figlia di Geometrixx, quando l'utente tenta di modificare il modello Geometrixx viene visualizzato il messaggio seguente:

![](assets/manage_units_8.png)

Le unità organizzative possono limitare l'accesso a funzioni diverse come i profili. For example, if our Geometrixx Clothes user access the **[!UICONTROL Profiles]** tab, he will be able to fully access and modify the profiles with the Geometrixx Clothes organizational unit.

Whereas the profiles with the Geometrixx organizational unit will be read only, the following error will appear if our user tries to modify one profile: **[!UICONTROL You do not have the rights needed to modify the 'profile' resource of ID]**.

![](assets/manage_units_10.png)

## Partitioning profiles {#partitioning-profiles}

Se l'organizzazione deve isolare i profili contattati da ciascuno dei marchi, potete suddividere i profili in base alle unità organizzative.

Per impostazione predefinita, i campi unità organizzativi non sono disponibili sui profili e devono essere aggiunti.

Gli utenti non possono accedere ai profili senza unità organizzative.

>[!CAUTION]
>
>È consigliabile aggiungere questa opzione prima di importare qualsiasi profilo. Se avete già importato il database del cliente, è necessario un aggiornamento per impostare i valori dell'unità organizzativa sui profili già importati.

1. From the advanced menu, via the Adobe Campaign logo, select **Administration &gt; Development &gt; Custom resources**.
1. Select **Profile** or create a new custom resource to extend the profiles.
1. Check the **Add access authorization management fields** box to add the organizational units in the **Profile** extension.

   ![](assets/user_management_9.png)

1. Click **[!UICONTROL Save]**.
1. Aggiornate la struttura ripubblicando le risorse personalizzate. For more information about the publication process, refer to [Updating the structure](../../developing/using/data-model-concepts.md) section.

The organizational unit field is added to your profiles in the **[!UICONTROL Access authorization]** section.

![](assets/user_management_10.png)

**Argomenti correlati**:

* [Informazioni sulle unità](../../administration/using/organizational-units.md#about-units)
* [Informazioni sulla gestione degli accessi](../../administration/using/about-access-management.md)

