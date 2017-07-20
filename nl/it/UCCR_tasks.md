---

copyright:
  years: 2017
lastupdated: "2017-6-22"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}

# Gestione delle attività
{: #tasks_overview}

Un'attività rappresenta un'attività significativa di business associata a una distribuzione software. Le attività sono definite nei piani di distribuzione.

{:shortdesc}

Molte attività hanno un punto di avvio e di fine e una durata misurabile.  Un'attività può essere di uno dei seguenti tipi:

<ul>
<li>Un'attività **Manuale** può rappresentare qualsiasi attività associata a una distribuzione software, come il rendere un server offline o aggiornare un database.</li>
<li>Un'attività **UrbanCode Deploy** rappresenta un'applicazione IBM&reg; UrbanCode&reg; Deploy. Puoi eseguire le applicazioni UrbanCode Deploy con questo tipo di attività.</li>
<li>Un'attività **Continuous Delivery pipeline** rappresenta una pipeline {{site.data.keyword.contdelivery_full}}. Puoi gestire le tue pipeline {{site.data.keyword.contdelivery_short}} con questo tipo di attività.</li>
<li>Un'attività **Ritardata** rappresenta un evento critico che si verifica in un momento specifico.</li>
<li>Un'attività **Intestazione** è un elemento organizzativo. Ad esempio, potresti utilizzare un'attività intestazione per identificare un gruppo di attività.</li>
<li>Un'attività **Email** invia un messaggio email quando eseguita.</li>
<li>Un'attività **Esecuzione di un altro piano** esegue le distribuzioni di altri piani di distribuzione che partecipano allo stesso evento della release. Questo è un tipo di attività sperimentale.</li>
<l1>Un'attivià **Slack** invia un messaggio a un canale Slack quando eseguita.</l1>
</ul>

Puoi aggiungere le attività ai piani di distribuzione creandole o puoi importare le attività da file CSV che vengono creati da IBM UrbanCode Release o da un'altra applicazione. Puoi anche copiare le attività da altri piani di distribuzione. Consulta [Importazione delle attività](/docs/services/UCCR/UCCR_deployPlan.html#plan_importTasks) per informazioni sul formato del file CSV.

## Creazione di attività
{: #tasks_create}

Quando crei un'attività, selezioni il piano di distribuzione a cui desideri aggiungere l'attività. Per impostazione predefinita, le nuove attività vengono inserite alla fine del piano di distribuzione.  Dopo aver creato un'attività, puoi spostarla o copiarla e incollarla in un altro piano di distribuzione. [Puoi anche creare dipendenze con altre attività](/docs/services/UCCR/UCCR_tasks.html#tasks_dependencies).

Dopo aver salvato un'attività, vengono visualizzate le icone di azione. Utilizzi le icone di azione per modificare lo stato dell'attività durante una distribuzione. Tutte le attività hanno l'icona di azione **Skip**. Le altre icone, come **Start**, vengono visualizzate quando il contesto è appropriato per esse.

![](images/deploy-plan-intro.png "Piano di distribuzione tipico")

Figura 1. Piano di distribuzione di esempio con attività e pulsanti di azione

Ogni attività in un piano di distribuzione è contenuta in una riga separata. Le informazioni che vengono visualizzate per ogni attività sono descritte nella seguente tabella.

### Tabella 1.  Proprietà attività

| Proprietà  | Descrizione  |
| ------------------ | ------------------ |
| Nome               |Nome attività       |
| Tipo               |Tipo di attività: manuale, UrbanCode Deploy, ritardata, intestazione |             
| Stato             |Stato dell'attività: non avviato, completo, non riuscito, ignorato, non applicabile |
| Proprietario              |La persona a cui è assegnata l'attività                                                        |
| Ora di inizio  |L'ora di inizio corretta o prevista basata sull'avvio pianificato o la durata stimata di altre attività        |
| Ora di fine               |L'ora in cui è stata risolta l'attività        |
| Durata               |La durata dall'avvio alla risoluzione dell'attività (tempo calcolato in minuti)        |
| Dipendenze               |Indica il numero di attività prerequisite e dipendenti dall'attività        |

---
Dopo aver aggiunto le attività ai piani di distribuzione, puoi gestirle in diversi modi.

Per spostare un'attività, fai clic in un qualsiasi punto sull'attività e trascinala in una nuova posizione.

Per copiare un'attività o un gruppo, selezionare l'attività e fai clic su **Copy** <img class="inline" src="images/copy-group.png"  alt="pulsante copia"> e quindi posiziona il cursore dove desideri inserire l'attività copiata e fai clic su **Paste** <img class="inline" src="images/paste-group.png"  alt="pulsante incolla">.

Per tagliare un'attività o un gruppo da un piano di distribuzione, seleziona l'attività e fai clic su **Cut** <img class="inline" src="images/cut-group.png"  alt="pulsante taglia">.

Per eliminare un'attività, selezionala e fai clic su **Delete** <img class="inline" src="images/trash-group.png"  alt="pulsante elimina">. L'attività viene rimossa dal piano di distribuzione.

## Creazione di attività UrbanCode Deploy
{: #tasks_UDTasks}

Le attività UrbanCode Deploy gestiscono le applicazioni UrbanCode Deploy. Quando esegui un'attività UrbanCode Deploy, l'applicazione UrbanCode Deploy associata viene eseguita utilizzando il processo, la versione e l'ambiente specificati dall'attività. Puoi impostare la versione e l'ambiente in fase di progettazione o attendere e selezionarli al runtime.

Durante le distribuzioni, le attività UrbanCode Deploy vengono avviate automaticamente quando diventano eleggibili per l'esecuzione.   

**Importante** le applicazioni diventano disponibili dopo che {{site.data.keyword.uccr_short}} viene integrato con UrbanCode Deploy. Le applicazioni disponibili per un piano di distribuzione dipendono dal team assegnato al piano. Le applicazioni gestite dal team in UrbanCode Deploy sono anche disponibili in {{site.data.keyword.uccr_short}}.

Completa le seguenti attività per creare un'attività UrbanCode Deploy.

1. Nella pagina Deployment Plan Details, fai clic su **Create Task**. Se desideri inserire un'attività in una posizione specifica nel piano, seleziona un'attività prima di utilizzare **Create Task**. La nuova attività viene inserita sopra l'attività selezionata.

1. Nella finestra di dialogo Create Task, nell'elenco **Type**, seleziona **UrbanCode Deploy**.

1. Nel campo **Name**, immetti un nome per l'attività.

3. Nel campo **Duration (minutes)**, immetti il numero di minuti che prevedi servano per l'esecuzione dell'attività fino al completamento. La durata stimata viene utilizzata per calcolare i tempi di distribuzione previsti.

3. Nell'elenco **Tags**, allega una tag all'attività. Puoi selezionare più tag. Per creare una tag, immettine il nome nel campo di testo dell'elenco.

3. Nell'elenco **Application Name**, seleziona un'applicazione.

3. Nell'elenco **Process**, seleziona un processo dell'applicazione. I processi che appartengono all'applicazione UrbanCode Deploy selezionata sono disponibili.

3. Nell'elenco **Environment**, seleziona un ambiente dell'applicazione. Gli ambienti che appartengono all'applicazione UrbanCode Deploy selezionata sono disponibili.  Per posticipare la selezione di un ambiente finché non sei pronto ad eseguire la distribuzione, seleziona **Use Version Tab**.

3. Nell'elenco **Version**, seleziona una versione dell'applicazione. Le versioni fanno riferimento alle istantanee dell'applicazione IBM UrbanCode Deploy. Le versioni che appartengono all'applicazione selezionata sono disponibili.  Per posticipare la selezione di una versione, seleziona **Use Version Tab**. Se il processo dell'applicazione non richiede una versione, seleziona **No Version**. Potresti selezionare quest'ultima opzione se stai eseguendo un processo del tipo configurazione che non richiede componenti.

3. Nell'elenco **Assigned groups and users**, assegna l'attività a un utente o gruppo. L'utente assegnato esegue l'attività durante la distribuzione.

3. Nell'elenco **Owner**, seleziona il proprietario dell'attività. Il proprietario predefinito è l'utente che ha creato l'attività. L'elenco **Owner** viene visualizzato dopo che l'attività viene assegnata a un utente o gruppo.    

5. Fai clic su **Save**. L'attività viene inserita nel piano di distribuzione.

Dopo aver creato l'attività, la scheda **Version** del piano viene aggiornata con le informazioni sull'applicazione assegnata all'attività. Se hai selezionato **Use Version Tab** per la versione e l'ambiente dell'applicazione, utilizza la scheda Version per impostare queste opzioni prima di eseguire la distribuzione.

## Creazione di attività manuali
{: #tasks_manual}

Generalmente, le attività manuali rappresentano alcune attività associate a una release software con un punto di avvio e di fine e una durata misurabile.

Completa le seguenti attività per creare un'attività manuale:

1. Nella pagina Deployment Plan Details, fai clic su **Create Task**. Se desideri inserire un'attività in una posizione specifica nel piano, seleziona un'attività prima di utilizzare **Create Task**. La nuova attività viene inserita sopra l'attività selezionata.

1. Nella finestra di dialogo Create Task, nell'elenco **Type**, seleziona **Manual**.

1. Nel campo **Name**, immetti un nome per l'attività.

3. Nel campo **Duration (minutes)**, immetti il numero di minuti che prevedi servano per l'esecuzione dell'attività fino al completamento. La durata stimata viene utilizzata per calcolare i tempi di distribuzione previsti.

3. Nell'elenco **Tags**, allega una tag all'attività. Puoi selezionare più tag. Per creare una tag, immettine il nome nel campo di testo dell'elenco.

3. Nell'elenco **Assigned groups and users**, assegna l'attività a un utente o gruppo. L'utente assegnato esegue l'attività durante la distribuzione.

3. Nell'elenco **Owner**, seleziona il proprietario dell'attività. Il proprietario predefinito è l'utente che ha creato l'attività. L'elenco **Owner** viene visualizzato dopo che l'attività viene assegnata a un utente o gruppo.    

5. Fai clic su **Save**. L'attività viene inserita nel piano di distribuzione.

## Creazione di attività ritardate
{: #tasks_delayed}

Le attività del tipo ritardata rappresentano i punti cardini o gli eventi critici durante una distribuzione. Con le attività ritardate, puoi garantire che le attività importanti vengano avviate all'ora prevista. Generalmente, le attività ritardate sono prerequisite per altre attività importanti.

Un'attività ritardata si avvia come diventa eleggibile per l'esecuzione e finisce all'ora specificata dall'utente. Un'attività del tipo ritardata avviata ha uno stato di `In Progress` finché non raggiunge la propria ora pianificata, in cui modifica il proprio stato in `Complete`. Quando le attività ritardate vengono completate, le attività automatiche dipendenti da esse iniziano l'esecuzione.

Completa le seguenti attività per creare un'attività ritardata:

1. Nella pagina Deployment Plan Details, fai clic su **Create Task**. Se desideri inserire un'attività in una posizione specifica nel piano, seleziona un'attività prima di utilizzare **Create Task**. La nuova attività viene inserita sopra l'attività selezionata.

1. Nella finestra di dialogo Create Task, nell'elenco **Type**, seleziona **Delayed**.

1. Nel campo **Name**, immetti un nome per l'attività.

3. Nel campo **Time**, immetti o seleziona l'ora in cui l'attività verrà completata.

3. Nell'elenco **Time Zone**, seleziona il fuso orario per il valore immesso nel campo **Time**.    

5. Fai clic su **Save**. L'attività viene inserita nel piano di distribuzione.

## Creazione di attività di intestazione
{: #tasks_header}

Le attività di intestazione rappresentano gli elementi organizzativi che puoi aggiungere ai piani di distribuzione. Se crei un gruppo di attività, potresti identificarlo con un'attività di intestazione. Le attività di intestazione possono avere dipendenze come qualsiasi altra attività.

Quando importi un piano di distribuzione dalla release IBM UrbanCode, le attività del segmento sono inserite tra parentesi per le attività Start Segment e End Segment del tipo di nota. Le dipendenze del segmento vengono rappresentate dalle dipendenze alle attività End Segment.

Per creare un'attività di intestazione, completa la seguente procedura:

1. Nella pagina Deployment Plan Details, fai clic su **Create Task**. Se desideri inserire un'attività in una posizione specifica nel piano, seleziona un'attività prima di utilizzare **Create Task**. La nuova attività viene inserita sopra l'attività selezionata.

1. Nella finestra di dialogo Create Task, nell'elenco **Type**, seleziona **Header**.

1. Nel campo **Name**, immetti un nome per l'attività. Il nome potrebbe rappresentare un nome del gruppo di attività.

3. Nel campo **Description**, immetti o incolla una descrizione. Nel campo potresti inserire una nota, un promemoria o altre istruzioni.

5. Fai clic su **Save**. L'attività viene inserita nel piano di distribuzione.

## Creazione di attività della pipeline Continuous Delivery
{: #tasks_pipelineCD}

Le pipeline {{site.data.keyword.contdelivery_full}} automatizzano i tuoi flussi di lavoro DevOps. Una pipeline è una sequenza di fasi che richiamano l'input ed eseguono i lavori. Puoi gestire le tue pipeline {{site.data.keyword.contdelivery_short}} con le attività pipeline. Le attività pipeline Continuous Delivery sono attività automatiche e vengono eseguite come diventano eleggibili.

Per creare un'attività pipeline Continuous Delivery, completa la seguente procedura:

1. Nella pagina Deployment Plan Details, fai clic su **Create Task**. Se desideri inserire un'attività in una posizione specifica nel piano, seleziona un'attività prima di utilizzare l'azione **Create Task**. La nuova attività viene inserita prima dell'attività selezionata.

1. Nella finestra di dialogo Create Task, nell'elenco **Type**, seleziona **Continuous Delivery Pipeline**.

1. Nel campo **Name**, immetti un nome per l'attività.

3. Nel campo **Description**, immetti o incolla una descrizione. Nel campo potresti inserire una nota, un promemoria o altre istruzioni.

3. Nel campo **Pipeline**, immetti o seleziona la pipeline.

3. Nel campo **Stage Name**, immetti o seleziona il nome della fase. Le fasi definite per la pipeline selezionata sono disponibili.

3. Nell'elenco **Tags**, allega una tag all'attività. Puoi selezionare più tag. Per creare una tag, immettine il nome nel campo di testo dell'elenco.

3. Nell'elenco **Assigned groups and users**, assegna l'attività a un utente o gruppo. L'utente assegnato esegue l'attività durante la distribuzione.

3. Nell'elenco **Owner**, seleziona il proprietario dell'attività. Il proprietario predefinito è l'utente che ha creato l'attività. L'elenco **Owner** viene visualizzato dopo che l'attività viene assegnata a un utente o gruppo.    

5. Fai clic su **Save**. L'attività viene inserita nel piano di distribuzione.

Quando un'attività pipeline Continuous Delivery è in esecuzione, esegue i lavori nella fase specificata per la pipeline selezionata.

## Creazione di attività email
{: #tasks_email}

Un'attività email invia un messaggio email quando l'attività viene eseguita. Specifichi il messaggio e i destinatari dell'email quando crei l'attività. Le attività email sono attività automatiche e vengono eseguite come diventano eleggibili.

Per creare un'attività email, completa la seguente procedura:

1. Nella pagina Deployment Plan Details, fai clic su **Create Task**. Se desideri inserire un'attività in una posizione specifica nel piano, seleziona un'attività prima di utilizzare l'azione **Create Task**. La nuova attività viene inserita prima dell'attività selezionata.

1. Nella finestra di dialogo Create Task, nell'elenco **Type**, seleziona **Email**.

1. Nel campo **Name**, immetti un nome per l'attività.

3. Nel campo **Recipients**, immetti o seleziona il destinatario dell'email. L'elenco dei destinatari disponibili include gli utenti e i gruppi membri del tuo team. Puoi anche digitare gli indirizzi email di membri non del team. Puoi specificare più destinatari. 

3. Nel campo **Email subject**, immetti l'argomento dell'email.

3. Nel campo **Email message**, immetti o incolla il messaggio dell'email.

5. Fai clic su **Save**. L'attività viene inserita nel piano di distribuzione.

Quando l'attività viene eseguita, i destinatari ricevono un'email da **IBM Continuous Release** con l'oggetto che hai specificato quando hai creato l'attività.

## Creazione di attività di esecuzione di un altro piano
{: #tasks_runAnother}

Un'attività di esecuzione di un altro piano esegue una distribuzione per un altro piano di distribuzione. Il piano di destinazione deve essere creato da un modello. Sia il modello che il piano di destinazione devono essere nella stessa release del piano con l'attività di esecuzione di un altro piano.

Tieni presente che questo è un tipo di attività sperimentale. 

Per creare un'attività di esecuzione di un altro piano, completa la seguente procedura: 

1. Nella pagina Deployment Plan Details, fai clic su **Create Task**. Se desideri inserire un'attività in una posizione specifica nel piano, seleziona un'attività prima di utilizzare l'azione **Create Task**. La nuova attività viene inserita prima dell'attività selezionata.

1. Nella finestra di dialogo Create Task, nell'elenco **Type**, seleziona **Run Another Plan**.

1. Nel campo **Name**, immetti un nome per l'attività.

3. Nell'elenco **Plan Template Name**, seleziona un modello del piano di distribuzione. Il modello deve essere nello stesso evento della release del piano principale dell'attività.

3. Nell'elenco **Tags**, allega una tag all'attività. Puoi selezionare più tag. Per creare una tag, immettine il nome nella casella di testo. 

5. Fai clic su **Save**. L'attività viene inserita nel piano di distribuzione.

Quando l'attività viene eseguita, viene avviata una distribuzione per il piano di distribuzione creato dal modello selezionato e nello stesso evento della release. Se vengono creati più piani nell'evento della release dal modello, le distribuzioni vengono avviate per ognuno di essi. Mentre vengono eseguite le altre distribuzioni, vengono fornite le informazioni sullo stato dall'attività di esecuzione di un altro piano. Espandi l'attività per visualizzare le informazioni sullo stato. Puoi aprire le altre distribuzioni utilizzando i link nell'attività. Mentre vengono eseguite le altre distribuzioni, l'attività di esecuzione di un altro piano ha uno stato di **In Progress**.

## Creazione di attività Slack
{: #tasks_slack}

Un'attivià Slack invia un messaggio a un canale Slack quando eseguita. Il messaggio può contenere testo e collegamenti ipertestuali. Un'attività Slack si avvia come diventa eleggibile per l'esecuzione. 

Per creare un'attività Slack, completa la seguente procedura: 

1. Nella pagina Deployment Plan Details, fai clic su **Create Task**. Se desideri inserire un'attività in una posizione specifica nel piano, seleziona un'attività prima di utilizzare l'azione **Create Task**. La nuova attività viene inserita prima dell'attività selezionata.

1. Nella finestra di dialogo Create Task, nell'elenco **Type**, seleziona **Slack**.

1. Nel campo **Name**, immetti un nome per l'attività.

3. Nel campo **Webhook URL**, immetti l'URL del canale Slack in cui desideri venga consegnato il messaggio, ad esempio, `https://hooks.slack.com/services/my_webhook`.

3. Nella casella **Message**, immetti il corpo del messaggio.  Il messaggio può contenere testo e collegamenti ipertestuali. 

3. Nel campo **Duration (minutes)**, immetti il numero di minuti che prevedi servano per l'esecuzione dell'attività fino al completamento. La durata stimata viene utilizzata per calcolare i tempi di distribuzione previsti.

3. Nell'elenco **Tags**, allega una tag all'attività. Puoi selezionare più tag. Per creare una tag, immettine il nome nella casella di testo. 

3. Nell'elenco **Assigned groups and users**, assegna l'attività a un utente o gruppo. L'utente assegnato esegue l'attività durante la distribuzione.

5. Fai clic su **Save**. L'attività viene inserita nel piano di distribuzione.

Quando viene eseguita l'attività, il messaggio definito nel campo Message viene inviato al canale Slack specificato nel campo Webhook URL.

## Gestione dei gruppi di attività
{: #tasks_groups}

Puoi combinare due o più attività in un gruppo di attività. Quando crei un gruppo, definisci il modello di esecuzione del gruppo, se sequenziale o parallela. Puoi eseguire le attività in un gruppo con il modello parallelo in qualsiasi ordine e, a meno che siano presenti delle dipendenze, simultaneamente. Le attività nei gruppi sequenziali vengono eseguite in ordine di elenco iniziando con la prima o con l'attività più in alto.  

Puoi integrare i gruppi in altri gruppi. Puoi integrare un gruppo con modello sequenziale in un gruppo con modello parallelo e viceversa. Tuttavia, non puoi integrare un gruppo di modello sequenziale in un altro gruppo sequenziale o un gruppo con modello parallelo in un altro gruppo parallelo.   

Completa le seguenti istruzioni per creare un gruppo di attività. 

1. Nella pagina Deployment Plan Detail, seleziona due o più attività.

1. A seconda del tipo di gruppo che vuoi creare, completa uno dei seguenti passi. 

  <ul>
  <li>Per creare un gruppo parallelo, fai clic sul pulsante **Parallel** <img class="inline" src="images/para-icon.png"  alt="pulsante gruppo parallelo">. Se non puoi creare un gruppo parallelo con le attività selezionate, il pulsante è disabilitato. Potresti non essere in grado di creare un gruppo parallelo se tutte le attività selezionate sono già in un gruppo parallelo, ad esempio.
  </li>
  <li>Per creare un gruppo sequenziale, fai clic sul pulsante **Sequential** <img class="inline" src="images/seq-icon.png"  alt="pulsante gruppo sequenziale">.
  </li>
  </ul>

Il gruppo viene creato e una **barra di selezione gruppo** viene aggiunta al piano di distribuzione. Se hai selezionato attività discontinue, le attività creano un elenco continuo partendo con l'attività selezionata più in alto.

La seguente figura mostra un gruppo parallelo. La **barra di selezione gruppo** identifica il tipo di gruppo: parallelo <img class="inline" src="images/para-select.png"  alt="selezione gruppo parallelo"> o sequenziale <img class="inline" src="images/seq-select.png"  alt="selezione gruppo sequenziale">.

![](images/group-select.png "Piano di distribuzione tipico")

Figura 2. Gruppo parallelo

Per spostare un gruppo, seleziona la **barra di selezione gruppo** o fai clic in un qualsiasi punto sul gruppo e trascinalo in una nuova posizione.

Per copiare un gruppo, selezionalo e fai clic su **Copy** <img class="inline" src="images/copy-group.png"  alt="pulsante copia"> e quindi posiziona il cursore dove desideri inserire il gruppo copiato e fai clic su **Paste** <img class="inline" src="images/paste-group.png"  alt="pulsante incolla">.

Per tagliare un gruppo, selezionalo e fai clic su **Cut** <img class="inline" src="images/cut-group.png"  alt="pulsante taglia">.

Per annullare un gruppo, selezionalo e fai clic sull'icona **Ungroup** <img class="inline" src="images/ungroup-icon.png"  alt="icona annulla gruppo"> nella **barra di selezione gruppo**.

Per eliminare le attività in un gruppo, seleziona il gruppo e fai clic su **Delete** <img class="inline" src="images/trash-group.png"  alt="pulsante elimina">. Le attività vengono rimosse dal piano di distribuzione.

## Gestione delle tag dell'attività
{: #tasks_tags}

Le tag sono elementi organizzativi che puoi aggiungere alle attività. Puoi filtrare i piani di distribuzione per tag. Ad esempio, durante una distribuzione a un ambiente di produzione, potresti disabilitare le attività con la tag `DEV_only`, pensata per essere utilizzata solo negli ambienti di sviluppo.

Per aggiungere una tag a un'attività, completa la seguente procedura.

1. Nella pagina Deployment Plan Details, seleziona un'attività o un gruppo di attività e fai quindi clic su **Manage Tags**  <img class="inline" src="images/task-tag.png"  alt="gestisci tag">. Puoi selezionare più attività e gruppi. 

1. Nella finestra di dialogo Manage Tags for Selected Tasks, nell'elenco **Common Tags**, seleziona le tag. Puoi creare una nuova tag immettendo un nome nella casella di testo dell'elenco.

1. Fai clic su **Save**.

Le tag vengono visualizzate nelle righe dell'attività nella pagina Deployment Plan Detail. Nella seguente figura, l'attività **Deploy WAR** ha due tag assegnate ad essa, `Deployment` e `Critical`.

Le tag utilizzate da un piano di distribuzione vengono visualizzate nella scheda **Versions** della pagina Deployment Plan Detail. Per restituire le attività con una tag specificata `Not Applicable` per una distribuzione, cancellare la tag. Le attività con lo stato `Not Applicable` non possono essere avviate.  

![](images/task-tag-labels.png "Piano di distribuzione tipico")

Figura 3. Dipendenze dell'attività

## Creazione delle dipendenze dell'attività
{: #tasks_dependencies}

Puoi rendere un'attività un prerequisito di altre attività. Se un'attività è un prerequisito, le attività dipendenti non possono essere avviate, anche se sono eleggibili, finché l'attività prerequisita non viene risolta.

Un'attività può avere più attività dipendenti e prerequisite. Puoi definire le dipendenze per un'attività con qualsiasi altra attività nel piano di distribuzione. Tuttavia, non puoi creare dipendenze circolari. Non puoi, ad esempio, rendere un'attività dipendente da un'attività che a sua volta dipende dalla prima attività.

Controllando le dipendenze dell'attività, puoi assicurarti che gli eventi si verifichino nel loro ordine previsto.

Per rendere un'attività un prerequisito di altre attività, completa la seguente procedura:

1. Nella pagina Deployment Plan Details, seleziona un'attività o un gruppo di attività e fai quindi clic su **Manage Prerequisites** <img class="inline" src="images/task-depend.png"  alt="prerequisito attività">. Puoi selezionare più attività e gruppi. 

1. Nella finestra di dialogo Manage Prerequisites for Selected Tasks, nell'elenco **Prerequisite tasks for selected tasks**, seleziona l'attività prerequisita.

1. Fai clic su **Save**.

Le dipendenze dell'attività sono mostrate nella colonna **Dependencies** nella pagina Deployment Plan Detail. Le frecce verso l'alto indicano i prerequisiti dell'attività; le frecce verso il basso le dipendenze dell'attività.

Nella seguente figura, la prima attività non ha alcun prerequisito e ha due attività dipendenti da essa.  La seconda attività ha una attività prerequisita e non ha attività dipendenti da essa.

(![](images/plan-w-depend.png "Piano di distribuzione tipico"))

Figura 4. Dipendenze dell'attività

Per rivedere o modificare le dipendenze, seleziona l'attività e fai quindi clic su  **Manage Prerequisites** <img class="inline" src="images/task-depend.png"  alt="prerequisito attività">. Utilizza la finestra di dialogo Manage Prerequisites for Selected Tasks per modificare o rimuovere le dipendenze. 
