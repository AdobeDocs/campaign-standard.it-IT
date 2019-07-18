---
title: Informazioni sull'posta diretta
seo-title: Informazioni sull'posta diretta
description: Informazioni sull'posta diretta
seo-description: Scopri le specificità principali del canale Direct Mail in Adobe Campaign.
page-status-flag: never-activated
uuid: 24 add 992-2 efe -4 b 73-81 c 9-cda 3 e 921 ab 16
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: canali
content-type: riferimento
topic-tags: direct-mail
discoiquuid: e 1 fbf 39 c -9 c 30-493 c -8322-9 c 71 e 18 ce 98 c
context-tags: delivery, directmailcontent, back; Deliverycreation, procedura guidata
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b0cf437ec97153b53bd4502171b24286abb25731

---


# About direct mail{#about-direct-mail}

Direct Mail è un canale offline che consente di personalizzare e generare il file richiesto dai provider di posta diretta. Ti permette di combinare canali online e offline nei percorsi dei clienti.

>[!NOTE]
>
>Questa funzione è facoltativa. Controllate il contratto di licenza. **[!UICONTROL Export]** Il ruolo è necessario per utilizzare la posta diretta. Contattate l'amministratore.

I canali online consentono di creare messaggi (e-mail, SMS, consegna app per dispositivi mobili ecc.) e inviarli direttamente al pubblico da Adobe Campaign. Con i canali offline, è diverso. Quando preparate una consegna diretta, Adobe Campaign genera un file contenente tutti i profili di targeting e le informazioni di contatto selezionate (ad esempio, indirizzo postale). Potrete quindi inviare questo file al provider di posta diretta che occuperà l'invio effettivo.

Nella sezione seguente viene illustrato come creare e generare una consegna diretta di una sola ripresa. Potete anche includere un'attività di posta diretta in un flusso di lavoro per orchestrare le campagne che combinano canali online e offline. For more on this, refer to the [Workflows](../../automating/using/workflow-data-and-processes.md) guide.

Il processo utente in Adobe Campaign è il seguente:

1. Creazione della distribuzione
1. Scelta dell'audience
1. Definizione del contenuto
1. Impostazione della data di contatto
1. Generazione del file

## Recommendations {#recommendations}

### Direct mail providers {#direct-mail-providers}

Prima di tutto, dovete contattare il provider di posta diretta e raccogliere le raccomandazioni. Identificare le informazioni sul profilo da includere nel file di estrazione, in modo che possano personalizzare la comunicazione e inviarla al pubblico. Ad esempio, il nome e il cognome, l'indirizzo postale, un codice di promozione, ecc. These fields are the ones that you will add in the [Defining the extraction](../../channels/using/defining-the-direct-mail-content.md#defining-the-extraction) tab of the direct mail's content.

Make sure you have checked the **[!UICONTROL Address specified]** box in your profiles' information. Se questa opzione è attivata, il profilo viene aggiunto alla destinazione. It is not, it will excluded by a typology rule during the preparation phase (see [Creating the direct mail](../../channels/using/creating-the-direct-mail.md)). Durante l'importazione del profilo, non dimenticate di aggiornare questo campo.

![](assets/direct_mail_22.png)

### Postal addresses {#postal-addresses}

When you add the fields to include in the extraction file, the postal address fields are available in the **[!UICONTROL Location]** node.

Adobe Campaign offre un set di campi calcolati predefiniti che seguono le normalizzazioni più comuni dell'indirizzo postale. The fields are available in the **[!UICONTROL Postal address]** node.

An address can contain up to six lines by default: the first calculated field ( **[!UICONTROL Line 1]** contains the first name and last name, the next lines contain the postal address (road etc.), and the last line contains the ZIP/Postal code and town or city.

![](assets/direct_mail_23.png)

