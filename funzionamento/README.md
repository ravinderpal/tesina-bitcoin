# Funzionamento

##Il sistema Bitcoin
Il bitcoin è stato pensato per evitare i principali problemi delle valute correnti, in particolare il fatto che il livello di fiducia in esse dipenda da persone che non sempre mettono al primo posto gli interessi dei detentori di queste valute.
__Ogni valuta__ al mondo (__tranne Bitcoin__) __è controllata da grandi istituti__ che monitorano le operazioni in questa valuta e possono manipolarne il prezzo.
Le valute hanno un certo valore perché le persone ripongono la propria fiducia negli istituti che controllano queste valute. Bitcoin non chiede ai propri utenti di affidarsi a una qualche organizzazione.

La sicurezza del sistema __si basa sulla crittografia__, che ne costituisce parte integrante ed è di dominio pubblico. Invece di creare un’organizzazione indipendente che controlli le __transazioni__, queste verranno __controllate dall’intera rete__, per cui è estremamente difficile rubare bitcoin o frodare in altri modi. I bitcoin vengono emessi regolarmente e in modo calcolato. Vengono creati da una pluralità di utenti, in modo che nessuno da solo possa crearne troppi e farne diminuire il valore.
I __bitcoin__ sono stati creati in modo da essere __protetti dall’inflazione e dalla doppia spesa__ (double-spending).

Il __sistema__ è altamente __distribuito__. Tuttavia, vi sono vari modi per ottendere bitcoin in modo indebito. Innanzitutto, le chiavi private possono essere rubate. Il furto di chiavi non rientra nella lista di cose da cui il sistema Bitcoin è protetto. Le modalità di conservazione delle chiavi personali per evitarne il furto dipendono solo dagli utenti. Tuttavia la protezione crittografica del sistema è strutturata in modo tale da non permettere a nessuno di ottenere il codice personale di un utente, anche se ne conosce il codice pubblico. Finché utilizzerete una chiave privata in modo individuale, non avete nulla di cui preoccuparvi.
Il sistema Bitcoin puo’ essere forzato, ma ciò è molto difficile da attuare e richiede il coinvolgimento di esperti e di enormi di capacità di calcolo.

Il sistema Bitcoin non è totalmente inattaccabile, tuttavia è molto vicino alla perfezione. Essendo open sorce, molti sviluppatori da tutto il mondo cercano di migliorarlo sempre di più.

###Gli indirizzi
__Ogni utente__ che partecipa alla rete Bitcoin __possiede__ un portafoglio che contiene un numero arbitrario di __coppie di chiavi crittografiche__. Le __chiavi pubbliche__, o _indirizzi bitcoin_, __fungono da punti d'invio o ricezione per tutti i pagamenti__. La corrispondente __chiave privata autorizza il pagamento solo all'utente proprietario__ di una certa moneta. Gli indirizzi non contengono informazioni riguardo ai loro proprietari ed in genere sono anonimi. Gli indirizzi in forma leggibile sono sequenze casuali di caratteri e cifre lunghe in media 33 caratteri, che cominciano sempre per 1, della forma 175tWpb8K1S7NmH4Zx6rewF9WQrcZv245W. Gli utenti possono avere un numero arbitrario di indirizzi Bitcoin, ed infatti è possibile generarne a piacimento senza nessun limite in quanto la loro generazione costa poco tempo di calcolo (equivalente alla generazione di una coppia di chiavi pubblica/privata) e non richiede nessun contatto con altri nodi della rete. Creare una nuova coppia di chiavi per ogni transazione aiuta a mantenere l'anonimato.


###Le transazioni
__I bitcoin contengono la chiave pubblica del loro proprietario__ (cioè l'indirizzo). Quando un utente A trasferisce della moneta all'utente B rinuncia alla sua proprietà aggiungendo la chiave pubblica di B (il suo indirizzo) sulle monete in oggetto e firmandole con la propria chiave privata. Trasmette poi queste monete in un apposito messaggio, la _transazione_, attraverso la rete peer-to-peer. Il resto dei nodi validano le firme crittografiche e l'ammontare delle cifre coinvolte prima di accettarla.

###La _block chain_ e le conferme
Per impedire la possibilità di utilizzare più volte la stessa moneta, la rete implementa quella che Satoshi Nakamoto descrive come un _server di marcatura oraria peer-to-peer_, che assegna identificatori sequenziali ad ognuna delle transazioni che vengono poi rafforzate nei confronti di tentativi di modifica usando l'idea di una catena di proof-of-work (mostrate in Bitcoin come _conferme_).
Ogni volta che viene effettuata una transazione, essa parte nello stato di "non confermata"; diventerà "confermata" solo quando riconosciuta valida dagli altri nodi della rete e aggiunta alla block chain.
In particolare, __ogni nodo raccoglie__ tutte le __transazioni non confermate__ che conosce __in un _blocco_ __ candidato, un file che, tra le altre cose, contiene un hash crittografico del precedente blocco valido conosciuto a quel nodo. __Prova poi a riprodurre un hash di quel blocco__ con determinate caratteristiche, uno sforzo che richiede in media una quantità definibile di prove da dover effettuare. __Quando un nodo trova tale soluzione la annuncia al resto della rete__ e i peer che ricevono il blocco ne controllano la validità prima di accettarlo e poi aggiungerlo alla catena.
Quando una transazione viene ammessa per la prima volta in un blocco, riceve una conferma. Ogni volta che al di sopra di quel blocco vengono creati altri blocchi figli ad esso collegato, riceve un'altra conferma.
La motivazione dietro a questa procedura è che ad ogni conferma della transazione, ovvero ad ogni nuovo blocco che viene creato al di sopra del blocco con la transazione stessa, risulta via via più difficile e costoso annullare la transazione. Un ipotetico attaccante, per annullare una transazione con un certo numero di conferme, dovrebbe generare una catena parallela senza la transazione che desidera annullare e composta da un numero di blocchi pari o superiore alle conferme ricevute dalla transazione.
Ne consegue che __la catena dei blocchi contiene lo storico di tutti i movimenti di tutti i bitcoin generati a partire dall'indirizzo del loro creatore fino all'attuale proprietario__. Quindi, se un utente prova a riutilizzare una moneta che ha già speso, la rete rifiuterà la transazione in quanto la somma risulterà già essere spesa.
Nakamoto ha progettato il sistema in modo che, nonostante il database aumenti di dimensioni nel tempo, sia possibile averne una versione ridotta che riguardi nel dettaglio solo alcune transazioni, ma che rimanga completamente verificabile in modo indipendente. Ad esempio, per un utente privato potrebbe essere interessante avere la catena dei blocchi con le sole transazioni che lo riguardano. Oppure, potrebbe essere desiderabile ripulire dal database tutte le transazioni le cui somme in uscita sono già state utilizzate in altre transazioni, diminuendone di molto le dimensioni.






