---
solution: Campaign Standard
product: campaign
title: Informazioni sull’integrazione di Campaign ed Experience Manager
description: Con l'integrazione Adobe Experience Manager, potete creare contenuti direttamente in AEM e usarli successivamente in  Adobe Campaign.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '642'
ht-degree: 1%

---


# Informazioni sull’integrazione di Campaign ed Experience Manager{#integrating-with-experience-manager}

Questa integrazione tra  Adobe Campaign Standard e Adobe Experience Manager consente di utilizzare il contenuto creato in Adobe Experience Manager nelle e-mail  Adobe Campaign.

È quindi possibile sfruttare al massimo le funzionalità di modifica dei contenuti di Adobe Experience Manager, nonché  funzionalità di distribuzione e gestione dei dati di Adobe Campaign. Non è possibile eseguire test A/B per i contenuti importati da Adobe Experience Manager.

 Adobe Campaign Standard è compatibile con Adobe Experience Manager 6.1, 6.2, 6.3, 6.4 e 6.5. Nelle sezioni seguenti viene fornita una panoramica delle azioni che è possibile eseguire. Per ulteriori informazioni, fare riferimento alle sezioni dedicate a [configurazione](https://docs.adobe.com/content/help/en/experience-manager-65/administering/integration/campaignstandard.html) e all&#39; [uso](https://docs.adobe.com/content/help/en/experience-manager-65/authoring/aem-adobe-campaign/campaign.html) dell&#39;integrazione.

>[!NOTE]
>
>  modelli Adobe Campaign Standard non sono più disponibili con Adobe Experience Manager 6.5.

## Suggerimenti sull&#39;utilizzo dell&#39;integrazione di Experience Manager Campaign- {#tips-aem}

* **Saperne il modello da utilizzare con l&#39;integrazione**

   Poiché i modelli e-mail sono modificabili in Adobe Experience Manager, potrebbe essere più semplice modificare qualsiasi modello in Adobe Experience Manager. Ma alcuni modelli non sono facilmente adattabili. Per questa integrazione non sono consigliati modelli personalizzati specifici per un cliente, che devono essere modificati direttamente in  Adobe Campaign Standard.

   Per ulteriori informazioni sui modelli, fare riferimento a questa [pagina](https://docs.adobe.com/content/help/en/experience-manager-65/developing/platform/templates/templates.html).

* **Accertatevi che Externalizer sia stato configurato durante l&#39;implementazione**

   La configurazione dell&#39;Externalizer durante l&#39;implementazione  Experience Manager per  Adobe Campaign Standard consente di trasformare un percorso di risorsa in un URL. Questo consente di rendere le immagini visibili sulla pagina. Se l&#39;Externalizer non è configurato correttamente, i messaggi e-mail conterranno immagini interrotte.

   Per informazioni su come configurare l&#39;Externalizer, fare riferimento a questa [pagina](https://docs.adobe.com/content/help/en/experience-manager-65/developing/platform/externalizer.html).

* **Organizzate i modelli delle e-mail per evitare abusi.**

   Mantenendo i modelli organizzati, è possibile che i modelli appropriati si trovino nelle cartelle appropriate e che non si scelgano quelli sbagliati per errore. Durante l&#39;implementazione, è necessario creare percorsi per salvare i modelli nei luoghi giusti.

   Per ulteriori informazioni sui modelli, fare riferimento a questa [pagina](https://docs.adobe.com/content/help/en/experience-manager-65/developing/platform/templates/templates.html#template-availability).

* **Introduzione rapida ai componenti forniti.**

   I componenti forniti da Adobe Experience Manager per  Adobe Campaign Standard consentono di iniziare rapidamente a utilizzare i modelli in uso anche se non sono complessi.
Nel  Experience Manager sono disponibili sette componenti out-of-the-box che è possibile utilizzare:

   * Intestazione
   * Immagine
   * Collegamento
   * Modello immagine Scene7
   * Riferimento mirato
   * Testo e immagine
   * Testo e personalizzazione

* **L’HTML per le e-mail è diverso da HTML per il Web**

   È importante comprendere che non è possibile utilizzare gli stessi componenti utilizzati nel contenuto Web per i modelli di e-mail. L’utilizzo di componenti predefiniti assicura che i componenti siano compatibili con le e-mail.

* **Scollegare i contenuti dai modelli e riutilizzarli più e più volte.**

   Quando configurate le e-mail in Campaign Standard e selezionate un modello di Experience Manager , potete scegliere solo uno che non sia già stato collegato a un’altra campagna. In caso contrario, se modificate il contenuto in Adobe Experience Manager per una campagna e lo aggiornate, potete avere un impatto involontario sul contenuto dell&#39;altra campagna.
Per evitare questo problema, una volta completato l’utilizzo del modello, potete scollegarlo per riutilizzarlo. È sufficiente selezionare il modello e fare clic su **[!UICONTROL Delete the link with Adobe Experience Manager content]**.

* **Utilizzate Adobe Experience Manager per creare varianti di e-mail per  Adobe Campaign Standard.**

   Questa integrazione consente di trasformare facilmente un messaggio e-mail in diverse versioni con la segmentazione.
Per informazioni su come impostare la segmentazione in Adobe Experience Manager e come creare e-mail con contenuti mirati, fare riferimento a questa [pagina](https://docs.adobe.com/help/en/experience-manager-65/authoring/aem-adobe-campaign/target-adobe-campaign.html#setting-up-segmentation-in-aem).

* **Per una sincronizzazione corretta, il nome del segmento nel Experience Manager  deve corrispondere esattamente al nome del segmento in Campaign.**