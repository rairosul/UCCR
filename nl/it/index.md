---

copyright:
 years: 2017
lastupdated: "2017-6-22"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}


# Introduzione a Continuous Release (Beta)

{: #gettingstartedtemplate}

Il servizio {{site.data.keyword.uccr_full}} in IBM {{site.data.keyword.Bluemix_short}} è una soluzione per la gestione della release completa. Con {{site.data.keyword.uccr_short}}, puoi eseguire le release e le distribuzioni per tutte le applicazioni software nel tuo ciclo di vita di sviluppo.
{:shortdesc}

[Dopo aver creato un'istanza](https://console.ng.bluemix.net/catalog/services/continuous-release/){:new_window} ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno") di {{site.data.keyword.uccr_short}}, scegli come vuoi iniziare.

* Inizia **[creando una release ed eseguendo una distribuzione](#gs_create_plan)** se desideri lanciarti ed iniziare a creare piani di distribuzione.

* Inizia **[installando e configurando DevOps Connect](#gs_install_dc)** se desideri integrare {{site.data.keyword.uccr_short}} con la tua istanza IBM UrbanCode&trade; Deploy in loco. Dopo aver configurato un'integrazione, puoi utilizzare le attività di Continuous Release per gestire le applicazioni UrbanCode Deploy.


## Creazione di una release ed esecuzione di una distribuzione
{: #gs_create_plan}

1. [Crea una release](/docs/services/UCCR/UCCR_releases.html##releases_create) e assegnala a uno dei tuoi team. Qualsiasi membro del team può creare i piani di distribuzione per la release ed eseguire le distribuzioni.

1. Aggiungi una piano di distribuzione alla release.

  * [Crea il piano](/docs/services/UCCR/UCCR_releases.html#releases_planAdd) e assegnalo alla release. 

  * [Aggiungi le attività al piano di distribuzione](/docs/services/UCCR/UCCR_tasks.html#tasks_create). Ogni attività è elencata in una riga separata nel piano di distribuzione. Prova aggiungendo diversi tipi di attività: manuale, UrbanCode Deploy, pipeline di fornitura continua, ritardo, Email, e Slack. 

  * Puoi modificare l'elenco delle attività nel piano in vari modi. Puoi riposizionare, copiare ed eliminare le attività.  

4. Quando il tuo piano di distribuzione è pronto, esegui una distribuzione utilizzando il piano di distribuzione che hai creato nel passo precedente. 

  * [Esegui una distribuzione risolvendo le attività in un piano di distribuzione](/docs/services/UCCR/UCCR_deployRun.html). Risolvi le attività avviandole e quindi modificandone lo stato in `Completo`, `Non riuscito` o `Ignorato`. Dopo che tutte le attività in un piano di distribuzione sono state risolte, la distribuzione ha uno stato di Fatto. 

  * Le attività possono essere avviate quando sono eleggibili per l'avvio. L'eleggibilità viene determinata dal modello di esecuzione del piano. Per impostazione predefinita, un modello di esecuzione del piano è sequenziale. Inizialmente la prima attività, o l'attività in primo piano, è eleggibile per l'avvio. Puoi modificare il modello di esecuzione raggruppando le attività. Un gruppo di attività può avere un modello di esecuzione parallela, che significa che le attività del gruppo possono essere avviate in qualsiasi ordine e possono essere eseguite simultaneamente. Un piano di distribuzione può avere più gruppi e gruppi nidificati in altri gruppi.

  * Alcune attività, denominate attività automatiche, si avviano come diventano eleggibili per l'esecuzione. Le attività del tipo UrbanCode Deploy e pipeline di fornitura continua si avviano come diventano eleggibili, senza intervento manuale. Le attività automatiche aggiornano inoltre i loro stati senza intervento manuale.  

## Installazione e configurazione di DevOps Connect
{: #gs_install_dc}

IBM Bluemix DevOps Connect coordina la comunicazione tra la tua installazione IBM UrbanCode Deploy in loco e {{site.data.keyword.uccr_short}}. Dopo aver installato DevOps Connect, puoi creare integrazioni che ti abilitano di gestire le applicazioni UrbanCode Deploy con le attività {{site.data.keyword.uccr_short}}.

**Prerequisiti**

* Per la registrazione a DevOps Connect, devi disporre di un ID IBM.

* Devi disporre di [Java™ Runtime Environment versione 7 o successiva](https://java.com/en/download/){:new_window} ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno") sul sistema host e impostare la variabile PATH sulla sua ubicazione.

* Hai bisogno di un token di autorizzazione di gestione da UrbanCode Deploy.    


1. Installa DevOps Connect e utilizzalo per l'integrazione di {{site.data.keyword.uccr_short}} con UrbanCode Deploy.

  1.  In {{site.data.keyword.uccr_short}}, nella pagina Getting Started, fai clic su **Setup**.

  1.  Nella finestra di dialogo UrbanCode Deploy Integration Setup, fai clic su **Download** per scaricare DevOps Connect. Posiziona il file JAR in un computer con accesso a UrbanCode Deploy.

  1.  Utilizzando la finestra di dialogo, copia lo script di installazione di DevOps Connect. Lo script contiene il comando per avviare DevOps Connect e le credenziali necessarie per identificare il tuo servizio {{site.data.keyword.uccr_short}} Bluemix.

  1.  Sul computer in cui è collocato DevOps Connect, aprire una shell dei comandi e incolla lo script in essa 

  1.  Esegui lo script.  DevOps Connect visualizza i messaggi di avvio. 

2. Registra DevOps Connect.

  1.  Utilizza un browser web per aprire il dashboard DevOps Connect. L'URL predefinito è `https://localhost:8443`. Per modificare l'URL e conoscere altre opzioni di avvio, consulta la [documentazione DevOps Connect](https://developer.ibm.com/urbancode/plugindoc/urbancode-sync/ibm-urbancode-sync-utility/1-2/){:new_window} ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")

  1.  Nella pagina di registrazione, specifica un nome per l'installazione DevOps Connect. 

  1.  Fai clic su **Register**. La prima volta che accedi a DevOps Connect, ti verrà richiesto di registrarti con il tuo ID IBM.

  1.  Nella pagina **Sign-in to IBM**, immetti la tua password e il tuo ID IBM e quindi fai clic su **Sign In**. Devi accedere ogni volta che avvii DevOps Connect.

3. Con DevOps Connect, utilizza il plugin IBM UrbanCode Deploy for Cloud Reporting per creare un'integrazione tra {{site.data.keyword.uccr_short}} e UrbanCode Deploy.

    1.  Dal dashboard DevOps Connect, fai clic su **Integrations** e quindi su **Add New**.

    1.  Nel campo **Name**, immetti un nome per l'integrazione.

    1.  Dall'elenco **Integration Type**, seleziona **IBM UrbanCode Deploy for Cloud Reporting**. Il plugin IBM UrbanCode Deploy for Cloud Reporting viene incluso in DevOps Connect.

    1.  Nel campo **Server URI**, immetti l'URL pubblico del server UrbanCode Deploy. Ad esempio, `https://my_UCD.example.com:8447`.

    1.  Nel campo **Authentication Token**, immetti o incolla il token di autenticazione che è stato generato da UrbanCode Deploy.

    1.  Nel campo **Admin User Email**, immetti il tuo indirizzo email.

    1.  Fai clic su **Save**.

4.  Esegui l'integrazione per controllare che funzioni.

    1.  Nella pagina di integrazione, fai clic su **Run**. DevOps Connect si collega all'istanza UrbanCode Deploy specificata nel campo **Server URI**. DevOps Connect viene autorizzato dal token incollato nel campo **Authentication Token**.

    1.  In {{site.data.keyword.uccr_short}}, controlla che l'integrazione sia corretta creando un attività del tipo UrbanCode Deploy. Se puoi selezionare un'applicazione UrbanCode Deploy, l'integrazione ha avuto esito positivo. L'istanza {{site.data.keyword.uccr_short}} utilizza i parametri di avvio e accesso DevOps Connect per identificare le applicazioni UrbanCode Deploy.  
