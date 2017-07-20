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

# Gestion des plans de déploiement
{: #plan_overview}

Un plan de déploiement est un conteneur de tâches. Les tâches définissent les activités effectuées par votre équipe pour réaliser un déploiement de logiciel.

{:shortdesc}

Vous créez un plan de déploiement en affectant une équipe pour le gérer, puis an ajoutant des tâches au plan. Les membres de l'équipe concernée ajoutent des tâches au plan et réalisent les tâches lors du déploiement. L'équipe de gestion détermine également les applications IBM UrbanCode Deploy disponibles. Une fois qu'une intégration a été configurée avec DevOps Connect, toutes les applications gérées par l'équipe dans IBM UrbanCode Deploy sont disponibles dans {{site.data.keyword.uccr_short}}.  

Les tâches définissent les activités effectuées par l'équipe pour réaliser un déploiement. Vous pouvez créer de nouvelles tâches, ajouter des tâches depuis d'autres plans de déploiement ou importer des tâches à partir de fichiers CSV. Lorsque vous êtes satisfait du plan, vous pouvez planifier un déploiement. Vous pouvez également exécuter un déploiement à n'importe quel moment en lançant l'une des tâches du plan.

Les tâches sont affichées sur des lignes distinctes dans les plans de déploiement. Chaque ligne contient des informations qui identifient la tâche et indiquent son statut. Chaque ligne comporte également des icônes d'action utilisées lors des déploiements, telles que la tâche **Start** ou la tâche **Skip**. 

Par défaut, les tâches sont exécutées séquentiellement, à compter de la première, ou de la plus haute, dans le plan. Lorsque la première s'achève, la seconde devient éligible pour son exécution, et ainsi de suite. L'ordre d'éligibilité des tâches pour leur lancement est dénommé ordre d'exécution.

L'ordre d'exécution peut être modifié en combinant des tâches dans des groupes. [Lorsque vous créez un groupe](/docs/services/UCCR/UCCR_tasks.html#tasks_groups), vous définissez le schéma d'exécution du groupe, à savoir séquentiel ou parallèle. Dans le cas d'un groupe avec schéma d'exécution séquentiel, ses tâches sont lancées séquentiellement en commençant par la première. Le schéma d'exécution par défaut d'un plan de déploiement est le schéma séquentiel. Dans le cas d'un groupe avec schéma d'exécution parallèle, ses tâches peuvent commencer dans n'importe quel ordre et s'exécuter simultanément. Si un plan est composé entièrement de tâches parallèles, vous pouvez lancer n'importe quelle tâche, quelque soit sa position dans la liste.

L'éligibilité des tâches peut également être affectée par des dépendances de tâche. [Si une tâche a des prérequis](/docs/services/UCCR/UCCR_tasks.html#tasks_dependencies), elle ne peut pas démarrer, même si par ailleurs elle était éligible, jusqu'à ce que toutes ses tâches prérequises aient été réalisées.

Certaines tâches démarrent automatiquement dès qu'elles sont éligibles pour leur exécution, tandis que d'autres sont lancées manuellement. Le type de la tâche détermine si elle peut démarrer automatiquement. Les tâches manuelles, comme leur nom l'indique, sont lancées manuellement. Les tâches de type UrbanCode Deploy ou Différée démarrent automatiquement dès lors qu'elles sont éligibles.

Les tâches éligibles affichent un bouton **Start Task**. Pour lancer un déploiement, vous devez déclencher l'une des tâches éligibles du plan. Les déploiements planifiés débutent automatiquement au moment planifié si une tâche éligible de leur plan correspond à un type pouvant démarrer automatiquement, comme UrbanCode Deploy.

## Création de plans de déploiement
{: #plan_create}
Vous pouvez commencer par un plan vierge, lequel ne comporte pas encore de tâches définies, ou bien copier un plan existant. Vous pouvez également partir d'un modèle de plan. Lorsque vous copiez un plan ou utilisez un modèle, de nombreuses tâches sont déjà définies.

Pour créer un plan de déploiement, procédez comme suit :

1. Sur la page Releases ou la page Release Detail, cliquez sur **Create Deployment Plan**.

2. Dans la liste **Template** de la fenêtre Create Deployment Plan, spécifiez le modèle sur lequel baser le plan. La valeur par défaut est **None**.

2. Dans la zone **Plan name**, entrez un nom pour le plan.

3. Dans la liste **Team**, sélectionnez l'équipe qui gérera le plan. Toutes les équipes dont vous êtes membre dont disponibles. Les membres de l'équipe peuvent modifier la plan et gérer ses tâches. Les applications UrbanCode Deploy gérées par l'équipe dans UrbanCode Deploy sont disponibles pour leur affectation à des tâches de ce type.

4. Pour planifier un déploiement pour le plan, cliquez sur **Start time**, puis sélectionnez une date et heure pour le déploiement. Les déploiements planifiés sont lancés automatiquement au moment prévu si leur plan comporte des tâches automatiques éligibles. Vous pouvez planifier un déploiement pour une date future de votre choix.

5. Dans la liste **Release**, sélectionnez l'édition à laquelle ajouter le plan. Les éditions dont est propriétaire l'une de vos équipes sont disponibles. Si vous sélectionnez une édition, le plan de déploiement est affiché sur la page Release Detail.

6. Cliquez sur **Save**. Si vous avez créé le plan sur une page Release Detail, le plan fait partie de l'édition sélectionnée.

Après avoir sauvegardé le plan, cliquez sur **Edit** pour modifier ses détails.

## Importation de tâches dans des plans de déploiement
{: #plan_importTasks}

Vous pouvez importer dans un plan de déploiement des tâches qui ont été définies dans des fichiers CSV. Vous pouvez utiliser des fichiers CSV exportés depuis IBM UrbanCode Release ou depuis n'importe quelle application capable de créer de tels fichiers.

**Important :** lorsque vous importez des tâches, celles déjà définies dans le plan de déploiement sont écrasées et remplacées par celles figurant dans le fichier CSV.

Pour importer des tâches dans un plan de déploiement, procédez comme suit.

1. Sur la page Deployment Plan Details, cliquez sur **Import Tasks**.

3. Dans la boîte de dialogue Import Tasks, cliquez sur **Choose File**, puis sélectionnez le fichier CSV. Vous pouvez également faire glisser un fichier dans la zone **Choose File**.

6. Cliquez sur **Import**. Les tâches sont ajoutées au plan de déploiement. Si la procédure d'importation échoue, cliquez sur **View Report** pour examiner le journal des erreurs.

Lorsque vous importez un plan de déploiement depuis IBM UrbanCode Release, les segments sont convertis en groupes avec le même schéma d'exécution que les segments d'origine. Les tâches de segment sont délimitées par les annotations de tâches Start Segment et End Segment. Les dépendances de tâche sont préservées par la procédure d'importation. Les dépendances de segment sont représentées par des dépendances à des tâches End Segment.

Le tableau suivant recense les zones qui définissent une tâche dans un plan de déploiement IBM UrbanCode Release. La première ligne du fichier CSV contient les en-têtes de colonne, lesquels correspondent à la colonne **Zone** dans le tableau. Les lignes après la première contiennent les données de tâche, avec une tâche par ligne. L'ordre des colonnes n'a pas d'importance.

Pour vous familiariser avec les plans de déploiement exportés depuis IBM UrbanCode Release, téléchargez le fichier `SamplePlan.csv` depuis la boîte de dialogue Import Tasks.

Si vous créez des tâches dans un fichier CSV, vous devez inclure les zones obligatoires identifiées par un astérisque (*) dans le tableau ci-dessous.

| Zone  | Description  |
| ------------------ |------------------|
|segmentName*                 |Nom du segment. Zone obligatoire.|                                                    
|name*                        |Nom de la tâche de déploiement. Zone obligatoire.|                                                                
|type*                        |Type de tâche. Valeurs possibles : `note`, `waitfortimetask`, `ucdtask`, `manual`. Lors de l'importation, si la zone contient une valeur non reconnue, le type `manual est affecté à la tâche.|
|description                 |Description du plan de déploiement.|                                                                                                    
|property:processId           |ID de processus dans IBM UrbanCode Deploy qui correspond à la tâche.|
|property:task-environments   |Environnements d'application disponibles pour la tâche.|
|property:mailRecipients|Adresses électroniques des utilisateurs recevant des courriers électroniques lorsque des notifications sont envoyées.|
|taskTagNames                 |Noms des étiquettes associées à la tâche.|
|taskPrequisiteIds         |Liste séparée par des virgules des ID de tâches devant être réalisées avant que la tâche puisse démarrer.|
|segmentPrerequisitelds       |Liste séparée par des virgules des ID de segments envers lesquels le segment actuel est sujet à des dépendances.|
|taskPrequisiteNames         |Liste séparée par des virgules des noms de tâches devant être réalisées avant que la tâche puisse démarrer.|
|segmentPrerequisiteNames       |Liste séparée par des virgules des noms de segments envers lesquels le segment actuel est sujet à des dépendances.|
|assignedUserEmail                |Adresse électronique de l'utilisateur affecté à la tâche actuelle.|
|executorGroup                |Groupe d'utilisateurs affecté à la tâche actuelle.|
|segmentPattern                |Schéma d'exécution du segment sélectionné.|

{: caption="Table 1. Zones du plan de déploiement IBM UrbanCode Release" caption-side="top"}

## Copie et promotion de plans de déploiement
{: #plan_copyPromote}

Vous pouvez dupliquer des plans de déploiement via une promotion et copie de ces plans. Le statut d'un plan copié ou promu indique '`draft`' même si le statut du plan d'origine correspond à '`done`' ou à '`in progress`'.

Pour copier un plan, utilisez l'action **Copy this plan** sur la page Deployment Plan. Lorsque vous copiez un plan, un nouveau plan nommé "Copy of `nom_plan`" est inséré sur la page Deployment Plan. Le plan copié contient toutes les tâches définies dans le plan d'origine. Si des tâches UrbanCode Deploy figurent dans le plan, les applications, les versions, et les environnements sélectionnés dans le plan d'origine sont également sélectionnés dans le plan copié. Les applications, versions, et environnements sont affichés dans l'onglet **Versions** de la page Deployment Plan Detail.

Pour promouvoir un plan, utilisez l'action **Promote this plan** sur la page Deployment Plan. Lorsque vous promouvez un plan, un nouveau plan nommé "Promotion of `nom_plan`" est inséré dans la page Deployment Plan. Le plan promu contient toutes les tâches définies dans le plan d'origine. Si des tâches UrbanCode Deploy figurent dans le plan, les applications et les versions sélectionnées dans le plan d'origine sont également sélectionnées dans le plan promu. La différence entre les plans copiés et les plans promus tient à ce que les versions d'application ne sont pas définies dans les plans promus.

## Gestion des modèles de plan
{: #plan_templates}

Vous pouvez convertir des plans de déploiement afin de créer des modèles de plan de déploiement.

Pour créer un modèle, utilisez l'action **Template this plan** sur la page Deployment Plan. Lorsque vous créez un modèle, un nouveau plan nommé "Copy of nom_plan' est inséré dans la page Deployment Plan. Le statut du modèle indique '`template`' même si celui du plan d'origine correspond à '`done`' ou à '`in progress`'. Le modèle contient toutes les tâches définies dans le plan d'origine. Si des tâches UrbanCode Deploy figurent dans le plan, les applications sélectionnées dans le plan d'origine sont également sélectionnées dans le modèle. 

Vous ne pouvez pas effectuer des déploiements à l'aide de modèles. Pour utiliser un modèle pour un déploiement, vous devez d'abord copier ou promouvoir le modèle, puis utiliser le plan copié ou promu.

## Archivage de plans de déploiement
{: #plan_arch}

Lorsque vous placez un plan de déploiement dans une archive, le statut du plan indique '`Archived`' et le plan n'est pas affiché sur la page Deployment Plan à moins que vous n'utilisiez le filtre **Archive**.

Les plans de déploiement conservés dans l'archive peuvent être restaurés au statut '`draft`'. Vous ne pouvez pas supprimer définitivement un plan de déploiement.

## Rétablissement et restauration
{: #plan_history}

Un historique des modifications et des révisions est conservé pour chaque plan de déploiement. Vous pouvez examiner les révisions dans l'onglet **Change History** de la page Deployment Plan Detail.

Pour revenir à une version antérieure d'un plan, utilisez l'action **Restore** <img class="inline" src="images/restore-icon.png"  alt="Action Restaurer"> correspondant à la version que vous désirez restaurer. Le plan est restauré à la version sélectionnée.  

## Estimation de la durée du déploiement
{: #plan_durationEst}

Lorsque vous lancez un déploiement, vous pouvez estimer la durée prévue de l'opération. Pour estimer cette durée, utilisez l'action **Estimate Task Times** sur la page Deployment Plan Detail. L'heure estimée correspond à l'heure où devrait s'achever le déploiement si vous lancez l'opération maintenant.
