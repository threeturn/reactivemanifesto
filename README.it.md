Manifesto dei sistemi Reattivi
----------------------

Le organizzazioni che lavorano nei domini più diversi stanno scoprendo pattern sostanzialmente identici per costruire software.
Questi sistemi sono più robusti, più resilienti, più flessibili e sono meglio posizionati per rispondere alle esigenze moderne.

Questi cambiamenti si sono verificati poiché in anni recenti i requisti delle applicazioni sono radicalmente cambiati. Solo pochi anni fa una applicazione di grandi dimensioni aveva decine di server, tempi di risposta nell'ordine dei secondi, finestre di manutenzione di ore e gigabytes di dati.

Oggi le applicazioni vengono installate in modo ubiquo dai device mobili ai cluster in cloud con migliaia di processori multi-core.
Gli utenti si aspettano tempi di risposta nell'ordine dei millisecondi e il 100% di disponibilità dei sistemi. I dati sono misurati i Petabyte.
Più semplicemente, le architetture software di ieri non soddisfano più i requisiti dei sistemi di oggi.

Noi crediamo che un approccio coerente alle architetture software sia necessario e crediamo che tutti gli aspetti necessari siano stati individualmente riconoscuti:
Vogliamo che i sistemi siano Responsivi, Resilienti, Elastici e Orientati ai Messaggi. Chiameremo questi sistemi, Sistemi Reattivi.

I sistemi costruiti come Sistemi Reattivi sono più flessibili, meno interdipendenti e più [scalabili](/glossary.it#Scalabilità). Questo li rende più facili da sviluppare e più adattabili al cambiamento. Saranno significativamente più tolleranti ai [guasti](/glossary.it#Guasti) e qualora dovessero verificarsi verranno recepiti elegantemente e non in modo disastroso. I Sistemi Reattivi sono altamente responsivi, dando agli [utenti](/glossary.it#Utenti) un reale feedback interattivo.

*i Sistemi Reattivi sono:*

* <a name="Responsivi"></a>**Responsivi**: i [sistemi](/glossary.it#Sistemi) rispondono, quando è possibile, in modo tempestivo. La responsività è alla base della usabilità e della utilità dei sistemi, ma ancora di più, responsività significa che i problemi possono essere rilevati in fretta e gestiti più efficacemente.
I sistemi responsivi si focalizzano nel fornire rapidi e costanti tempi di risposta, stabilendone un affidabile limite superiore in modo da fornire una qualità di servizio costante. Questo comportamento costante si traduce in una gestione più semplice degli errori, crea fiducia nell'utente finale incoraggiando ulteriori interazioni.

* <a name="Resilienti"></a>**Resilienti**: Il sistema rimane responsivo anche durante i [guasti](/glossary.it#Guasti). Questo concetto si applica non solo ai sistemi mission critical e in alta disponibilità — qualunque sistema che non è resiliente non sarà responsivo dopo un guasto. La Resilienza è ottenuta mediante [replicazione](/glossary.it#Replicazione), contenimento, [isolamento](/glossary.it#Isolamento) e [delega](/glossary.it#Delega). I Guasti sono confinati all'intero di ogni [componente](/glossary.it#Componente), isolando i componenti tra loro e quindi assicurando che parti del sistema possano guastarsi e ripararsi senza compromettere l'intero sistema nel suo complesso. Il ripristino di ciascun componente è delegato ad un altro componente (esterno) e l'alta disponibilità è garantita ove necessario dalla replicazione. L'onere della gestione dei guasti di un componente non è a carico di chi lo utilizza.

* <a name="Elastici"></a>**Elastici**: Il sistema rimane responsivo al variare del carico di lavoro. I Sistemi Reattivi possono reagire ai cambiamenti relativi alla velocità dell'input incrementando o decrementando le [risorse](/glossary.it#Risorse) allocate per servire questi input. Questo implica un design che non abbia elementi contesi o colli di bottiglia centrali, risultando così nella capacità di frazionare o replicare i componenti e di distribuire tra loro gli input. I Sistemi Reattivi supportano algoritmi di scaling sia predittivi sia reattivi fornendo in tempo reale delle misure relative alle performance. L'[elasticità](/glossary.it#Elasticità) viene ottenuta in un modo economicamente efficace utilizzando piattaforme hardware e software di basso costo e di largo consumo.

* <a name="Orientati ai Messaggi"></a>**Orientati ai Messaggi**: I sistemi reattivi si affidano al [message-passing](/glossary.it#Message-Driven) [asincrono](/glossary.it#Asynchronous) per stabilire un confine tra i componenti assicurando così accoppiamento lasco, isolamento, [location transparency](/glossary#Location-Transparency), e fornendo i mezzi per delegare gli [errori](/glossary.it#Failure) come messaggi. Impiegando il message-passing esplicito si permette la gestione del carico, l'elasticità e il controllo di flusso modellando e monitorando la coda dei messaggi nel sistema, applicando il [back-pressure](/glossary#Back-Pressure) quando necessario. La messaggistica location transparent come mezzo per comunicare rende possibile lavorare per la gestione dei guasti con gli stessi costrutti e la stessa semantica tra cluster o all'interno di un singolo host. La comunicazione [Non Bloccante](/glossary#Non-Blocking) permette ai destinatari di consumare solo [risorse](/glossary.it#Resource) quando sono attive, portando così ad un sistema meno sovraccaricato.

I grandi sistemi sono composti da sistemi più piccoli e perciò dipendono dalla reattività dei loro costituenti. Ciò significa che i sistemi reattivi applicano i principi di progettazione in modo che queste caratteristiche si applichino a tutti i livelli indipendentemente dalla dimensione, rendendoli componibili. I più grandi sistemi del mondo si affidano a architetture basate su queste caratteristiche e soddisfano le esigenze di miliardi di persone ogni giorno. È giunto il momento di applicare questi principi di progettazione in modo consapevole fin dall'inizio invece di riscoprirli ogni volta.


[Sottoscrivi il manifesto](http://www.reactivemanifesto.org/)
