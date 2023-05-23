---
title: Verifica dei messaggi e-mail tramite profili di destinazione
description: Scopri come verificare i messaggi utilizzando profili di destinazione e indirizzi di sostituzione.
audience: sending
content-type: reference
topic-tags: preparing-and-testing-messages
context-tags: seedMember,overview
feature: Control Groups
role: User
level: Intermediate
exl-id: aa68914f-0497-40ba-98c8-4d4b2c6705fb
source-git-commit: 6530ca1726a2aff18c5be9566d8008c317918e64
workflow-type: tm+mt
source-wordcount: '1530'
ht-degree: 4%

---

# Verifica dei messaggi e-mail tramite profili di destinazione {#testing-message-profiles}

## Panoramica {#overview}

In aggiunta a [profili di test](../../audiences/using/managing-test-profiles.md), puoi testare un messaggio e-mail mettendoti nella posizione di uno dei profili target. Ciò ti consente di ottenere una rappresentazione esatta del messaggio che verrà ricevuto dal profilo (campi personalizzati, informazioni dinamiche e personalizzate, inclusi dati aggiuntivi dei flussi di lavoro...).

>[!IMPORTANT]
>
>Questa funzione ti consente di inviare le informazioni personali del profilo agli indirizzi e-mail esterni. L’esecuzione di richieste di privacy (GDPR e CCPA) all’interno di Campaign Standard NON eseguirà la richiesta esternamente.

Le fasi principali sono le seguenti:

1. Configura il messaggio, quindi avvia **Preparazione** fase.
1. **Seleziona uno o più profili** tra i profili target del messaggio.
1. Associa a ciascun profilo **indirizzo di sostituzione** a cui verranno inviate le bozze.
1. (facoltativo) Per ciascun profilo, definisci un **prefisso** da aggiungere alla riga dell’oggetto della bozza.
1. **Anteprima** in E-mail Designer come verrà visualizzato il messaggio per i profili.
1. Invia le bozze.

   >[!IMPORTANT]
   >
   >Le bozze vengono elaborate da [!DNL Campaign Standard] come consegne standard. Di conseguenza, l’invio di bozze utilizzando la sostituzione dei profili aggiungerà dei record ai registri di consegna e di tracciamento dei profili selezionati.

![](assets/do-not-localize/how-to-video.png) [Scopri questa funzione nel video](#video)

## Selezione di profili e indirizzi di sostituzione {#selecting-profiles}

Per utilizzare i profili target per il test, devi innanzitutto selezionarli e quindi definire gli indirizzi di sostituzione che riceveranno le bozze. A tale scopo, puoi effettuare le seguenti operazioni: [seleziona profili specifici](#selecting-individual-profiles) tra i profili target, oppure [importare profili da un pubblico esistente](#importing-from-audience).

>[!NOTE]
>
>Puoi selezionare un massimo di 100 profili da testare.

### Selezione di singoli profili {#selecting-individual-profiles}

1. Nel dashboard dei messaggi, assicurati che la preparazione dei messaggi sia avvenuta correttamente, quindi fai clic su **[!UICONTROL Audience]** blocco.

   ![](assets/substitution_preparation.png)

1. In **[!UICONTROL Profile substitutions]** , fare clic sulla scheda **[!UICONTROL Create element]** per selezionare i profili da utilizzare per il test.

   ![](assets/substitution_tab.png)

1. Fai clic sul pulsante di selezione del profilo per visualizzare l’elenco dei profili target del messaggio.

   ![](assets/substitution_recipient_selection.png)

1. Seleziona il profilo da utilizzare per il test, quindi immetti nella **[!UICONTROL Address]** inserisci l’indirizzo di sostituzione desiderato, quindi fai clic su **[!UICONTROL Confirm]**. Tutte le bozze con targeting per il profilo verranno inviate a questo indirizzo e-mail, anziché a quello definito nel database per questo profilo.

   Per aggiungere un prefisso specifico alla riga dell’oggetto delle bozze, compila la sezione **[!UICONTROL Subject line prefix]** campo.

   >[!NOTE]
   >
   >Il prefisso della riga oggetto può contenere fino a 500 caratteri.

   ![](assets/substitution_address.png)

   Il prefisso verrà visualizzato come segue:

   ![](assets/substitution_prefixsample.png)

1. Il profilo viene aggiunto all&#39;elenco, con l&#39;indirizzo e il prefisso di sostituzione associati. Ripeti i passaggi precedenti per tutti i profili da utilizzare per il test, quindi fai clic su **[!UICONTROL Confirm]**.

   ![](assets/substitution_recipients_confirm.png)

   Se desideri inviare una bozza a più indirizzi di sostituzione per uno stesso profilo, devi aggiungere questo profilo il numero di volte necessario.

   Nell’esempio seguente, la bozza basata sul profilo John Smith verrà inviata a due indirizzi di sostituzione diversi:

   ![](assets/substitution_multiple_addresses.png)

1. Una volta definiti tutti i profili e gli indirizzi di sostituzione, puoi inviare una bozza per testare il messaggio. A questo scopo, fai clic su **[!UICONTROL Test]** , quindi selezionare il tipo di test da eseguire.

   Se non è stato aggiunto alcun profilo di test al target del messaggio, il **[!UICONTROL Email rendering]** e **[!UICONTROL Proof + Email rendering]** opzioni non disponibili.  Per ulteriori informazioni sull’invio delle bozze, consulta [questa sezione](../../sending/using/sending-proofs.md).

   ![](assets/substitution_send_test.png)

>[!IMPORTANT]
>
>Se apporti modifiche al messaggio, assicurati di avviare di nuovo la preparazione del messaggio. In caso contrario, le modifiche non verranno riportate nella bozza.

### Importazione di profili da un pubblico {#importing-from-audience}

Campaign Standard ti consente di importare un pubblico di profili che puoi utilizzare per il test. Ciò ti consente, ad esempio, di inviare a un indirizzo e-mail univoco un intero set di messaggi destinati a profili diversi.

Inoltre, se il pubblico è già configurato con le colonne indirizzo e prefisso, potrai importare queste informazioni in **[!UICONTROL Profile substitutions]** scheda. Un esempio di importazione di tipi di pubblico con indirizzi di sostituzione è descritto in [questa sezione](#use-case).

>[!NOTE]
>
>Durante l’importazione di un pubblico, vengono selezionati e aggiunti al gruppo solo i profili corrispondenti al target del messaggio **[!UICONTROL Profile substitutions]** scheda.

Per importare profili da utilizzare per il test da un pubblico, effettua le seguenti operazioni:

1. Nel dashboard dei messaggi, assicurati che la preparazione dei messaggi sia stata eseguita correttamente, quindi fai clic su **[!UICONTROL Audience]** blocco.

   ![](assets/substitution_preparation.png)

1. Nella scheda **[!UICONTROL Profile substitutions]**, fai clic su **[!UICONTROL Import from an audience]**.

   ![](assets/substitution_audience_import.png)

1. Seleziona il pubblico da utilizzare, quindi inserisci l’indirizzo di sostituzione e il prefisso da utilizzare per le bozze inviate al pubblico.

   >[!NOTE]
   >
   >Il prefisso della riga dell’oggetto può contenere fino a 500 caratteri.

   ![](assets/substitution_audience_define.png)

   Se gli indirizzi e/o i prefissi di sostituzione da utilizzare sono già stati definiti nel pubblico, seleziona la **[!UICONTROL From Audience]** , quindi specificare la colonna da utilizzare per recuperare tali informazioni.

   ![](assets/substitution_fromaudience.png)

1. Fai clic sul pulsante **[!UICONTROL Import]**. I profili del pubblico corrispondenti al target del messaggio vengono aggiunti al **[!UICONTROL Profile substitution]** nonché gli indirizzi e i prefissi di sostituzione associati.

![](assets/substitution_audience_imported.png)

>[!NOTE]
>
>Se importi nuovamente lo stesso pubblico, con indirizzi e/o prefissi di sostituzione diversi, i profili verranno aggiunti all’elenco in aggiunta a quelli dell’importazione precedente.

## Anteprima del messaggio con profili di destinazione

>[!NOTE]
>
>L’anteprima è disponibile solo con E-mail Designer.

Per poter visualizzare in anteprima i messaggi utilizzando i profili di destinazione, assicurati di averli aggiunti alla sezione **[!UICONTROL Profile substitution]** elenco (vedere [Definizione di profili e indirizzi di sostituzione](#selecting-profiles)).

Se desideri utilizzare i campi di personalizzazione nel messaggio, devi aggiungerli **prima di** avviare la preparazione dei messaggi. In caso contrario, non verranno prese in considerazione nell’anteprima. Di conseguenza, assicurati di avviare nuovamente la preparazione dei messaggi se vengono apportate modifiche ai campi di personalizzazione.

Per visualizzare l’anteprima dei messaggi utilizzando la sostituzione del profilo, effettua le seguenti operazioni:

1. Nel dashboard dei messaggi, fai clic sullo snapshot del contenuto per aprire il messaggio in E-mail Designer.

   ![](assets/substitution_preview_access.png)

1. Seleziona la **[!UICONTROL Preview]** , quindi fai clic su **[!UICONTROL Change profile]**.

   ![](assets/substitution_preview_changeprofile.png)

1. Fai clic su **[!UICONTROL Profile Substitution]** per visualizzare i profili di sostituzione aggiunti per il test.

   Seleziona i profili da utilizzare per l’anteprima, quindi fai clic su **[!UICONTROL Select]**.

   ![](assets/substitution_preview_selection.png)

1. Viene visualizzata un’anteprima del messaggio. Utilizza le frecce per spostarti tra i profili selezionati.

   ![](assets/substitution_preview.png)

## Caso d’uso {#use-case}

In questo caso d’uso, vogliamo inviare a un set di profili specifici una newsletter e-mail personalizzata. Prima di inviare la newsletter, vogliamo visualizzarla in anteprima utilizzando alcuni dei profili target e inviare bozze agli indirizzi e-mail interni definiti in un file esterno.

I passaggi principali per questo caso d’uso sono i seguenti:

1. Crea il pubblico da utilizzare per il test.
1. Crea un flusso di lavoro per eseguire il targeting dei profili e inviare la newsletter.
1. Configura le sostituzioni del profilo del messaggio.
1. Visualizza l’anteprima del messaggio utilizzando i profili di destinazione.
1. Invia bozze.

### Passaggio 1: creare il pubblico da utilizzare per il test

1. Prepara il file da importare per creare il pubblico. Nel nostro caso, dovrebbe contenere l’indirizzo di sostituzione da utilizzare per la bozza e un prefisso da aggiungere nella riga dell’oggetto della bozza.

   In questo esempio, l’indirizzo e-mail &quot;oliver.vaughan@internal.com&quot; riceverà una bozza del messaggio destinato al profilo con l’indirizzo e-mail &quot;john.doe@mail.com&quot;. Il prefisso &quot;JD&quot; verrà aggiunto alla riga dell’oggetto della bozza.

   ![](assets/substitution_uc1.png)

1. Crea il flusso di lavoro per creare un pubblico dal file. A questo scopo, aggiungi e configura le attività seguenti:

   * **[!UICONTROL Load file]** attività: importa il file CSV (per ulteriori informazioni, consulta [questa sezione](../../automating/using/load-file.md)).
   * **[!UICONTROL Reconciliation]** attività: collega le informazioni del file alle informazioni del database. In questo esempio, utilizza l’indirizzo e-mail del profilo come campo di riconciliazione (per ulteriori informazioni su questa attività, consulta [questa sezione](../../automating/using/reconciliation.md)).
   * **[!UICONTROL Save audience]** attività: crea un pubblico in base al file importato (per ulteriori informazioni su questa attività, consulta [questa sezione](../../automating/using/save-audience.md)).

   ![](assets/substitution_uc2.png)

1. Esegui il flusso di lavoro, quindi vai al **[!UICONTROL Audiences]** per verificare che il pubblico sia stato creato con le informazioni desiderate.

   In questo esempio, il pubblico è composto da tre profili. Ciascuno di essi è collegato a un indirizzo e-mail di sostituzione che riceverà la bozza, con un prefisso da utilizzare nella riga dell’oggetto della bozza.

   ![](assets/substitution_uc3.png)

### Passaggio 2: creare un flusso di lavoro per eseguire il targeting dei profili e inviare la newsletter

1. Aggiungi **[!UICONTROL Query]** e **[!UICONTROL Email delivery]** attività, quindi configurale in base alle tue esigenze (consulta [Query](../../automating/using/query.md) e [Consegna e-mail](../../automating/using/email-delivery.md) sezioni).

   ![](assets/substitution_uc4.png)

1. Esegui il flusso di lavoro e assicurati che la preparazione dei messaggi sia avvenuta correttamente.

### Passaggio 3: configurare la scheda Sostituzione profilo del messaggio

1. Apri **[!UICONTROL Email delivery]** attività. Nel dashboard dei messaggi, fai clic su **[!UICONTROL Audience]** blocco.

   ![](assets/substitution_uc5.png)

1. Seleziona la **[!UICONTROL Profile substitutions]** , quindi fai clic su **[!UICONTROL Import from an audience]**.

   ![](assets/substitution_uc6.png)

1. In **[!UICONTROL Audience]**  , seleziona il pubblico creato dal file.

   ![](assets/substitution_uc7.png)

1. Definisci l’indirizzo di sostituzione e il prefisso della riga dell’oggetto da utilizzare per l’invio delle bozze.

   A questo scopo, seleziona la **[!UICONTROL From audience]** , quindi seleziona la colonna del pubblico che contiene le informazioni.

   ![](assets/substitution_uc8.png)

1. Fai clic sul pulsante **[!UICONTROL Import]**. I profili del pubblico vengono aggiunti all’elenco, con i relativi indirizzi di sostituzione e prefissi dell’oggetto associati.

   ![](assets/substitution_uc9.png)

   >[!NOTE]
   >
   >Nel nostro caso, tutti i profili del pubblico sono targetizzati dal **[!UICONTROL Query]** attività. Se uno di questi profili non faceva parte del target del messaggio, non veniva aggiunto all’elenco.

### Passaggio 4: visualizzare in anteprima il messaggio utilizzando i profili di destinazione

1. Nel dashboard dei messaggi, fai clic sullo snapshot del contenuto per aprire il messaggio in E-mail Designer.

   ![](assets/substitution_uc10.png)

1. Seleziona la **[!UICONTROL Preview]** , quindi fai clic su **[!UICONTROL Change profile]**.

   ![](assets/substitution_uc_preview.png)

1. Fai clic su **[!UICONTROL Profile Substitution]** per visualizzare i profili di sostituzione aggiunti in precedenza.

   Seleziona i profili da utilizzare per l’anteprima, quindi fai clic su **[!UICONTROL Select]**.

   ![](assets/substitution_uc_selectpreview.png)

1. Viene visualizzata un’anteprima del messaggio. Utilizza le frecce per spostarti tra i profili selezionati.

   ![](assets/substitution_uc_previewprofile.png)

### Passaggio 5: inviare bozze

1. Nel dashboard dei messaggi, fai clic su **[!UICONTROL Test]** , quindi conferma.

   ![](assets/substitution_uc_sendproof.png)

1. Le bozze vengono inviate in base a quanto configurato in **[!UICONTROL Profile substitutions]** scheda.

   ![](assets/substitution_uc_proofs.png)

## Video tutorial {#video}

Questo video mostra come verificare i messaggi e-mail utilizzando la sostituzione del profilo.

>[!VIDEO](https://video.tv.adobe.com/v/32368?quality=12)

Sono disponibili altri video dimostrativi sui Campaign Standard [qui](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=it).
