---
title: Cronologia marketing DataModel
description: Scopri il modello dati
audience: developing
content-type: reference
feature: Data Model
role: Developer
level: Experienced
exl-id: 7f2a3139-57eb-48ff-9b1a-ac2caad2f691
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '1347'
ht-degree: 9%

---

# Cronologia marketing (nms:history)

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
                  <td>età</td>
                  <td>Età</td>
                  <td>intero </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>bornDate</td>
                  <td>Data di nascita</td>
                  <td>data </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>blackList</td>
                  <td>Non contattare più (tramite nessun canale)</td>
                  <td>booleano </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>blackListEmail</td>
                  <td>Non contattare più tramite e-mail</td>
                  <td>booleano </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>blackListFax</td>
                  <td>Non contattare più via fax</td>
                  <td>booleano </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>blackListMobile</td>
                  <td>Non contattare più tramite SMS</td>
                  <td>booleano </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>blackListPhone</td>
                  <td>Non contattare più telefonicamente</td>
                  <td>booleano </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>blackListPostalMail</td>
                  <td>Non contattare più tramite direct mail</td>
                  <td>booleano </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>blackListPushnotification</td>
                  <td>Non contattare più tramite notifica push</td>
                  <td>booleano </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>countBroadLogEvents</td>
                  <td>CountBroadLogEvents</td>
                  <td>intero </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>countSubHistoEvents</td>
                  <td>CountSubHistoEvents</td>
                  <td>intero </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>paese (paesi)</td>
                  <td>Paese</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>countryIsoA2</td>
                  <td>Codice ISO A2</td>
                  <td>stringa (2)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>creato</td>
                  <td>Creato</td>
                  <td>data </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>createdBy (userBase)</td>
                  <td>Creato da</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>cusHobbieslink (cusHobbies)</td>
                  <td>CusHobbieslink</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>cusLastTransactionDate</td>
                  <td>Data ultima transazione</td>
                  <td>data </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>cusTransactionslink</td>
                  <td>Transazioni</td>
                  <td>raccolta </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>e-mail</td>
                  <td>E-mail</td>
                  <td>stringa (128)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>Eventi</td>
                  <td>Risorsa eterogenea</td>
                  <td>raccolta </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>fax</td>
                  <td>Fax</td>
                  <td>stringa (32)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>firstName</td>
                  <td>Nome</td>
                  <td>stringa (30)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>genere</td>
                  <td>Genere</td>
                  <td>enumerazione (byte) </td>
                  <td>
                     <ul>
                        <li>Non specificato - sconosciuto - 0</li>
                        <li>Maschio - maschio - 1</li>
                        <li>Femmina - femmina - 2</li>
                        <li>VALORE NON VALIDO - __Valore_non valido__ - __Valore_non valido__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>isExternal</td>
                  <td>È una risorsa esterna</td>
                  <td>booleano </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>kpiAndChart</td>
                  <td>KpiAndChart</td>
                  <td>elemento </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>lastModified</td>
                  <td>Ultima modifica</td>
                  <td>data </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>lastName</td>
                  <td>Cognome</td>
                  <td>stringa (50)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>posizione</td>
                  <td>Posizione</td>
                  <td>elemento </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>middleName</td>
                  <td>Secondo nome</td>
                  <td>stringa (30)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>minBroadLogEvents</td>
                  <td>MinBroadLogEvents</td>
                  <td>data </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>minSubHistoEvents</td>
                  <td>MinSubHistoEvents</td>
                  <td>data </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>mobilePhone</td>
                  <td>Mobile</td>
                  <td>stringa (32)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>modifiedBy (userBase)</td>
                  <td>Modificato da</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>telefono</td>
                  <td>Telefono</td>
                  <td>stringa (32)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>saluto</td>
                  <td>Titolo</td>
                  <td>stringa (20)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>stateLink (state)</td>
                  <td>Stato</td>
                  <td>link </td>
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
                        <li>(GMT+06:30) Rangoon - Asia_Rangoon - Asia/Rangoon</li>
                        <li>(GMT+11:00) Magadan, Isole Salomone, Nuova Caledonia - Pacifico_Guadalcanal - Pacifico/Guadalcanal</li>
                        <li>(GMT+02:00) Cairo - Africa_Cairo - Africa/Cairo</li>
                        <li>(GMT+05:00) Iekaterinburg - Asia_Ekaterinburg - Asia/Ekaterinburg</li>
                        <li>(GMT+08:00) Irkoutsk - Asia_Irkutsk - Asia/Irkutsk</li>
                        <li>(GMT+10:00) Guam, Port Moresby - Pacific_Guam - Pacifico/Guam</li>
                        <li>(GMT-04:00) Ora standard dell’Atlantico (Canada) - America_Halifax - America/Halifax</li>
                        <li>(GMT) Ora di Greenwich - GMT - GMT</li>
                        <li>Predefinito - nessuno - nessuno</li>
                        <li>(GMT-04:00) La Paz - America_La_Paz - America/La_Paz</li>
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
                  <td>titolo</td>
                  <td>Profilo</td>
                  <td>stringa (255)</td>
                  <td> </td>
               </tr>
            </table>

## Filtri

Compleanno (compleanno)

<table>
<tr>
<th>Nome</th>
<th>Tipo</th>
</tr>
<tr>
<td>includeStart</td>
<td>booleano</td>
</tr>
<tr>
<td>previousUnitsValue</td>
<td>intero</td>
</tr>
<tr>
<td>nextUnitsValue</td>
<td>intero</td>
</tr>
<tr>
<td>endDay</td>
<td>data</td>
</tr>
<tr>
<td>precisione</td>
<td>enumerazione</td>
</tr>
<tr>
<td>relativeValue</td>
<td>stringa</td>
</tr>
<tr>
<td>mese</td>
<td>data</td>
</tr>
<tr>
<td>operatore</td>
<td>enumerazione</td>
</tr>
<tr>
<td>includeEnd</td>
<td>booleano</td>
</tr>
<tr>
<td>endMonth</td>
<td>data</td>
</tr>
<tr>
<td>tipo</td>
<td>enumerazione</td>
</tr>
<tr>
<td>giorno</td>
<td>data</td>
</tr>
</table>

Per e-mail (byEmail)

<table>
<tr>
<th>Nome</th>
<th>Tipo</th>
</tr>
<tr>
<td>e-mail</td>
<td>stringa</td>
</tr>
</table>

Per chiavi (byKeysProfile)

<table>
<tr>
<th>Nome</th>
<th>Tipo</th>
</tr>
<tr>
<td>e-mail</td>
<td>stringa</td>
</tr>
</table>

Per nome o e-mail (byText)

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

Per pubblico statico (byStaticAudience)

<table>
<tr>
<th>Nome</th>
<th>Tipo</th>
</tr>
<tr>
<td>pubblico</td>
<td>link</td>
</tr>
</table>

Clic effettuato (hasClickedDelivery)

<table>
<tr>
<th>Nome</th>
<th>Tipo</th>
</tr>
<tr>
<td>consegna</td>
<td>link</td>
</tr>
</table>

Aperto (hasOpenedDelivery)

<table>
<tr>
<th>Nome</th>
<th>Tipo</th>
</tr>
<tr>
<td>consegna</td>
<td>link</td>
</tr>
</table>

Profilo (profilo)

<table>
<tr>
<th>Nome</th>
<th>Tipo</th>
</tr>
<tr>
<td>profilo</td>
<td>link</td>
</tr>
</table>

Received (hasReceivedDelivery)

<table>
<tr>
<th>Nome</th>
<th>Tipo</th>
</tr>
<tr>
<td>consegna</td>
<td>link</td>
</tr>
</table>

Abbonati (subscribers)

<table>
<tr>
<th>Nome</th>
<th>Tipo</th>
</tr>
<tr>
<td>servizio</td>
<td>link</td>
</tr>
</table>
