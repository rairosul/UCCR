---

copyright:
 years: 2017
lastupdated: "2017-6-22"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:pre: .pre}


# Informazioni su {{site.data.keyword.uccr_short}}
{: #about_UCCR}


## Definizione di {{site.data.keyword.uccr_short}}
{: #what}

{{site.data.keyword.uccr_full}} è uno strumento di gestione della release ridimensionato per l'azienda. {{site.data.keyword.uccr_short}} funziona perfettamente con altri servizi Bluemix e con i tuo prodotti UrbanCode&reg; in loco.

Con {{site.data.keyword.uccr_short}} puoi fare quanto segue:

<ul>
<li>orchestrare le distribuzioni con più applicazioni
</li>
<li>visualizzare le dipendenze dell'applicazione e del progetto
</li>
<li>automatizzare la promozione di codice basata sulla qualità
</li>
<li>semplificare la pianificazione degli eventi della release principali
</li>
</ul>


## Termini chiave
{: #keyterms}

I seguenti termini sono utilizzati frequentemente con {{site.data.keyword.uccr_short}}:

**Attività**: le attività fanno riferimento agli elementi che possono essere visualizzati nell'elenco **Activities** nella pagina Releases. Le attività includono le release, gli eventi e i piani di distribuzione. Puoi filtrare l'elenco **Activities** per stato, ora e tag.  

**Applicazione**: l'applicazione fa riferimento alle applicazioni IBM UrbanCode Deploy che gestisce {{site.data.keyword.uccr_short}}. In {{site.data.keyword.uccr_short}}, assegni le applicazioni integrate alle attività del tipo UrbanCode Deploy. Selezioni gli ambienti, le versioni e i processi dell'applicazione. Quando viene eseguita un'attività UrbanCode Deploy, anche l'applicazione associata viene eseguita in IBM UrbanCode Deploy.

**Attività automatica**: durante le distribuzioni, le attività automatiche si avviano come diventano eleggibili per l'esecuzione. Le attività automatiche includono i seguenti tipi di attività: UrbanCode Deploy, Continuous Delivery Pipeline, email, Slack, esecuzione di un altro piano e ritardata.

**Attività dipendenti**: la capacità di un'attività di avviarsi può dipendere dal completamento di altre attività. Un'attività in attesa del completamento di altre attività viene chiamata un'attività dipendente. Un'attività attesa da un'attività dipendente viene chiamata attività prerequisita. Le attività dipendenti non possono essere avviate finché tutte le relative attività prerequisite non sono state risolte. Generalmente, utilizzi le dipendenze per assicurarti che le attività vengano eseguite nell'ordine previsto.

**Durata**: il tempo necessario per eseguire le attività. La durata viene misurata dall'ora di avvio dell'attività finché non viene risolta. Quando crei alcuni tipi di attività, puoi stimare la durata prevista. La durata viene riportata in minuti.

**Ambiente**: rappresenta gli ambienti dell'applicazione IBM UrbanCode Deploy. In UrbanCode Deploy, gli ambienti definiscono le destinazioni della distribuzione. In {{site.data.keyword.uccr_short}}, quando esegui le attività UrbanCode Deploy, selezioni l'ambiente. Puoi specificare l'ambiente quando crei l'attività o al runtime. 

**Modello di esecuzione**: fa riferimento all'ordine in cui le attività in una distribuzione diventano eleggibili per l'esecuzione. Per impostazione predefinita, un modello di esecuzione del piano è sequenziale. Le attività sequenziali vengono avviate in ordine iniziando dalla prima attività nel piano di distribuzione. Puoi combinare le attività in gruppi e assegnare il modello di esecuzione parallela al gruppo. Le attività parallele possono essere eseguite in qualsiasi ordine e simultaneamente.

Assegni il modello di esecuzione parallela ai gruppi quando li crei. Il modello di esecuzione previsto può essere influenzato dalle dipendenze dell'attività. 

**Integrazione**: fa riferimento alla comunicazione regolarizzata tra {{site.data.keyword.uccr_short}} e altri prodotti e servizi. La comunicazione tra {{site.data.keyword.uccr_short}} e i prodotti integrati può essere bidirezionale. Ad esempio, IBM UrbanCode Deploy può inviare i dati dell'applicazione a {{site.data.keyword.uccr_short}} e {{site.data.keyword.uccr_short}} può quindi eseguire le applicazioni. Le integrazioni sono configurate con IBM Bluemix DevOps Connect. 

**Processo**: fa riferimento ai processi dell'applicazione UrbanCode Deploy. In UrbanCode Deploy, i processi definiscono le attività di automazione, come la distribuzione dei componenti. In {{site.data.keyword.uccr_short}}, quando esegui le attività UrbanCode Deploy, selezioni il processo. Puoi selezionare il processo quando crei l'attività o al runtime.

**Tag**: una tag è un'etichetta che puoi applicare alle attività o alle release. Quando applicate alle attività, le tag possono determinare l'applicabilità dell'attività a una distribuzione fornita. Quando applicate alle release, le tag possono essere utilizzate per organizzare e filtrare le release.

**Gruppo di attività**: puoi combinare due o più attività in un gruppo di attività. Quando crei un gruppo, definisci il modello di esecuzione del gruppo, se sequenziale o parallela.

**Team**: un team è una raccolta di utenti e gruppi. In {{site.data.keyword.uccr_short}}, i team gestiscono le release, gli eventi e i piani di distribuzione. I team possono essere importati da IBM UrbanCode Deploy.

**Versione**: rappresenta un'istantanea dell'applicazione IBM UrbanCode Deploy. Quando crei un'attività UrbanCode Deploy, le versioni che appartengono all'applicazione assegnata all'attività vengono archiviate nel piano di distribuzione. Puoi utilizzare la scheda Version per selezionare gli ambienti e le versioni dell'applicazione da utilizzare quando viene eseguita un'attività.

## Concetti chiave
{: #keyconcepts}

**Distribuzione**:
Il termine distribuzione fa riferimento alle attività utilizzate per consegnare un progetto software a una destinazione di distribuzione. Generalmente, esegui le distribuzioni per ogni fase del tuo ciclo di vita della release, terminando con la fase di produzione. Le attività che vengono eseguite durante una distribuzione, chiamate attività, sono definite nei piani di distribuzione. Avvii una distribuzione avviando una delle attività eleggibili del piano. Completi una distribuzione risolvendo tutte le attività nel piano di distribuzione.

**Piano di distribuzione**: un piano di distribuzione è un piano ripetibile che viene utilizzato per gestire le release software. I piani di distribuzione contengono le attività che utilizzi per eseguire le distribuzioni. Quando aggiungi un'attività a un piano di distribuzione, ne definisci il tipo e la durata.

Quando sei pronto per eseguire una distribuzione, avvia una delle attività eleggibili del piano. L'eleggibilità di avvio di un'attività viene determinata dal proprio modello di esecuzione. Le attività automatiche si avviano come diventano eleggibili per l'esecuzione. Le attività manuali vengono avviate manualmente.   

**Evento**: gli eventi sono attività correlate alle release che vengono applicate alle release e tracciate con il calendario. Puoi utilizzare gli eventi per organizzare le tue release e altre attività dipendenti dal tempo, come le festività e i blackout. 

**Attività**: generalmente, un'attività rappresenta un'attività significativa di business con punti di avvio e fine e una durata misurabile. Le durate sono utilizzate per stimare i tempi di distribuzione. Aggiungi le attività ai piani di distribuzione. Quando esegui una distribuzione, completi le attività nel piano.

Puoi definire diversi tipi di attività. 
<ul>
<li>Le attività UrbanCode Deploy eseguono i processi dell'applicazione in IBM UrbanCode Deploy. La fornitura continua traccia le versioni (istantanee) e gli ambienti che vengono utilizzati dalle applicazioni. Queste attività si avviano in automatico quando diventano eleggibili per l'esecuzione.
</li>
<li>Le attività manuali possono rappresentare qualsiasi attività relativa a una distribuzione, come l'avvio di un server. Le attività manuali, come implica il nome, vengono avviate manualmente. </li>
<li>Le attività ritardate rappresentano gli eventi cardine importanti. Un'attività ritardata, poiché è un'attività automatica, si avvia come è eleggibile e finisce all'ora specificata per l'attività. Generalmente, le attività ritardate sono prerequisite per altre attività.
</li>
<li>Le attività di intestazione forniscono gli elementi organizzativi ai piani di distribuzione. Puoi utilizzare un'attività di intestazione per identificare un gruppo di attività o per aggiungere note o istruzioni a un gruppo. Le attività di intestazione sono attività automatiche e terminano appena cominciano. Non puoi definire la durata delle attività di intestazione.
</li>
<li>Le attività email inviano i messaggi agli account email.
</li>
<li>Le attività Slack inviano i messaggi a un canale Slack specifico per l'utente.
</li>
<li>Le attività pipeline Continuous Delivery automatizzano i tuoi flussi di lavoro DevOps. Puoi gestire le tue pipeline con le attività pipeline.
</li>
</ul>

**Release**:
Una release è un contenitore per i piani di distribuzione, gli eventi e le tag. Generalmente, una release contiene diversi piani di distribuzione anche se non c'è bisogno che contenga più di un piano. Parlando sempre in senso generico, ogni piano in una release rappresenta una fase nel ciclo di vita dello sviluppo, come QA o produzione. Alle fasi o ai piano di distribuzione, viene collettivamente fatto riferimento come al ciclo di vita della release.
