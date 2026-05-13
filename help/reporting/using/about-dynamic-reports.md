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
TQID: https://experienceleague.adobe.com/L392oFEzYUkSajzO3Gi7gjWLmDrpbOhW24k1OXFmoRc
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
  - id: c309ee4e-82e4-4f7e-b608-ef345678c34e
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
subfeature_v2:
  - id: ca3c1dd6-bdd2-41a9-bc5a-e35f5cca9e63
role_v2:
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 831
ht-degree: 10%

---

# Introduzione ai rapporti dinamici {#about-dynamic-reports}

Reporting dinamico fornisce rapporti completamente personalizzabili e in tempo reale. Consente di accedere ai dati del profilo, abilitando l’analisi demografica per dimensioni di profilo, come genere, città ed età, oltre ai dati funzionali delle campagne e-mail come aperture e clic. L’interfaccia di trascinamento consente di esaminare i dati, determinare le prestazioni delle campagne e-mail rispetto ai segmenti di clienti più importanti e misurare il loro impatto sui destinatari.

>[!NOTE]
>
>Solo gli utenti con diritti di amministrazione o con unità organizzative impostate su **All** possono creare o salvare un nuovo report. Per ulteriori informazioni, consulta questa [sezione](../../administration/using/users-management.md).

## Accesso ai report dinamici {#accessing-dynamic-reports}

I report sono accessibili:

* Dalla home page selezionando la scheda **[!UICONTROL Reports]** nella barra superiore o la scheda **[!UICONTROL Reports]** per accedere ai rapporti per tutte le consegne.

  ![](assets/campaign_reports_access.png)

* In ogni programma, campagna e messaggio, dal pulsante **Rapporti** facendo clic su **Rapporti dinamici** per visualizzare solo i rapporti specifici della consegna.

  ![](assets/campaign_reports_description.png)

Alcuni rapporti non possono essere disponibili immediatamente dopo una consegna, a seconda del tempo necessario per raccogliere ed elaborare le informazioni.

I rapporti dinamici sono suddivisi in due categorie:

* **Modelli**, che possono essere modificati copiandoli con l&#39;opzione **Salva con nome** (**Progetto > Salva con nome..**) nel modello.
* **Report personalizzati** (identificati in blu), che possono essere creati direttamente facendo clic sul pulsante **Crea nuovo progetto** nella home page di **Report**.

>[!NOTE]
>
>I dati vengono filtrati in base alle unità organizzative.

![](assets/dynamic_report_overview.png)

## Accordo di utilizzo del reporting dinamico {#dynamic-reporting-usage-agreement}

Lo scopo del Dynamic Reporting Usage Agreement è quello di funzionare come consenso pop-up per l’elaborazione dei dati. Per impostazione predefinita, l&#39;accordo è visibile solo e può essere accettato o rifiutato solo dagli utenti a cui sono stati assegnati diritti di amministrazione.

Sono disponibili tre opzioni:

* **[!UICONTROL Ask me later]**: facendo clic su **Chiedi più tardi**, la finestra non verrà più visualizzata per 24 ore. Fino a quando non accetti o rifiuti il contratto, le dimensioni del profilo non verranno visualizzate nei rapporti e le informazioni di identificazione personale dei clienti non verranno raccolte o inviate.
* **[!UICONTROL Accept]**: accettando questo contratto, autorizzi Adobe Campaign a raccogliere le informazioni di identificazione personale dei tuoi clienti e a trasferirle al centro dati o reportistica.
* **[!UICONTROL Decline]**: rifiutando il contratto, le dimensioni del profilo non verranno visualizzate nei rapporti e le informazioni di identificazione personale dei clienti non verranno raccolte o inviate. In questo caso externalID verrà comunque raccolto e utilizzato per identificare gli utenti finali.

Nella tabella seguente viene illustrato ciò che accade dopo l&#39;accettazione del contratto, a seconda dell&#39;area geografica.

|  | Reporting dinamico | Connettore Microsoft Dynamics 365 |
|---|---|---|
| Americhe e APAC (Asia Pacifico) | **Funzionalità disponibile**. <br>Tutte le informazioni predefinite (ad esempio città, paese, stato, genere e segmenti in base all&#39;età) e i profili personalizzati sono stati inviati al centro rapporti negli Stati Uniti. Per ulteriori informazioni sulle dimensioni del profilo, consulta questa [pagina](../../reporting/using/list-of-components.md) | **Funzionalità disponibile**. <br>Tutti i campi predefiniti e personalizzati dei profili e i campi degli eventi di Adobe Campaign Standard vengono elaborati nel centro dati degli Stati Uniti. |
| EMEA (Europa, Medio Oriente e Africa) | **Funzionalità disponibile**. <br>Tutte le informazioni predefinite (ovvero città, paese, stato, genere e segmenti in base all&#39;età) e i profili personalizzati inviati al centro rapporti dell&#39;area EMEA. Per ulteriori informazioni sulle dimensioni del profilo, consulta questa [pagina](../../reporting/using/list-of-components.md) | **Funzionalità disponibile.** <br>Tutti i campi predefiniti e personalizzati dei profili e i campi degli eventi di Adobe Campaign Standard vengono elaborati nel data center dell&#39;area EMEA. <br>**[!UICONTROL Control data]**&#x200B;che contiene i dati di registrazione di Adobe I/O e gli ID degli eventi dell&#39;utente finale del cliente inviati e memorizzati nel data center statunitense. |

La tabella seguente mostra cosa accade dopo aver rifiutato il contratto, a seconda della regione. Anche se si rifiuta questo contratto, saranno comunque disponibili rapporti sulle consegne e sull’integrazione di Microsoft Dynamics 365.

| Area geografica | Reporting dinamico | Connettore Microsoft Dynamics 365 |
|---|---|---|
| Americhe e APAC (Asia Pacifico) | **Funzionalità disponibile**. <br> Non sono state inviate informazioni predefinite e personalizzate sui profili al centro rapporti degli Stati Uniti ad eccezione di ExternalID. | **Funzionalità disponibile**. <br>Nessun campo di profilo predefinito o personalizzato inviato al centro dati degli Stati Uniti ad eccezione dell&#39;ID esterno e dell&#39;ID destinatario. <br>Tutti i campi evento di Adobe Campaign Standard vengono elaborati nel data center statunitense ad eccezione dell&#39;ID pagina mirror. <br>Per ulteriori informazioni sull&#39;integrazione di Microsoft Dynamics 365, fare riferimento a questa [pagina](../../integrating/using/d365-acs-get-started.md). |
| EMEA (Europa, Medio Oriente e Africa) | **Funzionalità disponibile**. <br>Nessuna informazione preconfigurata e personalizzata inviata al centro rapporti EMEA ad eccezione di ExternalID. | **Funzionalità disponibile.** <br>Nessun campo di profilo predefinito o personalizzato inviato al data center dell&#39;area EMEA, ad eccezione dell&#39;ID esterno e dell&#39;ID destinatario. <br>Tutti i campi evento di Adobe Campaign Standard elaborati nel data center dell&#39;area EMEA ad eccezione dell&#39;ID pagina mirror. <br>**[!UICONTROL Control data]**&#x200B;contiene i dati di registrazione di Adobe I/O e gli ID degli eventi degli utenti finali dei clienti inviati e memorizzati nel data center degli Stati Uniti.<br>Per ulteriori informazioni sull&#39;integrazione di Microsoft Dynamics 365, fare riferimento a questa [pagina](../../integrating/using/d365-acs-get-started.md). |

Questa scelta non è definitiva, è sempre possibile modificarla selezionando **[!UICONTROL Enable PII data to be transferred to US region to use reporting on Profile data]** in **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Options]**.

Il valore può essere modificato in qualsiasi momento. Il valore 1 corrisponde a **[!UICONTROL Ask me later]**, 2 **[!UICONTROL Decline]** e 3 **[!UICONTROL Accept]**.

![](assets/pii_window_2.png)
