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
TQID: https://experienceleague.adobe.com/UyKD0H4ffjVDfJRubitjN0pJs2DQbswTlOPNzvU6zLo
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
subfeature_v2:
  - id: a39dbcf0-89cb-4765-9bcb-cf9dfbe2875f
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2:
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 475
ht-degree: 1%

---

# Risoluzione dei problemi{#troubleshooting}

Si è verificato un problema di recapito messaggi? La soluzione potrebbe essere disponibile qui.

## Stesso messaggio di errore per un ISP {#same-error-for-an-isp}

**Perché viene visualizzato sempre lo stesso messaggio di errore per un ISP specifico?**

Se ricevi sempre lo stesso messaggio di errore per un ISP, l’e-mail o l’IP potrebbero essere stati rilevati come difettosi dall’ISP. Effettua le seguenti raccomandazioni:

* Verifica se ricevi una grande percentuale di errori collegati a indirizzi e-mail inesistenti (**Utente sconosciuto** errori).
* Aggiorna i moduli di abbonamento per rilevare eventuali errori nei nomi di dominio immessi (ad esempio: gmaul.com o yaho.com).
* Se noti errori che indicano che i tuoi messaggi sono dichiarati come spam o che i tuoi messaggi sono costantemente bloccati, prova ad escludere dal target i destinatari che non hanno aperto o cliccato in uno dei tuoi messaggi negli ultimi 12 mesi.

Se il problema persiste, contatta il servizio commerciale, il servizio di consegna o il supporto Adobe Campaign.

## di Inserisco nell&#39;elenco Bloccati rispetto alla quarantena {#denylist-versus-quarantine}

* **Qual è la differenza tra un indirizzo e-mail nel inserisco nell&#39;elenco Bloccati di e un indirizzo e-mail in quarantena?**

   * Lo stato **[!UICONTROL On denylist]** è il risultato di un [ciclo di feedback](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html#feedback-loops) (quando una persona segnala un messaggio come spam).

   * Lo stato **[!UICONTROL Quarantined]** è il risultato di un mancato recapito non permanente o permanente.

  Per ulteriori informazioni, consulta questa [sezione](../../sending/using/understanding-quarantine-management.md#quarantine-vs-denylist).

* **Che cosa significano i diversi motivi di errore di quarantena?**

  Ecco 10 possibili motivi: non definito, utente sconosciuto, dominio non valido, indirizzo in fase di inserisco nell&#39;elenco Bloccati di, rifiutato, errore ignorato, non raggiungibile, account disabilitato, cassetta postale piena, non connesso.

  Per ulteriori informazioni, consulta [Informazioni sulla gestione della quarantena](../../sending/using/understanding-quarantine-management.md).

## Rimozione dal inserisco nell&#39;elenco Bloccati di {#removing-from-denylist}

* **Uno dei destinatari è stato aggiunto per errore al elenco Bloccati di. Come è possibile rimuoverli dal inserisco nell&#39;elenco Bloccati di in modo da poter iniziare a inviare nuovamente i messaggi?**

   * Vai a **[!UICONTROL Administration > Channels > Quarantines > Addresses]**.
   * Nei dettagli del record corrispondente, impostare il valore del campo **[!UICONTROL Status]** su **[!UICONTROL Valid]**.
   * Salvare il record.

* **Come posso sapere se uno dei miei IP si trova in modalità di inserisce nell&#39;elenco Bloccati di un IP? Come posso rimuovere i miei IP da un inserisco nell&#39;elenco Bloccati di?**

  Per verificare se l’indirizzo IP si trova in fase di inserisce nell&#39;elenco Bloccati, puoi utilizzare vari siti web per verificarlo, ad esempio:
   * [Casella degli strumenti MX](https://mxtoolbox.com/)
   * [Qual è il mio indirizzo IP](https://whatismyipaddress.com)

  In genere, il risultato della verifica dell’indirizzo IP restituirà un elenco contenente i dettagli del inserisco nell&#39;elenco Bloccati di e anche il nome del sito web che ha bloccato l’indirizzo IP.

  Facendo clic sul collegamento corrispondente, è possibile accedere ai dettagli del sito Web.

  Quindi puoi richiedere che il tuo sito web venga cancellato dal sito web che ha aggiunto l’indirizzo IP al suo inserisco nell&#39;elenco Bloccati di.

  >[!NOTE]
  >
  >Il processo di cancellazione dall’elenco può variare a seconda del sito web. Alcuni siti richiedono la creazione di un account, mentre altri richiedono solo che tu fornisca l’indirizzo IP.
