---

copyright:
 years: 2017
lastupdated: "2017-6-22"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}

# Informazioni sulle release
{: #releases_overview}

Una release è un contenitore per i piani di distribuzione, gli eventi e le tag. 

{:shortdesc}

Generalmente, una release contiene i piani di distribuzione e gli eventi che sono collegati in qualche modo significativamente al business. Ad esempio, i piani di distribuzione potrebbe rappresentare le fasi in un ciclo di sviluppo software, come sviluppo, QA e produzione. Un evento potrebbe rappresentare un blackout che interessa la release.

Se aggiungi eventi a una release, puoi utilizzare il calendario per filtrare la pagina Releases in modo che visualizzi le release e i piani di distribuzione.

## Creazione delle release
{: #releases_create}

Per creare una release, completa la seguente procedura:

1. Nella pagina Releases, fai clic su **Create release**.

1. Nella finestra Create release, nel campo **Name**, immetti un nome per la release. Un nome è obbligatorio.

3. Nell'elenco **Team**, seleziona un team per gestire la release. Puoi aggiungere i piani di distribuzione da altri team all'evento della release, non solo dal team di proprietà del team che gestisce la release. Tutti i team a cui appartieni sono disponibili. Un team è obbligatorio.

3. Nel campo **Start Time**, seleziona una data e ora di avvio. Le ore di avvio sono obbligatorie per tutte le release.

3. Nel campo **End Time**, seleziona la data e l'ora di fine.

3. Nell'elenco **Tags**, seleziona un evento o una tag. Puoi selezionare più elementi.  Se desideri che l'evento sia visualizzato nel calendario, [seleziona un evento creato nella pagina Configure Calendar](UCCR_events.html#events_tagCreate).

1. Facoltativamente, puoi creare una tag immettendo il nome della tag nel campo **Tags**. Le tag che crei con la finestra Create release non sono visualizzate nel calendario, per evitare i messaggi secondari del calendario.

5. Fai clic su **Save**.

Per visualizzare la release nell'elenco Activities, assicurati che l'intervallo di date includa le date nelle ore di avvio e di fine della release.  

Dopo avere creato la release, puoi aggiungervi i piani di distribuzione, gli eventi e le tag.

## Aggiunta dei piani di distribuzione a una release 
{: #releases_planAdd}

Puoi aggiungere i piani di distribuzione esistenti a una release o crearne di nuovi. 

Per aggiungere i piani di distribuzione esistenti a una release, completa la seguente procedura: 

1. Nella pagina Releases, seleziona la release. 

1. Nella pagina Release Detail, fai clic su **Create deployment plan**.

1. Nella finestra Add Plan, seleziona i piani che desideri aggiungere alla release. Vengono elencati i piani pianificati che appartengono ai tuoi team.

3. Fai clic su **Save**.

[Per creare un piano](UCCR_deployPlan.html#plan_create), fai clic su **Create Deployment Plan**. I piani creati con la pagina Release detail vengono automaticamente assegnati alla release. Quando crei un piano di distribuzione indipendente da una release, puoi selezionare la release a cui desideri aggiungere il piano.

## Gestione delle release
{: #releases_manage}

La pagina Release Detail visualizza i piani di distribuzione che appartengono alla release. Per gestire una release o i piani di distribuzione che appartengono ad essa, apri la pagina Release Detail e completa una delle seguenti attività:
<ul>
<li>Fai clic su **Edit** per modificare la definizione della release. Con questa opzione, puoi aggiungere eventi e tag all'evento della release.
</li>
<li>Seleziona **Edit this plan** per modificare un piano di distribuzione. Viene visualizzata la finestra Edit Deployment Plan.
</li>
<li>Seleziona **Reschedule this plan** per modificare le ore di avvio e di fine pianificate.
</li>
<li>Seleziona **Copy this plan** per copiare un piano di distribuzione. Una copia del piano selezionato viene aggiunta alla release.</li>
<li>Seleziona **Remove from release** per rimuovere il piano di distribuzione dalla release. I piani rimossi da una release non vengono eliminati e possono essere aggiunti a un'altra release.
</li>
</li>
<li>Seleziona **Archive this plan** per spostare il piano di distribuzione nell'archivio. I piani archiviati possono essere ripristinati.
</li>
</ul>

Per avviare una distribuzione, [consulta Esecuzione delle distribuzioni.](UCCR_deployRun.html#deployment_run)

## Archivio e ripristino delle release
{: #releases_archiveRelease}

Anche se non puoi eliminare una release, puoi archiviarla nell'archivio. Le release archiviate non vengono visualizzate nella pagina Releases.

Per archiviare una release, completa la seguente procedura:

1. Nella pagina Releases, seleziona l'azione **Archive** per la release.

1. Nella finestra Archive release event, determina quale piano di distribuzione archiviare selezionando una delle seguenti opzioni:
<ul>
<li>Seleziona **Archive all deployment plans** per archiviare la release e tutti i piani di distribuzione indipendentemente dal loro stato.</li>
<li>Seleziona **Archive completed deployment plans only** per archiviare la release e solo i piani di distribuzione con lo stato di Complete. I piani di distribuzione con altri stati non vengono archiviati e mantengono il loro stato corrente.</li>
</ul>

3. Fai clic su **Archive**.

Per ripristinare una release archiviata, completa queste istruzioni:

1. Nella pagina Releases, fai clic su **Archived**.

2. Nell'elenco delle release archiviate, fai clic sull'azione **Restore** per la release.

Una release ripristinata conserva tutti i suoi piani di distribuzione originali.
