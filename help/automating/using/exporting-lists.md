---
title: Esportazione di elenchi
description: 'Adobe Campaign consente di esportare i dati visualizzati come elenchi da una schermata di panoramica direttamente in un file per un utilizzo futuro. '
page-status-flag: never-activated
uuid: c64fe706-bd6e-4746-958e-f94226f4e2cb
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: importing-and-exporting-data
discoiquuid: 12c874da-435f-44b6-a3c8-873301e177cc
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e35fdca6cb8cad79975f8150aa63bd65e50a4e1a

---


# Esportazione di elenchi{#exporting-lists}

Adobe Campaign consente di esportare gli elenchi direttamente in un file per un utilizzo futuro. L’esportazione di un elenco in un file genera una voce di registro nel **[!UICONTROL Export audits]**menu. Per ulteriori informazioni sui controlli delle esportazioni, consultare la sezione[Controllo delle esportazioni](../../administration/using/auditing-export-logs.md).

L’opzione di elenco di esportazione consente di esportare un massimo di 100.000 righe per impostazione predefinita e definita dall’opzione **Nms_ExportListLimit** . Questa opzione può essere gestita dall&#39;amministratore funzionale, nel menu **[!UICONTROL Administration]**>**[!UICONTROL Application settings]** > **[!UICONTROL Options]**.

L’elenco di esportazione è disponibile in tutte le schermate che dispongono di una visualizzazione in modalità **Elenco** , per gli utenti con il **[!UICONTROL EXPORT (export)]**ruolo.

1. Passate alla schermata **Elenco** selezionata. Ad esempio, la schermata di panoramica del profilo di test ( **[!UICONTROL Profiles & audiences]**>**[!UICONTROL Test profiles]** ).
1. Verificate che la schermata sia in modalità **Elenco** .

   ![](assets/export_list_mode_switch.png)

1. Organizzare le colonne nell’elenco nell’ordine in cui desiderate esportarle mediante il **[!UICONTROL Configure list]**pulsante, nell’angolo in alto a destra. Oltre alle colonne configurate, verrà esportata anche la chiave primaria della risorsa.
1. Se lo desideri, puoi applicare un filtro. A tale scopo, fare clic sul pulsante in alto a sinistra per visualizzare il riquadro di ricerca.

   Se si esegue un&#39;esportazione da un elenco contenente risorse diverse, è necessario applicare i filtri in modo che nell&#39;elenco venga visualizzato un solo tipo di risorsa.

1. Se lo desiderate, ordinate le colonne selezionate.
1. Fate clic sul pulsante di esportazione ![](assets/exportlistbutton.png).

   Viene visualizzata una finestra a comparsa per confermare l’esportazione. Dopo aver confermato l’esportazione, il file viene scaricato automaticamente nel computer.

Il file viene generato in formato CSV con estensione .TXT. Viene denominato in base alla risorsa esportata e alla data di esportazione. Ad esempio: il nome profileBase_20150426_120253.txt verrà applicato a un&#39;esportazione di profilo effettuata il 26 aprile 2015 alle 12:02:53. È codificato in formato UTF-8.

I valori numerici e le date tengono conto dell’ora locale (impostazione internazionale) dell’utente che esegue l’esportazione. Ad esempio: GG-MM-AAAA o MM-GG-AAAA.

Per eseguire un&#39;esportazione di dimensioni maggiori, è necessario creare un flusso di lavoro dedicato. Fare riferimento alla sezione [Estrai file](../../automating/using/extract-file.md) .

**Esempio**

L&#39;esempio seguente è un&#39;esportazione eseguita dall&#39;elenco di profili definito di seguito:

* Colonne visualizzate (in ordine): Cognome, Nome, Data di nascita, Indirizzo e-mail.
* I nomi sono ordinati in ordine alfabetico.

![](assets/export_list_example1.png)

Il file generato viene presentato come segue (per i primi dieci record):

```
Last name;First name;Birth date;Email;Zip code
Abalo;Patrick;11/11/1941 02:00:00;patrick.a@testmail.com;29200
Abasq;Joel;21/08/1977 02:00:00;abasq.joel@testmail.com;92160
Abernot;John;12/07/1963 01:00:00;john.abernot@testmail.com;78510
Abiven;Christian;16/03/1975 01:00:00;chris.a@mailtest.com;35000
Abouvier;Peter;02/07/1975 01:00:00;pabouvier@mailtest.com;94560
Accardi;Mike;22/06/1948 01:00:00;mike.accardi@mail.com;76400
Accremont;Frank;27/04/1947 01:00:00;accr.frank@mailtest.com;13500
Adam;Daniel;17/09/1953 01:00:00;danieladam@mail.com;17000
Adama;Pascal;22/01/1990 01:00:00;adapascal@mailtest.com;75012
Adama;Henry;22/09/1992 02:00:00;henry.adama@mail.com;64120
```

**Argomenti correlati:**

* [Ruoli](../../administration/using/list-of-roles.md)
* [Personalizzazione degli elenchi](../../start/using/customizing-lists.md)
* [Configurazione video elenco](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/getting-started/configure-a-list.html)
