---
title: Creazione della direct mailing
description: Segui questi passaggi per creare una consegna direct mailing in Adobe Campaign.
page-status-flag: never-activated
uuid: 3b1365c4-4ea1-4434-818b-05ff0c9b42c1
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: direct-mail
discoiquuid: 5b02227f-9438-4001-bc2f-3d8661d173b3
context-tags: delivery,directMailContent,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 9c812b0b622b82ba7aa382f04edb7a2a3f717cd4
workflow-type: tm+mt
source-wordcount: '594'
ht-degree: 96%

---


# Creazione della direct mailing{#creating-the-direct-mail}

La creazione di una consegna direct mailing è molto simile alla creazione di un’e-mail regolare. I passaggi seguenti descrivono la configurazione specifica di questo canale. Per ulteriori informazioni sulle altre opzioni, consulta [Creazione di un’e-mail](../../channels/using/creating-an-email.md).

>[!NOTE]
>
>Puoi anche aggiungere un’attività di direct mailing in un flusso di lavoro. Per ulteriori informazioni, consulta la guida [Flussi di lavoro](../../automating/using/direct-mail-delivery.md).

1. Crea una nuova direct mailing. Puoi crearne una dalla [pagina Home](../../start/using/interface-description.md#home-page) di Adobe Campaign, in una [campagna](../../start/using/marketing-activities.md#creating-a-marketing-activity) o in un [elenco di attività di marketing](../../start/using/programs-and-campaigns.md#creating-a-campaign).

   ![](assets/direct_mail_1.png)

1. Scegli il modello di **[!UICONTROL Direct mail]** preconfigurato o uno dei modelli personalizzati. Per ulteriori informazioni sui modelli, consulta la sezione [Gestione dei modelli](../../start/using/marketing-activity-templates.md).

   ![](assets/direct_mail_2.png)

1. Immetti le proprietà generali della consegna.

   ![](assets/direct_mail_3.png)

1. Definisci il pubblico da includere nel file di estrazione, nonché i profili di test e di trappola. Consulta [Definizione del pubblico della direct mailing](../../channels/using/defining-the-direct-mail-audience.md).

   ![](assets/direct_mail_4.png)

   >[!NOTE]
   >
   >La definizione del pubblico è molto simile alla definizione del pubblico di un’e-mail regolare. Consulta [Creazione di tipi di pubblico](../../audiences/using/creating-audiences.md).

1. Modifica il contenuto del file: colonne da includere per ciascun profilo, struttura del file, intestazione e piè di pagina. Consulta [Definizione del contenuto della direct mailing](../../channels/using/defining-the-direct-mail-content.md).

   ![](assets/direct_mail_5.png)

1. Fai clic sulla sezione **[!UICONTROL Schedule]** del dashboard di consegna per definire la data di contatto. Per la direct mailing, la data di contatto è obbligatoria. Per ulteriori informazioni, consulta [pianificazione dell’invio](../../sending/using/about-scheduling-messages.md).

   ![](assets/direct_mail_8.png)

1. Se hai aggiunto dei profili di test (consulta [Aggiunta di profili di test e di trappola](../../channels/using/defining-the-direct-mail-audience.md#adding-test-and-trap-profiles)), puoi testare la consegna prima di preparare il file finale. Ciò ti consente di creare un file campione contenente solo i profili di test selezionati.

   Fai clic su **[!UICONTROL Test]** per generare il file campione. Fai clic su **[!UICONTROL Summary]**, nell’angolo in alto a sinistra, quindi seleziona **[!UICONTROL Proofs]**. Nella parte sinistra della schermata, seleziona la bozza e fai clic su **[!UICONTROL Download file]**.

   >[!NOTE]
   >
   >Il ruolo **[!UICONTROL Export]** è necessario per consentire ad Adobe Campaign di esportare il file e renderlo disponibile per il download. Contatta l’amministratore.

   ![](assets/direct_mail_19.png)

1. Una volta definiti il contenuto, il pubblico e la data di contatto della consegna, fai clic sul pulsante **[!UICONTROL Prepare]**, nel dashboard di consegna.

   ![](assets/direct_mail_16.png)

   Le regole di tipologia vengono applicate. Ad esempio, tutti gli indirizzi postali non specificati sono esclusi dal target. Per questo motivo, accertati di aver selezionato la casella **[!UICONTROL Address specified]** nelle informazioni dei profili (consulta [Raccomandazioni](../../channels/using/about-direct-mail.md#recommendations)). Se hai definito un **[!UICONTROL Maximum volume of message]** nelle proprietà della direct mailing o a livello di modello, sarà applicato anche qui.

   ![](assets/direct_mail_25.png)

   >[!NOTE]
   >
   >Puoi impostare regole di affaticamento globali cross-channel che escludono automaticamente i profili sollecitati eccessivamente dalle campagne. Consulta [Regole di affaticamento](../../sending/using/fatigue-rules.md).

1. Fai clic su **[!UICONTROL Explore file]** per visualizzare in anteprima le prime 100 righe del file.

   ![](assets/direct_mail_18.png)

   Il file completo è accessibile per il download locale nella parte sinistra della schermata. Il download del file genera una voce di log nel menu **[!UICONTROL Export audits]**. Per ulteriori informazioni sui controlli delle esportazioni, consulta la sezione [Controllo delle esportazioni](../../administration/using/auditing-export-logs.md).

   >[!NOTE]
   >
   >Il ruolo **[!UICONTROL Export]** è necessario per consentire ad Adobe Campaign di esportare il file e renderlo disponibile per il download. Contatta l’amministratore.

   Per modificare il contenuto della consegna, è sufficiente fare clic sul pulsante **[!UICONTROL Regenerate file]** per tenere conto della modifica. Non è necessario eseguire nuovamente la preparazione.

   ![](assets/direct_mail_21.png)

1. Per confermare che il file è definitivo, fai clic su **[!UICONTROL Confirm]** nel dashboard di consegna.

   ![](assets/direct_mail_20.png)

Ora puoi inviare il file di estrazione al provider della direct mailing. A tal fine, sono disponibili diverse opzioni:

* Inviarla tramite e-mail regolare, con il file allegato
* Inviarla tramite Campaign: esegui la direct mailing in un [flusso di lavoro](../../automating/using/direct-mail-delivery.md) della campagna e aggiungi un **[!UICONTROL Transfer file]** per inviare il file, ad esempio tramite FTP. Consulta [Trasferire file](../../automating/using/transfer-file.md).

Il provider recupera l&#39;elenco degli indirizzi errati e invia queste informazioni a  Adobe Campaign, che elenco Bloccati automaticamente gli indirizzi errati. Consulta [Rendi al mittente](../../channels/using/return-to-sender.md).
