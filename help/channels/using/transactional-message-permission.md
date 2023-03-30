---
title: Autorizzazione per la messaggistica transazionale
description: Scopri le autorizzazioni collegate agli eventi transazionali.
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
hide: true
hidefromtoc: true
feature: Transactional Messaging
role: User
level: Intermediate
source-git-commit: d7e0912dd7d19a1f5dd2172235f28a40e130cac1
workflow-type: tm+mt
source-wordcount: '453'
ht-degree: 0%

---

# Autorizzazione per la messaggistica transazionale {#transactional-message-permission}

Attualmente, in Adobe Campaign Standard, gli utenti senza il gruppo di sicurezza Amministratore non possono accedere, creare o pubblicare eventi, il che causa problemi agli utenti aziendali che devono configurare e pubblicare eventi ma non dispongono dei diritti di amministratore.

Abbiamo implementato i seguenti miglioramenti al controllo degli accessi alla messaggistica transazionale:

* Nuovo **[!UICONTROL Role]**, chiamato **Utente MC**&#x200B;è stato aggiunto per consentire agli utenti non amministratori di gestire gli eventi transazionali. La **Utente MC** Il ruolo consente a questi utenti di accedere, creare, pubblicare e annullare la pubblicazione di eventi e messaggi transazionali.

* Le consegne figlio sono ora impostate su **[!UICONTROL Organizational unit]** del gruppo di sicurezza a cui appartiene l&#39;utente che crea il modello di messaggio, anziché essere limitato al **[!UICONTROL Organizational unit]** del **Agente del Centro messaggi (mcExec)** gruppo di sicurezza.

* Il valore predefinito **Esecuzione centro messaggi (mcExec)** campaign, che raccoglie i messaggi transazionali relativi alle consegne figlio, è ora impostato sull’unità organizzativa . **Tutto** consentire a tutti gli utenti di visualizzare i rapporti sulle consegne figlio.

Per assegnare la **Utente MC** ruolo:

1. Crea un nuovo **[!UICONTROL Security group]** o aggiorna una esistente. [Ulteriori informazioni](../../administration/using/managing-groups-and-users.md).

1. Fai clic su **[!UICONTROL Create element]** per assegnare ruoli al gruppo di sicurezza.

   ![](assets/event_access_1.png)

1. Selezionare l&#39;utente MC **[!UICONTROL Role]** e fai clic su **[!UICONTROL Confirm]**.

   >[!IMPORTANT]
   >
   > Procedi con cautela quando assegni il ruolo MC User agli operatori, in quanto ciò consente loro di annullare la pubblicazione degli eventi.

   ![](assets/event_access_2.png)

1. Una volta configurata, fai clic su **[!UICONTROL Save]**.

Utenti collegati a questo **[!UICONTROL Security group]** ora può accedere, creare e pubblicare eventi e messaggi transazionali.

La tabella seguente illustra l’impatto di questa funzione sul controllo degli accessi:

| Oggetti | Prima di questa modifica | Dopo questa modifica |
|:-: | :--: | :-:|
| Campagna mcExec (Message Center Execution) | **Esecuzione centro messaggi (mcExec)** la campagna è impostata sull’unità organizzativa della **Agente del Centro messaggi (mcExec)** gruppo di sicurezza. | **Esecuzione centro messaggi (mcExec)** campagna è impostata sull’unità organizzativa **Tutto** per consentire l’associazione di tutte le consegne figlio a questa campagna.</br> Tutti gli utenti potranno visualizzare i rapporti sulle consegne figlie, ma avranno accesso in sola lettura al contenuto della consegna. |
| Consegne di bambini | Le consegne figlio sono impostate su **Unità organizzativa** del **Agente del Centro messaggi (mcExec)** gruppo di sicurezza. | Le consegne figlio saranno impostate su **Unità organizzativa** del gruppo di sicurezza a cui appartiene l&#39;utente che crea il modello di messaggio. |
| Modello di messaggio | I modelli di messaggio sono impostati su **Unità organizzativa** del **Agente del Centro messaggi (mcExec)** gruppo di sicurezza. | I modelli di messaggio saranno impostati su **Unità organizzativa** del gruppo di sicurezza a cui appartiene l&#39;utente che crea il modello di messaggio. |
| Eventi transazionali | Solo gli utenti all&#39;interno della **Amministratore** gruppo di sicurezza può creare e pubblicare eventi. | La **Utente MC** Il ruolo consente agli utenti di creare e pubblicare eventi. |
| Modelli di messaggi transazionali | I modelli di messaggio transazionale sono impostati sull’unità organizzativa . **Tutto**. | Il modello di messaggio di transazione sarà impostato su **Unità organizzativa** del gruppo di sicurezza a cui appartiene l&#39;utente che crea il modello di messaggio. |