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
# <a name="atp-anti-phishing-capabilities-in-office-365"></a>Office 365 中的 ATP 防钓鱼功能

ATP 防钓鱼作为[Office 365 高级威胁保护](https://technet.microsoft.com/en-us/library/exchange-online-advanced-threat-protection-service-description.aspx)的一部分提供。ATP 防钓鱼适用于以提供的商品和矛网络钓鱼攻击保护的传入消息的计算机学习模型以及模拟检测算法的集合。所有的消息将受到一组广泛的培训来检测网络钓鱼邮件，以及用于防范各种用户和域模拟攻击的高级算法的一组计算机学习模型。ATP 防钓鱼保护您的组织根据要策略的设置您的 Office 365 全局或安全管理员。
  
若要了解详细信息，请参阅[设置 Office 365 中的反钓鱼策略](set-up-anti-phishing-policies.md)。
  
> [!NOTE]
> ATP 防钓鱼才高级威胁防护，提供与 Office 365 企业 E5 中可用。如果您的组织使用的另一个 Office 365 企业版订阅，高级威胁保护可以作为加载项进行购买。(作为全局管理员在 Office 365 管理中心中，选择**帐单** \> **添加订阅**。)有关规划选项的详细信息，请参阅[比较 Office 365 的业务计划](https://go.microsoft.com/fwlink/?linkid=844053)。 
    
## <a name="how-atp-anti-phishing-works"></a>ATP 防钓鱼的工作原理
<a name="Howantiphishworks"> </a>

ATP 防钓鱼检查邮件可能网络钓鱼的指标的传入消息。只要用户涵盖 ATP 策略 （安全附件、 安全链接或防钓鱼） 将传入邮件计算由多个计算机学习分析邮件以确定是否将策略应用于邮件以及相应的操作的模型执行，基于已配置的策略。
  
ATP 防钓鱼允许 Office 365 全局管理员或安全管理员定义提供针对包含模拟的用户或域的网络钓鱼攻击保护的策略。（或两者）。Office 365 全局管理员或安全管理员定义的用户和域应防止使用模拟攻击在策略中的用户或域或通过使用邮箱智能固定的列表。邮箱智能是高级的了解用户的电子邮件习惯和个人联系人。ATP 学习如何每个用户与组织内部和外部的其他用户进行通信，并建立这些关系的映射。此映射允许 ATP 了解有关如何确保正确的邮件被标识为模拟的详细信息。
  
ATP 防钓鱼策略可应用到一组特定的联系人或在组织中的组或整个域或所有自定义域。若要了解详细信息，请参阅[设置 Office 365 中的反钓鱼策略](set-up-anti-phishing-policies.md)。
  
## <a name="how-to-get-atp-anti-phishing"></a>如何获取 ATP 防钓鱼
<a name="Howtogetantiphish"> </a>

ATP 防钓鱼是高级威胁保护，它包含 Office 365 企业 E5 的一部分。也可以作为 Office 365 企业版 E1 或 Office 365 企业版 E3 购买高级的威胁保护。有关规划选项的详细信息，请参阅[比较 Office 365 的业务计划](https://go.microsoft.com/fwlink/?linkid=844053)。
  
ATP 防钓鱼适用时防钓鱼策略，如基于模拟的策略设置。（请参阅[Set up Office 365 中的反钓鱼策略](set-up-anti-phishing-policies.md)）。
  
## <a name="how-to-know-if-atp-anti-phishing-is-in-place"></a>如何知道 ATP 防钓鱼是否就地
<a name="IsantiphishOn"> </a>

为了保护处于活动状态，必须定义 ATP 防钓鱼策略。对于 ATP 防钓鱼机器学习模型是活动的用户，该用户必须是安全的定义的附件、 安全链接或防钓鱼策略的一部分。下表介绍了几个示例方案。在每个示例中，组织在使用 Office 365 企业 E5，其中包括高级威胁保护。
  
|**示例应用场景**|**ATP 防钓鱼不适用于这种情况下？**|
|:-----|:-----|
|Pat 组织具有 Office 365 企业 E5，但没有人已定义的 ATP 安全附件，ATP 安全链接或 ATP 尚未高级网络钓鱼的任何策略。|不。虽然可用的功能，必须为了 ATP 计算机学习模型，以定义至少一个 ATP 策略。用于模拟的 ATP 防钓鱼策略还必须满足。|
|李是 contoso 销售部的员工。李的组织仅财务人员应用于的位置中具有 ATP 防钓鱼策略。|不。在这种情况下，ATP 防钓鱼 （机模型和模拟保护） 将应用于 finance 员工，但其他员工，包括销售部门，不会。|
|昨天、 上 Jean 的组织的 Office 365 管理员设置适用于所有员工 ATP 防钓鱼策略。如今，前面 Jean 收到包含模拟策略所涉及的电子邮件。|是的。本示例中，Jean 具有许可证的高级威胁保护，并已定义 ATP 防钓鱼策略，其中包括 Jean。通常大约需要 30 分钟的新策略跨数据中心; 才会生效由于一天过后在这种情况下，该策略应实际上所示。|
   
## <a name="related-topics"></a>相关主题
<a name="IsantiphishOn"> </a>

[Office 365 高级威胁防护](office-365-atp.md)
  
[Office 365 中的防钓鱼保护](anti-phishing-protection.md)
  
[设置 Office 365 中的反钓鱼策略](set-up-anti-phishing-policies.md)
  
[ATP Office 365 中的安全链接](atp-safe-links.md)
  
[设置 Office 365 中的 ATP 安全链接策略](set-up-atp-safe-links-policies.md)
  
[Office 365 中的 ATP 安全附件](atp-safe-attachments.md)
  
[设置 Office 365 中的 ATP 附件安全策略](set-up-atp-safe-attachments-policies.md)
  
[查看高级威胁保护报告](view-reports-for-atp.md)
  

