---
title: Office 365 服务加密
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: '摘要: 了解 Microsoft Office 365 中的数据恢复能力。'
ms.openlocfilehash: 4e9dd52adbeada92d14db369b386ff1ca7e42fc5
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30220342"
---
# <a name="office-365-service-encryption"></a><span data-ttu-id="b03f0-103">Office 365 服务加密</span><span class="sxs-lookup"><span data-stu-id="b03f0-103">Office 365 Service Encryption</span></span>

<span data-ttu-id="b03f0-p101">除了使用卷级加密之外, Exchange Online、Skype for business、SharePoint online 和 OneDrive for business 还使用服务加密来加密客户数据。服务加密允许两个密钥管理选项:</span><span class="sxs-lookup"><span data-stu-id="b03f0-p101">In addition to using volume-level encryption, Exchange Online, Skype for Business, SharePoint Online, and OneDrive for Business also use Service Encryption to encrypt customer data. Service Encryption allows for two key management options:</span></span>
- <span data-ttu-id="b03f0-p102">Microsoft 管理所有加密密钥。(此选项目前在 SharePoint Online、OneDrive for business 和 Skype for business 中可用。它当前位于 Exchange Online 的路线图中。</span><span class="sxs-lookup"><span data-stu-id="b03f0-p102">Microsoft manages all cryptographic keys. (This option is currently available in SharePoint Online, OneDrive for Business, and Skype for Business. It is currently on the roadmap for Exchange Online.)</span></span>
- <span data-ttu-id="b03f0-p103">客户提供用于服务加密的根键, 并且客户使用 Azure Key Vault 管理这些密钥。Microsoft 管理所有其他密钥。此选项称为 "客户密钥", 目前适用于 Exchange online、SharePoint online 和 OneDrive for business。(以前称为使用 BYOK 的高级加密。请参阅增强针对原始公告的[Office 365 客户的透明度和控制](http://blogs.office.com/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/)。</span><span class="sxs-lookup"><span data-stu-id="b03f0-p103">The customer supplies root keys used with service encryption and the customer manages these keys using Azure Key Vault. Microsoft manages all other keys. This option is called Customer Key, and it is currently available for Exchange Online, SharePoint Online, and OneDrive for Business. (Previously referred to as Advanced Encryption with BYOK. See [Enhancing transparency and control for Office 365 customers](http://blogs.office.com/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/) for the original announcement.)</span></span>

<span data-ttu-id="b03f0-p104">服务加密提供了多项优势。例如, 它:</span><span class="sxs-lookup"><span data-stu-id="b03f0-p104">Service encryption provides multiple benefits. For example, it:</span></span>
- <span data-ttu-id="b03f0-116">在强加密保护之上提供权限保护和管理功能。</span><span class="sxs-lookup"><span data-stu-id="b03f0-116">provides rights protection and management features on top of strong encryption protection.</span></span>
- <span data-ttu-id="b03f0-117">包括一个 "客户密钥" 选项, 该选项使多租户服务能够提供每租户密钥管理。</span><span class="sxs-lookup"><span data-stu-id="b03f0-117">includes a Customer Key option that enables multi-tenant services to provide per-tenant key management.</span></span>
- <span data-ttu-id="b03f0-118">提供 Windows 操作系统管理员的分离, 以访问由操作系统存储或处理的客户数据。</span><span class="sxs-lookup"><span data-stu-id="b03f0-118">provides separation of Windows operating system administrators from access to customer data stored or processed by the operating system.</span></span>
- <span data-ttu-id="b03f0-119">增强了 Office 365 满足有关加密合规性要求的客户需求的能力。</span><span class="sxs-lookup"><span data-stu-id="b03f0-119">enhances the ability of Office 365 to meet the demands of customers that have compliance requirements regarding encryption.</span></span>

## <a name="customer-key"></a><span data-ttu-id="b03f0-120">客户密钥</span><span class="sxs-lookup"><span data-stu-id="b03f0-120">Customer Key</span></span>
<span data-ttu-id="b03f0-p105">使用客户密钥, 您可以使用本地 HSM 或 Azure Key Vault 生成自己的加密密钥。无论密钥的生成方式如何, 客户都可以使用 Azure key Vault 控制和管理 Office 365 使用的加密密钥。密钥存储在 Azure Key Vault 中后, 可以将其分配给诸如 Exchange online 和 SharePoint online 之类的工作负荷, 并可用作用于对邮箱数据和文件进行加密的密钥链的根。使用客户密钥的另一个好处是, 控制 Microsoft 处理客户数据的能力。此功能存在, 以便希望从 Office 365 中删除数据的客户 (例如, 当客户终止使用 Microsoft 的服务或删除存储在云中的数据部分时) 可以这样做, 并将客户密钥用作技术控制, 以确保没有任何人(包括 Microsoft) 可以访问或处理数据。这是对客户密码箱功能的补充 (和补充), 可用于控制 Microsoft 人员对客户数据的访问。</span><span class="sxs-lookup"><span data-stu-id="b03f0-p105">Using Customer Key, you can generate your own cryptographic keys using either an on-premises HSM or Azure Key Vault. Regardless of how the key is generated, customers use Azure Key Vault to control and manage the cryptographic keys used by Office 365. Once your keys are stored in Azure Key Vault, they can be assigned to workloads such as Exchange Online and SharePoint Online and used to as the root of the keychain used to encrypt your mailbox data and files. One of the other benefits of using Customer Key is to control the ability of Microsoft to process customer data. This capability exists so that a customer that wants to remove data from Office 365 (such as when a customer terminates service with Microsoft or removes a portion of data stored in the cloud) can do so and use Customer Key as a technical control to ensure that no one, including Microsoft, can access or process the data. This is in addition (and a complement) to the Customer Lockbox feature that can be used to control access to customer data by Microsoft personnel.</span></span>

<span data-ttu-id="b03f0-p106">若要了解如何设置适用于 Exchange Online、Skype for business、SharePoint online 和 OneDrive for business 的 office 365 客户密钥, 请参阅[使用客户密钥在 Office 365 中控制您的数据](https://support.office.com/article/Controlling-your-data-in-Office-365-using-Customer-Key-f2cd475a-e592-46cf-80a3-1bfb0fa17697)。有关详细信息, 请参阅[适用于 Office 365 FAQ 的客户密钥](https://support.office.com/article/Customer-Key-for-Office-365-FAQ-41ae293a-bd5c-4083-acd8-e1a2b4329da6), 并[管理和控制你的数据, 以使用客户密钥帮助满足合规性需求](https://techcommunity.microsoft.com/t5/Microsoft-Ignite-Content-2017/Manage-and-control-your-data-to-help-meet-compliance-needs-with/td-p/117580)。</span><span class="sxs-lookup"><span data-stu-id="b03f0-p106">To learn how to set up Customer Key for Office 365 for Exchange Online, Skype for Business, SharePoint Online, and OneDrive for Business, see [Controlling your data in Office 365 using Customer Key](https://support.office.com/article/Controlling-your-data-in-Office-365-using-Customer-Key-f2cd475a-e592-46cf-80a3-1bfb0fa17697). For additional information, see the [Customer Key for Office 365 FAQ](https://support.office.com/article/Customer-Key-for-Office-365-FAQ-41ae293a-bd5c-4083-acd8-e1a2b4329da6), and [Manage and control your data to help meet compliance needs with Customer Key](https://techcommunity.microsoft.com/t5/Microsoft-Ignite-Content-2017/Manage-and-control-your-data-to-help-meet-compliance-needs-with/td-p/117580).</span></span>
