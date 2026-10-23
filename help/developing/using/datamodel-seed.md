---
title: Membro di seed DataModel
description: Scopri il modello dati
audience: developing
content-type: reference
feature: Data Model
role: Developer
level: Experienced
exl-id: 9b522c84-e296-47c7-9588-2e5ed08ab631
TQID: 'https://experienceleague.adobe.com/lfD2ncth570TSScQZE3UiO3ikqqxpjf4CVd7PvuAFXs'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: a1681cd8-6b2e-4955-9113-33b5f7a22b8c
    internal-label: Data model architecture
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 46%
---
# Membro seed (nms:seedMember)

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
                  <td>paese (paesi)</td>
                  <td>Paese</td>
                  <td>collegamento </td>
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
                  <td>e-mail</td>
                  <td>E-mail</td>
                  <td>stringa (128)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>emailRendering</td>
                  <td>Rendering e-mail</td>
                  <td>booleano </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>fax</td>
                  <td>Fax</td>
                  <td>stringa (32)</td>
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
                  <td>lastModified</td>
                  <td>Ultima modifica</td>
                  <td>data </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>posizione</td>
                  <td>Posizione</td>
                  <td>elemento </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>marketingCloudId</td>
                  <td>ID MARKETING CLOUD</td>
                  <td>stringa (256)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>mobileApp</td>
                  <td>App mobile</td>
                  <td>elemento </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>mobilePhone</td>
                  <td>Dispositivi mobili</td>
                  <td>stringa (32)</td>
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
                  <td>nms_recipient</td>
                  <td>Profilo</td>
                  <td>elemento </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>nms_rtEvent</td>
                  <td>Evento</td>
                  <td>elemento </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>orgUnit (orgUnitBase)</td>
                  <td>Unità organizzativa</td>
                  <td>collegamento </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>telefono</td>
                  <td>Telefono</td>
                  <td>stringa (32)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>bozza</td>
                  <td>Bozza</td>
                  <td>booleano </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>pushNotification</td>
                  <td>Notifica push</td>
                  <td>stringa (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>registrationToken</td>
                  <td>Token di registrazione</td>
                  <td>stringa (256)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>sampleData</td>
                  <td>Dati di esempio</td>
                  <td>booleano </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>sms</td>
                  <td>Dispositivi mobili</td>
                  <td>stringa (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>stateLink (state)</td>
                  <td>Stato</td>
                  <td>collegamento </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>targetData</td>
                  <td>Estensione</td>
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
                  <td>titolo</td>
                  <td>Profilo di prova</td>
                  <td>stringa (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>trappola</td>
                  <td>Abbondanza</td>
                  <td>booleano </td>
                  <td> </td>
               </tr>
            </table>

## Filtri

Per tipo di evento (byEventType)

<table>
        <tr>
        <th>Nome</th>
        <th>Tipo</th>
        </tr>
        <tr>
        <td>eventType</td>
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

Per utilizzo (byUsage)

<table>
        <tr>
        <th>Nome</th>
        <th>Tipo</th>
        </tr>
        <tr>
        <td>trappola</td>
        <td>booleano</td>
        </tr>
        <tr>
        <td>emailRendering</td>
        <td>booleano</td>
        </tr>
        <tr>
        <td>bozza</td>
        <td>booleano</td>
        </tr>
    </table>

Profilo di test (profilo)

<table>
    <tr>
    <th>Nome</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>seedMember</td>
    <td>collegamento</td>
    </tr>
</table>
