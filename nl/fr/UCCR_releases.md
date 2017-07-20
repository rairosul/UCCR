---

copyright:
 years: 2017
lastupdated: "2017-6-22"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}

# A propos des éditions
{: #releases_overview}

Une édition est un conteneur hébergeant des plans de déploiement, des événements et des étiquettes.

{:shortdesc}

Généralement, une édition contient des plans de déploiement et des événements avec une association métier marquante. Par exemple, les plans de déploiement peuvent représenter les phases du cycle de vie du développement d'un logiciel (par exemple, développement, assurance qualité et production). Un événement pourrait correspondre à une interruption totale qui affecte la mise à disposition de l'édition.

Si vous affectez des événements à une édition, vous pouvez utiliser le calendrier pour filtrer la page Releases afin d'afficher les éditions et les plans de déploiement.

## Création d'éditions
{: #releases_create}

Pour créer une édition, procédez comme suit :

1. Sur la page Releases, cliquez sur **Create release**.

1. Dans la fenêtre Create release, dans la zone **Name**, attribuez un nom à l'édition. Le nom est obligatoire.

3. Dans la liste **Team**, sélectionnez l'équipe chargée de gérer l'édition. Vous pouvez ajouter à l'édition des plans de développement générés par d'autres équipes, et non pas seulement par celle qui la gère. Toutes les équipes dont vous êtes membre sont disponibles. La stipulation de l'équipe est obligatoire.

3. Dans la zone **Start Time**, sélectionnez une date et heure de début. L'heure de début est obligatoire pour toutes les éditions.

3. Dans la zone **End Time**, sélectionnez une date et heure de fin. 

3. Dans la liste **Tags**, sélectionnez un événement ou une étiquette. Vous pouvez sélectionner plusieurs éléments. Si vous désirez que l'événement figure dans le calendrier, [sélectionnez un événement existant sur la page Configure Calendar](UCCR_events.html#events_tagCreate).

1. Vous pouvez éventuellement créer une étiquette en entrant son nom dans la zone **Tags**. Les étiquettes que vous créez depuis la fenêtre Create release ne sont pas affichées dans le calendrier, ce qui peut éviter son encombrement excessif.

5. Cliquez sur **Save**. 

Pour afficher l'édition dans la liste Activities, prenez soin que la plage de dates couvre la date de début ou de fin de l'édition. 

Une fois que l'édition a été créée, vous pouvez lui adjoindre des plans de déploiement, des événements et des étiquettes.

## Ajout de plans de déploiement à une édition
{: #releases_planAdd}

Vous pouvez ajouter des plans de déploiement existants à une édition, ou en créer de nouveaux.

Pour ajouter des plans de déploiement existants à une édition, procédez comme suit :

1. Sur la page Releases, sélectionnez l'édition.

1. Su la page Release Detail, cliquez sur **Create deployment plan**.

1. Dans la fenêtre Add Plan, sélectionnez les plans que vous désirez ajouter à l'édition. Les plans planifiés appartenant à votre équipe sont listés.

3. Cliquez sur **Save**. 

[Pour créer un plan](UCCR_deployPlan.html#plan_create), cliquez sur **Create Deployment Plan**. Les plans créés depuis la page Release sont automatiquement affectés à l'édition. Lorsque vous créez un plan de déploiement indépendant d'une édition, vous pouvez sélectionner l'édition à laquelle ajouter le plan.

## Gestion des éditions
{: #releases_manage}

La page Release Detail affiche les plans de déploiement rattachés à l'édition. Pour gérer une édition ou les plans de déploiement qui lui sont rattachés, ouvrez la page Release Detail, puis effectuez l'une des tâches suivantes :
<ul>
<li>Cliquez sur **Edit** pour modifier la définition de l'édition. Cette option vous permet d'ajouter des événements et des étiquettes à un événement d'édition.
</li>
<li>Sélectionnez **Edit this plan** pour modifier un plan de déploiement. La fenêtre Edit Deployment Plan s'affiche.
</li>
<li>Sélectionnez **Reschedule this plan** pour modifier la date/heure de début et de fin programmée.
</li>
<li>Sélectionnez **Copy this plan** pour copier un plan de déploiement. Une copie du plan sélectionné est ajoutée à l'édition.</li>
<li>Sélectionnez **Remove from release** pour retirer de l'édition le plan de déploiement. Les plans retirés d'une édition ne sont pas supprimés et peuvent être ajoutés à une autre édition.
</li>
</li>
<li>Sélectionnez **Archive this plan** pour déplacer le plan de déploiement vers l'archive. Les plans archivés peuvent être restaurés.
</li>
</ul>

Pour lancer un déploiement, voir [Exécution de déploiements](UCCR_deployRun.html#deployment_run).

## Archivage et restauration de versions
{: #releases_archiveRelease}

Bien que vous ne puissiez pas supprimer une édition, vous pouvez la stocker dans l'archive. Les éditions archivées ne sont pas affichées sur la page Releases.

Pour archiver une édition, procédez comme suit :

1. Su la page Releases, sélectionnez l'action **Archive** pour l'édition.

1. Dans la fenêtre d'événement Archive release, déterminez les plans de déploiement à archiver en sélectionnant l'une des options suivantes :
<ul>
<li>Sélectionnez **Archive all deployment plans** pour archiver l'édition et tous ses plans de déploiement quel que soit leur statut.</li>
<li>Sélectionnez **Archive completed deployment plans only** pour archiver l'édition et les seuls plans de déploiement dont le statut indique Complete. Les plans de déploiement avec d'autres statuts ne sont pas archivés et conservent leur statut actuel.</li>
</ul>

3. Cliquez sur **Archiver**.

Pour restaurer une édition archivée, procédez comme suit :

1. Sur la page Releases, cliquez sur **Archived**.

2. Dans la liste des éditions archivées, cliquez sur l'action **Restore** pour l'édition.

Une édition restaurée conserve tous ses plans de déploiement d'origine.
