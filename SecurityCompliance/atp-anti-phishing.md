---
title: Office 365 中的 ATP 防钓鱼功能
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 7/2/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 5076d0f6-7a59-4d6c-bd07-ba95033f0682
description: ATP 防钓鱼作为 Office 365 高级威胁保护的一部分提供。ATP 防钓鱼适用于以提供的商品和矛网络钓鱼攻击保护的传入消息的计算机学习模型以及模拟检测算法的集合。所有的消息将受到一组广泛的培训来检测网络钓鱼邮件，以及用于防范各种用户和域模拟攻击的高级算法的一组计算机学习模型。ATP 防钓鱼保护您的组织根据要策略的设置您的 Office 365 全局或安全管理员。
ms.openlocfilehash: e7bb4c4a28109c40bf745a25c9c8366558cf2ac7
ms.sourcegitcommit: ba2175e394d0cb9f8ede9206aabb44b5b677fa0a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/11/2018
ms.locfileid: "25496886"
---
# <a name="atp-anti-phishing-capabilities-in-office-365"></a><span data-ttu-id="3e06f-106">Office 365 中的 ATP 防钓鱼功能</span><span class="sxs-lookup"><span data-stu-id="3e06f-106">ATP anti-phishing capabilities in Office 365</span></span>

<span data-ttu-id="3e06f-p102">ATP 防钓鱼作为[Office 365 高级威胁保护](https://technet.microsoft.com/en-us/library/exchange-online-advanced-threat-protection-service-description.aspx)的一部分提供。ATP 防钓鱼适用于以提供的商品和矛网络钓鱼攻击保护的传入消息的计算机学习模型以及模拟检测算法的集合。所有的消息将受到一组广泛的培训来检测网络钓鱼邮件，以及用于防范各种用户和域模拟攻击的高级算法的一组计算机学习模型。ATP 防钓鱼保护您的组织根据要策略的设置您的 Office 365 全局或安全管理员。</span><span class="sxs-lookup"><span data-stu-id="3e06f-p102">ATP anti-phishing is offered as part of [Office 365 Advanced Threat Protection](https://technet.microsoft.com/en-us/library/exchange-online-advanced-threat-protection-service-description.aspx). ATP anti-phishing applies a set of machine learning models together with impersonation detection algorithms to incoming messages to provide protection for commodity and spear phishing attacks. All messages are subject to an extensive set of machine learning models trained to detect phishing messages, together with a set of advanced algorithms used to protect against various user and domain impersonation attacks. ATP anti-phishing protects your organization according to polices that are set by your Office 365 global or security administrators.</span></span>
  
<span data-ttu-id="3e06f-111">若要了解详细信息，请参阅[设置 Office 365 中的反钓鱼策略](set-up-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="3e06f-111">To learn more, see [Set up anti-phishing policies in Office 365](set-up-anti-phishing-policies.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="3e06f-p103">ATP 防钓鱼才高级威胁防护，提供与 Office 365 企业 E5 中可用。如果您的组织使用的另一个 Office 365 企业版订阅，高级威胁保护可以作为加载项进行购买。(作为全局管理员在 Office 365 管理中心中，选择**帐单** \> **添加订阅**。)有关规划选项的详细信息，请参阅[比较 Office 365 的业务计划](https://go.microsoft.com/fwlink/?linkid=844053)。</span><span class="sxs-lookup"><span data-stu-id="3e06f-p103">ATP anti-phishing is only available in Advanced Threat Protection, available with Office 365 Enterprise E5. If your organization is using another Office 365 Enterprise subscription, Advanced Threat Protection can be purchased as an add-on. (As a global admin, in the Office 365 admin center, choose **Billing** \> **Add subscriptions**.) For more information about plan options, see [Compare All Office 365 for Business Plans](https://go.microsoft.com/fwlink/?linkid=844053).</span></span> 
    
## <a name="how-atp-anti-phishing-works"></a><span data-ttu-id="3e06f-115">ATP 防钓鱼的工作原理</span><span class="sxs-lookup"><span data-stu-id="3e06f-115">How ATP anti-phishing works</span></span>
<span data-ttu-id="3e06f-116"><a name="Howantiphishworks"> </a></span><span class="sxs-lookup"><span data-stu-id="3e06f-116"></span></span>

<span data-ttu-id="3e06f-p104">ATP 防钓鱼检查邮件可能网络钓鱼的指标的传入消息。只要用户涵盖 ATP 策略 （安全附件、 安全链接或防钓鱼） 将传入邮件计算由多个计算机学习分析邮件以确定是否将策略应用于邮件以及相应的操作的模型执行，基于已配置的策略。</span><span class="sxs-lookup"><span data-stu-id="3e06f-p104">ATP anti-phishing checks incoming messages for indicators that the message may be phishing. Whenever a user is covered by an ATP policy (safe attachments, safe links or anti-phishing) the incoming message is evaluated by multiple machine learning models that analyze the message to determine if the policy applies to the message and the appropriate action is taken, based on the configured policy.</span></span>
  
<span data-ttu-id="3e06f-p105">ATP 防钓鱼允许 Office 365 全局管理员或安全管理员定义提供针对包含模拟的用户或域的网络钓鱼攻击保护的策略。（或两者）。Office 365 全局管理员或安全管理员定义的用户和域应防止使用模拟攻击在策略中的用户或域或通过使用邮箱智能固定的列表。邮箱智能是高级的了解用户的电子邮件习惯和个人联系人。ATP 学习如何每个用户与组织内部和外部的其他用户进行通信，并建立这些关系的映射。此映射允许 ATP 了解有关如何确保正确的邮件被标识为模拟的详细信息。</span><span class="sxs-lookup"><span data-stu-id="3e06f-p105">ATP anti-phishing allows Office 365 global administrators or security admins to define policies that provide protection against phishing attacks that include impersonation of either users or domains. (or both). Office 365 global administrators or security admins define within the policy which user and domains should be protected from impersonation attacks using either a fixed list of users or domains or by using mailbox intelligence. Mailbox intelligence is an advanced understanding of a user's email habits and personal contacts. ATP learns how each individual user communicates with other users inside and outside the organization and builds up a map of these relationships. This map allows ATP to understand more details about how to ensure the right messages are identified as impersonation.</span></span>
  
<span data-ttu-id="3e06f-p106">ATP 防钓鱼策略可应用到一组特定的联系人或在组织中的组或整个域或所有自定义域。若要了解详细信息，请参阅[设置 Office 365 中的反钓鱼策略](set-up-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="3e06f-p106">ATP anti-phishing polices can be applied to a specific set of people or groups in your organization, or to an entire domain or all of your custom domains. To learn more, see [Set up anti-phishing policies in Office 365](set-up-anti-phishing-policies.md).</span></span>
  
## <a name="how-to-get-atp-anti-phishing"></a><span data-ttu-id="3e06f-127">如何获取 ATP 防钓鱼</span><span class="sxs-lookup"><span data-stu-id="3e06f-127">How to get ATP anti-phishing</span></span>
<span data-ttu-id="3e06f-128"><a name="Howtogetantiphish"> </a></span><span class="sxs-lookup"><span data-stu-id="3e06f-128"></span></span>

<span data-ttu-id="3e06f-p107">ATP 防钓鱼是高级威胁保护，它包含 Office 365 企业 E5 的一部分。也可以作为 Office 365 企业版 E1 或 Office 365 企业版 E3 购买高级的威胁保护。有关规划选项的详细信息，请参阅[比较 Office 365 的业务计划](https://go.microsoft.com/fwlink/?linkid=844053)。</span><span class="sxs-lookup"><span data-stu-id="3e06f-p107">ATP anti-phishing is part of Advanced Threat Protection, which is included in Office 365 Enterprise E5. Advanced Threat Protection can also be purchased as an add-on to Office 365 Enterprise E1 or Office 365 Enterprise E3. For more information about plan options, see [Compare All Office 365 for Business Plans](https://go.microsoft.com/fwlink/?linkid=844053).</span></span>
  
<span data-ttu-id="3e06f-p108">ATP 防钓鱼适用时防钓鱼策略，如基于模拟的策略设置。（请参阅[Set up Office 365 中的反钓鱼策略](set-up-anti-phishing-policies.md)）。</span><span class="sxs-lookup"><span data-stu-id="3e06f-p108">ATP anti-phishing applies when an anti-phishing policy, such as an impersonation-based policy are set up. (See [Set up anti-phishing policies in Office 365](set-up-anti-phishing-policies.md).)</span></span>
  
## <a name="how-to-know-if-atp-anti-phishing-is-in-place"></a><span data-ttu-id="3e06f-134">如何知道 ATP 防钓鱼是否就地</span><span class="sxs-lookup"><span data-stu-id="3e06f-134">How to know if ATP anti-phishing is in place</span></span>
<span data-ttu-id="3e06f-135"><a name="IsantiphishOn"> </a></span><span class="sxs-lookup"><span data-stu-id="3e06f-135"></span></span>

<span data-ttu-id="3e06f-p109">为了保护处于活动状态，必须定义 ATP 防钓鱼策略。对于 ATP 防钓鱼机器学习模型是活动的用户，该用户必须是安全的定义的附件、 安全链接或防钓鱼策略的一部分。下表介绍了几个示例方案。在每个示例中，组织在使用 Office 365 企业 E5，其中包括高级威胁保护。</span><span class="sxs-lookup"><span data-stu-id="3e06f-p109">ATP anti-phishing policies must be defined in order for protection to be active. For ATP anti-phishing machine learning models to be active for a user, that user must be part of a defined safe attachment, safe links, or anti-phishing policy. The following table describes a few example scenarios. In each of these examples, the organization is using Office 365 Enterprise E5, which includes Advanced Threat Protection.</span></span>
  
|<span data-ttu-id="3e06f-140">**示例应用场景**</span><span class="sxs-lookup"><span data-stu-id="3e06f-140">**Example scenario**</span></span>|<span data-ttu-id="3e06f-141">**ATP 防钓鱼不适用于这种情况下？**</span><span class="sxs-lookup"><span data-stu-id="3e06f-141">**Does ATP anti-phishing apply in this case?**</span></span>|
|:-----|:-----|
|<span data-ttu-id="3e06f-142">Pat 组织具有 Office 365 企业 E5，但没有人已定义的 ATP 安全附件，ATP 安全链接或 ATP 尚未高级网络钓鱼的任何策略。</span><span class="sxs-lookup"><span data-stu-id="3e06f-142">Pat's organization has Office 365 Enterprise E5, but no one has defined any policies for ATP safe attachments, ATP safe links or ATP advanced phishing yet.</span></span>|<span data-ttu-id="3e06f-p110">不。虽然可用的功能，必须为了 ATP 计算机学习模型，以定义至少一个 ATP 策略。用于模拟的 ATP 防钓鱼策略还必须满足。</span><span class="sxs-lookup"><span data-stu-id="3e06f-p110">No. Although the feature is available, at least one ATP policy must be defined in order for the ATP machine learning models to work. For impersonation an ATP anti-phishing policy must also be in place.</span></span>|
|<span data-ttu-id="3e06f-p111">李是 contoso 销售部的员工。李的组织仅财务人员应用于的位置中具有 ATP 防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="3e06f-p111">Lee is an employee in the sales department at Contoso. Lee's organization has an ATP anti-phishing policy in place that applies to finance employees only.</span></span>|<span data-ttu-id="3e06f-p112">不。在这种情况下，ATP 防钓鱼 （机模型和模拟保护） 将应用于 finance 员工，但其他员工，包括销售部门，不会。</span><span class="sxs-lookup"><span data-stu-id="3e06f-p112">No. In this case, ATP anti-phishing (machine models and impersonation protection) would apply to finance employees, but other employees, including the sales department, would not.</span></span>|
|<span data-ttu-id="3e06f-p113">昨天、 上 Jean 的组织的 Office 365 管理员设置适用于所有员工 ATP 防钓鱼策略。如今，前面 Jean 收到包含模拟策略所涉及的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="3e06f-p113">Yesterday, an Office 365 administrator at Jean's organization set up an ATP anti-phishing policy that applies to all employees. Earlier today, Jean received an email message that includes an impersonation covered by the policy.</span></span>|<span data-ttu-id="3e06f-p114">是的。本示例中，Jean 具有许可证的高级威胁保护，并已定义 ATP 防钓鱼策略，其中包括 Jean。通常大约需要 30 分钟的新策略跨数据中心; 才会生效由于一天过后在这种情况下，该策略应实际上所示。</span><span class="sxs-lookup"><span data-stu-id="3e06f-p114">Yes. In this example, Jean has a license for Advanced Threat Protection, and an ATP anti-phishing policy that includes Jean has been defined. It typically takes about 30 minutes for a new policy to take effect across datacenters; since a day has passed in this case, the policy should be in effect.</span></span>|
   
## <a name="related-topics"></a><span data-ttu-id="3e06f-155">相关主题</span><span class="sxs-lookup"><span data-stu-id="3e06f-155">Related topics</span></span>
<span data-ttu-id="3e06f-156"><a name="IsantiphishOn"> </a></span><span class="sxs-lookup"><span data-stu-id="3e06f-156"></span></span>

[<span data-ttu-id="3e06f-157">Office 365 高级威胁防护</span><span class="sxs-lookup"><span data-stu-id="3e06f-157">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
  
[<span data-ttu-id="3e06f-158">Office 365 中的防钓鱼保护</span><span class="sxs-lookup"><span data-stu-id="3e06f-158">Anti-phishing protection in Office 365</span></span>](anti-phishing-protection.md)
  
[<span data-ttu-id="3e06f-159">设置 Office 365 中的反钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="3e06f-159">Set up anti-phishing policies in Office 365</span></span>](set-up-anti-phishing-policies.md)
  
[<span data-ttu-id="3e06f-160">ATP Office 365 中的安全链接</span><span class="sxs-lookup"><span data-stu-id="3e06f-160">ATP safe links in Office 365</span></span>](atp-safe-links.md)
  
[<span data-ttu-id="3e06f-161">设置 Office 365 中的 ATP 安全链接策略</span><span class="sxs-lookup"><span data-stu-id="3e06f-161">Set up ATP safe links policies in Office 365</span></span>](set-up-atp-safe-links-policies.md)
  
[<span data-ttu-id="3e06f-162">Office 365 中的 ATP 安全附件</span><span class="sxs-lookup"><span data-stu-id="3e06f-162">ATP safe attachments in Office 365</span></span>](atp-safe-attachments.md)
  
[<span data-ttu-id="3e06f-163">设置 Office 365 中的 ATP 附件安全策略</span><span class="sxs-lookup"><span data-stu-id="3e06f-163">Set up ATP safe attachments policies in Office 365</span></span>](set-up-atp-safe-attachments-policies.md)
  
[<span data-ttu-id="3e06f-164">查看高级威胁保护报告</span><span class="sxs-lookup"><span data-stu-id="3e06f-164">View the reports for Advanced Threat Protection</span></span>](view-reports-for-atp.md)
  

