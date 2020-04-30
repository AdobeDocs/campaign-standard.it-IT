---
title: Configurazione di Microsoft Dynamics 365 per l’integrazione con Campaign
description: Scopri come configurare Microsoft Dynamics 365 per l'integrazione con Campaign.
page-status-flag: never-activated
uuid: effa1028-66b2-4bef-b5e4-7319dbb23d5d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics
discoiquuid: eb3639f5-7246-46c4-8ddb-da9413b40c32
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 4e05dafb087c43a13c60d6bb2f54d0e44455ea8d

---


# Configurazione di Microsoft Dynamics 365 per l’integrazione con Campaign

Scopri come configurare l&#39;integrazione con Microsoft Dynamics 365 e attivare i dati CRM nelle comunicazioni tra canali con Adobe Campaign Standard.

## Panoramica

L&#39;integrazione Adobe Campaign Standard - Microsoft Dynamics 365 è descritta in [questa pagina](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md).

Tre sistemi che devono essere predisposti per questa integrazione:

1. Adobe Campaign Standard - [Ulteriori informazioni](../../integrating/using/configure-adobe-io-for-ms-dynamic.md)
1. Microsoft Dynamics 365 per le vendite - Descrizione riportata di seguito
1. Unifi - [Ulteriori informazioni](../../integrating/using/configure-unifi-for-microsoft-dynamics-365-integration.md)

Una volta effettuato il provisioning, questi sistemi devono essere configurati da un amministratore.

Questo articolo evidenzia i passaggi, dal lato Microsoft Dynamics 365, necessari durante il post-provisioning per consentire al cliente di utilizzare l&#39;integrazione Adobe Campaign Standard - Microsoft Dynamics 365.

## Prerequisiti

Prima di eseguire i passaggi successivi al provisioning in questo documento, si suppone che sia già stato eseguito il provisioning e che l&#39;utente abbia accesso amministratore all&#39;istanza di Microsoft Dynamics 365 dell&#39;organizzazione.  Se ciò non è avvenuto, per completare il provisioning di Dynamics 365 dovrete contattare il supporto clienti Microsoft.

## Impostazione dell’applicazione e delle autorizzazioni

Un token di accesso OAuth consente ad Unifi di autenticarsi con l&#39;istanza di Microsoft Dynamics 365 tramite API Web per pubblicare gli eventi esperienza di Campaign Standard nella visualizzazione della cronologia dell&#39;interfaccia di Microsoft Dynamics 365.

I passaggi principali sono descritti nel seguente video:

>[!VIDEO](https://video.tv.adobe.com/v/27637)

Per generare il token di accesso OAuth, segui i passaggi descritti di seguito.

### Registrazione di una nuova applicazione

1. Con l’accesso dell’amministratore, accedi a Portal.azure.com.

1. Fare clic su **[!UICONTROL Azure Active Directory]** nel menu a sinistra; quindi fate clic **[!UICONTROL App registrations]** sul sottomenu visualizzato.

1. Fate clic **[!UICONTROL New registration]** nella parte superiore dello schermo.

   ![](assets/do-not-localize/MSdynACSIntegration-7.png)

1. Compilate la schermata di registrazione dell&#39;app:

   * Nome: adobe campaign
   * Tipo di account supportato: **[!UICONTROL Accounts in this organizational directory only]** (valore predefinito)

Per ulteriori informazioni sulla creazione di una nuova applicazione, consultare [questa sezione](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app).

>[!NOTE]
>
>Azure AD assegna un ID applicazione (client) univoco all&#39;app. Questo ID sarà necessario in seguito per configurare Dynamics 365, nonché per eseguire i passaggi di Unifi Post Provisioning.

### Genera segreto cliente

1. Dalla schermata della panoramica dell&#39;app, nel sottomenu a sinistra, fai clic su **[!UICONTROL Certificates and Secrets > New client secret]**

   ![](assets/do-not-localize/MSdynACSIntegration-8.png)

1. Inserite una descrizione, impostate la durata e fate clic su **[!UICONTROL OK]**.

È stato creato il segreto cliente.  Mantenete il valore per il completamento dei passaggi di post-provisioning Unifi.

>[!CAUTION]
>
>Mantenete questo valore così come sarà necessario per completare il passaggio di post-provisioning Unifi. Non può essere recuperato in seguito.

Per ulteriori informazioni sulla generazione di un segreto client, consultate questa sezione.

### Autorizzazioni di configurazione

1. Da questa schermata o dalla schermata della panoramica dell&#39;app, fate clic su **[!UICONTROL API permissions]** nel sottomenu a sinistra.  Dopo aver fatto clic **[!UICONTROL Add a permission]**, è necessario selezionare **[!UICONTROL Dynamics CRM]** il menu.

   ![](assets/do-not-localize/MSdynACSIntegration-9.png)

1. Quindi selezionate la casella per **[!UICONTROL user_impersonation]**, quindi fate clic sul **[!UICONTROL Add permissions]** pulsante.

   ![](assets/do-not-localize/MSdynACSIntegration-10.png)

Per ulteriori informazioni sulla configurazione delle autorizzazioni, consultate [questa sezione](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-configure-app-access-web-apis#add-permissions-to-access-web-apis).

### Creare l&#39;utente dell&#39;app

Questo nuovo utente è un utente generico. Sarà utilizzato dall&#39;applicazione: qualsiasi modifica a Microsoft Dynamics 365 tramite l&#39;API verrà eseguita da questo utente. Per crearlo, attenetevi alla procedura seguente:

1. Passa all&#39;istanza di Dynamics 365 ed effettua l&#39;accesso come amministratore.

1. Fate clic sull&#39;icona dell&#39;ingranaggio nell&#39;angolo superiore destro e fate clic su **[!UICONTROL Advanced Settings]**. Nel banner superiore, fate clic sul menu a discesa accanto a **[!UICONTROL Settings]**, quindi fate clic su **[!UICONTROL Security > Users]**.

1. Fare clic sul menu a discesa fino a **[!UICONTROL Application Users]**. Clic **[!UICONTROL New]**.

1. Accertati che sia disponibile un elenco a discesa accanto all’icona dell’utente **[!UICONTROL USER:APPLICATION USER]**.

   Compilate lo schermo per il nuovo utente.  Suggerimenti sui parametri:

   * **[!UICONTROL User Name]** (e-mail): adobeapi@`<hostname>`, dove `<hostname>` è il nome host dell&#39;istanza Dynamics 365
   * **[!UICONTROL Application ID]**: ID dell&#39;applicazione registrata in Azure AD (obbligatorio)
   * Potete lasciare vuoto **[!UICONTROL Application ID URI]** e **[!UICONTROL Azure AD Object ID]**
   * **[!UICONTROL Full Name]**: API Adobe
   * **[!UICONTROL Email]**: come **[!UICONTROL User Name]** (o e-mail dell&#39;amministratore, se lo desiderate)
   Per ulteriori informazioni sulla creazione dell&#39;utente dell&#39;app, consulta [questa sezione](https://docs.microsoft.com/en-gb/power-platform/admin/create-users-assign-online-security-roles#create-an-application-user).

1. Fate clic sull&#39;icona dell&#39;utente e caricate un&#39;icona di Adobe Campaign; questa è l&#39;icona che verrà visualizzata nella visualizzazione Timeline quando nuovi eventi Adobe verranno visualizzati in Dynamics 365.

<!-- ***getfile*** adobe campaign logo-->

1. Aprite l’elenco dei ruoli utente facendo clic **[!UICONTROL MANAGE ROLES]** sulla barra multifunzione superiore.

1. Scorrete verso il basso e selezionate **[!UICONTROL System administrator]** l&#39;accesso per l&#39;utente corrente.

1. Clic **[!UICONTROL OK]**.

### Ottieni ID tenant

Seguite le istruzioni riportate nel seguente collegamento per trovare l&#39;ID tenant.  Questo ID sarà necessario durante il post-provisioning in Unifi: [https://docs.microsoft.com/en-us/onedrive/find-your-office-365-tenant-id](https://docs.microsoft.com/en-us/onedrive/find-your-office-365-tenant-id).

## Installa Campaign Standard per Microsoft Dynamics 365

Per integrare l&#39;app Dynamics 365 nell&#39;ambiente Campaign Standard, procedi come segue:

1. Passa al seguente collegamento: [https://appsource.microsoft.com/en-us/marketplace/apps](https://appsource.microsoft.com/en-us/marketplace/apps) e cerca _Adobe Campaign for Dynamics 365_ nella barra di ricerca.
In alternativa, puoi accedere a questo [collegamento](https://appsource.microsoft.com/en-us/product/dynamics-365/adobecampaign.re4snj-a4n7-5t6y-a14br-d5d1b?flightCodes=adobesignhide&amp;tab=Overview).
1. Seguite le istruzioni per installare l&#39;app per l&#39;istanza Dynamics 365.
1. Una volta installato, accedi all&#39;istanza di Dynamics 365 ed effettua l&#39;accesso come amministratore.
1. Fate clic sull&#39;icona dell&#39;ingranaggio nell&#39;angolo superiore destro e fate clic su **[!UICONTROL Advanced Settings]**. Nel banner superiore, fate clic sul menu a discesa accanto a **[!UICONTROL Settings]**, quindi fate clic su **[!UICONTROL Processes]** sotto **[!UICONTROL Process Center]**.
1. Cercare **[!UICONTROL Adobe Campaign Email Bounce]** attività e fare clic su di essa.
1. Nella **[!UICONTROL Administration]** scheda, imposta il proprietario sull&#39;utente dell&#39;applicazione Adobe API creato in precedenza facendo clic **[!UICONTROL Actions]** dalla barra multifunzione superiore, quindi seleziona **[!UICONTROL Assign to another User]** l&#39;opzione, seleziona **[!UICONTROL Adobe API application user]** dal menu a discesa da assegnare.
1. Riattivate il processo.
1. Esegue le stesse operazioni per l&#39; **[!UICONTROL Adobe Campaign Email Click]** attività.

>[!NOTE]
>
>Se in qualsiasi momento desiderate disattivare tali processi, potete farlo in questa **[!UICONTROL Processes]** schermata.

Al termine di questa configurazione, puoi configurare la configurazione Unifi. Per ulteriori informazioni, consultare questa [pagina](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md).

**Argomenti correlati**

* [Campaign Standard - Integrazione con Microsoft Dynamics 365](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md)
* [Configurazione di Adobe IO per l’integrazione con Microsoft Dynamics 365](../../integrating/using/configure-adobe-io-for-ms-dynamic.md)
* [Configurare Unifi per l&#39;integrazione di Campaign - Microsoft Dynamics 365](../../integrating/using/configure-unifi-for-microsoft-dynamics-365-integration.md)
