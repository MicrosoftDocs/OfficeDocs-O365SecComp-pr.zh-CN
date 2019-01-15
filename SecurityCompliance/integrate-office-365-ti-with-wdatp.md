---
title: 将 Office 365 威胁智能与 Windows Defender 高级威胁防护集成
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 3/21/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 414fa693-d7b7-4a1d-a387-ebc3b6a52889
description: 与 Windows Defender 高级威胁保护威胁管理的详细的信息，请参阅集成 Office 365 高级威胁保护。
ms.openlocfilehash: 48e879c1d41b5aa662f5128e234be91eb8225e7b
ms.sourcegitcommit: 9034809b6f308bedc3b8ddcca8242586b5c30f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/15/2019
ms.locfileid: "28014764"
---
# <a name="integrate-office-365-threat-intelligence-with-windows-defender-advanced-threat-protection"></a>将 Office 365 威胁智能与 Windows Defender 高级威胁防护集成

如果您是组织的安全工作组的一部分，您可以将 Office 365 集成与 Windows Defender 高级威胁保护 (ATP)。这可以帮助您快速了解用户的计算机是否在风险时正在调查 Office 365 中的威胁。例如，启用集成后，您将能够列表，请参阅使用检测到的电子邮件的收件人的计算机以及如何在 Windows Defender ATP 中的多个最近的通知这些计算机具有。
  
下图显示**设备**选项卡，您将看到已启用 Windows Defender ATP 集成时： 
  
![启用 Windows Defender ATP 后，您可以看到计算机的通知的列表。](media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)
  
本示例中，您可以看到收件人的电子邮件有四个计算机和一个 Windows Defender ATP 中有一条通知。单击指向计算机的链接计算机页中打开 Windows Defender ATP 新选项卡。
  
## <a name="requirements"></a>要求

- 您的组织必须具有 Office 365 威胁智能和 Windows Defender ATP。
    
- 您必须是 Office 365 全局管理员或具有安全管理员角色中分配[安全&amp;合规性中心](https://protection.office.com)。(请参阅[Permissions in Office 365 安全性&amp;合规性中心](permissions-in-the-security-and-compliance-center.md))
    
- 您必须具有对 Office 365 威胁智能和 Windows Defender ATP 门户网站的访问。
    
## <a name="to-integrate-office-365-threat-intelligence-with-windows-defender-atp"></a>与 Windows Defender ATP 集成 Office 365 威胁智能

在 Office 365 和 Windows Defender ATP 门户中与 Windows Defender ATP 集成 Office 365 威胁智能是设置。
  
1. 作为 Office 365 全局或安全管理员，请转到[https://protection.office.com](https://protection.office.com)和使用 Office 365 您工作或学校的帐户登录。 
    
2. 选择**威胁管理** \> **威胁资源管理器**。
    
3. 在**详细**菜单中，选择**WDATP 设置**。
    
4. 选择**连接到 Windows ATP**。
    
当您更改在 Office 365 中的设置后，必须启用从 Windows Defender ATP 的连接。为此，请参阅[Use Windows Defender 高级威胁保护门户](https://go.microsoft.com/fwlink/?linkid=859690)。
  
## <a name="related-topics"></a>相关主题

[Office 365 威胁智能](office-365-ti.md)
  
[Office 365 高级威胁防护](office-365-atp.md)
  

