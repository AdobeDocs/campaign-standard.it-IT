---
solution: Campaign Standard
product: campaign
title: Configurazione di Microsoft Dynamics 365 per l’integrazione con Campaign
description: Scopri come configurare Microsoft Dynamics 365 per l'integrazione con Campaign.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
translation-type: tm+mt
source-git-commit: 3ba3e0db816832ea57c124a9bea1fa82cf068859
workflow-type: tm+mt
source-wordcount: '911'
ht-degree: 1%

---


# Configurare Microsoft Dynamics 365 per l&#39;integrazione con  Adobe Campaign Standard

Scopri come configurare l&#39;integrazione con Microsoft Dynamics 365 e attivare i dati CRM nelle comunicazioni tra canali con  Adobe Campaign Standard.

## Panoramica

La descrizione generale dell&#39;integrazione  Adobe Campaign Standard con Microsoft Dynamics 365 è descritta in [questa pagina](../../integrating/using/d365-acs-get-started.md).

Per abilitare l&#39;integrazione sarà necessario configurare più applicazioni. Tuttavia, questo articolo sarà incentrato sui passaggi richiesti in Dynamics 365.

## Prerequisiti

Prima di eseguire l&#39;impostazione di pre-integrazione in questo documento, si suppone che sia già stato eseguito il provisioning e che l&#39;utente abbia accesso amministratore all&#39;istanza di Microsoft Dynamics 365 dell&#39;organizzazione.  Se ciò non è avvenuto, per completare il provisioning di Dynamics 365 dovrete contattare il supporto clienti Microsoft.

Se si sta configurando l&#39;integrazione sia per gli ambienti di staging che per quelli di produzione, sarà necessario eseguire i passaggi indicati di seguito per le istanze di staging e di produzione Dynamics 365. Alcune istruzioni riportate di seguito variano leggermente a seconda se state configurando un&#39;istanza di produzione o di uno stadio Dynamics 365 (ad esempio, per l&#39;istanza di produzione, selezionate &quot;prod&quot; per `<stage or prod>`)

## Impostazione dell’applicazione e delle autorizzazioni

Un token di accesso OAuth consente allo strumento di integrazione di autenticarsi con l&#39;istanza di Microsoft Dynamics 365 tramite API Web per pubblicare gli eventi di esperienza Campaign Standard nella visualizzazione della cronologia dell&#39;interfaccia di Microsoft Dynamics 365.

I passaggi principali sono descritti nel seguente video:

>[!VIDEO](https://video.tv.adobe.com/v/27637)

Per generare il token di accesso OAuth, segui i passaggi descritti di seguito.

### Registra una nuova applicazione {#register-a-new-app}

1. Con l’accesso dell’amministratore, accedi a Portal.azure.com.

1. Fare clic su **[!UICONTROL Azure Active Directory]** nel menu a sinistra; quindi fare clic su **[!UICONTROL App registrations]** nel sottomenu visualizzato.

1. Fare clic su **[!UICONTROL New registration]** nella parte superiore dello schermo.

   ![](assets/do-not-localize/MSdynACSIntegration-7.png)

1. Compilate la schermata di registrazione dell&#39;app:

   * Nome: adobe campaign `<stage or prod>`
   * Tipo di account supportato: **[!UICONTROL Accounts in this organizational directory only]** (valore predefinito)

Per ulteriori informazioni sulla creazione di una nuova applicazione, consultare [questa sezione](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app).

>[!NOTE]
>
>La directory di Microsoft Azure assegna un ID applicazione (client) univoco all&#39;app. Questo ID sarà necessario in seguito per configurare Dynamics 365 e per eseguire la configurazione dello strumento di integrazione.

### Genera segreto client {#generate-a-client-secret}

1. Dalla schermata della panoramica dell&#39;app, nel sottomenu a sinistra, fai clic su **[!UICONTROL Certificates and Secrets > New client secret]**

   ![](assets/do-not-localize/MSdynACSIntegration-8.png)

1. Inserite una descrizione, impostate la durata e fate clic su **[!UICONTROL OK]**.

È stato creato il segreto cliente. Mantenete temporaneamente il valore per il completamento della configurazione di pre-integrazione dello strumento di integrazione.

>[!CAUTION]
>
>Mantenete questo valore così come sarà necessario per completare la configurazione di pre-integrazione dello strumento di integrazione. Non può essere recuperato in seguito.


### Autorizzazioni di configurazione

1. Da questa schermata o dalla schermata di panoramica dell&#39;app, fate clic su **[!UICONTROL API permissions]** nel sottomenu a sinistra.  Dopo aver fatto clic su **[!UICONTROL Add a permission]**, è necessario selezionare **[!UICONTROL Dynamics CRM]** nel menu.

   ![](assets/do-not-localize/MSdynACSIntegration-9.png)

1. Selezionare la casella **[!UICONTROL user_impersonation]** e fare clic sul pulsante **[!UICONTROL Add permissions]**.

   ![](assets/do-not-localize/MSdynACSIntegration-10.png)

Per ulteriori informazioni sulla configurazione delle autorizzazioni, consultare [questa sezione](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-configure-app-access-web-apis#add-permissions-to-access-web-apis).

### Creare l&#39;utente dell&#39;app

Questo nuovo utente è un utente generico. Sarà utilizzato dall&#39;applicazione: qualsiasi modifica a Microsoft Dynamics 365 tramite l&#39;API verrà eseguita da questo utente. Per crearlo, attenetevi alla procedura seguente:

1. Passa all&#39;istanza di Dynamics 365 ed effettua l&#39;accesso come amministratore.

1. Fate clic sull&#39;icona dell&#39;ingranaggio nell&#39;angolo superiore destro e fate clic su **[!UICONTROL Advanced Settings]**. Nel banner superiore, fate clic sull&#39;elenco a discesa accanto a **[!UICONTROL Settings]**, fate clic su **[!UICONTROL Security > Users]**.

1. Fare clic sul menu a discesa fino a **[!UICONTROL Application Users]**. Fai clic su **[!UICONTROL New]**.

1. Accertati che l&#39;icona dell&#39;utente sia a discesa accanto a **[!UICONTROL USER:APPLICATION USER]**.

   Compilate lo schermo per il nuovo utente.  Suggerimenti sui parametri:

   * **[!UICONTROL User Name]** (e-mail): adobe_api_`<stage-or-prod>`@`<your-d365-hostname>`&quot; (ad esempio, adobe_api_stage@some-company.crm.dynamics.com)
   * **[!UICONTROL Application ID]**: ID dell&#39;applicazione registrata in Azure AD (obbligatorio)
   * È possibile lasciare vuoti **[!UICONTROL Application ID URI]** e **[!UICONTROL Azure AD Object ID]**
   * **[!UICONTROL Full Name]**: API Adobe   `<stage or prod>`
   * **[!UICONTROL Email]**: come  **[!UICONTROL User Name]** (o e-mail dell&#39;amministratore, se lo desiderate)

   Per ulteriori informazioni sulla creazione dell&#39;app da parte degli utenti, consultare [questa sezione](https://docs.microsoft.com/en-gb/power-platform/admin/create-users-assign-online-security-roles#create-an-application-user).

1. Fate clic sull’icona dell’utente e caricate un’icona Adobe Campaign ; si tratta dell&#39;icona che verrà visualizzata nella visualizzazione Timeline quando nuovi eventi di Adobe  vengono visualizzati in Dynamics 365.

1. Aprite l&#39;elenco dei ruoli utente facendo clic su **[!UICONTROL MANAGE ROLES]** nella barra multifunzione superiore.

1. Scorrete verso il basso e selezionate **[!UICONTROL System administrator]** l&#39;accesso per l&#39;utente.

1. Fai clic su **[!UICONTROL OK]**.

### Ottenere l&#39;ID tenant {#get-the-tenant-id}

Seguite le istruzioni [riportate in questa pagina](https://docs.microsoft.com/en-us/onedrive/find-your-office-365-tenant-id) per trovare l&#39;ID tenant.  Questo ID sarà necessario durante la configurazione precedente all’integrazione nello strumento di integrazione.

## Installare Campaign Standard per Microsoft Dynamics 365 {#install-appsource-app}

Per integrare l&#39;app Dynamics 365 nell&#39;ambiente Campaign Standard, effettua i seguenti passaggi:

1. Passa al seguente collegamento: [https://appsource.microsoft.com/en-us/marketplace/apps](https://appsource.microsoft.com/en-us/marketplace/apps) e cercare _Adobe Campaign per Dynamics 365_ nella barra di ricerca.
In alternativa, puoi passare a questo [collegamento](https://appsource.microsoft.com/en-us/product/dynamics-365/adobecampaign.re4snj-a4n7-5t6y-a14br-d5d1b?flightCodes=adobesignhide&amp;tab=Overview).
1. Seguite le istruzioni per installare l&#39;app per l&#39;istanza Dynamics 365.
1. Una volta installato, accedi all&#39;istanza di Dynamics 365 ed effettua l&#39;accesso come amministratore.
1. Fate clic sull&#39;icona dell&#39;ingranaggio nell&#39;angolo superiore destro e fate clic su **[!UICONTROL Advanced Settings]**. Nel banner superiore, fare clic sul menu a discesa accanto a **[!UICONTROL Settings]**, fare clic su **[!UICONTROL Processes]** in **[!UICONTROL Process Center]**.
1. Cercare l&#39;attività **[!UICONTROL Adobe Campaign Email Bounce]** e fare clic su di essa.
1. Nella scheda **[!UICONTROL Administration]**, cambiare il proprietario nell&#39;utente dell&#39;applicazione API del Adobe  creato in precedenza facendo clic su **[!UICONTROL Actions]** dalla barra multifunzione superiore, quindi selezionare l&#39;opzione **[!UICONTROL Assign to another User]**, selezionare **[!UICONTROL Adobe API application user]** dal menu a discesa da assegnare.
1. Riattivate il processo.
1. Esegue le stesse operazioni per l&#39;attività **[!UICONTROL Adobe Campaign Email Click]**.

>[!NOTE]
>
>Se in qualsiasi momento desiderate disattivare tali processi, potete farlo in questa schermata **[!UICONTROL Processes]**.

**Argomenti correlati**

* [Configurare  Adobe I/O per l&#39;](../../integrating/using/d365-acs-configure-adobe-io.md) integrazione con Microsoft Dynamics 365 è il passaggio successivo per l&#39;impostazione dell&#39;integrazione
* [Inizia con l’](../../integrating/using/d365-acs-self-service-app-quick-start-guide.md) app di integrazione self-service contenente l’elenco completo dei passaggi necessari per rendere l’integrazione operativa.