---
solution: Campaign Standard
product: campaign
title: Utilizzare i modelli di consegna
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
index: y
description: '"I modelli di consegna consentono una maggiore efficienza fornendo scenari pronti per la maggior parte dei tipi di attività comuni."'
feature: Deliverability
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '819'
ht-degree: 10%

---


# Utilizzare i modelli {#use-templates}

I modelli di consegna consentono una maggiore efficienza, fornendo scenari pronti per la maggior parte dei tipi di attività comuni. Con i modelli, gli esperti di marketing possono distribuire nuove campagne con una personalizzazione minima in un lasso di tempo più breve.

Ulteriori informazioni sui modelli di consegna in [questa sezione](../../start/using/marketing-activity-templates.md).

## Guida introduttiva ai modelli di consegna {#gs-templates}

Un [modello di consegna](../../start/using/marketing-activity-templates.md#creating-a-new-template) ti consente di definire una volta un set di proprietà tecniche e funzionali in base alle tue esigenze e che possono essere riutilizzate per le consegne future. Puoi quindi risparmiare tempo e standardizzare le consegne quando necessario.

Quando gestisci diversi marchi in Adobe Campaign, Adobe consiglia di disporre di un sottodominio per marchio. Ad esempio, una banca può avere diversi sottodomini corrispondenti a ciascuna delle sue agenzie regionali. Se una banca possiede il dominio bluebank.com, i suoi sottodomini possono essere @ny.bluebank.com, @ma.bluebank.com, @ca.bluebank.com, ecc. Disporre di un modello di consegna per sottodominio consente di utilizzare sempre i parametri preconfigurati giusti per ogni marchio, evitando errori e risparmiando tempo.

**Suggerimento**: Per evitare errori di configurazione in Campaign, ti consigliamo di duplicare un modello nativo e modificarne le proprietà anziché creare un nuovo modello.

## Configurare gli indirizzi

* L’indirizzo del mittente è obbligatorio per consentire l’invio di un’e-mail.

* Alcuni ISP (provider di servizi Internet) controllano la validità dell&#39;indirizzo del mittente prima di accettare i messaggi.

* Un indirizzo formato in modo non corretto può causare il rifiuto da parte del server ricevente. È necessario assicurarsi che venga fornito un indirizzo corretto.

* L&#39;indirizzo deve identificare esplicitamente il mittente. Il dominio deve essere di proprietà del mittente e registrato al mittente.

* Adobe consiglia di creare account e-mail corrispondenti agli indirizzi specificati per le consegne e le risposte. Rivolgiti all’amministratore del sistema di messaggistica.

Nella sezione **[!UICONTROL Advanced parameters]** delle proprietà di un modello e-mail, il campo **[!UICONTROL From (email address)]** corrisponde all’indirizzo del mittente.

![](assets/template-parameters.png)

Il dominio dell&#39;indirizzo deve essere lo stesso del sottodominio configurato.

I campi **[!UICONTROL Reply to]** corrispondono all’indirizzo e-mail e al nome utilizzati per le risposte.

**Suggerimento** : l&#39;Adobe consiglia di utilizzare un indirizzo reale esistente, ad esempio l&#39;assistenza clienti del tuo marchio. In questo caso, se un destinatario invia una risposta, l’assistenza clienti sarà in grado di gestirla.

Per modificare il nome del mittente che verrà visualizzato nell’intestazione dei messaggi inviati, vai alla scheda **[!UICONTROL Properties]** della home page di E-mail Designer (accessibile tramite l’icona Home) e fai clic sul blocco **[!UICONTROL Default sender name]** .

![](assets/template-content.png)

Per aumentare il tasso di apertura delle consegne, Adobe consiglia di utilizzare un nome facilmente identificabile dai destinatari, ad esempio il nome del brand.

**Suggerimento**  - Per migliorare ulteriormente l&#39;esperienza del destinatario, puoi aggiungere il nome di una persona, ad esempio &quot;Emma da Megastore&quot;.

Per ulteriori informazioni sulla personalizzazione del nome del mittente, consulta [Mittente e-mail](../../designing/using/subject-line.md#email-sender).

## Personalizza il nome del mittente dell’SMS

Nella sezione **Parametri avanzati** delle proprietà di un modello SMS, l’opzione **Da** ti consente di personalizzare il nome del mittente del messaggio SMS utilizzando una stringa di caratteri. Questo è il nome visualizzato come mittente del messaggio SMS sul telefono cellulare del destinatario.

Se questo campo è vuoto, viene quindi utilizzato il numero di origine fornito nell’account esterno. Se non viene fornito alcun numero di origine, viene utilizzato il codice breve. Per ulteriori informazioni, consulta la sezione [Configurazione degli SMS](../../administration/using/configuring-sms-channel.md).

**Suggerimento**  - Controlla la legislazione del tuo paese riguardo alla modifica dell&#39;indirizzo del mittente. Dovresti anche verificare con il provider di servizi SMS se offre questa funzionalità.

## Imposta un gruppo di controllo

Una volta inviata la consegna, puoi confrontare il comportamento dei destinatari esclusi con quello dei destinatari che hanno ricevuto la consegna. Puoi quindi misurare l’efficienza delle campagne. Ulteriori informazioni sui gruppi di controllo [questa sezione](../../sending/using/control-group.md).

## Utilizzare le tipologie per applicare filtri o regole di controllo

Una tipologia contiene le regole di controllo applicate durante la fase di analisi, prima di inviare qualsiasi messaggio.

Nella sezione **[!UICONTROL Advanced parameters]** > **[!UICONTROL Preparation]** delle proprietà del modello, modifica la tipologia predefinita in base alle tue esigenze.

Ad esempio, per controllare meglio il traffico in uscita, puoi definire quali indirizzi IP possono essere utilizzati definendo un’affinità per sottodominio e creando una tipologia per affinità. Le affinità sono definite nel file di configurazione dell’istanza. Contatta il tuo amministratore Adobe Campaign.

Per ulteriori informazioni sulle tipologie, consulta [questa sezione](../../sending/using/managing-typologies.md).

## Collegamento di un brand a un modello

I parametri delle e-mail inviate relativi all’identità di un marchio (ad esempio il logo del marchio o l’indirizzo del mittente) vengono gestiti centralmente in Adobe Campaign. Puoi creare uno o più marchi e collegarli ai modelli di consegna.

Per ulteriori informazioni sull’utilizzo e la configurazione dei brand in Adobe Campaign, consulta Branding .

Per visualizzare o modificare il marchio assegnato a un modello di consegna, seleziona il pulsante Modifica proprietà del modello e individua i dettagli del marchio.

![](assets/template-brand.png)

Per ulteriori informazioni sul collegamento di un marchio a un modello, consulta [Assegnazione di un marchio a un’e-mail](../../administration/using/branding.md#assigning-a-brand-to-an-email).

Scopri come creare e configurare un marchio [in questa sezione](../../administration/using/branding.md#creating-a-brand).
