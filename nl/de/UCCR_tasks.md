---

copyright:
  years: 2017
lastupdated: "2017-6-22"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}

# Tasks verwalten
{: #tasks_overview}

Eine Task stellt eine geschäftsrelevante Aktivität dar, die mit einer Softwarebereitstellung verbunden ist. Tasks werden in Bereitstellungsplänen definiert.

{:shortdesc}

Die meisten Tasks verfügen über einen Start- und einen Endpunkt sowie über eine messbare Dauer. Für Tasks sind die folgenden Tasktypen verfügbar:

<ul>
<li>Eine Task des Typs **Manuell** kann eine Aktivität darstellen, die mit einer Softwarebereitstellung verbunden ist (z. B. das Offlineschalten eines Servers oder das Aktualisieren einer Datenbank).</li>
<li>Eine Task des Typs **UrbanCode Deploy** stellt eine IBM&reg; UrbanCode&reg; Deploy-Anwendung dar. Mit diesem Tasktyp können Sie UrbanCode Deploy-Anwendungen ausführen.</li>
<li>Eine Task des Typs **Continuous Delivery Pipeline** stellt eine {{site.data.keyword.contdelivery_full}}-Pipeline dar. Mit diesem Tasktyp können Sie Ihre {{site.data.keyword.contdelivery_short}}-Pipelines verwalten.</li>
<li>Eine Task des Typs **Verzögert** stellt ein kritisches Ereignis dar, das an einem bestimmten Zeitpunkt auftritt.</li>
<li>Eine Task des Typs **Header** ist ein Organisationselement. Eine Header-Task kann beispielsweise verwendet werden, um eine Taskgruppe zu identifizieren.</li>
<li>Eine Task des Typs **E-Mail** sendet eine E-Mail-Nachricht, wenn sie ausgeführt wird.</li>
<li>Eine Task des Typs **Anderen Plan ausführen** führt Bereitstellungen für andere Bereitstellungspläne aus, die an demselben Releaseereignis teilnehmen. Dies ist ein experimenteller Tasktyp.</li>
<l1>Eine Task des Typs **Slack** sendet eine Nachricht an einen Slack-Kanal, wenn sie ausgeführt wird. </l1>
</ul>

Sie können Tasks erstellen und zu Bereitstellungsplänen hinzufügen oder Tasks aus CSV-Dateien importieren, die mit IBM UrbanCode Release oder mit einer anderen Anwendung erstellt wurden. Außerdem können Sie Tasks aus anderen Bereitstellungsplänen kopieren. Informationen zum Format der CSV-Datei finden Sie unter [Tasks importieren](/docs/services/UCCR/UCCR_deployPlan.html#plan_importTasks).

## Tasks erstellen
{: #tasks_create}

Beim Erstellen einer Task wählen Sie aus, in welchem Bereitstellungsplan die Task hinzugefügt werden soll. Neue Tasks werden standardmäßig am Ende des Bereitstellungsplans hinzugefügt. Nachdem eine Task erstellt wurde, kann sie verschoben oder kopiert und in einen anderen Bereitstellungsplan eingefügt werden. Außerdem können Sie [Abhängigkeiten von anderen Tasks erstellen](/docs/services/UCCR/UCCR_tasks.html#tasks_dependencies).

Nachdem Sie eine Task gespeichert haben, werden Aktionssymbole für die Task angezeigt. Mithilfe der Aktionssymbole können Sie den Status der Task während einer Bereitstellung ändern. Alle Tasks verfügen über das Aktionssymbol **Überspringen**. Andere Symbole (z. B. **Starten**) werden angezeigt, wenn der Kontext dies zulässt.

![](images/deploy-plan-intro.png "Typischer Bereitstellungsplan")

Abbildung 1. Einfacher Bereitstellungsplan mit Tasks und Aktionsschaltflächen

Jede Task in einem Bereitstellungsplan ist in einer separaten Zeile enthalten. In der folgenden Tabelle werden die Informationen beschrieben, die für jede Task angezeigt werden.

### Tabelle 1. Taskeigenschaften

| Eigenschaft  | Beschreibung  |
| ------------------ | ------------------ |
| Name               |Name der Task      |
| Typ               |Typ der Task: Manuell, UrbanCode Deploy, Verzögert, Header |             
| Status             |Status der Task: Nicht gestartet, Abgeschlossen, Fehlgeschlagen, Übersprungen, Nicht zutreffend |
| Eigner              |Person, der die Task zugeordnet ist|
| Startzeit  |Startzeit oder erwartete Startzeit bei geplantem Start; oder die geschätzte Dauer bei anderen Tasks        |
| Endzeit               |Zeitpunkt, an dem die Task aufgelöst sein sollte        |
| Dauer               |Der Zeitraum vom Start bis zur Auflösung der Task (angegeben in Minuten)        |
| Abhängigkeiten               |Die Anzahl der vorausgesetzten Tasks bzw. der abhängigen Tasks für die aktuelle Task        |

---
Nachdem Tasks in Bereitstellungsplänen hinzugefügt wurden, können sie auf verschiedene Arten verwaltet werden.

Um eine Task zu verschieben, klicken Sie an einer beliebigen Stelle auf die Task und ziehen Sie sie an eine neue Postion.

Um eine Task oder Gruppe zu kopieren, wählen Sie die Task oder Gruppe aus, klicken Sie auf **Kopieren** <img class="inline" src="images/copy-group.png"  alt="Schaltfläche 'Kopieren'">, platzieren Sie den Cursor an der Stelle, an der die kopierte Task eingefügt werden soll, und klicken Sie auf **Einfügen** <img class="inline" src="images/paste-group.png"  alt="Schaltfläche 'Einfügen'">.

Um eine Task oder Gruppe aus einem Bereitstellungsplan auszuschneiden, wählen Sie die Task oder Gruppe aus und klicken Sie auf **Ausschneiden** <img class="inline" src="images/cut-group.png"  alt="Schaltfläche 'Ausschneiden'">.

Um eine Task zu löschen, wählen Sie die Task aus und klicken Sie auf **Löschen** <img class="inline" src="images/trash-group.png"  alt="Schaltfläche 'Löschen'">. Die Task wird aus dem Bereitstellungsplan entfernt.

## Tasks des Typs 'UrbanCode Deploy' erstellen
{: #tasks_UDTasks}

Tasks des Typs 'UrbanCode Deploy' dienen zum Verwalten von UrbanCode Deploy-Anwendungen. Wenn Sie eine Task des Typs 'UrbanCode Deploy' ausführen, wird die zugeordnete UrbanCode Deploy-Anwendung mit dem Prozess, der Version und der Umgebung ausgeführt, die in der Task angegeben sind. Die Version und die Umgebung kann in der Entwicklungsphase festgelegt werden oder während der Laufzeit.

Bei der Ausführung von Bereitstellungen werden Tasks des Typs 'UrbanCode Deploy' automatisch gestartet, sobald sie für die Ausführung infrage kommen.   

**Wichtig:** Anwendungen sind erst verfügbar, nachdem {{site.data.keyword.uccr_short}} mit UrbanCode Deploy integriert wurde. Welche Anwendungen für einen Bereitstellungsplan verfügbar sind, hängt davon ab, welches Team dem Plan zugeordnet ist. Anwendungen, die in UrbanCode Deploy von diesem Team verwaltet werden, sind auch in {{site.data.keyword.uccr_short}} verfügbar.

Führen Sie die folgenden Tasks aus, um eine Task des Typs 'UrbanCode Deploy' zu erstellen.

1. Klicken Sie auf der Seite 'Bereitstellungsdetails' auf **Task erstellen**. Wenn Sie eine Task an einer bestimmten Stelle im Plan hinzufügen möchten, wählen Sie eine Task aus, bevor Sie die Aktion **Task erstellen** verwenden. Die neue Task wird vor der ausgewählten Task hinzugefügt.

1. Wählen Sie im Dialogfeld 'Task erstellen' in der Liste **Typ** den Eintrag **UrbanCode Deploy** aus.

1. Geben Sie in das Feld **Name** einen Namen für die Task ein.

3. Geben Sie in das Feld **Dauer (Minuten)** ein, wie viele Minuten die vollständige Ausführung der Task voraussichtlich dauert. Die geschätzte Dauer wird verwendet, um die zu erwartenden Bereitstellungszeiten zu berechnen.

3. Ordnen Sie in der Liste **Tags** einen Tag für die Task zu. Sie können mehrere Tags auswählen. Um einen Tag zu erstellen, geben Sie den Tagnamen in das Textfeld für die Liste ein. 

3. Wählen Sie in der Liste **Anwendungsname** eine Anwendung aus.

3. Wählen Sie in der Liste **Prozess** einen Anwendungsprozess aus. Prozesse, die der ausgewählten UrbanCode Deploy-Anwendung zugeordnet sind, stehen zur Verfügung. 

3. Wählen Sie in der Liste **Umgebung** eine Anwendungsumgebung aus. Umgebungen, die der ausgewählten UrbanCode Deploy-Anwendung zugeordnet sind, stehen zur Verfügung.  Um das Auswählen einer Umgebung zurückzustellen, bis die Bereitstellung zum Ausführen bereit ist, wählen Sie **Registerkarte 'Version' verwenden** aus.

3. Wählen Sie in der Liste **Version** eine Anwendungsversion aus. Versionen verweisen auf Momentaufnahmen von IBM UrbanCode Deploy-Anwendungen. Versionen, die der ausgewählten Anwendung zugeordnet sind, stehen zur Verfügung. Um das Auswählen einer Version zurückzustellen, wählen Sie **Registerkarte 'Version' verwenden** aus. Wenn für den Anwendungsprozess keine Version erforderlich ist, wählen Sie **Keine Version** aus. Diese Option kann beispielsweise ausgewählt werden, wenn Sie einen Konfigurationsprozess ausführen, für den keine Komponenten erforderlich sind.

3. Ordnen Sie in der Liste **Zugewiesene Gruppen und Benutzer** einen Benutzer oder eine Gruppe für die Task zu. Der zugewiesene Benutzer führt die Task während der Bereitstellung aus.

3. Wählen Sie in der Liste **Eigner** den Taskeigner aus. Der standardmäßige Eigner ist der Benutzer, von dem die Task erstellt wurde. Die Liste **Eigner** wird angezeigt, nachdem die Task einem Benutzer oder einer Gruppe zugewiesen wurde.    

5. Klicken Sie auf **Speichern**. Die Task wird in den Bereitstellungsplan eingefügt.

Nach dem Erstellen der Task wird die Registerkarte **Version** in dem Plan mit den Informationen der Anwendung aktualisiert, die der Task zugeordnet ist. Wenn Sie für die Anwendungsumgebung und -version die Option **Registerkarte 'Version' verwenden** ausgewählt haben, verwenden Sie die Registerkarte 'Version', um diese Optionen festzulegen, bevor Sie die Bereitstellung ausführen.

## Manuelle Tasks erstellen
{: #tasks_manual}

Manuelle Tasks stellen in der Regel zugeordnete Aktivitäten für ein Software-Release dar, die über einen Startpunkt, einen Endpunkt und eine messbare Dauer verfügt.

Führen Sie die folgenden Schritte aus, um eine manuelle Task zu erstellen:

1. Klicken Sie auf der Seite 'Bereitstellungsdetails' auf **Task erstellen**. Wenn Sie eine Task an einer bestimmten Stelle im Plan hinzufügen möchten, wählen Sie eine Task aus, bevor Sie die Aktion **Task erstellen** verwenden. Die neue Task wird vor der ausgewählten Task hinzugefügt.

1. Wählen Sie im Dialogfeld 'Task erstellen' in der Liste **Typ** den Eintrag **Manuell** aus.

1. Geben Sie in das Feld **Name** einen Namen für die Task ein.

3. Geben Sie in das Feld **Dauer (Minuten)** ein, wie viele Minuten die vollständige Ausführung der Task voraussichtlich dauert. Die geschätzte Dauer wird verwendet, um die zu erwartenden Bereitstellungszeiten zu berechnen.

3. Ordnen Sie in der Liste **Tags** einen Tag für die Task zu. Sie können mehrere Tags auswählen. Um einen Tag zu erstellen, geben Sie den Tagnamen in das Textfeld für die Liste ein. 

3. Ordnen Sie in der Liste **Zugewiesene Gruppen und Benutzer** einen Benutzer oder eine Gruppe für die Task zu. Der zugewiesene Benutzer führt die Task während der Bereitstellung aus.

3. Wählen Sie in der Liste **Eigner** den Taskeigner aus. Der standardmäßige Eigner ist der Benutzer, von dem die Task erstellt wurde. Die Liste **Eigner** wird angezeigt, nachdem die Task einem Benutzer oder einer Gruppe zugewiesen wurde.    

5. Klicken Sie auf **Speichern**. Die Task wird in den Bereitstellungsplan eingefügt.

## Verzögerte Tasks erstellen
{: #tasks_delayed}

Verzögerte Tasks stellen Meilensteine oder kritische Ereignisse für eine Bereitstellung dar. Durch eine verzögerte Task können Sie sicherstellen, dass wichtig Tasks am erwarteten Zeitpunkt gestartet werden. Verzögerte Tasks sind in der Regel Voraussetzungen für andere wichtige Tasks.

Eine verzögerte Task wird gestartet, sobald sie für die Ausführung infrage kommt, und sie wird an einem vom Benutzer definierten Zeitpunkt beendet. Eine gestartete verzögerte Task hat den Status `In Bearbeitung`, bis der geplante Zeitpunkt erreicht ist. An diesem Zeitpunkt wird der Status in `Abgeschlossen` geändert. Sobald eine verzögerte Task abgeschlossen ist, werden automatische Tasks gestartet, die von der verzögerten Task abhängig sind.

Führen Sie die folgenden Schritte aus, um eine verzögerte Task zu erstellen:

1. Klicken Sie auf der Seite 'Bereitstellungsdetails' auf **Task erstellen**. Wenn Sie eine Task an einer bestimmten Stelle im Plan hinzufügen möchten, wählen Sie eine Task aus, bevor Sie die Aktion **Task erstellen** verwenden. Die neue Task wird vor der ausgewählten Task hinzugefügt.

1. Wählen Sie im Dialogfeld 'Task erstellen' in der Liste **Typ** den Eintrag **Verzögert** aus.

1. Geben Sie in das Feld **Name** einen Namen für die Task ein.

3. Geben Sie in das Feld **Zeit** den Zeitpunkt ein oder wählen Sie den Zeitpunkt aus, an dem die Task abgeschlossen werden soll.

3. Wählen Sie in der Liste **Zeitzone** die Zeitzone für den Wert im Feld **Zeit** aus.    

5. Klicken Sie auf **Speichern**. Die Task wird in den Bereitstellungsplan eingefügt.

## Header-Tasks erstellen
{: #tasks_header}

Header-Tasks stellen Organisationselemente dar, die Sie zu Bereitstellungsplänen hinzufügen können. Wenn Sie eine Taskgruppe erstellen, können Sie die Gruppe bei Bedarf durch eine Header-Task identifizieren. Header-Tasks können wie jede andere Task über Abhängigkeiten verfügen.

Beim Importieren eines Bereitstellungsplans aus IBM UrbanCode Release werden Segmenttasks in Segmentstart- und Segmentendetasks des Typs 'note' eingeschlossen. Segmentabhängigkeiten werden als Abhängigkeiten von Segmentendetasks dargestellt. 

Führen Sie die folgenden Schritte aus, um eine Header-Task zu erstellen:

1. Klicken Sie auf der Seite 'Bereitstellungsdetails' auf **Task erstellen**. Wenn Sie eine Task an einer bestimmten Stelle im Plan hinzufügen möchten, wählen Sie eine Task aus, bevor Sie die Aktion **Task erstellen** verwenden. Die neue Task wird vor der ausgewählten Task hinzugefügt.

1. Wählen Sie im Dialogfeld 'Task erstellen' in der Liste **Typ** den Eintrag **Header** aus.

1. Geben Sie in das Feld **Name** einen Namen für die Task ein. Dieser Name kann auch der Name einer Taskgruppe sein. 

3. Geben Sie in das Feld **Beschreibung** eine Beschreibung ein oder fügen Sie eine kopierte Beschreibung ein. Sie können auch einen Hinweis, eine Erinnerung oder Anweisungen in das Feld eingeben.

5. Klicken Sie auf **Speichern**. Die Task wird in den Bereitstellungsplan eingefügt.

## Tasks des Typs 'Continuous Delivery Pipeline' erstellen
{: #tasks_pipelineCD}

Mit {{site.data.keyword.contdelivery_full}}-Pipelines können Sie Ihre DevOps-Workflows automatisieren. Eine Pipeline ist eine Abfolge von Phasen (Stages) zum Abrufen von Eingabedaten und zum Ausführen von Jobs. Mithilfe von Pipeline-Tasks können Sie Ihre {{site.data.keyword.contdelivery_short}}-Pipelines verwalten. Continuous Delivery-Pipeline-Tasks sind automatische Tasks, die ausgeführt werden, sobald sie für die Ausführung infrage kommen.

Führen Sie die folgenden Schritte aus, um eine Continuous Delivery-Pipeline-Task zu erstellen: 

1. Klicken Sie auf der Seite 'Bereitstellungsdetails' auf **Task erstellen**. Wenn Sie eine Task an einer bestimmten Stelle im Plan einfügen möchten, wählen Sie eine Task aus, bevor Sie die Aktion **Task erstellen** verwenden. Die neue Task wird vor der ausgewählten Task eingefügt.

1. Wählen Sie im Dialogfeld 'Task erstellen' in der Liste **Typ** den Eintrag **Continuous Delivery Pipeline** aus.

1. Geben Sie in das Feld **Name** einen Namen für die Task ein.

3. Geben Sie in das Feld **Beschreibung** eine Beschreibung ein oder fügen Sie eine kopierte Beschreibung ein. Sie können auch einen Hinweis, eine Erinnerung oder Anweisungen in das Feld eingeben.

3. Geben Sie in das Feld **Pipeline** die Pipeline ein, oder wählen Sie die Pipeline aus.

3. Geben Sie in das Feld **Stagename** den Namen für die Stage ein oder wählen Sie ihn aus. Die für die ausgewählte Pipeline definierten Stages stehen zur Verfügung.

3. Ordnen Sie in der Liste **Tags** einen Tag für die Task zu. Sie können mehrere Tags auswählen. Um einen Tag zu erstellen, geben Sie den Tagnamen in das Textfeld für die Liste ein. 

3. Ordnen Sie in der Liste **Zugewiesene Gruppen und Benutzer** einen Benutzer oder eine Gruppe für die Task zu. Der zugewiesene Benutzer führt die Task während der Bereitstellung aus.

3. Wählen Sie in der Liste **Eigner** den Taskeigner aus. Der standardmäßige Eigner ist der Benutzer, von dem die Task erstellt wurde. Die Liste **Eigner** wird angezeigt, nachdem die Task einem Benutzer oder einer Gruppe zugewiesen wurde.    

5. Klicken Sie auf **Speichern**. Die Task wird in den Bereitstellungsplan eingefügt.

Beim Ausführen einer Task des Typs 'Continuous Delivery Pipeline' werden die Jobs der angegebenen Stage für die ausgewählte Pipeline ausgeführt.

## E-Mail-Tasks erstellen
{: #tasks_email}

Eine E-Mail-Task sendet eine E-Mail-Nachricht, wenn die Task ausgeführt wird. Die E-Mail-Empfänger und die E-Mail-Nachricht werden beim Erstellen der Task angegeben. E-Mail-Tasks sind automatische Tasks, die ausgeführt werden, sobald sie für die Ausführung infrage kommen.

Führen Sie die folgenden Schritte aus, um eine E-Mail-Task zu erstellen:

1. Klicken Sie auf der Seite 'Bereitstellungsdetails' auf **Task erstellen**. Wenn Sie eine Task an einer bestimmten Stelle im Plan einfügen möchten, wählen Sie eine Task aus, bevor Sie die Aktion **Task erstellen** verwenden. Die neue Task wird vor der ausgewählten Task eingefügt.

1. Wählen Sie im Dialogfeld 'Task erstellen' in der Liste **Typ** den Eintrag **E-Mail** aus.

1. Geben Sie in das Feld **Name** einen Namen für die Task ein.

3. Geben Sie in das Feld **Empfänger** den Empfänger für die E-Mail ein oder wählen Sie den Empfänger aus. Die Liste der verfügbaren Empfänger enthält Benutzer und Gruppen, die Mitglieder Ihres Teams sind. Es können auch E-Mail-Adressen von Benutzern eingegeben werden, die keine Teammitglieder sind. Sie können mehrere Empfänger angeben.

3. Geben Sie in das Feld **E-Mail-Betreff** das Thema für die E-Mail ein. 

3. Geben Sie in das Feld **E-Mail-Nachricht** den Nachrichtentext für die E-Mail ein oder fügen Sie ihn ein.

5. Klicken Sie auf **Speichern**. Die Task wird in den Bereitstellungsplan eingefügt.

Wenn die Task ausgeführt wird, erhalten die Empfänger eine E-Mail-Nachricht von **IBM Continuous Release** mit dem Betreff, den Sie beim Erstellen der Task angegeben haben. 

## Tasks des Typs 'Anderen Plan ausführen' erstellen
{: #tasks_runAnother}

Eine Task 'Anderen Plan ausführen' führt eine Bereitstellung für einen anderen Bereitstellungsplan aus. Der gewünschte Plan muss aus einer Vorlage erstellt werden. Die Vorlage und der gewünschte Plan (Zielplan) müssen im selben Releaseereignis wie die Task zum Ausführen eines anderen Plans enthalten sein.

Beachten Sie, dass es sich bei diesem Tasktyp um einen experimentellen Typ handelt.

Führen Sie die folgenden Schritte aus, um eine Task des Typs 'Anderen Plan ausführen' zu erstellen:

1. Klicken Sie auf der Seite 'Bereitstellungsdetails' auf **Task erstellen**. Wenn Sie eine Task an einer bestimmten Stelle im Plan einfügen möchten, wählen Sie eine Task aus, bevor Sie die Aktion **Task erstellen** verwenden. Die neue Task wird vor der ausgewählten Task eingefügt.

1. Wählen Sie im Dialogfeld 'Task erstellen' in der Liste **Typ** den Eintrag **Anderen Plan ausführen** aus.

1. Geben Sie in das Feld **Name** einen Namen für die Task ein.

3. Wählen Sie in der Liste **Name der Planvorlage** eine Bereitstellungsplanvorlage aus. Die Vorlage muss in demselben Releaseereignis enthalten sein wie der übergeordnete Plan der Task.

3. Ordnen Sie in der Liste **Tags** einen Tag für die Task zu. Sie können mehrere Tags auswählen. Um einen Tag zu erstellen, geben Sie den Tagnamen in das Textfeld ein.

5. Klicken Sie auf **Speichern**. Die Task wird in den Bereitstellungsplan eingefügt.

Beim Ausführen der Task wird eine Bereitstellung für den Bereitstellungsplan gestartet, der aus der ausgewählten Vorlage und im selben Releaseereignis erstellt wird. Wenn aus der Vorlage mehrere Pläne in dem Releaseereignis erstellt werden, werden Bereitstellungen für alle erstellten Pläne gestartet. Während der Ausführung der anderen Bereitstellungen werden von der Task des Typs 'Anderen Plan ausführen' Statusinformationen bereitgestellt. Erweitern Sie die Task, um die Statusinformationen anzuzeigen. Die anderen Bereitstellungen können über Links in der Task geöffnet werden. Während der Ausführung der anderen Bereitstellungen weist die Task des Typs 'Anderen Plan ausführen' den Status **In Bearbeitung** auf.

## Slack-Tasks erstellen
{: #tasks_slack}

Beim Ausführen einer Slack-Task wird eine Nachricht an einen Slack-Kanal gesendet. Die Nachricht kann Text und Hyperlinks enthalten. Eine Slack-Task wird gestartet, sobald sie für die Ausführung infrage kommt.

Führen Sie die folgenden Schritte aus, um eine Slack-Task zu erstellen:

1. Klicken Sie auf der Seite 'Bereitstellungsdetails' auf **Task erstellen**. Wenn Sie eine Task an einer bestimmten Stelle im Plan einfügen möchten, wählen Sie eine Task aus, bevor Sie die Aktion **Task erstellen** verwenden. Die neue Task wird vor der ausgewählten Task eingefügt.

1. Wählen Sie im Dialogfeld 'Task erstellen' in der Liste **Typ** den Eintrag **Slack** aus.

1. Geben Sie in das Feld **Name** einen Namen für die Task ein.

3. Geben Sie in das Feld **Web-Hook-URL** die URL des Slack-Kanals ein, an den die Nachricht zugestellt werden soll (z. B. `https://hooks.slack.com/services/my_webhook`).

3. Geben Sie in das Feld **Nachricht** den Nachrichtentext ein. Die Nachricht kann Text und Hyperlinks enthalten. 

3. Geben Sie in das Feld **Dauer (Minuten)** ein, wie viele Minuten die vollständige Ausführung der Task voraussichtlich dauert. Die geschätzte Dauer wird verwendet, um die zu erwartenden Bereitstellungszeiten zu berechnen.

3. Ordnen Sie in der Liste **Tags** einen Tag für die Task zu. Sie können mehrere Tags auswählen. Um einen Tag zu erstellen, geben Sie den Tagnamen in das Textfeld ein.

3. Ordnen Sie in der Liste **Zugewiesene Gruppen und Benutzer** einen Benutzer oder eine Gruppe für die Task zu. Der zugewiesene Benutzer führt die Task während der Bereitstellung aus.

5. Klicken Sie auf **Speichern**. Die Task wird in den Bereitstellungsplan eingefügt.

Beim Ausführen der Task wird die im Feld 'Nachricht' definierte Nachricht an den Slack-Kanal gesendet, der im Feld 'Web-Hook-URL' angegeben ist.

## Taskgruppen verwalten
{: #tasks_groups}

Sie können zwei oder mehr Tasks in einer Taskgruppe zusammenfassen. Beim Erstellen einer Gruppe definieren Sie das Ausführungsmuster (sequenziell oder parallel) für die Gruppe. Die Tasks aus einer Gruppe mit paralleler Ausführung können in beliebiger Reihenfolge und (sofern keine Abhängigkeiten bestehen) gleichzeitig ausgeführt werden. Die Tasks aus Gruppen mit sequenzieller Ausführung werden nacheinander ausgeführt, beginnend mit der ersten (obersten) Task.

Sie können Gruppen in andere Gruppen einbetten. Dabei kann eine Gruppe mit sequenzieller Ausführung in eine Gruppe mit paralleler Ausführung eingebettet werden und umgekehrt. Es ist jedoch nicht möglich, eine Gruppe mit sequenzieller Ausführung bzw. mit paralleler Ausführung in eine andere Gruppe mit demselben Ausführungsmuster einzubetten.  

Führen Sie die folgenden Schritte aus, um eine Taskgruppe zu erstellen:

1. Wählen Sie auf der Seite 'Bereitstellungsplandetails' zwei oder mehr Tasks aus.

1. Führen Sie entsprechend dem Gruppentyp, den Sie erstellen möchten, einen der folgenden Schritte aus:

  <ul>
  <li>Um eine Gruppe mit paralleler Ausführung zu erstellen, klicken Sie auf die Schaltfläche **Parallel** <img class="inline" src="images/para-icon.png"  alt="Schaltfläche für parallele Gruppe">. Wenn für die ausgewählten Tasks keine Gruppe mit paralleler Ausführung erstellt werden kann, ist die Schaltfläche inaktiviert. Beispiel: Möglicherweise kann keine Gruppe mit paralleler Ausführung erstellt werden, wenn alle ausgewählten Tasks bereits in einer Gruppe mit paralleler Ausführung enthalten sind.</li>
  <li>Um eine Gruppe mit sequenzieller Ausführung zu erstellen, klicken Sie auf die Schaltfläche **Sequenziell** <img class="inline" src="images/seq-icon.png"  alt="Schaltfläche für sequenzielle Gruppe">.
  </li>
  </ul>

Die Gruppe wird gebildet und eine **Gruppenauswahlleiste** wird zum Bereitstellungsplan hinzugefügt. Wenn Sie nicht zusammenhängende Tasks ausgewählt haben, bilden die Tasks eine fortlaufende Liste, die mit der obersten ausgewählten Task beginnt.

Die folgende Abbildung zeigt eine Gruppe mit paralleler Ausführung. In der **Gruppenauswahlleiste** wird der Gruppentyp 'Parallel' <img class="inline" src="images/para-select.png"  alt="Auswahl für parallele Gruppen"> oder 'Sequenziell' <img class="inline" src="images/seq-select.png"  alt="Auswahl für sequenzielle Gruppen"> angegeben.

![](images/group-select.png "Typischer Bereitstellungsplan")

Abbildung 2. Gruppe mit paralleler Ausführung

Um eine Gruppe zu verschieben, wählen Sie die **Gruppenauswahlleiste** aus oder klicken Sie an einer beliebigen Stelle auf die Gruppe und ziehen Sie sie an eine neue Position.

Um eine Gruppe zu kopieren, wählen Sie die Gruppe aus, klicken Sie auf **Kopieren** <img class="inline" src="images/copy-group.png"  alt="Schaltfläche 'Kopieren'">, platzieren Sie die Gruppe anschließend an der Stelle, an der die kopierte Gruppe eingefügt werden soll, und klicken Sie auf **Einfügen** <img class="inline" src="images/paste-group.png"  alt="Schaltfläche 'Einfügen'">.

Um eine Gruppe auszuschneiden, wählen Sie die Gruppe aus und klicken Sie auf **Ausschneiden** <img class="inline" src="images/cut-group.png"  alt="Schaltfläche 'Ausschneiden'">.

Um eine Gruppe aufzulösen, wählen Sie die Gruppe aus und klicken Sie auf das Symbol **Gruppe auflösen** <img class="inline" src="images/ungroup-icon.png"  alt="Symbol 'Gruppe auflösen'"> in der **Gruppenauswahlleiste**.

Um die Tasks in einer Gruppe zu löschen, wählen Sie die Gruppe aus und klicken Sie auf **Löschen** <img class="inline" src="images/trash-group.png"  alt="Schaltfläche 'Löschen'">. Die Tasks werden aus dem Bereitstellungsplan entfernt.

## Task-Tags verwalten
{: #tasks_tags}

Tags sind Organisationselemente, die Sie zu Tasks hinzufügen können. Sie können Bereitstellungspläne nach Tags filtern. Beispielsweise können Sie während einer Bereitstellung für eine Produktionsumgebung die Task mit dem Tag `DEV_only`, das nur in Entwicklungsumgebungen verwendet werden sollte, inaktivieren.

Führen Sie die folgenden Schritte aus, um einen Tag zu einer Task hinzuzufügen:

1. Wählen Sie auf der Seite 'Bereitstellungsplandetails' eine Task oder Taskgruppe aus und klicken Sie anschließend auf **Tags verwalten**  <img class="inline" src="images/task-tag.png"  alt="Tags verwalten">. Sie können mehrere Tasks und Gruppen auswählen.

1. Wählen Sie im Dialogfeld 'Tags für ausgewählte Tasks verwalten' in der Liste **Allgemeine Tags** die gewünschten Tags aus. Sie können einen neuen Tag erstellen, indem Sie in der Liste einen Namen in das Textfeld eingeben.

1. Klicken Sie auf **Speichern**.

Tags werden in den Zeilen für Tasks auf der Seite 'Bereitstellungsplandetails' angezeigt. In der nachfolgenden Abbildung sind der Task **Deploy WAR** die beiden Tags `Deployment` und `Critical` zugeordnet.

Die für einen Bereitstellungsplan verwendeten Tags werden auf der Seite 'Bereitstellungsplandetails auf der Registerkarte **Versionen** angezeigt. Um Tasks mit einem bestimmten Tag `Nicht zutreffend` für eine Bereitstellung darzustellen, löschen Sie den Tag. Tasks mit dem Status `Nicht zutreffend` können nicht gestartet werden.  

![](images/task-tag-labels.png "Typischer Bereitstellungsplan")

Abbildung 3. Taskabhängigkeiten

## Taskabhängigkeiten erstellen
{: #tasks_dependencies}

Sie können eine Task als Voraussetzung für andere Tasks deklarieren. Wenn eine Task als Voraussetzung deklariert ist, können die zugehörigen abhängigen Tasks erst gestartet werden (selbst wenn sie für die Ausführung infrage kommen), nachdem die vorausgesetzte Task aufgelöst wurde.

Eine Task kann über mehrere abhängige Tasks und über mehrere vorausgesetzte Tasks verfügen. Sie können Abhängigkeiten zwischen einer Task und jeder anderen Task im Bereitstellungsplan definieren. Sie können jedoch keine Schleifenabhängigkeiten erstellen. Beispiel: Sie dürfen eine Task nicht als von einer anderen Task abhängig definieren, die wiederum von der ersten Task abhängig ist.

Durch das Steuern von Taskabhängigkeiten können Sie sicherstellen, dass Ereignisse in der erwarteten Reihenfolge auftreten.

Führen Sie die folgenden Schritte aus, um eine Task als Voraussetzung für andere Tasks zu deklarieren:

1. Wählen Sie auf der Seite 'Bereitstellungsplandetails' eine Task oder Taskgruppe aus und klicken Sie anschließend auf **Voraussetzungen verwalten** <img class="inline" src="images/task-depend.png"  alt="Taskvoraussetzung">. Sie können mehrere Tasks und Gruppen auswählen.

1. Wählen Sie im Dialogfeld 'Voraussetzungen für ausgewählte Tasks verwalten' in der Liste **Vorausgesetzte Tasks für ausgewählte Tasks** die vorausgesetzte Task aus.

1. Klicken Sie auf **Speichern**.

Taskabhängigkeiten werden in der Spalte **Abhängigkeiten** auf der Seite 'Bereitstellungsplandetails' angezeigt. Aufwärtspfeile geben Taskvoraussetzungen an und Abwärtspfeile geben Taskabhängigkeiten an.

Die erste Task in der folgenden Abbildung hat keine Voraussetzungen, aber sie hat zwei Tasks, die von ihr abhängig sind. Die zweite Task hat eine Voraussetzung und keine Tasks, die von ihr abhängig sind.

(![](images/plan-w-depend.png "Typischer Bereitstellungsplan"))

Abbildung 4. Taskabhängigkeiten

Um Abhängigkeiten zu überprüfen oder zu ändern, wählen Sie die Task aus und klicken Sie anschließend auf **Voraussetzungen verwalten** <img class="inline" src="images/task-depend.png"  alt="Taskvoraussetzung">. Verwenden Sie das Dialogfeld 'Voraussetzungen für ausgewählte Tasks verwalten', um Abhängigkeiten zu ändern oder zu entfernen.
