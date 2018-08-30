---
title: 设置 Office 365 企业版中的加密
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 4/2/2018
ms.audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e86fc991-0161-4f01-9c1c-d25e87733d06
description: 与 Office 365 中，某些加密功能已打开默认设置。可以配置其他功能，以满足特定合规性或法律要求。
ms.openlocfilehash: 80deced80283ac36d82ac15cee9af6d390c4749a
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525153"
---
# <a name="set-up-encryption-in-office-365-enterprise"></a>设置 Office 365 企业版中的加密

加密可以保护您的内容从正在读取未经授权的用户。由于可以完成[Office 365 中的加密](encryption.md)使用各种技术和方法，不存在的一个位置在打开或加密设置。本文提供了多种方法可设置或配置您的信息保护战略的一部分的加密信息。 
  
> [!TIP]
> 如果您要查找有关加密的更多技术详细信息，请参阅[Office 365 中的加密技术参考信息](technical-reference-details-about-encryption.md)。 
  
与 Office 365 几个加密功能是默认情况下可用。可以配置其他加密功能，以满足特定合规性或法律要求。下表介绍几种不同方案的加密方法。
  
|**方案**|**加密方法**|
|:-----|:-----|
|文件和网页保存在 Windows 的计算机上  <br/> |可在计算机级别的加密在 Windows 设备上使用 BitLocker。为企业管理员或 IT 专业人员，您可以设置此使用 Microsoft Deployment Toolkit (MDT)。请参阅[设置的 BitLocker MDT](https://go.microsoft.com/fwlink/?linkid=849282)。<br/> |
|文件和网页保存在移动设备上  <br/> |某些类型的移动设备加密文件的默认情况下保存到这些设备。与[Office 365 的内置移动设备管理功能](https://support.office.com/article/a1da44e5-7475-4992-be91-9ccec25905b0)，您可以设置确定是否允许移动设备访问 Office 365 中的数据的策略。例如，您可以设置允许仅加密内容访问 Office 365 数据的设备的策略。请参阅[创建和部署设备安全策略](https://support.office.com/article/d310f556-8bfb-497b-9bd7-fe3c36ea2fd6)。<br/> 其他控制如何移动设备进行交互与 Office 365 中，您可以考虑添加[Microsoft Intune](https://aka.ms/qzln04)。请参阅[Office 365 的 MDM 和 Microsoft Intune 之间进行选择](https://support.office.com/article/c93d9ab9-efb2-4349-9b93-30c30562ee22)。<br/> |
|您需要控制用于对您在 Microsoft 数据中心中的数据进行加密的加密密钥  <br/> | 作为 Office 365 管理员，您可以控制您的组织的加密密钥，然后配置 Office 365 使用它们在 Microsoft 数据中心中的 rest 数据进行加密。  <br/> [使用客户密钥控制 Office 365 中的数据](controlling-your-data-using-customer-key.md) <br/> [Office 365 常见问题的客户参数](service-encryption-with-customer-key-faq.md) <br/> |
|通过电子邮件 (Exchange Online) 进行通信的人员  <br/> | 作为 Exchange Online 管理员，您可以用于配置电子邮件加密的几个选项。这些工具包括：<br/>  使用 Azure 权限管理 (Azure RMS) 与[Office 365 邮件加密 (OME)](set-up-new-message-encryption-capabilities.md)使人们可以发送您的组织内外的加密的邮件  <br/>  使用[S/MIME 邮件签名和加密的](https://aka.ms/c6dozg)加密和数字签名的电子邮件  <br/>  [设置用于与其他组织的安全邮件流连接器](https://aka.ms/hs809p)使用 TLS <br/>  请参阅[Office 365 中的电子邮件加密](https://aka.ms/hic3f7)。  <br/> |
|文件访问工作组网站或文档库 (OneDrive for Business 或 SharePoint Online)  <br/> |时文件保存到 OneDrive for Business 或 SharePoint Online 工作人员，请使用 TLS 连接。这会自动内置到 Office 365。请参阅[OneDrive for Business 和 SharePoint Online 中的数据加密](https://go.microsoft.com/fwlink/?linkid=526379)。<br/> |
|文件共享中联机会议和 IM 对话 (Skype 业务 online)  <br/> |当用户使用的业务 online 使用 Skype 文件时，TLS 用于连接。这会自动内置到 Office 365。请参阅[安全性和存档 (Skype for Business Online)](https://aka.ms/nuq4ws)。<br/> |
   
## <a name="additional-information"></a>其他信息

若要了解有关文件保护解决方案，包括加密选项的详细信息，请参阅[Office 365 中的文件保护解决方案](https://www.microsoft.com/en-us/download/details.aspx?id=55523)。
  

