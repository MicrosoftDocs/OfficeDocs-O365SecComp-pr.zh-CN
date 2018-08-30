---
title: 疑难解答信息和支持信息
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 5d9f75f5-bb7f-458c-ad30-5c8eae0b0e4e
description: 本主题介绍了针对最终用户和管理员的疑难解答步骤，并提供了有关如何联系技术支持以寻求帮助的信息。
ms.openlocfilehash: 249f6fabf0ae7037ef905c455cfb45582be0e40b
ms.sourcegitcommit: e9dca2d6a7838f98bb7eca127fdda2372cda402c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2018
ms.locfileid: "23003121"
---
# <a name="troubleshooting-and-support-information"></a>疑难解答信息和支持信息

本主题介绍了针对最终用户和管理员的疑难解答步骤，并提供了有关如何联系技术支持以寻求帮助的信息。
  
## <a name="troubleshooting-for-users"></a>用户的疑难解答

有时，您的 Microsoft Office Outlook 在添加垃圾邮件报告插件之后可能出现故障。以下是您可能遇到的问题以及解决这些问题的提示。 
  
- 单击**报告垃圾邮件**时没有响应
    
- 当您选择一封电子邮件之后，Outlook 停止响应
    
- 由于收到"未送达"回复，报告的垃圾邮件无法传递
    
### <a name="troubleshooting-tip"></a>疑难解答提示

1. 关闭并重启 Microsoft Office Outlook。
    
2. 验证您是否能够创建和发送测试邮件。要执行此操作，您可以发送一封测试邮件到另一个您负责的电子帐户，然后验证是否收到该电子邮件。
    
如果问题仍然存在，请与 IT 管理员联系。
  
> [!TIP]
> 您还可以使用[not_junk@office365.microsoft.com](mailto: not_junk@office365.microsoft.com)电子邮件地址提交垃圾邮件直接向 Microsoft 使用[junk@office365.microsoft.com](mailto:junk@office365.microsoft.com)电子邮件地址和误报邮件。有关详细信息，请参阅[提交垃圾邮件和非垃圾邮件和网络钓鱼诈骗邮件提交给 Microsoft 进行分析](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)。 
  
## <a name="troubleshooting-for-administrators"></a>管理员的疑难解答

作为管理员，您可能遇到关于用户使用 Microsoft Office Outlook 的垃圾邮件报告加载项的问题。以下是解决您可能遇到的问题的提示。 
  
 **问题：** 不断出现要求用户联系系统管理员的错误消息。 
  
### <a name="troubleshooting-tip"></a>疑难解答提示

1. 设置以下注册表项的值为"详细"：
    
  - **32 位操作系统上安装的 32 位 Outlook：**
    
    HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Junk Email Reporting\Addins\LoggingLevel
    
  - **64 位操作系统上安装的 32 位 Outlook：**
    
    HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Junk Email Reporting\Addins\LoggingLevel
    
  - **64 位 Outlook（通常安装在 64 位操作系统上）：**
    
    HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Junk Email Reporting\Addins\LoggingLevel
    
2. 重启 Microsoft Office Outlook 并要求用户在看到错误信息时回报。
    
3. 收集在以下位置找到的日志信息： 
    
    %LOCALAPPDATA%\Microsoft\Junk Email Reporting Add-in\SpamReporterAddinLog.txt
    
4. 联系 Exchange Online Protection 技术支持并向他们提供日志信息。 
    
 **问题：** 在将电子邮件提交为垃圾邮件时，用户选择不接收确认邮件，但现在他们想要返回选择该选项。 
  
### <a name="troubleshooting-tip"></a>疑难解答提示

1. 设置以下注册表项的值为"True"：HKEY_CURRENT_USER\Software\Microsoft\Junk E-mail Reporting\Preferences\ConfirmReportJunk
    
2. 重启 Microsoft Office Outlook。
    
## <a name="support-information"></a>支持信息

如果您需要安装的帮助，配置或卸载外接程序，请联系技术支持在 Office 365 管理中心的支持页上使用新建服务请求链接。包括提交服务请求通过电话和自助支持选项的其他选项，请参阅[帮助和支持 eop](eop/help-and-support-for-eop.md)。
  
## <a name="for-more-information"></a>详细信息

[启用报告消息加载项](https://support.office.com/article/4250c4bc-6102-420b-9e0a-a95064837676)
  
[向 Microsoft 报告垃圾邮件](report-junk-email-messages-to-microsoft.md)
  

