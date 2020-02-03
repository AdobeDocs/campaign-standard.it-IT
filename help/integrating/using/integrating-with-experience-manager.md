---
title: Informazioni sull’integrazione di Campaign ed Experience Manager
description: Con l'integrazione di Adobe Experience Manager, puoi creare contenuti direttamente in AEM e usarli successivamente in Adobe Campaign.
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
source-git-commit: 5c1a540475b7d93c18c957243ee2a403b8154aa3

---


# Informazioni sull’integrazione di Campaign ed Experience Manager{#integrating-with-experience-manager}

Questa integrazione tra Adobe Campaign Standard e Adobe Experience Manager consente di utilizzare il contenuto creato in Adobe Experience Manager nelle e-mail di Adobe Campaign.

Di conseguenza, puoi sfruttare al massimo le funzionalità di modifica dei contenuti di Adobe Experience Manager, nonché le funzionalità di consegna e gestione dei dati di Adobe Campaign. Non potete eseguire test A/B per i contenuti importati da Adobe Experience Manager.

Adobe Campaign Standard è compatibile con Adobe Experience Manager 6.1, 6.2, 6.3, 6.4 e 6.5. Nelle sezioni seguenti viene fornita una panoramica delle azioni che è possibile eseguire. Per ulteriori informazioni, consultare le sezioni dedicate alla [configurazione](https://docs.adobe.com/content/help/en/experience-manager-65/administering/integration/campaignstandard.html) e all&#39; [utilizzo](https://docs.adobe.com/content/help/en/experience-manager-65/authoring/aem-adobe-campaign/campaign.html) dell&#39;integrazione.

>[!NOTE]
>
> I modelli di Adobe Campaign Standard non sono più disponibili con Adobe Experience Manager 6.5.

## Suggerimenti sull&#39;utilizzo dell&#39;integrazione Campaign-Experience Manager {#tips-aem}

* **Saperne il modello da utilizzare con l&#39;integrazione**

   Poiché i modelli e-mail sono modificabili in Adobe Experience Manager, la modifica di qualsiasi modello in Adobe Experience Manager potrebbe risultare più semplice. Ma alcuni modelli non sono facilmente adattabili. Per questa integrazione non sono consigliati modelli personalizzati specifici per un cliente, che devono essere modificati direttamente in Adobe Campaign Standard.

   Per ulteriori informazioni sui modelli, consultare questa [pagina](https://docs.adobe.com/content/help/en/experience-manager-65/developing/platform/templates/templates.html).

* **Accertatevi che Externalizer sia stato configurato durante l&#39;implementazione**

   La configurazione dell&#39;Externalizer durante l&#39;implementazione di Experience Manager per Adobe Campaign Standard consente di trasformare un percorso di risorsa in un URL. Questo consente di rendere le immagini visibili sulla pagina. Se l&#39;Externalizer non è configurato correttamente, i messaggi e-mail conterranno immagini interrotte.

   Per informazioni su come configurare l&#39;Externalizer, consulta questa [pagina](https://docs.adobe.com/content/help/en/experience-manager-65/developing/platform/externalizer.html)

* **Organizzate i modelli delle e-mail per evitare abusi.**

   Mantenendo i modelli organizzati, è possibile che i modelli appropriati si trovino nelle cartelle appropriate e che non vengano selezionati per errore quelli sbagliati. Durante l&#39;implementazione, è necessario creare percorsi per salvare i modelli nei luoghi giusti.

   Per ulteriori informazioni sui modelli, consulta questa [pagina](https://docs.adobe.com/content/help/en/experience-manager-65/developing/platform/templates/templates.html#template-availability)

* **Introduzione rapida ai componenti forniti.**

   I componenti forniti in Adobe Experience Manager per Adobe Campaign Standard possono aiutarti a iniziare rapidamente se i modelli non sono complessi.
In Experience Manager sono disponibili sette componenti out-of-the-box che puoi utilizzare:
   1. Intestazione
   1. Immagine
   1. Collegamento
   1. Modello immagini Scene7
   1. Riferimento mirato
   1. Testo e immagine
   1. Testo e personalizzazione

* **HTML for email è diverso da HTML per Web**

   È importante comprendere che non è possibile utilizzare gli stessi componenti utilizzati nel contenuto Web per i modelli di e-mail. L’utilizzo di componenti predefiniti assicura che i componenti siano compatibili con le e-mail.

* **Scollegare i contenuti dai modelli e riutilizzarli ripetutamente.**

   Quando configurate le e-mail in Campaign Standard e selezionate un modello Experience Manager, potete scegliere solo uno che non sia già stato collegato a un&#39;altra campagna. In caso contrario, se modificate il contenuto in Adobe Experience Manager per una campagna e lo aggiornate, potete avere un impatto involontario sul contenuto dell&#39;altra campagna.
Per evitare questo problema, una volta completato l’utilizzo del modello, potete scollegarlo per riutilizzarlo. È sufficiente selezionare il modello e fare clic **[!UICONTROL Delete the link with Adobe Experience Manager content]**.

* **Utilizzate Adobe Experience Manager per creare varianti di e-mail per Adobe Campaign Standard.**

   Questa integrazione consente di trasformare facilmente un messaggio e-mail in diverse versioni con la segmentazione.
Per informazioni su come impostare la segmentazione in Adobe Experience Manager e come creare e-mail con contenuti mirati, consulta questa [pagina](https://docs.adobe.com/help/en/experience-manager-65/authoring/aem-adobe-campaign/target-adobe-campaign.html#setting-up-segmentation-in-aem).

* **Per una sincronizzazione corretta, il nome del segmento in Experience Manager deve corrispondere esattamente al nome del segmento in Campaign.**