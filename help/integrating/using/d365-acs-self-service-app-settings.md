---
title: Configurare l’app di integrazione Campaign-Dynamics
description: Scopri come configurare l’app di integrazione Campaign-Dynamics
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
feature: Integrazione con Microsoft CRM
role: Architetto dati
level: Intermedio
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '801'
ht-degree: 2%

---


# Collegare i sistemi con l’applicazione di integrazione

## Aggiungere credenziali all’app di integrazione

La schermata **[!UICONTROL Settings]** ti consente di specificare le credenziali API di Microsoft Dynamics 365 e Adobe. Puoi anche configurare le impostazioni relative all’istanza SFTP di Adobe Campaign.

### Credenziali di Microsoft Dynamics 365

Le credenziali di Microsoft Dynamics 365 consentono all’applicazione di integrazione di estrarre i dati da Microsoft Dynamics 365.  Per generare i valori che verranno incollati in questa schermata, è innanzitutto necessario seguire i passaggi descritti nella schermata [Configura Microsoft Dynamics 365 per l’integrazione di Campaign](../../integrating/using/d365-acs-configure-d365.md) . Gli input descritti di seguito fanno riferimento a questa schermata.

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-settings-d365.png)

* **[!UICONTROL Client ID]**: Scopri come fare riferimento al tuo ID client in  [questa sezione](../../integrating/using/d365-acs-configure-d365.md#register-a-new-app)

* **[!UICONTROL Client Secret]**: Scopri come generare il segreto client in  [questa sezione](../../integrating/using/d365-acs-configure-d365.md#generate-a-client-secret)

* **[!UICONTROL Tenant]**: Scopri come trovare il tuo ID tenant in  [questa sezione](../../integrating/using/d365-acs-configure-d365.md#get-the-tenant-id)

* **[!UICONTROL URL]**: L’URL avrà il formato &quot;https://&lt;servername>.api.crm.dynamics.com/

### Adobe di credenziali API

Le credenziali Adobe Campaign vengono generate utilizzando [Adobe I/O](https://www.adobe.io/). È necessario visitare la schermata [Configura Adobe I/O](../../integrating/using/d365-acs-configure-adobe-io.md) e seguire le istruzioni in essa contenute prima di poter compilare gli input in questa sezione.

L&#39;immagine seguente illustra in dettaglio la mappatura tra gli input dello schermo di Adobe I/O e delle impostazioni.

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-settings-adobeio.png)

* *Chiave* privata: il processo da definire inizia facendo clic sul pulsante &quot;Genera coppia di chiavi pubblica/privata&quot;. Questo creerà un file zip da scaricare. Una volta scaricata, decomprimi il file che si tradurrà in due file denominati certificate_pub.crt e private.key. Assicurati di mettere private.key in un luogo sicuro e non condividerlo. Apri il file private.key in un editor di testo. Copiare l&#39;intero valore nell&#39;editor di testo (Ctrl-A e Ctrl-C su un PC, o Comando-A e Comando-C su Mac). Ciò dovrebbe includere le linee con &quot;INIZIA CHIAVE PRIVATA&quot; e &quot;FINE CHIAVE PRIVATA&quot; nella loro interezza. Incolla l’intero testo su più righe nell’input &quot;Chiave privata&quot; nella schermata Impostazioni.

* *URL*: Questo valore si adatta al pattern https\://mc.adobe.io/&lt;campaign-instance-name>. L’intestazione dell’app di integrazione include sia &quot;Org&quot; che &quot;Instance&quot; (Istanza). La porzione &quot;campaign-instance-name&quot; dell&#39;url è semplicemente il nome trovato in questo valore di istanza.

## Impostazioni Adobe Campaign SFTP {#ac-smtp-settings}

Queste impostazioni sono facoltative. Devi definirli se prevedi di utilizzare la tua istanza SFTP di Adobe Campaign per generare i registri dal connettore. Questo è utile se si verificano problemi durante l&#39;esecuzione dell&#39;integrazione e devi eseguire il debug del motivo per cui l&#39;output non soddisfa le tue aspettative.

L’altro motivo per configurare il server SFTP è che si prevede di eseguire il flusso di lavoro di consenso/rinuncia e che vi sia un flusso di dati da Adobe Campaign a Microsoft Dynamics 365, sia **[!UICONTROL Unidirectional (Campaign to Microsoft Dynamics 365)]** che **[!UICONTROL Bidirectional]**.

>[!IMPORTANT]
>
>Sei responsabile delle informazioni che accedi e scarica dalle cartelle SFTP. Se le informazioni contengono dati personali, l&#39;utente è responsabile del rispetto di tutte le leggi e i regolamenti sulla privacy applicabili. [Ulteriori informazioni](../../integrating/using/d365-acs-notices-and-recommendations.md#acs-msdyn-manage-privacy).


Per definire le impostazioni SFTP di Campaign per l’integrazione con Microsoft Dynamics 365, accedi alla sezione seguente:

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-settings-sftp.png)

È necessario specificare:

* **Host** SFTP: questo campo conterrà  &lt;campaign-instance-name>.campaign.adobe.com. L&#39;intestazione dell&#39;app di integrazione include sia **Org** che **Instance**. La porzione &quot;campaign-instance-name&quot; dell&#39;url è semplicemente il nome trovato in questo valore di istanza.

* **Utente** SFTP: Se disponi dell’utente SFTP, aggiungilo qui. In caso contrario, fare riferimento a [questa sezione](#ac-control-panel-settings). Come parte del processo, ti verrà mostrato il nome utente.

* **Chiave** SFTP: Se disponi di una chiave SSH, aggiungilo qui. In caso contrario, fare riferimento a [questa sezione](#ac-control-panel-settings).

* È necessario includere **intervalli IP** nella configurazione SFTP di Adobe Campaign. Questi dovranno essere inseriti nell&#39;elenco Consentiti affinché l’integrazione possa utilizzare l’endpoint SFTP.

* I **Vuoi esportare i registri nel tuo SFTP Adobe Campaign?** consente di determinare se l’integrazione invierà informazioni di registrazione all’endpoint SFTP. Questa funzione può essere utilizzata per facilitare il debug se Adobe Campaign o Microsoft Dynamics 365 non mostrano le informazioni previste.

## Configurazione SFTP in Adobe Campaign {#ac-control-panel-settings}

Scopri la gestione SFTP con [Pannello di controllo Campaign campagna](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=it) nelle seguenti sezioni:

* [Informazioni sulla gestione SFTP](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/about-sftp-management.html?lang=en#sftp-management)

* [Gestione dell’archiviazione SFTP](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/key-management.html?lang=en#installing-ssh-key)

* [Aggiungi intervalli IP](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/ip-range-allow-listing.html?lang=en#sftp-management)

* [Gestisci chiavi](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/key-management.html?lang=en#sftp-management)

* [Accedi al tuo server SFTP](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/logging-into-sftp-server.html?lang=en#sftp-management)

Al termine della configurazione, accedi al server SFTP con la chiave privata e crea la directory &quot;d365_loads/export&quot;.

[Visita questa ](https://experienceleague.adobe.com/docs/campaign-standard-learn/control-panel/sftp-management/monitoring-server-capacity.html?lang=en#sftp-management) pagina per informazioni sul server SFTP di Adobe Campaign Standard.
