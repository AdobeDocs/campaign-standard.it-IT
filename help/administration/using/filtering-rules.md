---
title: Regole di filtro
description: Utilizza le regole di filtro per ridefinire il pubblico dei messaggi.
page-status-flag: mai attivato
uuid: ed3eea62-3a47-4318-ae22-d82aa857448f
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: regole di utilizzo
discoiquuid: 7daf36c-74e6-4501-b3eb-3d03f005aaa6
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Regole di filtro{#filtering-rules}

Le regole di filtro consentono di escludere una parte della destinazione del messaggio in base ai criteri definiti in una query, ad esempio profili o profili in quarantena già inviati da un certo numero di e-mail.

Ad esempio, potete filtrare gli utenti iscritti alla newsletter in modo che gli utenti con meno di 18 anni non ricevano mai comunicazioni.

## Creazione di una regola di filtro {#creating-a-filtering-rule}

1. Create una regola di tipo **Filtraggio** , da applicare a tutti i canali di comunicazione.

   ![](assets/typology_create-rule.png)

1. Nella **[!UICONTROL Filtering criteria]** scheda, selezionate le iscrizioni nella **[!UICONTROL Subscription]** categoria.

   ![](assets/typology_create-rule-subscription.png)

1. Nella **[!UICONTROL Explorer]** scheda dell'editor di query, trascinare il **[!UICONTROL Subscriber]** nodo nella parte principale dello schermo.

   ![](assets/typology_create-rule-subscriber.png)

1. Selezionate il **[!UICONTROL Age]** campo e definite le condizioni di filtraggio in modo che l’età degli abbonati sia pari o superiore a 18 anni.

   ![](assets/typology_create-rule-age.png)

1. Nella **[!UICONTROL Typologies]** scheda, collegate questa regola a una tipologia.

   ![](assets/typology_create-rule-typology.png)

1. Accertatevi che la tipologia in questione sia selezionata nel modello di consegna che desiderate utilizzare.

   ![](assets/typology_template.png)

   >[!NOTE]
   >
   >Per accedere ai modelli di consegna, seleziona **[!UICONTROL Resources]** &gt; **[!UICONTROL Templates]** nel menu di navigazione, accessibile tramite il logo Adobe Campaign.

Ogni volta che questa regola viene utilizzata in un messaggio, gli abbonati che sono considerati minori verranno automaticamente esclusi.

## Limitazione dell'applicabilità di una regola di filtro {#restricting-the-applicability-of-a-filtering-rule}

È possibile limitare l'applicabilità di una regola di filtro in base al messaggio da inviare.

1. Nella **[!UICONTROL Application criteria]** scheda della regola di tipologia, deselezionare l'opzione **[!UICONTROL Apply the rule on all deliveries]** , abilitata per impostazione predefinita.

   ![](assets/typology_limit.png)

1. Utilizzate l'editor di query per definire un filtro. Ad esempio, puoi applicare la regola solo ai messaggi la cui etichetta inizia con una determinata parola o il cui ID contiene determinate lettere.

   ![](assets/typology_limit-rule.png)

In questo caso, la regola viene applicata solo ai messaggi che corrispondono ai criteri definiti.

## Regole di esclusione recapito predefinite {#default-deliverability-exclusion-rules}

Per impostazione predefinita sono disponibili due regole di filtro: **[!UICONTROL Exclusion of addresses]** ( **[!UICONTROL addressExclusions]** ) e **[!UICONTROL Exclusion of domains]** ( **[!UICONTROL domainExclusions]** ). Durante l'analisi delle e-mail, queste regole confrontano gli indirizzi e-mail dei destinatari con gli indirizzi o i nomi di dominio vietati contenuti in un elenco di soppressione globale crittografato gestito nell'istanza di recapito. In caso di corrispondenza, il messaggio non viene inviato al destinatario.

Questo per evitare di essere inseriti in blacklist a causa di attività dannose, soprattutto l'uso di uno Spamtrap. Ad esempio, se si utilizza uno Spamtrap per effettuare la sottoscrizione tramite uno dei moduli Web, viene automaticamente inviata una e-mail di conferma a tale Spamtrap, che comporta la blacklist automatica dell'indirizzo.

>[!NOTE]
>
>Gli indirizzi e i nomi di dominio contenuti nell'elenco di soppressione globale sono nascosti. Solo il numero di destinatari esclusi è indicato nei registri di analisi della consegna.

