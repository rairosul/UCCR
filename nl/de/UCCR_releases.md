---

copyright:
 years: 2017
lastupdated: "2017-6-22"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}

# Informationen zu  Releases
{: #releases_overview}

Ein Release ist ein Container für Bereitstellungspläne, Ereignisse und Tags.

{:shortdesc}

Ein Release enthält normalerweise Bereitstellungspläne und Ereignisse, die zusammen bestimmten geschäftlichen Zwecke dienen. Die Bereitstellungspläne können beispielsweise die Phasen in einem Lebenszyklus für Softwareentwicklung darstellen (z. B. Entwicklung, Qualitätssicherung und Produktion). Ein Ereignis kann eine Ausfallzeit darstellen, die sich auf das Release auswirkt.

Wenn Sie Ereignisse zu einem Release hinzufügen, können Sie mithilfe des Kalenders die Seite 'Releases' so filtern, dass die Releases und die Bereitstellungspläne angezeigt werden.

## Releases erstellen
{: #releases_create}

Führen Sie die folgenden Schritte aus, um ein Release zu erstellen:

1. Klicken Sie auf der Seite 'Releases' auf **Release erstellen**.

1. Geben Sie im Fenster 'Release erstellen' in das Feld **Name** einen Namen für das Release ein. Ein Name ist erforderlich.

3. Wählen Sie in der Liste **Team** ein Team aus, von dem das Release verwaltet werden soll. Sie können nicht nur Bereitstellungspläne des Teams, von dem das Release verwaltet wird, zu dem Releaseereignis hinzufügen, sondern auch Bereitstellungspläne von anderen Teams. Alle Teams, zu denen Sie gehören, können hinzugefügt werden. Ein Team ist erforderlich.

3. Wählen Sie im Feld **Startzeit** einen Startzeitpunkt (Datum und Uhrzeit) aus. Für jedes Release ist eine Startzeit erforderlich.

3. Wählen Sie im Feld **Endzeit** einen Endzeitpunkt (Datum und Uhrzeit) aus.

3. Wählen Sie in der Liste **Tags** ein Ereignis oder einen Tag aus. Sie können mehrere Elemente auswählen. Wenn das Ereignis im Kalender angezeigt werden soll, [wählen Sie ein Ereignis aus, das auf der Seite 'Kalender konfigurieren' erstellt wird](UCCR_events.html#events_tagCreate).

1. Sie können optional einen Tag erstellen, indem Sie den Tagnamen in das Feld **Tags** eingeben. Tags, die Sie im Fenster 'Release erstellen' erstellen, werden nicht im Kalender angezeigt, damit der Kalender übersichtlich bleibt.

5. Klicken Sie auf **Speichern**.

Wenn das Release in der Liste 'Aktivitäten' angezeigt werden soll, stellen Sie sicher, dass der Datumsbereich Tage enthält, die zwischen der Start- und der Endzeit für das Release liegen. 

Nachdem das Release erstellt ist, können Sie Bereitstellungspläne, Ereignisse und Tags zu dem Release hinzufügen.

## Bereitstellungspläne zu einem Release hinzufügen
{: #releases_planAdd}

Sie können vorhandene Bereitstellungsplan zu einem Release hinzufügen oder neue Bereitstellungspläne erstellen.

Führen Sie die folgenden Schritte aus, um vorhandene Bereitstellungspläne zu einem Release hinzuzufügen:

1. Wählen Sie auf der Seite 'Releases' das gewünschte Release aus.

1. Klicken Sie auf der Seite 'Releasedetails' auf **Bereitstellungsplan erstellen**.

1. Wählen Sie im Fenster 'Plan hinzufügen' die Pläne aus, die Sie zu dem Release hinzufügen möchten. Alle terminierten Pläne, die Ihren Teams zugeordnet sind, werden angezeigt.

3. Klicken Sie auf **Speichern**.

[Um einen Plan zu erstellen](UCCR_deployPlan.html#plan_create), klicken Sie auf **Bereitstellungsplan erstellen**. Auf der Seite 'Releasedetails' erstellte Pläne werden automatisch dem Release zugeordnet. Wenn Sie einen Bereitstellungsplan unabhängig von einem Release erstellen, können Sie auswählen, zu welchem Release der Plan hinzugefügt werden soll.

## Releases verwalten
{: #releases_manage}

Auf der Seite 'Releasedetails' werden die Bereitstellungspläne angezeigt, die zu dem Release gehören. Um das Release oder die zugehörigen Bereitstellungspläne zu verwalten, öffnen Sie die Seite 'Releasedetails' und führen Sie anschließend eine der folgenden Tasks aus:
<ul>
<li>Klicken Sie auf **Bearbeiten**, um die Releasedefinition zu ändern. Mit dieser Option können Sie
Ereignisse und Tags zu dem Releaseereignis hinzufügen.
</li>
<li>Wählen Sie **Plan bearbeiten** aus, um einen Bereitstellungsplan zu bearbeiten. Das Fenster 'Bereistellungsplan bearbeiten' wird angezeigt.
</li>
<li>Wählen Sie **Plan erneut planen** aus, um die geplante Startzeit und die geplante Endzeit zu ändern.
</li>
<li>Wählen Sie **Plan kopieren** aus, um einen Bereitstellungsplan zu kopieren. Eine Kopie des ausgewählten Plans wird zu dem Release hinzugefügt.</li>
<li>Wählen Sie **Aus Release entfernen** aus, um den Bereitstellungsplan aus dem Release zu entfernen. Pläne, die aus einem Release entfernt wurden, werden nicht gelöscht und können zu einem anderen Release hinzugefügt werden.
</li>
</li>
<li>Wählen Sie **Plan archivieren** aus, um den Bereitstellungsplan in das Archiv zu verschieben. Archivierte Pläne können wiederhergestellt werden.
</li>
</ul>

Informationen zum Starten einer Bereitstellung finden Sie in [Bereitstellungen ausführen](UCCR_deployRun.html#deployment_run).

## Releases archivieren und wiederherstellen
{: #releases_archiveRelease}

Ein Release kann nicht gelöscht werden, aber es kann im Archiv gespeichert werden. Archivierte Releases werden nicht auf der Seite 'Releases' angezeigt.

Führen Sie die folgenden Schritte aus, um ein Release zu archivieren:

1. Wählen Sie auf der Seite 'Releases' die Aktion **Archivieren** für das Release aus.

1. Geben Sie im Fenster zum Archivieren von Releaseereignissen an, welche Bereitstellungspläne archiviert werden sollen, indem Sie eine der folgenden Optionen auswählen:
<ul>
<li>Wählen Sie **Alle Bereitstellungspläne archivieren** aus, um das Release und alle Bereitstellungspläne unabhängig vom aktuellen Status zu archivieren.</li>
<li>Wählen Sie **Nur abgeschlossene Bereitstellungspläne archivieren** aus, um das Release und alle Bereitstellungspläne mit dem Status 'Abgeschlossen' zu archivieren. Bereitstellungspläne mit anderen Statuswerten werden nicht archiviert und behalten den aktuellen Status bei.</li>
</ul>

3. Klicken Sie auf **Archivieren**.

Führen Sie die folgenden Schritte aus, um ein archiviertes Release wiederherzustellen: 

1. Klicken Sie auf der Seite 'Releases' auf **Archiviert**.

2. Klicken Sie in der Liste der archivierten Releases auf die Aktion **Wiederherstellen** für das gewünschte Release.

Ein wiederhergestelltes Release enthält alle ursprünglichen Bereitstellungspläne.
