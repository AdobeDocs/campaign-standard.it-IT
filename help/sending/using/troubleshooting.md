---
title: Risoluzione dei problemi di recapito messaggi in Adobe Campaign Standard
description: Scopri cosa fare in caso di problemi di recapito messaggi con Adobe Campaign Standard.
audience: sending
content-type: reference
topic-tags: sheduling-messages
context-tags: delivery,schedule,back
feature: Deliverability
role: User
level: Intermediate
exl-id: 0470b986-c00a-4441-8621-82c7112a9953
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '467'
ht-degree: 2%

---

# Risoluzione dei problemi{#troubleshooting}

Si è verificato un problema di recapito messaggi? La soluzione potrebbe essere disponibile qui.

## Stesso messaggio di errore per un ISP {#same-error-for-an-isp}

**Perché viene sempre visualizzato lo stesso messaggio di errore per un ISP specifico?**

Se ricevi sempre lo stesso messaggio di errore per un ISP, l’e-mail o l’IP potrebbero essere stati rilevati come difettosi dall’ISP. Effettua le seguenti raccomandazioni:
* Controlla se ricevi un’ampia percentuale di errori collegati a indirizzi e-mail inesistenti (**Utente sconosciuto** errori).
* Aggiorna i moduli di abbonamento per rilevare eventuali errori nei nomi di dominio immessi (ad esempio: gmaul.com o yaho.com).
* Se noti errori che indicano che i tuoi messaggi sono dichiarati come spam o che i tuoi messaggi sono costantemente bloccati, prova ad escludere dal target i destinatari che non hanno aperto o cliccato in uno dei tuoi messaggi negli ultimi 12 mesi.

Se il problema persiste, contatta il servizio commerciale, il servizio di consegna o il supporto Adobe Campaign.

## Inserisco nell&#39;elenco Bloccati rispetto alla quarantena {#denylist-versus-quarantine}

* **Qual è la differenza tra un indirizzo e-mail nel inserisco nell&#39;elenco Bloccati di e un indirizzo e-mail in quarantena?**

   * Stato **[!UICONTROL On denylist]** è il risultato di un [ciclo di feedback](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html#feedback-loops) (quando una persona segnala un messaggio come spam).

   * Stato **[!UICONTROL Quarantined]** è il risultato di un mancato recapito morbido o permanente.
   Per ulteriori informazioni, consulta questa [sezione](../../sending/using/understanding-quarantine-management.md#quarantine-vs-denylist).

* **Cosa significano i diversi motivi di errore di quarantena?**

   Ecco 10 possibili motivi: non definito, utente sconosciuto, dominio non valido, indirizzo in fase di inserisco nell&#39;elenco Bloccati, rifiutato, errore ignorato, non raggiungibile, account disabilitato, cassetta postale piena, non connesso.

   Per ulteriori informazioni, consulta [Informazioni sulla gestione della quarantena](../../sending/using/understanding-quarantine-management.md).

## Rimozione dal inserisco nell&#39;elenco Bloccati {#removing-from-denylist}

* **Uno dei destinatari è stato aggiunto al elenco Bloccati per errore. Come è possibile rimuoverli dal inserisco nell&#39;elenco Bloccati di in modo da poter iniziare a inviare nuovamente i messaggi?**

   * Vai a **[!UICONTROL Administration > Channels > Quarantines > Addresses]**.
   * Nei dettagli del record corrispondente, imposta il valore del **[!UICONTROL Status]** campo a **[!UICONTROL Valid]**.
   * Salvare il record.

* **Come posso scoprire se uno dei miei IP è in inserito nell&#39;elenco Bloccati di? Come posso rimuovere gli IP da un inserisco nell&#39;elenco Bloccati di?**

   Per verificare se l’indirizzo IP è in inserito nell&#39;elenco Bloccati, puoi utilizzare vari siti web, ad esempio:
   * [Casella degli strumenti MX](https://mxtoolbox.com/)
   * [Qual è il mio indirizzo IP](https://whatismyipaddress.com)

   In genere, il risultato della verifica dell’indirizzo IP restituirà un elenco contenente i dettagli del inserisco nell&#39;elenco Bloccati di e anche il nome del sito web che ha bloccato l’indirizzo IP.

   Facendo clic sul collegamento corrispondente, è possibile accedere ai dettagli del sito Web.

   Quindi puoi richiedere che il tuo sito web venga cancellato dal sito web che ha aggiunto l’indirizzo IP al suo inserisco nell&#39;elenco Bloccati di.

   >[!NOTE]
   >
   >Il processo di cancellazione dall’elenco può variare a seconda del sito web. Alcuni siti richiedono la creazione di un account, mentre altri richiedono solo che tu fornisca l’indirizzo IP.
