---
solution: Campaign Standard
product: campaign
title: DataModel
description: Scopri il modello dati
audience: developing
content-type: reference
feature: Data Model
role: Developer
level: Experienced
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '81'
ht-degree: 6%

---


# Evento iscrizione (nms:rtEvent)

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
        <td>ctx</td>
        <td>Contesto dell'evento</td>
        <td>item </td>
        <td> </td>
    </tr>
    <tr>
        <td>email</td>
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
        <td>eventHistoId</td>
        <td>ID evento archiviato</td>
        <td>integer </td>
        <td> </td>
    </tr>
    <tr>
        <td>mobilePhone</td>
        <td>Numero cellulare</td>
        <td>string (32)</td>
        <td> </td>
    </tr>
    <tr>
        <td>serverUrl</td>
        <td>ServerUrl</td>
        <td>string </td>
        <td> </td>
    </tr>
</table>

## Filtri

Per e-mail (per e-mail)

<table>
    <tr>
    <th>Nome</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>email</td>
    <td>string</td>
    </tr>
</table>

Per stato o tipo (byStatusOrType)

<table>
        <tr>
        <th>Nome</th>
        <th>Tipo</th>
        </tr>
        <tr>
        <td>status</td>
        <td>enumerazione</td>
        </tr>
        <tr>
        <td>type</td>
        <td>string</td>
        </tr>
    </table>