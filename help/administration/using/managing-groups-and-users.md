---
title: Gestione di gruppi e utenti
seo-title: Gestione di gruppi e utenti
description: Gestione di gruppi e utenti
seo-description: Scopri come creare gruppi di sicurezza e gestire gli utenti.
page-status-flag: never-activated
uuid: b 3 a 3 a 2 e 3-9 d 69-4231-b 724-8 f 37419 f 7 a 61
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: administration
content-type: riferimento
topic-tags: utenti e sicurezza
discoiquuid: 12 f 896 ab-ee 79-4 d 96-976 d-cf 34643491 b 4
context-tags: utente, panoramica; user, main; protezione, panoramica; protezione, principale
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a12df43de55dedf388a397fbf4670d99e3ea7f3d

---


# Managing groups and users{#managing-groups-and-users}

## About security groups {#about-security-groups}

I gruppi di sicurezza sono insiemi di utenti che condividono gli stessi ruoli e diritti all'interno dell'organizzazione.

Gli utenti devono essere sempre collegati a un gruppo di sicurezza. In questo modo potrete assegnare ruoli e unità organizzative specifiche.

For more information on roles, the tables in the following page present the different operations available according to a user's role(s): [Adobe Campaign Standard authorizations](https://docs.campaign.adobe.com/doc/standard/en/Technotes/AdobeCampaign-ACSRights.pdf).

I gruppi di protezione predefiniti sono:

* **[!UICONTROL Administrators]**
* **[!UICONTROL Delivery supervisors]**
* **[!UICONTROL Message Center agents]**
* **[!UICONTROL Standard Users]**
* **[!UICONTROL Workflow supervisors]**

Se un utente non è collegato a un gruppo di sicurezza, non potrà accedere ad Adobe Campaign.

To restrict a user's access, do not add the user to the Campaign Standard users group as this is linked to **[!UICONTROL All]** organizational unit.

## Creating a security group and assigning users {#creating-a-security-group-and-assigning-users}

>[!CAUTION]
>
>Nell'Admin Console, i gruppi di sicurezza sono indicati come profili.

Potete creare gruppi di sicurezza personalizzati se i gruppi forniti non sono sufficienti per gestire gli utenti. Possono essere gestiti da Amministratori che hanno accesso ai menu di amministrazione di Adobe Campaign e ad Admin Console. For more information on the Admin console, refer to this [documentation](https://helpx.adobe.com/enterprise/managing/user-guide.html).

Qui, dobbiamo innanzitutto assegnare i due gruppi standard standard e amministratore ai nostri utenti. Tali gruppi di sicurezza limitano alcune funzionalità di Adobe Campaign: L'utente Standard dispone dell'accesso di base ad Adobe Campaign, mentre l'amministratore può accedere ai menu di amministrazione ad esempio.

Eventuali modifiche apportate ai gruppi di sicurezza nell'admin console verranno sincronizzate non appena gli utenti accedono ad Adobe Campaign.

Quindi, vogliamo creare un set di gruppi di sicurezza Geometrixx e Geometrixx Vestiti che limiteranno l'accesso a seconda delle unità organizzative del nostro utente e amministratore Standard.

![](assets/ootb_security_group_1.png)

Occorre innanzitutto assegnare un gruppo di protezione predefinito agli utenti:

1. In the Admin console, select your instance then the **Users** tab.

   ![](assets/manage_security_group_2.png)

1. Click the **[!UICONTROL Add user]** button and enter your user's email address.
1. In the **[!UICONTROL Assign Products]** tab, select your instance then the **[!UICONTROL Administrators]** out-of-the-box security group from the drop-down list. In tal modo l'utente potrà accedere ai menu di amministrazione e creare i gruppi di protezione successivi.

   ![](assets/ootb_security_group_2.png)

1. Click **[!UICONTROL Save]** and follow the same procedures to assign the **[!UICONTROL Standard Users]** out-of-the-box security group to your new user.

   ![](assets/ootb_security_group_3.png)

Once your two users are attached to the **[!UICONTROL Administrators]** and **[!UICONTROL Standard users]** out-of-the-box security groups which assign roles to our users, the Administrator user can now create the two security groups **Geometrixx** and **Geometrixx Clothes** that will assign organizational units to our users in addition to the out-of-the-box security groups.

1. In the Admin console, select your instance then the **Products** tab.
1. Click the **New Profile** button to create the **Geometrixx** security group.

   ![](assets/create_security_1.png)

1. Type the **[!UICONTROL Profile name]** by following this exact syntax: **[!UICONTROL Campaign Standard- instance name - ID of the security group]** and click **[!UICONTROL Done]**.

   L'ID scelto verrà usato quando si crea il gruppo di protezione in Adobe Campaign.

   >[!NOTE]
   >
   >If the above syntax doesn't seem to work with an older instance, it needs to be replaced by **[!UICONTROL Campaign - instance name - ID of the security group]**.

   ![](assets/manage_security_group_1.png)

1. Then, follow the same procedures to create the **Geometrixx Clothes** security group.
1. Assign your security group to your user by selecting the **[!UICONTROL Users]** tab.

   ![](assets/manage_security_group_2.png)

1. Click your previously created user then the ![](assets/managing_security_group_10.png) icon in the **[!UICONTROL Products]** category.

   Select **[!UICONTROL Edit products assigned directly]** to start assigning new security group to your user.

   ![](assets/manage_security_group_8.png)

1. In the **[!UICONTROL Assign Products]** tab, select your instance then your previously created security groups Geometrixx from the drop-down list to assign it to your Administrator user.

   Click **[!UICONTROL Save]**.

   ![](assets/manage_security_group_3.png)

   Se un utente si trova in più gruppi:

   * I ruoli dei diversi gruppi sono cumulativi. Qui gli utenti si trovano in due gruppi diversi: uno che agisce su ruoli l'altro su unità.
   * It is the unit that is the highest in the hierarchy that will be used (see example in the [Organizational units](../../administration/using/organizational-units.md) section).
   * L'utente non sarà più in grado di connettersi se le unità hanno lo stesso livello equivalente e si trovano in rami paralleli nella gerarchia.

1. Seguite le stesse procedure per assegnare il gruppo di sicurezza Geometrixx Clothes al vostro utente Standard.

   ![](assets/manage_security_group_9.png)

I nuovi gruppi di protezione creati vengono ora creati in Admin Console. Affinché siano completamente sincronizzati, devi crearli in Adobe Campaign.

L'utente Amministratore deve creare il set di gruppi di protezione utilizzati per assegnare le unità organizzative: Geometrixx e Geometrixx Clothes. To learn how to create organizational units, see [Creating and managing units](../../administration/using/organizational-units.md#creating-and-managing-units) .

1. Click the **[!UICONTROL Adobe Campaign]** logo, in the top left corner, then select **[!UICONTROL Administration > Users & Security > Security groups]**.
1. Create your new security group and specify its **[!UICONTROL Label]** and **[!UICONTROL ID]**.

   L'ID deve essere uguale a quello scelto in Admin Console.

1. In the **[!UICONTROL User access]** field, assign organizational unit. Here, the Geometrixx security group is assigned the **[!UICONTROL All]** organizational unit.

   ![](assets/manage_security_group_6.png)

1. Potete anche assegnare ruoli al gruppo di protezione. In our case, this step is not needed since the out-of-the-box security groups **[!UICONTROL Administrators]** and **[!UICONTROL Standard users]** are used to assign roles.
1. Seguite le stesse procedure per creare l'ultima protezione di Geometrixx Clothes e assegnare l'unità organizzazione Geometrixx Clothes.

   ![](assets/manage_security_group_7.png)

Gli utenti vengono ora assegnati a un gruppo di sicurezza e possono connettersi ad Adobe Campaign.

>[!CAUTION]
>
>Se gli utenti vengono rimossi da un gruppo di sicurezza in Admin Console, rimarranno parte del gruppo di sicurezza di Adobe Campaign e non potranno più effettuare il login ad Adobe Campaign. In questo caso, rimuovete gli indirizzi e-mail degli utenti nell'admin console per evitare di ricevere informazioni riservate.

