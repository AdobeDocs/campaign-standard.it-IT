---
title: Informazioni sull’integrazione di Campaign ed Experience Manager
description: Con l’integrazione Adobe Experience Manager, puoi creare contenuti direttamente in AEM e utilizzarli successivamente in Adobe Campaign.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: ff94f69b-3036-4103-a841-6b85feb0eb7e
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '631'
ht-degree: 1%

---

# Informazioni sull’integrazione di Campaign ed Experience Manager{#integrating-with-experience-manager}

Questa integrazione tra Adobe Campaign Standard e Adobe Experience Manager consente di utilizzare il contenuto creato in Adobe Experience Manager nelle e-mail Adobe Campaign.

Puoi quindi sfruttare al massimo le funzionalità di modifica dei contenuti di Adobe Experience Manager, nonché le funzionalità di consegna e gestione dei dati di Adobe Campaign. Non è possibile eseguire test A/B per i contenuti importati da Adobe Experience Manager.

Adobe Campaign Standard è compatibile con Adobe Experience Manager 6.1, 6.2, 6.3, 6.4 e 6.5. Le sezioni seguenti presentano una panoramica delle azioni che puoi eseguire. Per ulteriori informazioni, consulta le sezioni dedicate a [configurazione](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/campaignstandard.html) e [use](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/aem-adobe-campaign/campaign.html) dell&#39;integrazione.

>[!NOTE]
>
> I modelli di Adobe Campaign Standard non sono più disponibili con Adobe Experience Manager 6.5.

## Suggerimenti sull’utilizzo dell’integrazione Campaign-Experience Manager {#tips-aem}

* **Scopri quale modello utilizzare con l’integrazione**

   Poiché i modelli e-mail sono modificabili all’interno di Adobe Experience Manager, la modifica di qualsiasi modello in Adobe Experience Manager potrebbe risultare più semplice. Ma alcuni modelli non sono facilmente adattabili. Per questa integrazione non sono consigliati modelli specifici per un cliente e devono essere modificati direttamente in Adobe Campaign Standard.

   Per ulteriori informazioni sui modelli, consulta questo [page](https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/templates/templates.html).

* **Assicurati che l’esternalizzatore sia stato configurato durante l’implementazione**

   La configurazione dell’esternalizzatore durante l’implementazione di Experience Manager per Adobe Campaign Standard consente di trasformare un percorso di risorsa in un URL. Questo consente di rendere le immagini visibili sulla pagina. Se l’esternalizzatore non è configurato correttamente, le e-mail conterranno immagini interrotte.

   Per informazioni su come configurare l’Externalizer, consulta [page](https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/externalizer.html).

* **Organizza i modelli e-mail per evitare abusi.**

   Mantenere organizzati i modelli assicura che i modelli appropriati si trovino nelle cartelle appropriate e non scelgano quelli sbagliati per errore. Durante l’implementazione, è necessario creare percorsi per salvare i modelli nelle posizioni giuste.

   Per ulteriori informazioni sui modelli, consulta questo [page](https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/templates/templates.html#template-availability).

* **Inizia subito a usare i componenti predefiniti.**

   I componenti predefiniti in Adobe Experience Manager per Adobe Campaign Standard possono aiutarti a iniziare rapidamente se i modelli non sono complessi.
Nell’Experience Manager sono disponibili sette componenti predefiniti che è possibile utilizzare:

   * Intestazione
   * Immagine
   * Collegamento
   * Modello immagini Scene7
   * Riferimento mirato
   * Testo e immagine
   * Testo e personalizzazione

* **HTML for emails è diverso da HTML per web**

   È importante comprendere che non è possibile utilizzare gli stessi componenti utilizzati nel contenuto web per i modelli e-mail. L’utilizzo di componenti predefiniti assicura la compatibilità con le e-mail dei componenti.

* **Scollega i contenuti dai modelli e riutilizzali più e più volte.**

   Quando configuri le e-mail in Campaign Standard e selezioni un modello di Experience Manager, puoi scegliere solo uno che non è già stato collegato a un’altra campagna. In caso contrario, se modifichi il contenuto in Adobe Experience Manager per una campagna e un aggiornamento, puoi influenzare involontariamente il contenuto dell’altra campagna.
Per evitare questo problema, una volta terminato l’utilizzo del modello, puoi scollegarlo per riutilizzarlo. È sufficiente selezionare il modello e fare clic su **[!UICONTROL Delete the link with Adobe Experience Manager content]**.

* **Utilizza Adobe Experience Manager per creare varianti di e-mail per Adobe Campaign Standard.**

   Questa integrazione ti consente di trasformare facilmente un’e-mail in diverse versioni con la segmentazione.
Per informazioni su come impostare la segmentazione in Adobe Experience Manager e come creare e-mail con contenuto di destinazione, consulta questo [page](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/aem-adobe-campaign/target-adobe-campaign.html#setting-up-segmentation-in-aem).

* **Per una sincronizzazione corretta, il nome del segmento in Experience Manager deve corrispondere esattamente al nome del segmento in Campaign.**
