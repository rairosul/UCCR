---

copyright:
 years: 2017
lastupdated: "2017-6-22"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}

# Gestione eventi e tag 
{: #events_overview}

Un evento rappresenta un'attività correlata alla release che gestisci con il calendario. 

Una tag è un'etichetta che puoi aggiungere a una release o a un evento. Puoi utilizzare le tag per filtrare l'elenco delle attività nella pagina Release. A differenza degli eventi, le tag non vengono visualizzate sul calendario. 

{:shortdesc}

Gli eventi sono organizzati in categorie generali che includono le release, le festività e le finestre di manutenzione. [Le tag e gli eventi del calendario sono assegnati alle release](UCCR_releases.html#releases_overview). Puoi aggiungere gli eventi alle release o utilizzarli indipendentemente.   

Quando viene assegnato un evento, viene rappresentato sul calendario da un'icona appropriata per la categoria evento. Puoi utilizzare le icone per filtrare la pagina Releases e selezionare le release per qualsiasi data o intervallo di date interessato.

Le tag sono assegnate alle release e possono essere utilizzate per filtrare la pagina Releases. Le tag assegnate vengono visualizzate nella pagina Release ma non vengono visualizzate sul calendario. Puoi utilizzare le tag per evitare i messaggi secondari del calendario.

## Filtro degli eventi della release e dei piani di distribuzione
{: #events_findFilter}

La pagina Releases visualizza le release, gli eventi e i piani di distribuzione creati da te e dal tuo team. Dalla pagina Releases, puoi eseguire le attività maggiormente correlate alla release, come la creazione delle release e dei piani di distribuzione.

Per impostazione predefinita, la pagina Releases visualizza le attività che sono pianificate per i prossimi sette giorni. Puoi filtrare la visualizzazione per ora, evento, tag e stato. Ad esempio, potresti limitare la visualizzazione alle release che sono pianificate per domani. L'intervallo di date selezionato corrente viene visualizzato nella barra delle azioni.

Per filtrare la pagina Releases per evento o tag, seleziona l'evento o la tag nella barra di ricerca e quindi premi Invio.

Per filtrare le attività pianificate per data, completa una delle seguenti attività: 
<ul>
<li>Seleziona un valore dall'elenco **Dates** nella barra delle azioni. Ad esempio, per visualizzare gli elementi pianificati per la prossima settimana, seleziona **Next 7 days**.</li>
<li>Nel calendario, seleziona una data o un intervallo di date. Quando selezioni le data nel calendario, il valore **Dates** nella barra delle azioni viene impostato su **Custom**.</li>
</ul>

Vengono visualizzate le attività che sono state pianificate per le date selezionate.

Per filtrare gli elementi in base allo stato, seleziona uno dei seguenti filtri: 
<ul>
<li>Seleziona **All** per visualizzare tutte le attività. Visualizza tutte le release, gli eventi e i piani di distribuzione tranne quelli che sono stati archiviati. Utilizza questa opzione per visualizzare i piani di distribuzione non pianificati. </li>
<li>Seleziona **Draft** per visualizzare i piani di distribuzione con uno stato diverso da In Progress, Complete o Failed.
</li>
<li>Seleziona **Scheduled** per visualizzare le release, gli eventi e i piani pianificati per l'intervallo di date selezionato.
</li>
<li>Seleziona **In Progress** per visualizzare le distribuzioni in corso ma che non hanno lo stato di Complete o Failed.
</li>
<li>Seleziona **Failed** per visualizzare le distribuzioni con lo stato di Failed.</li>
<li>Seleziona **Complete** per visualizzare le distribuzioni con lo stato di Complete.
</li>
</li>
<li>Seleziona **Archive** per visualizzare le release, gli eventi e i piani di distribuzione salvati nell'archivio. Gli elementi archiviati possono essere ripristinati.
</li>
<li>Seleziona **Templates** per visualizzare i piani di distribuzione salvati come modelli. Puoi utilizzare i modelli per creare i piani. Puoi riportare i modelli ai piani di distribuzione.  
</li>
</ul>

## Utilizzo del calendario
{: #events_calendarManage}

Puoi filtrare l'elenco **Activities** selezionando le icone evento nel calendario. Le icone evento sono progettate per categoria, il che rende più semplice dire quale categoria rappresenti. Le categorie dell'evento sono descritte nel seguente elenco:

<ul>
<li>Gli eventi della release sono rappresentati da cerchi con colore a tinta unita <img class="inline" src="images/event-icon-release.png"  alt="Icona evento release">.</li>
<li>I black out e gli eventi di manutenzione sono rappresentati da cerchi con contorni colorati <img class="inline" src="images/event-icon-window.png"  alt="Impostazioni calendario">.</li></li>
<li>Gli eventi di festività sono rappresentati da simboli come un ombrello colorati sopra la data <img class="inline" src="images/event-icon-holiday.png"  alt="Impostazioni calendario">.</li>
</ul>

Nella seguente figura, l'evento della release colorato di verde è pianificato da domenica a martedì. L'evento della release colorato di blu è pianificato per mercoledì. L'evento di manutenzione è pianificato da giovedì a sabato. L'evento di festività è pianificato per la seconda domenica.

![](images/event-icon-styles2.png "Stili icona evento predefiniti")

Figura 1. Stili icona evento predefiniti

Per filtrare l'elenco **Activities**, completa una delle seguenti azioni:

<ul>
<li>Fai clic su una data.</li>
<li>Seleziona un intervallo di date. Puoi selezionare un intervallo di date facendo clic su una data e quindi facendo clic tenendo premuto il tasto Maiusc su un'altra data. </li>
</ul>

Vengono visualizzate le release, gli eventi e le distribuzioni pianificate per le date selezionate. Se una data ha più di un evento calendario pianificato, la data viene sottolineata <img class="inline" src="images/event-icon-twoIcons.png"  alt="Impostazioni calendario">.

## Creazione di tipi di evento 
{: #events_eventTypeCreate}

In aggiunta ai tipi di evento predefiniti, puoi creare tipi di evento per qualsiasi categoria evento.

Quando crei un tipo di evento, vengono automaticamente applicati gli stili grafici all'icona associata. Puoi modificare lo stile dell'icona dopo aver creato un evento. 

Per creare un evento, completa la seguente procedura:

1. Nella pagina Releases, fai clic su **Calendar settings** <img class="inline" src="images/cal-set.png"  alt="Impostazioni calendario">.

1. Nella pagina Configure calendar, fai clic su **Add event type** <img class="inline" src="images/event-add.png"  alt="Aggiungi tipo evento"> per la categoria dell'evento che desideri creare.

3. Nella casella di testo, immetti un nome per l'evento. 

3. Fai clic su **Save**. Puoi modificare ed eliminare le tag evento. 

## Gestione dei tipi di evento
{: #events_eventEdit}

Per impostazione predefinita, gli stili dell'icona evento vengono applicati automaticamente e in modo casuale a secondo della categoria. 

Nella seguente illustrazione, gli stili nelle prime due righe sono applicati agli eventi nella categoria degli eventi della release; gli stili nella terza riga sono applicati agli eventi di manutenzione e di black out; gli stili nella quarta riga sono applicati alle festività.

![](images/event-styles.png "Piano di distribuzione tipico")

Figura 2. Stili icona evento

Per modificare uno stile del tipo di evento, completa la seguente procedura: 

1. Nella pagina Releases, fai clic su **Calendar settings**.

2. Nella pagina Configure calendar, fai clic sull'icona **Edit** accanto all'icona evento che desideri modificare e quindi fai clic su **More**.

3. Seleziona uno stile. Puoi selezionare qualsiasi stile indipendentemente dalla categoria. 

Per modificare un nome del tipo di evento, fai clic sull'icona **Edit** accanto al nome del tipo di evento e quindi modifica il nome.

Per eliminare un tipo di evento, fai clic sull'icona **Delete** accanto al nome.

## Importazione di release e eventi
{: #events_importing}

Puoi importare i tuoi propri eventi e release.  Per importare gli elementi, definiscili in un file CSV (comma-separated values). Il formato file CSV è un formato standard utilizzato per scambiare i dati tra le applicazioni. Nei file CSV, ogni campo in un record viene separato da virgole e ogni record è su una riga separata. Utilizza il seguente formato per definire gli eventi e le release:  

`name*,description,start*,end,team*,tag`

I seguenti campi sono obbligatori:

`name,start,team`

Ad esempio, `Holiday,New Years Day,1/1/18,1/1/18,my_team,National Holiday` 

Per importare gli eventi e le release, completa queste istruzioni: 

1. Nella pagina Releases, fai clic su **Import** <img class="inline" src="images/import-events.png"  alt="Importa eventi">.

2. Nella finestra di dialogo Import from CSV, seleziona il file CSV che contiene i tuoi eventi e release e quindi fai clic su **Import Events**. La finestra di dialogo fornisce un link da cui puoi scaricare un file evento CSV di esempio.

Se l'importazione ha esito positivo, le release e gli eventi vengono visualizzati nella pagina Releases. Se il valore nel campo **tag** contiene un tipo di evento precedentemente definito, l'evento viene visualizzato nel calendario. Altrimenti, il valore nel campo **tag** viene trattato come una tag.

## Creazione di tag
{: #events_tagManage}

[Crei le tag nella pagina Create Release quando crei o modifichi una release.](UCCR_releases.html#releases_create) Le tag sono visualizzate nella pagina Releases insieme alla release proprietaria. Sebbene le tag non vengono visualizzate nel calendario, puoi utilizzarle per filtrare gli elementi visualizzati nella pagina Releases.
