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

La descrizione generale dell’integrazione di Adobe Campaign Standard con Microsoft Dynamics 365 è descritta in [questa pagina](../../integrating/using/d365-acs-get-started.md).

Per abilitare l’integrazione è necessario configurare più applicazioni. Tuttavia, questo articolo si concentrerà sui passaggi necessari in Dynamics 365.

## Prerequisiti

Prima di eseguire la configurazione della preintegrazione in questo documento, si presume che sia già stato eseguito il provisioning e che si disponga dell’accesso amministratore all’istanza Microsoft Dynamics 365 della tua organizzazione.  In caso contrario, dovrai contattare l’Assistenza clienti di Microsoft per completare il provisioning di Dynamics 365.

Se configuri l’integrazione sia per gli ambienti di staging che per quelli di produzione, dovrai eseguire i passaggi seguenti sia per le istanze di staging che per quelle di produzione Dynamics 365. Alcune istruzioni di seguito variano leggermente a seconda che si stia configurando un’istanza di Stage o Production Dynamics 365 (ad esempio, per l’istanza di produzione, seleziona &quot;prod&quot; per `<stage or prod>`)

## Configurazione dell’applicazione e delle autorizzazioni

Un token di accesso OAuth consente allo strumento di integrazione di eseguire l’autenticazione con l’istanza di Microsoft Dynamics 365 tramite API web per pubblicare gli eventi di esperienza di Campaign Standard nella visualizzazione timeline dell’interfaccia di Microsoft Dynamics 365.

I passaggi principali sono descritti nel seguente video:

>[!VIDEO](https://video.tv.adobe.com/v/27637)

Per generare il token di accesso OAuth, segui i passaggi descritti di seguito.

### Registra una nuova applicazione {#register-a-new-app}

1. Con il login amministratore, accedi a [portal.azure.com](https://portal.azure.com){target="_blank"}.

1. Fai clic su **[!UICONTROL Azure Active Directory]** nel menu a sinistra, quindi fare clic su **[!UICONTROL App registrations]** nel sottomenu visualizzato.

1. Clic **[!UICONTROL New registration]** nella parte superiore dello schermo.

1. Compila la schermata di registrazione dell’app:

   * Nome: adobe campaign `<stage or prod>`
   * Tipo di account supportato: **[!UICONTROL Accounts in this organizational directory only]** (valore predefinito)

Per ulteriori informazioni sulla creazione di una nuova applicazione, consulta [questa sezione](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app){target="_blank"}.

>[!NOTE]
>
>La directory di Microsoft Azure assegna un ID applicazione (client) univoco all&#39;app. Questo ID sarà necessario successivamente nella configurazione di Dynamics 365, nonché quando esegui la configurazione dello strumento di integrazione.

### Genera segreto client {#generate-a-client-secret}

1. Dalla schermata di panoramica dell’app, nel sottomenu a sinistra, fai clic su **[!UICONTROL Certificates and Secrets > New client secret]**

1. Inserisci una descrizione, imposta la durata e fai clic su **[!UICONTROL OK]**.

Il segreto client è stato creato. Accettate temporaneamente il valore per completare la configurazione di pre-integrazione dello strumento di integrazione.

>[!CAUTION]
>
>Mantieni questo valore in base alle tue esigenze per completare la configurazione di pre-integrazione dello strumento di integrazione. Non può essere recuperato in seguito.


### Autorizzazioni di configurazione

1. Da questa schermata o dalla schermata di panoramica dell’app, fai clic su **[!UICONTROL API permissions]** nel sottomenu a sinistra.  Dopo aver fatto clic su **[!UICONTROL Add a permission]**, è necessario selezionare **[!UICONTROL Dynamics CRM]** nel menu.

1. Quindi seleziona la casella per **[!UICONTROL user_impersonation]**, quindi fare clic su **[!UICONTROL Add permissions]** pulsante.

Per ulteriori informazioni sulla configurazione delle autorizzazioni, consulta [questa sezione](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-configure-app-access-web-apis#add-permissions-to-access-web-apis){target="_blank"}.

### Creare l’utente dell’app

Questo nuovo utente è generico. Verrà utilizzato dall’applicazione: qualsiasi modifica a Microsoft Dynamics 365 tramite l’API verrà eseguita da questo utente. Per crearlo, effettua le seguenti operazioni:

1. Passa all’istanza di Dynamics 365 e accedi come Amministratore.

1. Fai clic sull’icona dell’ingranaggio nell’angolo superiore destro e fai clic su **[!UICONTROL Advanced Settings]**. Nel banner superiore, fai clic sul menu a discesa accanto a **[!UICONTROL Settings]**, fai clic su **[!UICONTROL Security > Users]**.

1. Fai clic sul menu a discesa per passare a **[!UICONTROL Application Users]**. Fai clic su **[!UICONTROL New]**.

1. Assicurati che il menu a discesa accanto all’icona dell’utente indichi **[!UICONTROL USER:APPLICATION USER]**.

   Compila la schermata per il nuovo utente.  Suggerimenti sui parametri:

   * **[!UICONTROL User Name]** (e-mail): adobe_api_`<stage-or-prod>`@`<your-d365-hostname>`&quot; (ad esempio, adobe_api_stage@some-company.crm.dynamics.com)
   * **[!UICONTROL Application ID]**: ID dell&#39;applicazione registrata in Azure AD (obbligatorio)
   * Puoi lasciare vuoto il campo **[!UICONTROL Application ID URI]** e **[!UICONTROL Azure AD Object ID]**
   * **[!UICONTROL Full Name]**: API ADOBE `<stage or prod>`
   * **[!UICONTROL Email]**: uguale a **[!UICONTROL User Name]** (o e-mail dell’amministratore, se lo desideri)

   Per ulteriori informazioni sulla creazione di utenti di app, consulta [questa sezione](https://docs.microsoft.com/en-gb/power-platform/admin/create-users-assign-online-security-roles#create-an-application-user){target="_blank"}.

1. Fai clic sull’icona utente e carica un’icona di Adobe Campaign; questa è l’icona che verrà visualizzata nella vista Timeline quando vengono visualizzati nuovi eventi di Adobe in Dynamics 365.

1. Aprire l&#39;elenco dei ruoli utente facendo clic su **[!UICONTROL MANAGE ROLES]** sulla barra multifunzione superiore.

1. Scorri verso il basso e seleziona **[!UICONTROL System administrator]** accesso per questo utente.

1. Fai clic su **[!UICONTROL OK]**.

### Ottieni l’ID tenant {#get-the-tenant-id}

Segui le istruzioni [in questa pagina](https://docs.microsoft.com/en-us/onedrive/find-your-office-365-tenant-id) per trovare il tuo ID tenant.  Questo ID è necessario durante la configurazione di pre-integrazione nello strumento di integrazione.

## Installare Campaign Standard per Microsoft Dynamics 365 {#install-appsource-app}

Per integrare l’app Dynamics 365 nell’ambiente Campaign Standard, effettua le seguenti operazioni:

1. Sfoglia per [Applicazioni aziendali Microsoft](https://appsource.microsoft.com/en-us/marketplace/apps)e search for_Adobe Campaign Standard_ nella barra di ricerca.
In alternativa, puoi passare a questo [link](https://appsource.microsoft.com/en-us/product/dynamics-365/adobe.adobe_campaign_d365?tab=Overview){target="_blank"}.
1. Segui le istruzioni per installare l’app per l’istanza di Dynamics 365.
1. Una volta installata, accedi all’istanza di Dynamics 365 e accedi come amministratore.
1. Fai clic sull’icona dell’ingranaggio nell’angolo superiore destro e fai clic su **[!UICONTROL Advanced Settings]**. Nel banner superiore, fai clic sul menu a discesa accanto a **[!UICONTROL Settings]**, fai clic su **[!UICONTROL Processes]** in **[!UICONTROL Process Center]**.
1. Cerca **[!UICONTROL Adobe Campaign Email Bounce]** e fare clic su di esso.
1. Il giorno **[!UICONTROL Administration]** , modifica il proprietario impostando l’utente dell’applicazione API Adobe creato in precedenza facendo clic su **[!UICONTROL Actions]** dalla barra multifunzione superiore, quindi selezionare **[!UICONTROL Assign to another User]** , seleziona **[!UICONTROL Adobe API application user]** dal menu a discesa per assegnare.
1. Riattiva il processo.
1. Effettua le stesse operazioni per **[!UICONTROL Adobe Campaign Email Click]** attività.

>[!NOTE]
>
>Se in qualsiasi momento desideri disattivare questi processi, puoi farlo in questo **[!UICONTROL Processes]** schermo.

**Argomenti correlati**

* [Configurare l’integrazione di Adobe Developer per Microsoft Dynamics 365](../../integrating/using/d365-acs-configure-adobe-io.md) è il passaggio successivo nella configurazione dell’integrazione
* [Introduzione all’applicazione di integrazione self-service](../../integrating/using/d365-acs-self-service-app-quick-start-guide.md) contiene l’elenco completo dei passaggi necessari per rendere operativa l’integrazione.
