---
title: Limitazioni delle pagine di destinazione
seo-title: Limitazioni delle pagine di destinazione
description: Limitazioni delle pagine di destinazione
seo-description: Scoprite le pagine di destinazione della campagna e il relativo ciclo di vita.
page-status-flag: never-activated
uuid: b 316 bf 47-7 d 98-46 fa-ab 4 f -67 ff 50 de 8095
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: canali
content-type: riferimento
topic-tags: landing-pages
discoiquuid: ca 8 d 1698-6 e 8 a -4 f 5 a-b 017-74 a 152 e 14286
context-tags: Landingpage, wizard; Landingpage, overview; Landingpage, main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 578993ccdf8f31c527c62a9d7fc84daa1c61e94a

---


# Landing page limitations{#landing-page-limitations}

**Scrittura e aggiornamento dei dati**

* Landing pages are limited to **[!UICONTROL Profile]** and **[!UICONTROL Subscription]** resources only. Record can be saved and updated from **[!UICONTROL Profile]** and a subscription/unsubscription to a **[!UICONTROL Service]**.
To learn more on resources configuration, see [Configuring the resource's data structure](../../developing/using/configuring-the-resource-s-data-structure.md).

>[!CAUTION]
>
> A landing page cannot display or update data from any other resource than **[!UICONTROL Profile]** and **[!UICONTROL Subscription]**.

**Precaricamento**

* La pagina di destinazione non può visualizzare automaticamente un elenco di record, ma non può elencare i servizi a cui sono già stati iscritti. For more information on services, refer to this [page](../../audiences/using/creating-a-service.md).

* È possibile accedere a una pagina di destinazione con un modulo precompilato (dati precompilati con la pagina) da un'e-mail di Adobe Campaign. Non è possibile accedere a tale modulo dalla pagina di un sito Web.

**Riconciliazione**

* Il comportamento di riconciliazione è il seguente: Non appena viene trovata una corrispondenza, il processo di riconciliazione si interrompe. Ciò significa che la riconciliazione può essere effettuata solo su un record di profilo e non su più record in presenza di duplicati.

Ad esempio, vuoi inviare la seguente pagina di destinazione di acquisizione ai tuoi profili per aggiornare il database campagna con i numeri dei dispositivi mobili dei tuoi profili.

![](assets/landing_page_limitation_1.png)

Se uno del profilo compila la pagina di destinazione con nuove informazioni ma dispone già di un profilo duplicato, il profilo corrispondente con la data di creazione prima verrà aggiornato in base alla priorità di creazione dei profili in base alla data di creazione.

Qui solo il primo profilo è stato aggiornato in quanto era la voce più obsoleta.

![](assets/landing_page_limitation_2.png)

**Verifica della pagina di destinazione**

* Le pagine di destinazione funzionano solo sui profili e non sui profili, per cui non è possibile testare le pagine di destinazione come parte di una prova e-mail.
