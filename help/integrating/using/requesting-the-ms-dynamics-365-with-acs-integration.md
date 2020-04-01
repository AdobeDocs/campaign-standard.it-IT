---
title: Richiesta e configurazione di Microsoft Dynamics 365 con integrazione Campaign Standard
description: Scopri come richiedere e configurare Microsoft Dynamics 365 con integrazione Campaign Standard
page-status-flag: never-activated
uuid: ed6c1b76-87f7-4d23-b5e2-0765297a905c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
discoiquuid: 6c0c3c5b-b596-459e-87dd-a06bb7d633d2
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a1bc9d23163d12517c4501a572fc92aac6aacbc6

---


# Richiesta di Microsoft Dynamics 365 con integrazione Campaign Standard

Per eseguire il provisioning di questa integrazione, è necessario seguire i passaggi indicati di seguito.

Questa integrazione utilizza un provider di terze parti, Unifi.  In relazione alle richieste di assistenza, Adobe potrebbe essere tenuta a condividere le informazioni sull&#39;istanza di Adobe Campaign con Unifi.

Seguite i dettagli del diagramma di flusso e del diagramma di flusso riportati di seguito per richiedere e configurare l&#39;integrazione.

![](assets/provisioning-wf.png)

Dettagli diagramma di flusso (mappatura ai passaggi precedenti):

1. È già necessario disporre di Campaign Standard e Microsoft Dynamics 365 con accesso amministratore per iniziare a implementare questa integrazione.

1. Leggete questo articolo, controllate le notifiche e i passaggi di configurazione.

1. Inviate una richiesta di account a adobe-support@unifisoftware.com; Unifi richiederà le seguenti informazioni quando richiedete un account:
* Nome utente
* Cognome utente
* E-mail utente
* Nome società
* Regione (America del Nord, EMEA o APAC)
* Tipo di utilizzo:  Tipo di cliente (utenti cliente che utilizzeranno i dati di produzione in questa integrazione), o Tipo di partner (consulenti partner che stanno testando l&#39;integrazione per capire meglio in modo da poter aiutare i clienti Campaign) o Tipo di interno (utenti interni Adobe che stanno testando l&#39;integrazione per comprendere meglio la soluzione)
* Stato dei dati di Campaign Standard (a partire da un database pulito o con l&#39;integrazione di dati esistenti)
* ID tenant della campagna (consultate Configurare la sezione Integrazione campagna al punto 3 per ottenere l&#39;ID tenant)
* URL istanza campagna

Tempo di risposta previsto da Unifi: 1 ora durante le normali ore di ufficio negli Stati Uniti (dalle 9.00 alle 17.00 ora del Pacifico, lun - ven, escluse le vacanze).

1. Completa i passaggi successivi al provisioning per Microsoft Dynamics 365 e per Campaign Standard.
Invia inoltre un ticket all&#39;Assistenza clienti Adobe (direttamente o tramite il contatto Adobe) per far sì che nell&#39;istanza Campaign sia attivato il flag della funzione di accesso singolo. I partner devono contattare l&#39;assistenza clienti Adobe per attivare il flag di funzione, contattando l&#39;assistenza clienti Adobe.
Se in Campaign sono presenti dati esistenti che intendi includere nell&#39;integrazione, segui le indicazioni riportate in &quot;Dati campagna esistenti&quot; e consulta attentamente i tuoi contatti tecnici Adobe prima di procedere.

1. Completate i primi passaggi di registrazione in Unifi navigando su Unifi, facendo clic sulle schermate di registrazione, compilando le credenziali account Dynamics 365 e Campaign Standard e avvisando Unifi al termine.

1. Unifi chiederà al cliente la configurazione desiderata per il rifiuto e la mappatura degli attributi di rinuncia.

1. Il cliente indicherà la configurazione di rifiuto e la mappatura degli attributi di rifiuto selezionati.
Tempo di risposta previsto da Unifi: 1 giorno lavorativo (lun - ven, esclusi i giorni festivi)

1. La configurazione di Unifi prevede la revisione di mappature OOTB, filtri, processi, ecc. e apportare eventuali modifiche.  Per ulteriori informazioni, consulta la Guida utente di Unifi.
Questo passaggio prevede l&#39;impostazione della frequenza di esecuzione dei programmi Unifi
* Impostare la frequenza di esecuzione dei programmi nella schermata dei programmi in Unifi; tuttavia, per i programmi di &quot;ingresso&quot; e &quot;uscita&quot;, eseguiteli manualmente una volta prima di impostare la frequenza di programma
* Sono consigliate le seguenti frequenze di pianificazione: Ingressi (15 minuti), Avanzamento (15 minuti), Eliminazioni (Una volta al giorno), Rifiuti (Una volta al giorno)

**Si consiglia di lavorare con Unifi e/o Adobe Consulting (contattare il team di account Adobe) durante la configurazione di Unifi.**

Per abilitare l&#39;integrazione tra Adobe Campaign Standard e Microsoft Dynamics 365, i clienti devono creare un account utente con Unifi, un fornitore di terze parti, come descritto in questo documento.   In qualità di utente finale del sistema Unifi, per qualsiasi richiesta di dati avviata dal cliente all&#39;interno del sistema Unifi, il cliente deve contattare Unifi.

## Configurazione dell&#39;integrazione

Per questa integrazione è necessario configurare tre sistemi: Adobe Campaign Standard, Microsoft Dynamics 365 per le vendite e Unifi. Gli articoli di configurazione sono collegati di seguito.

>[!CAUTION]
>
>Per ciascun sistema, questi passaggi devono essere eseguiti da un amministratore.
>
>I passaggi descritti negli articoli di seguito guidano l&#39;utente nella creazione di integrazioni/registrazioni che richiedono l&#39;assegnazione di autorizzazioni e/o l&#39;accesso dell&#39;amministratore.  È responsabilità dell&#39;utente assicurarsi che questi passaggi siano conformi alle politiche aziendali prima di eseguire e di eseguirli con attenzione.

In ADOBE CAMPAIGN, devi configurare l&#39;accesso API e configurare una nuova integrazione per Unifi. A tal fine, consultate [questo articolo](../../integrating/using/configure-adobe-io-for-ms-dynamic.md).

In MICROSOFT DYNAMICS 365, è necessario creare una nuova registrazione dell&#39;app e consentire a un utente dell&#39;applicazione di utilizzare l&#39;integrazione.  Per configurare Microsoft Dynamics 365 per questa integrazione, consultare [questo articolo](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md).

In UNIFI, è necessario configurare l&#39;integrazione e configurare la mappatura o aggiungere attributi personalizzati. Per configurare Unifi per questa integrazione, consultate [questo articolo](../../integrating/using/configure-unifi-for-microsoft-dynamics-365-integration.md).

## Richiesta di assistenza

In caso di problemi, contattate l&#39;assistenza clienti di Unifi: [support@unifisoftware.atlassian.net](mailto:support@unifisoftware.atlassian.net).

Tempo di risposta previsto da Unifi: 4 ore durante le normali ore di ufficio negli Stati Uniti (dalle 9.00 alle 17.00 (ora del Pacifico, lun - ven, escluse le vacanze).

>[!CAUTION]
>
>In relazione alla richiesta di assistenza, Adobe potrebbe essere tenuta a condividere le informazioni sull&#39;istanza di Adobe Campaign con Unifi.