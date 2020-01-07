---
title: Elenco delle funzioni
description: Lo strumento di modifica delle query consente di utilizzare funzioni avanzate per eseguire filtri complessi.
page-status-flag: never-activated
uuid: fd50fc99-1e7a-479b-beb7-1f246b419d46
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: filtering-data
discoiquuid: 3cdbe962-1c59-4cd8-b29e-36aa2562fac6
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: fa9d2be71b4bbf5eceadbd1835db324618f9529c

---


# Elenco delle funzioni{#list-of-functions}

## Informazioni sulle funzioni {#about-functions}

Lo strumento di modifica delle query consente di utilizzare funzioni avanzate per eseguire filtri complessi. A tal fine, la palette degli strumenti contiene l&#39; **[!UICONTROL Expression]**elemento che è possibile utilizzare nell&#39;area di lavoro. Ulteriori informazioni su questo elemento sono dettagliate in una sezione[](../../automating/using/advanced-expression-editing.md)specifica.

Questo elemento consente di inserire manualmente le condizioni. Qui è possibile utilizzare le funzioni definite nelle sezioni seguenti.

Sono disponibili diversi tipi di funzioni, a seconda dei risultati desiderati e dei tipi di dati manipolati:

* Date
* Geomarketing
* Valori numerici
* Altre funzioni
* Aggregati
* Modifica stringa
* Ordinamento

## Date {#dates}

Le funzioni data vengono utilizzate per manipolare i valori di data o ora.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Nome</strong><br /> </td> 
   <td> <strong>Descrizione</strong><br /> </td> 
   <td> <strong>Sintassi</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>AggiungiGiorni</strong><br /> </td> 
   <td> Aggiunge un numero di giorni a una data<br /> </td> 
   <td> AddDays(&lt;data&gt;, &lt;numero&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>AggiungiOre</strong><br /> </td> 
   <td> Aggiunge un numero di ore a una data<br /> </td> 
   <td> AddHours(&lt;data&gt;, &lt;numero&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Aggiungi minuti</strong><br /> </td> 
   <td> Aggiunge un numero di minuti a una data<br /> </td> 
   <td> AddMinutes(&lt;data&gt;, &lt;numero&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>AddMonths</strong><br /> </td> 
   <td> Aggiunge un numero di mesi a una data<br /> </td> 
   <td> AddMonths(&lt;data&gt;, &lt;numero&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>AggiungiSecondi</strong><br /> </td> 
   <td> Aggiunge un numero di secondi a una data<br /> </td> 
   <td> AddSeconds(&lt;data&gt;, &lt;numero&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Aggiungi anni</strong><br /> </td> 
   <td> Aggiunge un numero di anni a una data<br /> </td> 
   <td> Aggiungi anni(&lt;data&gt;, &lt;numero&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>DateOnly</strong><br /> </td> 
   <td> Restituisce solo la data (con l'ora a 00:00)<br /> </td> 
   <td> DateOnly(&lt;data&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Day</strong><br /> </td> 
   <td> Restituisce il numero che rappresenta il giorno della data<br /> </td> 
   <td> Day(&lt;date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>DayOfYear</strong><br /> </td> 
   <td> Restituisce un numero che rappresenta il giorno dell'anno della data<br /> </td> 
   <td> DayOfYear(&lt;data&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Giorni fa</strong><br /> </td> 
   <td> Restituisce la data corrente meno n giorni<br /> </td> 
   <td> DaysAgo(&lt;numero&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>DaysAgoInt</strong><br /> </td> 
   <td> Restituisce la data corrente meno n giorni (come numero intero yyyymmdd).<br /> </td> 
   <td> DaysgoInt(&lt;numero&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>DaysDiff</strong><br /> </td> 
   <td> Numero di giorni tra due date<br /> </td> 
   <td> DaysDiff(&lt;data di fine&gt;, &lt;data di inizio&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>DaysOld</strong><br /> </td> 
   <td> Restituisce l'età in giorni di una data<br /> </td> 
   <td> DaysOld(&lt;data&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>GetDate</strong><br /> </td> 
   <td> Restituisce la data di sistema corrente del server<br /> </td> 
   <td> GetDate()<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Ora</strong><br /> </td> 
   <td> Restituisce l'ora della data<br /> </td> 
   <td> Ora(&lt;data&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>OreDiff</strong><br /> </td> 
   <td> Restituisce il numero di ore tra due date<br /> </td> 
   <td> HoursDiff(&lt;data di fine&gt;, &lt;data di inizio&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>LocalToUTC</strong><br /> </td> 
   <td> Converte una data e un'ora locali in UTC<br /> </td> 
   <td> LocalToUTC(&lt;data&gt;, &lt;fuso orario&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Minuto</strong><br /> </td> 
   <td> Restituisce i minuti della data<br /> </td> 
   <td> Minute(&lt;data&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>MinutiDiff</strong><br /> </td> 
   <td> Restituisce il numero di minuti tra due date<br /> </td> 
   <td> MinutesDiff(&lt;data di fine&gt;, &lt;data di inizio&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Mese</strong><br /> </td> 
   <td> Restituisce il numero che rappresenta il mese della data<br /> </td> 
   <td> Mese(&lt;data&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Mesi Fa</strong><br /> </td> 
   <td> Restituisce la data corrispondente alla data corrente meno n mesi<br /> </td> 
   <td> Mesi fa(&lt;numero&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>MesiDiff</strong><br /> </td> 
   <td> Restituisce il numero di mesi compresi tra due date<br /> </td> 
   <td> MonthsDiff(&lt;data di fine&gt;, &lt;data di inizio&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>MesiVecchi</strong><br /> </td> 
   <td> Restituisce l'età in mesi di una data<br /> </td> 
   <td> MonthsOld(&lt;data&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Secondo</strong><br /> </td> 
   <td> Restituisce i secondi della data<br /> </td> 
   <td> Second(&lt;data&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Meno recente</strong><br /> </td> 
   <td> Restituisce la data meno recente </td> 
   <td> Meno recente(&lt;Data&gt;, &lt;Data&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>SecondsDiff</strong><br /> </td> 
   <td> Restituisce il numero di secondi tra due date<br /> </td> 
   <td> SecondsDiff(&lt;data di fine&gt;, &lt;data di inizio&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>SubDays</strong><br /> </td> 
   <td> Sottrae un numero di giorni da una data<br /> </td> 
   <td> SubDays(&lt;data&gt;, &lt;numero&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>SubHours</strong><br /> </td> 
   <td> Sottrae un numero di ore da una data<br /> </td> 
   <td> SubHours(&lt;data&gt;, &lt;numero&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Minuti secondari</strong><br /> </td> 
   <td> Sottrae un numero di minuti da una data<br /> </td> 
   <td> SubMinutes(&lt;data&gt;, &lt;numero&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>SubMonths</strong><br /> </td> 
   <td> Sottrae un numero di mesi da una data<br /> </td> 
   <td> SubMonths(&lt;data&gt;, &lt;numero&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>SubSeconds</strong><br /> </td> 
   <td> Sottrae un numero di secondi da una data<br /> </td> 
   <td> SubSeconds(&lt;data&gt;, &lt;numero&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>SubYears</strong><br /> </td> 
   <td> Sottrae un numero di anni da una data<br /> </td> 
   <td> SubYears(&lt;data&gt;, &lt;numero&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ToDate</strong><br /> </td> 
   <td> Converte una data + ora come data<br /> </td> 
   <td> ToDate(&lt;data + ora&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ToDateTime</strong><br /> </td> 
   <td> Converte una stringa in data + ora<br /> </td> 
   <td> ToDateTime(&lt;stringa&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ToDateTimeWithTimezone</strong><br /> </td> 
   <td> Converte una stringa in data + fuso orario.<br /> Esempio: ToDateTimeWithTimezone ("2019-02-19 08:09:00", "Asia/Teheran")<br /> </td> 
   <td> ToDateTimeWithTimezone(&lt;stringa&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>TruncDate</strong><br /> </td> 
   <td> Arrotonda data+ora al secondo più vicino<br /> </td> 
   <td> TruncDate(@lastModified, &lt;numero di secondi&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>TruncDateTZ</strong><br /> </td> 
   <td> Arrotonda data + ora a una determinata precisione, espressa in secondi<br /> </td> 
   <td> TruncDateTZ(&lt;data&gt;, &lt;numero di secondi&gt;, &lt;fuso orario&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>TruncQuarter</strong><br /> </td> 
   <td> Arrotonda una data al trimestre<br /> </td> 
   <td> TruncQuarter(&lt;data&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Tempi di esecuzione</strong><br /> </td> 
   <td> Arrotonda la parte temporale al secondo più vicino<br /> </td> 
   <td> TruncTime(&lt;data&gt;, &lt;numero di secondi&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>TruncWeek</strong><br /> </td> 
   <td> Arrotonda una data alla settimana<br /> </td> 
   <td> TruncWeek(&lt;data&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>AnnoTrunc</strong><br /> </td> 
   <td> Arrotonda una data + ora al 1° gennaio dell'anno<br /> </td> 
   <td> TruncYear(&lt;data&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>WeekDay</strong><br /> </td> 
   <td> Restituisce il numero che rappresenta il giorno della settimana della data<br /> </td> 
   <td> WeekDay(&lt;data&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Anno</strong><br /> </td> 
   <td> Restituisce il numero che rappresenta l'anno della data<br /> </td> 
   <td> Year(&lt;data&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Anno e mese</strong><br /> </td> 
   <td> Restituisce il numero che rappresenta l'anno e il mese della data<br /> </td> 
   <td> YearAndMonth(&lt;data&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>YearsDiff</strong><br /> </td> 
   <td> Restituisce il numero di anni tra le due date<br /> </td> 
   <td> YearsDiff(&lt;data di fine&gt;, &lt;data di inizio&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>YearsOld</strong><br /> </td> 
   <td> Restituisce l'età in anni di una data<br /> </td> 
   <td> YearsOld(&lt;data&gt;)<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Geomarketing {#geomarketing}

Le funzioni di geomarketing sono utilizzate per manipolare i valori geografici.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Nome</strong><br /> </td> 
   <td> <strong>Descrizione</strong><br /> </td> 
   <td> <strong>Sintassi</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Distanza</strong><br /> </td> 
   <td> Restituisce la distanza in chilometri tra due punti definiti dalla longitudine e dalla latitudine (espressa in gradi).<br /> </td> 
   <td> Distanza(&lt;Longitudine A&gt;, &lt;Latitudine A&gt;, &lt;Longitudine B&gt;, &lt;Latitudine B&gt;)<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Numerico {#numerical}

Le funzioni relative al valore numerico vengono utilizzate per convertire il testo in numeri.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Nome</strong><br /> </td> 
   <td> <strong>Descrizione</strong><br /> </td> 
   <td> <strong>Sintassi</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Abs</strong><br /> </td> 
   <td> Restituisce il valore assoluto di un numero<br /> </td> 
   <td> Abs(&lt;numero&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Ceil</strong><br /> </td> 
   <td> Restituisce il numero intero più basso maggiore o uguale a un numero<br /> </td> 
   <td> Ceil(&lt;numero&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Floor</strong><br /> </td> 
   <td> Restituisce il numero intero più grande minore o uguale a un numero<br /> </td> 
   <td> Floor(&lt;numero&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Maggiore</strong><br /> </td> 
   <td> Restituisce il numero maggiore di due numeri<br /> </td> 
   <td> Greatest(&lt;numero 1&gt;, &lt;numero 2&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Meno</strong><br /> </td> 
   <td> Restituisce il minore di due numeri<br /> </td> 
   <td> Least(&lt;numero 1&gt;, &lt;numero 2&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Mod</strong><br /> </td> 
   <td> Restituisce il resto della divisione del numero intero da n1 per n2<br /> </td> 
   <td> Mod(&lt;numero 1&gt;, &lt;numero 2&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Percentuale</strong><br /> </td> 
   <td> Restituisce il rapporto di due numeri espresso come percentuale<br /> </td> 
   <td> Percent(&lt;numero 1&gt;, &lt;numero 2&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Casuale</strong><br /> </td> 
   <td> Restituisce il valore casuale<br /> </td> 
   <td> Random()<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Round</strong><br /> </td> 
   <td> Arrotonda un numero a n decimali<br /> </td> 
   <td> Round(&lt;numero&gt;, &lt;numero di decimali&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Sign</strong><br /> </td> 
   <td> Restituisce il segno del numero<br /> </td> 
   <td> Sign(&lt;numero&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ToDouble</strong><br /> </td> 
   <td> Converte un numero intero in un float<br /> </td> 
   <td> ToDouble(&lt;numero&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ToInt64</strong><br /> </td> 
   <td> Converte un valore mobile in un numero intero a 64 bit<br /> </td> 
   <td> ToInt64(&lt;numero&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ToInteger</strong><br /> </td> 
   <td> Converte un float in un numero intero<br /> </td> 
   <td> ToInteger(&lt;numero&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Trunc</strong><br /> </td> 
   <td> Tronca i decimali da n1 a n2<br /> </td> 
   <td> Trunc(&lt;n1&gt;, &lt;n2&gt;)<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Altro {#others}

Questa tabella contiene le altre funzioni disponibili.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Nome</strong><br /> </td> 
   <td> <strong>Descrizione</strong><br /> </td> 
   <td> <strong>Sintassi</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Case</strong><br /> </td> 
   <td> Restituisce il valore 1 se la condizione è verificata. In caso contrario, restituisce il valore 2<br /> </td> 
   <td> Case(When(&lt;condition&gt;, &lt;valore 1&gt;), Else(&lt;valore 2&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ClearBit</strong><br /> </td> 
   <td> Elimina il contrassegno nel valore<br /> </td> 
   <td> ClearBit(&lt;identifier&gt;, &lt;flag&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Riposo</strong><br /> </td> 
   <td> Restituisce il valore 2 se il valore 1 è zero o null, altrimenti restituisce il valore 1<br /> </td> 
   <td> Coalesce(&lt;valore 1&gt;, &lt;valore 2&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Decode</strong><br /> </td> 
   <td> Restituisce il valore 3 è il valore 1 = valore 2, altrimenti restituisce 4<br /> </td> 
   <td> Decode(&lt;valore 1&gt;, &lt;valore 2&gt;, &lt;valore 3&gt;, &lt;valore 4&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Altro</strong><br /> </td> 
   <td> Restituisce il valore 1 (può essere utilizzato solo come parametro della funzione case)<br /> </td> 
   <td> Else(&lt;valore 1&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>GetEmailDomain</strong><br /> </td> 
   <td> Estrae il dominio da un indirizzo e-mail<br /> </td> 
   <td> GetEmailDomain(&lt;valore&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>GetMirrorURL</strong><br /> </td> 
   <td> Recupera l'URL del server delle pagine mirror<br /> </td> 
   <td> GetMirrorURL(&lt;valore&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Iif</strong><br /> </td> 
   <td> Restituisce il valore 1 se l'espressione è true, altrimenti restituisce il valore 2<br /> </td> 
   <td> Iif(&lt;condizione&gt;, &lt;valore 1&gt;, &lt;valore 2&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>IsBitSet</strong><br /> </td> 
   <td> Indica se il contrassegno si trova nel valore<br /> </td> 
   <td> IsBitSet(&lt;identifier&gt;, &lt;flag&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>IsEmptyString</strong><br /> </td> 
   <td> Restituisce il valore 2 se la stringa è vuota, altrimenti restituisce il valore 3<br /> </td> 
   <td> IsEmptyString(&lt;stringa&gt;, &lt;valore 2&gt;, &lt;valore 3&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>NoNull</strong><br /> </td> 
   <td> Restituisce la stringa vuota se l'argomento è NULL<br /> </td> 
   <td> NoNull(&lt;valore&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>RowId</strong><br /> </td> 
   <td> Restituisce il numero di riga<br /> </td> 
   <td> RowId<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>SetBit</strong><br /> </td> 
   <td> Forza il contrassegno nel valore<br /> </td> 
   <td> SetBit(&lt;identifier&gt;, &lt;flag&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ToBoolean</strong><br /> </td> 
   <td> Converte un numero in booleano<br /> </td> 
   <td> ToBoolean(&lt;numero&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Quando</strong><br /> </td> 
   <td> Restituisce il valore 1 se l'espressione è verificata. In caso contrario, restituisce il valore 2 (può essere utilizzato solo come parametro della funzione case)<br /> </td> 
   <td> Quando(&lt;condizione&gt;, &lt;valore 1&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>newUID</strong><br /> </td> 
   <td> Restituisce un nuovo UUID.<br /> </td> 
   <td> newUID<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Stringa {#string}

Le funzioni stringa vengono utilizzate per manipolare un insieme di stringhe.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Nome</strong><br /> </td> 
   <td> <strong>Descrizione</strong><br /> </td> 
   <td> <strong>Sintassi</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>AllNonNull2</strong><br /> </td> 
   <td> Indica se tutti i parametri non sono null e non sono vuoti<br /> </td> 
   <td> AllNonNull2(&lt;stringa&gt;, &lt;stringa&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>AllNonNull3</strong><br /> </td> 
   <td> Indica se tutti i parametri non sono null e non sono vuoti<br /> </td> 
   <td> AllNonNull3(&lt;stringa&gt;, &lt;stringa&gt;, &lt;stringa&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ASCII</strong><br /> </td> 
   <td> Restituisce il valore ASCII del primo carattere della stringa<br /> </td> 
   <td> Ascii(&lt;stringa&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Char</strong><br /> </td> 
   <td> Restituisce il carattere corrispondente al codice ASCII 'n'<br /> </td> 
   <td> Char(&lt;numero&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Charindex</strong><br /> </td> 
   <td> Restituisce la posizione della stringa 2 nella stringa 1<br /> </td> 
   <td> Charindex(&lt;stringa&gt;, &lt;stringa&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>DataLength</strong><br /> </td> 
   <td> Restituisce il numero di caratteri in una stringa<br /> </td> 
   <td> DataLength(&lt;String&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>GetLine</strong><br /> </td> 
   <td> Restituisce l'ennesima riga (da 1 a n) della stringa<br /> </td> 
   <td> GetLine(&lt;stringa&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>IfEquals</strong><br /> </td> 
   <td> Restituisce il terzo parametro se i primi due parametri sono uguali, altrimenti restituisce l'ultimo parametro<br /> </td> 
   <td> IfEquals(&lt;stringa&gt;, &lt;stringa&gt;, &lt;stringa&gt;, &lt;stringa&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>IsMemoNull</strong><br /> </td> 
   <td> Indica se il promemoria passato come parametro è null<br /> </td> 
   <td> IsMemoNull(&lt;Memo&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>JuxtWords</strong><br /> </td> 
   <td> Concede le due stringhe passate come parametri. Uno spazio viene aggiunto tra ciascuna stringa del valore restituito.<br /> </td> 
   <td> JuxtWords(&lt;stringa&gt;, &lt;stringa&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>JuxtWords3</strong><br /> </td> 
   <td> Concede le tre stringhe passate come parametri. Uno spazio viene aggiunto tra ciascuna stringa del valore restituito.<br /> </td> 
   <td> JuxtWords3(&lt;stringa&gt;, &lt;stringa&gt;, &lt;stringa&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>LP</strong><br /> </td> 
   <td> Restituisce la stringa completata a sinistra<br /> </td> 
   <td> LP(&lt;stringa&gt;, &lt;numero&gt;, &lt;caractère&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>A sinistra</strong><br /> </td> 
   <td> Restituisce i primi n caratteri della stringa<br /> </td> 
   <td> Left(&lt;stringa&gt;, &lt;numero&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Lunghezza</strong><br /> </td> 
   <td> Restituisce la lunghezza della stringa<br /> </td> 
   <td> Length(&lt;stringa&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Lower</strong><br /> </td> 
   <td> Restituisce la stringa in lettere minuscole<br /> </td> 
   <td> Lower(&lt;stringa&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Ltrim</strong><br /> </td> 
   <td> Rimuove gli spazi a sinistra della stringa<br /> </td> 
   <td> Ltrim(&lt;stringa&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Md5Digest</strong><br /> </td> 
   <td> Restituisce una rappresentazione esadecimale della chiave MD5 di una stringa<br /> </td> 
   <td> Md5Digest(&lt;stringa&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>MemoContains</strong><br /> </td> 
   <td> Specifica se la nota contiene la stringa passata come parametro<br /> </td> 
   <td> MemoContains(&lt;memo&gt;, &lt;stringa&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>RPad</strong><br /> </td> 
   <td> Restituisce la stringa completata sulla destra<br /> </td> 
   <td> RPad(&lt;stringa&gt;, &lt;numero&gt;, &lt;carattere&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Replace</strong><br /> </td> 
   <td> Sostituisce tutte le occorrenze di un valore stringa specificato (secondo parametro) con un altro valore stringa (terzo parametro) in una stringa (primo parametro).<br /> </td> 
   <td> Replace(&lt;String&gt;, &lt;String&gt;, &lt;String&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Destra</strong><br /> </td> 
   <td> Restituisce gli ultimi n caratteri della stringa<br /> </td> 
   <td> Right(&lt;stringa&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Rtrim</strong><br /> </td> 
   <td> Rimuove gli spazi a destra della stringa<br /> </td> 
   <td> Rtrim(&lt;stringa&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Sha256Digest</strong><br /> </td> 
   <td> Calcola l'hash standard <strong>SHA256</strong> per una stringa UTF8 specificata<br /> </td> 
   <td> Sha256Digest(&lt;String&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Sha384Digest</strong><br /> </td> 
   <td> Calcola l'hash standard <strong>SHA384</strong> per una stringa UTF8 specificata<br /> </td> 
   <td> Sha384Digest(&lt;String&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Sha512Digest</strong><br /> </td> 
   <td> Calcola l'hash standard <strong>SHA512</strong> per una stringa UTF8 specificata<br /> </td> 
   <td> Sha512Digest(&lt;String&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Smart</strong><br /> </td> 
   <td> Restituisce la stringa con la prima lettera di ciascuna parola in maiuscolo<br /> </td> 
   <td> Smart(&lt;stringa&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Sottostringa</strong><br /> </td> 
   <td> Estrae la sottostringa a partire dal carattere n1 della stringa e con una lunghezza n2<br /> </td> 
   <td> Substring(&lt;stringa&gt;, &lt;offset&gt;, &lt;lunghezza&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ToIntlString</strong><br /> </td> 
   <td> Converte il numero in una stringa<br /> </td> 
   <td> ToIntlString(&lt;numero&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ToString</strong><br /> </td> 
   <td> Converte il numero in una stringa<br /> </td> 
   <td> ToString(&lt;numero&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Upper</strong><br /> </td> 
   <td> Restituisce la stringa in lettere maiuscole<br /> </td> 
   <td> Upper(&lt;stringa&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>VirtualLink</strong><br /> </td> 
   <td> Restituisce la chiave esterna di un collegamento passato come parametro se gli altri due parametri sono uguali<br /> </td> 
   <td> VirtualLink(&lt;numero&gt;, &lt;numero&gt;, &lt;numero&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>VirtualLinkStr</strong><br /> </td> 
   <td> Restituisce la chiave esterna (testo) di un collegamento passato come parametro se gli altri due parametri sono uguali<br /> </td> 
   <td> VirtualLinkStr(&lt;stringa&gt;, &lt;numero&gt;, &lt;numero&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Encryption_aescbcDecrypt</strong><br /> </td> 
   <td> Decrittografa un valore crittografato in formato HEX con il prefisso "<strong>x</strong>" (primo parametro) utilizzando una chiave in formato HEX (secondo parametro) e un vettore di inizializzazione in formato HEX (terzo parametro)<br /> </td> 
   <td> Encryption_aescbcDecrypt(&lt;String&gt;, &lt;String&gt;, &lt;String&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Encryption_aescbcEncrypt</strong><br /> </td> 
   <td> Cifra utilizzando l'algoritmo AES (modalità blocco CBC) una stringa di caratteri (primo parametro) con una chiave (secondo parametro) e un vettore di inizializzazione (terzo parametro). La chiave e il vettore di inizializzazione devono essere forniti in una rappresentazione esadecimale (a partire da <strong>\x</strong>). Il risultato sarà esadecimale senza il <strong>\x</strong>.<br /> Le dimensioni chiave possono essere 128 bit, 192 bit, 256 bit (16, 24, 32 caratteri esadecimali), ma consigliamo di usare 256 bit e un IV randomizzato della stessa lunghezza della chiave.<br /> </td> 
   <td> Encryption_aescbcEncrypt(&lt;String&gt;, &lt;String&gt;, &lt;String&gt;)<br /> Ad esempio: Encryption_aescbcEncrypt(johndoe@example.com, "<strong>\x0123456789ABCDEF0123456789ABCDEF</strong>", "<strong>\x0123456789ABCDEFFEDBA 9876543210</strong>")<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Aggregati {#aggregates}

Le funzioni di aggregazione sono disponibili solo quando si [aggiungono dati](../../automating/using/query.md#enriching-data) aggiuntivi dall&#39; **[!UICONTROL Query]**attività di un flusso di lavoro.

Le funzioni di aggregazione vengono utilizzate per eseguire calcoli su un insieme di valori.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Nome</strong><br /> </td> 
   <td> <strong>Descrizione</strong><br /> </td> 
   <td> <strong>Sintassi</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Media</strong>, Media<br /> </td> 
   <td> Restituisce la media in una colonna numerica.<br /> </td> 
   <td> Avg(&lt;valore&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Count</strong>, Count (tranne NULL)<br /> </td> 
   <td> Conta i valori non-null in una colonna.<br /> </td> 
   <td> Count(&lt;valore&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>CountAll</strong>, Count all<br /> </td> 
   <td> Conta tutti i valori (inclusi valori null e duplicati).<br /> </td> 
   <td> CountAll()<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Contabilità distinta</strong>, conteggio distinto<br /> </td> 
   <td> Conta i valori distinti non-null in una colonna.<br /> </td> 
   <td> Countdistinte(&lt;valore&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Max</strong>, Max<br /> </td> 
   <td> Restituisce il valore massimo in una colonna numerica, stringa o data.<br /> </td> 
   <td> Max(&lt;valore&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Min</strong>, Min<br /> </td> 
   <td> Restituisce il valore minimo in una colonna numerica, stringa o data.<br /> </td> 
   <td> Min(&lt;valore&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Sum</strong>, Sum<br /> </td> 
   <td> Restituisce la somma dei valori in una colonna numerica.<br /> </td> 
   <td> Sum(&lt;valore&gt;)<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Rappresentanza {#representation}

Le funzioni di rappresentazione vengono utilizzate per ordinare i valori.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Nome</strong><br /> </td> 
   <td> <strong>Descrizione</strong><br /> </td> 
   <td> <strong>Sintassi</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Desc</strong><br /> </td> 
   <td> Applica un ordinamento decrescente<br /> </td> 
   <td> Desc(&lt;valore 1&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>OrderBy</strong><br /> </td> 
   <td> Ordina il risultato all'interno della partizione<br /> </td> 
   <td> OrderBy(&lt;valore 1&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>PartitionBy</strong><br /> </td> 
   <td> Partizioni il risultato di una query su una tabella<br /> </td> 
   <td> PartitionBy(&lt;valore 1&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>RowNum</strong><br /> </td> 
   <td> Genera un numero di riga basato sulla partizione della tabella e su una sequenza di ordinamento. Questa funzione non è supportata per MySQL<br /> </td> 
   <td> RowNum(PartitionBy(&lt;valore 1&gt;), OrderBy(&lt;valore 1&gt;)<br /> </td> 
  </tr> 
 </tbody> 
</table>

