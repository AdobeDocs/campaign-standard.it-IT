---
solution: Campaign Standard
product: campaign
title: Avvio di una nuova piattaforma con Adobe Campaign Standard
description: Scopri come impostare una nuova piattaforma mantenendo la reputazione del dominio e dell’indirizzo IP con Adobe Campaign Standard.
audience: sending
content-type: reference
topic-tags: sheduling-messages
context-tags: delivery,schedule,back
feature: Consegna
role: Professionista
level: Intermedio
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '448'
ht-degree: 2%

---


# Avvio di una nuova piattaforma{#starting-new-platform}

Mantenere la reputazione del dominio e dell&#39;indirizzo IP è fondamentale. Ecco alcuni consigli per la creazione di una nuova piattaforma.

L’invio di e-mail su una nuova piattaforma è un passaggio delicato perché la piattaforma non dispone di alcuna cronologia di utilizzo e reputazione (quando gli IP di invio non sono mai stati utilizzati a questo scopo). Gli ISP sono naturalmente sospettosi degli indirizzi IP che non sono mai stati utilizzati per inviare e-mail e che improvvisamente iniziano a inviare grandi volumi di traffico e-mail. In effetti, gli spammer generalmente utilizzano indirizzi IP &quot;sconosciuti&quot; (indirizzi che non sono mai stati aggiunti al elenco Bloccati) per inviare il maggior numero possibile di messaggi prima del rilevamento.

Non ci si può aspettare di raggiungere la velocità operativa in termini di output all&#39;inizio della fase di produzione. Inoltre, non devi tentare di inviare messaggi a questo ritmo in quanto potrebbe indurre gli ISP a bloccare gli indirizzi di invio e a compromettere gravemente il resto della fase di avvio.

L’avvio di una piattaforma spesso avviene quando si utilizza per la prima volta un elenco di indirizzi che potrebbero non essere completamente qualificati. Se invii indirizzi non validi o a indirizzi non validi, ciò contribuirà a ridurre la reputazione della piattaforma.
* Se disponi di un elenco di indirizzi non validi, è nel tuo interesse importarlo nella tabella di quarantena (**[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Quarantines]** > **[!UICONTROL Addresses]**) prima di inviarlo per la prima volta. Per ulteriori informazioni, consulta questa [sezione](../../sending/using/understanding-quarantine-management.md#identifying-quarantined-addresses-for-the-entire-platform).
* Se, comunque, si desidera riqualificare gli indirizzi non validi, è di gran lunga preferibile farlo una volta che la reputazione della piattaforma è stabilita e bit per pezzo al fine di &quot;diluire&quot; l&#39;uso di indirizzi non validi nel tempo.

Per riepilogare i principi da seguire all&#39;avvio:
* **Configura un** sottodominio dedicato per lavorare con Campaign specifico per le campagne e-mail inviate da Adobe.
* **Importa indirizzi non validi/inattivi nella tabella**  di quarantena (se disponi di queste informazioni).
* **Limitare la consegna** tramite (impostazione tecnica: limitando il numero di unità).
* **Incremento progressivo dei volumi inviati**: non eseguire il targeting dell&#39;intero database fin dall&#39;inizio, ma aggiungere una frazione extra dell&#39;elenco ogni volta che si invia. Questo dovrebbe consentire di aumentare il volume a ogni passaggio riducendo al contempo il tasso complessivo di indirizzi non validi.
* **Invia messaggi regolarmente**: in un certo senso è meglio inviare regolarmente piccole riprese piuttosto che campagne di grandi dimensioni sporadicamente.
* **Monitora attentamente i rapporti** di consegna: indicatori di errore elevati possono indicare che un’impostazione tecnica non è configurata correttamente.
