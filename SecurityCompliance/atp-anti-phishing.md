---
title: Office 365 中的 ATP 防钓鱼功能
ms.author: tracyp
author: MSFTTracyp
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 5076d0f6-7a59-4d6c-bd07-ba95033f0682
ms.collection:
- M365-security-compliance
description: ATP 反网络钓鱼是 Office 365 高级威胁防护的一部分。 ATP 反网络钓鱼对传入的邮件应用一组计算机学习模式以及模拟检测算法, 以提供对商品和 spear 网络钓鱼攻击的保护。 所有邮件都服从一组专门培训的计算机学习模式, 以检测网络钓鱼邮件, 以及一组用于防止各种用户和域模拟攻击的高级算法。
ms.openlocfilehash: 0c17273d935dbdaec6d78a62a4edfa015b6b8efa
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2019
ms.locfileid: "34155544"
---
# <a name="atp-anti-phishing-capabilities-in-office-365"></a>Office 365 中的 ATP 防钓鱼功能

ATP 反网络钓鱼是[Office 365 高级威胁防护](office-365-atp.md)的一部分。 ATP 反网络钓鱼对传入的邮件应用一组计算机学习模式以及模拟检测算法, 以提供对商品和 spear 网络钓鱼攻击的保护。 所有邮件都服从一组专门培训的计算机学习模式, 以检测网络钓鱼邮件, 以及一组用于防止各种用户和域模拟攻击的高级算法。 ATP 反网络钓鱼根据 Office 365 全局或安全管理员设置的策略来保护您的组织。
  
若要了解详细信息, 请参阅[在 Office 365 中设置反网络钓鱼策略](set-up-anti-phishing-policies.md)。
  
> [!NOTE]
> ATP 反网络钓鱼仅适用于订阅中包含的高级威胁防护, 如[microsoft 365 企业版](https://www.microsoft.com/microsoft-365/enterprise/home)、 [Microsoft 365 商业](https://www.microsoft.com/microsoft-365/business)版、Office 365 企业版 E5、Office 365 教育版 A5 等。如果您的组织有一个不包含 Office 365 ATP 的 Office 365 订阅, 则可能会将 ATP 作为加载项进行购买。 有关详细信息, 请参阅[office 365 高级威胁防护计划和定价](https://products.office.com/exchange/advance-threat-protection)和[Office 365 高级威胁防护服务说明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)。

## <a name="how-atp-anti-phishing-works"></a>ATP 反网络钓鱼的工作原理

ATP 反网络钓鱼检查传入邮件, 以了解邮件可能是网络钓鱼的指示器。 只要 ATP 策略涵盖用户 (安全的附件、安全链接或反钓鱼), 传入的邮件将由多个机器学习模型进行评估, 以确定该策略是否适用于该邮件, 以及适当的操作是根据配置的策略执行。
  
ATP 反网络钓鱼允许 Office 365 全局管理员或安全管理员定义策略, 以抵御包含用户或域模拟的网络钓鱼攻击。 (或两者)。 Office 365 全局管理员或安全管理员在策略中定义应使用用户或域的固定列表或使用邮箱智能来保护用户和域的模拟攻击。 邮箱智能是对用户的电子邮件习惯和个人联系人的高级了解。 ATP 学习了每个用户如何与组织内部和外部的其他用户通信, 并建立这些关系的地图。 此地图允许 ATP 了解有关如何确保将正确的邮件标识为模拟的更多详细信息。
  
ATP 反网络钓鱼策略可应用于组织中的一组特定用户或组, 或者应用于整个域或所有自定义域。 若要了解详细信息, 请参阅[在 Office 365 中设置反网络钓鱼策略](set-up-anti-phishing-policies.md)。
  
## <a name="how-to-get-atp-anti-phishing"></a>如何获取 ATP 反网络钓鱼

ATP 反网络钓鱼功能是[高级威胁防护](office-365-atp.md)的一部分;但是, 当定义了反网络钓鱼策略时, 将应用 ATP 反钓鱼保护。 (一个示例是基于模拟的策略。)请参阅[在 Office 365 中设置反网络钓鱼策略](set-up-anti-phishing-policies.md)。
  
## <a name="how-to-know-if-atp-anti-phishing-is-in-place"></a>如何了解 ATP 反网络钓鱼是否已就绪

必须定义 ATP 反网络钓鱼策略, 才能使保护生效。 先检查此项以验证是否已实施保护。

此外, 报告可用于显示服务在您的组织中的工作方式。 若要了解详细信息, 请参阅[查看 Office 365 高级威胁防护的报告](view-reports-for-atp.md)。

对于特定用户的 ATP 反钓鱼计算机学习模型处于活动状态, 该用户必须是定义的[ATP 安全附件](atp-safe-attachments.md)、 [atp 安全链接](atp-safe-links.md)或 atp 反网络钓鱼策略的一部分。 

下表介绍了几个示例方案。 在上述每个示例中, 组织都使用 Office 365 企业版 E5, 其中包括高级威胁防护。
  
|**示例方案**|**在这种情况下, ATP 反网络钓鱼是否适用？**|
|:-----|:-----|
|Pat 的组织拥有 Office 365 企业版 E5, 但没有人为 ATP 安全附件、ATP 安全链接或 ATP 高级网络钓鱼定义任何策略。|否。 虽然该功能可用, 但必须至少定义一个 ATP 策略, 才能使 ATP 机器学习模型能够正常工作。 对于模拟, ATP 反网络钓鱼策略也必须已准备就绪。|
|先生为在 Contoso 的销售部门的员工。 先生/她的组织已实施了仅适用于财务员工的 ATP 反网络钓鱼策略。|否。 在这种情况下, ATP 反网络钓鱼 (计算机模型和模拟保护) 将应用于财务员工, 但其他员工 (包括销售部门) 将不会。|
|昨天, Jean 的组织中的 Office 365 管理员设置适用于所有员工的 ATP 反网络钓鱼策略。 在今天的早期, Jean 收到一封包含策略所涵盖的模拟的电子邮件。|是。 在此示例中, Jean 具有高级威胁防护的许可证, 并且已定义包括 Jean 的 ATP 反网络钓鱼策略。 新策略通常需要30分钟的时间才能在数据中心内生效;由于在这种情况下已过一天, 因此该策略应有效。|

## <a name="related-topics"></a>相关主题

[Office 365 高级威胁防护](office-365-atp.md)
  
[Office 365 中的防钓鱼保护](anti-phishing-protection.md)
  
[在 Office 365 中设置反网络钓鱼策略](set-up-anti-phishing-policies.md)
  
[Office 365 中的 ATP 安全链接](atp-safe-links.md)
  
[在 Office 365 中设置 ATP 安全链接策略](set-up-atp-safe-links-policies.md)
  
[Office 365 中的 ATP 安全附件](atp-safe-attachments.md)
  
[在 Office 365 中设置 ATP 安全附件策略](set-up-atp-safe-attachments-policies.md)
  
[查看高级威胁防护报告](view-reports-for-atp.md)
