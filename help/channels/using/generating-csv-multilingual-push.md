---
title: Generazione di un file CSV per la notifica push multilingue con Campaign Standard
description: Il caricamento di un file CSV per generare contenuto per la distribuzione è una funzione utilizzata per supportare le notifiche push multilingue.
page-status-flag: never-activated
uuid: e90f4ec8-14e3-4304-b5fc-bce0ba08a4ef
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: email-messages
discoiquuid: 79231445-1d51-499a-adcf-0c0f6db1cfa3
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '1127'
ht-degree: 0%

---


# Generazione di un file CSV per notifiche push multilingue{#generating-csv-multilingual-push}

Il caricamento di un file CSV per generare contenuto per la distribuzione è una funzione utilizzata per supportare le notifiche push in più lingue. Il formato del file CSV deve rispettare alcune linee guida per il corretto caricamento del file e, di conseguenza, per creare una consegna. Le sezioni seguenti descrivono il formato del file e le relative considerazioni.

## Formato file {#file-format}

Il push multilingue richiede 14 colonne nel file CSV:

1. title
1. messageBody
1. sound
1. data
1. deeplinkURI
1. category
1. iosMediaAttachmentURL
1. androidMediaAttachmentURL
1. isContentAvailable
1. isMablesContent
1. customFields
1. locale
1. language
1. silentPush

Controllate l’esempio CSV facendo clic sul file **[!UICONTROL Download a sample file]** nella **[!UICONTROL Manage Content Variants]** finestra. For more on this, refer to the this [section](../../channels/using/creating-a-multilingual-push-notification.md).

* **title, messageBody, sound, badge, deeplinkURI, category, iosMediaAttachmentURL, androidMediaAttachmentURL**: contenuto normale del payload push. Devi fornire queste informazioni in modo simile a quando crei consegne push.
* **Campi** personalizzati:  utilizza il formato JSON per i campi personalizzati, ad esempio `{"key1":"value1","key2":"value2"}`. Per un esempio di campi personalizzati, fare riferimento al file di esempio precedente.
* **isContentAvailable**: flag per la verifica Contenuto disponibile, il valore 1 indica true, il valore 0 indica false. Il valore predefinito è 0. Se lasciate vuota questa colonna, il valore sarà considerato 0.
* **isMablesContent**: flag per Contenuto variabile, il valore 1 indica true, il valore 0 indica false. Il valore predefinito è 0. Se lasciate vuota questa colonna, il valore sarà considerato 0.
* **locale**: locale è il campo per le varianti di lingua, ad esempio &quot;en_us&quot; per US-English e &quot;fr_fr&quot; per France-French.
* **lingua**: nome della lingua associata alle impostazioni internazionali. Ad esempio, se l&#39;impostazione internazionale è &quot;en_us&quot;, il nome della lingua deve essere &quot;Inglese-Stati Uniti&quot;.
* **silentPush**: flag per il tipo di notifica push. Se si tratta di una notifica push regolare, il valore deve essere 0. Se si tratta di un push silenzioso, il valore deve essere 1. Il valore predefinito è 0. Se lasciate vuota questa colonna, il valore sarà considerato 0.

## Vincoli e Linee guida per la creazione di file CSV {#constraints-guideline-csv}

**Il nome di ogni colonna è fisso**.
Dovete includere il nome di ciascuna colonna nel file CSV, se non utilizzate colonne per il contenuto, lasciatelo vuoto.

**Le colonne &quot;locale&quot; e &quot;lingua&quot; sono obbligatorie e il valore è univoco per ogni riga.**
Un valore vuoto per questa colonna causerà un errore nel caricamento del file.

**L&#39;ordine delle colonne è importante**. L’ordine delle colonne nel file caricato deve seguire lo stesso formato del file di esempio.

**Contenuto** della colonna Preventivo. Poiché si tratta di un file CSV (che sta per valori separati da virgole), qualsiasi contenuto di colonna che includa la virgola (,) deve essere citato. Per esempio, &quot;Ciao, Tom!&quot;

**La codifica UTF-8 è necessaria per i caratteri internazionali.**

**Se generate il file in testo normale, separate ogni colonna per &quot;,&quot;.**

**Variante non corrispondente.** Se utilizzate audience di blocchi di contenuto e target con lingue specifiche, dovete elencare tutte le lingue di destinazione nel file CSV oppure ricevete un errore durante l&#39;invio della consegna.

## Inserimento di un campo di personalizzazione nel file CSV {#personalization-field-csv}

Se desiderate utilizzare i campi di personalizzazione, dovete includere <span> tag nel file.

Per inserire il campo di personalizzazione &quot;firstName&quot; in messageBody, il messaggio deve essere:

```
 "Hello <span class="nl-dce-field nl-dce-done"  data-nl-expr="/context/profile/firstName">First name</span>, this is message".
```

Il campo &quot;firstName&quot; è rappresentato da:

```
 <span class="nl-dce-field nl-dce-done" data-nl-expr="/context/profile/firstName">First name</span>
```

Nell&#39;estensione sono presenti due attributi obbligatori:

* Una è la classe che è statica. Indipendentemente dal campo di personalizzazione che intendi utilizzare, sarà sempre class=&quot;nl-dce-field nl-dce-done&quot;.

* Un altro è data-nl-expr che è il percorso del campo di personalizzazione. Ad esempio, se inserisci il campo di personalizzazione &quot;firstName&quot; dall’interfaccia utente, il percorso di navigazione sarà **[!UICONTROL Context (context)]** > **[!UICONTROL Profile (profile)]** > **[!UICONTROL First name (firstName)]** (come mostrato nell’immagine seguente). In questo caso, il percorso sarà

   ```
   /context/profile/firstName. data-nl-expr="/context/profile/firstName".
   ```

![](assets/multilingual_push_2.png)

## Nomi lingua e lingua {#locale-language-names}

Sono supportate le seguenti lingue:

| locale | language |
|:-:|:-:|
| af_za | Afrikaans - Sudafrica |
| sq_al | Albania |
| ar_dz | Arabo - Algeria |
| ar_bh | Arabo - Bahrein |
| ar_iq | Arabo - Iraq |
| ar_il | Arabo - Israele |
| ar_jo | Arabo - Giordania |
| ar_kw | Arabo - Kuwait |
| ar_lb | Arabo - Libano |
| ar_ma | Arabo - Marocco |
| ar_om | Arabo - Oman |
| ar_qa | Arabo - Qatar |
| ar_sa | Arabo - Arabia Saudita |
| ar_sy | Arabo - Siria |
| ar_tn | Arabo - Tunisia |
| ar_ae | Arabo - Emirati Arabi Uniti |
| ar_ye | Arabo - Yemen |
| hy_am | Armeno - Armenia |
| az_az | Azeri - Azerbaigian |
| be_by | Bielorussia - Bielorussia |
| bs_ba | Bosniaco - Bosnia |
| bg_bg | Bulgaria - Bulgaria |
| ca_es | Catalano - Spagna |
| zh_cn | Cinese (semplificato) - Cina |
| zh_sg | Cinese (semplificato) - Singapore |
| zh_hk | Cinese (tradizionale) - Hong Kong (RAS) della Cina |
| zh_tw | Cinese (tradizionale) - Taiwan |
| hr_hr | Croato - Croazia |
| cs_cz | Ceco - Ceca |
| da_dk | Danese - Danimarca |
| nl_be | Olandese - Belgio |
| nl_nl | Olandese - Paesi Bassi |
| en_au | Inglese - Australia |
| en_bz | Inglese - Belize |
| en_ca | Inglese - Canada |
| en_in | Inglese - India |
| en_ie | Inglese - Irlanda |
| en_jm | Inglese - Giamaica |
| en_nz | Inglese - Nuova Zelanda |
| en_ph | Inglese - Filippine |
| en_za | Inglese - Sudafrica |
| en_tt | Inglese - Trinidad e Tobago |
| en_gb | Inglese - Regno Unito |
| en_us | Inglese - Stati Uniti |
| en_zw | Inglese - Zimbabwe |
| et_ee | Estone - Estonia |
| fi_fi | Finlandese - Finlandia |
| fr_be | Francese - Belgio |
| fr_ca | Francese - Canada |
| fr_fr | Francese - Francia |
| fr_lu | Francese - Lussemburgo |
| fr_ch | Francese - Svizzera |
| de_at | Tedesco - Austria |
| de_de | Tedesco - Germania |
| de_lu | Tedesco - Lussemburgo |
| de_ch | Tedesco - Svizzera |
| el_cy | Greco - Cipro |
| el_gr | Grecia - Grecia |
| gu_in | Gujarati - India |
| he_il | Ebraico - Israele |
| hi_in | Hindi - India |
| hu_hu | Ungherese - Ungheria |
| is_is | Islandese - Islanda |
| id_id | Indonesia |
| it_it | Italiano - Italia |
| it_ch | Italiano - Svizzera |
| ja_jp | Giapponese - Giappone |
| kn_in | Kannada - India |
| kk_kz | Kazako - Kazakistan |
| ko_kr | Coreano - Corea del Sud |
| lv_lv | Lettone - Lettonia |
| lt_lt | Lituano - Lituania |
| mk_mk | Macedone - Macedonia |
| ms_my | Malese - Malesia |
| mr_in | Marathi - India |
| no_no | Norvegese - Norvegia |
| pl_pl | Polacco - Polonia |
| pt_br | Portoghese - Brasile |
| pt_pt | Portoghese - Portogallo |
| pa_in | Punjabi - India |
| ro_md | Rumeno - Moldavia |
| ro_ro | Rumeno - Romania |
| ru_kz | Russo - Kazakistan |
| ru_ru | Russia |
| ru_ua | Russia - Ucraina |
| a_in | Sanscrito - India |
| sr_ba | Serbo - Bosnia |
| sr_rs | Serbo - Serbia |
| sk_sk | Slovacco - Slovacchia |
| sl_si | Sloveno - Slovenia |
| es_ar | Spagnolo - Argentina |
| es_bo | Spagnolo - Bolivia |
| es_cl | Spagnolo - Cile |
| es_co | Spagnolo - Colombia |
| es_cr | Spagnolo - Costa Rica |
| es_do | Spagnolo - Repubblica Dominicana |
| es_ec | Spagnolo - Ecuador |
| es_sv | Spagnolo - El Salvador |
| es_gt | Spagnolo - Guatemala |
| es_hn | Spagnolo - Honduras |
| es_mx | Spagnolo - Messico |
| es_ni | Spagnolo - Nicaragua |
| es_pa | Spagnolo - Panama |
| es_py | Spagnolo - Paraguay |
| es_pe | Spagnolo - Perù |
| es_pr | Spagnolo - Porto Rico |
| es_es | Spagnolo - Spagna |
| es_uy | Spagnolo - Uruguay |
| es_ve | Spagnolo - Venezuela |
| sw_ke | Swahili - Kenya |
| sv_fi | Svedese - Finlandia |
| sv_se | Svedese - Svezia |
| ta_in | Tamil - India |
| tt_ru | Tatar - Russo |
| te_in | Telugu - India |
| th_th | Thai - Tailandia |
| tr_cy | Turchia - Cipro |
| tr_tr | Turco - Turchia |
| uk_ua | Ucraino - Ucraina |
| ur_in | Urdu - India |
| ur_pk | Urdu - Pakistan |
| vi_vn | Vietnamita - Vietnam |
