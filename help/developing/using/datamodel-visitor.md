---
solution: Campaign Standard
product: campaign
title: DataModel
description: Scopri il modello dati
audience: developing
content-type: reference
feature: Modello dati
role: Sviluppatore
level: Esperienza
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 5%

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
        <td>string </td>
        <td> </td>
    </tr>
    <tr>
        <td>commento</td>
        <td>Commento referente</td>
        <td>string (255)</td>
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
        <td>consegna (consegna)</td>
        <td>Consegna</td>
        <td>collegamento </td>
        <td> </td>
    </tr>
    <tr>
        <td>deliveryId</td>
        <td>ID dell’ultima consegna</td>
        <td>integer </td>
        <td> </td>
    </tr>
    <tr>
        <td>desc</td>
        <td>Descrizione</td>
        <td>string (512)</td>
        <td> </td>
    </tr>
    <tr>
        <td>email</td>
        <td>E-mail</td>
        <td>string (128)</td>
        <td> </td>
    </tr>
    <tr>
        <td>externalId</td>
        <td>ID esterno</td>
        <td>string (64)</td>
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
        <td>URL successivo</td>
        <td>string (255)</td>
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
            <li>VALORE NON VALIDO - __Invalid_value__ - __Invalid_value__</li>
            </ul>
        </td>
    </tr>
    <tr>
        <td>destinatario (destinatario)</td>
        <td>Profilo identificato</td>
        <td>collegamento </td>
        <td> </td>
    </tr>
    <tr>
        <td>recipientId</td>
        <td>ID profilo</td>
        <td>integer </td>
        <td> </td>
    </tr>
    <tr>
        <td>referrerEmail</td>
        <td>Indirizzo e-mail referrer</td>
        <td>string (128)</td>
        <td> </td>
    </tr>
    <tr>
        <td>referrerFirstName</td>
        <td>Nome referente</td>
        <td>stringa (30)</td>
        <td> </td>
    </tr>
    <tr>
        <td>referrerId</td>
        <td>ID referente</td>
        <td>integer </td>
        <td> </td>
    </tr>
    <tr>
        <td>referrerLastName</td>
        <td>Cognome referente</td>
        <td>string (50)</td>
        <td> </td>
    </tr>
    <tr>
        <td>referrerRcp (recipient)</td>
        <td>Referrer</td>
        <td>collegamento </td>
        <td> </td>
    </tr>
    <tr>
        <td>title</td>
        <td>Etichetta</td>
        <td>string (255)</td>
        <td> </td>
    </tr>
</table>

## Filtri

Per cognome, nome o e-mail (perText)</p>

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