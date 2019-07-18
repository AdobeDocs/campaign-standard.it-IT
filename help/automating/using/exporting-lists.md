---
title: Esportazione di elenchi
seo-title: Esportazione di elenchi
description: Esportazione di elenchi
seo-description: 'Adobe Campaign consente di esportare i dati visualizzati come elenchi da una schermata panoramica direttamente in un file per utilizzi futuri. '
page-status-flag: never-activated
uuid: c 64 fe 706-bd 6 e -4746-958 e-f 94226 f 4 e 2 cb
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automazione
content-type: riferimento
topic-tags: import-and-exporting-data
discoiquuid: 12 c 874 da -435 f -44 b 6-a 3 c 8-873301 e 177 cc
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 36727e82d3aa73add6116fa2916752ff0e407d9d

---


# Exporting lists{#exporting-lists}

Adobe Campaign consente di esportare gli elenchi direttamente in un file per uso futuro. Exporting a list in a file generates a log entry in the **[!UICONTROL Export audits]** menu. For more information on export audits, refer to the [Auditing exports](../../administration/using/auditing-export-logs.md) section.

The export list option allows you to export a maximum of 100,000 lines by default and defined by the **Nms_ExportListLimit** option. This option can be managed by the functional administrator, under the **[!UICONTROL Administration]** &gt; **[!UICONTROL Application settings]** &gt; **[!UICONTROL Options]** menu.

Export list is available in all the screens that have a **List** mode view, for users with the **[!UICONTROL EXPORT (export)]** role.

1. Go to your chosen **List** screen. For example, the test profile overview screen ( **[!UICONTROL Profiles & audiences]** &gt; **[!UICONTROL Test profiles]** ).
1. Check that the screen is in **List** mode.

   ![](assets/export_list_mode_switch.png)

1. Organize the columns in the list in the order that you want to export them using the **[!UICONTROL Configure list]** button, in the top right corner. Oltre alle colonne configurate, viene esportata anche la chiave primaria della risorsa.
1. Se lo desiderate, potete applicare un filtro. A tal fine, fate clic sul pulsante nell'angolo in alto a sinistra per visualizzare il riquadro di ricerca.

   Se eseguite un'esportazione da un elenco contenente risorse diverse, dovete applicare i filtri per visualizzare nell'elenco un solo tipo di risorsa.

1. Se necessario, ordinate le colonne selezionate.
1. Select the export button ![](assets/exportlistbutton.png).

   Viene visualizzata una finestra a comparsa che conferma l'esportazione. Una volta confermato l'esportazione, il file viene scaricato automaticamente nel computer.

Il file viene generato in formato CSV, a meno che l'esportazione non venga eseguita in iOS, nel qual caso il file generato è in formato TXT. Viene denominato in base alla risorsa esportata e alla data di esportazione. Ad esempio: il nome profilebase_ 20150426_ 120253. csv verrebbe applicato a un'esportazione di profilo eseguita il 26 aprile alle 12:02:53. Viene codificata in formato UTF -8.

I valori numerici e le date prendono in considerazione l'ora locale (impostazione internazionale) dell'utente che esegue l'esportazione. Ad esempio: DD-MM-AAAA o MM-GG-AAAA.

Per eseguire un'esportazione più grande di questa, dovete creare un flusso di lavoro dedicato. Refer to the [Extract file](../../automating/using/extract-file.md) section.

**Esempio**

L'esempio seguente è un'esportazione eseguita nell'elenco di profilo di seguito:

* Colonne visualizzate (nell'ordine): Cognome, Nome, Data di nascita, Indirizzo e-mail.
* I nomi vengono ordinati in ordine alfabetico.

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
* [Configurazione del video dell'elenco](https://helpx.adobe.com/campaign/kt/acs/using/acs-configuring-a-list-feature-video-setup.html)

