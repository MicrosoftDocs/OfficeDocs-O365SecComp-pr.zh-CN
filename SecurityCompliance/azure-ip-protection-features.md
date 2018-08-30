---
title: 在向现有 Office 365 租户推出的 Azure 信息保护保护功能
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/29/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 7ad6f58e-65d7-4c82-8e65-0b773666634d
description: 为了帮助保护您的信息，启动年 7 月 2018 Azure 信息保护符合条件的所有租户中的初始步骤将具有 Azure Information Protection 中的保护功能打开默认情况下。Azure Information Protection 中的保护功能已以前为权限管理或 Azure RMS 的 Office 365 中的名称。如果您的组织已 Office E3 服务计划或更高的服务计划将得到一个良好的开端保护信息通过 Azure 信息保护时推出这些功能。
ms.openlocfilehash: be0200da3032dccbcf54e67f3bdfbac800b65526
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525134"
---
# <a name="protection-features-in-azure-information-protection-rolling-out-to-existing-office-365-tenants"></a>在向现有 Office 365 租户推出的 Azure 信息保护保护功能

为了帮助保护您的信息，启动年 7 月 2018 Azure 信息保护符合条件的所有租户中的初始步骤将具有 Azure Information Protection 中的保护功能打开默认情况下。Azure Information Protection 中的保护功能已以前为权限管理或 Azure RMS 的 Office 365 中的名称。如果您的组织已 Office E3 服务计划或更高的服务计划将得到一个良好的开端保护信息通过 Azure 信息保护时推出这些功能。
  
## <a name="changes-beginning-july-1-2018"></a>开始 2018 年 7 月 1，更改

启动年 7 月 1 2018 Microsoft 将为具有以下订阅计划之一的所有 Office 365 租户启用 Azure Information Protection 中的保护功能：
  
- Office 365 邮件加密的 Office 365 E3 和 E5、 Microsoft E3 和 E5、 Office 365 A1，A3，和 A5 和 Office 365 G3 和 G5 一部分提供。不需要额外许可证接收由 Azure 信息保护的新保护功能。 
    
- 您还可以添加到以下 Azure 信息保护计划 1 计划收到新的 Office 365 邮件加密功能： Exchange Online 计划 1、 Exchange Online 计划 2、 Office 365 F1、 Office 365 业务 Essentials、 Office 365 企业高级版，或Office 365 企业版 E1。
    
- 受益于 Office 365 邮件加密的每个用户需要被许可功能覆盖。
    
- 完整列表请参阅为 Office 365 邮件加密的[Exchange Online 服务说明](https://technet.microsoft.com/library/exchange-online-service-description.aspx)。 
    
租户管理员可以检查 Office 365 管理门户中的保护状态。 
  
![显示已激活 Office 365 中的权限管理的屏幕截图。](media/303453c8-e4a5-4875-b49f-e80c3eb7b91e.png)
  
## <a name="why-are-we-making-this-change"></a>我们为什么要进行此更改？

Office 365 邮件加密利用 Azure Information Protection 中的保护功能。对 Office 365 邮件加密的最近改进和到 Microsoft 365 中的信息保护我们更广泛投资的核心，我们将从而方便组织打开和使用我们保护功能，为过去，加密技术已设置变得比较困难。通过打开默认情况下在 Azure 信息保护的保护功能，您可以快速开始来保护敏感数据。
  
## <a name="does-this-impact-me"></a>这会影响我？

如果您的 Office 365 组织购买合格的 Office 365 许可证，然后将受此更改影响您的租户。
  
 **重要说明 ！** 如果您的本地环境中使用 Active Directory Rights Management Services (AD RMS)，您必须退出此更改立即或之前我们推出此更改下一个 30 天内将迁移到 Azure 信息保护。有关如何以退出，请参阅本文后面的"使用 AD RMS，如何选择 out?"的信息。如果您希望迁移，请参阅[从 AD RMS 迁移到 Azure Information Protection。](https://docs.microsoft.com/azure/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)
  
## <a name="can-i-use-azure-information-protection-with-active-directory-rights-management-services-ad-rms"></a>可以使用 Active Directory Rights Management Services (AD RMS) 使用 Azure 信息保护？

不。这不是受支持的部署方案。不采用其他退出步骤，某些计算机可能会自动开始使用 Azure 权限管理服务和还连接到 AD RMS 群集。此方案中不受支持，并具有不可靠的结果，因此很重要退出之前推出这些新功能下一步的 30 天内此更改。有关如何以退出，请参阅本文后面的"使用 AD RMS，如何选择 out?"的信息。如果您希望迁移，请参阅[从 AD RMS 迁移到 Azure Information Protection。](https://docs.microsoft.com/azure/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)
  
## <a name="how-do-i-know-if-im-using-ad-rms"></a>如何知道是否我使用的 AD RMS？

使用以下说明从[准备 Azure 权限管理时还具有 Active Directory Rights Management Services (AD RMS) 的环境](https://docs.microsoft.com/azure/information-protection/deploy-use/prepare-environment-adrms)检查是否已部署 AD RMS: 
  
1. 可选的尽管大多数 AD RMS 部署发布到 Active Directory 服务连接点 (SCP)，以便域计算机可以发现 AD RMS 群集。 
  
使用 ADSI Edit 以查看是否必须在 Active Directory 中发布 SCP: CN = Configuration [服务器名称]，CN = Services、 CN = RightsManagementServices，CN = SCP
    
2. 如果您不使用 SCP，必须使用 Windows 注册表配置客户端服务发现或许可重定向连接到 AD RMS 群集的 Windows 计算机： HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\ServiceLocation 或 HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\MSIPC\ServiceLocation 
  
有关这些注册表配置的详细信息，请参阅[使用 Windows 注册表启用客户端服务发现](https://docs.microsoft.com/azure/information-protection/rms-client/client-deployment-notes#enabling-client-side-service-discovery-by-using-the-windows-registry)和[重定向授权服务器的通信](https://docs.microsoft.com/azure/information-protection/rms-client/client-deployment-notes#redirecting-licensing-server-traffic)。
    
## <a name="i-use-ad-rms-how-do-i-opt-out"></a>使用 AD RMS 如何执行我退出？

若要选择退出即将发布的更改，请完成以下步骤：
  
1. 使用 Office 365 组织中具有全局管理员权限的工作或学校帐户，请启动 Windows PowerShell 会话并连接到 Exchange Online。有关说明，请参阅[Connect to Exchange Online PowerShell 中](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)。
    
2. 运行 Set-irmconfiguration cmdlet 使用以下语法：
    
  ```
  Set-IRMConfiguration -AutomaticServiceUpdateEnabled $false 
  ```

## <a name="what-can-i-expect-after-this-change-has-been-made"></a>可以什么预期后已进行此更改？

一旦启用此，前提是您没有选择，您可以开始使用新版本的 Office 365 邮件加密的已发布在[Microsoft Ignite 2017](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Email-Encryption-and-Rights-Protection/ba-p/110801)和利用 Azure 信息的加密和保护功能保护。 
  
![显示 OME 的屏幕截图保护 web 上的 Outlook 电子邮件中。](media/599ca9e7-c05a-429e-ae8d-359f1291a3d8.png)
  
有关新的增强功能的详细信息，请参阅[Office 365 邮件加密](ome.md)。
  

