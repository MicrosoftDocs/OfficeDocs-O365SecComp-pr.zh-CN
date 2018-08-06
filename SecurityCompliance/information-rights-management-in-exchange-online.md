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
# <a name="information-rights-management-in-exchange-online"></a><span data-ttu-id="646cd-104">Exchange Online 中的信息权限管理</span><span class="sxs-lookup"><span data-stu-id="646cd-104">Information Rights Management in Exchange Online</span></span>

<span data-ttu-id="646cd-p102">人们经常使用电子邮件来交换敏感信息，例如财务数据、法律合同、机密产品信息、销售报表和预测、患者健康信息或客户和员工信息。因此，邮箱可能会成为一个包含大量潜在敏感信息的存储库，信息泄露可能会成为您组织的严重威胁。</span><span class="sxs-lookup"><span data-stu-id="646cd-p102">People often use email to exchange sensitive information, such as financial data, legal contracts, confidential product information, sales reports and projections, patient health information, or customer and employee information. As a result, mailboxes can become repositories for large amounts of potentially sensitive information and information leakage can become a serious threat to your organization.</span></span>
  
<span data-ttu-id="646cd-p103">为了帮助防止信息泄露，Exchange Online 包括信息权限管理 (IRM) 功能，提供的电子邮件和附件的联机和脱机保护。通过 Microsoft Outlook 或 Outlook web 上的用户可以应用 IRM 保护并可由管理员使用传输保护规则或 Outlook 保护规则。IRM 有助于您和您用户控制哪些人可以访问、 转发、 打印或复制电子邮件中的敏感数据。</span><span class="sxs-lookup"><span data-stu-id="646cd-p103">To help prevent information leakage, Exchange Online includes Information Rights Management (IRM) functionality that provides online and offline protection of email messages and attachments. IRM protection can be applied by users in Microsoft Outlook or Outlook on the web, and it can be applied by administrators using transport protection rules or Outlook protection rules. IRM helps you and your users control who can access, forward, print, or copy sensitive data within an email.</span></span>
  
## <a name="changes-to-how-irm-works-with-office-365-message-encryption-ome-and-azure-active-directory"></a><span data-ttu-id="646cd-110">对 IRM 方式与 Office 365 邮件加密 (OME) 和 Azure Active Directory 更改</span><span class="sxs-lookup"><span data-stu-id="646cd-110">Changes to how IRM works with Office 365 Message Encryption (OME) and Azure Active Directory</span></span>

<span data-ttu-id="646cd-p104">从年 9 月 2017，当您设置新的 Office 365 邮件加密功能为您的组织，您还设置 IRM 与 Azure 权限管理 (Azure RMS) 一起使用。您不再与 Azure RMS 的 IRM 分别设置。而是 OME 和权限管理都将无缝协同工作。有关新功能的详细信息，请参阅[Office 365 邮件加密 FAQ](https://support.office.com/article/0432dce9-d9b6-4e73-8a13-4a932eb0081e)。如果您已准备好开始使用您的组织中的新 OME 功能，请参阅[设置新的 Office 365 邮件加密功能构建到 Azure 信息保护的顶部](https://support.office.com/article/7ff0c040-b25c-4378-9904-b1b50210d00e)。</span><span class="sxs-lookup"><span data-stu-id="646cd-p104">As of September 2017, when you set up the new Office 365 Message Encryption capabilities for your organization, you also set up IRM for use with Azure Rights Management (Azure RMS). You no longer set up IRM with Azure RMS separately. Instead, OME and rights management work seamlessly together. For more details about the new capabilities, see [Office 365 Message Encryption FAQ](https://support.office.com/article/0432dce9-d9b6-4e73-8a13-4a932eb0081e). If you're ready to get started using the new OME capabilities within your organization, see [Set up new Office 365 Message Encryption capabilities built on top of Azure Information Protection](https://support.office.com/article/7ff0c040-b25c-4378-9904-b1b50210d00e).</span></span>
  
## <a name="how-irm-works-with-exchange-online-and-active-directory-rights-management-services"></a><span data-ttu-id="646cd-116">IRM 方式与 Exchange Online 和 Active Directory Rights Management Services</span><span class="sxs-lookup"><span data-stu-id="646cd-116">How IRM works with Exchange Online and Active Directory Rights Management Services</span></span>

<span data-ttu-id="646cd-p105">Exchange Online IRM 使用内部部署 Active Directory Rights Management Services (AD RMS)，在 Windows Server 2008 及更高版本信息保护技术。通过将 AD RMS 权限策略模板应用于电子邮件到电子邮件应用 IRM 保护。权限附加到邮件本身，以便保护发生联机和脱机和内部和外部组织的防火墙。</span><span class="sxs-lookup"><span data-stu-id="646cd-p105">Exchange Online IRM uses on-premises Active Directory Rights Management Services (AD RMS), an information protection technology in Windows Server 2008 and later. IRM protection is applied to email by applying an AD RMS rights policy template to an email message. Rights are attached to the message itself so that protection occurs online and offline and inside and outside of your organization's firewall.</span></span>
  
<span data-ttu-id="646cd-p106">用户可以应用于电子邮件控制收件人对一条消息的权限模板。可以通过将 AD RMS 权限策略应用到邮件控制操作，如转接、 从邮件中提取信息、 保存一条消息，或打印一条消息。</span><span class="sxs-lookup"><span data-stu-id="646cd-p106">Users can apply a template to an email message to control the permissions that recipients have on a message. Actions, such as forwarding, extracting information from a message, saving a message or printing a message can be controlled by applying an AD RMS rights policy to the message.</span></span>
  
<span data-ttu-id="646cd-p107">您可以配置 IRM 以使用 AD RMS 服务器运行 Windows Server 2008 或更高版本。此 AD RMS 服务器可用于管理基于云的组织的 AD RMS 权限策略模板。Outlook 还依靠 AD RMS 服务器，以使用户能够向他们发送的邮件应用 IRM 保护。有关详细信息，请参阅[配置 IRM 以使用内部部署 AD RMS 服务器](configure-irm-to-use-an-on-premises-ad-rms-server.md)。</span><span class="sxs-lookup"><span data-stu-id="646cd-p107">You can configure IRM to use an AD RMS server running Windows Server 2008 or later. You can use this AD RMS server to manage the AD RMS rights policy templates for your cloud-based organization. Outlook also relies on the AD RMS server to enable users to apply IRM protection to messages they send. For details, see [Configure IRM to use an on-premises AD RMS server](configure-irm-to-use-an-on-premises-ad-rms-server.md).</span></span> 
  
<span data-ttu-id="646cd-126">启用后，IRM 保护可以应用于邮件，如下所示：</span><span class="sxs-lookup"><span data-stu-id="646cd-126">After it's enabled, IRM protection can be applied to messages as follows:</span></span>
  
- <span data-ttu-id="646cd-p108">**用户可以手动应用使用 Outlook 和 Outlook web 上的模板。** 用户可以通过从**设置权限**列表中选择模板至的电子邮件应用 AD RMS 权限策略模板。当用户发送受 IRM 保护的邮件时，使用受支持的格式的任何附加的文件还会收到邮件的相同 IRM 保护。IRM 保护应用于 Word、 Excel 和 PowerPoint，以及.xps 文件和附加的电子邮件与关联的文件。</span><span class="sxs-lookup"><span data-stu-id="646cd-p108">**Users can manually apply a template using Outlook and Outlook on the web.** Users can apply an AD RMS rights policy template to an email message by selecting the template from the **Set permissions** list. When users send an IRM-protected message, any attached files that use a supported format also receive the same IRM protection as the message. IRM protection is applied to files associated with Word, Excel, and PowerPoint, as well as .xps files and attached email messages.</span></span> 
    
- <span data-ttu-id="646cd-p109">**管理员可以使用传输保护规则 Outlook 和 Outlook web 上的自动应用 IRM 保护。** 您可以创建 IRM 保护的邮件传输保护规则。配置将 AD RMS 权限策略模板应用于邮件满足该规则条件的传输保护规则操作。启用 IRM 后，可供使用与传输保护规则操作调用**应用于邮件的权限保护**组织的 AD RMS 权限策略模板。</span><span class="sxs-lookup"><span data-stu-id="646cd-p109">**Administrators can use transport protection rules to apply IRM protection automatically to both Outlook and Outlook on the web.** You can create transport protection rules to IRM-protect messages. Configure the transport protection rule action to apply an AD RMS rights policy template to messages that meet the rule condition. After you enable IRM, your organization's AD RMS rights policy templates are available to use with the transport protection rule action called **Apply rights protection to the message with**.</span></span>
    
- <span data-ttu-id="646cd-p110">**管理员可创建 Outlook 保护规则。** Outlook 保护规则自动根据邮件条件包含发件人的部门，邮件发送给，用户在 Outlook 2010 中 (不在 web 上的 Outlook) 的邮件应用 IRM 保护和内部或外部收件人是否您组织。有关详细信息，请参阅[Create Outlook 保护规则](http://technet.microsoft.com/library/da64750d-faaf-44de-ad8c-888eba7fbdbf.aspx)。</span><span class="sxs-lookup"><span data-stu-id="646cd-p110">**Administrators can create Outlook protection rules.** Outlook protection rules automatically apply IRM-protection to messages in Outlook 2010 (not Outlook on the web) based on message conditions that include the sender's department, who the message is sent to, and whether recipients are inside or outside your organization. For details, see [Create an Outlook Protection Rule](http://technet.microsoft.com/library/da64750d-faaf-44de-ad8c-888eba7fbdbf.aspx).</span></span>
    

