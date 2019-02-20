---
title: Office 365 中的管理访问控制
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
description: '摘要: Office 365 的管理访问控制和数据分类概述。'
ms.openlocfilehash: f5cac8b6161ea7eab6ea390e32caec1c5ddb9bac
ms.sourcegitcommit: c94cb88a9ce5bcc2d3c558f0fcc648519cc264a2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/20/2019
ms.locfileid: "30091020"
---
# <a name="administrative-access-controls-in-office-365"></a><span data-ttu-id="a4254-103">Office 365 中的管理访问控制</span><span class="sxs-lookup"><span data-stu-id="a4254-103">Administrative Access Controls in Office 365</span></span> 

## <a name="introduction"></a><span data-ttu-id="a4254-104">简介</span><span class="sxs-lookup"><span data-stu-id="a4254-104">Introduction</span></span>
<span data-ttu-id="a4254-p101">microsoft 已在系统和控件中进行了大量投资, 以自动化大多数 Office 365 操作, 同时有意限制 Microsoft 对客户内容的访问。人类控制服务, 软件运行服务。这使 Microsoft 能够以扩展方式管理 Office 365, 并管理对客户内容 (如恶意参与者、Microsoft 工程师的 spear 和网络钓鱼等) 的内部威胁的风险。</span><span class="sxs-lookup"><span data-stu-id="a4254-p101">Microsoft has invested heavily and accordingly in systems and controls that automate most Office 365 operations while intentionally limiting Microsoft's access to customer content. Humans govern the service, and software operates the service. This enables Microsoft to manage Office 365 at scale, as well as manage the risks of internal threats to customer content such as malicious actors, the spear-phishing of a Microsoft engineer, and so forth.</span></span>

<span data-ttu-id="a4254-p102">默认情况下, Microsoft 工程师的管理权限为零, 并且在 Office 365 中对客户内容拥有零权限。microsoft 工程师在有限的时间段中, 可以对客户的内容进行有限、经过审核和安全的访问, 但仅当服务操作必要时, 并且仅当由 Microsoft 高级管理人员批准时 (对于那些授权为客户密码箱功能 (客户)。</span><span class="sxs-lookup"><span data-stu-id="a4254-p102">By default, Microsoft engineers have zero standing administrative privileges and zero standing access to customer content in Office 365. A Microsoft engineer can have limited, audited, and secured access to a customer's content for a limited amount of time, but only when necessary for service operations, and only when approved by a member of Microsoft senior management (and for customers that are licensed for the Customer Lockbox feature, the customer).</span></span>

<span data-ttu-id="a4254-110">Microsoft 提供了在线服务, 包括 Office 365, 使用了多种形式的云传递:</span><span class="sxs-lookup"><span data-stu-id="a4254-110">Microsoft provides online services, including Office 365, using multiple forms of cloud delivery:</span></span>

- <span data-ttu-id="a4254-111">**公共云**-包括在北美、南美洲、欧洲、亚洲、澳大利亚等托管的 Office 365、Azure 和其他服务的多租户版本。</span><span class="sxs-lookup"><span data-stu-id="a4254-111">**Public Clouds** - includes multi-tenant versions of Office 365, Azure, and other services that are hosted in North America, South America, Europe, Asia, Australia, etc.</span></span>
- <span data-ttu-id="a4254-112">**国家/地区云**-包括美国境外的所有 sovereign 和第三方运营云 (上面提到的云除外), 如中国 (由世纪互联运营) 的 office 365 和德国的 office (由 Microsoft 运营, 但在一种模型中, 德国数据受信者、德国电信, 控制并监控 Microsoft 对客户数据和包含客户数据的系统的访问。</span><span class="sxs-lookup"><span data-stu-id="a4254-112">**National Clouds** - includes all sovereign and third party-operated clouds outside of the United States (except for those noted above), such as Office 365 in China (which is operated by 21Vianet), and Office 365 in Germany (which is operated by Microsoft but under a model in which a German data trustee, Deutsche Telekom, controls and monitors Microsoft's access to Customer Data and systems that contain Customer Data).</span></span>
- <span data-ttu-id="a4254-113">**政府群**-包括适用于美国政府客户的 Office 365 和 Azure 服务。</span><span class="sxs-lookup"><span data-stu-id="a4254-113">**Government Clouds** - includes Office 365 and Azure services that are available to United States government customers.</span></span>

<span data-ttu-id="a4254-p103">出于本文的目的, Office 365 服务包括[exchange online](https://docs.microsoft.com/Exchange/exchange-online)、 [exchange online Protection](https://docs.microsoft.com/Office365/SecurityCompliance/eop/exchange-online-protection-overview)、 [SharePoint online](https://docs.microsoft.com/sharepoint/sharepoint-online) (包括[OneDrive for business](https://docs.microsoft.com/OneDrive/onedrive)) 和[Skype for](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-online)business, 以及其他信息关于一些[Yammer Enterprise](https://support.office.com/article/yammer-–-admin-help-e1464355-1f97-49ac-b2aa-dd320b179dbe?ui=en-US&rs=en-US&ad=US) access 控件。其他 Office 365 服务超出了本文的范围。</span><span class="sxs-lookup"><span data-stu-id="a4254-p103">For purposes of this article, Office 365 services include [Exchange Online](https://docs.microsoft.com/Exchange/exchange-online), [Exchange Online Protection](https://docs.microsoft.com/Office365/SecurityCompliance/eop/exchange-online-protection-overview), [SharePoint Online](https://docs.microsoft.com/sharepoint/sharepoint-online) (including [OneDrive for Business](https://docs.microsoft.com/OneDrive/onedrive)) and [Skype for Business](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-online), with additional information about some [Yammer Enterprise](https://support.office.com/article/yammer-–-admin-help-e1464355-1f97-49ac-b2aa-dd320b179dbe?ui=en-US&rs=en-US&ad=US) access controls. Other Office 365 services are out of scope for this article.</span></span>

## <a name="office-365-access-controls"></a><span data-ttu-id="a4254-116">Office 365 访问控制</span><span class="sxs-lookup"><span data-stu-id="a4254-116">Office 365 Access Controls</span></span>
<span data-ttu-id="a4254-p104">出于访问控制目的, Office 365 数据被分类为 "客户数据" 或其他类型的数据。客户数据是由客户使用 Office 365 服务提供或代表客户提供的所有数据, 例如客户内容 (由 office 365 用户直接创建或上载的内容, 包括电子邮件、SharePoint Online 内容、即时消息存储在 Office 365 中的日历项目、文档和联系人) 和最终用户的可识别信息 (EUII) (用户特有或 linkable 给个人用户但不包含客户内容的数据)。</span><span class="sxs-lookup"><span data-stu-id="a4254-p104">For access control purposes, Office 365 data is categorized as either Customer Data or other types of data. Customer Data is all data provided by or on behalf of a customer through the customer's use of Office 365 services, such as customer content (content directly created or uploaded by Office 365 users including emails, SharePoint Online content, instant messages, calendar items, documents, and contacts stored in Office 365) and end-user identifiable information (EUII) (data that is unique to a user or that is linkable to an individual user but does not include customer content).</span></span> 

<span data-ttu-id="a4254-119">其他类型的数据包括帐户数据 (包括管理数据, 即管理员在注册或购买服务时提供的信息) 和付款数据 (这是有关付款仪器的信息, 如信用卡详细信息)。组织可识别信息 (可用于标识租户的数据; 或使用率数据; 不 linkable 单个用户, 也不包含客户内容) 和系统元数据 (包括包含配置设置的服务日志) 和系统元数据 (包括包含配置设置的服务日志)系统状态、Microsoft IP 地址和有关订阅和租户的技术信息)。</span><span class="sxs-lookup"><span data-stu-id="a4254-119">Other types of data include account data (includes administrative data, which is the information provided by administrators when they sign-up or purchase services, and payment data, which is information about payment instruments, such as credit card details), organizationally identifiable information (data that can be used to identify a tenant; or usage data; it is not linkable to an individual user and does not include customer content), and system metadata (includes service logs that contain configuration settings, system status, Microsoft IP addresses, and technical information about subscriptions and tenants).</span></span>

<span data-ttu-id="a4254-120">Microsoft 已建立了访问控制机制, 以确保没有人对客户数据或访问控制数据 (用于管理对环境中其他类型的数据或函数的访问, 包括对客户内容或 EUII 的访问) 进行未批准的访问权限; 它包括 Microsoft 密码、安全证书和其他与身份验证相关的数据) 或对 Office 365 生产环境的未经批准的物理、逻辑或远程访问。</span><span class="sxs-lookup"><span data-stu-id="a4254-120">Microsoft has established access control mechanisms to ensure that no one has unapproved access to Customer Data or access control data (used to manage access to other types of data or functions within the environment, including access to customer content or EUII; it includes Microsoft passwords, security certificates, and other authentication-related data) or unapproved physical, logical, or remote access to the Office 365 production environment.</span></span>

<span data-ttu-id="a4254-121">Microsoft for Office 365 使用的访问控制可分为以下三类:</span><span class="sxs-lookup"><span data-stu-id="a4254-121">The access controls used by Microsoft for operating Office 365 can be grouped into three categories:</span></span>
- <span data-ttu-id="a4254-122">隔离控件</span><span class="sxs-lookup"><span data-stu-id="a4254-122">Isolation Controls</span></span>
- <span data-ttu-id="a4254-123">人员控制</span><span class="sxs-lookup"><span data-stu-id="a4254-123">Personnel Controls</span></span>
- <span data-ttu-id="a4254-124">技术控制</span><span class="sxs-lookup"><span data-stu-id="a4254-124">Technology Controls</span></span>

<span data-ttu-id="a4254-p105">组合后, 这些控件有助于防止和检测 Office 365 中的恶意操作。除了 Microsoft 使用的隔离、人员和技术控件之外, 还有第四个类别的控件: 由客户实施的控件。</span><span class="sxs-lookup"><span data-stu-id="a4254-p105">When combined, these controls help prevent and detect malicious actions in Office 365. In addition to the isolation, personnel, and technology controls used by Microsoft, there is a fourth category of controls: those implemented by customers.</span></span>

<span data-ttu-id="a4254-p106">Office 365 使您能够以与在本地环境中管理数据的相同方式管理数据。注册 Office 365 组织的人员将自动成为全局管理员 (管理员)。全局管理员可以访问管理门户中的所有功能 (例如, admin 中心和远程 PowerShell), 还可以创建或编辑用户、向其他人分配管理员角色、重置用户密码、管理用户许可证、管理域和批准客户密码箱请求, 以及其他操作。我们建议每个组织至少指定两个管理员帐户, 并且根据组织的规模, 您可能需要指定多个服务的不同管理员。有关分配管理员角色和权限的信息, 请参阅[在 office 365 中分配管理员角色](https://support.office.com/article/Assigning-admin-roles-in-Office-365-eac4d046-1afd-4f1a-85fc-8219c79e1504)和[关于 Office 365 管理员角色](https://support.office.com/article/Permissions-in-Office-365-DA585EEA-F576-4F55-A1E0-87090B6AAA9D)。</span><span class="sxs-lookup"><span data-stu-id="a4254-p106">Office 365 allows you to manage your data much in the same way data is managed in on-premises environments. The person who signs up an organization for Office 365 automatically becomes a global administrator (admin). The global admin has access to all features in the management portals (e.g., admin centers and remote PowerShell), and can create or edit users, assign admin roles to others, reset user passwords, manage user licenses, manage domains, and approve Customer Lockbox requests, among other things. We recommend that each organization designate at least two admin accounts, and depending on the size of your organization, you may want to designate several admins who serve different functions. For information about assigning admin roles and permissions, see [Assigning admin roles in Office 365](https://support.office.com/article/Assigning-admin-roles-in-Office-365-eac4d046-1afd-4f1a-85fc-8219c79e1504) and [About Office 365 admin roles](https://support.office.com/article/Permissions-in-Office-365-DA585EEA-F576-4F55-A1E0-87090B6AAA9D).</span></span>


## <a name="related-links"></a><span data-ttu-id="a4254-132">相关链接</span><span class="sxs-lookup"><span data-stu-id="a4254-132">Related Links</span></span>

- [<span data-ttu-id="a4254-133">隔离控件</span><span class="sxs-lookup"><span data-stu-id="a4254-133">Isolation Controls</span></span>](office-365-isolation-controls.md)
- [<span data-ttu-id="a4254-134">人员控制</span><span class="sxs-lookup"><span data-stu-id="a4254-134">Personnel Controls</span></span>](office-365-personnel-controls.md)
- [<span data-ttu-id="a4254-135">技术控制</span><span class="sxs-lookup"><span data-stu-id="a4254-135">Technology Controls</span></span>](office-365-technology-controls.md)
- [<span data-ttu-id="a4254-136">监视和审核访问控制</span><span class="sxs-lookup"><span data-stu-id="a4254-136">Monitoring and Auditing Access Controls</span></span>](office-365-monitoring-and-auditing-access-controls.md)
- [<span data-ttu-id="a4254-137">Yammer Enterprise访问控制</span><span class="sxs-lookup"><span data-stu-id="a4254-137">Yammer Enterprise Access Controls</span></span>](office-365-yammer-enterprise-access-controls.md)