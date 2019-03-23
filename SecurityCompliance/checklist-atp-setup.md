---
title: '快速入门: 设置 Office 365 高级威胁防护'
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 03/19/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: 您可以使用下面的快速入门指南来确保为您的组织设置和配置 Office 365 高级威胁防护 (ATP)。
ms.openlocfilehash: 5aecbdb63f30a620812de44907b29dcae838ba36
ms.sourcegitcommit: 0f93b37c39d807dec91f118aa671a3430c47a9ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/20/2019
ms.locfileid: "30693292"
---
# <a name="quick-start-guide-set-up-office-365-advanced-threat-protection"></a>快速入门指南: 设置 Office 365 高级威胁防护

下面是可用作检查表以确保为您的组织设置了 Office 365 高级威胁防护 (ATP) 的快速入门指南。 如果你是 Office 365 中的威胁防护新手, 或者你不确定从何处入手, 请使用以下指南作为起点。 

> [!IMPORTANT]
> **为每种策略提供了初始推荐设置; 但是, 有许多可用选项, 您可以调整设置以满足特定组织的需求**。 为你的策略或更改允许大约30分钟, 以在你的数据中心中工作。

## <a name="prerequisites"></a>先决条件

- 您的组织必须具有包含[Office 365 高级威胁防护](office-365-atp.md)(ATP) 的订阅。

- 必须为您分配适当的角色才能访问 ATP 功能。 下表包括一些示例: 

    |角色或角色组  |了解详细信息  |
    |---------|---------|
    |Office 365 全局管理员 |[关于 Office 365 管理员角色](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)|
    |Security Administrator |[Azure Active Directory 中的管理员角色权限](https://docs.microsoft.com/en-us/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
    |Exchange Online 组织管理 |[Exchange Online 中的权限](https://docs.microsoft.com/en-us/exchange/permissions-exo/permissions-exo) <br>and<br> [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)|

    (请参阅[Office 365 安全&amp;合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。)

## <a name="part-1---anti-malware"></a>第1部分-反恶意软件

1. 在 " [Office 365 安全 & 合规中心](https://protection.office.com)" 中, 选择 "**威胁管理** > **策略** > **反恶意软件**"。
2. 双击**默认**策略, 然后选择 "**设置**"。
3. 指定以下设置:
    - 在 "**恶意软件检测响应**" 部分, 保留默认设置 "**否**"。
    - 在 "**常见附件类型筛选器**" 部分, 选择 **"启用"**。
4. 单击“保存”****。

若要了解有关反恶意软件策略选项的详细信息, 请参阅[配置反恶意软件策略](configure-anti-malware-policies.md)。

## <a name="part-2---zero-day-protection"></a>第2部分-零天保护

通过策略 (如 ATP 安全链接和安全附件策略) 设置零日保护。

### <a name="atp-safe-attachments-policies"></a>ATP 安全附件策略

1. 在 " [Office 365 安全 & 合规中心](https://protection.office.com)" 中, 选择 "**威胁管理** > **策略** > **ATP 安全附件**"。
2. 选择 "**打开适用于 SharePoint、OneDrive 和 Microsoft 团队的 ATP**" 选项。
3. 在 "**保护电子邮件附件**" 部分, 单击加号 (**+**)。
4. 指定以下设置:
    - 在 "**名称**" 框中`Block malware`, 键入。
    - 在 "响应" 部分, 选择 "**阻止**"。
    - 在 "**重定向附件**" 部分中, 选择 "**启用重定向**" 选项, 然后指定将查看检测到的文件的组织的安全管理员或操作员的电子邮件地址。
    - 在 "**应用**于" 部分中, 选择 **"收件人域"**。 然后, 选择您的域, 选择 "**添加**", 然后单击 **"确定"**。
5. 单击“保存”****。
6. (建议的附加步骤)作为全局管理员或 SharePoint Online 管理员, 运行**[set-spotenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant?view=sharepoint-ps)** cmdlet, 并将 Office 365 环境的**DisallowInfectedFileDownload**参数设置为*true* 。 (这将阻止用户打开、移动、复制或共享被检测为恶意的文件。)  

若要了解详细信息, 请参阅[设置 office 365 atp 安全附件策略](set-up-atp-safe-attachments-policies.md)和[打开 SharePoint、OneDrive 和 Microsoft 团队的 Office 365 ATP](turn-on-atp-for-spo-odb-and-teams.md)。

### <a name="atp-safe-links-policies"></a>ATP 安全链接策略

若要设置 ATP 安全链接, 请查看您的默认策略并添加策略。

1. 在 " [Office 365 安全 & 合规中心](https://protection.office.com)" 中, 选择 "**威胁管理** > **策略** > **ATP 安全链接**"。
2. 双击**默认**策略。
3. 在 "**使用安全链接**" 部分, 选择 " **office 365 专业增强版"、"office for iOS" 和 "Android**" 选项, 然后单击 "**保存**"。
4. 在 "**适用于特定收件人的策略**" 部分, 单击加号 (**+**)。
5. 指定以下设置:
    - 在 "**名称**" 框中, 键入一个名称, `Safe Links`例如。
    - 在 "**选择操作**" 部分, 选择 **"启用"**。
    - 选择以下选项:
        - **使用安全附件扫描可下载的内容** 
        - **将安全链接应用于在组织内发送的电子邮件**
        - **不要让用户通过指向原始 URL 的安全链接进行单击**
    - 在 "**应用**于" 部分中, 选择 **"收件人域"**。 然后, 选择您的域, 选择 "**添加**", 然后单击 **"确定"**。
6. 单击“保存”****。

若要了解详细信息, 请参阅[设置 Office 365 ATP 安全链接策略](set-up-atp-safe-links-policies.md)。 

## <a name="part-3---anti-phishing"></a>第3部分-反网络钓鱼 

1. 在 " [Office 365 安全 & 合规中心](https://protection.office.com)" 中, 选择 "**威胁管理** > **策略** > **ATP 反网络钓鱼**"。
2. 单击 "**默认策略**"。
3. 在 "**模拟**" 部分, 单击 "**编辑**", 然后指定以下设置:
    -  在 "**添加要保护的用户**" 选项卡上打开 "保护"。 然后添加用户, 如贵组织的董事会成员、CEO、CFO 和其他高级领导者。 (可以键入单个电子邮件地址, 或单击以显示列表。)
    - 在 "**要保护的添加域**" 选项卡上, 打开 "**自动包括我拥有的域"**。 如果你有自定义域, 请将其添加。
    - 在 "**操作**" 选项卡上, 选择 "**将邮件移至收件人的垃圾邮件文件夹"** 以模拟用户和模拟域, 然后打开安全提示。
    - 在 "**邮箱智能**" 选项卡上, 确保邮箱智能已打开。
    - 查看设置选项卡上的 "**查看设置**" 选项卡后, 单击 "**保存**"。
4. 在 "**欺骗**" 部分, 单击 "**编辑**", 然后指定以下设置:
    - 在 "**哄骗筛选器设置**" 选项卡上, 确保已打开 "反欺骗保护"。
    - 在 "**操作**" 选项卡上, 选择 "将邮件移动到收件人的垃圾邮件文件夹"。
    - 查看设置选项卡上的 "**查看设置**" 选项卡后, 单击 "**保存**"。 (如果未进行任何更改, 请单击 "**取消**"。)
5. 关闭 "默认策略设置" 页。

若要了解有关反网络钓鱼策略选项的详细信息, 请参阅[设置 Office 365 ATP 反网络钓鱼和反网络钓鱼策略](set-up-anti-phishing-policies.md)。

## <a name="part-4---anti-spam"></a>第4部分-反垃圾邮件

1. 在 " [Office 365 安全 & 合规中心](https://protection.office.com)" 中, 选择 "**威胁管理** > **策略** > **反垃圾邮件**"。
2. 在 "**自定义**" 选项卡上, 打开**自定义设置**。
3. 展开 "**默认垃圾邮件筛选器策略**", 单击 "**编辑策略**", 然后指定以下设置:
    - 在 "**垃圾邮件和批量操作**" 部分, 将阈值设置为值5或6。
    - 在 "**允许列表**" 部分中, 查看 (必要时编辑) 您允许的发件人和域。
4. 单击“保存”****。

若要了解有关反垃圾邮件策略选项的详细信息, 请参阅[配置反垃圾邮件策略](configure-the-anti-spam-policies.md)。

## <a name="part-5---service-wide-settings"></a>第5部分-服务范围设置

### <a name="zero-hour-auto-purge"></a>零小时自动清除

0小时自动清除 (ZAP) 在默认情况下处于打开状态。但是, 必须满足以下条件:
- 垃圾邮件操作设置为将**邮件移动到**反垃圾邮件策略中的 "垃圾邮件" 文件夹。
- 用户保留其默认的垃圾邮件设置, 但尚未关闭垃圾邮件保护。

若要了解详细信息, 请参阅[针对垃圾邮件和恶意软件的零小时自动清除保护](zero-hour-auto-purge.md)。

### <a name="audit-logging"></a>审核日志记录

为了查看威胁防护报告中的数据 (如[安全仪表板](security-dashboard.md)和[浏览器](use-explorer-in-security-and-compliance.md)), 必须为您的组织打开审核日志记录。

请参阅[打开或关闭 Office 365 审核日志搜索](turn-audit-log-search-on-or-off.md)。

## <a name="post-setup-tasks"></a>安装后任务

### <a name="watch-for-new-features-and-service-updates"></a>监视新功能和服务更新

- [访问 Microsoft 365 路线图](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection)

- [请参阅 Office 365 高级威胁防护服务说明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp)

### <a name="see-how-atp-is-working-for-your-organization"></a>了解 ATP 如何为你的组织工作

- [查看 Office 365 高级威胁防护报告](view-reports-for-atp.md)

- [在安全&amp;合规中心中使用资源管理器](use-explorer-in-security-and-compliance.md)

### <a name="periodically-review-and-revise-your-atp-policies"></a>定期查看和修订 ATP 策略

- [使用 office 365 的威胁调查和响应确保 office 365 用户安全](keep-users-safe-with-office-365-ti.md) 

- [在 Office 365 安全&amp;合规中心中使用智能报告和见解](reports-and-insights-in-security-and-compliance.md) 