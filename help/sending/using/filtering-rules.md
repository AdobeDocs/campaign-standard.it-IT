---
solution: Campaign Standard
product: campaign
title: Regole di filtro
description: Utilizza le regole di filtro per perfezionare il pubblico dei messaggi.
audience: administration
content-type: reference
topic-tags: working-with-typology-rules
feature: Regole di tipologia
role: Professionista
level: Intermedio
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '658'
ht-degree: 3%

---


# Regole di filtro {#filtering-rules}

Le regole di filtro ti consentono di escludere una parte del target del messaggio in base ai criteri definiti in una query, ad esempio profili in quarantena o profili a cui è già stato inviato un certo numero di e-mail.

## Regole di tipologia di filtro predefinite {#default-filtering-typology-rules}

La tabella seguente fornisce informazioni sulle regole di filtro predefinite e sui relativi canali.

| Etichetta | Canale | Descrizione |
---------|----------|---------
| **[!UICONTROL Address not specified]** | Tutto | Esclude la popolazione target senza indirizzo specifico (e-mail, indirizzo postale, ecc.) secondo il canale selezionato). |
| **[!UICONTROL Address on denylist]** | Tutto | Esclude gli indirizzi presenti nel elenco Bloccati. |
| **[!UICONTROL Duplicate]** | Tutto | Esclude i duplicati in base al campo della popolazione target **[!UICONTROL Address]** . |
| **[!UICONTROL Exclude mobile applications]** | App mobile | Sono escluse le sottoscrizioni di app che non corrispondono all’app mobile definita nel messaggio. |
| **[!UICONTROL Exclude mobile applications for In-App]** | In-App | Sono escluse le sottoscrizioni di app che non corrispondono all’app mobile definita nel messaggio (modello in-app). |
| **[!UICONTROL Exclude mobile applications for In-App broadcast]** | In-App | Sono escluse le sottoscrizioni di app che non corrispondono all’app mobile definita nel messaggio (modello di trasmissione in-app) |
| **[!UICONTROL Exclude mobile applications for Push]** | App mobile | Sono escluse le sottoscrizioni di app che non corrispondono all’app mobile definita nel messaggio (per push) |
| **[!UICONTROL Quarantined address]** | Tutto | Esclude gli indirizzi messi in quarantena. |
| **[!UICONTROL Target limited in size]** | Tutto | Controlla se la dimensione massima di consegna è stata raggiunta per la destinazione. Si applica alle consegne di direct mailing con l’opzione &quot;limite di consegna&quot; attivata. |

Inoltre, a queste regole di filtro predefinite sono disponibili due regole di esclusione:

* **[!UICONTROL Exclusion of addresses]** ( **[!UICONTROL addressExclusions]** )
* **[!UICONTROL Exclusion of domains]** ( **[!UICONTROL domainExclusions]** ).

Durante l’analisi delle e-mail, queste regole confrontano gli indirizzi e-mail dei destinatari con gli indirizzi o i nomi di dominio vietati contenuti in un elenco di eliminazione globale crittografato gestito nell’istanza di recapito messaggi. In caso di corrispondenza, il messaggio non viene inviato al destinatario.

Questo per evitare di essere aggiunti al elenco Bloccati a causa di attività dannose, soprattutto l&#39;uso di uno Spamtrap. Ad esempio, se si utilizza uno Spamtrap per effettuare l’abbonamento tramite uno dei moduli web, viene inviata automaticamente un’e-mail di conferma a tale Spamtrap, con conseguente aggiunta automatica dell’indirizzo al elenco Bloccati.

>[!NOTE]
>
>Gli indirizzi e i nomi di dominio contenuti nell’elenco di soppressione globale sono nascosti. Nei registri di analisi della consegna è indicato solo il numero di destinatari esclusi.

## Creazione di una regola di filtro {#creating-a-filtering-rule}

Puoi creare regole di filtro personalizzate in base alle tue esigenze. Ad esempio, è possibile filtrare la popolazione target delle newsletter in modo che gli abbonati con età inferiore ai 18 anni non ricevano mai comunicazioni.

Per creare una regola di tipologia di filtro, effettua le seguenti operazioni:

1. Crea una nuova regola di tipologia. I passaggi principali per creare le regole di tipologia sono descritti in [questa sezione](../../sending/using/managing-typology-rules.md).

1. Seleziona il tipo di regola **[!UICONTROL Filtering]**, quindi specifica il canale desiderato.

1. Nella scheda **[!UICONTROL Filtering criteria]** , seleziona le sottoscrizioni nella categoria **[!UICONTROL Subscription]** .

   ![](assets/typology_create-rule-subscription.png)

1. Nella scheda **[!UICONTROL Explorer]** dell’editor delle query, trascina e rilascia il nodo **[!UICONTROL Subscriber]** nella parte principale dello schermo.

   ![](assets/typology_create-rule-subscriber.png)

1. Seleziona il campo **[!UICONTROL Age]** e definisci le condizioni di filtro in modo che l’età degli abbonati sia uguale o superiore a 18 anni.

   ![](assets/typology_create-rule-age.png)

1. Nella scheda **[!UICONTROL Typologies]** , collega questa regola a una tipologia.

   ![](assets/typology_create-rule-typology.png)

1. Assicurati che la tipologia sia selezionata nel modello di consegna o consegna che desideri utilizzare. Per ulteriori informazioni al riguardo, consulta [questa sezione](../../sending/using/managing-typologies.md#applying-typologies-to-messages).

   ![](assets/typology_template.png)

Ogni volta che questa regola viene utilizzata in un messaggio, gli abbonati che sono considerati minori verranno automaticamente esclusi.

## Configurazione del contesto di targeting delle regole di filtro {#configuring-filtering-rules-targeting-context}

Campaign Standard consente di configurare le dimensioni **Targeting** e **Filtro** da utilizzare in base ai dati di destinazione.

A questo scopo, apri le proprietà della regola di tipologia, quindi accedi alla sezione **[!UICONTROL Advanced information]** .

Per impostazione predefinita, il filtraggio viene eseguito sul **[!UICONTROL Profiles]**. Ad esempio, se la regola è destinata a un’app mobile, è possibile modificare **[!UICONTROL Filtering dimension]** in **[!UICONTROL Subscriptions to an application]**.

![](assets/typology_rule-order_2.png)

## Limitazione dell&#39;applicabilità di una regola di filtro {#restricting-the-applicability-of-a-filtering-rule}

Puoi limitare l’applicabilità di una regola di filtro in base al messaggio da inviare.

1. Nella scheda **[!UICONTROL Application criteria]** della regola di tipologia, deseleziona l’opzione **[!UICONTROL Apply the rule on all deliveries]** che è attivata per impostazione predefinita.

   ![](assets/typology_limit.png)

1. Utilizza l’editor delle query per definire un filtro. Ad esempio, puoi applicare la regola solo ai messaggi la cui etichetta inizia con una determinata parola o il cui ID contiene determinate lettere.

   ![](assets/typology_limit-rule.png)

In questo caso, la regola viene applicata solo ai messaggi che corrispondono ai criteri definiti.
