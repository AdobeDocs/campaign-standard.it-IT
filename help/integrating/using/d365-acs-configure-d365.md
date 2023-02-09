---
title: Configurazione di Microsoft Dynamics 365 per l’integrazione con Campaign
description: Scopri come configurare Microsoft Dynamics 365 per l’integrazione con Campaign.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
exl-id: 57e85f8e-65b4-44ea-98e6-0c555acf6dee
source-git-commit: bee4da592e0b3727949bc44c6e41b81d4e7e73d4
workflow-type: tm+mt
source-wordcount: '913'
ht-degree: 1%

---

# Configurazione di Microsoft Dynamics 365 per l’integrazione con Adobe Campaign Standard

Scopri come configurare l’integrazione Microsoft Dynamics 365 e attivare i dati CRM nelle comunicazioni cross-channel con Adobe Campaign Standard.

## Panoramica

La descrizione generale dell’integrazione di Adobe Campaign Standard con Microsoft Dynamics 365 è descritta in [questa pagina](../../integrating/using/d365-acs-get-started.md).

Per abilitare l’integrazione sarà necessario configurare più applicazioni. Tuttavia, questo articolo si concentrerà sui passaggi necessari in Dynamics 365.

## Prerequisiti

Prima di eseguire la configurazione di pre-integrazione in questo documento, si presume che tu abbia già effettuato il provisioning e che tu abbia accesso come amministratore all’istanza Microsoft Dynamics 365 della tua organizzazione.  In caso contrario, dovrai contattare il supporto clienti Microsoft per completare il provisioning di Dynamics 365.

Se stai configurando l’integrazione sia per gli ambienti di staging che per quelli di produzione, dovrai eseguire i passaggi seguenti sia per le istanze di staging che per quelle di produzione Dynamics 365. Alcune istruzioni di seguito variano leggermente a seconda che si stia configurando un’istanza di Stage o Production Dynamics 365 (ad esempio, per un’istanza di produzione, seleziona &quot;prod&quot; per `<stage or prod>`)

## Configurazione dell&#39;applicazione e delle autorizzazioni

Un token di accesso OAuth consente allo strumento di integrazione di eseguire l’autenticazione con l’istanza Microsoft Dynamics 365 tramite API web per pubblicare gli eventi di esperienza Campaign Standard nella visualizzazione timeline dell’interfaccia di Microsoft Dynamics 365.

I passaggi principali sono descritti nel seguente video:

>[!VIDEO](https://video.tv.adobe.com/v/27637)

Per generare il token di accesso OAuth, segui i passaggi descritti di seguito.

### Registra una nuova applicazione {#register-a-new-app}

1. Accedi a [portal.azure.com](https://portal.azure.com){target="_blank"}.

1. Fai clic su **[!UICONTROL Azure Active Directory]** nel menu a sinistra; quindi fai clic su **[!UICONTROL App registrations]** nel sottomenu visualizzato.

1. Fai clic su **[!UICONTROL New registration]** nella parte superiore dello schermo.

1. Compila la schermata di registrazione dell’app:

   * Nome: adobe campaign `<stage or prod>`
   * Tipo di account supportato: **[!UICONTROL Accounts in this organizational directory only]** (valore predefinito)

Per ulteriori informazioni sulla creazione di una nuova applicazione, consulta [questa sezione](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app){target="_blank"}.

>[!NOTE]
>
>La directory di Microsoft Azure assegna un ID applicazione (client) univoco all’app. Questo ID sarà necessario in seguito per configurare Dynamics 365 e per eseguire la configurazione dello strumento di integrazione.

### Genera segreto client {#generate-a-client-secret}

1. Dalla schermata di panoramica dell’app, fai clic su nel sottomenu a sinistra **[!UICONTROL Certificates and Secrets > New client secret]**

1. Immetti una descrizione, imposta la durata e fai clic su **[!UICONTROL OK]**.

È stato creato il segreto client. Mantenere temporaneamente il valore per il completamento della configurazione di pre-integrazione dello strumento di integrazione.

>[!CAUTION]
>
>Mantieni questo valore così come sarà necessario per completare la configurazione di pre-integrazione dello strumento di integrazione. Non può essere recuperato in seguito.


### Autorizzazioni di installazione

1. Da questa schermata o dalla schermata di panoramica dell’app, fai clic su **[!UICONTROL API permissions]** nel sottomenu a sinistra.  Dopo aver fatto clic su **[!UICONTROL Add a permission]**, è necessario selezionare **[!UICONTROL Dynamics CRM]** nel menu .

1. Quindi seleziona la casella per **[!UICONTROL user_impersonation]**, quindi fai clic su **[!UICONTROL Add permissions]** pulsante .

Per ulteriori informazioni sulla configurazione delle autorizzazioni, consulta [questa sezione](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-configure-app-access-web-apis#add-permissions-to-access-web-apis){target="_blank"}.

### Creare l’utente dell’app

Questo nuovo utente è un utente generico. Sarà utilizzato dall&#39;applicazione: l’utente eseguirà qualsiasi modifica a Microsoft Dynamics 365 utilizzando l’API. Per crearlo, segui i passaggi seguenti:

1. Passa all’istanza di Dynamics 365 e accedi come amministratore.

1. Fai clic sull’icona dell’ingranaggio nell’angolo in alto a destra e fai clic su **[!UICONTROL Advanced Settings]**. Nel banner superiore, fai clic sull’elenco a discesa accanto a **[!UICONTROL Settings]**, fai clic su **[!UICONTROL Security > Users]**.

1. Fai clic sul menu a discesa per accedere a **[!UICONTROL Application Users]**. Fai clic su **[!UICONTROL New]**.

1. Accertati che sia disponibile un elenco a discesa accanto alle parole dell’icona utente **[!UICONTROL USER:APPLICATION USER]**.

   Compila la schermata per il nuovo utente.  Suggerimenti sui parametri:

   * **[!UICONTROL User Name]** (e-mail): adobe_api_`<stage-or-prod>`@`<your-d365-hostname>`&quot; (esempio: adobe_api_stage@some-company.crm.dynamics.com)
   * **[!UICONTROL Application ID]**: ID dell’applicazione registrata in Azure AD (obbligatorio)
   * Puoi lasciare vuoto **[!UICONTROL Application ID URI]** e **[!UICONTROL Azure AD Object ID]**
   * **[!UICONTROL Full Name]**: API Adobe `<stage or prod>`
   * **[!UICONTROL Email]**: uguale a **[!UICONTROL User Name]** (o e-mail dell&#39;amministratore, se lo desideri)

   Per ulteriori informazioni sulla creazione di utenti dell’app, consulta [questa sezione](https://docs.microsoft.com/en-gb/power-platform/admin/create-users-assign-online-security-roles#create-an-application-user){target="_blank"}.

1. Fai clic sull’icona utente e carica un’icona Adobe Campaign; questa è l’icona che verrà visualizzata nella vista Timeline quando i nuovi eventi di Adobe vengono visualizzati in Dynamics 365.

1. Apri l’elenco dei ruoli utente facendo clic su **[!UICONTROL MANAGE ROLES]** nel nastro superiore.

1. Scorri verso il basso e seleziona **[!UICONTROL System administrator]** accesso per questo utente.

1. Fai clic su **[!UICONTROL OK]**.

### Ottieni l&#39;ID tenant {#get-the-tenant-id}

Seguire le istruzioni [in questa pagina](https://docs.microsoft.com/en-us/onedrive/find-your-office-365-tenant-id) per trovare l’ID tenant.  Questo ID è necessario durante la configurazione di pre-integrazione nello strumento di integrazione.

## Installare Campaign Standard per Microsoft Dynamics 365 {#install-appsource-app}

Per integrare l’app Dynamics 365 nell’ambiente Campaign Standard, procedi come segue:

1. Passa al seguente collegamento: [https://appsource.microsoft.com/en-us/marketplace/apps](https://appsource.microsoft.com/en-us/marketplace/apps) e cerca _Adobe Campaign per Dynamics 365_ nella barra di ricerca.
In alternativa, puoi passare a questo [collegamento](https://appsource.microsoft.com/en-us/product/dynamics-365/adobecampaign.re4snj-a4n7-5t6y-a14br-d5d1b?flightCodes=adobesignhide&amp;tab=Overview)
{target="_blank"}.
1. Segui le istruzioni per installare l’app per la tua istanza Dynamics 365.
1. Una volta installato, accedi all’istanza di Dynamics 365 e accedi come amministratore.
1. Fai clic sull’icona dell’ingranaggio nell’angolo in alto a destra e fai clic su **[!UICONTROL Advanced Settings]**. Nel banner superiore, fai clic sull’elenco a discesa accanto a **[!UICONTROL Settings]**, fai clic su **[!UICONTROL Processes]** sotto **[!UICONTROL Process Center]**.
1. Cerca **[!UICONTROL Adobe Campaign Email Bounce]** e fare clic su di esso.
1. Sulla **[!UICONTROL Administration]** modifica il proprietario dell’utente dell’applicazione API Adobe creato in precedenza facendo clic su **[!UICONTROL Actions]** dalla barra multifunzione superiore, selezionare **[!UICONTROL Assign to another User]** seleziona **[!UICONTROL Adobe API application user]** dal menu a discesa da assegnare.
1. Riattiva il processo.
1. Fai lo stesso per il **[!UICONTROL Adobe Campaign Email Click]** compito.

>[!NOTE]
>
>Se desideri disattivare questi processi in qualsiasi momento, puoi farlo in questo **[!UICONTROL Processes]** schermo.

**Argomenti correlati**

* [Configurazione dell’integrazione di Adobe Developer per Microsoft Dynamics 365](../../integrating/using/d365-acs-configure-adobe-io.md) è il passaggio successivo nella configurazione dell’integrazione
* [Guida introduttiva all’app di integrazione self-service](../../integrating/using/d365-acs-self-service-app-quick-start-guide.md) contiene l’elenco completo dei passaggi per rendere l’integrazione operativa.
