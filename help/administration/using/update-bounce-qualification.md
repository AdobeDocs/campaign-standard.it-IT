---
title: Aggiornare la qualifica di mancato recapito dopo un’interruzione del servizio ISP
description: Scopri come aggiornare la qualifica di mancato recapito dopo un’interruzione del servizio dell’ISP.
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

In caso di interruzione di un ISP, le e-mail inviate tramite Campaign non possono essere consegnate correttamente al destinatario: verranno contrassegnate erroneamente come mancate consegne.

A dicembre 2020, un problema globale in Gmail ha causato la mancata ricezione di alcuni messaggi e-mail inviati a indirizzi e-mail Gmail validi, che sono stati erroneamente inseriti dai server Gmail come indirizzi e-mail non validi, con la seguente risposta di mancato recapito: *&quot;550-5.1.1 L’account e-mail che hai tentato di raggiungere non esiste.&quot;*

Google ha dichiarato che le interruzioni e i disagi di Gmail che hanno causato questo problema sono iniziati il 14 dicembre alle 06:55 e si sono conclusi alle 18:09 EST del 15 dicembre. L’analisi dei nostri dati ha anche mostrato un picco molto breve nei mancati recapiti Gmail alle 02:06 EST del 16 dicembre, la maggior parte dei quali si è verificata il 15 dicembre tra le 14:00 EST e le 18:30 EST.

>[!NOTE]
>
>Puoi controllare il dashboard di stato dell’area di lavoro di Google su [questa pagina](https://www.google.com/appsstatus#hl=en&amp;v=status).


In base alla logica standard di gestione dei mancati recapiti, Adobe Campaign ha aggiunto automaticamente questi destinatari all’elenco di quarantena con una **[!UICONTROL Status]** impostazione di **[!UICONTROL Quarantine]**. Per risolvere questo problema, aggiorna la tabella di quarantena in Campaign trovando e rimuovendo questi destinatari o modificando i **[!UICONTROL Status]** a **[!UICONTROL Valid]** in modo che il flusso di lavoro di pulizia notturna li rimuova.

Per trovare i destinatari interessati da questo problema Gmail o nel caso in cui si verifichi di nuovo con un altro ISP, consulta le istruzioni di seguito.

## Processo di aggiornamento

Dovrai eseguire una query sulla tabella di quarantena per filtrare tutti i destinatari Gmail (o altri ISP) potenzialmente interessati dall’interruzione, in modo che possano essere rimossi dall’elenco di quarantena e inclusi nelle consegne e-mail future di Campaign.

In base alla tempistica dell’incidente, di seguito sono riportate le linee guida consigliate per questa query.

>[!IMPORTANT]
>
>Queste date/ore si basano sul fuso orario standard orientale (EST). Effettua le regolazioni in base al fuso orario dell’istanza.

Per le istanze di Campaign con informazioni di risposta SMTP non recapitate in **[!UICONTROL Error text]** campo dell’elenco di quarantena:

* **Testo di errore (testo di quarantena)** contiene &quot;550-5.1.1 L’account e-mail che hai tentato di raggiungere non esiste&quot; E **Testo di errore (testo di quarantena)** contiene &quot;support.google.com&quot; **
* **Stato aggiornamento (@lastModified)** il 12/14/2020 o dopo il 6:55:00 AM
* **Stato aggiornamento (@lastModified)** il 12/16/2020 o prima del 6:00:00 AM

Dopo aver visualizzato l’elenco dei destinatari interessati, puoi impostarli sullo stato **[!UICONTROL Valid]** in modo che vengano rimossi dall’elenco di quarantena dal **[!UICONTROL Database cleanup]** oppure eliminarli dalla tabella.

**Argomenti correlati:**
* [Errori di consegna](../../sending/using/understanding-delivery-failures.md)
* [Qualificazione di mail non recapitate](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification)
