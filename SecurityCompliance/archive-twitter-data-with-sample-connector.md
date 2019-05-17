---
title: 使用示例连接器在 Office 365 中存档 Twitter 数据 (预览)
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
description: 管理员可以设置本机连接器以将 Twitter 数据导入 Office 365。 这使您可以在 Office 365 中存档第三方数据源中的数据, 以便您可以使用合规性功能 (如法律封存、内容搜索和保留策略) 来管理组织的第三方数据的管理。
ms.openlocfilehash: b561c5f471988e567624b49475bbf24a6dd88a2a
ms.sourcegitcommit: 5bd7a97aeab1c89e0a3660ba7bdb3200224107a1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/16/2019
ms.locfileid: "34103798"
---
# <a name="use-a-sample-connector-to-archive-twitter-data-in-office-365-preview"></a><span data-ttu-id="8ee1b-104">使用示例连接器在 Office 365 中存档 Twitter 数据 (预览)</span><span class="sxs-lookup"><span data-stu-id="8ee1b-104">Use a sample connector to archive Twitter data in Office 365 (Preview)</span></span>

<span data-ttu-id="8ee1b-105">在 Office 365 中存档 Twitter 数据的示例连接器功能处于预览阶段。</span><span class="sxs-lookup"><span data-stu-id="8ee1b-105">The sample connector feature to archive Twitter data in Office 365 is in Preview.</span></span>

<span data-ttu-id="8ee1b-106">在 Office 365 的 Security & 合规性中心中使用示例连接器, 以从 Twitter 导入和存档数据。</span><span class="sxs-lookup"><span data-stu-id="8ee1b-106">Use a sample connector in the Security & Compliance Center in Office 365 to import and archive data from Twitter.</span></span> <span data-ttu-id="8ee1b-107">在设置和配置示例连接器之后, 它会连接到您的组织的 Twitter 帐户 (根据计划), 将项目的内容转换为电子邮件格式, 然后将这些项目导入到 Office 365 中的邮箱中。</span><span class="sxs-lookup"><span data-stu-id="8ee1b-107">After you set up and configure a sample connector, it connects to your organization's Twitter account (on a scheduled basis), converts the content of an item to an email message format, and then imports those items to a mailbox in Office 365.</span></span>

<span data-ttu-id="8ee1b-108">在导入 Twitter 数据之后, 您可以将 Office 365 合规性功能 (如诉讼保留、内容搜索、就地存档、审核、监督和 Office 365 保留策略) 应用于邮箱中存储的数据。</span><span class="sxs-lookup"><span data-stu-id="8ee1b-108">After Twitter data is imported, you can apply Office 365 compliance features such as Litigation Hold, Content Search, In-Place Archiving, Auditing, Supervision, and Office 365 retention policies to the data stored in the mailbox.</span></span> <span data-ttu-id="8ee1b-109">例如, 您可以使用内容搜索来搜索第三方数据, 或将其与高级电子数据展示事例中的保管人程序相关联。</span><span class="sxs-lookup"><span data-stu-id="8ee1b-109">For example,you can search third-party data using Content Search or associate it with a custodian in an Advanced eDiscovery case.</span></span> <span data-ttu-id="8ee1b-110">使用示例连接器在 Office 365 中导入和存档 Twitter 数据可帮助您的组织遵守政府和法规策略。</span><span class="sxs-lookup"><span data-stu-id="8ee1b-110">Using sample connectors to import and archive Twitter data in Office 365 can help your organization stay compliant with government and regulatory policies.</span></span>

> [!NOTE]
> <span data-ttu-id="8ee1b-111">目前, 仅可使用 Twitter 和[Facebook 商业页面](archive-facebook-data-with-sample-connector.md)的示例连接器进行预览。</span><span class="sxs-lookup"><span data-stu-id="8ee1b-111">Currently, only the sample connectors for Twitter and [Facebook Business pages](archive-facebook-data-with-sample-connector.md) are available for Preview.</span></span> <span data-ttu-id="8ee1b-112">即将推出更多示例连接器。</span><span class="sxs-lookup"><span data-stu-id="8ee1b-112">More sample connectors are coming soon.</span></span>


## <a name="prerequisites-for-setting-up-a-connector-for-twitter"></a><span data-ttu-id="8ee1b-113">为 Twitter 设置连接器的先决条件</span><span class="sxs-lookup"><span data-stu-id="8ee1b-113">Prerequisites for setting up a connector for Twitter</span></span>

<span data-ttu-id="8ee1b-114">必须先完成以下先决条件, 然后才能在 Security & 合规性中心中设置和配置示例连接器, 以便从组织的 Twitter 帐户导入和存档数据。</span><span class="sxs-lookup"><span data-stu-id="8ee1b-114">You must complete the following prerequisites before you can set up and configure a sample connector in the Security & Compliance Center to import and archive data from your organization's Twitter account.</span></span> 

- <span data-ttu-id="8ee1b-115">您的组织需要 Twitter 帐户;设置连接器时, 需要登录到此帐户。</span><span class="sxs-lookup"><span data-stu-id="8ee1b-115">You need a Twitter account for your organization; you'll need to sign in to this account when setting up the connector.</span></span>

- <span data-ttu-id="8ee1b-116">您的组织必须具有有效的 Azure 订阅。</span><span class="sxs-lookup"><span data-stu-id="8ee1b-116">Your organization must have a valid Azure subscription.</span></span> <span data-ttu-id="8ee1b-117">如果你没有现有的 Azure 订阅, 你可以注册以下选项之一:</span><span class="sxs-lookup"><span data-stu-id="8ee1b-117">If you don't have an existing Azure subscription, you can sign up for one of these options:</span></span>

    - [<span data-ttu-id="8ee1b-118">注册免费的1年 Azure 订阅</span><span class="sxs-lookup"><span data-stu-id="8ee1b-118">Sign up for a free 1 year Azure subscription</span></span>](https://azure.microsoft.com/free) 

    - [<span data-ttu-id="8ee1b-119">注册 "转到即点即用 Azure 订阅"</span><span class="sxs-lookup"><span data-stu-id="8ee1b-119">Sign up for a Pay-As-You-Go Azure subscription</span></span>](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/)

    > [!NOTE]
    > <span data-ttu-id="8ee1b-120">Office 365 订阅附带的[免费 Azure Active Directory 订阅](use-your-free-azure-ad-subscription-in-office-365.md)不支持 Security _AMP_ 合规中心中的示例连接器。</span><span class="sxs-lookup"><span data-stu-id="8ee1b-120">The [free Azure Active Directory subscription](use-your-free-azure-ad-subscription-in-office-365.md) that's included with your Office 365 subscription doesn't support the sample connectors in the Security & Compliance Center.</span></span>

- <span data-ttu-id="8ee1b-121">您的组织必须同意允许 Office 365 导入服务访问组织中的邮箱数据。</span><span class="sxs-lookup"><span data-stu-id="8ee1b-121">Your organization must consent to allow the Office 365 Import service to access mailbox data in your organization.</span></span> <span data-ttu-id="8ee1b-122">若要同意此请求, 请转到[此页](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent), 使用 Office 365 全局管理员的凭据登录, 然后接受该请求。</span><span class="sxs-lookup"><span data-stu-id="8ee1b-122">To consent to this request, go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent), sign in with the credentials of an Office 365 global admin, and then accept the request.</span></span>

- <span data-ttu-id="8ee1b-123">在安全 & 合规性 (步骤 7) 中设置自定义连接器的用户必须在 Exchange Online 中分配邮箱导入导出角色。</span><span class="sxs-lookup"><span data-stu-id="8ee1b-123">The user who sets up the custom connector in the Security & Compliance (in Step 7) must be assigned the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="8ee1b-124">默认情况下, 此角色不会分配给 Exchange Online 中的任何角色组。</span><span class="sxs-lookup"><span data-stu-id="8ee1b-124">By default, this role isn't assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="8ee1b-125">您可以将邮箱导入导出角色添加到 Exchange Online 中的 "组织管理" 角色组。</span><span class="sxs-lookup"><span data-stu-id="8ee1b-125">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="8ee1b-126">或者, 您可以创建新的角色组, 分配邮箱导入导出角色, 然后将相应的用户添加为成员。</span><span class="sxs-lookup"><span data-stu-id="8ee1b-126">Or you can create a new role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="8ee1b-127">有关详细信息, 请参阅文章 "管理 Exchange Online 中的角色组" 中的 "[创建角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups)" 或 "[修改角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)" 部分。</span><span class="sxs-lookup"><span data-stu-id="8ee1b-127">For more information, see the  [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-download-the-pre-built-connector-app-package-from-github"></a><span data-ttu-id="8ee1b-128">步骤 1: 从 Github 下载预建的连接器应用程序包</span><span class="sxs-lookup"><span data-stu-id="8ee1b-128">Step 1: Download the pre-built connector app package from Github</span></span>

<span data-ttu-id="8ee1b-129">第一步是下载将使用 Twitter API 连接到 Twitter 帐户并提取数据的 Twitter 示例连接器应用的源代码, 以便您可以将数据导入到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="8ee1b-129">The first step is to download the source code for the Twitter sample connector app that will use a Twitter API to connect to your Twitter account and extract data so you can import it to Office 365.</span></span>

1. <span data-ttu-id="8ee1b-130">转到[此 GitHub 网站](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet/releases)。</span><span class="sxs-lookup"><span data-stu-id="8ee1b-130">Go to [this GitHub site](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet/releases).</span></span> 
2. <span data-ttu-id="8ee1b-131">在最新版本下, 单击 " **SampleConnector** " 文件。</span><span class="sxs-lookup"><span data-stu-id="8ee1b-131">Under the latest release, click the **SampleConnector.zip** file.</span></span>
3. <span data-ttu-id="8ee1b-132">将 ZIP 文件保存到本地计算机上的某个位置。</span><span class="sxs-lookup"><span data-stu-id="8ee1b-132">Save the ZIP file to a location on your local computer.</span></span> <span data-ttu-id="8ee1b-133">你将在步骤4中将此 zip 文件上传到 Azure。</span><span class="sxs-lookup"><span data-stu-id="8ee1b-133">You'll upload this zip file to Azure in Step 4.</span></span>

## <a name="step-2-create-an-app-in-azure-active-directory"></a><span data-ttu-id="8ee1b-134">步骤 2: 在 Azure Active Directory 中创建应用程序</span><span class="sxs-lookup"><span data-stu-id="8ee1b-134">Step 2: Create an app in Azure Active Directory</span></span>

<span data-ttu-id="8ee1b-135">下一步是在 Azure Active Directory (AAD) 中注册新应用程序。</span><span class="sxs-lookup"><span data-stu-id="8ee1b-135">The next step is to register a new app in Azure Active Directory (AAD).</span></span> <span data-ttu-id="8ee1b-136">此应用程序将对应于您将在您在 Twitter 连接器的步骤4中实现的 web 应用资源。</span><span class="sxs-lookup"><span data-stu-id="8ee1b-136">This app will correspond to the web app resource that you'll implement in Step 4 for the Twitter connector.</span></span> 

<span data-ttu-id="8ee1b-137">有关分步说明, 请参阅["步骤 2: 在 Azure Active Directory 中创建应用程序](deploy-twitter-connector.md#step-2-create-an-app-in-azure-active-directory)"。</span><span class="sxs-lookup"><span data-stu-id="8ee1b-137">For step-by-step instructions, see [Step 2: Create an app in Azure Active Directory](deploy-twitter-connector.md#step-2-create-an-app-in-azure-active-directory).</span></span>

<span data-ttu-id="8ee1b-138">在完成此步骤 (按照分步说明操作) 后, 您将把以下信息保存到文本文件中。</span><span class="sxs-lookup"><span data-stu-id="8ee1b-138">During the completion of this step (by following the step-by-step instructions), you'll save the following information to a text file.</span></span> <span data-ttu-id="8ee1b-139">这些值将在部署过程的后续步骤中使用。</span><span class="sxs-lookup"><span data-stu-id="8ee1b-139">The values for these will be used in later steps in the deployment process.</span></span>

- <span data-ttu-id="8ee1b-140">AAD 应用程序 ID</span><span class="sxs-lookup"><span data-stu-id="8ee1b-140">AAD application ID</span></span>
- <span data-ttu-id="8ee1b-141">AAD 应用程序密码</span><span class="sxs-lookup"><span data-stu-id="8ee1b-141">AAD application secret</span></span>
- <span data-ttu-id="8ee1b-142">AAD 应用程序 Uri</span><span class="sxs-lookup"><span data-stu-id="8ee1b-142">AAD application Uri</span></span>
- <span data-ttu-id="8ee1b-143">租户 Id</span><span class="sxs-lookup"><span data-stu-id="8ee1b-143">Tenant Id</span></span>

## <a name="step-3-create-an-azure-storage-account"></a><span data-ttu-id="8ee1b-144">步骤 3: 创建 Azure 存储帐户</span><span class="sxs-lookup"><span data-stu-id="8ee1b-144">Step 3: Create an Azure storage account</span></span>

<span data-ttu-id="8ee1b-145">为您的组织部署的 Twitter 连接器会将这些项目从 Twitter 上传到您在此步骤中创建的 Azure 存储位置。</span><span class="sxs-lookup"><span data-stu-id="8ee1b-145">The Twitter connector that you deploy for your organization will upload the items from Twitter to the Azure storage location that you create in this step.</span></span> <span data-ttu-id="8ee1b-146">在 Security & 合规中心 (步骤 7) 中创建自定义连接器后, Office 365 导入服务会将 Twitter 数据从 Azure 存储位置复制到 Office 365 中的邮箱。</span><span class="sxs-lookup"><span data-stu-id="8ee1b-146">After you create a custom connector in the Security & Compliance Center (in Step 7), the Office 365 Import service will copy the Twitter data from the Azure storage location to a mailbox in Office 365.</span></span> <span data-ttu-id="8ee1b-147">如前面的 "[先决条件](#prerequisites-for-setting-up-a-connector-for-twitter)" 部分中所述, 您必须具有有效的 azure 订阅才能创建 azure 存储帐户。</span><span class="sxs-lookup"><span data-stu-id="8ee1b-147">As previous explained in the [Prerequisites](#prerequisites-for-setting-up-a-connector-for-twitter) section, you must have a valid Azure subscription to create an Azure storage account.</span></span>

<span data-ttu-id="8ee1b-148">有关分步说明, 请参阅[第3步: 创建 Azure 存储帐户](deploy-twitter-connector.md#step-3-create-an-azure-storage-account)。</span><span class="sxs-lookup"><span data-stu-id="8ee1b-148">For step-by-step instructions, see [Step 3: Create an Azure storage account](deploy-twitter-connector.md#step-3-create-an-azure-storage-account).</span></span>

<span data-ttu-id="8ee1b-149">在完成此步骤 (按照分步说明操作) 后, 将保存生成的连接字符串 Uri。</span><span class="sxs-lookup"><span data-stu-id="8ee1b-149">During the completion of this step (by following the step-by-step instructions) you'll save the connection string Uri that is generated.</span></span> <span data-ttu-id="8ee1b-150">在第4步中的 Azure 中创建 web 应用资源时, 将使用此字符串。</span><span class="sxs-lookup"><span data-stu-id="8ee1b-150">You'll use this string when creating a web app resource in Azure in Step 4.</span></span>

## <a name="step-4-create-a-web-app-resource-in-azure"></a><span data-ttu-id="8ee1b-151">步骤 4: 在 Azure 中创建 web 应用资源</span><span class="sxs-lookup"><span data-stu-id="8ee1b-151">Step 4: Create a web app resource in Azure</span></span>

<span data-ttu-id="8ee1b-152">下一步是在 Azure 中为 Twitter 连接器创建 web 应用资源。</span><span class="sxs-lookup"><span data-stu-id="8ee1b-152">The next step is to create a web app resource in Azure for the Twitter connector.</span></span> 

<span data-ttu-id="8ee1b-153">有关分步说明, 请参阅[第4步: 在 Azure 中创建新的 web 应用资源](deploy-twitter-connector.md#step-4-create-a-new-web-app-resource-in-azure)。</span><span class="sxs-lookup"><span data-stu-id="8ee1b-153">For step-by-step instructions, see [Step 4: Create a new web app resource in Azure](deploy-twitter-connector.md#step-4-create-a-new-web-app-resource-in-azure).</span></span>

<span data-ttu-id="8ee1b-154">在完成此步骤 (按照分步说明操作) 后, 您将在创建 web 应用资源时提供以下信息 (在完成前面的步骤之后, 您已将其复制到文本文件中)。</span><span class="sxs-lookup"><span data-stu-id="8ee1b-154">During the completion of this step (by following the step-by-step instructions), you'll provide the following information (that you've copied to a text file after completing the previous steps) when creating the web app resource.</span></span>

- <span data-ttu-id="8ee1b-155">APISecretKey –你将在完成此步骤过程中创建此密码;它将在步骤7中使用。</span><span class="sxs-lookup"><span data-stu-id="8ee1b-155">APISecretKey – You will create this secret during the completion of this step; it will be used in Step 7.</span></span>
- <span data-ttu-id="8ee1b-156">StorageAccountConnectionString –在步骤3中创建 Azure 存储帐户后复制的连接字符串 Uri。</span><span class="sxs-lookup"><span data-stu-id="8ee1b-156">StorageAccountConnectionString – The connection string Uri that you copied after creating the Azure storage account in Step 3.</span></span>
- <span data-ttu-id="8ee1b-157">tenantId –在步骤2中创建 Azure Active Directory 中的 Twitter 连接器应用之后复制的 Office 365 组织的租户 ID。</span><span class="sxs-lookup"><span data-stu-id="8ee1b-157">tenantId – The tenant ID of your Office 365 organization that you copied after creating the Twitter connector app in Azure Active Directory in Step 2.</span></span>

<span data-ttu-id="8ee1b-158">此外, 在此步骤中, 您将上载在步骤1中下载的 SampleConnector 文件, 以部署 Twitter 连接器应用的源代码。</span><span class="sxs-lookup"><span data-stu-id="8ee1b-158">Additionally, you will upload the SampleConnector.zip file (that you downloaded in Step 1) in this step to deploy the source code for the Twitter connector app.</span></span>

<span data-ttu-id="8ee1b-159">完成此步骤后, 请务必复制 Azure 应用服务 URL (例如, https://twitterconnector.azurewebsites.net)。</span><span class="sxs-lookup"><span data-stu-id="8ee1b-159">After completing this step, be sure to copy the Azure app service URL (for example, https://twitterconnector.azurewebsites.net).</span></span> <span data-ttu-id="8ee1b-160">您需要使用此操作来完成步骤5、步骤6和步骤7。</span><span class="sxs-lookup"><span data-stu-id="8ee1b-160">You'll need to use this to complete Step 5, Step 6, and Step 7).</span></span>

## <a name="step-5-create-developer-app-on-twitter"></a><span data-ttu-id="8ee1b-161">步骤 5: 在 Twitter 上创建开发人员应用</span><span class="sxs-lookup"><span data-stu-id="8ee1b-161">Step 5: Create developer app on Twitter</span></span>

<span data-ttu-id="8ee1b-162">下一步是在 Twitter 上创建和配置开发人员应用程序。</span><span class="sxs-lookup"><span data-stu-id="8ee1b-162">The next step is to create and configure a developer app on Twitter.</span></span> <span data-ttu-id="8ee1b-163">您在步骤7中创建的自定义连接器将使用 Twitter 应用与 Twitter API 进行交互, 以从组织的 Twitter 帐户中获取数据。</span><span class="sxs-lookup"><span data-stu-id="8ee1b-163">The custom connector that you create in Step 7 will use the Twitter app to interact with the Twitter API to obtain data from your organization's Twitter account.</span></span>

<span data-ttu-id="8ee1b-164">有关分步说明, 请参阅[第5步: 创建 Twitter 应用](deploy-twitter-connector.md#step-5-create-the-twitter-app)。</span><span class="sxs-lookup"><span data-stu-id="8ee1b-164">For step-by-step instructions, see [Step 5: Create the Twitter app](deploy-twitter-connector.md#step-5-create-the-twitter-app).</span></span>

<span data-ttu-id="8ee1b-165">在完成此步骤 (按照分步说明操作) 后, 您将把以下信息保存到文本文件中。</span><span class="sxs-lookup"><span data-stu-id="8ee1b-165">During the completion of this step (by following the step-by-step instructions), you'll save the following information to a text file.</span></span> <span data-ttu-id="8ee1b-166">这些值将用于在步骤6中配置 Twitter 连接器应用。</span><span class="sxs-lookup"><span data-stu-id="8ee1b-166">The values for these will be used to configure the Twitter connector app in Step 6.</span></span>

- <span data-ttu-id="8ee1b-167">Twitter 应用程序 ID</span><span class="sxs-lookup"><span data-stu-id="8ee1b-167">Twitter application ID</span></span>
- <span data-ttu-id="8ee1b-168">Twitter 应用程序密码 (API 密钥)</span><span class="sxs-lookup"><span data-stu-id="8ee1b-168">Twitter application secret (API secret key)</span></span>
- <span data-ttu-id="8ee1b-169">Twitter 客户端令牌</span><span class="sxs-lookup"><span data-stu-id="8ee1b-169">Twitter client token</span></span>
- <span data-ttu-id="8ee1b-170">Twitter 客户端令牌机密</span><span class="sxs-lookup"><span data-stu-id="8ee1b-170">Twitter client token secret</span></span>

## <a name="step-6-configure-the-twitter-connector-app"></a><span data-ttu-id="8ee1b-171">步骤 6: 配置 Twitter 连接器应用</span><span class="sxs-lookup"><span data-stu-id="8ee1b-171">Step 6: Configure the Twitter connector app</span></span>

<span data-ttu-id="8ee1b-172">下一步是将配置设置添加到在步骤4中创建 Azure web 应用资源时上载的 Twitter 连接器应用。</span><span class="sxs-lookup"><span data-stu-id="8ee1b-172">The next step is to add configurations settings to the Twitter connector app that you uploaded when you created the Azure web app resource in Step 4.</span></span> <span data-ttu-id="8ee1b-173">你将通过转到连接器应用的主页并对其进行配置来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="8ee1b-173">You'll do this by going to the home page of your connector app and configuring it.</span></span>

<span data-ttu-id="8ee1b-174">有关分步说明, 请参阅 "[步骤 6: 配置连接器 web 应用程序"](deploy-twitter-connector.md#step-6-configure-the-connector-web-app)。</span><span class="sxs-lookup"><span data-stu-id="8ee1b-174">For step-by-step instructions, see [Step 6: Configure the connector web app](deploy-twitter-connector.md#step-6-configure-the-connector-web-app).</span></span>

<span data-ttu-id="8ee1b-175">在完成此步骤 (按照分步说明操作) 后, 您将提供以下信息 (在完成上述步骤后, 您已将其复制到文本文件中):</span><span class="sxs-lookup"><span data-stu-id="8ee1b-175">During the completion of this step (by following the step-by-step instructions), you'll provide the following information (that you've copied to a text file after completing the previous steps):</span></span>

- <span data-ttu-id="8ee1b-176">Twitter 应用程序 ID (在步骤5中获取)</span><span class="sxs-lookup"><span data-stu-id="8ee1b-176">Twitter application ID (obtained in Step 5)</span></span>
- <span data-ttu-id="8ee1b-177">Twitter 应用程序密码 (在步骤5中获取)</span><span class="sxs-lookup"><span data-stu-id="8ee1b-177">Twitter application secret (obtained in Step 5)</span></span>
- <span data-ttu-id="8ee1b-178">Twitter 客户端令牌 (在步骤5中获取)</span><span class="sxs-lookup"><span data-stu-id="8ee1b-178">Twitter client token (obtained in Step 5)</span></span>
- <span data-ttu-id="8ee1b-179">Twitter 客户端令牌机密 (在步骤5中获取)</span><span class="sxs-lookup"><span data-stu-id="8ee1b-179">Twitter client token secret (obtained in Step 5)</span></span>
- <span data-ttu-id="8ee1b-180">Azure Active Directory 应用程序 ID (在步骤2中获取的 AAD 应用程序 ID)</span><span class="sxs-lookup"><span data-stu-id="8ee1b-180">Azure Active Directory application ID (the AAD application ID obtained in Step 2)</span></span>
- <span data-ttu-id="8ee1b-181">Azure Active Directory 应用程序密码 (在步骤2中获取的 AAD 应用程序密码)</span><span class="sxs-lookup"><span data-stu-id="8ee1b-181">Azure Active Directory application secret (the AAD application secret obtained in Step 2)</span></span>
- <span data-ttu-id="8ee1b-182">Azure Active Directory 应用程序 Uri (在步骤2中获取的 AAD 应用程序 Uri; 例如,https://microsoft.onmicrosoft.com/2688yu6n-12q3-23we-e3ee-121111123213)</span><span class="sxs-lookup"><span data-stu-id="8ee1b-182">Azure Active Directory application Uri (the AAD application Uri obtained in Step 2; for example, https://microsoft.onmicrosoft.com/2688yu6n-12q3-23we-e3ee-121111123213)</span></span>

## <a name="step-7-set-up-a-custom-connector-in-the-security--compliance-center"></a><span data-ttu-id="8ee1b-183">步骤 7: 在安全 & 合规中心中设置自定义连接器</span><span class="sxs-lookup"><span data-stu-id="8ee1b-183">Step 7: Set up a custom connector in the Security & Compliance Center</span></span>

<span data-ttu-id="8ee1b-184">最后一步是在安全 & 合规性中心中设置自定义连接器, 将组织的 Twitter 帐户中的数据导入 Office 365 中的指定邮箱。</span><span class="sxs-lookup"><span data-stu-id="8ee1b-184">The final step is to set up the custom connector in the Security & Compliance Center that will import data from your organization's Twitter account to a specified mailbox in Office 365.</span></span> <span data-ttu-id="8ee1b-185">在成功完成此步骤后, Office 365 导入服务将启动从 Twitter 向 Office 365 导入数据的过程。</span><span class="sxs-lookup"><span data-stu-id="8ee1b-185">After you successfully complete this step, the Office 365 Import service will start the process of importing data from Twitter to Office 365.</span></span> 

<span data-ttu-id="8ee1b-186">有关分步说明, 请参阅[第7步: 在安全与合规中心中设置自定义连接器](deploy-twitter-connector.md#step-7-set-up-a-custom-connector-in-the-security-and-compliance-center)。</span><span class="sxs-lookup"><span data-stu-id="8ee1b-186">For step-by-step instructions, see [Step 7: Set up a custom connector in the security and compliance center](deploy-twitter-connector.md#step-7-set-up-a-custom-connector-in-the-security-and-compliance-center).</span></span> 

<span data-ttu-id="8ee1b-187">在完成此步骤 (按照分步说明操作) 后, 您将提供以下信息 (在完成这些步骤后, 您已将其复制到文本文件中)。</span><span class="sxs-lookup"><span data-stu-id="8ee1b-187">During the completion of this step (by following the step-by-step instructions), you'll provide the following information (that you've copied to a text file after completing the steps).</span></span>

- <span data-ttu-id="8ee1b-188">Azure 应用服务 URL (在步骤4中获取; 例如https://twitterconnector.azurewebsites.net)</span><span class="sxs-lookup"><span data-stu-id="8ee1b-188">Azure app service URL (obtained in Step 4; for example https://twitterconnector.azurewebsites.net)</span></span>
- <span data-ttu-id="8ee1b-189">APISecretKey (您在步骤4中创建)</span><span class="sxs-lookup"><span data-stu-id="8ee1b-189">APISecretKey (that you created in Step 4)</span></span>
