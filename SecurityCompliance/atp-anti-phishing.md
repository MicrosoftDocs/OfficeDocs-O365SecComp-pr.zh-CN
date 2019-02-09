---
title: Office 365 中的 ATP 防钓鱼功能
ms.author: krowley
author: kccross
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 5076d0f6-7a59-4d6c-bd07-ba95033f0682
description: ATP 防钓鱼是 Office 365 高级威胁保护的一部分。ATP 防钓鱼适用于以提供的商品和矛网络钓鱼攻击保护的传入消息的计算机学习模型以及模拟检测算法的集合。所有的消息将受到一组广泛的培训来检测网络钓鱼邮件，以及用于防范各种用户和域模拟攻击的高级算法的一组计算机学习模型。
ms.openlocfilehash: c3e44a313bf9c823fbfda138fc5a10294993d509
ms.sourcegitcommit: c1c41744c2de89c9e172f817c8f73bb0ada81a58
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2019
ms.locfileid: "29792267"
---
# <a name="atp-anti-phishing-capabilities-in-office-365"></a><span data-ttu-id="ef27a-105">Office 365 中的 ATP 防钓鱼功能</span><span class="sxs-lookup"><span data-stu-id="ef27a-105">ATP anti-phishing capabilities in Office 365</span></span>

<span data-ttu-id="ef27a-p102">ATP 防钓鱼是[Office 365 高级威胁保护](office-365-atp.md)的一部分。ATP 防钓鱼适用于以提供的商品和矛网络钓鱼攻击保护的传入消息的计算机学习模型以及模拟检测算法的集合。所有的消息将受到一组广泛的培训来检测网络钓鱼邮件，以及用于防范各种用户和域模拟攻击的高级算法的一组计算机学习模型。ATP 防钓鱼保护您的组织根据要策略的设置您的 Office 365 全局或安全管理员。</span><span class="sxs-lookup"><span data-stu-id="ef27a-p102">ATP anti-phishing is part of [Office 365 Advanced Threat Protection](office-365-atp.md). ATP anti-phishing applies a set of machine learning models together with impersonation detection algorithms to incoming messages to provide protection for commodity and spear phishing attacks. All messages are subject to an extensive set of machine learning models trained to detect phishing messages, together with a set of advanced algorithms used to protect against various user and domain impersonation attacks. ATP anti-phishing protects your organization according to polices that are set by your Office 365 global or security administrators.</span></span>
  
<span data-ttu-id="ef27a-110">若要了解详细信息，请参阅[设置 Office 365 中的反钓鱼策略](set-up-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="ef27a-110">To learn more, see [Set up anti-phishing policies in Office 365](set-up-anti-phishing-policies.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="ef27a-p103">ATP 防钓鱼才高级威胁 Protection，它包含订阅，如[Microsoft 365 企业版](https://www.microsoft.com/microsoft-365/enterprise/home)、 [Microsoft 365 企业版](https://www.microsoft.com/microsoft-365/business)、 Office 365 企业 E5、 Office 365 教育版 A5 等中可用。如果您的组织具有不包括 Office 365 ATP 的 Office 365 订阅，您可能可以作为购买 ATP。有关详细信息，请参阅[Office 365 高级威胁保护计划和定价](https://products.office.com/exchange/advance-threat-protection)和[Office 365 高级威胁 Protection Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)。</span><span class="sxs-lookup"><span data-stu-id="ef27a-p103">ATP anti-phishing is only available in Advanced Threat Protection, which is included in subscriptions, such as [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise/home), [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business), Office 365 Enterprise E5, Office 365 Education A5, etc. If your organization has an Office 365 subscription that does not include Office 365 ATP, you can potentially purchase ATP as an add-on. For more information, see [Office 365 Advanced Threat Protection plans and pricing](https://products.office.com/exchange/advance-threat-protection) and the [Office 365 Advanced Threat Protection Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

## <a name="how-atp-anti-phishing-works"></a><span data-ttu-id="ef27a-113">ATP 防钓鱼的工作原理</span><span class="sxs-lookup"><span data-stu-id="ef27a-113">How ATP anti-phishing works</span></span>

<span data-ttu-id="ef27a-p104">ATP 防钓鱼检查邮件可能网络钓鱼的指标的传入消息。只要用户涵盖 ATP 策略 （安全附件、 安全链接或防钓鱼） 将传入邮件计算由多个计算机学习分析邮件以确定是否将策略应用于邮件以及相应的操作的模型执行，基于已配置的策略。</span><span class="sxs-lookup"><span data-stu-id="ef27a-p104">ATP anti-phishing checks incoming messages for indicators that the message may be phishing. Whenever a user is covered by an ATP policy (safe attachments, safe links or anti-phishing) the incoming message is evaluated by multiple machine learning models that analyze the message to determine if the policy applies to the message and the appropriate action is taken, based on the configured policy.</span></span>
  
<span data-ttu-id="ef27a-p105">ATP 防钓鱼允许 Office 365 全局管理员或安全管理员定义提供针对包含模拟的用户或域的网络钓鱼攻击保护的策略。（或两者）。Office 365 全局管理员或安全管理员定义的用户和域应防止使用模拟攻击在策略中的用户或域或通过使用邮箱智能固定的列表。邮箱智能是高级的了解用户的电子邮件习惯和个人联系人。ATP 学习如何每个用户与组织内部和外部的其他用户进行通信，并建立这些关系的映射。此映射允许 ATP 了解有关如何确保正确的邮件被标识为模拟的详细信息。</span><span class="sxs-lookup"><span data-stu-id="ef27a-p105">ATP anti-phishing allows Office 365 global administrators or security admins to define policies that provide protection against phishing attacks that include impersonation of either users or domains. (or both). Office 365 global administrators or security admins define within the policy which user and domains should be protected from impersonation attacks using either a fixed list of users or domains or by using mailbox intelligence. Mailbox intelligence is an advanced understanding of a user's email habits and personal contacts. ATP learns how each individual user communicates with other users inside and outside the organization and builds up a map of these relationships. This map allows ATP to understand more details about how to ensure the right messages are identified as impersonation.</span></span>
  
<span data-ttu-id="ef27a-p106">ATP 防钓鱼策略可应用到一组特定的联系人或在组织中的组或整个域或所有自定义域。若要了解详细信息，请参阅[设置 Office 365 中的反钓鱼策略](set-up-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="ef27a-p106">ATP anti-phishing polices can be applied to a specific set of people or groups in your organization, or to an entire domain or all of your custom domains. To learn more, see [Set up anti-phishing policies in Office 365](set-up-anti-phishing-policies.md).</span></span>
  
## <a name="how-to-get-atp-anti-phishing"></a><span data-ttu-id="ef27a-124">如何获取 ATP 防钓鱼</span><span class="sxs-lookup"><span data-stu-id="ef27a-124">How to get ATP anti-phishing</span></span>

<span data-ttu-id="ef27a-p107">ATP 防钓鱼功能属于[高级威胁保护](office-365-atp.md);但是，ATP 防钓鱼保护适用时防钓鱼策略定义。（一个示例是一个基于模拟的策略）。请参阅[Office 365 中的反钓鱼策略设置](set-up-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="ef27a-p107">ATP Anti-Phishing features are part of [Advanced Threat Protection](office-365-atp.md); however, ATP anti-phishing protection applies when anti-phishing policies are defined. (One example is an impersonation-based policy.) See [Set up anti-phishing policies in Office 365](set-up-anti-phishing-policies.md).</span></span>
  
## <a name="how-to-know-if-atp-anti-phishing-is-in-place"></a><span data-ttu-id="ef27a-127">如何知道 ATP 防钓鱼是否就地</span><span class="sxs-lookup"><span data-stu-id="ef27a-127">How to know if ATP anti-phishing is in place</span></span>

<span data-ttu-id="ef27a-p108">为了保护需要生效，必须定义 ATP 防钓鱼策略。检查这首先要验证保护是就地。</span><span class="sxs-lookup"><span data-stu-id="ef27a-p108">ATP anti-phishing policies must be defined in order for protection to be in effect. Check this first to verify protection is in place.</span></span>

<span data-ttu-id="ef27a-p109">此外，报告是可用于显示如何使用服务运行您的组织。若要了解详细信息，请参阅[Office 365 高级威胁 protection 查看报告](view-reports-for-atp.md)。</span><span class="sxs-lookup"><span data-stu-id="ef27a-p109">In addition, reports are available to show how the service is working for your organization. To learn more, see [View reports for Office 365 Advanced Threat Protection](view-reports-for-atp.md).</span></span>

<span data-ttu-id="ef27a-132">对于 ATP 防钓鱼学习模型是活动的某个特定用户的计算机，用户必须定义[ATP 安全附件](atp-safe-attachments.md)、 [ATP 安全链接](atp-safe-links.md)或 ATP 防钓鱼策略的一部分。</span><span class="sxs-lookup"><span data-stu-id="ef27a-132">For ATP anti-phishing machine learning models to be active for a particular user, that user must be part of a defined [ATP Safe Attachements](atp-safe-attachments.md), [ATP Safe Links](atp-safe-links.md), or ATP Anti-Phishing policy.</span></span> 

<span data-ttu-id="ef27a-p110">下表介绍了几个示例方案。在每个示例中，组织在使用 Office 365 企业 E5，其中包括高级威胁保护。</span><span class="sxs-lookup"><span data-stu-id="ef27a-p110">The following table describes a few example scenarios. In each of these examples, the organization is using Office 365 Enterprise E5, which includes Advanced Threat Protection.</span></span>
  
|<span data-ttu-id="ef27a-135">**示例应用场景**</span><span class="sxs-lookup"><span data-stu-id="ef27a-135">**Example scenario**</span></span>|<span data-ttu-id="ef27a-136">**ATP 防钓鱼不适用于这种情况下？**</span><span class="sxs-lookup"><span data-stu-id="ef27a-136">**Does ATP anti-phishing apply in this case?**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ef27a-137">Pat 组织具有 Office 365 企业 E5，但没有人已定义的 ATP 安全附件，ATP 安全链接或 ATP 尚未高级网络钓鱼的任何策略。</span><span class="sxs-lookup"><span data-stu-id="ef27a-137">Pat's organization has Office 365 Enterprise E5, but no one has defined any policies for ATP safe attachments, ATP safe links or ATP advanced phishing yet.</span></span>|<span data-ttu-id="ef27a-p111">不。虽然可用的功能，必须为了 ATP 计算机学习模型，以定义至少一个 ATP 策略。用于模拟的 ATP 防钓鱼策略还必须满足。</span><span class="sxs-lookup"><span data-stu-id="ef27a-p111">No. Although the feature is available, at least one ATP policy must be defined in order for the ATP machine learning models to work. For impersonation an ATP anti-phishing policy must also be in place.</span></span>|
|<span data-ttu-id="ef27a-p112">李是 contoso 销售部的员工。李的组织仅财务人员应用于的位置中具有 ATP 防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="ef27a-p112">Lee is an employee in the sales department at Contoso. Lee's organization has an ATP anti-phishing policy in place that applies to finance employees only.</span></span>|<span data-ttu-id="ef27a-p113">不。在这种情况下，ATP 防钓鱼 （机模型和模拟保护） 将应用于 finance 员工，但其他员工，包括销售部门，不会。</span><span class="sxs-lookup"><span data-stu-id="ef27a-p113">No. In this case, ATP anti-phishing (machine models and impersonation protection) would apply to finance employees, but other employees, including the sales department, would not.</span></span>|
|<span data-ttu-id="ef27a-p114">昨天、 上 Jean 的组织的 Office 365 管理员设置适用于所有员工 ATP 防钓鱼策略。如今，前面 Jean 收到包含模拟策略所涉及的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="ef27a-p114">Yesterday, an Office 365 administrator at Jean's organization set up an ATP anti-phishing policy that applies to all employees. Earlier today, Jean received an email message that includes an impersonation covered by the policy.</span></span>|<span data-ttu-id="ef27a-p115">是的。本示例中，Jean 具有许可证的高级威胁保护，并已定义 ATP 防钓鱼策略，其中包括 Jean。通常大约需要 30 分钟的新策略跨数据中心; 才会生效由于一天过后在这种情况下，该策略应实际上所示。</span><span class="sxs-lookup"><span data-stu-id="ef27a-p115">Yes. In this example, Jean has a license for Advanced Threat Protection, and an ATP anti-phishing policy that includes Jean has been defined. It typically takes about 30 minutes for a new policy to take effect across datacenters; since a day has passed in this case, the policy should be in effect.</span></span>|

## <a name="related-topics"></a><span data-ttu-id="ef27a-150">相关主题</span><span class="sxs-lookup"><span data-stu-id="ef27a-150">Related topics</span></span>

[<span data-ttu-id="ef27a-151">Office 365 高级威胁防护</span><span class="sxs-lookup"><span data-stu-id="ef27a-151">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
  
[<span data-ttu-id="ef27a-152">Office 365 中的防钓鱼保护</span><span class="sxs-lookup"><span data-stu-id="ef27a-152">Anti-phishing protection in Office 365</span></span>](anti-phishing-protection.md)
  
[<span data-ttu-id="ef27a-153">设置 Office 365 中的反钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="ef27a-153">Set up anti-phishing policies in Office 365</span></span>](set-up-anti-phishing-policies.md)
  
[<span data-ttu-id="ef27a-154">ATP Office 365 中的安全链接</span><span class="sxs-lookup"><span data-stu-id="ef27a-154">ATP safe links in Office 365</span></span>](atp-safe-links.md)
  
[<span data-ttu-id="ef27a-155">设置 Office 365 中的 ATP 安全链接策略</span><span class="sxs-lookup"><span data-stu-id="ef27a-155">Set up ATP safe links policies in Office 365</span></span>](set-up-atp-safe-links-policies.md)
  
[<span data-ttu-id="ef27a-156">Office 365 中的 ATP 安全附件</span><span class="sxs-lookup"><span data-stu-id="ef27a-156">ATP safe attachments in Office 365</span></span>](atp-safe-attachments.md)
  
[<span data-ttu-id="ef27a-157">设置 Office 365 中的 ATP 附件安全策略</span><span class="sxs-lookup"><span data-stu-id="ef27a-157">Set up ATP safe attachments policies in Office 365</span></span>](set-up-atp-safe-attachments-policies.md)
  
[<span data-ttu-id="ef27a-158">查看高级威胁保护报告</span><span class="sxs-lookup"><span data-stu-id="ef27a-158">View the reports for Advanced Threat Protection</span></span>](view-reports-for-atp.md)
