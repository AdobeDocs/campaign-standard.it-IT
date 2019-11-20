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


# Visitatore (nms:visitatore)

## Descrizione oggetto

    &lt;tabella&gt;
    &lt;tr&gt;
    &lt;th&gt;Nome&lt;/th&gt;
    &lt;th&gt;Etichetta&lt;/th&gt;
    &lt;th&gt;Tipo (lunghezza)&lt;/th&gt;
    &lt;th&gt;Valori di enumerazione&lt;/th&gt;
    &lt;/tr&gt;
    &lt;tr&gt;
    &lt;td&gt;PKey&lt;/td&gt;
    &lt;td&gt;ID risorsa principale&lt;/td&gt;
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    &lt;td&gt;stringa &lt;/td&gt;primaria&lt;td&gt;&lt;/td&gt; tr&gt;&lt;tr&gt;&lt;td&gt;commento&lt;/td&gt;&lt;td&gt;Commento referente&lt;/td&gt;&lt;td&gt;stringa (255)&lt;/td&gt;&lt;td&gt; &lt;/td&gt;&lt;/td&gt;&lt;/tr&gt;&lt;tr&gt;creata&lt;/td&gt;creata&lt;td&gt;data &lt;/td&gt;&lt;td&gt; &lt;/td&gt;&lt;/td&gt;&lt;/&lt; &lt;tr&gt;&lt;td&gt;createBy (userBase)&lt;/td&gt;Create da&lt;/td&gt;link &lt;/td&gt;&lt;td&gt; &lt;/td&gt;&lt;/tr&gt;&lt;/tr&gt;&lt;tr&gt;&lt;td&gt;consegna (consegna)&lt;/td&gt;&lt;td&gt;Consegna&lt;/td&gt;&lt;td&gt;collegamento &lt;/td&gt;&lt;td&gt; &lt;/td&gt;&lt;/td&gt;&lt;td&lt;tr&gt;&lt;td&gt;deliveryId&lt;/td&gt;&lt;td&gt;ID dell'ultima consegna&lt;/td&gt;&lt;td&gt;numero intero &lt;/td&gt;&lt;td&gt; &lt;/td&gt;&lt;/tr&gt;&lt;tr&gt;&lt;td&gt;desc&lt;/td&gt;&lt;td&gt;Descrizione&lt;/td&gt;stringa (512)&lt;/td&gt;&lt;td&gt; &lt;/td&gt;&lt;/td&gt;&lt;/tr &lt;tr&gt;&lt;td&gt;email&lt;/td&gt;&lt;td&gt;Email&lt;/td&gt;&lt;td&gt;stringa (128)&lt;/td&gt;&lt;td&gt; &lt;/td&gt;&lt;/tr&gt;&lt;tr&gt;&lt;td&gt;externalId&lt;/td&gt;&lt;td&gt;ID esterno&lt;/td&gt;&lt;td&gt;stringa (64)&lt;/td&gt;&lt;td&gt; &lt;/td&gt;/tr&gt;&lt;tr&gt;&lt;td&gt;Nome&lt;/td&gt;Nome&lt;/td&gt;Nome&lt;/td&gt;&lt;td&gt;Stringa (30)&lt;/td&gt;&lt;td&gt; &lt;/td&gt;&lt;/td&gt;Nome&lt;/td&gt;Nome&lt;/td&gt;Nome&lt;/td&gt;UrlAvanti&lt;/td&gt;Corda (255)&lt;/td&gt;&lt;td&gt;&lt;td &lt;/td&gt;&lt;/tr&gt;&lt;tr&gt;&lt;td&gt;geoUnit (geoUnitBase)&lt;/td&gt;&lt;td&gt;Unità geografica&lt;/td&gt;&gt;link &lt;/td&gt;link &lt;/td&gt;&lt;td&gt;&gt; &lt;/td&gt;&gt;&lt;tr&gt;lastModified&lt;/td&gt;Anteprima&lt;td&lt;/td&gt;Data &lt;/td &lt;td&gt; &lt;/td&gt;&lt;/tr&gt;&lt;tr&gt;&lt;td&gt;lastName&lt;/td&gt;&lt;td&gt;Cognome&lt;/td&gt;&lt;td&gt;stringa (50)&lt;/td&gt;&lt;td&gt; &lt;/td&gt;&lt;/tr&gt;&lt;td&gt;modificataDa (userBase)&lt;/td&gt;con&lt;td&gt;Modified&lt;/td&gt;&lt;td&gt;link&gt;link&lt;td&gt; &lt;/td&gt;&lt;/tr&gt;&lt;td&gt;orgUnit (orgUnitBase)&lt;/td&gt;&lt;td&gt;Unità organizzativa&lt;/td&gt;&lt;td&gt;collegamento &lt;/td&gt;link&lt;/td&gt;&lt;td&gt; &lt;/td&gt;/tr&gt;&lt;tr&gt;&lt;tr&gt;&lt;td&gt;origine&lt;/td&gt;Nascosto&lt;/td&gt;Origin&lt;/td&gt;&gt;enumerazione &lt;/td&gt;&lt;td&gt;&lt;ul&gt;Non definita - non definita - 0&lt;/li&gt;INVALID VALUE - __Invalid_value__ - __Invalid_value_____&lt;/li&gt;&lt;/ul&gt;profilo&lt;/tr&gt;&lt;/tr&gt;provider&lt;tr&gt;ordinato&lt;td&gt;destinatario (destinatario)&lt;/td&gt;&lt;td&gt;Identificato&lt;/td&gt;collegamento &lt;/td&gt;&lt;td&gt;&lt;td&gt; &lt;/td&gt;&lt;/tr&gt;&lt;td&gt;id&lt;/td&gt;&lt;td&gt;ID profilo&lt;/td&gt;&lt;/td&gt;Numero intero &lt;/td&gt;&lt;td&gt; &lt;/td&gt;&lt;/tr&gt;&lt;tr&gt;referrerEmail&lt;/td&gt;referrerEmail&lt;/td&gt;&lt;td&lt;td td&gt;&lt;td&gt;stringa (128)&lt;/td&gt;&lt;td&gt; &lt;/td&gt;&lt;/tr&gt;&lt;td&gt;referrerFirstName&lt;/td&gt;&lt;td&gt;Nome di riferimento&lt;/td&gt;&lt;td&gt;Stringa (30)&lt;/td&gt;&lt;td&gt; &lt;/td&gt;&lt;/tr&gt;&lt;rtr&gt;&lt;rtf erId&lt;/td&gt;&lt;td&gt;ID referente&lt;/td&gt;&lt;td&gt;Numero intero &lt;/td&gt;&lt;td&gt; &lt;/td&gt;&lt;/tr&gt;&lt;tr&gt;&lt;td&gt;referrerLastName&lt;/td&gt;tr&lt;td&gt;Cognome referente&lt;/td&gt;Stringa (50)&lt;/td&gt;&lt;td&lt;&gt;&lt;/td&gt;&lt;/td &lt;tr&gt;&lt;td&gt;referrerRcp (destinatario)&lt;/td&gt;&lt;td&gt;Referrer&lt;/td&gt;&lt;td&gt;link &lt;/td&gt;&lt;td&gt; &lt;/td&gt;&lt;/td&gt;&lt;tr&gt;&lt;td&gt;title&lt;/td&gt;Etichetta&lt;/td&gt;&lt;td&gt;Stringa (255)&lt;/td&gt;&lt;td&gt; &lt;/td&gt; &lt;/tr&gt;&lt;/table&gt;

## Filtri

Per cognome, nome o e-mail (per testo)</p>

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