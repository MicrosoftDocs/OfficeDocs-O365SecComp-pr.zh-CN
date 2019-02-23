---
title: 在 Office 365 安全&amp;合规中心中创建活动通知
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 11/7/2017
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- BCS160
- MET150
ms.assetid: 72bbad69-035b-4d33-b8f4-549a2743e97d
description: 在安全&amp;合规中心中添加和管理活动警报, 以便 office 365 会在用户在 Office 365 中执行特定活动时向您发送电子邮件通知。
ms.openlocfilehash: 25262105332b5317ddf29d49e0364faed57f3d3a
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30214902"
---
# <a name="create-activity-alerts-in-the-office-365-security-amp-compliance-center"></a><span data-ttu-id="aeae8-103">在 Office 365 安全&amp;合规中心中创建活动通知</span><span class="sxs-lookup"><span data-stu-id="aeae8-103">Create activity alerts in the Office 365 Security &amp; Compliance Center</span></span>

<span data-ttu-id="aeae8-p101">您可以创建一个活动通知, 当用户在 Office 365 中执行特定活动时, 将向您发送电子邮件通知。活动通知类似于在 Office 365 审核日志中搜索事件, 不同之处在于, 当您创建了通知的活动事件发生时, 将向您发送一封电子邮件。</span><span class="sxs-lookup"><span data-stu-id="aeae8-p101">You can create an activity alert that will send you an email notification when users perform specific activities in Office 365. Activity alerts are similar to searching for events in the Office 365 audit log, except that you'll be sent an email message when an event for an activity that you've created an alert for happens.</span></span> 
  
 <span data-ttu-id="aeae8-p102">**为什么要使用活动通知而不是在审核日志中搜索？** 特定用户可能会执行某些类型的活动或活动, 您真正希望了解这些活动或活动。您可以使用活动通知让 Office 365 在用户执行这些活动时向您发送电子邮件, 而无需记住在审核日志中搜索这些活动。例如, 您可以创建一个活动通知, 以在用户删除 SharePoint 中的文件时通知您, 也可以创建一个通知, 以在用户从其邮箱中永久删除邮件时通知您。发送给您的电子邮件通知包括有关执行了哪个活动以及执行该活动的用户的信息。</span><span class="sxs-lookup"><span data-stu-id="aeae8-p102">**Why use activity alerts instead of searching the audit log?** There might be certain kinds of activity or activity performed by specific users that you really want to know about. Instead of having to remember to search the audit log for those activities, you can use activity alerts to have Office 365 send you an email message when users perform those activities. For example, you can create an activity alert to notify you when a user deletes files in SharePoint or you can create an alert to notify you when a user permanently deletes messages from their mailbox. The email notification sent to you includes information about which activity was performed and the user who performed it.</span></span> 

> [!NOTE]
> <span data-ttu-id="aeae8-p103">我们建议您开始使用安全 & 合规性中心中的通知策略, 而不是创建新的活动警报。警报策略提供了一些附加功能, 如创建在任何用户执行指定活动时触发警报的通知策略, 以及在安全 & 合规性中心中的 "**查看警报**" 页上显示警报等功能。有关详细信息, 请参阅[Office 365 安全&amp;合规中心中的警报策略](alert-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="aeae8-p103">We recommend that you start using alert policies in the Security & Compliance Center instead of creating new activity alerts. Alert policies provide addition functionality such as the ability to create an alert policy that triggers an alert when any user performs a specified activity, and displaying alerts on the **View alerts** page in the Security & Compliance Center. For more information, see [Alert policies in the Office 365 Security &amp; Compliance Center](alert-policies.md).</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="aeae8-114">准备工作</span><span class="sxs-lookup"><span data-stu-id="aeae8-114">Before you begin</span></span>

- <span data-ttu-id="aeae8-p104">必须在安全&amp;合规中心中向您分配 "组织配置" 角色, 才能管理活动通知。默认情况下, 此角色分配给合规性管理员和组织管理角色组。有关向角色组添加成员的详细信息, 请参阅[向用户授予对 Office 365 安全&amp;合规中心的访问权限](grant-access-to-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="aeae8-p104">You must be assigned the Organization Configuration role in the Security &amp; Compliance Center to manage activity alerts. By default, this role is assigned to the Compliance Administrator and Organization Management role groups. For more information about adding members to role groups, see [Give users access to the Office 365 Security &amp; Compliance Center](grant-access-to-the-security-and-compliance-center.md).</span></span>
    
- <span data-ttu-id="aeae8-p105">您 (或另一个管理员) 必须先为您的组织启用审核日志记录, 然后才能开始使用活动通知。若要执行此操作, 只需单击 "**活动通知**" 页面上的 "**开始记录用户和管理员活动**"。(如果看不到此链接, 表明已为您的组织启用了审核。)您还可以&amp;在安全合规性中心的 "**审核日志搜索**" 页上启用审核 (转**到&amp;搜索调查** \> **审核日志搜索**)。您只需为组织执行一次此操作。</span><span class="sxs-lookup"><span data-stu-id="aeae8-p105">You (or another admin) must first turn on audit logging for your organization before you can start using activity alerts. To do this, just click **Start recording user and admin activity** on the **Activity alerts** page. (If you don't see this link, auditing has already been turned on for your organization.) You can also turn on auditing on the **Audit log search** page in the Security &amp; Compliance Center (go to **Search &amp; investigation** \> **Audit log search**). You only have to do this once for your organization.</span></span>
  
- <span data-ttu-id="aeae8-p106">您可以为可在 Office 365 审核日志中搜索的相同活动创建通知。请参阅[详细信息](#more-information)部分, 了解您可以为其创建通知的常见方案 (和要监视的特定活动) 的列表。</span><span class="sxs-lookup"><span data-stu-id="aeae8-p106">You can create alerts for the same activities that you can search for in the Office 365 audit log. See the [More information](#more-information) section for a list of common scenarios (and the specific activity to monitor) that you can create alerts for.</span></span> 
    
- <span data-ttu-id="aeae8-p107">您可以使用安全&amp;合规中心中的 "**活动通知**" 页来创建警报, 这些通知只针对组织的通讯簿中列出的用户所执行的活动。无法使用此页面为未在通讯簿中列出的外部用户执行的活动创建通知。</span><span class="sxs-lookup"><span data-stu-id="aeae8-p107">You can use the **Activity alerts** page in the Security &amp; Compliance Center to create alerts only for activity performed by users who are listed in your organization's address book. You can't use this page to create alerts for activity performed by external users who aren't listed in the address book.</span></span> 
    
## <a name="create-an-activity-alert"></a><span data-ttu-id="aeae8-126">创建活动通知</span><span class="sxs-lookup"><span data-stu-id="aeae8-126">Create an activity alert</span></span>

1. <span data-ttu-id="aeae8-127">转到 [https://protection.office.com/#/managealerts](https://protection.office.com/#/managealerts)。</span><span class="sxs-lookup"><span data-stu-id="aeae8-127">Go to [https://protection.office.com/#/managealerts](https://protection.office.com/#/managealerts).</span></span>
    
2. <span data-ttu-id="aeae8-128">使用工作或学校帐户登录到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="aeae8-128">Sign in to Office 365 using your work or school account.</span></span>
    
3. <span data-ttu-id="aeae8-129">在 "**活动通知**" 页面上![, 单击](media/8ee52980-254b-440b-99a2-18d068de62d3.gif) "**新建**图标"。</span><span class="sxs-lookup"><span data-stu-id="aeae8-129">On the **Activity alerts** page, click ![Add icon](media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **New**.</span></span>

   <span data-ttu-id="aeae8-130">将显示用于创建活动通知的飞出页面。</span><span class="sxs-lookup"><span data-stu-id="aeae8-130">The flyout page to create an activity alert is displayed.</span></span>

    
    ![创建活动通知](media/53888bd5-9fa2-4398-8ccc-1a9dc72517ac.png)
  
4. <span data-ttu-id="aeae8-132">填写以下字段以创建活动通知:</span><span class="sxs-lookup"><span data-stu-id="aeae8-132">Complete the following fields to create an activity alert:</span></span>
    
    <span data-ttu-id="aeae8-p108">a. **name** -键入警报的名称。警报名称在您的组织中必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="aeae8-p108">a. **Name** - Type a name for the alert. Alert names must be unique within your organization.</span></span>
    
    <span data-ttu-id="aeae8-p109">b.**说明**(可选)-描述警报, 例如活动和要跟踪的用户, 以及发送电子邮件通知的用户。说明提供了一种快速而简单的方法, 可将警报的用途描述给其他管理员。</span><span class="sxs-lookup"><span data-stu-id="aeae8-p109">b. **Description** (Optional) - Describe the alert, such as the activities and users being tracked, and the users that email notifications are sent to. Descriptions provide a quick and easy way to describe the purpose of the alert to other admins.</span></span>
    
    <span data-ttu-id="aeae8-p110">c.**警报类型**-请确保选择 "**自定义**" 选项。</span><span class="sxs-lookup"><span data-stu-id="aeae8-p110">c. **Alert type** - Make sure the **Custom** option is selected.</span></span> 

    <span data-ttu-id="aeae8-p111">d. 当-单击时**发送此**通知, 然后在配置这两个字段时发送**此通知**:</span><span class="sxs-lookup"><span data-stu-id="aeae8-p111">d. **Send this alert when** - Click **Send this alert when** and then configure these two fields:</span></span>
    
    - <span data-ttu-id="aeae8-p112">**活动**-单击下拉列表以显示您可以为其创建通知的活动。这是在搜索 Office 365 审核日志时显示的活动列表。您可以选择一个或多个特定活动, 也可以单击活动组名称以选择组中的所有活动。有关这些活动的说明, 请参阅在[Office 365 安全 & 合规中心中搜索审核日志](search-the-audit-log-in-security-and-compliance.md#audited-activities)中的 "已审核的活动" 一节。当用户执行已添加到通知中的任何活动时, 都会发送电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="aeae8-p112">**Activities** - Click the drop-down list to display the activities that you can create an alert for. This is the same activities list that's displayed when you search the Office 365 audit log. You can select one or more specific activities or you can click the activity group name to select all activities in the group. For a description of these activities, see the "Audited activities" section in [Search the audit log in the Office 365 Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md#audited-activities). When a user performs any of the activities that you've added to the alert, an email notification is sent.</span></span> 
    
     - <span data-ttu-id="aeae8-p113">**用户**-单击此框, 然后选择一个或多个用户。如果此框中的用户执行您添加到 "**活动**" 框中的活动, 则会发送一个警告。将 "**用户**" 框留空可以在组织中的任何用户执行由警报指定的活动时发送警报。</span><span class="sxs-lookup"><span data-stu-id="aeae8-p113">**Users** - Click this box and then select one or more users. If the users in this box perform the activities that you added to the **Activities** box, an alert will be sent. Leave the **Users** box blank to send an alert when any user in your organization performs the activities specified by the alert.</span></span> 

    <span data-ttu-id="aeae8-p114">e. 将**此通知发送到**-单击 "**发送此通知**", 然后单击 "**收件人**" 框并键入名称, 以添加在用户 (在 "**用户**" 框中指定) 执行活动时将收到电子邮件通知的用户 (在**活动**"框)。请注意, 默认情况下会将您添加到收件人列表中。您可以从此列表中删除您的姓名。</span><span class="sxs-lookup"><span data-stu-id="aeae8-p114">e. **Send this alert to** - Click **Send this alert**, and then click in the **Recipients** box and type a name to add a users who will receive an email notification when a user (specified in the **Users** box) performs an activity (specified in the **Activities** box). Note that you are added to the list of recipients by default. You can remove your name from this list.</span></span>
    
5. <span data-ttu-id="aeae8-155">单击 "**保存**" 以创建通知。</span><span class="sxs-lookup"><span data-stu-id="aeae8-155">Click **Save** to create the alert.</span></span> 
    
    <span data-ttu-id="aeae8-156">新通知将显示在 "**活动通知**" 页面上的列表中。</span><span class="sxs-lookup"><span data-stu-id="aeae8-156">The new alert is displayed in the list on the **Activity alerts** page.</span></span> 
    
    ![安全&amp;合规中心中的 "活动通知" 页面上显示一个警报列表](media/02b774f2-1719-41de-bbc9-5e5b7576f335.png)
  
    <span data-ttu-id="aeae8-p115">通知的状态设置为 **"开**"。请注意, 还会列出接收通知时接收电子邮件通知的收件人。</span><span class="sxs-lookup"><span data-stu-id="aeae8-p115">The status of the alert is set to **On**. Note that the recipients who will received an email notification when an alert is sent are also listed.</span></span> 
  
## <a name="turn-off-an-activity-alert"></a><span data-ttu-id="aeae8-160">关闭活动通知</span><span class="sxs-lookup"><span data-stu-id="aeae8-160">Turn off an activity alert</span></span>

<span data-ttu-id="aeae8-p116">您可以关闭活动通知, 以便不发送电子邮件通知。关闭活动通知后, 它仍显示在您的组织的活动通知列表中, 您仍可以查看其属性。</span><span class="sxs-lookup"><span data-stu-id="aeae8-p116">You can turn off an activity alert so that an email notification isn't sent. After you turn off the activity alert, it's still displayed in the list of activity alerts for your organization, and you can still view its properties.</span></span>
  
1. <span data-ttu-id="aeae8-163">转到 [https://protection.office.com/#/managealerts](https://protection.office.com/#/managealerts)。</span><span class="sxs-lookup"><span data-stu-id="aeae8-163">Go to [https://protection.office.com/#/managealerts](https://protection.office.com/#/managealerts).</span></span>
    
2. <span data-ttu-id="aeae8-164">使用工作或学校帐户登录到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="aeae8-164">Sign in to Office 365 using your work or school account.</span></span>
    
3. <span data-ttu-id="aeae8-165">在组织的活动通知列表中, 单击要禁用的通知。</span><span class="sxs-lookup"><span data-stu-id="aeae8-165">In the list of activity alerts for your organization, click the alert that you want to turn off.</span></span>
    
4. <span data-ttu-id="aeae8-166">在 "**编辑通知**" 页上, \*\*\*\* 单击 "切换开关" 将状态更改为 "**关闭**", 然后单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="aeae8-166">On the **Edit alert** page, click the **On** toggle switch to change the status to **Off**, and then click **Save**.</span></span>
    
    <span data-ttu-id="aeae8-167">"**活动通知**" 页面上通知的状态设置为 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="aeae8-167">The status of the alert on the **Activity alerts** pages is set to **Off**.</span></span> 
    
<span data-ttu-id="aeae8-168">若要重新打开活动通知, 只需重复这些步骤, 然后单击 "**关闭**" 切换开关, 将状态更改为 **"开启**"。</span><span class="sxs-lookup"><span data-stu-id="aeae8-168">To turn an activity alert back on, just repeat these steps and click the **Off** toggle switch to change the status to **On**.</span></span>
  
## <a name="more-information"></a><span data-ttu-id="aeae8-169">更多信息</span><span class="sxs-lookup"><span data-stu-id="aeae8-169">More information</span></span>

- <span data-ttu-id="aeae8-170">下面的示例展示了如何向安全&amp;合规中心中的 "发送到此通知的用户" 字段 (并在 "**活动通知**" 页面上的 "**收件人**" 下列出) 中指定的用户发送电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="aeae8-170">Here's an example of the email notification that is sent to the users that are specified in the Sent this alert to field (and listed under **Recipients** on the **Activity alerts** page ) in the Security &amp; Compliance Center.</span></span> 
    
    ![为活动通知发送的电子邮件 notifcation 的示例通知](media/a5f91611-fae6-4fe9-82f5-58521a2e2541.png)
  
- <span data-ttu-id="aeae8-p117">下面是您可以为其创建活动通知的一些常见文档和电子邮件活动。这些表介绍了活动、要为其创建通知的活动的名称, 以及活动下拉列表中 "活动" 下列出的活动组的名称。 \*\*\*\* 若要查看您可以为其创建活动通知的活动的完整列表, 请参阅在[Office 365 安全 & 合规中心中搜索审核日志](search-the-audit-log-in-security-and-compliance.md#audited-activities)中的 "已审核的活动" 部分。</span><span class="sxs-lookup"><span data-stu-id="aeae8-p117">Here's are some common document and email activities that you can create an activity alerts for. The tables describes the activity, the name of the activity to create an alert for, and the name of the activity group that the activity is listed under in the **Activities** drop-down list. To see a complete list of the activities that you can create activity alerts for, see the "Audited activities" section in [Search the audit log in the Office 365 Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md#audited-activities).</span></span>
    
    > [!TIP]
    > <span data-ttu-id="aeae8-p118">您可能想要为任何用户执行的一个活动仅创建一个活动通知。或者, 您可能想要创建一个活动通知来跟踪由一个或 mores 用户执行的多个活动。</span><span class="sxs-lookup"><span data-stu-id="aeae8-p118">You might want to create an activity alert for just one activity that's performed by any user. Or you might want to create an activity alert that track multiple activities performed by one or mores users.</span></span> 
  
    <span data-ttu-id="aeae8-177">下表列出了 SharePoint 或 OneDrive for business 中的一些常见的与文档相关的活动。</span><span class="sxs-lookup"><span data-stu-id="aeae8-177">The following table lists some common document-related activities in SharePoint or OneDrive for Business.</span></span>
    
    |<span data-ttu-id="aeae8-178">**当用户执行此 .。。**</span><span class="sxs-lookup"><span data-stu-id="aeae8-178">**When a user does this...**</span></span>|<span data-ttu-id="aeae8-179">**为此活动创建通知**</span><span class="sxs-lookup"><span data-stu-id="aeae8-179">**Create an alert for this activity**</span></span>|<span data-ttu-id="aeae8-180">**活动组**</span><span class="sxs-lookup"><span data-stu-id="aeae8-180">**Activity group**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="aeae8-181">查看网站上的文档。</span><span class="sxs-lookup"><span data-stu-id="aeae8-181">Views a document on a site.</span></span>  <br/> |<span data-ttu-id="aeae8-182">访问的文件</span><span class="sxs-lookup"><span data-stu-id="aeae8-182">Accessed file</span></span>  <br/> |<span data-ttu-id="aeae8-183">文件和文件夹活动</span><span class="sxs-lookup"><span data-stu-id="aeae8-183">File and folder activities</span></span>  <br/> |
    |<span data-ttu-id="aeae8-184">编辑或更改文档。</span><span class="sxs-lookup"><span data-stu-id="aeae8-184">Edits or changes a document.</span></span>  <br/> |<span data-ttu-id="aeae8-185">修改的文件</span><span class="sxs-lookup"><span data-stu-id="aeae8-185">Modified file</span></span>  <br/> |<span data-ttu-id="aeae8-186">文件和文件夹活动</span><span class="sxs-lookup"><span data-stu-id="aeae8-186">File and folder activities</span></span>  <br/> |
    |<span data-ttu-id="aeae8-187">与组织外部的用户共享文档。</span><span class="sxs-lookup"><span data-stu-id="aeae8-187">Shares a document with a user outside of your organization.</span></span>  <br/> |<span data-ttu-id="aeae8-188">共享文件、文件夹或网站</span><span class="sxs-lookup"><span data-stu-id="aeae8-188">Share file, folder, or site</span></span>  <br/> <span data-ttu-id="aeae8-189">和</span><span class="sxs-lookup"><span data-stu-id="aeae8-189">And</span></span>  <br/> <span data-ttu-id="aeae8-190">已创建共享邀请</span><span class="sxs-lookup"><span data-stu-id="aeae8-190">Created sharing invitation</span></span>  <br/> <span data-ttu-id="aeae8-191">有关详细信息, 请参阅[在 Office 365 审核日志中使用共享审核](use-sharing-auditing.md)。</span><span class="sxs-lookup"><span data-stu-id="aeae8-191">For more information, see [Use sharing auditing in the Office 365 audit log](use-sharing-auditing.md).</span></span>  <br/> |<span data-ttu-id="aeae8-192">共享和访问请求活动</span><span class="sxs-lookup"><span data-stu-id="aeae8-192">Sharing and access request activities</span></span>  <br/> |
    |<span data-ttu-id="aeae8-193">上载或下载文档。</span><span class="sxs-lookup"><span data-stu-id="aeae8-193">Uploads or downloads a document.</span></span>  <br/> |<span data-ttu-id="aeae8-194">上载的文件</span><span class="sxs-lookup"><span data-stu-id="aeae8-194">Uploaded file</span></span>  <br/> <span data-ttu-id="aeae8-195">和/或</span><span class="sxs-lookup"><span data-stu-id="aeae8-195">And/or</span></span>  <br/> <span data-ttu-id="aeae8-196">下载文件</span><span class="sxs-lookup"><span data-stu-id="aeae8-196">Downloaded file</span></span>  <br/> |<span data-ttu-id="aeae8-197">文件和文件夹活动</span><span class="sxs-lookup"><span data-stu-id="aeae8-197">File and folder activities</span></span>  <br/> |
    |<span data-ttu-id="aeae8-198">更改对网站的访问权限。</span><span class="sxs-lookup"><span data-stu-id="aeae8-198">Changes the access permissions to a site.</span></span>  <br/> |<span data-ttu-id="aeae8-199">修改的网站权限</span><span class="sxs-lookup"><span data-stu-id="aeae8-199">Modified site permissions</span></span>  <br/> |<span data-ttu-id="aeae8-200">网站管理活动</span><span class="sxs-lookup"><span data-stu-id="aeae8-200">Site administration activities</span></span>  <br/> |

    <span data-ttu-id="aeae8-201">下表列出了 Exchange Online 中与电子邮件相关的一些常见活动。</span><span class="sxs-lookup"><span data-stu-id="aeae8-201">The following table lists some common email-related activities in Exchange Online.</span></span>

    |<span data-ttu-id="aeae8-202">**当用户执行此 .。。**</span><span class="sxs-lookup"><span data-stu-id="aeae8-202">**When a user does this...**</span></span>|<span data-ttu-id="aeae8-203">**为此活动创建通知**</span><span class="sxs-lookup"><span data-stu-id="aeae8-203">**Create an alert for this activity**</span></span>|<span data-ttu-id="aeae8-204">**活动组**</span><span class="sxs-lookup"><span data-stu-id="aeae8-204">**Activity group**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="aeae8-205">从邮箱中永久删除 (清除) 电子邮件。</span><span class="sxs-lookup"><span data-stu-id="aeae8-205">Permanently deletes (purges) an email message from their mailbox.</span></span>  <br/> |<span data-ttu-id="aeae8-206">已清除邮箱中的邮件</span><span class="sxs-lookup"><span data-stu-id="aeae8-206">Purged messages from mailbox</span></span>  <br/> | <span data-ttu-id="aeae8-207">Exchange 邮箱活动</span><span class="sxs-lookup"><span data-stu-id="aeae8-207">Exchange mailbox activities</span></span>  <br/> |
    |<span data-ttu-id="aeae8-208">从共享邮箱发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="aeae8-208">Sends an email message from a shared mailbox.</span></span>  <br/> |<span data-ttu-id="aeae8-209">使用 "代理发送" 权限发送邮件</span><span class="sxs-lookup"><span data-stu-id="aeae8-209">Sent message using Send As permissions</span></span>  <br/> <span data-ttu-id="aeae8-210">和</span><span class="sxs-lookup"><span data-stu-id="aeae8-210">And</span></span>  <br/> <span data-ttu-id="aeae8-211">使用 "代表发送" 权限发送的邮件</span><span class="sxs-lookup"><span data-stu-id="aeae8-211">Sent message using Send On Behalf permissions</span></span>  <br/> | <span data-ttu-id="aeae8-212">Exchange 邮箱活动</span><span class="sxs-lookup"><span data-stu-id="aeae8-212">Exchange mailbox activities</span></span>  <br/> |
   
- <span data-ttu-id="aeae8-p119">您还可以使用安全&amp;合规中心 PowerShell 中的**set-activityalert**和**set-activityalert** cmdlet 来创建和编辑活动通知。如果您使用这些 cmdlet 创建或编辑活动通知, 请记住以下几点:</span><span class="sxs-lookup"><span data-stu-id="aeae8-p119">You can also use the **New-ActivityAlert** and **Set-ActivityAlert** cmdlets in Security &amp; Compliance Center PowerShell to create and edit activity alerts. Keep the following things in mind if you use these cmdlets to create or edit activity alerts:</span></span> 
    
  - <span data-ttu-id="aeae8-215">如果使用 cmdlet 将活动添加到未在 "**活动**" 下拉列表中列出的警报中, 则会在警告的属性页中显示一条消息, 指出 "此通知具有未在选取器中列出的自定义操作"。</span><span class="sxs-lookup"><span data-stu-id="aeae8-215">If you use a cmdlet to add an activity to the alert that isn't listed in the **Activities** drop-down list, a message is displayed in on the property page for the alert that says, "This alert has custom operations not listed in the picker."</span></span> 
    
  - <span data-ttu-id="aeae8-p120">使用 cmdlet 创建或编辑活动通知的最佳原因是将电子邮件通知发送给组织外部的某个人。此外部用户将列在通知的收件人列表中。但是, 如果您从警报中删除此外部用户, 则无法使用安全&amp;合规中心中的 "**编辑通知**" 页将该用户重新添加到通知中。您必须使用**set-activityalert** cmdlet 重新添加外部用户, 或使用**set-activityalert** cmdlet 将相同 (或不同) 的外部用户添加到新警报。</span><span class="sxs-lookup"><span data-stu-id="aeae8-p120">A good reason to use the cmdlets to create or edit an activity alert is to send email notifications to someone outside of your organization. This external user will be listed in the list of recipients for the alert. But if you remove this external user from the alert, that user can't be re-added to the alert by using **Edit alert** page in the Security &amp; Compliance Center. You'll have to re-add the external user using the **Set-ActivityAlert** cmdlet, or use the **New-ActivityAlert** cmdlet to add the same (or different) external user to a new alert.</span></span> 
    
  

