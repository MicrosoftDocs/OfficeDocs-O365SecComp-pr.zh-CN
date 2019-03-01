---
title: 在 EOP 中管理收件人
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 2921f544-8257-4bae-8e3a-ce9250e9f162
description: Microsoft Exchange Online Protection (EOP) 提供了几种用于管理邮件收件人的方法。作为管理员，您可以在 Exchange 管理中心 (EAC) 内或使用远程 Windows PowerShell 执行特定的管理任务，并能验证在 Microsoft Office 365 管理中心内执行的其他管理任务。
ms.openlocfilehash: 55b28dcb107df85052ff623f653eecaaf88c7bda
ms.sourcegitcommit: 48fa456981b5c52ab8aeace173c8366b9f36723b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2019
ms.locfileid: "30341653"
---
# <a name="manage-recipients-in-eop"></a><span data-ttu-id="cfe35-104">在 EOP 中管理收件人</span><span class="sxs-lookup"><span data-stu-id="cfe35-104">Manage recipients in EOP</span></span>

<span data-ttu-id="cfe35-p102">Microsoft Exchange Online Protection (EOP) 提供了几种用于管理邮件收件人的方法。作为管理员，您可以在 Exchange 管理中心 (EAC) 内或使用远程 Windows PowerShell 执行特定的管理任务，并能验证在 Microsoft Office 365 管理中心内执行的其他管理任务。</span><span class="sxs-lookup"><span data-stu-id="cfe35-p102">Microsoft Exchange Online Protection (EOP) offers several ways to manage your mail recipients. As an administrator, you can perform certain management tasks within the Exchange admin center (EAC) or using remote Windows PowerShell, and verify other management tasks performed in the Microsoft Office 365 admin center.</span></span>
  
<span data-ttu-id="cfe35-107">EOP 支持以下类型的收件人：</span><span class="sxs-lookup"><span data-stu-id="cfe35-107">EOP supports the following types of recipients:</span></span>
  
- <span data-ttu-id="cfe35-p103">**邮件用户**邮件用户是 EOP 托管域中的收件人。这些收件人在 Office 365 组织中有登录凭据, 但它们具有外部电子邮件地址, 这意味着他们的收件人邮箱位于云组织之外。您可以添加邮件用户, 以便他们可以接收邮件, 也可以为特定用户创建邮件流规则 (也称为传输规则)。您还可以向组织中的邮件用户分配角色;具有管理角色组权限的用户可以访问 Exchange 管理中心 (EAC) 并执行某些管理任务。若要了解有关用户角色以及如何在 EOP 中分配用户角色的详细信息, 请参阅[Manage admin role group 权限 in EOP](manage-admin-role-group-permissions-in-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="cfe35-p103">**Mail Users** Mail users are recipients in your EOP managed domains. These recipients have logon credentials in your Office 365 organization, but they have external email addresses, meaning that their recipient mailboxes are located outside of your cloud organization. You can add mail users so that they can receive mail and you can also create mail flow rules (also known as transport rules) for specific users. You can also assign roles to mail users in your organization; users with management role group privileges can access the Exchange admin center (EAC) and perform certain management tasks. To learn more about user roles and how to assign user roles in EOP, see [Manage admin role group permissions in EOP](manage-admin-role-group-permissions-in-eop.md).</span></span>
    
    <span data-ttu-id="cfe35-113">有关在 EOP 中管理邮件用户的详细信息，请参阅[在 EOP 中管理邮件用户](manage-mail-users-in-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="cfe35-113">For more information about managing mail users in EOP, see [Manage mail users in EOP](manage-mail-users-in-eop.md).</span></span>
    
- <span data-ttu-id="cfe35-114">**组** 可以将邮件用户归入通讯组或安全组。</span><span class="sxs-lookup"><span data-stu-id="cfe35-114">**Groups** Mail users can be grouped together into distribution groups or security groups.</span></span> 
    
    <span data-ttu-id="cfe35-115">有关在 EOP 中管理组的详细信息，请参阅[在 EOP 中管理组](manage-groups-in-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="cfe35-115">For more information about managing groups in EOP, see [Manage groups in EOP](manage-groups-in-eop.md).</span></span>
    
<span data-ttu-id="cfe35-p104">是否正在寻找此主题的 Exchange Online 版本？请参阅 [Recipients in Exchange Online](http://technet.microsoft.com/library/50d16941-5cd7-435d-8715-e2b69f8410ab.aspx)。</span><span class="sxs-lookup"><span data-stu-id="cfe35-p104">Looking for the Exchange Online version of this topic? See [Recipients in Exchange Online](http://technet.microsoft.com/library/50d16941-5cd7-435d-8715-e2b69f8410ab.aspx).</span></span>
  
<span data-ttu-id="cfe35-p105">是否正在寻找此主题的 Exchange Server 版本？请参阅[Recipients](http://technet.microsoft.com/library/40300ed4-85a5-463d-bb3a-cf787bd44e9d.aspx)。</span><span class="sxs-lookup"><span data-stu-id="cfe35-p105">Looking for the Exchange Server version of this topic? See [Recipients](http://technet.microsoft.com/library/40300ed4-85a5-463d-bb3a-cf787bd44e9d.aspx).</span></span>
  

