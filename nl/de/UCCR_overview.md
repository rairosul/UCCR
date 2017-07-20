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


# Informationen zu {{site.data.keyword.uccr_short}}
{: #about_UCCR}


## Was ist {{site.data.keyword.uccr_short}}?
{: #what}

{{site.data.keyword.uccr_full}} ist ein Tool für die unternehmensweite Release-Verwaltung. {{site.data.keyword.uccr_short}} arbeitet nahtlos mit anderen Bluemix-Services und mit Ihren lokalen UrbanCode&reg;-Produkten zusammen.

Mit {{site.data.keyword.uccr_short}} können Sie Folgendes ausführen:

<ul>
<li>Bereitstellungen für viele Anwendungen koordinieren
</li>
<li>Abhängigkeiten von Projekten und Anwendungen visualisieren
</li>
<li>Qualitätsabhängige Förderung von Code automatisieren
</li>
<li>Planung für Hauptreleaseereignisse optimieren
</li>
</ul>


## Schlüsselbegriffe
{: #keyterms}

Die folgenden Begriffe werden im Zusammenhang mit {{site.data.keyword.uccr_short}} häufig verwendet:

**Aktivität**: Aktivitäten bezeichnen Elemente, die in der Liste **Aktivitäten** auf der Seite 'Releases' angezeigt werden können. Zu den Aktivitäten gehören Releases, Ereignisse und Bereitstellungspläne. Sie können die Liste **Aktivitäten** nach Status, Zeit und Tag filtern.  

**Anwendung**: Als Anwendungen werden die IBM UrbanCode Deploy-Anwendungen bezeichnet, die von {{site.data.keyword.uccr_short}} verwaltet werden. In {{site.data.keyword.uccr_short}} werden integrierte Anwendungen den Tasks des Typs 'UrbanCode Deploy' zugewiesen. Sie können Anwendungsprozesse, Versionen und Umgebungen auswählen. Beim Ausführen einer Task des Typs 'UrbanCode Deploy' wird auch die zugeordnete Anwendung in IBM UrbanCode Deploy ausgeführt.

**Automatische Task**: Im Rahmen von Bereitstellungen werden automatische Tasks automatisch gestartet, sobald sie für die Ausführung infrage kommen. Zu den automatischen Tasks gehören die folgenden Tasktypen: 'UrbanCode Deploy', 'Continuous Delivery Pipeline', 'E-Mail', 'Slack', 'Anderen Plan ausführen' und 'Verzögert'.

**Abhängige Task**: Das Starten einer Task kann von der Beendigung anderer Tasks abhängen. Eine Task, die darauf wartet, dass eine andere Task abgeschlossen ist, wird als abhängige Task bezeichnet. Eine Task, auf deren Beendigung eine abhängige Task wartet, wird als vorausgesetzte Task bezeichnet. Abhängige Tasks können erst gestartet werden, nachdem alle zugehörigen vorausgesetzten Tasks aufgelöst sind. Durch Abhängigkeiten wird in der Regel sichergestellt, dass Tasks in der erwarteten Reihenfolge ausgeführt werden.

**Dauer**: Die zum Ausführen von Tasks benötigte Zeit. Die Dauer wird vom Start einer Task bis zu ihrer Auflösung (Beendigung) gemessen. Beim Erstellen mancher Tasktypen können Sie die voraussichtliche Dauer schätzen. Die Dauer wird in Minuten angegeben.

**Umgebung**: Bezeichnet die IBM UrbanCode Deploy-Anwendungsumgebungen. In UrbanCode Deploy werden Bereitstellungsziele als Umgebungen definiert. In {{site.data.keyword.uccr_short}} wählen Sie die Umgebung zum Ausführen von Tasks des Typs 'UrbanCode Deploy' aus. Sie können die Umgebung beim Erstellen der Task oder während der Laufzeit angeben.

**Ausführungsmuster**: Bezeichnet die Reihenfolge, in der die Tasks in einem Bereitstellungsplan für die Ausführung infrage kommen. Für einen Plan wird standardmäßig das sequenzielle Ausführungsmuster verwendet. Sequenzielle Tasks werden ab der ersten Task im Bereitstellungsplan nacheinander ausgeführt. Sie können Tasks zu einer Gruppe zusammenfassen und der Gruppe das parallele Ausführungsmuster zuweisen. Parallele Tasks können in beliebiger Reihenfolge und gleichzeitig ausgeführt werden.

Das parallele Ausführungsmuster können Sie einer Gruppe beim Erstellen der Gruppe zuweisen. Das erwartete Ausführungsmuster kann durch Taskabhängigkeiten beeinflusst werden.

**Integration**: Bezeichnet die geregelte Kommunikation zwischen {{site.data.keyword.uccr_short}} und anderen Produkten und Services. Die Kommunikation zwischen {{site.data.keyword.uccr_short}} und integrierten Produkten kann bidirektional erfolgen. Beispiel: IBM UrbanCode Deploy sendet Anwendungsdaten an {{site.data.keyword.uccr_short}} und {{site.data.keyword.uccr_short}} führt anschließend die Anwendungen aus. Integrationen werden mit IBM Bluemix DevOps Connect konfiguriert.

**Prozess**: Bezeichnet einen UrbanCode Deploy-Anwendungsprozess. In UrbanCode Deploy definieren Prozesse Automationsaktivitäten wie das Bereitstellen von Komponenten. Beim Ausführen von Tasks des Typs 'UrbanCode Deploy' in  {{site.data.keyword.uccr_short}} wählen Sie den Prozess aus. Der Prozess kann beim Erstellen der Task oder während der Ausführungszeit ausgewählt werden.

**Tag**: Ein Tag ist eine Bezeichnung, die auf Tasks oder Releases angewendet werden kann. Durch Tags für Tasks kann die Anwendbarkeit der Tasks auf eine bestimmte Bereitstellung festgelegt werden. Ein Tag für Releases kann zum Organisieren und Filtern der Releases verwendet werden.

**Taskgruppe**: Sie können zwei oder mehr Tasks in einer Taskgruppe zusammenfassen. Beim Erstellen einer Gruppe wird das Ausführungsmuster (sequenziell oder parallel) für die Gruppe definiert.

**Team**: Ein Team ist eine Zusammenstellung von Benutzern und Gruppen. In {{site.data.keyword.uccr_short}} werden Releases, Ereignisse und Bereitstellungspläne von Teams verwaltet. Teams können aus IBM UrbanCode Deploy importiert werden.

**Version**: Bezeichnet eine Momentaufnahme einer IBM UrbanCode Deploy-Anwendung. Beim Erstellen einer Task des Typs 'UrbanCode Deploy' werden Versionen der Anwendung, die der Task zugewiesen ist, im Bereitstellungsplan gespeichert. Auf der Registerkarte für Versionen können Sie die Anwendungsversionen und Umgebungen auswählen, die beim Ausführen einer Task verwendet werden sollen.

## Wichtige Konzepte
{: #keyconcepts}

**Bereitstellung**:
Der Begriff 'Bereitstellung' bezeichnet die Aktivitäten zum Liefern eines Softwareprojekts an ein Bereitstellungsziel. Bereitstellungen werden normalerweise in jeder Phase des Releaselebenszyklus bis zur Produktionsphase ausgeführt. Die während der Bereitstellung ausgeführten Aktivitäten werden als Tasks bezeichnet und in Bereitstellungsplänen definiert. Eine Bereitstellung wird gestartet, indem eine für die Ausführung infrage kommende Task aus dem Bereitstellungsplan gestartet wird. Eine Bereitstellung gilt als abgeschlossen, wenn alle Tasks aus dem Bereitstellungsplan aufgelöst (beendet) sind.

**Bereistellungsplan**: Bezeichnet einen wiederholt ausführbaren Plan, der zum Ausliefern von Software-Releases verwendet wird. Bereitstellungspläne enthalten die Tasks, die zum Ausführen von Bereitstellungen verwendet werden. Durch das Hinzufügen einer Task zu einem Bereitstellungsplan wird der Typ und die Dauer des Plans definiert.

Wenn Sie eine Bereitstellung starten möchten, starten Sie eine der für die Ausführung infrage kommenden Tasks aus dem zugehörigen Bereitstellungsplan. Ob eine Task für die Ausführung infrage kommt, wird durch das Ausführungsmuster der Task festgelegt. Automatische Tasks werden automatisch gestartet, sobald sie für die Ausführung infrage kommen. Manuelle Tasks werden manuell gestartet.  

**Ereignis**: Ereignisse sind auf Releases bezogene Aktivitäten, die auf Releases angewendet und im Kalender überwacht werden. Mithilfe von Ereignissen können Sie Ihre Releases und andere zeitabhängige Aktivitäten wie arbeitsfreie Zeiten und Ausfallzeiten organisieren.

**Task**: Eine Task bezeichnet eine allgemeine Aktivität, die für das Geschäft von Bedeutung ist und die einen Anfangspunkt, einen Endpunkt sowie eine messbare Dauer aufweist. Die Dauer wird verwendet, um die Bereitstellungszeiten zu schätzen. Tasks werden zu Bereitstellungsplänen hinzugefügt. Beim Ausführen einer Bereitstellung werden die im zugehörigen Plan enthaltenen Tasks ausgeführt.

Sie können verschiedene Tasktypen definieren.
<ul>
<li>Tasks des Typs 'UrbanCode Deploy' führen Anwendungsprozesse in IBM UrbanCode Deploy aus. Continuous Release überwacht die Versionen (Momentaufnahmen) und die Umgebungen, die von den Anwendungen verwendet werden. Tasks dieses Typs werden automatisch gestartet, sobald sie für die Ausführung infrage kommen.
</li>
<li>Manuelle Tasks können eine Aktivität darstellen, die sich auf eine Bereitstellung bezieht (z. B. das Starten eines Servers). Manuelle Tasks werden (wie der Name schon sagt) manuell gestartet.
</li>
<li>Verzögerte Tasks stellen wichtige Meilensteine dar. Eine verzögerte Task gehört zu den automatischen Tasks. Sie wird gestartet, sobald sie für die Ausführung infrage kommt, und sie endet nach der für die Task angegebenen Zeit. Verzögerte Tasks sind in der Regel Voraussetzungen für andere Tasks.
</li>
<li>Header-Tasks stellen Organisationselemente für Bereitstellungspläne zur Verfügung. Sie können eine Header-Task verwenden, um eine Taskgruppe anzugeben oder um Hinweise oder Anweisungen für eine Gruppe hinzuzufügen. Header-Tasks sind automatische Tasks und sie enden unmittelbar nachdem sie gestartet wurden. Für Header-Tasks kann keine Dauer definiert werden.
</li>
<li>E-Mail-Tasks senden Nachrichten an E-Mail-Konten.
</li>
<li>Slack-Tasks senden Nachrichten an einen benutzerdefinierten Slack-Kanal.
</li>
<li>Continuous Delivery Pipeline-Tasks automatisieren Ihre DevOps-Workflows. Mithilfe von Pipeline-Tasks können Sie Ihre Pipelines verwalten.
</li>
</ul>

**Release**:
Ein Release ist ein Container für Bereitstellungspläne, Ereignisse und Tags. Ein Release enthält in der Regel mindestens einen Bereitstellungsplan. Dabei stellt jeder Plan in einem Release normalerweise eine Phase (Stage) des Entwicklungszyklus dar (z. B. Qualitätssicherung oder Produktion). Die einzelnen Phasen (oder Bereitstellungspläne) werden zusammen als Releaselebenszyklus bezeichnet.
