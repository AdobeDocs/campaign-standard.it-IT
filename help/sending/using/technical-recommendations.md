---
solution: Campaign Standard
product: campaign
title: Consigli tecnici per  Adobe Campaign Standard
description: Leggi alcune raccomandazioni tecniche per migliorare la recapito con  Adobe Campaign Standard.
audience: sending
content-type: reference
topic-tags: sheduling-messages
context-tags: delivery,schedule,back
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '465'
ht-degree: 0%

---


# Raccomandazioni tecniche{#technical-recommendations}

Di seguito sono elencate diverse tecniche, configurazioni e strumenti utilizzabili per migliorare il tasso di recapito. Di seguito sono riportate alcune definizioni dei principali termini tecnici.

**Inverti DNS**:  Adobe Campaign verifica se per un indirizzo IP viene fornito un DNS inverso e che questo indichi correttamente l&#39;IP.

**Le** regole MX vengono utilizzate per controllare la velocità con cui il MTA della campagna (Agente di trasferimento messaggi) invia e-mail a ogni singolo dominio e-mail o ISP (ad esempio, hotmail.com, comcast.net). Tali regole si basano in genere sui limiti pubblicati dagli ISP (ad esempio, non includono più di 20 messaggi per ogni connessione SMTP).

**TLS** (Transport Layer Security) è un protocollo di cifratura che può essere utilizzato per proteggere la connessione tra due server e-mail e proteggere il contenuto di un&#39;e-mail dalla lettura da parte di altri destinatari.

**SPF** (Sender Policy Framework) è uno standard di autenticazione tramite e-mail che consente al proprietario di un dominio di specificare quali server e-mail possono inviare e-mail per conto di tale dominio. Questo standard utilizza il dominio nell&#39;intestazione &quot;Return-Path&quot; dell&#39;e-mail (detto anche indirizzo &quot;Envelope From&quot;).

**L&#39;autenticazione DKIM** (Domain Keys Identified Mail) è un successore di SPF e utilizza la crittografia a chiave pubblica che consente al server di posta elettronica ricevente di verificare che un messaggio sia stato effettivamente inviato dalla persona o dall&#39;entità da cui sostiene di essere stato inviato, e se il contenuto del messaggio sia stato alterato tra il momento dell&#39;invio originale (e DKIM &quot;signed&quot;) e l&#39;ora in cui è stato ricevuto. In genere, questo standard utilizza il dominio nell’intestazione &quot;Da&quot; o &quot;Mittente&quot;.

**DMARC** (Domain-based Message Authentication, Reporting and Conformance) è la forma più recente di autenticazione e-mail e si basa sia sull&#39;autenticazione SPF che su quella DKIM per determinare se un&#39;e-mail viene passata o meno. DMARC è unico e potente in due modi molto importanti:
* Conformità: consente al mittente di indicare agli ISP cosa fare con qualsiasi messaggio che non riesce ad autenticarsi (ad es. non accettarlo).
* Reporting: fornisce al mittente un rapporto dettagliato che mostra tutti i messaggi che non hanno superato l&#39;autenticazione DMARC, insieme al dominio &quot;Da&quot; e all&#39;indirizzo IP utilizzati per ciascuno di essi. Questo consente a un&#39;azienda di identificare e-mail legittime che non ottengono l&#39;autenticazione e che necessitano di alcuni tipi di &quot;correzione&quot; (ad esempio, l&#39;aggiunta di indirizzi IP al proprio record SPF), nonché le fonti e la prevalenza dei tentativi di phishing nei propri domini e-mail.

DMARC può sfruttare i report generati da 250ok.

**SMTP**  (Simple Mail Transfer Protocol) è uno standard Internet per la trasmissione di posta elettronica.

**IP** dedicati:  Adobe offre una strategia IP dedicata a ciascun cliente con un IP di espansione per costruire una reputazione e ottimizzare le prestazioni di distribuzione.
