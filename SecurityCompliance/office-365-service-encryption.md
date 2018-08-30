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
# <a name="office-365-service-encryption"></a><span data-ttu-id="92071-103">Office 365 服务加密</span><span class="sxs-lookup"><span data-stu-id="92071-103">Office 365 Service Encryption</span></span>

<span data-ttu-id="92071-p101">除了使用 Exchange Online 的音量级别加密的业务和 SharePoint Online 的 OneDrive for Business 的 Skype 还使用服务加密客户数据进行加密。加密服务允许两个关键管理选项：</span><span class="sxs-lookup"><span data-stu-id="92071-p101">In addition to using volume-level encryption, Exchange Online, Skype for Business, SharePoint Online, and OneDrive for Business also use Service Encryption to encrypt customer data. Service Encryption allows for two key management options:</span></span>
- <span data-ttu-id="92071-p102">Microsoft 管理所有的加密密钥。（此选项是在 SharePoint Online、 OneDrive for Business 和 for Business 的 Skype 当前可用。它位于当前 Exchange Online 的路线图。）</span><span class="sxs-lookup"><span data-stu-id="92071-p102">Microsoft manages all cryptographic keys. (This option is currently available in SharePoint Online, OneDrive for Business, and Skype for Business. It is currently on the roadmap for Exchange Online.)</span></span>
- <span data-ttu-id="92071-p103">客户提供用于服务加密的根键和客户管理使用 Azure 键存储库这些密钥。Microsoft 管理的其他所有项。此选项称为客户参数，并且当前可用于 Exchange Online、 SharePoint Online 和 OneDrive for Business。（以前称为与 BYOK 高级加密。请参阅[增强透明度和为 Office 365 客户的控件](http://blogs.office.com/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/)的原始通知）。</span><span class="sxs-lookup"><span data-stu-id="92071-p103">The customer supplies root keys used with service encryption and the customer manages these keys using Azure Key Vault. Microsoft manages all other keys. This option is called Customer Key, and it is currently available for Exchange Online, SharePoint Online, and OneDrive for Business. (Previously referred to as Advanced Encryption with BYOK. See [Enhancing transparency and control for Office 365 customers](http://blogs.office.com/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/) for the original announcement.)</span></span>

<span data-ttu-id="92071-p104">加密服务提供了多种优势。例如，它：</span><span class="sxs-lookup"><span data-stu-id="92071-p104">Service encryption provides multiple benefits. For example, it:</span></span>
- <span data-ttu-id="92071-116">提供权限保护和管理功能在强的加密保护。</span><span class="sxs-lookup"><span data-stu-id="92071-116">provides rights protection and management features on top of strong encryption protection.</span></span>
- <span data-ttu-id="92071-117">包括启用多租户服务以提供每个租户密钥管理客户参数选项。</span><span class="sxs-lookup"><span data-stu-id="92071-117">includes a Customer Key option that enables multi-tenant services to provide per-tenant key management.</span></span>
- <span data-ttu-id="92071-118">提供分离的 Windows 操作系统管理员从 access 客户数据存储或处理的操作系统。</span><span class="sxs-lookup"><span data-stu-id="92071-118">provides separation of Windows operating system administrators from access to customer data stored or processed by the operating system.</span></span>
- <span data-ttu-id="92071-119">增强了 Office 365 能够满足客户具有有关加密的合规性要求。</span><span class="sxs-lookup"><span data-stu-id="92071-119">enhances the ability of Office 365 to meet the demands of customers that have compliance requirements regarding encryption.</span></span>

## <a name="customer-key"></a><span data-ttu-id="92071-120">客户密钥</span><span class="sxs-lookup"><span data-stu-id="92071-120">Customer Key</span></span>
<span data-ttu-id="92071-p105">使用客户参数，您可以生成加密密钥使用本地 HSM 或 Azure 键存储库。如何生成密钥，无论客户使用 Azure 键仓库控制和管理 Office 365 使用的加密密钥。一旦您的密钥存储在 Azure 键电子仓库，他们可以分配给工作负荷，例如 Exchange Online 和 SharePoint Online 并用作钥匙链用于加密您的邮箱数据和文件的根目录。使用客户参数的其他好处之一是控制过程客户数据的 Microsoft 的能力。存在此功能，以便想要从 Office 365 （如时客户终止与 Microsoft 服务或删除存储在云中的数据的一部分） 中删除数据的客户可以这样和用作技术控制客户参数确保没有人包括 Microsoft，可以访问或处理数据。这是可用于控制对客户数据访问由 Microsoft 人员客户密码箱功能中添加 （和补充）。</span><span class="sxs-lookup"><span data-stu-id="92071-p105">Using Customer Key, you can generate your own cryptographic keys using either an on-premises HSM or Azure Key Vault. Regardless of how the key is generated, customers use Azure Key Vault to control and manage the cryptographic keys used by Office 365. Once your keys are stored in Azure Key Vault, they can be assigned to workloads such as Exchange Online and SharePoint Online and used to as the root of the keychain used to encrypt your mailbox data and files. One of the other benefits of using Customer Key is to control the ability of Microsoft to process customer data. This capability exists so that a customer that wants to remove data from Office 365 (such as when a customer terminates service with Microsoft or removes a portion of data stored in the cloud) can do so and use Customer Key as a technical control to ensure that no one, including Microsoft, can access or process the data. This is in addition (and a complement) to the Customer Lockbox feature that can be used to control access to customer data by Microsoft personnel.</span></span>

<span data-ttu-id="92071-p106">若要了解如何为 Office 365 的客户参数设置为 Exchange Online，Skype 的业务和 SharePoint Online 的 OneDrive for Business，请参阅[控制您使用客户密钥的 Office 365 中的数据](https://support.office.com/article/Controlling-your-data-in-Office-365-using-Customer-Key-f2cd475a-e592-46cf-80a3-1bfb0fa17697)。其他信息，请参阅[Office 365 常见问题的客户参数](https://support.office.com/article/Customer-Key-for-Office-365-FAQ-41ae293a-bd5c-4083-acd8-e1a2b4329da6)，和[数据以帮助满足合规性管理和控制需要与客户参数](https://techcommunity.microsoft.com/t5/Microsoft-Ignite-Content-2017/Manage-and-control-your-data-to-help-meet-compliance-needs-with/td-p/117580)。</span><span class="sxs-lookup"><span data-stu-id="92071-p106">To learn how to set up Customer Key for Office 365 for Exchange Online, Skype for Business, SharePoint Online, and OneDrive for Business, see [Controlling your data in Office 365 using Customer Key](https://support.office.com/article/Controlling-your-data-in-Office-365-using-Customer-Key-f2cd475a-e592-46cf-80a3-1bfb0fa17697). For additional information, see the [Customer Key for Office 365 FAQ](https://support.office.com/article/Customer-Key-for-Office-365-FAQ-41ae293a-bd5c-4083-acd8-e1a2b4329da6), and [Manage and control your data to help meet compliance needs with Customer Key](https://techcommunity.microsoft.com/t5/Microsoft-Ignite-Content-2017/Manage-and-control-your-data-to-help-meet-compliance-needs-with/td-p/117580).</span></span>
