---
title: Configurare l'app di integrazione Campaign-Dynamics
description: Scopri come configurare l'app di integrazione Campaign-Dynamics
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
translation-type: tm+mt
source-git-commit: efa30d7ed4a0caf929da6f485681078318849cda
workflow-type: tm+mt
source-wordcount: '795'
ht-degree: 2%

---


# Collegare i sistemi con l&#39;app di integrazione

## Aggiunta di credenziali all&#39;app di integrazione

La schermata **[!UICONTROL Settings]** consente di specificare le credenziali API di Microsoft Dynamics 365 e  Adobe. Potete anche configurare le impostazioni relative all&#39;istanza  Adobe Campaign SFTP.

### Credenziali di Microsoft Dynamics 365

Le credenziali di Microsoft Dynamics 365 consentono all&#39;applicazione di integrazione di estrarre i dati da Microsoft Dynamics 365.  È innanzitutto necessario seguire i passaggi sullo schermo [Configura Microsoft Dynamics 365 per l&#39;integrazione con Campaign](../../integrating/using/d365-acs-configure-d365.md) per generare i valori che verranno incollati in questa schermata. Gli input descritti di seguito fanno riferimento a questa schermata.

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-settings-d365.png)

* **[!UICONTROL Client ID]**: Scopri come fare riferimento all&#39;ID cliente in  [questa sezione](../../integrating/using/d365-acs-configure-d365.md#register-a-new-app)

* **[!UICONTROL Client Secret]**: Scopri come generare il Segreto cliente in  [questa sezione](../../integrating/using/d365-acs-configure-d365.md#generate-a-client-secret)

* **[!UICONTROL Tenant]**: Scopri come trovare il tuo ID tenant in  [questa sezione](../../integrating/using/d365-acs-configure-d365.md#get-the-tenant-id)

* **[!UICONTROL URL]**: L&#39;URL avrà il formato &quot;https://&lt;servername>.api.crm.dDynamics.com/

###  credenziali API Adobe

Le credenziali Adobe Campaign  vengono generate utilizzando [ Adobe I/O](https://www.adobe.io/). Prima di compilare gli ingressi in questa sezione è necessario visitare la schermata [Configura  Adobe I/O](../../integrating/using/d365-acs-configure-adobe-io.md) e seguire le istruzioni riportate.

L&#39;immagine seguente spiega in dettaglio la mappatura tra  Adobe I/O e gli ingressi dello schermo delle impostazioni.

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-settings-adobeio.png)

* *Chiave* privata: il processo da definire inizia facendo clic sul pulsante &quot;Generate public/private keypair&quot;. Questo creerà un file zip da scaricare. Una volta scaricata, decomprimete il file con due file denominati certificate_pub.crt e private.key. Assicuratevi di mettere private.key in un luogo sicuro e non condividerlo. Aprite il file private.key in un editor di testo. Copiate l’intero valore nell’editor di testo (Ctrl+A, Ctrl+C su PC o Comando+A, quindi Comando+C su Mac). Ciò dovrebbe includere le righe con &quot;BEGIN PRIVATE KEY&quot; e &quot;END PRIVATE KEY&quot; nella loro interezza. Incollate tutto questo testo multiriga nell’input &quot;Chiave privata&quot; nella schermata Impostazioni.

* *URL*: Questo valore si adatta al pattern https\://mc.adobe.io/&lt;campaign-instance-name>. L&#39;intestazione dell&#39;app di integrazione include sia &quot;Org&quot; che &quot;Instance&quot;. La porzione &quot;campaign-instance-name&quot; dell’URL corrisponde semplicemente al nome trovato in questo valore dell’istanza.

##  impostazioni SFTP Adobe Campaign {#ac-smtp-settings}

Queste impostazioni sono facoltative. È necessario definirli se si prevede di utilizzare l&#39;istanza  Adobe Campaign SFTP per trasmettere i registri dal connettore. Questa funzione è utile se si verificano dei problemi durante l’integrazione e dovete eseguire il debug del motivo per cui l’output non soddisfa le vostre aspettative.

L&#39;altro motivo per impostare il server SFTP sarebbe se si prevede di eseguire il flusso di lavoro di consenso/rifiuto e vi è un flusso di dati da  Adobe Campaign a Microsoft Dynamics 365, **[!UICONTROL Unidirectional (Campaign to Microsoft Dynamics 365)]** o **[!UICONTROL Bidirectional]**.

>[!IMPORTANT]
>
>Siete responsabili delle informazioni a cui avete accesso e che scaricate dalle cartelle SFTP. Se le informazioni contengono dati personali, l&#39;Utente è tenuto a rispettare tutte le leggi e le normative vigenti in materia di privacy. [Ulteriori informazioni](../../integrating/using/d365-acs-notices-and-recommendations.md#acs-msdyn-manage-privacy).


Per definire le impostazioni SFTP delle campagne per l&#39;integrazione con Microsoft Dynamics 365, accedere alla sezione seguente:

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-settings-sftp.png)

È necessario specificare:

* **Host** SFTP: questo campo conterrà  &lt;campaign-instance-name>.campaign.adobe.com. L&#39;intestazione dell&#39;app di integrazione include sia **Org** che **Instance**. La porzione &quot;campaign-instance-name&quot; dell’URL corrisponde semplicemente al nome trovato in questo valore dell’istanza.

* **Utente** SFTP: Se disponete dell&#39;utente SFTP, aggiungetelo qui. In caso contrario, fare riferimento a [questa sezione](#ac-control-panel-settings). Come parte del processo, vi verrà mostrato il nome utente.

* **Chiave** SFTP: Se disponete di una chiave SSH, aggiungetela qui. In caso contrario, fare riferimento a [questa sezione](#ac-control-panel-settings).

* È necessario includere **Intervalli IP** nella configurazione Adobe Campaign SFTP . Per consentire l&#39;integrazione di utilizzare l&#39;endpoint SFTP, questi dovranno essere inseriti nell&#39;elenco Consentiti.

* **Esportare i file di registro nel  Adobe Campaign SFTP?** consente di determinare se l&#39;integrazione restituirà le informazioni di registrazione all&#39;endpoint SFTP. Questo può essere utilizzato per facilitare il debug se  Adobe Campaign o Microsoft Dynamics 365 non mostra le informazioni previste.

## Configurazione SFTP in  Adobe Campaign {#ac-control-panel-settings}

Scopri la gestione SFTP con [Pannello di controllo Campaign campagna](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=it) nelle seguenti sezioni:

* [Informazioni sulla gestione SFTP](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/about-sftp-management.html?lang=en#sftp-management)

* [Gestione dell’archiviazione SFTP](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/key-management.html?lang=en#installing-ssh-key)

* [Aggiungi intervalli IP](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/ip-range-allow-listing.html?lang=en#sftp-management)

* [Gestisci chiavi](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/key-management.html?lang=en#sftp-management)

* [Accedere al server SFTP](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/logging-into-sftp-server.html?lang=en#sftp-management)

Al termine della configurazione, accedete al server SFTP con la chiave privata e create la directory &quot;d365_loads/export&quot;.

[Visitate questa ](https://experienceleague.adobe.com/docs/campaign-standard-learn/control-panel/sftp-management/monitoring-server-capacity.html?lang=en#sftp-management) pagina per informazioni sul server Adobe Campaign Standard SFTP .
