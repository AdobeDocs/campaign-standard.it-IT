---
title: DataModel
description: Scopri il modello dati
uuid: 99277e46-e4f7-49a9-ba27-b878780f90da
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
discoiquuid: 6e21db35-daf9-4edb-977a-6ef606db0e4d
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '687'
ht-degree: 6%

---


# Consegna (nms:consegna)

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
                  <td>boolean </td>
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
                  <td>Distribuzione avanzata</td>
                  <td>boolean </td>
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
                  <td>Contenuti Adobe Experience Manager</td>
                  <td>collection </td>
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
                  <td>accessorio</td>
                  <td>File allegati</td>
                  <td>collection </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>branding (brandingBase)</td>
                  <td>Marchio</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>wideLogs</td>
                  <td>Log di consegna</td>
                  <td>collection </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>buildIn</td>
                  <td>Oggetto applicazione predefinito</td>
                  <td>boolean </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>campaign (campaignBase)</td>
                  <td>Campagna</td>
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
                  <td>command</td>
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
                        <li> Adobe Campaign - campagna - 0</li>
                        <li>VALORE INVALID - __Invalid_value__ - __Invalid_value___</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>contextResourceType</td>
                  <td>Tipo risorsa</td>
                  <td>string </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>created</td>
                  <td>Creato</td>
                  <td>date </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>createBy (userBase)</td>
                  <td>Creato da</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>deliveryMode</td>
                  <td>Modalità consegna</td>
                  <td>enumerazione (byte) </td>
                  <td>
                     <ul>
                        <li>Consegna alla rinfusa - 1</li>
                        <li>Media-sourcing - midSourcing - 4</li>
                        <li>Descrizione - descrittivo - 2</li>
                        <li>VALORE INVALID - __Invalid_value__ - __Invalid_value___</li>
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
                  <td>collection </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>esclusioni</td>
                  <td>Cause di esclusione</td>
                  <td>collection </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>esecuzione</td>
                  <td>Parametri di esecuzione del recapito</td>
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
                        <li>VALORE INVALID - __Invalid_value__ - __Invalid_value___</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>ForecLogs</td>
                  <td>ForecastLog</td>
                  <td>collection </td>
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
                  <td>Aggiungere i file allegati</td>
                  <td>boolean </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>icon</td>
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
                        <li>Altri - altri - 120</li>
                        <li>SMS ricorrenti - smsRefresh - 31</li>
                        <li>Applicazione mobile - pushNotification - 40</li>
                        <li>SMS transazionali - smsLightning - 61</li>
                        <li>Email - email - 0</li>
                        <li>VALORE INVALID - __Invalid_value__ - __Invalid_value___</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>isExternal</td>
                  <td>È una risorsa esterna</td>
                  <td>boolean </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>isMaster</td>
                  <td>Master</td>
                  <td>boolean </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>isTemplate</td>
                  <td>Modello</td>
                  <td>boolean </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>iterazioni</td>
                  <td>Consegne</td>
                  <td>collection </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>job</td>
                  <td>Job</td>
                  <td>collection </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>jobLogs</td>
                  <td>Registri</td>
                  <td>collection </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>kpis</td>
                  <td>Indicatori</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>label</td>
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
                  <td>Stato esecuzione</td>
                  <td>enumerazione (stringa) (255)</td>
                  <td>
                     <ul>
                        <li>In corso - avviato - avviato</li>
                        <li>Editing - edizione</li>
                        <li>Finito - finito - finito</li>
                        <li>Avvertenza - Avviso</li>
                        <li>Erroneo - errore - errore</li>
                        <li>VALORE INVALID - __Invalid_value__ - __Invalid_value___</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>mailParameters</td>
                  <td>Parametri intestazione e-mail</td>
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
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>master (deliveryBase)</td>
                  <td>Istanza principale</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>masterKpis</td>
                  <td>Indicatori principali</td>
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
                        <li>Email - email - 0</li>
                        <li>Telefono - 2</li>
                        <li>Posta diretta - carta - 3</li>
                        <li>Applicazione mobile - pushNotification - 40</li>
                        <li>Altri - altri - 120</li>
                        <li>VALORE INVALID - __Invalid_value__ - __Invalid_value___</li>
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
                  <td>string (64)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>offerManagement</td>
                  <td>Gestione offerte</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>orgUnit (orgUnitBase)</td>
                  <td>Unità organizzativa</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>parent (deliveryBase)</td>
                  <td>Consegna principale</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>priority</td>
                  <td>Priorità di consegna</td>
                  <td>enumerazione (byte) </td>
                  <td>
                     <ul>
                        <li>Alta - alta - 20</li>
                        <li>VALORE INVALID - __Invalid_value__ - __Invalid_value___</li>
                        <li>Normale - normale - 10</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>program (programBase)</td>
                  <td>programma</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>prove</td>
                  <td>Proofs</td>
                  <td>collection </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>pushNotificationPreview</td>
                  <td>Anteprima delle notifiche push</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>pushNotificationParameters</td>
                  <td>Parametri PushNotification</td>
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
                  <td>Messaggio barra multifunzione</td>
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
                  <td>Pianificazione consegna</td>
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
                  <td>state</td>
                  <td>Stato</td>
                  <td>enumerazione (byte) </td>
                  <td>
                     <ul>
                        <li>Avvia in sospeso - startPending - 51</li>
                        <li>Pronto per essere consegnato - pronto - 45</li>
                        <li>Riprova in sospeso - RiprovaIn sospeso - 61</li>
                        <li>Riprova in corso - tryInProgress - 62</li>
                        <li>Non riuscito - non riuscito - 87</li>
                        <li>In corso - avviato - 55</li>
                        <li>Targeting pending - targetPrepPending - 11</li>
                        <li>Personalizzazione in sospeso - messagePrepPending - 21</li>
                        <li>In pausa - in pausa - 75</li>
                        <li>Editing - edizione - 0</li>
                        <li>Finito - finito - 95</li>
                        <li>Conteggio in corso - targetSelection - 12</li>
                        <li>Messaggio completato - messageReady - 25</li>
                        <li>Personalizzazione o conteggio non riuscito - PreparazioneErrore - 37</li>
                        <li>Interrotto - annullato - 85</li>
                        <li>Personalizzazione in corso - messagePreparazione - 22</li>
                        <li>Target ready - targetReady - 15</li>
                        <li>VALORE INVALID - __Invalid_value__ - __Invalid_value___</li>
                        <li>Arbitrato in corso - targetArbitration - 13</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>target</td>
                  <td>Popolazione bersaglio di consegna</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>template (deliveryTemplateSummary)</td>
                  <td>Modello di consegna</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>thumbnail</td>
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
                  <td>Tracciamento dei registri</td>
                  <td>collection </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>trackingUrls</td>
                  <td>URL tracciati</td>
                  <td>collection </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>triggerMessage</td>
                  <td>Parametri del messaggio di transazione</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>typology (typologyBase)</td>
                  <td>Tipologia</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>workflow (workflowBase)</td>
                  <td>Flusso di lavoro di targeting</td>
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
                        <li>Editing - edizione</li>
                        <li>Finito - finito - finito</li>
                        <li>Avvertenza - Avviso</li>
                        <li>Erroneo - errore - errore</li>
                        <li>VALORE INVALID - __Invalid_value__ - __Invalid_value___</li>
                     </ul>
                  </td>
               </tr>
            </table>

## Filtri

Per tipo di canale (per canale)

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
    <td>state</td>
    <td>enumerazione</td>
    </tr>
</table>

Per nome o etichetta (per testo)

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

Per periodo (per periodo)

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

Per stato (per stato)

<table>
    <tr>
    <th>Nome</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>state</td>
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
    <td>boolean</td>
    </tr>
</table>

Includi consegne avanzate (con Advanced)

<table>
    <tr>
    <th>Nome</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>avanzato</td>
    <td>boolean</td>
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
    <td>boolean</td>
    </tr>
</table>

Includi prove (con FCP)

<table>
    <tr>
    <th>Nome</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>con FCP</td>
    <td>boolean</td>
    </tr>
</table>

Pianificato durante il periodo specificato (tramite pianificazione)

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

Presente durante il periodo specificato (per calendario)

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

Mostra out-of-the-box (showOob)

<table>
    <tr>
    <th>Nome</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>fesso</td>
    <td>boolean</td>
    </tr>
</table>