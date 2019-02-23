---
title: Office 365 中的 ATP 防钓鱼功能
ms.author: krowley
author: kccross
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 5076d0f6-7a59-4d6c-bd07-ba95033f0682
description: ATP 反网络钓鱼是 Office 365 高级威胁防护的一部分。ATP 反网络钓鱼对传入的邮件应用一组计算机学习模式以及模拟检测算法, 以提供对商品和 spear 网络钓鱼攻击的保护。所有邮件都服从一组专门培训的计算机学习模式, 以检测网络钓鱼邮件, 以及一组用于防止各种用户和域模拟攻击的高级算法。
ms.openlocfilehash: 1510fb0ca248b847eb02e648295c350b11c4dd28
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30215132"
---
# <a name="atp-anti-phishing-capabilities-in-office-365"></a><span data-ttu-id="80dbd-105">Office 365 中的 ATP 防钓鱼功能</span><span class="sxs-lookup"><span data-stu-id="80dbd-105">ATP anti-phishing capabilities in Office 365</span></span>

<span data-ttu-id="80dbd-p102">ATP 反网络钓鱼是[Office 365 高级威胁防护](office-365-atp.md)的一部分。ATP 反网络钓鱼对传入的邮件应用一组计算机学习模式以及模拟检测算法, 以提供对商品和 spear 网络钓鱼攻击的保护。所有邮件都服从一组专门培训的计算机学习模式, 以检测网络钓鱼邮件, 以及一组用于防止各种用户和域模拟攻击的高级算法。ATP 反网络钓鱼根据 Office 365 全局或安全管理员设置的策略来保护您的组织。</span><span class="sxs-lookup"><span data-stu-id="80dbd-p102">ATP anti-phishing is part of [Office 365 Advanced Threat Protection](office-365-atp.md). ATP anti-phishing applies a set of machine learning models together with impersonation detection algorithms to incoming messages to provide protection for commodity and spear phishing attacks. All messages are subject to an extensive set of machine learning models trained to detect phishing messages, together with a set of advanced algorithms used to protect against various user and domain impersonation attacks. ATP anti-phishing protects your organization according to polices that are set by your Office 365 global or security administrators.</span></span>
  
<span data-ttu-id="80dbd-110">若要了解详细信息, 请参阅[在 Office 365 中设置反网络钓鱼策略](set-up-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="80dbd-110">To learn more, see [Set up anti-phishing policies in Office 365](set-up-anti-phishing-policies.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="80dbd-p103">ATP 反网络钓鱼仅适用于订阅中包含的高级威胁防护, 如[microsoft 365 企业版](https://www.microsoft.com/microsoft-365/enterprise/home)、 [microsoft 365 商业](https://www.microsoft.com/microsoft-365/business)版、office 365 企业版 E5、office 365 教育版 A5 等。如果您的组织有一个不包含 office 365 ATP 的 office 365 订阅, 则可能会将 ATP 作为加载项进行购买。有关详细信息, 请参阅[office 365 高级威胁防护计划和定价](https://products.office.com/exchange/advance-threat-protection)和[Office 365 高级威胁防护服务说明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)。</span><span class="sxs-lookup"><span data-stu-id="80dbd-p103">ATP anti-phishing is only available in Advanced Threat Protection, which is included in subscriptions, such as [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise/home), [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business), Office 365 Enterprise E5, Office 365 Education A5, etc. If your organization has an Office 365 subscription that does not include Office 365 ATP, you can potentially purchase ATP as an add-on. For more information, see [Office 365 Advanced Threat Protection plans and pricing](https://products.office.com/exchange/advance-threat-protection) and the [Office 365 Advanced Threat Protection Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

## <a name="how-atp-anti-phishing-works"></a><span data-ttu-id="80dbd-113">ATP 反网络钓鱼的工作原理</span><span class="sxs-lookup"><span data-stu-id="80dbd-113">How ATP anti-phishing works</span></span>

<span data-ttu-id="80dbd-p104">ATP 反网络钓鱼检查传入邮件, 以了解邮件可能是网络钓鱼的指示器。只要 ATP 策略涵盖用户 (安全的附件、安全链接或反钓鱼), 传入的邮件将由多个机器学习模型进行评估, 以确定该策略是否适用于该邮件, 以及适当的操作是根据配置的策略执行。</span><span class="sxs-lookup"><span data-stu-id="80dbd-p104">ATP anti-phishing checks incoming messages for indicators that the message may be phishing. Whenever a user is covered by an ATP policy (safe attachments, safe links or anti-phishing) the incoming message is evaluated by multiple machine learning models that analyze the message to determine if the policy applies to the message and the appropriate action is taken, based on the configured policy.</span></span>
  
<span data-ttu-id="80dbd-p105">ATP 反网络钓鱼允许 Office 365 全局管理员或安全管理员定义策略, 以抵御包含用户或域模拟的网络钓鱼攻击。(或两者)。Office 365 全局管理员或安全管理员在策略中定义应使用用户或域的固定列表或使用邮箱智能来保护用户和域的模拟攻击。邮箱智能是对用户的电子邮件习惯和个人联系人的高级了解。ATP 学习了每个用户如何与组织内部和外部的其他用户通信, 并建立这些关系的地图。此地图允许 ATP 了解有关如何确保将正确的邮件标识为模拟的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="80dbd-p105">ATP anti-phishing allows Office 365 global administrators or security admins to define policies that provide protection against phishing attacks that include impersonation of either users or domains. (or both). Office 365 global administrators or security admins define within the policy which user and domains should be protected from impersonation attacks using either a fixed list of users or domains or by using mailbox intelligence. Mailbox intelligence is an advanced understanding of a user's email habits and personal contacts. ATP learns how each individual user communicates with other users inside and outside the organization and builds up a map of these relationships. This map allows ATP to understand more details about how to ensure the right messages are identified as impersonation.</span></span>
  
<span data-ttu-id="80dbd-p106">ATP 反网络钓鱼策略可应用于组织中的一组特定用户或组, 或者应用于整个域或所有自定义域。若要了解详细信息, 请参阅[在 Office 365 中设置反网络钓鱼策略](set-up-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="80dbd-p106">ATP anti-phishing polices can be applied to a specific set of people or groups in your organization, or to an entire domain or all of your custom domains. To learn more, see [Set up anti-phishing policies in Office 365](set-up-anti-phishing-policies.md).</span></span>
  
## <a name="how-to-get-atp-anti-phishing"></a><span data-ttu-id="80dbd-124">如何获取 ATP 反网络钓鱼</span><span class="sxs-lookup"><span data-stu-id="80dbd-124">How to get ATP anti-phishing</span></span>

<span data-ttu-id="80dbd-p107">ATP 反网络钓鱼功能是[高级威胁防护](office-365-atp.md)的一部分;但是, 当定义了反网络钓鱼策略时, 将应用 ATP 反钓鱼保护。(一个示例是基于模拟的策略。)请参阅[在 Office 365 中设置反网络钓鱼策略](set-up-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="80dbd-p107">ATP Anti-Phishing features are part of [Advanced Threat Protection](office-365-atp.md); however, ATP anti-phishing protection applies when anti-phishing policies are defined. (One example is an impersonation-based policy.) See [Set up anti-phishing policies in Office 365](set-up-anti-phishing-policies.md).</span></span>
  
## <a name="how-to-know-if-atp-anti-phishing-is-in-place"></a><span data-ttu-id="80dbd-127">如何了解 ATP 反网络钓鱼是否已就绪</span><span class="sxs-lookup"><span data-stu-id="80dbd-127">How to know if ATP anti-phishing is in place</span></span>

<span data-ttu-id="80dbd-p108">必须定义 ATP 反网络钓鱼策略, 才能使保护生效。先检查此项以验证是否已实施保护。</span><span class="sxs-lookup"><span data-stu-id="80dbd-p108">ATP anti-phishing policies must be defined in order for protection to be in effect. Check this first to verify protection is in place.</span></span>

<span data-ttu-id="80dbd-p109">此外, 报告可用于显示服务在您的组织中的工作方式。若要了解详细信息, 请参阅[查看 Office 365 高级威胁防护的报告](view-reports-for-atp.md)。</span><span class="sxs-lookup"><span data-stu-id="80dbd-p109">In addition, reports are available to show how the service is working for your organization. To learn more, see [View reports for Office 365 Advanced Threat Protection](view-reports-for-atp.md).</span></span>

<span data-ttu-id="80dbd-132">对于特定用户的 ATP 反钓鱼计算机学习模型处于活动状态, 该用户必须是定义的[ATP 安全附件](atp-safe-attachments.md)、 [atp 安全链接](atp-safe-links.md)或 atp 反网络钓鱼策略的一部分。</span><span class="sxs-lookup"><span data-stu-id="80dbd-132">For ATP anti-phishing machine learning models to be active for a particular user, that user must be part of a defined [ATP Safe attachments](atp-safe-attachments.md), [ATP Safe Links](atp-safe-links.md), or ATP Anti-Phishing policy.</span></span> 

<span data-ttu-id="80dbd-p110">下表介绍了几个示例方案。在上述每个示例中, 组织都使用 Office 365 企业版 E5, 其中包括高级威胁防护。</span><span class="sxs-lookup"><span data-stu-id="80dbd-p110">The following table describes a few example scenarios. In each of these examples, the organization is using Office 365 Enterprise E5, which includes Advanced Threat Protection.</span></span>
  
|<span data-ttu-id="80dbd-135">**示例应用场景**</span><span class="sxs-lookup"><span data-stu-id="80dbd-135">**Example scenario**</span></span>|<span data-ttu-id="80dbd-136">**在这种情况下, ATP 反网络钓鱼是否适用？**</span><span class="sxs-lookup"><span data-stu-id="80dbd-136">**Does ATP anti-phishing apply in this case?**</span></span>|
|:-----|:-----|
|<span data-ttu-id="80dbd-137">Pat 的组织拥有 Office 365 企业版 E5, 但没有人为 atp 安全附件、atp 安全链接或 atp 高级网络钓鱼定义任何策略。</span><span class="sxs-lookup"><span data-stu-id="80dbd-137">Pat's organization has Office 365 Enterprise E5, but no one has defined any policies for ATP safe attachments, ATP safe links or ATP advanced phishing yet.</span></span>|<span data-ttu-id="80dbd-p111">不。虽然该功能可用, 但必须至少定义一个 atp 策略, 才能使 ATP 机器学习模型能够正常工作。对于模拟, ATP 反网络钓鱼策略也必须已准备就绪。</span><span class="sxs-lookup"><span data-stu-id="80dbd-p111">No. Although the feature is available, at least one ATP policy must be defined in order for the ATP machine learning models to work. For impersonation an ATP anti-phishing policy must also be in place.</span></span>|
|<span data-ttu-id="80dbd-p112">先生为在 Contoso 的销售部门的员工。先生/她的组织已实施了仅适用于财务员工的 ATP 反网络钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="80dbd-p112">Lee is an employee in the sales department at Contoso. Lee's organization has an ATP anti-phishing policy in place that applies to finance employees only.</span></span>|<span data-ttu-id="80dbd-p113">不。在这种情况下, ATP 反网络钓鱼 (计算机模型和模拟保护) 将应用于财务员工, 但其他员工 (包括销售部门) 将不会。</span><span class="sxs-lookup"><span data-stu-id="80dbd-p113">No. In this case, ATP anti-phishing (machine models and impersonation protection) would apply to finance employees, but other employees, including the sales department, would not.</span></span>|
|<span data-ttu-id="80dbd-p114">昨天, Jean 的组织中的 Office 365 管理员设置适用于所有员工的 ATP 反网络钓鱼策略。在今天的早期, Jean 收到一封包含策略所涵盖的模拟的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="80dbd-p114">Yesterday, an Office 365 administrator at Jean's organization set up an ATP anti-phishing policy that applies to all employees. Earlier today, Jean received an email message that includes an impersonation covered by the policy.</span></span>|<span data-ttu-id="80dbd-p115">是的。在此示例中, Jean 具有高级威胁防护的许可证, 并且已定义包括 Jean 的 ATP 反网络钓鱼策略。新策略通常需要30分钟的时间才能在数据中心内生效;由于在这种情况下已过一天, 因此该策略应有效。</span><span class="sxs-lookup"><span data-stu-id="80dbd-p115">Yes. In this example, Jean has a license for Advanced Threat Protection, and an ATP anti-phishing policy that includes Jean has been defined. It typically takes about 30 minutes for a new policy to take effect across datacenters; since a day has passed in this case, the policy should be in effect.</span></span>|

## <a name="related-topics"></a><span data-ttu-id="80dbd-150">相关主题</span><span class="sxs-lookup"><span data-stu-id="80dbd-150">Related topics</span></span>

[<span data-ttu-id="80dbd-151">Office 365 高级威胁防护</span><span class="sxs-lookup"><span data-stu-id="80dbd-151">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
  
[<span data-ttu-id="80dbd-152">Office 365 中的防钓鱼保护</span><span class="sxs-lookup"><span data-stu-id="80dbd-152">Anti-phishing protection in Office 365</span></span>](anti-phishing-protection.md)
  
[<span data-ttu-id="80dbd-153">在 Office 365 中设置反网络钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="80dbd-153">Set up anti-phishing policies in Office 365</span></span>](set-up-anti-phishing-policies.md)
  
[<span data-ttu-id="80dbd-154">Office 365 中的 ATP 安全链接</span><span class="sxs-lookup"><span data-stu-id="80dbd-154">ATP safe links in Office 365</span></span>](atp-safe-links.md)
  
[<span data-ttu-id="80dbd-155">在 Office 365 中设置 ATP 安全链接策略</span><span class="sxs-lookup"><span data-stu-id="80dbd-155">Set up ATP safe links policies in Office 365</span></span>](set-up-atp-safe-links-policies.md)
  
[<span data-ttu-id="80dbd-156">Office 365 中的 ATP 安全附件</span><span class="sxs-lookup"><span data-stu-id="80dbd-156">ATP safe attachments in Office 365</span></span>](atp-safe-attachments.md)
  
[<span data-ttu-id="80dbd-157">在 Office 365 中设置 ATP 安全附件策略</span><span class="sxs-lookup"><span data-stu-id="80dbd-157">Set up ATP safe attachments policies in Office 365</span></span>](set-up-atp-safe-attachments-policies.md)
  
[<span data-ttu-id="80dbd-158">查看高级威胁防护报告</span><span class="sxs-lookup"><span data-stu-id="80dbd-158">View the reports for Advanced Threat Protection</span></span>](view-reports-for-atp.md)
