# Glossario del manifesto per lo sviluppo di sistemi Reattivi

* [Asincrono](#Asynchronous)
* [Back-Pressure](#Back-Pressure)
* [Batching](#Batching)
* [Delega](#Delegation)
* [Componente](#Component)
* [Elasticità (in contrasto con scalabilità)](#Elasticity)
* [Guasto (a differenza di Errore)](#Failure)
* [Isolamento (e contenimento)](#Isolation)
* [Location Transparency](#Location-Transparency)
* [Orientato ai messaggi (in contrasto ad orientato agli eventi)](#Message-Driven)
* [Non-Bloccante](#Non-Blocking)
* [Protocollo](#Protocol)
* [Replica](#Replication)
* [Risorsa](#Resource)
* [Scalabilità](#Scalability)
* [Sistema](#System)
* [Utente](#User)

## <a Name="Asynchronous"></a>Asincrono
La Treccani definisce asincrono come _"che non avviene o si manifesta nel medesimo tempo"_. Nel contesto di questo manifesto intendiamo che il trattamento di una richiesta si verifica in un punto arbitrario nel tempo, in alcuni casi dopo che è stato trasmesso al servizio dal client. Quest'ultimo non è in grado di osservare direttamente o di sincronizzarsi con l'esecuzione che avviene all'interno del servizio. Ciò è l'opposto della elaborazione sincrona che implica che il client riprenda la propria esecuzione solo quando il servizio ha processato la richiesta.

## <a Name="Back-Pressure"></a>Back-Pressure
Quando uno [componente](#Component) sta facendo fatica a tenere il passo, il [sistema](#System) nel suo complesso deve continuare a rispondere in modo sensato. É inaccettabile per la componente sotto stress fallire catastroficamente o perdere messaggi in modo incontrollato. Non potendo mantenere il passo e non potendo andare in errore il componente deve comunicare che è sotto stress ai componenti a monte per indurli a ridurre il carico. La back-pressure è un importante meccanismo di feedback che permette ai sistemi di rispondere gradualmente al carico piuttosto che collassare. L'effetto della back-pressure può ripercuotersi sull'utente, e a questo punto la responsività può degradarsi, ma questo meccanismo assicurerà che il sistema sia resiliente sotto carico, e fornirà informazioni che possono consentire al sistema stesso di aggiungere altre risorse per aiutare distribuire il carico, vedere [elasticità](#Elasticity).

## <a Name="Batching"></a>Batching
Gli attuali Computer sono ottimizzati per l'esecuzione ripetuta della stessa operazione: il branch prediction e il caching delle istruzioni aumenta il numero delle istruzioni che possono essere elaborate al secondo mantenendo inalterata la frequenza di clock. Ciò significa che dare operazioni diverse per lo stesso core della CPU in rapida successione non permetterà di beneficiare del massimo delle prestazioni che potrebbero altrimenti essere realizzate: se possibile, dovremmo strutturare il programma in modo tale la sua esecuzione si alterni meno frequentemente tra diverse operazioni. Questo può significare l'elaborazione di un insieme di elementi di dati in batch, o può significare eseguire diverse fasi di computazione su thread hardware dedicati.

Lo stesso ragionamento vale per l'uso di risorse [risorse](#Resource) esterne che necessitano di sincronizzazione e di coordinamento. La larghezza di banda dell'I/O fornito da dispositivi di memorizzazione persistente può migliorare significativamente quando l'esecuzione delle operazioni avviene su un unico thread (e quindi core della CPU) invece di essere contesa tra tutti i core. Utilizzare un unico punto di ingresso ha il vantaggio che le operazioni possono essere riordinate per soddisfare meglio i modelli di accesso ottimali del dispositivo (i dispositivi di storage attuali hanno prestazioni migliori per accessi lineari piuttosto che casuali).

Inoltre, il batching offre l'opportunità di condividere il costo delle operazioni costose, come quelle costose in termini di I/O o di computazione. Ad esempio, aggregare più elementi di dati nello stesso pacchetto di rete o nello stesso blocco del disco per aumentare l'efficienza e ridurre l'utilizzo.


## <a Name="Delegation"></a>Delega
Delegare una operazione [asincrona](#Asynchronous) ad un altro [componente](#Component) significa che l'esecuzione del task si svolgerà nel contesto di tale componente. Questo contesto delegato potrebbe comportare l'esecuzione in un diverso contesto di gestione degli errori, in un thread diverso, in un processo diverso, o su un nodo di rete differente, per citarne alcune possibilità. Lo scopo della delega è quello di consegnare la responsabilità di elaborazione di una operazione ad un altro componente in modo che il componente delegante possa eseguire delle altre elaborazioni o possa opzionalmente osservare i progressi del compito delegato in caso siano necessarie azioni aggiuntive come la gestione dei guasti o il riportarne l'avanzamento.




## <a Name="User"></a>utente
Usiamo questo termine informale per riferirsi a tutti i consumatori di un servizio, sia esso essere umano o un altro servizio.

