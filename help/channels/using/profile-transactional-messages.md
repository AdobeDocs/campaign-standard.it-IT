---
title: Messaggi sulle transazioni di profilo
description: Scopri come creare e pubblicare un messaggio di transazione profilo.
page-status-flag: mai attivato
uuid: a8efe979-74ae-46ff-a305-b86a90679581
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: canali
content-type: reference
topic-tags: messaggistica transazionale
discoiquuid: dcb90afc-42c3-419e-8345-79cdf969e41
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Messaggi sulle transazioni di profilo{#profile-transactional-messages}

Puoi inviare messaggi transazionali basati sui profili di marketing dei clienti, per:

* Applica regole di tipologia di marketing, ad esempio **[!UICONTROL Blacklisted address]** o [regole](../../administration/using/fatigue-rules.md)di affaticamento.
* Includi il collegamento di annullamento della sottoscrizione nei messaggi.
* Aggiungete i messaggi transazionali al reporting globale sulla distribuzione.
* Utilizza i messaggi transazionali nel percorso del cliente.

Dopo aver creato e pubblicato un evento (l'abbandono del carrello come nell' [esempio](../../channels/using/about-transactional-messaging.md#transactional-messaging-operating-principle) precedente), il messaggio transazionale corrispondente viene creato automaticamente.

I passaggi di configurazione sono descritti nella sezione [Configurazione di un evento per l’invio di un messaggio](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message) transazionale di profilo.

Affinché l'evento attivi l'invio di un messaggio transazionale, è necessario personalizzare il messaggio, testarlo e pubblicarlo.

>[!NOTE]
>
>Per accedere ai messaggi transazionali, devi far parte del gruppo di **[!UICONTROL Administrators (all units)]** sicurezza.
>
>Le regole di Fatigue sono compatibili con i messaggi transazionali del profilo. Consultate [Regole](../../administration/using/fatigue-rules.md)di fatica.

## Invio di un messaggio di transazione profilo {#sending-a-profile-transactional-message}

I passaggi per creare, personalizzare e pubblicare un messaggio di transazione profilo sono gli stessi che per un messaggio di transazione evento. See [Event transactional messages](../../channels/using/event-transactional-messages.md).

Le differenze sono elencate di seguito.

1. Vai al messaggio transazionale creato per modificarlo.
1. Nel messaggio di transazione, fai clic sulla **[!UICONTROL Content]** sezione. Oltre al modello di transazione, potete anche scegliere qualsiasi targeting per modello e-mail **[!UICONTROL Profile]**.

   ![](assets/message-center_marketing_templates.png)

1. Selezionate il modello e-mail predefinito.

   Analogamente a tutte le e-mail di marketing, include un collegamento per annullare l'iscrizione.

   ![](assets/message-center_marketing_perso_unsubscription.png)

   Inoltre, a differenza delle configurazioni basate su eventi in tempo reale, puoi accedere direttamente a tutte le informazioni sul profilo per personalizzare il messaggio. Consultate [Inserimento di un campo](../../designing/using/personalization.md#inserting-a-personalization-field)di personalizzazione.

1. Salva le modifiche e pubblica il messaggio. Consultate [Pubblicazione di un messaggio](../../channels/using/event-transactional-messages.md#publishing-a-transactional-message)transazionale.

## Monitoraggio della distribuzione di messaggi transazionali di profilo {#monitoring-a-profile-transactional-message-delivery}

Dopo aver pubblicato il messaggio e aver completato l'integrazione con il sito, puoi monitorare la distribuzione.

1. Per visualizzare il registro di distribuzione dei messaggi, fai clic sull'icona in basso a destra del **[!UICONTROL Deployment]** blocco.

   Per ulteriori informazioni sull’accesso ai registri, consulta [Monitoraggio della distribuzione](../../sending/using/monitoring-a-delivery.md).

1. Selezionate la **[!UICONTROL Sending logs]** scheda. Nella **[!UICONTROL Status]** colonna, **[!UICONTROL Sent]** indica che un profilo ha acconsentito.

   ![](assets/message-center_marketing_sending_logs.png)

1. Selezionate la **[!UICONTROL Exclusions logs]** scheda per visualizzare i destinatari che sono stati esclusi dalla destinazione del messaggio, ad esempio gli indirizzi in lista nera.

   ![](assets/message-center_marketing_exclusion_logs.png)

Per qualsiasi profilo che ha rinunciato, la regola di **[!UICONTROL Blacklisted address]** tipologia ha escluso il destinatario corrispondente.

Questa regola fa parte di una tipologia specifica che si applica a tutti i messaggi transazionali basati sulla **[!UICONTROL Profile]** tabella.

![](assets/message-center_marketing_typology.png)

**Argomenti** correlati:

* [Integrazione del sito](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)
* [Tipologie](../../administration/using/about-typology-rules.md)

