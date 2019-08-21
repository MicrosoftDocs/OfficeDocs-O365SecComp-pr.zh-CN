---
title: 数据丢失防护和 Microsoft 团队
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/12/2019
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: 现在, 你可以将 DLP 策略应用于 Microsoft 团队聊天和频道。 阅读本文, 了解详细了解它的工作原理。
ms.openlocfilehash: 4edc05a2e0759884570239a038d0869e15240d17
ms.sourcegitcommit: a5a7e43822336ed18d8f5879167766686cf6b2a3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2019
ms.locfileid: "36478221"
---
# <a name="data-loss-prevention-and-microsoft-teams"></a><span data-ttu-id="d7186-104">数据丢失防护和 Microsoft 团队</span><span class="sxs-lookup"><span data-stu-id="d7186-104">Data loss prevention and Microsoft Teams</span></span>
<!-- the note duplicates the first sentence of the overview, delete one or the other- -->

> [!NOTE]
> <span data-ttu-id="d7186-105">最近将数据丢失防护功能添加到 Microsoft 团队聊天和针对 Office 365 高级合规性的用户的频道消息 (可作为独立选项提供, 包括在 Office 365 E5 和 Microsoft 365 E5 合规性中)。</span><span class="sxs-lookup"><span data-stu-id="d7186-105">Data loss prevention capabilities were recently added to Microsoft Teams chat and channel messages for users licensed for Office 365 Advanced Compliance, which is available as a standalone option and is included in Office 365 E5 and Microsoft 365 E5 Compliance.</span></span> <span data-ttu-id="d7186-106">若要了解有关许可要求的详细信息, 请参阅[Microsoft 365 租户级服务许可指南](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance)。</span><span class="sxs-lookup"><span data-stu-id="d7186-106">To learn more about licensing requirements, see [Microsoft 365 Tenant-Level Services Licensing Guidance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance).</span></span>

## <a name="overview-of-dlp-for-microsoft-teams"></a><span data-ttu-id="d7186-107">适用于 Microsoft 团队的 DLP 概述</span><span class="sxs-lookup"><span data-stu-id="d7186-107">Overview of DLP for Microsoft Teams</span></span>

<span data-ttu-id="d7186-108">最近,[数据丢失防护](data-loss-prevention-policies.md)(DLP) 功能进行了扩展, 以包括 Microsoft 团队聊天和频道消息。</span><span class="sxs-lookup"><span data-stu-id="d7186-108">Recently, [data loss prevention](data-loss-prevention-policies.md) (DLP) capabilities were extended to include Microsoft Teams chat and channel messages.</span></span> <span data-ttu-id="d7186-109">如果你的组织拥有 DLP, 你现在可以定义策略, 以防止用户在 Microsoft 团队频道或聊天会话中共享敏感信息。</span><span class="sxs-lookup"><span data-stu-id="d7186-109">If your organization has DLP, you can now define policies that prevent people from sharing sensitive information in a Microsoft Teams channel or chat session.</span></span> <span data-ttu-id="d7186-110">下面是有关此保护工作方式的一些示例:</span><span class="sxs-lookup"><span data-stu-id="d7186-110">Here are some examples of how this protection works:</span></span>

- <span data-ttu-id="d7186-111">**示例 1: 保护邮件中的敏感信息**。</span><span class="sxs-lookup"><span data-stu-id="d7186-111">**Example 1: Protecting sensitive information in messages**.</span></span> <span data-ttu-id="d7186-112">假定有人尝试在团队聊天或频道中与来宾 (外部用户) 共享敏感信息。</span><span class="sxs-lookup"><span data-stu-id="d7186-112">Suppose that someone attempts to share sensitive information in a Teams chat or channel with guests (external users).</span></span> <span data-ttu-id="d7186-113">如果您定义了一个 DLP 策略来防止出现这种情况, 则会删除包含发送给外部用户的敏感信息的邮件。</span><span class="sxs-lookup"><span data-stu-id="d7186-113">If you have a DLP policy defined to prevent this, messages with sensitive information that are sent to external users are deleted.</span></span> <span data-ttu-id="d7186-114">这将根据您的 DLP 策略的配置方式在几秒内自动发生。</span><span class="sxs-lookup"><span data-stu-id="d7186-114">This happens automatically, and within seconds, according to how your DLP policy is configured.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d7186-115">当与 Microsoft 工作组用户共享时, Microsoft 团队的 DLP 将阻止敏感内容:</span><span class="sxs-lookup"><span data-stu-id="d7186-115">DLP for Microsoft Teams blocks sensitive content when shared with Microsoft Teams users who have:</span></span><br/><span data-ttu-id="d7186-116">- 团队和频道中的[来宾访问](https://docs.microsoft.com/MicrosoftTeams/guest-access);和</span><span class="sxs-lookup"><span data-stu-id="d7186-116">- [guest access](https://docs.microsoft.com/MicrosoftTeams/guest-access) in teams and channels; or</span></span><br/><span data-ttu-id="d7186-117">- 会议和聊天会话中的[外部访问](https://docs.microsoft.com/MicrosoftTeams/manage-external-access)。</span><span class="sxs-lookup"><span data-stu-id="d7186-117">- [external access](https://docs.microsoft.com/MicrosoftTeams/manage-external-access) in meetings and chat sessions.</span></span> <p><span data-ttu-id="d7186-118">仅当发件人和收件人均处于 "仅团队" 模式并使用[Microsoft 团队本机联合身份验证](https://docs.microsoft.com/microsoftteams/manage-external-access)时, 才能使用 DLP 作为外部聊天会话。</span><span class="sxs-lookup"><span data-stu-id="d7186-118">DLP for external chat sessions will only work if both the sender and the receiver are in Teams Only mode and using [Microsoft Teams native federation](https://docs.microsoft.com/microsoftteams/manage-external-access).</span></span> <span data-ttu-id="d7186-119">对于 Skype for Business 或非本机联合聊天会话, 工作组的 DLP 不会阻止[互操作](https://docs.microsoft.com/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability#interoperability-of-teams-and-skype-for-business)性邮件。</span><span class="sxs-lookup"><span data-stu-id="d7186-119">DLP for Teams does not block messages in [interop](https://docs.microsoft.com/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability#interoperability-of-teams-and-skype-for-business) with Skype for Business or non-native federated chat sessions.</span></span>

- <span data-ttu-id="d7186-120">**示例 2: 保护文档中的敏感信息**。</span><span class="sxs-lookup"><span data-stu-id="d7186-120">**Example 2: Protecting sensitive information in documents**.</span></span> <span data-ttu-id="d7186-121">假定有人尝试与 Microsoft 团队频道或聊天中的来宾共享文档, 并且文档包含敏感信息。</span><span class="sxs-lookup"><span data-stu-id="d7186-121">Suppose that someone attempts to share a document with guests in a Microsoft Teams channel or chat, and the document contains sensitive information.</span></span> <span data-ttu-id="d7186-122">如果您定义了一个 DLP 策略来阻止这种情况, 则不会为这些用户打开该文档。</span><span class="sxs-lookup"><span data-stu-id="d7186-122">If you have a DLP policy defined to prevent this, the document won't open for those users.</span></span> <span data-ttu-id="d7186-123">请注意, 在这种情况下, 您的 DLP 策略必须包括 SharePoint 和 OneDrive, 以便保护就绪。</span><span class="sxs-lookup"><span data-stu-id="d7186-123">Note that in this case, your DLP policy must include SharePoint and OneDrive in order for protection to be in place.</span></span> <span data-ttu-id="d7186-124">(这是在 Microsoft 团队中显示的适用于 SharePoint 的 DLP for SharePoint, 因此要求用户授予 Office 365 DLP (包含在 Office 365 E3 中) 的许可, 但不要求用户授予 Office 365 高级合规性许可。)</span><span class="sxs-lookup"><span data-stu-id="d7186-124">(This is an example of DLP for SharePoint that shows up in Microsoft Teams, and therefore requires that users are licensed for Office 365 DLP (included in Office 365 E3), but does not require users to be licensed for Office 365 Advanced Compliance.)</span></span>

## <a name="policy-tips-help-educate-users"></a><span data-ttu-id="d7186-125">策略提示有助于教育用户</span><span class="sxs-lookup"><span data-stu-id="d7186-125">Policy tips help educate users</span></span>

<span data-ttu-id="d7186-126">与 DLP 在[Exchange、outlook、web 上的 outlook](data-loss-prevention-policies.md#policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web)、 [SharePoint Online、OneDrive for Business 网站](data-loss-prevention-policies.md#policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites)和[Office 桌面客户端](data-loss-prevention-policies.md#policy-evaluation-in-the-office-desktop-programs)中的工作方式类似, 当操作与 DLP 策略冲突时, 将显示策略提示。</span><span class="sxs-lookup"><span data-stu-id="d7186-126">Similar to how DLP works in [Exchange, Outlook, Outlook on the web](data-loss-prevention-policies.md#policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web), [SharePoint Online, OneDrive for Business sites](data-loss-prevention-policies.md#policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites), and [Office desktop clients](data-loss-prevention-policies.md#policy-evaluation-in-the-office-desktop-programs), policy tips appear when an action conflicts with a DLP policy.</span></span> <span data-ttu-id="d7186-127">下面是策略提示的一个示例:</span><span class="sxs-lookup"><span data-stu-id="d7186-127">Here's an example of a policy tip:</span></span>

![团队中阻止的邮件通知](media/dlp-teams-blockedmessage-notification.png)

<span data-ttu-id="d7186-129">在这种情况下, 发件人试图在 Microsoft 团队频道中共享社会保障号。</span><span class="sxs-lookup"><span data-stu-id="d7186-129">In this case, the sender attempted to share a social security number in a Microsoft Teams channel.</span></span> <span data-ttu-id="d7186-130">**我可以执行的操作？** link 打开一个对话框, 为发件人提供解决问题的选项。</span><span class="sxs-lookup"><span data-stu-id="d7186-130">The **What can I do?** link opens a dialog box that provides options for the sender to resolve the issue.</span></span> <span data-ttu-id="d7186-131">请注意, 在这种情况下, 发件人可以选择替代策略, 也可以通知管理员查看和解决该策略。</span><span class="sxs-lookup"><span data-stu-id="d7186-131">Notice that in this case, the sender can opt to override the policy, or notify an admin to review and resolve it.</span></span>

![用于解析阻止的邮件的选项](media/dlp-teams-blockedmessage-possibleactions.png)

<span data-ttu-id="d7186-133">在您的组织中, 您可以选择允许用户替代 DLP 策略。</span><span class="sxs-lookup"><span data-stu-id="d7186-133">In your organization, you can choose to allow users to override a DLP policy.</span></span> <span data-ttu-id="d7186-134">在配置 DLP 策略时, 您可以使用默认策略提示, 也可以为您的组织[自定义策略提示](#to-customize-policy-tips)。</span><span class="sxs-lookup"><span data-stu-id="d7186-134">And, when you configure your DLP policies, you can use the default policy tips, or [customize policy tips](#to-customize-policy-tips) for your organization.</span></span> 

<span data-ttu-id="d7186-135">返回到我们的示例, 其中发件人在团队频道中共享社会安全号码, 以下是收件人看到的内容:</span><span class="sxs-lookup"><span data-stu-id="d7186-135">Returning to our example, where a sender shared a social security number in a Teams channel, here's what the recipient saw:</span></span>

![阻止的邮件](media/dlp-teams-blockedmessage-notification-to-user.png)

<span data-ttu-id="d7186-137">"**这是什么？** " 链接将打开有关 DLP 策略的[文章](data-loss-prevention-policies.md), 可帮助解释阻止邮件的原因。</span><span class="sxs-lookup"><span data-stu-id="d7186-137">The **What's this?** link opens an [article](data-loss-prevention-policies.md) about DLP policies, which helps explain why the message was blocked.</span></span>

### <a name="to-customize-policy-tips"></a><span data-ttu-id="d7186-138">自定义策略提示</span><span class="sxs-lookup"><span data-stu-id="d7186-138">To customize policy tips</span></span>

<span data-ttu-id="d7186-139">若要执行此任务, 必须为您分配具有编辑 DLP 策略的权限的角色。</span><span class="sxs-lookup"><span data-stu-id="d7186-139">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="d7186-140">若要了解详细信息，请参阅[权限](data-loss-prevention-policies.md#permissions)。</span><span class="sxs-lookup"><span data-stu-id="d7186-140">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="d7186-141">转到 Office 365 安全 & 合规中心 ([https://protection.office.com](https://protection.office.com)) 并登录。</span><span class="sxs-lookup"><span data-stu-id="d7186-141">Go to the Office 365 Security & Compliance Center ([https://protection.office.com](https://protection.office.com)) and sign in.</span></span>

2. <span data-ttu-id="d7186-142">选择 "**数据丢失防护** > **策略**"。</span><span class="sxs-lookup"><span data-stu-id="d7186-142">Choose **Data loss prevention** > **Policy**.</span></span> 

3. <span data-ttu-id="d7186-143">选择一个策略, 然后在 "**策略设置**" 旁边, 选择 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="d7186-143">Select a policy, and next to **Policy settings**, choose **Edit**.</span></span>

4. <span data-ttu-id="d7186-144">为策略创建新规则, 或编辑现有规则。</span><span class="sxs-lookup"><span data-stu-id="d7186-144">Either create a new rule, or edit an existing rule for the policy.</span></span><br/>![编辑策略规则](media/dlp-teams-editrule.png)<br/>

5. <span data-ttu-id="d7186-146">在 "**用户通知**" 选项卡上, 选择 "**自定义电子邮件文本"** 和/或 **"自定义策略提示文本"** 选项。</span><span class="sxs-lookup"><span data-stu-id="d7186-146">On the **User notifications** tab, select **Customize the email text** and/or **Customize the policy tip text** options.</span></span><br/><span data-ttu-id="d7186-147">![自定义用户通知和策略提示](media/dlp-teams-editrule-usernotifications.png)</span><span class="sxs-lookup"><span data-stu-id="d7186-147">![Customize user notifications and policy tips](media/dlp-teams-editrule-usernotifications.png)</span></span><br/>  

6. <span data-ttu-id="d7186-148">指定要用于电子邮件通知和/或策略提示的文本, 然后选择 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="d7186-148">Specify the text you want to use for email notifications and/or policy tips, and then choose **Save**.</span></span> 

7. <span data-ttu-id="d7186-149">在 "**策略设置**" 选项卡上, 选择 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="d7186-149">On the **Policy settings** tab, choose **Save**.</span></span>

<span data-ttu-id="d7186-150">允许大约一小时的更改通过数据中心工作并同步到用户帐户。</span><span class="sxs-lookup"><span data-stu-id="d7186-150">Allow approximately one hour for your changes to work their way through your data center and sync to user accounts.</span></span>
 <!-- why are these syncing to user accounts? -->
## <a name="add-microsoft-teams-as-a-location-to-existing-dlp-policies"></a><span data-ttu-id="d7186-151">将 Microsoft 团队添加为现有 DLP 策略的位置</span><span class="sxs-lookup"><span data-stu-id="d7186-151">Add Microsoft Teams as a location to existing DLP policies</span></span>

<span data-ttu-id="d7186-152">若要执行此任务, 必须为您分配具有编辑 DLP 策略的权限的角色。</span><span class="sxs-lookup"><span data-stu-id="d7186-152">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="d7186-153">若要了解详细信息，请参阅[权限](data-loss-prevention-policies.md#permissions)。</span><span class="sxs-lookup"><span data-stu-id="d7186-153">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="d7186-154">转到 Office 365 安全 & 合规中心 ([https://protection.office.com](https://protection.office.com)) 并登录。</span><span class="sxs-lookup"><span data-stu-id="d7186-154">Go to the Office 365 Security & Compliance Center ([https://protection.office.com](https://protection.office.com)) and sign in.</span></span>

2. <span data-ttu-id="d7186-155">选择 "**数据丢失防护** > **策略**"。</span><span class="sxs-lookup"><span data-stu-id="d7186-155">Choose **Data loss prevention** > **Policy**.</span></span> 

3. <span data-ttu-id="d7186-156">选择一个策略, 并查看 "**位置**" 下的值。</span><span class="sxs-lookup"><span data-stu-id="d7186-156">Select a policy, and look at the values under **Locations**.</span></span> <span data-ttu-id="d7186-157">如果你看到**团队聊天和频道消息**, 一切都已设置。</span><span class="sxs-lookup"><span data-stu-id="d7186-157">If you see **Teams chat and channel messages**, you're all set.</span></span> <span data-ttu-id="d7186-158">如果不是, 请单击 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="d7186-158">If you don't, click **Edit**.</span></span><br/><span data-ttu-id="d7186-159">![现有策略的位置](media/dlp-teams-editexistingpolicy.png)</span><span class="sxs-lookup"><span data-stu-id="d7186-159">![Locations for existing policy](media/dlp-teams-editexistingpolicy.png)</span></span><br/>

4. <span data-ttu-id="d7186-160">在 "**状态**" 列中, 为 "**团队聊天" 和 "频道消息**" 启用策略。</span><span class="sxs-lookup"><span data-stu-id="d7186-160">In the **Status** column, turn the policy on for **Teams chat and channel messages**.</span></span><br/><span data-ttu-id="d7186-161">![适用于团队聊天和频道的 DLP](media/dlp-teams-addteamschatschannels.png)</span><span class="sxs-lookup"><span data-stu-id="d7186-161">![DLP for Teams chats and channels](media/dlp-teams-addteamschatschannels.png)</span></span><br/>

5. <span data-ttu-id="d7186-162">保留所有帐户的默认设置, 或指定要包含或排除的帐户。</span><span class="sxs-lookup"><span data-stu-id="d7186-162">Keep the default settings of all accounts, or specify which accounts to include or exclude.</span></span>

6. <span data-ttu-id="d7186-163">单击“保存”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d7186-163">Click **Save**.</span></span>

<span data-ttu-id="d7186-164">允许大约一小时的更改通过数据中心工作并同步到用户帐户。</span><span class="sxs-lookup"><span data-stu-id="d7186-164">Allow approximately one hour for your changes to work their way through your data center and sync to user accounts.</span></span>
<!-- again, why user accounts? -->
## <a name="define-a-new-dlp-policy-for-microsoft-teams"></a><span data-ttu-id="d7186-165">为 Microsoft 团队定义新的 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="d7186-165">Define a new DLP policy for Microsoft Teams</span></span>

<span data-ttu-id="d7186-166">若要执行此任务, 必须为您分配具有编辑 DLP 策略的权限的角色。</span><span class="sxs-lookup"><span data-stu-id="d7186-166">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="d7186-167">若要了解详细信息，请参阅[权限](data-loss-prevention-policies.md#permissions)。</span><span class="sxs-lookup"><span data-stu-id="d7186-167">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="d7186-168">转到 Office 365 安全 & 合规中心 ([https://protection.office.com](https://protection.office.com)) 并登录。</span><span class="sxs-lookup"><span data-stu-id="d7186-168">Go to the Office 365 Security & Compliance Center ([https://protection.office.com](https://protection.office.com)) and sign in.</span></span>

2. <span data-ttu-id="d7186-169">选择 "**数据丢失防护** > **策略** > **+ 创建策略**"。</span><span class="sxs-lookup"><span data-stu-id="d7186-169">Choose **Data loss prevention** > **Policy** > **+ Create a policy**.</span></span> 

3. <span data-ttu-id="d7186-170">选择一个[模板](data-loss-prevention-policies.md#dlp-policy-templates), 然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="d7186-170">Choose a [template](data-loss-prevention-policies.md#dlp-policy-templates), and then choose **Next**.</span></span><br/><span data-ttu-id="d7186-171">在我们的示例中, 我们选择美国的 "个人身份信息" 数据模板。</span><span class="sxs-lookup"><span data-stu-id="d7186-171">In our example, we chose the U.S. Personally Identifiable Information Data template.</span></span><br/><span data-ttu-id="d7186-172">![DLP 策略的隐私模板](media/dlp-teams-createnewpolicy-template.png)</span><span class="sxs-lookup"><span data-stu-id="d7186-172">![Privacy template for DLP policy](media/dlp-teams-createnewpolicy-template.png)</span></span><br/>

4. <span data-ttu-id="d7186-173">在 "**命名策略**" 选项卡上, 指定策略的名称和说明, 然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="d7186-173">On the **Name your policy** tab, specify a name and description for the policy, and then choose **Next**.</span></span> 

5. <span data-ttu-id="d7186-174">在 "**选择位置**" 选项卡上, 保留 "所有位置" 的默认设置, 或选择 "**让我选择特定位置**", 然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="d7186-174">On the **Choose locations** tab, keep the default setting of all locations, or select **Let me choose specific locations**, and then choose **Next**.</span></span><br/><span data-ttu-id="d7186-175">如果您选择了特定位置, 请为您的 DLP 策略选择它们, 然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="d7186-175">If you chose specific locations, select them for your DLP policy, and then choose **Next**.</span></span><br/><span data-ttu-id="d7186-176">![DLP 策略位置](media/dlp-teams-selectlocationsnewpolicy.png)</span><span class="sxs-lookup"><span data-stu-id="d7186-176">![DLP policy locations](media/dlp-teams-selectlocationsnewpolicy.png)</span></span><br/>
    > [!NOTE]
    > <span data-ttu-id="d7186-177">如果要确保包含敏感信息的文档不会被不当共享, 请确保**SharePoint 网站**和**OneDrive 帐户**以及**团队聊天和频道消息**都已打开。</span><span class="sxs-lookup"><span data-stu-id="d7186-177">If you want to make sure documents that contain sensitive information are not shared inappropriately, make sure **SharePoint sites** and **OneDrive accounts** are turned on, along with **Teams chat and channel messages**.</span></span>
<br/>

6. <span data-ttu-id="d7186-178">在 "**策略设置**" 选项卡上的 "**自定义要保护的内容类型**" 下, 保留默认的简单设置, 或选择 "**使用高级设置**", 然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="d7186-178">On the **Policy settings** tab, under **Customize the type of content you want to protect**, keep the default simple settings, or choose **Use advanced settings**, and then choose **Next**.</span></span> <span data-ttu-id="d7186-179">如果选择 "高级设置", 则可以为策略创建或编辑规则。</span><span class="sxs-lookup"><span data-stu-id="d7186-179">If you choose advanced settings, you can create or edit rules for your policy.</span></span> <span data-ttu-id="d7186-180">(若要获取有关此方面的帮助, 请参阅[简单设置与高级设置](data-loss-prevention-policies.md#simple-settings-vs-advanced-settings)。)</span><span class="sxs-lookup"><span data-stu-id="d7186-180">(To get help with this, see [Simple settings vs. advanced settings](data-loss-prevention-policies.md#simple-settings-vs-advanced-settings).)</span></span>

7.  <span data-ttu-id="d7186-181">在 "**策略设置**" 选项卡上的 "**如果检测到敏感信息, 您希望执行什么操作？**" 下, 查看设置。</span><span class="sxs-lookup"><span data-stu-id="d7186-181">On the **Policy settings** tab, under **What do you want to do if we detect sensitive info?**, review the settings.</span></span> <span data-ttu-id="d7186-182">(你可以在此处选择保留默认[策略提示和电子邮件通知](use-notifications-and-policy-tips.md), 或对其进行自定义。)</span><span class="sxs-lookup"><span data-stu-id="d7186-182">(Here's where you can choose to keep default [policy tips and email notifications](use-notifications-and-policy-tips.md), or customize them.)</span></span><br/><span data-ttu-id="d7186-183">![具有提示和通知的 DLP 策略设置](media/dlp-teams-policysettings-tipsemails.png)</span><span class="sxs-lookup"><span data-stu-id="d7186-183">![DLP policy settings with tips and notifications](media/dlp-teams-policysettings-tipsemails.png)</span></span><br/><span data-ttu-id="d7186-184">完成查看或编辑设置后, 选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="d7186-184">When you're finished reviewing or editing settings, choose **Next**.</span></span>

8. <span data-ttu-id="d7186-185">在 "**策略设置**" 选项卡上, 在 "**是否要打开策略或先进行测试？**" 下, 选择是要将策略打开、[先测试](data-loss-prevention-policies.md#roll-out-dlp-policies-gradually-with-test-mode)还是将其保持关闭状态, 然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="d7186-185">On the **Policy settings** tab, under **Do you want to turn on the policy or test things out first?**, choose whether to turn the policy on, [test it first](data-loss-prevention-policies.md#roll-out-dlp-policies-gradually-with-test-mode), or keep it turned off for now, and then choose **Next**.</span></span><br/><span data-ttu-id="d7186-186">![指定是否要启用策略](media/dlp-teams-policysettings-turnonnow.png)</span><span class="sxs-lookup"><span data-stu-id="d7186-186">![Specify whether to turn the policy on](media/dlp-teams-policysettings-turnonnow.png)</span></span><br/>

9. <span data-ttu-id="d7186-187">在 "**查看您的设置**" 选项卡上, 查看新策略的设置。</span><span class="sxs-lookup"><span data-stu-id="d7186-187">On the **Review your settings** tab, review the settings for your new policy.</span></span> <span data-ttu-id="d7186-188">选择 "**编辑**" 以进行更改。</span><span class="sxs-lookup"><span data-stu-id="d7186-188">Choose **Edit** to make changes.</span></span> <span data-ttu-id="d7186-189">完成后, 选择 "**创建**"。</span><span class="sxs-lookup"><span data-stu-id="d7186-189">When you're finished, choose **Create**.</span></span> 

<span data-ttu-id="d7186-190">为新策略留出约一小时的时间, 以便通过数据中心并同步到用户帐户。</span><span class="sxs-lookup"><span data-stu-id="d7186-190">Allow approximately one hour for your new policy to work its way through your data center and sync to user accounts.</span></span>

## <a name="related-articles"></a><span data-ttu-id="d7186-191">相关文章</span><span class="sxs-lookup"><span data-stu-id="d7186-191">Related articles</span></span>

[<span data-ttu-id="d7186-192">创建、测试和优化 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="d7186-192">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)

[<span data-ttu-id="d7186-193">发送电子邮件通知并显示 DLP 策略的策略提示</span><span class="sxs-lookup"><span data-stu-id="d7186-193">Send email notifications and show policy tips for DLP policies</span></span>](use-notifications-and-policy-tips.md)
