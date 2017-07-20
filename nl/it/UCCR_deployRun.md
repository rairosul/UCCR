---

copyright:
 years: 2017
lastupdated: "2017-6-22"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}

# Esecuzione delle distribuzioni
{: #deployment_run}

Utilizza {{site.data.keyword.uccr_short}} per eseguire le distribuzioni software. Completa le distribuzioni risolvendo le attività in un piano di distribuzione.
{:shortdesc}

Una distribuzione si avvia quando una delle attività eleggibili del piano si avvia. Una distribuzione pianificata si avvia automaticamente all'ora pianificata se una delle proprie attività eleggibili è un'attività automatica, come le attività UrbanCode Deploy o Delayed-type. Altrimenti, avviare una distribuzione avviando una delle attività eleggibili del piano. Se il piano contiene diverse attività eleggibili, puoi avviarne una qualsiasi. Puoi avviare manualmente una distribuzione in qualsiasi momento. Puoi avviare manualmente una distribuzione pianificata prima della relativa ora pianificata.    

Il modello di esecuzione del piano di distribuzione determina quando le attività sono eleggibili per l'avvio. Se il piano ha il modello di esecuzione sequenziale, che è il modello predefinito, le attività diventano eleggibili nell'ordine in cui sono elencate nel piano, a partire dalla prima attività. Dopo che è stata risolta la prima attività, la seconda diventa eleggibile. Avvia le attività manuali eleggibili facendo clic sul pulsante **Start** dell'attività. Le attività automatiche, come le attività UrbanCode Deploy, si avviano automaticamente non appena diventano eleggibili. 

Le attività in un gruppo con un modello di esecuzione parallela diventano eleggibili contemporaneamente. Le attività nei gruppi paralleli possono essere avviate in qualsiasi ordine. Le attività e i gruppi nidificati con dipendenze ad hoc possono influenzare il modello di esecuzione.

Puoi modificare un piano di distribuzione dopo aver avviato una distribuzione. Puoi aggiungere, eliminare e modificare le attività. 

Dopo che tutte le attività sono state risolte, la distribuzione è completa. Un'attività è risolta se ha uno stato di `Complete`, `Failed` o `Skipped`. Se riapri un'attività o ne aggiungi una dopo il completamento della distribuzione, lo stato della distribuzione viene modificato in `In Progress`.

## Avvio delle distribuzioni manualmente
{: #deployment_start}

Puoi avviare una distribuzione manualmente in qualsiasi momento, incluse le distribuzioni pianificate per un avvio successivo. 

Le attività in un piano di distribuzione potrebbero non essere applicabili per la distribuzione. Le attività UrbanCode Deploy non sono applicabili se non ne viene specificato un ambiente o una versione. Quando crei le attività UrbanCode Deploy, puoi ritardare di selezionare l'ambiente e la versione utilizzando l'opzione **Use Version**. Prima di avviare la distribuzione, assicurati che tutte le attività UrbanCode Deploy siano applicabili per la distribuzione imminente.    

Puoi deliberatamente escludere le attività da una distribuzione. Puoi rendere le attività contrassegnate non applicabili escludendone le tag dalla distribuzione. Le attività con tag escluse non sono applicabili per la distribuzione.  

Le attività non applicabili hanno lo stato di `Not Applicable`. Le attività con lo stato `Not Applicable` non possono essere avviate. Se un'attività non applicabile è un prerequisito di un'attività attiva, la dipendenza viene ignorata.  

Per avviare una distribuzione, completa la seguente procedura:

1. Nella pagina Deployment, fai clic sul piano di distribuzione che desideri utilizzare per la distribuzione. Viene visualizzata la pagina dei dettagli della distribuzione.

2. Per rendere le attività contrassegnate con tag non applicabili per la distribuzione corrente, fai clic su **Versions** e nell'area **Tags**, cancella le tag. Se un'attività ha più di una tag, deselezionarle tutte. 

2. Per selezionare la versione o l'ambiente di tutte le attività UrbanCode Deploy non applicabili, fai clic su **Versions** e seleziona quindi l'ambiente e la versione. Puoi anche modificare le tue scelte per le attività con i propri ambienti e versioni già selezionati.

1. Facoltativamente, fai clic su **Hide Not Applicable Tasks** per rimuovere le attività non applicabili dall'elenco delle attività visualizzate. Le attività nascoste non vengono rimosse dal piano di distribuzione. 

1. Fai clic sull'azione **Start** <img class="inline" src="images/task-start.png"  alt="azione avvia attività"> di una delle attività eleggibili del piano. Se più di un'attività è eleggibile, puoi avviarne una qualsiasi. Soltanto le attività eleggibili visualizzano il pulsante di avvio. Un'attività avviata ha lo stato di `In Progress` finché non viene risolta.

Dopo aver avviato una distribuzione, lo stato del piano viene modificato in `In Progress`. Lo stato rimane `In Progress` finché non vengono risolte tutte le attività. Quando tutte le attività sono state risolte, lo stato del piano viene modificato in `Done`.

## Risoluzione delle attività
{: #deployment_taskComplete}

Completa una distribuzione risolvendo le attività nel piano di distribuzione. Un'attività avviata è risolta quando il suo stato viene modificato in `Complete`, `Failed` o `Skipped`.

Risolvi le attività manuali utilizzando l'azione di stato appropriata. Le attività automatiche, come le attività UrbanCode Deploy, modificano lo stato automaticamente come vengono modificate le condizioni. Tuttavia, puoi risolvere le attività automatiche manualmente. Ad esempio, potresti manualmente cambiare lo stato di un'attività UrbanCode Deploy in non riuscito per un'attività che sta impiegando troppo tempo per il completamento.

Per risolvere un'attività avviata, applica uno dei seguenti stati:

<ul>
<li>Fai clic su **Complete** <img class="inline" src="images/task-complete.png"  alt="azione completa attività"> per terminare un'attività. `Complete` significa che l'attività è terminata con i risultati previsti.
</li>
<li>Fai clic su **Skip** <img class="inline" src="images/task-skip.png"  alt="azione ignora attività"> per ignorare un'attività per la distribuzione corrente.
</li>
<li>Fai clic su **Fail** <img class="inline" src="images/task-fail.png"  alt="azione attività non riuscita"> per terminare un'attività. `Fail` significa che l'attività non è stata terminata o lo è stata con risultati non previsti.
</li>
<li>Fai clic su **Task Reopen** <img class="inline" src="images/task-reopen.png"  alt="azione riapri attività"> per aprire un'attività risolta. Se tutte le attività sono state completate, riaprire un'attività riapre la distribuzione.
</li>
</ul>

## Esecuzione delle distribuzioni pianificate
{: #deployment_startSchedule}

Una distribuzione pianificata si avvia automaticamente nell'ora pianificata se una qualsiasi delle proprie attività automatiche è eleggibile per l'avvio. Se un piano di distribuzione non contiene alcuna attività automatica eleggibile, avvia la distribuzione avviando manualmente una delle attività eleggibili.

Puoi avviare manualmente una distribuzione pianificata in qualsiasi momento anche se il piano ha attività automatiche eleggibili.
