---
title: Controllare prima dell’invio
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
index: y
description: "Quando il messaggio è pronto, scopri come eseguire tutti i controlli prima di inviarlo"
feature: Deliverability
role: User
level: Intermediate
exl-id: dfc5fc00-87aa-4d22-ad7c-cc0ba1ee21be
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '410'
ht-degree: 19%

---

# Esegui tutti i controlli prima dell’invio {#perform-all-checks}

Quando il messaggio è pronto, accertati che il suo contenuto sia visualizzato correttamente, su tutti i dispositivi, e non contenga errori quali personalizzazione errata o collegamenti interrotti.

Prima di inviare il messaggio, assicurati anche che i parametri e la configurazione siano coerenti con la consegna.

## Perché la convalida è fondamentale {#validation-is-key}

Prima di inviare una consegna, è necessario assicurarsi che i destinatari ricevano il messaggio che si desidera veramente inviare. A questo scopo, devi convalidare il contenuto del messaggio e i parametri di consegna.

Questo passaggio ti consente di rilevare eventuali errori e correggerli prima di consegnarli al target principale.

I passaggi per la convalida di una consegna sono descritti [in questa sezione](../../sending/using/get-started-sending-messages.md#prepare-test-send).

## Rendering di e-mail {#email-rendering}

Prima di premere il pulsante **[!UICONTROL Send]**, accertati che il messaggio venga visualizzato in modo ottimale in vari client web, servizi di posta sul web e dispositivi.

Per ottenere questo risultato, Adobe Campaign acquisisce il rendering e lo rende disponibile in un report dedicato. Ciò ti permette di visualizzare in anteprima il messaggio inviato nei vari contesti in cui potrebbe essere ricevuto.

**suggerimenti**:

* Puoi visualizzare il messaggio inviato nei diversi contesti in cui può essere ricevuto: posta sul web, servizio messaggi, dispositivi mobili, ecc.

* Le funzionalità di rendering di e-mail sono fondamentali per identificare se le campagne e-mail sono riuscite a superare i filtri dei principali ISP (provider di servizi Internet) e servizi di posta sul web. Tali strumenti inviano una copia pre-volo di un’e-mail a una rete di caselle in entrata di prova, in modo da poter vedere come verrà visualizzato il messaggio o come verrà eseguito il rendering tra questi servizi. Possono inoltre includere rapporti e opzioni di correzione del codice che consentono di identificare rapidamente e apportare correzioni che migliorano il recapito messaggi.

Per ulteriori informazioni, consulta [questa sezione](../../sending/using/email-rendering.md).

## Messaggi di bozza {#proof-messages}

L’invio di bozze ti consente di controllare il collegamento di rinuncia, la pagina speculare e tutti gli altri collegamenti, convalidare il messaggio, verificare che siano visualizzate le immagini, rilevare eventuali errori, ecc. Puoi anche controllare la progettazione e il rendering su dispositivi diversi.

Per ulteriori informazioni, consulta [questa sezione](../../sending/using/sending-proofs.md).

## Configurare le consegne dei test A/B {#a-b-testing-deliveries}

Se disponi di diversi contenuti per una consegna e-mail, puoi utilizzare il test A/B per individuare la versione che avrà l’impatto maggiore sulla popolazione target.

**suggerimenti**:

* Inviare le diverse versioni ad alcuni destinatari

* Seleziona quello con il tasso di successo più alto e invialo al resto della destinazione

Per ulteriori informazioni, consulta [questa sezione](../../channels/using/designing-an-a-b-test-email.md).
