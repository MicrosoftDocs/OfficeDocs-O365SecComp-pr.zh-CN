---
title: Exchange Online 中的信息权限管理
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/13/2017
ms.audience: End User
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 2c956776-0016-4be6-b4cd-133a237f4a9e
description: 人们经常使用电子邮件来交换敏感信息，例如财务数据、法律合同、机密产品信息、销售报表和预测、患者健康信息或客户和员工信息。因此，邮箱可能会成为一个包含大量潜在敏感信息的存储库，信息泄露可能会成为您组织的严重威胁。
ms.openlocfilehash: de3bc22075a4a0f5e81fddece4c7ff3a54b22382
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2018
ms.locfileid: "22027229"
---
# <a name="information-rights-management-in-exchange-online"></a>Exchange Online 中的信息权限管理

人们经常使用电子邮件来交换敏感信息，例如财务数据、法律合同、机密产品信息、销售报表和预测、患者健康信息或客户和员工信息。因此，邮箱可能会成为一个包含大量潜在敏感信息的存储库，信息泄露可能会成为您组织的严重威胁。
  
为了帮助防止信息泄露，Exchange Online 包括信息权限管理 (IRM) 功能，提供的电子邮件和附件的联机和脱机保护。通过 Microsoft Outlook 或 Outlook web 上的用户可以应用 IRM 保护并可由管理员使用传输保护规则或 Outlook 保护规则。IRM 有助于您和您用户控制哪些人可以访问、 转发、 打印或复制电子邮件中的敏感数据。
  
## <a name="changes-to-how-irm-works-with-office-365-message-encryption-ome-and-azure-active-directory"></a>对 IRM 方式与 Office 365 邮件加密 (OME) 和 Azure Active Directory 更改

从年 9 月 2017，当您设置新的 Office 365 邮件加密功能为您的组织，您还设置 IRM 与 Azure 权限管理 (Azure RMS) 一起使用。您不再与 Azure RMS 的 IRM 分别设置。而是 OME 和权限管理都将无缝协同工作。有关新功能的详细信息，请参阅[Office 365 邮件加密 FAQ](https://support.office.com/article/0432dce9-d9b6-4e73-8a13-4a932eb0081e)。如果您已准备好开始使用您的组织中的新 OME 功能，请参阅[设置新的 Office 365 邮件加密功能构建到 Azure 信息保护的顶部](https://support.office.com/article/7ff0c040-b25c-4378-9904-b1b50210d00e)。
  
## <a name="how-irm-works-with-exchange-online-and-active-directory-rights-management-services"></a>IRM 方式与 Exchange Online 和 Active Directory Rights Management Services

Exchange Online IRM 使用内部部署 Active Directory Rights Management Services (AD RMS)，在 Windows Server 2008 及更高版本信息保护技术。通过将 AD RMS 权限策略模板应用于电子邮件到电子邮件应用 IRM 保护。权限附加到邮件本身，以便保护发生联机和脱机和内部和外部组织的防火墙。
  
用户可以应用于电子邮件控制收件人对一条消息的权限模板。可以通过将 AD RMS 权限策略应用到邮件控制操作，如转接、 从邮件中提取信息、 保存一条消息，或打印一条消息。
  
您可以配置 IRM 以使用 AD RMS 服务器运行 Windows Server 2008 或更高版本。此 AD RMS 服务器可用于管理基于云的组织的 AD RMS 权限策略模板。Outlook 还依靠 AD RMS 服务器，以使用户能够向他们发送的邮件应用 IRM 保护。有关详细信息，请参阅[配置 IRM 以使用内部部署 AD RMS 服务器](configure-irm-to-use-an-on-premises-ad-rms-server.md)。 
  
启用后，IRM 保护可以应用于邮件，如下所示：
  
- **用户可以手动应用使用 Outlook 和 Outlook web 上的模板。** 用户可以通过从**设置权限**列表中选择模板至的电子邮件应用 AD RMS 权限策略模板。当用户发送受 IRM 保护的邮件时，使用受支持的格式的任何附加的文件还会收到邮件的相同 IRM 保护。IRM 保护应用于 Word、 Excel 和 PowerPoint，以及.xps 文件和附加的电子邮件与关联的文件。 
    
- **管理员可以使用传输保护规则 Outlook 和 Outlook web 上的自动应用 IRM 保护。** 您可以创建 IRM 保护的邮件传输保护规则。配置将 AD RMS 权限策略模板应用于邮件满足该规则条件的传输保护规则操作。启用 IRM 后，可供使用与传输保护规则操作调用**应用于邮件的权限保护**组织的 AD RMS 权限策略模板。
    
- **管理员可创建 Outlook 保护规则。** Outlook 保护规则自动根据邮件条件包含发件人的部门，邮件发送给，用户在 Outlook 2010 中 (不在 web 上的 Outlook) 的邮件应用 IRM 保护和内部或外部收件人是否您组织。有关详细信息，请参阅[Create Outlook 保护规则](http://technet.microsoft.com/library/da64750d-faaf-44de-ad8c-888eba7fbdbf.aspx)。
    

