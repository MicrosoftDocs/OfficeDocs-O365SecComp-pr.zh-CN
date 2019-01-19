---
title: 启用报告消息加载项
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/18/2019
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 4250c4bc-6102-420b-9e0a-a95064837676
description: 了解如何启用报告消息加载项的 Outlook 和 Outlook web，为各个用户或您的整个组织上。
ms.openlocfilehash: 013145813e8feb3e7389f6248ee26195c1df3d08
ms.sourcegitcommit: 1169a5759b9c2336fbc89d4651daf29e556f62fb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/18/2019
ms.locfileid: "28727866"
---
# <a name="enable-the-report-message-add-in"></a>启用报告消息加载项

## <a name="overview"></a>概述

报告消息外接程序 Outlook 和在 web 上的 Outlook 中，使人们能够轻松地分类的电子邮件安全还是恶意，向 Microsoft 和报告或其关联公司进行分析。Microsoft 使用这些提交来提高效率的电子邮件保护技术。此外，如果您的组织使用[Office 365 高级威胁保护](office-365-atp.md)或[Office 365 威胁智能](office-365-ti.md)，报告消息外接程序提供了有用的信息，它们可用于查看和更新组织的安全工作组安全策略。 

例如，假设人员包括报告很多为网络钓鱼邮件。在[安全仪表板](security-dashboard.md)和其他报表中此信息曲面。贵组织的安全工作组可以使用此信息，以指示防钓鱼策略可能需要更新。或者，如果人员报告大量使用报告消息加载项已标记为垃圾邮件为非垃圾邮件的邮件，贵组织的安全工作组可能需要调整[反垃圾邮件策略](configure-the-anti-spam-policies.md)。 

报告消息外接程序适用于 Office 365 订阅和以下产品：
 - Outlook 网页版
 - Outlook 2013 SP1
 - Outlook 2016
 - Outlook 2016 for Mac
 - 包含 Office 365 ProPlus 的 outlook

> [!NOTE]
> 报告消息加载项的 Outlook 和 Outlook web 上的是不完全不同于[Outlook 垃圾邮件筛选器](https://support.office.com/article/Overview-of-the-Junk-Email-Filter-5ae3ea8e-cf41-4fa0-b02a-3b96e21de089)时，尽管二者可以用来将电子邮件标记为垃圾、 不是垃圾邮件或网络钓鱼尝试。报告消息外接程序 Outlook 和 Outlook web 上的关于错误分类的电子邮件，而 Outlook 垃圾邮件筛选器，用于组织用户的邮箱中的电子邮件将通知 Microsoft。 
  
如果您是单个用户，您还可以[启用报告消息外接程序自己](#get-the-report-message-add-in-for-yourself)。 
  
如果您是 Office 365 全局管理员或 Exchange Online 管理员，并且 Exchange 配置为使用 OAuth 身份验证，则可以[启用报告消息外接程序为您的组织](#get-and-enable-the-report-message-add-in-for-your-organization)。报表消息加载项是现在可通过[集中部署](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins)。
    
## <a name="get-the-report-message-add-in-for-yourself"></a>获取外接程序为自己的报告邮件

1. 在[Microsoft AppSource](https://appsource.microsoft.com/marketplace/apps)，搜索的[邮件报告加载项](https://appsource.microsoft.com/product/office/wa104381180)。
    
2. 选择**获取 IT 现在**。<br/>![报告消息-立即获取](media/ReportMessageGETITNOW.png)<br/> 
    
3. 查看相应条款的使用和隐私策略。然后选择**继续**。 
    
4. 登录到 Office 365 使用您的工作或学校 （供业务使用） 的帐户或您的 Microsoft 帐户 （供个人使用）。
    
外接程序是安装并启用后，您将看到以下图标： 

- 在 Outlook 中，图标如下所示： <br/> ![报告用于 Outlook 的邮件外接程序图标](media/OutlookReportMessageIcon.png)<br/>
- 在 Outlook Web App （或在 web 上的 Outlook） 中，图标如下所示：<br/>![Outlook 邮件报告加载项的 web 图标](media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)<br/>

> [!TIP]
> 下一步，以了解如何[使用报告消息加载项](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)。
  
## <a name="get-and-enable-the-report-message-add-in-for-your-organization"></a>获取和报告消息外接程序为组织启用

> [!IMPORTANT]
> 您必须是 Office 365 全局管理员或 Exchange Online 管理员才能完成此任务。此外，Exchange 必须配置为使用 OAuth 身份验证以了解详细信息，请参阅[Exchange 要求 （集中部署的加载项）](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins&view=o365-worldwide#exchange-requirements)。 

1. 转到 Microsoft 365 管理中心中的[服务 & 外接程序页](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns)。<br/>![服务和加载项在新的 Microsoft 365 管理中心页](media/ServicesAddInsPageNewM365AdminCenter.png)<br/> 
    
2. 选择 **+ 部署外接程序**。<br/>![选择外接程序部署](media/ServicesAddIns-ChooseDeployAddIn.png)<br/> 
    
3. 在**新加载项**屏幕中，查看信息，，然后选择**下一步**。<br/>![新的外接程序详细信息](media/NewAddInScreen1.png)<br/>
    
4. 选择**我希望外接程序从 Office 商店添加**，，然后选择**下一步**。<br/>![我想要添加新加载项](media/NewAddInScreen2.png)<br/> 
    
5. 搜索**报告消息**，并在结果，旁边**报告消息加载项**列表中，选择**添加**。<br/>![搜索报告消息，然后选择添加](media/NewAddInScreen3.png)<br/>
    
6. 在**报告消息**屏幕上，查看信息，，然后选择**下一步**。<br/>![报告邮件详细信息](media/ReportMessageAdd-InNewScreen4.png)<br/>

7. 指定 Outlook 用户默认设置，然后选择**下一步**。<br/>![报告用于 Outlook 的邮件默认设置](media/ReportMessageOptionsScreen5.png)<br/>

8. 指定谁报告消息外接程序，，然后选择**保存**。 <br/>![谁将报告消息外接程序](media/ReportMessageOptionsScreen6.png)<br/>

> [!TIP]
> 我们建议[设置获取一份报告的用户的电子邮件的规则](#set-up-a-rule-to-get-a-copy-of-email-messages-reported-by-your-users)。

根据时设置外接程序 (步骤 7-8 上方)，您选择的内容在组织中的人员将具有[报告消息外接程序](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)可用。您的组织中的人员将看到以下图标： 

- 在 Outlook 中，图标如下所示： <br/> ![Outlook 报表消息外接程序图标](media/OutlookReportMessageIcon.png)<br/>
- 在 Outlook Web App （或在 web 上的 Outlook） 中，图标如下所示：<br/>![Outlook Web 报告消息外接程序图标](media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)<br/>

> [!TIP]
> 时通知用户有关邮件报告加载项，包括[使用报告消息加载项](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)的链接。

## <a name="set-up-a-rule-to-get-a-copy-of-email-messages-reported-by-your-users"></a>设置规则来获取一份报告的用户的电子邮件

> [!IMPORTANT]
> 您必须是 Exchange Online 管理员才能执行此任务。
  
您可以设置规则，若要获取的电子邮件组织中的用户报告的副本。在下载并为组织启用报告消息外接程序后执行此操作。
  
1. 在 Exchange 管理中心中，选择**邮件流** \> **规则**。 
    
2. 选择**+** \> **创建新规则**。 
    
3. 在**名称**框中，键入一个名称，例如提交。
    
4. 在**以下情况应用此规则**列表中，选择**在收件人地址包括...**。 
    
5. 在**指定词语或短语**屏幕中，添加`junk@office365.microsoft.com`和`phish@office365.microsoft.com`，然后选择**确定**。<br/>![指定规则的垃圾邮件和网络钓鱼电子邮件地址](media/018c1833-f336-4333-a45c-f2e8b75cd698.png)<br/>
  
6. 在 **...请执行以下**列表中，选择**密件抄送邮件到...**。 
    
7. 添加的全局管理员、 安全管理员和/或安全读者用户应收到人员报告给 Microsoft，每个电子邮件的副本，然后选择**确定**。<br/>![添加全局或安全管理员以接收报告的每封邮件的副本](media/a91ab9d1-66f2-4a2e-9dc1-f9f81a2298ad.png)<br/>
  
8. 选择**审核严重性级别与此规则**，然后选择**中等**。 
    
9. 在**选择此规则的模式**，下选择**强制**。<br/>![设置规则来获取每个报告的邮件的副本](media/f1cd95ce-e40d-4a8a-8f48-893469eba691.png)<br/>
  
10. 选择" **保存**"。 
    
与就地此规则，当您的组织中的某人报告电子邮件的邮件报告加载项，使用您的全局管理员、 安全管理员和/或安全读者将收到该邮件的副本。这些信息使您可以设置或调整策略，如[Office 365 ATP 安全链接](atp-safe-links.md)策略或您的[反垃圾邮件](anti-spam-protection.md)设置。 

## <a name="learn-how-to-use-the-report-message-add-in"></a>了解如何使用报告消息外接程序

请参阅[使用报告消息加载项](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)。

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a>查看或编辑报告消息加载项的设置

您可以查看和编辑报告消息外接程序在[服务 & 加载项页](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns)上的默认设置。 

> [!IMPORTANT]
> 您必须是 Office 365 全局管理员或 Exchange Online 管理员才能完成此任务。
    
1. 转到 Microsoft 365 管理中心中的[服务 & 外接程序页](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns)。<br/>![服务和加载项在新的 Microsoft 365 管理中心页](media/ServicesAddInsPageNewM365AdminCenter.png)<br/>

2. 查找并选择报告消息加载项。<br/>![查找并选择报告消息外接程序](media/FindReportMessageAddIn.png)<br/> 
    
3. 在报告消息屏幕上，查看和编辑根据您的组织的设置。<br/>![设置报告消息加载项](media/EditReportMessageAddIn.png)<br/> 
  
## <a name="related-topics"></a>相关主题

[使用报告消息外接程序](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)
  
[查看安全中的电子邮件安全报告&amp;合规性中心](view-email-security-reports.md)

[Office 365 高级威胁保护的视图报告](view-reports-for-atp.md)

[在安全中使用资源管理器&amp;合规性中心](use-explorer-in-security-and-compliance.md)
  

