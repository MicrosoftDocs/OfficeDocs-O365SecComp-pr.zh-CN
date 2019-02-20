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
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: '摘要: Microsoft 针对 Office 365 的技术控制措施概述。'
ms.openlocfilehash: 3fe7f47a2a1903d17c5240a0efec1c2abb94a25d
ms.sourcegitcommit: c94cb88a9ce5bcc2d3c558f0fcc648519cc264a2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/20/2019
ms.locfileid: "30090764"
---
# <a name="office-365-technology-controls"></a>Office 365 技术控制 

Microsoft 使用多种工具和技术来控制、管理和审核对 Exchange online 和 SharePoint online 中的客户数据的访问, 包括密码箱和客户密码箱、多重身份验证等。yammer enterprise 使用类似的控件, 如[Yammer Enterprise Access 控件](office-365-yammer-enterprise-access-controls.md)中所述。

office 365 工程师对 office 365 客户数据具有零的访问权限, 并且必须通过包含 Microsoft 和–如果客户对 Exchange online 和 SharePoint online 的客户密码箱功能进行了授权的审批流程 (客户)。批准, 然后才能访问客户数据以执行服务操作。授予批准后, 将立即预配特定于服务的管理帐户, 并且只需足够的访问权限即可执行服务请求所需的任务。

## <a name="lockbox-and-customer-lockbox"></a>密码箱和客户密码箱
虽然极少数情况下, 客户可以从 microsoft 请求获取帮助, 以向客户的内容提供 microsoft 工程师帮助他们解决问题。控制对 Exchange online 的访问 (包括存储在用户邮箱中的任何 Skype for business 数据 (skype for business 覆盖率不包括 skype 会议直播录制或用户上载到会议的内容) 和 SharePoint online (这包括 OneDrive for business) 时, Microsoft 使用称为 "密码箱" 的访问控制系统。在任何 Microsoft 工程师都可以访问任何 Exchange online 或 SharePoint online 系统或数据之前, 他们必须使用密码箱提交访问请求。对 Exchange online 或 SharePoint online 的所有提升访问权限都需要使用密码箱。

密码箱处理授予工程师在服务中执行操作和管理功能的能力的权限请求。工程师通过密码箱提交请求, 在工程师获得访问客户数据的能力之前, 必须由经理批准。在经理批准时, 工程师对客户数据具有受时间限制和范围限制的访问权限, 以处理客户问题。

适用于 Office 365 的客户密码箱可帮助您满足在 FedRAMP 和 HIPAA 中找到的合规性义务 (如果您需要实施显式数据访问授权的过程)。在 Microsoft 服务工程师需要访问您的数据时, 在极少数的实例中, 仅授予对解决问题所需的数据的访问权限, 并且只需一段有限的时间。支持工程师采取的操作是出于审核目的而记录的, 可通过[Office 365 管理活动 API](https://msdn.microsoft.com/library/office/dn707383.aspx)和[安全与合规中心](http://protection.office.com/)进行访问。客户密码箱将客户插入到密码箱审批过程, 并向他们提供控制 Microsoft 访问 Exchange online 或 SharePoint online 内容以进行服务操作的权限。

>**注意**: 客户密码箱在[office 365 企业版 E5](https://products.office.com/business/office-365-enterprise-e5-business-software)中可用, 并作为加载项购买, 但必须在 Office 365 管理中心中采取手动操作 (在 "服务设置" 下) (在 "服务设置" | "客户密码箱) 以启用它。有关详细信息, 请参阅[Office 365 客户密码箱请求](https://support.office.com/article/Office-365-Customer-Lockbox-Requests-36f9cdd1-e64c-421b-a7e4-4a54d16440a2)。

Exchange online 和 SharePoint online 的所有服务请求都由密码箱系统处理。在客户密码箱中, 任何服务操作 necessitating 对这些服务的访问权限, 并将其暴露给客户数据会经历密码箱审批过程, 并使客户能够在此后批准或拒绝该请求。
 
*图 1-客户密码箱工作流*

如果客户拒绝了该请求, Microsoft 工程师将无法访问客户的内容, 并且无法完成服务操作。如果客户批准了请求, Microsoft 工程师将通过受监控和约束的管理界面实时访问客户的内容。通过密码箱和客户密码箱, 所有批准的访问都可对唯一用户进行跟踪, 使工程师对客户数据的处理负责。

## <a name="just-in-time-access"></a>实时访问
Microsoft 使用 Office 365 的实时 (JIT) 访问原则来进一步降低凭据篡改和横向攻击的风险。JIT 可删除服务的持续管理访问权限, 并将这些权利替换为根据需要提升为这些角色的能力。从管理员中删除永久权限可确保凭据仅在需要时可用, 并消除凭据失窃情况下对公司造成的风险。

JIT 访问模型要求工程师在有限的时段内请求提升的权限, 以执行管理任务。此外, OCEs 还使用使用计算机生成的复杂密码创建的临时帐户, 并只授予那些允许他们执行必要任务的角色。例如, 由密码箱授予的管理访问是时间限制的, 并且授予访问权限的时间量取决于所请求的角色。工程师指定在密码箱系统请求期间所需的时间访问的持续时间。密码箱系统将拒绝请求, 其中所请求的时间超过提升的最长允许时间。提升请求到期后, 将删除管理访问权限并过期临时帐户。

当授权和批准访问 (例如, 调试系统) 时, 工程师将收到一次性使用的管理密码, 该密码由授权系统在每次批准请求提升访问时生成。此密码由工程师将其复制到密码安全, 与工程师的 Microsoft 公司环境凭据不同, 并且仅适用于已获得提升访问权限的会话。

## <a name="constrained-management-interfaces"></a>受约束的管理接口
OCEs 使用两个管理接口执行管理任务: 通过安全的终端服务网关 (TSGs) 和远程 PowerShell 的远程桌面。在这些管理界面中, 有一些软件策略和访问控制, 它们对可执行的应用程序以及可用的命令和 cmdlet 施加重大限制。 

Office 365 服务器将并发会话限制为每个服务的团队管理员, 每个服务器一个会话。TSGs 配置为仅允许用户使用单个并发会话, 并且不允许多个会话。TSGs 允许 Office 365 服务团队管理员同时连接到多台服务器, 每个服务器使用一个会话, 以便管理员能够有效地执行其职责。服务团队管理员对 TSGs 本身没有任何权限。TSG 仅用于强制实施多因素身份验证 (MFA) 和加密要求。一旦服务团队管理员通过 TSG 连接到特定服务器, 则该特定服务器将强制每个管理员一个会话限制为一个。

Office 365 人员的使用限制和连接和配置要求由 Active Directory 组策略建立。这些策略包括以下特征:
- 将 TSGs 配置为仅使用[FIPS](https://www.microsoft.com/en-us/TrustCenter/Compliance/FIPS) 140-2 验证的加密
- 将 TSG 会话配置为在不活动30分钟后断开连接
- 将 TSG 会话配置为在24小时后自动注销

与 TSGs 的连接还需要使用单独的物理智能卡和与工程师的 Microsoft 公司凭据分开的帐户进行 MFA。为各种平台颁发不同的智能卡的工程师和机密管理平台用于确保凭据的安全存储。TSGs 使用 Active Directory 组策略来控制谁可以登录到远程服务器、允许的会话数和空闲超时设置。设置了其他策略, 以限制对允许的应用程序的访问并限制 Internet 访问。

除了使用巧尽心思配置的 TSGs 的远程访问权限之外, Exchange Online 还允许具有服务工程师操作角色的用户使用远程 PowerShell 访问生产服务器上的特定管理功能。若要执行此操作, 用户必须获得对 Office 365 生产环境的只读 (调试) 访问权限。启用权限提升的方式与使用密码箱进程为 TSGs 启用权限的方式相同。

对于远程访问, 每个数据中心都有一个负载平衡的虚拟 IP 充当单个访问点。可以执行的远程 PowerShell cmdlet 基于身份验证期间获取的访问声明中标识的权限级别。这些 cmdlet 是唯一可由使用此方法进行连接的用户访问和执行的管理功能。远程 PowerShell 用于限制可用于工程师的命令的范围, 这取决于通过密码箱进程授予的访问级别。例如, 在 Exchange Online 中, 可以使用 "获取邮箱", 但设置邮箱将不会。
