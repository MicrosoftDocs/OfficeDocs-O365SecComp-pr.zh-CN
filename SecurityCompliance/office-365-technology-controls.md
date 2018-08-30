---
title: Office 365 技术控制
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 摘要： Office 365 的做法 Microsoft 技术控制的概述。
ms.openlocfilehash: 2ef04b558f5fa82075d9aa602b83d437aa4b2ee6
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525293"
---
# <a name="office-365-technology-controls"></a>Office 365 技术控制 

Microsoft 使用多种工具和技术，可控制、 管理和审核在 Exchange 在联机访问客户数据和 SharePoint Online，包括密码箱和客户密码箱、 多因素身份验证，等等。Yammer Enterprise 使用类似的控件，如[Yammer Enterprise 访问控件](office-365-yammer-enterprise-access-controls.md)中所述。

Office 365 工程师具有零个位置访问 Office 365 客户数据，并且必须经过审批过程，其中包括 Microsoft 和 – 如果客户许可客户密码箱功能的 Exchange Online 和 SharePoint Online – 客户审批，客户数据访问的服务操作发生之前。授予审批时，特定于服务的管理帐户都是已设置的实时具有足够的访问权限来执行任务所需的服务请求。

## <a name="lockbox-and-customer-lockbox"></a>密码箱和客户密码箱
虽然极少，客户无法请求可能公开客户的内容的 Microsoft 工程师，以帮助他们与问题的 Microsoft 帮助。控制对 Exchange Online 访问 (包括业务数据存储在用户的邮箱中任何 Skype （Skype 会议广播录制或由用户上载到会议的内容不包括业务范围的 Skype）) 和 SharePoint Online (包括 OneDrive for Business），Microsoft 使用调用密码箱访问控制系统。任何 Microsoft 工程师可以访问所有 Exchange Online 或 SharePoint Online 系统或数据之前，他们必须提交使用密码箱都访问请求。使用密码箱访问所需的所有提升到 Exchange Online 或 SharePoint Online。

密码箱处理请求授予工程师能够执行服务中的操作和管理功能的权限。通过密码箱，其中必须经管理者之前获得访问客户数据的能力工程师工程师提交请求。管理器审批时工程师具有对客户数据处理客户的问题的时间限制和范围有限访问权限。

Office 365 客户密码箱可帮助您满足合规性要求，如位于 FedRAMP 和 HIPAA，如果需要显式数据访问授权就地的过程。在极少数实例时 Microsoft 服务工程师需要访问数据，您将授予访问只对需要解决问题的数据和有限的时间。支持工程师执行的操作以进行审计记录，通过[Office 365 管理活动 API](https://msdn.microsoft.com/library/office/dn707383.aspx) [安全性和合规性中心](http://protection.office.com/)可访问。客户密码箱客户插入密码箱审批过程，并为他们提供控制对其 Exchange Online 或 SharePoint Online 内容的 Microsoft access 服务操作的授权的能力。

>**注意**： 客户密码箱可用在[Office 365 企业 E5](https://products.office.com/business/office-365-enterprise-e5-business-software)和为加载项购买，但必须在 Office 365 管理中心中执行手动操作 (在服务设置下 |客户密码箱） 来启用它。有关详细信息，请参阅[Office 365 客户密码箱请求](https://support.office.com/article/Office-365-Customer-Lockbox-Requests-36f9cdd1-e64c-421b-a7e4-4a54d16440a2)。

Exchange Online 和 SharePoint Online 的所有服务请求都处理密码箱系统。和与客户密码箱，因而需要访问这些服务向客户数据公开，从而任何服务操作经历密码箱审批过程，然后使客户能够批准或拒绝该请求此后。
 
*图 1-客户密码箱工作流*

如果请求被拒绝的客户，Microsoft 工程师将无法访问的客户的内容，并将无法完成服务操作。如果客户批准请求，Microsoft 工程师将具有有限的实时访问通过受约束的监视和管理界面的客户的内容。使用密码箱和客户密码箱，所有批准的访问是可跟踪到唯一用户，使工程师负责其处理客户数据。

## <a name="just-in-time-access"></a>在实时访问
Microsoft 使用 Office 365 中实时 (JIT) 访问原则进一步缓解凭据篡改和横向攻击的风险。JIT 删除持久管理访问服务，并能够按需提升到这些角色中替换这些权利。从管理员删除持久权限的凭据可确保仅他们需要并删除到公司凭据被盗的情况下在带来的风险。

JIT 访问模型要求工程师请求的有限的时间内执行管理职责提升的权限。此外，OCEs 使用计算机生成复杂密码创建的临时帐户并授予允许其执行必要的任务的那些角色。例如，密码箱授予访问权限管理时间绑定，并授予访问权限的时间量取决于所请求的角色。工程师指定过程对密码箱系统的请求中所需的时间访问权限的持续的时间。密码箱系统将拒绝请求的时间超过了最大允许时间提升的请求。提升请求的到期日期后删除的管理访问权限和临时帐户已过期。

授权和批准可用于访问 （例如，要调试的系统），工程师收到生成授权系统的提升访问请求已获得批准每次一次性使用管理密码。此密码工程师复制到安全密码、 独立于 Microsoft 企业环境中，工程师的凭据，并且仅适合会话提升的访问已为其批准。

## <a name="constrained-management-interfaces"></a>受约束的管理界面
OCEs 使用两个管理界面执行管理任务： 通过安全的终端服务网关 (Tsg) 和远程 PowerShell 远程桌面。这些管理中提供了有软件策略和放置在可执行哪些应用程序的重要限制哪些命令和 cmdlet 的访问控制的接口。 

Office 365 服务器将并发会话限制为一个会话每个服务团队管理员联系，每台服务器。Tsg 配置为允许只能有一个并发会话的用户，并且它们不允许多个会话。Tsg 允许 Office 365 服务团队管理员同时连接到多台服务器，使用单个会话每台服务器，以便管理员可以有效地执行其职责。服务团队管理员 Tsg 本身没有任何权限。TSG 仅用于强制实施多因素身份验证 (MFA) 和加密要求。服务团队管理员连接到通过 TSG 特定服务器后，特定服务器将强制实施每个管理员一个会话的限制。

使用率限制和 Office 365 人员连接和配置要求都被根据 Active Directory 组策略。这些策略包括以下特征：
- Tsg 配置为使用仅[FIPS](https://www.microsoft.com/en-us/TrustCenter/Compliance/FIPS) 140-2 验证的加密
- TSG 会话配置为在 30 分钟无活动后断开连接
- TSG 会话都配置为自动登录关闭 24 小时后

连接到 Tsg 也需要使用单独的物理智能卡和工程师 Microsoft 企业凭据分开的帐户的 MFA。工程师颁发不同的各种平台的智能卡和机密管理平台用于确保安全存储的凭据。Tsg 使用 Active Directory 组策略以控制哪些人可以登录到远程服务器，允许的会话数和空闲超时设置。其他策略来限制访问允许应用程序并限制 Internet 访问。

除了使用专门配置 Tsg 的远程访问，Exchange Online 允许与服务工程师操作角色的用户可以访问某些在使用远程 PowerShell 的生产服务器上的管理功能。若要执行此操作，用户必须为只读 （调试） 访问 Office 365 生产环境授权。特权提升启用相同的方式为 Tsg 使用密码箱过程启用它。

对于远程访问，充当单点访问每个数据中心没有负载平衡的虚拟 IP。远程 PowerShell cmdlet，可以执行基于 access 声明身份验证过程中获得中标识的权限级别。这些 cmdlet 都可以访问和使用此方法进行连接的用户执行的仅管理功能。使用远程 PowerShell 来限制范围的命令可用于通过密码箱过程授予的访问级别基于工程师。例如，在 Exchange Online 中，Get-mailbox 可能可用，但不是设置邮箱。
