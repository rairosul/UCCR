---

copyright:
 years: 2017
lastupdated: "2017-6-22"

---


<!-- Common attributes used in the template are defined as follows: -->
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}

# Gestione dei piani di distribuzione 
{: #plan_overview}

Un piano di distribuzione è un contenitore per le attività. Le attività definiscono le attività che il tuo team esegue per completare una distribuzione software.

{:shortdesc}

Crea un piano di distribuzione assegnando un team per gestirlo e poi aggiungendo le attività al piano. I membri del team aggiungono le attività al piano e le eseguono durante le distribuzioni. Il team di gestione determina inoltre quali applicazioni IBM UrbanCode Deploy sono disponibili. Dopo aver configurato un'integrazione con DevOps Connect, tutte le applicazioni gestite dal team in IBM UrbanCode Deploy sono disponibili in {{site.data.keyword.uccr_short}}.  

Le attività definiscono le attività che il team esegue per completare una distribuzione. Puoi creare nuove attività, copiare le attività da altri piani di distribuzione o importare le attività dai file CSV. Quando sei soddisfatto del piano, puoi pianificare una distribuzione. Puoi inoltre eseguire una distribuzione in qualsiasi momento avviando una delle attività del piano.

Le attività sono visualizzate su righe individuali nei piani di distribuzione. Ogni riga contiene informazioni che identificano l'attività e ne forniscono lo stato. Ogni riga contiene inoltre le icone azione utilizzate durante le distribuzioni, come l'attività **Start** o **Skip** 

Per impostazione predefinita, le attività sono eseguite in modo sequenziale iniziando dalla prima attività, o dall'attività in primo piano, nel piano. Dopo il completamento della prima attività, la seconda è eleggibile per l'esecuzione e così via. L'ordine in cui le attività sono eleggibili per l'esecuzione viene denominato l'ordine di esecuzione.

L'ordine di esecuzione può essere modificato combinando le attività in gruppi. [Quando crei un gruppo](/docs/services/UCCR/UCCR_tasks.html#tasks_groups), imposti il modello di esecuzione del gruppo, che può essere sequenziale o parallelo. Se un gruppo ha un modello di esecuzione sequenziale, le sue attività vengono eseguite in sequenza iniziando dalla prima attività. Il modello di esecuzione predefinito di un piano di distribuzione è sequenziale. Se un gruppo ha un modello di esecuzione parallela, le attività nel gruppo possono essere avviate in qualsiasi ordine e possono essere eseguite simultaneamente. Se un piano è formato solo da attività parallele, puoi avviare qualsiasi attività indipendentemente dalla sua posizione nell'elenco.

L'eleggibilità dell'attività può anche essere influenzata dalle dipendenze dell'attività. [Se un'attività ha dei prerequisiti](/docs/services/UCCR/UCCR_tasks.html#tasks_dependencies), non può essere avviata, anche se eleggibile, finché non sono risolte tutte le attività prerequisite.

Alcune attività si avviano automaticamente come diventano eleggibili per l'esecuzione, mentre altre attività vengono avviate manualmente. Se un'attività si avvia automaticamente o meno dipende dal suo tipo. Le attività manuali, come implica il nome, vengono avviate manualmente. Le attività UrbanCode Deploy e del tipo ritardato si avviano automaticamente come diventano eleggibili.

Le attività eleggibili visualizzano un pulsante **Start Task**. Per avviare una distribuzione, avvia una delle attività eleggibili del piano. Le distribuzioni pianificate si avviano automaticamente nell'ora pianificata se un'attività eleggibile è di un tipo che si avvia automaticamente, come UrbanCode Deploy.

## Creazione dei piani di distribuzione
{: #plan_create}
Puoi iniziare con un piano vuoto senza attività definite o puoi copiare un piano esistente. Puoi anche iniziare con un modello del piano.  Quando copi un piano o utilizzi un modello, molte attività sono già definite.

Completa le seguenti istruzioni per creare un piano di distribuzione:

1. Nella pagina Releases o Release Detail, fai clic su **Create Deployment Plan**.

2. Nella finestra Create Deployment Plan, nell'elenco **Template**, specifica il modello su cui desideri basare il piano. Il valore predefinito è **None**. 

2. Nel campo **Plan name**, immetti il nome del piano.

3. Nell'elenco **Team**, seleziona un team per gestire il piano. Sono disponibili tutti i team di cui sei membro. I membri del team possono modificare il piano e gestire le attività. Le applicazioni UrbanCode Deploy gestite dal team in UrbanCode Deploy sono disponibili per assegnare le attività del tipo UrbanCode Deploy.

4. Per pianificare una distribuzione per un piano, fai clic su **Start time** e seleziona una data e ora per la distribuzione. Le distribuzioni pianificate si avviano automaticamente nell'ora pianificata se il piano contiene attività automatiche eleggibili. Puoi pianificare una distribuzione per un qualsiasi momento successivo.

5. Nell'elenco **Release**, seleziona la release a cui desideri aggiungere il piano. Le release che appartengono a uno dei tuoi team sono disponibili. Se selezioni una release, il piano di distribuzione viene visualizzato nella pagina Release Detail.

6. Fai clic su **Save**. Se hai creato il piano in una pagina Release Detail, il piano è parte della release selezionata.

Dopo aver salvato il piano, fai clic su **Edit** per modificare i dettagli del piano.

## Importazione delle attività nei piani di distribuzione.
{: #plan_importTasks}

Puoi importare le attività definite nei file CSV (comma-separated values) in un piano di distribuzione. Puoi utilizzare i file CSV esportati dalla release IBM UrbanCode o da un'altra applicazione capace di creare i file CSV.

**Importante:** quando importi le attività, le attività già definite nel piano di distribuzione vengono sovrascritte e sostituite dalle attività nel file CSV.

Completa le seguenti istruzioni per importare le attività in un piano di distribuzione. 

1. Nella pagina Deployment Plan Details, fai clic su **Import Tasks**.

3. Nella finestra di dialogo Import Tasks, fai clic su **Choose File** e seleziona quindi il file CSV. Puoi anche trascinare un file nel campo **Choose File**.

6. Fai clic su **Import**. Le attività vengono aggiunte al piano di distribuzione. Se il processo di importazione ha esito negativo, fai clic su **View Report** per visualizzare il log degli errori.

Quando importi una piano di distribuzione dalla release IBM UrbanCode, i segmenti sono convertiti in gruppi con lo stesso modello di esecuzione dei segmenti originali. Le attività del segmento sono inserite tra parentesi per le attività Start Segment e End Segment del tipo di nota. Le dipendenze dell'attività sono conservate durante l'importazione. Le dipendenze del segmento vengono rappresentate dalle dipendenze alle attività End Segment.

La seguente tabella contiene i campi che definiscono un'attività in un piano di distribuzione della release IBM UrbanCode. La prima riga nel file CSV contiene le intestazioni di colonna, che corrispondono alla colonna **Field** della tabella. Le righe dopo la prima contengono i dati dell'attività, un'attività per riga. L'ordine delle colonne non è importante.

Per informazioni sui piani di distribuzione esportati dalla release IBM UrbanCode, scarica il file `SamplePlan.csv` dalla finestra di dialogo Import Tasks.

Se stai creando delle attività in un file CSV, devi includere i campi obbligatori identificati dal carattere asterisco (*) nella seguente tabella.

| Campo  | Descrizione  |
| ------------------ |------------------|
|segmentName*                 |Il nome del segmento. Campo obbligatorio.|                                                    
|name*                        |Il nome dell'attività di distribuzione. Campo obbligatorio.|                                                                
|type*                        |Il tipo di attività. I valori possibili sono `note`, `waitfortimetask`, `ucdtask` o `manual`. Durante l'importazione, se il campo contiene un valore non riconosciuto, all'attività viene assegnato il tipo `manual.|
|description                 |La descrizione del piano di distribuzione. |                                                                                                    
|property:processId           |L'ID del processo in IBM UrbanCode Deploy che corrisponde all'attività.|
|property:task-environments   |Gli ambienti dell'applicazione disponibili per l'attività.|
|property:mailRecipients|Gli indirizzi email degli utenti che ricevono i messaggi email quando vengono inviate le notifiche.|
|taskTagNames                 |I nomi delle tag associate all'attività.|
|taskPrequisiteIds         |Un elenco separato da virgole di ID delle attività che devono essere completate prima che questa attività possa essere avviata.|
|segmentPrerequisitelds       |Un elenco separato da virgole di ID dei segmenti con cui il segmento corrente ha delle dipendenze. |
|taskPrequisiteNames         |Un elenco separato da virgole di nomi delle attività che devono essere completate prima che questa attività possa essere avviata. |
|segmentPrerequisiteNames       |Un elenco separato da virgole di nomi dei segmenti con cui il segmento corrente ha delle dipendenze. |
|assignedUserEmail                |L'indirizzo email dell'utente assegnato all'attività corrente.|
|executorGroup                |Il gruppo di utenti assegnato all'attività corrente.|
|segmentPattern                |Il modello di esecuzione del segmento selezionato.|

{: caption="Tabella 1. Campi del piano di distribuzione della release IBM UrbanCode" caption-side="top"}

## Copia e promozione dei piani di distribuzione
{: #plan_copyPromote}

Puoi duplicare i piani di distribuzione promuovendoli o copiandoli. Lo stato di un piano promosso o copiato è `draft` anche se il piano originale ha lo stato di `done` o `in progress`.

Per copiare un piano, utilizza l'azione **Copy this plan** nella pagina Deployment Plan. Quando copi un piano, viene inserito un nuovo piano con il nome "Copy of `plan_name`" nella pagina Deployment Plan. Il piano copiato contiene tutte le attività definite nel piano originale. Se sono presenti nel piano attività UrbanCode Deploy, le applicazioni, le versioni e gli ambienti selezionati nel piano originale sono anche selezionati nel piano copiato. Le applicazioni, le versioni e gli ambienti sono visualizzati nella scheda **Versions** nella pagina Deployment Plan Detail.

Per promuovere un piano, utilizza l'azione **Promote this plan** nella pagina Deployment Plan. Quando promuovi un piano, viene inserito un nuovo piano con il nome "Promotion of `plan_name`" nella pagina Deployment Plan. Il piano promosso contiene tutte le attività definite nel piano originale. Se sono presenti nel piano attività UrbanCode Deploy, le applicazioni e le versioni selezionate nel piano originale sono anche selezionati nel piano copiato. La differenza tra i piani promossi e copiati è che le versioni dell'applicazione non sono configurate nei piani promossi.

## Gestione dei modelli del piano
{: #plan_templates}

Puoi convertire i piani distribuiti per creare i modelli del piano di distribuzione.

Per creare un modello, utilizza l'azione **Template this plan** nella pagina Deployment Plan. Quando crei un modello, viene inserito un nuovo piano con il nome "Copy of plan_name' nella pagina Deployment Plan. Lo stato del modello è `template` anche se il piano originale ha lo stato di `done` o `in progress`. Il modello contiene tutte le attività definite nel piano originale. Se sono presenti nel piano attività UrbanCode Deploy, le applicazioni selezionate nel piano originale sono anche selezionati nel modello. 

Non è possibile eseguire le distribuzioni con i modelli. Per utilizzare un modello per una distribuzione, per prima cosa copialo o promuovilo e utilizza quindi il piano promosso o copiato.

## Archiviazione dei piani di distribuzione
{: #plan_arch}

Quando inserisci un piano nell'archivio, ha lo stato di `Archived` e non viene visualizzato nella pagina Deployment Plan a meno che utilizzi il filtro **Archive**.

I piani di distribuzione nell'archivio possono essere ripristinati nello stato di `draft`. Non è possibile eliminare definitivamente un piano di distribuzione. 

## Annullamento e ripristino
{: #plan_history}

Viene conservata una cronologia delle modifiche per ogni piano di distribuzione. Puoi visualizzare le revisioni nella scheda **Change History** nella pagina Deployment Plan Detail.

Per ripristinare una versione precedente del piano, utilizza l'azione **Restore** <img class="inline" src="images/restore-icon.png"  alt="azione restore"> per la versione che desideri ripristinare. Il piano viene ripristinato alla versione selezionata.  

## Stima dei tempi di distribuzione
{: #plan_durationEst}

Prima di avviare una distribuzione, puoi stimarne la durata prevista. Per stimare i tempi di durata, utilizza l'azione **Estimate Task Times** nella pagina Deployment Plan Detail. L'ora visualizzata rappresenta l'ora in cui termina la distribuzione se la avvii ora.
