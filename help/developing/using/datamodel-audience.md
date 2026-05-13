---
title: Pubblico DataModel
description: Scopri il modello dati
audience: developing
content-type: reference
feature: Data Model
role: Developer
level: Experienced
exl-id: 53da6c4e-d4fb-4677-acff-744e3eb10960
TQID: https://experienceleague.adobe.com/Fd12meY1UY9hZudGc18wtTTi2cVWWvN9wth8JSLzBQA
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 213
ht-degree: 40%

---

# Pubblico (nms:audience)

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
                  <td>aamMappingId</td>
                  <td>ID mappatura Audience Manager</td>
                  <td>stringa (100)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>amcDataSource (amcDataSourceBase)</td>
                  <td>Origine dati AMC</td>
                  <td>collegamento </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>audienceData</td>
                  <td>Anteprima popolazione selezionata</td>
                  <td>raccolta </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>audienceDataSchema</td>
                  <td>Schema dati</td>
                  <td>stringa (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>audienceMetadata</td>
                  <td>AudienceMetadata</td>
                  <td>stringa (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>collectLineNumber</td>
                  <td>Utilizza un numero di riga come ID</td>
                  <td>booleano </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>count</td>
                  <td>Conteggio</td>
                  <td>intero </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>countDate</td>
                  <td>Data di conteggio</td>
                  <td>data </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>countPreview</td>
                  <td>CountPreview</td>
                  <td>elemento </td>
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
                  <td>doNotPersist</td>
                  <td>Non creare cronologia per questo processo</td>
                  <td>booleano </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>errorLimit</td>
                  <td>Errori prima dell’interruzione</td>
                  <td>intero </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>expirationDate</td>
                  <td>Scade il</td>
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
                  <td>hasSchema</td>
                  <td>HasSchema</td>
                  <td>booleano </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>isAMC</td>
                  <td>Pubblico Adobe Marketing Cloud</td>
                  <td>booleano </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>isExternal</td>
                  <td>È una risorsa esterna</td>
                  <td>booleano </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>jobLogs</td>
                  <td>Registri</td>
                  <td>raccolta </td>
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
                  <td>rifiutaNomeFile</td>
                  <td>File di rifiuto</td>
                  <td>stringa </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>sharedAudience</td>
                  <td>Nome del pubblico condiviso</td>
                  <td>elemento </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>sorgente</td>
                  <td>Origine</td>
                  <td>elemento </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>sourceId</td>
                  <td>ID origine</td>
                  <td>intero </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>titolo</td>
                  <td>Pubblico</td>
                  <td>stringa (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>tipo</td>
                  <td>Tipo</td>
                  <td>enumerazione (stringa) (100)</td>
                  <td>
                     <ul>
                        <li>Query - query - query</li>
                        <li>Elenco - elenco - elenco</li>
                        <li>File - file - file</li>
                        <li>VALORE NON VALIDO - __Valore_non valido__ - __Valore_non valido__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>dove</td>
                  <td>Definizione di query</td>
                  <td>elemento </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>workflow (workflow)</td>
                  <td>Flusso di lavoro</td>
                  <td>collegamento </td>
                  <td> </td>
               </tr>
            </table>

## Filtri

Per dimensione filtro (byFilteringResource)

<table>
    <tr>
    <th>Nome</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>filteringResource</td>
    <td>stringa</td>
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

Per tipo (byType)

<table>
    <tr>
    <th>Nome</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>tipo</td>
    <td>enumerazione</td>
    </tr>
    <tr>
    <td>isAMC</td>
    <td>stringa</td>
    </tr>
</table>
