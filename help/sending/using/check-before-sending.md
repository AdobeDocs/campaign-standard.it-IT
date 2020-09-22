---
title: Controlla prima dell'invio
seo-title: Controlla prima dell'invio
page-status-flag: never-activated
uuid: a540efc7-105d-4c7f-a2ee-ade4d22b3445
contentOwner: sauviat
products: SG_CAMPAIGN/CLASSIC
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
discoiquuid: 0cbc4e92-482f-4dac-a1fb-b738e7127938
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: d5d9d50474142306457a8c76a24388c3c574791d
workflow-type: tm+mt
source-wordcount: '400'
ht-degree: 15%

---


# Esegui tutti i controlli prima dell&#39;invio {#perform-all-checks}

Una volta che il messaggio è pronto, accertati che il contenuto sia visualizzato correttamente, su tutti i dispositivi, e non contenga errori quali personalizzazione errata o collegamenti interrotti.

Prima di inviare il messaggio, assicurati anche che i parametri e la configurazione siano coerenti con la consegna.

## Perché la convalida è fondamentale {#validation-is-key}

Prima di inviare una consegna, è necessario assicurarsi che i destinatari ricevano il messaggio che si desidera inviare. A tal fine, devi convalidare il contenuto del messaggio e i parametri di consegna.

Questo passaggio consente di rilevare eventuali errori e correggerli prima di inviarli alla destinazione principale.

I passaggi per la convalida di una consegna sono descritti [in questa sezione](../../sending/using/get-started-sending-messages.md#prepare-test-send).

## Rendering di e-mail {#email-rendering}

Prima di premere il pulsante **[!UICONTROL Send]**, accertati che il messaggio venga visualizzato in modo ottimale in vari client web, servizi di posta sul web e dispositivi.

Per ottenere questo risultato, Adobe Campaign acquisisce il rendering e lo rende disponibile in un report dedicato. Ciò ti permette di visualizzare in anteprima il messaggio inviato nei vari contesti in cui potrebbe essere ricevuto.

**Suggerimenti**:

* Puoi visualizzare il messaggio inviato nei diversi contesti in cui potrebbe essere ricevuto: webmail, servizio messaggi, mobile, ecc.

* Le funzionalità di rendering delle e-mail sono fondamentali per identificare se le campagne e-mail riescono a superare i filtri dei principali ISP (Internet Service Provider) e dei servizi di posta elettronica. Tali strumenti inviano una copia pre-verifica di un messaggio e-mail a una rete di caselle in entrata di prova, in modo da visualizzare il modo in cui il messaggio verrà visualizzato, o renderizzato, tra questi servizi. Possono inoltre includere rapporti e opzioni di correzione del codice che consentono di identificare e correggere rapidamente i problemi di recapito.

Ulteriori informazioni [in questa sezione](../../sending/using/email-rendering.md).

## Messaggi di prova {#proof-messages}

L&#39;invio di prove consente di controllare il collegamento di rinuncia, la pagina mirror e qualsiasi altro collegamento, convalidare il messaggio, verificare che le immagini siano visualizzate, rilevare eventuali errori, ecc. È inoltre possibile controllare la progettazione e il rendering su diversi dispositivi.

Ulteriori informazioni [[in questa sezione](../../sending/using/sending-proofs.md).

## Configurare le consegne di test A/B {#a-b-testing-deliveries}

Se disponete di diversi contenuti per la consegna delle e-mail, potete utilizzare il test A/B per scoprire quale versione avrà il maggiore impatto sulla popolazione interessata.

**Suggerimenti**:

* Inviare le diverse versioni ad alcuni dei destinatari

* Seleziona quella con il tasso di successo più elevato e inviala al resto della destinazione

Ulteriori informazioni [in questa sezione](../../channels/using/designing-an-a-b-test-email.md).

