---
title: DataModel Unsubscription, evento
description: Scopri il modello dati
audience: developing
content-type: reference
feature: Data Model
role: Developer
level: Experienced
exl-id: 508361d1-6a0b-4476-a058-4162fb3e8d5e
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '55'
ht-degree: 58%

---

# Evento annullamento abbonamento (nms:rtEvent)

## Descrizione oggetto

<table>
               <tr>
                  <th>Nome</th>
                  <th>Sola lettura</th>
                  <th>Tipo</th>
                  <th>Obbligatorio</th>
               </tr>
               <tr>
                  <td>PKey</td>
                  <td>Falso</td>
                  <td>stringa</td>
                  <td>Falso</td>
               </tr>
               <tr>
                  <td>ctx</td>
                  <td>Falso</td>
                  <td>elemento</td>
                  <td>Falso</td>
               </tr>
               <tr>
                  <td>e-mail</td>
                  <td>Falso</td>
                  <td>stringa</td>
                  <td>Falso</td>
               </tr>
               <tr>
                  <td>emailFormat</td>
                  <td>Falso</td>
                  <td>enumerazione</td>
                  <td>Falso</td>
               </tr>
               <tr>
                  <td>mobilePhone</td>
                  <td>Falso</td>
                  <td>stringa</td>
                  <td>Falso</td>
               </tr>
               <tr>
                  <td>serverUrl</td>
                  <td>Vero</td>
                  <td>stringa</td>
                  <td>Falso</td>
               </tr>
            </table>

## Filtri

byEmail

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

byStatusOrType

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
