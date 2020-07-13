---
title: Predictive capacità di coinvolgimento degli utenti
description: Scopri come utilizzare il tempo di invio predittivo e il punteggio di coinvolgimento.
page-status-flag: never-activated
uuid: c2c13934-9819-4e18-b5c7-60915c907f37
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: ai-powered-emails
discoiquuid: 609355f6-9003-41b9-9981-ea787419fbf5
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: f45985c030c3d5059bfef444287c10b842298f49
workflow-type: tm+mt
source-wordcount: '1058'
ht-degree: 0%

---


# Ottimizzazione della progettazione e della distribuzione con e-mail alimentate dall&#39;intelligenza artificiale{#journey-ai}

## Introduzione alle e-mail basate sull&#39;intelligenza artificiale{#journey-ai-ovv}

Utilizzando Campaign, puoi ottimizzare la progettazione e la consegna dei percorsi dei clienti per prevedere le preferenze di coinvolgimento di ogni individuo. Basato su Journey AI,  Adobe Campaign può analizzare e prevedere le tariffe aperte, i tempi di invio ottimali e il probabile churn in base alle metriche di coinvolgimento storiche.

**Modelli di apprendimento automatico**

 Adobe Campaign Standard offre due nuovi modelli di apprendimento automatico: **Ottimizzazioni** predittive dei tempi di invio e punteggio **di coinvolgimento** predittivo. Questi due modelli sono denominati insieme Journey AI, una classe di modelli di machine learning che sono specifici per progettare e fornire percorsi migliori per i clienti.

* **Ottimizzazione** tempo di invio predittiva: Predictive ottimizzazione dell&#39;ora di invio prevede che si tratti del tempo di invio migliore per ciascun profilo del destinatario per le aperture e-mail o i clic. Per ciascun profilo del destinatario, i punteggi indicano il tempo di invio migliore per ogni giorno feriale e il giorno feriale migliore da inviare per ottenere risultati ottimali.

* **Predictive Engagement Scoring**: Il punteggio relativo al coinvolgimento predittivo prevede la probabilità che un destinatario si impegni con un messaggio e la probabilità di non partecipare (annullamento dell&#39;iscrizione) entro i successivi 7 giorni dall&#39;invio successivo dell&#39;e-mail. Le probabilità sono ulteriormente suddivise in bucce a seconda del rischio specifico di disimpegno, medio o basso. Tra questi il modello fornisce anche il grado percentile di rischio per i clienti per capire dove il grado di un determinato cliente rispetto ad altri.

>[!NOTE]
> **Prerequisiti **
>
>Questa funzionalità non è disponibile all&#39;esterno come parte del prodotto. L&#39;implementazione richiede il coinvolgimento di Adobe Consulting. Per maggiori informazioni, contattate il vostro rappresentante Adobe.
>
>Separatamente, la funzionalità richiedeva l&#39;utilizzo di un archivio di Azure che deve essere fornito dal cliente.

## Ottimizzazione del tempo di invio predittiva{#predictive-send-time}

### Ottimizzare clic e aperture{#about-predictive-send-time}

Predictive tempi di invio prevede che è il tempo di invio migliore per ciascun profilo del destinatario per le aperture e i clic dell&#39;e-mail. Per ciascun profilo del destinatario, i punteggi indicano il tempo di invio migliore per ogni giorno feriale e il giorno feriale migliore da inviare per ottenere risultati ottimali.

Nel modello Predictive Send Time Optimization sono presenti due modelli secondari:
* Tempo di invio predittivo per l&#39;apertura è il momento migliore per inviare una comunicazione al cliente per massimizzare le aperture
* Tempo di invio predittivo per click è il momento migliore per inviare una comunicazione al cliente per massimizzare i clic

**Ingresso** modello: Registri di distribuzione, registri di monitoraggio e attributi di profilo (non PII)

**Output** modello: Momento migliore per inviare un messaggio (per aperture e clic)


Dettagli di output

* Calcola l’ora migliore per inviare un messaggio e-mail per i successivi 7 giorni con intervalli di 1 ora (ad es.: 9:00, 10:00, 11:00)
* Il modello indicherà l&#39;ora migliore entro i prossimi 7 giorni per inviare l&#39;e-mail
* Ogni tempo ottimale viene calcolato due volte: una volta per massimizzare il tasso di apertura e una volta per massimizzare il tasso di clic
* Sono forniti 16 campi (14 per i giorni della settimana e 2 per l&#39;intera settimana):
   * è il momento migliore per inviare un&#39;e-mail per ottimizzare i clic per lunedì - valori compresi tra 0 e 23
   * è il momento migliore per inviare un messaggio e-mail per ottimizzare le aperture per lunedì - valori compresi tra 0 e 23
   * è il momento migliore per inviare un&#39;e-mail per ottimizzare i clic per il martedì - valori compresi tra 0 e 23
   * ...
   * è il momento migliore per inviare un&#39;e-mail per ottimizzare i clic per la domenica - valori compresi tra 0 e 23
   * è il momento migliore per inviare un messaggio e-mail per ottimizzare le aperture per domenica - valori compresi tra 0 e 23
   * ...
   * giorno migliore per inviare un&#39;e-mail per ottimizzare le aperture per tutta la settimana - da lunedì a domenica
   * il momento migliore per inviare un&#39;e-mail per ottimizzare le aperture per tutta la settimana - valori compresi tra 0 e 23

>[!NOTE]
>
>Queste funzionalità predittive si applicano solo alle comunicazioni e-mail.
>
>Il modello necessita di almeno un mese di dati per produrre risultati significativi.


### Risultati profilo di accesso{#access-predictive-send-time-scores}

Una volta implementate in Campaign, le funzionalità di machine Learning arricchiscono i dati dei profili con le nuove schede con i punteggi migliori di apertura e clic. Le metriche sono calcolate da Journey AI e vengono inserite in Campaign utilizzando flussi di lavoro tecnici.

Per accedere a tali metriche, è necessario:

1. Aprite un profilo e fate clic sul pulsante Modifica.

1. Fare clic sulla scheda **Send Time Score By Click** o **Send Time Score By Open** .

Per impostazione predefinita, i punteggi dei profili danno il tempo migliore del giorno per ogni giorno della settimana e il tempo complessivo migliore della settimana.

![](assets/do-not-localize/SendTimeScore.png)

### Invia messaggi al momento migliore{#use-predictive-send-time}

Affinché le e-mail possano essere inviate al momento ottimale per profilo, la consegna deve essere pianificata utilizzando l&#39;opzione **[!UICONTROL Send at a custom date defined by a formula]**.
Scopri come calcolare la data di invio [in questa sezione](../../sending/using/computing-the-sending-date.md).

La formula deve essere compilata con il momento migliore specifico del giorno in cui la consegna andrà fuori.

![](assets/do-not-localize/ComputeSendingDate.png)

Esempio di formula:

```
AddHours([currentDelivery/scheduling/@contactDate], 
[cusSendTimeScoreByClickprofile_link/@EMAIL_BEST_TIME_TO_CLICK_WEDNESDAY])
```

![](assets/do-not-localize/SendingDateFormula.png)

>[!NOTE]
>
>Il modello dati potrebbe essere diverso a seconda dell&#39;implementazione.



## Predictive Engagement Scoring {#predictive-scoring}

Il punteggio di coinvolgimento predittivo consente di:

* **Selezionate un&#39;audience**: utilizzando l&#39;attività di query, puoi selezionare l&#39;audience con cui interagire con un messaggio specifico
* **Escludere un&#39;audience**: utilizzando l&#39;attività di query, potete rimuovere l&#39;audience per annullare la sottoscrizione
* **Personalizza**: personalizza i messaggi in base al livello di coinvolgimento (gli utenti altamente coinvolti riceveranno un messaggio diverso da quelli non coinvolti)

Questo modello utilizza più punteggi per indicare:

* **Aprite Il Punteggio Del Coinvolgimento / Fate Clic Sul Punteggio** Del Coinvolgimento: questo valore corrisponde alla probabilità che un utente iscritto si occupi di un messaggio specifico (aperto o clic). I valori sono compresi tra 0,0 e 1,0.
* **Probabilità** di annullamento sottoscrizione: questo valore corrisponde alla probabilità che il destinatario annulli l’iscrizione dal canale e-mail a causa di un messaggio e-mail aperto. I valori sono compresi tra 0,0 e 1,0.
* **Livello** di mantenimento:  questo valore classifica gli utenti in tre livelli: bassa, media e alta. Il valore elevato è molto probabile che rimanga con il marchio e il valore basso che potrebbe annullare l&#39;iscrizione.
* **Grado percentuale di conservazione**: la classificazione del profilo in termini di probabilità di annullamento della sottoscrizione. I valori sono compresi tra 0,0 e 1,0. Ad esempio, se la percentuale di mantenimento è 0,953, il destinatario ha più probabilità di restare con il marchio e meno probabilità di annullare l’iscrizione rispetto al 95,3% di tutti i destinatari.

>[!NOTE]
>
>Queste funzionalità predittive si applicano solo alle comunicazioni e-mail.
>
>Il modello necessita di almeno un mese di dati per produrre risultati significativi.


**Input** modello: Registri di distribuzione, registri di monitoraggio e attributi di profilo specifici

**Output** modello: Un attributo di profilo che descrive la valutazione e la categoria del profilo


### Utilizzo del punteggio di coinvolgimento per il canale e-mail

Per accedere a tali metriche, è necessario:

1. Aprite un profilo e fate clic sul pulsante Modifica.

1. Fate clic sulla scheda **Punteggi di coinvolgimento per canale** e-mail.

Utilizzando un&#39;attività di query in un flusso di lavoro, potete utilizzare la valutazione per ottimizzare il pubblico.

Ad esempio, con i criteri del livello **** Mantenimento:

![](assets/do-not-localize/predictive_score_query.png)























