---
title: 将 Office 365 威胁智能与 Windows Defender 高级威胁防护集成
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/22/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 414fa693-d7b7-4a1d-a387-ebc3b6a52889
ms.collection:
- M365-security-compliance
description: 将 Office 365 高级威胁防护与 Windows Defender 高级威胁防护集成, 以查看更详细的威胁管理信息。
ms.openlocfilehash: 892d04152d6029c48a52d37c6235d45a8ba67b81
ms.sourcegitcommit: a80bd8626720fabdf592b84e4424cd3a83d08280
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30222811"
---
# <a name="integrate-office-365-threat-intelligence-with-windows-defender-advanced-threat-protection"></a>将 Office 365 威胁智能与 Windows Defender 高级威胁防护集成

如果您是组织的安全团队的一部分, 则可以使用 Windows Defender 高级威胁防护将 Office 365 高级威胁防护和威胁智能功能集成在一起。这可以帮助您快速了解在调查 Office 365 中的威胁时用户的计算机是否存在风险。例如, 在启用集成后, 您将能够查看检测到的电子邮件的收件人使用的计算机列表, 以及这些计算机在 Windows Defender 高级威胁防护中的最近通知数。
  
下图显示了启用 Windows Defender 高级威胁防护集成时将看到的 "**设备**" 选项卡: 
  
![启用 Windows Defender ATP 后, 你可以查看包含警报的计算机列表。](media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)
  
在此示例中, 您可以看到电子邮件的收件人有四台设备, 并且有一个警报。单击设备的链接将在 Windows Defender 高级威胁防护门户中打开其页面。
  
## <a name="requirements"></a>要求

- 您的组织必须具有 Office 365 威胁智能和 Windows Defender ATP。
    
- 您必须是 Office 365 全局管理员或在[ &amp;安全合规中心](https://protection.office.com)中分配安全管理员角色 (例如安全管理员)。(请参阅[Office 365 安全&amp;合规中心中的权限](permissions-in-the-security-and-compliance-center.md))
    
- 您必须具有对 Office 365 威胁智能和 Windows Defender 高级威胁防护门户的访问权限。
    
## <a name="to-integrate-office-365-threat-intelligence-with-windows-defender-atp"></a>将 Office 365 威胁智能与 Windows Defender ATP 集成

通过使用 office 365 安全 & 合规中心和 windows defender 高级威胁防护门户, 将 office 365 威胁智能集成到 windows defender 高级威胁防护中。
  
1. 作为 office 365 全局管理员或安全管理员, 请转到[https://protection.office.com](https://protection.office.com)并使用 Office 365 的工作或学校帐户登录。 
    
2. 选择 "**威胁管理** \> **资源管理器**"。<br>![威胁管理菜单中的资源管理器](media/ThreatMgmt-Explorer-nav.png)<br>
    
3. 在屏幕的右上角, 选择 " **WDATP 设置**"。
    
4. 在 "Windows Defender ATP 连接" 对话框中, 启用 "连接到 Windows ATP"。<br>![Windows Defender ATP 连接](media/Explorer-WDATPConnection-dialog.png)<br>
    
5. 启用 Windows Defender 高级威胁防护中的连接。请参阅[使用 Windows Defender 高级威胁防护门户](https://go.microsoft.com/fwlink/?linkid=859690)。

  
## <a name="related-topics"></a>相关主题

[Office 365 威胁智能](office-365-ti.md)
  
[Office 365 高级威胁防护](office-365-atp.md)
  

