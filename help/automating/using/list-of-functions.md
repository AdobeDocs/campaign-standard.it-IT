---
title: Elenco delle funzioni
seo-title: Elenco delle funzioni
description: Elenco delle funzioni
seo-description: Lo strumento di modifica delle query consente di utilizzare funzioni avanzate per filtrare più facilmente.
page-status-flag: never-activated
uuid: fd 50 fc 99-1 e 7 a -479 b-beb 7-1 f 246 b 419 d 46
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automazione
content-type: riferimento
topic-tags: filtering-data
discoiquuid: 3 cdbe 962-1 c 59-4 cd 8-b 29 e -36 aa 2562 fac 6
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 83be3f22f3508248f2a4666080a7207998093dc3

---


# Elenco delle funzioni{#list-of-functions}

## Informazioni sulle funzioni {#about-functions}

Lo strumento di modifica delle query consente di utilizzare funzioni avanzate per filtrare più facilmente. A tal fine, la palette dello strumento contiene l' **[!UICONTROL Expression]** elemento che è possibile utilizzare nell'area di lavoro. Ulteriori informazioni su questo elemento sono dettagliate in una [sezione specifica](../../automating/using/advanced-expression-editing.md).

Questo elemento consente di inserire manualmente le condizioni. Qui è possibile utilizzare le funzioni definite nelle sezioni seguenti.

Sono disponibili diversi tipi di funzioni, a seconda dei risultati desiderati e dei tipi di dati manipolati:

* Date
* Geomarketing
* Valori numerici
* Altre funzioni
* Aggregati
* Manipolazione stringa
* Ordinamento

## Date {#dates}

Le funzioni della data vengono utilizzate per manipolare i valori di data e ora.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Nome</strong><br /> </td> 
   <td> <strong>Descrizione</strong><br /> </td> 
   <td> <strong>Sintassi</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Adddays</strong><br /> </td> 
   <td> Aggiunge un numero di giorni a una data<br /> </td> 
   <td> Adddays (&lt; data &gt;, &lt; numero &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Addhours</strong><br /> </td> 
   <td> Aggiunge un numero di ore a una data<br /> </td> 
   <td> Addhours (&lt; data &gt;, &lt; numero &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Addminutes</strong><br /> </td> 
   <td> Aggiunge un numero di minuti a una data<br /> </td> 
   <td> Addminutes (&lt; data &gt;, &lt; numero &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Addmonth</strong><br /> </td> 
   <td> Aggiunge un numero di mesi a una data<br /> </td> 
   <td> Addmonths (&lt; data &gt;, &lt; numero &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Addseconds</strong><br /> </td> 
   <td> Aggiunge un numero di secondi a una data<br /> </td> 
   <td> Addseconds (&lt; data &gt;, &lt; numero &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Addyears</strong><br /> </td> 
   <td> Aggiunge un numero di anni a una data<br /> </td> 
   <td> Addyears (&lt; data &gt;, &lt; numero &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Dateonly</strong><br /> </td> 
   <td> Restituisce solo la data (con il tempo alle 00:00)<br /> </td> 
   <td> Dateonly (&lt; data &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Giorno</strong><br /> </td> 
   <td> Restituisce il numero che rappresenta il giorno della data<br /> </td> 
   <td> Giorno (&lt; data &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Dayofyear</strong><br /> </td> 
   <td> Restituisce un numero che rappresenta il giorno nell'anno della data<br /> </td> 
   <td> Dayofyear (&lt; data &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Daysago</strong><br /> </td> 
   <td> Restituisce la data corrente meno n giorni<br /> </td> 
   <td> Daysago (&lt; numero &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Daysagoint</strong><br /> </td> 
   <td> Restituisce la data corrente meno n giorni (come numero intero yyyymmdd)<br /> </td> 
   <td> Daysagoint (&lt; numero &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Daysdiff</strong><br /> </td> 
   <td> Numero di giorni tra due date<br /> </td> 
   <td> Daysdiff (&lt; data di fine &gt;, &lt; data iniziale &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Daysell</strong><br /> </td> 
   <td> Restituisce l'età in giorni di una data<br /> </td> 
   <td> Daysell (&lt; data &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Getdate</strong><br /> </td> 
   <td> Restituisce la data di sistema corrente del server.<br /> </td> 
   <td> Getdate ()<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Ora</strong><br /> </td> 
   <td> Restituisce l'ora della data<br /> </td> 
   <td> Ora (&lt; data &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Hoursdiff</strong><br /> </td> 
   <td> Restituisce il numero di ore tra due date<br /> </td> 
   <td> Hoursdiff (&lt; data di fine &gt;, &lt; data iniziale &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Localtoutc</strong><br /> </td> 
   <td> Converte una data e un'ora locali in UTC<br /> </td> 
   <td> Localtoutc (&lt; data &gt;, &lt; Fuso orario &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Minuto</strong><br /> </td> 
   <td> Restituisce i minuti della data<br /> </td> 
   <td> Minuto (&lt; data &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Minutesdiff</strong><br /> </td> 
   <td> Restituisce il numero di minuti tra due date<br /> </td> 
   <td> Minutesdiff (&lt; data di fine &gt;, &lt; data iniziale &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Mese</strong><br /> </td> 
   <td> Restituisce il numero che rappresenta il mese della data<br /> </td> 
   <td> Mese (&lt; data &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Monthsago</strong><br /> </td> 
   <td> Restituisce la data corrispondente alla data corrente meno n mesi<br /> </td> 
   <td> Monthsago (&lt; numero &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Monthsdiff</strong><br /> </td> 
   <td> Restituisce il numero di mesi tra due date.<br /> </td> 
   <td> Monthsdiff (&lt; data di fine &gt;, &lt; data iniziale &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Monthsell</strong><br /> </td> 
   <td> Restituisce l'età in mesi di una data<br /> </td> 
   <td> Monthsell (&lt; data &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Secondo</strong><br /> </td> 
   <td> Restituisce i secondi della data<br /> </td> 
   <td> Secondo (&lt; data &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Meno recente</strong><br /> </td> 
   <td> Restituisce la data più obsoleta </td> 
   <td> Meno recente (&lt; Data &gt;, &lt; Data &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Secondsdiff</strong><br /> </td> 
   <td> Restituisce il numero di secondi tra due date<br /> </td> 
   <td> Secondsdiff (&lt; data di fine &gt;, &lt; data iniziale &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Subdays</strong><br /> </td> 
   <td> Sottrae un numero di giorni da una data<br /> </td> 
   <td> Subdays (&lt; data &gt;, &lt; numero &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Subhours</strong><br /> </td> 
   <td> Sottrae un numero di ore da una data<br /> </td> 
   <td> Subhours (&lt; data &gt;, &lt; numero &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Subminutes</strong><br /> </td> 
   <td> Sottrae un numero di minuti da una data<br /> </td> 
   <td> Subminutes (&lt; data &gt;, &lt; numero &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Submonth</strong><br /> </td> 
   <td> Sottrae un numero di mesi da una data<br /> </td> 
   <td> Submonths (&lt; data &gt;, &lt; numero &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Subseconds</strong><br /> </td> 
   <td> Sottrae un numero di secondi da una data<br /> </td> 
   <td> Subseconds (&lt; data &gt;, &lt; numero &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Subyears</strong><br /> </td> 
   <td> Sottrae un numero di anni da una data<br /> </td> 
   <td> Subyears (&lt; data &gt;, &lt; numero &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Todate</strong><br /> </td> 
   <td> Converte una data + ora come data<br /> </td> 
   <td> Todate (&lt; data + ora &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Todatetime</strong><br /> </td> 
   <td> Converte una stringa in una data + ora<br /> </td> 
   <td> Todatetime (&lt; stringa &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Todatetimewithtimezone</strong><br /> </td> 
   <td> Converte una stringa in una data + fuso orario.<br /> Esempio: Todatetimewithtimezone ("2019-02-19 08:09:00", "Asia/Tehran")<br /> </td> 
   <td> Todatetimewithtimezone (&lt; stringa &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Truncdate</strong><br /> </td> 
   <td> Arrotonda una data + ora al secondo più vicino<br /> </td> 
   <td> Truncdate (@ lastmodified, &lt; numero di secondi &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Truncdatetz</strong><br /> </td> 
   <td> Arrotonda una data + ora a una data specificata espressa in secondi<br /> </td> 
   <td> Truncdatetz (&lt; data &gt;, &lt; numero di secondi &gt;, &lt; fuso orario &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Truncquarter</strong><br /> </td> 
   <td> Arrotonda una data al trimestre<br /> </td> 
   <td> Truncquarter (&lt; data &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Trunctime</strong><br /> </td> 
   <td> Arrotonda la parte temporale fino al secondo<br /> </td> 
   <td> Trunctime (&lt; data &gt;, &lt; numero di secondi &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Truncweek</strong><br /> </td> 
   <td> Arrotonda una data alla settimana<br /> </td> 
   <td> Truncweek (&lt; data &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Truncyear</strong><br /> </td> 
   <td> Arrotonda una data + ora al 1 ° dell'anno<br /> </td> 
   <td> Truncyear (&lt; data &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Weekday</strong><br /> </td> 
   <td> Restituisce il numero che rappresenta il giorno nella settimana della data<br /> </td> 
   <td> Weekday (&lt; data &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Anno</strong><br /> </td> 
   <td> Restituisce il numero che rappresenta l'anno della data<br /> </td> 
   <td> Anno (&lt; data &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Yearand Month</strong><br /> </td> 
   <td> Restituisce il numero che rappresenta l'anno e il mese della data<br /> </td> 
   <td> Yearandmonth (&lt; data &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Yearsdiff</strong><br /> </td> 
   <td> Restituisce il numero di anni tra le due date<br /> </td> 
   <td> Yearsdiff (&lt; data di fine &gt;, &lt; data iniziale &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Yearsell</strong><br /> </td> 
   <td> Restituisce l'età in anni di una data<br /> </td> 
   <td> Yearsell (&lt; data &gt;)<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Geomarketing {#geomarketing}

Le funzioni geomarketing vengono utilizzate per manipolare i valori geografici.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Nome</strong><br /> </td> 
   <td> <strong>Descrizione</strong><br /> </td> 
   <td> <strong>Sintassi</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Distanza</strong><br /> </td> 
   <td> Restituisce la distanza in chilometri tra due punti definiti dalla relativa longitudine e latitudine (espresso in gradi).<br /> </td> 
   <td> Distanza (&lt; Longitudine A &gt;, &lt; Latitudine A &gt;, &lt; Longitudine B &gt;, &lt; Latitudine B &gt;)<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Numerico {#numerical}

Le funzioni di valore numerico consentono di convertire il testo in numeri.

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
   <td> Abs (&lt; numero &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Ceil</strong><br /> </td> 
   <td> Restituisce il numero intero più basso maggiore o uguale a un numero<br /> </td> 
   <td> Ceil (&lt; numero &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Floor</strong><br /> </td> 
   <td> Restituisce il numero intero maggiore maggiore o uguale a un numero<br /> </td> 
   <td> Floor (&lt; numero &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Maggiore</strong><br /> </td> 
   <td> Restituisce il numero massimo di due numeri<br /> </td> 
   <td> Maggiore (&lt; numero 1 &gt;, &lt; numero 2 &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Minima</strong><br /> </td> 
   <td> Restituisce un valore inferiore a due numeri<br /> </td> 
   <td> Least (&lt; numero 1 &gt;, &lt; numero 2 &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Mod</strong><br /> </td> 
   <td> Restituisce il resto della divisione integer da n 1 di n 2<br /> </td> 
   <td> Mod (&lt; numero 1 &gt;, &lt; numero 2 &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Percentuale</strong><br /> </td> 
   <td> Restituisce il rapporto di due numeri espresso come percentuale<br /> </td> 
   <td> Percent (&lt; numero 1 &gt;, &lt; numero 2 &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Casuale</strong><br /> </td> 
   <td> Restituisce il valore casuale<br /> </td> 
   <td> Random ()<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Round</strong><br /> </td> 
   <td> Arrotonda un numero a n decimali<br /> </td> 
   <td> Round (&lt; numero &gt;, &lt; numero di decimali &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Sign</strong><br /> </td> 
   <td> Restituisce il segno del numero<br /> </td> 
   <td> Firma (&lt; numero &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Todouble</strong><br /> </td> 
   <td> Converte un numero intero in un float<br /> </td> 
   <td> Todouble (&lt; numero &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ToInt64</strong><br /> </td> 
   <td> Converte un float in un numero intero a 64 bit<br /> </td> 
   <td> Toint 64 (&lt; numero &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Tointeger</strong><br /> </td> 
   <td> Converte un float in un numero intero<br /> </td> 
   <td> Tointeger (&lt; numero &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Trunc</strong><br /> </td> 
   <td> Tronca n 1 a n 2 decimali<br /> </td> 
   <td> Trunc (&lt; n 1 &gt;, &lt; n 2 &gt;)<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Altri {#others}

Questa tabella contiene le funzioni rimanenti avalaible.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Nome</strong><br /> </td> 
   <td> <strong>Descrizione</strong><br /> </td> 
   <td> <strong>Sintassi</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Maiuscole/minuscole</strong><br /> </td> 
   <td> Restituisce il valore 1 se la condizione viene verificata. In caso contrario, restituisce il valore 2<br /> </td> 
   <td> Maiuscole/minuscole (&lt; condizione &gt;, &lt; valore 1 &gt;), Else (&lt; valore 2 &gt;))<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Clearbit</strong><br /> </td> 
   <td> Elimina il flag nel valore<br /> </td> 
   <td> Clearbit (&lt; identificatore &gt;, &lt; flag &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Coalante</strong><br /> </td> 
   <td> Restituisce il valore 2 se il valore 1 è zero o null, altrimenti restituisce value 1<br /> </td> 
   <td> Coalancy (&lt; valore 1 &gt;, &lt; valore 2 &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Decode</strong><br /> </td> 
   <td> Restituisce valore 3 è valore 1 = valore 2, altrimenti restituisce 4<br /> </td> 
   <td> Decode (&lt; valore 1 &gt;, &lt; valore 2 &gt;, &lt; valore 3 &gt;, &lt; valore 4 &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Else</strong><br /> </td> 
   <td> Restituisce il valore 1 (può essere utilizzato solo come parametro della funzione maiuscolo/minuscolo)<br /> </td> 
   <td> Else (&lt; valore 1 &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Getemaildomain</strong><br /> </td> 
   <td> Estrae il dominio da un indirizzo e-mail<br /> </td> 
   <td> Getemaildomain (&lt; valore &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Getmirrorurl</strong><br /> </td> 
   <td> Recupera l'URL del server della pagina speculare<br /> </td> 
   <td> Getmirrorurl (&lt; valore &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Iif</strong><br /> </td> 
   <td> Restituisce il valore 1 se l'espressione è true, altrimenti restituisce value 2<br /> </td> 
   <td> Iif (&lt; condizione &gt;, &lt; valore 1 &gt;, &lt; valore 2 &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Isbitset</strong><br /> </td> 
   <td> Indica se il flag è incluso nel valore<br /> </td> 
   <td> Isbitset (&lt; identificatore &gt;, &lt; flag &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Isemptystring</strong><br /> </td> 
   <td> Restituisce il valore 2 se la stringa è vuota, altrimenti restituisce value 3<br /> </td> 
   <td> Isemptystring (&lt; stringa &gt;, &lt; valore 2 &gt;, &lt; valore 3 &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Nonull</strong><br /> </td> 
   <td> Restituisce la stringa vuota se l'argomento è NULL<br /> </td> 
   <td> Nonull (&lt; valore &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Rowid</strong><br /> </td> 
   <td> Restituisce il numero della riga<br /> </td> 
   <td> Rowid<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Setbit</strong><br /> </td> 
   <td> Forza il flag nel valore<br /> </td> 
   <td> Setbit (&lt; identificatore &gt;, &lt; flag &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Toboolean</strong><br /> </td> 
   <td> Converte un numero in un booleano<br /> </td> 
   <td> Toboolean (&lt; numero &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Quando</strong><br /> </td> 
   <td> Restituisce il valore 1 se l'espressione viene verificata. In caso contrario, restituisce il valore 2 (può essere utilizzato solo come parametro della funzione maiuscola)<br /> </td> 
   <td> Quando (&lt; condizione &gt;, &lt; valore 1 &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Newuuid</strong><br /> </td> 
   <td> Restituisce un nuovo UUID.<br /> </td> 
   <td> Newuuid<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Stringa {#string}

Le funzioni stringa vengono utilizzate per manipolare un set di stringhe.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Nome</strong><br /> </td> 
   <td> <strong>Descrizione</strong><br /> </td> 
   <td> <strong>Sintassi</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>AllNonNull2</strong><br /> </td> 
   <td> Indica se tutti i parametri sono non-null e non sono vuoti<br /> </td> 
   <td> Allnonnull 2 (&lt; stringa &gt;, &lt; stringa &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>AllNonNull3</strong><br /> </td> 
   <td> Indica se tutti i parametri sono non-null e non sono vuoti<br /> </td> 
   <td> Allnonnull 3 (&lt; stringa &gt;, &lt; stringa &gt;, &lt; stringa &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ASCII</strong><br /> </td> 
   <td> Restituisce il valore ASCII del primo carattere nella stringa<br /> </td> 
   <td> ASCII (&lt; stringa &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Char</strong><br /> </td> 
   <td> Restituisce il carattere corrispondente al codice ASCIl'n '<br /> </td> 
   <td> Carattere (&lt; numero &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Charindex</strong><br /> </td> 
   <td> Restituisce la posizione della stringa 2 nella stringa 1.<br /> </td> 
   <td> Charindex (&lt; stringa &gt;, &lt; stringa &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Datalength</strong><br /> </td> 
   <td> Restituisce il numero di caratteri in una stringa.<br /> </td> 
   <td> Datalength (&lt; String &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Getline</strong><br /> </td> 
   <td> Restituisce la n. nth (da 1 a n) della stringa<br /> </td> 
   <td> Getline (&lt; stringa &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Ifequals</strong><br /> </td> 
   <td> Restituisce il terzo parametro se i primi due parametri sono uguali in caso contrario restituisce l'ultimo parametro.<br /> </td> 
   <td> Ifequals (&lt; stringa &gt;, &lt; stringa &gt;, &lt; stringa &gt;, &lt; stringa &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Ismemonull</strong><br /> </td> 
   <td> Indica se la memo passata come parametro è null<br /> </td> 
   <td> Ismemonull (&lt; Memo &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Juxtwords</strong><br /> </td> 
   <td> Configura le due stringhe passate come parametri. Uno spazio viene aggiunto tra ciascuna stringa nel valore restituito.<br /> </td> 
   <td> Juxtwords (&lt; stringa &gt;, &lt; stringa &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>JuxtWords3</strong><br /> </td> 
   <td> Configura le tre stringhe passate come parametri. Uno spazio viene aggiunto tra ciascuna stringa nel valore restituito.<br /> </td> 
   <td> Juxtwords 3 (&lt; stringa &gt;, &lt; stringa &gt;, &lt; stringa &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Lpad</strong><br /> </td> 
   <td> Restituisce la stringa completata a sinistra<br /> </td> 
   <td> Lpad (&lt; stringa &gt;, &lt; numero &gt;, &lt; caractère &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Sinistra</strong><br /> </td> 
   <td> Restituisce i primi caratteri n della stringa<br /> </td> 
   <td> Left (&lt; stringa &gt;, &lt; numero &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Lunghezza</strong><br /> </td> 
   <td> Restituisce la lunghezza della stringa<br /> </td> 
   <td> Lunghezza (&lt; stringa &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Lower</strong><br /> </td> 
   <td> Restituisce la stringa in minuscolo<br /> </td> 
   <td> Lower (&lt; stringa &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Ltrim</strong><br /> </td> 
   <td> Rimuove gli spazi a sinistra della stringa<br /> </td> 
   <td> Ltrim (&lt; stringa &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Md5Digest</strong><br /> </td> 
   <td> Restituisce una rappresentazione esadecimale della chiave MD 5 di una stringa.<br /> </td> 
   <td> Md 5 Digest (&lt; stringa &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Memocontains</strong><br /> </td> 
   <td> Specifica se il memo contiene la stringa passata come parametro<br /> </td> 
   <td> Memocontains (&lt; memo &gt;, &lt; stringa &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Rpad</strong><br /> </td> 
   <td> Restituisce la stringa completata sulla destra<br /> </td> 
   <td> Rpad (&lt; stringa &gt;, &lt; numero &gt;, &lt; carattere &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Replace (Sostituisci)</strong><br /> </td> 
   <td> Sostituisce tutte le occorrenze di un valore stringa specificato (2 nd parameter) con un altro valore di stringa (3 rd parameter) in una stringa (parametro 1 st)<br /> </td> 
   <td> Replace (&lt; String &gt;, &lt; String &gt;, &lt; String &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Destra</strong><br /> </td> 
   <td> Restituisce gli ultimi caratteri n della stringa<br /> </td> 
   <td> Right (&lt; stringa &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Rtrim</strong><br /> </td> 
   <td> Rimuove gli spazi a destra della stringa<br /> </td> 
   <td> Rtrim (&lt; stringa &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Sha256Digest</strong><br /> </td> 
   <td> Calcola l'hash <strong>SHA 256</strong> standard per una determinata stringa UTF 8<br /> </td> 
   <td> Sha 256 Digest (&lt; String &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Sha384Digest</strong><br /> </td> 
   <td> Calcola l'hash <strong>SHA 384</strong> standard per una determinata stringa UTF 8<br /> </td> 
   <td> Sha 384 Digest (&lt; String &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Sha512Digest</strong><br /> </td> 
   <td> Calcola l'hash <strong>SHA 512</strong> standard per una determinata stringa UTF 8<br /> </td> 
   <td> Sha 512 Digest (&lt; String &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Smart</strong><br /> </td> 
   <td> Restituisce la stringa con la prima lettera di ciascuna parola in maiuscolo.<br /> </td> 
   <td> Smart (&lt; stringa &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Sottostringa</strong><br /> </td> 
   <td> Estrae la stringa a partire dal carattere n 1 della stringa e con un valore n 2.<br /> </td> 
   <td> Substring (&lt; stringa &gt;, &lt; offset &gt;, &lt; lunghezza &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Tointlstring</strong><br /> </td> 
   <td> Converte il numero in una stringa<br /> </td> 
   <td> Tointlstring (&lt; numero &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Tostring</strong><br /> </td> 
   <td> Converte il numero in una stringa<br /> </td> 
   <td> Tostring (&lt; numero &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Upper</strong><br /> </td> 
   <td> Restituisce la stringa in lettere maiuscole<br /> </td> 
   <td> Upper (&lt; stringa &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Virtuallink</strong><br /> </td> 
   <td> Restituisce la chiave esterna di un collegamento passato come parametro se gli altri due parametri sono uguali<br /> </td> 
   <td> Virtuallink (&lt; numero &gt;, &lt; numero &gt;, &lt; numero &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Virtuallinkstr</strong><br /> </td> 
   <td> Restituisce la chiave esterna (testo) di un collegamento passato come parametro se gli altri due parametri sono uguali<br /> </td> 
   <td> Virtuallinkstr (&lt; stringa &gt;, &lt; numero &gt;, &lt; numero &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>encryption_ aescbcdecrypt</strong><br /> </td> 
   <td> Decrittografa un valore crittografato in formato HEX con il prefisso<strong>"x</strong>" (parametro 1 st) utilizzando una chiave in formato HEX (2 nd) e un vettore di inizializzazione in formato HEX (3 rd parameter)<br /> </td> 
   <td> encryption_ aescbcdecrypt (&lt; String &gt;, &lt; String &gt;, &lt; String &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>encryption_ aescbcencrypt</strong><br /> </td> 
   <td> Cifra utilizzando l'algoritmo AES (modalità blocco CBC) una stringa di caratteri (parametro 1 st) con una chiave (2 nd parametro) e un vettore di inizializzazione (3 rd parameter). La chiave e il vettore di inizializzazione devono essere forniti sotto forma di rappresentazione esadecimale (a partire <strong>da\ x</strong>). Il risultato sarà esadecimale senza <strong>\ x</strong>.<br /> Tenere presente che la dimensione della chiave può essere pari a 128 bit, 192 bit, 256 bit (16, 24, 32 caratteri esadecimali) ma consigliamo di utilizzare 256 bit e un IV casuale della stessa lunghezza della chiave.<br /> </td> 
   <td> encryption_ aescbcencrypt (&lt; String &gt;, &lt; String &gt;, &lt; String &gt;)<br /> , ad esempio: encryption_ aescbcencrypt (johndoe@example.com, "<strong>\ x 0123456789 ABCDEF 0123456789 ABCDEF</strong>", "<strong>\ x 0123456789 ABCDEFFEDCBA 9876543210</strong>")<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Aggregati {#aggregates}

Le funzioni di aggregazione sono disponibili solo [quando si aggiungono dati aggiuntivi](../../automating/using/query.md#enriching-data) dall **[!UICONTROL Query]** 'attività di un flusso di lavoro.

Le funzioni di aggregazione vengono utilizzate per eseguire calcoli su un insieme di valori.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Nome</strong><br /> </td> 
   <td> <strong>Descrizione</strong><br /> </td> 
   <td> <strong>Sintassi</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Avg</strong>, Media<br /> </td> 
   <td> Restituisce la media in una colonna numerica.<br /> </td> 
   <td> Avg (&lt; valore &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Count</strong>, Count (tranne NULL)<br /> </td> 
   <td> Conta i valori non-null in una colonna.<br /> </td> 
   <td> Count (&lt; valore &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Countall</strong>, Count<br /> </td> 
   <td> Conta tutti i valori (compresi valori null e duplicati).<br /> </td> 
   <td> Countall ()<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Countdistinct</strong>, Numero distinto<br /> </td> 
   <td> Conta i valori non-null e distinti in una colonna.<br /> </td> 
   <td> Countdistinct (&lt; valore &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Max</strong>, Max<br /> </td> 
   <td> Restituisce il valore massimo in una colonna numerica, numerica o data.<br /> </td> 
   <td> Max (&lt; valore &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Min</strong>, Min<br /> </td> 
   <td> Restituisce il valore minimo in una colonna numerica, numerica o data.<br /> </td> 
   <td> Min (&lt; valore &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Sum</strong>, Sum<br /> </td> 
   <td> Restituisce la somma dei valori in una colonna numerica.<br /> </td> 
   <td> Sum (&lt; valore &gt;)<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Rappresentazione {#representation}

Le funzioni di rappresentazione vengono utilizzate per l'ordine dei valori.

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
   <td> Desc (&lt; valore 1 &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Orderby</strong><br /> </td> 
   <td> Ordina il risultato all'interno della partizione<br /> </td> 
   <td> Orderby (&lt; valore 1 &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Partitionby</strong><br /> </td> 
   <td> Partisce il risultato di una query su una tabella<br /> </td> 
   <td> Partitionby (&lt; valore 1 &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Rownum</strong><br /> </td> 
   <td> Genera un numero di riga basato sulla partizione della tabella e su una sequenza di ordinamento. Questa funzione non è supportata per mysql<br /> </td> 
   <td> Rownum (partitionby (&lt; valore 1 &gt;), orderby (&lt; valore 1 &gt;))<br /> </td> 
  </tr> 
 </tbody> 
</table>

