---

copyright:
 years: 2017
lastupdated: "2017-6-22"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}

# Exécution de déploiements 
{: #deployment_run}

Utilisez {{site.data.keyword.uccr_short}} pour exécuter des déploiements de logiciels. Complétez les déploiements en résolvant les tâches du plan de déploiement.
{:shortdesc}

Un déploiement est déclenché lorsque l'une des tâches éligibles du plan est lancée. Un déploiement planifié démarre automatiquement à la date/heure planifiée si l'une de ses tâches éligibles est une tâche automatique, par exemple une tâche UrbanCode Deploy ou une tâche de type Différé. Autrement, vous pouvez déclencher un déploiement en lançant l'une des tâches éligibles du plan. Si le plan contient plusieurs tâches éligibles, vous pouvez lancer n'importe laquelle de celles-ci. Vous pouvez lancer manuellement un déploiement à n'importe quel moment. Vous pouvez lancer manuellement un déploiement planifié avant la date/heure pour laquelle il était programmé.   

Le schéma du plan de déploiement détermine quand des tâches sont éligibles pour leur exécution. Si le plan suit le schéma d'exécution séquentiel (le schéma par défaut), les tâches deviennent éligibles dans l'ordre où elles sont listées par le plan, en commençant par la première tâche. Après la résolution de la première tâche, la seconde devient éligible. Les tâches manuelles éligibles sont lancées en cliquant sur le bouton **Start**. Les tâches automatiques, telles que les tâches UrbanCode Deploy, démarrent automatiquement aussitôt qu'elles deviennent éligibles.

Les tâches d'un groupe avec schéma d'exécution parallèle deviennent éligibles simultanément. Ces tâches peuvent être lancées dans n'importe quel ordre. Les groupes imbriqués et les tâches avec des dépendances ad hoc peuvent affecter le schéma d'exécution.

Vous pouvez modifier un plan de déploiement après avoir lancé un déploiement. Vous pouvez ajouter, supprimer et modifier des tâches.

Une fois que toutes les tâches ont été résolues, le déploiement est complet. Une tâche est résolue si son statut indique `Complete` (complétée), `Failed` (échec) ou `Skipped` (Ignorée). Si vous rouvrez une tâche ou ajoutez une tâche après que le déploiement est complet, le statut du déploiement passe à `In Progress` (en cours).

## Lancements manuels de déploiements
{: #deployment_start}

Vous pouvez lancer manuellement un déploiement à n'importe quel moment, y-compris des déploiements planifiés pour un démarrage ultérieur.

Les tâches d'un plan de déploiement peuvent être inapplicables pour le déploiement. Les tâches UrbanCode Deploy sont inapplicables si aucune version ou environnement n'ont été spécifiés pour les tâches. Lorsque vous créez des tâches UrbanCode Deploy, vous pouvez reporter la sélection de l'environnement et de l'environnement à l'aide de l'option **Use Version**. Avant le démarrage du déploiement, vérifiez que toutes les tâches UrbanCode Deploy sont applicables pour le déploiement qui suivra.    

Vous pouvez exclure délibérément des tâches d'un déploiement. Vous pouvez désigner comme inapplicables des tâches sélectionnées en excluant leurs étiquettes du déploiement. Les tâches dont les étiquettes sont exclues sont inapplicables pour le déploiement.  

Le statut des tâches inapplicables indique `Not Applicable`. Les tâches avec le statut `Not Applicable` ne peuvent pas être lancées. Si une tâche inapplicable constitue un prérequis pour une tâche active, cette dépendance est ignorée.  

Pour lancer un déploiement, procédez comme suit :

1. Sur la page Deployment Plans, cliquez sur le plan de déploiement que vous désirez utiliser pour le déploiement. La page des détails du déploiement s'affiche.

2. Vous pouvez désigner comme inapplicables des tâches sélectionnées pour le déploiement actuel en cliquant sur **Versions**, puis en les désélectionnant dans la zone **Tags**. Si une tâche a plusieurs étiquettes, désélectionnez toutes ces étiquettes.

2. Pour sélectionner la version ou l'environnement pour des tâches UrbanCode Deploy inapplicables, cliquez sur **Versions**, puis sélectionnez l'environnement et la version. Vous pouvez également modifier vos choix pour des tâches dont l'environnement et la version ont déjà été sélectionnés.

1. Vous pouvez cliquer sur **Hide Not Applicable Tasks** pour retirer de la liste affichée des tâches inapplicables. Les tâches masquées ne sont pas supprimées du plan de déploiement.

1. Cliquez sur l'action **Start** <img class="inline" src="images/task-start.png"  alt="Action de lancement de tâche"> d'une des tâches éligibles du plan. Si plusieurs tâches sont éligibles, vous pouvez lancer celle de votre choix. Le bouton de lancement n'est affiché que pour les tâches éligibles. Le statut d'une tâche lancée affiche '`In Progress`' jusqu'à sa résolution.

Après le lancement d'un plan, son statut affiche '`In Progress`'. Le statut '`In Progress`' persiste jusqu'à ce que toutes les tâches aient été résolues. Une fois que toutes les tâches ont été résolues, le statut du plan passe à '`Done`'.

## Résolution de tâches
{: #deployment_taskComplete}

Le déploiement s'achève une fois que toutes ses tâches ont été complétées. Une tâche lancée est dite résolue lorsque son statut passe à `Complete` (complétée) , `Failed` (échec) ou `Skipped` (ignorée).

Les tâches manuelles sont résolues via l'action d'attribution de statut appropriée. Les tâches automatiques, telles que les tâches UrbanCode Deploy, changent de statut automatiquement avec la modification de la situation. Vous pouvez toutefois résoudre manuellement les tâches automatiques. Vous pourriez, par exemple, affecter manuellement un statut d'échec à une tâche UrbanCode Deploy dont l'exécution est trop longue.

Pour résoudre une tâche lancée,  attribuez-lui l'un des statuts suivants :

<ul>
<li>Cliquez sur **Complete** (complétée) <img class="inline" src="images/task-complete.png"  alt="Action Tâche complète"> pour terminer une tâche. `Complete` signifie que la tâche s'est terminée avec les résultats escomptés.
</li>
<li>Cliquez sur **Skip** (ignorer) <img class="inline" src="images/task-skip.png"  alt="Action Tâche ignorée"> pour ignorer une tâche dans le déploiement en cours.
</li>
<li>Cliquez sur **Fail** (échec) <img class="inline" src="images/task-fail.png"  alt="Action Echec de la tâche"> pour mettre un terme à la tâche. `Fail` signifie que la tâche ne s'est pas terminée ou s'est achevée avec des résultats imprévus.
</li>
<li>Cliquez sur **Task Reopen** (réouverture de la tâche) <img class="inline" src="images/task-reopen.png"  alt="Tâche Réouverture de la tâche"> pour ouvrir une tâche résolue. Si toutes les tâches ont été achevées, la réouverture d'une tâche rouvre le déploiement.
</li>
</ul>

## Exécution de déploiements planifiés
{: #deployment_startSchedule}

Un déploiement planifié démarre automatiquement à la date/heure planifiée si l'une de ses tâches automatiques est éligible pour son démarrage. Si un plan de déploiement ne comporte aucune tâche automatique éligible, vous pouvez déclencher son déploiement en lançant manuellement l'une des tâches éligibles.

Vous pouvez lancer manuellement à n'importe quel moment un déploiement planifié même si son plan est associé à des tâches automatiques éligibles.
