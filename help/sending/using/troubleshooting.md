---
solution: Campaign Standard
product: campaign
title: Risoluzione dei problemi di recapito messaggi in Adobe Campaign Standard
description: Scopri cosa fare quando si verificano problemi di recapito messaggi con Adobe Campaign Standard.
audience: sending
content-type: reference
topic-tags: sheduling-messages
context-tags: delivery,schedule,back
feature: Consegna
role: Professionista
level: Intermedio
translation-type: tm+mt
source-git-commit: fb9a6218bb754f803affde1fdf6c6fc01570126f
workflow-type: tm+mt
source-wordcount: '471'
ht-degree: 2%

---


# Risoluzione dei problemi{#troubleshooting}

Si verifica un problema di recapito messaggi? Puoi trovare la soluzione qui.

## Stesso messaggio di errore per un ISP {#same-error-for-an-isp}

**Perché ricevo sempre lo stesso messaggio di errore per un particolare ISP?**

Se ricevi sempre lo stesso messaggio di errore per un ISP, l&#39;e-mail o l&#39;IP potrebbe essere stato rilevato come difettoso dall&#39;ISP. Eseguite le seguenti raccomandazioni:
* Controlla se ricevi una grande percentuale di errori collegati a indirizzi e-mail inesistenti (**Utente sconosciuto** non riusciti).
* Aggiorna i moduli di abbonamento per rilevare eventuali errori nei nomi di dominio immessi (ad esempio: gmaul.com o yaho.com).
* Se noti degli errori che indicano che i messaggi sono dichiarati come spam o che i messaggi sono costantemente bloccati, prova ad escludere i destinatari che non hanno aperto o fatto clic in uno dei tuoi messaggi negli ultimi 12 mesi dal target.

Se il problema persiste, contatta il servizio commerciale o di recapito messaggi o il supporto Adobe Campaign.

## Elenco Bloccati a confronto {#denylist-versus-quarantine}

* **Qual è la differenza tra un indirizzo e-mail elenco Bloccati e un indirizzo e-mail messo in quarantena?**

   * Lo stato **[!UICONTROL On denylist]** è il risultato di un [ciclo di feedback](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html#feedback-loops) (quando una persona segnala un messaggio come spam).

   * Lo stato **[!UICONTROL Quarantined]** è il risultato di un messaggio non recapitato morbido o rigido.
   Per ulteriori informazioni, consulta questa [sezione](../../sending/using/understanding-quarantine-management.md#quarantine-vs-denylist).

* **Cosa significano i diversi motivi di errore di quarantena?**

   Ecco 10 possibili ragioni: non definito, utente sconosciuto, dominio non valido, indirizzo elenco Bloccati, rifiutato, errore ignorato, non raggiungibile, account disabilitato, cassetta postale piena, non connesso.

   Per ulteriori informazioni, consulta [Informazioni sulla gestione della quarantena](../../sending/using/understanding-quarantine-management.md).

## Rimozione dal elenco Bloccati {#removing-from-denylist}

* **Uno dei miei destinatari è stato aggiunto al elenco Bloccati per errore. Come rimuoverli dal elenco Bloccati in modo da poter iniziare a inviarli nuovamente?**

   * Vai a **[!UICONTROL Administration > Channels > Quarantines > Addresses]**.
   * Nei dettagli del record corrispondente, imposta il valore del campo **[!UICONTROL Status]** su **[!UICONTROL Valid]**.
   * Salvare il record.

* **Come posso scoprire se uno dei miei IP è elenco Bloccati? Come posso rimuovere gli IP da un elenco Bloccati?**

   Per verificare se l&#39;indirizzo IP è elenco Bloccati, puoi utilizzare vari siti web per verificarlo, ad esempio:
   * [Casella degli strumenti MX](https://mxtoolbox.com/)
   * [Qual è il mio indirizzo IP?](https://whatismyipaddress.com)

   Generalmente, il risultato del controllo dell&#39;indirizzo IP restituirà un elenco contenente i dettagli del elenco Bloccati e anche il nome del sito web che ha bloccato l&#39;indirizzo IP.

   Facendo clic sul collegamento corrispondente, puoi accedere ai dettagli del sito web.

   Quindi, puoi richiedere che il tuo sito web venga cancellato dal sito web che ha aggiunto l&#39;indirizzo IP al suo elenco Bloccati.

   >[!NOTE]
   >
   >Il processo di eliminazione può variare a seconda del sito web. Alcuni siti richiedono la creazione di un account, mentre altri richiedono solo che tu fornisca l’indirizzo IP.
