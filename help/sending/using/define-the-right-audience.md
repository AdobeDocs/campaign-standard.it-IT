---
title: Definire il pubblico adatto
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
index: y
description: "Quando il contenuto sarà pronto, scopri come definire con attenzione chi riceverà il messaggio."
feature: Deliverability
role: User
level: Intermediate
exl-id: 1e06fd9d-e850-4856-8f7b-b581dbe157df
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '516'
ht-degree: 12%

---

# Definire il pubblico adatto {#define-the-right-audience}

La popolazione target è fondamentale: crea i tuoi elenchi con attenzione, testa le e-mail sui client e-mail e sui dispositivi mobili più diffusi e assicurati che i tuoi elenchi e-mail siano aggiornati (senza indirizzi sconosciuti o obsoleti). Puoi anche inviare bozze utili per impostare un ciclo di convalida completo.

Ulteriori informazioni sulle popolazioni target [in questa sezione](../../audiences/using/selecting-an-audience-in-a-message.md)

## Rivolgersi al pubblico giusto {#target-the-right-audience}

Quando il contenuto è pronto, è necessario definire con attenzione chi riceverà il messaggio.

Per garantire la corretta consegna, desideri inviare i contenuti personalizzati più rilevanti ai destinatari giusti. Adobe Campaign ti consente di creare il target più preciso: puoi selezionare i destinatari in base all’età, alla localizzazione, a cosa hanno acquistato, se hanno fatto clic su un collegamento in una consegna precedente, ecc. Con Adobe Campaign, puoi anche definire profili di test, gruppi di controllo e indirizzi di seed per assicurarti che il target sia corretto.

## Mappature di destinazione {#target-mappings}

Per impostazione predefinita, i modelli di consegna sono target **Profili**. Adobe Campaign offre altre mappature di destinazione per le consegne, che puoi modificare in base alle tue esigenze.

Vengono presentate queste mappature [in questa sezione](../../automating/using/query.md#targeting-dimensions-and-resources).

Puoi anche creare e utilizzare una mappatura di destinazione personalizzata. Per ulteriori informazioni al riguardo, consulta [questa sezione](../../administration/using/target-mappings-in-campaign.md).

## Dati esterni {#external-data}

Puoi consegnare a destinatari memorizzati in un file esterno anziché salvati nel database. A questo scopo, progetta un flusso di lavoro per caricare i dati nel database da un file e creare un pubblico associato.  Ulteriori informazioni [in questo caso d’uso](../../automating/using/use-case-calling-workflow.md). Vedi anche [Chiamata di un flusso di lavoro con parametri](../../automating/using/calling-a-workflow-with-external-parameters.md).

## Invia ai tuoi abbonati {#send-to-subscribers}

Per inviare messaggi agli abbonati di una newsletter, puoi indirizzare direttamente questi ultimi al servizio di informazioni corrispondente. Per ulteriori informazioni, consulta [questa sezione](../../audiences/using/about-subscriptions.md).

**Suggerimento** : puoi creare un pubblico di tipo List che rivolge gli abbonati alla newsletter utilizzando un flusso di lavoro. Puoi quindi selezionare questo pubblico in una consegna. Per ulteriori informazioni, consulta [Creazione di tipi di pubblico di tipo list](../../audiences/using/creating-audiences.md#creating-list-audiences).

## Bozze, profili di test e gruppi di controllo {#proofs-test-control-groups}

Per verificare la consegna, utilizza le bozze prima di inviare al target principale.
Accertati di selezionare i destinatari della bozza appropriati, in quanto convalidano il modulo e il contenuto del messaggio. Vengono descritti i passaggi per l’invio delle bozze [in questa sezione](../../sending/using/sending-proofs.md).

Ulteriori informazioni sui profili di test [in questa sezione](../../audiences/using/managing-test-profiles.md).

È possibile utilizzare [Gruppi di controllo](../../sending/using/control-group.md) per misurare l’impatto delle campagne escludendo parte delle relative audience. Puoi quindi confrontare il comportamento della popolazione di destinazione che ha ricevuto il messaggio con il comportamento dei contatti non mirati. In base ai registri di invio, puoi anche eseguire il targeting di un gruppo di controllo in campagne future.

## Deduplica indirizzi {#deduplicate-addresses}

È importante evitare di avere indirizzi e-mail duplicati, perché questo può avere un impatto sul target:

* Lo stesso messaggio può essere inviato più di una volta quando una destinazione viene divisa.

* Se un destinatario annulla l’iscrizione dopo aver ricevuto un messaggio, il suo profilo duplicato riceverà comunque messaggi futuri.

La deduplicazione degli indirizzi protegge la reputazione del mittente e garantisce una buona gestione della quarantena.

Ulteriori informazioni [in questo caso d’uso](../../automating/using/deduplicating-data-imported-file.md).
