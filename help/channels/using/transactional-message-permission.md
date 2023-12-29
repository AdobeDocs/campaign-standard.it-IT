---
title: Autorizzazione per la messaggistica transazionale
description: Scopri le autorizzazioni collegate agli eventi transazionali.
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
feature: Transactional Messaging
role: User
level: Intermediate
exl-id: 995da330-6c86-444b-86b2-61d887f37db4
source-git-commit: 7247fe596494690ac0676196fbb72c6139aeb0c7
workflow-type: tm+mt
source-wordcount: '797'
ht-degree: 1%

---

# Miglioramenti degli eventi transazionali {#transactional-event-improvements}

>[!AVAILABILITY]
>
>Queste funzioni sono attualmente disponibili solo per un set di organizzazioni (disponibilità limitata). Per ulteriori informazioni, contatta il rappresentante Adobe.

Attualmente, in Adobe Campaign Standard, gli utenti senza il gruppo di sicurezza Amministratore non possono accedere, creare o pubblicare eventi transazionali, causando problemi agli utenti aziendali che devono configurare e pubblicare eventi ma non dispongono dei diritti di Amministratore. Inoltre, non è possibile duplicare eventi transazionali.

Abbiamo implementato i seguenti miglioramenti al controllo dell’accesso alla messaggistica transazionale:

* Una nuova **[!UICONTROL Role]**, chiamato **Utente MC**, è stato aggiunto per consentire agli utenti non amministratori di gestire la configurazione degli eventi transazionali. Il **Utente MC** Questo ruolo consente a questi utenti di accedere a eventi e messaggi transazionali, crearli, pubblicarli e annullarne la pubblicazione.

* Le consegne di esecuzione (ovvero i messaggi tecnici creati ogni volta che un messaggio sulle transazioni viene modificato e pubblicato nuovamente o una volta al mese per impostazione predefinita) ora sono impostate su **[!UICONTROL Organizational unit]** del gruppo di sicurezza a cui appartiene l’utente che crea l’evento, anziché essere limitato al **[!UICONTROL Organizational unit]** del **Agente del Centro messaggi (mcExec)** gruppo di sicurezza.

* **Amministratori** ora è possibile duplicare gli eventi transazionali pubblicati, oltre che gli utenti con **Utente MC** ruolo, a condizione che si trovino nello stesso **Unità organizzativa** hierarchy come utente che ha creato l&#39;evento.

## Assegnare il ruolo utente MC {#assign-role}

Per assegnare **Utente MC** ruolo al gruppo di sicurezza:

1. Crea un nuovo **[!UICONTROL Security group]** o aggiornarne uno esistente. [Ulteriori informazioni](../../administration/using/managing-groups-and-users.md).

1. Clic **[!UICONTROL Create element]** per assegnare ruoli al gruppo di sicurezza.

   ![](assets/event_access_1.png)

1. Selezionare l&#39;utente MC **[!UICONTROL Role]** e fai clic su **[!UICONTROL Confirm]**.

   >[!IMPORTANT]
   >
   > Procedere con cautela quando si assegna il ruolo di utente MC agli operatori, in quanto ciò consente loro di annullare la pubblicazione degli eventi.

   ![](assets/event_access_2.png)

1. Una volta configurata, fai clic su **[!UICONTROL Save]**.

Utenti collegati a questo **[!UICONTROL Security group]** ora può accedere, creare e pubblicare eventi e messaggi transazionali.

## Assegnare il gruppo di protezione utente MC {#assign-group}

1. Nell’Admin Console, seleziona la **Prodotti** scheda.

1. Seleziona **Adobe Campaign Standard** quindi scegli l’istanza.

1. Dalla sezione **Profili di prodotto** , seleziona la **Utente MC** gruppo.

1. Clic **Aggiungi utente** e inserisci il nome, il gruppo di utenti o l’indirizzo e-mail del profilo che desideri aggiungere a questo profilo di prodotto.

1. Una volta aggiunto, fai clic su **Salva**.

Utenti aggiunti a questo **[!UICONTROL Security group]** ora può accedere, creare e pubblicare eventi e messaggi transazionali.

## Eventi transazionali duplicati {#duplicate-transactional-events}

Un utente con **Amministratore** gruppo di sicurezza<!--([Functional administrators](../../administration/using/users-management.md#functional-administrators)?)--> può ora duplicare una configurazione di evento se l’evento è stato **pubblicato**.

Inoltre, gli utenti non amministratori con **Utente MC** role può ora accedere alle configurazioni degli eventi, ma la loro autorizzazione per la duplicazione è determinata dal **Unità organizzativa** appartengono a. Se l’utente corrente e l’utente che ha creato l’evento appartengono alla stessa gerarchia di unità organizzative, è consentita la duplicazione.

Ad esempio, se un utente appartenente all’unità organizzativa &quot;France Sales&quot; crea una configurazione evento:

* Un altro utente la cui unità organizzativa è &quot;Paris Sales&quot; sarà in grado di duplicare questo evento, perché &quot;Paris Sales&quot; fa parte dell’unità organizzativa &quot;France Sales&quot;.

* Tuttavia, un utente la cui unità organizzativa è &quot;San Francisco Sales&quot; non sarà in grado di farlo, perché &quot;San Francisco Sales&quot; si trova nell’unità organizzativa &quot;US Sales&quot;, separata dall’unità organizzativa &quot;France Sales&quot;.

Per duplicare una configurazione di evento, segui la procedura riportata di seguito.

1. Fai clic su **Adobe** nell&#39;angolo in alto a sinistra, quindi seleziona **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Event configuration]**.

1. Passa il mouse sulla configurazione dell’evento pubblicato desiderata e seleziona l’opzione **[!UICONTROL Duplicate element]** pulsante.

   ![](assets/message-center_duplicate-button.png)

   >[!CAUTION]
   >
   >Non puoi duplicare una configurazione di evento che non è pubblicata. [Ulteriori informazioni](publishing-transactional-event.md)

1. Viene visualizzato automaticamente l’evento duplicato. Contiene la stessa configurazione definita per l’evento originale, ma presenta **[!UICONTROL Draft]** stato.

   ![](assets/message-center_duplicated-draft-event.png)

1. Il messaggio transazionale corrispondente viene creato automaticamente. Per accedervi, vai a **[!UICONTROL Transactional messages]** > **[!UICONTROL Transactional messages]**.

   ![](assets/message-center_duplicated-message.png)

1. Apri il messaggio appena duplicato. Contiene la stessa struttura definita per il messaggio originale, ma presenta **[!UICONTROL Draft]** anche se il messaggio sulle transazioni originale è stato pubblicato.

   ![](assets/message-center_duplicated-draft-message.png)

1. Ora puoi modificare e personalizzare questo messaggio. Consulta [Modifica dei messaggi transazionali](../../channels/using/editing-transactional-message.md).

## Impatti {#impacts}

La tabella seguente illustra l&#39;impatto di questi miglioramenti:

| Oggetti | Prima di questa modifica | Dopo questa modifica |
|:-: | :--: | :-:|
| Eventi transazionali | Solo gli utenti all’interno di **Amministratore** il gruppo di sicurezza può creare e pubblicare eventi. | Il **Utente MC** Il ruolo consente agli utenti di creare e pubblicare eventi. |
| Messaggi transazionali | I messaggi transazionali sono impostati su **Unità organizzativa** del **Agente del Centro messaggi (mcExec)** gruppo di sicurezza. | I messaggi transazionali sono impostati su **Unità organizzativa** del gruppo di sicurezza a cui appartiene l’utente che crea l’evento/messaggio transazionale. |
| Consegne di esecuzione | Le consegne di esecuzione sono impostate su **Unità organizzativa** del **Agente del Centro messaggi (mcExec)** gruppo di sicurezza. | Le consegne di esecuzione sono impostate su **Unità organizzativa** del gruppo di sicurezza a cui appartiene l’utente che crea l’evento/messaggio transazionale. |
| Eventi transazionali pubblicati | La duplicazione non è possibile per nessun utente. | <ul><li>Utenti con **Amministratore** il gruppo di sicurezza può duplicare gli eventi pubblicati.</li> <li>Utenti con **Utente MC** Il ruolo può duplicare gli eventi pubblicati a condizione che si trovino nello stesso **Unità organizzativa** hierarchy come utente che ha creato l&#39;evento.</li></ul> |


<!--Transactional Message Templates| Transactional Message templates are set to the Organizational unit **All**. | Transaction Message Template will be set to the **Organizational unit** of the security group to which the user creating the message template belongs.-->