---
title: Aggiornare la qualifica di mancato recapito dopo un’interruzione del servizio ISP
description: Scopri come aggiornare la qualifica del mancato recapito dopo un'interruzione dell'ISP.
audience: delivery
hidefromtoc: true
exl-id: b06e9009-70c7-459f-8a9f-d5b7020d662f
source-git-commit: f81b8a3b076a6e29b697f21ea4d99fa7d5b6788c
workflow-type: tm+mt
source-wordcount: '425'
ht-degree: 4%

---

# Aggiornare la qualifica di mancato recapito dopo un’interruzione del servizio ISP {#update-bounce-qualification.md}

## Contesto

In caso di interruzione di un ISP, le e-mail inviate tramite Campaign non possono essere recapitate correttamente al destinatario: queste e-mail verranno erroneamente contrassegnate come messaggi non recapitati.

Nel dicembre 2020, un problema globale a Gmail causava l’invio errato di alcuni messaggi e-mail a indirizzi e-mail Gmail validi, in quanto gli indirizzi e-mail non validi da parte dei server Gmail con la seguente risposta non recapitata: *&quot;550-5.1.1 L&#39;account e-mail che hai cercato di raggiungere non esiste.&quot;*

Google ha dichiarato che le interruzioni e le interruzioni di Gmail che hanno causato questo problema sono iniziate il 14 dicembre alle 6:55 e sono terminate alle 6:09 PM EST il 15 dicembre. La nostra analisi dei dati ha anche mostrato un picco molto breve in Gmail rimbalzi alle 2:06AM EST il 16 dicembre, con la maggior parte che si verifica il 15 dicembre tra le 2:00 EST e le 6:30 pm EST.

>[!NOTE]
>
>Puoi controllare il dashboard di stato di Google Workspace su [questa pagina](https://www.google.com/appsstatus#hl=en&amp;v=status).


Per logica standard di gestione dei messaggi non recapitati, Adobe Campaign ha aggiunto automaticamente questi destinatari all’elenco di quarantena con un **[!UICONTROL Status]** definizione **[!UICONTROL Quarantine]**. Per correggere questo problema, devi aggiornare la tabella di quarantena in Campaign trovando e rimuovendo questi destinatari o modificando i relativi **[!UICONTROL Status]** a **[!UICONTROL Valid]** in modo che il flusso di lavoro di pulizia notturna li rimuova.

Per trovare i destinatari interessati da questo problema Gmail o nel caso in cui questo si verifichi nuovamente con un altro ISP, consulta le istruzioni riportate di seguito.

## Processo di aggiornamento

Sarà necessario eseguire una query sulla tabella di quarantena per filtrare tutti i destinatari Gmail (o altri ISP) potenzialmente interessati dall’interruzione, in modo che possano essere rimossi dall’elenco di quarantena e inclusi nelle future consegne e-mail di Campaign.

In base al calendario dell’incidente, di seguito sono riportate le linee guida consigliate per questa query.

>[!IMPORTANT]
>
>Queste date/ore si basano sul fuso orario standard orientale (EST). Modifica il fuso orario dell’istanza.

Per le istanze Campaign con le informazioni di risposta non recapitata SMTP nel **[!UICONTROL Error text]** campo dell’elenco di quarantena:

* **Testo di errore (testo di quarantena)** contiene &quot;550-5.1.1 L&#39;account e-mail che hai cercato di raggiungere non esiste&quot; E **Testo di errore (testo di quarantena)** contiene &quot;support.google.com&quot; **
* **Stato aggiornamento (@lastModified)** il 14/12/2020 o successivo 6:55:00
* **Stato aggiornamento (@lastModified)** il 12/16/2020 o anteriormente 6:00:00

Una volta visualizzato l’elenco dei destinatari interessati, puoi impostarli su uno stato **[!UICONTROL Valid]** in modo che vengano rimosse dall&#39;elenco di quarantena **[!UICONTROL Database cleanup]** oppure eliminali dalla tabella.

**Argomenti correlati:**
* [Comprendere gli errori di consegna](../../sending/using/understanding-delivery-failures.md)
* [Qualificazione di mail non recapitate](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification)
