---
title: Utilizzo di Email Designer
description: Scoprite il Designer e-mail e come abilita il contenuto della progettazione e-mail.
page-status-flag: mai attivato
uuid: 571ffc01-6e41-4501-9094-2f812b041a10
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: progettazione
content-type: reference
topic-tags: editing-email-content
discoiquuid: 39b86fda-7766-4e5f-ab48-bcc536ab66b3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Utilizzo di Email Designer {#email-designer}

## Panoramica di Email Designer {#about-the-email-designer}

Designer e-mail consente di creare contenuti e modelli di contenuto e-mail. È compatibile con e-mail semplici, e-mail transazionali, e-mail di test A/B, e-mail in più lingue ed e-mail ricorrenti.

Per iniziare a utilizzare e-mail Designer, guarda questo [set di video](https://helpx.adobe.com/campaign/kt/acs/using/acs-email-designer-tutorial.html#GettingStarted) che illustrano le funzionalità generali di e-mail Designer e come progettare un'e-mail da zero o utilizzando i modelli.

### Pagina principale di Designer e-mail {#email-designer-home-page}

Quando [create un messaggio e-mail](../../channels/using/creating-an-email.md), la pagina principale viene visualizzata automaticamente quando si seleziona il contenuto dell'e-mail **[!UICONTROL Email Designer]** .

![](assets/email_designer_home_page.png)

La **[!UICONTROL Properties]** scheda consente di modificare i dettagli dell'e-mail, ad esempio l'etichetta, l'indirizzo e il nome del mittente o l'oggetto dell'e-mail. Per accedere a questa scheda, fai clic sull’etichetta dell’e-mail nella parte superiore dello schermo.

![](assets/email_designer_home_properties.png)

La **[!UICONTROL Templates]** scheda consente di scegliere tra i contenuti HTML predefiniti o i modelli già creati per iniziare rapidamente a progettare l’e-mail. Consultate Modelli [di](../../designing/using/using-reusable-content.md#content-templates)contenuto.

![](assets/email_designer_home_templates.png)

La **[!UICONTROL Learn & support]** scheda consente di accedere facilmente alla documentazione e alle esercitazioni correlate.

![](assets/email_designer_home_support.png)

Se non si seleziona un modello, la home page di Designer e-mail consente inoltre di scegliere come iniziare a progettare il contenuto:

* Fate clic sul **[!UICONTROL Create]** pulsante per iniziare un nuovo contenuto da zero. Consultate [Progettazione di contenuti e-mail da zero](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch).
* Fate clic sul **[!UICONTROL Upload]** pulsante per caricare un file dal computer. Consultate [Importazione di contenuto da un file](../../designing/using/using-existing-content.md#importing-content-from-a-file).
* Fate clic sul **[!UICONTROL Import from URL]** pulsante per recuperare il contenuto esistente da un URL. Consultate [Importazione di contenuto da un URL](../../designing/using/using-existing-content.md#importing-content-from-a-url).

### Interfaccia di Progettazione e-mail {#email-designer-interface}

Designer e-mail offre diverse opzioni che consentono di creare, modificare e personalizzare ogni aspetto del contenuto.

L'interfaccia è composta da diverse aree che offrono diverse funzionalità:

![](assets/email_designer_overview.png)

Dagli elementi disponibili nella **palette** (1), trascinare componenti di struttura e frammenti di contenuto nell’ **area di lavoro** principale (2). Selezionate un componente o un elemento in **Workspace** (2) e personalizzatene lo stile principale e le caratteristiche di visualizzazione dal riquadro **Impostazioni** (3).

Accesso alle opzioni e alle impostazioni generali dalla **barra degli strumenti** principale (4).

>[!NOTE]
>
>Il riquadro **Impostazioni** può spostarsi a sinistra in base alla risoluzione e alla visualizzazione dello schermo.

![](assets/email_designer_toolbar.png)

La barra degli strumenti **contestuale** dell’interfaccia dell’editor offre diverse funzionalità a seconda della zona selezionata. Contiene pulsanti di azione e pulsanti che consentono di modificare lo stile del testo. Le modifiche effettuate si applicano sempre alla zona selezionata.

### Terminologia {#terminology}

**Modelli**: I modelli sono strutture di e-mail che potete creare e riutilizzare per diverse consegne.

**Frammenti**: Un frammento è un componente riutilizzabile a cui è possibile fare riferimento in una o più e-mail.

**Componenti** struttura: Elementi strutturali che definiscono il layout del messaggio e-mail

**Componenti** contenuto: I componenti contenuto sono componenti vuoti e non elaborati che possono essere modificati una volta inseriti in un messaggio e-mail.

### Best practice per la progettazione dei contenuti {#content-design-best-practices}

Per utilizzare in modo appropriato il Designer e-mail e creare le e-mail migliori il più semplicemente possibile, si consiglia di applicare i seguenti principi:

* Utilizzate lo stile in linea anziché CSS e CSS separati nella sezione &lt;head&gt; dell'HTML. Utilizzando lo stile in linea potete ottimizzare il salvataggio e il riutilizzo dei frammenti di contenuto.

   Consultate [Aggiunta di attributi](../../designing/using/styles.md#adding-inline-styling-attributes)di stile in linea.

* Se importate dei file ZIP contenenti contenuto HTML, utilizzate i normali CSS. I fogli di stile SCSS non sono supportati.

* Puoi impostare facilmente il tuo marchio creando e riutilizzando frammenti di contenuto per mantenere la coerenza tra le campagne di marketing.

   Vedere [Creazione di un frammento](../../designing/using/using-reusable-content.md#creating-a-content-fragment)di contenuto.

* Durante la modifica del contenuto **** e-mail:

   Visualizzare l'anteprima dei messaggi prima di inviarli. Adobe Campaign offre un modo per testare il rendering delle e-mail tramite Litmus. Per ulteriori informazioni, consultate Rendering [e-](../../sending/using/email-rendering.md)mail.

Una maggiore progettazione e best practice generali relative ai messaggi sono illustrate nella seguente guida passo-passo di Adobe Campaign: Best practice [di distribuzione con Adobe Campaign](https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_DeliveryBestPractices.html).

### Limiti di Email Designer {#email-designer-limitations}

* Non è possibile utilizzare campi di personalizzazione in un frammento. Per ulteriori informazioni sui frammenti, consultare [questa sezione](../../designing/using/using-reusable-content.md#about-fragments).
<!--* You cannot save directly as a fragment some content of an email that you are editing within the Email Designer. You need to copy-paste the HTML corresponding to that content into a new fragment. For more on this, see [Saving content as a fragment](../../designing/using/using-reusable-content.md#saving-content-as-a-fragment).-->
* Durante la modifica degli stili, sono disponibili solo i font Web ufficialmente supportati dalla maggior parte dei client e-mail.
* Non è possibile salvare gli stili come tema da riutilizzare in futuro. Tuttavia, lo stile CSS può essere salvato in un modello di contenuto o in un messaggio e-mail. Per ulteriori informazioni sugli stili, consulta [questa sezione](../../designing/using/styles.md).

### Aggiornamento dei frammenti {#email-designer-updates}

E-mail Designer è in continuo miglioramento. Se avete creato un contenuto e-mail da zero, da un modello preconfigurato o se avete creato dei frammenti, alla successiva apertura del contenuto potreste visualizzare il seguente messaggio di aggiornamento:

![](assets/email_designer_fragment_patch_message.png)

Adobe consiglia di aggiornare il contenuto alla versione più recente per evitare problemi quali problemi di collisione CSS. Click **[!UICONTROL Update now]**.

Se si verifica un errore durante l'aggiornamento del contenuto, controllate il codice HTML e correggetelo prima di eseguire nuovamente l'aggiornamento.

Per quanto riguarda i frammenti, tenere presente quanto segue:

* Se si desidera aggiungere un frammento a un nuovo indirizzo e-mail o modello e se si riceve questo messaggio, è necessario aggiornare prima il frammento.

* Se si dispone di più frammenti, è necessario aggiornare ogni frammento che si desidera utilizzare in un contenuto e-mail.

* Per evitare l’impatto sugli attuali messaggi e-mail non ancora preparati, è possibile scegliere di non aggiornare alcuni frammenti.

* È comunque possibile inviare e-mail in cui un frammento non aggiornato è già utilizzato, ma tale frammento non è modificabile.

* L'aggiornamento dei frammenti utilizzati nelle e-mail già preparate non ha alcun impatto su tali e-mail.