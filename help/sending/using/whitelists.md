---
title: Whitelists in Adobe Campaign Standard
description: Scopri come ottimizzare le whitelist con Adobe Campaign Standard.
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


# Whitelists{#whitelists}

I principali provider di servizi Internet (ISP) e provider di posta Web gestiscono le whitelist dai mittenti di messaggi e-mail riconosciuti. Adobe Campaign ti aiuta a ottenere la certificazione sulle migliori whitelist.

Una whitelist e-mail è un elenco di indirizzi e-mail o nomi di dominio da cui un programma di blocco e-mail consentirà la ricezione di messaggi.

Esistono due tipi di whitelist:
* Liste bianche non commerciali
* Whitelist commerciale

## Liste bianche non commerciali {#non-commercial-whitelists}

Per essere accettato da queste whitelist, il mittente deve superare una serie di test basati su una verifica tecnica (il suo server di posta elettronica non deve essere un relè aperto ma deve avere un IP statico) dell'infrastruttura o della sua attività (frequenza di consegna, volume, numero di reclami).

Se il mittente non segue una di queste regole, può essere eliminato dalla whitelist. Nel pacchetto **Adobe Campaign Email Deliverability** , Adobe Campaign offre un servizio di consulenza specialistica che accompagna il processo di certificazione per le whitelist non commerciali.

## Whitelist commerciale {#commercial-whitelists}

Le whitelist commerciali si basano su un sistema che consente al mittente di bypassare del tutto i filtri antispam o di ricevere punti incrementali al momento dell'ingresso nel sistema. Queste whitelist a pagamento (CPT o su base annuale) sono offerte da sistemi come Return Path Sender Score (Punteggio mittente percorso di ritorno).

Gli ISP sono liberi di utilizzare questi servizi e il numero di ISP può variare a seconda della whitelist. Un mittente può quindi essere più sicuro di sé quando invia i suoi messaggi con una garanzia di consegna. Alcune whitelist offrono inoltre l’opportunità di aprire le immagini e attivare i collegamenti.

La visualizzazione di una whitelist è una risorsa innegabile per qualsiasi campagna e-mail. Nel pacchetto **Adobe Campaign Email Deliverability** , Adobe Campaign offre un servizio di certificazione della whitelist commerciale come CSA e Return Path Sender Score.