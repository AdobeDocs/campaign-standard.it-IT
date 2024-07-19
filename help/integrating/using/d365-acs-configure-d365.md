---
title: Configurare Microsoft Dynamics 365 per l’integrazione con Campaign
description: Scopri come configurare Microsoft Dynamics 365 per l’integrazione con Campaign.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
exl-id: 57e85f8e-65b4-44ea-98e6-0c555acf6dee
source-git-commit: 6947d163119dd6fc5966fdc723530b02bdd4a469
workflow-type: tm+mt
source-wordcount: '879'
ht-degree: 0%

---

# Configurare Microsoft Dynamics 365 per l’integrazione con Adobe Campaign Standard

Scopri come configurare l’integrazione di Microsoft Dynamics 365 e attivare i dati CRM sulla comunicazione cross-channel con Adobe Campaign Standard.

## Panoramica

La descrizione generale dell&#39;integrazione di Adobe Campaign Standard con Microsoft Dynamics 365 è descritta in [questa pagina](../../integrating/using/d365-acs-get-started.md).

Per abilitare l’integrazione è necessario configurare più applicazioni. Tuttavia, questo articolo si concentrerà sui passaggi necessari in Dynamics 365.

## Prerequisiti

Prima di eseguire la configurazione della preintegrazione in questo documento, si presume che sia già stato eseguito il provisioning e che si disponga dell’accesso amministratore all’istanza Microsoft Dynamics 365 della tua organizzazione.  In caso contrario, dovrai contattare l’Assistenza clienti di Microsoft per completare il provisioning di Dynamics 365.

Se configuri l’integrazione sia per gli ambienti di staging che per quelli di produzione, dovrai eseguire i passaggi seguenti sia per le istanze di staging che per quelle di produzione Dynamics 365. Alcune istruzioni di seguito variano leggermente a seconda che si stia configurando un&#39;istanza di Stage o Production Dynamics 365 (ad esempio, per l&#39;istanza di produzione, selezionare &quot;prod&quot; per `<stage or prod>`)

## Configurazione dell’applicazione e delle autorizzazioni

Un token di accesso OAuth consente allo strumento di integrazione di eseguire l’autenticazione con l’istanza di Microsoft Dynamics 365 tramite API web per pubblicare gli eventi di esperienza di Campaign Standard nella visualizzazione timeline dell’interfaccia di Microsoft Dynamics 365.

I passaggi principali sono descritti nel seguente video:

>[!VIDEO](https://video.tv.adobe.com/v/27637)

Per generare il token di accesso OAuth, segui i passaggi descritti di seguito.

### Registra una nuova applicazione {#register-a-new-app}

1. Accedi a [portal.azure.com](https://portal.azure.com){target="_blank"} con il tuo account di accesso amministratore.

1. Fare clic su **[!UICONTROL Azure Active Directory]** nel menu a sinistra, quindi fare clic su **[!UICONTROL App registrations]** nel sottomenu visualizzato.

1. Fai clic su **[!UICONTROL New registration]** nella parte superiore della schermata.

1. Compila la schermata di registrazione dell’app:

   * Nome: campagna Adobe `<stage or prod>`
   * Tipo di account supportato: **[!UICONTROL Accounts in this organizational directory only]** (valore predefinito)

Per ulteriori informazioni sulla creazione di una nuova applicazione, consultare [questa sezione](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app){target="_blank"}.

>[!NOTE]
>
>La directory di Microsoft Azure assegna un ID applicazione (client) univoco all&#39;app. Questo ID sarà necessario successivamente nella configurazione di Dynamics 365, nonché quando esegui la configurazione dello strumento di integrazione.

### Genera segreto client {#generate-a-client-secret}

1. Dalla schermata di panoramica dell&#39;app, nel sottomenu a sinistra, fai clic su **[!UICONTROL Certificates and Secrets > New client secret]**

1. Immettere una descrizione, impostare la durata e fare clic su **[!UICONTROL OK]**.

Il segreto client è stato creato. Accettate temporaneamente il valore per completare la configurazione di pre-integrazione dello strumento di integrazione.

>[!CAUTION]
>
>Mantieni questo valore in base alle tue esigenze per completare la configurazione di pre-integrazione dello strumento di integrazione. Non può essere recuperato in seguito.


### Autorizzazioni di configurazione

1. Da questa schermata o dalla schermata di panoramica dell&#39;app, fai clic su **[!UICONTROL API permissions]** nel sottomenu a sinistra.  Dopo aver fatto clic su **[!UICONTROL Add a permission]**, devi selezionare **[!UICONTROL Dynamics CRM]** nel menu.

1. Quindi selezionare la casella per **[!UICONTROL user_impersonation]** e fare clic sul pulsante **[!UICONTROL Add permissions]**.

Per ulteriori informazioni sulla configurazione delle autorizzazioni, consulta [questa sezione](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-configure-app-access-web-apis#add-permissions-to-access-web-apis){target="_blank"}.

### Creare l’utente dell’app

Questo nuovo utente è generico. Verrà utilizzato dall’applicazione: qualsiasi modifica a Microsoft Dynamics 365 tramite l’API verrà eseguita da questo utente. Per crearlo, effettua le seguenti operazioni:

1. Passa all’istanza di Dynamics 365 e accedi come Amministratore.

1. Fai clic sull&#39;icona dell&#39;ingranaggio nell&#39;angolo superiore destro e fai clic su **[!UICONTROL Advanced Settings]**. Nel banner superiore, fai clic sul menu a discesa accanto a **[!UICONTROL Settings]**, quindi su **[!UICONTROL Security > Users]**.

1. Fare clic sul menu a discesa per passare a **[!UICONTROL Application Users]**. Fai clic su **[!UICONTROL New]**.

1. Assicurarsi che il menu a discesa accanto all&#39;icona utente indichi **[!UICONTROL USER:APPLICATION USER]**.

   Compila la schermata per il nuovo utente.  Suggerimenti sui parametri:

   * **[!UICONTROL User Name]** (e-mail): adobe_api_`<stage-or-prod>`@`<your-d365-hostname>`&quot; (esempio: adobe_api_stage@some-company.crm.dynamics.com)
   * **[!UICONTROL Application ID]**: ID dell&#39;applicazione registrata in Azure AD (obbligatorio)
   * Puoi lasciare vuoti **[!UICONTROL Application ID URI]** e **[!UICONTROL Azure AD Object ID]**
   * **[!UICONTROL Full Name]**: API Adobe `<stage or prod>`
   * **[!UICONTROL Email]**: uguale a **[!UICONTROL User Name]** (o indirizzo e-mail dell&#39;amministratore, se lo si desidera)

   Per ulteriori informazioni sulla creazione di utenti di app, consulta [questa sezione](https://docs.microsoft.com/en-gb/power-platform/admin/create-users-assign-online-security-roles#create-an-application-user){target="_blank"}.

1. Fai clic sull’icona utente e carica un’icona di Adobe Campaign; questa è l’icona che verrà visualizzata nella vista Timeline quando vengono visualizzati nuovi eventi di Adobe in Dynamics 365.

1. Aprire l&#39;elenco dei ruoli utente facendo clic su **[!UICONTROL MANAGE ROLES]** nella barra multifunzione superiore.

1. Scorri verso il basso e seleziona l&#39;accesso **[!UICONTROL System administrator]** per questo utente.

1. Fai clic su **[!UICONTROL OK]**.

### Ottieni l’ID tenant {#get-the-tenant-id}

Segui le istruzioni [in questa pagina](https://docs.microsoft.com/en-us/onedrive/find-your-office-365-tenant-id) per trovare il tuo ID tenant.  Questo ID è necessario durante la configurazione di pre-integrazione nello strumento di integrazione.

## Installare Campaign Standard per Microsoft Dynamics 365 {#install-appsource-app}

Per integrare l’app Dynamics 365 nell’ambiente Campaign Standard, effettua le seguenti operazioni:

1. Passa a [Microsoft Business Apps](https://appsource.microsoft.com/en-us/marketplace/apps) e cerca Adobe Campaign Standard_ nella barra di ricerca.
In alternativa, puoi passare a questo [collegamento](https://appsource.microsoft.com/en-us/product/dynamics-365/adobe.adobe_campaign_d365?tab=Overview){target="_blank"}.
1. Segui le istruzioni per installare l’app per l’istanza di Dynamics 365.
1. Una volta installata, accedi all’istanza di Dynamics 365 e accedi come amministratore.
1. Fai clic sull&#39;icona dell&#39;ingranaggio nell&#39;angolo superiore destro e fai clic su **[!UICONTROL Advanced Settings]**. Nel banner superiore, fai clic sul menu a discesa accanto a **[!UICONTROL Settings]**, quindi su **[!UICONTROL Processes]** in **[!UICONTROL Process Center]**.
1. Cercare l&#39;attività **[!UICONTROL Adobe Campaign Email Bounce]** e fare clic su di essa.
1. Nella scheda **[!UICONTROL Administration]**, cambia il proprietario con l&#39;utente dell&#39;applicazione API Adobe creato in precedenza facendo clic su **[!UICONTROL Actions]** nella barra multifunzione superiore, quindi seleziona l&#39;opzione **[!UICONTROL Assign to another User]**, seleziona **[!UICONTROL Adobe API application user]** dal menu a discesa da assegnare.
1. Riattiva il processo.
1. Eseguire la stessa operazione per l&#39;attività **[!UICONTROL Adobe Campaign Email Click]**.

>[!NOTE]
>
>Se in qualsiasi momento si desidera disattivare questi processi, è possibile farlo in questa schermata **[!UICONTROL Processes]**.

**Argomenti correlati**

* [Configurare Adobe Developer per l&#39;integrazione con Microsoft Dynamics 365](../../integrating/using/d365-acs-configure-adobe-io.md) è il passaggio successivo per la configurazione dell&#39;integrazione
* [Introduzione all&#39;applicazione di integrazione self-service](../../integrating/using/d365-acs-self-service-app-quick-start-guide.md) contiene l&#39;elenco completo dei passaggi necessari per rendere operativa l&#39;integrazione.
