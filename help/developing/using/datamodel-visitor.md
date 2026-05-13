---
title: Visitatore DataModel
description: Scopri il modello dati
audience: developing
content-type: reference
feature: Data Model
role: Developer
level: Experienced
exl-id: 20dafd81-8546-450a-87a0-59a2509efb7a
TQID: https://experienceleague.adobe.com/jzmKAer7SITNpxJRT1CsPf-LWW-bglgNhDl5NKP6mzU
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 154
ht-degree: 40%

---

# Visitatore (nms:visitor)

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
        <td>commento</td>
        <td>Commento del referrer</td>
        <td>stringa (255)</td>
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
        <td>consegna (delivery)</td>
        <td>Consegna</td>
        <td>collegamento </td>
        <td> </td>
    </tr>
    <tr>
        <td>deliveryId</td>
        <td>ID dell’ultima consegna</td>
        <td>intero </td>
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
        <td>externalId</td>
        <td>ID esterno</td>
        <td>stringa (64)</td>
        <td> </td>
    </tr>
    <tr>
        <td>firstName</td>
        <td>Nome</td>
        <td>stringa (30)</td>
        <td> </td>
    </tr>
    <tr>
        <td>forwardUrl</td>
        <td>URL di inoltro</td>
        <td>stringa (255)</td>
        <td> </td>
    </tr>
    <tr>
        <td>geoUnit (geoUnitBase)</td>
        <td>Unità geografica</td>
        <td>collegamento </td>
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
        <td>modifiedBy (userBase)</td>
        <td>Modificato da</td>
        <td>collegamento </td>
        <td> </td>
    </tr>
    <tr>
        <td>orgUnit (orgUnitBase)</td>
        <td>Unità organizzativa</td>
        <td>collegamento </td>
        <td> </td>
    </tr>
    <tr>
        <td>origine</td>
        <td>Origine</td>
        <td>enumerazione (byte) </td>
        <td>
            <ul>
            <li>Non definito - non definito - 0</li>
            <li>VALORE NON VALIDO - __Valore_non valido__ - __Valore_non valido__</li>
            </ul>
        </td>
    </tr>
    <tr>
        <td>destinatario (recipient)</td>
        <td>Profilo identificato</td>
        <td>collegamento </td>
        <td> </td>
    </tr>
    <tr>
        <td>recipientId</td>
        <td>ID profilo</td>
        <td>intero </td>
        <td> </td>
    </tr>
    <tr>
        <td>referrerEmail</td>
        <td>E-mail referrer</td>
        <td>stringa (128)</td>
        <td> </td>
    </tr>
    <tr>
        <td>referrerFirstName</td>
        <td>Nome referrer</td>
        <td>stringa (30)</td>
        <td> </td>
    </tr>
    <tr>
        <td>referrerId</td>
        <td>ID referrer</td>
        <td>intero </td>
        <td> </td>
    </tr>
    <tr>
        <td>referrerLastName</td>
        <td>Cognome referrer</td>
        <td>stringa (50)</td>
        <td> </td>
    </tr>
    <tr>
        <td>referrerRcp (recipient)</td>
        <td>Referrer</td>
        <td>collegamento </td>
        <td> </td>
    </tr>
    <tr>
        <td>titolo</td>
        <td>Etichetta</td>
        <td>stringa (255)</td>
        <td> </td>
    </tr>
</table>

## Filtri

Per cognome, nome o indirizzo e-mail (byText)</p>

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
