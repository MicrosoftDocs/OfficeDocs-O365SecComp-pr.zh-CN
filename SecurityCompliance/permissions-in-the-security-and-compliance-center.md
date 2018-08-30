---
title: Office 365 安全性权限&amp;合规性中心
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: overview
f1_keywords:
- ms.o365.cc.AdminRoleGroups
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: d10608af-7934-490a-818e-e68f17d0e9c1
description: Office 365 安全性&amp;合规性中心，可以向执行合规性任务，如设备管理、 数据丢失防护、 电子数据展示、 保留、 等的人员授予权限。这些人员可以执行只能您明确向其授予权限的任务。若要访问安全性&amp;合规性中心，用户需要为 Office 365 全局管理员或成员的一个或多个安全&amp;合规性中心角色组。
ms.openlocfilehash: e393bad7c3a57b0734835e56fcd781cc31327c18
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "23013426"
---
# <a name="permissions-in-the-office-365-security-amp-compliance-center"></a>Office 365 安全性权限&amp;合规性中心

Office 365 安全性&amp;合规性中心，可以向执行合规性任务，如设备管理、 数据丢失防护、 电子数据展示、 保留、 等的人员授予权限。这些人员可以执行只能您明确向其授予权限的任务。若要访问安全性&amp;合规性中心，用户需要为 Office 365 全局管理员或成员的一个或多个安全&amp;合规性中心角色组。
  
安全中的权限&amp;合规性中心基于角色基于访问控制 (RBAC) 权限模型。这是相同的权限模型由 Exchange，因此如果您熟悉 Exchange，授予安全中的权限&amp;合规性中心将会非常相似。非常重要但请记住，该 Exchange 角色组和安全&amp;合规性中心角色组成员身份或权限不共享。时都安装了组织管理角色组，它们不相同。具有不同他们授予的权限，权限和角色组的成员。没有安全列表&amp;下的合规性中心角色组。
  
![Office 365 安全权限页面&amp;合规性中心](media/992c20ca-e82e-497c-9c8d-6fab212deb80.png)
  
## <a name="relationship-of-members-roles-and-role-groups"></a>成员、角色和角色组之间的关系

**角色**可授予执行一组任务的权限；例如，事例管理角色可以让人员处理电子数据展示事例。 
  
**角色组**是一套角色，以便其他人执行其作业跨安全&amp;合规性中心;例如，合规性管理员角色组包括角色案例管理、 内容搜索和组织配置 （以及其他人） 因为合规性管理的某人，将需要这些任务完成其作业的权限。 
  
安全&amp;合规性中心包含的最常见任务和您需要分配到的人员的功能的默认角色组。建议您只需将各个用户作为**成员**添加到默认角色组。 
  
![显示角色组与角色和成员之间关系的图表](media/2a16d200-968c-4755-98ec-f1862d58cb8b.png)
  
您可以编辑或删除现有角色组，但我们不建议这样做。而不是编辑默认角色组，您可以将其复制、 修改它，然后将其保存具有不同名称。
  
## <a name="permissions-needed-to-use-features-in-the-security-amp-compliance-center"></a>使用中的安全功能所需的权限&amp;合规性中心

下表列出了安全中可用的默认角色组&amp;合规性中心。若要执行合规性任务的用户授予权限，请将其添加到适当的安全性&amp;合规性中心角色组。
  
管理安全中的权限&amp;合规性中心只让用户访问的安全中可用的合规性功能&amp;合规性中心本身。如果您想要授予权限到不安全中其他合规性功能&amp;合规性中心，如 Exchange 传输规则，您需要使用 Exchange 管理中心。
  
若要查看如何授予访问权限的安全&amp;合规性中心，签出[授予用户对 Office 365 合规性管理中心的访问权限](grant-access-to-the-security-and-compliance-center.md)。
  
|**角色组**|**说明**|
|:-----|:-----|
|**合规性管理员**<sup>1</sup> <br/> |成员可以管理设备管理、 数据丢失防护、 报表和保留的设置。  <br/> |
|**电子数据展示管理员** <br/> | 成员可以执行搜索并将邮箱、SharePoint Online 网站和 OneDrive for Business 位置置于保留状态。成员还可以创建和管理电子数据展示事例、添加和删除成员至事例，并创建和编辑与事例关联的内容搜索。<br/>  电子数据展示管理员是电子数据展示管理员角色组的成员，该成员已分配有其他权限。电子数据展示管理员可以：<br/>  查看组织中的所有电子数据展示事例。  <br/>  将自己添加为任何电子数据展示事例的成员后管理这些事例。  <br/>  访问 Office 365 高级电子数据展示。这是因为电子数据展示管理员将自动添加为高级电子数据展示中的管理员。请注意，您必须是电子数据展示管理员安全中&amp;合规性中心以访问高级电子数据展示。有关进行电子数据展示管理员的用户的详细信息，请参阅[Office 365 安全性的电子数据展示事例&amp;合规性中心](https://go.microsoft.com/fwlink/p/?LinkId=780738)。<br/> 如果您希望为用户提供高级电子数据展示中的管理权限，但不希望让其电子数据展示管理员安全中&amp;合规性中心，您可以将其添加到电子数据展示管理员角色组，然后将其添加为中的管理员高级电子数据展示。有关说明，请参阅[用户和 Office 365 高级电子数据展示中的情况下的设置](https://go.microsoft.com/fwlink/p/?LinkId=780696)。           |
|**组织管理**<sup>1</sup> <br/> |成员可以控制用于访问安全中的功能的权限&amp;合规性中心以及管理的设备管理、 数据丢失防护、 报表和保留设置。  <br/> 请注意，在不是全局管理员才能通过 MDM 管理 Office 365 的设备列表，请参阅的用户的顺序和这些设备上执行操作，如为 Office 365 从 MDM retiring 设备，用户必须是 Exchange 管理员。  <br/> Office 365 全局管理员将自动添加为此角色组的成员。           |
|**记录管理** <br/> |成员可以管理和释放记录内容。  <br/> |
|**Reviewer** <br/> |成员只能在安全的电子数据展示案例页上查看的情况下列表&amp;合规性中心。他们无法创建、 打开或管理电子数据展示事例。此角色组的主要用途是允许成员添加到视图和访问 case 高级电子数据展示中的数据。  <br/> 此角色组中与电子数据展示相关的权限最具限制性。  <br/> |
|**Security Administrator** <br/> |此角色组中的成员资格是同步服务和集中管理。此角色组不通过管理员门户易于管理。跨服务管理员，以及外部合作伙伴组和 Microsoft 支持，可能包括此角色组的成员。默认情况下，此组可能不被分配任何角色。但是，它将 Security Administrators 角色组的成员，并将继承该角色组的功能。  <br/> 所有安全读者角色，以及大量的相同服务的其他管理权限的只读权限： Azure 信息保护、 标识防护中心、 特权身份管理和监视 Office 365 服务运行状况和 Office 365 安全性&amp;合规性中心。  <br/> |
|**安全读者** <br/> |成员具有只读访问权限的标识防护中心、 特权标识管理、 监控 Office 365 服务运行状况和 Office 365 安全性的安全功能的数量&amp;合规性中心。  <br/> 此角色组中的成员资格是同步服务和集中管理。此角色组不通过管理员门户易于管理。跨服务管理员，以及外部合作伙伴组和 Microsoft 支持，可能包括此角色组的成员。默认情况下，此组可能不被分配任何角色。但是，它将安全读者角色组的成员，并将继承该角色组的功能。  <br/> |
|**服务保证用户** <br/> |成员可以访问 Office 365 安全性服务保证部分&amp;合规性中心。服务保证提供报告和描述 Microsoft 的安全做法客户数据存储在 Office 365 中的文档。它还提供有关 Office 365 的独立的第三方审核报告。有关详细信息，请参阅[服务 Office 365 安全性保证&amp;合规性中心](http://go.microsoft.com/fwlink/p/?LinkID=717765)。<br/> |
|**监督审阅** <br/> |成员可以创建和管理其定义的策略 communications 受到查看组织中。有关详细信息，请参阅[Configure 监督查看为您的组织的策略](configure-supervision-policies.md)。<br/> |
   
> [!NOTE]
> <sup>1</sup>该角色组不成员分配 Office 365 审核日志中搜索或使用可能包括 Exchange 数据，如 DLP 或 ATP 报告任何报告所需的权限。若要搜索的审核日志或查看所有报告，用户必须为其分配 Exchange Online 中的权限。这是因为基础 cmdlet 用于搜索的审核日志是 Exchange Online cmdlet。Office 365 全局管理员可以搜索审核日志和查看所有报告，因为它们会自动添加为 Organization Management 角色组的成员在 Exchange Online。有关详细信息，请参阅[Office 365 安全性搜索审核日志&amp;合规性中心](https://go.microsoft.com/fwlink/p/?LinkID=708432)。 
  

