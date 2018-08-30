---
title: Office 365 中创建诉讼保留
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 3/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 39db1659-0b12-4243-a21c-2614512dcb44
ms.openlocfilehash: 18b3b3a42e5671b1507522c89faaa4ae34198831
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525801"
---
# <a name="create-a-litigation-hold-in-office-365"></a><span data-ttu-id="d8e16-102">Office 365 中创建诉讼保留</span><span class="sxs-lookup"><span data-stu-id="d8e16-102">Create a Litigation Hold in Office 365</span></span>

<span data-ttu-id="d8e16-p101">您可以将邮箱置于诉讼保留状态，保留所有邮箱内容，包括已删除的项目和已修改项目的原始版本。如果您将用户邮箱置于诉讼保留时，用户的存档邮箱中的内容 （如果已启用） 是还会保留。创建保留项时，您可以指定 （也称为*基于时间的保留*） 保留持续时间，以便删除和修改的项的保留指定的时间段，然后永久删除邮箱。或可以只是无限期保留内容 （称为*无限期保留*） 或直到诉讼保留被删除。如果您指定保留持续时间段，它计算从日期收到一条消息，或创建邮箱项目。</span><span class="sxs-lookup"><span data-stu-id="d8e16-p101">You can place a mailbox on Litigation Hold to retain all mailbox content, including deleted items and the original versions of modified items. When you place a user mailbox on Litigation Hold, content in the user's archive mailbox (if it's enabled) is also retained. When you create a hold, you can specify a hold duration (also called a *time-based hold*) so that deleted and modified items are retained for a specified period and then permanently deleted from the mailbox. Or you can just retain content indefinitely (called an *infinite hold*) or until the Litigation Hold is removed. If you do specify a hold duration period, it's calculated from the date a message is received or a mailbox item is created.</span></span> 
  
<span data-ttu-id="d8e16-108">下面是创建诉讼保留时，会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="d8e16-108">Here's what happens when you create a Litigation Hold.</span></span>
  
- <span data-ttu-id="d8e16-109">用户被永久删除的项目保留的持续时间内保留用户的邮箱中的可恢复的项目文件夹中。</span><span class="sxs-lookup"><span data-stu-id="d8e16-109">Items that are permanently deleted by the user are retained in the Recoverable Items folder in the user's mailbox for the duration of the hold.</span></span>
    
- <span data-ttu-id="d8e16-110">保留项的持续时间内保留用户从可恢复邮件文件夹清除的项目。</span><span class="sxs-lookup"><span data-stu-id="d8e16-110">Items that are purged from the Recoverable Items folder by the user are retained for the duration of the hold.</span></span>
    
- <span data-ttu-id="d8e16-111">可恢复邮件文件夹的存储配额为 110 GB 增加从 30 GB。</span><span class="sxs-lookup"><span data-stu-id="d8e16-111">The storage quota for the Recoverable Items folder is increased from 30 GB to 110 GB.</span></span>
    
- <span data-ttu-id="d8e16-112">保留用户的主和存档邮箱中的项目</span><span class="sxs-lookup"><span data-stu-id="d8e16-112">Items in the user's primary and the archive mailboxes are retained</span></span>
    
## <a name="before-you-begin"></a><span data-ttu-id="d8e16-113">准备工作</span><span class="sxs-lookup"><span data-stu-id="d8e16-113">Before you begin</span></span>

- <span data-ttu-id="d8e16-p102">若要将 Exchange Online 邮箱置于诉讼保留状态，必须将它分配的 Exchange Online 计划 2 许可证。如果邮箱已分配的 Exchange Online 计划 1 许可证，您必须将其单独 Exchange Online Archiving 的许可证将它置于保留分配。</span><span class="sxs-lookup"><span data-stu-id="d8e16-p102">To place an Exchange Online mailbox on Litigation Hold, it must be assigned an Exchange Online Plan 2 license. If a mailbox is assigned an Exchange Online Plan 1 license, you would have to assign it a separate Exchange Online Archiving license to place it on hold.</span></span>
    

## <a name="place-a-mailbox-on-litigation-hold-in-the-office-365-admin-center"></a><span data-ttu-id="d8e16-116">将邮箱置于诉讼保留在 Office 365 管理中心</span><span class="sxs-lookup"><span data-stu-id="d8e16-116">Place a mailbox on Litigation Hold in the Office 365 admin center</span></span>

<span data-ttu-id="d8e16-117">以下是将置于诉讼保留状态使用 Office 365 管理中心 maibox 的步骤。</span><span class="sxs-lookup"><span data-stu-id="d8e16-117">Here are the steps to place a maibox on Litigation Hold using the Office 365 admin center.</span></span>

1. <span data-ttu-id="d8e16-118">转到https://portal.office.com/adminportal/home和使用您的全局管理员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="d8e16-118">Go to https://portal.office.com/adminportal/home and sign in using your global administrator account.</span></span>
2. <span data-ttu-id="d8e16-119">单击**用户** > 左的导航窗格中的**活动用户**。</span><span class="sxs-lookup"><span data-stu-id="d8e16-119">Click **Users** > **Active users** in the left navigation pane.</span></span>
3. <span data-ttu-id="d8e16-120">选择您要置于诉讼保留其邮箱的用户。</span><span class="sxs-lookup"><span data-stu-id="d8e16-120">Select the user whose mailbox you want to place on Litigation Hold.</span></span>
4. <span data-ttu-id="d8e16-121">在飞出页上，单击**邮件设置**，然后单击**诉讼保留**旁边的**编辑**。</span><span class="sxs-lookup"><span data-stu-id="d8e16-121">On the fly-out page, click **Mail settings**, and then click **Edit** next to **Litigation hold**.</span></span>
5. <span data-ttu-id="d8e16-122">在**诉讼保留**页上，单击打开置于诉讼保留状态并完成以下显示的可选设置切换:</span><span class="sxs-lookup"><span data-stu-id="d8e16-122">On the **Litigation hold** page, click the toggle to turn on Litigation Hold and complete the following optional settings that are displayed:</span></span>
 
    ![O365_LitigationHold1.png](media/O365-LitigationHold1.png)

    <span data-ttu-id="d8e16-p103">答：**保留持续时间 （天）** -使用此框可以创建基于时间的保留并指定当邮箱置于诉讼保留多长时间保留邮箱项目。接收或创建邮箱项目时，将从日期计算持续时间。如果将此框保留为空，项目保留无限期或直到保留被删除。使用天指定持续时间。</span><span class="sxs-lookup"><span data-stu-id="d8e16-p103">a. **Hold duration (days)** - Use this box to create a time-based hold and specify how long mailbox items are held when the mailbox is placed on Litigation Hold. The duration is calculated from the date a mailbox item is received or created. If you leave this box blank, items are held indefinitely or until the hold is removed. Use days to specify the duration.</span></span>
    
    <span data-ttu-id="d8e16-p104">b.**注意**-使用此框通知用户其邮箱位于诉讼保留。如果他们正在使用 Outlook 2010 或更高版本，注释将显示在用户的邮箱的帐户信息页上。若要访问此页，用户可以单击在 Outlook 中的**文件**。</span><span class="sxs-lookup"><span data-stu-id="d8e16-p104">b. **Note** - Use this box to inform the user their mailbox is on Litigation Hold. The note will appear on the Account Information page in the user's mailbox if they're using Outlook 2010 or later. To access this page, users can click **File** in Outlook.</span></span>
     
    <span data-ttu-id="d8e16-p105">c. **Web 页**-使用此框可以将用户定向到有关诉讼保留的详细信息的网站。如果他们使用 Outlook 2010 或更高版本，此 URL 将出现在用户的邮箱的帐户信息页上。若要访问此页，用户可以单击在 Outlook 中的**文件**。</span><span class="sxs-lookup"><span data-stu-id="d8e16-p105">c. **Web page** - Use this box to direct the user to a website for more information about Litigation Hold. This URL appears on the Account Information page in the user's mailbox if they are using Outlook 2010 or later. To access this page, users can click **File** in Outlook.</span></span>
 
6. <span data-ttu-id="d8e16-137">单击**保存**以创建诉讼保留。</span><span class="sxs-lookup"><span data-stu-id="d8e16-137">Click **Save** to create the Litigation Hold.</span></span>

<span data-ttu-id="d8e16-138">创建保留项后，飞出页面上的邮件设置显示诉讼保留已打开所选用户。</span><span class="sxs-lookup"><span data-stu-id="d8e16-138">After you create the hold, the mail settings on the fly-out page shows that Litigation Hold is turned on for the selected user.</span></span>

![O365_LitigationHold2.png](media/O365-LitigationHold2.png)

<span data-ttu-id="d8e16-140">有关创建和管理诉讼保留和使用 Exchange Online PowerShell 中批量创建诉讼保留的详细信息，请参阅[位置上诉讼保留的邮箱](https://docs.microsoft.com/office365/SecurityCompliance/place-a-mailbox-on-litigation-hold)。</span><span class="sxs-lookup"><span data-stu-id="d8e16-140">For more information about creating and managing Litigation Holds and using Exchange Online PowerShell to bulk-create Litigation Holds, see [Place a mailbox on Litigation Hold](https://docs.microsoft.com/office365/SecurityCompliance/place-a-mailbox-on-litigation-hold).</span></span>
