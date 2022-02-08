---
title: Branding
description: Scopri tutti gli strumenti disponibili per gestire le tue brand identity
audience: administration
context-tags: branding,overview;branding,main
feature: Instance Settings
role: Admin
level: Experienced
exl-id: b6032160-fd8b-4a19-b868-b2fb85e6a56b
source-git-commit: bfba6b156d020e8d2656239e713d2d24625bda54
workflow-type: tm+mt
source-wordcount: '1282'
ht-degree: 76%

---

# Branding{#branding}

## Informazioni sulla brand identity {#about-brand-identity}

Ogni azienda dispone di linee guida visive e tecniche per il brand. Con Adobe Campaign, puoi definire una serie di specifiche per presentare ai clienti un brand coerente, dai loghi agli aspetti tecnici, come il mittente dell’e-mail, l’URL o i domini.

Gli amministratori tecnici possono definire uno o più brand per immettere in modo centrale i parametri che influiscono sull’identità del brand. Ciò include il logo del brand, il dominio dell’URL di accesso delle pagine di destinazione o le impostazioni di tracciamento dei messaggi. Con Adobe Campaign, puoi creare questi brand e collegarli a messaggi o pagine di destinazione. Questa configurazione viene gestita tramite modelli.

## Configurazione e utilizzo dei brand {#configuring-and-using-brands}

Il principio fondamentale della configurazione e dell’utilizzo dei brand è:

1. Crea e configura il brand: questa operazione richiede autorizzazioni specifiche e viene eseguita dall’amministratore tecnico di Adobe Campaign. I passaggi per ottenere un nuovo marchio in Campaign sono descritti in dettaglio [in questa sezione](#creating-a-brand).
1. Crea uno o più modelli di consegna e pagine di destinazione per questo brand. Fai riferimento alla sezione [Creazione di un modello](../../start/using/marketing-activity-templates.md).
1. Crea messaggi e pagine di destinazione in base a questo modello. Consulta le sezioni [Creazione di un messaggio e-mail](../../channels/using/creating-an-email.md) e [Creazione di una pagina di destinazione](../../channels/using/designing-a-landing-page.md).

>[!IMPORTANT]
>
>I brand non possono essere creati o modificati dagli utenti finali: queste operazioni devono essere eseguite dall’amministratore tecnico di Adobe Campaign. Per qualsiasi richiesta, contatta l’Assistenza cliente di Adobe.
>
>L’utilizzo di più brand non è possibile nel contesto della messaggistica transazionale. Per ulteriori informazioni, consulta [Messaggi transazionali e branding](../../channels/using/transactional-messaging-limitations.md#permissions-and-branding).

I brand si trovano nel menu **[!UICONTROL Administration > Instance settings > Brand configuration]**.

Per impostazione predefinita, un brand appena creato è visibile solo agli utenti ai quali l’amministratore ha assegnato i diritti corrispondenti.

Un **Brand** è definito dalle seguenti caratteristiche:

* Una **Identity**, che definisce e personalizza il brand. Questa sezione contiene i seguenti campi:

   ![](assets/branding_01.png)

   * **Label**, visibile nell’interfaccia
   * **Brand name**
   * **Website URL** e **Website label** del brand
   * **Logo del brand**

* **[!UICONTROL Header parameters of sent emails]**, che personalizza i contenuti visualizzati dai destinatari delle campagne. Questa sezione contiene i seguenti campi:

   ![](assets/branding_04_header.png)

   * **Sender (email address)**, che contiene l’indirizzo e-mail del brand.
   * **Sender (name)**, che contiene il nome del brand.
   * **Reply to (email address)**, che contiene l’indirizzo e-mail a cui il cliente può rispondere.
   * **Reply to (name)**, che contiene il nome del brand.
   * **Error (email address)**, che contiene l’indirizzo e-mail da utilizzare in caso di errore.

   >[!IMPORTANT]
   >
   >Dopo aver aggiornato i parametri di intestazione delle e-mail, se il nome e l’indirizzo e-mail del mittente non sono cambiati nell’e-mail creata dal modello, controlla le impostazioni avanzate del modello.

* **Server(s) exposed on the internet** definisce i server utilizzati per il tracciamento ma anche per l’accesso alle pagine di destinazione. Questa sezione contiene i seguenti campi:

   ![](assets/configure_branding_04.png)

   * **External URL of the application server**, utilizzato per l’hosting e per l’accesso alle diverse pagine di destinazione create.
   * **External URL of the tracking server**, utilizzato come URL tracciato durante le consegne.
   * **External URL of the mirror page server**, utilizzato come pagina speculare predefinita nelle consegne.

   >[!NOTE]
   >
   >Per visualizzare l’anteprima della pagina di destinazione e il rendering della pagina speculare nell’interfaccia utente di Campaign, è necessario che gli URL del server dell’applicazione e del server della pagina speculare siano sicuri. In tal caso, per configurare questi URL utilizza https:// anziché http://.

* **[!UICONTROL Tracking URL configuration (Web Analytics)]**, che definisce la configurazione del tracciamento degli URL per il brand.

   Qui sono definiti i parametri aggiuntivi che consentono il tracciamento dei collegamenti su sistemi esterni quali strumenti di analisi web come Adobe Analytics o Google Analytics.

   ![](assets/branding_05.png)

## Creazione di un nuovo brand {#creating-a-brand}

Puoi aggiungere nuove entità dell’organizzazione in Campaign o creare un nuovo tipo di e-mail da inviare con un sottodominio diverso. Per eseguire questa operazione, effettua le seguenti operazioni:

1. **Configurare un nuovo sottodominio** - Per qualsiasi nuovo sottodominio da utilizzare per Adobe, il primo passaggio consiste nel configurarlo. Puoi eseguire questa operazione tramite [Pannello di controllo Campaign campagna](https://experienceleague.adobe.com/docs/control-panel/using/subdomains-and-certificates/subdomains-branding.html?lang=it) o contatta il tuo contatto tecnico Adobe. Ulteriori informazioni sulla configurazione dei sottodomini [nel presente articolo](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/campaign/ac-domain-name-setup.html).

   >[!NOTE]
   >
   >Il Pannello di controllo Campaign è accessibile a tutti gli utenti amministratori. I passaggi per concedere a un utente l’accesso come amministratore sono descritti in[questa pagina](https://experienceleague.adobe.com/docs/control-panel/using/discover-control-panel/managing-permissions.html?lang=it#discover-control-panel).

1. **Creare un biglietto** - Una volta configurato il sottodominio, Adobe lo configurerà nell’ambiente di produzione. Per richiedere questo, [creare un ticket per l’Assistenza clienti](https://helpx.adobe.com/it/enterprise/using/support-for-experience-cloud.html) con le seguenti informazioni:

   * Oggetto: ACS Nuova configurazione del brand

   * Contenuto: È stato configurato un nuovo dominio e vorremmo configurarlo nella nostra piattaforma Campaign

   * Dominio: XXX

   * URL di produzione: XXX.campaign.adobe.com

1. **Creare un modello di consegna** - Una volta che il nuovo marchio è disponibile, la best practice prevede la creazione di almeno un nuovo modello di consegna vuoto che faccia riferimento a questo nuovo marchio. [Ulteriori informazioni](#linking-a-brand-to-a-template).

1. **Controllare le linee guida per il recapito messaggi** - Prima di iniziare a utilizzare il nuovo dominio, la strategia deve essere discussa con il team di Adobe Deliverability. Aiuteranno a definire le best practice, se è necessario creare una nuova affinità per dividere gli IP tra domini, ad esempio, e/o se è necessario definire un piano di espansione. Ulteriori informazioni sulle best practice sul recapito messaggi [in questa sezione](../../sending/using/about-deliverability.md).

## Assegnazione di un brand a un’e-mail {#assigning-a-brand-to-an-email}

### Collegamento di un brand a un modello {#linking-a-brand-to-a-template}

Per utilizzare i parametri definiti per un brand, quest’ultimo deve essere collegato a un modello di consegna o a un modello di pagina di destinazione. A tal fine, devi creare o modificare un modello.

>[!NOTE]
>
>Per ulteriori informazioni sulla creazione di un modello, consulta la sezione [Creazione di un modello](../../start/using/marketing-activity-templates.md).

Una volta creato il modello, puoi collegarlo a un brand. Per eseguire questa operazione:

1. Fai clic sul pulsante **[!UICONTROL Edit properties]** per accedere alle proprietà del modello.

   ![](assets/branding_04.png)

1. Utilizza l’elenco a discesa per selezionare il brand da collegare al modello.

   >[!NOTE]
   >
   >Per impostazione predefinita, l’opzione **[!UICONTROL Default brand (branding)]** è selezionata.

   ![](assets/branding_05.png)

   Per visualizzare la configurazione del brand selezionato, fai clic sull’icona **[!UICONTROL Navigate to the detail of the element selected]**.

   ![](assets/branding_06.png)

1. Conferma la selezione e salva il modello.

Il modello è collegato al brand. Nell’editor e-mail, gli elementi come l’**Email address of default sender**, **Default sender name** o **Logo** utilizzeranno i dati del brand configurato.

### Caso di utilizzo del branding {#branding-use-case}

In questo esempio, creeremo un nuovo brand connesso ai viaggi e lo utilizzeremo in un’e-mail.

#### Passaggio 1: Configurare un nuovo brand {#configure-a-new-brand}

>[!IMPORTANT]
>
>La configurazione del brand è gestita solo da Adobe in quanto richiede autorizzazioni specifiche e impostazioni tecniche.

1. L’amministratore di Adobe Campaign crea prima il brand dal **[!UICONTROL Administration > Instance settings > Brand configuration]** e aggiunge il **Vacanze ai tropici** e configura il **[!UICONTROL ID]** e **[!UICONTROL Header parameters of sent emails]** del marchio.

   ![](assets/branding_07.png)

1. L’amministratore configura quindi l’URL dei **Server(s) exposed on the Internet** in modo tale da poter utilizzare le pagine di destinazione e quindi gli URL di tracciamento.

   In questo esempio, lo strumento di **analisi web** utilizzato è **Google Analytics**. L’amministratore configura l’URL di tracciamento come segue:

   ![](assets/branding_12.png)

Il brand è creato e configurato correttamente. Ora può essere utilizzato dai team di marketing.

#### Passaggio 2: Implementare un nuovo brand {#implement-a-new-brand}

In qualità di responsabile della consegna, hai il compito di creare i modelli di consegna per utilizzare il nuovo brand. A questo scopo, segui i passaggi seguenti:

1. Nel menu avanzato **[!UICONTROL Resources > Templates > Delivery templates]**, duplica un modello incorporato per configurare un nuovo modello di consegna.

   ![](assets/branding_08.png)

1. Per collegare questo modello al brand **Vacations in the Tropics**, modifica le proprietà del modello e seleziona il brand dall’elenco a discesa.

   ![](assets/branding_09.png)

1. Configura questo modello e-mail affinché rifletta la brand identity.
1. Una volta completato il modello, puoi salvarlo.

   ![](assets/branding_10.png)

   Ora è possibile utilizzare il modello di consegna per creare e-mail che verranno inviate a un pubblico.

#### Passaggio 3: Utilizzare il nuovo brand in una consegna {#use-the-new-brand-in-a-delivery}

Per creare un’e-mail collegata a un brand, segui i passaggi seguenti:

1. Fai clic sul pulsante **[!UICONTROL Create]** dal menu **[!UICONTROL Marketing activities]**.

   ![](assets/branding_14.png)

1. Seleziona l’attività **[!UICONTROL Email]**, quindi scegli il modello collegato al nuovo brand.

   ![](assets/branding_15.png)

1. L’e-mail è già configurata. Puoi verificare le informazioni prima di testarla utilizzando i profili di test, quindi inviarla al pubblico.

   ![](assets/branding_16.png)
