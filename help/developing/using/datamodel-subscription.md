---
title: DataModel
description: Scopri il modello dati
uuid: 99277e46-e4f7-49a9-ba27-b878780f90da
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
discoiquuid: 6e21db35-daf9-4edb-977a-6ef606db0e4d
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c7e83d7d5130ce93b880e4835e634dad03504ebb

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
        <td>Contesto evento</td>
        <td>item </td>
        <td> </td>
    </tr>
    <tr>
        <td>email</td>
        <td> E-mail</td>
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
            <li>VALORE INVALID - __Invalid_value__ - __Invalid_value___</li>
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