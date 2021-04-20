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
source-wordcount: '691'
ht-degree: 6%

---


# Consegna (nms:delivery)

## Descrizione oggetto

<table>
               <tr>
                  <th>Nome</th>
                  <th>Etichetta</th>
                  <th>Tipo (lunghezza)</th>
                  <th>Valori di enumerazione</th>
               </tr>
               <tr>
                  <td>FCP</td>
                  <td>Prova</td>
                  <td>booleano </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>PKey</td>
                  <td>ID risorsa principale</td>
                  <td>string </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>abTesting</td>
                  <td>Test A/B</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>avanzato</td>
                  <td>Consegna avanzata</td>
                  <td>booleano </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>advancedParameters</td>
                  <td>Parametri avanzati</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>aemContents</td>
                  <td>Contenuto Adobe Experience Manager</td>
                  <td>raccolta </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>alertMessage</td>
                  <td>Messaggio di avviso</td>
                  <td>string </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>alertMode</td>
                  <td>Tipo di avviso</td>
                  <td>string </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>attacco</td>
                  <td>File allegati</td>
                  <td>raccolta </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>branding (brandingBase)</td>
                  <td>Brand</td>
                  <td>collegamento </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>wideLogs</td>
                  <td>Log di consegna</td>
                  <td>raccolta </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>incorporato</td>
                  <td>Oggetto applicativo incorporato</td>
                  <td>booleano </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>campaign (campaignBase)</td>
                  <td>Campagna</td>
                  <td>collegamento </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>cmsAccount (extAccountAEMBase)</td>
                  <td>Account Adobe Experience Manager</td>
                  <td>collegamento </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>comandi</td>
                  <td>Comandi</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>content</td>
                  <td>Contenuto</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>contentSource</td>
                  <td>Origine contenuto</td>
                  <td>enumerazione (byte) </td>
                  <td>
                     <ul>
                        <li>Adobe Experience Manager - aem - 1</li>
                        <li>Adobe Campaign - campagna - 0</li>
                        <li>VALORE NON VALIDO - __Invalid_value__ - __Invalid_value__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>contextResourceType</td>
                  <td>Tipo di risorsa</td>
                  <td>string </td>
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
                  <td>deliveryMode</td>
                  <td>Modalità di consegna</td>
                  <td>enumerazione (byte) </td>
                  <td>
                     <ul>
                        <li>Consegna in blocco - bulk - 1</li>
                        <li>mid-sourcing - midSourcing - 4</li>
                        <li>Descrizione - descrittivo - 2</li>
                        <li>VALORE NON VALIDO - __Invalid_value__ - __Invalid_value__</li>
                        <li>Esterno - esterno - 0</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>deliveryProvider (extAccountBase)</td>
                  <td>Indirizzamento</td>
                  <td>collegamento </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>desc</td>
                  <td>Descrizione</td>
                  <td>string (512)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>emailPreview</td>
                  <td>Anteprima e-mail</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>excludeLogs</td>
                  <td>Log di esclusione</td>
                  <td>raccolta </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>esclusioni</td>
                  <td>Cause di esclusione</td>
                  <td>raccolta </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>esecuzione</td>
                  <td>Parametri di esecuzione della consegna</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>executeType</td>
                  <td>Tipo di esecuzione</td>
                  <td>enumerazione (byte) </td>
                  <td>
                     <ul>
                        <li>Univoco - una tantum - 0</li>
                        <li>Continuo - continuo - 1</li>
                        <li>Centro messaggi - messageCenter - 2</li>
                        <li>VALORE NON VALIDO - __Invalid_value__ - __Invalid_value__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>ForecLogs</td>
                  <td>ForecastLog</td>
                  <td>raccolta </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>geoUnit (geoUnitBase)</td>
                  <td>Unità geografica</td>
                  <td>collegamento </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>hasAttachments</td>
                  <td>Aggiungi file allegati</td>
                  <td>booleano </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>icona</td>
                  <td>Icona</td>
                  <td>enumerazione (byte) </td>
                  <td>
                     <ul>
                        <li>E-mail transazionale - emailLightning - 60</li>
                        <li>Fax - fax - 4</li>
                        <li>Mobile (SMS) - sms - 1</li>
                        <li>E-mail ricorrente - emailRefresh - 30</li>
                        <li>Posta diretta - carta - 3</li>
                        <li>Telefono - 2</li>
                        <li>Altro - altri - 120</li>
                        <li>SMS ricorrenti - smsRefresh - 31</li>
                        <li>App mobile - pushNotification - 40</li>
                        <li>SMS transazionali - smsLightning - 61</li>
                        <li>E-mail - 0</li>
                        <li>VALORE NON VALIDO - __Invalid_value__ - __Invalid_value__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>isExternal</td>
                  <td>È una risorsa esterna</td>
                  <td>booleano </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>isMaster</td>
                  <td>Master</td>
                  <td>booleano </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>isTemplate</td>
                  <td>Modello</td>
                  <td>booleano </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>iterazioni</td>
                  <td>Consegne</td>
                  <td>raccolta </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>lavoro</td>
                  <td>Processo</td>
                  <td>raccolta </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>jobLogs</td>
                  <td>Registri</td>
                  <td>raccolta </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>kpis</td>
                  <td>Indicatori</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>etichetta</td>
                  <td>Etichetta</td>
                  <td>string (128)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>lastModified</td>
                  <td>Ultima modifica</td>
                  <td>date </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>logicalStatus</td>
                  <td>Stato di esecuzione</td>
                  <td>enumerazione (stringa) (255)</td>
                  <td>
                     <ul>
                        <li>In corso - avviato - avviato</li>
                        <li>Editing - edizione</li>
                        <li>Finito - finito - finito - finito</li>
                        <li>Avviso - avviso</li>
                        <li>Errore - Errore - Errore</li>
                        <li>VALORE NON VALIDO - __Invalid_value__ - __Invalid_value__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>mailParameters</td>
                  <td>Parametri di intestazione e-mail</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>mainDate</td>
                  <td>Data</td>
                  <td>date </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>mapping (deliveryMapping)</td>
                  <td>Mappatura del target</td>
                  <td>collegamento </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>master (deliveryBase)</td>
                  <td>Istanza principale</td>
                  <td>collegamento </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>masterKpis</td>
                  <td>Indicatori master</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>messageType</td>
                  <td>Canale</td>
                  <td>enumerazione (byte) </td>
                  <td>
                     <ul>
                        <li>Fax - fax - 4</li>
                        <li>Mobile (SMS) - sms - 1</li>
                        <li>E-mail - 0</li>
                        <li>Telefono - 2</li>
                        <li>Posta diretta - carta - 3</li>
                        <li>App mobile - pushNotification - 40</li>
                        <li>Altro - altri - 120</li>
                        <li>VALORE NON VALIDO - __Invalid_value__ - __Invalid_value__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>modifiedBy (userBase)</td>
                  <td>Modificato da</td>
                  <td>collegamento </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>name</td>
                  <td>ID</td>
                  <td>string (64)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>offerManagement</td>
                  <td>Gestione delle offerte</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>orgUnit (orgUnitBase)</td>
                  <td>Unità organizzativa</td>
                  <td>collegamento </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>parent (deliveryBase)</td>
                  <td>Consegna padre</td>
                  <td>collegamento </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>priorità</td>
                  <td>Priorità di consegna</td>
                  <td>enumerazione (byte) </td>
                  <td>
                     <ul>
                        <li>Alto - alto - 20</li>
                        <li>VALORE NON VALIDO - __Invalid_value__ - __Invalid_value__</li>
                        <li>Normale - normale - 10</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>programma (programBase)</td>
                  <td>programma</td>
                  <td>collegamento </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>bozze</td>
                  <td>Bozze</td>
                  <td>raccolta </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>pushNotificationPreview</td>
                  <td>Anteprima notifiche push</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>pushnotificationParameters</td>
                  <td>Parametri pushNotification</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>realtimeReport</td>
                  <td>Rapporti in tempo reale</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>resourceVersion</td>
                  <td>Versione risorsa</td>
                  <td>string (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>ribbonMessage</td>
                  <td>Messaggio a barre multifunzione</td>
                  <td>string </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>scenario</td>
                  <td>Parametri del modello di consegna</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>programmazione</td>
                  <td>Pianificazione delle consegne</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>smsParameters</td>
                  <td>Parametri SMS</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>smsPreview</td>
                  <td>Anteprima SMS</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>stato</td>
                  <td>Stato</td>
                  <td>enumerazione (byte) </td>
                  <td>
                     <ul>
                        <li>Avvia in sospeso - startPending - 51</li>
                        <li>Pronto per la consegna - pronto - 45</li>
                        <li>Riprova in sospeso - riprovaIn sospeso - 61</li>
                        <li>Nuovo tentativo in corso - tryInProgress - 62</li>
                        <li>Non riuscito - non riuscito - 87</li>
                        <li>In corso - avviato - 55</li>
                        <li>Targeting in sospeso - targetPrepPending - 11</li>
                        <li>Personalizzazione in sospeso - messagePrepPending - 21</li>
                        <li>In pausa - in pausa - 75</li>
                        <li>Editing - edizione - 0</li>
                        <li>Finito - finito - 95</li>
                        <li>Conteggio in corso - targetSelection - 12</li>
                        <li>Messaggio finalizzato - messageReady - 25</li>
                        <li>Personalizzazione o conteggio non riuscito - preparationError - 37</li>
                        <li>Arrestato - annullato - 85</li>
                        <li>Personalizzazione in corso - messagePreparation - 22</li>
                        <li>Target ready - targetReady - 15</li>
                        <li>VALORE NON VALIDO - __Invalid_value__ - __Invalid_value__</li>
                        <li>Arbitrato in corso - targetArbitrato - 13</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>target</td>
                  <td>Popolazione target di consegna</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>template (deliveryTemplateSummary)</td>
                  <td>Modello di consegna</td>
                  <td>collegamento </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>miniatura</td>
                  <td>Miniatura di consegna</td>
                  <td>string (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>title</td>
                  <td>Consegna</td>
                  <td>string (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>tracking</td>
                  <td>Parametri di tracciamento</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>trackingLogs</td>
                  <td>Registri di tracciamento</td>
                  <td>raccolta </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>trackingUrl</td>
                  <td>URL tracciati</td>
                  <td>raccolta </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>triggerMessage</td>
                  <td>Parametri del messaggio sulle transazioni</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>tipologia (typologyBase)</td>
                  <td>Tipologia</td>
                  <td>collegamento </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>workflow (workflowBase)</td>
                  <td>Flusso di lavoro di targeting</td>
                  <td>collegamento </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>workflowStatus</td>
                  <td>Stato del flusso di lavoro</td>
                  <td>enumerazione (stringa) (255)</td>
                  <td>
                     <ul>
                        <li>In corso - avviato - avviato</li>
                        <li>Editing - edizione</li>
                        <li>Finito - finito - finito - finito</li>
                        <li>Avviso - avviso</li>
                        <li>Errore - Errore - Errore</li>
                        <li>VALORE NON VALIDO - __Invalid_value__ - __Invalid_value__</li>
                     </ul>
                  </td>
               </tr>
            </table>

## Filtri

Per tipo di canale (byChannel)

<table>
    <tr>
    <th>Nome</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>canale</td>
    <td>enumerazione</td>
    </tr>
</table>

Per tipo di esecuzione (byExecutionType)

<table>
    <tr>
    <th>Nome</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>executeType</td>
    <td>enumerazione</td>
    </tr>
</table>

Per stato logico (byLogicalStatus)

<table>
    <tr>
    <th>Nome</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>stato</td>
    <td>enumerazione</td>
    </tr>
</table>

Per nome o etichetta (byText)

<table>
    <tr>
    <th>Nome</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>text</td>
    <td>string</td>
    </tr>
    <tr>
    <td>mc</td>
    <td>string</td>
    </tr>
</table>

Per periodo (perPeriodo)

<table>
    <tr>
    <th>Nome</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>timePeriod</td>
    <td>string</td>
    </tr>
</table>

Per periodo (byStartPeriod)

<table>
    <tr>
    <th>Nome</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>startDate</td>
    <td>date</td>
    </tr>
    <tr>
    <td>timePeriod</td>
    <td>string</td>
    </tr>
</table>

Per stato di pubblicazione (byPublicationStatus)

<table>
    <tr>
    <th>Nome</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>pStatus</td>
    <td>enumerazione</td>
    </tr>
</table>

Per stato (perStato)

<table>
    <tr>
    <th>Nome</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>stato</td>
    <td>enumerazione</td>
    </tr>
</table>

Messaggi di follow-up (showFollowup)

<table>
    <tr>
    <th>Nome</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>seguito</td>
    <td>booleano</td>
    </tr>
</table>

Includere consegne avanzate (con Advanced)

<table>
    <tr>
    <th>Nome</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>avanzato</td>
    <td>booleano</td>
    </tr>
</table>

Includi consegne continue da un elenco eterogeneo (con Continuous)

<table>
    <tr>
    <th>Nome</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>withContinuous</td>
    <td>booleano</td>
    </tr>
</table>

Includi bozze (con FCP)

<table>
    <tr>
    <th>Nome</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>con FCP</td>
    <td>booleano</td>
    </tr>
</table>

Pianificato durante il periodo specificato (daPlanning)

<table>
    <tr>
    <th>Nome</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>startDate</td>
    <td>date</td>
    </tr>
    <tr>
    <td>endDate</td>
    <td>date</td>
    </tr>
</table>

Presente durante un determinato periodo (byCalendar)

<table>
    <tr>
    <th>Nome</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>startDate</td>
    <td>date</td>
    </tr>
    <tr>
    <td>endDate</td>
    <td>date</td>
    </tr>
</table>

Mostra preconfigurato (showOob)

<table>
    <tr>
    <th>Nome</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>forca</td>
    <td>booleano</td>
    </tr>
</table>