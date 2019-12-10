---
title: Consigli tecnici per la distribuzione per Adobe Campaign Standard
description: Leggi alcune raccomandazioni tecniche per migliorare la recapito dei messaggi con Adobe Campaign Standard.
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
source-git-commit: 44049443f8028ed26089ee0d49944ebac6a62111

---


# Raccomandazioni tecniche{#technical-recommendations}

Inoltre, di seguito sono elencate diverse tecniche, configurazioni e strumenti utilizzabili per migliorare il tasso di recapito.

Di seguito sono riportate alcune definizioni dei principali termini tecnici.

**Inverti DNS** Adobe Campaign verifica se viene fornito un DNS inverso per un indirizzo IP e che questo indichi correttamente l'IP.

**Le regole** MX vengono utilizzate per controllare la velocità alla quale Campaign MTA (Message Transfer Agent) invia e-mail a ciascun dominio e-mail o ISP (ad esempio, hotmail.com, comcast.net). Tali regole si basano in genere sui limiti pubblicati dagli ISP (ad esempio, non includono più di 20 messaggi per ogni connessione SMTP).

**TLS** TLS (Transport Layer Security) è un protocollo di cifratura che può essere utilizzato per proteggere la connessione tra due server di posta elettronica e proteggere il contenuto di un'e-mail dalla lettura da parte di altri destinatari.

**SPF** SPF (Sender Policy Framework) è uno standard di autenticazione tramite e-mail che consente al proprietario di un dominio di specificare quali server e-mail possono inviare e-mail per conto di tale dominio. Questo standard utilizza il dominio nell'intestazione "Return-Path" dell'e-mail (detto anche indirizzo "Envelope From").

**L'autenticazione DKIM** DKIM (Domain Keys Identified Mail) è un successore di SPF e utilizza la crittografia a chiave pubblica che consente al server di posta elettronica ricevente di verificare che un messaggio sia stato effettivamente inviato dalla persona o dall'entità da cui sostiene di essere stato inviato e se il contenuto del messaggio sia stato alterato tra il momento in cui è stato inviato originariamente (e DKIM "firmato") e l'ora in cui è stato ricevuto. In genere, questo standard utilizza il dominio nell’intestazione "Da" o "Mittente".

**DMARC** DMARC (Domain-based Message Authentication, Reporting and Conformance) è la forma più recente di autenticazione tramite e-mail e si basa sia sull'autenticazione SPF che su quella DKIM per determinare se un'e-mail viene passata o meno. DMARC è unico e potente in due modi molto importanti:
* Conformità: consente al mittente di indicare agli ISP cosa fare con qualsiasi messaggio che non riesce ad autenticarsi (ad es. non accettarlo).
* Reporting: fornisce al mittente un rapporto dettagliato che mostra tutti i messaggi che non hanno superato l'autenticazione DMARC, insieme al dominio "Da" e all'indirizzo IP utilizzati per ciascuno di essi. Questo consente a un'azienda di identificare e-mail legittime che non ottengono l'autenticazione e che necessitano di alcuni tipi di "correzione" (ad esempio, l'aggiunta di indirizzi IP al record SPF), nonché le fonti e la prevalenza dei tentativi di phishing nei propri domini e-mail.

DMARC può sfruttare i report generati da 250ok.

**SMTP**(Simple Mail Transfer Protocol) è uno standard Internet per la trasmissione di posta elettronica.

**Gli IP** Adobe dedicati forniscono una strategia IP dedicata a ciascun cliente con un IP di espansione per creare una reputazione e ottimizzare le prestazioni di distribuzione.
