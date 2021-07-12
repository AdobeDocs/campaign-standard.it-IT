---
solution: Campaign Standard
product: campaign
title: Controllare prima dell’invio
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
index: y
description: '"Quando il messaggio è pronto, scopri come eseguire tutti i controlli prima di inviare"'
feature: Recapito messaggi
role: User
level: Intermediate
exl-id: dfc5fc00-87aa-4d22-ad7c-cc0ba1ee21be
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '411'
ht-degree: 16%

---

# Esegui tutti i controlli prima dell’invio {#perform-all-checks}

Quando il messaggio è pronto, accertati che il relativo contenuto sia visualizzato correttamente, su tutti i dispositivi, e non contenga errori quali personalizzazione errata o collegamenti interrotti.

Prima di inviare il messaggio, assicurati anche che i parametri e la configurazione siano coerenti con la consegna.

## Perché la convalida è fondamentale {#validation-is-key}

Prima di inviare una consegna, è necessario assicurarsi che i destinatari ricevano il messaggio che si desidera inviare loro. A questo scopo, devi convalidare il contenuto del messaggio e i parametri di consegna.

Questo passaggio ti consente di rilevare eventuali errori e correggerli prima di consegnarli al target principale.

I passaggi per la convalida di una consegna sono descritti [in questa sezione](../../sending/using/get-started-sending-messages.md#prepare-test-send).

## Rendering di e-mail {#email-rendering}

Prima di premere il pulsante **[!UICONTROL Send]**, accertati che il messaggio venga visualizzato in modo ottimale in vari client web, servizi di posta sul web e dispositivi.

Per ottenere questo risultato, Adobe Campaign acquisisce il rendering e lo rende disponibile in un report dedicato. Ciò ti permette di visualizzare in anteprima il messaggio inviato nei vari contesti in cui potrebbe essere ricevuto.

**Suggerimenti**:

* Puoi visualizzare il messaggio inviato nei diversi contesti in cui potrebbe essere ricevuto: webmail, servizio messaggi, dispositivi mobili, ecc.

* Le funzionalità di rendering delle e-mail sono fondamentali per identificare se le campagne e-mail superano con successo i filtri dei principali ISP (Internet Service Provider) e dei servizi di posta web. Tali strumenti inviano una copia pre-volo di un’e-mail a una rete di caselle in entrata di prova, in modo da visualizzare il messaggio o eseguirne il rendering in questi servizi. Possono anche includere rapporti e opzioni di correzione del codice che ti aiutano a identificare rapidamente e a risolvere i problemi che migliorano il recapito messaggi.

Ulteriori informazioni [in questa sezione](../../sending/using/email-rendering.md).

## Messaggi di prova {#proof-messages}

L’invio di bozze consente di controllare il collegamento di rinuncia, la pagina speculare e qualsiasi altro collegamento, convalidare il messaggio, verificare che le immagini siano visualizzate, rilevare eventuali errori e così via. Puoi anche controllare la progettazione e il rendering su diversi dispositivi.

Ulteriori informazioni [in questa sezione](../../sending/using/sending-proofs.md).

## Configurare le consegne di test A/B {#a-b-testing-deliveries}

Se disponi di più contenuti per una consegna e-mail, puoi utilizzare il test A/B per scoprire quale versione avrà il maggiore impatto sulla popolazione target.

**Suggerimenti**:

* Inviare versioni diverse ad alcuni dei tuoi destinatari

* Seleziona quella con il tasso di successo più alto e inviala al resto del target

Ulteriori informazioni [in questa sezione](../../channels/using/designing-an-a-b-test-email.md).
