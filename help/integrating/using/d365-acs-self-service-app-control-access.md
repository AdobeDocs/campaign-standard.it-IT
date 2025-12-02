---
title: Accedere all’app self-service per l’integrazione di Adobe Campaign Standard con Dynamics 365
description: Integrazione di Adobe Campaign Standard con l’app self-service Dynamics 365
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
feature: Microsoft CRM Integration
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 44b59f56-99be-41ae-af8d-76272bb94d18
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '415'
ht-degree: 1%

---

# Accedere all’integrazione di Adobe Campaign Standard con l’app self-service Microsoft Dynamics 365

Per questa configurazione è necessario rivolgersi a un amministratore Experience Cloud (EC) dell’organizzazione. Questi sono i passaggi iniziali necessari per consentire l&#39;accesso all&#39;interfaccia dell&#39;applicazione di integrazione self-service. Una volta che hai accesso allo strumento, configurerai le connessioni ai tuoi dati e configurerai il flusso di dati tra Adobe Campaign e Microsoft Dynamics 365.

>[!NOTE]
>
>Devi contattare il tuo rappresentante Adobe e fornire i nomi delle organizzazioni e delle istanze Adobe Campaign Standard. Verrà registrato un ticket per richiedere che l’app di integrazione sia abilitata per la tua organizzazione.

## Aggiungere un profilo di prodotto

In questa sezione imparerai a concedere l’accesso all’integrazione Adobe Campaign Standard con l’app self-service Microsoft Dynamics 365. Gli utenti che hanno accesso alla tua organizzazione in Adobe Experience Cloud non avranno accesso all’app self-service di integrazione, a meno che tu non segua i passaggi seguenti per concedere loro l’accesso.

>[!IMPORTANT]
>
> Questi passaggi richiedono il ruolo di **Amministratore** in Experience Cloud per la tua organizzazione.
>

1. Passa a https://experience.adobe.com/ e accedi a Adobe Experience Cloud.
1. Accedi a **Admin Console**.

   ![](assets/do-not-localize/d365-to-acs-access-3.png)

1. Fai clic su **[!UICONTROL Products]** per accedere alle tue soluzioni Experience Cloud.

   ![](assets/do-not-localize/d365-to-acs-access-6.png)


   >[!IMPORTANT]
   >
   >I passaggi rimanenti in questa sezione vengono eseguiti per ciascuna istanza di Campaign (sviluppo, testo, produzione).
   >

1. Fai clic sulla prima istanza da configurare.

   ![](assets/do-not-localize/d365-to-acs-access-6.png)

   La pagina dell’istanza deve avere un aspetto simile al seguente:

   ![](assets/do-not-localize/d365-to-acs-access-8.png)

1. Fai clic sul pulsante **[!UICONTROL New Profile]** e aggiungi una nuova voce denominata: **Campaign Standard - your-prod-instance-name - D365/ACS Integration**

   * Se vedi questa voce nell’elenco, non è necessario procedere. Fai clic su **Adobe Campaign Standard** nel menu a sinistra e controlla le altre istanze di Campaign.

   * Assicurati di sostituire &quot;your-prod-instance-name&quot; con il nome effettivo dell’istanza.

1. È possibile lasciare il menu a discesa **[!UICONTROL Permission Group]** con il valore predefinito.

1. Se le voci sono simili alle seguenti, fare clic sul pulsante **[!UICONTROL Done]**.

   ![](assets/do-not-localize/d365-to-acs-access-14.png)

   È stato aggiunto il nuovo profilo di prodotto.

   ![](assets/do-not-localize/d365-to-acs-access-15.png)

## Concedere l’accesso agli utenti {#add-users-to-profile}

Dalla pagina **[!UICONTROL Products]**, seleziona l’istanza Campaign e segui i passaggi seguenti:

1. Fai clic sul nuovo profilo creato in precedenza: **Campaign Standard - nome-istanza-prod - Integrazione D365/ACS**

   ![](assets/do-not-localize/d365-to-acs-access-15.png)

1. Fare clic sulla scheda **[!UICONTROL Developers]**.

   ![](assets/do-not-localize/d365-to-acs-access-18.png)

1. Fare clic sul pulsante **[!UICONTROL Add Developer]**

1. Immettere il nome o l&#39;indirizzo di posta elettronica dell&#39;utente che si desidera aggiungere.  Seleziona il risultato che corrisponde all’utente.

   Se si tratta della prima volta che l’utente viene aggiunto all’organizzazione, inserisci i dettagli.

1. Fai clic su **[!UICONTROL Save]** per confermare.
