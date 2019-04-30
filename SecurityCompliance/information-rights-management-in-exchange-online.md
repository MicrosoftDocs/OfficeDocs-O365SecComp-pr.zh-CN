---
title: 使用 AD RMS 的 Exchange Online 邮件加密
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/13/2017
ms.audience: End User
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 2c956776-0016-4be6-b4cd-133a237f4a9e
description: 如果需要, 您可以将 Exchange Online IRM 配置为使用内部部署 Active Directory 权限管理服务 (AD RMS), 以满足您的组织的要求。 这并不常见。 如果您不需要使用 AD RMS, 请改用 Office 邮件加密。
ms.openlocfilehash: 423c6008a55539123b76225458a39c4f98e7725d
ms.sourcegitcommit: 696c1ed6b270be3f9da7395b49a7d8fec98e6db0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/29/2019
ms.locfileid: "33470382"
---
# <a name="exchange-online-mail-encryption-with-ad-rms"></a>使用 AD RMS 的 Exchange Online 邮件加密

为了帮助防止信息泄露，Exchange Online 的信息权限管理 (IRM) 功能可为电子邮件和附件提供联机和脱机保护。 如果需要, 您可以将 Exchange Online IRM 配置为使用内部部署 Active Directory 权限管理服务 (AD RMS), 以满足您的组织的要求。 这并不常见。 如果您不需要使用 AD RMS, 请改用[Office 邮件加密](ome.md)。 

IRM 保护可以由 Microsoft Outlook 或 web 上的 outlook 中的用户应用, 并且可以由使用传输保护规则或 outlook 保护规则的管理员应用。 IRM 可帮助您和您的用户控制谁可以访问、转发、打印或复制电子邮件中的敏感数据。
  
## <a name="changes-to-how-irm-works-with-office-365-message-encryption-ome-and-azure-active-directory"></a>对 Office 365 邮件加密 (OME) 和 Azure Active Directory 的 IRM 工作方式的更改

从9月 2017, 到为您的组织设置新的 Office 365 邮件加密功能时, 还可以设置 IRM 以用于 Azure 权限管理 (azure RMS)。 你不再使用 Azure RMS 单独设置 IRM。 相反, OME 和权限管理可以无缝地结合在一起。 有关新功能的更多详细信息, 请参阅[Office 365 邮件加密常见问题解答](https://support.office.com/article/0432dce9-d9b6-4e73-8a13-4a932eb0081e)。 如果你已准备好开始使用组织中的新 OME 功能, 请参阅[设置基于 Azure 信息保护基础构建的新 Office 365 邮件加密功能](https://support.office.com/article/7ff0c040-b25c-4378-9904-b1b50210d00e)。
  
## <a name="how-irm-works-with-exchange-online-and-active-directory-rights-management-services"></a>IRM 如何与 Exchange Online 和 Active Directory 权限管理服务配合使用

Exchange Online IRM 使用本地 Active Directory 权限管理服务 (AD RMS), 这是 Windows Server 2008 及更高版本中的一种信息保护技术。 通过将 AD RMS 权限策略模板应用于电子邮件，可将 IRM 保护应用于电子邮件。 权限附加到邮件本身, 以便在联机和脱机以及组织的防火墙内部和外部进行保护。
  
用户可以将模板应用于电子邮件, 以控制收件人对邮件的权限。 通过对邮件应用 AD RMS 权限策略，您可以控制转发、从邮件提取信息、保存邮件或打印邮件等操作。
  
您可以将 IRM 配置为使用运行 Windows server 2008 或更高版本的 AD RMS 服务器。 您可以使用此 AD RMS 服务器为基于云的组织管理 AD RMS 权限策略模板。 Outlook 还依靠 AD RMS 服务器来使用户可以向他们发送的邮件应用 IRM 保护。 有关详细信息, 请参阅[将 IRM 配置为使用本地 AD RMS 服务器](configure-irm-to-use-an-on-premises-ad-rms-server.md)。 
  
启用后，IRM 保护可以应用于邮件，如下所示：
  
- **用户可以使用 outlook 和 web 上的 outlook 手动应用模板。** 通过从 "**设置权限**" 列表中选择模板, 用户可以将 AD RMS 权限策略模板应用于电子邮件。 当用户发送受 IRM 保护的邮件时，任何使用支持格式的附加文件也会受到与邮件相同的 IRM 保护。 IRM 保护会应用于与 Word、Excel 和 PowerPoint 相关联的文件以及 .xps 文件和附加的电子邮件。 
    
- **管理员可以使用传输保护规则自动将 IRM 保护应用于 outlook 和 web 上的 outlook。** 您可以为 IRM 保护邮件创建传输保护规则。 将传输保护规则操作配置为将 AD RMS 权限策略模板应用于符合规则条件的邮件。 启用 IRM 之后, 您的组织的 AD RMS 权限策略模板可用于传输保护规则操作 (称为**将权限保护应用于邮件**)。
    
- **管理员可以创建 Outlook 保护规则。** outlook 保护规则根据邮件条件 (不包括发件人的部门) 自动将 IRM 保护应用于 outlook 2010 中的邮件, 将邮件发送到的收件人, 以及收件人是否在您的内部或外部组织. 有关详细信息，请参阅[Create an Outlook Protection Rule](http://technet.microsoft.com/library/da64750d-faaf-44de-ad8c-888eba7fbdbf.aspx)。
    

