---
title: Gestione di gruppi e utenti
description: Scopri come creare gruppi di sicurezza e gestire utenti.
page-status-flag: never-activated
uuid: b3a3a2e3-9d69-4231-b724-8f37419f7a61
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: users-and-security
discoiquuid: 12f896ab-ee79-4d96-976d-cf34643491b4
context-tags: user,overview;user,main;security,overview;security,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '926'
ht-degree: 97%

---


# Gestione di gruppi e utenti{#managing-groups-and-users}

## Informazioni sui gruppi di sicurezza {#about-security-groups}

I gruppi di sicurezza sono insiemi di utenti che condividono gli stessi ruoli e diritti all’interno di un’organizzazione.

Gli utenti devono sempre essere collegati a un gruppo di sicurezza. In questo modo, puoi assegnare loro ruoli e unità organizzative specifici.

Per ulteriori informazioni sui ruoli, le tabelle della pagina seguente presentano diverse operazioni disponibili in base ai ruoli di un utente: [Autorizzazioni di Adobe Campaign Standard](https://docs.campaign.adobe.com/doc/standard/en/Technotes/AdobeCampaign-ACSRights.pdf).

I gruppi di sicurezza predefiniti sono:

* **[!UICONTROL Administrators]**
* **[!UICONTROL Delivery supervisors]**
* **[!UICONTROL Message Center agents]**
* **[!UICONTROL Standard Users]**
* **[!UICONTROL Workflow supervisors]**

Se un utente non è collegato ad alcun gruppo di sicurezza, non può accedere ad Adobe Campaign.

Per limitare l’accesso di un utente, non aggiungere l’utente al gruppo di utenti di Campaign Standard, in quanto è collegato all’unità organizzativa **[!UICONTROL All]**.

>[!NOTE]
>
>Per impostazione predefinita, l’unità organizzativa **[!UICONTROL All (all)]** viene assegnata al gruppo di sicurezza **[!UICONTROL Administrators]**. È di sola lettura e non può essere modificata.

## Creazione di un gruppo di sicurezza e assegnazione di utenti {#creating-a-security-group-and-assigning-users}

>[!IMPORTANT]
>
>In Admin Console, i gruppi di sicurezza sono denominati profili.

Puoi creare gruppi di sicurezza personalizzati se quelli predefiniti non sono sufficienti per gestire gli utenti. Gli amministratori che hanno accesso ai menu di amministrazione di Adobe Campaign e Admin Console possono gestirli. Per ulteriori informazioni su Admin Console, consulta questa [documentazione](https://helpx.adobe.com/it/enterprise/managing/user-guide.html).

In questo caso, devi innanzitutto assegnare agli utenti i due gruppi preconfigurati Utente standard e Amministratore. Questi gruppi di sicurezza limitano alcune funzionalità di Adobe Campaign: l’utente standard dispone dell’accesso di base ad Adobe Campaign, mentre l’amministratore può accedere, ad esempio, ai menu di amministrazione.

Eventuali modifiche apportate ai gruppi di sicurezza in Admin Console vengono sincronizzate non appena gli utenti accedono ad Adobe Campaign.

Quindi, crei un insieme di gruppi di sicurezza Geometrixx e Geometrixx Clothes che limitano l’accesso a seconda delle unità organizzative dell’utente standard e dell’amministratore.

![](assets/ootb_security_group_1.png)

Innanzitutto devi assegnare agli utenti uno dei gruppi di sicurezza predefiniti:

1. In Admin Console, seleziona l’istanza e quindi la scheda **Users**.

   ![](assets/manage_security_group_2.png)

1. Fai clic sul pulsante **[!UICONTROL Add user]** e immetti l’indirizzo e-mail dell’utente.
1. Nella scheda **[!UICONTROL Assign Products]**, seleziona l’istanza e quindi il gruppo di sicurezza predefinito **[!UICONTROL Administrators]** dall’elenco a discesa. In questo modo l’utente può accedere ai menu di amministrazione e creare i gruppi di sicurezza successivi.

   ![](assets/ootb_security_group_2.png)

1. Fai clic su **[!UICONTROL Save]** e segui le stesse procedure per assegnare il gruppo di sicurezza predefinito **[!UICONTROL Standard Users]** al nuovo utente.

   ![](assets/ootb_security_group_3.png)

Dopo aver collegato i due utenti ai gruppi di sicurezza predefiniti **[!UICONTROL Administrators]** e **[!UICONTROL Standard users]**, che assegnano ruoli agli utenti, l’utente amministratore può ora creare i due gruppi di sicurezza **Geometrixx** e **Geometrixx Clothes**, che attribuiscono unità organizzative agli utenti oltre ai gruppi di sicurezza predefiniti.

1. In Admin Console, seleziona l’istanza e quindi la scheda **Products**.
1. Fai clic sul pulsante **New Profile** per creare il gruppo di sicurezza **Geometrixx**.

   ![](assets/create_security_1.png)

1. Digita il testo **[!UICONTROL Profile name]** seguendo questa sintassi esatta: **[!UICONTROL Campaign Standard- instance name - ID of the security group]** e fai clic su **[!UICONTROL Done]**.

   L’ID scelto viene quindi utilizzato durante la creazione del gruppo di sicurezza in Adobe Campaign.

   >[!NOTE]
   >
   >Se la sintassi illustrata sopra non funziona con un’istanza precedente, deve essere sostituita da **[!UICONTROL Campaign - instance name - ID of the security group]**.

   ![](assets/manage_security_group_1.png)

1. Quindi, segui le stesse procedure per creare il gruppo di sicurezza **Geometrixx Clothes**.
1. Assegna il gruppo di sicurezza all’utente selezionando la scheda **[!UICONTROL Users]**.

   ![](assets/manage_security_group_2.png)

1. Fai clic sull’utente creato in precedenza e quindi sull’icona ![](assets/managing_security_group_10.png) nella categoria **[!UICONTROL Products]**.

   Seleziona **[!UICONTROL Edit products assigned directly]** per iniziare ad assegnare un nuovo gruppo di sicurezza all’utente.

   ![](assets/manage_security_group_8.png)

1. Nella scheda **[!UICONTROL Assign Products]**, seleziona l’istanza e quindi i gruppi di sicurezza Geometrixx creati in precedenza dall’elenco a discesa, per assegnarla all’utente amministratore.

   Fai clic su **[!UICONTROL Save]**.

   ![](assets/manage_security_group_3.png)

   Se un utente fa parte di diversi gruppi:

   * I ruoli dei diversi gruppi sono cumulativi. In questo caso gli utenti si trovano in due gruppi diversi: uno che agisce sui ruoli e l’altro sulle unità.
   * Si tratta dell’unità più alta della gerarchia che viene utilizzata (vedi esempio nella sezione [Unità organizzative](../../administration/using/organizational-units.md)).
   * L’utente non riesce più a connettersi se le unità hanno lo stesso livello equivalente e si trovano in rami paralleli nella gerarchia.

1. Segui le stesse procedure per assegnare il gruppo di sicurezza Geometrixx Clothes all’utente standard.

   ![](assets/manage_security_group_9.png)

I nuovi gruppi di sicurezza vengono ora creati in Admin Console. Per poter sincronizzarli completamente, devi anche crearli in Adobe Campaign.

L’amministratore deve creare l’insieme dei gruppi di sicurezza utilizzati per assegnare le unità organizzative: Geometrixx e Geometrixx Clothes. Per scoprire come creare unità organizzative, consulta [Creazione e gestione di unità](../../administration/using/organizational-units.md#creating-and-managing-units).

1. Fai clic sul logo di **[!UICONTROL Adobe Campaign]**, nell’angolo in alto a sinistra, quindi seleziona **[!UICONTROL Administration > Users & Security > Security groups]**.
1. Crea il nuovo gruppo di sicurezza e specifica i relativi **[!UICONTROL Label]** e **[!UICONTROL ID]**.

   L’ID deve essere lo stesso scelto in Admin Console.

1. Nel campo **[!UICONTROL User access]**, assegna l’unità organizzativa. In questo caso, al gruppo di sicurezza Geometrixx viene assegnata l’unità organizzativa **[!UICONTROL All]**.

   >[!NOTE]
   >
   >Se assegnate un gruppo di sicurezza out-of-the-box agli utenti, dovrete reimpostare l&#39;unità organizzativa.

   ![](assets/manage_security_group_6.png)

1. Puoi anche assegnare ruoli al gruppo di sicurezza. Nel nostro caso, questo passaggio non è necessario perché i gruppi di sicurezza predefiniti **[!UICONTROL Administrators]** e **[!UICONTROL Standard users]** vengono utilizzati per assegnare ruoli.
1. Segui le stesse procedure per creare l’ultimo gruppo di sicurezza Geometrixx Clothes e assegna l’unità organizzativa Geometrixx Clothes.

   ![](assets/manage_security_group_7.png)

Gli utenti sono ora assegnati a un gruppo di sicurezza e possono connettersi ad Adobe Campaign.

>[!IMPORTANT]
>
>Se gli utenti vengono rimossi da un gruppo di sicurezza in Admin Console, continuano a far parte dell’unità organizzativa di Adobe Campaign e non possono più accedere ad Adobe Campaign. In questo caso, rimuovi gli indirizzi e-mail degli utenti in Admin Console per impedire che ricevano informazioni riservate.

