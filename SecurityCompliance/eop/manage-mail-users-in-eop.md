---
title: 在 EOP 中管理邮件用户
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/9/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 4bfaf2ab-e633-4227-8bde-effefb41a3db
description: 定义邮件用户是管理 Exchange Online Protection (EOP) 服务的重要部分。
ms.openlocfilehash: e985adf5659b50cf567ea798a092f809d77ca470
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2018
ms.locfileid: "22027389"
---
# <a name="manage-mail-users-in-eop"></a><span data-ttu-id="7d6f2-103">在 EOP 中管理邮件用户</span><span class="sxs-lookup"><span data-stu-id="7d6f2-103">Manage mail users in EOP</span></span>

<span data-ttu-id="7d6f2-p101">定义邮件用户是管理 Exchange Online Protection (EOP) 服务的重要部分。在 EOP 中，您可以使用多种方法来管理用户：</span><span class="sxs-lookup"><span data-stu-id="7d6f2-p101">Defining mail users is an important part of managing the Exchange Online Protection (EOP) service. There are several ways that you can manage users in EOP:</span></span>
  
- <span data-ttu-id="7d6f2-p102">使用目录同步管理邮件用户： 如果您的公司具有内部部署 Active Directory 环境中的现有用户帐户，则可以同步到 Azure Active Directory (AD)，其中一份帐户存储在云中这些帐户。在同步到 Azure Active Directory 现有用户帐户时，您可以在 Exchange 管理员中心 (EAC) 的**收件人**窗格中查看这些用户。建议使用目录同步。</span><span class="sxs-lookup"><span data-stu-id="7d6f2-p102">Use directory synchronization to manage mail users: If your company has existing user accounts in an on-premises Active Directory environment, you can synchronize those accounts to Azure Active Directory (AD), where a copy of the accounts is stored in the cloud. When you synchronize your existing user accounts to Azure Active Directory, you can view those users in the **Recipients** pane of the Exchange admin center (EAC). Using directory synchronization is recommended.</span></span> 
    
- <span data-ttu-id="7d6f2-p103">使用 EAC 管理邮件用户：在 EAC 中直接添加和管理邮件用户。这是添加邮件用户最简单的方式，并且对于一次添加一个用户非常有用。</span><span class="sxs-lookup"><span data-stu-id="7d6f2-p103">Use the EAC to manage mail users: Add and manage mail users directly in the EAC. This is the easiest way to add mail users and is useful for adding one user at a time.</span></span>
    
- <span data-ttu-id="7d6f2-p104">使用远程 Windows PowerShell 管理邮件用户：通过运行远程 Windows PowerShell 添加和管理邮件用户。此方法可用于添加多个记录并创建脚本。</span><span class="sxs-lookup"><span data-stu-id="7d6f2-p104">Use remote Windows PowerShell to manage mail users: Add and manage mail users by running remote Windows PowerShell. This method is useful for adding multiple records and creating scripts.</span></span>
    
> [!NOTE]
> <span data-ttu-id="7d6f2-113">可以在 Office 365 管理中心添加用户，但是，这些用户不能用作邮件收件人。</span><span class="sxs-lookup"><span data-stu-id="7d6f2-113">You can add users in the Office 365 admin center, however these users can't be used as mail recipients.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="7d6f2-114">开始之前</span><span class="sxs-lookup"><span data-stu-id="7d6f2-114">Before you begin</span></span>

- <span data-ttu-id="7d6f2-p105">本主题中的过程需要特定权限。请参阅每个过程，以了解其权限信息。</span><span class="sxs-lookup"><span data-stu-id="7d6f2-p105">Procedures in this topic require specific permissions. See each procedure for its permissions information.</span></span>
    
- <span data-ttu-id="7d6f2-117">若要了解可能适用于此主题中过程的键盘快捷键，请参阅 **Exchange 管理中心内的键盘快捷键**。</span><span class="sxs-lookup"><span data-stu-id="7d6f2-117">For information about keyboard shortcuts that may apply to the procedures in this topic, see **Keyboard shortcuts in the Exchange admin center**.</span></span>
    
> [!TIP]
> <span data-ttu-id="7d6f2-p106">遇到问题了吗？请在 Exchange 论坛中寻求帮助。 请访问以下论坛：[Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612)、[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542)或 [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351)。</span><span class="sxs-lookup"><span data-stu-id="7d6f2-p106">Having problems? Ask for help in the Exchange forums. Visit the forums at [Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612),[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542), or [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351).</span></span> 
  
## <a name="use-directory-synchronization-to-manage-mail-users"></a><span data-ttu-id="7d6f2-121">使用目录同步管理邮件用户</span><span class="sxs-lookup"><span data-stu-id="7d6f2-121">Use directory synchronization to manage mail users</span></span>

<span data-ttu-id="7d6f2-122">本节提供了有关使用目录同步管理电子邮件用户的信息。</span><span class="sxs-lookup"><span data-stu-id="7d6f2-122">This section provides information about managing email users by using directory synchronization.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="7d6f2-p107">如果您使用目录同步来管理收件人，那么您仍然可以在 Office 365 管理中心中添加和管理用户，但是他们无法与您的本地 Active Directory 同步。这是因为目录同步只能将来自本地 Active Directory 的收件人同步到云。</span><span class="sxs-lookup"><span data-stu-id="7d6f2-p107">If you use directory synchronization to manage your recipients, you can still add and manage users in the Office 365 admin center, but they will not be synchronized with your on-premises Active Directory. This is because directory synchronization only syncs recipients from your on-premises Active Directory to the cloud.</span></span> 
  
> [!TIP]
>  <span data-ttu-id="7d6f2-p108">建议使用目录同步用于以下功能： > **Outlook 安全发件人和阻止发件人列表**-同步到服务时，这些列表将优先于垃圾邮件筛选服务中。这允许用户管理其自己的安全发件人和阻止发件人列表基于每个用户或每个域。>**目录基于边缘阻止 (DBEB)** -有关 DBEB 的详细信息，请参阅[使用 Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](http://technet.microsoft.com/library/ca7b7416-92ed-40ad-abdb-695be46ea2e4.aspx)。>**最终用户垃圾邮件隔离**-以访问最终用户垃圾邮件隔离，最终用户必须具有有效的 Office 365 用户 ID 和密码。保护内部部署邮箱的 EOP 客户必须是有效的电子邮件用户。>**传输规则**-时使用目录同步，您现有的 Active Directory 用户和组自动上载到云，然后可以创建面向特定用户和/或组，而不必的传输规则手动将其添加通过 EAC 或远程 Windows PowerShell。请注意，不能通过目录同步同步该[动态通讯组](https://go.microsoft.com/fwlink/?LinkId=507569)。</span><span class="sxs-lookup"><span data-stu-id="7d6f2-p108">Using directory synchronization is recommended for use with the following features: > **Outlook safe sender and blocked sender lists** - When synchronized to the service, these lists will take precedence over spam filtering in the service. This lets users manage their own safe sender and blocked sender lists on a per-user or per-domain basis. > **Directory Based Edge Blocking (DBEB)** - For more information about DBEB, see [Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](http://technet.microsoft.com/library/ca7b7416-92ed-40ad-abdb-695be46ea2e4.aspx). > **End user spam quarantine** - In order to access the end user spam quarantine, end users must have a valid Office 365 user ID and password. EOP customers protecting on-premises mailboxes must be valid email users. > **Transport rules** - When you use directory synchronization, your existing Active Directory users and groups are automatically uploaded to the cloud, and you can then create Transport rules that target specific users and/or groups without having to manually add them via the EAC or remote Windows PowerShell. Note that [dynamic distribution groups](https://go.microsoft.com/fwlink/?LinkId=507569) can't be synchronized via directory synchronization.</span></span> 
  
 <span data-ttu-id="7d6f2-132">**开始之前**</span><span class="sxs-lookup"><span data-stu-id="7d6f2-132">**Before you begin**</span></span>
  
<span data-ttu-id="7d6f2-133">按[准备进行目录同步](https://go.microsoft.com/fwlink/p/?LinkId=308908)中所述，获取所需权限，并准备进行目录同步。</span><span class="sxs-lookup"><span data-stu-id="7d6f2-133">Get the necessary permissions and prepare for directory synchronization, as described in [Prepare for directory synchronization](https://go.microsoft.com/fwlink/p/?LinkId=308908).</span></span>
  
### <a name="to-synchronize-user-directories"></a><span data-ttu-id="7d6f2-134">同步用户目录的步骤</span><span class="sxs-lookup"><span data-stu-id="7d6f2-134">To synchronize user directories</span></span>

1. <span data-ttu-id="7d6f2-135">按[激活目录同步](https://go.microsoft.com/fwlink/p/?LinkId=308909)中所述，激活目录同步。</span><span class="sxs-lookup"><span data-stu-id="7d6f2-135">Activate directory synchronization, as described in [Activate directory synchronization](https://go.microsoft.com/fwlink/p/?LinkId=308909).</span></span>
    
2. <span data-ttu-id="7d6f2-136">按[设置目录同步计算机](http://go.microsoft.com/fwlink/p/?LinkId=308911)中所述，设置您的目录同步计算机。</span><span class="sxs-lookup"><span data-stu-id="7d6f2-136">Set up your directory synchronization computer, as described in [Set up your directory sync computer](http://go.microsoft.com/fwlink/p/?LinkId=308911).</span></span>
    
3. <span data-ttu-id="7d6f2-137">按[使用配置向导同步目录](http://go.microsoft.com/fwlink/?LinkId=308912)中所述，同步目录。</span><span class="sxs-lookup"><span data-stu-id="7d6f2-137">Synchronize your directories, as described in [Use the Configuration Wizard to sync your directories](http://go.microsoft.com/fwlink/?LinkId=308912).</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="7d6f2-p109">Azure Active Directory 同步工具配置向导后，在您的 Active Directory 林中创建**MSOL_AD_SYNC**帐户。此帐户用于读取和同步的本地 Active Directory 信息。为了目录同步正常工作，请确保该 TCP 443 上本地目录同步服务器已打开。</span><span class="sxs-lookup"><span data-stu-id="7d6f2-p109">When you finish the Azure Active Directory Sync Tool Configuration Wizard, the **MSOL_AD_SYNC** account is created in your Active Directory forest. This account is used to read and synchronize your on-premises Active Directory information. In order for directory synchronization to work correctly, make sure that TCP 443 on your local directory synchronization server is open.</span></span> 
  
4. <span data-ttu-id="7d6f2-141">按[激活同步用户](http://go.microsoft.com/fwlink/p/?LinkId=308913)中所述，激活同步用户。</span><span class="sxs-lookup"><span data-stu-id="7d6f2-141">Activate synced users, as described in [Activate synced users](http://go.microsoft.com/fwlink/p/?LinkId=308913).</span></span>
    
5. <span data-ttu-id="7d6f2-142">按[管理目录同步](http://go.microsoft.com/fwlink/p/?LinkId=308915)中所述，管理目录同步。</span><span class="sxs-lookup"><span data-stu-id="7d6f2-142">Manage directory synchronization, as described in [Manage directory synchronization](http://go.microsoft.com/fwlink/p/?LinkId=308915).</span></span>
    
6. <span data-ttu-id="7d6f2-p110">验证已正确同步 EOP。在 EAC 中，转到**收件人** \> **联系人**和用户列表已正确同步内部部署环境中的视图。</span><span class="sxs-lookup"><span data-stu-id="7d6f2-p110">Verify that EOP is synchronizing correctly. In the EAC, go to **Recipients** \> **Contacts** and view that the list of users was correctly synchronized from your on-premises environment.</span></span> 
    
## <a name="use-the-eac-to-manage-mail-users"></a><span data-ttu-id="7d6f2-145">使用 EAC 管理邮件用户</span><span class="sxs-lookup"><span data-stu-id="7d6f2-145">Use the EAC to manage mail users</span></span>

<span data-ttu-id="7d6f2-146">本节提供有关在 EAC 中直接添加和管理电子邮件用户的信息。</span><span class="sxs-lookup"><span data-stu-id="7d6f2-146">This section provides information about adding and managing email users directly in the EAC.</span></span>
  
 <span data-ttu-id="7d6f2-147">**开始之前**</span><span class="sxs-lookup"><span data-stu-id="7d6f2-147">**Before you begin**</span></span>
  
<span data-ttu-id="7d6f2-p111">您必须先获得权限，然后才能执行此过程或多个过程。若要查看所需的权限，请参阅 [EOP 中的功能权限](feature-permissions-in-eop.md)主题中的"用户、联系人和角色组"条目。</span><span class="sxs-lookup"><span data-stu-id="7d6f2-p111">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Users, Contacts, and Role Groups" entry in [Feature permissions in EOP](feature-permissions-in-eop.md).</span></span>
  
### <a name="to-add-a-mail-user-in-the-eac"></a><span data-ttu-id="7d6f2-150">在 EAC 中添加邮件用户的步骤</span><span class="sxs-lookup"><span data-stu-id="7d6f2-150">To add a mail user in the EAC</span></span>

1. <span data-ttu-id="7d6f2-151">创建电子邮件用户转到**收件人** \> **联系人**中的 EAC 中，和然后单击**新建 +**。</span><span class="sxs-lookup"><span data-stu-id="7d6f2-151">Create an email user by going to go to **Recipients** \> **Contacts** in the EAC, and then clicking **New +**.</span></span>
    
2. <span data-ttu-id="7d6f2-152">在**新邮件用户**页上，输入用户的信息，其中包括：</span><span class="sxs-lookup"><span data-stu-id="7d6f2-152">On the **New mail user** page, enter the user's information, including the following:</span></span> 
    
   ****

|<span data-ttu-id="7d6f2-153">**邮件用户属性**</span><span class="sxs-lookup"><span data-stu-id="7d6f2-153">**Mail user property**</span></span>|<span data-ttu-id="7d6f2-154">**说明**</span><span class="sxs-lookup"><span data-stu-id="7d6f2-154">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="7d6f2-155">**名字**、**缩写**和**姓氏**</span><span class="sxs-lookup"><span data-stu-id="7d6f2-155">**First name**, **Initials**, and **Last name**</span></span> <br/> |<span data-ttu-id="7d6f2-156">在相应的框中键入用户的全名。</span><span class="sxs-lookup"><span data-stu-id="7d6f2-156">Type the user's full name in the appropriate boxes.</span></span>  <br/> |
|<span data-ttu-id="7d6f2-157">**显示名**</span><span class="sxs-lookup"><span data-stu-id="7d6f2-157">**Display name**</span></span> <br/> |<span data-ttu-id="7d6f2-p112">键入一个名称，使用最多为 64 个字符。默认情况下，此框显示在**名字**、**缩写**和**姓氏**框如果任何名称。所需的显示名称。</span><span class="sxs-lookup"><span data-stu-id="7d6f2-p112">Type a name, using up to 64 characters. By default, this box shows the names in the **First name**, **Initials**, and **Last name** boxes if any. The display name is required.  </span></span><br/> |
|<span data-ttu-id="7d6f2-161">**别名**</span><span class="sxs-lookup"><span data-stu-id="7d6f2-161">**Alias**</span></span> <br/> |<span data-ttu-id="7d6f2-p113">为用户键入唯一的别名，最多 64 个字符。别名为必填项。</span><span class="sxs-lookup"><span data-stu-id="7d6f2-p113">Type a unique alias, using up to 64 characters, for the user. The alias is required.</span></span>  <br/> |
|<span data-ttu-id="7d6f2-164">**外部电子邮件地址**</span><span class="sxs-lookup"><span data-stu-id="7d6f2-164">**External email address**</span></span> <br/> |<span data-ttu-id="7d6f2-165">键入用户的外部电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="7d6f2-165">Type the external email address of the user.</span></span>  <br/> |
|<span data-ttu-id="7d6f2-166">**用户 ID**</span><span class="sxs-lookup"><span data-stu-id="7d6f2-166">**User id**</span></span> <br/> |<span data-ttu-id="7d6f2-p114">键入邮件用户将用来登录到服务的名称。用户登录名由 (@) 符号左侧的用户名和右侧的后缀组成。通常，后缀是用户帐户所在域的域名。</span><span class="sxs-lookup"><span data-stu-id="7d6f2-p114">Type the name that the mail user will use to sign in to the service. The user sign-in name consists of a user name on the left side of the at (@) symbol and a suffix on the right side. Typically, the suffix is the domain name in which the user account resides.</span></span>  <br/> |
|<span data-ttu-id="7d6f2-170">**新密码**</span><span class="sxs-lookup"><span data-stu-id="7d6f2-170">**New password**</span></span> <br/> |<span data-ttu-id="7d6f2-p115">键入邮件用户将用来登录到服务的密码。请确保所提供的密码符合在其中创建用户帐户的域的密码长度、复杂程度和历史要求。</span><span class="sxs-lookup"><span data-stu-id="7d6f2-p115">Type the password that the mail user will use to sign in to the service. Make sure that the password you supply complies with the password length, complexity, and history requirements of the domain in which you're creating the user account.</span></span>  <br/> |
|<span data-ttu-id="7d6f2-173">**确认密码**</span><span class="sxs-lookup"><span data-stu-id="7d6f2-173">**Confirm password**</span></span> <br/> |<span data-ttu-id="7d6f2-174">重新键入密码进行确认。</span><span class="sxs-lookup"><span data-stu-id="7d6f2-174">Retype the password to confirm it.</span></span>  <br/> |
   
3. <span data-ttu-id="7d6f2-p116">单击**保存**以创建新的电子邮件用户。新的用户应出现在用户列表。</span><span class="sxs-lookup"><span data-stu-id="7d6f2-p116">Click **Save** to create the new email user. The new user should appear in the list of users.</span></span> 
    
### <a name="to-edit-or-remove-a-mail-user-in-the-eac"></a><span data-ttu-id="7d6f2-177">在 EAC 中编辑或删除邮件用户的步骤</span><span class="sxs-lookup"><span data-stu-id="7d6f2-177">To edit or remove a mail user in the EAC</span></span>

- <span data-ttu-id="7d6f2-p117">在 EAC 中，转到**收件人** \> **联系人**。在用户列表中，单击您想要查看或更改的用户，然后选择**编辑**![编辑图标](../media/ITPro-EAC-EditIcon.png)以根据需要更新的用户设置。您可以更改用户的名称、 别名或联系人信息，并且您可以在组织中记录有关用户的角色的详细的信息。您可以选择一名用户，然后选择**删除**![删除图标](../media/ITPro-EAC-RemoveIcon.png)删除它。</span><span class="sxs-lookup"><span data-stu-id="7d6f2-p117">In the EAC, go to **Recipients** \> **Contacts**. In the list of users, click the user that you want to view or change, and then select **Edit**![Edit icon](../media/ITPro-EAC-EditIcon.png) to update the user settings as needed. You can change the user's name, alias, or contact information, and you can record detailed information about the user's role in the organization. You can also select a user and then choose **Remove**![Remove icon](../media/ITPro-EAC-RemoveIcon.png) to delete it.</span></span> 
    
## <a name="use-remote-windows-powershell-to-manage-mail-users"></a><span data-ttu-id="7d6f2-182">使用远程 Windows PowerShell 管理邮件用户</span><span class="sxs-lookup"><span data-stu-id="7d6f2-182">Use remote Windows PowerShell to manage mail users</span></span>

<span data-ttu-id="7d6f2-183">本部分提供了有关使用远程 Windows PowerShell 添加和管理邮件用户的信息。</span><span class="sxs-lookup"><span data-stu-id="7d6f2-183">This section provides information about adding and managing mail users by using remote Windows PowerShell.</span></span>
  
 <span data-ttu-id="7d6f2-184">**开始之前**</span><span class="sxs-lookup"><span data-stu-id="7d6f2-184">**Before you begin**</span></span>
  
- <span data-ttu-id="7d6f2-p118">您必须先获得权限，然后才能执行此过程或多个过程。若要查看所需的权限，请参阅 [EOP 中的功能权限](feature-permissions-in-eop.md)主题中的"用户、联系人和角色组"条目。</span><span class="sxs-lookup"><span data-stu-id="7d6f2-p118">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Users, Contacts, and Role Groups" entry in [Feature permissions in EOP](feature-permissions-in-eop.md).</span></span>
    
- <span data-ttu-id="7d6f2-187">请注意，在使用远程 PowerShell cmdlet 创建邮件用户时，您可能会遇到限制。</span><span class="sxs-lookup"><span data-stu-id="7d6f2-187">Be aware that when creating mail users by using remote PowerShell cmdlets, you may encounter throttling.</span></span>
    
- <span data-ttu-id="7d6f2-188">此 cmdlet 使用批处理方法，在显示 cmdlet 结果之前，有几分钟的传播延迟。</span><span class="sxs-lookup"><span data-stu-id="7d6f2-188">This cmdlet uses a batch processing method that results in a propagation delay of a few minutes before the results of the cmdlet are visible.</span></span>
    
- <span data-ttu-id="7d6f2-189">要了解如何使用 Windows PowerShell 连接到 Exchange Online Protection，请参阅[使用远程 PowerShell 连接到 Exchange Online Protection](http://technet.microsoft.com/library/054e0fd7-d465-4572-93f8-a00a9136e4d1.aspx)。</span><span class="sxs-lookup"><span data-stu-id="7d6f2-189">To learn how to use Windows PowerShell to connect to Exchange Online Protection, see [Connect to Exchange Online Protection Using Remote PowerShell](http://technet.microsoft.com/library/054e0fd7-d465-4572-93f8-a00a9136e4d1.aspx).</span></span>
    
 <span data-ttu-id="7d6f2-190">**使用远程 PowerShell 添加邮件用户**</span><span class="sxs-lookup"><span data-stu-id="7d6f2-190">**To add a mail user using remote PowerShell**</span></span>
  
<span data-ttu-id="7d6f2-191">此示例使用 [New-EOPMailUser](http://technet.microsoft.com/library/0520cf33-4ad0-44e4-99a3-1b485739fc05.aspx) cmdlet 在 EOP 内为 Jeffrey Zeng 创建了一个启用邮件功能的用户帐户，详细信息如下：</span><span class="sxs-lookup"><span data-stu-id="7d6f2-191">This example uses the [New-EOPMailUser](http://technet.microsoft.com/library/0520cf33-4ad0-44e4-99a3-1b485739fc05.aspx) cmdlet to create a mail-enabled user account for Jeffrey Zeng in EOP with the following details:</span></span> 
  
- <span data-ttu-id="7d6f2-192">名是 Jeffrey，姓是 Zeng。</span><span class="sxs-lookup"><span data-stu-id="7d6f2-192">The first name is Jeffrey and the last name is Zeng.</span></span>
    
- <span data-ttu-id="7d6f2-193">名字是 Jeffrey，显示名称是 Jeffrey Zeng。</span><span class="sxs-lookup"><span data-stu-id="7d6f2-193">The name is Jeffrey and the display name is Jeffrey Zeng.</span></span>
    
- <span data-ttu-id="7d6f2-194">别名是 jeffreyz。</span><span class="sxs-lookup"><span data-stu-id="7d6f2-194">The alias is jeffreyz.</span></span>
    
- <span data-ttu-id="7d6f2-195">外部电子邮件地址是 jzeng@tailspintoys.com。</span><span class="sxs-lookup"><span data-stu-id="7d6f2-195">The external email address is jzeng@tailspintoys.com.</span></span>
    
- <span data-ttu-id="7d6f2-196">Office 365 登录名为 jeffreyz@contoso.onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="7d6f2-196">The Office 365 sign in name is jeffreyz@contoso.onmicrosoft.com.</span></span>
    
- <span data-ttu-id="7d6f2-197">密码为 Pa$$word1。</span><span class="sxs-lookup"><span data-stu-id="7d6f2-197">The password is Pa$$word1.</span></span>
    
```
New-EOPMailUser -LastName Zeng -FirstName Jeffrey -DisplayName "Jeffrey Zeng" -Name Jeffrey -Alias jeffreyz -MicrosoftOnlineServicesID jeffreyz@contoso.onmicrosoft.com -ExternalEmailAddress jeffreyz@tailspintoys.com -Password (ConvertTo-SecureString -String 'Pa$$word1' -AsPlainText -Force)
```

 <span data-ttu-id="7d6f2-198">**验证此操作已生效**</span><span class="sxs-lookup"><span data-stu-id="7d6f2-198">**To verify that this worked**</span></span>
  
<span data-ttu-id="7d6f2-199">运行 [Get-User](http://technet.microsoft.com/library/2a33c9e6-33da-438c-912d-28ce3f4c9afb.aspx) cmdlet，如下所示，以显示有关新邮件用户 Jeffrey Zeng 的信息：</span><span class="sxs-lookup"><span data-stu-id="7d6f2-199">Run the [Get-User](http://technet.microsoft.com/library/2a33c9e6-33da-438c-912d-28ce3f4c9afb.aspx) cmdlet as follows to display information about new mail user Jeffrey Zeng:</span></span> 
  
```
Get-User "Jeffrey Zeng"

```

 <span data-ttu-id="7d6f2-200">**若要使用远程 PowerShell 编辑邮件用户的属性**</span><span class="sxs-lookup"><span data-stu-id="7d6f2-200">**To edit the properties of a mail user using remote PowerShell**</span></span>
  
<span data-ttu-id="7d6f2-201">使用 [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) 和 [Set-EOPMailUser](http://technet.microsoft.com/library/834c3de6-1485-4d50-bb96-262a2c0c8619.aspx) cmdlet 查看或更改邮件用户的属性。</span><span class="sxs-lookup"><span data-stu-id="7d6f2-201">Use the [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) and [Set-EOPMailUser](http://technet.microsoft.com/library/834c3de6-1485-4d50-bb96-262a2c0c8619.aspx) cmdlets to view or change properties for mail users.</span></span> 
  
<span data-ttu-id="7d6f2-202">此示例将设置 Pilar Pinilla 的外部电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="7d6f2-202">This example sets the external email address for Pilar Pinilla.</span></span>
  
```
Set-EOPMailUser -Identity "Pilar Pinilla" -EmailAddresses pilarp@tailspintoys.com
```

<span data-ttu-id="7d6f2-203">此示例将所有邮件用户的"公司"属性设置为 Contoso。</span><span class="sxs-lookup"><span data-stu-id="7d6f2-203">This example sets the Company property for all mail users to Contoso.</span></span>
  
```
$Recip = Get-Recipient -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'mailuser')}
$Recip | foreach {Set-EOPUser -Identity $_.Alias -Company Contoso}

```

 <span data-ttu-id="7d6f2-204">**验证此操作已生效**</span><span class="sxs-lookup"><span data-stu-id="7d6f2-204">**To verify that this worked**</span></span>
  
<span data-ttu-id="7d6f2-p119">在之前的示例中，我们已经为邮件用户 Pilar Pinella 更改了属性，还可以使用 [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) cmdlet 来验证这些更改。（请注意，您可以查看多个邮件联系人的多个属性。）</span><span class="sxs-lookup"><span data-stu-id="7d6f2-p119">In the previous example where we changed the properties for mail user Pilar Pinella, use the [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) cmdlet to verify the changes. (Note that you can view multiple properties for multiple mail contacts.)</span></span> 
  
```
Get-Recipient -Identity "Pilar Pinilla" | Format-List 

```

<span data-ttu-id="7d6f2-207">在之前的示例中，所有邮件用户的"公司"属性都设置为 Contoso，请运行以下命令验证更改：</span><span class="sxs-lookup"><span data-stu-id="7d6f2-207">In the previous example where the Company property was set to Contoso for all mail users, run the following command to verify the changes:</span></span>
  
```
Get-Recipient -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'mailuser')} | Format-List Name,Company
```

> [!IMPORTANT]
> <span data-ttu-id="7d6f2-208">此 cmdlet 使用批处理方法，在显示 cmdlet 结果之前，有几分钟的传播延迟。</span><span class="sxs-lookup"><span data-stu-id="7d6f2-208">This cmdlet uses a batch processing method that results in a propagation delay of a few minutes before the results of the cmdlet are visible.</span></span> 
  
 <span data-ttu-id="7d6f2-209">**使用远程 PowerShell 删除邮件用户**</span><span class="sxs-lookup"><span data-stu-id="7d6f2-209">**To remove a mail user using remote PowerShell**</span></span>
  
<span data-ttu-id="7d6f2-210">此示例使用 [Remove-EOPMailUser](http://technet.microsoft.com/library/cb91dc26-ed22-4d3c-9f64-df9df1754edb.aspx) cmdlet 删除用户 Jeffrey Zeng：</span><span class="sxs-lookup"><span data-stu-id="7d6f2-210">This example uses the [Remove-EOPMailUser](http://technet.microsoft.com/library/cb91dc26-ed22-4d3c-9f64-df9df1754edb.aspx) cmdlet to delete user Jeffrey Zeng:</span></span> 
  
```
Remove-EOPMailUser -Identity Jeffrey
```

 <span data-ttu-id="7d6f2-211">**验证此操作已生效**</span><span class="sxs-lookup"><span data-stu-id="7d6f2-211">**To verify that this worked**</span></span>
  
<span data-ttu-id="7d6f2-p120">如下所述运行 [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) cmdlet：因为该用户已不存在，所以您应该会收到错误邮件。</span><span class="sxs-lookup"><span data-stu-id="7d6f2-p120">Run the [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) cmdlet as follows. You should get an error message since the user no longer exists.</span></span> 
  
```
Get-Recipient Jeffrey | fl
```

