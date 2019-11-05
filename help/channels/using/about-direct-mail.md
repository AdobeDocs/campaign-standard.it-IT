---
title: Informazioni sulla direct mail
description: Scopri le principali specificità del canale di posta diretta in Adobe Campaign.
page-status-flag: mai attivato
uuid: 24add992-2efe-4b73-81c9-cda3e921ab16
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: canali
content-type: reference
topic-tags: direct-mail
discoiquuid: e1fbf39c-9c30-493c-8322-9c71e18ce98c
context-tags: consegna,directMailContent,back;deliveryCreation,procedura guidata
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Informazioni sulla direct mail{#about-direct-mail}

La posta diretta è un canale offline che consente di personalizzare e generare il file richiesto dai provider di posta diretta. Offre la possibilità di combinare canali online e offline nei viaggi dei clienti.

>[!NOTE]
>
>Questa funzione è facoltativa. Controllare il contratto di licenza. Il **[!UICONTROL Export]** ruolo è necessario per utilizzare la posta diretta. Contattare l'amministratore.

I canali online consentono di creare i messaggi (e-mail, SMS, distribuzione di app mobili, ecc.) e inviali al tuo pubblico direttamente da Adobe Campaign. Con i canali offline, è diverso. Quando prepari la consegna diretta per posta, Adobe Campaign genera un file contenente tutti i profili di destinazione e le informazioni di contatto scelte (ad esempio l'indirizzo postale). Sarà quindi possibile inviare questo file al provider di posta diretta che si prenderà cura dell'invio effettivo.

Nella sezione seguente viene illustrato come creare e generare una distribuzione di posta diretta con un solo colpo. È inoltre possibile includere un'attività di posta diretta in un flusso di lavoro per orchestrare campagne che combinano canali online e offline. Per ulteriori informazioni, consulta la guida [Flussi](../../automating/using/workflow-data-and-processes.md) di lavoro.

Il processo utente in Adobe Campaign è il seguente:

1. Creazione della consegna
1. Scelta del pubblico
1. Definizione del contenuto
1. Impostazione della data del contatto
1. Generazione del file

## Recommendations {#recommendations}

### Fornitori di posta diretta {#direct-mail-providers}

Prima di tutto, dovete contattare il vostro fornitore di posta diretta e raccogliere le loro raccomandazioni. Identificare le informazioni di profilo da includere nel file di estrazione in modo che possano personalizzare la comunicazione e inviarla al pubblico. Ad esempio, il nome e il cognome, l'indirizzo postale, un codice di promozione ecc. Questi campi sono quelli che verranno aggiunti nella scheda [Definizione dell'estrazione](../../channels/using/defining-the-direct-mail-content.md#defining-the-extraction) del contenuto della posta diretta.

Accertatevi di aver selezionato la **[!UICONTROL Address specified]** casella nelle informazioni dei profili. Se questa opzione è attivata, il profilo verrà aggiunto alla destinazione. Non lo è, sarà escluso da una regola di tipologia durante la fase di preparazione (vedere [Creazione della posta](../../channels/using/creating-the-direct-mail.md)diretta). Durante l'importazione del profilo, non dimenticare di aggiornare il campo.

![](assets/direct_mail_22.png)

### Indirizzi postali {#postal-addresses}

Quando si aggiungono i campi da includere nel file di estrazione, i campi indirizzo postale sono disponibili nel **[!UICONTROL Location]** nodo.

Adobe Campaign offre una serie di campi calcolati predefiniti che seguono le normalizzazioni degli indirizzi postali più comuni. I campi sono disponibili nel **[!UICONTROL Postal address]** nodo.

Per impostazione predefinita, un indirizzo può contenere fino a sei righe: il primo campo calcolato ( **[!UICONTROL Line 1]** contiene il nome e il cognome, le righe successive contengono l'indirizzo postale (strada, ecc.), e l'ultima riga contiene il codice postale ZIP e la città o città.

![](assets/direct_mail_23.png)

