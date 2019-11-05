---
title: Personalizzazione dei messaggi SMS
description: Scopri la specificità delle opzioni di traduzione durante la personalizzazione dei messaggi SMS.
page-status-flag: mai attivato
uuid: 123fe70c-c279-40a3-88b6-6bfb2453ec83
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: canali
content-type: reference
topic-tags: sms-messages
discoiquuid: 7c64785c-e3c2-4caa-a547-002990aae3f9
delivercontext-tags: deliveryCreation,procedura guidata;consegna,smsContent,back;consegna,smsContent,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Personalizzazione dei messaggi SMS{#personalizing-sms-messages}

I principi per la personalizzazione dei messaggi SMS sono gli stessi applicati alle [e-mail](../../designing/using/personalization.md#inserting-a-personalization-field). È tuttavia necessario essere consapevoli delle opzioni di traslazione in quanto queste possono influenzare la codifica e quindi il numero di messaggi SMS da inviare. Per ulteriori informazioni, consulta la sezione [Traslitterazione e lunghezza](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration) SMS.

Di seguito è riportato un esempio di SMS contenente campi di personalizzazione che, a seconda che sia stata selezionata o meno la traslitterazione, non genereranno lo stesso numero di invii:

**Hey &lt; NomeNome &gt; &lt; Cognome &gt;, sono ora disponibili nuovi prodotti. Vieni a controllarle al negozio!**

* Per un destinatario denominato 'John Smith', poiché non contiene caratteri speciali, Adobe Campaign sceglierà la codifica GSM che consentirà di immettere fino a 160 caratteri per messaggio SMS. Il messaggio verrà pertanto inviato in una sola parte.
* Per un destinatario denominato Raphaël Forêt, i caratteri 'ë' e 'ê' non possono essere codificati in GSM. A seconda che la traslitterazione sia stata abilitata o meno, Adobe Campaign può selezionare due comportamenti:

   * Se la traslitterazione è autorizzata 'ë' e 'ê' sarà sostituito da 'e', il che significa che la codifica GSM può essere utilizzata e quindi è possibile utilizzare fino a 160 caratteri nell'SMS. Questo messaggio verrà inviato come singolo messaggio SMS, ma verrà leggermente modificato.
   * Se la traslitterazione non è autorizzata, Adobe Campaign sceglierà di inviare il messaggio in formato binario (Unicode): tutti i caratteri verranno quindi inviati come tali. Poiché i messaggi SMS in Unicode sono limitati a 70 caratteri, Adobe Campaign dovrà inviare il messaggio in due parti.

>[!NOTE]
>
>L'algoritmo che sceglie automaticamente la codifica migliore viene eseguito in modo indipendente per ogni messaggio, caso per caso. In questo modo, solo i messaggi personalizzati che richiedono la codifica Unicode verranno inviati in Unicode; tutti gli altri utilizzeranno la codifica GSM.

## Mittente SMS {#sms-sender}

Potete personalizzare il nome del mittente SMS. Per ulteriori informazioni, consulta la sezione relativa alla configurazione [](../../administration/using/configuring-sms-channel.md#configuring-sms-properties) SMS.
