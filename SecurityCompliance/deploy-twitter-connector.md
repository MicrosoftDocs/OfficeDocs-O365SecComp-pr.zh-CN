---
title: 部署连接器以在 Office 365 中存档 Twitter 数据
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
ROBOTS: NOINDEX, NOFOLLOW
description: 管理员可以设置本机连接器以将 Twitter 数据导入和存档到 Office 365。 将此数据导入 Office 365 后, 您可以使用合规性功能 (如法律封存、内容搜索和保留策略) 来管理组织的 Twitter 数据的管理。
ms.openlocfilehash: c3c5af0fc42057d9fc2e8b8e67423398d6ed0ddf
ms.sourcegitcommit: f2798d46acfbd56314e809cd3fe0350be807e420
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/17/2019
ms.locfileid: "35014771"
---
# <a name="deploy-a-connector-to-archive-twitter-data-in-office-365"></a><span data-ttu-id="5330c-104">部署连接器以在 Office 365 中存档 Twitter 数据</span><span class="sxs-lookup"><span data-stu-id="5330c-104">Deploy a connector to archive Twitter data in Office 365</span></span>

<span data-ttu-id="5330c-105">本文包含的分步过程可部署使用 Office 365 导入服务将数据从组织的 Twitter 帐户导入 Office 365 的连接器。</span><span class="sxs-lookup"><span data-stu-id="5330c-105">This article contains the step-by-step process to deploy a connector that uses the Office 365 Import service to import data from your organization's Twitter account to Office 365.</span></span> <span data-ttu-id="5330c-106">有关此过程的高级概述以及部署 Twitter 连接器所需的先决条件列表, 请参阅[使用示例连接器在 Office 365 中存档 Twitter 数据 (预览)](archive-twitter-data-with-sample-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="5330c-106">For a high-level overview of this process and a list of prerequisites required to deploy a Twitter connector, see [Use a sample connector to archive Twitter data in Office 365 (Preview)](archive-twitter-data-with-sample-connector.md).</span></span> 

## <a name="step-1-download-the-package"></a><span data-ttu-id="5330c-107">步骤 1: 下载程序包</span><span class="sxs-lookup"><span data-stu-id="5330c-107">Step 1: Download the package</span></span>

<span data-ttu-id="5330c-108">从位于 GitHub 存储库中的 "发布" 部分下载预[https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet/releases](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet/releases)建程序包 (网址为)。</span><span class="sxs-lookup"><span data-stu-id="5330c-108">Download the prebuilt package from the Release section in the GitHub repository at [https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet/releases](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet/releases).</span></span> <span data-ttu-id="5330c-109">在最新版本下, 下载名为**SampleConnector**的 zip 文件。</span><span class="sxs-lookup"><span data-stu-id="5330c-109">Under the latest release, download the zip file named **SampleConnector.zip**.</span></span> <span data-ttu-id="5330c-110">您在步骤4中将此 zip 文件上传到 Azure。</span><span class="sxs-lookup"><span data-stu-id="5330c-110">You upload this zip file to Azure in Step 4.</span></span>

## <a name="step-2-create-an-app-in-azure-active-directory"></a><span data-ttu-id="5330c-111">步骤 2: 在 Azure Active Directory 中创建应用程序</span><span class="sxs-lookup"><span data-stu-id="5330c-111">Step 2: Create an app in Azure Active Directory</span></span>

1. <span data-ttu-id="5330c-112">转到<https://portal.azure.com>并使用 Office 365 全局管理员帐户的凭据登录。</span><span class="sxs-lookup"><span data-stu-id="5330c-112">Go to <https://portal.azure.com> and sign in using the credentials of an Office 365 global admin account.</span></span>

   ![](media/TCimage01.png)

2. <span data-ttu-id="5330c-113">在左侧导航窗格中, 单击 " **Azure Active Directory**"。</span><span class="sxs-lookup"><span data-stu-id="5330c-113">In the left navigation pane, click **Azure Active Directory**.</span></span>

   ![](media/TCimage02.png)

3. <span data-ttu-id="5330c-114">在左侧导航窗格中, 单击 "**应用程序注册 (预览)** ", 然后单击 "**新建注册**"。</span><span class="sxs-lookup"><span data-stu-id="5330c-114">In the left navigation pane, click **App registrations (Preview)** and then click **New registration**.</span></span>

   ![](media/TCimage03.png)

4. <span data-ttu-id="5330c-115">注册应用程序。</span><span class="sxs-lookup"><span data-stu-id="5330c-115">Register the application.</span></span> <span data-ttu-id="5330c-116">在 "**重定向 URI (可选)**" 下, 选择 "应用程序类型" 下拉<https://portal.azure.com>列表中的 "Web", 然后在 URI 框中键入 uri。</span><span class="sxs-lookup"><span data-stu-id="5330c-116">Under **Redirect URI (optional)**, select Web in the application type dropdown list and then type <https://portal.azure.com> in the box for the URI.</span></span>

   ![](media/TCimage04.png)

5. <span data-ttu-id="5330c-117">复制**应用程序 (客户端) id**和**目录 (租户) id** , 并将其保存到文本文件或其他安全位置。</span><span class="sxs-lookup"><span data-stu-id="5330c-117">Copy the **Application (client) ID** and **Directory (tenant) ID** and save them to a text file or other safe location.</span></span> <span data-ttu-id="5330c-118">可在后续步骤中使用这些 Id。</span><span class="sxs-lookup"><span data-stu-id="5330c-118">You use these IDs in later steps.</span></span>

    ![](media/TCimage05.png)

6. <span data-ttu-id="5330c-119">转到**证书 & 新应用程序的证书**, 并在 "**客户端密码**" 下, 单击 "**新建客户端密码**"。</span><span class="sxs-lookup"><span data-stu-id="5330c-119">Go to **Certificates & secrets for the new app** and under **Client secrets** click **New client secret**.</span></span>

   ![](media/TCimage06.png)

7. <span data-ttu-id="5330c-120">创建新的机密。</span><span class="sxs-lookup"><span data-stu-id="5330c-120">Create a new secret.</span></span> <span data-ttu-id="5330c-121">在 "说明" 框中, 键入密码, 然后选择一个过期时间段。</span><span class="sxs-lookup"><span data-stu-id="5330c-121">In the description box, type the secret and then choose an expiration period.</span></span> 

   ![](media/TCimage08.png)

8. <span data-ttu-id="5330c-122">复制密码的值, 并将其保存到文本文件或其他存储位置。</span><span class="sxs-lookup"><span data-stu-id="5330c-122">Copy the value of the secret and save it to a text file or other storage location.</span></span> <span data-ttu-id="5330c-123">这是您在后续步骤中使用的 AAD 应用程序密码。</span><span class="sxs-lookup"><span data-stu-id="5330c-123">This is the AAD application secret that you use in later steps.</span></span>

   ![](media/TCimage09.png)

9. <span data-ttu-id="5330c-124">转到**清单**并复制 identifierUris (也称为 AAD 应用程序 Uri), 如以下屏幕截图中所示。</span><span class="sxs-lookup"><span data-stu-id="5330c-124">Go to **Manifest** and copy the identifierUris (which is also called the AAD application Uri) as highlighted in the following screenshot.</span></span> <span data-ttu-id="5330c-125">将 AAD 应用程序 Uri 复制到文本文件或其他存储位置。</span><span class="sxs-lookup"><span data-stu-id="5330c-125">Copy the AAD application Uri to a text file or other storage location.</span></span> <span data-ttu-id="5330c-126">您可以在步骤6中使用它。</span><span class="sxs-lookup"><span data-stu-id="5330c-126">You use it in Step 6.</span></span>

    ![](media/TCimage10.png)

## <a name="step-3-create-an-azure-storage-account"></a><span data-ttu-id="5330c-127">步骤 3: 创建 Azure 存储帐户</span><span class="sxs-lookup"><span data-stu-id="5330c-127">Step 3: Create an Azure storage account</span></span>

1.  <span data-ttu-id="5330c-128">转到您的组织的 Azure 主页。</span><span class="sxs-lookup"><span data-stu-id="5330c-128">Go to the Azure home page for your organization.</span></span>

    ![](media/TCimage11.png)

2. <span data-ttu-id="5330c-129">单击 "**创建资源**", 然后在搜索框中键入**存储帐户**。</span><span class="sxs-lookup"><span data-stu-id="5330c-129">Click **Create a resource** and they type **storage account** in the search box.</span></span>

   ![](media/TCimage12.png)

3. <span data-ttu-id="5330c-130">单击 "**存储**", 然后单击 "**存储帐户**"。</span><span class="sxs-lookup"><span data-stu-id="5330c-130">Click **Storage**, and then click **Storage account**.</span></span>

   ![](media/TCimage13.png)

4. <span data-ttu-id="5330c-131">在 "**创建存储帐户**" 页上的 "订阅" 框中, 根据您拥有的 Azure 订阅的类型选择 "按即点**即**用" 或 "**免费试用**"。</span><span class="sxs-lookup"><span data-stu-id="5330c-131">On the **Create storage account** page, in the Subscription box, select **Pay-As-You-Go** or **Free Trial** depending on which type of Azure subscription you have.</span></span> 

   ![](media/TCimage14.png)

5. <span data-ttu-id="5330c-132">选择或创建一个资源组。</span><span class="sxs-lookup"><span data-stu-id="5330c-132">Select or create a resource group.</span></span>

   ![](media/TCimage15.png)

6. <span data-ttu-id="5330c-133">键入存储帐户的名称。</span><span class="sxs-lookup"><span data-stu-id="5330c-133">Type a name for the storage account.</span></span>

   ![](media/TCimage16.png)

7. <span data-ttu-id="5330c-134">查看, 然后单击 "**创建**" 以创建存储帐户。</span><span class="sxs-lookup"><span data-stu-id="5330c-134">Review and then click **Create** to create the storage account.</span></span>

   ![](media/TCimage17.png)

8. <span data-ttu-id="5330c-135">几分钟后, 单击 "**刷新**", 然后单击 "**转到资源**" 以导航到存储帐户。</span><span class="sxs-lookup"><span data-stu-id="5330c-135">After a few moments, click **Refresh** and then click **Go to resource** to navigate to the storage account.</span></span>

   ![](media/TCimage18.png)

9. <span data-ttu-id="5330c-136">单击左侧导航窗格中的 "**访问密钥**"。</span><span class="sxs-lookup"><span data-stu-id="5330c-136">Click **Access keys** in the left navigation pane.</span></span>

   ![](media/TCimage19.png)

10. <span data-ttu-id="5330c-137">复制**连接字符串**并将其保存到文本文件或其他存储位置。</span><span class="sxs-lookup"><span data-stu-id="5330c-137">Copy a **Connection string** and save it to a text file or other storage location.</span></span> <span data-ttu-id="5330c-138">在步骤4中创建 web 应用资源时, 可以使用此操作。</span><span class="sxs-lookup"><span data-stu-id="5330c-138">You use this when creating a web app resource in Step 4.</span></span>

    ![](media/TCimage20.png)

## <a name="step-4-create-a-new-web-app-resource-in-azure"></a><span data-ttu-id="5330c-139">步骤 4: 在 Azure 中创建新的 web 应用资源</span><span class="sxs-lookup"><span data-stu-id="5330c-139">Step 4: Create a new web app resource in Azure</span></span>

1. <span data-ttu-id="5330c-140">在 Azure 门户的**主页**上, 单击 "**创建资源\>所有\> Web 应用程序**"。</span><span class="sxs-lookup"><span data-stu-id="5330c-140">On the **Home** page in the Azure portal, click **Create a resource \> Everything \> Web app**.</span></span> <span data-ttu-id="5330c-141">在 " **Web 应用程序**" 页上, 单击 "**创建**"。</span><span class="sxs-lookup"><span data-stu-id="5330c-141">On the **Web app** page, click **Create**.</span></span>

   ![](media/TCimage21.png)

2. <span data-ttu-id="5330c-142">填写详细信息 (如下所示), 然后创建 Web 应用程序。</span><span class="sxs-lookup"><span data-stu-id="5330c-142">Fill in the details (as shown below) and then create the Web app.</span></span> <span data-ttu-id="5330c-143">您在 "**应用名称**" 框中输入的名称用于创建 Azure 应用服务 URL;例如, twitterconnector.azurewebsites.net。</span><span class="sxs-lookup"><span data-stu-id="5330c-143">The name that you enter in the **App name** box is used to create the Azure app service URL; for example, twitterconnector.azurewebsites.net.</span></span>

   ![](media/TCimage22.png)

3. <span data-ttu-id="5330c-144">转到新创建的 web 应用资源, 并单击左侧导航窗格中的 "**应用程序设置**"。</span><span class="sxs-lookup"><span data-stu-id="5330c-144">Go to the newly created web app resource and click **Application Settings** in the left navigation pane.</span></span> <span data-ttu-id="5330c-145">在 "**应用程序设置**" 下, 单击 "**添加新设置**", 然后添加以下三个设置。</span><span class="sxs-lookup"><span data-stu-id="5330c-145">Under **Application settings**, click **Add new setting** and add the following three settings.</span></span> <span data-ttu-id="5330c-146">使用从前面的步骤中复制到文本文件中的值:</span><span class="sxs-lookup"><span data-stu-id="5330c-146">Use the values (that you copied to the text file from the previous steps):</span></span> 

    <span data-ttu-id="5330c-147">– \* \* APISecretKey —您可以键入任何值作为密码。</span><span class="sxs-lookup"><span data-stu-id="5330c-147">– \*\*APISecretKey — You can type any value as the secret.</span></span> <span data-ttu-id="5330c-148">这用于在步骤7中访问连接器 web 应用。</span><span class="sxs-lookup"><span data-stu-id="5330c-148">This is used to access the connector web app in Step 7.</span></span>

    <span data-ttu-id="5330c-149">– **StorageAccountConnectionString** –在步骤3中创建 Azure 存储帐户后复制的连接字符串 Uri。</span><span class="sxs-lookup"><span data-stu-id="5330c-149">– **StorageAccountConnectionString** – The connection string Uri that you copied after creating the Azure storage account in Step 3.</span></span>

    <span data-ttu-id="5330c-150">– **tenantId** –在步骤2中创建 Azure Active Directory 中的 Twitter 连接器应用之后复制的 Office 365 组织的租户 ID。</span><span class="sxs-lookup"><span data-stu-id="5330c-150">– **tenantId** – The tenant ID of your Office 365 organization that you copied after creating the Twitter connector app in Azure Active Directory in Step 2.</span></span>

    ![](media/TCimage23.png)

4. <span data-ttu-id="5330c-151">在 "**常规设置**" 下, 单击 "**始终打开**" 旁边的 **""** 。</span><span class="sxs-lookup"><span data-stu-id="5330c-151">Under **General settings**, click **On** next to the **Always On**.</span></span> <span data-ttu-id="5330c-152">单击页面顶部的 "**保存**" 以保存应用程序设置。</span><span class="sxs-lookup"><span data-stu-id="5330c-152">Click **Save** at the top of the page to save the application settings.</span></span>

   ![](media/TCimage24.png)

5. <span data-ttu-id="5330c-153">最后一步是将连接器应用源代码上载到您在步骤1中下载的 Azure。</span><span class="sxs-lookup"><span data-stu-id="5330c-153">The final step is to upload the connector app source code to Azure that you downloaded in Step 1.</span></span> <span data-ttu-id="5330c-154">在 web 浏览器中, 转到<AzureAppResourceName>https://. scm.azurewebsites.net/ZipDeployUi。</span><span class="sxs-lookup"><span data-stu-id="5330c-154">In a web browser, go to https://<AzureAppResourceName>.scm.azurewebsites.net/ZipDeployUi.</span></span> <span data-ttu-id="5330c-155">例如, 如果您的 Azure 应用资源的名称 (在此部分中的步骤2中命名) 为**twitterconnector**, 则您将转到https://twitterconnector.scm.azurewebsites.net/ZipDeployUi。</span><span class="sxs-lookup"><span data-stu-id="5330c-155">For example, if the name of your Azure app resource (which you named in step 2 in this section) is **twitterconnector**, then you would go to https://twitterconnector.scm.azurewebsites.net/ZipDeployUi.</span></span>

6. <span data-ttu-id="5330c-156">将 SampleConnector (您在步骤1中下载的) 拖放到此页面。</span><span class="sxs-lookup"><span data-stu-id="5330c-156">Drag and drop the SampleConnector.zip (that you downloaded in Step 1) to this page.</span></span> <span data-ttu-id="5330c-157">上载文件并成功部署后, 页面外观将类似于以下屏幕截图:</span><span class="sxs-lookup"><span data-stu-id="5330c-157">After the files are uploaded and the deployment is successful, the page will look similar to the following screenshot:</span></span>

   ![](media/TCimage25.png)

## <a name="step-5-create-the-twitter-app"></a><span data-ttu-id="5330c-158">步骤 5: 创建 Twitter 应用</span><span class="sxs-lookup"><span data-stu-id="5330c-158">Step 5: Create the Twitter app</span></span>

1. <span data-ttu-id="5330c-159">转到https://developer.twitter.com, 使用组织的开发人员帐户的凭据登录, 然后单击 "**应用**"。</span><span class="sxs-lookup"><span data-stu-id="5330c-159">Go to https://developer.twitter.com, log in using the credentials for the developer account for your organization, and then click **Apps**.</span></span>

   ![TCimage25-5](media/TCimage25-5.png)
2. <span data-ttu-id="5330c-161">单击 "**创建应用程序**"。</span><span class="sxs-lookup"><span data-stu-id="5330c-161">Click **Create an app**.</span></span>
   
   ![](media/TCimage26.png)

3. <span data-ttu-id="5330c-162">在 "**应用程序详细信息**" 下, 添加有关应用程序的信息。</span><span class="sxs-lookup"><span data-stu-id="5330c-162">Under **App details**, add information about the application.</span></span>

   ![](media/TCimage27.png)

4. <span data-ttu-id="5330c-163">在 Twitter 开发人员仪表板上, 选择刚创建的应用程序, 并复制显示的应用 ID 并将其保存到文本文件或其他存储位置。</span><span class="sxs-lookup"><span data-stu-id="5330c-163">On the Twitter developer dashboard, select the app that you just created and copy the App ID that's displayed  and save it to a text file or other storage location.</span></span> <span data-ttu-id="5330c-164">然后单击 "**详细信息**"。</span><span class="sxs-lookup"><span data-stu-id="5330c-164">Then click **Details**.</span></span>
   
   ![](media/TCimage28.png)

5. <span data-ttu-id="5330c-165">在 "**密钥和标记**" 选项卡上的 "**使用者 api 密钥**" 下, 复制 api 密钥并将其保存到文本文件或其他存储位置。</span><span class="sxs-lookup"><span data-stu-id="5330c-165">On the **Keys and tokens** tab, under **Consumer API keys** copy the API secret key and save it to a text file or other storage location.</span></span> <span data-ttu-id="5330c-166">然后, 单击 "**创建**" 以生成访问令牌和访问令牌机密, 并将它们复制到文本文件或其他存储位置。</span><span class="sxs-lookup"><span data-stu-id="5330c-166">Then click **Create** to generate an access token and an access token secret, and copy these to a text file or other storage location.</span></span>
   
   ![](media/TCimage29.png)

   <span data-ttu-id="5330c-167">然后, 单击 "**创建**" 以生成访问令牌和访问令牌机密, 并将它们复制到文本文件或其他存储位置。</span><span class="sxs-lookup"><span data-stu-id="5330c-167">Then click **Create** to generate an access token and an access token secret, and copy these to a text file or other storage location.</span></span>

6. <span data-ttu-id="5330c-168">单击 "**权限**" 选项卡并配置权限, 如以下屏幕截图所示:</span><span class="sxs-lookup"><span data-stu-id="5330c-168">Click the **Permissions** tab and configure the permissions as shown in the following screenshot:</span></span>

   ![](media/TCimage30.png)

7. <span data-ttu-id="5330c-169">保存权限设置后, 单击 "**应用程序详细信息**" 选项卡, 然后单击 "编辑" > "编辑**详细信息**"。</span><span class="sxs-lookup"><span data-stu-id="5330c-169">After you save the permission settings, click the **App details** tab, and then click **Edit > Edit details**.</span></span>

   ![](media/TCimage31.png)

8. <span data-ttu-id="5330c-170">执行以下任务:</span><span class="sxs-lookup"><span data-stu-id="5330c-170">Do the following tasks:</span></span>

   <span data-ttu-id="5330c-171">–选中此复选框可允许连接器应用登录 Twitter。</span><span class="sxs-lookup"><span data-stu-id="5330c-171">– Select the checkbox to allow the connector app to sign in to Twitter.</span></span>
   
   <span data-ttu-id="5330c-172">–使用以下格式添加 OAuth 重定向 Uri: \*\* \<connectorserviceuri>/views/twitteroauth\**, 其中*connectorserviceuri\*的值为您的组织的 Azure 应用服务 URL;例如, https://twitterconnector.azurewebsites.net/Views/TwitterOAuth。</span><span class="sxs-lookup"><span data-stu-id="5330c-172">– Add the OAuth redirect Uri using the following format: **\<connectorserviceuri>/Views/TwitterOAuth**, where the value of *connectorserviceuri* is the Azure app service URL for your organization; for example, https://twitterconnector.azurewebsites.net/Views/TwitterOAuth.</span></span>

   ![](media/TCimage32.png)

<span data-ttu-id="5330c-173">现在可以使用 Twitter 开发人员应用。</span><span class="sxs-lookup"><span data-stu-id="5330c-173">The Twitter developer app is now ready to use.</span></span>

## <a name="step-6-configure-the-connector-web-app"></a><span data-ttu-id="5330c-174">步骤 6: 配置连接器 web 应用程序</span><span class="sxs-lookup"><span data-stu-id="5330c-174">Step 6: Configure the connector web app</span></span> 

1. <span data-ttu-id="5330c-175">转到 https://\<AzureAppResourceName> azurewebsites.net (其中**AzureAppResourceName**是您在步骤4中命名的 Azure 应用程序资源的名称)。</span><span class="sxs-lookup"><span data-stu-id="5330c-175">Go to https://\<AzureAppResourceName>.azurewebsites.net (where **AzureAppResourceName** is the name of your Azure app resource that you named in Step 4).</span></span> <span data-ttu-id="5330c-176">例如, 如果名称为**twitterconnector**, 请转到https://twitterconnector.azurewebsites.net。</span><span class="sxs-lookup"><span data-stu-id="5330c-176">For example, if the name is **twitterconnector**, go to https://twitterconnector.azurewebsites.net.</span></span> <span data-ttu-id="5330c-177">该应用程序的主页如以下屏幕截图所示:</span><span class="sxs-lookup"><span data-stu-id="5330c-177">The home page of the app looks like the following screenshot:</span></span>

   ![](media/FBCimage41.png)

2. <span data-ttu-id="5330c-178">单击 "**配置**" 以显示登录页。</span><span class="sxs-lookup"><span data-stu-id="5330c-178">Click **Configure** to display a sign in page.</span></span>

   ![](media/FBCimage42.png)

3. <span data-ttu-id="5330c-179">在 "租户 Id" 框中, 键入或粘贴您在步骤2中获取的租户 Id。</span><span class="sxs-lookup"><span data-stu-id="5330c-179">In the Tenant Id box, type or paste your tenant Id (that you obtained in Step 2).</span></span> <span data-ttu-id="5330c-180">在 "密码" 框中, 键入或粘贴 APISecretKey (您在步骤2中获取), 然后单击 "**设置配置设置**" 以显示 "**配置详细信息**" 页。</span><span class="sxs-lookup"><span data-stu-id="5330c-180">In the password box, type or paste the APISecretKey (that you obtained in Step 2), and then click **Set Configuration Settings** to display the **Configuration Details** page.</span></span>

   ![](media/TCimage35.png)

4. <span data-ttu-id="5330c-181">在 "**配置详细信息**" 下, 输入以下配置设置</span><span class="sxs-lookup"><span data-stu-id="5330c-181">Under **Configuration Details**, enter the following configuration settings</span></span> 

   <span data-ttu-id="5330c-182">– **Twitter Api 密钥**–您在步骤5中创建的 twitter 应用程序的应用程序 ID。</span><span class="sxs-lookup"><span data-stu-id="5330c-182">– **Twitter Api Key** – The app ID for the Twitter application that you created in Step 5.</span></span>
   <span data-ttu-id="5330c-183">– **Twitter Api**密钥–您在步骤5中创建的 twitter 应用程序的 Api 密钥。</span><span class="sxs-lookup"><span data-stu-id="5330c-183">– **Twitter Api Secret Key** – The API secret key for the Twitter application that you created in Step 5.</span></span>
   <span data-ttu-id="5330c-184">– **Twitter 访问令牌**–您在步骤5中创建的访问令牌。</span><span class="sxs-lookup"><span data-stu-id="5330c-184">– **Twitter Access Token** – The access token that you created in Step 5.</span></span>
   <span data-ttu-id="5330c-185">– **Twitter 访问令牌密码**–您在步骤5中创建的访问令牌密码。</span><span class="sxs-lookup"><span data-stu-id="5330c-185">– **Twitter Access Token Secret** – The access token secret that you created in Step 5.</span></span>
   <span data-ttu-id="5330c-186">– **AAD 应用程序 id** –您在步骤2– **AAD 应用程序机密**中创建的 Azure ACTIVE Directory 应用程序 Id –您在步骤4中创建的 APISecretKey 密码的值。</span><span class="sxs-lookup"><span data-stu-id="5330c-186">– **AAD Application ID** – The application ID for the Azure Active Directory app that you created in Step 2 – **AAD Application Secret** – The value for the APISecretKey secret that you created in Step 4.</span></span>
   <span data-ttu-id="5330c-187">– **Aad 应用程序 uri** –在步骤2中获取的 aad 应用程序 uri;例如, https://microsoft.onmicrosoft.com/2688yu6n-12q3-23we-e3ee-121111123213。</span><span class="sxs-lookup"><span data-stu-id="5330c-187">– **AAD Application Uri** – The AAD application Uri obtained in Step 2; for example, https://microsoft.onmicrosoft.com/2688yu6n-12q3-23we-e3ee-121111123213.</span></span>
   <span data-ttu-id="5330c-188">– **App Insights 检测键**–将此框保留为空。</span><span class="sxs-lookup"><span data-stu-id="5330c-188">– **App Insights Instrumentation Key** – Leave this box blank.</span></span>

5. <span data-ttu-id="5330c-189">单击 "**保存**" 以保存连接器设置。</span><span class="sxs-lookup"><span data-stu-id="5330c-189">Click **Save** to save the connector settings.</span></span>

## <a name="step-7-set-up-a-custom-connector-in-the-security-and-compliance-center"></a><span data-ttu-id="5330c-190">步骤 7: 在安全与合规中心中设置自定义连接器</span><span class="sxs-lookup"><span data-stu-id="5330c-190">Step 7: Set up a custom connector in the security and compliance center</span></span>

1.  <span data-ttu-id="5330c-191">转到<https://protection.office.com> , 然后单击 "**数据\>调控\>导入存档第三方数据**"。</span><span class="sxs-lookup"><span data-stu-id="5330c-191">Go to <https://protection.office.com> and then click **Data governance \> Import \> Archive third-party data**.</span></span>

    ![](media/TCimage36.png)

2. <span data-ttu-id="5330c-192">单击 "**添加连接器**", 然后单击 " **Twitter**"。</span><span class="sxs-lookup"><span data-stu-id="5330c-192">Click **Add a connector** and then click **Twitter**.</span></span>

   ![](media/TCimage37.png)

3. <span data-ttu-id="5330c-193">在 "**添加连接器应用程序**" 页上, 输入以下信息, 然后单击 "**验证连接器**"。</span><span class="sxs-lookup"><span data-stu-id="5330c-193">On the **Add Connector App** page, enter the following information and then click **Validate connector**.</span></span>

    <span data-ttu-id="5330c-194">–在第一个框中, 键入连接器的名称, 如**Twitter**。</span><span class="sxs-lookup"><span data-stu-id="5330c-194">– In the first box, type a name for the connector, such as **Twitter**.</span></span>
    <span data-ttu-id="5330c-195">–在第二个框中, 键入或粘贴您在步骤4中添加的 APISecretKey 的值。</span><span class="sxs-lookup"><span data-stu-id="5330c-195">– In the second box, type or paste the value of the APISecretKey that you added in Step 4.</span></span>
    <span data-ttu-id="5330c-196">–在第三个框中, 键入或粘贴 Azure 应用服务 URL;例如, **https://twitterconnector.azurewebsites.net**。</span><span class="sxs-lookup"><span data-stu-id="5330c-196">– In the third box, type or paste the Azure app service URL; for example, **https://twitterconnector.azurewebsites.net**.</span></span>

   <span data-ttu-id="5330c-197">成功验证连接器后, 单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="5330c-197">After the connector is successfully validated, click **Next**.</span></span>

   ![](media/TCimage38.png)

4. <span data-ttu-id="5330c-198">单击 "**使用连接器应用登录**"。</span><span class="sxs-lookup"><span data-stu-id="5330c-198">Click **Login with Connector App**.</span></span>

   ![](media/TCimage39.png)

5. <span data-ttu-id="5330c-199">再次键入或粘贴 APISecretKey, 然后单击 "**登录到连接器服务**"。</span><span class="sxs-lookup"><span data-stu-id="5330c-199">Type or paste the APISecretKey again and then click  **Login to Connector Service**.</span></span>

   ![](media/TCimage40.png)


6. <span data-ttu-id="5330c-200">单击 "**继续使用 Twitter**。</span><span class="sxs-lookup"><span data-stu-id="5330c-200">Click **Continue with Twitter**.</span></span>

7. <span data-ttu-id="5330c-201">在 Twitter 登录页面上, 使用组织的 Twitter 帐户的帐户的凭据进行登录。</span><span class="sxs-lookup"><span data-stu-id="5330c-201">On the Twitter sign in page, sign in using the credentials for the account for your organization’s Twitter account.</span></span>

   ![](media/TCimage42.png)

   <span data-ttu-id="5330c-202">登录后, Twitter 页面将显示以下消息: "已成功设置 Twitter 连接器作业"。</span><span class="sxs-lookup"><span data-stu-id="5330c-202">After you sign in, the Twitter page will display the following message, "Twitter Connector Job Successfully set up."</span></span>

8. <span data-ttu-id="5330c-203">单击 "**完成**" 以完成 Twitter 连接器的设置。</span><span class="sxs-lookup"><span data-stu-id="5330c-203">Click **Finish** to complete setting up the Twitter connector.</span></span>

9. <span data-ttu-id="5330c-204">在 "**设置筛选器**" 页上, 可以应用筛选器以导入 (和存档) 特定时间的项目。</span><span class="sxs-lookup"><span data-stu-id="5330c-204">On the **Set Filters** page, you can apply a filter to import (and archive) items that are a certain age.</span></span> <span data-ttu-id="5330c-205">单击“下一步”。\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="5330c-205">Click **Next**.</span></span>

   ![](media/TCimage44.png)

10. <span data-ttu-id="5330c-206">在 "**设置存储帐户**" 页上, 键入将向 Twitter 项目导入的 Office 365 邮箱的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="5330c-206">On the **Set Storage Account** page, type the email address of an Office 365 mailbox that the Twitter items will be imported to.</span></span>

    ![](media/TCimage45.png)

11. <span data-ttu-id="5330c-207">查看您的设置, 然后单击 "**完成**" 以完成安全性 & 合规性中心中的连接器设置。</span><span class="sxs-lookup"><span data-stu-id="5330c-207">Review your settings and then click **Finish** to complete the connector setup in the Security & Compliance Center.</span></span>

    ![](media/TCimage46.png)

    ![](media/TCimage47.png)

12. <span data-ttu-id="5330c-208">转到 "**存档第三方数据**" 页, 查看导入过程的进度。</span><span class="sxs-lookup"><span data-stu-id="5330c-208">Go to the **Archive third-party data** page to see the progress of the import process.</span></span>

    ![](media/TCimage48.png)
