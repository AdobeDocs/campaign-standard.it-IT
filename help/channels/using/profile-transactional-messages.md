---
title: Messaggi sulle transazioni di profilo
description: Scopri come creare e pubblicare un messaggio transazionale di profilo.
page-status-flag: never-activated
uuid: a8efe979-74ae-46ff-a305-b86a90679581
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: transactional-messaging
discoiquuid: dcb90afc-42c3-419e-8345-79cddf969e41
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 1b1fb4a0dc0f7881e24e10f8ac171feab2ac8cba
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Messaggi sulle transazioni di profilo{#profile-transactional-messages}

Puoi inviare messaggi transazionali basati sui profili di marketing dei clienti, che ti consentono di:

* Applicare regole di tipologie di marketing, ad esempio **[!UICONTROL Address on denylist]** o [regole di affaticamento](../../sending/using/fatigue-rules.md);
* Includere il collegamento di annullamento all’abbonamento nei messaggi;
* Aggiungere messaggi transazionali al reporting globale sulla distribuzione;
* Utilizzare messaggi transazionali nel customer journey.

Dopo la creazione e la pubblicazione di un evento (l’abbandono del carrello come nell’[esempio](../../channels/using/getting-started-with-transactional-msg.md#transactional-messaging-operating-principle)illustrato sopra), il messaggio transazionale corrispondente viene creato automaticamente.

I passaggi di configurazione sono descritti nella sezione [Configurazione di un evento per l’invio di un messaggio transazionale di profilo](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message).

Per fare in modo che l’evento attivi l’invio di un messaggio transazionale, devi personalizzare il messaggio, verificarlo e pubblicarlo.

>[!NOTE]
>
>Per accedere ai messaggi transazionali, devi far parte del gruppo di sicurezza **[!UICONTROL Administrators (all units)]**.
>
>Le regole di affaticamento sono compatibili con i messaggi transazionali di profilo. Consulta [Regole di affaticamento](../../sending/using/fatigue-rules.md).

## Invio di un messaggio transazionale di profilo {#sending-a-profile-transactional-message}

I passaggi per creare, personalizzare e pubblicare un messaggio transazionale di profilo sono gli stessi che per un messaggio transazionale di evento. Vedi [Messaggi transazionali di evento](../../channels/using/event-transactional-messages.md).

Le differenze sono elencate di seguito.

1. Passa al messaggio transazionale creato per modificarlo.
1. Nel messaggio transazionale, fai clic sulla sezione **[!UICONTROL Content]**. Oltre al modello transazionale, puoi anche scegliere qualsiasi modello di e-mail che effettua il targeting su **[!UICONTROL Profile]**.

   ![](assets/message-center_marketing_templates.png)

1. Seleziona il modello di e-mail predefinito.

   Analogamente a tutte le e-mail di marketing, include un collegamento di annullamento all’abbonamento.

   ![](assets/message-center_marketing_perso_unsubscription.png)

   Inoltre, a differenza delle configurazioni basate su eventi in tempo reale, puoi accedere direttamente a tutte le informazioni sul profilo per personalizzare il messaggio. Consulta [Inserimento di un campo di personalizzazione](../../designing/using/personalization.md#inserting-a-personalization-field).

1. Salva le modifiche e pubblica il messaggio. Consulta [Pubblicazione di un messaggio transazionale](../../channels/using/event-transactional-messages.md#publishing-a-transactional-message).

## Monitoraggio della consegna dei messaggi transazionali di profilo {#monitoring-a-profile-transactional-message-delivery}

Dopo la pubblicazione del messaggio e il completamento dell’integrazione con il sito puoi monitorare la consegna.

1. Fai clic sull’icona in basso a destra del blocco **[!UICONTROL Deployment]** per visualizzare il registro di consegna del messaggio.

   Per ulteriori informazioni sull’accesso ai log, consulta [Monitoraggio della consegna](../../sending/using/monitoring-a-delivery.md).

1. Seleziona la scheda **[!UICONTROL Sending logs]**. Nella colonna **[!UICONTROL Status]**, **[!UICONTROL Sent]** indica che un profilo ha acconsentito.

   ![](assets/message-center_marketing_sending_logs.png)

1. Select the **[!UICONTROL Exclusions logs]** tab to view recipients who have been excluded from the message target, such as addresses on denylist.

   ![](assets/message-center_marketing_exclusion_logs.png)

Per ogni profilo che ha rinunciato, la regola di tipologia **[!UICONTROL Address on denylist]** ha escluso il destinatario corrispondente.

Questa regola fa parte di una tipologia specifica che si applica a tutti i messaggi transazionali basati sulla tabella **[!UICONTROL Profile]**.

![](assets/message-center_marketing_typology.png)

**Argomenti correlati**:

* [Integrazione del sito](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)
* [Tipologie](../../sending/using/about-typology-rules.md)

