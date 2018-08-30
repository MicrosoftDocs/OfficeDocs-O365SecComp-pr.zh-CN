---
title: 使用客户密钥控制 Office 365 中的数据
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 7/2/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: f2cd475a-e592-46cf-80a3-1bfb0fa17697
description: 了解如何设置客户参数 Office 365 的 Exchange Online、 Skype 的业务和 SharePoint Online 的 OneDrive for Business。与客户参数，您将控制组织的加密密钥，然后配置 Office 365 使用它们在 Microsoft 数据中心中的 rest 数据进行加密。
ms.openlocfilehash: f8d7c12c32ca74b842f676f4a2ccde4d1c758361
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22559227"
---
# <a name="controlling-your-data-in-office-365-using-customer-key"></a><span data-ttu-id="b336e-104">使用客户密钥控制 Office 365 中的数据</span><span class="sxs-lookup"><span data-stu-id="b336e-104">Controlling your data in Office 365 using Customer Key</span></span>

<span data-ttu-id="b336e-p102">与客户参数，您将控制组织的加密密钥，然后配置 Office 365 使用它们在 Microsoft 数据中心中的 rest 数据进行加密。静态数据包括 Exchange Online 和 Skype for Business 内的邮箱和 SharePoint Online 中存储的文件中存储和 OneDrive for Business 中的数据。</span><span class="sxs-lookup"><span data-stu-id="b336e-p102">With Customer Key, you control your organization's encryption keys and then configure Office 365 to use them to encrypt your data at rest in Microsoft's data centers. Data at rest includes data from Exchange Online and Skype for Business that is stored in mailboxes and files that are stored in SharePoint Online and OneDrive for Business.</span></span>
  
<span data-ttu-id="b336e-p103">可以使用的 Office 365 客户密钥之前，必须设置 Azure。本主题介绍了您需要按照创建和配置所需的 Azure 资源的步骤，然后设置 Office 365 中的客户参数提供的步骤。Azure 安装完成后，您可以确定哪些策略，因此，哪些键，分配给邮箱和您的组织中的文件。邮箱和不为其分配策略的文件将使用的控制以及由 Microsoft 托管加密策略。有关客户参数的详细信息，或的一般概述，请参阅[Office 365 常见问题的客户参数](service-encryption-with-customer-key-faq.md)。</span><span class="sxs-lookup"><span data-stu-id="b336e-p103">You must set up Azure before you can use Customer Key for Office 365. This topic describes the steps you need to follow to create and configure the required Azure resources and then provides the steps for setting up Customer Key in Office 365. After you have completed Azure setup, you determine which policy, and therefore, which keys, to assign to mailboxes and files in your organization. Mailboxes and files for which you don't assign a policy will use encryption policies that are controlled and managed by Microsoft. For more information about Customer Key, or for a general overview, see the [Customer Key for Office 365 FAQ](service-encryption-with-customer-key-faq.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="b336e-p104">我们强烈建议您按照本主题中的最佳做法。这些称为作为**提示**和**重要**。客户密钥使您能够控制其范围可为您的整个组织的根加密密钥。这意味着错误用这些项可以具有广泛的影响，并且可能会导致服务中断或不可撤消丢失数据。</span><span class="sxs-lookup"><span data-stu-id="b336e-p104">We strongly recommend that you follow the best practices in this topic. These are called out as **TIP** and **IMPORTANT**. Customer Key gives you control over root encryption keys whose scope can be as large as your entire organization. This means that mistakes made with these keys can have a broad impact and may result in service interruptions or irrevocable loss of your data.</span></span> 
  
## <a name="before-you-begin-setting-up-customer-key"></a><span data-ttu-id="b336e-116">开始之前设置客户参数</span><span class="sxs-lookup"><span data-stu-id="b336e-116">Before you begin setting up Customer Key</span></span>
<span data-ttu-id="b336e-117"><a name="Beforeyoustart"> </a></span><span class="sxs-lookup"><span data-stu-id="b336e-117"></span></span>

<span data-ttu-id="b336e-p105">在开始之前，确保您具有相应组织的授权。Office 365 中的客户参数是 Office 365 E5 或高级合规性 SKU 中提供的。</span><span class="sxs-lookup"><span data-stu-id="b336e-p105">Before you get started, be sure you have the appropriate licensing for your organization. Customer Key in Office 365 is offered in Office 365 E5 or the Advanced Compliance SKU.</span></span>
  
<span data-ttu-id="b336e-p106">然后，若要了解的概念和本主题中的过程，您应当查看[Azure 键仓库](https://azure.microsoft.com/en-us/documentation/services/key-vault/)文档。此外，先熟悉在 Azure，例如，[租户](https://msdn.microsoft.com/library/azure/jj573650.aspx#BKMK_WhatIsAnAzureADTenant)中使用的术语。</span><span class="sxs-lookup"><span data-stu-id="b336e-p106">Then, to understand the concepts and procedures in this topic, you should review the [Azure Key Vault](https://azure.microsoft.com/en-us/documentation/services/key-vault/) documentation. Also, become familiar with the terms used in Azure, for example, [tenant](https://msdn.microsoft.com/library/azure/jj573650.aspx#BKMK_WhatIsAnAzureADTenant).</span></span>
  
<span data-ttu-id="b336e-122">若要提供反馈客户项，包括文档，请向 customerkeyfeedback@microsoft.com 发送您的想法、 建议和角度。</span><span class="sxs-lookup"><span data-stu-id="b336e-122">To provide feedback on Customer Key, including the documentation, send your ideas, suggestions and perspectives to customerkeyfeedback@microsoft.com.</span></span>
  
## <a name="overview-of-setting-up-customer-key-for-office-365"></a><span data-ttu-id="b336e-123">客户参数设置为 Office 365 概述</span><span class="sxs-lookup"><span data-stu-id="b336e-123">Overview of setting up Customer Key for Office 365</span></span>
<span data-ttu-id="b336e-124"><a name="Overview"> </a></span><span class="sxs-lookup"><span data-stu-id="b336e-124"></span></span>

<span data-ttu-id="b336e-p107">若要设置客户参数将完成这些任务。本主题的其余部分提供了详细的说明每项任务，或出过程中每个步骤的详细信息的链接。</span><span class="sxs-lookup"><span data-stu-id="b336e-p107">To set up Customer Key you will complete these tasks. The rest of this topic provides detailed instructions for each task, or links out to more information for each step in the process.</span></span>
  
<span data-ttu-id="b336e-127">**Azure 和 Microsoft FastTrack： 中**</span><span class="sxs-lookup"><span data-stu-id="b336e-127">**In Azure and Microsoft FastTrack:**</span></span>
  
<span data-ttu-id="b336e-p108">您将通过远程连接到 Azure PowerShell 完成这些任务的大部分。为了获得最佳结果，使用版本 4.4.0 或更高版本的 Azure PowerShell。</span><span class="sxs-lookup"><span data-stu-id="b336e-p108">You will complete most of these tasks by remotely connecting to Azure PowerShell. For best results, use version 4.4.0 or later of Azure PowerShell.</span></span>
  
- [<span data-ttu-id="b336e-130">创建两个新的 Azure 订阅</span><span class="sxs-lookup"><span data-stu-id="b336e-130">Create two new Azure subscriptions</span></span>](controlling-your-data-using-customer-key.md#Create2newsubs)
    
- [<span data-ttu-id="b336e-131">注册使用强制性的保留期的 Azure 订阅</span><span class="sxs-lookup"><span data-stu-id="b336e-131">Register Azure subscriptions to use a mandatory retention period</span></span>](controlling-your-data-using-customer-key.md#RegisterSubsforMRP)
    
    <span data-ttu-id="b336e-132">注册可能需要介于 1 到 5 个工作日。</span><span class="sxs-lookup"><span data-stu-id="b336e-132">Registration can take from one to five business days.</span></span>
    
- [<span data-ttu-id="b336e-133">提交一个请求激活的 Office 365 客户参数</span><span class="sxs-lookup"><span data-stu-id="b336e-133">Submit a request to activate Customer Key for Office 365</span></span>](controlling-your-data-using-customer-key.md#FastTrack)
    
    <span data-ttu-id="b336e-p109">创建两个新 Azure 订阅后，您需要通过完成 Microsoft FastTrack 门户中承载的 web 表单提交适当的客户参数提供请求。FastTrack 团队不与客户参数提供帮助。Office 只需使用 FastTrack 门户以允许您来提交表单，并将有助于我们开发出跟踪客户项相关的产品。</span><span class="sxs-lookup"><span data-stu-id="b336e-p109">Once you've created the two new Azure subscriptions, you'll need to submit the appropriate Customer Key offer request by completing a web form that is hosted in the Microsoft FastTrack portal. The FastTrack team doesn't provide assistance with Customer Key. Office simply uses the FastTrack portal to allow you to submit the form and to help us track the relevant offers for Customer Key.</span></span>
  
<span data-ttu-id="b336e-p110">后已提交客户参数版，Microsoft 审阅您的请求，并且可以继续执行安装任务的其余部分时通知您。此过程可能需要最多五个工作日。</span><span class="sxs-lookup"><span data-stu-id="b336e-p110">Once you have submitted a Customer Key offer, Microsoft reviews your request and notifies you when you can proceed with the rest of the setup tasks. This process can take up to five business days.</span></span>
    
- [<span data-ttu-id="b336e-139">在每个订阅中创建 Azure 键仓库 premium</span><span class="sxs-lookup"><span data-stu-id="b336e-139">Create a premium Azure Key Vault in each subscription</span></span>](controlling-your-data-using-customer-key.md#CreateKeyVault)
    
- [<span data-ttu-id="b336e-140">将权限分配给每个主要的存储库</span><span class="sxs-lookup"><span data-stu-id="b336e-140">Assign permissions to each key vault</span></span>](controlling-your-data-using-customer-key.md#KeyVaultPerms)
    
- [<span data-ttu-id="b336e-141">启用，然后确认软删除的主要存储库</span><span class="sxs-lookup"><span data-stu-id="b336e-141">Enable and then confirm soft delete on your key vaults</span></span>](controlling-your-data-using-customer-key.md#SoftDelete)
    
- [<span data-ttu-id="b336e-142">将项添加到每个关键电子仓库可以通过创建或导入密钥</span><span class="sxs-lookup"><span data-stu-id="b336e-142">Add a key to each key vault either by creating or importing a key</span></span>](controlling-your-data-using-customer-key.md#AddKeystoKeyVault)
    
- [<span data-ttu-id="b336e-143">检查您的密钥的恢复级别</span><span class="sxs-lookup"><span data-stu-id="b336e-143">Check the recovery level of your keys</span></span>](controlling-your-data-using-customer-key.md#CheckKeyRecoveryLevel)
    
- [<span data-ttu-id="b336e-144">备份 Azure 存储库</span><span class="sxs-lookup"><span data-stu-id="b336e-144">Backup Azure Key Vault</span></span>](controlling-your-data-using-customer-key.md#BackupAzureKeyVaultkeys)
    
- [<span data-ttu-id="b336e-145">验证 Azure 键仓库配置设置</span><span class="sxs-lookup"><span data-stu-id="b336e-145">Validate Azure Key Vault configuration settings</span></span>](controlling-your-data-using-customer-key.md#Validateconfiguration)
    
- [<span data-ttu-id="b336e-146">获取每个 Azure 键仓库键的 URI</span><span class="sxs-lookup"><span data-stu-id="b336e-146">Obtain the URI for each Azure Key Vault key</span></span>](controlling-your-data-using-customer-key.md#GetKeyURI)
    
<span data-ttu-id="b336e-147">**Office 365： 中**</span><span class="sxs-lookup"><span data-stu-id="b336e-147">**In Office 365:**</span></span>
  
<span data-ttu-id="b336e-148">Exchange Online 和 Skype for Business:</span><span class="sxs-lookup"><span data-stu-id="b336e-148">Exchange Online and Skype for Business:</span></span>
  
- [<span data-ttu-id="b336e-149">创建用于 Exchange Online 和 Skype 的业务数据加密策略 (DEP)</span><span class="sxs-lookup"><span data-stu-id="b336e-149">Create a data encryption policy (DEP) for use with Exchange Online and Skype for Business</span></span>](controlling-your-data-using-customer-key.md#CreateDEP4EXOSkype)
    
- [<span data-ttu-id="b336e-150">分配邮箱的 DEP</span><span class="sxs-lookup"><span data-stu-id="b336e-150">Assign a DEP to a mailbox</span></span>](controlling-your-data-using-customer-key.md#assignDEPtomailbox)
    
- [<span data-ttu-id="b336e-151">验证邮箱加密</span><span class="sxs-lookup"><span data-stu-id="b336e-151">Validate mailbox encryption</span></span>](controlling-your-data-using-customer-key.md#validatemailboxencryption)
    
<span data-ttu-id="b336e-152">SharePoint Online 和 OneDrive for Business:</span><span class="sxs-lookup"><span data-stu-id="b336e-152">SharePoint Online and OneDrive for Business:</span></span>
  
- [<span data-ttu-id="b336e-153">为业务地理位置的每个 SharePoint Online 和 OneDrive 创建数据加密策略 (DEP)</span><span class="sxs-lookup"><span data-stu-id="b336e-153">Create a data encryption policy (DEP) for each SharePoint Online and OneDrive for Business geo</span></span>](controlling-your-data-using-customer-key.md#CreateDEP4SPOODfB)
    
- [<span data-ttu-id="b336e-154">验证组网站、 工作组网站和 OneDrive for Business 的加密</span><span class="sxs-lookup"><span data-stu-id="b336e-154">Validate encryption of Group Sites, Team Sites, and OneDrive for Business</span></span>](controlling-your-data-using-customer-key.md#validateencryptionSPO)
    
## <a name="complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key"></a><span data-ttu-id="b336e-155">Azure 键仓库和客户键的 Microsoft FastTrack 中完成任务</span><span class="sxs-lookup"><span data-stu-id="b336e-155">Complete tasks in Azure Key Vault and Microsoft FastTrack for Customer Key</span></span>
<span data-ttu-id="b336e-156"><a name="AzureSteps"> </a></span><span class="sxs-lookup"><span data-stu-id="b336e-156"></span></span>

<span data-ttu-id="b336e-p111">Office 365 客户密钥设置为了完成 Azure 键存储库中的这些任务。您需要完成这些步骤，无论您是否打算客户参数为 Exchange Online 和设置 Skype 业务或 SharePoint Online 和 OneDrive for Business 或 Office 365 中的所有受支持的服务。</span><span class="sxs-lookup"><span data-stu-id="b336e-p111">Complete these tasks in Azure Key Vault in order to set up Customer Key for Office 365. You will need to complete these steps regardless of whether you intend to set up Customer Key for Exchange Online and Skype for Business or SharePoint Online and OneDrive for Business or for all supported services in Office 365.</span></span>
  
### <a name="create-two-new-azure-subscriptions"></a><span data-ttu-id="b336e-159">创建两个新的 Azure 订阅</span><span class="sxs-lookup"><span data-stu-id="b336e-159">Create two new Azure subscriptions</span></span>
<span data-ttu-id="b336e-160"><a name="Create2newsubs"> </a></span><span class="sxs-lookup"><span data-stu-id="b336e-160"></span></span>

<span data-ttu-id="b336e-p112">两个 Azure 订阅所需的客户参数。作为最佳实践，Microsoft 建议您与客户参数创建用于新 Azure 订阅。仅授权中相同的 Azure Active Directory (AAD) 租户的应用程序的 azure 键仓库键，您必须创建使用用于 Office 365 组织将分配给 DEPs 同一 Azure AD 租户的新订阅。例如，使用工作或学校帐户已在 Office 365 组织中的全局管理员权限。有关详细步骤，请参阅[注册为组织的 Azure](https://azure.microsoft.com/en-us/documentation/articles/sign-up-organization/)。</span><span class="sxs-lookup"><span data-stu-id="b336e-p112">Two Azure subscriptions are required for Customer Key. As a best practice, Microsoft recommends that you create new Azure subscriptions for use with Customer Key. Azure Key Vault keys can only be authorized for applications in the same Azure Active Directory (AAD) tenant, you must create the new subscriptions using the same Azure AD tenant used with your Office 365 organization where the DEPs will be assigned. For example, using your work or school account that has global administrator privileges in your Office 365 organization. For detailed steps, see [Sign up for Azure as an organization](https://azure.microsoft.com/en-us/documentation/articles/sign-up-organization/).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="b336e-p113">客户参数为每个数据加密策略 (DEP) 需要两个键。若要实现此目的，您必须创建两个 Azure 订阅。作为最佳实践，Microsoft 建议您让组织的单独成员在每个订阅中配置一个键。此外，这些 Azure 订阅，只应使用 Office 365 中管理加密密钥。您运算符之一意外、 有意，或恶意删除或否则 mismanages 他们有责任的键的情况下，此保护您的组织。</span><span class="sxs-lookup"><span data-stu-id="b336e-p113">Customer Key requires two keys for each data encryption policy (DEP). In order to achieve this, you must create two Azure subscriptions. As a best practice, Microsoft recommends that you have separate members of your organization configure one key in each subscription. In addition, these Azure subscriptions should only be used to administer encryption keys for Office 365. This protects your organization in case one of your operators accidentally, intentionally, or maliciously deletes or otherwise mismanages the keys for which they are responsible. </span></span><br/> <span data-ttu-id="b336e-p114">我们建议您设置仅用于客户密钥管理使用 Azure 键仓库资源的新 Azure 订阅。没有可行到可以为组织创建的 Azure 订阅数限制。遵循这些最佳做法将最小化人为错误的影响同时帮助管理客户参数使用的资源。</span><span class="sxs-lookup"><span data-stu-id="b336e-p114">We recommend that you set up new Azure subscriptions that are solely used for managing Azure Key Vault resources for use with Customer Key. There is no practical limit to the number of Azure subscriptions that you can create for your organization. Following these best practices will minimize the impact of human error while helping to manage the resources used by Customer Key.</span></span> 
  
### <a name="submit-a-request-to-activate-customer-key-for-office-365"></a><span data-ttu-id="b336e-174">提交一个请求激活的 Office 365 客户参数</span><span class="sxs-lookup"><span data-stu-id="b336e-174">Submit a request to activate Customer Key for Office 365</span></span>
<span data-ttu-id="b336e-175"><a name="FastTrack"> </a></span><span class="sxs-lookup"><span data-stu-id="b336e-175"></span></span>

<span data-ttu-id="b336e-p115">完成的 Azure 步骤之后，您需要提交[Microsoft FastTrack 门户](https://fasttrack.microsoft.com/)中的提供请求。一旦您已提交一个请求通过 FastTrack web 门户，Microsoft 将验证您提供的 Azure 键仓库配置数据和联系人信息。提供有关授权部主管的形式组织做的选择是关键和所需完成客户参数注册。您在窗体中选择您所在组织的部主管将用于确保任何请求撤销并销毁与客户参数数据加密策略所使用的所有项的可靠性。您需要执行一次此步骤的 Exchange Online 和 Skype 的业务范围和第二次 SharePoint Online 和 OneDrive for Business 的激活客户密钥激活客户参数。</span><span class="sxs-lookup"><span data-stu-id="b336e-p115">Once you've completed the Azure steps, you'll need to submit an offer request in the [Microsoft FastTrack portal](https://fasttrack.microsoft.com/). Once you have submitted a request through the FastTrack web portal, Microsoft verifies the Azure Key Vault configuration data and contact information you provided. The selections that you make in the offer form regarding the authorized officers of your organization is critical and necessary for completion of Customer Key registration. The officers of your organization that you select in the form will be the used to ensure the authenticity of any request to revoke and destroy all keys used with a Customer Key data encryption policy. You'll need to do this step once to activate Customer Key for Exchange Online and Skype for Business coverage and a second time to activate Customer Key for SharePoint Online and OneDrive for Business.</span></span>
  
<span data-ttu-id="b336e-181">若要提交提供的激活客户密钥，请完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="b336e-181">To submit an offer to activate Customer Key, complete these steps:</span></span>
  
1. <span data-ttu-id="b336e-182">使用 Office 365 组织中具有全局管理员权限的工作或学校帐户，登录到[Microsoft FastTrack 门户](https://fasttrack.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="b336e-182">Using a work or school account that has global administrator permissions in your Office 365 organization, log in to the [Microsoft FastTrack portal](https://fasttrack.microsoft.com/).</span></span>
    
2. <span data-ttu-id="b336e-183">一旦您登录，浏览到**仪表板**。</span><span class="sxs-lookup"><span data-stu-id="b336e-183">Once you're logged in, browse to the **Dashboard**.</span></span>
    
3. <span data-ttu-id="b336e-184">选择**提供**，并查看当前提供的列表。</span><span class="sxs-lookup"><span data-stu-id="b336e-184">Choose **Offers**, and review the list of current offers.</span></span>
    
4. <span data-ttu-id="b336e-185">**了解更多**选择为优惠适用于您：</span><span class="sxs-lookup"><span data-stu-id="b336e-185">Choose **Learn More** for the offer that applies to you:</span></span> 
    
  - <span data-ttu-id="b336e-186">**Exchange Online 和 Skype for Business:****Exchange 的客户参数**版上，选择**了解更多**。</span><span class="sxs-lookup"><span data-stu-id="b336e-186">**Exchange Online and Skype for Business:** Choose **Learn More** on the **Customer Key for Exchange** offer.</span></span> 
    
  - <span data-ttu-id="b336e-187">**SharePoint Online 和 OneDrive for Business:** 在**SharePoint 和 OneDrive for Business 的客户参数**版上，选择**了解更多**。</span><span class="sxs-lookup"><span data-stu-id="b336e-187">**SharePoint Online and OneDrive for Business:** Chose **Learn More** on the **Customer Key for SharePoint and OneDrive for Business** offer.</span></span> 
    
5. <span data-ttu-id="b336e-188">在**提供详细信息**页上，选择**创建申请**。</span><span class="sxs-lookup"><span data-stu-id="b336e-188">On the **Offer details** page, choose **Create Request**.</span></span>
    
6. <span data-ttu-id="b336e-p116">填写所有适用的详细信息和费窗体上的请求的信息。应特别注意您要对您的选择为哪些官员贵组织的授权批准永久和不可逆转地销毁加密密钥和数据。完成窗体后，选择**提交**。</span><span class="sxs-lookup"><span data-stu-id="b336e-p116">Fill out all applicable details and requested information on the offer form. Pay particular attention to your selections for which officers of your organization you want to authorize to approve the permanent and irreversible destruction of encryption keys and data. Once you've completed the form, choose **Submit**.</span></span>
    
    <span data-ttu-id="b336e-192">此过程可能需要最多五个工作日后 Microsoft 已经被通知您的请求。</span><span class="sxs-lookup"><span data-stu-id="b336e-192">This process can take up to five business days once Microsoft has been notified of your request.</span></span>
    
7. <span data-ttu-id="b336e-193">继续执行下面的强制性的保留期部分。</span><span class="sxs-lookup"><span data-stu-id="b336e-193">Continue on to the mandatory retention period section below.</span></span>
    
### <a name="register-azure-subscriptions-to-use-a-mandatory-retention-period"></a><span data-ttu-id="b336e-194">注册使用强制性的保留期的 Azure 订阅</span><span class="sxs-lookup"><span data-stu-id="b336e-194">Register Azure subscriptions to use a mandatory retention period</span></span>
<span data-ttu-id="b336e-195"><a name="RegisterSubsforMRP"> </a></span><span class="sxs-lookup"><span data-stu-id="b336e-195"></span></span>

<span data-ttu-id="b336e-p117">根加密密钥的临时或永久丢失可以非常中断或甚至灾难性服务操作，并会导致数据丢失。因此，与客户参数一起使用的资源要求强保护。与客户参数一起使用的所有 Azure 资源提供了保护机制超出默认配置。可以标记或以一种将阻止即时和不可撤消取消注册 azure 订阅。这称为为强制性的保留期注册。必需的保留期注册 Azure 订阅所需的步骤需要与 Office 365 团队协作。此过程可能需要介于 1 到 5 个工作日。以前，这是有时称为"不取消"。</span><span class="sxs-lookup"><span data-stu-id="b336e-p117">The temporary or permanent loss of root encryption keys can be very disruptive or even catastrophic to service operation and can result in data loss. For this reason, the resources used with Customer Key require strong protection. All the Azure resources that are used with Customer Key offer protection mechanisms beyond the default configuration. Azure subscriptions can be tagged or registered in a way that will prevent immediate and irrevocable cancellation. This is referred to as registering for a mandatory retention period. The steps required to register Azure subscriptions for a mandatory retention period require collaboration with the Office 365 team. This process can take from one to five business days. Previously, this was sometimes referred to as "Do Not Cancel".</span></span>
  
<span data-ttu-id="b336e-204">与 Office 365 团队联系之前, 必须为每个 Azure 订阅与客户参数一起使用来执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="b336e-204">Before contacting the Office 365 team, you must perform the following steps for each Azure subscription that you use with Customer Key:</span></span>
  
1. <span data-ttu-id="b336e-p118">登录到您使用 Azure PowerShell 的 Azure 订阅。有关说明，请参阅[使用 Azure PowerShell 登录](https://docs.microsoft.com/powershell/azure/authenticate-azureps?view=azurermps-4.3.1)。</span><span class="sxs-lookup"><span data-stu-id="b336e-p118">Log in to your Azure subscription with Azure PowerShell. For instructions, see [Log in with Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps?view=azurermps-4.3.1).</span></span>
    
2. <span data-ttu-id="b336e-207">运行注册 AzureRmProviderFeature cmdlet 以注册您的订阅用于强制性的保留期。</span><span class="sxs-lookup"><span data-stu-id="b336e-207">Run the Register-AzureRmProviderFeature cmdlet to register your subscriptions to use a mandatory retention period.</span></span>
    
  ```
  Register-AzureRmProviderFeature -FeatureName mandatoryRetentionPeriodEnabled -ProviderNamespace Microsoft.Resources
  ```

3. <span data-ttu-id="b336e-p119">与 Microsoft 联系以具有已完成的过程。有关 SharePoint 和 OneDrive for Business 团队，请联系[spock@microsoft.com](mailto:spock@microsoft.com)。有关 Exchange Online 和 for Business 的 Skype，联系人[exock@microsoft.com](mailto:exock@microsoft.com)。服务级别协议 (SLA) 用于完成此过程的前 5 个工作日后 Microsoft 已通知 （并验证） 的已注册您的订阅用于强制性的保留期。您的电子邮件中包括以下内容：</span><span class="sxs-lookup"><span data-stu-id="b336e-p119">Contact Microsoft to have the process finalized. For the SharePoint and OneDrive for Business team, contact [spock@microsoft.com](mailto:spock@microsoft.com). For Exchange Online and Skype for Business, contact [exock@microsoft.com](mailto:exock@microsoft.com). The Service Level Agreement (SLA) for completion of this process is five business days once Microsoft has been notified (and verified) that you have registered your subscriptions to use a mandatory retention period. Include the following in your email:</span></span>
    
    <span data-ttu-id="b336e-213">**主题**： 为客户参数\<*租户的完全限定的域名*\></span><span class="sxs-lookup"><span data-stu-id="b336e-213">**Subject**: Customer Key for \<*Your tenant's fully-qualified domain name*\></span></span> 
    
    <span data-ttu-id="b336e-214">**正文**： 您希望其具有期间已完成强制保留的订阅 Id。</span><span class="sxs-lookup"><span data-stu-id="b336e-214">**Body**: Subscription IDs for which you want to have the mandatory retention period finalized.</span></span> 
    
4. <span data-ttu-id="b336e-215">一旦您收到来自 Microsoft 注册已完成的通知，通过运行 Get AzureRmProviderFeature cmdlet，如下所示验证您注册的状态：</span><span class="sxs-lookup"><span data-stu-id="b336e-215">Once you receive notification from Microsoft that registration is complete, verify the status of your registration by running the Get-AzureRmProviderFeature cmdlet as follows:</span></span>
    
  ```
  Get-AzureRmProviderFeature -ProviderNamespace Microsoft.Resources -FeatureName mandatoryRetentionPeriodEnabled
  ```

5. <span data-ttu-id="b336e-216">确认后从 Get AzureRmProviderFeature cmdlet**注册 State**属性返回的值为**已注册**，运行以下命令以完成该过程：</span><span class="sxs-lookup"><span data-stu-id="b336e-216">After verifying that the **Registration State** property from the Get-AzureRmProviderFeature cmdlet returns a value of **Registered**, run the following command to complete the process:</span></span>
    
  ```
  Register-AzureRmResourceProvider -ProviderNamespace "Microsoft.KeyVault"
  ```

### <a name="create-a-premium-azure-key-vault-in-each-subscription"></a><span data-ttu-id="b336e-217">在每个订阅中创建 Azure 键仓库 premium</span><span class="sxs-lookup"><span data-stu-id="b336e-217">Create a premium Azure Key Vault in each subscription</span></span>
<span data-ttu-id="b336e-218"><a name="CreateKeyVault"> </a></span><span class="sxs-lookup"><span data-stu-id="b336e-218"></span></span>

<span data-ttu-id="b336e-219">要创建密钥的存储库的步骤均编档在[Getting Started with Azure 键存储库](https://azure.microsoft.com/documentation/articles/key-vault-get-started/)，它将引导您安装和启动 Azure PowerShell、 连接到您的 Azure 订阅、 创建资源组，并创建中的关键电子仓库资源组。</span><span class="sxs-lookup"><span data-stu-id="b336e-219">The steps to create a key vault are documented in [Getting Started with Azure Key Vault](https://azure.microsoft.com/documentation/articles/key-vault-get-started/), which guides you through installing and launching Azure PowerShell, connecting to your Azure subscription, creating a resource group, and creating a key vault in that resource group.</span></span>
  
<span data-ttu-id="b336e-p120">当您创建一个关键电子仓库时，您必须选择 SKU： 标准或者 Premium。标准 SKU 允许 Azure 键仓库键术 シ モ メ 软件-没有硬件安全模块 (HSM) 密钥保护-并 Premium SKU 允许 Hsm 用于保护密钥仓库键。客户参数接受使用任一 SKU、 的关键电子仓库，但 Microsoft 强烈建议您使用只有 Premium SKU。具有任一类型的项的操作的成本是相同的因此成本中唯一的区别是每月的每个 HSM 保护密钥的成本。有关详细信息，请参阅[键仓库定价](https://azure.microsoft.com/pricing/details/key-vault/)。</span><span class="sxs-lookup"><span data-stu-id="b336e-p120">When you create a key vault, you must choose a SKU: either Standard or Premium. The Standard SKU allows Azure Key Vault keys to be protected with software - there is no Hardware Security Module (HSM) key protection - and the Premium SKU allows the use of HSMs for protection of Key Vault keys. Customer Key accepts key vaults that use either SKU, though Microsoft strongly recommends that you use only the Premium SKU. The cost of operations with keys of either type is the same, so the only difference in cost is the cost per month for each HSM-protected key. See [Key Vault pricing](https://azure.microsoft.com/pricing/details/key-vault/) for details.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="b336e-225">用于生产数据的高级版 SKU 关键电子仓库和 HSM 保护键和仅用于测试和验证使用标准 SKU 关键电子仓库和键。</span><span class="sxs-lookup"><span data-stu-id="b336e-225">Use the Premium SKU key vaults and HSM-protected keys for production data, and only use Standard SKU key vaults and keys for testing and validation purposes.</span></span> 
  
<span data-ttu-id="b336e-p121">为与每个 Office 365 服务将使用客户参数，每个您创建的两个 Azure 订阅中创建关键存储库。例如，为 Exchange Online 和 Skype 业务仅或 SharePoint Online 的 OneDrive for Business 仅，您将创建只有一个对存储库。启用 Exchange Online 和 SharePoint Online 客户参数，您将创建两个关键电子仓库对。</span><span class="sxs-lookup"><span data-stu-id="b336e-p121">For each Office 365 service with which you will use Customer Key, create a key vault in each of the two Azure subscriptions that you created. For example, for Exchange Online and Skype for Business only or SharePoint Online and OneDrive for Business only, you will create only one pair of vaults. To enable Customer Key for both Exchange Online and SharePoint Online, you will create two pairs of key vaults.</span></span>
  
<span data-ttu-id="b336e-p122">使用反映将与其关联电子仓库 DEP 的预期的用途的关键电子仓库的命名约定。请参阅下面的命名约定建议的最佳实践部分。</span><span class="sxs-lookup"><span data-stu-id="b336e-p122">Use a naming convention for key vaults that reflects the intended use of the DEP with which you will associate the vaults. See the Best Practices section below for naming convention recommendations.</span></span>
  
<span data-ttu-id="b336e-p123">创建一套单独、 配对的每个数据加密策略电子仓库。Exchange Online 的数据加密策略的作用域是由您时选择将策略分配到邮箱。邮箱可以具有只能有一个策略分配，并且您可以创建最多为 50 个策略。SharePoint online 的范围是策略的所有地理位置或地理位置中组织内的数据。</span><span class="sxs-lookup"><span data-stu-id="b336e-p123">Create a separate, paired set of vaults for each data encryption policy. For Exchange Online, the scope of a data encryption policy is chosen by you when you assign the policy to mailbox. A mailbox can have only one policy assigned, and you can create up to fifty policies. For SharePoint Online the scope of a policy is all of the data within an organization in a geographic location, or geo.</span></span>
  
<span data-ttu-id="b336e-p124">关键电子仓库创建还需要创建 Azure 资源组，因为关键电子仓库需要存储容量 （尽管非常小） 和密钥仓库日志记录，如果启用，还会生成存储的数据。最佳做法是 Microsoft 建议使用单独的管理员管理每个资源组，与右边缘与一组将管理所有相关的客户关键资源的管理员管理。</span><span class="sxs-lookup"><span data-stu-id="b336e-p124">The creation of key vaults also requires the creation of Azure resource groups, since key vaults need storage capacity (though very small) and Key Vault logging, if enabled, also generates stored data. As a best practice Microsoft recommends using separate administrators to manage each resource group, with the administration aligned with the set of administrators that will manage all related Customer Key resources.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="b336e-p125">要最大化可用性，您关键电子仓库应为 Office 365 服务附近的区域。例如，在北美 Exchange Online 组织时，将您关键电子仓库放在北美。如果在欧洲 Exchange Online 组织，置于欧洲关键存储库。</span><span class="sxs-lookup"><span data-stu-id="b336e-p125">To maximize availability, your key vaults should be in regions close to your Office 365 service. For example, if your Exchange Online organization is in North America, place your key vaults in North America. If your Exchange Online organization is in Europe, place your key vaults in Europe.</span></span><br/><span data-ttu-id="b336e-p126">用于关键电子仓库，公共前缀，包含使用缩写和关键仓库和键的范围 (例如，用于电子仓库将位于北美的名称可能对 Contoso SharePoint 服务 Contoso O365SP NA VaultA1 和Contoso-O365SP-NA-VaultA2。存储库名称是 Azure 中的全局唯一字符串，因此可能需要已经由其他 Azure 客户占用了所需的名称的情况下尝试变体的程序所需的名称。从年 7 月 2017年仓库名称不能更改，因此最佳做法是已安装的编写的计划和另一个人用于验证正确执行计划。</span><span class="sxs-lookup"><span data-stu-id="b336e-p126">Use a common prefix for key vaults, and include an abbreviation of the use and scope of the key vault and keys (e.g., for the Contoso SharePoint service where the vaults will be located in North America, a possible pair of names is Contoso-O365SP-NA-VaultA1 and Contoso-O365SP-NA-VaultA2. Vault names are globally unique strings within Azure, so you may need to try variations of your desired names in case the desired names are already claimed by other Azure customers. As of July 2017 vault names cannot be changed, so a best practice is to have a written plan for setup and use a second person to verify the plan is executed correctly.</span></span><br/><span data-ttu-id="b336e-p127">如果可能，在非配对区域中创建存储库。配对 Azure 区域跨服务故障域提供高可用性。因此，可以将区域对看作彼此的备份的区域。这意味着放在一个区域的 Azure 资源自动获得通过配对区域的容错能力。因此，选择两个电子仓库其中区域是仅两个区域的可用性总共正在使用的配对的意味着 DEP 中使用的区域。多数地区仅具有两个区域，因此尚未可以选择非配对区域。如果可能，请选择用于部署的两个电子仓库的两个非配对地区这会受益总共四个区域的可用性。有关详细信息，请参阅[业务连续性和灾难恢复 (BCDR): Azure 配对区域](https://docs.microsoft.com/azure/best-practices-availability-paired-regions)区域对的当前列表。</span><span class="sxs-lookup"><span data-stu-id="b336e-p127">If possible, create your vaults in non-paired regions. Paired Azure regions provide high availability across service failure domains. Therefore, regional pairs can be thought of as each other's backup region. This means that an Azure resource that is placed in one region is automatically gaining fault tolerance through the paired region. For this reason, choosing regions for two vaults used in a DEP where the regions are paired means that only a total of two regions of availability are in use. Most geographies only have two regions, so it's not yet possible to select non-paired regions. If possible, choose two non-paired regions for the two vaults used with a DEP. This benefits from a total of four regions of availability. For more information, see [Business continuity and disaster recovery (BCDR): Azure Paired Regions](https://docs.microsoft.com/azure/best-practices-availability-paired-regions) for a current list of regional pairs.</span></span> 
  
### <a name="assign-permissions-to-each-key-vault"></a><span data-ttu-id="b336e-252">将权限分配给每个主要的存储库</span><span class="sxs-lookup"><span data-stu-id="b336e-252">Assign permissions to each key vault</span></span>
<span data-ttu-id="b336e-253"><a name="KeyVaultPerms"> </a></span><span class="sxs-lookup"><span data-stu-id="b336e-253"></span></span>

<span data-ttu-id="b336e-p128">每个关键电子仓库，需要定义三个单独的客户键，具体取决于您的实现的权限集。例如，需要定义一组的每个以下权限：</span><span class="sxs-lookup"><span data-stu-id="b336e-p128">For each key vault, you will need to define three separate sets of permissions for Customer Key, depending on your implementation. For example, you will need to define one set of permissions for each of the following:</span></span>
  
- <span data-ttu-id="b336e-p129">将为您的组织中执行日常管理的关键存储库的**密钥仓库管理员**。这些任务包括备份、 创建、 获取、 导入列表，并还原。</span><span class="sxs-lookup"><span data-stu-id="b336e-p129">**Key vault administrators** that will perform day-to-day management of your key vault for your organization. These tasks include backup, create, get, import, list, and restore.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="b336e-p130">一组权限分配给键仓库管理员不包括删除项的权限。这是有意以及重要实践。删除加密密钥不通常，因为执行操作，以便永久性销毁数据。最佳做法是，不要授予此权限关键仓库管理员默认情况下。而是保留此键仓库参与者和仅理解的后果清楚地了解后将其分配给短期基础上的管理员。</span><span class="sxs-lookup"><span data-stu-id="b336e-p130">The set of permissions assigned to key vault administrators does not include the permission to delete keys. This is intentional and an important practice. Deleting encryption keys is not typically done, since doing so permanently destroys data. As a best practice, do not grant this permission to key vault administrators by default. Instead, reserve this for key vault contributors and only assign it to an administrator on a short term basis once a clear understanding of the consequences is understood.</span></span> 
  
    <span data-ttu-id="b336e-p131">若要将这些权限分配给您的 Office 365 组织中的用户，登录到您使用 Azure PowerShell 的 Azure 订阅。有关说明，请参阅[使用 Azure PowerShell 登录](https://docs.microsoft.com/powershell/azure/authenticate-azureps?view=azurermps-4.3.1)。</span><span class="sxs-lookup"><span data-stu-id="b336e-p131">To assign these permissions to a user in your Office 365 organization, log in to your Azure subscription with Azure PowerShell. For instructions, see [Log in with Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps?view=azurermps-4.3.1).</span></span>
    
- <span data-ttu-id="b336e-265">运行设置 AzureRmKeyVaultAccessPolicy cmdlet 分配所需的权限。</span><span class="sxs-lookup"><span data-stu-id="b336e-265">Run the Set-AzureRmKeyVaultAccessPolicy cmdlet to assign the necessary permissions.</span></span>
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName <vaultname> 
  -UserPrincipalName <UPN of user> -PermissionsToKeys create,import,list,get,backup,restore
  ```

  <span data-ttu-id="b336e-266">例如：</span><span class="sxs-lookup"><span data-stu-id="b336e-266">For example:</span></span>
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
  -UserPrincipalName alice@contoso.com -PermissionsToKeys create,import,list,get,backup,restore
  ```

- <span data-ttu-id="b336e-p132">可以更改权限 Azure 键存储库本身的**密钥仓库参与者**。您需要更改这些权限，如员工离开或加入您的团队，或在极少的情况下，该密钥保险存储管理员合法需删除或还原项的权限。这套关键仓库参与者需要被授予您密钥的存储库上的**参与者**角色。您可以通过使用 Azure 资源管理器中分配此角色。详细步骤，请参阅[Use Role-Based 访问控制，来管理 Azure 订阅资源的访问权限](https://docs.microsoft.com/azure/active-directory/role-based-access-control-configure)。创建订阅的管理员访问此隐式，以及其他管理员分配参与者角色的功能。</span><span class="sxs-lookup"><span data-stu-id="b336e-p132">**Key vault contributors** that can change permissions on the Azure Key Vault itself. You'll need to change these permissions as employees leave or join your team, or in the extremely rare situation that the key vault administrators legitimately need permission to delete or restore a key. This set of key vault contributors needs to be granted the **Contributor** role on your key vault. You can assign this role by using Azure Resource Manager. For detailed steps, see [Use Role-Based Access Control to manage access to your Azure subscription resources](https://docs.microsoft.com/azure/active-directory/role-based-access-control-configure). The administrator who creates a subscription has this access implicitly, as well as the ability to assign other administrators to the Contributor role.</span></span>
    
- <span data-ttu-id="b336e-p133">如果您打算使用 Exchange Online 和 Skype 客户键用于业务，您需要向 Office 365 for Business 使用代表 Exchange Online 和 Skype 的关键电子仓库授予权限。同样，如果您想要使用客户参数 SharePoint Online 和 OneDrive for Business，您需要为 Office 365 使用的关键电子仓库，代表 SharePoint Online 和 OneDrive for Business 添加权限。若要向 Office 365 授予权限，运行**设置 AzureRmKeyVaultAccessPolicy** cmdlet 使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="b336e-p133">If you intend to use Customer Key with Exchange Online and Skype for Business, you need to give permission to Office 365 to use the key vault on behalf of Exchange Online and Skype for Business. Likewise, if you intend to use Customer Key with SharePoint Online and OneDrive for Business, you need to add permission for the Office 365 to use the key vault on behalf of SharePoint Online and OneDrive for Business. To give permission to Office 365, run the **Set-AzureRmKeyVaultAccessPolicy** cmdlet using the following syntax:</span></span> 
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName <vaultname> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
  ```

    <span data-ttu-id="b336e-276">其中：</span><span class="sxs-lookup"><span data-stu-id="b336e-276">Where:</span></span>
    
  - <span data-ttu-id="b336e-277">*vaultname*是您创建的关键电子仓库的名称。</span><span class="sxs-lookup"><span data-stu-id="b336e-277">*vaultname* is the name of the key vault you created.</span></span> 
    
  - <span data-ttu-id="b336e-278">有关 Exchange Online 和 for Business 的 Skype，替换与*Office 365 appID*`00000002-0000-0ff1-ce00-000000000000`</span><span class="sxs-lookup"><span data-stu-id="b336e-278">For Exchange Online and Skype for Business, replace  *Office 365 appID* with `00000002-0000-0ff1-ce00-000000000000`</span></span>
    
  - <span data-ttu-id="b336e-279">有关 SharePoint Online 和 OneDrive for Business，替换与*Office 365 appID*`00000003-0000-0ff1-ce00-000000000000`</span><span class="sxs-lookup"><span data-stu-id="b336e-279">For SharePoint Online and OneDrive for Business, replace  *Office 365 appID* with `00000003-0000-0ff1-ce00-000000000000`</span></span>
    
  <span data-ttu-id="b336e-280">示例： 设置 Exchange Online 和 Skype for Business 的权限：</span><span class="sxs-lookup"><span data-stu-id="b336e-280">Example: Setting permissions for Exchange Online and Skype for Business:</span></span>
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
  -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
  ```

  <span data-ttu-id="b336e-281">示例： 设置 SharePoint Online 和 OneDrive for Business 的权限</span><span class="sxs-lookup"><span data-stu-id="b336e-281">Example: Setting permissions for SharePoint Online and OneDrive for Business</span></span>
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1 
  -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000003-0000-0ff1-ce00-000000000000
  ```

### <a name="enable-and-then-confirm-soft-delete-on-your-key-vaults"></a><span data-ttu-id="b336e-282">启用，然后确认软删除的主要存储库</span><span class="sxs-lookup"><span data-stu-id="b336e-282">Enable and then confirm soft delete on your key vaults</span></span>
<span data-ttu-id="b336e-283"><a name="SoftDelete"> </a></span><span class="sxs-lookup"><span data-stu-id="b336e-283"></span></span>

<span data-ttu-id="b336e-p134">当您可以快速恢复您的密钥时，您是不太可能会遇到意外或恶意删除的项由于扩展的服务中断。您需要启用此配置中，称为软删除之前可用于您的密钥客户参数。启用软删除允许您删除的 90 天内恢复键或电子仓库，而无需从备份中还原。</span><span class="sxs-lookup"><span data-stu-id="b336e-p134">When you can quickly recover your keys, you are less likely to experience an extended service outage due to accidentally or maliciously deleted keys. You need to enable this configuration, referred to as Soft Delete, before you can use your keys with Customer Key. Enabling Soft Delete allows you to recover keys or vaults within 90 days of deletion without having to restore them from backup.</span></span>
  
<span data-ttu-id="b336e-287">若要启用关键存储库上的软删除，完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="b336e-287">To enable Soft Delete on your key vaults, complete these steps:</span></span>
  
1. <span data-ttu-id="b336e-p135">登录到您使用 Windows Powershell 的 Azure 订阅。有关说明，请参阅[使用 Azure PowerShell 登录](https://docs.microsoft.com/powershell/azure/authenticate-azureps)。</span><span class="sxs-lookup"><span data-stu-id="b336e-p135">Log in to your Azure subscription with Windows Powershell. For instructions, see [Log in with Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).</span></span>
    
2. <span data-ttu-id="b336e-p136">运行[Get AzureRmKeyVault](https://docs.microsoft.com/powershell/module/azurerm.keyvault/get-azurermkeyvault) cmdlet。本示例中， *vaultname*是要为其启用软删除该密钥存储库的名称：</span><span class="sxs-lookup"><span data-stu-id="b336e-p136">Run the [Get-AzureRmKeyVault](https://docs.microsoft.com/powershell/module/azurerm.keyvault/get-azurermkeyvault) cmdlet. In this example, *vaultname* is the name of the key vault for which you are enabling soft delete:</span></span> 
    
   ```
   $v = Get-AzureRmKeyVault -VaultName <vaultname>
   $r = Get-AzureRmResource -ResourceId $v.ResourceId
   $r.Properties | Add-Member -MemberType NoteProperty -Name enableSoftDelete -Value 'True'
   Set-AzureRmResource -ResourceId $r.ResourceId -Properties $r.Properties
   ``` 
    
3. <span data-ttu-id="b336e-p137">确认软删除配置为关键仓库通过运行**Get AzureRmKeyVault** cmdlet。如果关键电子仓库，软删除的配置是否正确，然后软删除启用？属性返回值为**True**:</span><span class="sxs-lookup"><span data-stu-id="b336e-p137">Confirm soft delete is configured for the key vault by running the **Get-AzureRmKeyVault** cmdlet. If soft delete is configured properly for the key vault, then the  Soft Delete Enabled? property returns a value of **True**:</span></span> 
    
   ```
   Get-AzureRmKeyVault -VaultName <vaultname> | fl
   ```

   
    
### <a name="add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key"></a><span data-ttu-id="b336e-294">将项添加到每个关键电子仓库可以通过创建或导入密钥</span><span class="sxs-lookup"><span data-stu-id="b336e-294">Add a key to each key vault either by creating or importing a key</span></span>
<span data-ttu-id="b336e-295"><a name="AddKeystoKeyVault"> </a></span><span class="sxs-lookup"><span data-stu-id="b336e-295"></span></span>

<span data-ttu-id="b336e-p138">有两种方法将项添加到 Azure 键仓库;您可以直接在项存储库中创建项或可以导入一个键。直接在项存储库中创建项时的复杂程度低方法，导入密钥提供总控制如何生成密钥。</span><span class="sxs-lookup"><span data-stu-id="b336e-p138">There are two ways to add keys to an Azure Key Vault; you can create a key directly in Key Vault, or you can import a key. Creating a key directly in Key Vault is the less complicated method, while importing a key provides total control over how the key is generated.</span></span>
  
<span data-ttu-id="b336e-298">直接在您密钥的存储库中创建一个密钥，请运行[添加 AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Add-AzureKeyVaultKey) cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="b336e-298">To create a key directly in your key vault, run the [Add-AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Add-AzureKeyVaultKey) cmdlet as follows:</span></span> 
  
```
Add-AzureKeyVaultKey -VaultName <vaultname> -Name <keyname> -Destination <HSM|Software> -KeyOps wrapKey,unwrapKey
```

<span data-ttu-id="b336e-299">其中：</span><span class="sxs-lookup"><span data-stu-id="b336e-299">Where:</span></span>
  
-  <span data-ttu-id="b336e-300">*vaultname*是您要在其中创建项关键存储库的名称。</span><span class="sxs-lookup"><span data-stu-id="b336e-300">*vaultname*  is the name of the key vault in which you want to create the key.</span></span> 
    
-  <span data-ttu-id="b336e-301">*键名*是要为新的密钥的名称。</span><span class="sxs-lookup"><span data-stu-id="b336e-301">*keyname*  is the name you want to give the new key.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="b336e-p139">使用类似的命名约定，如上述关键电子仓库名称键。这种方式，在显示仅键名的工具，该字符串自我描述。</span><span class="sxs-lookup"><span data-stu-id="b336e-p139">Name keys using a similar naming convention as described above for key vaults. This way, in tools that show only the key name, the string is self-describing.</span></span> 
  
- <span data-ttu-id="b336e-304">如果您打算使用 HSM 保护密钥，确保，否则，为_目标_参数的值指定**HSM**指定**软件**。</span><span class="sxs-lookup"><span data-stu-id="b336e-304">If you intend to protect the key with an HSM, ensure that you specify **HSM** as the value of the  _Destination_ parameter, otherwise, specify **Software**.</span></span>
    
<span data-ttu-id="b336e-305">例如，</span><span class="sxs-lookup"><span data-stu-id="b336e-305">For example,</span></span>
  
```
Add-AzureKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination Software -KeyOps wrapKey,unwrapKey
```

<span data-ttu-id="b336e-306">直接在您密钥的存储库导入密钥，您需要具有 Thales nShield 硬件安全模块。</span><span class="sxs-lookup"><span data-stu-id="b336e-306">To import a key directly into your key vault, you need to have a Thales nShield Hardware Security Module.</span></span>
  
<span data-ttu-id="b336e-307">某些组织希望此方法建立的其键，并且此 provenance 方法还提供以下各项：</span><span class="sxs-lookup"><span data-stu-id="b336e-307">Some organizations prefer this approach to establish the provenance of their keys, and the this method also provides the following:</span></span>
  
- <span data-ttu-id="b336e-308">用于导入工具集包括从 Thales 用于加密的密钥，生成密钥 Exchange 键 (KEK) 不是可导出的审计和内已由 Thales 生产正版 HSM 生成。</span><span class="sxs-lookup"><span data-stu-id="b336e-308">The toolset used for import includes attestation from Thales that the Key Exchange Key (KEK) that is used to encrypt the key you generate is not exportable and is generated inside a genuine HSM that was manufactured by Thales.</span></span>
    
- <span data-ttu-id="b336e-p140">工具集包括从 Thales 上由 Thales 生产正版 HSM 还生成 Azure 键仓库安全领域的审计。此审计向您证明 Microsoft 也使用正版 Thales 硬件。</span><span class="sxs-lookup"><span data-stu-id="b336e-p140">The toolset includes attestation from Thales that the Azure Key Vault security world was also generated on a genuine HSM manufactured by Thales. This attestation proves to you that Microsoft is also using genuine Thales hardware.</span></span>
    
<span data-ttu-id="b336e-p141">请与您的安全组，以确定是否需要进行上述 attestations。若要创建键，在部署并将其导入您的主要存储库的详细步骤，请参阅[如何生成和传输 Azure 键电子仓库 HSM 保护密钥](https://azure.microsoft.com/documentation/articles/key-vault-hsm-protected-keys/)。使用 Azure 说明在每个主要的存储库中创建一个键。</span><span class="sxs-lookup"><span data-stu-id="b336e-p141">Check with your security group to determine if the above attestations are required. For detailed steps to create a key on-premises and import it into your key vault, see [How to generate and transfer HSM-protected keys for Azure Key Vault](https://azure.microsoft.com/documentation/articles/key-vault-hsm-protected-keys/). Use the Azure instructions to create a key in each key vault.</span></span>
  
### <a name="check-the-recovery-level-of-your-keys"></a><span data-ttu-id="b336e-314">检查您的密钥的恢复级别</span><span class="sxs-lookup"><span data-stu-id="b336e-314">Check the recovery level of your keys</span></span>
<span data-ttu-id="b336e-315"><a name="CheckKeyRecoveryLevel"> </a></span><span class="sxs-lookup"><span data-stu-id="b336e-315"></span></span>

<span data-ttu-id="b336e-p142">Office 365 需要 Azure 键存储库订阅被设置为不取消和所使用的客户参数项已启用的软删除。您可以通过查看您的密钥上恢复级别进行确认。</span><span class="sxs-lookup"><span data-stu-id="b336e-p142">Office 365 requires that the Azure Key Vault subscription is set to Do Not Cancel and that the keys used by Customer Key have soft delete enabled. You can confirm this by looking at the recovery level on your keys.</span></span>
  
<span data-ttu-id="b336e-318">若要检查恢复级别的某个键，在 Azure PowerShell 中，运行 Get AzureKeyVaultKey cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="b336e-318">To check the recovery level of a key, in Azure PowerShell, run the Get-AzureKeyVaultKey cmdlet as follows:</span></span>
  
```
(Get-AzureKeyVaultKey -VaultName <vaultname> -Name <keyname>).Attributes 
```

<span data-ttu-id="b336e-319">如果_恢复级别_属性返回的值为**恢复 + ProtectedSubscription**之外的任何内容，您将需要查看以下主题，并确保您已按照所有订阅置于不取消列表的步骤和是否已在每个关键存储库上启用的软删除。</span><span class="sxs-lookup"><span data-stu-id="b336e-319">If the  _Recovery Level_ property returns anything other than a value of **Recoverable+ProtectedSubscription**, you will need to review this topic and ensure that you have followed all of the steps to put the subscription on the Do Not Cancel list and that you have soft delete enabled on each of your key vaults.</span></span>
  
### <a name="backup-azure-key-vault"></a><span data-ttu-id="b336e-320">备份 Azure 存储库</span><span class="sxs-lookup"><span data-stu-id="b336e-320">Backup Azure Key Vault</span></span>
<span data-ttu-id="b336e-321"><a name="BackupAzureKeyVaultkeys"> </a></span><span class="sxs-lookup"><span data-stu-id="b336e-321"></span></span>

<span data-ttu-id="b336e-p143">紧跟创建或任何更改到某个键，执行备份，并将存储的联机和脱机的备份副本。脱机副本应不连接到任何网络，如在物理安全或商业存储设备上。应将在发生灾难时可访问的位置中存储的备份的至少一个副本。备份 blob 应键仓库键永久性销毁或否则呈现一直还原密钥材料的唯一方法。键的外部到 Azure 键仓库和已导入到 Azure 键仓库未限定为备份由于客户参数使用密钥所需的元数据不存在具有外部键。仅备份 Azure 键存储库中可具有客户键用于还原操作。因此，很重要的 Azure 键仓库备份进行后上载或创建密钥。</span><span class="sxs-lookup"><span data-stu-id="b336e-p143">Immediately following creation or any change to a key, perform a backup and store copies of the backup, both online and offline. Offline copies should not be connected to any network, such as in a physical safe or commercial storage facility. At least one copy of the backup should be stored in a location that will be accessible in the event of a disaster. The backup blobs are the sole means of restoring key material should a Key Vault key be permanently destroyed or otherwise rendered inoperable. Keys that are external to Azure Key Vault and were imported to Azure Key Vault do not qualify as a backup because the metadata necessary for Customer Key to use the key does not exist with the external key. Only a backup taken from Azure Key Vault can be used for restore operations with Customer Key. Therefore, it is essential that a backup of Azure Key Vault be made once a key is uploaded or created.</span></span>
  
<span data-ttu-id="b336e-329">若要创建的 Azure 键仓库密钥备份，请运行[备份 AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Backup-AzureKeyVaultKey) cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="b336e-329">To create a backup of an Azure Key Vault key, run the [Backup-AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Backup-AzureKeyVaultKey) cmdlet as follows:</span></span>
```
Backup-AzureKeyVaultKey -VaultName <vaultname> -Name <keyname> 
-OutputFile <filename .backup>

```

<span data-ttu-id="b336e-330">确保您的输出文件使用后缀`.backup`。</span><span class="sxs-lookup"><span data-stu-id="b336e-330">Ensure that your output file uses the suffix  `.backup`.</span></span>
  
<span data-ttu-id="b336e-p144">此 cmdlet 生成的输出文件进行加密和不能使用 Azure 键仓库之外。可以仅与 Azure 订阅从中备份中还原备份。</span><span class="sxs-lookup"><span data-stu-id="b336e-p144">The output file resulting from this cmdlet is encrypted and cannot be used outside of Azure Key Vault. The backup can be restored only to the Azure subscription from which the backup was taken.</span></span>
  
> [!TIP]
> <span data-ttu-id="b336e-p145">对于输出文件中，选择您的电子仓库名称和键名的组合。这将使文件名称自我描述。它还可以确保备份文件名称不执行发生冲突。</span><span class="sxs-lookup"><span data-stu-id="b336e-p145">For the output file, choose a combination of your vault name and key name. This will make the file name self-describing. It will also ensure that backup file names do not collide.</span></span> 
  
<span data-ttu-id="b336e-336">例如：</span><span class="sxs-lookup"><span data-stu-id="b336e-336">For example:</span></span>
  
```
Backup-AzureKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -OutputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

### <a name="validate-azure-key-vault-configuration-settings"></a><span data-ttu-id="b336e-337">验证 Azure 键仓库配置设置</span><span class="sxs-lookup"><span data-stu-id="b336e-337">Validate Azure Key Vault configuration settings</span></span>
<span data-ttu-id="b336e-338"><a name="Validateconfiguration"> </a></span><span class="sxs-lookup"><span data-stu-id="b336e-338"></span></span>

<span data-ttu-id="b336e-p146">执行在 DEP 中使用键之前验证是可选的但强烈建议您部署。特别是，如果您使用步骤设置键和电子仓库本主题中描述的之外，您应验证 Azure 键仓库资源的运行状况之前配置客户参数。</span><span class="sxs-lookup"><span data-stu-id="b336e-p146">Performing validation before using keys in a DEP is optional, but highly recommended. In particular, if you use steps to set up your keys and vaults other than the ones described in this topic, you should validate the health of your Azure Key Vault resources before you configure Customer Key.</span></span>
  
<span data-ttu-id="b336e-341">若要验证您的密钥已启用的 get wrapKey，以及 unwrapKey 操作：</span><span class="sxs-lookup"><span data-stu-id="b336e-341">To verify that your keys have get, wrapKey, and unwrapKey operations enabled:</span></span>
  
<span data-ttu-id="b336e-342">运行[Get AzureRmKeyVault](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Get-AzureRmKeyVault) cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="b336e-342">Run the [Get-AzureRmKeyVault](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Get-AzureRmKeyVault) cmdlet as follows:</span></span> 
  
```
Get-AzureRMKeyVault -VaultName <vaultname>
```

<span data-ttu-id="b336e-p147">在输出中，根据需要查找访问策略和 Exchange Online 的标识 (GUID) 或 SharePoint Online 的标识 (GUID)。向键，必须在权限下显示所有这三个以上的权限。</span><span class="sxs-lookup"><span data-stu-id="b336e-p147">In the output, look for the Access Policy and for the Exchange Online identity (GUID) or the SharePoint Online identity (GUID) as appropriate. All three of the above permissions must be shown under Permissions to Keys.</span></span>
  
<span data-ttu-id="b336e-345">如果访问策略配置不正确，请运行设置 AzureRmKeyVaultAccessPolicy cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="b336e-345">If the access policy configuration is incorrect, run the Set-AzureRmKeyVaultAccessPolicy cmdlet as follows:</span></span>
  
```
Set-AzureRmKeyVaultAccessPolicy -VaultName <vaultname> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
```

<span data-ttu-id="b336e-346">例如，对于 Exchange Online 和 Skype for Business:</span><span class="sxs-lookup"><span data-stu-id="b336e-346">For example, for Exchange Online and Skype for Business:</span></span>
  
```
Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
```

<span data-ttu-id="b336e-347">例如，对于 SharePoint Online 和 OneDrive for Business:</span><span class="sxs-lookup"><span data-stu-id="b336e-347">For example, for SharePoint Online and OneDrive for Business:</span></span>
  
```
Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1 
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName TBD
```

<span data-ttu-id="b336e-348">若要验证您运行[Get AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Get-AzureKeyVaultKey) cmdlet，如下所示的密钥的未设置到期日期：</span><span class="sxs-lookup"><span data-stu-id="b336e-348">To verify that an expiration date is not set for your keys run the [Get-AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Get-AzureKeyVaultKey) cmdlet as follows:</span></span> 
  
```
Get-AzureKeyVaultKey -VaultName <vaultname> 
```

<span data-ttu-id="b336e-p148">过期的项不能由客户参数并尝试与过期键的操作将失败，并可能导致服务中断。我们强烈建议键用于客户参数没有到期日期。到期日期后设置，无法删除，但可以更改到不同的日期。如果必须使用密钥已设置的过期日期，更改为 12/31/9999 到期值。到期日期设置为日期以外 12/31/9999 将不能通过 Office 365 验证键。</span><span class="sxs-lookup"><span data-stu-id="b336e-p148">An expired key cannot be used by Customer Key and operations attempted with an expired key will fail, and possibly result in a service outage. We strongly recommend that keys used with Customer Key do not have an expiration date. An expiration date, once set, cannot be removed, but can be changed to a different date. If a key must be used that has an expiration date set, change the expiration value to 12/31/9999. Keys with an expiration date set to a date other than 12/31/9999 will not pass Office 365 validation.</span></span>
  
<span data-ttu-id="b336e-354">若要更改已设置为 12/31/9999 之外的任何值的到期日期，请运行[设置 AzureKeyVaultKeyAttribute](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Set-AzureKeyVaultKeyAttribute) cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="b336e-354">To change an expiration date that has been set to any value other than 12/31/9999, run the [Set-AzureKeyVaultKeyAttribute](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Set-AzureKeyVaultKeyAttribute) cmdlet as follows:</span></span> 
  
```
Set-AzureKeyVaultKeyAttribute -VaultName <vaultname> -Name <keyname> 
-Expires (Get-Date -Date "12/31/9999")
```

> [!CAUTION]
> <span data-ttu-id="b336e-355">不能在与客户参数一起使用的加密密钥设置到期日期。</span><span class="sxs-lookup"><span data-stu-id="b336e-355">Don't set expiration dates on encryption keys you use with Customer Key.</span></span> 
  
### <a name="obtain-the-uri-for-each-azure-key-vault-key"></a><span data-ttu-id="b336e-356">获取每个 Azure 键仓库键的 URI</span><span class="sxs-lookup"><span data-stu-id="b336e-356">Obtain the URI for each Azure Key Vault key</span></span>
<span data-ttu-id="b336e-357"><a name="GetKeyURI"> </a></span><span class="sxs-lookup"><span data-stu-id="b336e-357"></span></span>

<span data-ttu-id="b336e-p149">一旦您具有完成 Azure 设置键存储库中的所有步骤，并添加您的密钥，运行以下命令以获取 URI 的每个主要的存储库中的键。您将需要使用以下 Uri 时创建并分配每个 DEP 更高版本，因此将此信息保存在安全的地方。记住要运行此命令一次的每个主要的存储库。</span><span class="sxs-lookup"><span data-stu-id="b336e-p149">Once you have completed all the steps in Azure to set up your key vaults and added your keys, run the following command to get the URI for the key in each key vault. You will need to use these URIs when you create and assign each DEP later, so save this information in a safe place. Remember to run this command once for each key vault.</span></span>
  
<span data-ttu-id="b336e-361">在 Azure PowerShell 中：</span><span class="sxs-lookup"><span data-stu-id="b336e-361">In Azure PowerShell:</span></span>
  
```
(Get-AzureKeyVaultKey -VaultName <vaultname>).Id
```

## <a name="office-365-setting-up-customer-key-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="b336e-362">Office 365： 为 Exchange Online 和 Skype for Business 设置客户参数</span><span class="sxs-lookup"><span data-stu-id="b336e-362">Office 365: Setting up Customer Key for Exchange Online and Skype for Business</span></span>
<span data-ttu-id="b336e-363"><a name="AzureSteps"> </a></span><span class="sxs-lookup"><span data-stu-id="b336e-363"></span></span>

<span data-ttu-id="b336e-p150">在开始之前，确保您已完成的任务，需要设置 Azure 键存储库。信息，请参阅[在 Azure 键仓库和客户键的 Microsoft FastTrack 完成任务](controlling-your-data-using-customer-key.md#AzureSteps)。</span><span class="sxs-lookup"><span data-stu-id="b336e-p150">Before you begin, ensure that you have completed the tasks required to set up Azure Key Vault. See [Complete tasks in Azure Key Vault and Microsoft FastTrack for Customer Key](controlling-your-data-using-customer-key.md#AzureSteps) for information.</span></span> 
  
<span data-ttu-id="b336e-366">若要为 Exchange Online 和 Skype for Business 设置客户参数，您需要通过远程连接到 Exchange Online 使用 Windows PowerShell 执行这些步骤。</span><span class="sxs-lookup"><span data-stu-id="b336e-366">To set up Customer Key for Exchange Online and Skype for Business, you will need to perform these steps by remotely connecting to Exchange Online with Windows PowerShell.</span></span>
  
### <a name="create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business"></a><span data-ttu-id="b336e-367">创建用于 Exchange Online 和 Skype 的业务数据加密策略 (DEP)</span><span class="sxs-lookup"><span data-stu-id="b336e-367">Create a data encryption policy (DEP) for use with Exchange Online and Skype for Business</span></span>
<span data-ttu-id="b336e-368"><a name="CreateDEP4EXOSkype"> </a></span><span class="sxs-lookup"><span data-stu-id="b336e-368"></span></span>

<span data-ttu-id="b336e-p151">DEP 是与 Azure 键存储库中存储的键集相关联。Office 365 中的邮箱中分配 DEP。Office 365 将使用该策略中标识的键进行加密邮箱。若要创建 DEP，您需要之前获得的密钥仓库 Uri。有关说明，请参阅[获取每个 Azure 键仓库键的 URI](controlling-your-data-using-customer-key.md#GetKeyURI) 。</span><span class="sxs-lookup"><span data-stu-id="b336e-p151">A DEP is associated with a set of keys stored in Azure Key Vault. You assign a DEP to a mailbox in Office 365. Office 365 will then use the keys identified in the policy to encrypt the mailbox. To create the DEP, you need the Key Vault URIs you obtained earlier. See [Obtain the URI for each Azure Key Vault key](controlling-your-data-using-customer-key.md#GetKeyURI) for instructions.</span></span> 
  
<span data-ttu-id="b336e-p152">请记住 ！创建 DEP 时，您可以指定驻留在两个不同的 Azure 键电子仓库的两个键。确保这些注册表项位于两个单独的 Azure 区域以确保地理位置冗余。</span><span class="sxs-lookup"><span data-stu-id="b336e-p152">Remember! When you create a DEP, you specify two keys that reside in two different Azure Key Vaults. Ensure that these keys are located in two separate Azure regions to ensure geo-redundancy.</span></span>
  
<span data-ttu-id="b336e-377">若要创建 DEP，请按照下列步骤：</span><span class="sxs-lookup"><span data-stu-id="b336e-377">To create the DEP, follow these steps:</span></span>
  
1. <span data-ttu-id="b336e-378">在本地计算机上使用工作或学校帐户已[连接到 Exchange Online PowerShell 中](https://technet.microsoft.com/en-us/library/jj984289%28v=exchg.160%29.aspx)打开 Windows PowerShell 并运行以下命令在 Office 365 组织中的全局管理员权限。</span><span class="sxs-lookup"><span data-stu-id="b336e-378">On your local computer, using a work or school account that has global administrator permissions in your Office 365 organization, [connect to Exchange Online PowerShell](https://technet.microsoft.com/en-us/library/jj984289%28v=exchg.160%29.aspx) by opening Windows PowerShell and running the following command.</span></span> 
    
   ```
   $UserCredential = Get-Credential
   ```

2. <span data-ttu-id="b336e-379">Windows PowerShell 凭据请求对话框中，输入您的工作或学校帐户信息，再单击**确定**，，然后输入以下命令。</span><span class="sxs-lookup"><span data-stu-id="b336e-379">In the Windows PowerShell Credential Request dialog box, enter your work or school account information, click **OK**, and then enter the following command.</span></span> 
    
   ```
   $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
   ```

3. <span data-ttu-id="b336e-380">运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="b336e-380">Run the following command.</span></span>
    
   ```
   Import-PSSession $Session
   ```

4. <span data-ttu-id="b336e-381">若要创建 DEP，通过键入以下命令使用新建 DataEncryptionPolicy cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b336e-381">To create a DEP, use the New-DataEncryptionPolicy cmdlet by typing the following command.</span></span>
    
   ```
   New-DataEncryptionPolicy -Name <PolicyName> -Description "PolicyDescription " -AzureKeyIDs <KeyVaultURI1>, <KeyVaultURI2>
   ```

   <span data-ttu-id="b336e-382">其中：</span><span class="sxs-lookup"><span data-stu-id="b336e-382">Where:</span></span>
    
   -  <span data-ttu-id="b336e-p153">*PolicyName*是想要使用的策略的名称。名称不能包含空格。例如，USA_mailboxes。</span><span class="sxs-lookup"><span data-stu-id="b336e-p153">*PolicyName*  is the name you want to use for the policy. Names cannot contain spaces. For example, USA_mailboxes.</span></span> 
    
   -  <span data-ttu-id="b336e-p154">*使用 PolicyDescription*是策略的将有助于您记住策略的用途的用户友好说明。在说明，可以包含空格。例如，根 USA 和其区域中的邮箱的键。</span><span class="sxs-lookup"><span data-stu-id="b336e-p154">*PolicyDescription*  is a user friendly description of the policy that will help you remember what the policy is for. You can include spaces in the description. For example, Root key for mailboxes in USA and its territories.</span></span> 
    
   -  <span data-ttu-id="b336e-p155">*KeyVaultURI1*是策略中的第一个键的 URI。例如， https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01。</span><span class="sxs-lookup"><span data-stu-id="b336e-p155">*KeyVaultURI1*  is the URI for the first key in the policy. For example, https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01.</span></span> 
    
   -  <span data-ttu-id="b336e-p156">*KeyVaultURI2*是策略中的第二个键的 URI。例如， https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02。分隔逗号和空格的两个 Uri。</span><span class="sxs-lookup"><span data-stu-id="b336e-p156">*KeyVaultURI2*  is the URI for the second key in the policy. For example, https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02. Separate the two URIs by a comma and a space.</span></span> 
    
   <span data-ttu-id="b336e-394">示例：</span><span class="sxs-lookup"><span data-stu-id="b336e-394">Example:</span></span>
  
   ```
   New-DataEncryptionPolicy -Name USA_mailboxes -Description "Root key for mailboxes in USA and its territories" -AzureKeyIDs https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01, https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02
   ```

### <a name="assign-a-dep-to-a-mailbox"></a><span data-ttu-id="b336e-395">分配邮箱的 DEP</span><span class="sxs-lookup"><span data-stu-id="b336e-395">Assign a DEP to a mailbox</span></span>
<span data-ttu-id="b336e-396"><a name="assignDEPtomailbox"> </a></span><span class="sxs-lookup"><span data-stu-id="b336e-396"></span></span>

<span data-ttu-id="b336e-p157">使用 Set-mailbox cmdlet 分配邮箱 DEP。Office 365 后分配策略时，可以使用部署中指定密钥加密邮箱</span><span class="sxs-lookup"><span data-stu-id="b336e-p157">Assign the DEP to a mailbox by using the Set-Mailbox cmdlet. Once you assign the policy, Office 365 can encrypt the mailbox with the key designated in the DEP.</span></span>
  
```
Set-Mailbox -Identity <MailboxIdParameter> -DataEncryptionPolicy <PolicyName>
```

<span data-ttu-id="b336e-p158">其中*MailboxIdParameter*指定邮箱。有关 Set-mailbox cmdlet 的详细信息，请参阅[Set-mailbox](https://technet.microsoft.com/library/bb123981%28v=exchg.160%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="b336e-p158">Where *MailboxIdParameter* specifies a mailbox. For more information about the Set-Mailbox cmdlet, see [Set-Mailbox](https://technet.microsoft.com/library/bb123981%28v=exchg.160%29.aspx).</span></span>
  
### <a name="validate-mailbox-encryption"></a><span data-ttu-id="b336e-401">验证邮箱加密</span><span class="sxs-lookup"><span data-stu-id="b336e-401">Validate mailbox encryption</span></span>
<span data-ttu-id="b336e-402"><a name="validatemailboxencryption"> </a></span><span class="sxs-lookup"><span data-stu-id="b336e-402"></span></span>

<span data-ttu-id="b336e-p159">加密邮箱可能需要一些时间。第一个时间策略分配，邮箱也必须完成移动到另一个数据库中的，该服务可以加密邮箱之前。我们建议您等待 72 小时尝试后更改 DEP 或第一次您对邮箱分配 DEP 验证加密之前。</span><span class="sxs-lookup"><span data-stu-id="b336e-p159">Encrypting a mailbox can take some time. For first time policy assignment, the mailbox must also complete the move from one database to another before the service can encrypt the mailbox. We recommend that you wait 72 hours before you attempt to validate encryption after you change a DEP or the first time you assign a DEP to a mailbox.</span></span>
  
<span data-ttu-id="b336e-406">使用 Get-mailboxstatistics cmdlet 可确定是否加密邮箱。</span><span class="sxs-lookup"><span data-stu-id="b336e-406">Use the Get-MailboxStatistics cmdlet to determine if a mailbox is encrypted.</span></span>
  
```
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

<span data-ttu-id="b336e-407">如果该邮箱未加密，进行加密属性返回值为**true**如果加密邮箱和值为**false** 。</span><span class="sxs-lookup"><span data-stu-id="b336e-407">The IsEncrypted property returns a value of **true** if the mailbox is encrypted and a value of **false** if the mailbox is not encrypted.</span></span> 

<span data-ttu-id="b336e-p160">若要完成邮箱移动的时间取决于为邮箱的大小或向其分配的第一次，DEP 的邮箱数。如果邮箱已经不加密指派 DEP 的时间从每周后，使用 New-moverequest cmdlet 启动的未加密的邮箱的邮箱移动。</span><span class="sxs-lookup"><span data-stu-id="b336e-p160">The time to complete mailbox moves depends on the number of mailboxes to which you assign a DEP for the first time, as well as the size of the mailboxes. If the mailboxes have not been encrypted after a week from the time you assigned the DEP, initiate a mailbox move for the unencrypted mailboxes by using the New-MoveRequest cmdlet.</span></span>

```
New-MoveRequest <mailbox alias>
``` 

## <a name="office-365-setting-up-customer-key-for-sharepoint-online-and-onedrive-for-business"></a><span data-ttu-id="b336e-410">Office 365： 为 SharePoint Online 和 OneDrive for Business 设置客户参数</span><span class="sxs-lookup"><span data-stu-id="b336e-410">Office 365: Setting up Customer Key for SharePoint Online and OneDrive for Business</span></span>
<span data-ttu-id="b336e-411"><a name="AzureSteps"> </a></span><span class="sxs-lookup"><span data-stu-id="b336e-411"></span></span>

<span data-ttu-id="b336e-p161">在开始之前，确保您已完成的任务，需要设置 Azure 键存储库。信息，请参阅[在 Azure 键仓库和客户键的 Microsoft FastTrack 完成任务](controlling-your-data-using-customer-key.md#AzureSteps)。</span><span class="sxs-lookup"><span data-stu-id="b336e-p161">Before you begin, ensure that you have completed the tasks required to set up Azure Key Vault. See [Complete tasks in Azure Key Vault and Microsoft FastTrack for Customer Key](controlling-your-data-using-customer-key.md#AzureSteps) for information.</span></span> 
  
<span data-ttu-id="b336e-414">若要为 SharePoint Online 和 OneDrive for Business 设置客户参数，您需要通过远程连接到 SharePoint Online 使用 Windows PowerShell 执行这些步骤。</span><span class="sxs-lookup"><span data-stu-id="b336e-414">To set up Customer Key for SharePoint Online and OneDrive for Business, you will need to perform these steps by remotely connecting to SharePoint Online with Windows PowerShell.</span></span>
  
### <a name="create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo"></a><span data-ttu-id="b336e-415">为业务地理位置的每个 SharePoint Online 和 OneDrive 创建数据加密策略 (DEP)</span><span class="sxs-lookup"><span data-stu-id="b336e-415">Create a data encryption policy (DEP) for each SharePoint Online and OneDrive for Business geo</span></span>
<span data-ttu-id="b336e-416"><a name="CreateDEP4SPOODfB"> </a></span><span class="sxs-lookup"><span data-stu-id="b336e-416"></span></span>

<span data-ttu-id="b336e-p162">DEP 是与 Azure 键存储库中存储的键集相关联。您将 DEP 应用于所有在一个地理位置，也称为地理位置数据。如果您使用 Office 365 的多地理位置功能 （当前在预览） 时，您可以创建一个 DEP 每地理位置。如果您没有使用多地理位置，可以使用 SharePoint Online 和 OneDrive for Business 的用于 Office 365 中创建一个 DEP。Office 365 将使用 DEP 中标识的项中的地理位置数据进行加密。若要创建 DEP，您需要之前获得的密钥仓库 Uri。有关说明，请参阅[获取每个 Azure 键仓库键的 URI](controlling-your-data-using-customer-key.md#GetKeyURI) 。</span><span class="sxs-lookup"><span data-stu-id="b336e-p162">A DEP is associated with a set of keys stored in Azure Key Vault. You apply a DEP to all of your data in one geographic location, also called a geo. If you use the multi-geo feature of Office 365 (currently in Preview), you can create one DEP per geo. If you are not using multi-geo, you can create one DEP in Office 365 for use with SharePoint Online and OneDrive for Business. Office 365 will then use the keys identified in the DEP to encrypt your data in that geo. To create the DEP, you need the Key Vault URIs you obtained earlier. See [Obtain the URI for each Azure Key Vault key](controlling-your-data-using-customer-key.md#GetKeyURI) for instructions.</span></span> 
  
<span data-ttu-id="b336e-p163">请记住 ！创建 DEP 时，您可以指定驻留在两个不同的 Azure 键电子仓库的两个键。确保这些注册表项位于两个单独的 Azure 区域以确保地理位置冗余。</span><span class="sxs-lookup"><span data-stu-id="b336e-p163">Remember! When you create a DEP, you specify two keys that reside in two different Azure Key Vaults. Ensure that these keys are located in two separate Azure regions to ensure geo-redundancy.</span></span>
  
<span data-ttu-id="b336e-427">若要创建 DEP，您需要远程使用 Windows PowerShell 连接到 SharePoint Online。</span><span class="sxs-lookup"><span data-stu-id="b336e-427">To create a DEP, you need to remotely connect to SharePoint Online by using Windows PowerShell.</span></span>
  
1. <span data-ttu-id="b336e-428">在本地计算机上使用工作或学校帐户已[连接到 SharePoint Online Powershell](https://technet.microsoft.com/library/fp161372.aspx)在 Office 365 组织中的全局管理员权限。</span><span class="sxs-lookup"><span data-stu-id="b336e-428">On your local computer, using a work or school account that has global administrator permissions in your Office 365 organization, [Connect to SharePoint Online Powershell](https://technet.microsoft.com/library/fp161372.aspx).</span></span>
    
2. <span data-ttu-id="b336e-429">Microsoft SharePoint Online Management Shell 中，运行[注册 SPODataEncryptionPolicy](https://technet.microsoft.com/library/mt843950.aspx) cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="b336e-429">In the Microsoft SharePoint Online Management Shell, run the [Register-SPODataEncryptionPolicy](https://technet.microsoft.com/library/mt843950.aspx) cmdlet as follows:</span></span> 
    
   ```
   Register-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl> -PrimaryKeyVaultName <PrimaryKeyVaultName> -PrimaryKeyName <PrimaryKeyName> -PrimaryKeyVersion <PrimaryKeyVersion> -SecondaryKeyVaultName <SecondaryKeyVaultName> -SecondaryKeyName <SecondaryKeyName> -SecondaryKeyVersion <SecondaryKeyVersion>
   ```

   <span data-ttu-id="b336e-p164">注册 DEP 时，加密在其上开始地理位置中的数据。这可能需要一些时间。</span><span class="sxs-lookup"><span data-stu-id="b336e-p164">When you register the DEP, encryption begins on the data in the geo. This can take some time.</span></span>
    
### <a name="validate-encryption-of-group-sites-team-sites-and-onedrive-for-business"></a><span data-ttu-id="b336e-432">验证组网站、 工作组网站和 OneDrive for Business 的加密</span><span class="sxs-lookup"><span data-stu-id="b336e-432">Validate encryption of Group Sites, Team Sites, and OneDrive for Business</span></span>
<span data-ttu-id="b336e-433"><a name="validateencryptionSPO"> </a></span><span class="sxs-lookup"><span data-stu-id="b336e-433"></span></span>

<span data-ttu-id="b336e-434">您可以通过运行 Get SPODataEncryptionPolicy cmdlet，如下所示检查加密的状态：</span><span class="sxs-lookup"><span data-stu-id="b336e-434">You can check on the status of encryption by running the Get-SPODataEncryptionPolicy cmdlet as follows:</span></span>
  
```
Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

<span data-ttu-id="b336e-435">此 cmdlet 的输出包括：</span><span class="sxs-lookup"><span data-stu-id="b336e-435">The output from this cmdlet includes:</span></span>
  
- <span data-ttu-id="b336e-436">主键的 URI。</span><span class="sxs-lookup"><span data-stu-id="b336e-436">The URI of the primary key.</span></span>
    
- <span data-ttu-id="b336e-437">第二项的 URI。</span><span class="sxs-lookup"><span data-stu-id="b336e-437">The URI of the secondary key.</span></span>
    
- <span data-ttu-id="b336e-p165">Geo 加密状态。状态可能包括：</span><span class="sxs-lookup"><span data-stu-id="b336e-p165">The encryption status for the geo. Possible states include:</span></span>
    
  - <span data-ttu-id="b336e-440">**未注册：** 尚未应用客户密钥加密。</span><span class="sxs-lookup"><span data-stu-id="b336e-440">**Unregistered:** Customer Key encryption has not yet been applied.</span></span> 
    
  - <span data-ttu-id="b336e-p166">**注册：** 已应用客户密钥加密和文件正在进行加密。如果您地理处于此状态，您将还上会显示信息的地理位置中的网站百分比已完成，以便您可以监视加密进度。</span><span class="sxs-lookup"><span data-stu-id="b336e-p166">**Registering:** Customer Key encryption has been applied and your files are in the process of being encrypted. If your geo is in this state, you'll also be shown information on what percentage of sites in the geo are complete so that you can monitor encryption progress.</span></span> 
    
  - <span data-ttu-id="b336e-443">**注册：** 已应用客户密钥加密，且已加密的所有网站中的所有文件。</span><span class="sxs-lookup"><span data-stu-id="b336e-443">**Registered:** Customer Key encryption has been applied, and all files in all sites have been encrypted.</span></span> 
    
  - <span data-ttu-id="b336e-p167">**推出：** 关键滚正在进行。如果您地理处于此状态，您将还上会显示信息站点的比例完成关键滚动操作，以便您可以监视进度。</span><span class="sxs-lookup"><span data-stu-id="b336e-p167">**Rolling:** A key roll is in progress. If your geo is in this state, you'll also be shown information on what percentage of sites have completed the key roll operation so that you can monitor progress.</span></span> 
    
## <a name="managing-customer-key-for-office-365"></a><span data-ttu-id="b336e-446">管理 Office 365 的客户密钥</span><span class="sxs-lookup"><span data-stu-id="b336e-446">Managing Customer Key for Office 365</span></span>
<span data-ttu-id="b336e-447"><a name="ManageCustomerKey"> </a></span><span class="sxs-lookup"><span data-stu-id="b336e-447"></span></span>

<span data-ttu-id="b336e-448">已设置 Office 365 客户参数后，您可以执行这些额外的管理任务。</span><span class="sxs-lookup"><span data-stu-id="b336e-448">After you've set up Customer Key for Office 365, you can perform these additional management tasks.</span></span>
  
- [<span data-ttu-id="b336e-449">还原 Azure 键仓库键</span><span class="sxs-lookup"><span data-stu-id="b336e-449">Restore Azure Key Vault keys</span></span>](controlling-your-data-using-customer-key.md#RestoreAzureKeyVaultKeys)
    
- [<span data-ttu-id="b336e-450">回滚或旋转中与客户参数一起使用的 Azure 键仓库的键</span><span class="sxs-lookup"><span data-stu-id="b336e-450">Rolling or rotating a key in Azure Key Vault that you use with Customer Key</span></span>](controlling-your-data-using-customer-key.md#RollCKkey)
    
- [<span data-ttu-id="b336e-451">管理密钥的存储库的权限</span><span class="sxs-lookup"><span data-stu-id="b336e-451">Manage key vault permissions</span></span>](controlling-your-data-using-customer-key.md#Managekeyvaultperms)
    
- [<span data-ttu-id="b336e-452">确定分配给某个邮箱 DEP</span><span class="sxs-lookup"><span data-stu-id="b336e-452">Determine the DEP assigned to a mailbox</span></span>](controlling-your-data-using-customer-key.md#DeterminemailboxDEP)
    
### <a name="restore-azure-key-vault-keys"></a><span data-ttu-id="b336e-453">还原 Azure 键仓库键</span><span class="sxs-lookup"><span data-stu-id="b336e-453">Restore Azure Key Vault keys</span></span>
<span data-ttu-id="b336e-454"><a name="RestoreAzureKeyVaultKeys"> </a></span><span class="sxs-lookup"><span data-stu-id="b336e-454"></span></span>

<span data-ttu-id="b336e-p168">在执行还原之前, 使用软删除由提供的恢复功能。与客户参数一起使用的所有项都是必需已启用的软删除。软删除相当于回收站中，通过达 90 天内无需还原恢复。只应在极端或特殊情况下，例如，丢失的键或键的存储库时所需还原。如果您必须使用客户密钥还原密钥，以用于在 Azure PowerShell 中，运行还原 AzureKeyVaultKey cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="b336e-p168">Before performing a restore, use the recovery capabilities provided by soft delete. All keys that are used with Customer Key are required to have soft delete enabled. Soft delete acts like a recycle bin and allows recovery for up to 90 days without the need to restore. Restore should only be required in extreme or unusual circumstances, for example if the key or key vault is lost. If you must restore a key for use with Customer Key, in Azure PowerShell, run the Restore-AzureKeyVaultKey cmdlet as follows:</span></span>
  
```
Restore-AzureKeyVaultKey -VaultName <vaultname> -InputFile <filename>
```

<span data-ttu-id="b336e-460">例如：</span><span class="sxs-lookup"><span data-stu-id="b336e-460">For example:</span></span>
  
```
Restore-AzureKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -InputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

<span data-ttu-id="b336e-p169">如果键存储库中已存在同名的键，还原操作将失败。还原 AzureKeyVaultKey 还原所有的主要版本和所有元数据，包括键名键。</span><span class="sxs-lookup"><span data-stu-id="b336e-p169">If a key with the same name already exists in the key vault, the restore operation will fail. Restore-AzureKeyVaultKey restores all key versions and all metadata for the key including the key name.</span></span>
  
### <a name="rolling-or-rotating-a-key-in-azure-key-vault-that-you-use-with-customer-key"></a><span data-ttu-id="b336e-463">回滚或旋转中与客户参数一起使用的 Azure 键仓库的键</span><span class="sxs-lookup"><span data-stu-id="b336e-463">Rolling or rotating a key in Azure Key Vault that you use with Customer Key</span></span>
<span data-ttu-id="b336e-464"><a name="RollCKkey"> </a></span><span class="sxs-lookup"><span data-stu-id="b336e-464"></span></span>

<span data-ttu-id="b336e-p170">回滚键则不需要按任一 Azure 键仓库或客户键。此外，シ シ 术 シ HSM 的项是几乎可能破坏。即使根密钥已拥有的恶意 actor 没有可行使用它来解密数据，因为仅 Office 365 代码知道如何使用它的方法。但是，推出键都支持客户参数。</span><span class="sxs-lookup"><span data-stu-id="b336e-p170">Rolling keys is not required by either Azure Key Vault or by Customer Key. In addition, keys that are protected with an HSM are virtually impossible to compromise. Even if a root key were in the possession of a malicious actor there is no feasible means of using it to decrypt data, since only Office 365 code knows how to use it. However, rolling a key is supported by Customer Key.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="b336e-p171">仅将鼠标移存在清除技术原因或合规性要求指示已进行回滚键时，与客户参数使用加密密钥。此外，不要删除任何键或与其关联的策略。如果将您的键，将提供内容加密与以前的密钥。例如，活动邮箱都将被重新加密频繁，处于非活动状态，而断开连接，并禁用邮箱可能仍加密与以前的密钥。SharePoint Online 执行备份的内容的还原和恢复目的，因此可能仍使用原来的密钥的存档的内容。</span><span class="sxs-lookup"><span data-stu-id="b336e-p171">Only roll an encryption key that you use with Customer Key when a clear technical reason exists or a compliance requirement dictates that you have to roll the key. In addition, do not delete any keys that are or were associated with policies. When you roll your keys, there will be content encrypted with the previous keys. For example, while active mailboxes will be re-encrypted frequently, inactive, disconnected, and disabled mailboxes may still be encrypted with the previous keys. SharePoint Online performs backup of content for restore and recovery purposes, so there may still be archived content using older keys. </span></span><br/> <span data-ttu-id="b336e-p172">若要确保您的数据的安全，SharePoint Online： 将允许不多个键滚动操作，正在进行的一次。如果您想要在密钥的存储库中的滚动这两个注册表项，您需要等待到第一个关键滚动操作完全完成。我们建议是在不同的时间间隔，错开关键滚动操作，以便不是问题。</span><span class="sxs-lookup"><span data-stu-id="b336e-p172">To ensure the safety of your data, SharePoint Online will allow no more than one Key Roll operation to be in progress at a time. If you want to roll both of the keys in a key vault, you'll need to wait for the first key roll operation to fully complete. Our recommendation is to stagger your key roll operations at different intervals, so that this is not an issue.</span></span> 
  
<span data-ttu-id="b336e-p173">如果将某个键，您正在请求现有密钥的新版本。以请求现有密钥的新版本，请使用相同，[添加 AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Add-AzureKeyVaultKey)，带有 cmdlet 相同的语法用于首先创建项。</span><span class="sxs-lookup"><span data-stu-id="b336e-p173">When you roll a key, you are requesting a new version of an existing key. In order to request a new version of an existing key, you use the same cmdlet, [Add-AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Add-AzureKeyVaultKey), with the same syntax that you used to create the key in the first place.</span></span>
  
<span data-ttu-id="b336e-479">例如：</span><span class="sxs-lookup"><span data-stu-id="b336e-479">For example:</span></span>
  
```
Add-AzureKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination HSM -KeyOps @('wrapKey','unwrapKey') -NotBefore (Get-Date -Date "12/27/2016 12:01 AM")
```

<span data-ttu-id="b336e-p174">本示例中，因为一个名为**Contoso-O365EX-NA-VaultA1-Key001**已项存在**Contoso O365EX NA VaultA1**存储库中的将创建一个新的主要版本。操作中添加一个新的主要版本。此操作，以便仍然可以解密之前使用该密钥加密的数据保留中的项的版本历史记录的早期主要版本。完成推出相关联 DEP 任意键后，您必须运行其他 cmdlet，以确保客户参数开始使用新密钥。</span><span class="sxs-lookup"><span data-stu-id="b336e-p174">In this example, since a key named **Contoso-O365EX-NA-VaultA1-Key001** already exists in the **Contoso-O365EX-NA-VaultA1** vault, a new key version will be created. The operation adds a new key version. This operation preserves the previous key versions in the key's version history, so that data previously encrypted with that key can still be decrypted. Once you have completed rolling any key that is associated with a DEP, you must then run an additional cmdlet to ensure Customer Key begins using the new key.</span></span> 
  
#### <a name="enable-exchange-online-and-skype-for-business-to-use-a-new-key-after-you-roll-or-rotate-keys-in-azure-key-vault"></a><span data-ttu-id="b336e-484">启用 Exchange Online 和 for Business 的 Skype 以使用新密钥后滚动或旋转 Azure 键存储库中的项</span><span class="sxs-lookup"><span data-stu-id="b336e-484">Enable Exchange Online and Skype for Business to use a new key after you roll or rotate keys in Azure Key Vault</span></span>

<span data-ttu-id="b336e-485">当您滚动任一 DEP 与关联的 Azure 键仓库键与 Exchange Online 和 Skype 用于业务，必须运行以下命令以更新 DEP 和启用 Office 365 开始使用新的密钥。</span><span class="sxs-lookup"><span data-stu-id="b336e-485">When you roll either of the Azure Key Vault keys associated with a DEP used with Exchange Online and Skype for Business, you must run the following command to update the DEP and enable Office 365 to start using the new key.</span></span>
  
<span data-ttu-id="b336e-486">若要指示客户参数使用新密钥来加密 Office 365 中的邮箱运行设置 DataEncryptionPolicy cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="b336e-486">To instruct Customer Key to use the new key to encrypt mailboxes in Office 365 run the Set-DataEncryptionPolicy cmdlet as follows:</span></span>
  
```
Set-DataEncryptionPolicy <policyname> -Refresh 
```

<span data-ttu-id="b336e-p175">48 小时内使用此策略加密的活动邮箱将成为与更新键关联。使用[Determine DEP 分配给某个邮箱](controlling-your-data-using-customer-key.md#DeterminemailboxDEP)中的步骤检查邮箱的 DataEncryptionPolicyID 属性的值。在应用更新的密钥后，将更改此属性的值。</span><span class="sxs-lookup"><span data-stu-id="b336e-p175">Within 48 hours, the active mailboxes encrypted using this policy will become associated with the updated key. Use the steps in [Determine the DEP assigned to a mailbox](controlling-your-data-using-customer-key.md#DeterminemailboxDEP) to check the value for the DataEncryptionPolicyID property for the mailbox. The value for this property will change once the updated key has been applied.</span></span> 
  
#### <a name="enable-sharepoint-online-and-onedrive-for-business-to-use-a-new-key-after-you-roll-or-rotate-keys-in-azure-key-vault"></a><span data-ttu-id="b336e-490">启用 SharePoint Online 和 OneDrive for Business 使用新密钥后滚动或旋转 Azure 键存储库中的项</span><span class="sxs-lookup"><span data-stu-id="b336e-490">Enable SharePoint Online and OneDrive for Business to use a new key after you roll or rotate keys in Azure Key Vault</span></span>

<span data-ttu-id="b336e-491">当您滚动任一 DEP 与关联的 Azure 键仓库键用于 SharePoint Online 和 OneDrive for Business，您必须运行[更新 SPODataEncryptionPolicy](https://technet.microsoft.com/library/mt843948.aspx) cmdlet 以更新 DEP 和启用 Office 365 开始使用新密钥。</span><span class="sxs-lookup"><span data-stu-id="b336e-491">When you roll either of the Azure Key Vault keys associated with a DEP used with SharePoint Online and OneDrive for Business, you must run the [Update-SPODataEncryptionPolicy](https://technet.microsoft.com/library/mt843948.aspx) cmdlet to update the DEP and enable Office 365 to start using the new key.</span></span> 
  
```
Update-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl> -KeyVaultName <ReplacementKeyVaultName> -KeyName <ReplacementKeyName> -KeyVersion <ReplacementKeyVersion> -KeyType <Primary | Secondary>
```

<span data-ttu-id="b336e-p176">这将启动 SharePoint Online 和 OneDrive for Business 的关键回滚操作。此操作不会立即。若要查看的密钥滚动操作的进度，请运行 Get SPODataEncryptionPolicy cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="b336e-p176">This will start the key roll operation for SharePoint Online and OneDrive for Business. This action is not immediate. To see the progress of the key roll operation, run the Get-SPODataEncryptionPolicy cmdlet as follows:</span></span>
  
```
Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

### <a name="manage-key-vault-permissions"></a><span data-ttu-id="b336e-495">管理密钥的存储库的权限</span><span class="sxs-lookup"><span data-stu-id="b336e-495">Manage key vault permissions</span></span>
<span data-ttu-id="b336e-496"><a name="Managekeyvaultperms"> </a></span><span class="sxs-lookup"><span data-stu-id="b336e-496"></span></span>

<span data-ttu-id="b336e-p177">有多个 cmdlet，可以查看和，如有必要，删除键仓库权限。您可能需要删除权限，例如，当员工离开团队。</span><span class="sxs-lookup"><span data-stu-id="b336e-p177">Several cmdlets are available that enable you to view and, if necessary, remove key vault permissions. You might need to remove permissions, for example, when an employee leaves the team.</span></span>
  
<span data-ttu-id="b336e-499">若要查看关键仓库权限，请运行 Get AzureRmKeyVault cmdlet:</span><span class="sxs-lookup"><span data-stu-id="b336e-499">To view key vault permissions, run the Get-AzureRmKeyVault cmdlet:</span></span>
  
```
Get-AzureRmKeyVault -VaultName <vaultname>
```

<span data-ttu-id="b336e-500">例如：</span><span class="sxs-lookup"><span data-stu-id="b336e-500">For example:</span></span>
  
```
Get-AzureRmKeyVault -VaultName Contoso-O365EX-NA-VaultA1
```

<span data-ttu-id="b336e-501">若要删除的管理员权限，请运行删除 AzureRmKeyVaultAccessPolicy cmdlet:</span><span class="sxs-lookup"><span data-stu-id="b336e-501">To remove an administrator's permissions, run the Remove-AzureRmKeyVaultAccessPolicy cmdlet:</span></span>
  
```
Remove-AzureRmKeyVaultAccessPolicy -VaultName <vaultname> 
-UserPrincipalName <UPN of user>
```

<span data-ttu-id="b336e-502">例如：</span><span class="sxs-lookup"><span data-stu-id="b336e-502">For example:</span></span>
  
```
Remove-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
-UserPrincipalName alice@contoso.com
```

### <a name="determine-the-dep-assigned-to-a-mailbox"></a><span data-ttu-id="b336e-503">确定分配给某个邮箱 DEP</span><span class="sxs-lookup"><span data-stu-id="b336e-503">Determine the DEP assigned to a mailbox</span></span>
<span data-ttu-id="b336e-504"><a name="DeterminemailboxDEP"> </a></span><span class="sxs-lookup"><span data-stu-id="b336e-504"></span></span>

<span data-ttu-id="b336e-p178">若要确定 DEP 分配给某个邮箱，请使用 Get-mailboxstatistics cmdlet。此 cmdlet 返回的唯一标识符 (GUID)。</span><span class="sxs-lookup"><span data-stu-id="b336e-p178">To determine the DEP assigned to a mailbox, use the Get-MailboxStatistics cmdlet. The cmdlet returns a unique identifier (GUID).</span></span>
  
```
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl DataEncryptionPolicyID
```

<span data-ttu-id="b336e-p179">其中*GeneralMailboxOrMailUserIdParameter*指定邮箱。有关 Get-mailboxstatistics cmdlet 的详细信息，请参阅[Get-mailboxstatistics](https://technet.microsoft.com/library/bb124612%28v=exchg.160%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="b336e-p179">Where *GeneralMailboxOrMailUserIdParameter* specifies a mailbox. For more information about the Get-MailboxStatistics cmdlet, see [Get-MailboxStatistics](https://technet.microsoft.com/library/bb124612%28v=exchg.160%29.aspx).</span></span>
  
<span data-ttu-id="b336e-509">使用 GUID 以找出通过运行以下 cmdlet，邮箱分配到 DEP 的友好名称。</span><span class="sxs-lookup"><span data-stu-id="b336e-509">Use the GUID to find out the friendly name of the DEP to which the mailbox is assigned by running the following cmdlet.</span></span>
  
```
Get-DataEncryptionPolicy <GUID>
```

<span data-ttu-id="b336e-510">其中*GUID*是使用 Get-mailboxstatistics cmdlet 在上一步返回的 GUID。</span><span class="sxs-lookup"><span data-stu-id="b336e-510">Where *GUID* is the GUID returned by the Get-MailboxStatistics cmdlet in the previous step.</span></span> 
  

