---
title: 使用客户密钥控制 Office 365 中的数据
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 8/1/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: f2cd475a-e592-46cf-80a3-1bfb0fa17697
ms.collection:
- M365-security-compliance
description: 了解如何为 Exchange Online、Skype for Business、SharePoint Online 和 OneDrive for business 设置适用于 Office 365 的客户密钥。 使用 "客户密钥", 可以控制组织的加密密钥, 然后配置 Office 365 以使用它们在 Microsoft 数据中心中对静态数据进行加密。
ms.openlocfilehash: 839d0b56b3748e2ab4ccecc30a084447f22131aa
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2019
ms.locfileid: "34153714"
---
# <a name="controlling-your-data-in-office-365-using-customer-key"></a><span data-ttu-id="3a9b7-104">使用客户密钥控制 Office 365 中的数据</span><span class="sxs-lookup"><span data-stu-id="3a9b7-104">Controlling your data in Office 365 using Customer Key</span></span>

<span data-ttu-id="3a9b7-105">使用 "客户密钥", 可以控制组织的加密密钥, 然后配置 Office 365 以使用它们在 Microsoft 数据中心中对静态数据进行加密。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-105">With Customer Key, you control your organization's encryption keys and then configure Office 365 to use them to encrypt your data at rest in Microsoft's data centers.</span></span> <span data-ttu-id="3a9b7-106">换言之, 客户密钥允许客户添加属于其密钥的加密层。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-106">In other words, Customer Key allows customers to add a layer of encryption that belongs to them, with their keys.</span></span> <span data-ttu-id="3a9b7-107">静态数据包含来自 Exchange Online 和 Skype for Business 的数据, 这些数据存储在存储在 SharePoint Online 和 OneDrive for business 中的邮箱和文件中。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-107">Data at rest includes data from Exchange Online and Skype for Business that is stored in mailboxes and files that are stored in SharePoint Online and OneDrive for Business.</span></span>
  
<span data-ttu-id="3a9b7-108">您必须先安装 Azure, 然后才能使用适用于 Office 365 的客户密钥。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-108">You must set up Azure before you can use Customer Key for Office 365.</span></span> <span data-ttu-id="3a9b7-109">本主题介绍了创建和配置所需 Azure 资源时需要遵循的步骤, 然后提供在 Office 365 中设置客户密钥的步骤。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-109">This topic describes the steps you need to follow to create and configure the required Azure resources and then provides the steps for setting up Customer Key in Office 365.</span></span> <span data-ttu-id="3a9b7-110">完成 Azure 安装后, 确定要为组织中的邮箱和文件分配的策略, 并因此确定哪些项。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-110">After you have completed Azure setup, you determine which policy, and therefore, which keys, to assign to mailboxes and files in your organization.</span></span> <span data-ttu-id="3a9b7-111">未分配策略的邮箱和文件将使用由 Microsoft 控制和管理的加密策略。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-111">Mailboxes and files for which you don't assign a policy will use encryption policies that are controlled and managed by Microsoft.</span></span> <span data-ttu-id="3a9b7-112">有关客户密钥的详细信息, 或有关一般概述的详细信息, 请参阅[Customer key For Office 365 FAQ](service-encryption-with-customer-key-faq.md)。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-112">For more information about Customer Key, or for a general overview, see the [Customer Key for Office 365 FAQ](service-encryption-with-customer-key-faq.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="3a9b7-113">强烈建议您遵循本主题中的最佳实践。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-113">We strongly recommend that you follow the best practices in this topic.</span></span> <span data-ttu-id="3a9b7-114">这些信息称为**提示**和**重要**。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-114">These are called out as **TIP** and **IMPORTANT**.</span></span> <span data-ttu-id="3a9b7-115">通过 "客户密钥", 您可以控制其作用域与整个组织一样大的根加密密钥。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-115">Customer Key gives you control over root encryption keys whose scope can be as large as your entire organization.</span></span> <span data-ttu-id="3a9b7-116">这意味着, 使用这些密钥进行的错误可能会产生很大影响, 并且可能会导致数据中断或无法挽回的数据丢失。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-116">This means that mistakes made with these keys can have a broad impact and may result in service interruptions or irrevocable loss of your data.</span></span> 
  
## <a name="before-you-begin-setting-up-customer-key"></a><span data-ttu-id="3a9b7-117">开始设置客户密钥之前</span><span class="sxs-lookup"><span data-stu-id="3a9b7-117">Before you begin setting up Customer Key</span></span>
<span data-ttu-id="3a9b7-118"><a name="Beforeyoustart"> </a></span><span class="sxs-lookup"><span data-stu-id="3a9b7-118"></span></span>

<span data-ttu-id="3a9b7-119">在开始之前, 请确保你的组织拥有适当的许可。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-119">Before you get started, be sure you have the appropriate licensing for your organization.</span></span> <span data-ttu-id="3a9b7-120">Office 365 中的客户密钥在 Office 365 E5 或高级合规性 SKU 中提供。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-120">Customer Key in Office 365 is offered in Office 365 E5 or the Advanced Compliance SKU.</span></span>
  
<span data-ttu-id="3a9b7-121">然后, 若要了解本主题中的概念和过程, 应查看[Azure Key Vault](https://azure.microsoft.com/en-us/documentation/services/key-vault/)文档。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-121">Then, to understand the concepts and procedures in this topic, you should review the [Azure Key Vault](https://azure.microsoft.com/en-us/documentation/services/key-vault/) documentation.</span></span> <span data-ttu-id="3a9b7-122">此外, 还应熟悉 Azure 中使用的术语 (例如[租户](https://msdn.microsoft.com/library/azure/jj573650.aspx#BKMK_WhatIsAnAzureADTenant))。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-122">Also, become familiar with the terms used in Azure, for example, [tenant](https://msdn.microsoft.com/library/azure/jj573650.aspx#BKMK_WhatIsAnAzureADTenant).</span></span>
  
<span data-ttu-id="3a9b7-123">若要提供有关客户密钥的反馈 (包括文档), 请将你的想法、建议和观点发送到 customerkeyfeedback@microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-123">To provide feedback on Customer Key, including the documentation, send your ideas, suggestions and perspectives to customerkeyfeedback@microsoft.com.</span></span>
  
## <a name="overview-of-setting-up-customer-key-for-office-365"></a><span data-ttu-id="3a9b7-124">设置适用于 Office 365 的客户密钥的概述</span><span class="sxs-lookup"><span data-stu-id="3a9b7-124">Overview of setting up Customer Key for Office 365</span></span>
<span data-ttu-id="3a9b7-125"><a name="Overview"> </a></span><span class="sxs-lookup"><span data-stu-id="3a9b7-125"></span></span>

<span data-ttu-id="3a9b7-126">若要设置客户密钥, 你将完成这些任务。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-126">To set up Customer Key you will complete these tasks.</span></span> <span data-ttu-id="3a9b7-127">本主题的其余部分提供有关每个任务的详细说明, 或链接到过程中每个步骤的详细信息。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-127">The rest of this topic provides detailed instructions for each task, or links out to more information for each step in the process.</span></span>
  
<span data-ttu-id="3a9b7-128">**在 Azure 和 Microsoft FastTrack 中:**</span><span class="sxs-lookup"><span data-stu-id="3a9b7-128">**In Azure and Microsoft FastTrack:**</span></span>
  
<span data-ttu-id="3a9b7-129">你将通过远程连接到 Azure PowerShell 来完成大部分这些任务。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-129">You will complete most of these tasks by remotely connecting to Azure PowerShell.</span></span> <span data-ttu-id="3a9b7-130">为获得最佳结果, 请使用版本4.4.0 或更高版本的 Azure PowerShell。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-130">For best results, use version 4.4.0 or later of Azure PowerShell.</span></span>
  
- [<span data-ttu-id="3a9b7-131">创建两个新的 Azure 订阅</span><span class="sxs-lookup"><span data-stu-id="3a9b7-131">Create two new Azure subscriptions</span></span>](controlling-your-data-using-customer-key.md#Create2newsubs)
    
- [<span data-ttu-id="3a9b7-132">注册 Azure 订阅以使用强制保留期</span><span class="sxs-lookup"><span data-stu-id="3a9b7-132">Register Azure subscriptions to use a mandatory retention period</span></span>](controlling-your-data-using-customer-key.md#RegisterSubsforMRP)
    
    <span data-ttu-id="3a9b7-133">注册可能需要一到五个工作日的时间。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-133">Registration can take from one to five business days.</span></span>
    
- [<span data-ttu-id="3a9b7-134">提交为激活 Office 365 的客户密钥的请求</span><span class="sxs-lookup"><span data-stu-id="3a9b7-134">Submit a request to activate Customer Key for Office 365</span></span>](controlling-your-data-using-customer-key.md#FastTrack)
    
    <span data-ttu-id="3a9b7-135">创建了这两个新的 Azure 订阅后, 您需要通过完成 Microsoft FastTrack 门户中承载的 web 表单来提交相应的客户密钥提供请求。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-135">Once you've created the two new Azure subscriptions, you'll need to submit the appropriate Customer Key offer request by completing a web form that is hosted in the Microsoft FastTrack portal.</span></span> <span data-ttu-id="3a9b7-136">**FastTrack 团队不会向客户密钥提供帮助。Office 只是使用 FastTrack 门户来允许您提交表单并帮助我们跟踪客户密钥的相关优惠**。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-136">**The FastTrack team doesn't provide assistance with Customer Key. Office simply uses the FastTrack portal to allow you to submit the form and to help us track the relevant offers for Customer Key**.</span></span>
  
<span data-ttu-id="3a9b7-137">提交客户密钥提供后, Microsoft 会查看你的请求, 并在你继续执行其余设置任务时通知你。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-137">Once you have submitted a Customer Key offer, Microsoft reviews your request and notifies you when you can proceed with the rest of the setup tasks.</span></span> <span data-ttu-id="3a9b7-138">此过程最长可能需要5个工作日。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-138">This process can take up to five business days.</span></span>
    
- [<span data-ttu-id="3a9b7-139">在每个订阅中创建高级 Azure 密钥保管库</span><span class="sxs-lookup"><span data-stu-id="3a9b7-139">Create a premium Azure Key Vault in each subscription</span></span>](controlling-your-data-using-customer-key.md#CreateKeyVault)
    
- [<span data-ttu-id="3a9b7-140">将权限分配给每个密钥存储库</span><span class="sxs-lookup"><span data-stu-id="3a9b7-140">Assign permissions to each key vault</span></span>](controlling-your-data-using-customer-key.md#KeyVaultPerms)
    
- [<span data-ttu-id="3a9b7-141">启用然后确认密钥电子仓库上的软删除</span><span class="sxs-lookup"><span data-stu-id="3a9b7-141">Enable and then confirm soft delete on your key vaults</span></span>](controlling-your-data-using-customer-key.md#SoftDelete)
    
- [<span data-ttu-id="3a9b7-142">通过创建或导入密钥将密钥添加到每个密钥存储库</span><span class="sxs-lookup"><span data-stu-id="3a9b7-142">Add a key to each key vault either by creating or importing a key</span></span>](controlling-your-data-using-customer-key.md#AddKeystoKeyVault)
    
- [<span data-ttu-id="3a9b7-143">检查密钥的恢复级别</span><span class="sxs-lookup"><span data-stu-id="3a9b7-143">Check the recovery level of your keys</span></span>](controlling-your-data-using-customer-key.md#CheckKeyRecoveryLevel)
    
- [<span data-ttu-id="3a9b7-144">备份 Azure 密钥存储库</span><span class="sxs-lookup"><span data-stu-id="3a9b7-144">Backup Azure Key Vault</span></span>](controlling-your-data-using-customer-key.md#BackupAzureKeyVaultkeys)
    
- [<span data-ttu-id="3a9b7-145">验证 Azure Key Vault 配置设置</span><span class="sxs-lookup"><span data-stu-id="3a9b7-145">Validate Azure Key Vault configuration settings</span></span>](controlling-your-data-using-customer-key.md#Validateconfiguration)
    
- [<span data-ttu-id="3a9b7-146">获取每个 Azure Key Vault 密钥的 URI</span><span class="sxs-lookup"><span data-stu-id="3a9b7-146">Obtain the URI for each Azure Key Vault key</span></span>](controlling-your-data-using-customer-key.md#GetKeyURI)
    
<span data-ttu-id="3a9b7-147">**在 Office 365 中:**</span><span class="sxs-lookup"><span data-stu-id="3a9b7-147">**In Office 365:**</span></span>
  
<span data-ttu-id="3a9b7-148">Exchange Online 和 Skype for Business:</span><span class="sxs-lookup"><span data-stu-id="3a9b7-148">Exchange Online and Skype for Business:</span></span>
  
- [<span data-ttu-id="3a9b7-149">创建与 Exchange Online 和 Skype for Business 一起使用的数据加密策略 (DEP)</span><span class="sxs-lookup"><span data-stu-id="3a9b7-149">Create a data encryption policy (DEP) for use with Exchange Online and Skype for Business</span></span>](controlling-your-data-using-customer-key.md#CreateDEP4EXOSkype)
    
- [<span data-ttu-id="3a9b7-150">将 DEP 分配给邮箱</span><span class="sxs-lookup"><span data-stu-id="3a9b7-150">Assign a DEP to a mailbox</span></span>](controlling-your-data-using-customer-key.md#assignDEPtomailbox)
    
- [<span data-ttu-id="3a9b7-151">验证邮箱加密</span><span class="sxs-lookup"><span data-stu-id="3a9b7-151">Validate mailbox encryption</span></span>](controlling-your-data-using-customer-key.md#validatemailboxencryption)
    
<span data-ttu-id="3a9b7-152">SharePoint Online 和 OneDrive for Business:</span><span class="sxs-lookup"><span data-stu-id="3a9b7-152">SharePoint Online and OneDrive for Business:</span></span>
  
- [<span data-ttu-id="3a9b7-153">为每个 SharePoint Online 和 OneDrive for business 地域创建数据加密策略 (DEP)</span><span class="sxs-lookup"><span data-stu-id="3a9b7-153">Create a data encryption policy (DEP) for each SharePoint Online and OneDrive for Business geo</span></span>](controlling-your-data-using-customer-key.md#CreateDEP4SPOODfB)
    
- [<span data-ttu-id="3a9b7-154">验证组网站、团队网站和 OneDrive for Business 的加密</span><span class="sxs-lookup"><span data-stu-id="3a9b7-154">Validate encryption of Group Sites, Team Sites, and OneDrive for Business</span></span>](controlling-your-data-using-customer-key.md#validateencryptionSPO)
    
## <a name="complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key"></a><span data-ttu-id="3a9b7-155">在 Azure Key Vault 和 Microsoft FastTrack 中完成对客户密钥的任务</span><span class="sxs-lookup"><span data-stu-id="3a9b7-155">Complete tasks in Azure Key Vault and Microsoft FastTrack for Customer Key</span></span>
<span data-ttu-id="3a9b7-156"><a name="AzureSteps"> </a></span><span class="sxs-lookup"><span data-stu-id="3a9b7-156"></span></span>

<span data-ttu-id="3a9b7-157">在 Azure Key Vault 中完成这些任务, 以便设置适用于 Office 365 的客户密钥。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-157">Complete these tasks in Azure Key Vault in order to set up Customer Key for Office 365.</span></span> <span data-ttu-id="3a9b7-158">您需要完成这些步骤, 而不管您打算为 Exchange Online 和 Skype for business 或 SharePoint Online 和 OneDrive for business 或 SharePoint Online 和 OneDrive for business 或 Office 365 中的所有受支持的服务设置客户密钥。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-158">You will need to complete these steps regardless of whether you intend to set up Customer Key for Exchange Online and Skype for Business or SharePoint Online and OneDrive for Business or for all supported services in Office 365.</span></span>
  
### <a name="create-two-new-azure-subscriptions"></a><span data-ttu-id="3a9b7-159">创建两个新的 Azure 订阅</span><span class="sxs-lookup"><span data-stu-id="3a9b7-159">Create two new Azure subscriptions</span></span>
<span data-ttu-id="3a9b7-160"><a name="Create2newsubs"> </a></span><span class="sxs-lookup"><span data-stu-id="3a9b7-160"></span></span>

<span data-ttu-id="3a9b7-161">客户密钥需要两个 Azure 订阅。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-161">Two Azure subscriptions are required for Customer Key.</span></span> <span data-ttu-id="3a9b7-162">作为一种最佳做法, Microsoft 建议您创建新的 Azure 订阅以用于客户密钥。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-162">As a best practice, Microsoft recommends that you create new Azure subscriptions for use with Customer Key.</span></span> <span data-ttu-id="3a9b7-163">Azure Key Vault 密钥只能为同一 Azure Active Directory (AAD) 租户中的应用程序授权, 您必须使用用于将 DEPs 分配到的 Office 365 组织使用的相同 Azure AD 租户创建新订阅。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-163">Azure Key Vault keys can only be authorized for applications in the same Azure Active Directory (AAD) tenant, you must create the new subscriptions using the same Azure AD tenant used with your Office 365 organization where the DEPs will be assigned.</span></span> <span data-ttu-id="3a9b7-164">例如, 在 Office 365 组织中使用具有全局管理员权限的工作或学校帐户。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-164">For example, using your work or school account that has global administrator privileges in your Office 365 organization.</span></span> <span data-ttu-id="3a9b7-165">有关详细步骤, 请参阅[将 Azure 注册为组织](https://azure.microsoft.com/en-us/documentation/articles/sign-up-organization/)。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-165">For detailed steps, see [Sign up for Azure as an organization](https://azure.microsoft.com/en-us/documentation/articles/sign-up-organization/).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="3a9b7-166">客户密钥需要每个数据加密策略 (DEP) 的两个密钥。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-166">Customer Key requires two keys for each data encryption policy (DEP).</span></span> <span data-ttu-id="3a9b7-167">若要实现此目的, 必须创建两个 Azure 订阅。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-167">In order to achieve this, you must create two Azure subscriptions.</span></span> <span data-ttu-id="3a9b7-168">作为一种最佳做法, Microsoft 建议您的组织的各个成员在每个订阅中配置一个密钥。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-168">As a best practice, Microsoft recommends that you have separate members of your organization configure one key in each subscription.</span></span> <span data-ttu-id="3a9b7-169">此外, 这些 Azure 订阅应仅用于管理 Office 365 的加密密钥。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-169">In addition, these Azure subscriptions should only be used to administer encryption keys for Office 365.</span></span> <span data-ttu-id="3a9b7-170">这将保护您的组织, 以防您在某个操作员意外、有意或恶意删除或以其他方式 mismanages 它们所负责的密钥。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-170">This protects your organization in case one of your operators accidentally, intentionally, or maliciously deletes or otherwise mismanages the keys for which they are responsible.</span></span> <br/> <span data-ttu-id="3a9b7-171">我们建议您设置新的 Azure 订阅, 这些订阅仅用于管理 Azure Key Vault 资源, 以便与客户密钥配合使用。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-171">We recommend that you set up new Azure subscriptions that are solely used for managing Azure Key Vault resources for use with Customer Key.</span></span> <span data-ttu-id="3a9b7-172">您可以为您的组织创建的 Azure 订阅数没有实际限制。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-172">There is no practical limit to the number of Azure subscriptions that you can create for your organization.</span></span> <span data-ttu-id="3a9b7-173">按照这些最佳做法, 可以最大限度地减少人为错误的影响, 同时帮助管理由客户密钥使用的资源。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-173">Following these best practices will minimize the impact of human error while helping to manage the resources used by Customer Key.</span></span> 
  
### <a name="submit-a-request-to-activate-customer-key-for-office-365"></a><span data-ttu-id="3a9b7-174">提交为激活 Office 365 的客户密钥的请求</span><span class="sxs-lookup"><span data-stu-id="3a9b7-174">Submit a request to activate Customer Key for Office 365</span></span>
<span data-ttu-id="3a9b7-175"><a name="FastTrack"> </a></span><span class="sxs-lookup"><span data-stu-id="3a9b7-175"></span></span>

<span data-ttu-id="3a9b7-176">完成 Azure 步骤后, 你需要在[Microsoft FastTrack 门户](https://fasttrack.microsoft.com/)中提交服务请求。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-176">Once you've completed the Azure steps, you'll need to submit an offer request in the [Microsoft FastTrack portal](https://fasttrack.microsoft.com/).</span></span> <span data-ttu-id="3a9b7-177">通过 FastTrack web 门户提交请求后, Microsoft 将验证您提供的 Azure 密钥 Vault 配置数据和联系人信息。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-177">Once you have submitted a request through the FastTrack web portal, Microsoft verifies the Azure Key Vault configuration data and contact information you provided.</span></span> <span data-ttu-id="3a9b7-178">您在 "产品" 窗体中所做的有关组织的授权监察官的选择对完成客户密钥注册至关重要且必需。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-178">The selections that you make in the offer form regarding the authorized officers of your organization is critical and necessary for completion of Customer Key registration.</span></span> <span data-ttu-id="3a9b7-179">您在表单中选择的您组织的监察官将用于确保任何请求吊销的真实性, 并销毁与客户密钥数据加密策略一起使用的所有密钥。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-179">The officers of your organization that you select in the form will be the used to ensure the authenticity of any request to revoke and destroy all keys used with a Customer Key data encryption policy.</span></span> <span data-ttu-id="3a9b7-180">您需要执行此步骤一次, 激活 Exchange Online 和 Skype for business 覆盖的客户密钥, 并再次激活适用于 SharePoint Online 和 OneDrive for business 的客户密钥。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-180">You'll need to do this step once to activate Customer Key for Exchange Online and Skype for Business coverage and a second time to activate Customer Key for SharePoint Online and OneDrive for Business.</span></span>
  
<span data-ttu-id="3a9b7-181">若要提交用于激活客户密钥的服务, 请完成以下步骤:</span><span class="sxs-lookup"><span data-stu-id="3a9b7-181">To submit an offer to activate Customer Key, complete these steps:</span></span>
  
1. <span data-ttu-id="3a9b7-182">在 Office 365 组织中使用具有全局管理员权限的工作或学校帐户, 登录到[Microsoft FastTrack 门户](https://fasttrack.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-182">Using a work or school account that has global administrator permissions in your Office 365 organization, log in to the [Microsoft FastTrack portal](https://fasttrack.microsoft.com/).</span></span>
    
2. <span data-ttu-id="3a9b7-183">登录后, 请浏览到**仪表板**。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-183">Once you're logged in, browse to the **Dashboard**.</span></span>
    
3. <span data-ttu-id="3a9b7-184">选择 "**服务**", 并查看当前提供的列表。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-184">Choose **Offers**, and review the list of current offers.</span></span>
    
4. <span data-ttu-id="3a9b7-185">有关适用于你的优惠, 请选择 "**了解详细信息**":</span><span class="sxs-lookup"><span data-stu-id="3a9b7-185">Choose **Learn More** for the offer that applies to you:</span></span> 
    
  - <span data-ttu-id="3a9b7-186">**Exchange Online 和 Skype For business:** 选择 "了解 Exchange 的**客户密钥**" 提供的**详细信息**。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-186">**Exchange Online and Skype for Business:** Choose **Learn More** on the **Customer Key for Exchange** offer.</span></span> 
    
  - <span data-ttu-id="3a9b7-187">**SharePoint Online 和 OneDrive For business:** 选择了解有关**SharePoint 和 OneDrive for** business 产品的客户密钥的**详细信息**。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-187">**SharePoint Online and OneDrive for Business:** Chose **Learn More** on the **Customer Key for SharePoint and OneDrive for Business** offer.</span></span> 
    
5. <span data-ttu-id="3a9b7-188">在 "**提供详细信息**" 页上, 选择 "**创建请求**"。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-188">On the **Offer details** page, choose **Create Request**.</span></span>
    
6. <span data-ttu-id="3a9b7-189">填写 "产品" 窗体上的所有适用详细信息和请求的信息。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-189">Fill out all applicable details and requested information on the offer form.</span></span> <span data-ttu-id="3a9b7-190">特别注意您的组织中要授权的监察官, 以批准永久和不可恢复的加密密钥和数据的销毁。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-190">Pay particular attention to your selections for which officers of your organization you want to authorize to approve the permanent and irreversible destruction of encryption keys and data.</span></span> <span data-ttu-id="3a9b7-191">完成表单后, 选择 "**提交**"。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-191">Once you've completed the form, choose **Submit**.</span></span>
    
    <span data-ttu-id="3a9b7-192">在 Microsoft 收到你的请求通知后, 此过程最长可能需要5个工作日。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-192">This process can take up to five business days once Microsoft has been notified of your request.</span></span>
    
7. <span data-ttu-id="3a9b7-193">继续执行下面的必需保留期部分。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-193">Continue on to the mandatory retention period section below.</span></span>
    
### <a name="register-azure-subscriptions-to-use-a-mandatory-retention-period"></a><span data-ttu-id="3a9b7-194">注册 Azure 订阅以使用强制保留期</span><span class="sxs-lookup"><span data-stu-id="3a9b7-194">Register Azure subscriptions to use a mandatory retention period</span></span>
<span data-ttu-id="3a9b7-195"><a name="RegisterSubsforMRP"> </a></span><span class="sxs-lookup"><span data-stu-id="3a9b7-195"></span></span>

<span data-ttu-id="3a9b7-196">临时或永久丢失根加密密钥可能会非常中断, 甚至会导致服务操作发生故障, 并可能导致数据丢失。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-196">The temporary or permanent loss of root encryption keys can be very disruptive or even catastrophic to service operation and can result in data loss.</span></span> <span data-ttu-id="3a9b7-197">出于此原因, 使用客户密钥的资源需要加强保护。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-197">For this reason, the resources used with Customer Key require strong protection.</span></span> <span data-ttu-id="3a9b7-198">与客户密钥结合使用的所有 Azure 资源在默认配置之外提供保护机制。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-198">All the Azure resources that are used with Customer Key offer protection mechanisms beyond the default configuration.</span></span> <span data-ttu-id="3a9b7-199">可以通过阻止即时和不可撤销取消的方式对 Azure 订阅进行标记或注册。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-199">Azure subscriptions can be tagged or registered in a way that will prevent immediate and irrevocable cancellation.</span></span> <span data-ttu-id="3a9b7-200">这称为注册强制保留期。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-200">This is referred to as registering for a mandatory retention period.</span></span> <span data-ttu-id="3a9b7-201">为强制保留期注册 Azure 订阅所需的步骤需要与 Office 365 团队进行协作。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-201">The steps required to register Azure subscriptions for a mandatory retention period require collaboration with the Office 365 team.</span></span> <span data-ttu-id="3a9b7-202">此过程可能需要一至五个工作日。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-202">This process can take from one to five business days.</span></span> <span data-ttu-id="3a9b7-203">以前, 这有时称为 "不取消"。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-203">Previously, this was sometimes referred to as "Do Not Cancel".</span></span>
  
<span data-ttu-id="3a9b7-204">在联系 Office 365 团队之前, 必须为您使用客户密钥的每个 Azure 订阅执行以下步骤:</span><span class="sxs-lookup"><span data-stu-id="3a9b7-204">Before contacting the Office 365 team, you must perform the following steps for each Azure subscription that you use with Customer Key:</span></span>
  
1. <span data-ttu-id="3a9b7-205">使用 Azure PowerShell 登录到 Azure 订阅。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-205">Log in to your Azure subscription with Azure PowerShell.</span></span> <span data-ttu-id="3a9b7-206">有关说明, 请参阅[使用 Azure PowerShell 登录](https://docs.microsoft.com/powershell/azure/authenticate-azureps?view=azurermps-4.3.1)。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-206">For instructions, see [Log in with Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps?view=azurermps-4.3.1).</span></span>
    
2. <span data-ttu-id="3a9b7-207">运行 AzureRmProviderFeature cmdlet 以注册你的订阅, 以使用强制保留期。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-207">Run the Register-AzureRmProviderFeature cmdlet to register your subscriptions to use a mandatory retention period.</span></span>
    
  ```
  Register-AzureRmProviderFeature -FeatureName mandatoryRetentionPeriodEnabled -ProviderNamespace Microsoft.Resources
  ```

3. <span data-ttu-id="3a9b7-208">请与 Microsoft 联系以完成此过程。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-208">Contact Microsoft to have the process finalized.</span></span> <span data-ttu-id="3a9b7-209">对于 SharePoint 和 OneDrive for Business 团队, 请联系[spock@microsoft.com](mailto:spock@microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-209">For the SharePoint and OneDrive for Business team, contact [spock@microsoft.com](mailto:spock@microsoft.com).</span></span> <span data-ttu-id="3a9b7-210">对于 Exchange Online 和 Skype for Business, 请联系[exock@microsoft.com](mailto:exock@microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-210">For Exchange Online and Skype for Business, contact [exock@microsoft.com](mailto:exock@microsoft.com).</span></span> <span data-ttu-id="3a9b7-211">完成此过程所需的服务级别协议 (SLA) 是在 Microsoft 经过通知 (并验证) 后, 注册了你的订阅以使用强制保留期后, 此过程的服务级别协议 (SLA) 就是5个工作日。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-211">The Service Level Agreement (SLA) for completion of this process is five business days once Microsoft has been notified (and verified) that you have registered your subscriptions to use a mandatory retention period.</span></span> <span data-ttu-id="3a9b7-212">在您的电子邮件中包括以下内容:</span><span class="sxs-lookup"><span data-stu-id="3a9b7-212">Include the following in your email:</span></span>
    
    <span data-ttu-id="3a9b7-213">**Subject**: \<*租户的完全限定域名*的客户密钥\></span><span class="sxs-lookup"><span data-stu-id="3a9b7-213">**Subject**: Customer Key for \<*Your tenant's fully-qualified domain name*\></span></span> 
    
    <span data-ttu-id="3a9b7-214">**正文**: 要为其完成强制保留期的订阅 id。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-214">**Body**: Subscription IDs for which you want to have the mandatory retention period finalized.</span></span> 
    
4. <span data-ttu-id="3a9b7-215">收到 Microsoft 注册已完成的通知后, 通过运行 AzureRmProviderFeature cmdlet 验证注册的状态, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="3a9b7-215">Once you receive notification from Microsoft that registration is complete, verify the status of your registration by running the Get-AzureRmProviderFeature cmdlet as follows:</span></span>
    
  ```
  Get-AzureRmProviderFeature -ProviderNamespace Microsoft.Resources -FeatureName mandatoryRetentionPeriodEnabled
  ```

5. <span data-ttu-id="3a9b7-216">在验证 AzureRmProviderFeature cmdlet 中的**注册状态**属性返回**已注册**的值后, 请运行以下命令来完成此过程:</span><span class="sxs-lookup"><span data-stu-id="3a9b7-216">After verifying that the **Registration State** property from the Get-AzureRmProviderFeature cmdlet returns a value of **Registered**, run the following command to complete the process:</span></span>
    
  ```
  Register-AzureRmResourceProvider -ProviderNamespace "Microsoft.KeyVault"
  ```

### <a name="create-a-premium-azure-key-vault-in-each-subscription"></a><span data-ttu-id="3a9b7-217">在每个订阅中创建高级 Azure 密钥保管库</span><span class="sxs-lookup"><span data-stu-id="3a9b7-217">Create a premium Azure Key Vault in each subscription</span></span>
<span data-ttu-id="3a9b7-218"><a name="CreateKeyVault"> </a></span><span class="sxs-lookup"><span data-stu-id="3a9b7-218"></span></span>

<span data-ttu-id="3a9b7-219">创建密钥存储库的步骤在[开始使用 Azure Key vault](https://azure.microsoft.com/documentation/articles/key-vault-get-started/)时进行介绍, 此步骤将指导你完成安装和启动 azure PowerShell, 连接到 azure 订阅, 创建资源组, 以及在其中创建密钥存储库资源组。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-219">The steps to create a key vault are documented in [Getting Started with Azure Key Vault](https://azure.microsoft.com/documentation/articles/key-vault-get-started/), which guides you through installing and launching Azure PowerShell, connecting to your Azure subscription, creating a resource group, and creating a key vault in that resource group.</span></span>
  
<span data-ttu-id="3a9b7-220">创建密钥存储库时, 必须选择 SKU: 标准版或高级存储库。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-220">When you create a key vault, you must choose a SKU: either Standard or Premium.</span></span> <span data-ttu-id="3a9b7-221">标准 SKU 允许 Azure Key Vault 密钥受软件保护-没有硬件安全模块 (HSM) 密钥保护-并且 Premium SKU 允许使用 Hsm 来保护关键保管库密钥。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-221">The Standard SKU allows Azure Key Vault keys to be protected with software - there is no Hardware Security Module (HSM) key protection - and the Premium SKU allows the use of HSMs for protection of Key Vault keys.</span></span> <span data-ttu-id="3a9b7-222">客户密钥接受使用任何 SKU 的密钥电子仓库, 尽管 Microsoft 强烈建议您仅使用高级 SKU。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-222">Customer Key accepts key vaults that use either SKU, though Microsoft strongly recommends that you use only the Premium SKU.</span></span> <span data-ttu-id="3a9b7-223">无论是哪种类型的键的运算开销都是一样的, 因此, 每个受 HSM 保护的密钥的成本的唯一区别是每个月的成本。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-223">The cost of operations with keys of either type is the same, so the only difference in cost is the cost per month for each HSM-protected key.</span></span> <span data-ttu-id="3a9b7-224">有关详细信息, 请参阅[主要保管库定价](https://azure.microsoft.com/pricing/details/key-vault/)。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-224">See [Key Vault pricing](https://azure.microsoft.com/pricing/details/key-vault/) for details.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="3a9b7-225">对生产数据使用 Premium SKU 密钥电子仓库和受 HSM 保护的密钥, 并且仅使用标准 SKU 密钥电子仓库和密钥进行测试和验证。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-225">Use the Premium SKU key vaults and HSM-protected keys for production data, and only use Standard SKU key vaults and keys for testing and validation purposes.</span></span> 
  
<span data-ttu-id="3a9b7-226">对于每个将使用客户密钥的 Office 365 服务, 请在您创建的两个 Azure 订阅中的每个中创建一个密钥存储库。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-226">For each Office 365 service with which you will use Customer Key, create a key vault in each of the two Azure subscriptions that you created.</span></span> <span data-ttu-id="3a9b7-227">例如, 仅针对 Exchange Online 和 Skype for business 或 SharePoint Online 和 OneDrive for Business, 你将仅创建一对电子仓库。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-227">For example, for Exchange Online and Skype for Business only or SharePoint Online and OneDrive for Business only, you will create only one pair of vaults.</span></span> <span data-ttu-id="3a9b7-228">若要同时为 Exchange Online 和 SharePoint Online 启用客户密钥, 您将创建两对主要电子仓库。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-228">To enable Customer Key for both Exchange Online and SharePoint Online, you will create two pairs of key vaults.</span></span>
  
<span data-ttu-id="3a9b7-229">对密钥库使用命名约定, 以反映将与保管库关联的 DEP 的预期用途。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-229">Use a naming convention for key vaults that reflects the intended use of the DEP with which you will associate the vaults.</span></span> <span data-ttu-id="3a9b7-230">请参阅下面的 "最佳实践" 部分, 了解命名约定建议。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-230">See the Best Practices section below for naming convention recommendations.</span></span>
  
<span data-ttu-id="3a9b7-231">为每个数据加密策略创建一组单独的、成对的电子仓库。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-231">Create a separate, paired set of vaults for each data encryption policy.</span></span> <span data-ttu-id="3a9b7-232">对于 Exchange Online, 当您将策略分配给邮箱时, 会选择数据加密策略的范围。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-232">For Exchange Online, the scope of a data encryption policy is chosen by you when you assign the policy to mailbox.</span></span> <span data-ttu-id="3a9b7-233">一个邮箱只能分配一个策略, 并且最多可以创建50个策略。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-233">A mailbox can have only one policy assigned, and you can create up to fifty policies.</span></span> <span data-ttu-id="3a9b7-234">对于 SharePoint Online, 策略的范围是组织内的所有数据 (地理位置或地理位置)。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-234">For SharePoint Online the scope of a policy is all of the data within an organization in a geographic location, or geo.</span></span>
  
<span data-ttu-id="3a9b7-235">创建密钥存储库还需要创建 Azure 资源组, 因为密钥存储库需要存储容量 (尽管非常小) 和密钥存储库日志记录 (如果启用) 也会生成存储的数据。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-235">The creation of key vaults also requires the creation of Azure resource groups, since key vaults need storage capacity (though very small) and Key Vault logging, if enabled, also generates stored data.</span></span> <span data-ttu-id="3a9b7-236">作为一种最佳做法, Microsoft 建议使用单独的管理员来管理每个资源组, 并将管理与将管理所有相关客户密钥资源的一组管理员相一致。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-236">As a best practice Microsoft recommends using separate administrators to manage each resource group, with the administration aligned with the set of administrators that will manage all related Customer Key resources.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="3a9b7-237">若要最大限度地提高可用性, 关键电子仓库应位于与 Office 365 服务接近的区域。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-237">To maximize availability, your key vaults should be in regions close to your Office 365 service.</span></span> <span data-ttu-id="3a9b7-238">例如, 如果您的 Exchange Online 组织在北美, 请将您的密钥电子仓库放在北美。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-238">For example, if your Exchange Online organization is in North America, place your key vaults in North America.</span></span> <span data-ttu-id="3a9b7-239">如果你的 Exchange Online 组织在欧洲, 请将你的密钥电子仓库放在欧洲。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-239">If your Exchange Online organization is in Europe, place your key vaults in Europe.</span></span><br/><span data-ttu-id="3a9b7-240">对密钥存储库使用公用前缀, 并包含密钥保管库和密钥的使用和作用域的缩写 (例如, 对于将在北美使用电子仓库的 Contoso SharePoint 服务, 可能的姓名对是 Contoso-O365SP-VaultA1,Contoso-O365SP-NA-VaultA2。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-240">Use a common prefix for key vaults, and include an abbreviation of the use and scope of the key vault and keys (e.g., for the Contoso SharePoint service where the vaults will be located in North America, a possible pair of names is Contoso-O365SP-NA-VaultA1 and Contoso-O365SP-NA-VaultA2.</span></span> <span data-ttu-id="3a9b7-241">保管库名称在 Azure 中是全局唯一的字符串, 因此, 如果所需名称已由其他 Azure 客户声明, 则可能需要尝试其他名称的变体。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-241">Vault names are globally unique strings within Azure, so you may need to try variations of your desired names in case the desired names are already claimed by other Azure customers.</span></span> <span data-ttu-id="3a9b7-242">从7月2017电子仓库名称无法更改, 因此最佳做法是为设置编写计划, 并使用第二个人验证是否正确执行了计划。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-242">As of July 2017 vault names cannot be changed, so a best practice is to have a written plan for setup and use a second person to verify the plan is executed correctly.</span></span><br/><span data-ttu-id="3a9b7-243">如果可能, 请在非配对区域中创建您的电子仓库。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-243">If possible, create your vaults in non-paired regions.</span></span> <span data-ttu-id="3a9b7-244">配对的 Azure 区域在服务故障域之间提供高可用性。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-244">Paired Azure regions provide high availability across service failure domains.</span></span> <span data-ttu-id="3a9b7-245">因此, 可以将区域对视为彼此的备份区域。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-245">Therefore, regional pairs can be thought of as each other's backup region.</span></span> <span data-ttu-id="3a9b7-246">这意味着, 放置在一个区域中的 Azure 资源将自动获得配对区域的容错能力。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-246">This means that an Azure resource that is placed in one region is automatically gaining fault tolerance through the paired region.</span></span> <span data-ttu-id="3a9b7-247">出于此原因, 为在区域为成对的 DEP 中使用的两个电子仓库选择区域是指仅有两个可用性区域在使用中。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-247">For this reason, choosing regions for two vaults used in a DEP where the regions are paired means that only a total of two regions of availability are in use.</span></span> <span data-ttu-id="3a9b7-248">大多数地理位置仅有两个区域, 因此尚不能选择非配对区域。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-248">Most geographies only have two regions, so it's not yet possible to select non-paired regions.</span></span> <span data-ttu-id="3a9b7-249">如果可能, 请为用于 DEP 的两个电子仓库选择两个不成对的区域。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-249">If possible, choose two non-paired regions for the two vaults used with a DEP.</span></span> <span data-ttu-id="3a9b7-250">这从总共四个可用区域获益。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-250">This benefits from a total of four regions of availability.</span></span> <span data-ttu-id="3a9b7-251">有关详细信息, 请参阅[业务连续性和灾难恢复 (BCDR):](https://docs.microsoft.com/azure/best-practices-availability-paired-regions)当前区域对列表的 Azure 配对区域。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-251">For more information, see [Business continuity and disaster recovery (BCDR): Azure Paired Regions](https://docs.microsoft.com/azure/best-practices-availability-paired-regions) for a current list of regional pairs.</span></span> 
  
### <a name="assign-permissions-to-each-key-vault"></a><span data-ttu-id="3a9b7-252">将权限分配给每个密钥存储库</span><span class="sxs-lookup"><span data-stu-id="3a9b7-252">Assign permissions to each key vault</span></span>
<span data-ttu-id="3a9b7-253"><a name="KeyVaultPerms"> </a></span><span class="sxs-lookup"><span data-stu-id="3a9b7-253"></span></span>

<span data-ttu-id="3a9b7-254">对于每个密钥存储库, 您将需要为客户密钥定义三组不同的权限, 具体取决于您的实现。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-254">For each key vault, you will need to define three separate sets of permissions for Customer Key, depending on your implementation.</span></span> <span data-ttu-id="3a9b7-255">例如, 您需要为以下各项定义一组权限:</span><span class="sxs-lookup"><span data-stu-id="3a9b7-255">For example, you will need to define one set of permissions for each of the following:</span></span>
  
- <span data-ttu-id="3a9b7-256">将对您的组织执行关键电子仓库的日常管理的**主要保管库管理员**。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-256">**Key vault administrators** that will perform day-to-day management of your key vault for your organization.</span></span> <span data-ttu-id="3a9b7-257">这些任务包括备份、创建、获取、导入、列出和还原。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-257">These tasks include backup, create, get, import, list, and restore.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="3a9b7-258">分配给主要保管库管理员的权限集不包含删除密钥的权限。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-258">The set of permissions assigned to key vault administrators does not include the permission to delete keys.</span></span> <span data-ttu-id="3a9b7-259">这是有意和重要的做法。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-259">This is intentional and an important practice.</span></span> <span data-ttu-id="3a9b7-260">通常情况下, 删除加密密钥不会完成, 因为这样做会永久破坏数据。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-260">Deleting encryption keys is not typically done, since doing so permanently destroys data.</span></span> <span data-ttu-id="3a9b7-261">作为一种最佳做法, 默认情况下不要向主要保管库管理员授予此权限。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-261">As a best practice, do not grant this permission to key vault administrators by default.</span></span> <span data-ttu-id="3a9b7-262">相反, 请为重要的保管库参与者预留此权限, 并在清楚了解结果的情况下, 仅在短期内将其分配给管理员。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-262">Instead, reserve this for key vault contributors and only assign it to an administrator on a short term basis once a clear understanding of the consequences is understood.</span></span> 
  
    <span data-ttu-id="3a9b7-263">若要将这些权限分配给 Office 365 组织中的用户, 请使用 Azure PowerShell 登录 Azure 订阅。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-263">To assign these permissions to a user in your Office 365 organization, log in to your Azure subscription with Azure PowerShell.</span></span> <span data-ttu-id="3a9b7-264">有关说明, 请参阅[使用 Azure PowerShell 登录](https://docs.microsoft.com/powershell/azure/authenticate-azureps?view=azurermps-4.3.1)。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-264">For instructions, see [Log in with Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps?view=azurermps-4.3.1).</span></span>
    
- <span data-ttu-id="3a9b7-265">运行 AzureRmKeyVaultAccessPolicy cmdlet 以分配所需的权限。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-265">Run the Set-AzureRmKeyVaultAccessPolicy cmdlet to assign the necessary permissions.</span></span>
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName <vaultname> 
  -UserPrincipalName <UPN of user> -PermissionsToKeys create,import,list,get,backup,restore
  ```

  <span data-ttu-id="3a9b7-266">例如：</span><span class="sxs-lookup"><span data-stu-id="3a9b7-266">For example:</span></span>
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
  -UserPrincipalName alice@contoso.com -PermissionsToKeys create,import,list,get,backup,restore
  ```

- <span data-ttu-id="3a9b7-267">可以更改 Azure 密钥存储库本身权限的**主要保管库参与者**。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-267">**Key vault contributors** that can change permissions on the Azure Key Vault itself.</span></span> <span data-ttu-id="3a9b7-268">您需要更改这些权限, 因为员工离开或加入团队, 或者在极少数情况下, 主要保管库管理员合法需要删除或还原密钥的权限。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-268">You'll need to change these permissions as employees leave or join your team, or in the extremely rare situation that the key vault administrators legitimately need permission to delete or restore a key.</span></span> <span data-ttu-id="3a9b7-269">需要在密钥保管库中向此组密钥 vault 参与者授予**参与者**角色。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-269">This set of key vault contributors needs to be granted the **Contributor** role on your key vault.</span></span> <span data-ttu-id="3a9b7-270">您可以使用 Azure 资源管理器分配此角色。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-270">You can assign this role by using Azure Resource Manager.</span></span> <span data-ttu-id="3a9b7-271">有关详细步骤, 请参阅[使用基于角色的访问控制管理对 Azure 订阅资源的访问权限](https://docs.microsoft.com/azure/active-directory/role-based-access-control-configure)。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-271">For detailed steps, see [Use Role-Based Access Control to manage access to your Azure subscription resources](https://docs.microsoft.com/azure/active-directory/role-based-access-control-configure).</span></span> <span data-ttu-id="3a9b7-272">创建订阅的管理员将隐式拥有此访问权限, 以及将其他管理员分配给参与者角色的能力。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-272">The administrator who creates a subscription has this access implicitly, as well as the ability to assign other administrators to the Contributor role.</span></span>
    
- <span data-ttu-id="3a9b7-273">如果打算将客户密钥用于 Exchange Online 和 Skype for business, 则需要向 Office 365 授予权限, 以代表 Exchange Online 和 Skype for business 使用密钥保管库。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-273">If you intend to use Customer Key with Exchange Online and Skype for Business, you need to give permission to Office 365 to use the key vault on behalf of Exchange Online and Skype for Business.</span></span> <span data-ttu-id="3a9b7-274">同样, 如果您打算将客户密钥与 SharePoint Online 和 OneDrive for business 结合使用, 则需要添加 Office 365 的权限, 以代表 SharePoint Online 和 OneDrive for business 使用密钥存储库。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-274">Likewise, if you intend to use Customer Key with SharePoint Online and OneDrive for Business, you need to add permission for the Office 365 to use the key vault on behalf of SharePoint Online and OneDrive for Business.</span></span> <span data-ttu-id="3a9b7-275">若要向 Office 365 授予权限, 请使用以下语法运行**AzureRmKeyVaultAccessPolicy** cmdlet:</span><span class="sxs-lookup"><span data-stu-id="3a9b7-275">To give permission to Office 365, run the **Set-AzureRmKeyVaultAccessPolicy** cmdlet using the following syntax:</span></span> 
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName <vaultname> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
  ```

    <span data-ttu-id="3a9b7-276">其中：</span><span class="sxs-lookup"><span data-stu-id="3a9b7-276">Where:</span></span>
    
  - <span data-ttu-id="3a9b7-277">*vaultname*是您创建的主要保管库的名称。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-277">*vaultname* is the name of the key vault you created.</span></span> 
    
  - <span data-ttu-id="3a9b7-278">对于 Exchange Online 和 Skype for Business, 请将*Office 365 appID*替换为`00000002-0000-0ff1-ce00-000000000000`</span><span class="sxs-lookup"><span data-stu-id="3a9b7-278">For Exchange Online and Skype for Business, replace  *Office 365 appID* with `00000002-0000-0ff1-ce00-000000000000`</span></span>
    
  - <span data-ttu-id="3a9b7-279">对于 SharePoint Online 和 OneDrive for Business, 请将*Office 365 appID*替换为`00000003-0000-0ff1-ce00-000000000000`</span><span class="sxs-lookup"><span data-stu-id="3a9b7-279">For SharePoint Online and OneDrive for Business, replace  *Office 365 appID* with `00000003-0000-0ff1-ce00-000000000000`</span></span>
    
  <span data-ttu-id="3a9b7-280">示例: 设置 Exchange Online 和 Skype for business 的权限:</span><span class="sxs-lookup"><span data-stu-id="3a9b7-280">Example: Setting permissions for Exchange Online and Skype for Business:</span></span>
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
  -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
  ```

  <span data-ttu-id="3a9b7-281">示例: 设置 SharePoint Online 和 OneDrive for business 的权限</span><span class="sxs-lookup"><span data-stu-id="3a9b7-281">Example: Setting permissions for SharePoint Online and OneDrive for Business</span></span>
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1 
  -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000003-0000-0ff1-ce00-000000000000
  ```

### <a name="enable-and-then-confirm-soft-delete-on-your-key-vaults"></a><span data-ttu-id="3a9b7-282">启用然后确认密钥电子仓库上的软删除</span><span class="sxs-lookup"><span data-stu-id="3a9b7-282">Enable and then confirm soft delete on your key vaults</span></span>
<span data-ttu-id="3a9b7-283"><a name="SoftDelete"> </a></span><span class="sxs-lookup"><span data-stu-id="3a9b7-283"></span></span>

<span data-ttu-id="3a9b7-284">如果可以快速恢复密钥, 则由于意外或恶意删除的密钥而遇到的扩展服务故障的可能性较小。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-284">When you can quickly recover your keys, you are less likely to experience an extended service outage due to accidentally or maliciously deleted keys.</span></span> <span data-ttu-id="3a9b7-285">您需要先启用此配置 (称为 "软删除"), 然后才能在 "客户密钥" 中使用密钥。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-285">You need to enable this configuration, referred to as Soft Delete, before you can use your keys with Customer Key.</span></span> <span data-ttu-id="3a9b7-286">启用软删除允许您在删除90天内恢复密钥或电子仓库, 而无需从备份中还原它们。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-286">Enabling Soft Delete allows you to recover keys or vaults within 90 days of deletion without having to restore them from backup.</span></span>
  
<span data-ttu-id="3a9b7-287">若要在密钥保管库上启用软删除, 请完成以下步骤:</span><span class="sxs-lookup"><span data-stu-id="3a9b7-287">To enable Soft Delete on your key vaults, complete these steps:</span></span>
  
1. <span data-ttu-id="3a9b7-288">使用 Windows Powershell 登录到你的 Azure 订阅。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-288">Log in to your Azure subscription with Windows Powershell.</span></span> <span data-ttu-id="3a9b7-289">有关说明, 请参阅[使用 Azure PowerShell 登录](https://docs.microsoft.com/powershell/azure/authenticate-azureps)。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-289">For instructions, see [Log in with Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).</span></span>
    
2. <span data-ttu-id="3a9b7-290">运行[AzureRmKeyVault](https://docs.microsoft.com/powershell/module/azurerm.keyvault/get-azurermkeyvault) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-290">Run the [Get-AzureRmKeyVault](https://docs.microsoft.com/powershell/module/azurerm.keyvault/get-azurermkeyvault) cmdlet.</span></span> <span data-ttu-id="3a9b7-291">在此示例中, *vaultname*是要为其启用软删除的主要保管库的名称:</span><span class="sxs-lookup"><span data-stu-id="3a9b7-291">In this example, *vaultname* is the name of the key vault for which you are enabling soft delete:</span></span> 
    
   ```
   $v = Get-AzureRmKeyVault -VaultName <vaultname>
   $r = Get-AzureRmResource -ResourceId $v.ResourceId
   $r.Properties | Add-Member -MemberType NoteProperty -Name enableSoftDelete -Value 'True'
   Set-AzureRmResource -ResourceId $r.ResourceId -Properties $r.Properties
   ``` 
    
3. <span data-ttu-id="3a9b7-292">通过运行**AzureRmKeyVault** cmdlet, 确认已为密钥存储库配置了软删除。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-292">Confirm soft delete is configured for the key vault by running the **Get-AzureRmKeyVault** cmdlet.</span></span> <span data-ttu-id="3a9b7-293">如果为密钥存储库正确配置了软删除, 则会启用软删除？属性返回的值**为 True**:</span><span class="sxs-lookup"><span data-stu-id="3a9b7-293">If soft delete is configured properly for the key vault, then the  Soft Delete Enabled? property returns a value of **True**:</span></span> 
    
   ```
   Get-AzureRmKeyVault -VaultName <vaultname> | fl
   ```

   
    
### <a name="add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key"></a><span data-ttu-id="3a9b7-294">通过创建或导入密钥将密钥添加到每个密钥存储库</span><span class="sxs-lookup"><span data-stu-id="3a9b7-294">Add a key to each key vault either by creating or importing a key</span></span>
<span data-ttu-id="3a9b7-295"><a name="AddKeystoKeyVault"> </a></span><span class="sxs-lookup"><span data-stu-id="3a9b7-295"></span></span>

<span data-ttu-id="3a9b7-296">有两种方法可以将密钥添加到 Azure Key Vault;可以直接在密钥保管库中创建密钥, 也可以导入密钥。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-296">There are two ways to add keys to an Azure Key Vault; you can create a key directly in Key Vault, or you can import a key.</span></span> <span data-ttu-id="3a9b7-297">直接在 "密钥存储库" 中创建密钥是不太复杂的方法, 而导入密钥提供了对如何生成密钥的总体控制。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-297">Creating a key directly in Key Vault is the less complicated method, while importing a key provides total control over how the key is generated.</span></span>
  
<span data-ttu-id="3a9b7-298">若要直接在密钥保管库中创建密钥, 请运行[AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Add-AzureKeyVaultKey) cmdlet, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="3a9b7-298">To create a key directly in your key vault, run the [Add-AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Add-AzureKeyVaultKey) cmdlet as follows:</span></span> 
  
```
Add-AzureKeyVaultKey -VaultName <vaultname> -Name <keyname> -Destination <HSM|Software> -KeyOps wrapKey,unwrapKey
```

<span data-ttu-id="3a9b7-299">其中：</span><span class="sxs-lookup"><span data-stu-id="3a9b7-299">Where:</span></span>
  
-  <span data-ttu-id="3a9b7-300">*vaultname*是要在其中创建密钥的密钥保管库的名称。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-300">*vaultname*  is the name of the key vault in which you want to create the key.</span></span> 
    
-  <span data-ttu-id="3a9b7-301">*keyname*是要赋予新键的名称。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-301">*keyname*  is the name you want to give the new key.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="3a9b7-302">使用上面的密钥库的命名约定命名键。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-302">Name keys using a similar naming convention as described above for key vaults.</span></span> <span data-ttu-id="3a9b7-303">这样一来, 在仅显示密钥名称的工具中, 字符串是自我描述的。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-303">This way, in tools that show only the key name, the string is self-describing.</span></span> 
  
- <span data-ttu-id="3a9b7-304">如果打算使用 HSM 保护密钥, 请确保将**HSM**指定为_Destination_参数的值, 否则指定 "**软件**"。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-304">If you intend to protect the key with an HSM, ensure that you specify **HSM** as the value of the  _Destination_ parameter, otherwise, specify **Software**.</span></span>
    
<span data-ttu-id="3a9b7-305">For example,</span><span class="sxs-lookup"><span data-stu-id="3a9b7-305">For example,</span></span>
  
```
Add-AzureKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination Software -KeyOps wrapKey,unwrapKey
```

<span data-ttu-id="3a9b7-306">若要将密钥直接导入到密钥存储库中, 您需要具有 Thales nShield 硬件安全模块。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-306">To import a key directly into your key vault, you need to have a Thales nShield Hardware Security Module.</span></span>
  
<span data-ttu-id="3a9b7-307">某些组织首选使用此方法来建立其密钥的 provenance, 此方法还提供以下内容:</span><span class="sxs-lookup"><span data-stu-id="3a9b7-307">Some organizations prefer this approach to establish the provenance of their keys, and the this method also provides the following:</span></span>
  
- <span data-ttu-id="3a9b7-308">用于导入的工具集包括来自 Thales 的证明, 用于加密所生成密钥的密钥交换密钥 (KEK) 不可导出, 并在 Thales 制造的正版 HSM 中生成。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-308">The toolset used for import includes attestation from Thales that the Key Exchange Key (KEK) that is used to encrypt the key you generate is not exportable and is generated inside a genuine HSM that was manufactured by Thales.</span></span>
    
- <span data-ttu-id="3a9b7-309">该工具集包括来自 Thales 的证明, 这些安全世界也是在由 Thales 生产的正版 HSM 上生成的。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-309">The toolset includes attestation from Thales that the Azure Key Vault security world was also generated on a genuine HSM manufactured by Thales.</span></span> <span data-ttu-id="3a9b7-310">此认证向你证明 Microsoft 也在使用正版 Thales 硬件。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-310">This attestation proves to you that Microsoft is also using genuine Thales hardware.</span></span>
    
<span data-ttu-id="3a9b7-311">检查安全组以确定是否需要上述 attestations。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-311">Check with your security group to determine if the above attestations are required.</span></span> <span data-ttu-id="3a9b7-312">有关在本地创建密钥并将其导入到密钥保管库的详细步骤, 请参阅 how [to 为 Azure Key vault 生成和传输受 HSM 保护的密钥](https://azure.microsoft.com/documentation/articles/key-vault-hsm-protected-keys/)。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-312">For detailed steps to create a key on-premises and import it into your key vault, see [How to generate and transfer HSM-protected keys for Azure Key Vault](https://azure.microsoft.com/documentation/articles/key-vault-hsm-protected-keys/).</span></span> <span data-ttu-id="3a9b7-313">使用 Azure 说明在每个密钥存储库中创建密钥。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-313">Use the Azure instructions to create a key in each key vault.</span></span>
  
### <a name="check-the-recovery-level-of-your-keys"></a><span data-ttu-id="3a9b7-314">检查密钥的恢复级别</span><span class="sxs-lookup"><span data-stu-id="3a9b7-314">Check the recovery level of your keys</span></span>
<span data-ttu-id="3a9b7-315"><a name="CheckKeyRecoveryLevel"> </a></span><span class="sxs-lookup"><span data-stu-id="3a9b7-315"></span></span>

<span data-ttu-id="3a9b7-316">Office 365 要求 Azure Key Vault 订阅设置为 "不取消", 并且客户密钥使用的密钥启用了软删除。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-316">Office 365 requires that the Azure Key Vault subscription is set to Do Not Cancel and that the keys used by Customer Key have soft delete enabled.</span></span> <span data-ttu-id="3a9b7-317">你可以通过查看密钥上的恢复级别来确认这一点。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-317">You can confirm this by looking at the recovery level on your keys.</span></span>
  
<span data-ttu-id="3a9b7-318">若要检查注册表项的恢复级别, 请在 Azure PowerShell 中运行 AzureKeyVaultKey cmdlet, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="3a9b7-318">To check the recovery level of a key, in Azure PowerShell, run the Get-AzureKeyVaultKey cmdlet as follows:</span></span>
  
```
(Get-AzureKeyVaultKey -VaultName <vaultname> -Name <keyname>).Attributes 
```

<span data-ttu-id="3a9b7-319">如果_恢复级别_属性返回的值不是**可恢复 + ProtectedSubscription**的值, 则需要查看本主题, 并确保已按照所有步骤将订阅放在 "不要取消" 列表中, 并将已在每个密钥保管库上启用软删除。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-319">If the  _Recovery Level_ property returns anything other than a value of **Recoverable+ProtectedSubscription**, you will need to review this topic and ensure that you have followed all of the steps to put the subscription on the Do Not Cancel list and that you have soft delete enabled on each of your key vaults.</span></span>
  
### <a name="backup-azure-key-vault"></a><span data-ttu-id="3a9b7-320">备份 Azure 密钥存储库</span><span class="sxs-lookup"><span data-stu-id="3a9b7-320">Backup Azure Key Vault</span></span>
<span data-ttu-id="3a9b7-321"><a name="BackupAzureKeyVaultkeys"> </a></span><span class="sxs-lookup"><span data-stu-id="3a9b7-321"></span></span>

<span data-ttu-id="3a9b7-322">立即完成创建或对某个键的任何更改, 执行备份并存储联机和脱机的备份副本。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-322">Immediately following creation or any change to a key, perform a backup and store copies of the backup, both online and offline.</span></span> <span data-ttu-id="3a9b7-323">脱机副本不应连接到任何网络, 例如在物理安全或商业存储设施中。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-323">Offline copies should not be connected to any network, such as in a physical safe or commercial storage facility.</span></span> <span data-ttu-id="3a9b7-324">至少应将备份的一个副本存储在灾难发生时可访问的位置。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-324">At least one copy of the backup should be stored in a location that will be accessible in the event of a disaster.</span></span> <span data-ttu-id="3a9b7-325">备份 blob 是恢复密钥材料的唯一方法 (应永久销毁密钥保管库密钥), 或以其他方式呈现为不可操作。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-325">The backup blobs are the sole means of restoring key material should a Key Vault key be permanently destroyed or otherwise rendered inoperable.</span></span> <span data-ttu-id="3a9b7-326">Azure Key Vault 外部的密钥和已导入到 Azure Key Vault 的密钥不能作为备份, 因为客户密钥使用密钥所需的元数据在外部密钥中不存在。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-326">Keys that are external to Azure Key Vault and were imported to Azure Key Vault do not qualify as a backup because the metadata necessary for Customer Key to use the key does not exist with the external key.</span></span> <span data-ttu-id="3a9b7-327">只有从 Azure 密钥存储库中获取的备份才能用于使用客户密钥的还原操作。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-327">Only a backup taken from Azure Key Vault can be used for restore operations with Customer Key.</span></span> <span data-ttu-id="3a9b7-328">因此, 在上载或创建密钥时, 应创建 Azure 密钥存储库的备份, 这一点非常重要。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-328">Therefore, it is essential that a backup of Azure Key Vault be made once a key is uploaded or created.</span></span>
  
<span data-ttu-id="3a9b7-329">若要创建 Azure Key Vault 密钥的备份, 请运行[AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Backup-AzureKeyVaultKey) cmdlet, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="3a9b7-329">To create a backup of an Azure Key Vault key, run the [Backup-AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Backup-AzureKeyVaultKey) cmdlet as follows:</span></span>
```
Backup-AzureKeyVaultKey -VaultName <vaultname> -Name <keyname> 
-OutputFile <filename .backup>

```

<span data-ttu-id="3a9b7-330">确保输出文件使用后缀`.backup`。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-330">Ensure that your output file uses the suffix  `.backup`.</span></span>
  
<span data-ttu-id="3a9b7-331">此 cmdlet 生成的输出文件已加密, 不能在 Azure 密钥保管库外部使用。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-331">The output file resulting from this cmdlet is encrypted and cannot be used outside of Azure Key Vault.</span></span> <span data-ttu-id="3a9b7-332">只能将备份还原到从中获取备份的 Azure 订阅。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-332">The backup can be restored only to the Azure subscription from which the backup was taken.</span></span>
  
> [!TIP]
> <span data-ttu-id="3a9b7-333">对于输出文件, 选择您的电子仓库名称和密钥名称的组合。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-333">For the output file, choose a combination of your vault name and key name.</span></span> <span data-ttu-id="3a9b7-334">这将使文件名自我描述。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-334">This will make the file name self-describing.</span></span> <span data-ttu-id="3a9b7-335">它还将确保备份文件名称不会发生冲突。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-335">It will also ensure that backup file names do not collide.</span></span> 
  
<span data-ttu-id="3a9b7-336">例如：</span><span class="sxs-lookup"><span data-stu-id="3a9b7-336">For example:</span></span>
  
```
Backup-AzureKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -OutputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

### <a name="validate-azure-key-vault-configuration-settings"></a><span data-ttu-id="3a9b7-337">验证 Azure Key Vault 配置设置</span><span class="sxs-lookup"><span data-stu-id="3a9b7-337">Validate Azure Key Vault configuration settings</span></span>
<span data-ttu-id="3a9b7-338"><a name="Validateconfiguration"> </a></span><span class="sxs-lookup"><span data-stu-id="3a9b7-338"></span></span>

<span data-ttu-id="3a9b7-339">在 DEP 中使用密钥之前执行验证是可选的, 但强烈建议这样做。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-339">Performing validation before using keys in a DEP is optional, but highly recommended.</span></span> <span data-ttu-id="3a9b7-340">特别是, 如果您使用步骤设置了除本主题中所述的密钥和电子仓库之外的密钥和电子仓库, 则应在配置客户密钥之前验证 Azure Key Vault 资源的运行状况。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-340">In particular, if you use steps to set up your keys and vaults other than the ones described in this topic, you should validate the health of your Azure Key Vault resources before you configure Customer Key.</span></span>
  
<span data-ttu-id="3a9b7-341">若要验证您的密钥是否启用了 get、wrapKey 和 unwrapKey 操作, 请执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="3a9b7-341">To verify that your keys have get, wrapKey, and unwrapKey operations enabled:</span></span>
  
<span data-ttu-id="3a9b7-342">运行[AzureRmKeyVault](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Get-AzureRmKeyVault) cmdlet, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="3a9b7-342">Run the [Get-AzureRmKeyVault](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Get-AzureRmKeyVault) cmdlet as follows:</span></span> 
  
```
Get-AzureRMKeyVault -VaultName <vaultname>
```

<span data-ttu-id="3a9b7-343">在 "输出" 中, 根据需要查找访问策略和 Exchange Online 标识 (GUID) 或 SharePoint Online 标识 (GUID)。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-343">In the output, look for the Access Policy and for the Exchange Online identity (GUID) or the SharePoint Online identity (GUID) as appropriate.</span></span> <span data-ttu-id="3a9b7-344">所有三个权限都必须显示在 "键的权限" 下。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-344">All three of the above permissions must be shown under Permissions to Keys.</span></span>
  
<span data-ttu-id="3a9b7-345">如果访问策略配置不正确, 请运行 AzureRmKeyVaultAccessPolicy cmdlet, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="3a9b7-345">If the access policy configuration is incorrect, run the Set-AzureRmKeyVaultAccessPolicy cmdlet as follows:</span></span>
  
```
Set-AzureRmKeyVaultAccessPolicy -VaultName <vaultname> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
```

<span data-ttu-id="3a9b7-346">例如, 对于 Exchange Online 和 Skype for Business:</span><span class="sxs-lookup"><span data-stu-id="3a9b7-346">For example, for Exchange Online and Skype for Business:</span></span>
  
```
Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
```

<span data-ttu-id="3a9b7-347">例如, 对于 SharePoint Online 和 OneDrive for Business:</span><span class="sxs-lookup"><span data-stu-id="3a9b7-347">For example, for SharePoint Online and OneDrive for Business:</span></span>
  
```
Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1 
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName TBD
```

<span data-ttu-id="3a9b7-348">若要验证没有为你的密钥设置到期日期, 请运行[AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Get-AzureKeyVaultKey) cmdlet, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="3a9b7-348">To verify that an expiration date is not set for your keys run the [Get-AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Get-AzureKeyVaultKey) cmdlet as follows:</span></span> 
  
```
Get-AzureKeyVaultKey -VaultName <vaultname> 
```

<span data-ttu-id="3a9b7-349">已过期的密钥不能由客户密钥使用, 尝试使用过期密钥的操作将会失败, 并且可能会导致服务中断。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-349">An expired key cannot be used by Customer Key and operations attempted with an expired key will fail, and possibly result in a service outage.</span></span> <span data-ttu-id="3a9b7-350">强烈建议使用与客户密钥一起使用的密钥不具有过期日期。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-350">We strongly recommend that keys used with Customer Key do not have an expiration date.</span></span> <span data-ttu-id="3a9b7-351">过期日期一旦设置, 便无法删除, 但可以更改为不同的日期。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-351">An expiration date, once set, cannot be removed, but can be changed to a different date.</span></span> <span data-ttu-id="3a9b7-352">如果必须使用具有过期日期设置的密钥, 请将 "过期" 值更改为 "12/31/9999"。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-352">If a key must be used that has an expiration date set, change the expiration value to 12/31/9999.</span></span> <span data-ttu-id="3a9b7-353">过期日期设置为12/31/9999 之外的密钥将不会通过 Office 365 验证。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-353">Keys with an expiration date set to a date other than 12/31/9999 will not pass Office 365 validation.</span></span>
  
<span data-ttu-id="3a9b7-354">若要更改已设置为12/31/9999 以外的任何其他值的过期日期, 请运行[AzureKeyVaultKeyAttribute](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Set-AzureKeyVaultKeyAttribute) cmdlet, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="3a9b7-354">To change an expiration date that has been set to any value other than 12/31/9999, run the [Set-AzureKeyVaultKeyAttribute](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Set-AzureKeyVaultKeyAttribute) cmdlet as follows:</span></span> 
  
```
Set-AzureKeyVaultKeyAttribute -VaultName <vaultname> -Name <keyname> 
-Expires (Get-Date -Date "12/31/9999")
```

> [!CAUTION]
> <span data-ttu-id="3a9b7-355">不要在与客户密钥结合使用的加密密钥上设置到期日期。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-355">Don't set expiration dates on encryption keys you use with Customer Key.</span></span> 
  
### <a name="obtain-the-uri-for-each-azure-key-vault-key"></a><span data-ttu-id="3a9b7-356">获取每个 Azure Key Vault 密钥的 URI</span><span class="sxs-lookup"><span data-stu-id="3a9b7-356">Obtain the URI for each Azure Key Vault key</span></span>
<span data-ttu-id="3a9b7-357"><a name="GetKeyURI"> </a></span><span class="sxs-lookup"><span data-stu-id="3a9b7-357"></span></span>

<span data-ttu-id="3a9b7-358">完成 Azure 中的所有步骤以设置密钥存储库并添加密钥后, 运行以下命令以获取每个密钥存储库中的密钥的 URI。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-358">Once you have completed all the steps in Azure to set up your key vaults and added your keys, run the following command to get the URI for the key in each key vault.</span></span> <span data-ttu-id="3a9b7-359">在稍后创建和分配每个 DEP 时, 需要使用这些 Uri, 将此信息保存在安全的位置。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-359">You will need to use these URIs when you create and assign each DEP later, so save this information in a safe place.</span></span> <span data-ttu-id="3a9b7-360">请务必为每个密钥保管库运行一次此命令。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-360">Remember to run this command once for each key vault.</span></span>
  
<span data-ttu-id="3a9b7-361">在 Azure PowerShell 中:</span><span class="sxs-lookup"><span data-stu-id="3a9b7-361">In Azure PowerShell:</span></span>
  
```
(Get-AzureKeyVaultKey -VaultName <vaultname>).Id
```

## <a name="office-365-setting-up-customer-key-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="3a9b7-362">Office 365: 设置 Exchange Online 和 Skype for business 的客户密钥</span><span class="sxs-lookup"><span data-stu-id="3a9b7-362">Office 365: Setting up Customer Key for Exchange Online and Skype for Business</span></span>
<span data-ttu-id="3a9b7-363"><a name="AzureSteps"> </a></span><span class="sxs-lookup"><span data-stu-id="3a9b7-363"></span></span>

<span data-ttu-id="3a9b7-364">在开始之前, 请确保您已完成设置 Azure Key Vault 所需的任务。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-364">Before you begin, ensure that you have completed the tasks required to set up Azure Key Vault.</span></span> <span data-ttu-id="3a9b7-365">有关信息, 请参阅[Azure Key Vault 和 Microsoft FastTrack 中的 "完成任务" 以获取客户密钥](controlling-your-data-using-customer-key.md#AzureSteps)。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-365">See [Complete tasks in Azure Key Vault and Microsoft FastTrack for Customer Key](controlling-your-data-using-customer-key.md#AzureSteps) for information.</span></span> 
  
<span data-ttu-id="3a9b7-366">若要设置 Exchange Online 和 Skype for business 的客户密钥, 你将需要通过 Windows PowerShell 远程连接到 Exchange Online 来执行这些步骤。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-366">To set up Customer Key for Exchange Online and Skype for Business, you will need to perform these steps by remotely connecting to Exchange Online with Windows PowerShell.</span></span>
  
### <a name="create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business"></a><span data-ttu-id="3a9b7-367">创建与 Exchange Online 和 Skype for Business 一起使用的数据加密策略 (DEP)</span><span class="sxs-lookup"><span data-stu-id="3a9b7-367">Create a data encryption policy (DEP) for use with Exchange Online and Skype for Business</span></span>
<span data-ttu-id="3a9b7-368"><a name="CreateDEP4EXOSkype"> </a></span><span class="sxs-lookup"><span data-stu-id="3a9b7-368"></span></span>

<span data-ttu-id="3a9b7-369">一个 DEP 与 Azure Key Vault 中存储的一组密钥相关联。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-369">A DEP is associated with a set of keys stored in Azure Key Vault.</span></span> <span data-ttu-id="3a9b7-370">您在 Office 365 中向邮箱分配了一个 DEP。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-370">You assign a DEP to a mailbox in Office 365.</span></span> <span data-ttu-id="3a9b7-371">然后, Office 365 将使用在策略中标识的密钥来加密邮箱。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-371">Office 365 will then use the keys identified in the policy to encrypt the mailbox.</span></span> <span data-ttu-id="3a9b7-372">若要创建 DEP, 您需要之前获取的主要保管库 Uri。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-372">To create the DEP, you need the Key Vault URIs you obtained earlier.</span></span> <span data-ttu-id="3a9b7-373">有关说明, 请参阅[获取每个 Azure Key Vault 密钥的 URI](controlling-your-data-using-customer-key.md#GetKeyURI) 。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-373">See [Obtain the URI for each Azure Key Vault key](controlling-your-data-using-customer-key.md#GetKeyURI) for instructions.</span></span> 
  
<span data-ttu-id="3a9b7-374">还!</span><span class="sxs-lookup"><span data-stu-id="3a9b7-374">Remember!</span></span> <span data-ttu-id="3a9b7-375">创建 DEP 时, 请指定驻留在两个不同的 Azure Key 保管库中的两个密钥。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-375">When you create a DEP, you specify two keys that reside in two different Azure Key Vaults.</span></span> <span data-ttu-id="3a9b7-376">确保这些项位于两个单独的 Azure 区域中, 以确保地域冗余。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-376">Ensure that these keys are located in two separate Azure regions to ensure geo-redundancy.</span></span>
  
<span data-ttu-id="3a9b7-377">若要创建 DEP, 请按照以下步骤操作:</span><span class="sxs-lookup"><span data-stu-id="3a9b7-377">To create the DEP, follow these steps:</span></span>
  
1. <span data-ttu-id="3a9b7-378">在您的本地计算机上, 使用在 Office 365 组织中具有全局管理员权限的工作或学校帐户, 通过打开 Windows PowerShell 并运行以下命令[连接到 Exchange Online PowerShell](https://technet.microsoft.com/en-us/library/jj984289%28v=exchg.160%29.aspx) 。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-378">On your local computer, using a work or school account that has global administrator permissions in your Office 365 organization, [connect to Exchange Online PowerShell](https://technet.microsoft.com/en-us/library/jj984289%28v=exchg.160%29.aspx) by opening Windows PowerShell and running the following command.</span></span> 
    
   ```
   $UserCredential = Get-Credential
   ```

2. <span data-ttu-id="3a9b7-379">在 "Windows PowerShell 凭据请求" 对话框中, 输入你的工作或学校帐户信息, 单击 **"确定**", 然后输入以下命令。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-379">In the Windows PowerShell Credential Request dialog box, enter your work or school account information, click **OK**, and then enter the following command.</span></span> 
    
   ```
   $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
   ```

3. <span data-ttu-id="3a9b7-380">运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-380">Run the following command.</span></span>
    
   ```
   Import-PSSession $Session
   ```

4. <span data-ttu-id="3a9b7-381">若要创建 DEP, 请通过键入以下命令来使用 DataEncryptionPolicy cmdlet。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-381">To create a DEP, use the New-DataEncryptionPolicy cmdlet by typing the following command.</span></span>
    
   ```
   New-DataEncryptionPolicy -Name <PolicyName> -Description "PolicyDescription " -AzureKeyIDs <KeyVaultURI1>, <KeyVaultURI2>
   ```

   <span data-ttu-id="3a9b7-382">其中：</span><span class="sxs-lookup"><span data-stu-id="3a9b7-382">Where:</span></span>
    
   -  <span data-ttu-id="3a9b7-383">*PolicyName*是要用于策略的名称。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-383">*PolicyName*  is the name you want to use for the policy.</span></span> <span data-ttu-id="3a9b7-384">名称不能包含空格。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-384">Names cannot contain spaces.</span></span> <span data-ttu-id="3a9b7-385">例如, USA_mailboxes。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-385">For example, USA_mailboxes.</span></span> 
    
   -  <span data-ttu-id="3a9b7-386">*PolicyDescription*是一种用户友好的策略说明, 可帮助您记住该策略的用途。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-386">*PolicyDescription*  is a user friendly description of the policy that will help you remember what the policy is for.</span></span> <span data-ttu-id="3a9b7-387">您可以在说明中包含空格。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-387">You can include spaces in the description.</span></span> <span data-ttu-id="3a9b7-388">例如, 美国邮箱和其区域的根键。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-388">For example, Root key for mailboxes in USA and its territories.</span></span> 
    
   -  <span data-ttu-id="3a9b7-389">*KeyVaultURI1*是策略中的第一个项的 URI。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-389">*KeyVaultURI1*  is the URI for the first key in the policy.</span></span> <span data-ttu-id="3a9b7-390">例如，https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-390">For example, https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01.</span></span> 
    
   -  <span data-ttu-id="3a9b7-391">*KeyVaultURI2*是策略中的第二个项的 URI。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-391">*KeyVaultURI2*  is the URI for the second key in the policy.</span></span> <span data-ttu-id="3a9b7-392">例如，https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-392">For example, https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02.</span></span> <span data-ttu-id="3a9b7-393">用逗号和空格分隔两个 Uri。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-393">Separate the two URIs by a comma and a space.</span></span> 
    
   <span data-ttu-id="3a9b7-394">示例：</span><span class="sxs-lookup"><span data-stu-id="3a9b7-394">Example:</span></span>
  
   ```
   New-DataEncryptionPolicy -Name USA_mailboxes -Description "Root key for mailboxes in USA and its territories" -AzureKeyIDs https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01, https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02
   ```

### <a name="assign-a-dep-to-a-mailbox"></a><span data-ttu-id="3a9b7-395">将 DEP 分配给邮箱</span><span class="sxs-lookup"><span data-stu-id="3a9b7-395">Assign a DEP to a mailbox</span></span>
<span data-ttu-id="3a9b7-396"><a name="assignDEPtomailbox"> </a></span><span class="sxs-lookup"><span data-stu-id="3a9b7-396"></span></span>

<span data-ttu-id="3a9b7-397">使用 "设置邮箱" cmdlet 将 DEP 分配给邮箱。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-397">Assign the DEP to a mailbox by using the Set-Mailbox cmdlet.</span></span> <span data-ttu-id="3a9b7-398">一旦分配了策略, Office 365 就可以使用 DEP 中指定的密钥对邮箱进行加密。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-398">Once you assign the policy, Office 365 can encrypt the mailbox with the key designated in the DEP.</span></span>
  
```
Set-Mailbox -Identity <MailboxIdParameter> -DataEncryptionPolicy <PolicyName>
```

<span data-ttu-id="3a9b7-399">其中*MailboxIdParameter*指定邮箱。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-399">Where *MailboxIdParameter* specifies a mailbox.</span></span> <span data-ttu-id="3a9b7-400">有关设置邮箱 cmdlet 的详细信息, 请参阅[set-邮箱](https://technet.microsoft.com/library/bb123981%28v=exchg.160%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-400">For more information about the Set-Mailbox cmdlet, see [Set-Mailbox](https://technet.microsoft.com/library/bb123981%28v=exchg.160%29.aspx).</span></span>
  
### <a name="validate-mailbox-encryption"></a><span data-ttu-id="3a9b7-401">验证邮箱加密</span><span class="sxs-lookup"><span data-stu-id="3a9b7-401">Validate mailbox encryption</span></span>
<span data-ttu-id="3a9b7-402"><a name="validatemailboxencryption"> </a></span><span class="sxs-lookup"><span data-stu-id="3a9b7-402"></span></span>

<span data-ttu-id="3a9b7-403">对邮箱加密可能需要一段时间。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-403">Encrypting a mailbox can take some time.</span></span> <span data-ttu-id="3a9b7-404">在首次分配策略时, 该邮箱还必须完成从一个数据库到另一个数据库的移动, 然后才能对该邮箱进行加密。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-404">For first time policy assignment, the mailbox must also complete the move from one database to another before the service can encrypt the mailbox.</span></span> <span data-ttu-id="3a9b7-405">建议您在更改 DEP 或首次将 DEP 分配到邮箱之后, 先等待72小时, 再尝试验证加密。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-405">We recommend that you wait 72 hours before you attempt to validate encryption after you change a DEP or the first time you assign a DEP to a mailbox.</span></span>
  
<span data-ttu-id="3a9b7-406">使用 Get-mailboxstatistics cmdlet 可以确定邮箱是否已加密。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-406">Use the Get-MailboxStatistics cmdlet to determine if a mailbox is encrypted.</span></span>
  
```
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

<span data-ttu-id="3a9b7-407">如果邮箱已加密, 则 IsEncrypted 属性返回**true** , 如果邮箱未加密, 则返回**false**值。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-407">The IsEncrypted property returns a value of **true** if the mailbox is encrypted and a value of **false** if the mailbox is not encrypted.</span></span> 

<span data-ttu-id="3a9b7-408">完成邮箱移动的时间取决于第一次为其分配 DEP 的邮箱数以及邮箱的大小。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-408">The time to complete mailbox moves depends on the number of mailboxes to which you assign a DEP for the first time, as well as the size of the mailboxes.</span></span> <span data-ttu-id="3a9b7-409">如果自您分配 DEP 之后一周后邮箱尚未加密, 请使用 New-moverequest cmdlet 为未加密邮箱启动邮箱移动。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-409">If the mailboxes have not been encrypted after a week from the time you assigned the DEP, initiate a mailbox move for the unencrypted mailboxes by using the New-MoveRequest cmdlet.</span></span>

```
New-MoveRequest <mailbox alias>
``` 

## <a name="office-365-setting-up-customer-key-for-sharepoint-online-and-onedrive-for-business"></a><span data-ttu-id="3a9b7-410">Office 365: 设置适用于 SharePoint Online 和 OneDrive for business 的客户密钥</span><span class="sxs-lookup"><span data-stu-id="3a9b7-410">Office 365: Setting up Customer Key for SharePoint Online and OneDrive for Business</span></span>
<span data-ttu-id="3a9b7-411"><a name="AzureSteps"> </a></span><span class="sxs-lookup"><span data-stu-id="3a9b7-411"></span></span>

<span data-ttu-id="3a9b7-412">在开始之前, 请确保您已完成设置 Azure Key Vault 所需的任务。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-412">Before you begin, ensure that you have completed the tasks required to set up Azure Key Vault.</span></span> <span data-ttu-id="3a9b7-413">有关信息, 请参阅[Azure Key Vault 和 Microsoft FastTrack 中的 "完成任务" 以获取客户密钥](controlling-your-data-using-customer-key.md#AzureSteps)。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-413">See [Complete tasks in Azure Key Vault and Microsoft FastTrack for Customer Key](controlling-your-data-using-customer-key.md#AzureSteps) for information.</span></span> 
  
<span data-ttu-id="3a9b7-414">若要设置适用于 SharePoint Online 和 OneDrive for business 的客户密钥, 你将需要通过使用 Windows PowerShell 远程连接到 SharePoint Online 来执行这些步骤。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-414">To set up Customer Key for SharePoint Online and OneDrive for Business, you will need to perform these steps by remotely connecting to SharePoint Online with Windows PowerShell.</span></span>
  
### <a name="create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo"></a><span data-ttu-id="3a9b7-415">为每个 SharePoint Online 和 OneDrive for business 地域创建数据加密策略 (DEP)</span><span class="sxs-lookup"><span data-stu-id="3a9b7-415">Create a data encryption policy (DEP) for each SharePoint Online and OneDrive for Business geo</span></span>
<span data-ttu-id="3a9b7-416"><a name="CreateDEP4SPOODfB"> </a></span><span class="sxs-lookup"><span data-stu-id="3a9b7-416"></span></span>

<span data-ttu-id="3a9b7-417">一个 DEP 与 Azure Key Vault 中存储的一组密钥相关联。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-417">A DEP is associated with a set of keys stored in Azure Key Vault.</span></span> <span data-ttu-id="3a9b7-418">您将 DEP 应用于一个地理位置 (也称为地理位置) 中的所有数据。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-418">You apply a DEP to all of your data in one geographic location, also called a geo.</span></span> <span data-ttu-id="3a9b7-419">如果您使用的是 Office 365 的多地理位置功能 (当前处于预览阶段), 您可以为每个地理位置创建一个 DEP。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-419">If you use the multi-geo feature of Office 365 (currently in Preview), you can create one DEP per geo.</span></span> <span data-ttu-id="3a9b7-420">如果您不使用多地理位置, 则可以在 Office 365 中创建一个用于 SharePoint Online 和 OneDrive for business 的 DEP。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-420">If you are not using multi-geo, you can create one DEP in Office 365 for use with SharePoint Online and OneDrive for Business.</span></span> <span data-ttu-id="3a9b7-421">然后, Office 365 将使用在 DEP 中标识的密钥来加密该地理位置中的数据。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-421">Office 365 will then use the keys identified in the DEP to encrypt your data in that geo.</span></span> <span data-ttu-id="3a9b7-422">若要创建 DEP, 您需要之前获取的主要保管库 Uri。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-422">To create the DEP, you need the Key Vault URIs you obtained earlier.</span></span> <span data-ttu-id="3a9b7-423">有关说明, 请参阅[获取每个 Azure Key Vault 密钥的 URI](controlling-your-data-using-customer-key.md#GetKeyURI) 。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-423">See [Obtain the URI for each Azure Key Vault key](controlling-your-data-using-customer-key.md#GetKeyURI) for instructions.</span></span> 
  
<span data-ttu-id="3a9b7-424">还!</span><span class="sxs-lookup"><span data-stu-id="3a9b7-424">Remember!</span></span> <span data-ttu-id="3a9b7-425">创建 DEP 时, 请指定驻留在两个不同的 Azure Key 保管库中的两个密钥。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-425">When you create a DEP, you specify two keys that reside in two different Azure Key Vaults.</span></span> <span data-ttu-id="3a9b7-426">确保这些项位于两个单独的 Azure 区域中, 以确保地域冗余。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-426">Ensure that these keys are located in two separate Azure regions to ensure geo-redundancy.</span></span>
  
<span data-ttu-id="3a9b7-427">若要创建 DEP, 您需要使用 Windows PowerShell 远程连接到 SharePoint Online。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-427">To create a DEP, you need to remotely connect to SharePoint Online by using Windows PowerShell.</span></span>
  
1. <span data-ttu-id="3a9b7-428">在您的本地计算机上, 使用在 Office 365 组织中具有全局管理员权限的工作或学校帐户,[连接到 SharePoint Online Powershell](https://technet.microsoft.com/library/fp161372.aspx)。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-428">On your local computer, using a work or school account that has global administrator permissions in your Office 365 organization, [Connect to SharePoint Online Powershell](https://technet.microsoft.com/library/fp161372.aspx).</span></span>
    
2. <span data-ttu-id="3a9b7-429">在 Microsoft SharePoint Online 命令行管理程序中, 运行[SPODataEncryptionPolicy](https://technet.microsoft.com/library/mt843950.aspx) cmdlet, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="3a9b7-429">In the Microsoft SharePoint Online Management Shell, run the [Register-SPODataEncryptionPolicy](https://technet.microsoft.com/library/mt843950.aspx) cmdlet as follows:</span></span> 
    
   ```
   Register-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl> -PrimaryKeyVaultName <PrimaryKeyVaultName> -PrimaryKeyName <PrimaryKeyName> -PrimaryKeyVersion <PrimaryKeyVersion> -SecondaryKeyVaultName <SecondaryKeyVaultName> -SecondaryKeyName <SecondaryKeyName> -SecondaryKeyVersion <SecondaryKeyVersion>
   ```

   <span data-ttu-id="3a9b7-430">注册 DEP 时, 会开始对 geo 中的数据进行加密。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-430">When you register the DEP, encryption begins on the data in the geo.</span></span> <span data-ttu-id="3a9b7-431">这可能需要一些时间。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-431">This can take some time.</span></span>
    
### <a name="validate-encryption-of-group-sites-team-sites-and-onedrive-for-business"></a><span data-ttu-id="3a9b7-432">验证组网站、团队网站和 OneDrive for Business 的加密</span><span class="sxs-lookup"><span data-stu-id="3a9b7-432">Validate encryption of Group Sites, Team Sites, and OneDrive for Business</span></span>
<span data-ttu-id="3a9b7-433"><a name="validateencryptionSPO"> </a></span><span class="sxs-lookup"><span data-stu-id="3a9b7-433"></span></span>

<span data-ttu-id="3a9b7-434">您可以通过运行 SPODataEncryptionPolicy cmdlet 来检查加密状态, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="3a9b7-434">You can check on the status of encryption by running the Get-SPODataEncryptionPolicy cmdlet as follows:</span></span>
  
```
Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

<span data-ttu-id="3a9b7-435">此 cmdlet 的输出包括:</span><span class="sxs-lookup"><span data-stu-id="3a9b7-435">The output from this cmdlet includes:</span></span>
  
- <span data-ttu-id="3a9b7-436">主键的 URI。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-436">The URI of the primary key.</span></span>
    
- <span data-ttu-id="3a9b7-437">辅助密钥的 URI。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-437">The URI of the secondary key.</span></span>
    
- <span data-ttu-id="3a9b7-438">地理位置的加密状态。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-438">The encryption status for the geo.</span></span> <span data-ttu-id="3a9b7-439">可能的状态包括:</span><span class="sxs-lookup"><span data-stu-id="3a9b7-439">Possible states include:</span></span>
    
  - <span data-ttu-id="3a9b7-440">未**注册:** 尚未应用客户密钥加密。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-440">**Unregistered:** Customer Key encryption has not yet been applied.</span></span> 
    
  - <span data-ttu-id="3a9b7-441">**注册:** 客户密钥加密已应用, 并且您的文件正在被加密。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-441">**Registering:** Customer Key encryption has been applied and your files are in the process of being encrypted.</span></span> <span data-ttu-id="3a9b7-442">如果你的地理位置处于此状态, 则还会显示有关 geo 中的多少个网站的完成百分比的信息, 以便你可以监视加密进度。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-442">If your geo is in this state, you'll also be shown information on what percentage of sites in the geo are complete so that you can monitor encryption progress.</span></span> 
    
  - <span data-ttu-id="3a9b7-443">**注册:** 客户密钥加密已应用, 并且所有网站中的所有文件均已加密。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-443">**Registered:** Customer Key encryption has been applied, and all files in all sites have been encrypted.</span></span> 
    
  - <span data-ttu-id="3a9b7-444">**滚动:** 正在进行密钥滚动。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-444">**Rolling:** A key roll is in progress.</span></span> <span data-ttu-id="3a9b7-445">如果你的地理位置处于此状态, 则还会显示有关已完成密钥滚动操作的网站百分比的信息, 以便你可以监视进度。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-445">If your geo is in this state, you'll also be shown information on what percentage of sites have completed the key roll operation so that you can monitor progress.</span></span> 
    
## <a name="managing-customer-key-for-office-365"></a><span data-ttu-id="3a9b7-446">管理 Office 365 的客户密钥</span><span class="sxs-lookup"><span data-stu-id="3a9b7-446">Managing Customer Key for Office 365</span></span>
<span data-ttu-id="3a9b7-447"><a name="ManageCustomerKey"> </a></span><span class="sxs-lookup"><span data-stu-id="3a9b7-447"></span></span>

<span data-ttu-id="3a9b7-448">在设置了适用于 Office 365 的客户密钥之后, 可以执行这些额外的管理任务。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-448">After you've set up Customer Key for Office 365, you can perform these additional management tasks.</span></span>
  
- [<span data-ttu-id="3a9b7-449">还原 Azure Key Vault 密钥</span><span class="sxs-lookup"><span data-stu-id="3a9b7-449">Restore Azure Key Vault keys</span></span>](controlling-your-data-using-customer-key.md#RestoreAzureKeyVaultKeys)
    
- [<span data-ttu-id="3a9b7-450">在使用客户密钥的 Azure Key Vault 中滚动或旋转密钥</span><span class="sxs-lookup"><span data-stu-id="3a9b7-450">Rolling or rotating a key in Azure Key Vault that you use with Customer Key</span></span>](controlling-your-data-using-customer-key.md#RollCKkey)
    
- [<span data-ttu-id="3a9b7-451">管理密钥存储库权限</span><span class="sxs-lookup"><span data-stu-id="3a9b7-451">Manage key vault permissions</span></span>](controlling-your-data-using-customer-key.md#Managekeyvaultperms)
    
- [<span data-ttu-id="3a9b7-452">确定分配给邮箱的 DEP</span><span class="sxs-lookup"><span data-stu-id="3a9b7-452">Determine the DEP assigned to a mailbox</span></span>](controlling-your-data-using-customer-key.md#DeterminemailboxDEP)
    
### <a name="restore-azure-key-vault-keys"></a><span data-ttu-id="3a9b7-453">还原 Azure Key Vault 密钥</span><span class="sxs-lookup"><span data-stu-id="3a9b7-453">Restore Azure Key Vault keys</span></span>
<span data-ttu-id="3a9b7-454"><a name="RestoreAzureKeyVaultKeys"> </a></span><span class="sxs-lookup"><span data-stu-id="3a9b7-454"></span></span>

<span data-ttu-id="3a9b7-455">在执行还原之前, 请使用由软删除提供的恢复功能。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-455">Before performing a restore, use the recovery capabilities provided by soft delete.</span></span> <span data-ttu-id="3a9b7-456">需要使用与客户密钥一起使用的所有密钥才能启用软删除。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-456">All keys that are used with Customer Key are required to have soft delete enabled.</span></span> <span data-ttu-id="3a9b7-457">软删除操作类似于回收站, 允许恢复最长为90天, 而无需进行还原。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-457">Soft delete acts like a recycle bin and allows recovery for up to 90 days without the need to restore.</span></span> <span data-ttu-id="3a9b7-458">只有在极端或异常情况下才需要还原, 例如, 密钥或密钥存储库丢失。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-458">Restore should only be required in extreme or unusual circumstances, for example if the key or key vault is lost.</span></span> <span data-ttu-id="3a9b7-459">如果您必须还原密钥以用于客户密钥, 请在 Azure PowerShell 中运行 AzureKeyVaultKey cmdlet, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="3a9b7-459">If you must restore a key for use with Customer Key, in Azure PowerShell, run the Restore-AzureKeyVaultKey cmdlet as follows:</span></span>
  
```
Restore-AzureKeyVaultKey -VaultName <vaultname> -InputFile <filename>
```

<span data-ttu-id="3a9b7-460">例如：</span><span class="sxs-lookup"><span data-stu-id="3a9b7-460">For example:</span></span>
  
```
Restore-AzureKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -InputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

<span data-ttu-id="3a9b7-461">如果密钥存储区中已存在具有相同名称的键, 还原操作将失败。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-461">If a key with the same name already exists in the key vault, the restore operation will fail.</span></span> <span data-ttu-id="3a9b7-462">Restore-AzureKeyVaultKey 还原密钥的所有密钥版本和所有元数据, 包括密钥名称。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-462">Restore-AzureKeyVaultKey restores all key versions and all metadata for the key including the key name.</span></span>
  
### <a name="rolling-or-rotating-a-key-in-azure-key-vault-that-you-use-with-customer-key"></a><span data-ttu-id="3a9b7-463">在使用客户密钥的 Azure Key Vault 中滚动或旋转密钥</span><span class="sxs-lookup"><span data-stu-id="3a9b7-463">Rolling or rotating a key in Azure Key Vault that you use with Customer Key</span></span>
<span data-ttu-id="3a9b7-464"><a name="RollCKkey"> </a></span><span class="sxs-lookup"><span data-stu-id="3a9b7-464"></span></span>

<span data-ttu-id="3a9b7-465">Azure Key Vault 或 Customer 密钥不需要滚动密钥。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-465">Rolling keys is not required by either Azure Key Vault or by Customer Key.</span></span> <span data-ttu-id="3a9b7-466">此外, 通过 HSM 保护的密钥几乎不可能受到危害。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-466">In addition, keys that are protected with an HSM are virtually impossible to compromise.</span></span> <span data-ttu-id="3a9b7-467">即使某个根键是在拥有恶意参与者的情况下, 也没有使用它来解密数据的可行方法, 因为只有 Office 365 代码知道了如何使用它。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-467">Even if a root key were in the possession of a malicious actor there is no feasible means of using it to decrypt data, since only Office 365 code knows how to use it.</span></span> <span data-ttu-id="3a9b7-468">但是, 滚动密钥是由客户密钥支持的。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-468">However, rolling a key is supported by Customer Key.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="3a9b7-469">在明确的技术原因或合规性要求规定您必须滚动密钥时, 只需滚动与客户密钥一起使用的加密密钥。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-469">Only roll an encryption key that you use with Customer Key when a clear technical reason exists or a compliance requirement dictates that you have to roll the key.</span></span> <span data-ttu-id="3a9b7-470">此外, 请勿删除与策略关联的或与之相关联的任何密钥。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-470">In addition, do not delete any keys that are or were associated with policies.</span></span> <span data-ttu-id="3a9b7-471">在滚动键时, 会使用以前的密钥对内容进行加密。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-471">When you roll your keys, there will be content encrypted with the previous keys.</span></span> <span data-ttu-id="3a9b7-472">例如, 虽然活动邮箱将被频繁地重新加密, 但非活动邮箱、断开连接和已禁用邮箱仍可以使用以前的密钥进行加密。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-472">For example, while active mailboxes will be re-encrypted frequently, inactive, disconnected, and disabled mailboxes may still be encrypted with the previous keys.</span></span> <span data-ttu-id="3a9b7-473">SharePoint Online 执行用于还原和恢复目的的内容备份, 因此可能仍有存档的内容使用旧密钥。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-473">SharePoint Online performs backup of content for restore and recovery purposes, so there may still be archived content using older keys.</span></span> <br/> <span data-ttu-id="3a9b7-474">为了确保数据的安全性, SharePoint Online 将不允许一个以上的键滚动操作一次进行。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-474">To ensure the safety of your data, SharePoint Online will allow no more than one Key Roll operation to be in progress at a time.</span></span> <span data-ttu-id="3a9b7-475">如果要将密钥存储库中的两个密钥一起滚动, 则需要等待第一个密钥滚动操作完全完成。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-475">If you want to roll both of the keys in a key vault, you'll need to wait for the first key roll operation to fully complete.</span></span> <span data-ttu-id="3a9b7-476">我们建议您将密钥滚动操作以不同的间隔错开, 这样就不会出现问题。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-476">Our recommendation is to stagger your key roll operations at different intervals, so that this is not an issue.</span></span> 
  
<span data-ttu-id="3a9b7-477">当您滚动某个键时, 您请求的是现有密钥的新版本。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-477">When you roll a key, you are requesting a new version of an existing key.</span></span> <span data-ttu-id="3a9b7-478">若要请求现有密钥的新版本, 请使用相同的 cmdlet ( [AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Add-AzureKeyVaultKey)), 其语法与您在第一个位置创建密钥时使用的语法相同。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-478">In order to request a new version of an existing key, you use the same cmdlet, [Add-AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Add-AzureKeyVaultKey), with the same syntax that you used to create the key in the first place.</span></span>
  
<span data-ttu-id="3a9b7-479">例如：</span><span class="sxs-lookup"><span data-stu-id="3a9b7-479">For example:</span></span>
  
```
Add-AzureKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination HSM -KeyOps @('wrapKey','unwrapKey') -NotBefore (Get-Date -Date "12/27/2016 12:01 AM")
```

<span data-ttu-id="3a9b7-480">在此示例中, 由于名为**contoso-O365EX-VaultA1-Key001**的键在**contoso-O365EX-na-VaultA1**保管库中已存在, 将创建一个新的密钥版本。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-480">In this example, since a key named **Contoso-O365EX-NA-VaultA1-Key001** already exists in the **Contoso-O365EX-NA-VaultA1** vault, a new key version will be created.</span></span> <span data-ttu-id="3a9b7-481">该操作将添加新的密钥版本。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-481">The operation adds a new key version.</span></span> <span data-ttu-id="3a9b7-482">此操作将保留密钥版本历史记录中以前的密钥版本, 以便仍可以解密之前使用该密钥加密的数据。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-482">This operation preserves the previous key versions in the key's version history, so that data previously encrypted with that key can still be decrypted.</span></span> <span data-ttu-id="3a9b7-483">完成滚动与 DEP 关联的任何键后, 必须运行其他 cmdlet, 以确保客户密钥开始使用新密钥。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-483">Once you have completed rolling any key that is associated with a DEP, you must then run an additional cmdlet to ensure Customer Key begins using the new key.</span></span> 
  
#### <a name="enable-exchange-online-and-skype-for-business-to-use-a-new-key-after-you-roll-or-rotate-keys-in-azure-key-vault"></a><span data-ttu-id="3a9b7-484">在滚动或旋转 Azure Key Vault 中的密钥之后, 启用 Exchange Online 和 Skype for business 以使用新密钥</span><span class="sxs-lookup"><span data-stu-id="3a9b7-484">Enable Exchange Online and Skype for Business to use a new key after you roll or rotate keys in Azure Key Vault</span></span>

<span data-ttu-id="3a9b7-485">当您滚动与 Exchange Online 和 Skype for business 使用的 DEP 相关联的任何 Azure Key Vault 密钥时, 您必须运行以下命令来更新 DEP 并启用 Office 365 以开始使用新密钥。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-485">When you roll either of the Azure Key Vault keys associated with a DEP used with Exchange Online and Skype for Business, you must run the following command to update the DEP and enable Office 365 to start using the new key.</span></span>
  
<span data-ttu-id="3a9b7-486">若要指示客户密钥使用新密钥加密 Office 365 中的邮箱, 请运行 DataEncryptionPolicy cmdlet, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="3a9b7-486">To instruct Customer Key to use the new key to encrypt mailboxes in Office 365 run the Set-DataEncryptionPolicy cmdlet as follows:</span></span>
  
```
Set-DataEncryptionPolicy <policyname> -Refresh 
```

<span data-ttu-id="3a9b7-487">在48小时内, 使用此策略加密的活动邮箱将会与更新的密钥相关联。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-487">Within 48 hours, the active mailboxes encrypted using this policy will become associated with the updated key.</span></span> <span data-ttu-id="3a9b7-488">按照[确定分配给邮箱的 DEP](controlling-your-data-using-customer-key.md#DeterminemailboxDEP)中的步骤检查邮箱的 DataEncryptionPolicyID 属性的值。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-488">Use the steps in [Determine the DEP assigned to a mailbox](controlling-your-data-using-customer-key.md#DeterminemailboxDEP) to check the value for the DataEncryptionPolicyID property for the mailbox.</span></span> <span data-ttu-id="3a9b7-489">一旦应用了更新的键, 此属性的值将更改。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-489">The value for this property will change once the updated key has been applied.</span></span> 
  
#### <a name="enable-sharepoint-online-and-onedrive-for-business-to-use-a-new-key-after-you-roll-or-rotate-keys-in-azure-key-vault"></a><span data-ttu-id="3a9b7-490">启用 SharePoint Online 和 OneDrive for business 以在 Azure Key Vault 中滚动或旋转密钥后使用新密钥</span><span class="sxs-lookup"><span data-stu-id="3a9b7-490">Enable SharePoint Online and OneDrive for Business to use a new key after you roll or rotate keys in Azure Key Vault</span></span>

<span data-ttu-id="3a9b7-491">当您滚动与 SharePoint Online 和 OneDrive for Business 使用的 DEP 相关联的任何 Azure Key Vault 密钥时, 您必须运行[SPODataEncryptionPolicy](https://technet.microsoft.com/library/mt843948.aspx) cmdlet 以更新 DEP, 并启用 Office 365 以开始使用新密钥。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-491">When you roll either of the Azure Key Vault keys associated with a DEP used with SharePoint Online and OneDrive for Business, you must run the [Update-SPODataEncryptionPolicy](https://technet.microsoft.com/library/mt843948.aspx) cmdlet to update the DEP and enable Office 365 to start using the new key.</span></span> 
  
```
Update-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl> -KeyVaultName <ReplacementKeyVaultName> -KeyName <ReplacementKeyName> -KeyVersion <ReplacementKeyVersion> -KeyType <Primary | Secondary>
```

<span data-ttu-id="3a9b7-492">这将启动 SharePoint Online 和 OneDrive for business 的密钥滚动操作。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-492">This will start the key roll operation for SharePoint Online and OneDrive for Business.</span></span> <span data-ttu-id="3a9b7-493">此操作不是即时执行的。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-493">This action is not immediate.</span></span> <span data-ttu-id="3a9b7-494">若要查看密钥滚动操作的进度, 请运行 SPODataEncryptionPolicy cmdlet, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="3a9b7-494">To see the progress of the key roll operation, run the Get-SPODataEncryptionPolicy cmdlet as follows:</span></span>
  
```
Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

### <a name="manage-key-vault-permissions"></a><span data-ttu-id="3a9b7-495">管理密钥存储库权限</span><span class="sxs-lookup"><span data-stu-id="3a9b7-495">Manage key vault permissions</span></span>
<span data-ttu-id="3a9b7-496"><a name="Managekeyvaultperms"> </a></span><span class="sxs-lookup"><span data-stu-id="3a9b7-496"></span></span>

<span data-ttu-id="3a9b7-497">提供了多个 cmdlet, 以便你可以查看并在必要时删除密钥保管库权限 (如有必要)。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-497">Several cmdlets are available that enable you to view and, if necessary, remove key vault permissions.</span></span> <span data-ttu-id="3a9b7-498">您可能需要删除权限, 例如, 当员工离开团队时。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-498">You might need to remove permissions, for example, when an employee leaves the team.</span></span>
  
<span data-ttu-id="3a9b7-499">若要查看密钥存储区权限, 请运行 AzureRmKeyVault cmdlet:</span><span class="sxs-lookup"><span data-stu-id="3a9b7-499">To view key vault permissions, run the Get-AzureRmKeyVault cmdlet:</span></span>
  
```
Get-AzureRmKeyVault -VaultName <vaultname>
```

<span data-ttu-id="3a9b7-500">例如：</span><span class="sxs-lookup"><span data-stu-id="3a9b7-500">For example:</span></span>
  
```
Get-AzureRmKeyVault -VaultName Contoso-O365EX-NA-VaultA1
```

<span data-ttu-id="3a9b7-501">若要删除管理员权限, 请运行 AzureRmKeyVaultAccessPolicy cmdlet:</span><span class="sxs-lookup"><span data-stu-id="3a9b7-501">To remove an administrator's permissions, run the Remove-AzureRmKeyVaultAccessPolicy cmdlet:</span></span>
  
```
Remove-AzureRmKeyVaultAccessPolicy -VaultName <vaultname> 
-UserPrincipalName <UPN of user>
```

<span data-ttu-id="3a9b7-502">例如：</span><span class="sxs-lookup"><span data-stu-id="3a9b7-502">For example:</span></span>
  
```
Remove-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
-UserPrincipalName alice@contoso.com
```

### <a name="determine-the-dep-assigned-to-a-mailbox"></a><span data-ttu-id="3a9b7-503">确定分配给邮箱的 DEP</span><span class="sxs-lookup"><span data-stu-id="3a9b7-503">Determine the DEP assigned to a mailbox</span></span>
<span data-ttu-id="3a9b7-504"><a name="DeterminemailboxDEP"> </a></span><span class="sxs-lookup"><span data-stu-id="3a9b7-504"></span></span>

<span data-ttu-id="3a9b7-505">若要确定分配给邮箱的 DEP, 请使用 Get-mailboxstatistics cmdlet。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-505">To determine the DEP assigned to a mailbox, use the Get-MailboxStatistics cmdlet.</span></span> <span data-ttu-id="3a9b7-506">Cmdlet 返回唯一标识符 (GUID)。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-506">The cmdlet returns a unique identifier (GUID).</span></span>
  
```
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl DataEncryptionPolicyID
```

<span data-ttu-id="3a9b7-507">其中*GeneralMailboxOrMailUserIdParameter*指定邮箱。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-507">Where *GeneralMailboxOrMailUserIdParameter* specifies a mailbox.</span></span> <span data-ttu-id="3a9b7-508">有关 Get-mailboxstatistics cmdlet 的详细信息, 请参阅[get-mailboxstatistics](https://technet.microsoft.com/library/bb124612%28v=exchg.160%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-508">For more information about the Get-MailboxStatistics cmdlet, see [Get-MailboxStatistics](https://technet.microsoft.com/library/bb124612%28v=exchg.160%29.aspx).</span></span>
  
<span data-ttu-id="3a9b7-509">通过运行以下 cmdlet, 使用 GUID 找出邮箱所分配到的 DEP 的友好名称。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-509">Use the GUID to find out the friendly name of the DEP to which the mailbox is assigned by running the following cmdlet.</span></span>
  
```
Get-DataEncryptionPolicy <GUID>
```

<span data-ttu-id="3a9b7-510">其中*guid*是上一步中的 get-mailboxstatistics cmdlet 返回的 guid。</span><span class="sxs-lookup"><span data-stu-id="3a9b7-510">Where *GUID* is the GUID returned by the Get-MailboxStatistics cmdlet in the previous step.</span></span> 
  

