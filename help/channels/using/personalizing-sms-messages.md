---
title: Personalizzazione dei messaggi SMS
seo-title: Personalizzazione dei messaggi SMS
description: Personalizzazione dei messaggi SMS
seo-description: Scopri la specificità delle opzioni di translitazione durante la personalizzazione dei messaggi SMS.
page-status-flag: never-activated
uuid: 123 fe 70 c-c 279-40 a 3-88 b 6-6 bfb 2453 ec 83
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: canali
content-type: riferimento
topic-tags: sms-messages
discoiquuid: 7 c 64785 c-e 3 c 2-4 caa-a 547-002990 aae 3 f 9
delivercontext-tags: Deliverycreation, wizard; delivery, smscontent, back; delivery, smscontent, back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b0cf437ec97153b53bd4502171b24286abb25731

---


# Personalizing SMS messages{#personalizing-sms-messages}

The principles for personalizing SMS messages are the same as those for [emails](../../designing/using/inserting-a-personalization-field.md). Tuttavia, è necessario conoscere le opzioni di translitazione in quanto possono influire sulla codifica e quindi sul numero di messaggi SMS da inviare. For more on this, refer to the [Transliteration and SMS length](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration) section.

Di seguito viene fornito un messaggio SMS di esempio contenente campi di personalizzazione che, a seconda che siano stati selezionati o meno, non generino lo stesso numero di invia:

**Hey &lt; firstname &gt; &lt; lastname &gt;, sono disponibili nuovi prodotti. Come and check them out in store!**

* Per un destinatario denominato «John Smith», in quanto non contiene caratteri speciali, Adobe Campaign sceglierà la codifica GSM che autorizza fino a 160 caratteri per SMS. Il messaggio verrà quindi inviato in una singola parte.
* Per un destinatario denominatò Raphaël Forêt ', i caratteri «ë» e «ê» non possono essere codificati in GSM. A seconda se la traslittura è stata abilitata o meno, Adobe Campaign può selezionare tra due comportamenti:

   * Se la traslittura è autorizzata "ë" e "ê" verrà sostituita da "e", il che significa che la codifica GSM può essere utilizzata e quindi è possibile utilizzare fino a 160 caratteri nell'SMS. Questo messaggio verrà inviato come singolo messaggio SMS, ma sarà leggermente alterato.
   * Se la traslittura non è autorizzata, Adobe Campaign sceglie di inviare il messaggio in formato binario (Unicode): Tutti i caratteri verranno quindi inviati come tali. Poiché i messaggi SMS in Unicode sono limitati a 70 caratteri, Adobe Campaign dovrà inviare il messaggio in due parti.

>[!NOTE]
>
>L'algoritmo che sceglie automaticamente la codifica migliore viene eseguita in modo indipendente per ogni messaggio, caso per caso. In tal modo, solo i messaggi personalizzati che richiedono la codifica Unicode verranno inviati in Unicode, tutti gli altri utilizzeranno la codifica GSM.

