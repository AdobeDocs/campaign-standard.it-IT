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
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 012546e109b085b7ed968bcefa8f76482656ae0d
workflow-type: tm+mt
source-wordcount: '473'
ht-degree: 0%

---


# Risoluzione dei problemi{#troubleshooting}

Si è verificato un problema di recapito? Puoi trovare la soluzione qui.

## Stesso messaggio di errore per un ISP {#same-error-for-an-isp}

**Perché ricevo sempre lo stesso messaggio di errore per un particolare ISP?**

Se si riceve sempre lo stesso messaggio di errore per un ISP, l&#39;e-mail o l&#39;IP potrebbe essere stato rilevato come difettoso dal provider di servizi Internet. Eseguite le seguenti raccomandazioni:
* Verificate se ricevete una percentuale elevata di errori collegati a indirizzi e-mail inesistenti (errori **utente sconosciuti** ).
* Aggiornare i moduli di iscrizione per rilevare eventuali errori nei nomi di dominio immessi (ad esempio: gmaul.com o yaho.com).
* Se noti degli errori che indicano che i messaggi sono dichiarati come spam o che i messaggi sono costantemente bloccati, prova ad escludere i destinatari che non hanno aperto o fatto clic in uno dei tuoi messaggi negli ultimi 12 mesi dalla destinazione.

Se il problema persiste, contattare i servizi commerciali o di recapito o il supporto  Adobe Campaign.

## Elenco blocchi e quarantena {#block-list-versus-quarantine}

* **Qual è la differenza tra un indirizzo e-mail in un elenco di blocchi e un indirizzo e-mail in quarantena?**

   * Lo stato **[!UICONTROL On block list]** è il risultato di un ciclo di feedback (quando una persona segnala un messaggio come spam).

   * Lo stato **[!UICONTROL Quarantined]** è il risultato di un rimbalzo morbido o duro.
   Per ulteriori informazioni, consulta questa [sezione](../../sending/using/understanding-quarantine-management.md#quarantine-vs-block-list).

* **Cosa significano i diversi motivi di errore di quarantena?**

   I motivi possibili sono 10: non definito, utente sconosciuto, dominio non valido, indirizzo nell&#39;elenco blocchi, rifiutato, errore ignorato, non raggiungibile, account disabilitato, cassetta postale piena, non connesso.

   Per ulteriori informazioni, consulta [Informazioni sulla gestione](../../sending/using/understanding-quarantine-management.md)della quarantena.

## Rimozione dall&#39;elenco dei blocchi {#removing-from-block-list}

* **Uno dei miei destinatari è stato aggiunto all&#39;elenco dei blocchi per errore. Come posso rimuoverli dall&#39;elenco dei blocchi in modo da poter iniziare a inviarli di nuovo?**

   * Vai a **[!UICONTROL Administration > Channels > Quarantines > Addresses]**.
   * Nei dettagli del record corrispondente, impostare il valore del **[!UICONTROL Status]** campo su **[!UICONTROL Valid]**.
   * Salvare il record.

* **Come posso sapere se uno dei miei IP si trova in un elenco di blocchi? Come posso rimuovere i miei IP da un elenco di blocchi?**

   Per verificare se l&#39;indirizzo IP si trova in un elenco di blocchi, è possibile utilizzare vari siti Web per verificarlo, ad esempio:
   * [Toolbox MX](https://mxtoolbox.com/)
   * [Qual è il mio indirizzo IP?](https://whatismyipaddress.com)
   In genere, il risultato della verifica dell&#39;indirizzo IP restituirà un elenco contenente i dettagli dell&#39;elenco dei blocchi e il nome del sito Web che ha bloccato l&#39;indirizzo IP.

   Facendo clic sul collegamento corrispondente, potete accedere ai dettagli del sito Web.

   Quindi, potete richiedere che il sito Web venga eliminato dal sito Web che ha aggiunto l&#39;indirizzo IP al relativo elenco di blocchi.

   >[!NOTE]
   >
   >Il processo di eliminazione può variare a seconda del sito Web. Alcuni siti richiedono la creazione di un account, mentre altri richiedono solo l’indirizzo IP.
