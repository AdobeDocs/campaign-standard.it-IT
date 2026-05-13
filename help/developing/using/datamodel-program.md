---
title: Programma DataModel
description: Scopri il modello dati
audience: developing
content-type: reference
feature: Data Model
role: Developer
level: Experienced
exl-id: b05dc67a-6447-4d22-99f2-8a14a0ee46d2
TQID: https://experienceleague.adobe.com/zo3wFxqwI6LIHn4Uolv9oipkW17maikqcO4zExmYQxM
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 228
ht-degree: 37%

---

# Programma (nms:program)

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
                  <td>attività</td>
                  <td>Attività</td>
                  <td>raccolta </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>predefinito</td>
                  <td>Oggetto applicazione incorporato</td>
                  <td>booleano </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>creata</td>
                  <td>Creato</td>
                  <td>data </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>createdBy (userBase)</td>
                  <td>Creato da</td>
                  <td>collegamento </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>desc</td>
                  <td>Descrizione</td>
                  <td>stringa (512)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>fine</td>
                  <td>Data di fine</td>
                  <td>data </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>geoUnit (geoUnitBase)</td>
                  <td>Unità geografica</td>
                  <td>collegamento </td>
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
                  <td>etichetta</td>
                  <td>Etichetta</td>
                  <td>stringa (128)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>lastModified</td>
                  <td>Ultima modifica</td>
                  <td>data </td>
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
                  <td>modifiedBy (userBase)</td>
                  <td>Modificato da</td>
                  <td>collegamento </td>
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
                  <td>collegamento </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>parent (programBase)</td>
                  <td>Programma principale</td>
                  <td>collegamento </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>realtimeReport</td>
                  <td>Rapporti in tempo reale</td>
                  <td>elemento </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>inizio</td>
                  <td>Data di inizio</td>
                  <td>data </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>stato</td>
                  <td>Stato</td>
                  <td>enumerazione (byte) </td>
                  <td>
                     <ul>
                        <li>Avviato - Avviato - 1</li>
                        <li>Modifica - edizione - 0</li>
                        <li>Finito - finito - 2</li>
                        <li>VALORE NON VALIDO - __Valore_non valido__ - __Valore_non valido__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>modello (programma)</td>
                  <td>Modello di programma</td>
                  <td>collegamento </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>miniatura</td>
                  <td>Miniatura</td>
                  <td>stringa (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>titolo</td>
                  <td>Programma</td>
                  <td>stringa (255)</td>
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
    <td>testo</td>
    <td>stringa</td>
    </tr>
</table>

Per periodo (perPeriodo)

<table>
    <tr>
    <th>Nome</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>startDate</td>
    <td>data</td>
    </tr>
    <tr>
    <td>timePeriod</td>
    <td>stringa</td>
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

Includi sottoprogrammi (withParent)

<table>
        <tr>
        <th>Nome</th>
        <th>Tipo</th>
        </tr>
        <tr>
        <td>withParent</td>
        <td>booleano</td>
        </tr>
    </table>

Solo i genitori idonei (idoneeParents)

<table>
    <tr>
    <th>Nome</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>programma</td>
    <td>collegamento</td>
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
    <td>data</td>
    </tr>
    <tr>
    <td>endDate</td>
    <td>data</td>
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
    <td>data</td>
    </tr>
    <tr>
    <td>endDate</td>
    <td>data</td>
    </tr>
</table>
