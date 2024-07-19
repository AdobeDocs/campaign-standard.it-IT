---
title: Distribuzione DataModel
description: Scopri il modello dati
audience: developing
content-type: reference
feature: Data Model
role: Developer
level: Experienced
exl-id: aea3e72d-8e89-46c7-a796-bf856414c654
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '725'
ht-degree: 27%

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
                  <td>Bozza</td>
                  <td>booleano </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>PKey</td>
                  <td>ID risorsa principale</td>
                  <td>stringa </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>abTesting</td>
                  <td>Test A/B</td>
                  <td>elemento </td>
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
                  <td>elemento </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>aemContents</td>
                  <td>Contenuti Adobe Experience Manager</td>
                  <td>raccolta </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>alertMessage</td>
                  <td>Messaggio di avviso</td>
                  <td>stringa </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>alertMode</td>
                  <td>Tipo di avviso</td>
                  <td>stringa </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>allegato</td>
                  <td>File allegati</td>
                  <td>raccolta </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>branding (brandingBase)</td>
                  <td>Brand</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>broadLogs</td>
                  <td>Registri di consegna</td>
                  <td>raccolta </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>predefinito</td>
                  <td>Oggetto applicazione incorporato</td>
                  <td>booleano </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>campaign (campaignBase)</td>
                  <td>Campaign</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>cmsAccount (extAccountAEMBase)</td>
                  <td>Account Adobe Experience Manager</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>comandi</td>
                  <td>Comandi</td>
                  <td>elemento </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>contenuto</td>
                  <td>Contenuto</td>
                  <td>elemento </td>
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
                        <li>VALORE NON VALIDO - __Valore_non valido__ - __Valore_non valido__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>contextResourceType</td>
                  <td>Tipo di risorsa</td>
                  <td>stringa </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>creato</td>
                  <td>Creato</td>
                  <td>data </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>createdBy (userBase)</td>
                  <td>Creato da</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>deliveryMode</td>
                  <td>Modalità di consegna</td>
                  <td>enumerazione (byte) </td>
                  <td>
                     <ul>
                        <li>Consegna in blocco - in blocco - 1</li>
                        <li>Mid-sourcing - midSourcing - 4</li>
                        <li>Descrizione - descrittiva - 2</li>
                        <li>VALORE NON VALIDO - __Valore_non valido__ - __Valore_non valido__</li>
                        <li>Esterno - esterno - 0</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>deliveryProvider (extAccountBase)</td>
                  <td>Indirizzamento</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>desc</td>
                  <td>Descrizione</td>
                  <td>stringa (512)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>emailPreview</td>
                  <td>Anteprima e-mail</td>
                  <td>elemento </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>excludeLogs</td>
                  <td>Registri di esclusione</td>
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
                  <td>elemento </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>executionType</td>
                  <td>Tipo di esecuzione</td>
                  <td>enumerazione (byte) </td>
                  <td>
                     <ul>
                        <li>Univoco - oneTime - 0</li>
                        <li>Continuo - continuo - 1</li>
                        <li>Centro messaggi - messageCenter - 2</li>
                        <li>VALORE NON VALIDO - __Valore_non valido__ - __Valore_non valido__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>forecastLogs</td>
                  <td>ForecastLog</td>
                  <td>raccolta </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>geoUnit (geoUnitBase)</td>
                  <td>Unità geografica</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>hasAttachments</td>
                  <td>Aggiungi allegati</td>
                  <td>booleano </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>icona</td>
                  <td>Icona</td>
                  <td>enumerazione (byte) </td>
                  <td>
                     <ul>
                        <li>E-mail transazionale - e-mailLightning - 60</li>
                        <li>Fax - Fax - 4</li>
                        <li>Mobile (SMS) - sms - 1</li>
                        <li>E-mail ricorrente - emailRefresh - 30</li>
                        <li>Direct mail - carta - 3</li>
                        <li>Telefono - telefono - 2</li>
                        <li>Altro - altri - 120</li>
                        <li>SMS ricorrenti - smsRefresh - 31</li>
                        <li>Applicazione mobile - pushNotification - 40</li>
                        <li>SMS transazionali - smsLightning - 61</li>
                        <li>E-mail - e-mail - 0</li>
                        <li>VALORE NON VALIDO - __Valore_non valido__ - __Valore_non valido__</li>
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
                  <td>Principale</td>
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
                  <td>processo</td>
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
                  <td>kpi</td>
                  <td>Indicatori</td>
                  <td>elemento </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>etichetta</td>
                  <td>Etichetta</td>
                  <td>stringa (128)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>lastModified</td>
                  <td>Ultima modifica</td>
                  <td>data </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>logicalStatus</td>
                  <td>Stato di esecuzione</td>
                  <td>enumerazione (stringa) (255)</td>
                  <td>
                     <ul>
                        <li>In corso - avviato - avviato</li>
                        <li>Editing - edition - edition</li>
                        <li>Finito - finito - finito</li>
                        <li>Avviso - avviso - avviso</li>
                        <li>Errato - Errore - Errore</li>
                        <li>VALORE NON VALIDO - __Valore_non valido__ - __Valore_non valido__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>mailParameters</td>
                  <td>Parametri di intestazione e-mail</td>
                  <td>elemento </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>mainDate</td>
                  <td>Data</td>
                  <td>data </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>mappatura (deliveryMapping)</td>
                  <td>Mappatura del target</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>principale (deliveryBase)</td>
                  <td>Istanza principale</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>masterKpi</td>
                  <td>Indicatori principali</td>
                  <td>elemento </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>messageType</td>
                  <td>Canale</td>
                  <td>enumerazione (byte) </td>
                  <td>
                     <ul>
                        <li>Fax - Fax - 4</li>
                        <li>Mobile (SMS) - sms - 1</li>
                        <li>E-mail - e-mail - 0</li>
                        <li>Telefono - telefono - 2</li>
                        <li>Direct mail - carta - 3</li>
                        <li>Applicazione mobile - pushNotification - 40</li>
                        <li>Altro - altri - 120</li>
                        <li>VALORE NON VALIDO - __Valore_non valido__ - __Valore_non valido__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>modifiedBy (userBase)</td>
                  <td>Modificato da</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>name</td>
                  <td>ID</td>
                  <td>stringa (64)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>offerManagement</td>
                  <td>Gestione delle offerte</td>
                  <td>elemento </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>orgUnit (orgUnitBase)</td>
                  <td>Unità organizzativa</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>principale (deliveryBase)</td>
                  <td>Consegna principale</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>priorità</td>
                  <td>Priorità della consegna</td>
                  <td>enumerazione (byte) </td>
                  <td>
                     <ul>
                        <li>Alto - alto - 20</li>
                        <li>VALORE NON VALIDO - __Valore_non valido__ - __Valore_non valido__</li>
                        <li>Normale - normale - 10</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>program (programBase)</td>
                  <td>Programma</td>
                  <td>link </td>
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
                  <td>Anteprima notifica push</td>
                  <td>elemento </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>pushnotificationParameters</td>
                  <td>Parametri PushNotification</td>
                  <td>elemento </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>realtimeReport</td>
                  <td>Rapporti in tempo reale</td>
                  <td>elemento </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>resourceVersion</td>
                  <td>Versione risorsa</td>
                  <td>stringa (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>ribbonMessage</td>
                  <td>Messaggio barra multifunzione</td>
                  <td>stringa </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>scenario</td>
                  <td>Parametri del modello di consegna</td>
                  <td>elemento </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>pianificazione</td>
                  <td>Pianificazione della consegna</td>
                  <td>elemento </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>smsParameters</td>
                  <td>Parametri SMS</td>
                  <td>elemento </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>smsPreview</td>
                  <td>Anteprima SMS</td>
                  <td>elemento </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>stato</td>
                  <td>Stato</td>
                  <td>enumerazione (byte) </td>
                  <td>
                     <ul>
                        <li>Avvio in sospeso - startPending - 51</li>
                        <li>Pronto per la consegna - pronto - 45</li>
                        <li>Nuovo tentativo in sospeso - retryPending - 61</li>
                        <li>Nuovo tentativo in corso - retryInProgress - 62</li>
                        <li>Non riuscito - non riuscito - 87</li>
                        <li>In corso - avviato - 55</li>
                        <li>Targeting in sospeso - targetPrepPending - 11</li>
                        <li>Personalization in sospeso - messagePrepPending - 21</li>
                        <li>In pausa - in pausa - 75</li>
                        <li>Modifica - edizione - 0</li>
                        <li>Finito - finito - 95</li>
                        <li>Conteggio in corso - targetSelection - 12</li>
                        <li>Messaggio finalizzato - messageReady - 25</li>
                        <li>Personalization o conteggio non riuscito - preparationError - 37</li>
                        <li>Interrotto - annullato - 85</li>
                        <li>Personalization in corso - messagePreparation - 22</li>
                        <li>Target ready - targetReady - 15</li>
                        <li>VALORE NON VALIDO - __Valore_non valido__ - __Valore_non valido__</li>
                        <li>Arbitrato in corso - targetArbitrato - 13</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>target</td>
                  <td>Popolazione target della consegna</td>
                  <td>elemento </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>template (deliveryTemplateSummary)</td>
                  <td>Modello di consegna</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>miniatura</td>
                  <td>Miniatura della consegna</td>
                  <td>stringa (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>titolo</td>
                  <td>Consegna</td>
                  <td>stringa (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>tracciamento</td>
                  <td>Parametri di tracciamento</td>
                  <td>elemento </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>trackingLogs</td>
                  <td>Registri di tracciamento</td>
                  <td>raccolta </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>trackingUrls</td>
                  <td>URL tracciati</td>
                  <td>raccolta </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>triggerMessage</td>
                  <td>Parametri del messaggio transazionale</td>
                  <td>elemento </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>tipologia (typologyBase)</td>
                  <td>Tipologia</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>workflow (workflowBase)</td>
                  <td>Flusso di lavoro di destinazione</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>workflowStatus</td>
                  <td>Stato del flusso di lavoro</td>
                  <td>enumerazione (stringa) (255)</td>
                  <td>
                     <ul>
                        <li>In corso - avviato - avviato</li>
                        <li>Editing - edition - edition</li>
                        <li>Finito - finito - finito</li>
                        <li>Avviso - avviso - avviso</li>
                        <li>Errato - Errore - Errore</li>
                        <li>VALORE NON VALIDO - __Valore_non valido__ - __Valore_non valido__</li>
                     </ul>
                  </td>
               </tr>
            </table>

## Filtri

Per tipo di canale (perCanale)

<table>
    <tr>
    <th>Nome</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>channel</td>
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
    <td>executionType</td>
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
    <td>stringa</td>
    </tr>
    <tr>
    <td>mc</td>
    <td>stringa</td>
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
    <td>stringa</td>
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
    <td>data</td>
    </tr>
    <tr>
    <td>timePeriod</td>
    <td>stringa</td>
    </tr>
</table>

Per stato pubblicazione (byPublicationStatus)

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

Per stato (byState)

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

Includi consegne avanzate (conAvanzate)

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

Includi consegne continue da un elenco eterogeneo (conContinuo)

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
    <td>conFCP</td>
    <td>booleano</td>
    </tr>
</table>

Pianificato durante il periodo specificato (per Pianificazione)

<table>
    <tr>
    <th>Nome</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>startDate</td>
    <td>data</td>
    </tr>
    <tr>
    <td>endDate</td>
    <td>data</td>
    </tr>
</table>

Presente durante il periodo specificato (per calendario)

<table>
    <tr>
    <th>Nome</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>startDate</td>
    <td>data</td>
    </tr>
    <tr>
    <td>endDate</td>
    <td>data</td>
    </tr>
</table>

Mostra preconfigurato (showOob)

<table>
    <tr>
    <th>Nome</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>oob</td>
    <td>booleano</td>
    </tr>
</table>
