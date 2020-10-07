---
title: Risoluzione dei problemi di recapito in  Adobe Campaign Standard
description: Scopri cosa fare in caso di problemi di recapito con  Adobe Campaign Standard.
page-status-flag: never-activated
uuid: 286fceee-65a9-4cb9-b205-9ce5d024675c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: sheduling-messages
discoiquuid: 9c7fd670-bba9-4f3c-8cb1-87397a1acd27
context-tags: delivery,schedule,back
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '459'
ht-degree: 1%

---


# Risoluzione dei problemi{#troubleshooting}

Si è verificato un problema di recapito? Puoi trovare la soluzione qui.

## Stesso messaggio di errore per un ISP {#same-error-for-an-isp}

**Perché ricevo sempre lo stesso messaggio di errore per un particolare ISP?**

Se si riceve sempre lo stesso messaggio di errore per un ISP, l&#39;e-mail o l&#39;IP potrebbe essere stato rilevato come difettoso dal provider di servizi Internet. Eseguite le seguenti raccomandazioni:
* Verificate se ricevete una percentuale elevata di errori collegati a indirizzi e-mail inesistenti (errori **utente sconosciuti** ).
* Aggiornare i moduli di iscrizione per rilevare eventuali errori nei nomi di dominio immessi (ad esempio: gmaul.com o yaho.com).
* Se noti degli errori che indicano che i messaggi sono dichiarati come spam o che i messaggi sono costantemente bloccati, prova ad escludere i destinatari che non hanno aperto o fatto clic in uno dei tuoi messaggi negli ultimi 12 mesi dalla destinazione.

Se il problema persiste, contattate i servizi commerciali o di recapito o  supporto Adobe Campaign.

## elenco Bloccati e quarantena {#denylist-versus-quarantine}

* **Qual è la differenza tra un indirizzo e-mail elenco Bloccati e un indirizzo e-mail in quarantena?**

   * Lo stato **[!UICONTROL On denylist]** è il risultato di un ciclo di feedback (quando una persona segnala un messaggio come spam).

   * Lo stato **[!UICONTROL Quarantined]** è il risultato di un rimbalzo morbido o duro.
   Per ulteriori informazioni, consulta questa [sezione](../../sending/using/understanding-quarantine-management.md#quarantine-vs-denylist).

* **Cosa significano i diversi motivi di errore di quarantena?**

   I motivi possibili sono 10: non definito, utente sconosciuto, dominio non valido, indirizzo elenco Bloccati, rifiutato, errore ignorato, non raggiungibile, account disabilitato, cassetta postale piena, non connesso.

   For more on this, see [Understanding quarantine management](../../sending/using/understanding-quarantine-management.md).

## Rimozione dal elenco Bloccati {#removing-from-denylist}

* **Uno dei miei destinatari è stato aggiunto al elenco Bloccati per errore. Come posso rimuoverli dal elenco Bloccati in modo da poter iniziare a inviare nuovamente i messaggi?**

   * Vai a **[!UICONTROL Administration > Channels > Quarantines > Addresses]**.
   * Nei dettagli del record corrispondente, impostare il valore del **[!UICONTROL Status]** campo su **[!UICONTROL Valid]**.
   * Salvare il record.

* **Come posso sapere se uno dei miei IP è elenco Bloccati? Come posso rimuovere i miei IP da un elenco Bloccati?**

   Per verificare se l&#39;indirizzo IP è elenco Bloccati, potete utilizzare vari siti Web per verificarlo, ad esempio:
   * [Toolbox MX](https://mxtoolbox.com/)
   * [Qual è il mio indirizzo IP?](https://whatismyipaddress.com)

   In genere, il risultato della verifica dell&#39;indirizzo IP restituirà un elenco contenente i dettagli del elenco Bloccati e anche il nome del sito Web che ha bloccato l&#39;indirizzo IP.

   Facendo clic sul collegamento corrispondente, potete accedere ai dettagli del sito Web.

   Quindi, potete richiedere che il sito Web venga eliminato dal sito Web che ha aggiunto l&#39;indirizzo IP al suo elenco Bloccati.

   >[!NOTE]
   >
   >Il processo di eliminazione può variare a seconda del sito Web. Alcuni siti richiedono la creazione di un account, mentre altri richiedono solo l’indirizzo IP.
