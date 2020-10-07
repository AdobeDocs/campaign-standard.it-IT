---
title: DataModel
description: Scopri il modello dati
uuid: 99277e46-e4f7-49a9-ba27-b878780f90da
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
discoiquuid: 6e21db35-daf9-4edb-977a-6ef606db0e4d
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 7%

---


# Campaign (nms:campaign)

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
                  <td>activity</td>
                  <td>Attività</td>
                  <td>collection </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>buildIn</td>
                  <td>Oggetto applicazione predefinito</td>
                  <td>boolean </td>
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
                  <td>desc</td>
                  <td>Descrizione</td>
                  <td>string (512)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>length</td>
                  <td>Durata campagna</td>
                  <td>number </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>end</td>
                  <td>Data di fine</td>
                  <td>date </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>geoUnit (geoUnitBase)</td>
                  <td>Unità geografica</td>
                  <td>link </td>
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
                  <td>logicalStatus</td>
                  <td>Stato esecuzione</td>
                  <td>enumerazione (stringa) (255)</td>
                  <td>
                     <ul>
                        <li>In corso - avviato - avviato</li>
                        <li>Editing - edizione</li>
                        <li>Finito - finito - finito</li>
                        <li>Avvertenza - Avviso</li>
                        <li>Erroneo - errore - errore</li>
                        <li>VALORE INVALID - __Invalid_value__ - __Invalid_value___</li>
                     </ul>
                  </td>
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
                  <td>program (programBase)</td>
                  <td>programma</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>realtimeReport</td>
                  <td>Rapporti in tempo reale</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>start</td>
                  <td>Data di inizio</td>
                  <td>date </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>status</td>
                  <td>Stato</td>
                  <td>enumerazione (byte) </td>
                  <td>
                     <ul>
                        <li>Iniziato - 1</li>
                        <li>Editing - edizione - 0</li>
                        <li>Finito - finito - 2</li>
                        <li>VALORE INVALID - __Invalid_value__ - __Invalid_value___</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>template (campagna)</td>
                  <td>Modello campagna</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>thumbnail</td>
                  <td>Miniatura</td>
                  <td>string (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>title</td>
                  <td>Campagna</td>
                  <td>string (255)</td>
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

Per periodo (per periodo)

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
    <td>timePeriod</td>
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

Pianificato per il periodo specificato (per pianificazione)

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