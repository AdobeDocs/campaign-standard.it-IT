---
title: Configurare l’app di integrazione Campaign-Dynamics
description: Scopri come configurare l’app di integrazione Campaign-Dynamics
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
feature: Microsoft CRM Integration
role: Data Architect
level: Intermediate
exl-id: 184bc656-2107-4380-9b35-148cb4380547
source-git-commit: c701043cbba22711de1ea7ddc5266e193d771e14
workflow-type: tm+mt
source-wordcount: '670'
ht-degree: 5%

---

# Collegare i sistemi con l’applicazione di integrazione

## Aggiungere credenziali all’app di integrazione

Il **[!UICONTROL Settings]** consente di specificare le credenziali API di Microsoft Dynamics 365 e Adobe. Puoi anche configurare le impostazioni relative all’istanza SFTP di Adobe Campaign.

### Credenziali di Microsoft Dynamics 365

Le credenziali di Microsoft Dynamics 365 consentono all’applicazione di integrazione di estrarre i dati da Microsoft Dynamics 365.  Devi prima seguire i passaggi sullo schermo [Configurare Microsoft Dynamics 365 per l’integrazione con Campaign](../../integrating/using/d365-acs-configure-d365.md) per generare i valori che verranno incollati in questa schermata. Gli input descritti di seguito faranno riferimento a questa schermata.

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-settings-d365.png)

* **[!UICONTROL Client ID]**: scopri come fare riferimento all’ID client in [questa sezione](../../integrating/using/d365-acs-configure-d365.md#register-a-new-app)

* **[!UICONTROL Client Secret]**: scopri come generare il segreto client in [questa sezione](../../integrating/using/d365-acs-configure-d365.md#generate-a-client-secret)

* **[!UICONTROL Tenant]**: scopri come trovare l’ID tenant in [questa sezione](../../integrating/using/d365-acs-configure-d365.md#get-the-tenant-id)

* **[!UICONTROL URL]**: l’URL avrà il formato `https://&lt;servername&gt;.api.crm.dynamics.com/`

### Credenziali API Adobe

Le credenziali di Adobe Campaign vengono generate utilizzando [Adobe I/O](https://www.adobe.io/). Dovrai visitare lo schermo [Configura Adobe I/O](../../integrating/using/d365-acs-configure-adobe-io.md) e seguire le istruzioni qui prima di essere in grado di compilare gli input in questa sezione.

* Seleziona Tipo di autenticazione come OAuth poiché l’autenticazione basata su JWT è obsoleta.
* L&#39;immagine seguente illustra in dettaglio la mappatura tra gli Adobi I/O e gli ingressi della schermata delle impostazioni.

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-settings-adobeio.png)

* *URL*: questo valore si adatta al pattern https\://mc.adobe.io/&lt;campaign-instance-name>. L’intestazione dell’app di integrazione include sia &quot;Org&quot; che &quot;Instance&quot;. La porzione &quot;campaign-instance-name&quot; dell’URL sarebbe semplicemente il nome trovato in questo valore di istanza.

## Impostazioni SFTP di Adobe Campaign {#ac-smtp-settings}

Queste impostazioni sono facoltative. Devi definirli se intendi utilizzare l’istanza SFTP di Adobe Campaign per generare i registri dal connettore. Questa funzione è utile in caso di problemi durante l’esecuzione dell’integrazione e se devi eseguire il debug del motivo per cui l’output non soddisfa le aspettative.

L’altro motivo per configurare il server SFTP è se prevedi di eseguire il flusso di lavoro di consenso/rinuncia ed è presente un flusso di dati da Adobe Campaign a Microsoft Dynamics 365, **[!UICONTROL Unidirectional (Campaign to Microsoft Dynamics 365)]** o **[!UICONTROL Bidirectional]**.

>[!IMPORTANT]
>
>Sei responsabile delle informazioni a cui accedi e che scarichi dalle cartelle SFTP. Se le informazioni contengono dati personali, sei responsabile del rispetto di tutte le leggi e le normative sulla privacy applicabili. [Ulteriori informazioni](../../integrating/using/d365-acs-notices-and-recommendations.md#acs-msdyn-manage-privacy).
>

Per definire le impostazioni SFTP di Campaign per l’integrazione con Microsoft Dynamics 365, accedi alla sezione seguente:

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-settings-sftp.png)

È necessario specificare:

* **Host SFTP**: questo campo conterrà &lt;campaign-instance-name>.campaign.adobe.com. L’intestazione dell’applicazione di integrazione include sia **Organizzazione** e **Istanza**. La porzione &quot;campaign-instance-name&quot; dell’URL sarebbe semplicemente il nome trovato in questo valore di istanza.

* **Utente SFTP**: aggiungilo qui se disponi dell’utente SFTP. Altrimenti, fare riferimento a [questa sezione](#ac-control-panel-settings). Come parte del processo, ti verrà mostrato il nome utente.

* **Chiave SFTP**: se disponi di una chiave SSH, aggiungila qui. Altrimenti, fare riferimento a [questa sezione](#ac-control-panel-settings).

* Il **Intervalli IP** dovrà essere incluso nella configurazione SFTP di Adobe Campaign. Questi dovranno essere inseriti nell&#39;elenco Consentiti affinché l’integrazione possa utilizzare l’endpoint SFTP.

* Il **Esportare i registri nell’SFTP di Adobe Campaign?** consente di determinare se l’integrazione invierà le informazioni di registrazione all’endpoint SFTP. Può essere utilizzato per facilitare il debug se Adobe Campaign o Microsoft Dynamics 365 non visualizza le informazioni previste.

## Configurazione SFTP in Adobe Campaign {#ac-control-panel-settings}

Scopri la gestione SFTP con [Pannello di controllo Campaign della campagna](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=it) in queste sezioni:

* [Informazioni sulla gestione SFTP](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/about-sftp-management.html?lang=it#sftp-management)

* [Gestione dell’archiviazione SFTP](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/key-management.html#installing-ssh-key)

* [Aggiungere intervalli IP](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/ip-range-allow-listing.html#sftp-management)

* [Gestione chiavi](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/key-management.html#sftp-management)

* [Accesso al server SFTP](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/logging-into-sftp-server.html#sftp-management)

Al termine della configurazione, accedi al server SFTP con la chiave privata e crea la directory &quot;d365_loads/exports&quot;.

[Visita questa pagina](https://experienceleague.adobe.com/docs/campaign-standard-learn/control-panel/sftp-management/monitoring-server-capacity.html?lang=it#sftp-management) per informazioni sul server SFTP di Adobe Campaign Standard.
