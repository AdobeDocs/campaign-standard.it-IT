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

Reporting dinamico fornisce rapporti completamente personalizzabili e in tempo reale. Aggiunge l’accesso ai dati di profilo, abilitando l’analisi demografica per dimensioni di profilo come genere, città ed età, oltre ai dati funzionali delle campagne e-mail come aperture e clic. L’interfaccia di trascinamento consente di esaminare i dati, determinare le prestazioni delle campagne e-mail rispetto ai segmenti di clienti più importanti e misurare il loro impatto sui destinatari.

>[!NOTE]
>
>Solo gli utenti con diritti di amministrazione o con unità organizzative impostate su **All** possono creare o salvare un nuovo rapporto. Per ulteriori informazioni, consulta questa [sezione](../../administration/using/users-management.md).

## Accesso ai report dinamici {#accessing-dynamic-reports}

È possibile accedere ai rapporti:

* Dalla home page selezionando la scheda **[!UICONTROL Reports]** nella barra superiore o la scheda **[!UICONTROL Reports]** per accedere ai rapporti per tutte le consegne.

   ![](assets/campaign_reports_access.png)

* In ciascun programma, campagna e messaggio, dal pulsante **Report** facendo clic su **Report dinamici** per visualizzare solo i report specifici della consegna.

   ![](assets/campaign_reports_description.png)

Alcuni rapporti non possono essere disponibili immediatamente dopo la consegna, a seconda del tempo necessario per raccogliere ed elaborare le informazioni.

I rapporti dinamici sono suddivisi in due categorie:

* **Modelli**, che possono essere modificati copiandoli con l’opzione  **Salva** come (**Progetto > Salva con nome.**) nel modello.
* **Report personalizzati**  (identificati in blu), che possono essere creati direttamente facendo clic sul pulsante  **Crea nuovo** progetto nella pagina  **** Report.

>[!NOTE]
>
>I dati vengono filtrati a seconda delle unità organizzative.

![](assets/dynamic_report_overview.png)

## Accordo di utilizzo del reporting dinamico {#dynamic-reporting-usage-agreement}

Lo scopo del contratto di utilizzo per la generazione di rapporti dinamici è quello di fungere da consenso a comparsa per l’elaborazione dei dati. Per impostazione predefinita, il contratto è visibile solo e può essere accettato o rifiutato solo dagli utenti assegnati con diritti di amministrazione.

Sono disponibili tre opzioni:

* **[!UICONTROL Ask me later]**: Facendo clic su  **Chiedi più tardi**, la finestra smetterà di essere visualizzata per 24 ore. Finché non accetti o rifiuti il contratto, le dimensioni del profilo non verranno visualizzate nei rapporti e le informazioni di identificazione personale dei clienti non verranno raccolte o inviate.
* **[!UICONTROL Accept]**: Accettando questo contratto, autorizzi Adobe Campaign a raccogliere le informazioni personali dei tuoi clienti e a trasferirle al centro dati o rapporti.
* **[!UICONTROL Decline]**: Rifiutando il contratto, le dimensioni del profilo non verranno visualizzate nei rapporti e le informazioni di identificazione personale dei clienti non verranno raccolte o inviate. Tieni presente che in questo caso externalID verrà ancora raccolto e utilizzato per identificare gli utenti finali.

La tabella seguente mostra cosa accade dopo l&#39;accettazione con questo contratto a seconda della tua regione.

|  | Reporting dinamico | Connettore Microsoft Dynamics 365 |
|---|---|---|
| Americhe e APAC (Asia Pacifico) | **Funzionalità disponibile**. <br>Tutte le informazioni predefinite (città, paese, stato, genere e segmenti sulla base dell’età) e i profili personalizzati inviate al centro di reporting statunitense. Per ulteriori informazioni sulle dimensioni del profilo, consulta questa [pagina](../../reporting/using/list-of-components-.md) | **Funzionalità disponibile**. <br>Tutti i campi dei profili predefiniti e personalizzati e i campi dell’evento Adobe Campaign Standard vengono elaborati nel data center degli Stati Uniti. |
| EMEA (Europa Medio Oriente e Africa) | **Funzionalità disponibile**. <br>Informazioni preconfigurate su tutti i profili (città, paese, stato, genere e segmenti sulla base dell’età) e informazioni personalizzate inviate al centro di reporting EMEA. Per ulteriori informazioni sulle dimensioni del profilo, consulta questa [pagina](../../reporting/using/list-of-components-.md) | **Funzionalità disponibile.** <br>Tutti i campi predefiniti e personalizzati dei profili e i campi dell’evento Adobe Campaign Standard elaborati nel centro dati EMEA. <br>**[!UICONTROL Control data]**che contiene Adobi I/O di dati di registrazione e ID degli eventi degli utenti finali dei clienti inviati e memorizzati nel data center statunitense. |

La tabella seguente mostra cosa succede dopo aver rifiutato questo contratto a seconda della tua area geografica. Tieni presente che anche in caso di rifiuto di questo contratto, sarà comunque disponibile la generazione di rapporti sulle consegne e sull’integrazione con Microsoft Dynamics 365.

| Regione | Reporting dinamico | Connettore Microsoft Dynamics 365 |
|---|---|---|
| Americhe e APAC (Asia Pacifico) | **Funzionalità disponibile**. <br> Nessuna informazione preconfigurata sui profili personalizzati e preconfigurati inviata al centro di reporting degli Stati Uniti, ad eccezione di ExternalID. | **Funzionalità disponibile**. <br>Nessun campo di profilo predefinito o personalizzato inviato al data center degli Stati Uniti, ad eccezione di ID esterno e ID destinatario. <br>Tutti i campi evento Adobe Campaign Standard elaborati nel data center degli Stati Uniti, ad eccezione dell’ID pagina speculare. <br>Per ulteriori informazioni sull’integrazione con Microsoft Dynamics 365, consulta questa  [pagina](../../integrating/using/d365-acs-get-started.md). |
| EMEA (Europa Medio Oriente e Africa) | **Funzionalità disponibile**. <br>Nessuna informazione predefinita e personalizzata sui profili inviati al centro di reporting EMEA, ad eccezione di ExternalID. | **Funzionalità disponibile.** <br>Nessun campo predefinito o di profilo personalizzato inviato al centro dati EMEA, ad eccezione di ID esterno e ID destinatario. <br>Tutti i campi evento Adobe Campaign Standard elaborati nel centro dati EMEA, ad eccezione dell’ID pagina speculare.  <br>**[!UICONTROL Control data]**che contiene Adobi I/O di dati di registrazione e ID degli eventi degli utenti finali dei clienti inviati e memorizzati nel data center statunitense.<br>Per ulteriori informazioni sull’integrazione con Microsoft Dynamics 365, consulta questa  [pagina](../../integrating/using/d365-acs-get-started.md). |

Questa scelta non è definitiva, puoi sempre modificarla selezionando **[!UICONTROL Enable PII data to be transferred to US region to use reporting on Profile data]** in **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Options]**.

Il valore può essere modificato in qualsiasi momento. Il valore 1 corrisponde a **[!UICONTROL Ask me later]**, 2 **[!UICONTROL Decline]** e 3 **[!UICONTROL Accept]**.

![](assets/pii_window_2.png)
