---
title: Office 365 ATP 安全链接
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
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
ms.openlocfilehash: 9199c69d73a1585d76181c7a5feba79e465289db
ms.sourcegitcommit: e14dec9bed0c0009acbc1f1cb80b4d0794ad5739
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/05/2018
ms.locfileid: "25435109"
---
# <a name="office-365-atp-safe-links"></a>Office 365 ATP 安全链接

Office 365 ATP 安全链接 （ATP 安全链接） （以及[Office 365 ATP 安全附件](atp-safe-attachments.md)） 是一套安全功能的[Office 365 高级威胁保护](office-365-atp.md)企业组织的一部分提供。ATP 安全链接可帮助保护您的组织提供的[电子邮件](#how-atp-safe-links-works-with-email)和[Office 文档](#how-atp-safe-links-works-with-office-documents)中的 web 地址 (Url) 的时间的单击验证。保护通过[ATP 安全链接策略](set-up-atp-safe-links-policies.md)设置您的 Office 365 安全工作组的定义。 
  
位置 ATP 安全链接策略后，Office 365 全局管理员、 安全管理员和安全读者可以[用于高级威胁保护查看报告](view-reports-for-atp.md)。这些报告中的信息可帮助您采取进一步措施保护您的组织或调查安全事件的安全团队。
         
## <a name="how-atp-safe-links-works-with-email"></a>电子邮件时，ATP 安全链接的工作方式

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
    
## <a name="how-atp-safe-links-works-with-office-documents"></a>Office 文档时，ATP 安全链接的工作方式

在高级别，下面是 ATP 安全链接保护的工作原理 Url 的 Office 365 ProPlus 应用程序 （当前版本的 Word、 Excel 和 PowerPoint 在 Windows 或 Mac 上 iOS 或 Android 设备，在 Windows、 OneNote Online 和 Office Online 上的 Visio 的 Office 应用程序上） 中：
  
1. 人员已在其计算机、 smartphone 或平板电脑上安装 Office 365 ProPlus。（或者，将 Office Online，在其浏览器中。）
    
2. 用户打开 Word、 Excel、 PowerPoint 或 Visio，并登录到 Office 365 企业版使用其工作或学校帐户。文档包含的 Url。
    
3. 当用户单击文档中的 URL 时，链接将检查 ATP 安全链接服务。
    
  - 如果应用于用户的策略[自定义"执行不重写"Url 列表](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)中包含的网站 URL，该用户是转到网站。 
    
  - 如果到组织的[自定义被阻止的 Url 列表](set-up-a-custom-blocked-urls-list-wtih-atp.md)中包含的网站 URL，用户将转到[警告页](atp-safe-links-warning-pages.md)。
    
  - 如果已确定要恶意的网站 URL，用户进入，[警告页](atp-safe-links-warning-pages.md)。
    
  - 如果 URL 转到一个可下载的文件和[ATP 安全链接策略](set-up-atp-safe-links-policies.md)配置为扫描此类下载，则检查可下载文件。 
    
  - 如果认为 URL 是安全的用户将转到网站。

## <a name="new-features-added-to-atp-safe-links"></a>新功能添加到 ATP 安全链接

我们将继续向 ATP 安全链接添加新功能。以下是几个示例：
  
- 从开始后期年 10 月 2017年，ATP 安全链接保护扩展到 Url 为 Url 或电子邮件中 Office 365 ProPlus 的文档，如 Word、 Excel、 PowerPoint 和 Visio 中对应用 Windows，以及 Office iOS 和 Android 设备上的应用程序。（请确保您使用的[Office 现代身份验证](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016)。）
    
- 从开始年 3 月 2018年，被扩展 ATP 安全链接保护应用于组织内的人员之间发送的电子邮件。（请确保[查看](set-up-atp-safe-links-policies.md)和编辑 ATP 安全链接策略。）

- 年 6 月 2018，当用户使用 Outlook Web 应用程序 (OWA)，在开始 ATP 安全链接呈现原始 Url，并不显示重写的 Url。这样用户电子邮件中查看原始的链接。（我们调用此本机链接 visbility）。

- 年 9 月 2018年中的开始、 [Office 365 ATP 警告页](atp-safe-links-warning-pages.md)功能新的配色方案、 更多详细信息，和以继续前进到尽管网站的功能在给定警告和建议。 
  
- 开始在 2018年的第二部分中，ATP 安全链接被扩展保护于 Url 的 Office Online （Word Online、 Excel Online、 PowerPoint Online 和 OneNote 联机） 和 Office 365 ProPlus 上 mac。（请确保[查看](set-up-atp-safe-links-policies.md)和编辑 ATP 安全链接策略。）
   
- 从开始后期 2018年，本机链接可见性是 Outlook 中可用。无论使用 OWA 或 Outlook，用户能够在电子邮件，查看原始 Url (不重写 Url)。
    
## <a name="how-to-get-atp-safe-links-protection"></a>如何获取 ATP 安全链接保护

ATP 安全链接功能是[高级威胁保护](office-365-atp.md)，包括在 Office 365 企业 E5 的一部分。如果您的组织使用的另一个 Office 365 企业版订阅，高级威胁保护可以作为加载项进行购买。有关详细信息，请参阅[Office 365 平台服务说明： Office 365 安全性&amp;合规性中心](https://technet.microsoft.com/en-us/library/dn933793.aspx)和[购买或编辑企业的 Office 365 的加载项](https://support.office.com/article/4e7b57d6-b93b-457d-aecd-0ea58bff07a6)。
  
ATP 安全链接功能处于活动状态时：
  
- 为电子邮件和 Word、 Excel、 PowerPoint 和 Visio 文档中，则**ATP 安全链接策略设置**。（请参阅[Set up ATP Office 365 中的安全链接策略](set-up-atp-safe-links-policies.md)）。

- **Office 365 客户端应用程序配置为使用现代身份验证**。（请参阅[Office 2016 现代身份验证](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016)。） 
    
- **用户已登录到 Office 365**使用其工作或学校帐户。（请参阅[登录到 Office 或 Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426)）。
    
- **贵组织的电子邮件托管 Office 365 中**，不在内部部署服务器。 
    
## <a name="make-sure-atp-safe-links-protection-is-in-place"></a>请确保 ATP 安全链接保护就地

请参阅如何使用 ATP 安全链接保护运行您的组织的一个好办法是通过[查看高级威胁保护报告](view-reports-for-atp.md)。此外，作为全局或安全管理员，请务必查看您的[ATP 安全链接策略](set-up-atp-safe-links-policies.md)。ATP 安全链接策略确定是否保护适用于电子邮件中的超链接，或 Url 以及 Office 文档中。

## <a name="example-scenarios-where-atp-safe-links-protection-might-or-might-not-be-in-place"></a>示例方案 ATP 安全链接保护可能或可能不是就地的位置
  
下表介绍了一些示例方案 ATP 安全链接保护可能或可能不是就地的位置。（在所有这些情况下，我们假定组织具有 Office 365 企业 E5。）
  
|**示例应用场景**|**ATP 安全链接保护不适用于这种情况下？**|
|:-----|:-----|
|Jean 是组的具有 ATP 安全链接策略涵盖电子邮件和 Office 文档中的 Url 的成员。Jean 某人发送 PowerPoint 2016 中打开一个演示文稿，然后单击演示文稿中的 URL。  <br/> |是的。定义 ATP 安全链接策略应用于 Jean 的组、 Jean 的电子邮件、 Word、 Excel、 PowerPoint 或 Visio 文档 Jean 打开，只要 Jean 登录，并在 Windows、 iOS 或 Android 设备上使用 Office 365 ProPlus。  <br/> |
|Chris 的组织，不全局或安全管理员具有尚未定义任何 ATP 安全链接策略。Chris 接收的电子邮件包含恶意网站的 URL。Chris 不知道是恶意 URL，并单击的链接。  <br/> |不。为了保护，以准备就绪，必须定义默认策略，以涵盖的组织中的每个人的 Url。  <br/> |
|在 Pat 组织，不全局或安全管理员定义或者尚未编辑 ATP 安全链接的任何策略。Pat 打开 Word 文档，并单击该文件中的 URL。  <br/> |为了保护，以准备就绪，必须定义否。 A 策略，其中包括 Office 文档。请参阅[Office 365 中的安全链接 ATP 策略设置](set-up-atp-safe-links-policies.md)。<br/> |
|李的组织具有 ATP 安全链接策略已`http://tailspintoys.com`列为被阻止的网站。李接收电子邮件包含 URL 的`http://tailspintoys.com/aboutus/trythispage`。李单击的 URL。<br/> |这取决于整个网站及其所有及其子页都包含在列表中是否阻止 Url。请参阅[设置自定义阻止 Url 列表使用 ATP 安全链接](set-up-a-custom-blocked-urls-list-wtih-atp.md)。<br/> |
|晓明，Jean 的同事，将电子邮件发送到 Jean，不知道电子邮件包含恶意的 URL。  <br/> |这取决于是否为在组织中发送电子邮件定义 ATP 安全链接策略。请参阅[Office 365 中的安全链接 ATP 策略设置](set-up-atp-safe-links-policies.md)。<br/> |
   
## <a name="related-topics"></a>相关主题

[Office 365 高级威胁防护](office-365-atp.md)
  
[设置 Office 365 中的安全链接 ATP 策略](set-up-atp-safe-links-policies.md)
  
[Office 365 中的 ATP 安全附件](atp-safe-attachments.md)
  
[Office 365 中的 ATP 防钓鱼功能](atp-anti-phishing.md)
  
[查看高级威胁保护报告](view-reports-for-atp.md)
  

