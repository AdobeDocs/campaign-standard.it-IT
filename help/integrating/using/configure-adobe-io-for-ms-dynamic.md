---
title: Configurare l'integrazione Adobe IO per Microsoft Dynamics 365
description: Scoprite come configurare l'integrazione di Adobe IO per Microsoft Dynamics 365.
page-status-flag: never-activated
uuid: effa1028-66b2-4bef-b5e4-7319dbb23d5d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics
discoiquuid: eb3639f5-7246-46c4-8ddb-da9413b40c32
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a1bc9d23163d12517c4501a572fc92aac6aacbc6

---


# Configurare l&#39;integrazione Adobe IO per Microsoft Dynamics 365

Attiva i dati CRM sulla comunicazione tra canali: istruzioni sui passaggi necessari durante il post-provisioning per creare una nuova integrazione per Microsoft Dynamics 365.

## Panoramica

L&#39;integrazione Adobe Campaign Standard - Microsoft Dynamics 365 è descritta in [questa pagina](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md).

Prima di eseguire i passaggi successivi al provisioning in questo articolo, si presume che sia già stato eseguito il provisioning e che l&#39;amministratore abbia accesso all&#39;istanza Campaign Standard della propria organizzazione.  Se non è successo, per completare il provisioning di Campaign dovrete contattare l&#39;Assistenza clienti Adobe.

>[!CAUTION]
>
>I passaggi descritti di seguito devono essere eseguiti da un amministratore.

## Configurazione

Devi configurare l&#39;accesso alle API e una nuova integrazione per Unifi.

La configurazione viene effettuata in Adobe IO: devi creare una nuova integrazione per Unifi, come illustrato in questo video:

>[!VIDEO](https://video.tv.adobe.com/v/27308)

### Creare una nuova integrazione

A tal fine, attenersi alla procedura seguente:

1. Passa ad [Adobe IO Console](https://console.adobe.io/home#) e seleziona il tuo Adobe IMS Organization ID dal menu a discesa in alto a sinistra (vedi sotto).

Quindi fate clic su **[!UICONTROL New Integration]** in alto a destra.

>[!NOTE]
>
>Se si tratta della prima integrazione dell’organizzazione, il pulsante **[!UICONTROL New Integration]** potrebbe trovarsi al centro della pagina.

1. Selezionate **[!UICONTROL Access an API]** e fate clic su **[!UICONTROL Continue]**.

1. Seleziona _Adobe Campaign_ dalla **[!UICONTROL Experience Cloud]** sezione e fai clic su **[!UICONTROL Continue]**.

1. Generare un certificato e una chiave.

**Per le piattaforme MacOS e Linux**

Aprite l&#39;applicazione terminale ed eseguite il comando seguente:

```
openssl req -x509 -sha256 -nodes -days 365 -newkey rsa:2048 -keyout private.key -out certificate_pub.crt
```

**Per piattaforme Windows**

* Scaricate un client open per generare certificati pubblici (ad esempio, client [](https://bintray.com/vszakats/generic/download_file?file_path=openssl-1.1.1-win64-mingw.zip)Openssl windows)

* Estrarre la cartella dal file zip

* Aprite il prompt della riga di comando ed eseguite sotto i comandi.

Sostituisci `<containing folder path>` di seguito con il percorso della cartella estratta (ad esempio, C:\Users\labuser\Downloads\openssl-1.1.1-win64-mingw\openssl-1.1.1-win64-mingw):

```
set OPENSSL_CONF=<containing folder path>/openssl.cnf
 
cd <containing folder path>/
 
openssl req -x509 -sha256 -nodes -days 365 -newkey rsa:2048 -keyout private.key -out certificate_pub.crt
```

**Per tutte le piattaforme**

Seguite i prompt per completare la richiesta del certificato:

```
Generating a 2048 bit RSA private key
 
.................+++
 
.......................................+++
 
writing new private key to 'private.key'
 
-----
 
You are about to be asked to enter information that will be incorporated
 
into your certificate request.
 
What you are about to enter is what is called a Distinguished Name or a DN.
 
There are quite a few fields but you can leave some blank
 
For some fields there will be a default value,
 
If you enter '.', the field will be left blank.
 
-----
```

Dopo aver immesso le informazioni, verranno generati due file: **[!UICONTROL certificate_pub.crt]** e **[!UICONTROL private.key]**.

* **[!UICONTROL certificate_pub.crt]** scadrà tra 365 giorni. È possibile modificare il periodo di scadenza modificando il valore dei giorni nel comando open, ma ruotare le credenziali periodicamente è una buona procedura di sicurezza.

* **[!UICONTROL certificate_pub.crt]** verrà utilizzata nella schermata successiva per completare l&#39;integrazione nella console di I/O di Adobe.

>[!NOTE]
>
> **[!UICONTROL private.key]** verranno utilizzati in un secondo momento durante i passaggi successivi al provisioning per Unifi.

1. Tornate alla console di I/O di Adobe e immettete un nome e una descrizione per l’integrazione.

1. Carica **[!UICONTROL certificate_pub.crt]**

1. Selezionate il profilo di prodotto nel titolo:

* L&#39;ID organizzazione dell&#39;istanza della campagna
* **[!UICONTROL Administrators]**

Esempio:  Campaign Standard - Your campaign-organizerID - Administrators

Fate clic su **[!UICONTROL Create Integration]**.

![](assets/MSdynACSIntegration-4B.png)

### Impostazione dei dettagli di integrazione

1. Select **[!UICONTROL Continue to Integration Details]**

Esaminate i dettagli dell&#39;integrazione.  Dovrete farvi riferimento quando eseguite i passaggi di post-provisioning Unifi.

![](assets/MSdynACSIntegration-5.png)

1. Fare clic sulla **[!UICONTROL Services]** scheda e aggiungere **[!UICONTROL I/O Events]** e **[!UICONTROL I/O Management API]** servizi.  Per aggiungere il servizio, fare clic sul pulsante di scelta, quindi **[!UICONTROL Add service]**.  Questo verrà fatto separatamente per ogni servizio.

Al termine, i servizi dovrebbero essere visualizzati in alto come l&#39;immagine seguente. Non sarà necessario completare la sezione a-on generando un JWT e un token di accesso.

![](assets/MSdynACSIntegration-6.png)

Il post-provisioning in Campaign ora è completo.  Procedete con i passaggi [successivi al provisioning per Microsoft Dynamics 365](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md).

**Argomenti correlati**

* [Adobe IO - Integrazione dell&#39;account di servizio](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)
* [Campaign Standard - Impostazione accesso API](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#setting-up-api-access)
* [Campaign Standard - Integrazione Dynamics 365](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md)
