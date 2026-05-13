---
title: DataModel Subscription, evento
description: Scopri il modello dati
audience: developing
content-type: reference
feature: Data Model
role: Developer
level: Experienced
exl-id: cf0fac4e-59fd-4d6e-a411-41361f45938d
TQID: https://experienceleague.adobe.com/XssYu0sntbeCRq1uNe6MhztLtISXoJiOefIOnjqIaoQ
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 81
ht-degree: 33%

---

# Evento sottoscrizione (nms:rtEvent)

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
