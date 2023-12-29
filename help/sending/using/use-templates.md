---
title: Utilizzare i modelli di consegna
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
index: y
description: "I modelli di consegna consentono una maggiore efficienza, fornendo scenari pronti per i tipi di attività più comuni."
feature: Deliverability
role: User
level: Intermediate
exl-id: ca134a7f-9035-4885-b4cb-1170b6ec10cc
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '815'
ht-degree: 12%

---

# Utilizzare i modelli {#use-templates}

I modelli di consegna consentono una maggiore efficienza, fornendo scenari pronti per i tipi più comuni di attività. Con i modelli, gli esperti di marketing possono distribuire nuove campagne con una personalizzazione minima in un periodo di tempo più breve.

Ulteriori informazioni sui modelli di consegna in [questa sezione](../../start/using/marketing-activity-templates.md).

## Introduzione ai modelli di consegna {#gs-templates}

A [modello di consegna](../../start/using/marketing-activity-templates.md#creating-a-new-template) consente di definire una volta una serie di proprietà tecniche e funzionali che soddisfano le tue esigenze e che possono essere riutilizzate per le consegne future. Potrai quindi risparmiare tempo e standardizzare le consegne quando necessario.

Quando gestisci più marchi in Adobe Campaign, Adobe consiglia di avere un sottodominio per marchio. Ad esempio, una banca può avere diversi sottodomini corrispondenti a ciascuna delle sue agenzie regionali. Se una banca è proprietaria del dominio bluebank.com, i sottodomini possono essere @ny.bluebank.com, @ma.bluebank.com, @ca.bluebank.com, ecc. Disporre di un modello di consegna per sottodominio consente di utilizzare sempre i giusti parametri preconfigurati per ciascun marchio, evitando errori e risparmiando tempo.

**Suggerimento**: per evitare errori di configurazione in Campaign, ti consigliamo di duplicare un modello nativo e di modificarne le proprietà anziché creare un nuovo modello.

## Configurare gli indirizzi

* L’indirizzo del mittente è obbligatorio per consentire l’invio di un’e-mail.

* Alcuni ISP (provider di servizi Internet) verificano la validità dell’indirizzo del mittente prima di accettare i messaggi.

* Un indirizzo con formato non corretto può comportare il rifiuto da parte del server ricevente. Devi accertarti che sia stato fornito un indirizzo corretto.

* L’indirizzo deve identificare esplicitamente il mittente. Il dominio deve essere di proprietà del mittente e deve essere registrato nel mittente.

* L’Adobe consiglia di creare account e-mail corrispondenti agli indirizzi specificati per le consegne e le risposte. Rivolgiti all’amministratore del sistema di messaggistica.

In **[!UICONTROL Advanced parameters]** delle proprietà di un modello e-mail, la sezione **[!UICONTROL From (email address)]** corrisponde all&#39;indirizzo del mittente.

![](assets/template-parameters.png)

Il dominio dell’indirizzo deve essere lo stesso del sottodominio configurato.

Il **[!UICONTROL Reply to]** I campi corrispondono all’indirizzo e-mail e al nome utilizzati per le risposte.

**Suggerimento** : l’Adobe consiglia di utilizzare un indirizzo reale esistente, ad esempio l’assistenza clienti del tuo marchio. In questo caso, se un destinatario invia una risposta, l’assistenza clienti sarà in grado di gestirla.

Per modificare il nome del mittente che verrà visualizzato nell&#39;intestazione dei messaggi inviati, passare alla **[!UICONTROL Properties]**  della home page di E-mail Designer (accessibile tramite l’icona Home) e fai clic su **[!UICONTROL Default sender name]** blocco.

![](assets/template-content.png)

Per aumentare il tasso di apertura delle consegne, Adobe consiglia di utilizzare un nome facilmente identificabile dai destinatari, ad esempio il nome del brand.

**Suggerimento** - Per migliorare ulteriormente l’esperienza del destinatario, puoi aggiungere il nome di una persona, ad esempio &quot;Emma from Megastore&quot;.

Per ulteriori informazioni sulla personalizzazione del nome del mittente, consulta [Mittente e-mail](../../designing/using/subject-line.md#email-sender).

## Personalizzare il nome del mittente dell’SMS

In **Parametri avanzati** delle proprietà di un modello SMS, la sezione **Da** L’opzione ti consente di personalizzare il nome del mittente del messaggio SMS utilizzando una stringa di caratteri. Questo è il nome visualizzato come mittente del messaggio SMS sul telefono cellulare del destinatario.

Se questo campo è vuoto, viene quindi utilizzato il numero di origine fornito nell’account esterno. Se non viene fornito alcun numero di origine, viene utilizzato il codice breve. Per ulteriori informazioni, consulta la sezione [Configurazione degli SMS](../../administration/using/configuring-sms-channel.md).

**Suggerimento** - Controlla la legislazione del tuo paese relativa alla modifica dell’indirizzo del mittente. Dovresti anche verificare con il provider di servizi SMS se offre questa funzionalità.

## Configurare un gruppo di controllo

Una volta inviata la consegna, puoi confrontare il comportamento dei destinatari esclusi con quello dei destinatari che l’hanno ricevuta. Puoi quindi misurare l’efficienza delle campagne. Ulteriori informazioni sui gruppi di controllo [questa sezione](../../sending/using/control-group.md).

## Utilizzare le tipologie per applicare filtri o regole di controllo

Una tipologia contiene regole di controllo applicate durante la fase di analisi, prima di inviare qualsiasi messaggio.

In **[!UICONTROL Advanced parameters]** > **[!UICONTROL Preparation]** nelle proprietà del modello, modifica la tipologia predefinita in base alle tue esigenze.

Ad esempio, per controllare meglio il traffico in uscita, puoi definire quali indirizzi IP possono essere utilizzati definendo un’affinità per sottodominio e creando una tipologia per affinità. Le affinità sono definite nel file di configurazione dell’istanza. Contatta il tuo amministratore Adobe Campaign.

Per ulteriori informazioni sulle tipologie, consulta [questa sezione](../../sending/using/managing-typologies.md).

## Collegare un brand a un modello

I parametri delle e-mail inviate relativi all’identità di un brand (come il logo del brand o l’indirizzo del mittente) sono gestiti centralmente in Adobe Campaign. Puoi creare uno o più marchi e collegarli ai modelli di consegna.

Per ulteriori informazioni sull’utilizzo e la configurazione dei brand in Adobe Campaign, consulta Branding.

Per visualizzare o modificare il brand assegnato a un modello di consegna, seleziona il pulsante Modifica proprietà del modello e individua i dettagli del brand.

![](assets/template-brand.png)

Per ulteriori informazioni sul collegamento di un brand a un modello, consulta [Assegnazione di un brand a un’e-mail](../../administration/using/branding.md#assigning-a-brand-to-an-email).

Scopri come creare e configurare un brand [in questa sezione](../../administration/using/branding.md#creating-a-brand).
