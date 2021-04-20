---
solution: Campaign Standard
product: campaign
title: Configurazione di Microsoft Dynamics 365 per l’integrazione con Campaign
description: Scopri come configurare Microsoft Dynamics 365 per l’integrazione con Campaign.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '917'
ht-degree: 1%

---


# Configurazione di Microsoft Dynamics 365 per l’integrazione con Adobe Campaign Standard

Scopri come configurare l’integrazione con Microsoft Dynamics 365 e attivare i dati CRM nelle comunicazioni cross-channel con Adobe Campaign Standard.

## Panoramica

La descrizione generale dell’integrazione di Adobe Campaign Standard con Microsoft Dynamics 365 è descritta in [questa pagina](../../integrating/using/d365-acs-get-started.md).

Per abilitare l’integrazione sarà necessario configurare più applicazioni. Tuttavia, questo articolo si concentrerà sui passaggi necessari in Dynamics 365.

## Prerequisiti

Prima di eseguire la configurazione di pre-integrazione in questo documento, si presume che tu abbia già effettuato il provisioning e che tu abbia accesso come amministratore all’istanza Microsoft Dynamics 365 della tua organizzazione.  In caso contrario, è necessario contattare il supporto clienti Microsoft per completare il provisioning di Dynamics 365.

Se stai configurando l’integrazione sia per gli ambienti di staging che per quelli di produzione, dovrai eseguire i passaggi seguenti sia per le istanze di staging che per quelle di produzione Dynamics 365. Alcune istruzioni di seguito variano leggermente a seconda che si stia configurando un’istanza di Stage o Production Dynamics 365 (ad esempio, per un’istanza di produzione, seleziona &quot;prod&quot; per `<stage or prod>`)

## Configurazione dell&#39;applicazione e delle autorizzazioni

Un token di accesso OAuth consente allo strumento di integrazione di eseguire l’autenticazione con l’istanza Microsoft Dynamics 365 tramite API web per pubblicare gli eventi di esperienza Campaign Standard nella visualizzazione timeline dell’interfaccia di Microsoft Dynamics 365.

I passaggi principali sono descritti nel seguente video:

>[!VIDEO](https://video.tv.adobe.com/v/27637)

Per generare il token di accesso OAuth, segui i passaggi descritti di seguito.

### Registra una nuova applicazione {#register-a-new-app}

1. Accedi a portal.azure.com tramite l’accesso dell’amministratore.

1. Fai clic su **[!UICONTROL Azure Active Directory]** nel menu a sinistra; quindi fai clic su **[!UICONTROL App registrations]** nel sottomenu visualizzato.

1. Fai clic su **[!UICONTROL New registration]** nella parte superiore dello schermo.

   ![](assets/do-not-localize/MSdynACSIntegration-7.png)

1. Compila la schermata di registrazione dell’app:

   * Nome: adobe campaign `<stage or prod>`
   * Tipo di account supportato: **[!UICONTROL Accounts in this organizational directory only]** (valore predefinito)

Per ulteriori informazioni sulla creazione di una nuova applicazione, consulta [questa sezione](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app).

>[!NOTE]
>
>La directory di Microsoft Azure assegna un ID applicazione (client) univoco all’app. Questo ID sarà necessario in seguito per configurare Dynamics 365 e per eseguire la configurazione dello strumento di integrazione.

### Genera segreto client {#generate-a-client-secret}

1. Dalla schermata di panoramica dell’app, fai clic su **[!UICONTROL Certificates and Secrets > New client secret]** nel sottomenu a sinistra

   ![](assets/do-not-localize/MSdynACSIntegration-8.png)

1. Immetti una descrizione, imposta la durata e fai clic su **[!UICONTROL OK]**.

È stato creato il segreto client. Mantenere temporaneamente il valore per il completamento della configurazione di pre-integrazione dello strumento di integrazione.

>[!CAUTION]
>
>Mantieni questo valore così come sarà necessario per completare la configurazione di pre-integrazione dello strumento di integrazione. Non può essere recuperato in seguito.


### Autorizzazioni di installazione

1. Da questa schermata o dalla schermata di panoramica dell’app, fai clic su **[!UICONTROL API permissions]** nel sottomenu a sinistra.  Dopo aver fatto clic su **[!UICONTROL Add a permission]**, è necessario selezionare **[!UICONTROL Dynamics CRM]** nel menu.

   ![](assets/do-not-localize/MSdynACSIntegration-9.png)

1. Quindi seleziona la casella **[!UICONTROL user_impersonation]** e fai clic sul pulsante **[!UICONTROL Add permissions]** .

   ![](assets/do-not-localize/MSdynACSIntegration-10.png)

Per ulteriori informazioni sulla configurazione delle autorizzazioni, consulta [questa sezione](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-configure-app-access-web-apis#add-permissions-to-access-web-apis).

### Creare l’utente dell’app

Questo nuovo utente è un utente generico. Sarà utilizzato dall&#39;applicazione: l’utente eseguirà qualsiasi modifica a Microsoft Dynamics 365 utilizzando l’API. Per crearlo, segui i passaggi seguenti:

1. Passa all’istanza di Dynamics 365 e accedi come amministratore.

1. Fai clic sull&#39;icona dell&#39;ingranaggio nell&#39;angolo in alto a destra e fai clic su **[!UICONTROL Advanced Settings]**. Nel banner superiore, fai clic sul menu a discesa accanto a **[!UICONTROL Settings]**, quindi fai clic su **[!UICONTROL Security > Users]**.

1. Fai clic sul menu a discesa per passare a **[!UICONTROL Application Users]**. Fai clic su **[!UICONTROL New]**.

1. Assicurati che l&#39;elenco a discesa accanto all&#39;icona utente indichi **[!UICONTROL USER:APPLICATION USER]**.

   Compila la schermata per il nuovo utente.  Suggerimenti sui parametri:

   * **[!UICONTROL User Name]** (e-mail): adobe_api_`<stage-or-prod>`@`<your-d365-hostname>`&quot; (esempio: adobe_api_stage@some-company.crm.dynamics.com)
   * **[!UICONTROL Application ID]**: ID dell’applicazione registrata in Azure AD (obbligatorio)
   * Puoi lasciare vuoti **[!UICONTROL Application ID URI]** e **[!UICONTROL Azure AD Object ID]**
   * **[!UICONTROL Full Name]**: API Adobe  `<stage or prod>`
   * **[!UICONTROL Email]**: come  **[!UICONTROL User Name]** (o e-mail dell’amministratore, se lo desideri)

   Per ulteriori informazioni sulla creazione di utenti dell&#39;app, consulta [questa sezione](https://docs.microsoft.com/en-gb/power-platform/admin/create-users-assign-online-security-roles#create-an-application-user).

1. Fai clic sull’icona utente e carica un’icona Adobe Campaign; questa è l’icona che verrà visualizzata nella vista Timeline quando i nuovi eventi di Adobe vengono visualizzati in Dynamics 365.

1. Apri l’elenco dei ruoli utente facendo clic su **[!UICONTROL MANAGE ROLES]** nella barra multifunzione superiore.

1. Scorri verso il basso e seleziona l’accesso **[!UICONTROL System administrator]** per l’utente corrente.

1. Fai clic su **[!UICONTROL OK]**.

### Ottieni l&#39;ID tenant {#get-the-tenant-id}

Per trovare l’ID tenant, segui le istruzioni [presenti in questa pagina](https://docs.microsoft.com/en-us/onedrive/find-your-office-365-tenant-id) .  Questo ID è necessario durante la configurazione di pre-integrazione nello strumento di integrazione.

## Installare Campaign Standard per Microsoft Dynamics 365 {#install-appsource-app}

Per integrare l’app Dynamics 365 nell’ambiente Campaign Standard, procedi come segue:

1. Passa al seguente collegamento: [https://appsource.microsoft.com/en-us/marketplace/apps](https://appsource.microsoft.com/en-us/marketplace/apps) e cerca _Adobe Campaign per Dynamics 365_ nella barra di ricerca.
In alternativa, puoi passare a questo [collegamento](https://appsource.microsoft.com/en-us/product/dynamics-365/adobecampaign.re4snj-a4n7-5t6y-a14br-d5d1b?flightCodes=adobesignhide&amp;tab=Overview).
1. Segui le istruzioni per installare l’app per la tua istanza Dynamics 365.
1. Una volta installato, accedi all’istanza di Dynamics 365 e accedi come amministratore.
1. Fai clic sull&#39;icona dell&#39;ingranaggio nell&#39;angolo in alto a destra e fai clic su **[!UICONTROL Advanced Settings]**. Nel banner superiore, fai clic sul menu a discesa accanto a **[!UICONTROL Settings]**, fai clic su **[!UICONTROL Processes]** in **[!UICONTROL Process Center]**.
1. Cerca l&#39;attività **[!UICONTROL Adobe Campaign Email Bounce]** e fai clic su di essa.
1. Nella scheda **[!UICONTROL Administration]** , modifica il proprietario nell’utente dell’applicazione API Adobe creato in precedenza facendo clic su **[!UICONTROL Actions]** dalla barra multifunzione superiore, quindi seleziona l’opzione **[!UICONTROL Assign to another User]**, seleziona **[!UICONTROL Adobe API application user]** dal menu a discesa da assegnare.
1. Riattiva il processo.
1. Eseguire la stessa operazione per l&#39;attività **[!UICONTROL Adobe Campaign Email Click]**.

>[!NOTE]
>
>Se desideri disattivare questi processi in qualsiasi momento, puoi farlo in questa schermata **[!UICONTROL Processes]**.

**Argomenti correlati**

* [Configurare Adobe IO per l’](../../integrating/using/d365-acs-configure-adobe-io.md) integrazione con Microsoft Dynamics 365 è il passaggio successivo nella configurazione dell’integrazione
* [Inizia a usare l’](../../integrating/using/d365-acs-self-service-app-quick-start-guide.md) app di integrazione self-service contenente l’elenco completo dei passaggi necessari per rendere l’integrazione operativa.
