---
title: 创建 DLP 策略来保护具有 FCI 或其他属性的文档
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleContentPropertyContainsWords
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
description: 许多组织已拥有一个使用 Windows Server 文件分类基础结构 (FCI)、SharePoint 中的文档属性或由第三方系统应用的文档属性识别和分类敏感信息的流程。 如果您的组织就是这样，则可以在 Office 365 中创建一个 DLP 策略，来识别已由 Windows Server FCI 或其他系统应用到文档的属性，从而在带有特定 FCI 或其他属性值的 Office 文档上强制应用该 DLP 策略。
ms.openlocfilehash: d4468859781703012438a06ec782b75d1acce963
ms.sourcegitcommit: ed822a776d3419853453583e882f3c61ca26d4b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "30410527"
---
# <a name="create-a-dlp-policy-to-protect-documents-with-fci-or-other-properties"></a><span data-ttu-id="99ef3-104">创建 DLP 策略来保护具有 FCI 或其他属性的文档</span><span class="sxs-lookup"><span data-stu-id="99ef3-104">Create a DLP policy to protect documents with FCI or other properties</span></span>

<span data-ttu-id="99ef3-p102">在 Office 365 中，您可以使用数据丢失防护 (DLP) 策略来识别、监视和保护敏感信息。许多组织已拥有一个使用 Windows Server 文件分类基础结构 (FCI)、SharePoint 中的文档属性或由第三方系统应用的文档属性识别和分类敏感信息的流程。如果您的组织就是这样，则可以在 Office 365 中创建一个 DLP 策略，来识别已由 Windows Server FCI 或其他系统应用到文档的属性，从而在带有特定 FCI 或其他属性值的 Office 文档上强制应用该 DLP 策略。</span><span class="sxs-lookup"><span data-stu-id="99ef3-p102">In Office 365, you can use a data loss prevention (DLP) policy to identify, monitor, and protect sensitive information. Many organizations already have a process to identify and classify sensitive information by using the classification properties in Windows Server File Classification Infrastructure (FCI), the document properties in SharePoint, or the document properties applied by a third-party system. If this describes your organization, you can create a DLP policy in Office 365 that recognizes the properties that have been applied to documents by Windows Server FCI or other system, so that the DLP policy can be enforced on Office documents with specific FCI or other property values.</span></span>
  
![显示 Office 365 和外部分类系统的图表](media/59ad0ac1-4146-4919-abd1-c74d8508d25e.png)
  
<span data-ttu-id="99ef3-109">例如，您的组织可能会使用 Windows Server FCI 来识别包含个人身份信息 (PII) 的文档（如社会保险号），然后通过基于文档中找到的 PII 的类型和出现次数将“个人身份信息”\*\*\*\* 属性设置为“高”\*\*\*\*、“中等”\*\*\*\*、“低”\*\*\*\*、“公开”\*\*\*\* 或“非 PII”\*\*\*\* 来对文档进行分类。</span><span class="sxs-lookup"><span data-stu-id="99ef3-109">For example, your organization might use Windows Server FCI to identify documents with personally identifiable information (PII) such as social security numbers, and then classify the document by setting the **Personally Identifiable Information** property to **High**, **Moderate**, **Low**, **Public**, or **Not PII** based on the type and number of occurrences of PII found in the document.</span></span> <span data-ttu-id="99ef3-110">在 Office 365 中，您可以创建 DLP 策略，来标识将该属性设置为特定值（如“高”\*\*\*\* 和“中等”\*\*\*\*）的文档，然后对这些文件执行操作，如阻止访问。</span><span class="sxs-lookup"><span data-stu-id="99ef3-110">In Office 365, you can create a DLP policy that identifies documents that have that property set to specific values, such as **High** and **Medium**, and then takes an action such as blocking access to those files.</span></span> <span data-ttu-id="99ef3-111">如果将属性设置为“低”\*\*\*\*，则同一个策略可以使用其他规则来执行不同的操作，如发送电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="99ef3-111">The same policy can have another rule that takes a different action if the property is set to **Low**, such as sending an email notification.</span></span> <span data-ttu-id="99ef3-112">通过这种方式, Office 365 中的 DLP 与 windows server FCI 集成, 并可帮助保护从基于 Windows server 的文件服务器上传或共享到 office 365 的 office 文档。</span><span class="sxs-lookup"><span data-stu-id="99ef3-112">In this way, DLP in Office 365 integrates with Windows Server FCI and can help protect Office documents uploaded or shared to Office 365 from Windows Server-based file servers.</span></span>
  
<span data-ttu-id="99ef3-p104">DLP 策略只需查找特定的属性名称/值对。可以使用任何文档属性，只要该属性具有 SharePoint 搜索的相应托管属性。例如，SharePoint 网站集可能使用名为“行程报告”\*\*\*\* 的内容类型，包含名为“客户”\*\*\*\* 的必填字段。只要有人创建行程报告，就必须输入客户名称。此属性名称/值对还可在 DLP 策略中使用 — 例如，当“客户”\*\*\*\* 字段包含“Contoso”\*\*\*\* 时，您希望有一个规则可以阻止外部用户访问此文档。</span><span class="sxs-lookup"><span data-stu-id="99ef3-p104">A DLP policy simply looks for a specific property name/value pair. Any document property can be used, as long as the property has a corresponding managed property for SharePoint search. For example, a SharePoint site collection might use a content type named **Trip Report** with a required field named **Customer**. Whenever a person creates a trip report, they must enter the customer name. This property name/value pair can also be used in a DLP policy — for example, if you want a rule that blocks access to the document for external users when the **Customer** field contains **Contoso**.</span></span>
  
<span data-ttu-id="99ef3-118">请注意, 如果您想要将 DLP 策略应用于具有特定 Office 365 标签的内容, 则不应遵循此处的步骤。</span><span class="sxs-lookup"><span data-stu-id="99ef3-118">Note that if you want to apply your DLP policy to content with specific Office 365 labels, you should not follow the steps here.</span></span> <span data-ttu-id="99ef3-119">请改为了解如何将[标签用作 DLP 策略中的条件](data-loss-prevention-policies.md#using-a-label-as-a-condition-in-a-dlp-policy)。</span><span class="sxs-lookup"><span data-stu-id="99ef3-119">Instead, learn how to [Using a label as a condition in a DLP policy](data-loss-prevention-policies.md#using-a-label-as-a-condition-in-a-dlp-policy).</span></span>
  
## <a name="before-you-create-the-dlp-policy"></a><span data-ttu-id="99ef3-120">在创建 DLP 策略之前</span><span class="sxs-lookup"><span data-stu-id="99ef3-120">Before you create the DLP policy</span></span>

<span data-ttu-id="99ef3-121">您需要在 SharePoint 管理中心中创建托管属性，才能在 DLP 策略中使用 Windows Server FCI 属性或其他属性。</span><span class="sxs-lookup"><span data-stu-id="99ef3-121">Before you can use a Windows Server FCI property or other property in a DLP policy, you need to create a managed property in the SharePoint admin center.</span></span> <span data-ttu-id="99ef3-122">下面介绍了原因。</span><span class="sxs-lookup"><span data-stu-id="99ef3-122">Here's why.</span></span>
  
<span data-ttu-id="99ef3-p107">示例</span><span class="sxs-lookup"><span data-stu-id="99ef3-p107">In SharePoint Online and OneDrive for Business, the search index is built up by crawling the content on your sites. The crawler picks up content and metadata from the documents in the form of crawled properties. The search schema helps the crawler decide what content and metadata to pick up. Examples of metadata are the author and the title of a document. However, to get the content and metadata from the documents into the search index, the crawled properties must be mapped to managed properties. Only managed properties are kept in the index. For example, a crawled property related to author is mapped to a managed property related to author.</span></span>
  
<span data-ttu-id="99ef3-p108">这很重要，因为 Office 365 中的 DLP 使用搜索爬网程序来识别网站上的敏感信息，并对其进行分类，然后将该敏感信息存储在搜索索引的一个安全部分。当您将文档上载到 Office 365 时，SharePoint 会自动创建基于文档属性的已爬网属性。但是，要在 DLP 策略中使用 FCI 或其他属性，该已爬网属性需要映射到托管属性，以便将包含该属性的内容保留在索引中。</span><span class="sxs-lookup"><span data-stu-id="99ef3-p108">This is important because DLP in Office 365 uses the search crawler to identify and classify sensitive information on your sites, and then store that sensitive information in a secure portion of the search index. When you upload a document to Office 365, SharePoint automatically creates crawled properties based on the document properties. But to use an FCI or other property in a DLP policy, that crawled property needs to be mapped to a managed property so that content with that property is kept in the index.</span></span>
  
<span data-ttu-id="99ef3-133">有关搜索和托管属性的详细信息, 请参阅[在 SharePoint Online 中管理搜索架构](http://go.microsoft.com/fwlink/p/?LinkID=627454)。</span><span class="sxs-lookup"><span data-stu-id="99ef3-133">For more information on search and managed properties, see [Manage the search schema in SharePoint Online](http://go.microsoft.com/fwlink/p/?LinkID=627454).</span></span>
  
### <a name="step-1-upload-a-document-with-the-needed-property-to-office-365"></a><span data-ttu-id="99ef3-134">步骤 1：将包含所需属性的文档上载到 Office 365</span><span class="sxs-lookup"><span data-stu-id="99ef3-134">Step 1: Upload a document with the needed property to Office 365</span></span>

<span data-ttu-id="99ef3-135">首先需要上载包含要在您的 DLP 策略中引用的属性的文档。</span><span class="sxs-lookup"><span data-stu-id="99ef3-135">You first need to upload a document with the property that you want to reference in your DLP policy.</span></span> <span data-ttu-id="99ef3-136">Office 365 将检测此属性，并从该属性自动创建已爬网属性。</span><span class="sxs-lookup"><span data-stu-id="99ef3-136">Office 365 will detect the property and automatically create a crawled property from it.</span></span> <span data-ttu-id="99ef3-137">在下一步中, 您将创建托管属性, 然后将托管属性映射到此已爬网属性。</span><span class="sxs-lookup"><span data-stu-id="99ef3-137">In the next step, you'll create a managed property, and then map the managed property to this crawled property.</span></span>
  
### <a name="step-2-create-a-managed-property"></a><span data-ttu-id="99ef3-138">步骤 2：创建托管属性</span><span class="sxs-lookup"><span data-stu-id="99ef3-138">Step 2: Create a managed property</span></span>

1. <span data-ttu-id="99ef3-139">登录 Office 365 管理中心。</span><span class="sxs-lookup"><span data-stu-id="99ef3-139">Sign in to the Office 365 admin center.</span></span>
    
2. <span data-ttu-id="99ef3-140">在左侧导航中, 选择 "**管理中心** \> " " **SharePoint**"。</span><span class="sxs-lookup"><span data-stu-id="99ef3-140">In the left navigation, choose **Admin centers** \> **SharePoint**.</span></span> <span data-ttu-id="99ef3-141">You're now in the SharePoint admin center.</span><span class="sxs-lookup"><span data-stu-id="99ef3-141">You're now in the SharePoint admin center.</span></span>
    
3. <span data-ttu-id="99ef3-142">在左侧导航中, 选择 "**搜索管理**" 页\>上的 "**搜索** \> " "**管理搜索架构**"。</span><span class="sxs-lookup"><span data-stu-id="99ef3-142">In the left navigation, choose **search** \> on the **search administration** page \> **Manage Search Schema**.</span></span>
    
    ![SharePoint 管理中心内的搜索管理页面](media/6bcd3aec-d11a-4f8c-9987-8f35da14d80b.png)
  
4. <span data-ttu-id="99ef3-144">在 "**托管属性**" \>页上**新建托管属性**。</span><span class="sxs-lookup"><span data-stu-id="99ef3-144">On the **Managed Properties** page \> **New Managed Property**.</span></span>
    
    ![突出显示“新建托管属性”按钮的“托管属性”页面](media/b161c764-414c-4037-83ed-503a49fb4410.png)
  
5. <span data-ttu-id="99ef3-p111">输入属性的名称和说明。此名称将显示在您的 DLP 策略中。</span><span class="sxs-lookup"><span data-stu-id="99ef3-p111">Enter a name and description for the property. This name is what will appear in your DLP policies.</span></span>
    
6. <span data-ttu-id="99ef3-148">对于“类型”\*\*\*\*，选择“文本”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="99ef3-148">For **Type**, choose **Text**.</span></span> 
    
7. <span data-ttu-id="99ef3-149">在“主要特征”\*\*\*\* 下，选择“可查询”\*\*\*\* 和“可检索”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="99ef3-149">Under **Main characteristics**, select **Queryable** and **Retrievable**.</span></span>
    
8. <span data-ttu-id="99ef3-150">在 "到已\> **爬网属性的映射**" 下**添加映射**。</span><span class="sxs-lookup"><span data-stu-id="99ef3-150">Under **Mappings to crawled properties** \> **Add a mapping**.</span></span>
    
9. <span data-ttu-id="99ef3-151">在 "已**爬网属性选择**" 对话框中, \>查找并选择与将在 DLP 策略\> **"确定"** 中使用的 Windows Server FCI 属性或其他属性相对应的已爬网属性。</span><span class="sxs-lookup"><span data-stu-id="99ef3-151">In the **crawled property selection** dialog box \> find and select the crawled property that corresponds to the Windows Server FCI property or other property that you will use in your DLP policy \> **OK**.</span></span>
    
    ![已爬网属性选择对话框](media/aeda1dce-1342-48bf-9594-a8e4f230e8aa.png)
  
10. <span data-ttu-id="99ef3-153">在页面\>底部的 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="99ef3-153">At the bottom of the page \> **OK**.</span></span>
    
## <a name="create-a-dlp-policy-that-uses-an-fci-property-or-other-property"></a><span data-ttu-id="99ef3-154">创建使用 FCI 属性或其他属性的 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="99ef3-154">Create a DLP policy that uses an FCI property or other property</span></span>

<span data-ttu-id="99ef3-155">在此示例中, 组织在其基于 Windows Server 的文件服务器上使用 FCI;具体来说, 他们使用的是名为**个人身份信息**的 FCI 分类属性, 其可能\*\*\*\* 值为**高**、中、**低**、**公共**和**不是 PII**。</span><span class="sxs-lookup"><span data-stu-id="99ef3-155">In this example, an organization is using FCI on its Windows Server-based file servers; specifically, they're using the FCI classification property named **Personally Identifiable Information** with possible values of **High**, **Moderate**, **Low**, **Public**, and **Not PII**.</span></span> <span data-ttu-id="99ef3-156">现在他们想要在 Office 365 的 DLP 策略中利用其现有的 FCI 分类。</span><span class="sxs-lookup"><span data-stu-id="99ef3-156">Now they want to leverage their existing FCI classification in their DLP policies in Office 365.</span></span>
  
<span data-ttu-id="99ef3-157">首先，它们按照上述步骤在 SharePoint Online 中创建托管属性，该属性映射到从 FCI 属性自动创建的已爬网属性。</span><span class="sxs-lookup"><span data-stu-id="99ef3-157">First, they follow the steps above to create a managed property in SharePoint Online, which maps to the crawled property created automatically from the FCI property.</span></span>
  
<span data-ttu-id="99ef3-158">接下来, 他们创建一个 DLP 策略, 其中两个规则都使用条件**文档属性包含以下任一值**:</span><span class="sxs-lookup"><span data-stu-id="99ef3-158">Next, they create a DLP policy with two rules that both use the condition **Document properties contain any of these values**:</span></span>
  
- <span data-ttu-id="99ef3-159">**FCI PII 内容-高、中等**如果 FCI 分类属性的**个人可识别信息**等于**高**或**适中**, 并且与组织外部的人员共享文档, 则第一个规则将限制对文档的访问。</span><span class="sxs-lookup"><span data-stu-id="99ef3-159">**FCI PII content - High, Moderate** The first rule restricts access to the document if the FCI classification property **Personally Identifiable Information** equals **High** or **Moderate** and the document is shared with people outside the organization.</span></span> 
    
- <span data-ttu-id="99ef3-160">**FCI PII 内容-低**如果 FCI 分类属性的**个人可识别信息**等于**较低**, 并且与组织外部的人员共享文档, 则第二条规则会向文档所有者发送通知。</span><span class="sxs-lookup"><span data-stu-id="99ef3-160">**FCI PII content - Low** The second rule sends a notification to the document owner if the FCI classification property **Personally Identifiable Information** equals **Low** and the document is shared with people outside the organization.</span></span> 
    
### <a name="create-the-dlp-policy-by-using-powershell"></a><span data-ttu-id="99ef3-161">使用 PowerShell 创建 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="99ef3-161">Create the DLP policy by using PowerShell</span></span>

<span data-ttu-id="99ef3-162">请注意, 条件**文档属性包含这些值中的任何一个**暂时在安全&amp;合规性中心的 UI 中不可用, 但你仍可以使用 PowerShell 使用此条件。</span><span class="sxs-lookup"><span data-stu-id="99ef3-162">Note that the condition **Document properties contain any of these values** is temporarily not available in the UI of the Security &amp; Compliance Center, but you can still use this condition by using PowerShell.</span></span> <span data-ttu-id="99ef3-163">您`New\Set\Get-DlpCompliancePolicy`可以使用 cmdlet 来使用 DLP 策略, 并`New\Set\Get-DlpComplianceRule`将 cmdlet 与`ContentPropertyContainsWords`参数一起使用, 以添加条件**文档属性包含这些值中的任何一个**。</span><span class="sxs-lookup"><span data-stu-id="99ef3-163">You can use the  `New\Set\Get-DlpCompliancePolicy` cmdlets to work with a DLP policy, and use the  `New\Set\Get-DlpComplianceRule` cmdlets with the  `ContentPropertyContainsWords` parameter to add the condition **Document properties contain any of these values**.</span></span>
  
<span data-ttu-id="99ef3-164">有关这些 cmdlet 的详细信息, 请参阅[Office 365 &amp;安全合规中心 cmdlet](http://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409)。</span><span class="sxs-lookup"><span data-stu-id="99ef3-164">For more information on these cmdlets, see [Office 365 Security &amp; Compliance Center cmdlets](http://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409).</span></span>
  
1. [<span data-ttu-id="99ef3-165">使用远程 PowerShell 连接到 Office 365 安全与合规中心</span><span class="sxs-lookup"><span data-stu-id="99ef3-165">Connect to the Office 365 Security &amp; Compliance Center using remote PowerShell</span></span>](http://go.microsoft.com/fwlink/?LinkID=799771&amp;clcid=0x409)
    
2. <span data-ttu-id="99ef3-166">使用`New-DlpCompliancePolicy`创建策略。</span><span class="sxs-lookup"><span data-stu-id="99ef3-166">Create the policy by using  `New-DlpCompliancePolicy`.</span></span>
    
    <span data-ttu-id="99ef3-167">下面是 PowerShell 示例, 用于创建适用于所有位置的 DLP 策略。</span><span class="sxs-lookup"><span data-stu-id="99ef3-167">Here is a PowerShell example that creates a DLP policy that applies to all locations.</span></span>
    
      ```
      New-DlpCompliancePolicy -Name FCI_PII_policy -ExchangeLocation All -SharePointLocation All -OneDriveLocation All -Mode Enable
      ```

3. <span data-ttu-id="99ef3-168">通过`New-DlpComplianceRule`使用 (其中一个规则针对**低**值) 和另一个规则用于**高**和**中等**值, 创建上述两个规则。</span><span class="sxs-lookup"><span data-stu-id="99ef3-168">Create the two rules described above by using  `New-DlpComplianceRule`, where one rule is for the **Low** value, and another rule is for the **High** and **Moderate** values.</span></span> 
    
    <span data-ttu-id="99ef3-169">下面是创建这两个规则的 PowerShell 示例。</span><span class="sxs-lookup"><span data-stu-id="99ef3-169">Here is a PowerShell example that creates these two rules.</span></span> <span data-ttu-id="99ef3-170">请注意, 属性名称/值对括在引号中, 并且属性名称可以指定多个以逗号分隔的多个值, 不包含空格, 如`"<Property1>:<Value1>,<Value2>","<Property2>:<Value3>,<Value4>"....`</span><span class="sxs-lookup"><span data-stu-id="99ef3-170">Note that the property name/value pairs are enclosed in quotation marks, and a property name may specify multiple values separated by commas with no spaces, like  `"<Property1>:<Value1>,<Value2>","<Property2>:<Value3>,<Value4>"....`</span></span>
    
      ```
      New-DlpComplianceRule -Name FCI_PII_content-High,Moderate -Policy FCI_PII_policy -AccessScope NotInOrganization -BlockAccess $true -ContentPropertyContainsWords "Personally Identifiable Information:High,Moderate" -Disabled $falseNew-DlpComplianceRule -Name FCI_PII_content-Low -Policy FCI_PII_policy -AccessScope NotInOrganization -BlockAccess $false -ContentPropertyContainsWords "Personally Identifiable Information:Low" -Disabled $false -NotifyUser Owner
      ```

    <span data-ttu-id="99ef3-171">请注意, Windows Server FCI 包含许多内置属性, 包括本示例中使用的**个人身份信息**。</span><span class="sxs-lookup"><span data-stu-id="99ef3-171">Note that Windows Server FCI includes many built-in properties, including **Personally Identifiable Information** used in this example.</span></span> <span data-ttu-id="99ef3-172">每个组织的每个属性的可能值可能各不相同。</span><span class="sxs-lookup"><span data-stu-id="99ef3-172">The possible values for each property can be different for every organization.</span></span> <span data-ttu-id="99ef3-173">此处使用的 "**高**"、"**中等**" 和 "**低**" 值仅是一个示例。</span><span class="sxs-lookup"><span data-stu-id="99ef3-173">The **High**, **Moderate**, and **Low** values used here are only an example.</span></span> <span data-ttu-id="99ef3-174">对于您的组织, 您可以在基于 windows server 的文件服务器上的文件服务器资源管理器中查看 Windows Server FCI 分类属性及其可能的值。</span><span class="sxs-lookup"><span data-stu-id="99ef3-174">For your organization, you can view the Windows Server FCI classification properties with their possible values in the file Server Resource Manager on the Windows Server-based file server.</span></span> <span data-ttu-id="99ef3-175">有关详细信息, 请参阅[创建分类属性](http://go.microsoft.com/fwlink/p/?LinkID=627456)。</span><span class="sxs-lookup"><span data-stu-id="99ef3-175">For more information, see [Create a classification property](http://go.microsoft.com/fwlink/p/?LinkID=627456).</span></span>
    
<span data-ttu-id="99ef3-176">完成后, 策略应具有两个新规则, 它们都使用**文档属性包含这些值条件中的任何一个**。</span><span class="sxs-lookup"><span data-stu-id="99ef3-176">When you finish, your policy should have two new rules that both use the **Document properties contain any of these values** condition.</span></span> <span data-ttu-id="99ef3-177">请注意, 此条件不会显示在 UI 中, 但会显示其他条件、操作和设置。</span><span class="sxs-lookup"><span data-stu-id="99ef3-177">Note that this condition won't appear in the UI, though the other conditions, actions, and settings will appear.</span></span> 
  
<span data-ttu-id="99ef3-178">一个规则阻止访问其中“个人身份信息”\*\*\*\* 属性等于“高”\*\*\*\* 或“中等”\*\*\*\* 的内容。</span><span class="sxs-lookup"><span data-stu-id="99ef3-178">One rule blocks access to content where the **Personally Identifiable Information** property equals **High** or **Moderate**.</span></span> <span data-ttu-id="99ef3-179">第二个规则会发送有关“个人身份信息”\*\*\*\* 属性等于“低”\*\*\*\* 的内容的通知。</span><span class="sxs-lookup"><span data-stu-id="99ef3-179">A second rule sends a notification about content where the **Personally Identifiable Information** property equals **Low**.</span></span>
  
![显示刚创建的两条规则的“新建 DLP 策略”对话框](media/5c56c13b-62a5-4f25-8eb7-ce83a844bb12.png)
  
## <a name="after-you-create-the-dlp-policy"></a><span data-ttu-id="99ef3-181">创建 DLP 策略之后</span><span class="sxs-lookup"><span data-stu-id="99ef3-181">After you create the DLP policy</span></span>

<span data-ttu-id="99ef3-182">执行前面各节中的步骤将创建一个 DLP 策略, 该策略将使用该属性快速检测内容, 但前提是该内容是新上载的 (以便内容已编制索引), 或者该内容是旧的, 但只是进行了编辑 (以便重新编制内容索引).</span><span class="sxs-lookup"><span data-stu-id="99ef3-182">Doing the steps in the previous sections will create a DLP policy that will quickly detect content with that property, but only if that content is newly uploaded (so that the content's indexed), or if that content is old but just edited (so that the content's re-indexed).</span></span>
  
<span data-ttu-id="99ef3-p118">若要在任意位置检测包含该属性的内容，您可能需要手动请求对您的库、网站或网站集重新编制索引，以便 DLP 策略识别包含该属性的所有内容。在 SharePoint Online 中，内容基于已定义的爬网计划进行自动爬网。爬网程序选取自上次爬网以来已更改的内容，并更新索引。如果您需要在下一次计划的爬网之前，让您的 DLP 策略保护内容，您可以执行下列步骤。</span><span class="sxs-lookup"><span data-stu-id="99ef3-p118">To detect content with that property everywhere, you may want to manually request that your library, site, or site collection be re-indexed, so that the DLP policy is aware of all the content with that property. In SharePoint Online, content is automatically crawled based on a defined crawl schedule. The crawler picks up content that has changed since the last crawl and updates the index. If you need your DLP policy to protect content before the next scheduled crawl, you can take these steps.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="99ef3-187">重新编制网站的索引可能会导致搜索系统上的负荷大量增加。</span><span class="sxs-lookup"><span data-stu-id="99ef3-187">Re-indexing a site can cause a massive load on the search system.</span></span> <span data-ttu-id="99ef3-188">除非您的方案确实需要, 否则不要对网站重新编制索引。</span><span class="sxs-lookup"><span data-stu-id="99ef3-188">Don't re-index your site unless your scenario absolutely requires it.</span></span> 
  
<span data-ttu-id="99ef3-189">有关详细信息, 请参阅[手动对网站、库或列表的请求爬网和重新编制索引](http://go.microsoft.com/fwlink/p/?LinkID=627457)。</span><span class="sxs-lookup"><span data-stu-id="99ef3-189">For more information, see [Manually request crawling and re-indexing of a site, a library or a list](http://go.microsoft.com/fwlink/p/?LinkID=627457).</span></span>
  
### <a name="re-index-a-site-optional"></a><span data-ttu-id="99ef3-190">重新编制网站的索引（可选）</span><span class="sxs-lookup"><span data-stu-id="99ef3-190">Re-index a site (optional)</span></span>

1. <span data-ttu-id="99ef3-191">在网站上, 选择 "**设置**" (右上角的齿轮\>图标) "**网站设置**"。</span><span class="sxs-lookup"><span data-stu-id="99ef3-191">On the site, choose **Settings** (gear icon in upper right) \> **Site Settings**.</span></span>
    
2. <span data-ttu-id="99ef3-192">在 "**搜索**" 下, 选择 "**搜索和脱机可用性** \>重新**索引网站**"。</span><span class="sxs-lookup"><span data-stu-id="99ef3-192">Under **Search**, choose **Search and offline availability** \> **Reindex site**.</span></span>
    
## <a name="more-information"></a><span data-ttu-id="99ef3-193">更多信息</span><span class="sxs-lookup"><span data-stu-id="99ef3-193">More information</span></span>

- [<span data-ttu-id="99ef3-194">数据丢失防护策略概述</span><span class="sxs-lookup"><span data-stu-id="99ef3-194">Overview of data loss prevention policies</span></span>](data-loss-prevention-policies.md)
    
- [<span data-ttu-id="99ef3-195">从模板创建 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="99ef3-195">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)
    
- [<span data-ttu-id="99ef3-196">发送通知并显示 DLP 策略的策略提示</span><span class="sxs-lookup"><span data-stu-id="99ef3-196">Send notifications and show policy tips for DLP policies</span></span>](use-notifications-and-policy-tips.md)
    
- [<span data-ttu-id="99ef3-197">DLP 策略模板包含的内容</span><span class="sxs-lookup"><span data-stu-id="99ef3-197">What the DLP policy templates include</span></span>](what-the-dlp-policy-templates-include.md)
    
- [<span data-ttu-id="99ef3-198">敏感信息类型库存</span><span class="sxs-lookup"><span data-stu-id="99ef3-198">Sensitive information types inventory</span></span>](what-the-sensitive-information-types-look-for.md)
    

