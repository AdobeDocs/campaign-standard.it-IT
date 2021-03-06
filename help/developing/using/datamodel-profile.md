---
title: Profilo DataModel
description: Scopri il modello dati
audience: developing
content-type: reference
feature: Data Model
role: Developer
level: Experienced
exl-id: 652c22a5-7fff-4d08-9396-f0b292aaca76
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '1249'
ht-degree: 4%

---

# Profilo (nms:recipient)

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
                  <td>età</td>
                  <td>Età</td>
                  <td>integer </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>appSubscription</td>
                  <td>Abbonamenti a un’applicazione</td>
                  <td>raccolta </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>datadina</td>
                  <td>Data di nascita</td>
                  <td>date </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>blackList</td>
                  <td>Nessun contatto (da qualsiasi canale)</td>
                  <td>booleano </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>blackListEmail</td>
                  <td>Nessun contatto tramite e-mail</td>
                  <td>booleano </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>blackListFax</td>
                  <td>Non più contattare via fax</td>
                  <td>booleano </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>blackListMobile</td>
                  <td>Nessun contatto più tramite SMS</td>
                  <td>booleano </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>blackListPhone</td>
                  <td>Nessun contatto più telefonico</td>
                  <td>booleano </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>blackListPostalMail</td>
                  <td>Nessun contatto tramite direct mailing</td>
                  <td>booleano </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>blackListPushnotification</td>
                  <td>Nessun contatto più tramite notifica push</td>
                  <td>booleano </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>paese (paesi)</td>
                  <td>Paese</td>
                  <td>collegamento </td>
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
                  <td>collegamento </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>cryptedId</td>
                  <td>ID crittografato</td>
                  <td>string </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>cusHobbieslink (cusHobbies)</td>
                  <td>CusHobbieslink</td>
                  <td>collegamento </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>cusLastTransactionDate</td>
                  <td>Data ultima transazione</td>
                  <td>date </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>cusTransactionslink</td>
                  <td>Transazioni</td>
                  <td>raccolta </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>dominio</td>
                  <td>Dominio e-mail</td>
                  <td>string (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>e-mail</td>
                  <td>E-mail</td>
                  <td>string (128)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>emailFormat</td>
                  <td>Formato e-mail</td>
                  <td>enumerazione (byte) </td>
                  <td>
                     <ul>
                        <li>Testo - testo - 1</li>
                        <li>HTML - html - 2</li>
                        <li>VALORE NON VALIDO - __Invalid_value__ - __Invalid_value__</li>
                        <li>Sconosciuto - sconosciuto - 0</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>emailStatus (addressStatus)</td>
                  <td>Informazioni sull’e-mail</td>
                  <td>collegamento </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>excludeLogs</td>
                  <td>Log di esclusione</td>
                  <td>raccolta </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>externalId</td>
                  <td>ID risorsa esterna</td>
                  <td>string(100) </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>fax</td>
                  <td>Fax</td>
                  <td>string (32)</td>
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
                        <li>VALORE NON VALIDO - __Invalid_value__ - __Invalid_value__</li>
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
                  <td>lastModified</td>
                  <td>Ultima modifica</td>
                  <td>date </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>lastName</td>
                  <td>Cognome</td>
                  <td>string (50)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>posizione</td>
                  <td>Posizione</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>logs</td>
                  <td>Log di consegna</td>
                  <td>raccolta </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>middleName</td>
                  <td>Nome centrale</td>
                  <td>stringa (30)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>mobilePhone</td>
                  <td>Mobile</td>
                  <td>string (32)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>modifiedBy (userBase)</td>
                  <td>Modificato da</td>
                  <td>collegamento </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>telefono</td>
                  <td>Telefono</td>
                  <td>string (32)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>luoghi</td>
                  <td>Posizioni</td>
                  <td>raccolta </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>postalAddress</td>
                  <td>Indirizzo postale</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>saluto</td>
                  <td>Titolo</td>
                  <td>string (20)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>stateLink (stato)</td>
                  <td>Stato</td>
                  <td>collegamento </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>subHisto</td>
                  <td>Storico sottoscrizioni</td>
                  <td>raccolta </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>abbonamenti</td>
                  <td>Abbonamenti</td>
                  <td>raccolta </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>miniatura</td>
                  <td>Miniatura</td>
                  <td>string (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>timeZone</td>
                  <td>Fuso orario</td>
                  <td>enumerazione (stringa) (64)</td>
                  <td>
                     <ul>
                        <li>(GMT-02.00) Atlantico centrale - Atlantico_Sud_Georgia - Atlantico/Georgia meridionale</li>
                        <li>(GMT+02.00) Amman - Asia_Amman - Asia/Amman</li>
                        <li>(GMT-03.00) Brasi - America_Sao_Paulo - America/Sao_Paulo</li>
                        <li>(GMT+06.00) Astana, Dhaka - Asia_Dhaka - Asia/Dhaka</li>
                        <li>(GMT+06.00) Novossibirsk - Asia_Novosibirsk - Asia/Novosibirsk</li>
                        <li>(GMT+02.00) Windhoek - Africa_Windhoek - Africa/Windhoek</li>
                        <li>(GMT+04.00) Caucaso, Erevan - Asia_Yerevan - Asia/Yerevan</li>
                        <li>(GMT-04.00) Manaus - America_Manaus - America/Manaus</li>
                        <li>(GMT+03.30) Teheran - Asia_Teheran - Asia/Teheran</li>
                        <li>(GMT+12.00) Auckland, Wellington - Pacific_Auckland - Pacific/Auckland</li>
                        <li>(GMT+02.00) Gerusalemme - Asia_Gerusalemme - Asia/Gerusalemme</li>
                        <li>(GMT+03.00) Mosca, San Pietroburgo, Volgograd - Europa_Mosca - Europa/Mosca</li>
                        <li>(GMT+09.30) Adelaïde - Australia_Adelaide - Australia/Adelaide</li>
                        <li>(GMT+10.00) Canberra, Melbourne, Sydney - Australia_Canberra - Australia/Canberra</li>
                        <li>(GMT+08.00) Perth - Australia_Perth - Australia/Perth</li>
                        <li>(GMT+09.00) Yakoutsk - Asia_Yakutsk - Asia/Yakutsk</li>
                        <li>(GMT-10.00) Hawai - Pacific_Honolulu - Pacific/Honolulu</li>
                        <li>(GMT+04.00) Baku - Asia_Baku - Asia/Baku</li>
                        <li>(GMT+10.00) Vladivostok - Asia_Vladivostok - Asia/Vladivostok</li>
                        <li>(GMT+09.00) Seoul - Asia_Seoul - Asia/Seoul</li>
                        <li>(GMT+01.00) Sarajevo, Skoplje, Sofia, Varsavia, Zagabria - Europa_Sarajevo - Europa/Sarajevo</li>
                        <li>(GMT+04.00) Abu Dhabi, Muscat - Asia_Muscat - Asia/Muscat</li>
                        <li>(GMT+08.00) Kuala Lumpur, Singapore - Asia_Kuala_Lumpur - Asia/Kuala_Lumpur</li>
                        <li>(GMT+09.00) Osaka, Sapporo, Tokyo - Asia_Tokyo - Asia/Tokyo</li>
                        <li>(GMT+10.00) Brisbane - Australia_Brisbane - Australia/Brisbane</li>
                        <li>(GMT+05.30) Sri Jayawardenepura - Asia_Colombo - Asia/Colombo</li>
                        <li>(GMT+02.00) Harare, Pretoria - Africa_Harare - Africa/Harare</li>
                        <li>(GMT+08.00) Oulan-Bator - Asia_Ulan_Bator - Asia/Ulan_Bator</li>
                        <li>(GMT-02.00) Ora di Greenwich meno 2 ore - Gmt_m2 - Etc/GMT+2</li>
                        <li>(GMT-03.00) Ora di Greenwich meno 3 ore - Gmt_m3 - Etc/GMT+3</li>
                        <li>(GMT-1.00) Ora di Greenwich meno 1 ora - Gmt_m1 - Etc/GMT+1</li>
                        <li>(GMT-06.00) Ora di Greenwich meno 6 ore - Gmt_m6 - Etc/GMT+6</li>
                        <li>(GMT-07.00) Ora di Greenwich meno 7 ore - Gmt_m7 - Etc/GMT+7</li>
                        <li>(GMT-04.00) Ora di Greenwich meno 4 ore - Gmt_m4 - Etc/GMT+4</li>
                        <li>(GMT) Casablanca - Africa_Casablanca - Africa/Casablanca</li>
                        <li>(GMT+05.30) Calcutta, Chennai, Mumbai, Nuova Delhi - Asia_Calcutta - Asia/Calcutta</li>
                        <li>(GMT-11.00) Ora di Greenwich meno 11 ore - Gmt_m11 - Etc/GMT+11</li>
                        <li>(GMT-09.00) Ora di Greenwich meno 9 ore - Gmt_m9 - Etc/GMT+9</li>
                        <li>(GMT-03.30) Terranova - America_St_Johns - America/St_Johns</li>
                        <li>(GMT+03.00) Greenwich Mean Time plus 3 ore - Gmt_p3 - Etc/GMT-3</li>
                        <li>(GMT-04.30) Caracas - America_Caracas - America/Caracas</li>
                        <li>(GMT+01.00) Amsterdam, Berlino, Berna, Roma, Stoccolma, Vienna - Europa_Berlino - Europa/Berlino</li>
                        <li>(GMT-07.00) Chihuahua, La Paz, Mazatlan - America_Chihuahua - America/Chihuahua</li>
                        <li>(GMT+03.00) Nairobi - Africa_Nairobi - Africa/Nairobi</li>
                        <li>(GMT-04.00) Asunción - America_Asuncion - America/Asuncion</li>
                        <li>(GMT+03.00) Bagdad - Asia_Baghdad - Asia/Baghdad</li>
                        <li>(GMT-10.00) Ora di Greenwich meno 10 ore - Gmt_m10 - Etc/GMT+10</li>
                        <li>(GMT-03.00) Groenlandia - America_Godthab - America/Godthab</li>
                        <li>(GMT+02.00) Damas - Asia_Damasco - Asia/Damasco</li>
                        <li>(GMT-11.00) Samoa - Pacific_Samoa - Pacific/Samoa</li>
                        <li>(GMT-05.00) Bogota, Lima, Quito - America_Bogota - America/Bogota</li>
                        <li>(GMT+01.00) Bruxelles, Copenaghen, Madrid, Parigi - Europa_Parigi - Europa/Parigi</li>
                        <li>(GMT+08.00) Pechino, Chongqing, Hong Kong, Urumqi - Asia_Shanghai - Asia/Shanghai</li>
                        <li>(GMT+12.00) Fidji - Pacific_Fiji - Pacific/Fiji</li>
                        <li>(GMT+02.00) Atene, Istanbul, Minsk - Europa_Atene - Europa/Atene</li>
                        <li>(GMT+04.00) Tbilisi - Asia_Tbilisi - Asia/Tbilisi</li>
                        <li>VALORE NON VALIDO - __Invalid_value__ - __Invalid_value__</li>
                        <li>(GMT+05.45) Katmandu - Asia_Katmandu - Asia/Katmandu</li>
                        <li>(GMT-05.00) Indiana (Est) - America_Indianapolis - America/Indianapolis</li>
                        <li>(GMT-01.00) Isole del Capo Verde - Atlantic_Cape_Verde - Atlantic/Cape_Verde</li>
                        <li>(GMT+04.00) Port Louis - Indian_Mauritius - Indian/Mauritius</li>
                        <li>(GMT+08.00) Taipei - Asia_Taipei - Asia/Taipei</li>
                        <li>(GMT+06.30) Rangoon - Asia_Rangoon - Asia/Rangoon</li>
                        <li>(GMT+11.00) Magadan, Isole Salomone, Nuova Caledonia - Pacific_Guadalcanal - Pacific/Guadalcanal</li>
                        <li>(GMT+02.00) Cairo - Africa_Cairo - Africa/Cairo</li>
                        <li>(GMT+05.00) Iekaterinburg - Asia_Yekaterinburg - Asia/Yekaterinburg</li>
                        <li>(GMT+08.00) Irkoutsk - Asia_Irkutsk - Asia/Irkutsk</li>
                        <li>(GMT+10.00) Guam, Port Moresby - Pacific_Guam - Pacific/Guam</li>
                        <li>(GMT-04.00) Ora solare Atlantico (Canada) - America_Halifax - America/Halifax</li>
                        <li>(GMT) Greenwich tempo medio - GMT - GMT</li>
                        <li>Predefinito - nessuno - nessuno</li>
                        <li>(GMT-04.00) La Paz - America_La_Paz - America/La_Paz</li>
                        <li>(GMT-06.00) Guadalajara, Messico, Monterrey - America_Messico_City - America/Città del Messico</li>
                        <li>(GMT+09.30) Darwin - Australia_Darwin - Australia/Darwin</li>
                        <li>(GMT-05.00) Est (Stati Uniti e Canada) - America_New_York - America/New_York</li>
                        <li>(GMT-05.00) Ora di Greenwich meno 5 ore - Gmt_m5 - Etc/GMT+5</li>
                        <li>(GMT+05.00) Islamabad, Karachi, Tachkent - Asia_Karachi - Asia/Karachi</li>
                        <li>(GMT+03.00) Koweït, Riyad - Asia_Riyadh - Asia/Riyadh</li>
                        <li>(GMT-08.00) Ora di Greenwich meno 8 ore - Gmt_m8 - Etc/GMT+8</li>
                        <li>(GMT-01.00) Le Azzorre - Atlantic_Azores - Atlantic/Azores</li>
                        <li>(GMT+07.00) Bangkok, Hanoi, Djakarta - Asia_Bangkok - Asia/Bangkok</li>
                        <li>(GMT) Monrovia - Africa_Monrovia - Africa/Monrovia</li>
                        <li>(GMT-09.00) Alaska - America_Ancoraggio - America/Ancoraggio</li>
                        <li>(GMT+01.00) Belgrado, Bratislava, Budapest, Lubiana, Praga - Europa_Belgrado - Europa/Belgrado</li>
                        <li>(GMT) Reykjavik - Atlantic_Reykjavik - Atlantic/Reykjavik</li>
                        <li>(GMT+02.00) Bucarest - Europa_Bucarest - Europa/Bucarest</li>
                        <li>(GMT+05.00) Greenwich Mean Time plus 5 ore - Gmt_p5 - Etc/GMT-5</li>
                        <li>(GMT+04.00) Greenwich Mean Time plus 4 ore - Gmt_p4 - Etc/GMT-4</li>
                        <li>(GMT+07.00) Greenwich Mean Time plus 7 ore - Gmt_p7 - Etc/GMT-7</li>
                        <li>(GMT+06.00) Greenwich Mean Time plus 6 ore - Gmt_p6 - Etc/GMT-6</li>
                        <li>(GMT+01.00) Greenwich Mean Time plus 1 ora - Gmt_p1 - Etc/GMT-1</li>
                        <li>(GMT-08.00) Pacifico (Stati Uniti e Canada) - America_Los_Angeles - America/Los_Angeles</li>
                        <li>(GMT+02.00) Greenwich Mean Time plus 2 ore - Gmt_p2 - Etc/GMT-2</li>
                        <li>(GMT+07.00) Krasnoïarsk - Asia_Krasnoyarsk - Asia/Krasnoyarsk</li>
                        <li>(GMT+09.00) Greenwich Mean Time plus 9 ore - Gmt_p9 - Etc/GMT-9</li>
                        <li>(GMT+08.00) Greenwich Mean Time plus 8 ore - Gmt_p8 - Etc/GMT-8</li>
                        <li>(GMT+10.00) Hobart - Australia_Hobart - Australia/Hobart</li>
                        <li>(GMT+13.00) Nuku'alofa - Pacific_Tongatapu - Pacific/Tongatapu</li>
                        <li>(GMT-06.00) America centrale - America_Regina - America/Regina</li>
                        <li>(GMT-03.00) Buenos Aires, Cayenne, Fortaleza - America_Buenos_Aires - America/Buenos_Aires</li>
                        <li>(GMT-07.00) Montagne Rocciose (Stati Uniti e Canada) - America_Denver - America/Denver</li>
                        <li>(GMT+01.00) Africa centrale - Ovest - Africa_Luanda - Africa/Luanda</li>
                        <li>(GMT+02.00) Helsinki, Kiev, Riga, Sofia, Tallinn, Vilnius - Europe_Helsinki - Europa/Helsinki</li>
                        <li>(GMT) Ora di Greenwich: Dublino, Edimburgo, Lisbona, Londra - Europa_Londra - Europa/Londra</li>
                        <li>(GMT-07.00) Arizona - America_Phoenix - America/Phoenix</li>
                        <li>(GMT+02.00) Beirut - Asia_Beirut - Asia/Beirut</li>
                        <li>(GMT+04.30) Kabul - Asia_Kabul - Asia/Kabul</li>
                        <li>(GMT-06.00) Centro (Stati Uniti e Canada) - America_Chicago - America/Chicago</li>
                        <li>(GMT+11.00) Greenwich Mean Time plus 11 ore - Gmt_p11 - Etc/GMT-11</li>
                        <li>(GMT+10.00) Greenwich Mean Time plus 10 ore - Gmt_p10 - Etc/GMT-10</li>
                        <li>(GMT+13.00) Greenwich Mean Time plus 13 ore - Gmt_p13 - Etc/GMT-13</li>
                        <li>(GMT+12.00) Greenwich Mean Time plus 12 ore - Gmt_p12 - Etc/GMT-12</li>
                        <li>(GMT-04.00) Santiago - America_Santiago - America/Santiago</li>
                        <li>(GMT-03.00) Montevideo - America_Montevideo - America/Montevideo</li>
                        <li>(GMT-04.00) Cuiaba - America_Cuiaba - America/Cuiaba</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>title</td>
                  <td>Profilo</td>
                  <td>string (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>tracking</td>
                  <td>Registri di tracciamento</td>
                  <td>raccolta </td>
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
<td>integer</td>
</tr>
<tr>
<td>nextUnitsValue</td>
<td>integer</td>
</tr>
<tr>
<td>endDay</td>
<td>date</td>
</tr>
<tr>
<td>precisione</td>
<td>enumerazione</td>
</tr>
<tr>
<td>relativeValue</td>
<td>string</td>
</tr>
<tr>
<td>mese</td>
<td>date</td>
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
<td>date</td>
</tr>
<tr>
<td>type</td>
<td>enumerazione</td>
</tr>
<tr>
<td>giorno</td>
<td>date</td>
</tr>
</table>

Per e-mail (per e-mail)

<table>
<tr>
<th>Nome</th>
<th>Tipo</th>
</tr>
<tr>
<td>e-mail</td>
<td>string</td>
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
<td>string</td>
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
<td>string</td>
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
<td>collegamento</td>
</tr>
</table>

Clic (hasClicDelivery)

<table>
<tr>
<th>Nome</th>
<th>Tipo</th>
</tr>
<tr>
<td>consegna</td>
<td>collegamento</td>
</tr>
</table>

Aperto (hasOpenDelivery)

<table>
<tr>
<th>Nome</th>
<th>Tipo</th>
</tr>
<tr>
<td>consegna</td>
<td>collegamento</td>
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
<td>collegamento</td>
</tr>
</table>

Ricevuto (hasReceivedDelivery)

<table>
<tr>
<th>Nome</th>
<th>Tipo</th>
</tr>
<tr>
<td>consegna</td>
<td>collegamento</td>
</tr>
</table>

Abbonati (abbonati)

<table>
<tr>
<th>Nome</th>
<th>Tipo</th>
</tr>
<tr>
<td>servizio</td>
<td>collegamento</td>
</tr>
</table>
