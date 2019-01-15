---
title: Office 365 的 MDM 和 Microsoft Intune 之间进行选择
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 10/3/2017
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: c93d9ab9-efb2-4349-9b93-30c30562ee22
description: Microsoft Intune 和 Office 365 的内置移动设备管理使您能够管理组织中的移动设备。但有本主题中描述的主要区别。
ms.openlocfilehash: 553d401179f82b0f119f9e7d929b4af7d3df0c4a
ms.sourcegitcommit: 9034809b6f308bedc3b8ddcca8242586b5c30f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/15/2019
ms.locfileid: "28014734"
---
# <a name="choose-between-mdm-for-office-365-and-microsoft-intune"></a>Office 365 的 MDM 和 Microsoft Intune 之间进行选择

Microsoft Intune 和 Office 365 的内置移动设备管理使您能够管理组织中的移动设备。但有主要区别下, 表中所述。
  
> [!NOTE]
> 您可以管理用户和相同的 Office 365 租户中使用 Intune 和 Office 365 其移动设备。设置 Intune 和 MDM 允许您确定哪种解决方案最适用于特定的用户和其设备。如果您有两个可用的选项，您可以选择是否与您的 Office 365 或更多功能 Intune 解决方案管理 MDM 用户的设备。 
  
||||
|:-----|:-----|:-----|
|**功能区** <br/> |**MDM for Office 365** <br/> |**Microsoft Intune** <br/> |
|开销  <br/> |包含许多 Office 365 专业订阅。  <br/> |需要 Microsoft Intune 为付费的订阅，也可以与企业移动 Suite 购买。  <br/> |
|如何管理设备  <br/> |使用管理设备[Office 365 安全性&amp;合规性中心](https://protection.office.com)Office 365。  <br/> |如果您使用 Intune 本身，管理设备使用 Intune 管理控制台。  <br/> 如果您使用 System Center 2012 Configuration Manager 集成 Intune，您可以使用 Configuration Manager 控制台来管理设备在内部部署和云中。  <br/> |
|您可以管理的设备  <br/> |IOS、 Android，和 Windows 的基于云的管理设备  <br/> |基于云的管理适用于 iOS，Mac OS X、 Android，Windows 8.1 （电话和 PC） 和更高版本，以包括 Windows 10。 <br/> |
|主要功能  <br/> |帮助确保 Office 365 企业电子邮件和文档可以访问仅在手机和平板电脑由公司管理和在符合您的 IT 策略。  <br/> 设置和管理安全策略，如设备级别的 pin 锁定和 jailbreak 检测，以帮助防止未经授权的用户时丢失或被盗访问企业电子邮件和设备上的数据。  <br/> 同时就地保留其个人数据从员工的设备中删除 Office 365 公司数据。  <br/> [内置移动设备管理 Office 365 的功能](https://support.office.com/article/a1da44e5-7475-4992-be91-9ccec25905b0)中包含的详细信息。  <br/> |Office 365 功能的 MDM 加上：  <br/> 帮助安全地访问与证书、 Wi-fi、 VPN 和电子邮件配置文件的企业资源的用户。  <br/> 注册和管理企业拥有的设备，从而简化部署策略和应用程序的集合。  <br/> 向用户部署您的内部业务线应用程序和应用程序存储中。  <br/> 使用户可以更安全地访问公司使用移动 Office 的信息和业务应用程序行的他们知道，同时通过限制帮助确保数据的安全性操作类似于复制、 剪切，粘贴和存，这些 Intune 管理的相关应用程序。  <br/> 启用使用 Intune 托管浏览器应用程序的更安全 web 浏览。  <br/> 无需使用 Intune，基础结构与从云中管理 Pc 或连接到配置管理器以管理所有设备包括 Pc、 Mac、 Linux 和 UNIX 的 Intune 服务器和移动设备从一个管理控制台。  <br/> Intune 订阅还可以设置 MAM （移动应用程序管理） 策略通过使用 Azure 门户，即使不会加入 Intune 人的设备。请参阅[使用 MAM 策略保护应用程序数据](https://go.microsoft.com/fwlink/?LinkId=825439)。<br/> |


## <a name="related-topics"></a>相关主题
   
了解有关 Microsoft Intune 视频培训课程附带的[Microsoft 云服务： 管理 Office 365 和 Intune](https://support.office.com/article/c1224e20-3d49-4f40-99ee-fd0991880376.aspx)，进入您的 LinkedIn 学习。
  

