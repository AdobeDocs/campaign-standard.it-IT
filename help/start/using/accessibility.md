---
title: Accessibilità in Adobe Campaign Standard
description: Informazioni sul supporto dell’accessibilità nell’area di lavoro di Adobe Campaign Standard.
audience: designing
content-type: reference
topic-tags: accessibility
feature: Campaigns
role: User
level: Intermediate
exl-id: 958f7beb-ab41-4492-bc0a-e9e342e3c12e
source-git-commit: 13d419c5fc51845ee14f8a3b288f4c467e0a60d9
workflow-type: tm+mt
source-wordcount: '650'
ht-degree: 100%

---

# Accessibilità in Adobe Campaign Standard {#accessibility-acs}

Informazioni sul supporto dell’accessibilità nell’area di lavoro di Adobe Campaign Standard.

L’accessibilità consiste nel rendere i prodotti utilizzabili da persone con disabilità visive, uditive, cognitive, motorie e di altro tipo. Esempi di funzioni di accessibilità per i prodotti software includono contenuti semanticamente strutturati, supporto per utilità per la lettura dello schermo, equivalenti testuali per gli elementi grafici, scelte rapide da tastiera e così via.

 Adobe Campaign Standard offre funzioni che ne rendono più accessibile l’utilizzo tramite contrasto, etichette, contenuto strutturato, navigazione da tastiera e aiuto contestuale.

## Funzioni di accessibilità {#accessibility-features}

### Contrasto e colore {#contrast}

L’interfaccia utente di Adobe Campaign Standard cerca di fornire un contrasto sufficiente nell’applicazione per garantire un’esperienza di visualizzazione accessibile agli utenti ipovedenti o con deficienze cromatiche.

* Testo e intestazioni di grandi dimensioni sono stati migliorati per ottenere un rapporto di contrasto 3:1.

   ![](assets/accessibility_2.png)

* Il contenuto della guida e il corpo del testo dell’applicazione sono stati aggiornati per ottenere un rapporto di contrasto di 4,5:1.

* Le icone di pausa e annullamento dei flussi di lavoro sono state aggiornate per migliorare il contrasto tra i colori dello sfondo e del primo piano.

   ![](assets/accessibility_1.png)

* Colore, forma e posizione non sono gli unici metodi utilizzati per comunicare informazioni o gerarchia nell’applicazione.

### Interfaccia utente {#user-interface}

L’interfaccia utente di Adobe Campaign Standard semplifica l’interazione degli utenti con i contenuti grazie all’aggiunta di testi alternativi agli elementi visivi e all’utilizzo di una struttura semantica per trasmettere le informazioni sia visivamente che a livello di programmazione.

* Quando l’utente lascia vuoto un campo ID richiesto, un elemento grafico indica visivamente il campo in errore con il testo del messaggio di errore e le stesse informazioni vengono trasmesse programmaticamente agli utenti con tecnologie assistive come le utilità per la lettura dello schermo.

   ![](assets/accessibility_3.png)

* Il contenuto visualizzato al passaggio del mouse o sull’elemento attivo può essere ignorato dall’utente e non oscura altri contenuti.

   ![](assets/accessibility_4.png)

* Sono stati aggiunti testi alternativi per le immagini e nomi accessibili per i pulsanti, che possono essere letti ad alta voce con tecnologia assistiva, consentendo di non affidarsi esclusivamente ai segnali visivi per identificare gli elementi.

<!--
### Create responsive resize for multiple devices {#resize-devices}

When designing for multiple devices and platforms, it's important to create a seamless experience for screen sizes across mobile and desktop resolutions.

Adobe Campaign Standard allows you to design and test emails and push notifications on different devices such as: iPhone, Android devices, iPad, Android tablet and desktop.

![](assets/accessibility_6.png)
-->

## Aiuto contestuale {#contextual-help}

L’aiuto contestuale consente di comprendere meglio i diversi campi richiesti e le diverse funzioni disponibili. Inoltre, ti guida attraverso la documentazione del prodotto per scoprire di più sulla funzione selezionata.

Durante la progettazione di un’e-mail, è possibile accedere a un tooltip con le descrizioni delle funzioni e i collegamenti alla documentazione del prodotto.

![](assets/accessibility_7.png)

## Supporto per la tecnologia di accesso facilitato {#screen-magnifiers}

Facciamo il possibile per rendere l’applicazione Adobe Campaign Standard sempre più utilizzabile con varie tecnologie di accesso facilitato, tra cui tastiere modificate, software di ingrandimento dello schermo, utilità per la lettura dello schermo, software di riconoscimento vocale e altri dispositivi di assistenza.

## Utilizzare la lingua desiderata {#languages}

Adobe Campaign Standard è disponibile in diverse lingue: inglese, francese e tedesco.

Nota che la lingua viene impostata durante l’installazione e non può essere modificata successivamente.

## Scelte rapide da tastiera {#shortcuts}

### Homepage {#homepage-shortcuts}

| Azione | Scelta rapida |
| --- | --- |
| Passa ai singoli elementi dell’interfaccia utente | Tab |
| Attiva l’elemento selezionato | Invio o barra spaziatrice |

### E-mail Designer {#email-designer-shortcuts}

| Azione | Scelta rapida Windows | Scelta rapida macOS |
| --- | --- | --- |
| Annulla | Ctrl+Z | Comando+Z |
| Ripeti | Ctrl+Y | Maiusc+Comando+Z |

### Rapporti dinamici {#report-shortcuts}

| Azione | Scelta rapida Windows | Scelta rapida macOS |
| --- | --- | --- |
| Apri progetto | Ctrl+O | Comando + O |
| Salva | Ctrl+S | Comando+S |
| Salva con nome | Maiusc+Ctrl+S | Maiusc+Comando+S |
| Aggiorna progetto | Alt+R | Comando+R |
| Scarica file CSV | Maiusc+Ctrl+V | Maiusc+Comando+V |
| Stampa | Alt+P | Comando+P |
| Annulla | Ctrl+Z | Comando+Z |
| Ripeti | Ctrl+Y | Maiusc+Comando+Z |
| Nuovo pannello vuoto | Alt+B | Opzione+B |
| Nuova forma libera | Alt+A | Opzione+A |
| Nuova tabella a forma libera | Alt+1 | Opzione+1 |
| Nuova riga | Alt+2 | Opzione+2 |
| Nuova barra | Alt+3 | Opzione+3 |
| Invia rapporto ora | Alt+S | Opzione+S |
| Invia rapporto secondo pianificazione | Maiusc+Alt+S | Maiusc+Opzione+S |
| Rapporti pianificati | Maiusc+Alt+L | <!-- Should be 'Shift + Option + L ' but does not work on Mac --> |

## Letture di approfondimento {#further-reading}

 Adobe Campaign Standard si impegna a fornire un livello di accessibilità sempre maggiore, rendendo il prodotto più facile da utilizzare per tutti gli utenti.

Consigliamo di utilizzare il [modulo di feedback sull’accessibilità di Adobe](https://www.adobe.com/accessibility/feedback.html) per inviare suggerimenti di miglioramento e segnalare i problemi di accessibilità incontrati.

Per seguire gli ultimi miglioramenti e funzioni, puoi fare riferimento alle [note sulla versione di Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/release-notes/release-notes.html?lang=it#release-notes).
