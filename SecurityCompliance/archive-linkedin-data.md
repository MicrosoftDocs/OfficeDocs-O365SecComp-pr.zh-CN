---
title: 设置连接器以存档 Office 365 中的 LinkedIn 数据 (预览)
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
description: 管理员可以设置本机连接器以将数据从 LinkedIn 公司页面导入到 Office 365。 这使您可以在 Office 365 中存档第三方数据源中的数据, 以便您可以使用合规性功能 (如法律封存、内容搜索和保留策略) 来管理组织的第三方数据的合规性。
ms.openlocfilehash: 618cef7c0208378179d41a94f4a274a0bddadee9
ms.sourcegitcommit: ecc823c2a4f1465114cf1d3a4630e31c47779ddc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/19/2019
ms.locfileid: "35079376"
---
# <a name="set-up-a-connector-to-archive-linkedin-data-in-office-365-preview"></a><span data-ttu-id="6923a-104">设置连接器以存档 Office 365 中的 LinkedIn 数据 (预览)</span><span class="sxs-lookup"><span data-stu-id="6923a-104">Set up a connector to archive LinkedIn data in Office 365 (Preview)</span></span>

<span data-ttu-id="6923a-105">在 Office 365 中存档来自 LinkedIn 公司页面的数据的连接器功能处于预览阶段。</span><span class="sxs-lookup"><span data-stu-id="6923a-105">The connector feature to archive data from LinkedIn Company pages in Office 365 is in Preview.</span></span>

<span data-ttu-id="6923a-106">在 Office 365 的 Security & 合规性中心中使用本机连接器, 以从 LinkedIn 公司页面导入和存档数据。</span><span class="sxs-lookup"><span data-stu-id="6923a-106">Use a native connector in the Security & Compliance Center in Office 365 to import and archive data from LinkedIn Company pages.</span></span> <span data-ttu-id="6923a-107">在设置和配置连接器后, 它会每24小时连接到特定 "LinkedIn 公司" 页面的帐户。</span><span class="sxs-lookup"><span data-stu-id="6923a-107">After you set up and configure a connector, it connects to the account for the specific LinkedIn Company page once every 24 hours.</span></span> <span data-ttu-id="6923a-108">连接器将发布到公司页面的邮件转换为电子邮件, 然后将这些项目导入 Office 365 中的邮箱。</span><span class="sxs-lookup"><span data-stu-id="6923a-108">The connector converts the messages posted to the Company page to an email message, and then imports those items to a mailbox in Office 365.</span></span>

<span data-ttu-id="6923a-109">在将 LinkedIn 公司页面数据存储在邮箱中之后, 您可以将 Office 365 合规性功能 (如诉讼保留、内容搜索、就地存档、审核和 Office 365 保留策略) 应用于 LinkedIn 数据。</span><span class="sxs-lookup"><span data-stu-id="6923a-109">After the LinkedIn Company page data is stored in a mailbox, you can apply Office 365 compliance features such as Litigation Hold, Content Search, In-Place Archiving, Auditing, and Office 365 retention policies to LinkedIn data.</span></span> <span data-ttu-id="6923a-110">例如, 可以使用内容搜索来搜索这些项目, 或将存储邮箱与高级电子数据展示事例中的管理员相关联。</span><span class="sxs-lookup"><span data-stu-id="6923a-110">For example, you can search for these items using Content Search or associate the storage mailbox with a custodian in an Advanced eDiscovery case.</span></span> <span data-ttu-id="6923a-111">创建连接器以在 Office 365 中导入和存档 LinkedIn 数据可帮助您的组织遵守政府和法规策略。</span><span class="sxs-lookup"><span data-stu-id="6923a-111">Creating a connector to import and archive LinkedIn data in Office 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="before-you--begin"></a><span data-ttu-id="6923a-112">开始之前</span><span class="sxs-lookup"><span data-stu-id="6923a-112">Before you  begin</span></span>

- <span data-ttu-id="6923a-113">您的组织必须同意允许 Office 365 导入服务访问组织中的邮箱数据。</span><span class="sxs-lookup"><span data-stu-id="6923a-113">Your organization must consent to allow the Office 365 Import service to access mailbox data in your organization.</span></span> <span data-ttu-id="6923a-114">若要同意此请求, 请转到[此页](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent), 使用 Office 365 全局管理员的凭据登录, 然后接受该请求。</span><span class="sxs-lookup"><span data-stu-id="6923a-114">To consent to this request, go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent), sign in with the credentials of an Office 365 global admin, and then accept the request.</span></span>

- <span data-ttu-id="6923a-115">必须在 Exchange Online 中为创建 LinkedIn 公司页面连接器的用户分配邮箱导入导出角色。</span><span class="sxs-lookup"><span data-stu-id="6923a-115">The user who creates a LinkedIn Company Page connector must be assigned the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="6923a-116">这是访问安全 & 合规中心中的 "**存档第三方数据**" 页所必需的。</span><span class="sxs-lookup"><span data-stu-id="6923a-116">This is required to access the **Archive third-party data** page in the Security & Compliance Center.</span></span> <span data-ttu-id="6923a-117">默认情况下, 此角色不会分配给 Exchange Online 中的任何角色组。</span><span class="sxs-lookup"><span data-stu-id="6923a-117">By default, this role isn't assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="6923a-118">您可以将邮箱导入导出角色添加到 Exchange Online 中的 "组织管理" 角色组。</span><span class="sxs-lookup"><span data-stu-id="6923a-118">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="6923a-119">或者, 您可以创建角色组, 分配邮箱导入导出角色, 然后将相应的用户添加为成员。</span><span class="sxs-lookup"><span data-stu-id="6923a-119">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="6923a-120">有关详细信息, 请参阅文章 "管理 Exchange Online 中的角色组" 中的 "[创建角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups)" 或 "[修改角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)" 部分。</span><span class="sxs-lookup"><span data-stu-id="6923a-120">For more information, see the  [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

- <span data-ttu-id="6923a-121">您必须具有作为您要存档的 "LinkedIn 公司" 页面的管理员的 LinkedIn 用户帐户的登录凭据 (电子邮件地址或电话号码和密码)。</span><span class="sxs-lookup"><span data-stu-id="6923a-121">You must have the sign-in credentials (email address or phone number and password) of a LinkedIn user account that is an admin for the LinkedIn Company Page that you want to archive.</span></span> <span data-ttu-id="6923a-122">设置连接器时, 可以使用这些凭据登录到 LinkedIn。</span><span class="sxs-lookup"><span data-stu-id="6923a-122">You use these credentials to sign in to LinkedIn when setting up the connector.</span></span>

## <a name="create-a-linkedin-connector"></a><span data-ttu-id="6923a-123">创建 LinkedIn 连接器</span><span class="sxs-lookup"><span data-stu-id="6923a-123">Create a LinkedIn connector</span></span>

1. <span data-ttu-id="6923a-124">转到<https://protection.office.com> , 然后单击 "**数据\>调控导入**", 然后单击 "**存档第三方数据**"。</span><span class="sxs-lookup"><span data-stu-id="6923a-124">Go to <https://protection.office.com> and then click **Data governance \> Import** and then click **Archive third-party data**.</span></span>

2. <span data-ttu-id="6923a-125">在 "**存档第三方数据**" 页上, 单击 "**添加连接器**", 然后单击 " **LinkedIn**"。</span><span class="sxs-lookup"><span data-stu-id="6923a-125">On the **Archive third-party data** page, click **Add a connector**, and then click **LinkedIn**.</span></span>

3. <span data-ttu-id="6923a-126">在 "**服务条款**" 页上, 单击 "**接受**"。</span><span class="sxs-lookup"><span data-stu-id="6923a-126">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="6923a-127">在 "**使用 Linkedin 登录**" 页面上, 单击 "**使用 linkedin 登录**"。</span><span class="sxs-lookup"><span data-stu-id="6923a-127">On the **Sign in with LinkedIn** page, click **Sign in with LinkedIn**.</span></span>

   <span data-ttu-id="6923a-128">将显示 "LinkedIn 登录" 页面。</span><span class="sxs-lookup"><span data-stu-id="6923a-128">The LinkedIn sign in page is displayed.</span></span>

   ![LinkedIn 登录页](media/LinkedInSigninPage.png)

5. <span data-ttu-id="6923a-130">在 "LinkedIn 登录" 页面上, 输入与要存档的公司页面相关联的 LinkedIn 帐户的电子邮件地址 (或电话号码) 和密码, 然后单击 "**登录**"。</span><span class="sxs-lookup"><span data-stu-id="6923a-130">On the LinkedIn sign in page, enter the email address (or phone number) and password for the LinkedIn account that associated with the company page that you want to archive, and then click **Sign in**.</span></span>

   <span data-ttu-id="6923a-131">将显示一个向导页, 其中包含与您登录的帐户关联的所有 LinkedIn 公司页面的列表。</span><span class="sxs-lookup"><span data-stu-id="6923a-131">A wizard page is displayed with a list of all LinkedIn Company Pages associated with the account that you signed in to.</span></span> <span data-ttu-id="6923a-132">仅可为一个公司页面配置连接器。</span><span class="sxs-lookup"><span data-stu-id="6923a-132">A connector can only be configured for one company page.</span></span> <span data-ttu-id="6923a-133">如果您的组织具有多个 LinkedIn 公司页面, 则必须为每个公司创建一个连接器。</span><span class="sxs-lookup"><span data-stu-id="6923a-133">If your organization has multiple LinkedIn Company Pages, you have to create a connector for each one.</span></span>

   ![将显示一个包含 "LinkedIn 公司" 页面列表的页面](media/LinkedInSelectCompanyPage.png)

6. <span data-ttu-id="6923a-135">选择要存档其项目的公司页面, 然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="6923a-135">Select the company page that you want to archive items from, and then click **Next**.</span></span>

7. <span data-ttu-id="6923a-136">在 "**设置筛选器**" 页上, 您可以将筛选器应用于最初导入特定年龄的项目。</span><span class="sxs-lookup"><span data-stu-id="6923a-136">On the **Set filters** page, you can apply a filter to initially import items that are a certain age.</span></span> <span data-ttu-id="6923a-137">选择年龄, 然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="6923a-137">Select an age, and then click **Next**.</span></span>

8. <span data-ttu-id="6923a-138">在 "**设置存储帐户**" 页上, 键入将向其导入 LinkedIn 项目的 Office 365 邮箱的电子邮件地址, 然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="6923a-138">On the **Set storage account** page, type the email address of an Office 365 mailbox that the LinkedIn items will be imported to, and then click **Next**.</span></span> <span data-ttu-id="6923a-139">项目将导入到此邮箱的 "收件箱" 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="6923a-139">Items are imported to the Inbox folder in this mailbox.</span></span>

9. <span data-ttu-id="6923a-140">查看连接器设置, 然后单击 "**保存**" 以完成连接器设置。</span><span class="sxs-lookup"><span data-stu-id="6923a-140">Review the connector settings and then click **Save** to complete the connector setup.</span></span>

<span data-ttu-id="6923a-141">创建连接器后, 可以返回到 "**存档第三方数据**" 页 (如果需要更新连接器列表, 请单击 "**刷新**") 查看新的连接器。</span><span class="sxs-lookup"><span data-stu-id="6923a-141">After you create the connector, you can go back to the **Archive third-party data** page (click **Refresh** if necessary to update the list of connectors) a view the new connector.</span></span> <span data-ttu-id="6923a-142">"**状态**" 列中的值为 "**正在等待启动**"。</span><span class="sxs-lookup"><span data-stu-id="6923a-142">The value in the **Status** column is **Waiting to start**.</span></span> <span data-ttu-id="6923a-143">启动初始导入过程需要长达24小时。</span><span class="sxs-lookup"><span data-stu-id="6923a-143">It takes up to 24 hours for the initial import process to be started.</span></span> <span data-ttu-id="6923a-144">在第一次运行连接器并导入 LinkedIn 项目后, 连接器将每24小时运行一次, 并导入 "LinkedIn 公司" 页上的 "在前24小时内创建的任何新项目"。</span><span class="sxs-lookup"><span data-stu-id="6923a-144">After the first time the connector runs and imports the LinkedIn items, the connector will run once every 24 hours and import any new items that are created on the LinkedIn Company Page in the previous 24 hours.</span></span>

<span data-ttu-id="6923a-145">若要查看更多详细信息, 请单击 "**存档第三方数据**" 页上的列表中的连接器以显示弹出页面。</span><span class="sxs-lookup"><span data-stu-id="6923a-145">To view more details, click the connector in the list on the **Archive third-party data** page to display the flyout page.</span></span> <span data-ttu-id="6923a-146">在 "**状态**" 下, 显示的日期范围表示创建连接器时选择的年龄筛选器。</span><span class="sxs-lookup"><span data-stu-id="6923a-146">Under **Status**, the date range that's displayed indicates the age filter that was selected when the connector was created.</span></span> 

## <a name="more-information"></a><span data-ttu-id="6923a-147">更多信息</span><span class="sxs-lookup"><span data-stu-id="6923a-147">More information</span></span>

- <span data-ttu-id="6923a-148">将 LinkedIn 项目导入到 Office 365 中的存储邮箱的 "收件箱" 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="6923a-148">LinkedIn items are imported to the Inbox folder in the storage mailbox in Office 365.</span></span> <span data-ttu-id="6923a-149">它们显示为电子邮件。</span><span class="sxs-lookup"><span data-stu-id="6923a-149">They appear as email messages.</span></span> <span data-ttu-id="6923a-150">邮件发件人的显示名称是 "LinkedIn 公司" 页面的名称。</span><span class="sxs-lookup"><span data-stu-id="6923a-150">The display name of the sender of the message is the name of the LinkedIn Company Page.</span></span> <span data-ttu-id="6923a-151">发件人的实际电子邮件地址是存储邮箱的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="6923a-151">The actual email address of the sender is the email address of the storage mailbox.</span></span> <span data-ttu-id="6923a-152">公司页面的名称也会预先追加到主题行。</span><span class="sxs-lookup"><span data-stu-id="6923a-152">The name of the company page is also pre-appended to the subject line.</span></span> 

- <span data-ttu-id="6923a-153">由于以前的行为, 在使用 Microsoft 电子数据`from`展示`subject`工具搜索在 Office 365 中存档的 LinkedIn 项目时, 可以搜索或电子邮件属性。</span><span class="sxs-lookup"><span data-stu-id="6923a-153">Because of the previous behavior, you can search the `from` or `subject` email properties when using a Microsoft eDiscovery tool to search LinkedIn items that are archived in Office 365.</span></span> <span data-ttu-id="6923a-154">例如, 如果公司页面的名称是 "Contoso Company Page", 则可以在关键字搜索查询中使用下列*属性之一: 值*对:</span><span class="sxs-lookup"><span data-stu-id="6923a-154">For example if the name of the company page is "Contoso Company Page", then you can use one of the following *property:value* pairs in the keyword search query:</span></span>
   
   ```
   from:"Contoso Company Page"
   ```

    <span data-ttu-id="6923a-155">或</span><span class="sxs-lookup"><span data-stu-id="6923a-155">Or</span></span>

   ```
   subject:"Contoso Company Page"
   ```

- <span data-ttu-id="6923a-156">若要更轻松地查找或管理导入到 Office 365 的 LinkedIn 项目, 存储邮箱的所有者 (或任何被分配了 FullAccess 权限的人) 可以设置收件箱规则, 将项目从 LinkedIn 公司页面移动到特定文件夹。</span><span class="sxs-lookup"><span data-stu-id="6923a-156">To make it easier to locate or manage LinkedIn items imported to Office 365, the owner of the storage mailbox (or anyone assigned the FullAccess permission) can set up an inbox rule to move the items from a LinkedIn Company Page to a specific folder.</span></span> <span data-ttu-id="6923a-157">如果存储邮箱用于存档从不同第三方数据源导入的项目, 这将非常有用。</span><span class="sxs-lookup"><span data-stu-id="6923a-157">This is helpful if the storage mailbox is used to archive items imported from different third-party data sources.</span></span> <span data-ttu-id="6923a-158">例如, 您可以创建收件箱规则, 将 "主题" 字段中包含特定 "LinkedIn 公司" 页面的所有项目移到特定文件夹中。</span><span class="sxs-lookup"><span data-stu-id="6923a-158">For example, you can create an inbox rule that moves all items that contain the name of a specific LinkedIn Company Page in the subject field to a specific folder.</span></span>