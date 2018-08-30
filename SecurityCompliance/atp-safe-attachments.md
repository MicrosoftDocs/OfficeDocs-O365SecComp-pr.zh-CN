---
title: Office 365 ATP 安全附件
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 08/03/2018
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MET150
- MOE150
ms.assetid: 6e13311e-92ae-495e-a619-56d770199170
description: 安全附件功能提供电子邮件附件的时间的单击的验证。使用安全附件组织防止恶意文件人员发送或接收电子邮件中。
ms.openlocfilehash: 0a28923bff8aa2cd987159edd3cad77ed42f80f4
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525403"
---
# <a name="office-365-atp-safe-attachments"></a>Office 365 ATP 安全附件

ATP （以及[ATP 安全链接](atp-safe-links.md)） 的安全附件是[Office 365 高级威胁保护](office-365-atp.md)(ATP) 的一部分。ATP 安全附件功能将查看是否恶意，电子邮件附件，然后执行操作以保护您的组织。ATP 安全附件功能保护您的组织根据您的 Office 365 全局或安全管理员设置的[ATP 安全附件策略](set-up-atp-safe-attachments-policies.md)。 
  
后期年 3 月 2018年中和下一步的几个星期开始，ATP 保护进行了扩展到文件中 SharePoint Online、 OneDrive for Business 和 Microsoft 团队。若要了解详细信息，请参阅[Office 365 高级威胁 Protection for SharePoint、 OneDrive 和 Microsoft 团队](atp-for-spo-odb-and-teams.md)。
       
## <a name="how-it-works"></a>如何工作

ATP 安全附件功能检查您的组织中的人员的电子邮件附件。时 ATP 安全附件策略已就绪某人覆盖策略在 Office 365 中查看其电子邮件，则检查其电子邮件附件，并采取相应的操作，基于您 ATP 安全附件策略。根据您的策略定义的方式，人员可以继续工作，而不会知道他们发送恶意文件。
  
下面是在工作场所 ATP 安全附件的两个示例。
  
- **示例 1： 通过电子邮件附件**假设李接收包含附件的电子邮件。不明显到李是否附件安全或实际上包含恶意软件旨在窃取李的用户凭据。李的组织中的安全管理员定义的 ATP 安全附件策略几天前。使用 ATP 安全附件功能，电子邮件附件是打开和李获得它之前测试虚拟环境中。如果附件确定恶意，将自动删除。如果附件是安全的它将打开预期李单击它时。 
    
- **示例 2: SharePoint Online 中的文件**假设 Jean 收到的文件上载到 SharePoint Online 中的库。Jean 与工作组、 的其余部分不知道该文件实际恶意共享文件的链接。幸运的是， [SharePoint、 OneDrive 和 Microsoft 团队 ATP](atp-for-spo-odb-and-teams.md)检测到恶意文件，并阻止。更高版本，几天 Chris 转打开文档。尽管 Chris 可以看到该文件存在，Chris 无法打开或其，它可防止恶意文件 Chris 的计算机和其他人共享。 
    
ATP 安全附件策略可以应用到特定的某个人或组织中的组或整个域。若要了解详细信息，请参阅**[设置 Office 365 中的 ATP 安全附件策略](set-up-atp-safe-attachments-policies.md)**。 
  
## <a name="how-to-get-atp-safe-attachments"></a>如何获取 ATP 安全附件

ATP 安全附件功能是高级威胁保护，它包含 Office 365 企业 E5 的一部分。如果您的组织使用的另一个 Office 365 企业版订阅，高级威胁保护可以作为加载项进行购买。(作为全局管理员，在 Office 365 管理中心中，选择**帐单** \> **添加订阅**。)有关详细信息，请参阅[Office 365 平台服务说明： Office 365 安全性&amp;合规性中心](https://technet.microsoft.com/en-us/library/dn933793.aspx)和[购买或编辑企业的 Office 365 的加载项](https://support.office.com/article/4e7b57d6-b93b-457d-aecd-0ea58bff07a6)。
  
ATP 安全附件功能时适用：
  
- ATP 安全附件策略设置。（请参阅[Set up Office 365 中的 ATP 安全附件策略](set-up-atp-safe-attachments-policies.md)）。
    
- 用户已登录到 Office 365 使用其工作或学校帐户。（请参阅[登录到 Office 或 Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426)）。
    
## <a name="how-to-know-if-atp-safe-attachments-protection-is-in-place"></a>如何知道 ATP 安全附件保护是否就地

 为了 ATP 安全附件保护，以准备就绪，必须定义[ATP 安全附件策略](set-up-atp-safe-attachments-policies.md)。 
  
请参阅如何使用服务一个好方法是通过[查看高级威胁保护报告](view-reports-for-atp.md)。
  
此外下, 表介绍了一些示例方案。在所有这些情况下，我们假定组织具有 Office 365 企业 E5，其中包括高级威胁保护。
  
|**示例应用场景**|**ATP 安全附件保护不适用于这种情况下？**|
|:-----|:-----|
|Pat 组织具有 Office 365 企业 E5，但没有人具有尚未为 ATP 安全附件定义的任何策略。  <br/> |不。尽管功能可用，但至少一个 ATP 安全附件策略必须定义 ATP 安全附件保护，以准备就绪的顺序。  <br/> |
|李是 contoso 销售部的员工。李的组织仅财务人员应用于的位置中具有 ATP 安全附件策略。  <br/> |不。在这种情况下，财务人员将具有 ATP 安全附件保护，但其他员工，包括销售部门，将不是直到包括这些组的策略定义。  <br/> |
|昨天、 上 Jean 的组织的 Office 365 管理员设置适用于所有员工 ATP 安全附件策略。如今，前面 Jean 收到包含附件的电子邮件。  <br/> |是的。本示例中，Jean 具有许可证的高级威胁保护，并已定义 ATP 安全附件策略，其中包括 Jean。通常大约需要 30 分钟的新策略跨数据中心; 才会生效由于一天过后在这种情况下，该策略应实际上所示。  <br/> |
|Chris 的组织中的组织中的每个人的 ATP 安全附件策略与具有 Office 365 企业 E5。Chris 接收电子邮件有附件，并将转发组织之外的其他人的邮件。  <br/> |Chris 接收的邮件 ATP 安全附件保护。如果收件人的组织还就地具有 ATP 安全附件策略，则 Chris 转发的邮件将这些策略受转发的邮件到达时。  <br/> |
|晓明的组织在有 ATP 安全附件的策略和[SharePoint、 OneDrive 和 Microsoft 团队 ATP](atp-for-spo-odb-and-teams.md)开启。晓明假定 SharePoint Online 中的每个文件已扫描，可以安全地打开或下载。<br/> |根据定义; 策略就地是 ATP 安全附件保护但是，这并不意味着 SharePoint Online 的 OneDrive for Business 或 Microsoft 团队中的每个文件进行扫描。（若要了解详细信息，请参阅[SharePoint、 OneDrive 和 Microsoft 团队 ATP](atp-for-spo-odb-and-teams.md)。）<br/> |
   
## <a name="submitting-files-for-malware-analysis"></a>提交的恶意软件分析的文件

如果您收到要询问 Microsoft 进行分析的文件，请访问[提交恶意软件分析的文件](https://aka.ms/wdsi/submit)。
  
## <a name="related-topics"></a>相关主题

[Office 365 高级威胁防护](office-365-atp.md)
  
[设置 Office 365 中的 ATP 安全附件策略](set-up-atp-safe-attachments-policies.md)
  
[SharePoint、 OneDrive 和 Microsoft 团队 ATP](atp-for-spo-odb-and-teams.md)
  
[Office 365 中的 ATP 安全链接](atp-safe-links.md)
  
[Office 365 中的 ATP 防钓鱼功能](atp-anti-phishing.md)
  
[查看高级威胁保护报告](view-reports-for-atp.md)
  
