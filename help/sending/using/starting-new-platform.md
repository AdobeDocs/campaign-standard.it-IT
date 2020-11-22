---
solution: Campaign Standard
product: campaign
title: Avvio di una nuova piattaforma con  Adobe Campaign Standard
description: Scopri come impostare una nuova piattaforma mantenendo la reputazione del dominio e dell'indirizzo IP con  Adobe Campaign Standard.
audience: sending
content-type: reference
topic-tags: sheduling-messages
context-tags: delivery,schedule,back
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '444'
ht-degree: 2%

---


# Avvio di una nuova piattaforma{#starting-new-platform}

Mantenere la reputazione del dominio e dell&#39;indirizzo IP è fondamentale. Di seguito sono riportati alcuni consigli per la creazione di una nuova piattaforma.

L&#39;invio di e-mail su una nuova piattaforma è un passaggio sensibile in quanto la piattaforma non dispone di alcuna cronologia di utilizzo e non ha alcuna reputazione (quando gli IP di invio non sono mai stati utilizzati a questo scopo). Gli ISP sono naturalmente sospettosi degli indirizzi IP che non sono mai stati utilizzati per inviare email e che improvvisamente iniziano a inviare grandi volumi di traffico email. In effetti, gli spammer generalmente utilizzano indirizzi IP &quot;sconosciuti&quot; (indirizzi mai aggiunti al elenco Bloccati) per inviare il maggior numero possibile di messaggi prima del rilevamento.

Non ci si può aspettare di raggiungere la velocità operativa in termini di output all&#39;inizio della fase di produzione. Inoltre, non si dovrebbe tentare di inviare messaggi a questo tasso, in quanto potrebbe indurre gli ISP a bloccare gli indirizzi di invio e a compromettere gravemente il resto della fase di avvio.

L&#39;avvio di una piattaforma spesso avviene quando si utilizza per la prima volta un elenco di indirizzi che potrebbero non essere completi. Se invii a indirizzi non validi o a indirizzi in honeypot, ciò contribuirà a ridurre la reputazione della piattaforma.
* Se si dispone di un elenco di indirizzi non validi, è nell&#39;interesse dell&#39;utente importarlo nella tabella di quarantena (**[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Quarantines]** > **[!UICONTROL Addresses]**) prima di inviarlo per la prima volta. Per ulteriori informazioni, consulta questa [sezione](../../sending/using/understanding-quarantine-management.md#identifying-quarantined-addresses-for-the-entire-platform).
* Se, comunque, si desidera riqualificare gli indirizzi non validi, è di gran lunga preferibile farlo una volta che la reputazione della piattaforma è stabilita e un po&#39; alla volta, al fine di &quot;diluire&quot; l&#39;uso di indirizzi cattivi nel tempo.

Per riassumere i principi da seguire all&#39;avvio:
* **Configura un sottodominio** dedicato per lavorare con Campaign specifico per le campagne e-mail inviate dal  Adobe.
* **Importa indirizzi non validi/inattivi nella tabella** di quarantena (se disponi di tali informazioni).
* **Limita la velocità di consegna** (impostazione tecnica: limitare il numero di schede).
* **Aumentare progressivamente i volumi inviati**: non eseguite il targeting dell&#39;intero database fin dall&#39;inizio, ma aggiungete una frazione extra dell&#39;elenco ogni volta che inviate. Questo dovrebbe consentire di aumentare il volume in ogni fase, riducendo al contempo il tasso complessivo di indirizzi non validi.
* **Invia messaggi regolarmente**: in una certa misura è meglio inviare regolarmente piccole riprese piuttosto che campagne di grandi dimensioni sporadicamente.
* **Controlla attentamente i rapporti** di consegna: indicatori di errore elevati possono indicare che un&#39;impostazione tecnica non è configurata correttamente.
