---
title: Informazioni sull’integrazione di Campaign ed Experience Manager
description: Con l’integrazione di Adobe Experience Manager, puoi creare contenuti direttamente in AEM e utilizzarli successivamente in Adobe Campaign.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
feature: Triggers
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: ff94f69b-3036-4103-a841-6b85feb0eb7e
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '597'
ht-degree: 1%

---

# Informazioni sull’integrazione di Campaign ed Experience Manager{#integrating-with-experience-manager}

Questa integrazione tra Adobe Campaign Standard e Adobe Experience Manager consente di utilizzare i contenuti creati in Adobe Experience Manager nelle e-mail di Adobe Campaign.

Puoi quindi sfruttare al massimo le funzionalità di modifica dei contenuti di Adobe Experience Manager e le funzionalità di consegna e gestione dei dati di Adobe Campaign. Non è possibile eseguire test A/B per i contenuti importati da Adobe Experience Manager.

Adobe Campaign Standard è compatibile con Adobe Experience Manager 6.1, 6.2, 6.3, 6.4 e 6.5. Le sezioni seguenti presentano una panoramica delle azioni che è possibile eseguire. Per ulteriori informazioni, consulta le sezioni dedicate alla [configurazione](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/campaignstandard.html?lang=it) e al [utilizzo](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/aem-adobe-campaign/campaign.html?lang=it) dell&#39;integrazione.

>[!NOTE]
>
> I modelli Adobe Campaign Standard non sono più disponibili con Adobe Experience Manager 6.5.

## Suggerimenti sull’utilizzo dell’integrazione Campaign-Experience Manager {#tips-aem}

* **Scopri quale modello utilizzare con l&#39;integrazione**

  Poiché i modelli e-mail sono modificabili in Adobe Experience Manager, potrebbe essere più semplice modificare qualsiasi modello in Adobe Experience Manager. Tuttavia, alcuni modelli non sono facilmente adattabili. I modelli personalizzati specifici di un cliente non sono consigliati per questa integrazione e devono essere modificati direttamente in Adobe Campaign Standard.

  Per ulteriori informazioni sui modelli, consulta questa [pagina](https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/templates/templates.html?lang=it).

* **Verificare che Externalizer sia stato configurato durante l&#39;implementazione**

  La configurazione di Externalizer durante l’implementazione di Experience Manager per Adobe Campaign Standard consente di trasformare un percorso di risorsa in un URL. Questo consente di rendere visibili le immagini sulla pagina. Se Externalizer non è configurato correttamente, le e-mail conterranno immagini danneggiate.

  Per informazioni su come configurare Externalizer, consulta questa [pagina](https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/externalizer.html?lang=it).

* **Organizza i tuoi modelli e-mail per evitare utilizzi impropri.**

  Mantenendo organizzati i modelli, si garantisce che i modelli appropriati si trovino nelle cartelle appropriate e che non vengano selezionati erroneamente. Durante l’implementazione, è necessario creare i percorsi per salvare i modelli nelle posizioni giuste.

  Per ulteriori informazioni sui modelli, consulta questa [pagina](https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/templates/templates.html?lang=it#template-availability).

* **Introduzione rapida ai componenti predefiniti.**

  I componenti pronti all’uso in Adobe Experience Manager per Adobe Campaign Standard possono aiutarti a iniziare rapidamente se i modelli non sono complessi.
In Experience Manager sono disponibili sette componenti pronti all’uso che puoi iniziare a utilizzare:

   * Intestazione
   * Immagine
   * Collegamento
   * Modello immagini Scene7
   * Riferimento di destinazione
   * Testo e immagine
   * Testo e Personalization

* **HTML per le e-mail è diverso da HTML per il Web**

  È importante comprendere che non è possibile utilizzare gli stessi componenti utilizzati nel contenuto web per i modelli e-mail. L’utilizzo di componenti pronti all’uso garantisce la compatibilità dei componenti con la posta elettronica.

* **Scollega il contenuto dai modelli e riutilizzali più volte.**

  Quando imposti le e-mail in Campaign Standard e selezioni un modello Experience Manager, puoi sceglierne solo uno che non sia già stato collegato a un’altra campagna. In caso contrario, se modifichi il contenuto in Adobe Experience Manager per una campagna e aggiorni, puoi influire involontariamente sul contenuto nell’altra campagna.
Per evitare questo problema, dopo aver finito di utilizzare il modello, puoi scollegarlo e riutilizzarlo. Selezionare il modello e fare clic su **[!UICONTROL Delete the link with Adobe Experience Manager content]**.

* **Utilizza Adobe Experience Manager per creare varianti di e-mail per Adobe Campaign Standard.**

  Questa integrazione ti consente di trasformare facilmente un’e-mail in più versioni con la segmentazione.
Per informazioni su come impostare la segmentazione in Adobe Experience Manager e come creare e-mail con contenuto di destinazione, consulta questa [pagina](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/aem-adobe-campaign/target-adobe-campaign.html?lang=it#setting-up-segmentation-in-aem).

* **Per una sincronizzazione corretta, il nome del segmento in Experience Manager deve corrispondere esattamente al nome del segmento in Campaign.**
