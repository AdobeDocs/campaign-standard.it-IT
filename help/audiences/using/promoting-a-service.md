---
title: Promozione di un servizio
description: Utilizza Adobe Campaign per promuovere un servizio e coinvolgere i clienti tramite pagine di destinazione dedicate, e-mail o direttamente sul tuo sito web.
audience: audiences
content-type: reference
topic-tags: managing-subscriptions
feature: Audiences
role: User
level: Intermediate
exl-id: c1f8770a-8b25-41db-aa52-828e181a563d
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 3%

---

# Promozione di un servizio{#promoting-a-service}

È possibile offrire abbonamenti a un servizio in diversi modi e consentire ai visitatori di gestire i propri abbonamenti.

Puoi utilizzare Campaign per promuovere un servizio:

* [Inserimento di un collegamento di abbonamento a un servizio o di annullamento dell’abbonamento in un messaggio e-mail](../../designing/using/links.md#inserting-a-link).

* [Inserimento di un collegamento a una pagina di destinazione di abbonamento o del suo annullamento in un messaggio e-mail](../../designing/using/links.md). In questo caso, è necessario fare riferimento direttamente al servizio nelle proprietà delle pagine di destinazione correlate (consulta [Collegamento di una pagina di destinazione a un servizio](../../channels/using/configuring-landing-page.md#linking-a-landing-page-to-a-service)).

  >[!NOTE]
  >
  >È inoltre importante dare agli abbonati la possibilità di annullare l’abbonamento. A tale scopo, inserire un servizio <b>Collegamento per annullare l’iscrizione</b> nell’e-mail di conferma (definita nelle proprietà del servizio) inviata automaticamente ai nuovi abbonati e nelle e-mail delle newsletter future.

* Rendere disponibile su un sito web una pagina di destinazione di abbonamento o del suo annullamento. Gli URL che ti consentono di accedere alla pagina di destinazione devono specificare parametri quali il servizio associato e l’ID profilo che vi accede. Questo ID può essere definito nei parametri della pagina di destinazione (vedi [Configurazione di una pagina di destinazione](../../channels/using/configuring-landing-page.md)).
