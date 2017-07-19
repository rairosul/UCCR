---

copyright:
 years: 2017
lastupdated: "2017-7-17"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}

# Managing user security
{: #admin_security}

The Continuous Release security model is team-based. Team members manage releases, events, and deployments. Administrators manage teams and assign users to them.
{:shortdesc}

Bluemix security is managed on the organization level. You use organizations to enable collaboration among users and to facilitate the logical grouping of project resources. Users are authenticated to Bluemix with their IBMid. [Follow this link for an overview of Bluemix security services](https://console.bluemix.net/docs/security/index.html).

The team-based security model means that teams manage releases, events, and run deployments. Only team members can create or modify team-managed objects. Users can be assigned to more than one team. Users are identified by email address.

The manager of the organization that uses {{site.data.keyword.uccr_short}} is automatically a {{site.data.keyword.uccr_short}} administrator. The administrator manages the security system and manages teams. The administrator can assign any member of the Bluemix organization to a team. If an administrator is a member of several Bluemix organizations, they can manage users in all of the organizations.

After {{site.data.keyword.uccr_short}} is [integrated with IBM UrbanCode Deploy](index.html#gs_install_dc), UrbanCode Deploy teams and applications can be imported into {{site.data.keyword.uccr_short}}. When a team is imported, all team members are imported. Users are identified by email address. If an existing Bluemix account is found for an imported user, that account is used. If no existing Bluemix account is found, a {{site.data.keyword.uccr_short}} account is created. Administrators can also create users.

Before a user can do any meaningful work, he or she must have a Bluemix account. Users can create a Bluemix account by using their {{site.data.keyword.uccr_short}} user name, which is the same as their email address.

## Managing teams
{: admin_securityCreateTeams}

To prepare a team, you create the team and then add users or user groups to it. After you add users, you assign permissions to them.

To create a team and assign users, complete the following steps:

1. On the Releases page, click **Settings** <img class="inline" src="images/cal-set.png"  alt="Settings icon">, and then click **Teams**.

1. On the Teams page, click **New Team**, and in the Add a New Team window, enter a name for the team, and then click **Save**.

3. With the team selected, click **Add member** to add a user or group.  

3. In the Add User or Group window, in the **User** list, select a user, and then click **Save**. The user is added to the **Members** list. Instead of selecting an existing user, administrators can create new users. To create a user, enter the user's email address. The email address is used as the user name.

3. New team members have no permissions. To grant permissions to a user, with the team displayed, click the permission that you want to grant.

After a team is created, any team member can assign it to releases, events, and deployment plans.

## User permissions
{: admin_securityPermissions}

Permissions define the scope of user actions. Administrators assign permissions when they add users to teams. Permissions are granted to individual users or user groups. Users can have different permissions for different teams.

New users have no granted permissions. Before users can do any meaningful work, they must be granted permissions. The permission types are described in this list:
<ul>
<li>The **PARTICIPANT** permission enables users to perform all product functions except manage the security system. Users with this permission can create releases and deployment plans, and run deployments.</li>
<li>The **ADMIN** permission enables users to perform all product functions and manage the {{site.data.keyword.uccr_short}} security system. [To use UrbanCode Deploy applications with protected environments, a user must have this permission](#admin_securityUCDteams).</li>
</ul>

## Importing and managing IBM UrbanCode Deploy teams
{: admin_securityUCDteams}

When an UrbanCode Deploy team is imported, in addition to the roster of team members, all applications that are managed by the team are also imported. Imported applications can be used in any deployment that is managed by the team. If a user is a member of more than one team, they can use the applications from all of their teams. [Imported applications are managed with UrbanCode Deploy tasks](UCCR_tasks.html#tasks_UDTasks).

 If an imported application has a protected environment, the environment cannot be used until a team member is granted the **ADMIN** permission.

 If several imported users have the same email address, such as admins, only one user is created in {{site.data.keyword.uccr_short}}.

## Managing user groups
{: admin_securityGroups}

You can combine users into groups. When you grant permissions to the group, you simultaneously grant them to the group members. When you assign a group to a team, all group members are simultaneously assigned to the team.

To create a group, complete the following steps:

1. On the Releases page, click **Settings** <img class="inline" src="images/cal-set.png"  alt="Settings icon">, and then click **Groups**.

1. On the Groups page, click **New Group**, and in the Add New Group window, enter a name for the group, and then click **Save**.

3. With the group selected, click **Add user**.  

3. In the **User** list, select a user, and then click **Save**. The user is added to the **Members** list. You can add a user by typing the user's email address. The email address is used as the user name.

Groups cannot be imported from UrbanCode Deploy.


