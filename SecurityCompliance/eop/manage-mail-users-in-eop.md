---
title: 在 EOP 中管理邮件用户
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 12/9/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 4bfaf2ab-e633-4227-8bde-effefb41a3db
description: 定义邮件用户是管理 Exchange Online Protection (EOP) 服务的重要部分。
ms.openlocfilehash: 520ca0fb48a131026d9a46138605892203bf6e93
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2019
ms.locfileid: "35599598"
---
# <a name="manage-mail-users-in-eop"></a><span data-ttu-id="5a48f-103">在 EOP 中管理邮件用户</span><span class="sxs-lookup"><span data-stu-id="5a48f-103">Manage mail users in EOP</span></span>

<span data-ttu-id="5a48f-p101">定义邮件用户是管理 Exchange Online Protection (EOP) 服务的重要部分。在 EOP 中，您可以使用多种方法来管理用户：</span><span class="sxs-lookup"><span data-stu-id="5a48f-p101">Defining mail users is an important part of managing the Exchange Online Protection (EOP) service. There are several ways that you can manage users in EOP:</span></span>
  
- <span data-ttu-id="5a48f-106">使用目录同步管理邮件用户：如果贵公司在本地 Active Directory 环境中已有用户帐户，您可以将这些帐户同步到 Azure Active Directory (AD)，其中，这些帐户的副本会存储在云中。</span><span class="sxs-lookup"><span data-stu-id="5a48f-106">Use directory synchronization to manage mail users: If your company has existing user accounts in an on-premises Active Directory environment, you can synchronize those accounts to Azure Active Directory (AD), where a copy of the accounts is stored in the cloud.</span></span> <span data-ttu-id="5a48f-107">将现有用户帐户同步到 Azure Active Directory 时, 可以在 Exchange 管理中心 (EAC) 的 "**收件人**" 窗格中查看这些用户。</span><span class="sxs-lookup"><span data-stu-id="5a48f-107">When you synchronize your existing user accounts to Azure Active Directory, you can view those users in the **Recipients** pane of the Exchange admin center (EAC).</span></span> <span data-ttu-id="5a48f-108">建议使用目录同步。</span><span class="sxs-lookup"><span data-stu-id="5a48f-108">Using directory synchronization is recommended.</span></span> 
    
- <span data-ttu-id="5a48f-109">使用 EAC 管理邮件用户：在 EAC 中直接添加和管理邮件用户。</span><span class="sxs-lookup"><span data-stu-id="5a48f-109">Use the EAC to manage mail users: Add and manage mail users directly in the EAC.</span></span> <span data-ttu-id="5a48f-110">这是添加邮件用户最简单的方式，并且对于一次添加一个用户非常有用。</span><span class="sxs-lookup"><span data-stu-id="5a48f-110">This is the easiest way to add mail users and is useful for adding one user at a time.</span></span>
    
- <span data-ttu-id="5a48f-111">使用远程 Windows PowerShell 管理邮件用户：通过运行远程 Windows PowerShell 添加和管理邮件用户。</span><span class="sxs-lookup"><span data-stu-id="5a48f-111">Use remote Windows PowerShell to manage mail users: Add and manage mail users by running remote Windows PowerShell.</span></span> <span data-ttu-id="5a48f-112">此方法可用于添加多个记录并创建脚本。</span><span class="sxs-lookup"><span data-stu-id="5a48f-112">This method is useful for adding multiple records and creating scripts.</span></span>
    
> [!NOTE]
> <span data-ttu-id="5a48f-113">你可以在 Microsoft 365 管理中心添加用户, 但这些用户不能用作邮件收件人。</span><span class="sxs-lookup"><span data-stu-id="5a48f-113">You can add users in the Microsoft 365 admin center, however these users can't be used as mail recipients.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="5a48f-114">开始之前</span><span class="sxs-lookup"><span data-stu-id="5a48f-114">Before you begin</span></span>

- <span data-ttu-id="5a48f-p105">本主题中的过程需要特定权限。请参阅每个过程，以了解其权限信息。</span><span class="sxs-lookup"><span data-stu-id="5a48f-p105">Procedures in this topic require specific permissions. See each procedure for its permissions information.</span></span>
    
- <span data-ttu-id="5a48f-117">若要了解可能适用于此主题中过程的键盘快捷键，请参阅 **Exchange 管理中心内的键盘快捷键**。</span><span class="sxs-lookup"><span data-stu-id="5a48f-117">For information about keyboard shortcuts that may apply to the procedures in this topic, see **Keyboard shortcuts in the Exchange admin center**.</span></span>
    
> [!TIP]
> <span data-ttu-id="5a48f-p106">遇到问题了吗？请在 Exchange 论坛中寻求帮助。 请访问以下论坛：[Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612)、[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542)或 [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351)。</span><span class="sxs-lookup"><span data-stu-id="5a48f-p106">Having problems? Ask for help in the Exchange forums. Visit the forums at [Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612),[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542), or [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351).</span></span> 
  
## <a name="use-directory-synchronization-to-manage-mail-users"></a><span data-ttu-id="5a48f-121">使用目录同步管理邮件用户</span><span class="sxs-lookup"><span data-stu-id="5a48f-121">Use directory synchronization to manage mail users</span></span>

<span data-ttu-id="5a48f-122">本节提供了有关使用目录同步管理电子邮件用户的信息。</span><span class="sxs-lookup"><span data-stu-id="5a48f-122">This section provides information about managing email users by using directory synchronization.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="5a48f-123">如果使用目录同步来管理收件人, 您仍可以在 Microsoft 365 管理中心中添加和管理用户, 但不会将其与本地 Active Directory 同步。</span><span class="sxs-lookup"><span data-stu-id="5a48f-123">If you use directory synchronization to manage your recipients, you can still add and manage users in the Microsoft 365 admin center, but they will not be synchronized with your on-premises Active Directory.</span></span> <span data-ttu-id="5a48f-124">这是因为目录同步只能将来自本地 Active Directory 的收件人同步到云。</span><span class="sxs-lookup"><span data-stu-id="5a48f-124">This is because directory synchronization only syncs recipients from your on-premises Active Directory to the cloud.</span></span> 
  
> [!TIP]
>  <span data-ttu-id="5a48f-125">建议使用目录同步来使用以下功能: > **Outlook 安全发件人列表和阻止发件人列表**-同步到服务时, 这些列表将优先于服务中的垃圾邮件筛选。</span><span class="sxs-lookup"><span data-stu-id="5a48f-125">Using directory synchronization is recommended for use with the following features: > **Outlook safe sender and blocked sender lists** - When synchronized to the service, these lists will take precedence over spam filtering in the service.</span></span> <span data-ttu-id="5a48f-126">这允许用户在每个用户或每个域的基础上管理他们自己的白名单和黑名单。</span><span class="sxs-lookup"><span data-stu-id="5a48f-126">This lets users manage their own safe sender and blocked sender lists on a per-user or per-domain basis.</span></span><span data-ttu-id="5a48f-127"> > **基于目录的边缘阻止 (DBEB)** -有关 DBEB 的详细信息, 请参阅[使用基于目录的边缘阻止拒绝发送给无效收件人的邮件](http://technet.microsoft.com/library/ca7b7416-92ed-40ad-abdb-695be46ea2e4.aspx)。</span><span class="sxs-lookup"><span data-stu-id="5a48f-127"> > **Directory Based Edge Blocking (DBEB)** - For more information about DBEB, see [Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](http://technet.microsoft.com/library/ca7b7416-92ed-40ad-abdb-695be46ea2e4.aspx).</span></span><span data-ttu-id="5a48f-128"> > **最终用户垃圾邮件隔离**-为了访问最终用户的垃圾邮件隔离, 最终用户必须具有有效的 Office 365 用户 ID 和密码。</span><span class="sxs-lookup"><span data-stu-id="5a48f-128"> > **End user spam quarantine** - In order to access the end user spam quarantine, end users must have a valid Office 365 user ID and password.</span></span> <span data-ttu-id="5a48f-129">负责保护本地邮箱的 EOP 客户必须是有效的电子邮件用户。</span><span class="sxs-lookup"><span data-stu-id="5a48f-129">EOP customers protecting on-premises mailboxes must be valid email users.</span></span><span data-ttu-id="5a48f-130"> > **邮件流规则**-使用目录同步时, 会自动将现有的 Active directory 用户和组上载到云, 然后您可以创建针对特定用户和/或的邮件流规则 (也称为传输规则)。组, 而无需通过 EAC 或 Exchange Online Protection PowerShell 手动添加它们。</span><span class="sxs-lookup"><span data-stu-id="5a48f-130"> > **Mail flow rules** - When you use directory synchronization, your existing Active Directory users and groups are automatically uploaded to the cloud, and you can then create mail flow rules (also known as transport rules) that target specific users and/or groups without having to manually add them via the the EAC or Exchange Online Protection PowerShell.</span></span> <span data-ttu-id="5a48f-131">请注意， [动态通讯组](https://go.microsoft.com/fwlink/?LinkId=507569)无法通过目录同步进行同步。</span><span class="sxs-lookup"><span data-stu-id="5a48f-131">Note that [dynamic distribution groups](https://go.microsoft.com/fwlink/?LinkId=507569) can't be synchronized via directory synchronization.</span></span> 
  
 <span data-ttu-id="5a48f-132">**开始之前**</span><span class="sxs-lookup"><span data-stu-id="5a48f-132">**Before you begin**</span></span>
  
<span data-ttu-id="5a48f-133">按[准备进行目录同步](https://go.microsoft.com/fwlink/p/?LinkId=308908)中所述，获取所需权限，并准备进行目录同步。</span><span class="sxs-lookup"><span data-stu-id="5a48f-133">Get the necessary permissions and prepare for directory synchronization, as described in [Prepare for directory synchronization](https://go.microsoft.com/fwlink/p/?LinkId=308908).</span></span>
  
### <a name="to-synchronize-user-directories"></a><span data-ttu-id="5a48f-134">同步用户目录的步骤</span><span class="sxs-lookup"><span data-stu-id="5a48f-134">To synchronize user directories</span></span>

1. <span data-ttu-id="5a48f-135">按[激活目录同步](https://go.microsoft.com/fwlink/p/?LinkId=308909)中所述，激活目录同步。</span><span class="sxs-lookup"><span data-stu-id="5a48f-135">Activate directory synchronization, as described in [Activate directory synchronization](https://go.microsoft.com/fwlink/p/?LinkId=308909).</span></span>
    
2. <span data-ttu-id="5a48f-136">按[设置目录同步计算机](http://go.microsoft.com/fwlink/p/?LinkId=308911)中所述，设置您的目录同步计算机。</span><span class="sxs-lookup"><span data-stu-id="5a48f-136">Set up your directory synchronization computer, as described in [Set up your directory sync computer](http://go.microsoft.com/fwlink/p/?LinkId=308911).</span></span>
    
3. <span data-ttu-id="5a48f-137">按[使用配置向导同步目录](http://go.microsoft.com/fwlink/?LinkId=308912)中所述，同步目录。</span><span class="sxs-lookup"><span data-stu-id="5a48f-137">Synchronize your directories, as described in [Use the Configuration Wizard to sync your directories](http://go.microsoft.com/fwlink/?LinkId=308912).</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="5a48f-138">当您完成 Azure Active Directory 同步工具配置向导时, 将在 Active Directory 林中创建**MSOL_AD_SYNC**帐户。</span><span class="sxs-lookup"><span data-stu-id="5a48f-138">When you finish the Azure Active Directory Sync Tool Configuration Wizard, the **MSOL_AD_SYNC** account is created in your Active Directory forest.</span></span> <span data-ttu-id="5a48f-139">此帐户用于读取和同步您的本地 Active Directory 信息。</span><span class="sxs-lookup"><span data-stu-id="5a48f-139">This account is used to read and synchronize your on-premises Active Directory information.</span></span> <span data-ttu-id="5a48f-140">为了使目录同步正常工作，请确保本地目录同步服务器上的 TCP 443 处于打开状态。</span><span class="sxs-lookup"><span data-stu-id="5a48f-140">In order for directory synchronization to work correctly, make sure that TCP 443 on your local directory synchronization server is open.</span></span> 
  
4. <span data-ttu-id="5a48f-141">按[激活同步用户](http://go.microsoft.com/fwlink/p/?LinkId=308913)中所述，激活同步用户。</span><span class="sxs-lookup"><span data-stu-id="5a48f-141">Activate synced users, as described in [Activate synced users](http://go.microsoft.com/fwlink/p/?LinkId=308913).</span></span>
    
5. <span data-ttu-id="5a48f-142">按[管理目录同步](http://go.microsoft.com/fwlink/p/?LinkId=308915)中所述，管理目录同步。</span><span class="sxs-lookup"><span data-stu-id="5a48f-142">Manage directory synchronization, as described in [Manage directory synchronization](http://go.microsoft.com/fwlink/p/?LinkId=308915).</span></span>
    
6. <span data-ttu-id="5a48f-143">验证 EOP 是否正确同步。</span><span class="sxs-lookup"><span data-stu-id="5a48f-143">Verify that EOP is synchronizing correctly.</span></span> <span data-ttu-id="5a48f-144">在 EAC 中, 转到 "**收件人** \> " "**联系人**", 并查看从您的本地环境中正确同步的用户列表。</span><span class="sxs-lookup"><span data-stu-id="5a48f-144">In the EAC, go to **Recipients** \> **Contacts** and view that the list of users was correctly synchronized from your on-premises environment.</span></span> 
    
## <a name="use-the-eac-to-manage-mail-users"></a><span data-ttu-id="5a48f-145">使用 EAC 管理邮件用户</span><span class="sxs-lookup"><span data-stu-id="5a48f-145">Use the EAC to manage mail users</span></span>

<span data-ttu-id="5a48f-146">本节提供有关在 EAC 中直接添加和管理电子邮件用户的信息。</span><span class="sxs-lookup"><span data-stu-id="5a48f-146">This section provides information about adding and managing email users directly in the EAC.</span></span>
  
 <span data-ttu-id="5a48f-147">**开始之前**</span><span class="sxs-lookup"><span data-stu-id="5a48f-147">**Before you begin**</span></span>
  
<span data-ttu-id="5a48f-p111">您必须先获得权限，然后才能执行此过程或多个过程。若要查看所需的权限，请参阅 [EOP 中的功能权限](feature-permissions-in-eop.md)主题中的"用户、联系人和角色组"条目。</span><span class="sxs-lookup"><span data-stu-id="5a48f-p111">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Users, Contacts, and Role Groups" entry in [Feature permissions in EOP](feature-permissions-in-eop.md).</span></span>
  
### <a name="to-add-a-mail-user-in-the-eac"></a><span data-ttu-id="5a48f-150">在 EAC 中添加邮件用户的步骤</span><span class="sxs-lookup"><span data-stu-id="5a48f-150">To add a mail user in the EAC</span></span>

1. <span data-ttu-id="5a48f-151">转到 EAC 中的 "**收件人** \> **联系人**", 然后单击 "**新建 +**", 创建电子邮件用户。</span><span class="sxs-lookup"><span data-stu-id="5a48f-151">Create an email user by going to go to **Recipients** \> **Contacts** in the EAC, and then clicking **New +**.</span></span>
    
2. <span data-ttu-id="5a48f-152">在 "**新建邮件用户**" 页上, 输入用户信息, 包括以下信息:</span><span class="sxs-lookup"><span data-stu-id="5a48f-152">On the **New mail user** page, enter the user's information, including the following:</span></span> 
    
   ****

|<span data-ttu-id="5a48f-153">**邮件用户属性**</span><span class="sxs-lookup"><span data-stu-id="5a48f-153">**Mail user property**</span></span>|<span data-ttu-id="5a48f-154">**说明**</span><span class="sxs-lookup"><span data-stu-id="5a48f-154">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="5a48f-155">\*\*“名字” \*\*、“姓名缩写”\*\*\*\* 和“姓氏”\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="5a48f-155">**First name**, **Initials**, and **Last name**</span></span> <br/> |<span data-ttu-id="5a48f-156">在相应的框中键入用户的全名。</span><span class="sxs-lookup"><span data-stu-id="5a48f-156">Type the user's full name in the appropriate boxes.</span></span>  <br/> |
|<span data-ttu-id="5a48f-157">**显示名称**</span><span class="sxs-lookup"><span data-stu-id="5a48f-157">**Display name**</span></span> <br/> |<span data-ttu-id="5a48f-p112">键入名称，最多 64 个字符。默认情况下，此框将在“名字”\*\*\*\*、“姓名缩写”\*\*\*\* 和“姓氏”\*\*\*\* 框中显示名称（如果有）。显示名称是必填项。</span><span class="sxs-lookup"><span data-stu-id="5a48f-p112">Type a name, using up to 64 characters. By default, this box shows the names in the **First name**, **Initials**, and **Last name** boxes if any. The display name is required.  </span></span><br/> |
|<span data-ttu-id="5a48f-161">**Alias**</span><span class="sxs-lookup"><span data-stu-id="5a48f-161">**Alias**</span></span> <br/> |<span data-ttu-id="5a48f-p113">为用户键入唯一的别名，最多 64 个字符。别名为必填项。</span><span class="sxs-lookup"><span data-stu-id="5a48f-p113">Type a unique alias, using up to 64 characters, for the user. The alias is required.</span></span>  <br/> |
|<span data-ttu-id="5a48f-164">**外部电子邮件地址**</span><span class="sxs-lookup"><span data-stu-id="5a48f-164">**External email address**</span></span> <br/> |<span data-ttu-id="5a48f-165">键入用户的外部电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="5a48f-165">Type the external email address of the user.</span></span>  <br/> |
|<span data-ttu-id="5a48f-166">**用户 ID**</span><span class="sxs-lookup"><span data-stu-id="5a48f-166">**User id**</span></span> <br/> |<span data-ttu-id="5a48f-p114">键入邮件用户将用来登录到服务的名称。用户登录名由 (@) 符号左侧的用户名和右侧的后缀组成。通常，后缀是用户帐户所在域的域名。</span><span class="sxs-lookup"><span data-stu-id="5a48f-p114">Type the name that the mail user will use to sign in to the service. The user sign-in name consists of a user name on the left side of the at (@) symbol and a suffix on the right side. Typically, the suffix is the domain name in which the user account resides.</span></span>  <br/> |
|<span data-ttu-id="5a48f-170">**新密码**</span><span class="sxs-lookup"><span data-stu-id="5a48f-170">**New password**</span></span> <br/> |<span data-ttu-id="5a48f-p115">键入邮件用户将用来登录到服务的密码。请确保所提供的密码符合在其中创建用户帐户的域的密码长度、复杂程度和历史要求。</span><span class="sxs-lookup"><span data-stu-id="5a48f-p115">Type the password that the mail user will use to sign in to the service. Make sure that the password you supply complies with the password length, complexity, and history requirements of the domain in which you're creating the user account.</span></span>  <br/> |
|<span data-ttu-id="5a48f-173">**确认密码**</span><span class="sxs-lookup"><span data-stu-id="5a48f-173">**Confirm password**</span></span> <br/> |<span data-ttu-id="5a48f-174">重新键入密码进行确认。</span><span class="sxs-lookup"><span data-stu-id="5a48f-174">Retype the password to confirm it.</span></span>  <br/> |
   
3. <span data-ttu-id="5a48f-p116">单击“保存”\*\*\*\* 创建新电子邮件用户。新用户应显示在用户列表中。</span><span class="sxs-lookup"><span data-stu-id="5a48f-p116">Click **Save** to create the new email user. The new user should appear in the list of users.</span></span> 
    
### <a name="to-edit-or-remove-a-mail-user-in-the-eac"></a><span data-ttu-id="5a48f-177">在 EAC 中编辑或删除邮件用户的步骤</span><span class="sxs-lookup"><span data-stu-id="5a48f-177">To edit or remove a mail user in the EAC</span></span>

- <span data-ttu-id="5a48f-178">在 EAC 中, 转到 "**收件人** \> " "**联系人**"。</span><span class="sxs-lookup"><span data-stu-id="5a48f-178">In the EAC, go to **Recipients** \> **Contacts**.</span></span> <span data-ttu-id="5a48f-179">在用户列表中, 单击要查看或更改的用户, 然后选择 "**编辑** ![编辑" 图标](../media/ITPro-EAC-EditIcon.gif)以根据需要更新用户设置。</span><span class="sxs-lookup"><span data-stu-id="5a48f-179">In the list of users, click the user that you want to view or change, and then select **Edit** ![Edit icon](../media/ITPro-EAC-EditIcon.gif) to update the user settings as needed.</span></span> <span data-ttu-id="5a48f-180">您可以更改用户名、别名或联系人信息，还可以记录有关组织中的用户角色的详细信息。</span><span class="sxs-lookup"><span data-stu-id="5a48f-180">You can change the user's name, alias, or contact information, and you can record detailed information about the user's role in the organization.</span></span> <span data-ttu-id="5a48f-181">您还可以选择用户, 然后选择 "**删除**![删除"](../media/ITPro-EAC-RemoveIcon.gif)图标将其删除。</span><span class="sxs-lookup"><span data-stu-id="5a48f-181">You can also select a user and then choose **Remove**![Remove icon](../media/ITPro-EAC-RemoveIcon.gif) to delete it.</span></span> 
    
## <a name="use-remote-windows-powershell-to-manage-mail-users"></a><span data-ttu-id="5a48f-182">使用远程 Windows PowerShell 管理邮件用户</span><span class="sxs-lookup"><span data-stu-id="5a48f-182">Use remote Windows PowerShell to manage mail users</span></span>

<span data-ttu-id="5a48f-183">本部分提供了有关使用远程 Windows PowerShell 添加和管理邮件用户的信息。</span><span class="sxs-lookup"><span data-stu-id="5a48f-183">This section provides information about adding and managing mail users by using remote Windows PowerShell.</span></span>
  
 <span data-ttu-id="5a48f-184">**开始之前**</span><span class="sxs-lookup"><span data-stu-id="5a48f-184">**Before you begin**</span></span>
  
- <span data-ttu-id="5a48f-p118">您必须先获得权限，然后才能执行此过程或多个过程。若要查看所需的权限，请参阅 [EOP 中的功能权限](feature-permissions-in-eop.md)主题中的"用户、联系人和角色组"条目。</span><span class="sxs-lookup"><span data-stu-id="5a48f-p118">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Users, Contacts, and Role Groups" entry in [Feature permissions in EOP](feature-permissions-in-eop.md).</span></span>
    
- <span data-ttu-id="5a48f-187">请注意，在使用远程 PowerShell cmdlet 创建邮件用户时，您可能会遇到限制。</span><span class="sxs-lookup"><span data-stu-id="5a48f-187">Be aware that when creating mail users by using remote PowerShell cmdlets, you may encounter throttling.</span></span>
    
- <span data-ttu-id="5a48f-188">此 cmdlet 使用批处理方法，在显示 cmdlet 结果之前，有几分钟的传播延迟。</span><span class="sxs-lookup"><span data-stu-id="5a48f-188">This cmdlet uses a batch processing method that results in a propagation delay of a few minutes before the results of the cmdlet are visible.</span></span>
    
- <span data-ttu-id="5a48f-189">要了解如何使用 Windows PowerShell 连接到 Exchange Online Protection，请参阅[使用远程 PowerShell 连接到 Exchange Online Protection](http://technet.microsoft.com/library/054e0fd7-d465-4572-93f8-a00a9136e4d1.aspx)。</span><span class="sxs-lookup"><span data-stu-id="5a48f-189">To learn how to use Windows PowerShell to connect to Exchange Online Protection, see [Connect to Exchange Online Protection Using Remote PowerShell](http://technet.microsoft.com/library/054e0fd7-d465-4572-93f8-a00a9136e4d1.aspx).</span></span>
    
 <span data-ttu-id="5a48f-190">**使用远程 PowerShell 添加邮件用户**</span><span class="sxs-lookup"><span data-stu-id="5a48f-190">**To add a mail user using remote PowerShell**</span></span>
  
<span data-ttu-id="5a48f-191">此示例使用 [New-EOPMailUser](http://technet.microsoft.com/library/0520cf33-4ad0-44e4-99a3-1b485739fc05.aspx) cmdlet 在 EOP 内为 Jeffrey Zeng 创建了一个启用邮件功能的用户帐户，详细信息如下：</span><span class="sxs-lookup"><span data-stu-id="5a48f-191">This example uses the [New-EOPMailUser](http://technet.microsoft.com/library/0520cf33-4ad0-44e4-99a3-1b485739fc05.aspx) cmdlet to create a mail-enabled user account for Jeffrey Zeng in EOP with the following details:</span></span> 
  
- <span data-ttu-id="5a48f-192">名是 Jeffrey，姓是 Zeng。</span><span class="sxs-lookup"><span data-stu-id="5a48f-192">The first name is Jeffrey and the last name is Zeng.</span></span>
    
- <span data-ttu-id="5a48f-193">名字是 Jeffrey，显示名称是 Jeffrey Zeng。</span><span class="sxs-lookup"><span data-stu-id="5a48f-193">The name is Jeffrey and the display name is Jeffrey Zeng.</span></span>
    
- <span data-ttu-id="5a48f-194">别名是 jeffreyz。</span><span class="sxs-lookup"><span data-stu-id="5a48f-194">The alias is jeffreyz.</span></span>
    
- <span data-ttu-id="5a48f-195">外部电子邮件地址是 jzeng@tailspintoys.com。</span><span class="sxs-lookup"><span data-stu-id="5a48f-195">The external email address is jzeng@tailspintoys.com.</span></span>
    
- <span data-ttu-id="5a48f-196">Office 365 登录名为 jeffreyz@contoso.onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="5a48f-196">The Office 365 sign in name is jeffreyz@contoso.onmicrosoft.com.</span></span>
    
- <span data-ttu-id="5a48f-197">密码为 Pa$$word1。</span><span class="sxs-lookup"><span data-stu-id="5a48f-197">The password is Pa$$word1.</span></span>
    
```Powershell
New-EOPMailUser -LastName Zeng -FirstName Jeffrey -DisplayName "Jeffrey Zeng" -Name Jeffrey -Alias jeffreyz -MicrosoftOnlineServicesID jeffreyz@contoso.onmicrosoft.com -ExternalEmailAddress jeffreyz@tailspintoys.com -Password (ConvertTo-SecureString -String 'Pa$$word1' -AsPlainText -Force)
```

 <span data-ttu-id="5a48f-198">**验证此操作已生效**</span><span class="sxs-lookup"><span data-stu-id="5a48f-198">**To verify that this worked**</span></span>
  
<span data-ttu-id="5a48f-199">运行 [Get-User](http://technet.microsoft.com/library/2a33c9e6-33da-438c-912d-28ce3f4c9afb.aspx) cmdlet，如下所示，以显示有关新邮件用户 Jeffrey Zeng 的信息：</span><span class="sxs-lookup"><span data-stu-id="5a48f-199">Run the [Get-User](http://technet.microsoft.com/library/2a33c9e6-33da-438c-912d-28ce3f4c9afb.aspx) cmdlet as follows to display information about new mail user Jeffrey Zeng:</span></span> 
  
```Powershell
Get-User "Jeffrey Zeng"

```

 <span data-ttu-id="5a48f-200">**若要使用远程 PowerShell 编辑邮件用户的属性**</span><span class="sxs-lookup"><span data-stu-id="5a48f-200">**To edit the properties of a mail user using remote PowerShell**</span></span>
  
<span data-ttu-id="5a48f-201">使用 [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) 和 [Set-EOPMailUser](http://technet.microsoft.com/library/834c3de6-1485-4d50-bb96-262a2c0c8619.aspx) cmdlet 查看或更改邮件用户的属性。</span><span class="sxs-lookup"><span data-stu-id="5a48f-201">Use the [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) and [Set-EOPMailUser](http://technet.microsoft.com/library/834c3de6-1485-4d50-bb96-262a2c0c8619.aspx) cmdlets to view or change properties for mail users.</span></span> 
  
<span data-ttu-id="5a48f-202">此示例将设置 Pilar Pinilla 的外部电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="5a48f-202">This example sets the external email address for Pilar Pinilla.</span></span>
  
```Powershell
Set-EOPMailUser -Identity "Pilar Pinilla" -EmailAddresses pilarp@tailspintoys.com
```

<span data-ttu-id="5a48f-203">此示例将所有邮件用户的“公司”属性设置为 Contoso。</span><span class="sxs-lookup"><span data-stu-id="5a48f-203">This example sets the Company property for all mail users to Contoso.</span></span>
  
```Powershell
$Recip = Get-Recipient -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'mailuser')}
$Recip | foreach {Set-EOPUser -Identity $_.Alias -Company Contoso}

```

 <span data-ttu-id="5a48f-204">**验证此操作已生效**</span><span class="sxs-lookup"><span data-stu-id="5a48f-204">**To verify that this worked**</span></span>
  
<span data-ttu-id="5a48f-p119">在之前的示例中，我们已经为邮件用户 Pilar Pinella 更改了属性，还可以使用 [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) cmdlet 来验证这些更改。（请注意，您可以查看多个邮件联系人的多个属性。）</span><span class="sxs-lookup"><span data-stu-id="5a48f-p119">In the previous example where we changed the properties for mail user Pilar Pinella, use the [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) cmdlet to verify the changes. (Note that you can view multiple properties for multiple mail contacts.)</span></span> 
  
```Powershell
Get-Recipient -Identity "Pilar Pinilla" | Format-List 

```

<span data-ttu-id="5a48f-207">在之前的示例中，所有邮件用户的"公司"属性都设置为 Contoso，请运行以下命令验证更改：</span><span class="sxs-lookup"><span data-stu-id="5a48f-207">In the previous example where the Company property was set to Contoso for all mail users, run the following command to verify the changes:</span></span>
  
```Powershell
Get-Recipient -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'mailuser')} | Format-List Name,Company
```

> [!IMPORTANT]
> <span data-ttu-id="5a48f-208">此 cmdlet 使用批处理方法，在显示 cmdlet 结果之前，有几分钟的传播延迟。</span><span class="sxs-lookup"><span data-stu-id="5a48f-208">This cmdlet uses a batch processing method that results in a propagation delay of a few minutes before the results of the cmdlet are visible.</span></span> 
  
 <span data-ttu-id="5a48f-209">**使用远程 PowerShell 删除邮件用户**</span><span class="sxs-lookup"><span data-stu-id="5a48f-209">**To remove a mail user using remote PowerShell**</span></span>
  
<span data-ttu-id="5a48f-210">此示例使用 [Remove-EOPMailUser](http://technet.microsoft.com/library/cb91dc26-ed22-4d3c-9f64-df9df1754edb.aspx) cmdlet 删除用户 Jeffrey Zeng：</span><span class="sxs-lookup"><span data-stu-id="5a48f-210">This example uses the [Remove-EOPMailUser](http://technet.microsoft.com/library/cb91dc26-ed22-4d3c-9f64-df9df1754edb.aspx) cmdlet to delete user Jeffrey Zeng:</span></span> 
  
```Powershell
Remove-EOPMailUser -Identity Jeffrey
```

 <span data-ttu-id="5a48f-211">**验证此操作已生效**</span><span class="sxs-lookup"><span data-stu-id="5a48f-211">**To verify that this worked**</span></span>
  
<span data-ttu-id="5a48f-p120">如下所述运行 [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) cmdlet：因为该用户已不存在，所以您应该会收到错误邮件。</span><span class="sxs-lookup"><span data-stu-id="5a48f-p120">Run the [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) cmdlet as follows. You should get an error message since the user no longer exists.</span></span> 
  
```Powershell
Get-Recipient Jeffrey | fl
```


