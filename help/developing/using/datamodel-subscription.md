---
title: DataModel Subscription, evento
description: Scopri il modello dati
audience: developing
content-type: reference
feature: Data Model
role: Developer
level: Experienced
exl-id: cf0fac4e-59fd-4d6e-a411-41361f45938d
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '79'
ht-degree: 31%

---

# Evento abbonamento (nms:rtEvent)

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
        <td>ctx</td>
        <td>Contesto dell’evento</td>
        <td>elemento </td>
        <td> </td>
    </tr>
    <tr>
        <td>e-mail</td>
        <td>E-mail</td>
        <td>stringa (128)</td>
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
            <li>VALORE NON VALIDO - __Valore_non valido__ - __Valore_non valido__</li>
            <li>Sconosciuto - sconosciuto - 0</li>
            </ul>
        </td>
    </tr>
    <tr>
        <td>eventHistoId</td>
        <td>ID evento archiviato</td>
        <td>intero </td>
        <td> </td>
    </tr>
    <tr>
        <td>mobilePhone</td>
        <td>Numero di cellulare</td>
        <td>stringa (32)</td>
        <td> </td>
    </tr>
    <tr>
        <td>serverUrl</td>
        <td>ServerUrl</td>
        <td>stringa </td>
        <td> </td>
    </tr>
</table>

## Filtri

Per e-mail (byEmail)

<table>
    <tr>
    <th>Nome</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>e-mail</td>
    <td>stringa</td>
    </tr>
</table>

Per stato o tipo (byStatusOrType)

<table>
        <tr>
        <th>Nome</th>
        <th>Tipo</th>
        </tr>
        <tr>
        <td>stato</td>
        <td>enumerazione</td>
        </tr>
        <tr>
        <td>tipo</td>
        <td>stringa</td>
        </tr>
    </table>
