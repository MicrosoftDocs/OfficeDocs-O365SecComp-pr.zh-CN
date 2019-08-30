---
title: 在 EOP 中管理收件人
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/17/2014
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 2921f544-8257-4bae-8e3a-ce9250e9f162
description: Microsoft Exchange Online Protection (EOP) 提供了几种用于管理邮件收件人的方法。 作为管理员, 您可以在 Exchange 管理中心 (EAC) 或使用远程 Windows PowerShell 中执行某些管理任务, 并验证在 Microsoft 365 管理中心内执行的其他管理任务。
ms.openlocfilehash: 6b56bcf725fe461c7e059658e7981f27bd4c07eb
ms.sourcegitcommit: 361aab46b1bb295ed2dcc1a417ac81f699b8ff78
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/30/2019
ms.locfileid: "36676572"
---
# <a name="manage-recipients-in-eop"></a><span data-ttu-id="69569-104">在 EOP 中管理收件人</span><span class="sxs-lookup"><span data-stu-id="69569-104">Manage recipients in EOP</span></span>

<span data-ttu-id="69569-105">Microsoft Exchange Online Protection (EOP) 提供了几种用于管理邮件收件人的方法。</span><span class="sxs-lookup"><span data-stu-id="69569-105">Microsoft Exchange Online Protection (EOP) offers several ways to manage your mail recipients.</span></span> <span data-ttu-id="69569-106">作为管理员, 您可以在 Exchange 管理中心 (EAC) 或使用远程 Windows PowerShell 中执行某些管理任务, 并验证在 Microsoft 365 管理中心内执行的其他管理任务。</span><span class="sxs-lookup"><span data-stu-id="69569-106">As an administrator, you can perform certain management tasks within the Exchange admin center (EAC) or using remote Windows PowerShell, and verify other management tasks performed in the Microsoft 365 admin center.</span></span>
  
<span data-ttu-id="69569-107">EOP 支持以下类型的收件人：</span><span class="sxs-lookup"><span data-stu-id="69569-107">EOP supports the following types of recipients:</span></span>
  
- <span data-ttu-id="69569-108">**邮件用户**: 邮件用户是 EOP 托管域中的收件人。</span><span class="sxs-lookup"><span data-stu-id="69569-108">**Mail Users**: Mail users are recipients in your EOP managed domains.</span></span> <span data-ttu-id="69569-109">这些收件人在您的 Office 365 组织中拥有登录凭据，但是他们拥有外部电子邮件地址，这意味着他们的收件人邮箱位于您的云组织外部。</span><span class="sxs-lookup"><span data-stu-id="69569-109">These recipients have logon credentials in your Office 365 organization, but they have external email addresses, meaning that their recipient mailboxes are located outside of your cloud organization.</span></span>

  <span data-ttu-id="69569-110">您可以添加邮件用户, 以便他们可以接收邮件, 也可以为特定用户创建邮件流规则 (也称为传输规则)。</span><span class="sxs-lookup"><span data-stu-id="69569-110">You can add mail users so that they can receive mail and you can also create mail flow rules (also known as transport rules) for specific users.</span></span> <span data-ttu-id="69569-111">您还可以为您组织中的邮件用户分配角色，拥有管理角色组权限的用户可以访问 Exchange 管理中心 (EAC) 并执行特定的管理任务。</span><span class="sxs-lookup"><span data-stu-id="69569-111">You can also assign roles to mail users in your organization; users with management role group privileges can access the Exchange admin center (EAC) and perform certain management tasks.</span></span> <span data-ttu-id="69569-112">若要了解有关用户角色以及如何在 EOP 中分配用户角色的详细信息, 请参阅[Manage admin role group 权限 IN EOP](manage-admin-role-group-permissions-in-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="69569-112">To learn more about user roles and how to assign user roles in EOP, see [Manage admin role group permissions in EOP](manage-admin-role-group-permissions-in-eop.md).</span></span>

  <span data-ttu-id="69569-113">有关在 EOP 中管理邮件用户的详细信息，请参阅[在 EOP 中管理邮件用户](manage-mail-users-in-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="69569-113">For more information about managing mail users in EOP, see [Manage mail users in EOP](manage-mail-users-in-eop.md).</span></span>

- <span data-ttu-id="69569-114">**组**: 邮件用户可以分组到通讯组或安全组中。</span><span class="sxs-lookup"><span data-stu-id="69569-114">**Groups**: Mail users can be grouped together into distribution groups or security groups.</span></span>

<span data-ttu-id="69569-115">有关在 EOP 中管理组的详细信息，请参阅[在 EOP 中管理组](manage-groups-in-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="69569-115">For more information about managing groups in EOP, see [Manage groups in EOP](manage-groups-in-eop.md).</span></span>
