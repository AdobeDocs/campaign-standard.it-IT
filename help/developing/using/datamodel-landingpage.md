---
title: Pagina di destinazione DataModel
description: Scopri il modello dati
audience: designing
content-type: reference
topic-tags: editing-sms-and-push-content
context-tags: delivery,smsContent,back
feature: Data Model
role: Developer
level: Experienced
exl-id: bd12a214-5998-4fb9-9f54-0c886067b58b
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '1728'
ht-degree: 8%

---

# landingPage (nms:landingPage)

## Descrizione oggetto

<table>
      <tr>
         <th>Nome</th>
         <th>Etichetta</th>
         <th>Tipo (lunghezza)</th>
         <th>Valori di enumerazione</th>
      </tr>
      <tr>
         <td>PKey</td>
         <td>ID risorsa principale</td>
         <td>stringa </td>
         <td> </td>
      </tr>
      <tr>
         <td>additionalData</td>
         <td>Dati aggiuntivi</td>
         <td>raccolta </td>
         <td> </td>
      </tr>
      <tr>
         <td>additionalLanguages</td>
         <td>Altre lingue</td>
         <td>elemento </td>
         <td> </td>
      </tr>
      <tr>
         <td>allowNonIdentifiedTarget</td>
         <td>Autorizza visitatori non identificati</td>
         <td>booleano </td>
         <td> </td>
      </tr>
      <tr>
         <td>branding (brandingBase)</td>
         <td>Brand</td>
         <td>link </td>
         <td> </td>
      </tr>
      <tr>
         <td>predefinito</td>
         <td>Oggetto applicazione incorporato</td>
         <td>booleano </td>
         <td> </td>
      </tr>
      <tr>
         <td>cache</td>
         <td>Cache</td>
         <td>stringa </td>
         <td> </td>
      </tr>
      <tr>
         <td>campaign (campaignBase)</td>
         <td>Campaign</td>
         <td>link </td>
         <td> </td>
      </tr>
      <tr>
         <td>closedLog</td>
         <td>Registro "Pagina di destinazione chiusa"</td>
         <td>stringa </td>
         <td> </td>
      </tr>
      <tr>
         <td>contextResourceType</td>
         <td>TipoRisorsaContesto</td>
         <td>stringa </td>
         <td> </td>
      </tr>
      <tr>
         <td>creato</td>
         <td>Creato</td>
         <td>date </td>
         <td> </td>
      </tr>
      <tr>
         <td>createdBy (userBase)</td>
         <td>Creato da</td>
         <td>link </td>
         <td> </td>
      </tr>
      <tr>
         <td>cryptKey</td>
         <td>Chiave di crittografia AES</td>
         <td>stringa (64)</td>
         <td> </td>
      </tr>
      <tr>
         <td>defaultLanguage</td>
         <td>Lingua predefinita</td>
         <td>enumerazione (stringa) (255)</td>
         <td>
            <ul>
               <li>Greco - el - el</li>
               <li>Inglese - en - en</li>
               <li>Cinese - zh - zh</li>
               <li>Francese (Francia) - fr_FR - fr_FR</li>
               <li>Vietnamita - vi - vi</li>
               <li>Portoghese (Portogallo) - pt_PT - pt_PT</li>
               <li>Italiano (Italia) - it_IT - it_IT</li>
               <li>Italiano - it - it</li>
               <li>Olandese (Belgio) - nl_BE - nl_BE</li>
               <li>Norvegese (Norvegia) - no_NO - no_NO</li>
               <li>Olandese (Paesi Bassi) - nl_NL - nl_NL</li>
               <li>Arabo - ar - ar</li>
               <li>Inglese (Stati Uniti) - en_US - en_US</li>
               <li>Irlandese - ga - ga</li>
               <li>Ceco - cs - cs</li>
               <li>Estone - et - et</li>
               <li>Indonesiano - id - id</li>
               <li>Spagnolo - es - es</li>
               <li>Russo - ru - ru</li>
               <li>Olandese - nl - nl</li>
               <li>Vallonia - wa - wa</li>
               <li>Portoghese - pt - pt</li>
               <li>Francese (Belgio) - fr_BE - fr_BE</li>
               <li>Lettone - lv - lv</li>
               <li>Lituano - lt - lt</li>
               <li>Thailandese - th - th</li>
               <li>Inglese (Regno Unito) - en_GB - en_GB</li>
               <li>Francese - fr - fr</li>
               <li>Portoghese (Brasile) - pt_BR - pt_BR</li>
               <li>Tedesco - de - de</li>
               <li>Danese - da - da</li>
               <li>Finlandese - fi - fi</li>
               <li>Ungherese - hu - hu</li>
               <li>Svedese (Finlandia) - sv_FI - sv_FI</li>
               <li>Giapponese - ja - ja</li>
               <li>Ebraico - he - he</li>
               <li>Coreano - ko - ko</li>
               <li>Svedese - sv - sv</li>
               <li>Svezia (svedese) - sv_SE - sv_SE</li>
               <li>Slovacco - sk - sk</li>
               <li>Maltese - mt - mt</li>
               <li>Italiano (Svizzera) - it_CH - it_CH</li>
               <li>Polacco - pl - pl</li>
               <li>Sloveno - sl - sl</li>
               <li>VALORE NON VALIDO - __Valore_non valido__ - __Valore_non valido__</li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>defaultOrigin (delivery)</td>
         <td>Origine traffico</td>
         <td>link </td>
         <td> </td>
      </tr>
      <tr>
         <td>desc</td>
         <td>Descrizione</td>
         <td>stringa (512)</td>
         <td> </td>
      </tr>
      <tr>
         <td>designLanguage</td>
         <td>Lingua di progettazione</td>
         <td>enumerazione (stringa) (255)</td>
         <td>
            <ul>
               <li>Greco - el - el</li>
               <li>Inglese - en - en</li>
               <li>Cinese - zh - zh</li>
               <li>Francese (Francia) - fr_FR - fr_FR</li>
               <li>Vietnamita - vi - vi</li>
               <li>Portoghese (Portogallo) - pt_PT - pt_PT</li>
               <li>Italiano (Italia) - it_IT - it_IT</li>
               <li>Italiano - it - it</li>
               <li>Olandese (Belgio) - nl_BE - nl_BE</li>
               <li>Norvegese (Norvegia) - no_NO - no_NO</li>
               <li>Olandese (Paesi Bassi) - nl_NL - nl_NL</li>
               <li>Arabo - ar - ar</li>
               <li>Inglese (Stati Uniti) - en_US - en_US</li>
               <li>Irlandese - ga - ga</li>
               <li>Ceco - cs - cs</li>
               <li>Estone - et - et</li>
               <li>Indonesiano - id - id</li>
               <li>Spagnolo - es - es</li>
               <li>Russo - ru - ru</li>
               <li>Olandese - nl - nl</li>
               <li>Vallonia - wa - wa</li>
               <li>Portoghese - pt - pt</li>
               <li>Francese (Belgio) - fr_BE - fr_BE</li>
               <li>Lettone - lv - lv</li>
               <li>Lituano - lt - lt</li>
               <li>Thailandese - th - th</li>
               <li>Inglese (Regno Unito) - en_GB - en_GB</li>
               <li>Francese - fr - fr</li>
               <li>Portoghese (Brasile) - pt_BR - pt_BR</li>
               <li>Tedesco - de - de</li>
               <li>Danese - da - da</li>
               <li>Finlandese - fi - fi</li>
               <li>Ungherese - hu - hu</li>
               <li>Svedese (Finlandia) - sv_FI - sv_FI</li>
               <li>Giapponese - ja - ja</li>
               <li>Ebraico - he - he</li>
               <li>Coreano - ko - ko</li>
               <li>Svedese - sv - sv</li>
               <li>Svezia (svedese) - sv_SE - sv_SE</li>
               <li>Slovacco - sk - sk</li>
               <li>Maltese - mt - mt</li>
               <li>Italiano (Svizzera) - it_CH - it_CH</li>
               <li>Polacco - pl - pl</li>
               <li>Sloveno - sl - sl</li>
               <li>VALORE NON VALIDO - __Valore_non valido__ - __Valore_non valido__</li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>dynamicService</td>
         <td>Servizio dinamico</td>
         <td>booleano </td>
         <td> </td>
      </tr>
      <tr>
         <td>fine</td>
         <td>Data di scadenza</td>
         <td>date </td>
         <td> </td>
      </tr>
      <tr>
         <td>errorContextResourceType</td>
         <td>TipoRisorsaContestoErrore</td>
         <td>stringa </td>
         <td> </td>
      </tr>
      <tr>
         <td>errorPage</td>
         <td>Pagina di errore</td>
         <td>elemento </td>
         <td> </td>
      </tr>
      <tr>
         <td>geoUnit (geoUnitBase)</td>
         <td>Unità geografica</td>
         <td>link </td>
         <td> </td>
      </tr>
      <tr>
         <td>htmlPage</td>
         <td>Pagine</td>
         <td>raccolta </td>
         <td> </td>
      </tr>
      <tr>
         <td>identifierByUrlParam</td>
         <td>Identificazione tramite parametri URL</td>
         <td>booleano </td>
         <td> </td>
      </tr>
      <tr>
         <td>inactiveUrlRedirection</td>
         <td>URL di reindirizzamento</td>
         <td>stringa (4096)</td>
         <td> </td>
      </tr>
      <tr>
         <td>isExternal</td>
         <td>È una risorsa esterna</td>
         <td>booleano </td>
         <td> </td>
      </tr>
      <tr>
         <td>isTemplate</td>
         <td>Modello</td>
         <td>booleano </td>
         <td> </td>
      </tr>
      <tr>
         <td>processo</td>
         <td>Processo</td>
         <td>raccolta </td>
         <td> </td>
      </tr>
      <tr>
         <td>jobLogs</td>
         <td>Registri</td>
         <td>raccolta </td>
         <td> </td>
      </tr>
      <tr>
         <td>label</td>
         <td>Etichetta</td>
         <td>stringa (128)</td>
         <td> </td>
      </tr>
      <tr>
         <td>lastModified</td>
         <td>Ultima modifica</td>
         <td>date </td>
         <td> </td>
      </tr>
      <tr>
         <td>loadingFilter (queryFilterBase)</td>
         <td>Caricamento della chiave</td>
         <td>link </td>
         <td> </td>
      </tr>
      <tr>
         <td>loadingFilterMapping</td>
         <td>Parametri della chiave di caricamento</td>
         <td>raccolta </td>
         <td> </td>
      </tr>
      <tr>
         <td>logicalStatus</td>
         <td>Stato di esecuzione</td>
         <td>enumerazione (stringa) (255)</td>
         <td>
            <ul>
               <li>In corso - avviato - avviato</li>
               <li>Editing - edition - edition</li>
               <li>Finito - finito - finito</li>
               <li>Avviso - avviso - avviso</li>
               <li>Errato - Errore - Errore</li>
               <li>VALORE NON VALIDO - __Valore_non valido__ - __Valore_non valido__</li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>messageAction</td>
         <td>Inizia a inviare messaggio</td>
         <td>booleano </td>
         <td> </td>
      </tr>
      <tr>
         <td>messageActionDelivery (deliveryMCTemplateBase)</td>
         <td>Messaggio transazionale</td>
         <td>link </td>
         <td> </td>
      </tr>
      <tr>
         <td>modifiedBy (userBase)</td>
         <td>Modificato da</td>
         <td>link </td>
         <td> </td>
      </tr>
      <tr>
         <td>name</td>
         <td>ID</td>
         <td>stringa (64)</td>
         <td> </td>
      </tr>
      <tr>
         <td>orgUnit (orgUnitBase)</td>
         <td>Unità organizzativa</td>
         <td>link </td>
         <td> </td>
      </tr>
      <tr>
         <td>preriempimento</td>
         <td>Precarica dati visitatore</td>
         <td>booleano </td>
         <td> </td>
      </tr>
      <tr>
         <td>program (programBase)</td>
         <td>Programma</td>
         <td>link </td>
         <td> </td>
      </tr>
      <tr>
         <td>publicUrl</td>
         <td>URL pubblico</td>
         <td>stringa </td>
         <td> </td>
      </tr>
      <tr>
         <td>publicationDate</td>
         <td>Data pubblicazione</td>
         <td>date </td>
         <td> </td>
      </tr>
      <tr>
         <td>conciliationFilter (queryFilterBase)</td>
         <td>Chiave di riconciliazione</td>
         <td>link </td>
         <td> </td>
      </tr>
      <tr>
         <td>conciliationFilterMapping</td>
         <td>Parametri chiave riconciliazione</td>
         <td>raccolta </td>
         <td> </td>
      </tr>
      <tr>
         <td>conciliationUpdateStrategy</td>
         <td>Strategia di aggiornamento</td>
         <td>enumerazione (byte) </td>
         <td>
            <ul>
               <li>Update - updateTarget - 1</li>
               <li>Non autorizzato - non autorizzato - 0</li>
               <li>VALORE NON VALIDO - __Valore_non valido__ - __Valore_non valido__</li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>service (serviceBase)</td>
         <td>Servizio di abbonamento</td>
         <td>link </td>
         <td> </td>
      </tr>
      <tr>
         <td>specificAction</td>
         <td>Azione specifica</td>
         <td>enumerazione (byte) </td>
         <td>
            <ul>
               <li>Blacklist - blackList - 3</li>
               <li>Nessuna azione specifica - nessuno - 0</li>
               <li>Annullamento iscrizione - annullamento iscrizione - 2</li>
               <li>VALORE NON VALIDO - __Valore_non valido__ - __Valore_non valido__</li>
               <li>Abbonamento - abbonamento - 1</li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>inizio</td>
         <td>Data di distribuzione</td>
         <td>date </td>
         <td> </td>
      </tr>
      <tr>
         <td>stato</td>
         <td>Stato</td>
         <td>enumerazione (byte) </td>
         <td>
            <ul>
               <li>Modifica - modifica - 0</li>
               <li>Pubblicazione non riuscita - non riuscita - 99</li>
               <li>Chiuso - chiuso - 20</li>
               <li>VALORE NON VALIDO - __Valore_non valido__ - __Valore_non valido__</li>
               <li>Online - aperto - 10</li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>targetResource</td>
         <td>Dimensione targeting</td>
         <td>stringa (255)</td>
         <td> </td>
      </tr>
      <tr>
         <td>template (landingPage)</td>
         <td>Modello per pagina di destinazione</td>
         <td>link </td>
         <td> </td>
      </tr>
      <tr>
         <td>testUrl</td>
         <td>URL di prova</td>
         <td>stringa </td>
         <td> </td>
      </tr>
      <tr>
         <td>miniatura</td>
         <td>Miniatura</td>
         <td>stringa (255)</td>
         <td> </td>
      </tr>
      <tr>
         <td>fuso orario</td>
         <td>Fuso orario</td>
         <td>enumerazione (stringa) (64)</td>
         <td>
            <ul>
               <li>(GMT-02:00) Atlantico centrale - Atlantico_Georgia_del_Sud - Atlantico/Georgia_del_Sud</li>
               <li>(GMT+02:00) Amman - Asia_Amman - Asia/Amman</li>
               <li>(GMT-03:00) Brasi - America_Sao_Paulo - America/Sao_Paulo</li>
               <li>(GMT+06:00) Astana, Dacca - Asia_Dhaka - Asia/Dhaka</li>
               <li>(GMT+06:00) Novossibirsk - Asia_Novosibirsk - Asia/Novosibirsk</li>
               <li>(GMT+02:00) Windhoek - Africa_Windhoek - Africa/Windhoek</li>
               <li>(GMT+04:00) Caucaso, Erevan - Asia_Yerevan - Asia/Yerevan</li>
               <li>(GMT-04:00) Manaus - America_Manaus - America/Manaus</li>
               <li>(GMT+03:30) Teheran - Asia_Teheran - Asia/Teheran</li>
               <li>(GMT+12:00) Auckland, Wellington - Pacifico_Auckland - Pacifico/Auckland</li>
               <li>(GMT+02:00) Gerusalemme - Asia_Gerusalemme - Asia/Gerusalemme</li>
               <li>(GMT+03:00) Mosca, San Pietroburgo, Volgograd - Europa_Mosca - Europa/Mosca</li>
               <li>(GMT+09:30) Adelaïde - Australia_Adelaide - Australia/Adelaide</li>
               <li>(GMT+10:00) Canberra, Melbourne, Sydney - Australia_Canberra - Australia/Canberra</li>
               <li>(GMT+08:00) Perth - Australia_Perth - Australia/Perth</li>
               <li>(GMT+09:00) Yakoutsk - Asia_Yakutsk - Asia/Yakutsk</li>
               <li>(GMT-10:00) Hawai - Pacifico_Honolulu - Pacifico/Honolulu</li>
               <li>(GMT+04:00) Baku - Asia_Baku - Asia/Baku</li>
               <li>(GMT+10:00) Vladivostok - Asia_Vladivostok - Asia/Vladivostok</li>
               <li>(GMT+09:00) Seul - Asia_Seul - Asia/Seul</li>
               <li>(GMT+01:00) Sarajevo, Skoplje, Sofia, Varsavia, Zagabria - Europa_Sarajevo - Europa/Sarajevo</li>
               <li>Fuso orario del server - _server_ - _server_</li>
               <li>(GMT+04:00) Abu Dhabi, Muscat - Asia_Muscat - Asia/Mascate</li>
               <li>(GMT+08:00) Kuala Lumpur, Singapore - Asia_Kuala_Lumpur - Asia/Kuala_Lumpur</li>
               <li>(GMT+09:00) Osaka, Sapporo, Tokyo - Asia_Tokyo - Asia/Tokyo</li>
               <li>(GMT+10:00) Brisbane - Australia_Brisbane - Australia/Brisbane</li>
               <li>(GMT+05:30) Sri Jayawardenepura - Asia_Colombo - Asia/Colombo</li>
               <li>(GMT+02:00) Harare, Pretoria - Africa_Harare - Africa/Harare</li>
               <li>(GMT+08:00) Oulan-Bator - Asia_Ulan_Bator - Asia/Ulan_Bator</li>
               <li>(GMT-02:00) Ora di Greenwich meno 2 ore - Gmt_m2 - Etc/GMT+2</li>
               <li>(GMT-03:00) Ora di Greenwich meno 3 ore - Gmt_m3 - Etc/GMT+3</li>
               <li>(GMT-01:00) Ora di Greenwich meno 1 ora - Gmt_m1 - Etc/GMT+1</li>
               <li>(GMT-06:00) Ora di Greenwich meno 6 ore - Gmt_m6 - Etc/GMT+6</li>
               <li>(GMT-07:00) Ora di Greenwich meno 7 ore - Gmt_m7 - Etc/GMT+7</li>
               <li>(GMT-04:00) Ora di Greenwich meno 4 ore - Gmt_m4 - Etc/GMT+4</li>
               <li>(GMT) Casablanca - Africa_Casablanca - Africa/Casablanca</li>
               <li>(GMT+05:30) Calcutta, Chennai, Mumbai, Nuova Delhi - Asia_Calcutta - Asia/Calcutta</li>
               <li>(GMT-11:00) Ora di Greenwich meno 11 ore - Gmt_m11 - Etc/GMT+11</li>
               <li>(GMT-09:00) Ora di Greenwich meno 9 ore - Gmt_m9 - Etc/GMT+9</li>
               <li>(GMT-03:30) Terranova - America_St_Johns - America/St_Johns</li>
               <li>Predefinito - _inherit_ - _inherit_</li>
               <li>(GMT+03:00) Ora di Greenwich più 3 ore - Gmt_p3 - Etc/GMT-3</li>
               <li>(GMT-04:30) Caracas - America_Caracas - America/Caracas</li>
               <li>(GMT+01:00) Amsterdam, Berlino, Berna, Roma, Stoccolma, Vienna - Europa_Berlino - Europa/Berlino</li>
               <li>(GMT-07:00) Chihuahua, La Paz, Mazatlan - America_Chihuahua - America/Chihuahua</li>
               <li>(GMT+03:00) Nairobi - Africa_Nairobi - Africa/Nairobi</li>
               <li>(GMT-04:00) Asunción - America_Asuncion - America/Asuncion</li>
               <li>(GMT+03:00) Bagdad - Asia_Baghdad - Asia/Baghdad</li>
               <li>(GMT-10:00) Ora di Greenwich meno 10 ore - Gmt_m10 - Etc/GMT+10</li>
               <li>(GMT-03:00) Groenlandia - America_Godthab - America/Godthab</li>
               <li>(GMT+02:00) Damasco - Asia_Damascus - Asia/Damasco</li>
               <li>(GMT-11:00) Samoa - Pacifico_Samoa - Pacifico/Samoa</li>
               <li>(GMT-05:00) Bogota, Lima, Quito - America_Bogota - America/Bogota</li>
               <li>(GMT+01:00) Bruxelles, Copenaghen, Madrid, Parigi - Europa_Parigi - Europa/Parigi</li>
               <li>(GMT+08:00) Pechino, Chongqing, Hong Kong, Urumqi - Asia_Shanghai - Asia/Shanghai</li>
               <li>(GMT+12:00) Fidji - Pacifico_Figi - Pacifico/Figi</li>
               <li>(GMT+02:00) Atene, Istanbul, Minsk - Europa_Atene - Europa/Atene</li>
               <li>(GMT+04:00) Tbilisi - Asia_Tbilisi - Asia/Tbilisi</li>
               <li>VALORE NON VALIDO - __Valore_non valido__ - __Valore_non valido__</li>
               <li>(GMT+05:45) Katmandu - Asia_Katmandu - Asia/Katmandu</li>
               <li>(GMT-05:00) Indiana (Est) - America_Indianapolis - America/Indianapolis</li>
               <li>(GMT-01:00) Isole del Capo Verde - Atlantico_Capo_Verde - Atlantico/Capo_Verde</li>
               <li>(GMT+04:00) Port Louis - Indiano_Mauritius - Indiano/Mauritius</li>
               <li>(GMT+08:00) Taipei - Asia_Taipei - Asia/Taipei</li>
               <li>Fuso orario del database - _wdbc_ - _wdbc_</li>
               <li>(GMT+06:30) Rangoon - Asia_Rangoon - Asia/Rangoon</li>
               <li>(GMT+11:00) Magadan, Isole Salomone, Nuova Caledonia - Pacifico_Guadalcanal - Pacifico/Guadalcanal</li>
               <li>(GMT+02:00) Cairo - Africa_Cairo - Africa/Cairo</li>
               <li>(GMT+05:00) Iekaterinburg - Asia_Ekaterinburg - Asia/Ekaterinburg</li>
               <li>(GMT+08:00) Irkoutsk - Asia_Irkutsk - Asia/Irkutsk</li>
               <li>(GMT+10:00) Guam, Port Moresby - Pacific_Guam - Pacifico/Guam</li>
               <li>(GMT-04:00) Ora standard dell’Atlantico (Canada) - America_Halifax - America/Halifax</li>
               <li>(GMT) Ora di Greenwich - GMT - GMT</li>
               <li>(GMT-04:00) La Paz - America_La_Paz - America/La_Paz</li>
               <li>Fuso orario operatore - _login_ - _login_</li>
               <li>(GMT-06:00) Guadalajara, Messico, Monterrey - America_Città_del_Messico - America/Città_del_Messico</li>
               <li>(GMT+09:30) Darwin - Australia_Darwin - Australia/Darwin</li>
               <li>(GMT-05:00) Est (Stati Uniti e Canada) - America_New_York - America/New_York</li>
               <li>(GMT-05:00) Ora di Greenwich meno 5 ore - Gmt_m5 - Etc/GMT+5</li>
               <li>(GMT+05:00) Islamabad, Karachi, Tachkent - Asia_Karachi - Asia/Karachi</li>
               <li>(GMT+03:00) Koweït, Riyad - Asia_Riyadh - Asia/Riyadh</li>
               <li>(GMT-08:00) Ora di Greenwich meno 8 ore - Gmt_m8 - Etc/GMT+8</li>
               <li>(GMT-01:00) Azzorre - Atlantico_Azzorre - Atlantico/Azzorre</li>
               <li>(GMT+07:00) Bangkok, Hanoi, Djakarta - Asia_Bangkok - Asia/Bangkok</li>
               <li>(GMT) Monrovia - Africa_Monrovia - Africa/Monrovia</li>
               <li>(GMT-09:00) Alaska - America_Anchorage - America/Anchorage</li>
               <li>(GMT+01:00) Belgrado, Bratislava, Budapest, Lubiana, Praga - Europa_Belgrado - Europa/Belgrado</li>
               <li>(GMT) Reykjavik - Atlantico_Reykjavik - Atlantico/Reykjavik</li>
               <li>(GMT+02:00) Bucarest - Europa_Bucarest - Europa/Bucarest</li>
               <li>(GMT+05:00) Ora di Greenwich più 5 ore - Gmt_p5 - Etc/GMT-5</li>
               <li>(GMT+04:00) Ora di Greenwich più 4 ore - Gmt_p4 - Etc/GMT-4</li>
               <li>(GMT+07:00) Ora di Greenwich più 7 ore - Gmt_p7 - Etc/GMT-7</li>
               <li>(GMT+06:00) Ora di Greenwich più 6 ore - Gmt_p6 - Etc/GMT-6</li>
               <li>(GMT+01:00) Ora di Greenwich più 1 ora - Gmt_p1 - Etc/GMT-1</li>
               <li>(GMT-08:00) Pacifico (Stati Uniti e Canada) - America_Los_Angeles - America/Los_Angeles</li>
               <li>(GMT+02:00) Ora di Greenwich più 2 ore - Gmt_p2 - Etc/GMT-2</li>
               <li>(GMT+07:00) Krasnoïarsk - Asia_Krasnoyarsk - Asia/Krasnoyarsk</li>
               <li>(GMT+09:00) Ora di Greenwich più 9 ore - Gmt_p9 - Etc/GMT-9</li>
               <li>(GMT+08:00) Ora di Greenwich più 8 ore - Gmt_p8 - Etc/GMT-8</li>
               <li>(GMT+10:00) Hobart - Australia_Hobart - Australia/Hobart</li>
               <li>(GMT+13:00) Nuku’alofa - Pacifico_Tongatapu - Pacifico/Tongatapu</li>
               <li>(GMT-06:00) America centrale - America_Regina - America/Regina</li>
               <li>(GMT-03:00) Buenos Aires, Caienna, Fortaleza - America_Buenos_Aires - America/Buenos_Aires</li>
               <li>(GMT-07:00) Montagne Rocciose (Stati Uniti e Canada) - America_Denver - America/Denver</li>
               <li>(GMT+01:00) Africa centrale - Ovest - Africa_Luanda - Africa/Luanda</li>
               <li>(GMT+02:00) Helsinki, Kiev, Riga, Sofia, Tallinn, Vilnius - Europa_Helsinki - Europa/Helsinki</li>
               <li>(GMT) Ora di Greenwich: Dublino, Edimburgo, Lisbona, Londra - Europa_Londra - Europa/Londra</li>
               <li>(GMT-07:00) Arizona - America_Phoenix - America/Phoenix</li>
               <li>(GMT+02:00) Beirut - Asia_Beirut - Asia/Beirut</li>
               <li>(GMT+04:30) Kabul - Asia_Kabul - Asia/Kabul</li>
               <li>(GMT-06:00) Centro (Stati Uniti e Canada) - America_Chicago - America/Chicago</li>
               <li>(GMT+11:00) Ora di Greenwich più 11 ore - Gmt_p11 - Etc/GMT-11</li>
               <li>(GMT+10:00) Ora di Greenwich più 10 ore - Gmt_p10 - Etc/GMT-10</li>
               <li>(GMT+13:00) Ora di Greenwich più 13 ore - Gmt_p13 - Etc/GMT-13</li>
               <li>(GMT+12:00) Ora di Greenwich più 12 ore - Gmt_p12 - Etc/GMT-12</li>
               <li>(GMT-04:00) Santiago - America_Santiago - America/Santiago</li>
               <li>(GMT-03:00) Montevideo - America_Montevideo - America/Montevideo</li>
               <li>(GMT-04:00) Cuiaba - America_Cuiaba - America/Cuiaba</li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>title</td>
         <td>pagina di destinazione</td>
         <td>stringa (255)</td>
         <td> </td>
      </tr>
      <tr>
         <td>trackingEnabled</td>
         <td>Registro risposte</td>
         <td>booleano </td>
         <td> </td>
      </tr>
      <tr>
         <td>trackingUrlName</td>
         <td>Nome URL di tracciamento</td>
         <td>stringa </td>
         <td> </td>
      </tr>
      <tr>
         <td>tipo</td>
         <td>Tipo</td>
         <td>enumerazione (byte) </td>
         <td>
            <ul>
               <li>Generico - generico - 0</li>
               <li>Annullamento dell’abbonamento a un servizio - annullamento dell’abbonamento - 3</li>
               <li>Blacklist - blackList - 4</li>
               <li>VALORE NON VALIDO - __Valore_non valido__ - __Valore_non valido__</li>
               <li>Acquisizione - acquisizione - 1</li>
               <li>Abbonamento a un servizio - abbonamento - 2</li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>uuid</td>
         <td>ID sicurezza</td>
         <td>stringa </td>
         <td> </td>
      </tr>
      <tr>
         <td>webTrackingEnabled</td>
         <td>Abilita il tracciamento web</td>
         <td>booleano </td>
         <td> </td>
      </tr>
   </table>

## Filtri

Per stato logico (byLogicalStatus)

<table>
    <tr>
    <th>Nome</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>stato</td>
    <td>enumerazione</td>
    </tr>
</table>

Per nome o etichetta (byText)

<table>
    <tr>
    <th>Nome</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>text</td>
    <td>stringa</td>
    </tr>
</table>

Per stato (byState)

<table>
    <tr>
    <th>Nome</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>stato</td>
    <td>enumerazione</td>
    </tr>
</table>

Per risorsa targeting (byTargetResource)

<table>
<tr>
<th>Nome</th>
<th>Tipo</th>
</tr>
<tr>
<td>targetResource</td>
<td>stringa</td>
</tr>
</table>

Includi pagine di destinazione avanzate (conAvanzate)

<table>
    <tr>
    <th>Nome</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>avanzato</td>
    <td>booleano</td>
    </tr>
</table>

Includi consegne continue da un elenco eterogeneo (conContinuo)

<table>
        <tr>
        <th>Nome</th>
        <th>Tipo</th>
        </tr>
        <tr>
        <td>withContinuous</td>
        <td>booleano</td>
        </tr>
    </table>

Presente durante il periodo specificato (per calendario)

<table>
        <tr>
        <th>Nome</th>
        <th>Tipo</th>
        </tr>
        <tr>
        <td>startDate</td>
        <td>date</td>
        </tr>
        <tr>
        <td>endDate</td>
        <td>date</td>
        </tr>
    </table>

Pubblicato durante il periodo specificato (daPlanning)

<table>
    <tr>
    <th>Nome</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>startDate</td>
    <td>date</td>
    </tr>
    <tr>
    <td>endDate</td>
    <td>date</td>
    </tr>
</table>
