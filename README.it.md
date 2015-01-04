Manifesto per lo sviluppo di sistemi Reattivi
----------------------

Le organizzazioni che lavorano nei domini più diversi stanno scoprendo pattern sostanzialmente identici per costruire software.
Questi sistemi sono più robusti, più resilienti, più flessibili e sono meglio posizionati per rispondere alle esigenze moderne.

Questi cambiamenti si sono verificati poiché in anni recenti i requisti delle applicazioni sono radicalmente cambiati. Solo pochi anni fa una applicazione di grandi dimensioni aveva decine di server, tempi di risposta nell'ordine dei secondi, finestre di manutenzione di ore e gigabytes di dati.

Oggi le applicazioni vengono installate in modo ubiquo dai device mobili ai cluster in cloud con migliaia di processori multi-core.
Gli utenti si aspettano tempi di risposta nell'ordine dei millisecondi e il 100% di disponibilità dei sistemi. I dati sono misurati i Petabyte.
Più semplicemente, le architetture software di ieri non soddisfano più i requisiti dei sistemi di oggi.

Noi crediamo che un approccio coerente alle architetture software sia necessario e crediamo che tutti gli aspetti necessari siano stati individualmente riconoscuti:
Vogliamo che i sistemi siano Responsivi, Resilienti, Elastici e Orientati ai Messaggi. Chiameremo questi sistemi, Sistemi Reattivi.

I sistemi costruiti come Sistemi Reattivi sono più flessibili, meno interdipendenti e più [scalabili](/glossary.it#Scalabilità). Questo li rende più facili da sviluppare e più adattabili al cambiamento. Saranno significativamente più tolleranti ai guasti [guasti](/glossary.it#Guasti) e qualora dovessero verificarsi dei guasti verranno recepiti con elegantemente piuttosto in modo disastroso. I Sistemi Reattivi sono altamente responsivi, dando agli [utenti](/glossary.it#Utenti) un reale feedback interattivo.

*i Sistemi Reattivi sono:*

* <a name="Responsivi"></a>**Responsivi**: i [sistemi](/glossary.it#Sistemi) rispondono, quando è possibile, in modo tempestivo. La responsività è alla base della usabilità e della utilità, ma ancora di più, responsività significa che i problemi possono essere rilevati più in fretta e gestiti più efficacemente.
I sistemi responsivi si focalizzano nel fornire rapidi e costanti tempi di risposta, stabilendone un affidabile limite superiore in modo da fornire una qualità di servizio costante. Questo comportamente costante si traduce in una gestione più semplice degli errori, crea fiducia nell'utente finale incoraggiando ulteriori interazioni.

* <a name="Resilient"></a>**Resilient**: The system stays responsive in the face of [failure](/glossary#Failure). This applies not only to highly-available, mission critical systems — any system that is not resilient will be unresponsive after a failure. Resilience is achieved by [replication](/glossary#Replication), containment, [isolation](/glossary#Isolation) and [delegation](/glossary#Delegation). Failures are contained within each [component](/glossary#Component), isolating components from each other and thereby ensuring that parts of the system can fail and recover without compromising the system as a whole. Recovery of each component is delegated to another (external) component and high-availability is ensured by replication where necessary. The client of a component is not burdened with handling its failures.
* <a name="Elastic"></a>**Elastic**: The system stays responsive under varying workload. Reactive Systems can react to changes in the input rate by increasing or decreasing the [resources](/glossary#Resource) allocated to service these inputs. This implies designs that have no contention points or central bottlenecks, resulting in the ability to shard or replicate components and distribute inputs among them. Reactive Systems support predictive, as well as Reactive, scaling algorithms by providing relevant live performance measures. They achieve [elasticity](/glossary#Elasticity) in a cost-effective way on commodity hardware and software platforms.
* <a name="Message-Driven"></a>**Message Driven**: Reactive Systems rely on [asynchronous](/glossary#Asynchronous) [message-passing](/glossary#Message-Driven) to establish a boundary between components that ensures loose coupling, isolation, [location transparency](/glossary#Location-Transparency), and provides the means to delegate [errors](/glossary#Failure) as messages. Employing explicit message-passing enables load management, elasticity, and flow control by shaping and monitoring the message queues in the system and applying [back-pressure](/glossary#Back-Pressure) when necessary. Location transparent messaging as a means of communication makes it possible for the management of failure to work with the same constructs and semantics across a cluster or within a single host. [Non-blocking](/glossary#Non-Blocking) communication allows recipients to only consume [resources](/glossary#Resource) while active, leading to less system overhead.

Large systems are composed of smaller ones and therefore depend on the Reactive properties of their constituents. This means that Reactive Systems apply design principles so these properties apply at all levels of scale, making them composable. The largest systems in the world rely upon architectures based on these properties and serve the needs of billions of people daily. It is time to apply these design principles consciously from the start instead of rediscovering them each time.

[Sign the manifesto](http://www.reactivemanifesto.org/)
