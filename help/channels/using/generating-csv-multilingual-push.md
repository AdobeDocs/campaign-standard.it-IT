---
title: Generazione di un file CSV per notifiche push multilingue con Campaign Standard
description: Il caricamento di un file CSV per generare contenuti da distribuire è una funzione utilizzata per supportare le notifiche push multilingue.
audience: channels
content-type: reference
topic-tags: email-messages
feature: Push
role: User
level: Intermediate
exl-id: bd9ec3f9-e047-42dc-ab64-9fb274cb4656
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '1016'
ht-degree: 0%

---

# Generazione di un file CSV per notifiche push multilingue{#generating-csv-multilingual-push}

Il caricamento di un file CSV per generare contenuti da distribuire è una funzione utilizzata per supportare le notifiche push multilingue. Il formato del file CSV deve rispettare determinate linee guida affinché il caricamento dei file abbia esito positivo e possa quindi creare una consegna. Le sezioni seguenti descrivono il formato del file e le relative considerazioni.

## Formato file {#file-format}

Il push multilingue richiede 14 colonne nel file CSV:

1. titolo
1. messageBody
1. suono
1. adge
1. deeplinkURI
1. categoria
1. iosMediaAttachmentURL
1. androidMediaAttachmentURL
1. isContentAvailable
1. isMutableContent
1. customFields
1. lingua
1. lingua
1. silentPush

Controlla il file CSV campione facendo clic sul pulsante **[!UICONTROL Download a sample file]** nel **[!UICONTROL Manage Content Variants]** finestra. Per ulteriori informazioni, consulta questa [sezione](../../channels/using/creating-a-multilingual-push-notification.md).

* **title, messageBody, sound, badge, deeplinkURI, category, iosMediaAttachmentURL, androidMediaAttachmentURL**: contenuto del payload push regolare. Devi fornire queste informazioni in modo simile a quando crei le consegne push.
* **Campi personalizzati**: utilizza il formato JSON per i campi personalizzati, ad esempio `{"key1":"value1","key2":"value2"}`. Per un esempio di campi personalizzati, fai riferimento al file di esempio riportato sopra.
* **isContentAvailable**: flag per il controllo Contenuto disponibile; il valore 1 indica vero; il valore 0 indica falso. Il valore predefinito è 0. Se si lascia vuota questa colonna, il valore verrà considerato 0.
* **isMutableContent**: flag per Contenuto variabile, il valore 1 indica vero, il valore 0 indica falso. Il valore predefinito è 0. Se si lascia vuota questa colonna, il valore verrà considerato 0.
* **lingua**: locale è il campo per le varianti di lingua, ad esempio &quot;en_us&quot; per l’inglese americano e &quot;fr_fr&quot; per il francese.
* **lingua**: nome della lingua associata alla lingua. Ad esempio, se locale è &quot;en_us&quot;, il nome della lingua deve essere &quot;English-United States&quot;.
* **silentPush**: flag per il tipo di notifica push. Se si tratta di una notifica push regolare, il valore deve essere 0. Se si tratta di una richiesta push silenziosa, il valore deve essere 1. Il valore predefinito è 0. Se si lascia vuota questa colonna, il valore verrà considerato 0.

## Vincoli e linee guida per la creazione del file CSV {#constraints-guideline-csv}

**Il nome di ogni colonna è fisso**.
Devi includere il nome di ogni colonna nel file CSV; se non utilizzi alcuna colonna per il contenuto, lascialo vuoto.

**Le colonne &quot;lingua&quot; e &quot;lingua&quot; sono obbligatorie e il valore è univoco per ogni riga.**
Un valore vuoto per questa colonna causerà un errore nel caricamento del file.

**Ordine delle colonne**. L’ordine delle colonne nel file caricato deve seguire lo stesso formato del file di esempio.

**Contenuto colonna preventivo**. Poiché si tratta di un file CSV (acronimo di Comma-Separated Values, Valori separati da virgole), deve essere inserito un apice per qualsiasi contenuto di colonna che includa la virgola (,). Per esempio, &quot;Ciao, Tom!&quot;

**La codifica UTF-8 è necessaria per i caratteri internazionali.**

**Se il file viene generato in formato testo normale, separa ogni colonna con &quot;,&quot;.**

**Variante non corrispondente.** Se utilizzi i tipi di pubblico per blocchi di contenuto e target con lingue specifiche, devi elencare ogni lingua di destinazione nel file CSV, altrimenti riceverai un errore durante l’invio della consegna.

## Inserimento di un campo di personalizzazione nel file csv {#personalization-field-csv}

Se desideri utilizzare i campi di personalizzazione, devi includere <span> nel file.

Per inserire il campo di personalizzazione &quot;firstName&quot; in messageBody, il messaggio deve essere:

```
 "Hello <span class="nl-dce-field nl-dce-done"  data-nl-expr="/context/profile/firstName">First name</span>, this is message".
```

Il campo &quot;firstName&quot; è rappresentato da:

```
 <span class="nl-dce-field nl-dce-done" data-nl-expr="/context/profile/firstName">First name</span>
```

Nell’estensione sono presenti due attributi obbligatori:

* Uno è la classe, che è statica. Indipendentemente dal campo di personalizzazione che intendi utilizzare, sarà sempre class=&quot;nl-dce-field nl-dce-done&quot;.

* Un altro è data-nl-expr, che è il percorso del campo di personalizzazione. Ad esempio, se inserisci il campo di personalizzazione &quot;firstName&quot; dall’interfaccia utente, il percorso di navigazione sarà **[!UICONTROL Context (context)]** > **[!UICONTROL Profile (profile)]** > **[!UICONTROL First name (firstName)]** (come illustrato nell&#39;immagine seguente). In questo caso, il percorso sarà

  ```
  /context/profile/firstName. data-nl-expr="/context/profile/firstName".
  ```

![](assets/multilingual_push_2.png)

## Nomi lingue e impostazioni internazionali {#locale-language-names}

Sono supportate le seguenti lingue:

| lingua | lingua |
|:-:|:-:|
| af_za | Afrikaans - Sudafrica |
| sq_al | Albanese - Albania |
| ar_dz | Arabo - Algeria |
| ar_bh | Arabo - Bahrain |
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
| az_az | Azerbaigian - Azerbaigian |
| be_by | Bielorusso - Bielorussia |
| bs_ba | Bosniaco - Bosnia |
| bg_bg | Bulgaro - Bulgaria |
| ca_es | Catalano - Spagna |
| zh_cn | Cinese (semplificato) - Cina |
| zh_sg | Cinese (semplificato) - Singapore |
| zh_hk | Cinese (tradizionale) - Hong Kong RAS della Cina |
| zh_tw | Cinese (tradizionale) - Taiwan |
| hr_hr | Croato - Croazia |
| cs_cz | Ceco - Cechia |
| da_dk | Danese - Danimarca |
| nl_be | Olandese - Belgio |
| nl_n | Olandese - Paesi Bassi |
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
| el_gr | Greco - Grecia |
| gu_in | Gujarati - India |
| he_il | Ebraico - Israele |
| hi_in | Hindi - India |
| hu_hu | Ungherese - Ungheria |
| is_is | Islandese - Islanda |
| id_id | Indonesiano - Indonesia |
| it_it | Italiano - Italia |
| it_ch | Italiano - Svizzera |
| ja_jp | Giapponese - Giappone |
| kn_in | Kannada - India |
| kk_kz | Kazaco - Kazakistan |
| ko_kr | Coreano - Corea del Sud |
| lv_lv | Lettone - Lettonia |
| lt_lt | Lituano - Lituania |
| mk_mk | Macedone - Macedonia |
| ms_my | Malese - Malaysia |
| mr_in | Marathi - India |
| no_no | Norvegese - Norvegia |
| pl_pl | Polacco - Polonia |
| pt_br | Portoghese - Brasile |
| pt_pt | Portoghese - Portogallo |
| pa_in | Punjabi - India |
| ro_md | Rumeno - Moldavia |
| ro_ro | Rumeno - Romania |
| ru_kz | Russo - Kazakistan |
| ru_ru | Russo - Russia |
| ru_ua | Russo - Ucraina |
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
| tt_ru | Tartaro - Russo |
| te_in | Telugu - India |
| th_th | Thailandese - Thailandia |
| tr_cy | Turco - Cipro |
| tr_tr | Turco - Turchia |
| uk_ua | Ucraino - Ucraino |
| ur_in | Urdu - India |
| ur_pk | Urdu - Pakistan |
| vi_vn | Vietnamita - Vietnam |
