---

copyright:
  years: 2017
lastupdated: "2017-6-22"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}

# Gestion des tâches 
{: #tasks_overview}

Une tâche représente une activité métier marquante associée à un déploiement de logiciel. Les tâches sont définies dans des plans de déploiement.

{:shortdesc}

La plupart des tâches ont un point de départ et un point d'arrivée, ainsi qu'une durée de réalisation mesurable. Une tâche peut être de l'un des types suivants :

<ul>
<li>Une tâche **manuelle** peut représenter n'importe quelle activité associée à un déploiement de logiciel, comme la mise hors ligne d'un serveur ou la mise à jour d'une base de données.</li>
<li>Une tâche **UrbanCode Deploy** représente une application IBM&reg; UrbanCode&reg; Deploy. Vous pouvez exécuter des applications UrbanCode Deploy avec ce type de tâche.</li>
<li>Une tâche de **pipeline Continuous Delivery** représente un pipeline {{site.data.keyword.contdelivery_full}}. Vous pouvez gérer vos pipelines {{site.data.keyword.contdelivery_short}} avec ce type de tâche.</li>
<li>Une tâche **différée** représente un événement critique se produisant à un moment spécifique.</li>
<li>Une tâche d'**en-tête** est un élément organisationnel. Par exemple, vous pouvez utiliser une tâche d'en-tête pour identifier un groupe de tâches.</li>
<li>Une tâche de **courrier électronique** envoie un message électronique lorsqu'elle s'exécute.</li>
<li>Une tâche de type **exécution d'un autre plan** réalise des déploiements concernant d'autres plans de déploiement participant au même événement de publication de logiciel. Il s'agit d'un type de tâche expérimental.</li>
<l1>Une tâche **Slack** envoie un message à un canal Slack lorsqu'elle s'exécute. </l1>
</ul>

Vous pouvez ajouter des tâches à des plans de déploiement en créant ces tâches ou bien importer des tâches à partir de fichiers CSV créés par IBM UrbanCode Release ou une autre application. Vous pouvez également copier des tâches depuis d'autres plans de déploiement. Voir [Importation de tâches](/docs/services/UCCR/UCCR_deployPlan.html#plan_importTasks) pour plus d'informations sur le format du fichier CSV.

## Création de tâches
{: #tasks_create}

Lorsque vous créez une tâche, vous sélectionnez le plan de déploiement auquel vous voulez ajouter la tâche. Par défaut, les nouvelles tâches sont insérées au bas du plan de déploiement. Une fois qu'une tâche est créée, vous pouvez la déplacer ou la copier et la coller dans un autre plan de déploiement. [Vous pouvez également créer des dépendances avec d'autres tâches](/docs/services/UCCR/UCCR_tasks.html#tasks_dependencies).

Une fois que vous avez sauvegardé une tâche, des icônes d'action s'affichent pour cette tâche. Pour modifier le statut d'une tâche au cours du déploiement, vous devez utiliser des icônes d'action. Toutes les tâches disposent d'une icône d'action **Ignorer**. D'autres icônes, telles que **Démarrer**, sont affichées lorsque le contexte s'y prête.

![](images/deploy-plan-intro.png "Plan de déploiement usuel")

Figure 1. Plan de déploiement simple avec boutons de tâches et d'actions

Chaque tâche d'un plan de déploiement se trouve sur une ligne distincte. Les informations qui s'affichent pour chaque tâche sont décrites dans le tableau ci-dessous.

### Tableau 1. Propriétés de tâche

| Propriété  | Description  |
| ------------------ | ------------------ |
| Nom               |Nom de la tâche       |
| Type               |Type de tâche : manuelle, UrbanCode Deploy, différée, en-tête |             
| Statut             |Statut de la tâche : Non démarrée, terminée, en échec, ignorée, non applicable |
| Propriétaire              |Personne à laquelle la tâche est affectée                                                        |
| Heure de début  |Heure de début ou heure de début attendue en fonction du début planifié ou de la durée estimée des autres tâches        |
| Heure de fin               |Heure à laquelle la tâche a été résolue|
| Durée               |Durée écoulée entre le début de la tâche et sa résolution (mesurée en minutes)        |
| Dépendances               |Indique le nombre de tâches qui constituent des prérequis pour la tâche et dont elle dépend |

---
Une fois que des tâches ont été ajoutées à des plans de déploiement, vous pouvez les gérer de différentes façons.
Pour déplacer une tâche, cliquez n'importe où sur la tâche et faites-la glisser à son nouvel emplacement.

Pour copier une tâche ou un groupe, sélectionnez la tâche et cliquez sur **Copy** <img class="inline" src="images/copy-group.png"  alt="Bouton Copier">, puis positionnez le curseur à l'endroit où vous désirez insérer la tâche copiée et cliquez sur **Paste** <img class="inline" src="images/paste-group.png"  alt="Bouton Coller">.

Pour couper une tâche ou un groupe d'un plan de déploiement, sélectionnez la tâche et cliquez sur **Cut** <img class="inline" src="images/cut-group.png"  alt="Bouton Couper">.

Pour supprimer une tâche, sélectionnez-la et cliquez sur **Delete** <img class="inline" src="images/trash-group.png"  alt="Bouton Supprimer">. La tâche est supprimée du plan de déploiement.

## Création de tâches UrbanCode Deploy
{: #tasks_UDTasks}

Les tâches UrbanCode Deploy gèrent des applications UrbanCode Deploy. Lorsque vous lancez une tâche UrbanCode Deploy, l'application UrbanCode Deploy associée s'exécute en utilisant le processus, la version et l'environnement spécifiés par la tâche. Vous pouvez définir la version et l'environnement lors de la phase de conception ou attendre la phase d'exécution pour les sélectionner.

Lors des déploiements, les tâches UrbanCode Deploy démarrent automatiquement dès lors qu'elles deviennent éligibles pour leur exécution.   

**Important** : les applications deviennent disponibles une fois que {{site.data.keyword.uccr_short}} a été intégré avec UrbanCode Deploy. Les applications disponibles pour un plan de déploiement dépendent de l'équipe affectée à ce plan. Les applications gérées par l'équipe dans UrbanCode Deploy sont également disponibles dans {{site.data.keyword.uccr_short}}.

Pour créer une tâche UrbanCode Deploy, procédez comme suit. 

1. Sur la page Deployment Plan Details, cliquez sur **Create Task**. Si vous désirez insérer une tâche à un emplacement spécifique dans le plan, sélectionnez une tâche avant d'utiliser **Create Task**. La nouvelle tâche est insérée au-dessus de la tâche sélectionnée.

1. Dans la liste **Type** de la boîte de dialogue Create Task, sélectionnez **UrbanCode Deploy**.

1. Dans la zone **Name**, entrez un nom pour la tâche.

3. Dans la zone **Duration (minutes)**, entrez le nombre de minutes prévu pour exécution de la tâche jusqu'à son achèvement. La durée estimée est utilisée pour calculer la durée prévue pour le déploiement.

3. Dans la liste **Tags**, attachez une étiquette à la tâche. Vous pouvez sélectionner plusieurs étiquettes. Pour créer une étiquette, entrez son nom dans la zone de texte de la liste.

3. Dans la liste **Application Name**, sélectionnez une application.

3. Dans la liste **Process**, sélectionnez un processus d'application. Les processus relevant de l'application UrbanCode Deploy sélectionnée sont disponibles.

3. Dans la liste **Environment**, sélectionnez un environnement d'application. Les environnements qui relèvent de l'application UrbanCode Deploy sélectionnée sont disponibles. Pour différer la sélection d'un environnement jusqu'au lancement du déploiement, sélectionnez **Use Version Tab**.

3. Dans la liste **Version**, sélectionnez une version d'application. Les versions se réfèrent à des instantanés d'applications IBM UrbanCode Deploy. Les versions qui relèvent de l'application sélectionnée sont disponibles. Pour différer la sélection d'une version, sélectionnez **Use Version Tab**. Si le processus d'application n'exige pas une version, sélectionnez **No Version**. Vous pourriez sélectionner cette dernière option si vous exécutez un processus de type configuration ne nécessitant pas de composants.

3. Dans la liste **Assigned groups and users**, affectez la tâche à un utilisateur ou un groupe. L'utilisateur affecté à la tâche l'exécute lors du déploiement.

3. Dans la liste **Owner**, sélectionnez le propriétaire de la tâche. Le propriétaire par défaut est l'utilisateur qui a créé la tâche. La liste **Owner** est affichée une fois que la tâche a été affectée à un utilisateur ou à un groupe.    

5. Cliquez sur **Save**. La tâche est insérée dans le plan de déploiement.

Une fois la tâche créée, l'onglet **Version** du plan est mis à jour avec les informations sur l'application affectée à la tâche. Si vous avez sélectionné **Use Version Tab** pour l'environnement et la version de l'application, utilisez l'onglet Version pour configurer ces options avant de lancer le déploiement.

## Création de tâches manuelles
{: #tasks_manual}

En général, les tâches manuelles représentent les activités qui sont associées à une édition de logiciel et qui ont un point de départ, un point de fin et une durée mesurable.

Pour créer une tâche manuelle, procédez comme suit :

1. Sur la page Deployment Plan Details, cliquez sur **Create Task**. Si vous désirez insérer une tâche à un emplacement spécifique dans le plan, sélectionnez une tâche avant d'utiliser **Create Task**. La nouvelle tâche est insérée au-dessus de la tâche sélectionnée.

1. Dans la liste **Type** de la boîte de dialogue Create Task, sélectionnez **Manual**.

1. Dans la zone **Name**, entrez un nom pour la tâche.

3. Dans la zone **Duration (minutes)**, entrez le nombre de minutes prévu pour exécution de la tâche jusqu'à son achèvement. La durée estimée est utilisée pour calculer la durée prévue pour le déploiement.

3. Dans la liste **Tags**, attachez une étiquette à la tâche. Vous pouvez sélectionner plusieurs étiquettes. Pour créer une étiquette, entrez son nom dans la zone de texte de la liste.

3. Dans la liste **Assigned groups and users**, affectez la tâche à un utilisateur ou un groupe. L'utilisateur affecté à la tâche l'exécute lors du déploiement.

3. Dans la liste **Owner**, sélectionnez le propriétaire de la tâche. Le propriétaire par défaut est l'utilisateur qui a créé la tâche. La liste **Owner** est affichée une fois que la tâche a été affectée à un utilisateur ou à un groupe.    

5. Cliquez sur **Save**. La tâche est insérée dans le plan de déploiement.

## Création de tâches différées
{: #tasks_delayed}

Les tâches différées représentent des événements clés ou critiques lors d'un déploiement. Elles permettent de s'assurer que les tâches importantes commencent à l'heure prévue. Généralement, les tâches différées sont des prérequis pour d'autres tâches importantes.

Une tâche différée démarre dès qu'elle est éligible à l'exécution et se termine à une heure spécifiée par l'utilisateur. Le statut d'une tâche de type "différée" dont l'exécution a commencé indique `In Progress` jusqu'à ce qu'elle parvienne à son heure planifiée et passe alors au statut `Complete`. A l'achèvement d'une tâche différée, les tâches automatiques qui en dépendent commencent à s'exécuter.

Pour créer une tâche différée, procédez comme suit :

1. Sur la page Deployment Plan Details, cliquez sur **Create Task**. Si vous désirez insérer une tâche à un emplacement spécifique dans le plan, sélectionnez une tâche avant d'utiliser **Create Task**. La nouvelle tâche est insérée au-dessus de la tâche sélectionnée.

1. Dans la liste **Type** de la boîte de dialogue Create Task, sélectionnez **Delayed**.

1. Dans la zone **Name**, entrez un nom pour la tâche.

3. Dans la zone **Time**, saisissez ou sélectionnez l'heure à laquelle la tâche sera terminée.

3. Dans la liste **Time Zone**, sélectionnez le fuseau horaire pour la valeur saisie dans la zone **Time**.    

5. Cliquez sur **Save**. La tâche est insérée dans le plan de déploiement.

## Création de tâches d'en-tête
{: #tasks_header}

Les tâches d'en-tête représentent des éléments organisationnels que vous pouvez ajouter à des plans de déploiement. Si vous créez un groupe de tâches, vous pouvez l'identifier à l'aide d'une tâche d'en-tête. Les tâches d'en-tête peuvent avoir des dépendances comme n'importe quelle autre tâche.

Lorsque vous importez un plan de déploiement depuis IBM UrbanCode Release, les tâches de segment sont délimitées par les annotations de tâches Start Segment et End Segment. Les dépendances de segment sont représentées par des dépendances à des tâches End Segment.

Pour créer une tâche d'en-tête, procédez comme suit :

1. Sur la page Deployment Plan Details, cliquez sur **Create Task**. Si vous désirez insérer une tâche à un emplacement spécifique dans le plan, sélectionnez une tâche avant d'utiliser **Create Task**. La nouvelle tâche est insérée au-dessus de la tâche sélectionnée.

1. Dans la liste **Type** de la boîte de dialogue Create Task, sélectionnez **Header**.

1. Dans la zone **Name**, entrez un nom pour la tâche. Le nom peut représenter un groupe de tâches.

3. Dans la zone **Description**, entrez ou collez une description. Vous pouvez entrer dans cette zone une remarque, un rappel, ou d'autres instructions.

5. Cliquez sur **Save**. La tâche est insérée dans le plan de déploiement.

## Création de tâches de pipeline Continuous Delivery
{: #tasks_pipelineCD}

Les pipelines {{site.data.keyword.contdelivery_full}} permettent d'automatiser vos flux de travaux DevOps. Un pipeline est une séquence de phases qui extraient des entrées et exécutent des travaux. Vous pouvez gérer vos pipelines {{site.data.keyword.contdelivery_short}} à l'aide de tâches de pipeline. Les tâches de pipeline Continuous Delivery sont des tâches automatiques qui s'exécutent dès lors qu'elles sont éligibles.

Pour créer une tâche de pipeline Continuous Delivery, procédez comme suit :

1. Sur la page Deployment Plan Details, cliquez sur **Create Task**. Si vous désirez insérer une tâche à un emplacement spécifique dans le plan, sélectionnez une tâche avant d'utiliser **Create Task**. La nouvelle tâche est insérée avant la tâche sélectionnée.

1. Dans la liste **Type** de la boîte de dialogue Create Task, sélectionnez **Pipeline Continuous Delivery**.

1. Dans la zone **Name**, entrez un nom pour la tâche.

3. Dans la zone **Description**, entrez ou collez une description. Vous pouvez entrer dans cette zone une remarque, un rappel, ou d'autres instructions.

3. Dans la zone **Pipeline**, entrez ou sélectionnez le pipeline. 

3. Dans la zone **Stage Name**, entrez ou sélectionnez le nom de la phase. Les phases définies pour le pipeline sélectionné sont disponibles.

3. Dans la liste **Tags**, attachez une étiquette à la tâche. Vous pouvez sélectionner plusieurs étiquettes. Pour créer une étiquette, entrez son nom dans la zone de texte de la liste.

3. Dans la liste **Assigned groups and users**, affectez la tâche à un utilisateur ou un groupe. L'utilisateur affecté à la tâche l'exécute lors du déploiement.

3. Dans la liste **Owner**, sélectionnez le propriétaire de la tâche. Le propriétaire par défaut est l'utilisateur qui a créé la tâche. La liste **Owner** est affichée une fois que la tâche a été affectée à un utilisateur ou à un groupe.    

5. Cliquez sur **Save**. La tâche est insérée dans le plan de déploiement.

Lorsqu'une tâche de pipeline Continuous Delivery est lancée, elle exécute les travaux de la phase spécifiée pour le pipeline sélectionné.

## Création de tâches de courrier électronique
{: #tasks_email}

Une tâche de courrier électronique envoie un message électronique lorsqu'elle s'exécute. Vous devez spécifier le message et ses destinataires lorsque vous créez la tâche. Les tâches de courrier électronique sont des tâches automatiques qui s'exécutent dès lors qu'elles sont éligibles.

Pour créer une tâche de courrier électronique, procédez comme suit :

1. Sur la page Deployment Plan Details, cliquez sur **Create Task**. Si vous désirez insérer une tâche à un emplacement spécifique dans le plan, sélectionnez une tâche avant d'utiliser **Create Task**. La nouvelle tâche est insérée avant la tâche sélectionnée.

1. Dans la liste **Type** de la boîte de dialogue Create Task, sélectionnez **Email**.

1. Dans la zone **Name**, entrez un nom pour la tâche.

3. Dans la zone **Recipients**, entrez ou sélectionnez le destinataire du courrier électronique. La liste des destinataires disponibles inclut les utilisateurs et les groupes qui sont membres de votre équipe. Vous pouvez également indiquer l'adresse électronique d'utilisateurs qui ne sont pas membres de l'équipe. Vous pouvez spécifier plusieurs destinataires. 

3. Dans la zone **Email subject**, entrez l'objet du courrier électronique.

3. Dans la zone **Email message**, entrez ou collez le message électronique.

5. Cliquez sur **Save**. La tâche est insérée dans le plan de déploiement.

Lorsque la tâche s'exécute, les utilisateurs reçoivent un courrier électronique envoyé par **IBM Continuous Release** avec l'objet spécifié lorsque vous avez créé la tâche.

## Création de tâches de type Exécution d'un autre plan
{: #tasks_runAnother}

Une tâche de type Exécution d'un autre plan lance le déploiement d'un autre plan de déploiement. Le plan ciblé doit être créé depuis un modèle. Le modèle et le plan ciblé doivent exister dans le même événement de publication de logiciel que la tâche d'exécution de l'autre plan.

Notez qu'il s'agit ici d'un type de tâche expérimental.

Pour créer une tâche d'exécution d'un autre plan, procédez comme suit :

1. Sur la page Deployment Plan Details, cliquez sur **Create Task**. Si vous désirez insérer une tâche à un emplacement spécifique dans le plan, sélectionnez une tâche avant d'utiliser **Create Task**. La nouvelle tâche est insérée avant la tâche sélectionnée.

1. Dans la liste **Type** de la boîte de dialogue Create Task, sélectionnez **Run another plan**.

1. Dans la zone **Name**, entrez un nom pour la tâche.

3. Dans la liste **Plan Template Name**, sélectionnez un modèle de plan de déploiement. Le modèle doit exister dans le même événement de publication de logiciel que le plan parent de la tâche.

3. Dans la liste **Tags**, attachez une étiquette à la tâche. Vous pouvez sélectionner plusieurs étiquettes. Pour créer une étiquette, entrez son nom dans la zone de texte.

5. Cliquez sur **Save**. La tâche est insérée dans le plan de déploiement.

Lorsque la tâche est exécutée, un déploiement est lancé pour le plan de déploiement créé depuis le modèle sélectionné et dans le même événement de publication de logiciel. Si plusieurs plans dans l'événement de publication de logiciel ont été créés depuis le modèle, le déploiement est lancé pour tous ces plans. Tandis que les autres déploiements s'exécutent, des informations de statut sont fournies par la tâche d'exécution de l'autre plan. Développez la tâche pour examiner les informations de statut. Vous pouvez ouvrir les autres déploiements à l'aide des liens sur la tâche. Alors que les autres déploiements s'exécutent, le statut de la tâche d'exécution d'un autre plan indique **In Progress**.

## Création de tâches Slack
{: #tasks_slack}

Une tâche Slack envoie un message à un canal Slack lorsqu'elle s'exécute. Le message peut contenir du texte et des liens hypertexte. Une tâche Slack démarre dès qu'elle est éligible à l'exécution. 

Pour créer une tâche Slack, procédez comme suit :

1. Sur la page Deployment Plan Details, cliquez sur **Create Task**. Si vous désirez insérer une tâche à un emplacement spécifique dans le plan, sélectionnez une tâche avant d'utiliser **Create Task**. La nouvelle tâche est insérée avant la tâche sélectionnée.

1. Dans la liste **Type** de la boîte de dialogue Create Task, sélectionnez **Slack**.

1. Dans la zone **Name**, entrez un nom pour la tâche.

3. Dans la zone **Webhook URL**, entrez l'URL du canal Slack où vous désirez distribuer le message. Par exemple, `https://hooks.slack.com/services/my_webhook`.

3. Dans la zone **Message**, entrez le corps du message. Le message peut contenir du texte et des liens hypertexte. 

3. Dans la zone **Duration (minutes)**, entrez le nombre de minutes prévu pour exécution de la tâche jusqu'à son achèvement. La durée estimée est utilisée pour calculer la durée prévue pour le déploiement.

3. Dans la liste **Tags**, attachez une étiquette à la tâche. Vous pouvez sélectionner plusieurs étiquettes. Pour créer une étiquette, entrez son nom dans la zone de texte.

3. Dans la liste **Assigned groups and users**, affectez la tâche à un utilisateur ou un groupe. L'utilisateur affecté à la tâche l'exécute lors du déploiement.

5. Cliquez sur **Save**. La tâche est insérée dans le plan de déploiement.

Lorsque la tâche s'exécute, le message défini dans la zone Message est envoyé au canal Slack spécifié dans la zone Webhook URL.

## Gestion des groupes de tâches
{: #tasks_groups}

Vous pouvez combiner deux tâches, ou plus, dans un groupe de tâches. Lorsque vous créez un groupe, vous devez définir son schéma d'exécution : séquentiel ou parallèle. Vous pouvez exécuter les tâches d'un groupe avec schéma parallèle dans n'importe quel ordre et, en l'absence de dépendances, simultanément. Les tâches d'un groupe séquentiel sont réalisées dans l'ordre de la liste, en commençant par la première ou celle située tout en haut.

Vous pouvez imbriquer des groupes dans d'autres groupes. Vous pouvez imbriquer un groupe de masque séquentiel dans un groupe de masque parallèle, et inversement. Toutefois, vous ne pouvez pas imbriquer un groupe avec schéma séquentiel dans un autre du même type, ou un groupe avec schéma parallèle dans un autre du même type.  

Pour créer un groupe de tâches, procédez comme suit.

1. Sur la page Deployment Plan Detail, sélectionnez au moins deux tâches.

1. Procédez comme suit selon le type de groupe que vous désirez créer.

  <ul>
  <li>Pour créer un groupe parallèle, cliquez sur le bouton **Parallel** <img class="inline" src="images/para-icon.png"  alt="Bouton Groupe parallèle">. Si vous ne pouvez pas créer un groupe parallèle avec les tâches sélectionnées, le bouton est désactivé. Il se peut que vous ne puissiez pas créer un groupe parallèle, par exemple, si toutes les tâches sélectionnées font déjà partie d'un tel groupe.</li>
  <li>Pour créer un groupe séquentiel, cliquez sur le bouton **Sequential** <img class="inline" src="images/seq-icon.png"  alt="Bouton Groupe séquentiel">. </li>
  </ul>

Le groupe est constitué et une **barre de sélection de groupe ** est ajoutée au plan de déploiement. Si vous aviez sélectionné des tâches discontinues, les tâches forment une liste contiguë commençant par la plus haute.

La figure ci-dessous montre un groupe parallèle. La **barre de sélection de groupe** identifie le type du groupe : parallèle <img class="inline" src="images/para-select.png"  alt="sélection de groupe parallèle"> ou séquentiel <img class="inline" src="images/seq-select.png"  alt="sélection de groupe séquentiel">.

![](images/group-select.png "Plan de déploiement usuel")

Figure 2. Groupe parallèle

Pour déplacer un groupe, sélectionnez la **barre de sélection de groupe** ou cliquez n'importe où sur le groupe, puis faites-le glisser vers son nouvel emplacement.

Pour copier un groupe, sélectionnez le groupe et cliquez sur **Copy** <img class="inline" src="images/copy-group.png"  alt="Bouton Copy">, puis positionnez le curseur à l'endroit où vous désirez insérer le groupe copié et cliquez sur **Paste** <img class="inline" src="images/paste-group.png"  alt="Bouton Paste">.

Pour couper un groupe, sélectionnez-le, puis cliquez sur **Cut** <img class="inline" src="images/cut-group.png"  alt="Bouton Cut">.

Pour désagréger un groupe, sélectionnez-le et cliquez sur l'icône **Ungroup** <img class="inline" src="images/ungroup-icon.png"  alt="Icône Ungroup"> sur le **barre de sélection du groupe**.

Pour supprimer les tâches d'un groupe, sélectionnez-le et cliquez sur **Delete** <img class="inline" src="images/trash-group.png"  alt="Bouton Delete">. Les tâches sont supprimées du plan de déploiement.

## Gestion des étiquettes de tâche
{: #tasks_tags}

Les étiquettes sont des éléments organisationnels que vous pouvez ajouter à des tâches. Vous pouvez filtrer des plans de déploiement par étiquette. Par exemple, lors d'un déploiement en environnement de production, vous pourriez désactiver les tâches dotées d'une étiquette `DEV_only` tag, lesquelles sont destinées à être utilisées uniquement dans des environnements de développement.

Pour ajouter une étiquette à une tâche, procédez comme suit.

1. Sur la page Deployment Plan Details, sélectionnez une tâche ou un groupe de tâches, puis cliquez sur **Manage Tags**  <img class="inline" src="images/task-tag.png"  alt="Bouton Manage tags">. Vous pouvez sélectionner plusieurs tâches et groupes.

1. Sélectionnez des étiquettes dans la liste **Common Tags** de la boîte de dialogue Manage Tags for Selected Tasks. Vous pouvez créer une nouvelle étiquette en entrant un nom dans la zone de texte de la liste.

1. Cliquez sur **Save**. 

Les étiquettes sont affichées sur les lignes de tâches dans la page Deployment Plan Detail. Dans l'illustration ci-dessous, la tâche **Deploy WAR** comporte deux étiquettes qui lui sont affectées : `Deployment` et `Critical`.

Les étiquettes utilisées par un plan de déploiement sont affichées sous l'onglet **Versions** de la page Deployment Plan Detail. Pour désigner des tâches dotées d'une étiquette spécifique comme `Not Applicable` pour un déploiement, décochez leur étiquette. Les tâches dont le statut indique `Not Applicable` ne peuvent pas être lancées.  

![](images/task-tag-labels.png "Plan de déploiement usuel")

Figure 3. Dépendances de tâche

## Création de dépendances de tâche
{: #tasks_dependencies}

Vous pouvez faire d'une tâche une condition préalable requise pour d'autres tâches. Si une tâche constitue un prérequis, les tâches qui en sont dépendantes ne peuvent pas démarrer, même si par ailleurs elles seraient éligibles, jusqu'à ce que la tâche prérequise ait été résolue.

Une tâche peut avoir plusieurs tâches dépendantes et plusieurs tâches prérequises. Vous pouvez définir des dépendances pour une tâche par rapport à une autre tâche dans le plan de déploiement. Cependant, vous ne pouvez pas créer de dépendances circulaires. Vous ne pouvez pas, par exemple, rendre une tâche dépendante d'une autre qui elle-même est tributaire de la première.

En contrôlant les dépendances de tâche, vous pouvez vous assurer que les événements se produisent dans l'ordre prévu.

Pour désigner une tâche comme prérequis d'autres tâches, procédez comme suit :

1. Sur la page Deployment Plan Details, sélectionnez une tâche ou un groupe de tâches, puis cliquez sur **Manage Prerequisites** <img class="inline" src="images/task-depend.png"  alt="Bouton Task prerequisite">. Vous pouvez sélectionner plusieurs tâches et groupes.

1. Dans la liste **Prerequisite tasks for selected tasks** de la boîte de dialogue Manage Prerequisites for Selected Tasks, sélectionnez la tâche prérequise.

1. Cliquez sur **Save**. 

Les dépendances de tâche figurent dans la colonne **Dependencies** sur la page Deployment Plan Detail. Les flèches vers le haut indiquent les prérequis pour les tâches, tandis que les flèches vers le bas indiquent les dépendances de tâche.

Dans la figure ci-dessous, la première tâche n'a aucun prérequis et deux tâches en sont dépendantes. Le seconde tâche comporte une tâche en prérequis et n'a pas de tâches qui en sont dépendantes.

(![](images/plan-w-depend.png "Typical deployment plan"))

Figure 4. Dépendances de tâche

Pour examiner ou modifier des dépendances, sélectionnez la tâche, puis cliquez sur **Manage Prerequisites** <img class="inline" src="images/task-depend.png"  alt="Bouton Task prerequisite">. Utilisez la boîte de dialogue Manage Prerequisites for Selected Tasks pour modifier ou retirer des dépendances.
