---
title: 设置连接器以在 Office 365 中存档即时 Bloomberg 数据 (预览)
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
description: 管理员可以设置本机连接器以将数据从即时 Bloomberg 聊天工具导入 Office 365。 这使您可以在 Office 365 中存档第三方数据源中的数据, 以便您可以使用合规性功能 (如法律封存、内容搜索和保留策略) 来管理组织的第三方数据。
ms.openlocfilehash: 0b69ddaa21196bd0e149eba672fec104eabe2e5e
ms.sourcegitcommit: ab16ddf4c050a995471a058150767a0778be0b88
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2019
ms.locfileid: "35431593"
---
# <a name="set-up-a-connector-to-archive-instant-bloomberg-data-in-office-365-preview"></a><span data-ttu-id="fdb57-104">设置连接器以在 Office 365 中存档即时 Bloomberg 数据 (预览)</span><span class="sxs-lookup"><span data-stu-id="fdb57-104">Set up a connector to archive Instant Bloomberg data in Office 365 (Preview)</span></span>

<span data-ttu-id="fdb57-105">在 Office 365 中存档即时 Bloomberg 数据的连接器功能处于预览阶段。</span><span class="sxs-lookup"><span data-stu-id="fdb57-105">The connector feature to archive Instant Bloomberg data in Office 365 is in Preview.</span></span>

<span data-ttu-id="fdb57-106">使用 Office 365 的 Security & 合规性中心中的本机连接器从[即时 Bloomberg](https://www.bloomberg.com/professional/product/collaboration/)协作工具导入和存档金融 services 聊天数据。</span><span class="sxs-lookup"><span data-stu-id="fdb57-106">Use a native connector in the Security & Compliance Center in Office 365 to import and archive financial services chat data from [Instant Bloomberg](https://www.bloomberg.com/professional/product/collaboration/) collaboration tool.</span></span> <span data-ttu-id="fdb57-107">在设置和配置连接器后, 它每天连接到组织的 Bloomberg 安全 FTP 站点 (SFTP), 将聊天消息的内容转换为电子邮件格式, 然后将这些项目导入 Office 365 中的邮箱。</span><span class="sxs-lookup"><span data-stu-id="fdb57-107">After you set up and configure a connector, it connects to your organization's Bloomberg secure FTP site (SFTP) once every day, converts the content of chat messages to an email message format, and then imports those items to mailboxes in Office 365.</span></span>

<span data-ttu-id="fdb57-108">将即时 Bloomberg 数据存储在用户邮箱中之后, 您可以将 Office 365 合规性功能 (如诉讼保留、内容搜索、就地存档、审核和 Office 365 保留策略) 应用于即时 Bloomberg 数据。</span><span class="sxs-lookup"><span data-stu-id="fdb57-108">After Instant Bloomberg data is stored in user mailboxes, you can apply Office 365 compliance features such as Litigation Hold, Content Search, In-Place Archiving, Auditing, and Office 365 retention policies to Instant Bloomberg data.</span></span> <span data-ttu-id="fdb57-109">例如, 您可以使用内容搜索来搜索即时 Bloomberg 聊天邮件, 或将包含即时 Bloomberg 数据的邮箱与高级电子数据展示事例中的管理员关联起来。</span><span class="sxs-lookup"><span data-stu-id="fdb57-109">For example, you can search Instant Bloomberg chat messages using Content Search or associate the mailbox that contains the Instant Bloomberg data with a custodian in an Advanced eDiscovery case.</span></span> <span data-ttu-id="fdb57-110">使用即时 Bloomberg 连接器在 Office 365 中导入和存档数据可帮助您的组织遵守政府和法规策略。</span><span class="sxs-lookup"><span data-stu-id="fdb57-110">Using an Instant Bloomberg connector to import and archive data in Office 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-instant-bloomberg-data"></a><span data-ttu-id="fdb57-111">存档即时 Bloomberg 数据概述</span><span class="sxs-lookup"><span data-stu-id="fdb57-111">Overview of archiving Instant Bloomberg data</span></span>

<span data-ttu-id="fdb57-112">以下概述说明了使用连接器在 Office 365 中存档即时 Bloomberg 聊天数据的过程。</span><span class="sxs-lookup"><span data-stu-id="fdb57-112">The following overview explains the process of using a connector to archive Instant Bloomberg chat data in Office 365.</span></span> 

![即时 Bloomberg 导入和存档过程](media/InstantBloombergDataArchiving.png)

1. <span data-ttu-id="fdb57-114">您的组织与 Bloomberg 配合使用来设置 Bloomberg SFTP 站点。</span><span class="sxs-lookup"><span data-stu-id="fdb57-114">Your organization works with Bloomberg to set up a Bloomberg SFTP site.</span></span> <span data-ttu-id="fdb57-115">您还将使用 Bloomberg 将 "即时 Bloomberg" 配置为将聊天邮件复制到 Bloomberg SFTP 站点。</span><span class="sxs-lookup"><span data-stu-id="fdb57-115">You will also work with Bloomberg to configure Instant Bloomberg to copy chat messages to your Bloomberg SFTP site.</span></span>

2. <span data-ttu-id="fdb57-116">每24小时一次, 来自即时 Bloomberg 的聊天邮件将复制到 Bloomberg SFTP 站点。</span><span class="sxs-lookup"><span data-stu-id="fdb57-116">Once every 24 hours, chat messages from Instant Bloomberg are copied to the Bloomberg SFTP site.</span></span>
    
3. <span data-ttu-id="fdb57-117">您在安全 & 合规中心中创建的即时 Bloomberg 连接器每天连接到 Bloomberg SFTP 站点, 并将聊天消息从以前的24小时传输到 Microsoft 云中的安全 Azure 存储区域。</span><span class="sxs-lookup"><span data-stu-id="fdb57-117">The Instant Bloomberg connector that you create in the Security & Compliance Center connects to the Bloomberg SFTP site every day and transfers the chat messages from the previous 24 hours to a secure Azure Storage area in the Microsoft Cloud.</span></span> <span data-ttu-id="fdb57-118">连接器还将聊天 massage 的内容转换为电子邮件格式。</span><span class="sxs-lookup"><span data-stu-id="fdb57-118">The connector also converts the content of a chat massage to an email message format.</span></span>
    
4. <span data-ttu-id="fdb57-119">连接器将聊天邮件项目导入到特定用户的邮箱或备用邮箱。</span><span class="sxs-lookup"><span data-stu-id="fdb57-119">The connector imports the chat message items to the mailbox of a specific user or to an alternative mailbox.</span></span> <span data-ttu-id="fdb57-120">连接器通过使用*CorporateEmailAddress*属性的值来执行。</span><span class="sxs-lookup"><span data-stu-id="fdb57-120">The connector does by using the value of the *CorporateEmailAddress* property.</span></span> <span data-ttu-id="fdb57-121">每个聊天邮件都包含此属性, 该属性由聊天消息的每个参与者的电子邮件地址填充。</span><span class="sxs-lookup"><span data-stu-id="fdb57-121">Every chat message contains this property, which is populated with the email address of every participant of the chat message.</span></span> <span data-ttu-id="fdb57-122">是否将项目导入特定用户邮箱或根据以下条件将项目导入备用邮箱:</span><span class="sxs-lookup"><span data-stu-id="fdb57-122">Whether an item is imported into a specific user mailbox or to the alternative mailbox is based on the following criteria:</span></span>
    
    <span data-ttu-id="fdb57-123">a.</span><span class="sxs-lookup"><span data-stu-id="fdb57-123">a.</span></span> <span data-ttu-id="fdb57-124">**CorporateEmailAddress 属性中具有与 office 365 用户帐户对应的值的项目**–如果该连接器可以将*CorporateEmailAddress*属性中的电子邮件地址与 office 365 中的特定用户帐户相关联, 则将项目复制到用户的 Office 365 邮箱中的 "收件箱" 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="fdb57-124">**Items that have a value in the CorporateEmailAddress property that corresponds to an Office 365 user account** – If the connector can associate the email address in the *CorporateEmailAddress* property to a specific user account in Office 365, the item is copied to the Inbox folder in the user's Office 365 mailbox.</span></span>
    
    <span data-ttu-id="fdb57-125">b.</span><span class="sxs-lookup"><span data-stu-id="fdb57-125">b.</span></span> <span data-ttu-id="fdb57-126">**CorporateEmailAddress 属性中的值与 office 365 用户帐户不对应的项**–如果连接器无法将*CorporateEmailAddress*属性中的电子邮件地址与 office 中的特定用户帐户关联365, 将项目复制到 Office 365 中的替代 "捕获全部" 邮箱的 "收件箱" 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="fdb57-126">**Items that have a value in the CorporateEmailAddress property that doesn't correspond to an Office 365 user account** – If the connector can't associate an email address in the *CorporateEmailAddress* property to a specific user account in Office 365, the item is copied to the Inbox folder of an alternative, "catch-all" mailbox in Office 365.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="fdb57-127">开始之前</span><span class="sxs-lookup"><span data-stu-id="fdb57-127">Before you begin</span></span>

<span data-ttu-id="fdb57-128">存档即时 Bloomberg 数据所需的许多实施步骤都是 Office 365 外部的, 并且必须先完成, 然后才能在安全 & 合规性中心中创建连接器。</span><span class="sxs-lookup"><span data-stu-id="fdb57-128">Many of the implementation steps required to archive Instant Bloomberg data are external to Office 365 and must be completed before you can create the connector in the Security & Compliance Center.</span></span>

- <span data-ttu-id="fdb57-129">订阅[Blooomberg Anywhere](https://www.bloomberg.com/professional/product/remote-access/?bbgsum-page=DG-WS-PROF-PROD-BBA)。</span><span class="sxs-lookup"><span data-stu-id="fdb57-129">Subscribe to [Blooomberg Anywhere](https://www.bloomberg.com/professional/product/remote-access/?bbgsum-page=DG-WS-PROF-PROD-BBA).</span></span> <span data-ttu-id="fdb57-130">这是必需的, 以便您可以登录到 Bloomberg Anywhere 以访问您必须设置和配置的 Bloomberg SFTP 站点。</span><span class="sxs-lookup"><span data-stu-id="fdb57-130">This is required so that you can log in to Bloomberg Anywhere to access the Bloomberg SFTP site that you have to set up and configure.</span></span>

- <span data-ttu-id="fdb57-131">设置 Bloomberg SFTP (安全文件传输协议) 站点。</span><span class="sxs-lookup"><span data-stu-id="fdb57-131">Set up a Bloomberg SFTP (Secure file transfer protocol) site.</span></span> <span data-ttu-id="fdb57-132">使用 Bloomberg 设置 SFTP 站点后, 即时 Bloomberg 中的数据每天都将上传到 SFTP 站点。</span><span class="sxs-lookup"><span data-stu-id="fdb57-132">After working with Bloomberg to set up the SFTP site, data from Instant Bloomberg is uploaded to the SFTP site every day.</span></span> <span data-ttu-id="fdb57-133">您在步骤2中创建的连接器将连接到此 SFTP 站点, 并将聊天数据传输到 Office 365 邮箱。</span><span class="sxs-lookup"><span data-stu-id="fdb57-133">The connector you create in Step 2 connects to this SFTP site and transfers the chat data to Office 365 mailboxes.</span></span> <span data-ttu-id="fdb57-134">SFTP 还对在传输过程中发送到 Office 365 邮箱的即时 Bloomberg 聊天数据进行加密。</span><span class="sxs-lookup"><span data-stu-id="fdb57-134">SFTP also encrypts the Instant Bloomberg chat data that is sent to Office 365 mailboxes during the transfer process.</span></span>

    <span data-ttu-id="fdb57-135">有关 Bloomberg SFTP (也称为*BB-SFTP*) 的信息, 请执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="fdb57-135">For information about Bloomberg SFTP (also called *BB-SFTP*):</span></span>

    - <span data-ttu-id="fdb57-136">请参阅[Bloomberg 支持](https://www.bloomberg.com/professional/support/documentation/)中的 "SFTP 连接标准" 文档。</span><span class="sxs-lookup"><span data-stu-id="fdb57-136">See the "SFTP Connectivity Standards" document at [Bloomberg Support](https://www.bloomberg.com/professional/support/documentation/).</span></span>
    
    - <span data-ttu-id="fdb57-137">请联系[Bloomberg 客户支持](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc)部门。</span><span class="sxs-lookup"><span data-stu-id="fdb57-137">Contact [Bloomberg customer support](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc).</span></span>

    <span data-ttu-id="fdb57-138">在使用 Bloomberg 设置 SFTP 站点之后, 在您响应 Bloomberg 实施电子邮件之后, Bloomberg 将为您提供一些信息。</span><span class="sxs-lookup"><span data-stu-id="fdb57-138">After you work with Bloomberg to set up an SFTP site, Bloomberg will provide some information to you after you respond to the Bloomberg implementation email message.</span></span> <span data-ttu-id="fdb57-139">保存以下信息的副本。</span><span class="sxs-lookup"><span data-stu-id="fdb57-139">Save a copy of the following information.</span></span> <span data-ttu-id="fdb57-140">您可以使用它来设置步骤3中的连接器。</span><span class="sxs-lookup"><span data-stu-id="fdb57-140">You use it to set up a connector in Step 3.</span></span>

    - <span data-ttu-id="fdb57-141">固定代码, 它是组织的 ID, 用于登录到 Bloomberg SFTP 站点。</span><span class="sxs-lookup"><span data-stu-id="fdb57-141">Firm code, which is an ID for your organization and is used to log in to the Bloomberg SFTP site.</span></span>

    - <span data-ttu-id="fdb57-142">Bloomberg SFTP 站点的密码</span><span class="sxs-lookup"><span data-stu-id="fdb57-142">Password for your Bloomberg SFTP site</span></span>

    - <span data-ttu-id="fdb57-143">Bloomberg SFTP 网站的 URL (例如, sftp.bloomberg.com)</span><span class="sxs-lookup"><span data-stu-id="fdb57-143">URL for Bloomberg SFTP site (for example, sftp.bloomberg.com)</span></span>

    - <span data-ttu-id="fdb57-144">Bloomberg SFTP 站点的端口号</span><span class="sxs-lookup"><span data-stu-id="fdb57-144">Port number for Bloomberg SFTP site</span></span>

- <span data-ttu-id="fdb57-145">您的组织必须同意允许 Office 365 导入服务访问组织中的邮箱数据。</span><span class="sxs-lookup"><span data-stu-id="fdb57-145">Your organization must consent to allow the Office 365 Import service to access mailbox data in your organization.</span></span> <span data-ttu-id="fdb57-146">若要同意此请求, 请转到[此页](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent), 使用 Office 365 全局管理员的凭据登录, 然后接受该请求。</span><span class="sxs-lookup"><span data-stu-id="fdb57-146">To consent to this request, go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent), sign in with the credentials of an Office 365 global admin, and then accept the request.</span></span> <span data-ttu-id="fdb57-147">您必须完成此步骤, 然后才能在步骤3中成功创建即时 Bloomberg 连接器。</span><span class="sxs-lookup"><span data-stu-id="fdb57-147">You have to complete this step before you can successfully create the Instant Bloomberg connector in Step 3.</span></span>

- <span data-ttu-id="fdb57-148">在第3步 (以及在第1步中下载公钥和 IP 地址的用户) 中创建即时 Bloomberg 连接器的用户必须在 Exchange Online 中分配邮箱导入导出角色。</span><span class="sxs-lookup"><span data-stu-id="fdb57-148">The user who creates an Instant Bloomberg connector in Step 3 (and who downloads the public keys and IP address in Step 1) must be assigned the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="fdb57-149">这是访问安全 & 合规中心中的 "**存档第三方数据**" 页所必需的。</span><span class="sxs-lookup"><span data-stu-id="fdb57-149">This is required to access the **Archive third-party data** page in the Security & Compliance Center.</span></span> <span data-ttu-id="fdb57-150">默认情况下, 此角色不会分配给 Exchange Online 中的任何角色组。</span><span class="sxs-lookup"><span data-stu-id="fdb57-150">By default, this role isn't assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="fdb57-151">您可以将邮箱导入导出角色添加到 Exchange Online 中的 "组织管理" 角色组。</span><span class="sxs-lookup"><span data-stu-id="fdb57-151">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="fdb57-152">或者, 您可以创建角色组, 分配邮箱导入导出角色, 然后将相应的用户添加为成员。</span><span class="sxs-lookup"><span data-stu-id="fdb57-152">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="fdb57-153">有关详细信息, 请参阅文章 "管理 Exchange Online 中的角色组" 中的 "[创建角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups)" 或 "[修改角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)" 部分。</span><span class="sxs-lookup"><span data-stu-id="fdb57-153">For more information, see the  [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-obtain-ssh-and-pgp-public-keys"></a><span data-ttu-id="fdb57-154">步骤 1: 获取 SSH 和 PGP 公钥</span><span class="sxs-lookup"><span data-stu-id="fdb57-154">Step 1: Obtain SSH and PGP public keys</span></span>

<span data-ttu-id="fdb57-155">第一步是获取用于安全命令行管理程序 (SSH) 和相当出色的隐私 (PGP) 的公钥副本。</span><span class="sxs-lookup"><span data-stu-id="fdb57-155">The first step is to obtain a copy of the public keys for Secure Shell (SSH) and Pretty Good Privacy (PGP).</span></span> <span data-ttu-id="fdb57-156">您可以在步骤2中使用这些键来配置 Bloomberg SFTP 站点, 以允许连接器 (在步骤3中创建) 连接到 SFTP 站点, 并将 "即时 Bloomberg" 聊天数据传输到 Office 365 邮箱。</span><span class="sxs-lookup"><span data-stu-id="fdb57-156">You use these keys in Step 2 to configure the Bloomberg SFTP site to allow the connector (that you create in Step 3) to connect to the SFTP site and transfer the Instant Bloomberg chat data to Office 365 mailboxes.</span></span> <span data-ttu-id="fdb57-157">您还可以在此步骤中获取 IP 地址, 在配置 Bloomberg SFTP 站点时使用此地址。</span><span class="sxs-lookup"><span data-stu-id="fdb57-157">You also obtain an IP address in this step, which you use when configuring the Bloomberg SFTP site.</span></span>

1. <span data-ttu-id="fdb57-158">转到<https://protection.office.com> , 然后单击 "**数据\>调控导入**", 然后单击 "**存档第三方数据**"。</span><span class="sxs-lookup"><span data-stu-id="fdb57-158">Go to <https://protection.office.com> and then click **Data governance \> Import** and then click **Archive third-party data**.</span></span>

2. <span data-ttu-id="fdb57-159">在 "**存档第三方数据**" 页上, 单击 "**添加一个连接器**", 然后单击 "**即时 Bloomberg**"。</span><span class="sxs-lookup"><span data-stu-id="fdb57-159">On the **Archive third-party data** page, click **Add a connector**, and then click **Instant Bloomberg**.</span></span>

3. <span data-ttu-id="fdb57-160">在 "**服务条款**" 页上, 单击 "**接受**"。</span><span class="sxs-lookup"><span data-stu-id="fdb57-160">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="fdb57-161">在步骤1下的**BLOOMBERG SFTP 网站的 "添加凭据**" 中, 单击 "**下载 SSH 密钥**" 并**下载 "PGP 密钥**下载链接", 将每个公钥文件的副本保存到本地计算机。</span><span class="sxs-lookup"><span data-stu-id="fdb57-161">On the **Add credentials for Bloomberg SFTP site** under step 1, click **Download SSH key** and **Download PGP key** download links to save a copy of each public key file to your local computer.</span></span> <span data-ttu-id="fdb57-162">这些文件包含以下将在步骤2中用于配置 Bloomberg SFTP 网站的项:</span><span class="sxs-lookup"><span data-stu-id="fdb57-162">These files contain the following items that will be used to configure the Bloomberg SFTP site in Step 2:</span></span>

   - <span data-ttu-id="fdb57-163">SSH 公钥–此密钥将用于配置安全命令行管理程序 (SSH), 以便在连接器连接到 Bloomberg SFTP 站点时启用安全的远程登录。</span><span class="sxs-lookup"><span data-stu-id="fdb57-163">SSH public key – This key will be used to configure Secure Shell (SSH) to enable a secure remote login when the connector connects to the Bloomberg SFTP site.</span></span>

   - <span data-ttu-id="fdb57-164">PGP 公钥–此密钥将用于配置从 Bloomberg SFTP 站点传输到 Office 365 的数据的加密。</span><span class="sxs-lookup"><span data-stu-id="fdb57-164">PGP public key – This key will be used to configure the encryption of data that's transferred from the Bloomberg SFTP site to Office 365.</span></span>

   - <span data-ttu-id="fdb57-165">IP 地址– Bloomberg SFTP 站点将配置为仅接受来自此 IP 地址的连接请求, 该请求由您在步骤3中创建的 "即时 Bloomberg" 连接器使用。</span><span class="sxs-lookup"><span data-stu-id="fdb57-165">IP address – The Bloomberg SFTP site will be configured to accept a connection request only from this IP address, which is used by the Instant Bloomberg connector that you create in Step 3.</span></span> 

5. <span data-ttu-id="fdb57-166">单击 "**取消**" 关闭该向导。</span><span class="sxs-lookup"><span data-stu-id="fdb57-166">Click **Cancel** to close the wizard.</span></span> <span data-ttu-id="fdb57-167">您将在步骤3中返回到此向导来创建连接器。</span><span class="sxs-lookup"><span data-stu-id="fdb57-167">You come back to this wizard in Step 3 to create the connector.</span></span>

## <a name="step-2-configure-the-bloomberg-sftp-site"></a><span data-ttu-id="fdb57-168">步骤 2: 配置 Bloomberg SFTP 站点</span><span class="sxs-lookup"><span data-stu-id="fdb57-168">Step 2: Configure the Bloomberg SFTP site</span></span>

<span data-ttu-id="fdb57-169">下一步是使用 SSH 和 PGP 公钥以及您在步骤1中获取的 IP 地址, 以配置 Bloomberg SFTP 站点的 SSH 身份验证和 PGP 加密。</span><span class="sxs-lookup"><span data-stu-id="fdb57-169">The next step is to use the SSH and PGP public keys and the IP address that you obtained in Step 1 to configure SSH authentication and PGP encryption for the Bloomberg SFTP site.</span></span> <span data-ttu-id="fdb57-170">这将允许您在步骤3中创建的即时 Bloomberg 连接器连接到 Bloomberg SFTP 站点, 并将即时 Bloomberg 数据传输到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="fdb57-170">This allows the Instant Bloomberg connector that you create in Step 3 to connect to the Bloomberg SFTP site and transfer Instant Bloomberg data to Office 365.</span></span> <span data-ttu-id="fdb57-171">如果你需要进行设置, 请联系[Bloomberg 客户支持](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc)部门。</span><span class="sxs-lookup"><span data-stu-id="fdb57-171">Contact [Bloomberg customer support](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc) if you need assistance setting this up.</span></span>

1. <span data-ttu-id="fdb57-172">使用您的组织的帐户登录到 Bloomberg CCNS "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="fdb57-172">Log in to the Bloomberg CCNS control panel using an account for your organization.</span></span>

2. <span data-ttu-id="fdb57-173">转到 "CCNS", 然后单击 "**公钥**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="fdb57-173">Go to CCNS and click the **Public Keys** tab.</span></span>

3. <span data-ttu-id="fdb57-174">若要启用 SSH 身份验证, 请单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="fdb57-174">To enable SSH authentication, click **Add**.</span></span>

4. <span data-ttu-id="fdb57-175">在 "**添加公钥**" 窗口中, 单击 "**密钥类型**" 下拉列表, 然后单击 "**登录**"。</span><span class="sxs-lookup"><span data-stu-id="fdb57-175">In the **Add Public Key** window, click the **Key Type** dropdown list, and then click **Login**.</span></span>

5. <span data-ttu-id="fdb57-176">复制您在步骤1中下载的整个 SSH 公钥 (但不包括双引号), 并将其粘贴到此字段中, 然后单击 "**提交**" 以保存该注册表项。</span><span class="sxs-lookup"><span data-stu-id="fdb57-176">Copy the entire SSH public key (all characters between, but not including, the double quotation marks) that you downloaded in Step 1, paste it in this field, and then click **Submit** to save the key.</span></span>
 
    <span data-ttu-id="fdb57-177">例如, 您可以复制以下 SSH 公钥:</span><span class="sxs-lookup"><span data-stu-id="fdb57-177">For example, you would copy the following SSH public key:</span></span>

    `
    ssh-rsa
    AAAAB3NzaC1yc2EAAAABIwAAAQEA1dxAyc0JzCmc5NzgyzRYhnj3FGHK5Kd9T2cwZNkmL/9nFhQupQor081rmuw9gACAmeot7y+V/fmijo/q4rxDe3Auu3hfLl1NpWlIssQJHzycms8zimtdQcXbMKwDQOnRthpEocF5ySs76KE72vaYQJTvclAamWWq0D75SUmXDFFr7afvEy57F7KgMD1ecg6lH7q8seSKbiiWxX1Ul0kL15fzpUyhjDP41owb1XC/dF7fJwAmCO1+HZfDLEp62q4tnApLpdd92KoR41LZTryO5dICKhk+S+JxPLkksxL0wm5YevOr2n4ScuRdsBV8mWKZ1Xw+cOss9O6L7cCcEiB3Ow==
    `

6. <span data-ttu-id="fdb57-178">若要启用 PGP 加密, 请再次单击 "**公钥**" 选项卡上的 "**添加**", 单击 "**密钥类型**" 下拉列表, 这次单击 "**加密**"。</span><span class="sxs-lookup"><span data-stu-id="fdb57-178">To enable PGP encryption, click **Add** again on the **Public Keys** tab, click the **Key Type** dropdown list, and this time click **Encryption**.</span></span>

7. <span data-ttu-id="fdb57-179">复制您在步骤1中下载的整个 PGP 公钥 (但不包括双引号), 并将其粘贴到此字段中, 然后单击 "**提交**" 以保存该注册表项。</span><span class="sxs-lookup"><span data-stu-id="fdb57-179">Copy the entire PGP public key (all characters between, but not including, the double quotation marks) that you downloaded in Step 1, paste it in this field, and then click **Submit** to save the key.</span></span> 

    <span data-ttu-id="fdb57-180">例如, 您可以复制以下 PGP 公钥:</span><span class="sxs-lookup"><span data-stu-id="fdb57-180">For example, you would copy the following PGP public key:</span></span>

    `
    -----BEGIN PGP PUBLIC KEY BLOCK-----
    Version: BCPG C# v1.7.4137.9688
    nmQENBFz+6UQBCACKC4ilYoVOP5b/F0CO+oQYbag79Ov4NZxM4EKW51lUAvKNExRM\nc1C/gwXm8bghht8GEODckXXqx8qSSXUEeA/ROweXNtD1u1kn7PgYEFUeD/qE739m\nm5lxXF9Vod26AtKQ9Y1EvYoQEltwztAaXg8K8LQzB+tzN079d1cxM5tbiRQLttAh\nOt5amLXuINt8+dWyNas3DfgIBUmwfkwCbUO0ElrIhvvO3A85K97SX9Q6Py0SkfkK\nQpnULuhdjSm+7k7qlVMf0s8e/9jUXYKbMFkxlOoMq052vV0l0VQNSeuKoC+m6+LT\nEPab89AMt6S4Ujum9wTUy1eWNx9vV0y/w8N7ABEBAAG0JDM5MjM4ZTg3LWI1YWIt\nNGVmNi1hNTU5LWFmNTRjNmIwN2I0MokBHAQQAQIABgUCXP7pRAAKCRAJQdjaG//S\nCy70B/wKrR2CcqtZx56yrGJFfVy3niEt16VEA3xJM3D9nX0gmgo85Nh5gkiY3ahH\nnNEmgW5vlCM1gcgFeoZWe8A80G4QoabslSUzLbq9HsHOOAQApsfhrhXpylrAVa4n\nI53XUOxWdOTa4xsOob8hSRADqJbwHPOsoAr2A87TvZ9LSi2Mii5omeTq416CLnoS\nPBAEhelZm+ruy5JhzA1yXvWYFH08wNqSHO3bskdES2yW5SyQmYlcoEztWE0Q0Z+G\nZT3kOa/W2MbcZovFCQIfqhwVfXtIzx5uYUmxgk5cFKUJJMlO0AZK/HwM22xuuIWe\ndMa6OMo/n8tvEBxrLQMdVPlz+hZ6
    =AwmP
    -----END PGP PUBLIC KEY BLOCK-----
    `
8. <span data-ttu-id="fdb57-181">返回到 CCNS 控制面板主窗口中的 "在**此处添加 IP 地址**" 下, 在 "**添加地址" 字段**中输入以下 IP 地址 (包含在您在步骤1中下载的 Keys .txt 文件中)。</span><span class="sxs-lookup"><span data-stu-id="fdb57-181">Back on the main window of the CCNS control panel, under **Add your IP address here**, enter the following IP address (which is included in Keys.txt file that you downloaded in Step 1) in the **Add address field**.</span></span>

   `
   40.124.28.216
   `

## <a name="step-3-create-an-instant-bloomberg-connector"></a><span data-ttu-id="fdb57-182">步骤 3: 创建即时 Bloomberg 连接器</span><span class="sxs-lookup"><span data-stu-id="fdb57-182">Step 3: Create an Instant Bloomberg connector</span></span>

<span data-ttu-id="fdb57-183">最后一步是在安全 & 合规性中心中创建一个即时 Bloomberg 连接器。</span><span class="sxs-lookup"><span data-stu-id="fdb57-183">The last step is to create an Instant Bloomberg connector in the Security & Compliance Center.</span></span> <span data-ttu-id="fdb57-184">连接器使用您提供的信息连接到 Bloomberg SFTP 站点, 并将聊天邮件传输到 Office 365 中对应的用户邮箱框中。</span><span class="sxs-lookup"><span data-stu-id="fdb57-184">The connector uses the information you provide to connect to the Bloomberg SFTP site and transfer chat messages to the corresponding user mailbox boxes in Office 365.</span></span> 

1. <span data-ttu-id="fdb57-185">转到<https://protection.office.com> , 然后单击 "**数据\>调控导入**", 然后单击 "**存档第三方数据**"。</span><span class="sxs-lookup"><span data-stu-id="fdb57-185">Go to <https://protection.office.com> and then click **Data governance \> Import** and then click **Archive third-party data**.</span></span>

2. <span data-ttu-id="fdb57-186">在 "**存档第三方数据**" 页上, 单击 "**添加一个连接器**", 然后单击 "**即时 Bloomberg**"。</span><span class="sxs-lookup"><span data-stu-id="fdb57-186">On the **Archive third-party data** page, click **Add a connector**, and then click **Instant Bloomberg**.</span></span>

3. <span data-ttu-id="fdb57-187">在 "**服务条款**" 页上, 单击 "**接受**"。</span><span class="sxs-lookup"><span data-stu-id="fdb57-187">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="fdb57-188">在 "**添加 BLOOMBERG SFTP 网站的凭据**" 页上的 "步骤 3" 中的以下框中, 输入所需信息, 然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="fdb57-188">On the **Add credentials for Bloomberg SFTP site** page, under Step 3, enter the required information in the following boxes and then click **Next**.</span></span>

    - <span data-ttu-id="fdb57-189">**固定代码**–您的组织的 ID, 用作 Bloomberg SFTP 站点的用户名。</span><span class="sxs-lookup"><span data-stu-id="fdb57-189">**Firm code** – The ID for your organization and used as the username for the Bloomberg SFTP site.</span></span>

    - <span data-ttu-id="fdb57-190">**Password** – Bloomberg SFTP 站点的密码</span><span class="sxs-lookup"><span data-stu-id="fdb57-190">**Password** – Password for Bloomberg SFTP site</span></span>

    - <span data-ttu-id="fdb57-191">**SFTP url** – Bloomberg SFTP 网站的 URL (例如, sftp.bloomberg.com)。</span><span class="sxs-lookup"><span data-stu-id="fdb57-191">**SFTP URL** – The URL for Bloomberg SFTP site (for example, sftp.bloomberg.com).</span></span>

    - <span data-ttu-id="fdb57-192">**SFTP 端口**– Bloomberg SFTP 站点的端口号。</span><span class="sxs-lookup"><span data-stu-id="fdb57-192">**SFTP port** – The port number for Bloomberg SFTP site.</span></span> <span data-ttu-id="fdb57-193">连接器使用此连接到 SFTP 站点。</span><span class="sxs-lookup"><span data-stu-id="fdb57-193">The connector uses this to connect to the SFTP site.</span></span>

5. <span data-ttu-id="fdb57-194">在 "**备用邮箱**" 页上, 键入将用于存储来自即时 Bloomberg 的聊天消息的邮箱的电子邮件地址, 这些消息无法与组织中的用户邮箱相关联。</span><span class="sxs-lookup"><span data-stu-id="fdb57-194">On the **Alternative mailbox** page, type the email address of a mailbox that will be used to store chat messages from Instant Bloomberg that can't be associated with a user mailbox in your organization.</span></span>

   > [!NOTE]
   > <span data-ttu-id="fdb57-195">Bloomberg 中每个对话中的每个聊天邮件都包含一个名为*CorporateEmailAddress*的属性, 其中包含您的聊天参与者的组织的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="fdb57-195">Every chat message in every conversation in Instant Bloomberg includes a property called *CorporateEmailAddress*, which contains your organization's email address for the chat participant.</span></span> <span data-ttu-id="fdb57-196">在导入过程中, 连接器将尝试将聊天邮件导入到 Office 365 中的用户邮箱, 该邮箱与*CorporateEmailAddress*属性中的电子邮件地址相匹配。</span><span class="sxs-lookup"><span data-stu-id="fdb57-196">During the import process, the connector attempts to import chat messages to a user mailbox in Office 365 that has the same email addresses that matches the one in the *CorporateEmailAddress* property.</span></span> <span data-ttu-id="fdb57-197">如果没有 Office 365 邮箱与*CorporateEmailAddress*属性中的地址相同, 则连接器会将聊天消息导入您在此页面上指定的备用邮箱。</span><span class="sxs-lookup"><span data-stu-id="fdb57-197">If the there isn't an Office 365 mailbox with the same address as the one in the *CorporateEmailAddress* property, the connector imports the chat message to the alternative mailbox that you specify on this page.</span></span> <span data-ttu-id="fdb57-198">目前, Office 365 中的监督策略不会监视存档在备用邮箱中的即时 Bloomberg 聊天邮件。</span><span class="sxs-lookup"><span data-stu-id="fdb57-198">At this time, Instant Bloomberg chat messages archived in the alternative mailbox aren't monitored by supervision policies in Office 365.</span></span>

6. <span data-ttu-id="fdb57-199">单击 "**下一步**", 查看设置, 然后单击 "**准备**" 以创建连接器。</span><span class="sxs-lookup"><span data-stu-id="fdb57-199">Click **Next**, review your settings, and then click **prepare** to create the connector.</span></span>

7. <span data-ttu-id="fdb57-200">转到 "**存档第三方数据**" 页, 查看新连接器的导入过程的进度。</span><span class="sxs-lookup"><span data-stu-id="fdb57-200">Go to the **Archive third-party data** page to see the progress of the import process for the new connector.</span></span>
