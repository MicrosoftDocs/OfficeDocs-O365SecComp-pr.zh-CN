---
title: Office 365 服务加密
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 摘要： 了解 Microsoft Office 365 中的数据恢复能力。
ms.openlocfilehash: 1273cd5556bf51dcdac9bbde1b3e8003ab818811
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525407"
---
# <a name="office-365-service-encryption"></a>Office 365 服务加密

除了使用 Exchange Online 的音量级别加密的业务和 SharePoint Online 的 OneDrive for Business 的 Skype 还使用服务加密客户数据进行加密。加密服务允许两个关键管理选项：
- Microsoft 管理所有的加密密钥。（此选项是在 SharePoint Online、 OneDrive for Business 和 for Business 的 Skype 当前可用。它位于当前 Exchange Online 的路线图。）
- 客户提供用于服务加密的根键和客户管理使用 Azure 键存储库这些密钥。Microsoft 管理的其他所有项。此选项称为客户参数，并且当前可用于 Exchange Online、 SharePoint Online 和 OneDrive for Business。（以前称为与 BYOK 高级加密。请参阅[增强透明度和为 Office 365 客户的控件](http://blogs.office.com/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/)的原始通知）。

加密服务提供了多种优势。例如，它：
- 提供权限保护和管理功能在强的加密保护。
- 包括启用多租户服务以提供每个租户密钥管理客户参数选项。
- 提供分离的 Windows 操作系统管理员从 access 客户数据存储或处理的操作系统。
- 增强了 Office 365 能够满足客户具有有关加密的合规性要求。

## <a name="customer-key"></a>客户密钥
使用客户参数，您可以生成加密密钥使用本地 HSM 或 Azure 键存储库。如何生成密钥，无论客户使用 Azure 键仓库控制和管理 Office 365 使用的加密密钥。一旦您的密钥存储在 Azure 键电子仓库，他们可以分配给工作负荷，例如 Exchange Online 和 SharePoint Online 并用作钥匙链用于加密您的邮箱数据和文件的根目录。使用客户参数的其他好处之一是控制过程客户数据的 Microsoft 的能力。存在此功能，以便想要从 Office 365 （如时客户终止与 Microsoft 服务或删除存储在云中的数据的一部分） 中删除数据的客户可以这样和用作技术控制客户参数确保没有人包括 Microsoft，可以访问或处理数据。这是可用于控制对客户数据访问由 Microsoft 人员客户密码箱功能中添加 （和补充）。

若要了解如何为 Office 365 的客户参数设置为 Exchange Online，Skype 的业务和 SharePoint Online 的 OneDrive for Business，请参阅[控制您使用客户密钥的 Office 365 中的数据](https://support.office.com/article/Controlling-your-data-in-Office-365-using-Customer-Key-f2cd475a-e592-46cf-80a3-1bfb0fa17697)。其他信息，请参阅[Office 365 常见问题的客户参数](https://support.office.com/article/Customer-Key-for-Office-365-FAQ-41ae293a-bd5c-4083-acd8-e1a2b4329da6)，和[数据以帮助满足合规性管理和控制需要与客户参数](https://techcommunity.microsoft.com/t5/Microsoft-Ignite-Content-2017/Manage-and-control-your-data-to-help-meet-compliance-needs-with/td-p/117580)。
