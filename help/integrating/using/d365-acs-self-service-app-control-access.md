---
title: Accedere all’integrazione di Adobe Campaign Standard con l’app self-service Dynamics 365
description: Integrazione di Adobe Campaign Standard con l’app self-service di Dynamics 365
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
feature: Microsoft CRM Integration
role: Data Architect
level: Intermediate
exl-id: 44b59f56-99be-41ae-af8d-76272bb94d18
source-git-commit: e7fdaa4b1d77afdae8004a88bbe41bbbe75a3f3c
workflow-type: tm+mt
source-wordcount: '411'
ht-degree: 0%

---

# Accedere all’integrazione di Adobe Campaign Standard con l’app self-service Microsoft Dynamics 365

Questa configurazione richiede l’utilizzo di un amministratore di Experience Cloud (EC) per l’organizzazione. Questi sono i passaggi iniziali necessari per consentire l’accesso all’interfaccia dell’applicazione di integrazione self-service. Una volta effettuato l’accesso allo strumento, configurerai le connessioni ai tuoi dati e il flusso di dati tra Adobe Campaign e Microsoft Dynamics 365.

>[!NOTE]
>
>Devi contattare il tuo rappresentante Adobe e fornire i nomi delle organizzazioni e delle istanze Adobe Campaign Standard. Verrà registrato un ticket per richiedere che l’app di integrazione sia abilitata per la tua organizzazione.

## Aggiungere un profilo di prodotto

In questa sezione viene illustrato come concedere l’accesso all’integrazione Adobe Campaign Standard con l’app self-service Microsoft Dynamics 365. Gli utenti che hanno accesso alla tua organizzazione in Adobe Experience Cloud non avranno accesso all’app self-service di integrazione, a meno che tu non segua i passaggi seguenti per concedere loro l’accesso.

>[!IMPORTANT]
>
> Questi passaggi richiedono **Amministratore** nell’Experience Cloud per la tua organizzazione.

1. Vai su https://experience.adobe.com/ e accedi a Adobe Experience Cloud.
1. Accedere al **Admin Console**.

   ![](assets/do-not-localize/d365-to-acs-access-3.png)

1. Fai clic su **[!UICONTROL Products]** per accedere alle soluzioni Experience Cloud.

   ![](assets/do-not-localize/d365-to-acs-access-6.png)


   >[!IMPORTANT]
   >
   >I passaggi rimanenti in questa sezione verranno eseguiti per ciascuna istanza di Campaign (sviluppo, testo, produzione).

1. Fai clic sulla prima istanza da configurare.

   ![](assets/do-not-localize/d365-to-acs-access-6.png)

   La pagina di istanza deve avere un aspetto simile al seguente:

   ![](assets/do-not-localize/d365-to-acs-access-8.png)

1. Fai clic sul pulsante **[!UICONTROL New Profile]** e aggiungi una nuova voce denominata: **Campaign Standard - integrazione D365/ACS - nome-istanza-prod**

   * Se viene visualizzata questa voce nell&#39;elenco, non è necessario procedere. Fai clic su **Adobe Campaign Standard** nel menu a sinistra e controlla le altre istanze di Campaign.

   * Assicurati di sostituire &quot;your-prod-instance-name&quot; con il nome effettivo dell&#39;istanza.

1. Puoi lasciare il **[!UICONTROL Permission Group]** con il valore predefinito.

1. Se le voci sono simili alle seguenti, fai clic sul pulsante **[!UICONTROL Done]** pulsante .

   ![](assets/do-not-localize/d365-to-acs-access-14.png)

   È stato aggiunto il nuovo profilo di prodotto.

   ![](assets/do-not-localize/d365-to-acs-access-15.png)

## Concedere l’accesso agli utenti {#add-users-to-profile}

Da **[!UICONTROL Products]**  , seleziona l’istanza Campaign e segui i passaggi seguenti:

1. Fai clic sul nuovo profilo creato in precedenza:  **Campaign Standard - integrazione D365/ACS - nome-istanza-prod**

   ![](assets/do-not-localize/d365-to-acs-access-15.png)

1. Fai clic sul pulsante **[!UICONTROL Developers]** scheda .

   ![](assets/do-not-localize/d365-to-acs-access-18.png)

1. Fai clic sul pulsante **[!UICONTROL Add Developer]** pulsante

1. Immetti il nome o l’indirizzo e-mail dell’utente che desideri aggiungere.  Seleziona il risultato che corrisponde all’utente.

   Se questa è la prima volta che l’utente viene aggiunto all’organizzazione, immetti i dettagli.

1. Fai clic su **[!UICONTROL Save]** per confermare.
