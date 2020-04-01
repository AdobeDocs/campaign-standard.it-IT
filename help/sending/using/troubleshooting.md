---
title: Risoluzione dei problemi di recapito in Adobe Campaign Standard
description: Scopri cosa fare in caso di problemi di recapito con Adobe Campaign Standard.
page-status-flag: never-activated
uuid: 286fceee-65a9-4cb9-b205-9ce5d024675c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: sheduling-messages
discoiquuid: 9c7fd670-bba9-4f3c-8cb1-87397a1acd27
context-tags: delivery,schedule,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b4ba56e5cd639c547a7060be9c60985f5564160d

---


# Risoluzione dei problemi{#troubleshooting}

Si è verificato un problema di recapito? Puoi trovare la soluzione qui.

## Stesso messaggio di errore per un ISP {#same-error-for-an-isp}

**Perché ricevo sempre lo stesso messaggio di errore per un particolare ISP?**

Se si riceve sempre lo stesso messaggio di errore per un ISP, l&#39;e-mail o l&#39;IP potrebbe essere stato rilevato come difettoso dal provider di servizi Internet. Eseguite le seguenti raccomandazioni:
* Verificate se ricevete una percentuale elevata di errori collegati a indirizzi e-mail inesistenti (errori **utente sconosciuti** ).
* Aggiornare i moduli di iscrizione per rilevare eventuali errori nei nomi di dominio immessi (ad esempio: gmaul.com o yaho.com).
* Se noti degli errori che indicano che i messaggi sono dichiarati come spam o che i messaggi sono costantemente bloccati, prova ad escludere i destinatari che non hanno aperto o fatto clic in uno dei tuoi messaggi negli ultimi 12 mesi dalla destinazione.

Se il problema persiste, contatta i servizi commerciali o di recapito o il supporto Adobe Campaign.

## Lista nera e quarantena {#blacklisting-versus-quarantine}

* **Qual è la differenza tra un indirizzo e-mail inserito in blacklist e un indirizzo e-mail in quarantena?**

   * Lo stato **[!UICONTROL Blacklisted]** è il risultato di un ciclo di feedback (quando una persona segnala un messaggio come spam).

   * Lo stato **[!UICONTROL Quarantined]** è il risultato di un rimbalzo morbido o duro. Per ulteriori informazioni, consulta questa [sezione](../../sending/using/understanding-quarantine-management.md).

* **Cosa significano i diversi motivi di errore di quarantena?**

   I motivi possibili sono 10: non definito, utente sconosciuto, dominio non valido, indirizzo inserito in blacklist, rifiutato, errore ignorato, non raggiungibile, account disabilitato, cassetta postale piena, non connesso.

   Per ulteriori informazioni, consulta [Informazioni sulla gestione](../../sending/using/understanding-quarantine-management.md)della quarantena.

## Senza blacklist {#unblacklisting}

* **Uno dei miei destinatari è stato inserito in blacklist per errore. Come posso cancellarli in modo da poter iniziare a inviarli nuovamente?**

   * Vai a **[!UICONTROL Administration > Channels > Quarantines > Addresses]**.
   * Nei dettagli del record corrispondente, impostare il valore del **[!UICONTROL Status]** campo su **[!UICONTROL Valid]**.
   * Salvare il record.

* **Come posso sapere se uno dei miei IP è in lista nera? Come posso rimuovere la blacklist dei miei IP?**

   Per verificare se l&#39;indirizzo IP è inserito in una blacklist, potete usare diversi siti Web per verificarlo:
   * https://mxtoolbox.com/
   * https://whatismyipaddress.com/blacklist-check
   * https://www.blacklistalert.org/
   In genere, il risultato della verifica dell&#39;indirizzo IP restituirà un elenco contenente i dettagli della blacklist e il nome del sito Web che ha inserito in blacklist l&#39;indirizzo IP.

   Facendo clic sul collegamento corrispondente, potete accedere ai dettagli del sito Web.

   Quindi, potete richiedere che il vostro sito Web venga cancellato dal sito Web che ha inserito in blacklist l&#39;indirizzo IP.

   >[!NOTE]
   >
   >Il processo di eliminazione può variare a seconda del sito Web. Alcuni siti richiedono la creazione di un account, mentre altri richiedono solo l’indirizzo IP.
