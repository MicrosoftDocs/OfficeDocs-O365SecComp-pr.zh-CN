---
title: 设置 Office 365 ATP 安全附件策略
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 078eb946-819a-4e13-8673-fe0c0ad3a775
description: 定义附件安全策略，以从电子邮件中的恶意文件保护您的组织。
ms.openlocfilehash: 7c2bcfd1d9faad48cb8852b066f544abd1fb6ace
ms.sourcegitcommit: 2cf7f5bb282c971d33e00f65d9982a3f14aec74e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/27/2018
ms.locfileid: "26706066"
---
# <a name="set-up-office-365-atp-safe-attachments-policies"></a>设置 Office 365 ATP 安全附件策略

人员定期发送，接收和共享附件，如文档、 演示文稿、 电子表格和详细信息。它并不总是易于判断附件是安全或恶意只通过查看电子邮件。和所需的最后一项是通过，获取恶意附件现在为您的组织破坏。幸运的是，可以帮助[Office 365 高级威胁保护](office-365-atp.md)(ATP)。您可以设置[ATP 安全附件](atp-safe-attachments.md)策略，以帮助确保您的组织受不安全的电子邮件附件攻击。 
  
## <a name="what-to-do"></a>需执行的操作 
  
1. [查看先决条件](#review-the-prerequisites)
    
2. [设置 ATP 安全附件策略](#set-up-an-atp-safe-attachments-policy)
    
3. [了解 ATP 安全附件策略选项](#learn-about-atp-safe-attachments-policy-options)
    
## <a name="step-1-review-the-prerequisites"></a>步骤 1： 查看必备组件

- 请确保您的组织具有[Office 365 高级威胁保护](office-365-atp.md)。
    
- 请确保您具有必要[Office 365 安全权限&amp;合规性中心](permissions-in-the-security-and-compliance-center.md)。
    
- [了解 ATP 安全附件策略选项](#learn-about-atp-safe-attachments-policy-options)（本文中）。扫描的附件时，一些选项，如监视或替换选项中，会导致次要电子邮件的延迟。若要避免出现邮件延迟，请考虑使用[动态交付和预览](dynamic-delivery-and-previewing.md)。
    
- 允许最多 30 分钟的新的或更新策略传播到所有 Office 365 数据中心。
    
## <a name="step-2-set-up-or-edit-an-atp-safe-attachments-policy"></a>步骤 2： 设置 （或编辑） ATP 安全附件策略
  
1. 以全局管理员或 security 管理员程序中，转到[https://security.microsoft.com](https://security.microsoft.com)和使用工作或学校帐户登录。 
    
2. Office 365 安全性&amp;合规性中心在左侧的导航窗格中，**威胁管理**下面，选择**策略** \> **安全的附件**。
    
3. 如果您看到**打开 SharePoint、 OneDrive 和 Microsoft 团队 ATP**，我们建议您选择此选项。Office 365 环境，这将使[Office 365 高级威胁 Protection for SharePoint、 OneDrive 和 Microsoft 团队](atp-for-spo-odb-and-teams.md)。 
    
4. 选择**新建**(新建按钮图像类似一个加号 ( **+**)) 开始创建您的策略。
    
5. 指定名称、 说明和策略设置。<br/><br/>**示例：** 若要设置的策略名为"无延迟"立即传递每个人的邮件，然后重新附加附件，他们正在扫描后，您可能会指定以下设置： 
    
      - 在**名称**框中，键入任何延迟。
    
      - 在**说明**框中，键入类似，立即提供了邮件和重新附加附件扫描后的说明。
    
      - 在响应部分中，选择**动态传递**选项。（[了解更多关于动态交付和 ATP 安全附件预览](dynamic-delivery-and-previewing.md)。）
    
      - 在**重定向附件**部分中，选择启用重定向并键入您的 Office 365 全局管理员、 安全管理员或安全分析师，负责调查恶意附件的电子邮件地址的选项。 
    
      - 在**应用于**部分中，选择**收件人的域是**，，然后选择您的域。选择**添加**，然后选择**确定**。
    
6. 选择" **保存**"。
    
请考虑您的组织的多个 ATP 安全附件策略设置。将它们在**ATP 安全附件**上列出的顺序应用这些策略。已定义或编辑策略后，允许至少 30 分钟的策略生效整个 Microsoft 数据中心。 
  
## <a name="step-3-learn-about-atp-safe-attachments-policy-options"></a>第 3 步： 了解 ATP 安全附件策略选项

设置 ATP 安全附件策略时，将从多个选项，包括监视、 阻止、 Replace、 动态传递等选择。如果您想知道有关这些选项所执行的操作下, 表总结了每个和受到影响。
  
|**选项**|**效果**|**时要使用：**|
|:-----|:-----|:-----|
|**关** <br/> |不扫描附件的恶意软件  <br/> 不延迟邮件传递  <br/> |关闭扫描的内部发件人、 扫描程序、 传真或才会发送已知的良好的附件的智能主机  <br/> 阻止路由内部邮件中不必要的延迟  <br/> **不建议大多数用户使用此选项。使您可以关闭 ATP 安全附件扫描内部发件人一小组。**           |
|**监视器** <br/> |提供了带附件的邮件，然后跟踪与检测到恶意软件会发生什么情况  <br/> |请参阅您的组织中检测到恶意软件的位置  <br/> |
|**阻止** <br/> |阻止从继续检测到恶意软件附件的邮件  <br/> 将检测到恶意软件的邮件发送到[Office 365 中的隔离](manage-quarantined-messages-and-files.md)其中安全管理员或分析师可以查看和版本 （或删除） 这些消息  <br/> 自动阻止将来的邮件和附件  <br/> |保护您的组织中使用相同的恶意软件附件的重复攻击  <br/> |
|**替换** <br/> |删除检测到恶意软件的附件  <br/> 通知收件人的已删除附件  <br/> 将检测到恶意软件的邮件发送到[Office 365 中的隔离](manage-quarantined-messages-and-files.md)其中安全管理员或分析师可以查看和版本 （或删除） 这些消息  <br/> |提升到收件人的已删除由于检测到恶意软件的附件的可见性  <br/> |
|**动态传递** <br/> |立即发送的邮件  <br/> 替换附件是占位符文件之前扫描已完成，并且如果检测到没有恶意软件，然后重新附加附件  <br/> 包含附件预览功能对于大多数 Pdf 和 Office 在扫描过程中的文件  <br/> 将与检测到恶意软件的邮件发送到其中的安全管理员或分析师可以查看和版本 （或删除） 这些邮件隔离邮箱  <br/> [了解动态交付和 ATP 安全附件预览](dynamic-delivery-and-previewing.md) <br/> |避免同时从恶意文件保护收件人的邮件延迟  <br/> 启用收件人时扫描正在进行预览在安全模式下的附件  <br/> |
|**启用重定向** <br/> |适用时选择了监视、 阻止或替换选项  <br/> 发送到指定的电子邮件地址的附件安全管理员或分析师可以调查  <br/> |启用安全管理员和分析师研究可疑附件  <br/> |
   
## <a name="next-steps"></a>后续步骤

位置 ATP 安全附件策略后，您可以看到 ATP 通过查看报告的工作为您的组织。请参阅以下资源，以了解详细信息：
- [Office 365 高级威胁保护的视图报告](view-reports-for-atp.md)
- [在安全中使用资源管理器&amp;合规性中心](use-explorer-in-security-and-compliance.md)
 