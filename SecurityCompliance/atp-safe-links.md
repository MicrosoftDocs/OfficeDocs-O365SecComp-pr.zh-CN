---
title: Office 365 ATP 安全链接
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.date: 02/05/2019
ms.topic: overview
f1_keywords:
- "197503"
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MET150
- MOE150
- ZVO160
- ZXL160
- ZPP160
- ZWD160
ms.assetid: dd6a1fef-ec4a-4cf4-a25a-bb591c5811e3
description: 安全链接功能提供的超链接中 Office 文档和电子邮件中的时间的单击验证。使用安全的链接可从网络钓鱼和其他攻击保护您的组织。
ms.openlocfilehash: 8c63de9e62e33dbca6dde5a5bb45a7f7875ab71f
ms.sourcegitcommit: c1c41744c2de89c9e172f817c8f73bb0ada81a58
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2019
ms.locfileid: "29792237"
---
# <a name="office-365-atp-safe-links"></a>Office 365 ATP 安全链接

## <a name="overview-of-office-365-atp-safe-links"></a>Overview of Office 365 ATP 安全链接

> [!IMPORTANT]
> 本文适用于企业客户。如果您是家庭用户查找有关在 Outlook 中的安全链接的信息，请参阅[高级 Outlook.com security](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2)。

Office 365 ATP 安全链接 （[高级威胁保护](office-365-atp.md)的一部分） 可帮助保护您的组织提供的[电子邮件](#how-atp-safe-links-works-with-email)和[Office 文档](#how-atp-safe-links-works-with-office-documents)中的 web 地址 (Url) 的时间的单击验证。保护通过[ATP 安全链接策略](set-up-atp-safe-links-policies.md)设置您的 Office 365 安全工作组的定义。 
  
位置 ATP 安全链接策略后，Office 365 全局管理员、 安全管理员和安全读者可以[用于高级威胁保护查看报告](view-reports-for-atp.md)。这些报告中的信息可帮助您采取进一步措施保护您的组织或调查安全事件的安全团队。

为[新功能添加到 ATP](office-365-atp.md#new-features-are-continually-being-added-to-atp)，您的 Office 365 安全团队可以添加或编辑您的组织 ATP 安全链接策略。此外，您可能会注意到更改和增强功能，如我们的新修改的[警告页面](atp-safe-links-warning-pages.md)和呈现在 Outlook 中的本机链接。
         
## <a name="how-atp-safe-links-works-with-urls-in-email"></a>ATP 安全链接如何处理电子邮件中的 Url

在高级别，下面是 ATP 安全链接保护的工作原理 Url 的电子邮件 （托管在 Office 365 中，不在本地） 中：
  
1. 人员接收电子邮件，其中一些包含 Url。
    
2. 基于签名的恶意软件保护，反垃圾邮件通过 Exchange Online Protection，其中 internet 协议 (IP) 和信封筛选器，转所有电子邮件和反恶意软件筛选器应用。 
    
3. 电子邮件到达人的收件箱中。
    
4. 用户登录到 Office 365，并转到其电子邮件收件箱。
    
5. 用户打开一封电子邮件，并单击电子邮件中的 URL。
    
6. ATP 安全链接功能立即打开网站之前检查的 URL。URL 标识为阻止，恶意，或安全。
    
    - 如果 URL 包含应用于用户的策略[自定义"执行不重写"Url 列表](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)中的网站，网站打开。 
    
    - 如果 URL 是到组织的[自定义被阻止的 Url 列表](set-up-a-custom-blocked-urls-list-wtih-atp.md)中包含的网站，[警告页](atp-safe-links-warning-pages.md)将打开。 
    
    - 如果已确定要恶意的网站 URL，打开[警告页](atp-safe-links-warning-pages.md)。 
    
    - 如果 URL 转到一个可下载的文件和组织的[安全链接 ATP 策略](set-up-atp-safe-links-policies.md)配置为扫描此类内容，则检查可下载文件。 
    
    - 如果 URL 确定为安全起见，打开网站。
    
## <a name="how-atp-safe-links-works-with-urls-in-office-documents"></a>ATP 安全链接如何处理在 Office 文档中的 Url

在高级别，下面是 ATP 安全链接保护的工作原理 Url 的 Office 365 ProPlus 应用程序 （当前版本的 Word、 Excel 和 PowerPoint 在 Windows 或 Mac 上 iOS 或 Android 设备，在 Windows、 OneNote Online 和 Office Online 上的 Visio 的 Office 应用程序上） 中：
  
1. 人员已在其计算机、 smartphone 或平板电脑上安装 Office 365 ProPlus。（或者，将 Office Online，在其浏览器中。）
    
2. 用户打开 Word、 Excel、 PowerPoint 或 Visio，并登录到 Office 365 企业版使用其工作或学校帐户。文档包含的 Url。
    
3. 当用户单击文档中的 URL 时，链接将检查 ATP 安全链接服务。
    
  - 如果应用于用户的策略[自定义"执行不重写"Url 列表](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)中包含的网站 URL，该用户是转到网站。 
    
  - 如果到组织的[自定义被阻止的 Url 列表](set-up-a-custom-blocked-urls-list-wtih-atp.md)中包含的网站 URL，用户将转到[警告页](atp-safe-links-warning-pages.md)。
    
  - 如果已确定要恶意的网站 URL，用户进入，[警告页](atp-safe-links-warning-pages.md)。
    
  - 如果 URL 转到一个可下载的文件和[ATP 安全链接策略](set-up-atp-safe-links-policies.md)配置为扫描此类下载，则检查可下载文件。 
    
  - 如果认为 URL 是安全的用户将转到网站。

## <a name="how-to-get-atp-safe-links-protection"></a>如何获取 ATP 安全链接保护

首先，请确保您的订阅包括[高级威胁保护](office-365-atp.md)。ATP 中包含在订阅，如[Microsoft 365 企业版](https://www.microsoft.com/microsoft-365/enterprise/home)、 [Microsoft 365 企业版](https://www.microsoft.com/microsoft-365/business)、 Office 365 企业 E5、 Office 365 教育版 A5 等。如果您的组织具有不包括 Office 365 ATP 的 Office 365 订阅，您可能可以作为购买 ATP。有关详细信息，请参阅[Office 365 高级威胁保护计划和定价](https://products.office.com/exchange/advance-threat-protection)和[Office 365 高级威胁 Protection Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)。 
  
接下来，请确保您 ATP 安全链接的策略定义。（请参阅[Set up Office 365 ATP 安全链接策略](set-up-atp-safe-links-policies.md)）。ATP 安全链接功能处于活动状态时：
  
- 为电子邮件和 Word、 Excel、 PowerPoint 和 Visio 文档中，则**ATP 安全链接策略设置**。（请参阅[Set up ATP Office 365 中的安全链接策略](set-up-atp-safe-links-policies.md)）。

- **Office 365 客户端应用程序配置为使用现代身份验证**（这是 ATP 安全链接保护 Office 文档中的值）。（请参阅[Office 2016 现代身份验证](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016)。） 
    
- **用户已登录到 Office 365**使用其工作或学校帐户。（请参阅[登录到 Office 或 Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426)）。
    
- **贵组织的电子邮件托管 Office 365 中**。 

若要定义 （或编辑） ATP 策略，您必须为分配下表中所述的角色之一：

|角色  |其中/如何分配  |
|---------|---------|
|Office 365 全局管理员 |注册以购买 Office 365 的人是默认情况下是全局管理员。（请参阅要了解的[有关 Office 365 管理员角色](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)）。         |
|Security Administrator |Azure Active Directory 管理员中心 ([https://aad.portal.azure.com](https://aad.portal.azure.com))|
|Exchange Online 组织管理 |Exchange 管理员中心 ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) <br>或 <br>  PowerShell cmdlet (请参阅[Exchange Online PowerShell 中](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)) |
    
## <a name="how-to-make-sure-atp-safe-links-protection-is-in-place"></a>如何使确保 ATP 安全链接保护已就绪

以全局管理员或安全管理员，务必要查看您的[ATP 安全链接策略](set-up-atp-safe-links-policies.md)。ATP 安全链接策略确定是否保护适用于电子邮件中的超链接，或 Url 以及 Office 文档中。

贵组织的安全工作组 ATP 安全链接策略后，可以查看如何 ATP 安全链接保护正常为贵组织的[高级威胁 protection 查看报表](view-reports-for-atp.md)，请参阅。 

## <a name="example-scenarios"></a>示例场景
  
下表介绍了一些示例方案 ATP 安全链接保护可能或可能不是就地的位置。（在所有这些情况下，我们假定组织具有 Office 365 企业 E5。）
  
|**示例应用场景**|**ATP 安全链接保护不适用于这种情况下？**|
|:-----|:-----|
|Jean 是组的具有 ATP 安全链接策略涵盖电子邮件和 Office 文档中的 Url 的成员。Jean 某人发送，打开 PowerPoint 演示文稿，然后单击演示文稿中的 URL。  <br/> |是的。定义 ATP 安全链接策略应用于 Jean 的组、 Jean 的电子邮件、 Word、 Excel、 PowerPoint 或 Visio 文档 Jean 打开，只要 Jean 登录，并在 Windows、 iOS 或 Android 设备上使用 Office 365 ProPlus。  <br/> |
|Chris 的组织，不全局或安全管理员具有尚未定义任何 ATP 安全链接策略。Chris 接收的电子邮件包含恶意网站的 URL。Chris 不知道是恶意 URL，并单击的链接。  <br/> |不。为了保护，以准备就绪，必须定义默认策略，以涵盖的组织中的每个人的 Url。  <br/> |
|在 Pat 组织，不全局或安全管理员定义或者尚未编辑 ATP 安全链接的任何策略。Pat 打开 Word 文档，并单击该文件中的 URL。  <br/> |为了保护，以准备就绪，必须定义否。 A 策略，其中包括 Office 文档。请参阅[Office 365 中的安全链接 ATP 策略设置](set-up-atp-safe-links-policies.md)。<br/> |
|李的组织具有 ATP 安全链接策略已`http://tailspintoys.com`列为被阻止的网站。李接收电子邮件包含 URL 的`http://tailspintoys.com/aboutus/trythispage`。李单击的 URL。<br/> |这取决于整个网站及其所有及其子页都包含在列表中是否阻止 Url。请参阅[设置自定义阻止 Url 列表使用 ATP 安全链接](set-up-a-custom-blocked-urls-list-wtih-atp.md)。<br/> |
|晓明，Jean 的同事，将电子邮件发送到 Jean，不知道电子邮件包含恶意的 URL。  <br/> |这取决于是否为在组织中发送电子邮件定义 ATP 安全链接策略。请参阅[Office 365 中的安全链接 ATP 策略设置](set-up-atp-safe-links-policies.md)。<br/> |


  

