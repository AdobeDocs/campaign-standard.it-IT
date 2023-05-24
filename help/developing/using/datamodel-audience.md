---
title: Pubblico DataModel
description: Scopri il modello dati
audience: developing
content-type: reference
feature: Data Model
role: Developer
level: Experienced
exl-id: 53da6c4e-d4fb-4677-acff-744e3eb10960
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '208'
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
                  <td>link </td>
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
                  <td>date </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>countPreview</td>
                  <td>CountPreview</td>
                  <td>elemento </td>
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
                  <td>desc</td>
                  <td>Descrizione</td>
                  <td>stringa (512)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>doNotPersist</td>
                  <td>Non storicizzare questo processo</td>
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
                  <td>title</td>
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
                  <td>link </td>
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
    <td>text</td>
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
