---
title: 在 Office 365 安全性中创建活动通知&amp;合规性中心
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 11/7/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- BCS160
- MET150
ms.assetid: 72bbad69-035b-4d33-b8f4-549a2743e97d
description: 添加和管理安全中的活动通知&amp;合规性中心以便 Office 365 将向您发送电子邮件通知，当用户在 Office 365 中执行特定的活动。
ms.openlocfilehash: 2a579e850d16b730a777ce6c4e5c0446305a027d
ms.sourcegitcommit: 3a376619dbae472495c29da7c061f5c5faeeaddb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/12/2018
ms.locfileid: "26282736"
---
# <a name="create-activity-alerts-in-the-office-365-security-amp-compliance-center"></a><span data-ttu-id="44df3-103">在 Office 365 安全性中创建活动通知&amp;合规性中心</span><span class="sxs-lookup"><span data-stu-id="44df3-103">Create activity alerts in the Office 365 Security &amp; Compliance Center</span></span>

<span data-ttu-id="44df3-p101">您可以创建的活动报警时，将当用户执行特定的活动 Office 365 中向您发送的电子邮件通知。活动通知类似于搜索的 Office 365 审核日志中的事件，只不过发送一封电子邮件时为您创建通知的活动事件发生的情况。</span><span class="sxs-lookup"><span data-stu-id="44df3-p101">You can create an activity alert that will send you an email notification when users perform specific activities in Office 365. Activity alerts are similar to searching for events in the Office 365 audit log, except that you'll be sent an email message when an event for an activity that you've created an alert for happens.</span></span> 
  
 <span data-ttu-id="44df3-p102">**原因而不是搜索审核日志中使用活动通知？** 可能有某些类型的活动或执行确实要了解的特定用户的活动。而不是必须记住要搜索审核日志中的这些活动，您可以使用活动通知已向您发送一封电子邮件，当用户执行这些活动的 Office 365。例如，您可以创建活动通知时用户删除 SharePoint 中的文件，也可以创建警报，通知您从他们的邮箱用户可永久删除邮件时通知您。向您发送电子邮件通知包括已执行的活动和执行它的用户的信息。</span><span class="sxs-lookup"><span data-stu-id="44df3-p102">**Why use activity alerts instead of searching the audit log?** There might be certain kinds of activity or activity performed by specific users that you really want to know about. Instead of having to remember to search the audit log for those activities, you can use activity alerts to have Office 365 send you an email message when users perform those activities. For example, you can create an activity alert to notify you when a user deletes files in SharePoint or you can create an alert to notify you when a user permanently deletes messages from their mailbox. The email notification sent to you includes information about which activity was performed and the user who performed it.</span></span> 

> [!NOTE]
> <span data-ttu-id="44df3-p103">我们建议您开始使用安全性和合规性中心中的通知的策略，而不创建新的活动通知。警报策略提供附加功能，如创建通知的策略的任何用户执行指定的活动，并在安全性和合规性中心中**查看警报**页上显示通知时将触发通知的能力。有关详细信息，请参阅[警报策略在 Office 365 安全性&amp;合规性中心](alert-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="44df3-p103">We recommend that you start using alert policies in the Security & Compliance Center instead of creating new activity alerts. Alert policies provide addition functionality such as the ability to create an alert policy that triggers an alert when any user performs a specified activity, and displaying alerts on the **View alerts** page in the Security & Compliance Center. For more information, see [Alert policies in the Office 365 Security &amp; Compliance Center](alert-policies.md).</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="44df3-114">开始之前</span><span class="sxs-lookup"><span data-stu-id="44df3-114">Before you begin</span></span>

- <span data-ttu-id="44df3-p104">您必须先获得中安全性的组织配置角色&amp;合规性中心以管理活动通知。默认情况下，此角色分配给合规性管理员和组织管理角色组。有关向角色组添加成员的详细信息，请参阅[向 Office 365 安全性授予用户访问&amp;合规性中心](grant-access-to-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="44df3-p104">You must be assigned the Organization Configuration role in the Security &amp; Compliance Center to manage activity alerts. By default, this role is assigned to the Compliance Administrator and Organization Management role groups. For more information about adding members to role groups, see [Give users access to the Office 365 Security &amp; Compliance Center](grant-access-to-the-security-and-compliance-center.md).</span></span>
    
- <span data-ttu-id="44df3-p105">您 （或其他管理员） 必须首先打开审核日志记录您的组织可以开始使用活动通知之前。要执行此操作，只需单击**开始录制用户和管理活动\*\*\*\*活动通知**页面上。（如果您看不到此链接，具有已打开审核为您的组织。）您还可以在安全**审核日志搜索**页审核&amp;合规性中心 (转到**搜索&amp;调查** \> **审核日志搜索**)。您只需执行一次此为您的组织。</span><span class="sxs-lookup"><span data-stu-id="44df3-p105">You (or another admin) must first turn on audit logging for your organization before you can start using activity alerts. To do this, just click **Start recording user and admin activity** on the **Activity alerts** page. (If you don't see this link, auditing has already been turned on for your organization.) You can also turn on auditing on the **Audit log search** page in the Security &amp; Compliance Center (go to **Search &amp; investigation** \> **Audit log search**). You only have to do this once for your organization.</span></span>
  
- <span data-ttu-id="44df3-p106">您可以创建的同一个活动，您可以在 Office 365 审核日志中搜索的通知。[详细信息](#more-information)，请参阅常见方案 （和要监视的特定活动） 的列表部分，您可以创建的通知。</span><span class="sxs-lookup"><span data-stu-id="44df3-p106">You can create alerts for the same activities that you can search for in the Office 365 audit log. See the [More information](#more-information) section for a list of common scenarios (and the specific activity to monitor) that you can create alerts for.</span></span> 
    
- <span data-ttu-id="44df3-p107">您可以使用**活动通知**页面中安全&amp;创建通知仅由组织的通讯簿中列出的用户执行活动的合规性中心。此页不能用于创建通知的外部用户可以在通讯簿中没有列出执行活动。</span><span class="sxs-lookup"><span data-stu-id="44df3-p107">You can use the **Activity alerts** page in the Security &amp; Compliance Center to create alerts only for activity performed by users who are listed in your organization's address book. You can't use this page to create alerts for activity performed by external users who aren't listed in the address book.</span></span> 
    
## <a name="create-an-activity-alert"></a><span data-ttu-id="44df3-126">创建活动通知</span><span class="sxs-lookup"><span data-stu-id="44df3-126">Create an activity alert</span></span>

1. <span data-ttu-id="44df3-127">转到 [https://protection.office.com/#/managealerts](https://protection.office.com/#/managealerts)。</span><span class="sxs-lookup"><span data-stu-id="44df3-127">Go to [https://protection.office.com/#/managealerts](https://protection.office.com/#/managealerts).</span></span>
    
2. <span data-ttu-id="44df3-128">使用工作或学校帐户登录到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="44df3-128">Sign in to Office 365 using your work or school account.</span></span>
    
3. <span data-ttu-id="44df3-129">在**活动通知**页上单击![添加图标](media/8ee52980-254b-440b-99a2-18d068de62d3.gif)**新建**。</span><span class="sxs-lookup"><span data-stu-id="44df3-129">On the **Activity alerts** page, click ![Add icon](media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **New**.</span></span>

   <span data-ttu-id="44df3-130">显示弹出页后，可以创建活动通知。</span><span class="sxs-lookup"><span data-stu-id="44df3-130">The flyout page to create an activity alert is displayed.</span></span>

    
    ![创建活动通知](media/53888bd5-9fa2-4398-8ccc-1a9dc72517ac.png)
  
4. <span data-ttu-id="44df3-132">填写以下字段来创建活动通知：</span><span class="sxs-lookup"><span data-stu-id="44df3-132">Complete the following fields to create an activity alert:</span></span>
    
    <span data-ttu-id="44df3-p108">答：**名称**-键入警报的名称。警报名称必须是唯一贵组织中。</span><span class="sxs-lookup"><span data-stu-id="44df3-p108">a. **Name** - Type a name for the alert. Alert names must be unique within your organization.</span></span>
    
    <span data-ttu-id="44df3-p109">b.**说明**（可选） 的描述该警报，如活动和正在跟踪的用户和发送电子邮件通知的用户发送到。说明提供快速方便地描述其他管理员的警报的用途。</span><span class="sxs-lookup"><span data-stu-id="44df3-p109">b. **Description** (Optional) - Describe the alert, such as the activities and users being tracked, and the users that email notifications are sent to. Descriptions provide a quick and easy way to describe the purpose of the alert to other admins.</span></span>
    
    <span data-ttu-id="44df3-p110">c.**警报类型**-请确保选择了**自定义**选项。</span><span class="sxs-lookup"><span data-stu-id="44df3-p110">c. **Alert type** - Make sure the **Custom** option is selected.</span></span> 

    <span data-ttu-id="44df3-p111">d.**发送此警报何时**-单击**发送此警报时**，然后配置这两个字段：</span><span class="sxs-lookup"><span data-stu-id="44df3-p111">d. **Send this alert when** - Click **Send this alert when** and then configure these two fields:</span></span>
    
    - <span data-ttu-id="44df3-p112">**活动**-单击下拉列表以显示您可以创建通知的活动。这是搜索的 Office 365 审核日志时显示的同一个活动列表。您可以选择一个或多个特定的活动，也可以单击选择组中的所有活动的活动组名称。有关这些活动的说明，请参阅[的搜索审核日志在 Office 365 安全性和合规性中心](search-the-audit-log-in-security-and-compliance.md#audited-activities)中的"审核活动"一节。当用户执行任何已添加到通知的活动时，发送的电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="44df3-p112">**Activities** - Click the drop-down list to display the activities that you can create an alert for. This is the same activities list that's displayed when you search the Office 365 audit log. You can select one or more specific activities or you can click the activity group name to select all activities in the group. For a description of these activities, see the "Audited activities" section in [Search the audit log in the Office 365 Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md#audited-activities). When a user performs any of the activities that you've added to the alert, an email notification is sent.</span></span> 
    
     - <span data-ttu-id="44df3-p113">**用户**-单击此框，然后选择一个或多个用户。如果此框中的用户执行活动添加到**活动**框中，将发送通知。输入**用户**框为空时您的组织中的任何用户执行指定的通知的活动发送一条通知。</span><span class="sxs-lookup"><span data-stu-id="44df3-p113">**Users** - Click this box and then select one or more users. If the users in this box perform the activities that you added to the **Activities** box, an alert will be sent. Leave the **Users** box blank to send an alert when any user in your organization performs the activities specified by the alert.</span></span> 

    <span data-ttu-id="44df3-p114">e.**发送到此通知**-单击**发送此通知**，然后在**收件人**框中单击并键入要添加的用户 （在**用户**框中指定） 的用户执行活动时，将收到的电子邮件通知的名称 (中指定**活动**框）。请注意，您添加到的收件人列表默认情况下。您可以从此列表中删除您的姓名。</span><span class="sxs-lookup"><span data-stu-id="44df3-p114">e. **Send this alert to** - Click **Send this alert**, and then click in the **Recipients** box and type a name to add a users who will receive an email notification when a user (specified in the **Users** box) performs an activity (specified in the **Activities** box). Note that you are added to the list of recipients by default. You can remove your name from this list.</span></span>
    
5. <span data-ttu-id="44df3-155">单击**保存**以创建通知。</span><span class="sxs-lookup"><span data-stu-id="44df3-155">Click **Save** to create the alert.</span></span> 
    
    <span data-ttu-id="44df3-156">在新通知显示在**活动通知**页面上的列表。</span><span class="sxs-lookup"><span data-stu-id="44df3-156">The new alert is displayed in the list on the **Activity alerts** page.</span></span> 
    
    ![在安全活动通知页面上显示的通知列表&amp;合规性中心](media/02b774f2-1719-41de-bbc9-5e5b7576f335.png)
  
    <span data-ttu-id="44df3-p115">通知的状态设置为**上**。请注意还会列出的收件人发送通知时将接收的电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="44df3-p115">The status of the alert is set to **On**. Note that the recipients who will received an email notification when an alert is sent are also listed.</span></span> 
  
## <a name="turn-off-an-activity-alert"></a><span data-ttu-id="44df3-160">关闭活动通知</span><span class="sxs-lookup"><span data-stu-id="44df3-160">Turn off an activity alert</span></span>

<span data-ttu-id="44df3-p116">您可以关闭活动通知，以便不发送的电子邮件通知。关闭活动通知后，仍显示在您的组织的活动通知列表中，您仍然可以查看其属性。</span><span class="sxs-lookup"><span data-stu-id="44df3-p116">You can turn off an activity alert so that an email notification isn't sent. After you turn off the activity alert, it's still displayed in the list of activity alerts for your organization, and you can still view its properties.</span></span>
  
1. <span data-ttu-id="44df3-163">转到 [https://protection.office.com/#/managealerts](https://protection.office.com/#/managealerts)。</span><span class="sxs-lookup"><span data-stu-id="44df3-163">Go to [https://protection.office.com/#/managealerts](https://protection.office.com/#/managealerts).</span></span>
    
2. <span data-ttu-id="44df3-164">使用工作或学校帐户登录到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="44df3-164">Sign in to Office 365 using your work or school account.</span></span>
    
3. <span data-ttu-id="44df3-165">在您的组织的活动通知列表中，单击您想要关闭的通知。</span><span class="sxs-lookup"><span data-stu-id="44df3-165">In the list of activity alerts for your organization, click the alert that you want to turn off.</span></span>
    
4. <span data-ttu-id="44df3-166">在**编辑通知**页上，单击**在**切换开关状态更改为**关闭**，，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="44df3-166">On the **Edit alert** page, click the **On** toggle switch to change the status to **Off**, and then click **Save**.</span></span>
    
    <span data-ttu-id="44df3-167">**活动通知**页面上的通知的状态设置为**关闭**。</span><span class="sxs-lookup"><span data-stu-id="44df3-167">The status of the alert on the **Activity alerts** pages is set to **Off**.</span></span> 
    
<span data-ttu-id="44df3-168">若要重新启用活动通知，只需重复这些步骤，并单击**关闭**切换开关状态更改为**上**。</span><span class="sxs-lookup"><span data-stu-id="44df3-168">To turn an activity alert back on, just repeat these steps and click the **Off** toggle switch to change the status to **On**.</span></span>
  
## <a name="more-information"></a><span data-ttu-id="44df3-169">更多信息</span><span class="sxs-lookup"><span data-stu-id="44df3-169">More information</span></span>

- <span data-ttu-id="44df3-170">下面是发送到在发送此警报安全中的字段 （和下列出在**活动通知**页面上的**收件人**） 中指定的用户的电子邮件通知的一个示例&amp;合规性中心。</span><span class="sxs-lookup"><span data-stu-id="44df3-170">Here's an example of the email notification that is sent to the users that are specified in the Sent this alert to field (and listed under **Recipients** on the **Activity alerts** page ) in the Security &amp; Compliance Center.</span></span> 
    
    ![为活动警报发送电子邮件通知的示例](media/a5f91611-fae6-4fe9-82f5-58521a2e2541.png)
  
- <span data-ttu-id="44df3-p117">以下是您可以创建活动的一些常见文档和电子邮件活动通知的。表介绍活动、 创建通知，活动的名称和该活动将列出**活动**下拉列表中的活动组的名称。若要查看的活动，您可以创建活动通知的完整列表，请参阅[的搜索审核日志在 Office 365 安全性和合规性中心](search-the-audit-log-in-security-and-compliance.md#audited-activities)中的"审核活动"一节。</span><span class="sxs-lookup"><span data-stu-id="44df3-p117">Here's are some common document and email activities that you can create an activity alerts for. The tables describes the activity, the name of the activity to create an alert for, and the name of the activity group that the activity is listed under in the **Activities** drop-down list. To see a complete list of the activities that you can create activity alerts for, see the "Audited activities" section in [Search the audit log in the Office 365 Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md#audited-activities).</span></span>
    
    > [!TIP]
    > <span data-ttu-id="44df3-p118">您可能想要创建活动通知所执行的任何用户只有一个活动。或者可能想要创建活动通知的跟踪由一个或多个执行多个活动用户。</span><span class="sxs-lookup"><span data-stu-id="44df3-p118">You might want to create an activity alert for just one activity that's performed by any user. Or you might want to create an activity alert that track multiple activities performed by one or mores users.</span></span> 
  
    <span data-ttu-id="44df3-177">下表列出了一些常见文档与相关的活动 SharePoint 或 OneDrive for Business 中。</span><span class="sxs-lookup"><span data-stu-id="44df3-177">The following table lists some common document-related activities in SharePoint or OneDrive for Business.</span></span>
    
    |<span data-ttu-id="44df3-178">**当用户执行此操作...**</span><span class="sxs-lookup"><span data-stu-id="44df3-178">**When a user does this...**</span></span>|<span data-ttu-id="44df3-179">**为此活动创建通知**</span><span class="sxs-lookup"><span data-stu-id="44df3-179">**Create an alert for this activity**</span></span>|<span data-ttu-id="44df3-180">**活动组**</span><span class="sxs-lookup"><span data-stu-id="44df3-180">**Activity group**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="44df3-181">查看的网站上的文档。</span><span class="sxs-lookup"><span data-stu-id="44df3-181">Views a document on a site.</span></span>  <br/> |<span data-ttu-id="44df3-182">访问的文件</span><span class="sxs-lookup"><span data-stu-id="44df3-182">Accessed file</span></span>  <br/> |<span data-ttu-id="44df3-183">文件和文件夹的活动</span><span class="sxs-lookup"><span data-stu-id="44df3-183">File and folder activities</span></span>  <br/> |
    |<span data-ttu-id="44df3-184">编辑或更改文档。</span><span class="sxs-lookup"><span data-stu-id="44df3-184">Edits or changes a document.</span></span>  <br/> |<span data-ttu-id="44df3-185">已修改的文件</span><span class="sxs-lookup"><span data-stu-id="44df3-185">Modified file</span></span>  <br/> |<span data-ttu-id="44df3-186">文件和文件夹的活动</span><span class="sxs-lookup"><span data-stu-id="44df3-186">File and folder activities</span></span>  <br/> |
    |<span data-ttu-id="44df3-187">与组织外部用户共享文档。</span><span class="sxs-lookup"><span data-stu-id="44df3-187">Shares a document with a user outside of your organization.</span></span>  <br/> |<span data-ttu-id="44df3-188">共享文件、 文件夹或网站</span><span class="sxs-lookup"><span data-stu-id="44df3-188">Share file, folder, or site</span></span>  <br/> <span data-ttu-id="44df3-189">和</span><span class="sxs-lookup"><span data-stu-id="44df3-189">And</span></span>  <br/> <span data-ttu-id="44df3-190">创建共享邀请</span><span class="sxs-lookup"><span data-stu-id="44df3-190">Created sharing invitation</span></span>  <br/> <span data-ttu-id="44df3-191">有关详细信息，请参阅[使用共享 Office 365 审核日志中的审核功能](use-sharing-auditing.md)。</span><span class="sxs-lookup"><span data-stu-id="44df3-191">For more information, see [Use sharing auditing in the Office 365 audit log](use-sharing-auditing.md).</span></span>  <br/> |<span data-ttu-id="44df3-192">共享和访问请求活动</span><span class="sxs-lookup"><span data-stu-id="44df3-192">Sharing and access request activities</span></span>  <br/> |
    |<span data-ttu-id="44df3-193">上载或下载文档。</span><span class="sxs-lookup"><span data-stu-id="44df3-193">Uploads or downloads a document.</span></span>  <br/> |<span data-ttu-id="44df3-194">上载的文件</span><span class="sxs-lookup"><span data-stu-id="44df3-194">Uploaded file</span></span>  <br/> <span data-ttu-id="44df3-195">和/或</span><span class="sxs-lookup"><span data-stu-id="44df3-195">And/or</span></span>  <br/> <span data-ttu-id="44df3-196">下载的文件</span><span class="sxs-lookup"><span data-stu-id="44df3-196">Downloaded file</span></span>  <br/> |<span data-ttu-id="44df3-197">文件和文件夹的活动</span><span class="sxs-lookup"><span data-stu-id="44df3-197">File and folder activities</span></span>  <br/> |
    |<span data-ttu-id="44df3-198">更改网站的访问权限。</span><span class="sxs-lookup"><span data-stu-id="44df3-198">Changes the access permissions to a site.</span></span>  <br/> |<span data-ttu-id="44df3-199">修改的网站权限</span><span class="sxs-lookup"><span data-stu-id="44df3-199">Modified site permissions</span></span>  <br/> |<span data-ttu-id="44df3-200">网站管理活动</span><span class="sxs-lookup"><span data-stu-id="44df3-200">Site administration activities</span></span>  <br/> |

    <span data-ttu-id="44df3-201">下表列出了 Exchange Online 中某些常见的电子邮件相关活动。</span><span class="sxs-lookup"><span data-stu-id="44df3-201">The following table lists some common email-related activities in Exchange Online.</span></span>

    |<span data-ttu-id="44df3-202">**当用户执行此操作...**</span><span class="sxs-lookup"><span data-stu-id="44df3-202">**When a user does this...**</span></span>|<span data-ttu-id="44df3-203">**为此活动创建通知**</span><span class="sxs-lookup"><span data-stu-id="44df3-203">**Create an alert for this activity**</span></span>|<span data-ttu-id="44df3-204">**活动组**</span><span class="sxs-lookup"><span data-stu-id="44df3-204">**Activity group**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="44df3-205">永久删除 （清除） 电子邮件消息从他们的邮箱。</span><span class="sxs-lookup"><span data-stu-id="44df3-205">Permanently deletes (purges) an email message from their mailbox.</span></span>  <br/> |<span data-ttu-id="44df3-206">从邮箱的已清除的邮件</span><span class="sxs-lookup"><span data-stu-id="44df3-206">Purged messages from mailbox</span></span>  <br/> | <span data-ttu-id="44df3-207">Exchange 邮箱活动</span><span class="sxs-lookup"><span data-stu-id="44df3-207">Exchange mailbox activities</span></span>  <br/> |
    |<span data-ttu-id="44df3-208">从共享邮箱发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="44df3-208">Sends an email message from a shared mailbox.</span></span>  <br/> |<span data-ttu-id="44df3-209">发送邮件使用 Send As 权限</span><span class="sxs-lookup"><span data-stu-id="44df3-209">Sent message using Send As permissions</span></span>  <br/> <span data-ttu-id="44df3-210">和</span><span class="sxs-lookup"><span data-stu-id="44df3-210">And</span></span>  <br/> <span data-ttu-id="44df3-211">发送邮件使用代表发送权限</span><span class="sxs-lookup"><span data-stu-id="44df3-211">Sent message using Send On Behalf permissions</span></span>  <br/> | <span data-ttu-id="44df3-212">Exchange 邮箱活动</span><span class="sxs-lookup"><span data-stu-id="44df3-212">Exchange mailbox activities</span></span>  <br/> |
   
- <span data-ttu-id="44df3-p119">您还可以在安全使用**新建 ActivityAlert**和**设置 ActivityAlert** cmdlet&amp;合规性中心 PowerShell，可以创建和编辑活动通知。如果您使用这些 cmdlet 可以创建或编辑活动通知，请记住以下几点：</span><span class="sxs-lookup"><span data-stu-id="44df3-p119">You can also use the **New-ActivityAlert** and **Set-ActivityAlert** cmdlets in Security &amp; Compliance Center PowerShell to create and edit activity alerts. Keep the following things in mind if you use these cmdlets to create or edit activity alerts:</span></span> 
    
  - <span data-ttu-id="44df3-215">如果 cmdlet 用于将活动添加到**活动**下拉列表中未列出的通知，一条消息，显示在属性页上的通知，指出:"此警报具有在选取器中未列出自定义操作"。</span><span class="sxs-lookup"><span data-stu-id="44df3-215">If you use a cmdlet to add an activity to the alert that isn't listed in the **Activities** drop-down list, a message is displayed in on the property page for the alert that says, "This alert has custom operations not listed in the picker."</span></span> 
    
  - <span data-ttu-id="44df3-p120">使用 cmdlet 创建或编辑活动通知良好原因是为了向组织外部的某人发送电子邮件通知。将在通知收件人列表中列出此外部用户。如果从通知中删除此外部用户，用户不能重新添加到通知使用安全中**编辑通知**页，但是&amp;合规性中心。您将需要重新添加外部用户使用**集 ActivityAlert** cmdlet，或使用**新建 ActivityAlert** cmdlet 可将相同 （或不同） 的外部用户添加到新的通知。</span><span class="sxs-lookup"><span data-stu-id="44df3-p120">A good reason to use the cmdlets to create or edit an activity alert is to send email notifications to someone outside of your organization. This external user will be listed in the list of recipients for the alert. But if you remove this external user from the alert, that user can't be re-added to the alert by using **Edit alert** page in the Security &amp; Compliance Center. You'll have to re-add the external user using the **Set-ActivityAlert** cmdlet, or use the **New-ActivityAlert** cmdlet to add the same (or different) external user to a new alert.</span></span> 
    
  

