---
title: Garanzie per l'integrazione di Microsoft Dynamics 365
description: Microsoft Dynamics 365 con guardrails di integrazione Campaign Standard
page-status-flag: never-activated
uuid: ed6c1b76-87f7-4d23-b5e2-0765297a905c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
discoiquuid: 6c0c3c5b-b596-459e-87dd-a06bb7d633d2
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e90f878814e65a9a61ee4013d94fd0bf3b1f7875
workflow-type: tm+mt
source-wordcount: '585'
ht-degree: 0%

---


# Garanzie e limiti di integrazione

## Guardrail di integrazione

Nel pianificare l&#39;utilizzo di questa integrazione è necessario tenere conto dei seguenti tuteli. Consultate il vostro rappresentante tecnico  Adobe se ritenete di superare questi corrimani.

* Dovrai ottenere la licenza per il pacchetto Campaign corretto per supportare il volume di chiamate al motore ACS generato dall&#39;integrazione. Il superamento del volume di chiamate del motore concesso in licenza potrebbe causare un peggioramento delle prestazioni della campagna.

   Utilizzate quanto segue per stimare il volume delle chiamate del motore dall&#39;integrazione:

   * Inserti di record (ad es., nuovo record): 1 chiamata al motore
   * Eliminazioni di record: 1 chiamata al motore
   * Aggiornamenti dei record: 2 chiamate al motore (solo 1 chiamata se il record di destinazione è identico al record di origine - cioè, se non viene apportata alcuna modifica al record ACS)

   Nella stima del volume complessivo delle chiamate al motore ACS, è importante tenere conto di altre origini di chiamate al motore, incluse pagine di destinazione, WebApps, JSSP, API, registrazioni di app mobili, ecc.

   Vedi le informazioni sul pacchetto Campaign: https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html

* L&#39;integrazione supporta un massimo di 30 milioni di contatti.

* L&#39;offerta di integrazione standard include il supporto per fino a cinque entità personalizzate

* Per le entità personalizzate con più di 500 KB di record, sono necessarie ore di consulenza supplementari per eseguire un&#39;importazione iniziale basata su file una sola volta (per entità personalizzata) tramite il flusso di lavoro Campaign (che comporta un costo aggiuntivo)

* L&#39;offerta di integrazione standard include il supporto per le entità personalizzate con dimensioni fino a 50 colonne.

* Prima di implementare l&#39;integrazione, dovrete creare e pubblicare le risorse personalizzate.

* La profondità massima della tabella quando si collegano le tabelle è due (cioè, tabella1->tabella2->tabella3)

* Il supporto per i tipi di dati Dynamic 365 è limitato. Se il modello dati contiene un tipo di dati diverso dai tipi di dati semplici (ad esempio, stringhe, interi, decimali, ecc.), potrebbe essere necessario aggiornare il modello dati prima di utilizzare l&#39;integrazione.

* La conservazione dei dati esistenti nelle entità personalizzate di Campaign può comportare costi aggiuntivi di consulenza per preparare i dati per l&#39;integrazione.

* Le finestre di manutenzione di onboarding potrebbero dover essere configurate tra  Adobe e il cliente, in quanto il caricamento iniziale potrebbe causare rallentamenti della campagna.

* Si consiglia di comunicare le istanze note di aumento significativo o &quot;picchi&quot; nell&#39;utilizzo dell&#39;integrazione (ad esempio, un forte aumento dei record nuovi o aggiornati), in quanto ciò potrebbe causare rallentamenti nella sincronizzazione dei dati.

* Come parte dell&#39;integrazione, è previsto di completare i passaggi di configurazione pre-integrazione in Microsoft Azure e Dynamics 365. Vedi i passaggi di configurazione [in questa pagina](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md)

* È previsto che i modelli di dati Dynamics 365 e Campaign vengano portati all&#39;integrazione e che vengano mantenuti.

## Limiti di integrazione

L&#39;integrazione è stata progettata per risolvere il caso d&#39;uso generale dello spostamento di dati tra Dynamics 365 e Campaign, ma non è destinata a risolvere ogni caso d&#39;uso specifico per ciascun cliente:

* L&#39;integrazione non emette alcun elemento di privacy (ad esempio, GDPR) eliminato. La responsabilità di soddisfare le richieste di privacy degli utenti finali spetta al cliente; tali richieste devono essere effettuate sia in Campaign (tramite l&#39;Adobe Experience Platform Privacy Service ) che in Dynamics 365 in modo indipendente. Se necessario, l&#39;integrazione può rilasciare delle eliminazioni regolari per facilitare la sincronizzazione dei dati.

* Nessun profilo o dati di entità personalizzati verrà sincronizzato da Campaign a Dynamics 365, ad eccezione delle informazioni di rifiuto (se configurate dal cliente).

* La gestione degli abbonamenti alle campagne (ad es., abbonamenti/annullamento di iscrizioni) non è supportata in modo nativo.

* La composizione e l&#39;attivazione delle campagne e-mail di Campaign da Dynamics 365 non è supportata.

* L&#39;integrazione non supporterà la rimozione dei dati tra i modelli di dati Dynamics 365 e Campaign. È previsto che l&#39;integrazione sincronizzerà una tabella di Dynamics 365 in una tabella di Campaign.

* Non esiste alcuna interfaccia utente self-service con la versione corrente dell&#39;integrazione.
