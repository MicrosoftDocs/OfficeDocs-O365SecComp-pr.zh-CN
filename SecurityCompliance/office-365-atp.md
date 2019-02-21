---
title: Office 365 高级威胁防护
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 02/20/2019
ms.audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e100fe7c-f2a1-4b7d-9e08-622330b83653
ms.collection:
- M365-security-compliance
description: Office 365 高级威胁防护包括安全附件、安全链接、高级反钓鱼工具、报告工具和威胁智能功能。
ms.openlocfilehash: 5db4c5ff5ae7e536bba1f8730c724d151f367b54
ms.sourcegitcommit: 32cb896aef370764ec6e8f8278ebaf16f1c5ff37
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/20/2019
ms.locfileid: "30123923"
---
# <a name="office-365-advanced-threat-protection"></a><span data-ttu-id="95ce8-103">Office 365 高级威胁防护</span><span class="sxs-lookup"><span data-stu-id="95ce8-103">Office 365 Advanced Threat Protection</span></span>

> [!IMPORTANT]
> <span data-ttu-id="95ce8-p101">本文适用于 Office 365 企业客户。如果您使用的是 Outlook.com、office 365 家庭版或 office 365 个人版, 并且您正在查找有关 Outlook 中的安全链接的信息, 请参阅[Advanced Outlook.com security](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2)。</span><span class="sxs-lookup"><span data-stu-id="95ce8-p101">This article is intended for Office 365 Enterprise customers. If you are using Outlook.com, Office 365 Home, or Office 365 Personal, and you're looking for information about Safe Links in Outlook, see [Advanced Outlook.com security](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

## <a name="overview"></a><span data-ttu-id="95ce8-106">概述</span><span class="sxs-lookup"><span data-stu-id="95ce8-106">Overview</span></span>

<span data-ttu-id="95ce8-p102">Office 365 高级威胁防护 (ATP) 针对电子邮件、链接 (url) 和协作工具带来的恶意威胁来保护您的组织。ATP 包括:</span><span class="sxs-lookup"><span data-stu-id="95ce8-p102">Office 365 Advanced Threat Protection (ATP) safeguards your organization against malicious threats posed by email messages, links (URLs) and collaboration tools. ATP includes:</span></span>

- <span data-ttu-id="95ce8-109">[威胁防护策略](#configure-atp-policies): 定义威胁保护策略以为组织设置适当的保护级别。</span><span class="sxs-lookup"><span data-stu-id="95ce8-109">[Threat protection policies](#configure-atp-policies): Define threat-protection policies to set the appropriate level of protection for your organization.</span></span> 

- <span data-ttu-id="95ce8-110">[报告](#view-atp-reports): 查看实时报告以监视组织中的 ATP 绩效。</span><span class="sxs-lookup"><span data-stu-id="95ce8-110">[Reports](#view-atp-reports): View real-time reports to monitor ATP performance in your organization.</span></span> 

- <span data-ttu-id="95ce8-111">[威胁智能功能](#utilize-threat-intelligence-capabilities): 利用前沿工具调查、了解、模拟和阻止威胁。</span><span class="sxs-lookup"><span data-stu-id="95ce8-111">[Threat intelligence capabilities](#utilize-threat-intelligence-capabilities): Utilize leading-edge tools to investigate, understand, simulate, and prevent threats.</span></span> 
 

## <a name="configure-atp-policies"></a><span data-ttu-id="95ce8-112">配置 ATP 策略</span><span class="sxs-lookup"><span data-stu-id="95ce8-112">Configure ATP policies</span></span>

<span data-ttu-id="95ce8-113">Office 365 ATP 提供了多种工具来为您的组织设置适当的保护级别。</span><span class="sxs-lookup"><span data-stu-id="95ce8-113">Office 365 ATP provides numerous tools to set an appropriate level of protection for your organization.</span></span> 

<span data-ttu-id="95ce8-p103">您的组织的安全团队必须为 Office 365 security & 合规中心中的每个 ATP 工具定义策略。转到 "**威胁管理** > **策略**" 以访问策略选项。</span><span class="sxs-lookup"><span data-stu-id="95ce8-p103">Your organization's security team must define policies for each ATP tool in the Office 365 Security & Compliance Center. Go to **Threat management** > **Policy** to access policy options.</span></span> 

<span data-ttu-id="95ce8-p104">为你的组织定义的策略将确定预定义威胁的行为和保护级别。策略选项非常灵活。例如, 组织的安全团队可以在用户、组织、收件人和域级别设置细化的威胁保护。定期检查策略是非常重要的, 因为每天都会出现新的威胁和挑战。</span><span class="sxs-lookup"><span data-stu-id="95ce8-p104">The policies that are defined for your organization determine the behavior and protection level for predefined threats. Policy options are extremely flexible. For example, your organization's security team can set fine-grained threat protection at the user, organization, recipient, and domain level. It is important to review your policies regularly because new threats and challenges emerge daily.</span></span>  

- <span data-ttu-id="95ce8-p105">[ATP 安全附件](atp-safe-attachments.md): 通过检查电子邮件附件中的恶意内容, 提供为期零天的保护, 以保护您的邮件系统。它将不包含病毒/恶意软件签名的所有邮件和附件路由到特殊环境, 然后使用机器学习和分析技术来检测恶意意图。如果未找到可疑活动, 则邮件将转发到邮箱。若要了解详细信息, 请参阅[设置 Office 365 ATP 安全附件策略](set-up-atp-safe-attachments-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="95ce8-p105">[ATP Safe Attachments](atp-safe-attachments.md): Provides zero-day protection to safeguard your messaging system, by checking email attachments for malicious content. It routes all messages and attachments that do not have a virus/malware signature to a special environment, and then uses machine learning and analysis techniques to detect malicious intent. If no suspicious activity is found, the message is forwarded to the mailbox. To learn more, see [Set up Office 365 ATP Safe Attachments policies](set-up-atp-safe-attachments-policies.md).</span></span>

- <span data-ttu-id="95ce8-p106">[ATP 安全链接](atp-safe-links.md): 提供有关电子邮件和 Office 文件中的 url 的单击时验证的时间。保护正在进行中, 并适用于您的邮件和 Office 环境。每次单击都会扫描链接: 安全链接仍可访问, 并且会动态阻止恶意链接。若要了解详细信息, 请参阅[设置 Office 365 ATP 安全链接策略](https://docs.microsoft.com/en-us/office365/securitycompliance/set-up-atp-safe-links-policies)。</span><span class="sxs-lookup"><span data-stu-id="95ce8-p106">[ATP Safe Links](atp-safe-links.md): Provides time-of-click verification of URLs in emails messages and Office files. Protection is ongoing and applies across your messaging and Office environment. Links are scanned for each click: safe links remain accessible and malicious links are dynamically blocked. To learn more, see [Set up Office 365 ATP Safe Links policies](https://docs.microsoft.com/en-us/office365/securitycompliance/set-up-atp-safe-links-policies).</span></span> 

- <span data-ttu-id="95ce8-p107">[SharePoint、OneDrive 和 Microsoft 团队的 ATP](atp-for-spo-odb-and-teams.md): 在用户协作和共享文件时, 通过识别和阻止工作组网站和文档库中的恶意文件来保护组织。若要了解详细信息, 请参阅[打开 SharePoint、OneDrive 和 Microsoft 团队的 Office 365 ATP](turn-on-atp-for-spo-odb-and-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="95ce8-p107">[ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md): Protects your organization when users collaborate and share files, by identifying and blocking malicious files in team sites and document libraries. To learn more, see [Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span> 

- <span data-ttu-id="95ce8-p108">[ATP 反网络钓鱼防护](atp-anti-phishing.md): 检测模拟用户和自定义域的尝试。它应用机器学习模型和高级模拟检测算法来防止网络钓鱼攻击。若要了解详细信息, 请参阅[设置 Office 365 ATP 反网络钓鱼和反网络钓鱼策略](set-up-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="95ce8-p108">[ATP anti-phishing protection](atp-anti-phishing.md): Detects attempts to impersonate your users and custom domains. It applies machine learning models and advanced impersonation-detection algorithms to avert phishing attacks. To learn more, see [Set up Office 365 ATP anti-phishing and anti-phishing policies](set-up-anti-phishing-policies.md).</span></span>

## <a name="view-atp-reports"></a><span data-ttu-id="95ce8-133">查看 ATP 报表</span><span class="sxs-lookup"><span data-stu-id="95ce8-133">View ATP reports</span></span>

<span data-ttu-id="95ce8-p109">Office 365 ATP 包含一个高级[报告仪表板](view-reports-for-atp.md), 用于监控 ATP 性能。您可以在 Security & 合规性中心的**Reports > 仪表板**中访问它。</span><span class="sxs-lookup"><span data-stu-id="95ce8-p109">Office 365 ATP includes an advanced [reporting dashboard](view-reports-for-atp.md) to monitor your ATP performance. You can access it at **Reports > Dashboard** in the Security & Compliance Center.</span></span> 

<span data-ttu-id="95ce8-p110">实时报告更新, 为你提供最新的见解。这些报告还提供了建议, 并提醒您应对即将发生的威胁。预定义的报告包括[威胁防护状态报告](view-reports-for-atp.md#threat-protection-status-report)、 [atp 文件类型报告](view-reports-for-atp.md#atp-file-types-report)、 [atp 邮件处置报告](view-reports-for-atp.md#atp-message-disposition-report)等。</span><span class="sxs-lookup"><span data-stu-id="95ce8-p110">Reports update in real-time, providing you with the latest insights. These reports also provide recommendations and alert you to imminent threats. Predefined reports include the [Threat Protection Status report](view-reports-for-atp.md#threat-protection-status-report), [ATP File Types report](view-reports-for-atp.md#atp-file-types-report), [ATP Message Disposition report](view-reports-for-atp.md#atp-message-disposition-report) and more.</span></span> 

## <a name="utilize-threat-intelligence-capabilities"></a><span data-ttu-id="95ce8-139">利用威胁智能功能</span><span class="sxs-lookup"><span data-stu-id="95ce8-139">Utilize threat intelligence capabilities</span></span>

<span data-ttu-id="95ce8-140">Office 365 ATP 包含同类最佳的[威胁智能工具](office-365-ti.md), 使组织的安全团队能够预测、理解和防止恶意攻击。</span><span class="sxs-lookup"><span data-stu-id="95ce8-140">Office 365 ATP includes best-of-class [threat intelligence tools](office-365-ti.md) that enable your organization's security team to anticipate, understand, and prevent malicious attacks.</span></span> 

- <span data-ttu-id="95ce8-p111">[威胁跟踪](threat-trackers.md)提供了有关 cybersecurity 问题的最新智能。例如, 您可以查看有关最新恶意软件的信息, 并在将其转换为组织的实际威胁之前采取措施。可用跟踪跟踪包括[注意跟踪跟踪](threat-trackers.md#noteworthy-trackers)、[趋势跟踪跟踪](threat-trackers.md#trending-trackers)、[跟踪的查询](threat-trackers.md#tracked-queries)和[已保存的查询](threat-trackers.md#saved-queries)。</span><span class="sxs-lookup"><span data-stu-id="95ce8-p111">[Threat trackers](threat-trackers.md) provide the latest intelligence on prevailing cybersecurity issues. For example, you can view information about the latest malware, and take countermeasures before it becomes an actual threat to your organization. Available trackers include [Noteworthy trackers](threat-trackers.md#noteworthy-trackers), [Trending trackers](threat-trackers.md#trending-trackers), [Tracked queries](threat-trackers.md#tracked-queries), and [Saved queries](threat-trackers.md#saved-queries).</span></span>

- <span data-ttu-id="95ce8-p112">[浏览器](use-explorer-in-security-and-compliance.md)(也称为 "威胁资源管理器") 是一种实时报告, 可用于确定和分析最近的威胁。您可以配置 Explorer 以显示自定义时段的数据。</span><span class="sxs-lookup"><span data-stu-id="95ce8-p112">[Explorer](use-explorer-in-security-and-compliance.md) (also referred to as Threat Explorer) is a real-time report that allows you to identify and analyze recent threats. You can configure Explorer to show data for custom periods.</span></span>

- <span data-ttu-id="95ce8-p113">利用[攻击模拟器](attack-simulator.md), 您可以在组织中运行现实的攻击方案, 以确定 vulnerabilites。可以模拟当前类型的攻击, 包括[显示名称 spear 网络钓鱼](attack-simulator.md#display-name-spear-phishing-attack)攻击、[密码喷涂攻击](attack-simulator.md#password-spray-attack)、[强力密码攻击](attack-simulator.md#brute-force-password-attack)等等。</span><span class="sxs-lookup"><span data-stu-id="95ce8-p113">[Attack Simulator](attack-simulator.md) allows you to run realistic attack scenarios in your organization to identify vulnerabilites. Simulations of current types of attacks are available, including a [display name spear-phishing attack](attack-simulator.md#display-name-spear-phishing-attack), a [password-spray attack](attack-simulator.md#password-spray-attack), a [brute-force password attack](attack-simulator.md#brute-force-password-attack), and more.</span></span>
    
## <a name="permissions-required-to-use-atp-features"></a><span data-ttu-id="95ce8-148">使用 ATP 功能所需的权限</span><span class="sxs-lookup"><span data-stu-id="95ce8-148">Permissions required to use ATP features</span></span>

<span data-ttu-id="95ce8-p114">若要访问安全 & 合规性中心中的 ATP 功能, 必须为您分配适当的角色。下表包括一些示例:</span><span class="sxs-lookup"><span data-stu-id="95ce8-p114">To access ATP features in the Security & Compliance Center, you must be assigned an appropriate role. The following table includes some examples:</span></span>

|<span data-ttu-id="95ce8-151">角色或角色组</span><span class="sxs-lookup"><span data-stu-id="95ce8-151">Role or role group</span></span>  |<span data-ttu-id="95ce8-152">要了解详细信息的资源</span><span class="sxs-lookup"><span data-stu-id="95ce8-152">Resources to learn more</span></span>  |
|---------|---------|
|<span data-ttu-id="95ce8-153">Office 365 全局管理员</span><span class="sxs-lookup"><span data-stu-id="95ce8-153">Office 365 Global Administrator</span></span> |[<span data-ttu-id="95ce8-154">关于 Office 365 管理员角色</span><span class="sxs-lookup"><span data-stu-id="95ce8-154">About Office 365 admin roles</span></span>](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)|
|<span data-ttu-id="95ce8-155">Security Administrator</span><span class="sxs-lookup"><span data-stu-id="95ce8-155">Security Administrator</span></span> |[<span data-ttu-id="95ce8-156">Azure Active Directory 中的管理员角色权限</span><span class="sxs-lookup"><span data-stu-id="95ce8-156">Administrator role permissions in Azure Active Directory</span></span>](https://docs.microsoft.com/en-us/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|<span data-ttu-id="95ce8-157">Exchange Online 组织管理</span><span class="sxs-lookup"><span data-stu-id="95ce8-157">Exchange Online Organization Management</span></span> |[<span data-ttu-id="95ce8-158">Exchange Online 中的权限</span><span class="sxs-lookup"><span data-stu-id="95ce8-158">Permissions in Exchange Online</span></span>](https://docs.microsoft.com/en-us/exchange/permissions-exo/permissions-exo) <br><span data-ttu-id="95ce8-159">和</span><span class="sxs-lookup"><span data-stu-id="95ce8-159">and</span></span><br> [<span data-ttu-id="95ce8-160">Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="95ce8-160">Exchange Online PowerShell</span></span>](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)|

<span data-ttu-id="95ce8-161">另请参阅:</span><span class="sxs-lookup"><span data-stu-id="95ce8-161">See also:</span></span>
- [<span data-ttu-id="95ce8-162">Office 365 安全 & 合规中心中的权限</span><span class="sxs-lookup"><span data-stu-id="95ce8-162">Permissions in the Office 365 Security & Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md) 

- [<span data-ttu-id="95ce8-163">授予用户对 Office 365 Security & 合规中心的访问权限</span><span class="sxs-lookup"><span data-stu-id="95ce8-163">Give users access to the Office 365 Security & Compliance Center</span></span>](grant-access-to-the-security-and-compliance-center.md)

## <a name="get-office-365-atp"></a><span data-ttu-id="95ce8-164">获取 Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="95ce8-164">Get Office 365 ATP</span></span>

<span data-ttu-id="95ce8-p115">office 365 ATP 包含在 office 365 企业版 E5、Office 365 教育版 A5 和 Microsoft 365 商业版中。如果你的订阅不包含 Office 365 ATP, 则可能会将 atp 作为加载项进行购买。若要了解详细信息, 请参阅以下资源:</span><span class="sxs-lookup"><span data-stu-id="95ce8-p115">Office 365 ATP is included in Office 365 Enterprise E5, Office 365 Education A5, and Microsoft 365 Business. If your subscription does not include Office 365 ATP, you can potentially purchase ATP as an add-on. To learn more, see the following resources:</span></span>

- <span data-ttu-id="95ce8-168">有关包含 ATP 计划的订阅的列表, 请参阅[Office 365 高级威胁防护 (ATP) 可用性](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#office-365-advanced-threat-protection-atp-availability)。</span><span class="sxs-lookup"><span data-stu-id="95ce8-168">See [Office 365 Advanced Threat Protection (ATP) availability](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#office-365-advanced-threat-protection-atp-availability) for a list of subscriptions that include ATP plans.</span></span>

- <span data-ttu-id="95ce8-169">有关计划1和2中包含的功能列表, 请参阅[跨高级威胁防护 (ATP) 计划的功能可用性](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)。</span><span class="sxs-lookup"><span data-stu-id="95ce8-169">See [Feature availability across Advanced Threat Protection (ATP) plans](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans) for a list of features included in Plan 1 and 2.</span></span>

- <span data-ttu-id="95ce8-170">请参阅[获取正确的 Office 365 高级威胁防护](https://products.office.com/exchange/advance-threat-protection#pmg-allup-content), 以比较计划和购买 Office 365 ATP。</span><span class="sxs-lookup"><span data-stu-id="95ce8-170">See [Get the right Office 365 Advanced Threat Protection](https://products.office.com/exchange/advance-threat-protection#pmg-allup-content) to compare plans and purchase Office 365 ATP.</span></span>

## <a name="new-features-in-office-365-atp"></a><span data-ttu-id="95ce8-171">Office 365 ATP 中的新功能</span><span class="sxs-lookup"><span data-stu-id="95ce8-171">New features in Office 365 ATP</span></span>

<span data-ttu-id="95ce8-p116">新功能将持续添加到 Office 365 ATP 中。若要了解详细信息, 请参阅以下资源:</span><span class="sxs-lookup"><span data-stu-id="95ce8-p116">New features are added to Office 365 ATP continually. To learn more, see the following resources:</span></span>

- <span data-ttu-id="95ce8-174">[Microsoft 365 路线图](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection)提供了开发和推出的新功能的列表。</span><span class="sxs-lookup"><span data-stu-id="95ce8-174">The [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection) provides a list of new features in development and rolling out.</span></span>

- <span data-ttu-id="95ce8-175">[Office 365 高级威胁防护服务说明](https://docs.microsoft.com/en-us/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp)描述了 ATP 计划之间的功能和可用性。</span><span class="sxs-lookup"><span data-stu-id="95ce8-175">The [Office 365 Advanced Threat Protection Service Description](https://docs.microsoft.com/en-us/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp) describes features and availability across ATP plans.</span></span>
