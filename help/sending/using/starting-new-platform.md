---
title: Avvio di una nuova piattaforma con Adobe Campaign Standard
description: Scopri come configurare una nuova piattaforma mantenendo la reputazione del dominio e dell'indirizzo IP con Adobe Campaign Standard.
page-status-flag: never-activated
uuid: 286fceee-65a9-4cb9-b205-9ce5d024675c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: sheduling-messages
discoiquuid: 9c7fd670-bba9-4f3c-8cb1-87397a1acd27
context-tags: delivery,schedule,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 89965d859986b9176de6b6bf96df1fbbb89b5b8f

---


# Avvio di una nuova piattaforma{#starting-new-platform}

Mantenere la reputazione del dominio e dell'indirizzo IP è fondamentale. Di seguito sono riportati alcuni consigli per la creazione di una nuova piattaforma.

L'invio di e-mail su una nuova piattaforma è un passaggio sensibile in quanto la piattaforma non dispone di alcuna cronologia di utilizzo e non ha alcuna reputazione (quando gli IP di invio non sono mai stati utilizzati a questo scopo). Gli ISP sono naturalmente sospettosi degli indirizzi IP che non sono mai stati utilizzati per inviare email e che improvvisamente iniziano a inviare grandi volumi di traffico email. In effetti, gli spammer generalmente utilizzano indirizzi IP "sconosciuti" (cioè indirizzi che non sono mai stati inseriti in blacklist) per inviare il maggior numero possibile di messaggi prima del rilevamento.

Non ci si può aspettare di raggiungere la velocità operativa in termini di output all'inizio della fase di produzione. Inoltre, non si dovrebbe tentare di inviare messaggi a questo tasso, in quanto potrebbe indurre gli ISP a bloccare gli indirizzi di invio e a compromettere gravemente il resto della fase di avvio.

L'avvio di una piattaforma spesso avviene quando si utilizza per la prima volta un elenco di indirizzi che potrebbero non essere completi. Se invii a indirizzi non validi o a indirizzi in honeypot, ciò contribuirà a ridurre la reputazione della piattaforma. Se si dispone di un elenco di indirizzi non validi, è nell'interesse dell'utente importarlo nella tabella di quarantena (**[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Quarantines]** &gt; **[!UICONTROL Addresses]**) prima di inviarlo per la prima volta. Se, comunque, si desidera riqualificare gli indirizzi non validi, è di gran lunga preferibile farlo una volta che la reputazione della piattaforma è stabilita e un po' alla volta, al fine di "diluire" l'uso di indirizzi cattivi nel tempo.

Per riassumere i principi da seguire all'avvio:
* **Delega di un sottodominio** dedicato ad Adobe specifico per le campagne e-mail inviate da Adobe
* **Importa indirizzi non validi/inattivi nella tabella** di quarantena (se disponi di tali informazioni)
* **Limita la velocità di consegna** (impostazione tecnica: limitazione del numero di campioni)
* **Aumentare progressivamente i volumi inviati**: non eseguire il targeting dell'intero database fin dall'inizio, ma aggiungere una frazione extra dell'elenco ogni volta che si invia; questo dovrebbe consentire di aumentare il volume in ogni fase, riducendo al contempo il tasso complessivo di indirizzi non validi
* **Invia messaggi regolarmente**: In una certa misura è meglio inviare regolarmente piccole riprese piuttosto che campagne di grandi dimensioni sporadiche
* **Controlla attentamente i rapporti** di consegna: indicatori di errore elevati possono indicare che un'impostazione tecnica non è configurata correttamente.
