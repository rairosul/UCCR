---

copyright:
  years: 2017
lastupdated: "2017-8-7"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}

# Managing notifications and approvals
{: #plan_notifications}

Email notifications can be sent to team members as various deployment-related activities occur. Some notifications are informational while others require a response from the recipient. Notification recipients are determined by team membership and other task-related criteria.

The following events trigger notifications:

<ul>
<li>*Task ready* notifications are sent when a manual task becomes eligible to start. Notifications are sent to the assigned users of the task. The email contains a link to the task. If no users are assigned the task, notification is not sent.</li>
<li>*Task failed* notifications are sent when a manual task fails. Notifications are sent to everyone on the team. The email contains a link to the task.</li>
<li>*Plan started* notifications are sent when a deployment starts. Notifications are sent to team members with tasks assigned to them.</li>
<li>*Approval required* notifications are sent when a [Wait for approval task starts](/docs/services/UCCR/UCCR_tasksWaitApproval.html##tasks_waitApproval). Notifications are sent to users designated as approvers by the task. Tasks are approved by completing the task in the deployment. The email contains a link to the task.</li>
</ul>

