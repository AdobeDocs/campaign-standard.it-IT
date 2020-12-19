---
solution: Campaign Standard
product: campaign
title: Definire il pubblico adatto
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
index: y
translation-type: tm+mt
source-git-commit: a7300666587362048431d0bafacc317170b317aa
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Definire il pubblico adatto {#define-the-right-audience}

La popolazione mirata è la chiave: create con attenzione gli elenchi, verificate i messaggi e-mail sui client e dispositivi mobili più diffusi e verificate che gli elenchi delle e-mail siano aggiornati (senza indirizzi sconosciuti o obsoleti). È inoltre possibile inviare delle prove che aiutino a configurare un ciclo di convalida completo.

Ulteriori informazioni sulle popolazioni di destinazione [in questa sezione](../../audiences/using/selecting-an-audience-in-a-message.md)

## Esegue il targeting dell&#39;audience giusta {#target-the-right-audience}

Quando il contenuto è pronto, è necessario definire con attenzione chi riceverà il messaggio.

Per garantire il successo della distribuzione, è necessario inviare i contenuti personalizzati più rilevanti ai destinatari giusti.  Adobe Campaign consente di realizzare il target più preciso: potete selezionare i destinatari in base alla loro età, localizzazione, cosa hanno acquistato, se hanno fatto clic su un collegamento in una consegna precedente, ecc. Con  Adobe Campaign, potete anche definire profili di test, gruppi di controllo e indirizzi iniziali per essere certi che la destinazione sia corretta.

## Mappature di destinazione {#target-mappings}

Per impostazione predefinita, i modelli di consegna sono **Profili**.  Adobe Campaign offre altre mappature di destinazione per le consegne, che potete modificare in base alle vostre esigenze.

Questi mapping sono presentati [in questa sezione](../../automating/using/query.md#targeting-dimensions-and-resources).

Potete anche creare e utilizzare una mappatura di destinazione personalizzata. Per ulteriori informazioni al riguardo, consulta [questa sezione](../../administration/using/target-mappings-in-campaign.md).

## Dati esterni {#external-data}

È possibile inviare i dati ai destinatari memorizzati in un file esterno anziché salvati nel database. A tal fine, un flusso di lavoro di progettazione caricherà i dati nel database da un file e creerà un&#39;audience associata.  Ulteriori informazioni [in questo caso di utilizzo](../../automating/using/use-case-calling-workflow.md). Vedere anche [Chiamata di un flusso di lavoro con parametri](../../automating/using/calling-a-workflow-with-external-parameters.md).

## Invia ai tuoi abbonati {#send-to-subscribers}

Per inviare messaggi agli abbonati di una newsletter, potete indirizzare direttamente gli abbonati al servizio di informazioni corrispondente. Ulteriori informazioni [in questa sezione](../../audiences/using/about-subscriptions.md).

**Suggerimento** : puoi creare un pubblico Elenco con cui indirizzare gli utenti iscritti alla newsletter utilizzando un flusso di lavoro. Potete quindi selezionare questa audience in una consegna. Per ulteriori informazioni, vedere [Creazione di audience di elenchi](../../audiences/using/creating-audiences.md#creating-list-audiences).

## Prove, profili di prova e gruppi di controllo {#proofs-test-control-groups}

Per verificare la consegna, utilizzate le prove prima di inviare alla destinazione principale.
Accertarsi di aver selezionato i destinatari della prova appropriati, in quanto convalidano il modulo e il contenuto del messaggio. I passaggi per l&#39;invio delle prove sono presentati [in questa sezione](../../sending/using/sending-proofs.md).

Ulteriori informazioni sui profili di test [in questa sezione](../../audiences/using/managing-test-profiles.md).

È possibile utilizzare [Gruppi di controllo](../../sending/using/control-group.md) per misurare l&#39;impatto delle campagne escludendo una parte del pubblico. Puoi quindi confrontare il comportamento della popolazione di destinazione che ha ricevuto il messaggio con il comportamento dei contatti non mirati. In base ai registri di invio, puoi anche eseguire il targeting di un gruppo di controllo in campagne future.

## Indirizzi di deduplicazione {#deduplicate-addresses}

È importante evitare di avere indirizzi e-mail duplicati, in quanto ciò può avere un impatto sulla destinazione:

* Lo stesso messaggio può essere inviato più volte quando una destinazione viene divisa.

* Se un destinatario annulla la sottoscrizione dopo aver ricevuto un messaggio, il profilo duplicato riceverà comunque messaggi futuri.

Gli indirizzi di deduplicazione proteggono la reputazione dell&#39;invio e garantiscono una buona gestione della quarantena.

Ulteriori informazioni [in questo caso di utilizzo](../../automating/using/deduplicating-data-imported-file.md).
