---
title: 使用示例连接器在 Office 365 中存档 Facebook 数据 (预览)
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
description: 管理员可以设置本机连接器, 以便从数据源 (如 Facebook 商业页面、LinkedIn 公司网页和即时 Bloomberg) 导入第三方数据。 这使您可以在 Office 365 中存档第三方数据源中的数据, 以便您可以使用合规性功能 (如法律封存、内容搜索和保留策略) 来管理组织的第三方数据的管理。
ms.openlocfilehash: 7a71eac07d3d3260809f90cd2e470c32c44e9dda
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2019
ms.locfileid: "34152184"
---
# <a name="use-a-sample-connector-to-archive-facebook-data-in-office-365-preview"></a><span data-ttu-id="b75f0-104">使用示例连接器在 Office 365 中存档 Facebook 数据 (预览)</span><span class="sxs-lookup"><span data-stu-id="b75f0-104">Use a sample connector to archive Facebook data in Office 365 (Preview)</span></span>

<span data-ttu-id="b75f0-105">在 Office 365 中存档 Facebook 数据的示例连接器功能是 "预览"。。</span><span class="sxs-lookup"><span data-stu-id="b75f0-105">The sample connector feature to archive Facebook data in Office 365 is in Preview..</span></span>

<span data-ttu-id="b75f0-106">使用 Office 365 中安全 & 合规中心中的示例连接器从第三方数据源 (如 Facebook 商业页面、LinkedIn、Twitter 和 Bloomberg) 导入和存档数据。</span><span class="sxs-lookup"><span data-stu-id="b75f0-106">Use a sample connector in the Security & Compliance Center in Office 365 to import and archive data from a third-party data sources such as Facebook Business pages, LinkedIn, Twitter, and Bloomberg.</span></span> <span data-ttu-id="b75f0-107">在设置和配置示例连接器之后, 它会连接到第三方数据源 (定期), 将项目的内容转换为电子邮件格式, 然后将这些项目导入到 Office 365 中的邮箱中。</span><span class="sxs-lookup"><span data-stu-id="b75f0-107">After you set up and configure a sample connector, it connects to the third-party data source (on a scheduled basis), converts the content of an item to an email message format, and then imports those items to a mailbox in Office 365.</span></span>

<span data-ttu-id="b75f0-108">导入第三方数据后, 可以将 Office 365 合规性功能 (如诉讼保留、内容搜索、就地存档、审核、监督和 Office 365 保留策略) 应用于第三方数据。</span><span class="sxs-lookup"><span data-stu-id="b75f0-108">After third-party data is imported, you can apply Office 365 compliance features such as Litigation Hold, Content Search, In-Place Archiving, Auditing, Supervision, and Office 365 retention policies to the third-party data.</span></span> <span data-ttu-id="b75f0-109">例如, 当将邮箱置于诉讼保留状态或分配到保留策略时, 将保留第三方数据。</span><span class="sxs-lookup"><span data-stu-id="b75f0-109">For example, when a mailbox is placed on Litigation Hold or assigned to a retention policy, the third-party data will be retained.</span></span> <span data-ttu-id="b75f0-110">您可以使用内容搜索来搜索第三方数据, 或将其与高级电子数据展示事例中的保管人程序相关联。</span><span class="sxs-lookup"><span data-stu-id="b75f0-110">You can search third-party data using Content Search or associate it with a custodian in an Advanced eDiscovery case.</span></span> <span data-ttu-id="b75f0-111">使用示例连接器在 Office 365 中导入和存档第三方数据可帮助您的组织遵守政府和法规策略。</span><span class="sxs-lookup"><span data-stu-id="b75f0-111">Using sample connectors to import and archive third-party data in Office 365 can help your organization stay compliant with government and regulatory policies.</span></span>

> [!NOTE]
> <span data-ttu-id="b75f0-112">目前, 只有 Facebook 商业页面和[Twitter](archive-twitter-data-with-sample-connector.md)的示例连接器可供预览。</span><span class="sxs-lookup"><span data-stu-id="b75f0-112">Currently, only the sample connectors for Facebook Business pages and [Twitter](archive-twitter-data-with-sample-connector.md) is available for Preview.</span></span> <span data-ttu-id="b75f0-113">即将推出更多示例连接器。</span><span class="sxs-lookup"><span data-stu-id="b75f0-113">More sample connectors are coming soon.</span></span>


## <a name="prerequisites-for-setting-up-a-connector-for-facebook-business-pages"></a><span data-ttu-id="b75f0-114">设置用于 Facebook 商业页面的连接器的先决条件</span><span class="sxs-lookup"><span data-stu-id="b75f0-114">Prerequisites for setting up a connector for Facebook Business pages</span></span>

<span data-ttu-id="b75f0-115">您必须先完成以下先决条件, 然后才能在安全 & 合规中心中设置和配置示例连接器, 以便从组织的 Facebook 商业页面导入和存档数据。</span><span class="sxs-lookup"><span data-stu-id="b75f0-115">You must complete the following prerequisites before you can set up and configure a sample connector in the Security & Compliance Center to import and archive data from your organization's Facebook Business pages.</span></span> 

- <span data-ttu-id="b75f0-116">您的组织的业务页面需要一个 Facebook 帐户 (在设置连接器时, 需要登录到此帐户)。</span><span class="sxs-lookup"><span data-stu-id="b75f0-116">You need a Facebook account for your organization's business pages (you need to sign in to this account when setting up the connector).</span></span> <span data-ttu-id="b75f0-117">目前, 您只能存档 Facebook 商业页面中的数据;您不能存档单个 Facebook 配置文件中的数据。</span><span class="sxs-lookup"><span data-stu-id="b75f0-117">Currently, you can only archive data from Facebook Business pages; you can't archive data from individual Facebook profiles.</span></span>

- <span data-ttu-id="b75f0-118">您的组织必须具有有效的 Azure 订阅。</span><span class="sxs-lookup"><span data-stu-id="b75f0-118">Your organization must have a valid Azure subscription.</span></span> <span data-ttu-id="b75f0-119">如果你没有现有的 Azure 订阅, 你可以注册以下选项之一:</span><span class="sxs-lookup"><span data-stu-id="b75f0-119">If you don't have an existing Azure subscription, you can sign up for one of these options:</span></span>

    - [<span data-ttu-id="b75f0-120">注册免费的1年 Azure 订阅</span><span class="sxs-lookup"><span data-stu-id="b75f0-120">Sign up for a free 1 year Azure subscription</span></span>](https://azure.microsoft.com/free) 

    - [<span data-ttu-id="b75f0-121">注册 "转到即点即用 Azure 订阅"</span><span class="sxs-lookup"><span data-stu-id="b75f0-121">Sign up for a Pay-As-You-Go Azure subscription</span></span>](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/)

    > [!NOTE]
    > <span data-ttu-id="b75f0-122">Office 365 订阅附带的[免费 Azure Active Directory 订阅](use-your-free-azure-ad-subscription-in-office-365.md)不支持 Security _AMP_ 合规中心中的示例连接器。</span><span class="sxs-lookup"><span data-stu-id="b75f0-122">The [free Azure Active Directory subscription](use-your-free-azure-ad-subscription-in-office-365.md) that's included with your Office 365 subscription doesn't support the sample connectors in the Security & Compliance Center.</span></span>

- <span data-ttu-id="b75f0-123">您的组织必须同意允许 Office 365 导入服务访问组织中的邮箱数据。</span><span class="sxs-lookup"><span data-stu-id="b75f0-123">Your organization must consent to allow the Office 365 Import service to access mailbox data in your organization.</span></span> <span data-ttu-id="b75f0-124">若要同意此请求, 请转到[此页](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent), 使用 Office 365 全局管理员的凭据登录, 然后接受该请求。</span><span class="sxs-lookup"><span data-stu-id="b75f0-124">To consent to this request, go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent), sign in with the credentials of an Office 365 global admin, and then accept the request.</span></span>

- <span data-ttu-id="b75f0-125">在安全 & 合规性 (步骤 7) 中设置自定义连接器的用户必须在 Exchange Online 中分配邮箱导入导出角色。</span><span class="sxs-lookup"><span data-stu-id="b75f0-125">The user who sets up the custom connector in the Security & Compliance (in Step 7) must be assigned the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="b75f0-126">默认情况下, 此角色不会分配给 Exchange Online 中的任何角色组。</span><span class="sxs-lookup"><span data-stu-id="b75f0-126">By default, this role isn't assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="b75f0-127">您可以将邮箱导入导出角色添加到 Exchange Online 中的 "组织管理" 角色组。</span><span class="sxs-lookup"><span data-stu-id="b75f0-127">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="b75f0-128">或者, 您可以创建新的角色组, 分配邮箱导入导出角色, 然后将相应的用户添加为成员。</span><span class="sxs-lookup"><span data-stu-id="b75f0-128">Or you can create a new role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="b75f0-129">有关详细信息, 请参阅文章 "管理 Exchange Online 中的角色组" 中的 "[创建角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups)" 或 "[修改角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)" 部分。</span><span class="sxs-lookup"><span data-stu-id="b75f0-129">For more information, see the  [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-download-the-pre-built-connector-app-package-from-github"></a><span data-ttu-id="b75f0-130">步骤 1: 从 Github 下载预建的连接器应用程序包</span><span class="sxs-lookup"><span data-stu-id="b75f0-130">Step 1: Download the pre-built connector app package from Github</span></span>

<span data-ttu-id="b75f0-131">第一步是下载预构建的 Facebook 连接器应用程序的源代码, 该应用程序将使用 Facebook API 连接到你的 Facebook 商业页面并提取 Facebook 数据, 以便可以将其导入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="b75f0-131">The first step is to download the source code for the pre-built Facebook connector app that will use a Facebook API to connect to your Facebook Business pages and extract Facebook data so you can import it to Office 365.</span></span>

1. <span data-ttu-id="b75f0-132">转到[此 GitHub 网站](https://github.com/Microsoft/m365-sample-connector-csharp-aspnet/releases)。</span><span class="sxs-lookup"><span data-stu-id="b75f0-132">Go to [this GitHub site](https://github.com/Microsoft/m365-sample-connector-csharp-aspnet/releases).</span></span> 
2. <span data-ttu-id="b75f0-133">在最新版本下, 单击 " **SampleConnector** " 文件。</span><span class="sxs-lookup"><span data-stu-id="b75f0-133">Under the latest release, click the **SampleConnector.zip** file.</span></span>
3. <span data-ttu-id="b75f0-134">将 ZIP 文件保存到本地计算机上的某个位置。</span><span class="sxs-lookup"><span data-stu-id="b75f0-134">Save the ZIP file to a location on your local computer.</span></span> <span data-ttu-id="b75f0-135">你将在步骤4中将此 zip 文件上传到 Azure。</span><span class="sxs-lookup"><span data-stu-id="b75f0-135">You'll upload this zip file to Azure in Step 4.</span></span>

## <a name="step-2-create-an-app-in-azure-active-directory"></a><span data-ttu-id="b75f0-136">步骤 2: 在 Azure Active Directory 中创建应用程序</span><span class="sxs-lookup"><span data-stu-id="b75f0-136">Step 2: Create an app in Azure Active Directory</span></span>

<span data-ttu-id="b75f0-137">下一步是在 Azure Active Directory (AAD) 中注册新应用程序。</span><span class="sxs-lookup"><span data-stu-id="b75f0-137">The next step is to register a new app in Azure Active Directory (AAD).</span></span> <span data-ttu-id="b75f0-138">此应用程序将对应于您将在第4步中为 Facebook 连接器实现的 web 应用资源。</span><span class="sxs-lookup"><span data-stu-id="b75f0-138">This app will correspond to the web app resource that you'll implement in Step 4 for the Facebook connector.</span></span> 

<span data-ttu-id="b75f0-139">有关分步说明, 请参阅[在 Azure Active Directory 中创建应用](deploy-facebook-connector.md#step-2-create-an-app-in-azure-active-directory)。</span><span class="sxs-lookup"><span data-stu-id="b75f0-139">For step-by-step instructions, see [Create an app in Azure Active Directory](deploy-facebook-connector.md#step-2-create-an-app-in-azure-active-directory).</span></span>

<span data-ttu-id="b75f0-140">在完成此步骤 (按照分步说明操作) 后, 您将把以下信息保存到文本文件中。</span><span class="sxs-lookup"><span data-stu-id="b75f0-140">During the completion of this step (by following the step-by-step instructions), you'll save the following information to a text file.</span></span> <span data-ttu-id="b75f0-141">这些值将在部署过程的后续步骤中使用。</span><span class="sxs-lookup"><span data-stu-id="b75f0-141">The values for these will be used in later steps in the deployment process.</span></span>

- <span data-ttu-id="b75f0-142">AAD 应用程序 ID</span><span class="sxs-lookup"><span data-stu-id="b75f0-142">AAD application ID</span></span>
- <span data-ttu-id="b75f0-143">AAD 应用程序密码</span><span class="sxs-lookup"><span data-stu-id="b75f0-143">AAD application secret</span></span>
- <span data-ttu-id="b75f0-144">AAD 应用程序 Uri</span><span class="sxs-lookup"><span data-stu-id="b75f0-144">AAD application Uri</span></span>
- <span data-ttu-id="b75f0-145">租户 Id</span><span class="sxs-lookup"><span data-stu-id="b75f0-145">Tenant Id</span></span>

## <a name="step-3-create-an-azure-storage-account"></a><span data-ttu-id="b75f0-146">步骤 3: 创建 Azure 存储帐户</span><span class="sxs-lookup"><span data-stu-id="b75f0-146">Step 3: Create an Azure storage account</span></span>

<span data-ttu-id="b75f0-147">您为组织部署的 Facebook 连接器会将您的 Facebook 商业页面中的项目上载到您在此步骤中创建的 Azure 存储位置。</span><span class="sxs-lookup"><span data-stu-id="b75f0-147">The Facebook Connector that you deploy for your organization will upload the items from your Facebook Business pages to the Azure storage location that you create in this step.</span></span> <span data-ttu-id="b75f0-148">在 Security & 合规中心 (步骤 7) 中创建自定义连接器后, Office 365 导入服务会将 Facebook 数据从 Azure 存储位置复制到 Office 365 中的邮箱。</span><span class="sxs-lookup"><span data-stu-id="b75f0-148">After you create a custom connector in the Security & Compliance Center (in Step 7), the Office 365 Import service will copy the Facebook data from the Azure storage location to a mailbox in Office 365.</span></span> <span data-ttu-id="b75f0-149">如前面的 "[先决条件](#prerequisites-for-setting-up-a-connector-for-facebook-business-pages)" 部分中所述, 您必须具有有效的 azure 订阅才能创建 azure 存储帐户。</span><span class="sxs-lookup"><span data-stu-id="b75f0-149">As previous explained in the [Prerequisites](#prerequisites-for-setting-up-a-connector-for-facebook-business-pages) section, you must have a valid Azure subscription to create an Azure storage account.</span></span>

<span data-ttu-id="b75f0-150">有关分步说明, 请参阅[创建 Azure 存储帐户](deploy-facebook-connector.md#step-3-create-an-azure-storage-account)。</span><span class="sxs-lookup"><span data-stu-id="b75f0-150">For step-by-step instructions, see [Create an Azure storage account](deploy-facebook-connector.md#step-3-create-an-azure-storage-account).</span></span>

<span data-ttu-id="b75f0-151">在完成此步骤 (按照分步说明操作) 后, 将保存生成的连接字符串 Uri。</span><span class="sxs-lookup"><span data-stu-id="b75f0-151">During the completion of this step (by following the step-by-step instructions) you'll save the connection string Uri that is generated.</span></span> <span data-ttu-id="b75f0-152">在第4步中的 Azure 中创建 web 应用资源时, 将使用此字符串。</span><span class="sxs-lookup"><span data-stu-id="b75f0-152">You'll use this string when creating a web app resource in Azure in Step 4.</span></span>

## <a name="step-4-create-a-web-app-resource-in-azure"></a><span data-ttu-id="b75f0-153">步骤 4: 在 Azure 中创建 web 应用资源</span><span class="sxs-lookup"><span data-stu-id="b75f0-153">Step 4: Create a web app resource in Azure</span></span>

<span data-ttu-id="b75f0-154">下一步是在 Azure 中为 Facebook 连接器创建 web 应用资源。</span><span class="sxs-lookup"><span data-stu-id="b75f0-154">The next step is to create a web app resource in Azure for the Facebook Connector.</span></span> 

<span data-ttu-id="b75f0-155">有关分步说明, 请参阅[在 Azure 中创建新的 web 应用资源](deploy-facebook-connector.md#step-4-create-a-new-web-app-resource-in-azure)。</span><span class="sxs-lookup"><span data-stu-id="b75f0-155">For step-by-step instructions, see [Create a new web app resource in Azure](deploy-facebook-connector.md#step-4-create-a-new-web-app-resource-in-azure).</span></span>

<span data-ttu-id="b75f0-156">在完成此步骤 (按照分步说明操作) 后, 您将在创建 web 应用资源时提供以下信息 (在完成前面的步骤之后, 您已将其复制到文本文件中)。</span><span class="sxs-lookup"><span data-stu-id="b75f0-156">During the completion of this step (by following the step-by-step instructions), you'll provide the following information (that you've copied to a text file after completing the previous steps) when creating the web app resource.</span></span>

- <span data-ttu-id="b75f0-157">APISecretKey –你将在完成此步骤过程中创建此密码;它将在步骤7中使用。</span><span class="sxs-lookup"><span data-stu-id="b75f0-157">APISecretKey – You will create this secret during the completion of this step; it will be used in Step 7.</span></span>
- <span data-ttu-id="b75f0-158">StorageAccountConnectionString –在步骤3中创建 Azure 存储帐户后复制的连接字符串 Uri。</span><span class="sxs-lookup"><span data-stu-id="b75f0-158">StorageAccountConnectionString – The connection string Uri that you copied after creating the Azure storage account in Step 3.</span></span>
- <span data-ttu-id="b75f0-159">tenantId –在步骤2中创建 Azure Active Directory 中的 Facebook 连接器应用之后复制的 Office 365 组织的租户 ID。</span><span class="sxs-lookup"><span data-stu-id="b75f0-159">tenantId – The tenant ID of your Office 365 organization that you copied after creating the Facebook connector app in Azure Active Directory in Step 2.</span></span>

<span data-ttu-id="b75f0-160">此外, 在此步骤中, 您将上载在步骤1中下载的 SampleConnector 文件, 以部署 Facebook 连接器应用程序的源代码。</span><span class="sxs-lookup"><span data-stu-id="b75f0-160">Additionally, you will upload the SampleConnector.zip file (that you downloaded in Step 1) in this step to deploy the source code for the Facebook connector app.</span></span>

<span data-ttu-id="b75f0-161">完成此步骤后, 请务必复制应用服务 URL (例如, https://fbconnector.azurewebsites.net)。</span><span class="sxs-lookup"><span data-stu-id="b75f0-161">After completing this step, be sure to copy the app Service URL (for example, https://fbconnector.azurewebsites.net).</span></span> <span data-ttu-id="b75f0-162">您需要使用此操作来完成步骤5、步骤6和步骤7。</span><span class="sxs-lookup"><span data-stu-id="b75f0-162">You'll need to use this to complete Step 5, Step 6, and Step 7).</span></span>

## <a name="step-5-register-the-web-app-on-facebook"></a><span data-ttu-id="b75f0-163">步骤 5: 在 Facebook 上注册 web 应用程序</span><span class="sxs-lookup"><span data-stu-id="b75f0-163">Step 5: Register the web app on Facebook</span></span>

<span data-ttu-id="b75f0-164">下一步是在 Facebook 上创建和配置新的应用程序。</span><span class="sxs-lookup"><span data-stu-id="b75f0-164">The next step is to create and configure a new app on Facebook.</span></span> <span data-ttu-id="b75f0-165">您在步骤7中创建的自定义连接器将使用 Facebook web 应用与 Facebook API 进行交互, 以从组织的 Facebook 商业版页面中获取数据。</span><span class="sxs-lookup"><span data-stu-id="b75f0-165">The custom connector that you create in Step 7 will use the Facebook web app to interact with the Facebook API to obtain data from your organization's Facebook Business pages.</span></span>

<span data-ttu-id="b75f0-166">有关分步说明, 请参阅[注册 Facebook 应用](deploy-facebook-connector.md#step-5-register-the-facebook-app)。</span><span class="sxs-lookup"><span data-stu-id="b75f0-166">For step-by-step instructions, see [Register the Facebook app](deploy-facebook-connector.md#step-5-register-the-facebook-app).</span></span>

<span data-ttu-id="b75f0-167">在完成此步骤 (按照分步说明操作) 后, 您将把以下信息保存到文本文件中。</span><span class="sxs-lookup"><span data-stu-id="b75f0-167">During the completion of this step (by following the step-by-step instructions), you'll save the following information to a text file.</span></span> <span data-ttu-id="b75f0-168">这些值将用于配置步骤6中的 Facebook 连接器应用。</span><span class="sxs-lookup"><span data-stu-id="b75f0-168">The values for these will be used to configure the Facebook connector app in Step 6.</span></span>

- <span data-ttu-id="b75f0-169">Facebook 应用程序 ID</span><span class="sxs-lookup"><span data-stu-id="b75f0-169">Facebook application ID</span></span>
- <span data-ttu-id="b75f0-170">Facebook 应用程序密码</span><span class="sxs-lookup"><span data-stu-id="b75f0-170">Facebook application secret</span></span>
- <span data-ttu-id="b75f0-171">Facebook webhook verify token</span><span class="sxs-lookup"><span data-stu-id="b75f0-171">Facebook webhooks verify token</span></span>

## <a name="step-6-configure-the-facebook-connector-app"></a><span data-ttu-id="b75f0-172">步骤 6: 配置 Facebook 连接器应用程序</span><span class="sxs-lookup"><span data-stu-id="b75f0-172">Step 6: Configure the Facebook connector app</span></span>

<span data-ttu-id="b75f0-173">下一步是将配置设置添加到在步骤4中创建 Azure web 应用资源时上载的 Facebook 连接器应用。</span><span class="sxs-lookup"><span data-stu-id="b75f0-173">The next step is to add configurations settings to the Facebook connector app that you uploaded when you created the Azure web app resource in Step 4.</span></span> <span data-ttu-id="b75f0-174">你将通过转到连接器应用的主页并对其进行配置来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="b75f0-174">You'll do this by going to the home page of your connector app and configuring it.</span></span>

<span data-ttu-id="b75f0-175">有关分步说明, 请参阅 "[步骤 6: 配置连接器 web 应用程序"](deploy-facebook-connector.md#step-6-configure-the-connector-web-app)。</span><span class="sxs-lookup"><span data-stu-id="b75f0-175">For step-by-step instructions, see [Step 6: Configure the connector web app](deploy-facebook-connector.md#step-6-configure-the-connector-web-app).</span></span>

<span data-ttu-id="b75f0-176">在完成此步骤 (按照分步说明操作) 后, 您将提供以下信息 (在完成上述步骤后, 您已将其复制到文本文件中):</span><span class="sxs-lookup"><span data-stu-id="b75f0-176">During the completion of this step (by following the step-by-step instructions), you'll provide the following information (that you've copied to a text file after completing the previous steps):</span></span>

- <span data-ttu-id="b75f0-177">Facebook 应用程序 ID (在步骤5中获取)</span><span class="sxs-lookup"><span data-stu-id="b75f0-177">Facebook application ID (obtained in Step 5)</span></span>
- <span data-ttu-id="b75f0-178">Facebook 应用程序密码 (在步骤5中获取)</span><span class="sxs-lookup"><span data-stu-id="b75f0-178">Facebook application secret (obtained in Step 5)</span></span>
- <span data-ttu-id="b75f0-179">Facebook webhook verify token (在步骤5中获取)</span><span class="sxs-lookup"><span data-stu-id="b75f0-179">Facebook webhooks verify token (obtained in Step 5)</span></span>
- <span data-ttu-id="b75f0-180">Azure Active Directory 应用程序 ID (在步骤2中获取的 AAD 应用程序 ID)</span><span class="sxs-lookup"><span data-stu-id="b75f0-180">Azure Active Directory application ID (the AAD application ID obtained in Step 2)</span></span>
- <span data-ttu-id="b75f0-181">Azure Active Directory 应用程序密码 (在步骤2中获取的 AAD 应用程序密码)</span><span class="sxs-lookup"><span data-stu-id="b75f0-181">Azure Active Directory application secret (the AAD application secret obtained in Step 2)</span></span>
- <span data-ttu-id="b75f0-182">Azure Active Directory 应用程序 Uri (在步骤2中获取的 AAD 应用程序 Uri; 例如,https://microsoft.onmicrosoft.com/2688yu6n-12q3-23we-e3ee-121111123213)</span><span class="sxs-lookup"><span data-stu-id="b75f0-182">Azure Active Directory application Uri (the AAD application Uri obtained in Step 2; for example, https://microsoft.onmicrosoft.com/2688yu6n-12q3-23we-e3ee-121111123213)</span></span>

## <a name="step-7-set-up-a-custom-connector-in-the-security--compliance-center"></a><span data-ttu-id="b75f0-183">步骤 7: 在安全 & 合规中心中设置自定义连接器</span><span class="sxs-lookup"><span data-stu-id="b75f0-183">Step 7: Set up a custom connector in the Security & Compliance Center</span></span>

<span data-ttu-id="b75f0-184">最后一步是在安全 & 合规性中心中设置自定义连接器, 以将来自 Facebook 商业页面的数据导入 Office 365 中的指定邮箱。</span><span class="sxs-lookup"><span data-stu-id="b75f0-184">The final step is to set up the custom connector in the Security & Compliance Center that will import data from your Facebook Business pages to a specified mailbox in Office 365.</span></span> <span data-ttu-id="b75f0-185">在成功完成此步骤后, Office 365 导入服务将启动从 Facebook 商业版页面向 Office 365 导入数据的过程。</span><span class="sxs-lookup"><span data-stu-id="b75f0-185">After you successfully complete this step, the Office 365 Import service will start the process of importing data from your Facebook Business pages to Office 365.</span></span> 

<span data-ttu-id="b75f0-186">有关分步说明, 请参阅[在安全 _AMP_ 合规中心中设置自定义连接器](deploy-facebook-connector.md#step-7-set-up-a-custom-connector-in-the-security--compliance-center)。</span><span class="sxs-lookup"><span data-stu-id="b75f0-186">For step-by-step instructions, see [Set up a custom connector in the Security & Compliance Center](deploy-facebook-connector.md#step-7-set-up-a-custom-connector-in-the-security--compliance-center).</span></span> 

<span data-ttu-id="b75f0-187">在完成此步骤 (按照分步说明操作) 后, 您将提供以下信息 (在完成这些步骤后, 您已将其复制到文本文件中)。</span><span class="sxs-lookup"><span data-stu-id="b75f0-187">During the completion of this step (by following the step-by-step instructions), you'll provide the following information (that you've copied to a text file after completing the steps).</span></span>

- <span data-ttu-id="b75f0-188">Azure 应用服务 URL (在步骤4中获取; 例如https://fbconnector.azurewebsites.net)</span><span class="sxs-lookup"><span data-stu-id="b75f0-188">Azure app service URL (obtained in Step 4; for example https://fbconnector.azurewebsites.net)</span></span>
- <span data-ttu-id="b75f0-189">APISecretKey (您在步骤4中创建)</span><span class="sxs-lookup"><span data-stu-id="b75f0-189">APISecretKey (that you created in Step 4)</span></span>
