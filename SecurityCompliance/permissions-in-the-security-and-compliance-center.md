---
title: Permissions in the Office 365 Security &amp; Compliance Center
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.AdminRoleGroups
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
description: 通过 Office 365 安全&amp;合规中心, 您可以向执行合规性任务 (如设备管理、数据丢失防护、电子数据展示、保留等) 的人员授予权限。 这些人员只能执行你明确授予其访问权限的任务。 若要访问安全&amp;合规性中心, 用户必须是 Office 365 全局管理员或一个或多个安全&amp;合规中心角色组的成员。
ms.openlocfilehash: eba77fd6edcf41bac5eeebae3637707c2c5a7246
ms.sourcegitcommit: 799a958fcac643f62dfac6fa04020f2f4758635c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/29/2019
ms.locfileid: "30997078"
---
# <a name="permissions-in-the-office-365-security-amp-compliance-center"></a>Permissions in the Office 365 Security &amp; Compliance Center

通过 Office 365 安全&amp;合规中心, 您可以向执行合规性任务 (如设备管理、数据丢失防护、电子数据展示、保留等) 的人员授予权限。 这些人员只能执行你明确授予其访问权限的任务。 若要访问安全&amp;合规性中心, 用户必须是 Office 365 全局管理员或一个或多个安全&amp;合规中心角色组的成员。
  
安全&amp;合规性中心中的权限基于基于角色的访问控制 (RBAC) 权限模型。 这与 exchange 使用相同的权限模型, 因此, 如果您熟悉 exchange, 则在安全&amp;合规中心中授予权限将非常相似。 但请务必记住, Exchange 角色组和安全&amp;合规中心角色组不会共享成员资格或权限。 尽管二者都有一个组织管理角色组，但这两个角色组并不相同。 角色组授予的权限以及角色组的成员都有区别。 下面是安全&amp;合规中心角色组的列表。
  
![Office 365 安全&amp;合规中心中的 "权限" 页](media/992c20ca-e82e-497c-9c8d-6fab212deb80.png)
  
## <a name="relationship-of-members-roles-and-role-groups"></a>成员、角色和角色组之间的关系

**角色**可授予执行一组任务的权限；例如，事例管理角色可以让人员处理电子数据展示事例。 
  
**角色组**是允许用户在安全&amp;合规中心内执行其工作的一组角色;例如, 合规性管理员角色组包括用于案例管理、内容搜索和组织配置的角色 (另外还有其他), 因为符合管理员要求的人需要这些任务的权限才能完成其工作。 
  
安全&amp;合规性中心包含用于将用户分配到的最常见任务和功能的默认角色组。 我们建议您只是将单个用户添加为默认角色组的**成员**。 
  
![显示角色组与角色和成员之间关系的图表](media/2a16d200-968c-4755-98ec-f1862d58cb8b.png)
  
您可以编辑或删除现有的角色组, 但我们不建议这样做。 您可以复制和修改默认角色组，然后使用不同的名称进行保存，而不是对其进行编辑。
  
## <a name="permissions-needed-to-use-features-in-the-security-amp-compliance-center"></a>在安全&amp;合规中心中使用功能所需的权限

下表列出了安全&amp;合规性中心中提供的默认角色组。 若要向用户授予执行合规性任务的权限, 请将其添加到相应&amp;的安全合规中心角色组。
  
管理安全&amp;合规性中心中的权限仅使用户能够访问安全&amp;合规性中心本身提供的合规性功能。 如果要向不在安全&amp;合规中心中的其他合规性功能 (如 Exchange 邮件流规则 (也称为传输规则) 授予权限, 则需要使用 exchange 管理中心。
  
若要了解如何授予对安全&amp;合规中心的访问权限, 请参阅[授予用户对 Office 365 合规性管理中心的访问权限](grant-access-to-the-security-and-compliance-center.md)。
  
|**角色组**|**说明**|
|:-----|:-----|
|**合规性管理员**<sup>1</sup> <br/> |成员可以管理设备管理、数据丢失防护、报告和保留的设置。  <br/> |
|**合规性数据管理员** <br/> |成员可以管理设备管理、数据保护、数据丢失防护、报告和保留的设置。  <br/> |
|**电子数据展示管理员** <br/> | 成员可以执行搜索并将邮箱、SharePoint Online 网站和 OneDrive for Business 位置置于保留状态。 成员还可以创建和管理电子数据展示事例, 在案例中添加和删除成员, 创建和编辑与事例关联的内容搜索, 以及 Office 365 高级电子数据展示中的访问大小写数据。 <br/><br/>电子数据展示管理员是电子数据展示管理员角色组的成员，该成员已分配有其他权限。 除了电子数据展示管理器可以执行的任务外, 电子数据展示管理员还可以执行以下操作:  <br/><br/>  •查看组织中的所有电子数据展示案例。  <br/>  •在将自己添加为事例的成员之后管理任何电子数据展示事例。  <br/><br/>电子数据展示管理器和电子数据展示管理员的主要区别在于, 电子数据展示 Admininstrator 可以访问安全&amp;合规性中心中 "**电子数据展示事例**" 页面上列出的所有事例。 电子数据展示管理器只能访问他们创建的案例或其成员的情况。  有关使用户成为电子数据展示管理员的详细信息, 请参阅[在 Office 365 安全&amp;合规中心中分配电子数据展示权限](assign-ediscovery-permissions.md)。 <br/> |
|**邮件流管理员** <br/> |成员可以监视和查看 Security & 合规性中心中的邮件流见解和报告。 全局管理员可以向此组添加普通用户, 但是, 如果该用户不是 exchange 管理员组的成员, 则该用户将无法访问 exchange 管理员相关的任务。  <br/> |
|**组织管理**<sup>1</sup> <br/> |成员可以控制对安全&amp;合规性中心中的功能的访问权限, 还可以管理设备管理、数据丢失防护、报告和保留的设置。  <br/> 请注意, 若要使非全局管理员的用户能够查看由 mdm for office 365 管理的设备的列表, 并对这些设备执行操作 (例如, 从 MDM for office 365 中注销设备), 则该用户必须是 Exchange 管理员。  <br/> Office 365 全局管理员将自动添加为此角色组的成员。           |
|**记录管理** <br/> |成员可以管理和处置记录内容。  <br/> |
|**Reviewer** <br/> |成员只能查看安全&amp;合规性中心中 "电子数据展示事例" 页上的案例列表。 他们无法创建、打开或管理电子数据展示事例。 此角色组的主要用途是允许成员在高级电子数据展示中查看和访问事例数据。  <br/> 此角色组中与电子数据展示相关的权限最具限制性。  <br/> |
|**Security Administrator** <br/> |此角色组的成员可能包括跨服务管理员以及外部合作伙伴组和 Microsoft 支持。 默认情况下, 可能不会向该组分配任何角色。 但是, 它将是 Azure Active Directory 中的安全管理员角色的成员, 并将继承该角色的功能。 若要集中管理权限, 请在 azure active directory 管理中心中对此角色进行更改-有关详细信息, 请参阅[azure active directory 中的管理员角色权限](https://docs.microsoft.com/en-us/azure/active-directory/users-groups-roles/directory-assign-admin-roles)。 如果在 security & 合规中心中编辑此角色组, 则这些更改仅适用于 security & 合规中心, 而不是其他任何服务, 而在 Azure Active Directory 管理中心中所做的更改会影响所有服务。<br/> 安全读者角色的所有只读权限, 以及对相同服务的许多其他管理权限: Azure 信息保护、标识保护中心、特权身份管理、监视 Office 365 服务运行状况和 Office 365 安全&amp;合规中心。  <br/> |
|**Security 运算符** <br/> |成员可以管理安全警报, 还可以查看安全功能的报告和设置。 <br/> |
|**安全读者** <br/> |成员具有对身份保护中心的许多安全功能的只读访问权限、特权身份管理、监视 Office 365 服务运行状况和 Office 365 安全性&amp;合规性中心。  <br/> 此角色组中的成员身份将跨服务同步并集中管理。 此角色组的成员可能包括跨服务管理员以及外部合作伙伴组和 Microsoft 支持。 默认情况下, 可能不会向该组分配任何角色。 但是, 它将是 Azure Active Directory 中的安全读取器角色的成员, 并将继承该角色的功能。 若要集中管理权限, 请在 azure active directory 管理中心中对此角色进行更改-有关详细信息, 请参阅[azure active directory 中的管理员角色权限](https://docs.microsoft.com/en-us/azure/active-directory/users-groups-roles/directory-assign-admin-roles)。 如果在 security & 合规中心中编辑此角色组, 则这些更改仅适用于 security & 合规中心, 而不是其他任何服务, 而在 Azure Active Directory 管理中心中所做的更改会影响所有服务。<br/> |
|**服务保证用户** <br/> |成员可以访问 Office 365 安全&amp;合规中心中的服务保证部分。 服务保证提供了报告和文档, 这些报告和文档描述了 Microsoft 在 Office 365 中存储的客户数据的安全实践。 此外, 它还提供了有关 Office 365 的独立第三方审核报告。 有关详细信息, 请参阅[Office 365 安全&amp;合规中心中的服务保证](http://go.microsoft.com/fwlink/p/?LinkID=717765)。  <br/> |
|**监管审核** <br/> |成员可以创建和管理用于定义哪类通讯在组织中易受到审查的策略。 有关详细信息, 请参阅为[您的组织配置监管审核策略](configure-supervision-policies.md)。  <br/> |
   
> [!NOTE]
> <sup>1</sup>此角色组不会向成员分配搜索 Office 365 审核日志所需的权限, 也不能使用可能包含 Exchange 数据的任何报告 (如 DLP 或 ATP 报告)。 若要搜索审核日志或查看所有报告, 必须在 Exchange Online 中向用户分配权限。 这是因为用于搜索审核日志的基础 cmdlet 是 Exchange Online cmdlet。 Office 365 全局管理员可以搜索审核日志并查看所有报告, 因为它们会自动添加为 Exchange Online 中的 "组织管理" 角色组的成员。 有关详细信息, 请参阅[在 Office 365 安全&amp;合规中心中搜索审核日志](https://go.microsoft.com/fwlink/p/?LinkID=708432)。 
  
## <a name="mapping-of-role-groups-to-assigned-roles"></a>角色组到已分配角色的映射

默认情况下, 角色组具有分配给它们的一组角色。 此表显示分配给每个角色组的角色。

|**角色组**|**分配的角色**|
|:-----|:-----|
|**合规性管理员** <br/> |仅查看保留管理 <br/>管理通知 <br/>仅查看管理通知 <br/>仅查看设备管理 <br/>组织配置 <br/>DLP 合规性管理 <br/>仅查看 IB 合规性管理 <br/>处置管理 <br/>仅查看 DLP 合规性管理 <br/>RecordManagement <br/>IB 合规性管理 <br/>仅查看审核日志 <br/>合规性管理员 <br/>设备管理 <br/>合规性搜索 <br/>案例管理 <br/>保留管理 <br/>仅查看记录管理 <br/>仅查看收件人 <br/>同时 <br/> |
|**合规性数据管理员** <br/> |仅查看保留管理 <br/>管理通知 <br/>敏感度标签管理员 <br/>仅查看管理通知 <br/>仅查看设备管理 <br/>组织配置 <br/>DLP 合规性管理 <br/>仅查看 IB 合规性管理 <br/>处置管理 <br/>仅查看 DLP 合规性管理 <br/>RecordManagement <br/>IB 合规性管理 <br/>仅查看审核日志 <br/>合规性管理员 <br/>设备管理 <br/>合规性搜索 <br/>保留管理 <br/>仅查看记录管理 <br/>仅查看收件人<br/> |
|**电子数据展示管理员** <br/> |导出 <br/>RMS 解密 <br/>Custodian <br/>通 <br/>审阅 <br/>预览 <br/>合规性搜索 <br/>案例管理 <br/>同时 <br/> |
|**邮件流管理员** <br/> |仅查看收件人 <br/>  |
|**组织管理** <br/> |仅查看保留管理 <br/>管理通知 <br/>角色管理 <br/>敏感度标签管理员 <br/>仅查看管理通知 <br/>仅查看设备管理 <br/>组织配置 <br/>DLP 合规性管理 <br/>仅查看 IB 合规性管理 <br/>处置管理 <br/>仅查看 DLP 合规性管理 <br/>RecordManagement <br/>审核日志 <br/>IB 合规性管理 <br/>安全读者 <br/>Security Administrator <br/>服务保证视图 <br/>搜索和清除 <br/>仅查看审核日志 <br/>合规性管理员 <br/>设备管理 <br/>合规性搜索 <br/>案例管理 <br/>保留管理 <br/>仅查看记录管理 <br/>仅查看收件人 <br/>同时 <br/> |
|**记录管理** <br/> |RecordManagement <br/>审核日志 <br/>保留管理 <br/> |
|**Reviewer** <br/> |审阅 <br/> |
|**Security Administrator** <br/> |管理通知 <br/>敏感度标签管理员 <br/>仅查看管理通知 <br/>仅查看设备管理 <br/>DLP 合规性管理 <br/>仅查看 IB 合规性管理 <br/>仅查看 DLP 合规性管理 <br/>审核日志 <br/>IB 合规性管理 <br/>Security Administrator <br/>仅查看审核日志 <br/>设备管理 <br/> |
|**Security 运算符** <br/> |管理通知 <br/>仅查看管理通知 <br/>仅查看设备管理 <br/>仅查看 IB 合规性管理 <br/>仅查看 DLP 合规性管理 <br/>安全读者 <br/>仅查看审核日志 <br/>合规性搜索 <br/> |
|**安全读者** <br/> |仅查看管理通知 <br/>仅查看设备管理 <br/>仅查看 IB 合规性管理 <br/>仅查看 DLP 合规性管理 <br/>安全读者 <br/> |
|**服务保证用户** <br/> |服务保证视图 <br/> |
|**监管审核** <br/> |监管审核管理员 <br/> |
