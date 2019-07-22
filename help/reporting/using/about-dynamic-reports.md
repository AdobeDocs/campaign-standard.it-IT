---
title: Informazioni sui rapporti dinamici
seo-title: Informazioni sui rapporti dinamici
description: Informazioni sui rapporti dinamici
seo-description: Con rapporti dinamici, puoi trascinare variabili e dimensioni nel tuo ambiente a forma libera e analizzare il successo delle campagne.
page-status-flag: never-activated
uuid: a 84 a 18 bd -4 e 33-466 e-a 6 ce-d 7008 fe 12746
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: reporting
content-type: riferimento
topic-tags: informazioni sui rapporti
discoiquuid: bbb 41 c 38-12 c 1-4625-85 d 5-69627 e 2 f 4 b 39
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 4d95fe00c1958399ff4d22d5f0e7762f895b4032

---


# About dynamic reports{#about-dynamic-reports}

>[!NOTE]
>
>Only users with administration rights or with organizational units set to **All** can create or save a new report. For more on this, refer to this [section](../../administration/using/users-management.md).

![](assets/dynamic_report_intro.png)

La funzione di reporting dinamico fornisce rapporti completamente personalizzabili e in tempo reale. Consente di accedere ai dati di profilo, abilitando l'analisi demografica in base a dimensioni del profilo quali genere, città ed età, oltre a dati di campagna e-mail funzionali come aperture e clic. Con l'interfaccia di trascinamento, puoi esplorare i dati, determinare in che modo le campagne e-mail vengono eseguite sui segmenti di clienti più importanti e misurarne l'impatto sui destinatari.

Grazie al menu di trascinamento e alle visualizzazioni personalizzabili, la funzione dei rapporti dinamici consente di combinare dimensioni, metriche e intervallo di tempo in qualsiasi combinazione, con suddivisioni e confronti illimitati.


**Argomenti correlati:**

* [Elenco rapporti](../../reporting/using/defining-the-report-period.md)
* [Unità organizzative](../../administration/using/organizational-units.md)
* [Video sui rapporti](https://helpx.adobe.com/campaign/kt/acs/using/acs-creating-a-dynamic-report-feature-video-use.html) dinamici

## Accessing dynamic reports {#accessing-dynamic-reports}

I rapporti sono accessibili:

* From the home page by selecting **[!UICONTROL Reports]** tab in the top bar or the **[!UICONTROL Reports]** card to access reports for all deliveries.

   ![](assets/campaign_reports_access.png)

* In each program, campaign, and message, from the **Reports** button by clicking **Dynamic Reports** to only view the reports specific to the delivery.

   ![](assets/campaign_reports_description.png)

Alcuni rapporti non possono essere disponibili subito dopo la consegna, a seconda del tempo necessario per raccogliere e elaborare le informazioni.

I rapporti dinamici sono suddivisi in due categorie:

* **Modelli**, che possono essere modificati copiandoli mediante l'opzione **Salva come** (**Progetto &gt; Salva con nome.**) nel modello.
* **Rapporti personalizzati** (identificati in blu), che possono essere creati direttamente facendo clic sul **pulsante Crea nuovo progetto** nella home page **Rapporti** .

>[!NOTE]
>
>I dati vengono filtrati in base alle unità organizzative.

![](assets/dynamic_report_overview.png)


## Dynamic reporting usage agreement {#dynamic-reporting-usage-agreement}

I rapporti dinamici consentono di filtrare il rapporto in base ai dati del profilo con le dimensioni del profilo.

Le dimensioni del profilo possono essere visualizzate e utilizzate nei rapporti solo dopo l'accettazione del contratto di utilizzo dinamico del rapporto. Per impostazione predefinita, l'accordo è visibile e può essere accettato o rifiutato solo da utenti assegnati con diritti di amministrazione.

Questo contratto consente il trasferimento e l'archiviazione negli Stati Uniti dei seguenti dati di profilo: città, paese/regione, stato, genere e segmenti a livello di età.

Accettando questo contratto, tutti i dati europei e non europei verranno trasferiti negli Stati Uniti.

![](assets/pii_window.png)

Sono disponibili tre opzioni:

* **[!UICONTROL Ask me later]**: Facendo clic su Chiedi in un secondo momento, la finestra si interrompe per 24 ore.
* **[!UICONTROL Accept]**: Accettando questo contratto, autorizzate Adobe Campaign a raccogliere informazioni di identificazione personali dei clienti e a trasferire gli utenti negli Stati Uniti.
* **[!UICONTROL Decline]**: Rifiutando il contratto, le dimensioni del profilo non saranno incluse nei rapporti e le informazioni di identificazione personale dei clienti non saranno raccolte o inviate.

This choice is not final, you can always change it by selecting **[!UICONTROL Enable PII data to be transferred to US region to use reporting on Profile data]** in **[!UICONTROL Administration]** &gt; **[!UICONTROL Application Settings]** &gt; **[!UICONTROL Options]**.

Il valore può essere modificato in qualsiasi momento. The value -1 corresponds to **[!UICONTROL Ask me later]**, 1 **[!UICONTROL Accept]** and 0 **[!UICONTROL Decline]**.

![](assets/pii_window_2.png)

