---
title: 启用报告消息加载项
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 03/05/2019
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 4250c4bc-6102-420b-9e0a-a95064837676
ms.collection:
- M365-security-compliance
description: 了解如何为单个用户或您的整个组织启用 outlook 和 web 上的 outlook 和 outlook 网页版报告消息外接程序。
ms.openlocfilehash: f2bb79c4c613fdb804d19226fb359124387a678f
ms.sourcegitcommit: 0f93b37c39d807dec91f118aa671a3430c47a9ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/20/2019
ms.locfileid: "30693381"
---
# <a name="enable-the-report-message-add-in"></a>启用报告消息加载项

> [!NOTE]
> outlook 和 web 上的 outlook 的报告邮件外接程序与[outlook 垃圾邮件筛选器](https://support.office.com/article/Overview-of-the-Junk-Email-Filter-5ae3ea8e-cf41-4fa0-b02a-3b96e21de089)并不完全相同, 但这两者都可用于将电子邮件标记为垃圾邮件、非垃圾邮件或网络钓鱼尝试。 不同之处在于, outlook 和 web 上的 outlook 的报告邮件外接程序会通知 Microsoft misclassified 电子邮件, 而 outlook 垃圾邮件筛选器用于组织用户邮箱中的电子邮件。 

## <a name="overview"></a>概述

outlook 和 web 上的 outlook 的报告消息外接程序使用户能够轻松地向 Microsoft 及其子公司报告 misclassified 电子邮件 (无论是安全还是恶意)。 Microsoft 使用这些提交改进电子邮件保护技术的有效性。 此外, 如果您的组织使用的是[Office 365 高级威胁防护计划 1](office-365-atp.md)或[计划 2](office-365-ti.md), 则报告消息外接程序会为您组织的安全团队提供可用于查看和更新安全策略的有用信息。 

例如, 假设有人将大量邮件报告为网络钓鱼。 [安全仪表板](security-dashboard.md)和其他报告中的此信息图面。 组织的安全团队可以使用此信息指示可能需要更新的反网络钓鱼策略。 或者, 如果用户使用报告邮件外接程序报告大量被标记为垃圾邮件的邮件, 则组织的安全团队可能需要调整[反垃圾邮件策略](configure-the-anti-spam-policies.md)。 

报告邮件外接程序适用于 Office 365 订阅和以下产品:
 - Outlook 网页版
 - Outlook 2013 SP1
 - Outlook 2016
 - Outlook 2016 for Mac
 - Outlook 包含在 Office 365 专业增强版中

您的现有 web 浏览器应该能够满足报告消息外接程序的需要。但是, 如果您注意到加载项不可用或无法按预期工作, 请尝试使用不同的浏览器。
  
如果您是单个用户, 则可以[为自己启用报告邮件加载项](#get-the-report-message-add-in-for-yourself)。 
  
如果您是 Office 365 全局管理员或 exchange Online 管理员, 并且将 exchange 配置为使用 OAuth 身份验证, 则可以[为您的组织启用报告消息外接程序](#get-and-enable-the-report-message-add-in-for-your-organization)。 现在, 可以通过[集中部署](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins)使用报告消息加载项。
    
## <a name="get-the-report-message-add-in-for-yourself"></a>获取自己的报告邮件外接程序

1. 在[Microsoft AppSource](https://appsource.microsoft.com/marketplace/apps)中, 搜索[报告邮件外接程序](https://appsource.microsoft.com/product/office/wa104381180)。
    
2. 选择 "**立即获取**"。<br/>![报告消息-立即获取](media/ReportMessageGETITNOW.png)<br/> 
    
3. 查看使用条款和隐私策略。 然后选择" **继续**"。 
    
4. 使用你的工作或学校帐户 (用于商业用途) 或你的 Microsoft 帐户 (供个人使用) 登录 Office 365。
    
安装并启用加载项后, 您将看到以下图标: 

- 在 Outlook 中, 图标如下所示: <br/> ![报告邮件外接程序图标 (适用于 Outlook)](media/OutlookReportMessageIcon.png)<br/>
- 在 web 上的 Outlook (以前称为 Outlook web App) 中, 图标如下所示:<br/>![Outlook 网页报告邮件加载项图标](media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)<br/>

> [!TIP]
> 作为下一步, 了解如何[使用报告邮件加载项](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)。
  
## <a name="get-and-enable-the-report-message-add-in-for-your-organization"></a>为您的组织获取并启用报告邮件外接程序

> [!IMPORTANT]
> 若要完成此任务, 您必须是 Office 365 全局管理员或 Exchange Online 管理员。 此外, 必须将 Exchange 配置为使用 OAuth 身份验证以了解详细信息, 请参阅[exchange 要求 (加载项的集中部署)](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins&view=o365-worldwide#exchange-requirements)。 

1. 转到 Microsoft 365 管理中心中的 "[服务 & 外接程序" 页](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns)。<br/>![新 Microsoft 365 管理中心中的 "服务和外接程序" 页](media/ServicesAddInsPageNewM365AdminCenter.png)<br/> 
    
2. 选择 " **+ 部署外接端"**。<br/>![选择 "部署加载项"](media/ServicesAddIns-ChooseDeployAddIn.png)<br/> 
    
3. 在 "**新建外接端**" 屏幕中, 查看信息, 然后选择 "**下一步**"。<br/>![新加载项详细信息](media/NewAddInScreen1.png)<br/>
    
4. 选择 **"我想从 Office 应用商店添加外接程序**", 然后选择 "**下一步**"。<br/>![我想要添加新的外接程序](media/NewAddInScreen2.png)<br/> 
    
5. 搜索**报告消息**, 并在结果列表中的**报告邮件外接程序**旁边, 选择 "**添加**"。<br/>![搜索报告消息, 然后选择 "添加"](media/NewAddInScreen3.png)<br/>
    
6. 在 "**报告邮件**" 屏幕上, 查看信息, 然后选择 "**下一步**"。<br/>![报告消息详细信息](media/ReportMessageAdd-InNewScreen4.png)<br/>

7. 指定 Outlook 的用户默认设置, 然后选择 "**下一步**"。<br/>![为 Outlook 报告邮件的默认设置](media/ReportMessageOptionsScreen5.png)<br/>

8. 指定要获取报告邮件加载项的收件人, 然后选择 "**保存**"。 <br/>![谁可以获取报告邮件加载项](media/ReportMessageOptionsScreen6.png)<br/>

> [!TIP]
> 建议[设置一个规则, 以获取用户报告的电子](#set-up-a-rule-to-get-a-copy-of-email-messages-reported-by-your-users)邮件的副本。

根据您在设置加载项时选择的内容 (上面的步骤 7-8), 贵组织中的人员将会看到[报告消息外接程序](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)。 你组织中的人员将看到以下图标: 

- 在 Outlook 中, 图标如下所示: <br/> ![报告邮件外接程序图标 (适用于 Outlook)](media/OutlookReportMessageIcon.png)<br/>
- 在 web 上的 Outlook 中, 图标如下所示:<br/>![Outlook 网页报告邮件加载项图标](media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)<br/>

> [!TIP]
> 当您通知用户有关报告邮件加载项时, 请包含[使用报告邮件加载项](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)的链接。

## <a name="set-up-a-rule-to-get-a-copy-of-email-messages-reported-by-your-users"></a>设置一个规则, 以获取用户报告的电子邮件的副本

> [!IMPORTANT]
> 您必须是 Exchange Online 管理员才能执行此任务。
  
您可以设置一个规则, 以获取由组织中的用户报告的电子邮件的副本。 为组织下载并启用报告邮件外接程序后, 可以执行此操作。
  
1. 在 Exchange 管理中心中, 选择 "**邮件流** \> **规则**"。 
    
2. 选择**+** \> "**创建新规则**"。 
    
3. 在 "**名称**" 框中, 键入一个名称, 如 "提交"。
    
4. 在 "在**以下情况应用此规则**" 列表中, 选择**收件人地址包括 ...**。 
    
5. 在 "**指定字词或短语**" 屏幕中`junk@office365.microsoft.com` , `phish@office365.microsoft.com`添加和, 然后选择 **"确定"**。<br/>![指定规则的垃圾邮件和网络钓鱼电子邮件地址](media/018c1833-f336-4333-a45c-f2e8b75cd698.png)<br/>
  
6. 在 "**执行以下操作 ...** " 列表中, 选择 **"将邮件密件抄送给 ...**"。 
    
7. 添加全局管理员、安全管理员和/或安全阅读者, 这些读者应收到用户报告给 Microsoft 的每封电子邮件的副本, 然后选择 **"确定"**。<br/>![添加全局或安全管理员以接收每个报告的邮件的副本](media/a91ab9d1-66f2-4a2e-9dc1-f9f81a2298ad.png)<br/>
  
8. 选择 "**使用严重性级别审核此规则**", 然后选择 "**中**"。 
    
9. 在 "**为此规则选择模式**" 下, 选择 "**强制**"。<br/>![设置一个规则以获取每个报告的邮件的副本](media/f1cd95ce-e40d-4a8a-8f48-893469eba691.png)<br/>
  
10. 选择“保存”****。 
    
在适当的情况下, 当组织中的某人使用报告邮件加载项报告电子邮件时, 全局管理员、安全管理员和/或安全读者将收到该邮件的副本。 此信息可以让你设置或调整策略, 如[Office 365 ATP 安全链接](atp-safe-links.md)策略或[反垃圾邮件](anti-spam-protection.md)设置。 

## <a name="learn-how-to-use-the-report-message-add-in"></a>了解如何使用报告邮件加载项

请参阅[使用报告邮件加载项](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)。

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a>查看或编辑报告邮件外接程序的设置

您可以查看和编辑 "[服务 & 外接程序" 页](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns)上的 "报告邮件" 外接程序的默认设置。 

> [!IMPORTANT]
> 若要完成此任务, 您必须是 Office 365 全局管理员或 Exchange Online 管理员。
    
1. 转到 Microsoft 365 管理中心中的 "[服务 & 外接程序" 页](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns)。<br/>![新 Microsoft 365 管理中心中的 "服务和外接程序" 页](media/ServicesAddInsPageNewM365AdminCenter.png)<br/>

2. 查找并选择报告邮件加载项。<br/>![查找并选择报告邮件加载项](media/FindReportMessageAddIn.png)<br/> 
    
3. 在 "报告邮件" 屏幕上, 查看并编辑适用于您的组织的设置。<br/>![报告邮件外接程序的设置](media/EditReportMessageAddIn.png)<br/> 

## <a name="related-topics"></a>相关主题

[使用报告邮件加载项](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)
  
[查看安全&amp;合规性中心中的电子邮件安全报告](view-email-security-reports.md)

[查看 Office 365 高级威胁防护报告](view-reports-for-atp.md)

[在安全&amp;合规中心中使用资源管理器](use-explorer-in-security-and-compliance.md)
  

