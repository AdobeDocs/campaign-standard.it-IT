---
title: Configurare l’app di integrazione Campaign-Dynamics
description: Scopri come configurare l’app di integrazione Campaign-Dynamics
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
feature: Microsoft CRM Integration
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 184bc656-2107-4380-9b35-148cb4380547
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '629'
ht-degree: 2%

---

# Collegare i sistemi con l’applicazione di integrazione

## Aggiungere credenziali all’app di integrazione

La schermata **[!UICONTROL Settings]** consente di specificare le credenziali API di Microsoft Dynamics 365 e Adobe. Puoi anche configurare le impostazioni relative all’istanza SFTP di Adobe Campaign.

### Credenziali Microsoft Dynamics 365

Le credenziali di Microsoft Dynamics 365 consentono all&#39;applicazione di integrazione di estrarre i dati da Microsoft Dynamics 365.  Devi prima seguire i passaggi della schermata [Configurare Microsoft Dynamics 365 per l&#39;integrazione di Campaign](../../integrating/using/d365-acs-configure-d365.md) per generare i valori che verranno incollati in questa schermata. Gli input descritti di seguito faranno riferimento a questa schermata.

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-settings-d365.png)

* **[!UICONTROL Client ID]**: scopri come fare riferimento all&#39;ID client in [questa sezione](../../integrating/using/d365-acs-configure-d365.md#register-a-new-app)

* **[!UICONTROL Client Secret]**: scopri come generare il segreto client in [questa sezione](../../integrating/using/d365-acs-configure-d365.md#generate-a-client-secret)

* **[!UICONTROL Tenant]**: scopri come trovare il tuo ID tenant in [questa sezione](../../integrating/using/d365-acs-configure-d365.md#get-the-tenant-id)

* **[!UICONTROL URL]**: l&#39;URL avrà il formato `https://&lt;servername&gt;.api.crm.dynamics.com/`

### Credenziali API di Adobe

Le credenziali di Adobe Campaign vengono generate utilizzando [Adobe I/O](https://www.adobe.io/). Prima di compilare gli input in questa sezione, è necessario visitare la schermata [Configura Adobe I/O](../../integrating/using/d365-acs-configure-adobe-io.md) e seguire le istruzioni visualizzate.

* Seleziona Tipo di autenticazione come OAuth poiché l’autenticazione basata su JWT è obsoleta.
* L’immagine seguente illustra in dettaglio la mappatura tra Adobe I/O e gli input della schermata delle impostazioni.

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-settings-adobeio.png)

* *URL*: questo valore si adatta al pattern https\://mc.adobe.io/&lt;campaign-instance-name>. L’intestazione dell’app di integrazione include sia &quot;Org&quot; che &quot;Instance&quot;. La porzione &quot;campaign-instance-name&quot; dell’URL sarebbe semplicemente il nome trovato in questo valore di istanza.

## Impostazioni SFTP di Adobe Campaign {#ac-smtp-settings}

Queste impostazioni sono facoltative. Devi definirli se intendi utilizzare l’istanza SFTP di Adobe Campaign per generare i registri dal connettore. Questa funzione è utile in caso di problemi durante l’esecuzione dell’integrazione e se devi eseguire il debug del motivo per cui l’output non soddisfa le aspettative.

L&#39;altro motivo per configurare il server SFTP è se prevedi di eseguire il flusso di lavoro di consenso/rinuncia ed è presente un flusso di dati da Adobe Campaign a Microsoft Dynamics 365, **[!UICONTROL Unidirectional (Campaign to Microsoft Dynamics 365)]** o **[!UICONTROL Bidirectional]**.

>[!IMPORTANT]
>
>Sei responsabile delle informazioni a cui accedi e che scarichi dalle cartelle SFTP. Se le informazioni contengono dati personali, sei responsabile del rispetto di tutte le leggi e le normative sulla privacy applicabili. [Ulteriori informazioni](../../integrating/using/d365-acs-notices-and-recommendations.md#acs-msdyn-manage-privacy).
>

Per definire le impostazioni SFTP di Campaign per l’integrazione con Microsoft Dynamics 365, accedi alla sezione seguente:

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-settings-sftp.png)

È necessario specificare:

* **Host SFTP**: questo campo conterrà &lt;campaign-instance-name>.campaign.adobe.com. L&#39;intestazione dell&#39;applicazione di integrazione include sia **Org** che **Instance**. La porzione &quot;campaign-instance-name&quot; dell’URL sarebbe semplicemente il nome trovato in questo valore di istanza.

* **Utente SFTP**: se disponi dell&#39;utente SFTP, aggiungilo qui. Fare riferimento a [questa sezione](#ac-control-panel-settings). Come parte del processo, ti verrà mostrato il nome utente.

* **Chiave SFTP**: se disponi di una chiave SSH, aggiungila qui. Fare riferimento a [questa sezione](#ac-control-panel-settings).

* Gli **intervalli IP** dovranno essere inclusi nella configurazione SFTP Adobe Campaign. Questi dovranno essere inseriti nell&#39;elenco Consentiti affinché l’integrazione possa utilizzare l’endpoint SFTP.

* **Esportare i registri nel tuo SFTP Adobe Campaign?** consente di determinare se l&#39;integrazione invierà le informazioni di registrazione all&#39;endpoint SFTP. Può essere utilizzato per facilitare il debug se Adobe Campaign o Microsoft Dynamics 365 non visualizza le informazioni previste.

## Configurazione SFTP in Adobe Campaign {#ac-control-panel-settings}

Scopri la gestione SFTP con [Pannello di controllo Campaign di campagne](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=it) nelle seguenti sezioni:

* [Informazioni sulla gestione SFTP](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/about-sftp-management.html?lang=it#sftp-management)

* [Gestione dell’archiviazione SFTP](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/key-management.html?lang=it#installing-ssh-key)

* [Aggiungi intervalli IP](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/ip-range-allow-listing.html?lang=it#sftp-management)

* [Gestione chiavi](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/key-management.html?lang=it#sftp-management)

* [Accedi al server SFTP](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/logging-into-sftp-server.html?lang=it#sftp-management)

Al termine della configurazione, accedi al server SFTP con la chiave privata e crea la directory &quot;d365_loads/exports&quot;.

[Visita questa pagina](https://experienceleague.adobe.com/docs/campaign-standard-learn/control-panel/sftp-management/monitoring-server-capacity.html?lang=it#sftp-management) per informazioni sul server SFTP Adobe Campaign Standard.
