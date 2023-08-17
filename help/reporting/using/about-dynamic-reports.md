---
title: Introduzione ai rapporti dinamici
description: Con i rapporti dinamici, trascina e rilascia variabili e dimensioni nell’ambiente a forma libera e analizza il successo delle campagne.
audience: reporting
content-type: reference
topic-tags: about-reporting
feature: Reporting
role: Leader
level: Beginner
exl-id: fc3b28f3-63f6-4edc-923d-c7eb7925d1b7
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '791'
ht-degree: 5%

---

# Introduzione ai rapporti dinamici {#about-dynamic-reports}

Reporting dinamico fornisce rapporti completamente personalizzabili e in tempo reale. Aggiunge l’accesso ai dati del profilo, consentendo l’analisi demografica per dimensioni di profilo come genere, città ed età, oltre ai dati funzionali delle campagne e-mail come aperture e clic. L’interfaccia di trascinamento consente di esaminare i dati, determinare le prestazioni delle campagne e-mail rispetto ai segmenti di clienti più importanti e misurare il loro impatto sui destinatari.

>[!NOTE]
>
>Solo gli utenti con diritti di amministrazione o con unità organizzative impostate su **Tutti** può creare o salvare un nuovo rapporto. Per ulteriori informazioni, consulta questa [sezione](../../administration/using/users-management.md).

## Accesso ai report dinamici {#accessing-dynamic-reports}

I report sono accessibili:

* Dalla home page selezionando **[!UICONTROL Reports]** nella barra superiore o nella **[!UICONTROL Reports]** per accedere ai rapporti per tutte le consegne.

  ![](assets/campaign_reports_access.png)

* In ogni programma, campagna e messaggio, da **Rapporti** facendo clic **Rapporti dinamici** per visualizzare solo i rapporti specifici per la consegna.

  ![](assets/campaign_reports_description.png)

Alcuni rapporti non possono essere disponibili immediatamente dopo una consegna, a seconda del tempo necessario per raccogliere ed elaborare le informazioni.

I rapporti dinamici sono suddivisi in due categorie:

* **Modelli**, che può essere modificato copiandoli utilizzando **Salva con nome** opzione (**Progetto > Salva con nome.**) nel modello.
* **Rapporti personalizzati** (identificato in blu), che può essere creato direttamente facendo clic sul pulsante **Crea nuovo progetto** pulsante sulla **Rapporti** home page.

>[!NOTE]
>
>I dati vengono filtrati in base alle unità organizzative.

![](assets/dynamic_report_overview.png)

## Contratto di utilizzo per reporting dinamico {#dynamic-reporting-usage-agreement}

Lo scopo del Dynamic Reporting Usage Agreement è quello di funzionare come consenso pop-up per l’elaborazione dei dati. Per impostazione predefinita, l&#39;accordo è visibile solo e può essere accettato o rifiutato solo dagli utenti a cui sono stati assegnati diritti di amministrazione.

Sono disponibili tre opzioni:

* **[!UICONTROL Ask me later]**: facendo clic su **Chiedi in seguito**, la finestra smetterà di essere visualizzata per 24 ore. Fino a quando non accetti o rifiuti il contratto, le dimensioni del profilo non verranno visualizzate nei rapporti e le informazioni di identificazione personale dei clienti non verranno raccolte o inviate.
* **[!UICONTROL Accept]**: accettando questo contratto, autorizzi Adobe Campaign a raccogliere le informazioni di identificazione personale dei tuoi clienti e a trasferirle al centro dati o reportistica.
* **[!UICONTROL Decline]**: rifiutando il contratto, le dimensioni del profilo non verranno visualizzate nei rapporti e le informazioni di identificazione personale dei clienti non verranno raccolte o inviate. In questo caso externalID verrà comunque raccolto e utilizzato per identificare gli utenti finali.

Nella tabella seguente viene illustrato ciò che accade dopo l&#39;accettazione del contratto, a seconda dell&#39;area geografica.

|  | Reporting dinamico | Connettore Microsoft Dynamics 365 |
|---|---|---|
| Americhe e APAC (Asia Pacifico) | **Funzione disponibile**. <br>Tutte le informazioni pronte all’uso (ad esempio, città, paese, stato, genere e segmenti in base all’età) e i profili personalizzati sono stati inviati al centro di reporting degli Stati Uniti. Per ulteriori informazioni sulle dimensioni del profilo, consulta questa [pagina](../../reporting/using/list-of-components-.md) | **Funzione disponibile**. <br>Tutti i campi predefiniti e personalizzati dei profili e i campi dell’evento Adobe Campaign Standard vengono elaborati nel centro dati degli Stati Uniti. |
| EMEA (Europa, Medio Oriente e Africa) | **Funzione disponibile**. <br>Tutte le informazioni pronte all’uso (ad esempio, città, paese, stato, genere e segmenti in base all’età) e i profili personalizzati inviati al centro rapporti dell’EMEA. Per ulteriori informazioni sulle dimensioni del profilo, consulta questa [pagina](../../reporting/using/list-of-components-.md) | **Funzione disponibile.** <br>Tutti i campi predefiniti e personalizzati dei profili e i campi dell’evento Adobe Campaign Standard vengono elaborati nel data center dell’EMEA. <br>**[!UICONTROL Control data]**che contiene Adobi I/O di dati di registrazione e ID degli eventi degli utenti finali dei clienti inviati e memorizzati nel data center statunitense. |

La tabella seguente mostra cosa accade dopo aver rifiutato il contratto, a seconda della regione. Anche se si rifiuta questo contratto, il reporting sulle consegne e sull’integrazione di Microsoft Dynamics 365 sarà ancora disponibile.

| Area geografica | Reporting dinamico | Connettore Microsoft Dynamics 365 |
|---|---|---|
| Americhe e APAC (Asia Pacifico) | **Funzione disponibile**. <br> Non sono state inviate informazioni predefinite e personalizzate sui profili al centro rapporti degli Stati Uniti ad eccezione di ExternalID. | **Funzione disponibile**. <br>Nessun campo di profilo predefinito o personalizzato inviato al centro dati degli Stati Uniti ad eccezione di ID esterno e ID destinatario. <br>Tutti i campi dell’evento Adobe Campaign Standard vengono elaborati nel data center statunitense, ad eccezione dell’ID della pagina speculare. <br>Per ulteriori informazioni sull’integrazione con Microsoft Dynamics 365, consulta questa [pagina](../../integrating/using/d365-acs-get-started.md). |
| EMEA (Europa, Medio Oriente e Africa) | **Funzione disponibile**. <br>Non è stata inviata al centro rapporti EMEA alcuna informazione predefinita e personalizzata sui profili, ad eccezione di ExternalID. | **Funzione disponibile.** <br>Nessun campo di profilo predefinito o personalizzato inviato al data center dell’EMEA, ad eccezione dell’ID esterno e dell’ID destinatario. <br>Tutti i campi evento di Adobe Campaign Standard elaborati nel data center dell’area EMEA, ad eccezione dell’ID della pagina speculare.  <br>**[!UICONTROL Control data]**che contiene Adobi I/O di dati di registrazione e ID degli eventi degli utenti finali dei clienti inviati e memorizzati nel data center statunitense.<br>Per ulteriori informazioni sull’integrazione con Microsoft Dynamics 365, consulta questa [pagina](../../integrating/using/d365-acs-get-started.md). |

Questa scelta non è definitiva, puoi sempre modificarla selezionando **[!UICONTROL Enable PII data to be transferred to US region to use reporting on Profile data]** in **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Options]**.

Il valore può essere modificato in qualsiasi momento. Il valore 1 corrisponde a **[!UICONTROL Ask me later]**, 2 **[!UICONTROL Decline]** e 3 **[!UICONTROL Accept]**.

![](assets/pii_window_2.png)
