---
title: DataModel
description: Scopri il modello dati
page-status-flag: never-activated
uuid: 99277e46-e4f7-49a9-ba27-b878780f90da
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: designing
content-type: reference
topic-tags: editing-sms-and-push-content
discoiquuid: 6e21db35-daf9-4edb-977a-6ef606db0e4d
context-tags: delivery,smsContent,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 18d9b33e36db628ef1fc014e4abe6a4a7eef48b3

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
         <td>string </td>
         <td> </td>
      </tr>
      <tr>
         <td>AdditionalData</td>
         <td>Dati aggiuntivi</td>
         <td>collection </td>
         <td> </td>
      </tr>
      <tr>
         <td>AdditionalLanguages</td>
         <td>Altre lingue</td>
         <td>item </td>
         <td> </td>
      </tr>
      <tr>
         <td>allowNonIdentifiedTarget</td>
         <td>Autorizzare visitatori non identificati</td>
         <td>boolean </td>
         <td> </td>
      </tr>
      <tr>
         <td>branding (brandingBase)</td>
         <td>Marchio</td>
         <td>link </td>
         <td> </td>
      </tr>
      <tr>
         <td>buildIn</td>
         <td>Oggetto applicazione predefinito</td>
         <td>boolean </td>
         <td> </td>
      </tr>
      <tr>
         <td>cache</td>
         <td>Cache</td>
         <td>string </td>
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
         <td>Registro 'Pagina di destinazione chiusa'</td>
         <td>string </td>
         <td> </td>
      </tr>
      <tr>
         <td>contextResourceType</td>
         <td>ContextResourceType</td>
         <td>string </td>
         <td> </td>
      </tr>
      <tr>
         <td>created</td>
         <td>Creato</td>
         <td>date </td>
         <td> </td>
      </tr>
      <tr>
         <td>createBy (userBase)</td>
         <td>Creato da</td>
         <td>link </td>
         <td> </td>
      </tr>
      <tr>
         <td>cryptKey</td>
         <td>Chiave di crittografia AES</td>
         <td>string (64)</td>
         <td> </td>
      </tr>
      <tr>
         <td>defaultLanguage</td>
         <td>Linguaggio predefinito</td>
         <td>enumerazione (stringa) (255)</td>
         <td>
            <ul>
               <li>Grecia - el - el</li>
               <li>Inglese - en - en</li>
               <li>Cinese - zh - zh</li>
               <li>Francese (Francia) - fr_FR - fr_FR</li>
               <li>Vietnamita - vi - vi</li>
               <li>Portoghese (Portogallo) - pt_PT - pt_PT</li>
               <li>Italiano (Italia) - it_IT - it_IT</li>
               <li>Italiano - it</li>
               <li>Olandese (Belgio) - nl_BE - nl_BE</li>
               <li>Norvegese (Norvegia) - no_NO - no_NO</li>
               <li>Olandese (Paesi Bassi) - nl_NL - nl_NL</li>
               <li>Arabo - ar - ar</li>
               <li>Inglese (Stati Uniti) - en_US - en_US</li>
               <li>Irlandese - ga</li>
               <li>Ceco - cs - cs</li>
               <li>Estone - et - et - et</li>
               <li>Indonesiano - id - id</li>
               <li>Spagnolo - es - es</li>
               <li>Russo - ru - ru</li>
               <li>Olandese - nl - nl</li>
               <li>Vallonia - wa - wa</li>
               <li>Portoghese - pt - pt</li>
               <li>Francese (Belgio) - fr_BE - fr_BE</li>
               <li>Lettone - lv - lv</li>
               <li>Lituano - lt - lt</li>
               <li>Thai - th - th</li>
               <li>Inglese (Regno Unito) - en_GB - en_GB</li>
               <li>Francese - fr</li>
               <li>Portoghese (Brasile) - pt_BR - pt_BR</li>
               <li>tedesco - de - de</li>
               <li>Danese - da - da</li>
               <li>Finlandese - fi - fi</li>
               <li>Ungherese - hu - hu</li>
               <li>Svedese (Finlandia) - sv_FI - sv_FI</li>
               <li>Giapponese - ja - ja</li>
               <li>"Ebraico - egli -"</li>
               <li>Coreano - ko - ko</li>
               <li>Svedese - sv - sv</li>
               <li>Svezia (svedese) - sv_SE - sv_SE</li>
               <li>Slovacco - sk - sk</li>
               <li>Malta - mt - mt</li>
               <li>Italiano (Svizzera) - it_CH - it_CH</li>
               <li>Polacco - pl - pl</li>
               <li>Slovene - sl - sl</li>
               <li>VALORE INVALID - __Invalid_value__ - __Invalid_value___</li>
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
         <td>string (512)</td>
         <td> </td>
      </tr>
      <tr>
         <td>designLanguage</td>
         <td>Lingua di progettazione</td>
         <td>enumerazione (stringa) (255)</td>
         <td>
            <ul>
               <li>Grecia - el - el</li>
               <li>Inglese - en - en</li>
               <li>Cinese - zh - zh</li>
               <li>Francese (Francia) - fr_FR - fr_FR</li>
               <li>Vietnamita - vi - vi</li>
               <li>Portoghese (Portogallo) - pt_PT - pt_PT</li>
               <li>Italiano (Italia) - it_IT - it_IT</li>
               <li>Italiano - it</li>
               <li>Olandese (Belgio) - nl_BE - nl_BE</li>
               <li>Norvegese (Norvegia) - no_NO - no_NO</li>
               <li>Olandese (Paesi Bassi) - nl_NL - nl_NL</li>
               <li>Arabo - ar - ar</li>
               <li>Inglese (Stati Uniti) - en_US - en_US</li>
               <li>Irlandese - ga</li>
               <li>Ceco - cs - cs</li>
               <li>Estone - et - et - et</li>
               <li>Indonesiano - id - id</li>
               <li>Spagnolo - es - es</li>
               <li>Russo - ru - ru</li>
               <li>Olandese - nl - nl</li>
               <li>Vallonia - wa - wa</li>
               <li>Portoghese - pt - pt</li>
               <li>Francese (Belgio) - fr_BE - fr_BE</li>
               <li>Lettone - lv - lv</li>
               <li>Lituano - lt - lt</li>
               <li>Thai - th - th</li>
               <li>Inglese (Regno Unito) - en_GB - en_GB</li>
               <li>Francese - fr</li>
               <li>Portoghese (Brasile) - pt_BR - pt_BR</li>
               <li>tedesco - de - de</li>
               <li>Danese - da - da</li>
               <li>Finlandese - fi - fi</li>
               <li>Ungherese - hu - hu</li>
               <li>Svedese (Finlandia) - sv_FI - sv_FI</li>
               <li>Giapponese - ja - ja</li>
               <li>"Ebraico - egli -"</li>
               <li>Coreano - ko - ko</li>
               <li>Svedese - sv - sv</li>
               <li>Svezia (svedese) - sv_SE - sv_SE</li>
               <li>Slovacco - sk - sk</li>
               <li>Malta - mt - mt</li>
               <li>Italiano (Svizzera) - it_CH - it_CH</li>
               <li>Polacco - pl - pl</li>
               <li>Slovene - sl - sl</li>
               <li>VALORE INVALID - __Invalid_value__ - __Invalid_value___</li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>dynamicService</td>
         <td>Servizio dinamico</td>
         <td>boolean </td>
         <td> </td>
      </tr>
      <tr>
         <td>end</td>
         <td>Data di scadenza</td>
         <td>date </td>
         <td> </td>
      </tr>
      <tr>
         <td>errorContextResourceType</td>
         <td>ErrorContextResourceType</td>
         <td>string </td>
         <td> </td>
      </tr>
      <tr>
         <td>errorPage</td>
         <td>Pagina di errore</td>
         <td>item </td>
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
         <td>collection </td>
         <td> </td>
      </tr>
      <tr>
         <td>IdentificationByUrlParam</td>
         <td>Identificazione tramite parametri URL</td>
         <td>boolean </td>
         <td> </td>
      </tr>
      <tr>
         <td>inactiveUrlRedirection</td>
         <td>URL di reindirizzamento</td>
         <td>string (4096)</td>
         <td> </td>
      </tr>
      <tr>
         <td>isExternal</td>
         <td>È una risorsa esterna</td>
         <td>boolean </td>
         <td> </td>
      </tr>
      <tr>
         <td>isTemplate</td>
         <td>Modello</td>
         <td>boolean </td>
         <td> </td>
      </tr>
      <tr>
         <td>job</td>
         <td>Job</td>
         <td>collection </td>
         <td> </td>
      </tr>
      <tr>
         <td>jobLogs</td>
         <td>Registri</td>
         <td>collection </td>
         <td> </td>
      </tr>
      <tr>
         <td>label</td>
         <td>Etichetta</td>
         <td>string (128)</td>
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
         <td>Tasto di caricamento</td>
         <td>link </td>
         <td> </td>
      </tr>
      <tr>
         <td>loadingFilterMapping</td>
         <td>Parametri del tasto di caricamento</td>
         <td>collection </td>
         <td> </td>
      </tr>
      <tr>
         <td>logicalStatus</td>
         <td>Stato esecuzione</td>
         <td>enumerazione (stringa) (255)</td>
         <td>
            <ul>
               <li>In corso - avviato - avviato</li>
               <li>Editing - edizione</li>
               <li>Finito - finito - finito</li>
               <li>Avviso - Avviso</li>
               <li>Erroneo - errore - errore</li>
               <li>VALORE INVALID - __Invalid_value__ - __Invalid_value___</li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>messageAction</td>
         <td>Avvia messaggio di invio</td>
         <td>boolean </td>
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
         <td>string (64)</td>
         <td> </td>
      </tr>
      <tr>
         <td>orgUnit (orgUnitBase)</td>
         <td>Unità organizzativa</td>
         <td>link </td>
         <td> </td>
      </tr>
      <tr>
         <td>precompilare</td>
         <td>Precaricare i dati dei visitatori</td>
         <td>boolean </td>
         <td> </td>
      </tr>
      <tr>
         <td>program (programBase)</td>
         <td>Program</td>
         <td>link </td>
         <td> </td>
      </tr>
      <tr>
         <td>publicUrl</td>
         <td>URL pubblico</td>
         <td>string </td>
         <td> </td>
      </tr>
      <tr>
         <td>publicationDate</td>
         <td>Data pubblicazione</td>
         <td>date </td>
         <td> </td>
      </tr>
      <tr>
         <td>riconciliazioneFilter (queryFilterBase)</td>
         <td>Chiave di riconciliazione</td>
         <td>link </td>
         <td> </td>
      </tr>
      <tr>
         <td>riconciliazioneFilterMapping</td>
         <td>Parametri chiave di riconciliazione</td>
         <td>collection </td>
         <td> </td>
      </tr>
      <tr>
         <td>riconciliazioneUpdateStrategy</td>
         <td>Strategia di aggiornamento</td>
         <td>enumerazione (byte) </td>
         <td>
            <ul>
               <li>Aggiornamento - updateTarget - 1</li>
               <li>Non autorizzato - non autorizzato - 0</li>
               <li>VALORE INVALID - __Invalid_value__ - __Invalid_value___</li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>service (serviceBase)</td>
         <td>Servizio di iscrizione</td>
         <td>link </td>
         <td> </td>
      </tr>
      <tr>
         <td>specificAction</td>
         <td>Azione specifica</td>
         <td>enumerazione (byte) </td>
         <td>
            <ul>
               <li>Lista nera - 3</li>
               <li>Nessuna azione specifica - Nessuno - 0</li>
               <li>Annullamento sottoscrizione - annullamento sottoscrizione - 2</li>
               <li>VALORE INVALID - __Invalid_value__ - __Invalid_value___</li>
               <li>Iscrizione - Iscrizione - 1</li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>start</td>
         <td>Data di distribuzione</td>
         <td>date </td>
         <td> </td>
      </tr>
      <tr>
         <td>state</td>
         <td>Stato</td>
         <td>enumerazione (byte) </td>
         <td>
            <ul>
               <li>Modifica - Modifica - 0</li>
               <li>Pubblicazione non riuscita - non riuscita - 99</li>
               <li>Chiuso - chiuso - 20</li>
               <li>VALORE INVALID - __Invalid_value__ - __Invalid_value___</li>
               <li>Online - aperto - 10</li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>targetResource</td>
         <td>Dimensioni di targeting</td>
         <td>string (255)</td>
         <td> </td>
      </tr>
      <tr>
         <td>template (landingPage)</td>
         <td>Modello pagina di destinazione</td>
         <td>link </td>
         <td> </td>
      </tr>
      <tr>
         <td>testUrl</td>
         <td>URL test</td>
         <td>string </td>
         <td> </td>
      </tr>
      <tr>
         <td>thumbnail</td>
         <td>Miniatura</td>
         <td>string (255)</td>
         <td> </td>
      </tr>
      <tr>
         <td>timezone</td>
         <td>Fuso orario</td>
         <td>enumerazione (stringa) (64)</td>
         <td>
            <ul>
               <li>(GMT-02:00) Atlantico centrale - Atlantico meridionale - Atlantico meridionale - Atlantico/Georgia meridionale</li>
               <li>(GMT+02:00) Amman - Asia_Amman - Asia/Amman</li>
               <li>(GMT-03:00) Brasi - America_Sao_Paulo - America/Sao_Paulo</li>
               <li>(GMT+06:00) Astana, Dacca - Asia_Dhaka - Asia/Dhaka</li>
               <li>(GMT+06:00) Novossibirsk - Asia_Novosibirsk - Asia/Novosibirsk</li>
               <li>(GMT+02:00) Windhoek - Africa_Windhoek - Africa/Windhoek</li>
               <li>(GMT+04:00) Caucaso, Erevan - Asia_Yerevan - Asia/Yerevan</li>
               <li>(GMT-04:00) Manaus - America_Manaus - America/Manaus</li>
               <li>(GMT+03:30) Teheran - Asia_Teheran - Asia/Teheran</li>
               <li>(GMT+12:00) Auckland, Wellington - Pacific_Auckland - Pacific/Auckland</li>
               <li>(GMT+02:00) Gerusalemme - Asia_Gerusalemme - Asia/Gerusalemme</li>
               <li>(GMT+03:00) Mosca, San Pietroburgo, Volgograd - Europa_Mosca - Europa/Mosca</li>
               <li>(GMT+09:30) Adelaïde - Australia_Adelaide - Australia/Adelaide</li>
               <li>(GMT+10:00) Canberra, Melbourne, Sydney - Australia_Canberra - Australia/Canberra</li>
               <li>(GMT+08:00) Perth - Australia_Perth - Australia/Perth</li>
               <li>(GMT+09:00) Yakoutsk - Asia_Yakutsk - Asia/Yakutsk</li>
               <li>(GMT-10:00) Hawai - Pacific_Honolulu - Pacific/Honolulu</li>
               <li>(GMT+04:00) Baku - Asia_Baku - Asia/Baku</li>
               <li>(GMT+10:00) Vladivostok - Asia_Vladivostok - Asia/Vladivostok</li>
               <li>(GMT+09:00) Seoul - Asia_Seoul - Asia/Seoul</li>
               <li>(GMT+01:00) Sarajevo, Skoplje, Sofia, Varsavia, Zagabria - Europa_Sarajevo - Europa/Sarajevo</li>
               <li>Fuso orario server - _server_ - _server_</li>
               <li>(GMT+04:00) Abu Dhabi, Muscat - Asia_Muscat - Asia/Muscat</li>
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
               <li>(GMT+05:30) Calcutta, Chennai, Mumbai, Nuova Delhi - Asia_Kolkata - Asia/Calcutta</li>
               <li>(GMT-11:00) Ora di Greenwich meno 11 ore - Gmt_m11 - Etc/GMT+11</li>
               <li>(GMT-09:00) Ora di Greenwich meno 9 ore - Gmt_m9 - Etc/GMT+9</li>
               <li>(GMT-03:30) Terranova - America_St_Johns - America/St_Johns</li>
               <li>Valore predefinito - _inherit_ - _inherit_</li>
               <li>(GMT+03:00) Ora di Greenwich più 3 ore - Gmt_p3 - Etc/GMT-3</li>
               <li>(GMT-04:30) Caracas - America_Caracas - America/Caracas</li>
               <li>(GMT+01:00) Amsterdam, Berlino, Berna, Roma, Stoccolma, Vienna - Europa_Berlino - Europa/Berlino</li>
               <li>(GMT-07:00) Chihuahua, La Paz, Mazatlan - America_Chihuahua - America/Chihuahua</li>
               <li>(GMT+03:00) Nairobi - Africa_Nairobi - Africa/Nairobi</li>
               <li>(GMT-04:00) Asunción - America_Asuncion - America/Asuncion</li>
               <li>(GMT+03:00) Bagdad - Asia_Baghdad - Asia/Baghdad</li>
               <li>(GMT-10:00) Ora di Greenwich meno 10 ore - Gmt_m10 - Etc/GMT+10</li>
               <li>(GMT-03:00) Groenlandia - America_Godthab - America/Godthab</li>
               <li>(GMT+02:00) Damas - Asia_Damasco - Asia/Damasco</li>
               <li>(GMT-11:00) Samoa - Pacific_Samoa - Pacific/Samoa</li>
               <li>(GMT-05:00) Bogota, Lima, Quito - America_Bogota - America/Bogota</li>
               <li>(GMT+01:00) Bruxelles, Copenaghen, Madrid, Parigi - Europa_Parigi - Europa/Parigi</li>
               <li>(GMT+08:00) Pechino, Chongqing, Hong Kong, Urumqi - Asia_Shanghai - Asia/Shanghai</li>
               <li>(GMT+12:00) Fidji - Pacific_Fiji - Pacific/Fiji</li>
               <li>(GMT+02:00) Atene, Istanbul, Minsk - Europa_Atene - Europa/Atene</li>
               <li>(GMT+04:00) Tbilisi - Asia_Tbilisi - Asia/Tbilisi</li>
               <li>VALORE INVALID - __Invalid_value__ - __Invalid_value___</li>
               <li>(GMT+05:45) Katmandu - Asia_Katmandu - Asia/Katmandu</li>
               <li>(GMT-05:00) Indiana (Est) - America_Indianapolis - America/Indianapolis</li>
               <li>(GMT-01:00) Isole del Capo Verde - Atlantic_Cape_Verde - Atlantic/Cape_Verde</li>
               <li>(GMT+04:00) Port Louis - Indian_Mauritius - Indian/Mauritius</li>
               <li>(GMT+08:00) Taipei - Asia_Taipei - Asia/Taipei</li>
               <li>Fuso orario del database - _wdbc_ - _wdbc_</li>
               <li>(GMT+06:30) Rangoon - Asia_Rangoon - Asia/Rangoon</li>
               <li>(GMT+11:00) Magadan, Isole Salomone, Nuova Caledonia - Pacific_Guadalcanal - Pacific/Guadalcanal</li>
               <li>(GMT+02:00) Cairo - Africa_Cairo - Africa/Cairo</li>
               <li>(GMT+05:00) Iekaterinburg - Asia_Yekaterinburg - Asia/Yekaterinburg</li>
               <li>(GMT+08:00) Irkoutsk - Asia_Irkutsk - Asia/Irkutsk</li>
               <li>(GMT+10:00) Guam, Port Moresby - Pacific_Guam - Pacific/Guam</li>
               <li>(GMT-04:00) Ora solare Atlantico (Canada) - America_Halifax - America/Halifax</li>
               <li>(GMT) Ora media Greenwich - GMT - GMT</li>
               <li>(GMT-04:00) La Paz - America_La_Paz - America/La_Paz</li>
               <li>Fuso orario dell'operatore - _login_ - _login_</li>
               <li>(GMT-06:00) Guadalajara, Messico, Monterrey - America_Messico_City - America/Città del Messico</li>
               <li>(GMT+09:30) Darwin - Australia_Darwin - Australia/Darwin</li>
               <li>(GMT-05:00) Est (Stati Uniti e Canada) - America_New_York - America/New_York</li>
               <li>(GMT-05:00) Ora di Greenwich meno 5 ore - Gmt_m5 - Etc/GMT+5</li>
               <li>(GMT+05:00) Islamabad, Karachi, Tachkent - Asia_Karachi - Asia/Karachi</li>
               <li>(GMT+03:00) Koweït, Riyad - Asia_Riyadh - Asia/Riyadh</li>
               <li>(GMT-08:00) Ora di Greenwich meno 8 ore - Gmt_m8 - Etc/GMT+8</li>
               <li>(GMT-01:00) Le Azzorre - Atlantic_Azores - Atlantic/Azores</li>
               <li>(GMT+07:00) Bangkok, Hanoi, Djakarta - Asia_Bangkok - Asia/Bangkok</li>
               <li>(GMT) Monrovia - Africa_Monrovia - Africa/Monrovia</li>
               <li>(GMT-09:00) Alaska - America_Anchorage - America/Ancoraggio</li>
               <li>(GMT+01:00) Belgrado, Bratislava, Budapest, Lubiana, Praga - Europa_Belgrado - Europa/Belgrado</li>
               <li>(GMT) Reykjavik - Atlantic_Reykjavik - Atlantic/Reykjavik</li>
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
               <li>(GMT+13:00) Nuku'alofa - Pacific_Tongatapu - Pacific/Tongatapu</li>
               <li>(GMT-06:00) America centrale - America_Regina - America/Regina</li>
               <li>(GMT-03:00) Buenos Aires, Cayenne, Fortaleza - America_Buenos_Aires - America/Buenos_Aires</li>
               <li>(GMT-07:00) Montagne Rocciose (Stati Uniti e Canada) - America_Denver - America/Denver</li>
               <li>(GMT+01:00) Africa centrale - Ovest - Africa_Luanda - Africa/Luanda</li>
               <li>(GMT+02:00) Helsinki, Kiev, Riga, Sofia, Tallinn, Vilnius - Europe_Helsinki - Europa/Helsinki</li>
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
         <td>Pagina di destinazione</td>
         <td>string (255)</td>
         <td> </td>
      </tr>
      <tr>
         <td>trackingEnabled</td>
         <td>Risposte ai registri</td>
         <td>boolean </td>
         <td> </td>
      </tr>
      <tr>
         <td>trackingUrlName</td>
         <td>Nome URL tracciamento</td>
         <td>string </td>
         <td> </td>
      </tr>
      <tr>
         <td>type</td>
         <td>Tipo</td>
         <td>enumerazione (byte) </td>
         <td>
            <ul>
               <li>Generico - generico - 0</li>
               <li>Annullamento dell'iscrizione da un servizio - annullamento dell'iscrizione - 3</li>
               <li>Lista nera - lista nera - 4</li>
               <li>VALORE INVALID - __Invalid_value__ - __Invalid_value___</li>
               <li>Acquisizione - acquisizione - 1</li>
               <li>Iscrizione a un servizio - iscrizione - 2</li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>uuid</td>
         <td>ID protezione</td>
         <td>string </td>
         <td> </td>
      </tr>
      <tr>
         <td>webTrackingEnabled</td>
         <td>Abilita tracciamento Web</td>
         <td>boolean </td>
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
    <td>state</td>
    <td>enumerazione</td>
    </tr>
</table>

Per nome o etichetta (per testo)

<table>
    <tr>
    <th>Nome</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>text</td>
    <td>string</td>
    </tr>
</table>

Per stato (per stato)

<table>
    <tr>
    <th>Nome</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>state</td>
    <td>enumerazione</td>
    </tr>
</table>

Per targeting della risorsa (perTargetResource)

<table>
<tr>
<th>Nome</th>
<th>Tipo</th>
</tr>
<tr>
<td>targetResource</td>
<td>string</td>
</tr>
</table>

Includi pagine di destinazione avanzate (con Advanced)

<table>
    <tr>
    <th>Nome</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>avanzato</td>
    <td>boolean</td>
    </tr>
</table>

Includi consegne continue da un elenco eterogeneo (con Continuous)

<table>
        <tr>
        <th>Nome</th>
        <th>Tipo</th>
        </tr>
        <tr>
        <td>withContinuous</td>
        <td>boolean</td>
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

Pubblicato durante il periodo specificato (tramite Pianificazione)

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
