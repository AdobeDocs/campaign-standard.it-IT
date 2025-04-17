---
title: Gestione di gruppi e utenti
description: Scopri come creare gruppi di sicurezza e gestire utenti
audience: administration
feature: Access Management
role: Admin
level: Experienced
exl-id: 4b9834ab-0f7c-419e-a210-77a018ba874d
source-git-commit: 52217326ec7f17ab7ce4d058d185b2680681a9c0
workflow-type: tm+mt
source-wordcount: '947'
ht-degree: 65%

---

# Gestione di gruppi e utenti{#managing-groups-and-users}

## Informazioni sui gruppi di sicurezza {#about-security-groups}

>[!IMPORTANT]
>
>I gruppi di sicurezza **[!UICONTROL Access to the deliverability parameters (Deliverability)]** e **[!UICONTROL Message Center agents (mcExec)]** sono solo interni ad Adobe e non devono essere assegnati ad alcun utente.

I gruppi di sicurezza sono insiemi di utenti che condividono gli stessi ruoli e diritti all’interno di un’organizzazione.

Gli utenti devono sempre essere collegati a un gruppo di sicurezza. Questo ti consentirà di assegnare loro ruoli e unità organizzative specifici. Per limitare l&#39;accesso di un utente, non aggiungere l&#39;utente al gruppo Campaign **[!UICONTROL Standard Users]** poiché è collegato all&#39;unità organizzativa **[!UICONTROL All]**.

Per ulteriori informazioni sui ruoli, la tabella nella pagina seguente presenta le operazioni possibili disponibili in base ai ruoli di un utente: [autorizzazioni Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/assets/acs_rights.pdf).

I gruppi di sicurezza predefiniti sono:

* **[!UICONTROL Administrators]**
* **[!UICONTROL Delivery supervisors]**
* **[!UICONTROL Standard Users]**
* **[!UICONTROL Workflow supervisors]**

Si noti che questi gruppi di sicurezza incorporati sono di sola lettura e non possono essere modificati. Per creare un gruppo di sicurezza personalizzato con un set di ruoli specifici, consulta la sezione seguente.

## Creazione di un gruppo di sicurezza e assegnazione di utenti {#creating-a-security-group-and-assigning-users}

>[!IMPORTANT]
>
>In Admin Console, i gruppi di sicurezza sono denominati profili.

Puoi creare gruppi di sicurezza personalizzati se quelli predefiniti non sono sufficienti per gestire gli utenti. Possono essere gestiti dagli amministratori che hanno accesso sia ai menu di amministrazione di Adobe Campaign che a Admin Console. Per ulteriori informazioni su Admin Console, consulta questa [documentazione](https://helpx.adobe.com/it/enterprise/managing/user-guide.html).

In questo caso, devi innanzitutto assegnare agli utenti i due gruppi preconfigurati Utente standard e Amministratore. Questi gruppi di sicurezza limitano alcune funzionalità di Adobe Campaign: l’utente standard dispone dell’accesso di base ad Adobe Campaign, mentre l’amministratore può accedere, ad esempio, ai menu di amministrazione.

Eventuali modifiche apportate ai gruppi di sicurezza in Admin Console vengono sincronizzate non appena gli utenti accedono ad Adobe Campaign.

Quindi, crei un insieme di gruppi di sicurezza Geometrixx e Geometrixx Clothes che limitano l’accesso a seconda delle unità organizzative dell’utente standard e dell’amministratore.

![](assets/ootb_security_group_1.png)

Innanzitutto devi assegnare agli utenti uno dei gruppi di sicurezza predefiniti:

1. In Admin Console, seleziona l&#39;istanza e quindi la scheda **Utenti**.

   ![](assets/manage_security_group_2.png)

1. Fai clic sul pulsante **[!UICONTROL Add user]** e immetti l’indirizzo e-mail dell’utente.
1. Nella scheda **[!UICONTROL Assign Products]**, seleziona l’istanza e quindi il gruppo di sicurezza predefinito **[!UICONTROL Administrators]** dall’elenco a discesa. In questo modo l’utente può accedere ai menu di amministrazione e creare i gruppi di sicurezza successivi.

   ![](assets/ootb_security_group_2.png)

1. Fai clic su **[!UICONTROL Save]** e segui le stesse procedure per assegnare il gruppo di sicurezza predefinito **[!UICONTROL Standard Users]** al nuovo utente.

   ![](assets/ootb_security_group_3.png)

Dopo aver collegato i due utenti ai gruppi di sicurezza predefiniti **[!UICONTROL Administrators]** e **[!UICONTROL Standard users]**, che assegnano ruoli agli utenti, l’utente amministratore può ora creare i due gruppi di sicurezza **Geometrixx** e **Geometrixx Clothes**, che attribuiscono unità organizzative agli utenti oltre ai gruppi di sicurezza predefiniti.

1. In Admin Console, seleziona l&#39;istanza e quindi la scheda **Prodotti**.
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
   * Se le unità organizzative assegnate all’utente si trovano in rami paralleli nella gerarchia, ovvero non hanno un’unità padre assegnata in comune, il sistema seleziona l’unità organizzativa per l’utente e l’utente ha accesso all’unità organizzativa selezionata dal sistema e ai relativi figli.

1. Segui le stesse procedure per assegnare il gruppo di sicurezza Geometrixx Clothes all’utente standard.

   ![](assets/manage_security_group_9.png)

I nuovi gruppi di sicurezza vengono ora creati in Admin Console. Per poter sincronizzarli completamente, devi anche crearli in Adobe Campaign.

L’amministratore deve creare l’insieme dei gruppi di sicurezza utilizzati per assegnare le unità organizzative: Geometrixx e Geometrixx Clothes. Per scoprire come creare unità organizzative, consulta [Creazione e gestione di unità](../../administration/using/organizational-units.md#creating-and-managing-units).

1. Fai clic sul logo **Adobe** nell&#39;angolo in alto a sinistra, quindi seleziona **[!UICONTROL Administration > Users & Security > Security groups]**.
1. Crea il nuovo gruppo di sicurezza e specifica i relativi **[!UICONTROL Label]** e **[!UICONTROL ID]**.

   L’ID deve essere lo stesso scelto in Admin Console.

1. Nel campo **[!UICONTROL User access]**, assegna l’unità organizzativa. In questo caso, al gruppo di sicurezza Geometrixx viene assegnata l’unità organizzativa **[!UICONTROL All]**.

   >[!NOTE]
   >
   >Se stai assegnando un gruppo di sicurezza predefinito agli utenti, dovrai reimpostare l’unità organizzativa.

   ![](assets/manage_security_group_6.png)

1. Puoi anche assegnare ruoli al gruppo di sicurezza. Nel nostro caso, questo passaggio non è necessario perché i gruppi di sicurezza predefiniti **[!UICONTROL Administrators]** e **[!UICONTROL Standard users]** vengono utilizzati per assegnare ruoli.
1. Segui le stesse procedure per creare l’ultimo gruppo di sicurezza Geometrixx Clothes e assegna l’unità organizzativa Geometrixx Clothes.

   ![](assets/manage_security_group_7.png)

Gli utenti sono ora assegnati a un gruppo di sicurezza e possono connettersi ad Adobe Campaign.

>[!IMPORTANT]
>
>Se gli utenti vengono rimossi da un gruppo di sicurezza in Admin Console, rimarranno parte del gruppo di sicurezza di Adobe Campaign e non potranno più accedere ad Adobe Campaign. In questo caso, rimuovi gli indirizzi e-mail degli utenti in Admin Console per impedire che ricevano informazioni riservate.
