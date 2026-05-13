---
title: Aggiornare la qualificazione di mancato recapito dopo un’interruzione del servizio ISP
description: Scopri come aggiornare la qualifica di mancato recapito dopo un’interruzione del servizio dell’ISP.
audience: delivery
exl-id: b06e9009-70c7-459f-8a9f-d5b7020d662f
TQID: https://experienceleague.adobe.com/PcNbVFzTVJhadANGQ5uogj16VHiaNIf7HVn-7X-EbJA
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
topic_v2: id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 441
ht-degree: 3%

---

# Aggiornare la qualificazione di mancato recapito dopo un’interruzione del servizio ISP {#update-bounce-qualification.md}

## Contesto

In caso di interruzione di un ISP, le e-mail inviate tramite Campaign non possono essere consegnate correttamente al destinatario: verranno contrassegnate erroneamente come mancate consegne.

Nel dicembre 2020, un problema globale in Gmail ha causato la mancata disponibilità di alcuni messaggi di posta elettronica inviati a indirizzi di posta elettronica Gmail validi, erroneamente bloccati come indirizzi di posta elettronica non validi dai server Gmail con la seguente risposta di mancato recapito: *&quot;550-5.1.1 L&#39;account di posta elettronica che si è tentato di raggiungere non esiste.&quot;*

Google ha dichiarato che le interruzioni e le interruzioni di Gmail che hanno causato il problema sono iniziate il 14 dicembre alle 6:55AM e si sono concluse alle 6:09PM EST del 15 dicembre. L&#39;analisi dei dati ha inoltre mostrato un picco molto breve nei mancati recapiti Gmail alle 2:06AM EST del 16 dicembre, la maggior parte dei quali si è verificata il 15 dicembre tra le 2:00 PM EST e le 6:30 PM EST.

>[!NOTE]
>
>Puoi controllare il dashboard di stato di Google Workspace in [questa pagina](https://www.google.com/appsstatus#hl=en&v=status).


In base alla logica standard di gestione dei mancati recapiti, Adobe Campaign ha aggiunto automaticamente questi destinatari all&#39;elenco di quarantena con un&#39;impostazione **[!UICONTROL Status]** di **[!UICONTROL Quarantine]**. Per risolvere questo problema, devi aggiornare la tabella di quarantena in Campaign trovando e rimuovendo questi destinatari o modificando i loro **[!UICONTROL Status]** in **[!UICONTROL Valid]** in modo che il flusso di lavoro di pulizia notturna li rimuova.

Per trovare i destinatari interessati da questo problema Gmail o nel caso in cui si verifichi di nuovo con un altro ISP, consulta le istruzioni di seguito.

## Processo di aggiornamento

Dovrai eseguire una query sulla tabella di quarantena per filtrare tutti i destinatari Gmail (o altri ISP) potenzialmente interessati dall’interruzione, in modo che possano essere rimossi dall’elenco di quarantena e inclusi nelle consegne e-mail future di Campaign.

In base alla tempistica dell’incidente, di seguito sono riportate le linee guida consigliate per questa query.

>[!IMPORTANT]
>
>Queste date/ore si basano sul fuso orario standard orientale (EST). Effettua le regolazioni in base al fuso orario dell’istanza.

Per le istanze di Campaign con informazioni di risposta SMTP non recapitate nel campo **[!UICONTROL Error text]** dell’elenco di quarantena:

* **Testo di errore (testo di quarantena)** contiene &quot;550-5.1.1 L&#39;account di posta elettronica che si è tentato di raggiungere non esiste&quot; E **Testo di errore (testo di quarantena)** contiene &quot;support.google.com&quot; **
* **Aggiorna stato (@lastModified)** il 12/14/2020 o dopo le 6:55:00
* **Aggiorna stato (@lastModified)** entro il 12/16/2020 6:00:00

Una volta ottenuto l&#39;elenco dei destinatari interessati, è possibile impostarli sullo stato **[!UICONTROL Valid]** in modo che vengano rimossi dall&#39;elenco di quarantena dal flusso di lavoro **[!UICONTROL Database cleanup]** oppure eliminarli dalla tabella.

**Argomenti correlati:**
* [Errori di consegna](../../sending/using/understanding-delivery-failures.md)
* [Qualificazione di mail non recapitate](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification)
