---
title: 将 Office 365 威胁智能与 Windows Defender 高级威胁防护集成
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/22/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 414fa693-d7b7-4a1d-a387-ebc3b6a52889
description: 与 Windows Defender 高级威胁保护威胁管理的详细的信息，请参阅集成 Office 365 高级威胁保护。
ms.openlocfilehash: e5070e003972ae5308415dcdcca85b069d1163ac
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/11/2019
ms.locfileid: "29382535"
---
# <a name="integrate-office-365-threat-intelligence-with-windows-defender-advanced-threat-protection"></a>将 Office 365 威胁智能与 Windows Defender 高级威胁防护集成

如果您是组织的安全工作组的一部分，您可以与 Windows Defender 高级威胁保护集成 Office 365 高级威胁保护和威胁智能功能。这可以帮助您快速了解用户的计算机是否在风险时正在调查 Office 365 中的威胁。例如，启用集成后，您将能够列表，请参阅使用检测到的电子邮件的收件人的计算机以及如何在 Windows Defender 高级威胁保护中的多个最近的通知这些计算机具有。
  
下图显示**设备**选项卡，您将看到已启用 Windows Defender 高级威胁保护集成时： 
  
![启用 Windows Defender ATP 后，您可以看到计算机的通知的列表。](media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)
  
本示例中，您可以看到收件人的电子邮件有四个设备和一个具有一条通知。单击设备链接将在 Windows Defender 高级威胁保护门户中打开其页面。
  
## <a name="requirements"></a>要求

- 您的组织必须具有 Office 365 威胁智能和 Windows Defender ATP。
    
- 您必须是 Office 365 全局管理员或具有安全管理员角色 （如安全管理员） 中分配[安全&amp;合规性中心](https://protection.office.com)。(请参阅[Permissions in Office 365 安全性&amp;合规性中心](permissions-in-the-security-and-compliance-center.md))
    
- 您必须具有对 Office 365 威胁智能和 Windows Defender 高级威胁保护门户网站的访问。
    
## <a name="to-integrate-office-365-threat-intelligence-with-windows-defender-atp"></a>与 Windows Defender ATP 集成 Office 365 威胁智能

与 Windows Defender 高级威胁保护集成 Office 365 威胁智能设置使用这两个 Office 365 安全性 & 合规性中心和 Windows Defender 高级威胁保护门户。
  
1. 作为 Office 365 全局管理员或安全管理员，请转到[https://protection.office.com](https://protection.office.com)和使用 Office 365 您工作或学校的帐户登录。 
    
2. 选择**威胁管理** \> **资源管理器**。<br>![威胁管理菜单中的资源管理器](media/ThreatMgmt-Explorer-nav.png)<br>
    
3. 在屏幕的右上角，选择**WDATP 设置**。
    
4. 在 Windows Defender ATP 连接对话框中，打开连接到 Windows ATP。<br>![Windows Defender ATP 连接](media/Explorer-WDATPConnection-dialog.png)<br>
    
5. 启用 Windows Defender 高级威胁 Protection 中的连接。请参阅[Use Windows Defender 高级威胁保护门户](https://go.microsoft.com/fwlink/?linkid=859690)。

  
## <a name="related-topics"></a>相关主题

[Office 365 威胁智能](office-365-ti.md)
  
[Office 365 高级威胁防护](office-365-atp.md)
  

