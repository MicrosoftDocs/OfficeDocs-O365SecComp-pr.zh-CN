---
title: 将 IRM 配置为使用本地 AD RMS 服务器
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/13/2017
ms.audience: End User
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 3ecde857-4b7c-451d-b4aa-9eeffc8a8c61
description: 本主题显示了如何将 IRM 配置为使用 AD RMS 服务器。
ms.openlocfilehash: 82eed73797cfb4ade04bfeed9118d8466c5c5480
ms.sourcegitcommit: e9dca2d6a7838f98bb7eca127fdda2372cda402c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2018
ms.locfileid: "23002780"
---
# <a name="configure-irm-to-use-an-on-premises-ad-rms-server"></a>将 IRM 配置为使用本地 AD RMS 服务器
  
用于本地部署，Exchange Online 中的信息权限管理 (IRM) 使用 Active Directory Rights Management Services (AD RMS)，在 Windows Server 2008 及更高版本信息保护技术。通过将 AD RMS 权限策略模板应用于电子邮件到电子邮件应用 IRM 保护。权限附加到邮件本身，以便保护发生联机和脱机和内部和外部组织的防火墙。
  
本主题演示如何 IRM 配置为使用 AD RMS 服务器。有关使用的 Azure Active Directory 与 Azure 权限管理的 Office 365 邮件加密的新功能的信息，请参阅[Office 365 邮件加密 FAQ](https://support.office.com/article/0432dce9-d9b6-4e73-8a13-4a932eb0081e)。
  
有关 Exchange Online 中 IRM 的详细信息，请参阅[Exchange Online 中的信息权限管理](information-rights-management-in-exchange-online.md)。
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>在开始之前，您需要知道什么？
<a name="sectionSection0"> </a>

- 估计完成该任务的时间：30 分钟
    
- 您必须先获得权限，然后才能执行此过程或多个过程。若要查看所需的权限，请参阅 [Messaging policy and compliance permissions](http://technet.microsoft.com/library/ec4d3b9f-b85a-4cb9-95f5-6fc149c3899b.aspx)主题中的"信息权限管理"条目。 
    
- AD RMS 服务器必须运行 Windows Server 2008 或更高版本。有关如何部署 AD RMS 的详细信息，请参阅[安装 AD RMS 群集](https://go.microsoft.com/fwlink/?LinkId=210873)。
    
- 有关如何安装和配置 Windows PowerShell 以及连接到服务的详细信息，请参阅[使用远程 PowerShell 连接到 Exchange Online](http://technet.microsoft.com/library/c8bea338-6c1a-4bdf-8de0-7895d427ee5b.aspx)。
    
- 若要了解可能适用于此主题中过程的键盘快捷键，请参阅 **Exchange 管理中心内的键盘快捷键**。
    
> [!TIP]
> 遇到问题了吗？请在 Exchange 论坛中寻求帮助。 请访问以下论坛：[Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612)、[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542)或 [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351)。 
  
## <a name="how-do-you-do-this"></a>您该如何做？
<a name="sectionSection1"> </a>

### <a name="step-1-use-the-ad-rms-console-to-export-a-trusted-publishing-domain-tpd-from-an-ad-rms-server"></a>步骤 1：使用 AD RMS 控制台从 AD RMS 服务器导出受信任发布域 (TPD)

第一步是从内部部署 AD RMS 服务器将受信任发布域 (TPD) 导出到 XML 文件。TPD 包含以下使用 RMS 功能所需的设置： 
  
- 用于对证书和许可证进行签名和加密的服务器许可方证书 (SLC)
    
- 用于许可和发布的 URL
    
- 使用该 TPD 的特定 SLC 创建的 AD RMS 权限策略模板
    
导入 TPD 时，它在 Exchange Online 中进行存储并受保护。
  
1. 打开 Active Directory Rights Management Services 控制台，然后展开 AD RMS 群集。
    
2. 在控制台树中，展开**信任策略**，然后单击**受信任发布域**。
    
3. 在结果窗格中，选择要导出的域的证书。
    
4. 在**操作**窗格中，单击**导出受信任的发布域**。
    
5. 在**发布域文件**框中，单击**另存为**文件保存到本地计算机上的特定位置。键入文件名，并确保指定`.xml`文件扩展名，然后单击**保存**。
    
6. 在**密码**和**确认密码**框中，键入将用于加密的受信任的发布域文件的强密码。您将需要向基于云的电子邮件组织导入 TPD 时指定此密码。 
    
### <a name="step-2-use-the-exchange-management-shell-to-import-the-tpd-to-exchange-online"></a>步骤 2：使用 Exchange 命令行管理程序 将 TPD 导入到 Exchange Online

TPD 导出到 XML 文件后，您必须将其导入到 Exchange Online。导入 TPD 时，还会导入您的组织的 AD RMS 模板。导入第一个 TPD 时，它将成为默认 TPD 为您的基于云的组织。如果另一个 TPD 导入，您可以使用**默认**开关以使其对用户可用的 TPD 的默认。 
  
若要导入 TPD，请在 Windows PowerShell 中运行以下命令：
  
```
Import-RMSTrustedPublishingDomain -FileData $([byte[]](Get-Content -Encoding byte -Path <path to exported TPD file> -ReadCount 0)) -Name "<name of TPD>" -ExtranetLicensingUrl <URL> -IntranetLicensingUrl <URL>
```

您可在 Active Directory Rights Management Services 控制台中获取  _ExtranetLicensingUrl_ 和  _IntranetLicensingUrl_ 参数的值。在控制台树中选择 AD RMS 群集。许可 URL 显示在结果窗格中。当必须对内容进行解密时以及 Exchange Online 需要确定要使用的 TPD 时，电子邮件客户端会使用这些 URL。 
  
当运行此命令时，系统会提示您输入密码。输入您在从 AD RMS 服务器导出 TPD 时指定的密码。
  
例如，以下命令使用您从 AD RMS 服务器导出并保存到管理员帐户桌面的 XML 文件来导入名为 Exported TPD 的 TPD。Name 参数用于为 TPD 指定名称。
  
```
Import-RMSTrustedPublishingDomain -FileData $([byte[]](Get-Content -Encoding byte -Path C:\Users\Administrator\Desktop\ExportTPD.xml -ReadCount 0)) -Name "Exported TPD" -ExtranetLicensingUrl https://corp.contoso.com/_wmcs/licensing -IntranetLicensingUrl https://rmsserver/_wmcs/licensing
```

有关语法和参数的详细信息，请参阅 [Import-RMSTrustedPublishingDomain](http://technet.microsoft.com/library/7c5e7a0f-9c9d-4863-bab8-bcc729cc16a6.aspx)。
  
#### <a name="how-do-you-know-this-step-worked"></a>您如何知道此步骤有效？

若要验证已成功导入 TPD，运行 Exchange Online 组织中检索 TPDs **Get RMSTrustedPublishingDomain** cmdlet。有关详细信息，请参阅[Get RMSTrustedPublishingDomain](http://technet.microsoft.com/library/69499195-f08f-41bd-b0ed-443688410b12.aspx)中的示例。
  
### <a name="step-3-use-the-exchange-management-shell-to-distribute-an-ad-rms-rights-policy-template"></a>步骤 3：使用 Exchange 命令行管理程序 来分发 AD RMS 权限策略模板

导入 TPD 之后，必须确保已分发 AD RMS 权限策略模板。分发的模板对 Outlook Web App 用户可见，这些用户随后可将模板应用于电子邮件。
  
若要返回默认 TPD 中包含的所有模板的列表，请运行以下命令：
  
```
Get-RMSTemplate -Type All | fl
```

如果  _Type_ 参数的值为  `Archived`，则模板对用户不可见。只有默认 TPD 中的已分发模板才在 Outlook Web App 中可见。
  
若要分发模板，请运行以下命令：
  
```
Set-RMSTemplate -Identity "<name of the template>" -Type Distributed
```

例如，以下命令导入 Company Confidential 模板。
  
```
Set-RMSTemplate -Identity "Company Confidential" -Type Distributed
```

有关语法和参数的详细信息，请参阅 [Get-RMSTemplate](http://technet.microsoft.com/library/4a5066e8-b770-4aa2-b464-0d2190914f71.aspx) 和 [Set-RMSTemplate](http://technet.microsoft.com/library/4637f6b8-751a-4f5e-8869-428250230382.aspx)。
  
 **"不要转发"模板**
  
从内部部署组织到 Exchange Online 导入默认 TPD 时，导入名为**不要转发**的一个 AD RMS 权限策略模板。默认情况下导入默认 TPD 时分布此模板。不能使用**Set-rmstemplate** cmdlet 修改**不要转发**模板。 
  
**不要转发**模板应用于一条消息时, 仅在邮件中解决收件人可以阅读邮件。此外，收件人不能执行以下操作： 
  
- 将邮件转发给其他人。
    
- 复制邮件的内容。
    
- 打印邮件。
    
> [!IMPORTANT]
> **不要转发**模板无法阻止邮件中的信息与第三方屏幕捕获程序、 照相机或手动抄录信息的用户复制 
  
您可在内部部署组织中的 AD RMS 服务器上创建其他 AD RMS 权限策略模板，以满足 IRM 保护要求。如果创建其他 AD RMS 权限策略模板，则必须再次从内部部署 AD RMS 服务器导出 TPD，并刷新基于云的电子邮件组织中的 TPD。 
  
#### <a name="how-do-you-know-this-step-worked"></a>您如何知道此步骤有效？

若要验证是否已成功分发和 AD RMS 权限策略模板，运行**Get-rmstemplate** cmdlet 来检查该模板的属性。有关详细信息，请参阅[Get-rmstemplate](http://technet.microsoft.com/library/4a5066e8-b770-4aa2-b464-0d2190914f71.aspx)中的示例。
  
### <a name="step-4-use-the-exchange-management-shell-to-enable-irm"></a>步骤 4：使用 Exchange 命令行管理程序 启用 IRM

导入 TPD 并分发 AD RMS 权限策略模板之后，请运行以下命令来为基于云的电子邮件组织启用 IRM。
  
```
Set-IRMConfiguration -InternalLicensingEnabled $true
```

有关语法和参数的详细信息，请参阅 [Set-IRMConfiguration](http://technet.microsoft.com/library/5df0b56a-7bcc-4be2-b4b8-4de16720476c.aspx)。
  
#### <a name="how-do-you-know-this-step-worked"></a>您如何知道此步骤有效？

若要验证是否已成功启用 IRM，请运行 [Get-IRMConfiguration](http://technet.microsoft.com/library/e1821219-fe18-4642-a9c2-58eb0aadd61a.aspx) cmdlet 来检查 Exchange Online 组织中的 IRM 配置。 
  
## <a name="how-do-you-know-this-task-worked"></a>您如何知道此任务有效？
<a name="sectionSection2"> </a>

若要验证是否已成功导入 TPD 并启用 IRM，执行以下操作：
  
- 使用**Test-irmconfiguration** cmdlet 可以测试 IRM 功能。有关详细信息，请参阅[Test-irmconfiguration](http://technet.microsoft.com/library/a730e7ff-a67f-4360-b5ff-70d171bb5e1d.aspx)中的"示例 1"。
    
- 撰写新邮件中 Outlook Web App 和 IRM 保护其通过选择**设置的权限**选项从扩展菜单 (![更多选项图标](media/ITPro-EAC-MoreOptionsIcon.gif))。
    

