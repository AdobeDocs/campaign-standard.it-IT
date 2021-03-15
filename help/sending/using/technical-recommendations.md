---
solution: Campaign Standard
product: campaign
title: Raccomandazioni tecniche per il recapito messaggi per Adobe Campaign Standard
description: Leggi alcune raccomandazioni tecniche per migliorare il recapito messaggi con Adobe Campaign Standard.
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
source-wordcount: '469'
ht-degree: 0%

---


# Raccomandazioni tecniche{#technical-recommendations}

Di seguito sono elencate diverse tecniche, configurazioni e strumenti che è possibile utilizzare per migliorare il tasso di recapito messaggi. Di seguito sono riportate alcune definizioni dei principali termini tecnici.

**DNS** inversi: Adobe Campaign controlla se viene fornito un DNS inverso per un indirizzo IP e che questo punti correttamente all’IP.

**Le** regole MX vengono utilizzate per controllare la velocità con cui l’MTA della campagna (Agente di trasferimento messaggi) invia e-mail a ogni singolo dominio e-mail o ISP (ad esempio hotmail.com, comcast.net). Tali regole si basano in genere sui limiti pubblicati dagli ISP (ad esempio, non includono più di 20 messaggi per ogni connessione SMTP).

**TLS**  (Transport Layer Security) è un protocollo di cifratura che può essere utilizzato per proteggere la connessione tra due server e-mail e proteggere il contenuto di un’e-mail dalla lettura da parte di qualsiasi altro destinatario diverso da quello a cui è destinato.

**SPF**  (Sender Policy Framework) è uno standard di autenticazione e-mail che consente al proprietario di un dominio di specificare quali server e-mail possono inviare e-mail per conto di tale dominio. Questo standard utilizza il dominio nell’intestazione &quot;Return-Path&quot; dell’e-mail (noto anche come indirizzo &quot;Envelope From&quot;).

**L’autenticazione DKIM**  (Domain Keys Identified Mail) sostituisce SPF e utilizza la crittografia a chiave pubblica che consente al server di posta elettronica ricevente di verificare che un messaggio sia stato effettivamente inviato dalla persona o dall’entità da cui si dichiara di essere stato inviato e se il contenuto del messaggio è stato modificato o meno tra il momento dell’invio originale (e il momento in cui è stato ricevuto DKIM &quot;signed&quot;) e il momento in cui è stato ricevuto. In genere, questo standard utilizza il dominio nell’intestazione &quot;Da&quot; o &quot;Mittente&quot;.

**DMARC**  (Domain-based Message Authentication, Reporting and Conformance) è la forma più recente di autenticazione tramite e-mail e si basa sia sull’autenticazione SPF che su DKIM per determinare se un’e-mail viene passata o meno. Il DMARC è unico e potente in due modi molto importanti:
* Conformità : consente al mittente di istruire gli ISP su cosa fare con qualsiasi messaggio che non riesce ad autenticarsi (ad esempio, non accettarlo).
* Reporting : fornisce al mittente un rapporto dettagliato che mostra tutti i messaggi che non hanno eseguito l’autenticazione DMARC, insieme al dominio &quot;Da&quot; e all’indirizzo IP utilizzati per ciascuno di essi. Questo consente a un&#39;azienda di identificare e-mail legittime che non stanno eseguendo l&#39;autenticazione e che necessitano di un certo tipo di &quot;fix&quot; (ad esempio, l&#39;aggiunta di indirizzi IP al proprio record SPF), nonché le fonti e la prevalenza di tentativi di phishing nei loro domini e-mail.

Il DMARC può sfruttare i report generati da 250ok.

**SMTP**  (protocollo di trasferimento semplice della posta) è uno standard Internet per la trasmissione della posta elettronica.

**IP** dedicati: Adobe fornisce una strategia IP dedicata per ogni cliente con un IP di espansione per costruire una reputazione e ottimizzare le prestazioni di consegna.
