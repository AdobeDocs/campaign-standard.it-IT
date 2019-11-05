---
title: Informazioni sulle pagine di destinazione
description: Scopri le pagine di destinazione di Campaign e il loro ciclo di vita.
page-status-flag: mai attivato
uuid: b316bf47-7d98-46fa-ab4f-67ff50de8095
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: canali
content-type: reference
topic-tags: landing page
discoiquuid: ca8d1698-6e8a-4f5a-b017-74a152e14286
context-tags: landingPage,procedura guidata;landingPage,panoramica;landingPage,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Informazioni sulle pagine di destinazione{#about-landing-pages}

Campaign viene fornito con pagine di destinazione, moduli Web che possono essere utilizzati per acquisire informazioni sui tipi di pubblico, offrire iscrizioni a un servizio, visualizzare i dati e ampliare il database. Le pagine di destinazione possono essere utilizzate anche per acquisire o aggiornare i profili esistenti.

Per ulteriori informazioni sui passaggi necessari per impostare una pagina di destinazione, consulta [questa sezione](../../channels/using/main-steps-to-set-up-a-landing-page.md)

**Argomenti correlati:**

* [Video](https://helpx.adobe.com/campaign/kt/acs/using/acs-create-edit-landing-page-feature-video-use.html) sulla creazione di un’esercitazione sulla pagina di destinazione
* [Utilizzo di una pagina di destinazione per l’iscrizione a un servizio](../../audiences/using/creating-a-service.md)

## Ciclo di vita delle pagine di destinazione {#landing-pages-life-cycle}

L’intero ciclo di vita di una pagina di destinazione è il seguente:

1. Creazione: progettate e impostate il contenuto della pagina di destinazione.
1. Prova: simulare l’esecuzione della pagina di destinazione su un profilo di test.
1. Pubblicazione: pubblicate la pagina di destinazione per renderla live.
1. Scadenza o depubblicazione: annulla la pubblicazione manualmente o attendi la scadenza della pagina di destinazione, per cui non è più disponibile.

![](assets/lp_livecycle.png)

Una volta creata e pubblicata, potete rendere la pagina di destinazione accessibile tramite un sito Web o [inserire un collegamento diretto alla pagina di destinazione in un messaggio e-mail](../../designing/using/links.md#inserting-a-link).

## Limitazioni per la pagina di destinazione{#landing-page-limitations}

La sezione seguente elenca i limiti di cui dovreste essere consapevoli prima di iniziare a impostare le pagine di destinazione.

**Scrittura e aggiornamento dei dati**

* Le pagine di destinazione sono limitate solo a **[!UICONTROL Profile]** **[!UICONTROL Subscription]** risorse e risorse. La registrazione può essere salvata e aggiornata da **[!UICONTROL Profile]** e da una sottoscrizione o annullamento della sottoscrizione a un **[!UICONTROL Service]**.
Per ulteriori informazioni sulla configurazione delle risorse, vedere [Configurazione della struttura](../../developing/using/configuring-the-resource-s-data-structure.md)dati della risorsa.

>[!CAUTION]
>
>Una pagina di destinazione non può visualizzare o aggiornare i dati provenienti da altre risorse oltre a **[!UICONTROL Profile]** e **[!UICONTROL Subscription]**.

**Precaricamento**

* La pagina di destinazione non può visualizzare automaticamente un elenco di record, non può elencare i servizi a cui sono già stati sottoscritti profili. Per ulteriori informazioni sui servizi, consultare questa [pagina](../../audiences/using/creating-a-service.md).

* La pagina di destinazione con un modulo precompilato (i dati vengono precaricati con la pagina) è accessibile solo da un'e-mail di Adobe Campaign. Non è possibile accedere a tale modulo da una pagina Web.

**Riconciliazione**

* Il comportamento di riconciliazione è il seguente: non appena viene trovata una partita, il processo di riconciliazione si interrompe. Ciò significa che la riconciliazione può essere fatta solo su un record di profilo e non su più record in presenza di duplicati.

Ad esempio, vuoi inviare la seguente pagina di destinazione di acquisizione ai tuoi profili per aggiornare il database Campaign con i numeri di cellulare dei tuoi profili.

![](assets/landing_page_limitation_1.png)

Se uno dei profili inserisce nuove informazioni nella pagina di destinazione ma presenta già un profilo duplicato, verrà aggiornato il profilo corrispondente alla data di creazione più recente, in quanto la priorità dei profili dipende solo dalla data di creazione.

Qui è stato aggiornato solo il primo profilo, perché si trattava della voce più vecchia.

![](assets/landing_page_limitation_2.png)

**Verifica delle pagine di destinazione**

* Le pagine di destinazione funzionano solo sui profili e non sui profili di prova, il che significa che non è possibile sottoporre a test le pagine di destinazione come parte di una prova e-mail.
