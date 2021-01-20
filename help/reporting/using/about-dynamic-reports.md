---
solution: Campaign Standard
product: campaign
title: Guida introduttiva ai report dinamici
description: Con i rapporti dinamici, trascina e rilascia variabili e dimensioni nell’ambiente a forma libera e analizza il successo delle campagne.
audience: reporting
content-type: reference
topic-tags: about-reporting
translation-type: tm+mt
source-git-commit: b471fddd49037770e33a113374afd60c2e79e69b
workflow-type: tm+mt
source-wordcount: '791'
ht-degree: 5%

---


# Guida introduttiva ai report dinamici {#about-dynamic-reports}

I rapporti dinamici forniscono rapporti completamente personalizzabili e in tempo reale. Consente l&#39;accesso ai dati del profilo, consentendo l&#39;analisi demografica per dimensioni del profilo quali genere, città ed età, oltre ai dati funzionali delle campagne e-mail come aperture e clic. L’interfaccia di trascinamento consente di esaminare i dati, determinare le prestazioni delle campagne e-mail rispetto ai segmenti di clienti più importanti e misurare il loro impatto sui destinatari.

>[!NOTE]
>
>Solo gli utenti con diritti di amministrazione o con unità organizzative impostate su **All** possono creare o salvare un nuovo rapporto. Per ulteriori informazioni, consulta questa [sezione](../../administration/using/users-management.md).

## Accesso ai report dinamici {#accessing-dynamic-reports}

È possibile accedere ai report:

* Dalla home page selezionando la scheda **[!UICONTROL Reports]** nella barra superiore o la scheda **[!UICONTROL Reports]** per accedere ai rapporti per tutte le consegne.

   ![](assets/campaign_reports_access.png)

* In ciascun programma, campagna e messaggio, dal pulsante **Reports** facendo clic su **Dynamic Reports** per visualizzare solo i rapporti specifici per la consegna.

   ![](assets/campaign_reports_description.png)

Alcuni rapporti non possono essere disponibili subito dopo la consegna, a seconda del tempo necessario per raccogliere ed elaborare le informazioni.

I rapporti dinamici sono suddivisi in due categorie:

* **Modelli**, che possono essere modificati copiandoli con l’opzione  **Salva** come (**Progetto > Salva con nome).**) nel modello.
* **Report**  personalizzati (identificati in blu), che possono essere creati direttamente facendo clic sul pulsante  **Crea nuovo** progetto nella pagina  **** Rapporto.

>[!NOTE]
>
>I dati vengono filtrati in base alle unità aziendali.

![](assets/dynamic_report_overview.png)

## Contratto di utilizzo per rapporti dinamici {#dynamic-reporting-usage-agreement}

Lo scopo dell&#39;accordo di utilizzo di reporting dinamico è di fungere da consenso popup per l&#39;elaborazione dei dati. Per impostazione predefinita, il contratto è visibile e può essere accettato o rifiutato solo dagli utenti ai quali sono stati assegnati diritti di amministrazione.

Sono disponibili tre opzioni:

* **[!UICONTROL Ask me later]**: Facendo clic su  **Chiedi più tardi**, la finestra smetterà di visualizzare per 24 ore. Fino a quando non accetti o non rifiuti il contratto, le dimensioni del profilo non verranno visualizzate nei tuoi rapporti e i dati di identificazione personale dei clienti non saranno raccolti o inviati.
* **[!UICONTROL Accept]**: Accettando questo contratto, l&#39;utente autorizza  Adobe Campaign a raccogliere i dati personali dei propri clienti e a trasferirli al centro dati o al reporting.
* **[!UICONTROL Decline]**: Rifiutando l&#39;accordo, le dimensioni del profilo non verranno visualizzate nei rapporti e i dati personali dei clienti non verranno raccolti o inviati. In questo caso, externalID verrà comunque raccolto e utilizzato per identificare gli utenti finali.

Nella tabella seguente sono riportati gli eventi che si verificano dopo l&#39;accettazione del contratto in base alla propria area geografica.

|  | Generazione di rapporti dinamici | Connettore Microsoft Dynamics 365 |
|---|---|---|
| Americhe e APAC (Asia Pacifico) | **Funzionalità disponibile**. <br>Informazioni complete (città, paese, regione, stato, genere e segmenti in base all&#39;età) e profili personalizzati inviati al centro di reporting statunitense. Per ulteriori informazioni sulle dimensioni del profilo, fare riferimento a questa [pagina](../../reporting/using/list-of-components-.md) | **Funzionalità disponibile**. <br>Tutti i campi out-of-the-box e i campi dei profili personalizzati e  eventi Adobe Campaign Standard vengono elaborati nel centro dati statunitense. |
| EMEA (Europa Medio Oriente e Africa) | **Funzionalità disponibile**. <br>Informazioni complete (città, paese, regione, stato, genere e segmenti in base all&#39;età) e profili personalizzati inviati al centro di reporting EMEA. Per ulteriori informazioni sulle dimensioni del profilo, fare riferimento a questa [pagina](../../reporting/using/list-of-components-.md) | **Funzionalità disponibile.** <br>Tutti i campi out-of-the-box e i campi dei profili personalizzati e  eventi Adobe Campaign Standard elaborati nel centro dati EMEA. <br>**[!UICONTROL Control data]**che contiene  dati di registrazione Adobe I/O e ID degli eventi degli utenti finali del cliente inviati e memorizzati nel centro dati statunitense. |

Nella tabella seguente sono riportati gli eventi che si verificano dopo il rifiuto del contratto a seconda della regione. Anche in caso di rifiuto del contratto, sarà comunque disponibile la generazione di rapporti sulle consegne e l&#39;integrazione con Microsoft Dynamics 365.

| Regione | Generazione di rapporti dinamici | Connettore Microsoft Dynamics 365 |
|---|---|---|
| Americhe e APAC (Asia Pacifico) | **Funzionalità disponibile**. <br> Nessun&#39;informazione out-of-the-box e informazioni sui profili personalizzati inviate al centro di reporting statunitense, ad eccezione di ExternalID. | **Funzionalità disponibile**. <br>Nessun campo out-of-the-box o campo di profilo personalizzato inviato al centro dati degli Stati Uniti, ad eccezione di ID esterni e ID destinatario. <br>Tutti  campi evento Adobe Campaign Standard elaborati nel centro dati degli Stati Uniti, ad eccezione dell&#39;ID pagina mirror. <br>Per ulteriori informazioni sull&#39;integrazione con Microsoft Dynamics 365, fare riferimento a questa  [pagina](../../integrating/using/d365-acs-get-started.md). |
| EMEA (Europa Medio Oriente e Africa) | **Funzionalità disponibile**. <br>Nessuna informazione disponibile e nessuna informazione sui profili personalizzati inviati al centro di reporting EMEA, ad eccezione di ExternalID. | **Funzionalità disponibile.** <br>Nessun campo out-of-the-box o campo di profilo personalizzato inviato al centro dati EMEA, ad eccezione di ID esterni e ID destinatario. <br>Tutti  campi evento Adobe Campaign Standard elaborati nel centro dati EMEA, ad eccezione dell&#39;ID pagina mirror.  <br>**[!UICONTROL Control data]**che contiene  dati di registrazione Adobe I/O e ID degli eventi degli utenti finali del cliente inviati e memorizzati nel centro dati statunitense.<br>Per ulteriori informazioni sull&#39;integrazione con Microsoft Dynamics 365, fare riferimento a questa  [pagina](../../integrating/using/d365-acs-get-started.md). |

Questa scelta non è finale, è sempre possibile modificarla selezionando **[!UICONTROL Enable PII data to be transferred to US region to use reporting on Profile data]** in **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Options]**.

Il valore può essere modificato in qualsiasi momento. Il valore 1 corrisponde a **[!UICONTROL Ask me later]**, 2 **[!UICONTROL Decline]** e 3 **[!UICONTROL Accept]**.

![](assets/pii_window_2.png)
