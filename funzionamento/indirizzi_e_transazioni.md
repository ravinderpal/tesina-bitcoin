# Indirizzi e transazioni

## Gli indirizzi

**Ogni utente** che partecipa alla rete Bitcoin **possiede** un portafoglio che contiene un numero arbitrario di **coppie di chiavi crittografiche**. Le **chiavi pubbliche**, o _indirizzi bitcoin_, **fungono da punti d'invio o ricezione per tutti i pagamenti**. La corrispondente **chiave privata autorizza il pagamento solo all'utente proprietario** di una certa moneta. Gli indirizzi non contengono informazioni riguardo ai loro proprietari ed in genere sono anonimi. Gli indirizzi in forma leggibile sono sequenze casuali di caratteri e cifre lunghe in media 33 caratteri, che cominciano sempre per 1, della forma 175tWpb8K1S7NmH4Zx6rewF9WQrcZv245W. Gli utenti possono avere un numero arbitrario di indirizzi Bitcoin, ed infatti è possibile generarne a piacimento senza nessun limite in quanto la loro generazione costa poco tempo di calcolo \(equivalente alla generazione di una coppia di chiavi pubblica/privata\) e non richiede nessun contatto con altri nodi della rete. Creare una nuova coppia di chiavi per ogni transazione aiuta a mantenere l'anonimato.

## Le transazioni

![Transazione](http://www.businessmagazine.it/articoli/3710/digitalc2.jpg) **I bitcoin contengono la chiave pubblica del loro proprietario** \(cioè l'indirizzo\). Quando un utente A trasferisce della moneta all'utente B rinuncia alla sua proprietà aggiungendo la chiave pubblica di B \(il suo indirizzo\) sulle monete in oggetto e firmandole con la propria chiave privata. Trasmette poi queste monete in un apposito messaggio, la _transazione_, attraverso la rete peer-to-peer. Il resto dei nodi validano le firme crittografiche e l'ammontare delle cifre coinvolte prima di accettarla.

### La _block chain_ e le conferme

Per impedire la possibilità di utilizzare più volte la stessa moneta, la rete implementa quella che Satoshi Nakamoto descrive come un _server di marcatura oraria peer-to-peer_, che assegna identificatori sequenziali ad ognuna delle transazioni che vengono poi rafforzate nei confronti di tentativi di modifica usando l'idea di una catena di proof-of-work \(mostrate in Bitcoin come _conferme_\). Ogni volta che viene effettuata una transazione, essa parte nello stato di "non confermata"; diventerà "confermata" solo quando riconosciuta valida dagli altri nodi della rete e aggiunta alla block chain.

In particolare, **ogni nodo raccoglie** tutte le **transazioni non confermate** che conosce **in un** _**blocco**_ **** candidato, un file che, tra le altre cose, contiene un hash crittografico del precedente blocco valido conosciuto a quel nodo. **Prova poi a riprodurre un hash di quel blocco** con determinate caratteristiche, uno sforzo che richiede in media una quantità definibile di prove da dover effettuare. **Quando un nodo trova tale soluzione la annuncia al resto della rete** e i peer che ricevono il blocco ne controllano la validità prima di accettarlo e poi aggiungerlo alla catena. Quando una transazione viene ammessa per la prima volta in un blocco, riceve una conferma. Ogni volta che al di sopra di quel blocco vengono creati altri blocchi figli ad esso collegato, riceve un'altra conferma.

![blockchain](http://www.bitcoinsecurity.org/wp-content/uploads/2012/07/block-chain.png)

La motivazione dietro a questa procedura è che ad ogni conferma della transazione, ovvero ad ogni nuovo blocco che viene creato al di sopra del blocco con la transazione stessa, risulta via via più difficile e costoso annullare la transazione. Un ipotetico attaccante, per annullare una transazione con un certo numero di conferme, dovrebbe generare una catena parallela senza la transazione che desidera annullare e composta da un numero di blocchi pari o superiore alle conferme ricevute dalla transazione.

Ne consegue che **la catena dei blocchi contiene lo storico di tutti i movimenti di tutti i bitcoin generati a partire dall'indirizzo del loro creatore fino all'attuale proprietario**. Quindi, se un utente prova a riutilizzare una moneta che ha già speso, la rete rifiuterà la transazione in quanto la somma risulterà già essere spesa.

Nakamoto ha progettato il sistema in modo che, nonostante il database aumenti di dimensioni nel tempo, sia possibile averne una versione ridotta che riguardi nel dettaglio solo alcune transazioni, ma che rimanga completamente verificabile in modo indipendente. Ad esempio, per un utente privato potrebbe essere interessante avere la catena dei blocchi con le sole transazioni che lo riguardano. Oppure, potrebbe essere desiderabile ripulire dal database tutte le transazioni le cui somme in uscita sono già state utilizzate in altre transazioni, diminuendone di molto le dimensioni.

