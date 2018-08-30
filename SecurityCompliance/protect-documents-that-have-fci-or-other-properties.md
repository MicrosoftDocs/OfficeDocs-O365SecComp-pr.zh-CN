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
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Strat_O365_IP
ms.assetid: 1b9e3c6c-4308-4a20-b11e-c37b8013e177
description: 许多组织已识别和使用 Windows Server 文件分类基础结构 (FCI)、 SharePoint、 中的文档属性或文档属性中的分类属性分类敏感信息的过程应用通过第三方系统。如果这就是您的组织，则可以识别 Windows Server FCI 或其他系统中，应用于文档的属性，以便可以对 Office 文档与特定 FCI 或其他强制实施 DLP 策略的 Office 365 中创建 DLP 策略属性值。
ms.openlocfilehash: 057cdad981249e39d6f39f231d8d60ab977e717a
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "23013686"
---
# <a name="create-a-dlp-policy-to-protect-documents-with-fci-or-other-properties"></a><span data-ttu-id="0edff-104">创建 DLP 策略来保护具有 FCI 或其他属性的文档</span><span class="sxs-lookup"><span data-stu-id="0edff-104">Create a DLP policy to protect documents with FCI or other properties</span></span>

<span data-ttu-id="0edff-p102">在 Office 365 中，您可以使用数据丢失防护 (DLP) 策略来识别、监视和保护敏感信息。许多组织已拥有一个使用 Windows Server 文件分类基础结构 (FCI)、SharePoint 中的文档属性或由第三方系统应用的文档属性识别和分类敏感信息的流程。如果您的组织就是这样，则可以在 Office 365 中创建一个 DLP 策略，来识别已由 Windows Server FCI 或其他系统应用到文档的属性，从而在带有特定 FCI 或其他属性值的 Office 文档上强制应用该 DLP 策略。</span><span class="sxs-lookup"><span data-stu-id="0edff-p102">In Office 365, you can use a data loss prevention (DLP) policy to identify, monitor, and protect sensitive information. Many organizations already have a process to identify and classify sensitive information by using the classification properties in Windows Server File Classification Infrastructure (FCI), the document properties in SharePoint, or the document properties applied by a third-party system. If this describes your organization, you can create a DLP policy in Office 365 that recognizes the properties that have been applied to documents by Windows Server FCI or other system, so that the DLP policy can be enforced on Office documents with specific FCI or other property values.</span></span>
  
![显示 Office 365 和外部分类系统的图表](media/59ad0ac1-4146-4919-abd1-c74d8508d25e.png)
  
<span data-ttu-id="0edff-p103">例如，您的组织可能会使用 Windows Server FCI 使用社会保险号码，如个人身份信息 (PII) 标识文档，然后通过设置**个人身份信息**分类文档属性设为**高**、**中等**、**低**、**公共**，或**不 PII**基于类型，并在文档中找到 PII 的次数。在 Office 365 中，您可以创建 DLP 策略的标识该属性设置为特定值，如**高**和**Medium**的文档，然后对这些文件中执行操作，例如阻止访问。将相同的策略可以有采用不同的操作，如果属性设置为**低**，如发送的电子邮件通知的另一个规则。在这种方式，Office 365 中的 DLP 与 Windows Server FCI 集成，并有助于保护 Office 文档上载或从基于 Windows Server 的文件服务器共享复制到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="0edff-p103">For example, your organization might use Windows Server FCI to identify documents with personally identifiable information (PII) such as social security numbers, and then classify the document by setting the **Personally Identifiable Information** property to **High**, **Moderate**, **Low**, **Public**, or **Not PII** based on the type and number of occurrences of PII found in the document. In Office 365, you can create a DLP policy that identifies documents that have that property set to specific values, such as **High** and **Medium**, and then takes an action such as blocking access to those files. The same policy can have another rule that takes a different action if the property is set to **Low**, such as sending an email notification. In this way, DLP in Office 365 integrates with Windows Server FCI and can help protect Office documents uploaded or shared to Office 365 from Windows Server-based file servers.</span></span>
  
<span data-ttu-id="0edff-p104">DLP 策略只查找特定的属性名称/值对。可以使用任何文档属性，只要属性 SharePoint 搜索的相应托管的属性。例如，SharePoint 网站集可能需要使用名为**客户**必填字段具有的名为**行程报告**内容类型。只要人员创建的行程报告，他们必须输入的客户名称。此属性的名称/值对还可以采用 DLP 策略 — 例如，如果您希望块**客户**字段包含**Contoso**时对文档以进行外部用户访问的规则。</span><span class="sxs-lookup"><span data-stu-id="0edff-p104">A DLP policy simply looks for a specific property name/value pair. Any document property can be used, as long as the property has a corresponding managed property for SharePoint search. For example, a SharePoint site collection might use a content type named **Trip Report** with a required field named **Customer**. Whenever a person creates a trip report, they must enter the customer name. This property name/value pair can also be used in a DLP policy — for example, if you want a rule that blocks access to the document for external users when the **Customer** field contains **Contoso**.</span></span>
  
<span data-ttu-id="0edff-p105">请注意，是否您想要将您的 DLP 策略应用于与特定的 Office 365 标签的内容，您应遵循此处的步骤。相反，了解如何[使用 DLP 策略中，以状态标签](data-loss-prevention-policies.md#using-a-label-as-a-condition-in-a-dlp-policy)。</span><span class="sxs-lookup"><span data-stu-id="0edff-p105">Note that if you want to apply your DLP policy to content with specific Office 365 labels, you should not follow the steps here. Instead, learn how to [Using a label as a condition in a DLP policy](data-loss-prevention-policies.md#using-a-label-as-a-condition-in-a-dlp-policy).</span></span>
  
## <a name="before-you-create-the-dlp-policy"></a><span data-ttu-id="0edff-120">在创建 DLP 策略之前</span><span class="sxs-lookup"><span data-stu-id="0edff-120">Before you create the DLP policy</span></span>

<span data-ttu-id="0edff-p106">您可以使用 Windows Server FCI 属性或其他属性中的 DLP 策略之前，您需要在 SharePoint 管理中心中创建的托管的属性。下面是原因。</span><span class="sxs-lookup"><span data-stu-id="0edff-p106">Before you can use a Windows Server FCI property or other property in a DLP policy, you need to create a managed property in the SharePoint admin center. Here's why.</span></span>
  
<span data-ttu-id="0edff-p107">示例</span><span class="sxs-lookup"><span data-stu-id="0edff-p107">In SharePoint Online and OneDrive for Business, the search index is built up by crawling the content on your sites. The crawler picks up content and metadata from the documents in the form of crawled properties. The search schema helps the crawler decide what content and metadata to pick up. Examples of metadata are the author and the title of a document. However, to get the content and metadata from the documents into the search index, the crawled properties must be mapped to managed properties. Only managed properties are kept in the index. For example, a crawled property related to author is mapped to a managed property related to author.</span></span>
  
<span data-ttu-id="0edff-p108">这很重要，因为 Office 365 中的 DLP 使用搜索爬网程序来识别网站上的敏感信息，并对其进行分类，然后将该敏感信息存储在搜索索引的一个安全部分。当您将文档上载到 Office 365 时，SharePoint 会自动创建基于文档属性的已爬网属性。但是，要在 DLP 策略中使用 FCI 或其他属性，该已爬网属性需要映射到托管属性，以便将包含该属性的内容保留在索引中。</span><span class="sxs-lookup"><span data-stu-id="0edff-p108">This is important because DLP in Office 365 uses the search crawler to identify and classify sensitive information on your sites, and then store that sensitive information in a secure portion of the search index. When you upload a document to Office 365, SharePoint automatically creates crawled properties based on the document properties. But to use an FCI or other property in a DLP policy, that crawled property needs to be mapped to a managed property so that content with that property is kept in the index.</span></span>
  
<span data-ttu-id="0edff-133">有关搜索和托管的属性的详细信息，请参阅[Manage SharePoint Online 中的搜索架构](http://go.microsoft.com/fwlink/p/?LinkID=627454)。</span><span class="sxs-lookup"><span data-stu-id="0edff-133">For more information on search and managed properties, see [Manage the search schema in SharePoint Online](http://go.microsoft.com/fwlink/p/?LinkID=627454).</span></span>
  
### <a name="step-1-upload-a-document-with-the-needed-property-to-office-365"></a><span data-ttu-id="0edff-134">步骤 1：将包含所需属性的文档上载到 Office 365</span><span class="sxs-lookup"><span data-stu-id="0edff-134">Step 1: Upload a document with the needed property to Office 365</span></span>

<span data-ttu-id="0edff-p109">首先需要上载文档与您要在您的 DLP 策略中引用的属性。Office 365 将检测属性，并自动从其创建已爬网的属性。下一步，将创建一个托管的属性，然后将托管的属性映射到此已爬网属性。</span><span class="sxs-lookup"><span data-stu-id="0edff-p109">You first need to upload a document with the property that you want to reference in your DLP policy. Office 365 will detect the property and automatically create a crawled property from it. In the next step, you'll create a managed property, and then map the managed property to this crawled property.</span></span>
  
### <a name="step-2-create-a-managed-property"></a><span data-ttu-id="0edff-138">步骤 2：创建托管属性</span><span class="sxs-lookup"><span data-stu-id="0edff-138">Step 2: Create a managed property</span></span>

1. <span data-ttu-id="0edff-139">登录 Office 365 管理中心。</span><span class="sxs-lookup"><span data-stu-id="0edff-139">Sign in to the Office 365 admin center.</span></span>
    
2. <span data-ttu-id="0edff-p110">在左侧导航窗格中，选择**管理中心** \> **SharePoint**。现在，您在 SharePoint 管理中心。</span><span class="sxs-lookup"><span data-stu-id="0edff-p110">In the left navigation, choose **Admin centers** \> **SharePoint**. You're now in the SharePoint admin center.</span></span>
    
3. <span data-ttu-id="0edff-142">在左侧导航窗格中，选择**搜索** \> **搜索管理**页上\>**管理搜索架构**。</span><span class="sxs-lookup"><span data-stu-id="0edff-142">In the left navigation, choose **search** \> on the **search administration** page \> **Manage Search Schema**.</span></span>
    
    ![SharePoint 管理中心内的搜索管理页面](media/6bcd3aec-d11a-4f8c-9987-8f35da14d80b.png)
  
4. <span data-ttu-id="0edff-144">在**托管属性**页上\>**新建托管属性**。</span><span class="sxs-lookup"><span data-stu-id="0edff-144">On the **Managed Properties** page \> **New Managed Property**.</span></span>
    
    ![突出显示“新建托管属性”按钮的“托管属性”页面](media/b161c764-414c-4037-83ed-503a49fb4410.png)
  
5. <span data-ttu-id="0edff-p111">输入属性的名称和说明。此名称将显示在您的 DLP 策略中。</span><span class="sxs-lookup"><span data-stu-id="0edff-p111">Enter a name and description for the property. This name is what will appear in your DLP policies.</span></span>
    
6. <span data-ttu-id="0edff-148">对于**类型**，选择**文本**。</span><span class="sxs-lookup"><span data-stu-id="0edff-148">For **Type**, choose **Text**.</span></span> 
    
7. <span data-ttu-id="0edff-149">在**主特征**下选择**可查询**和**Retrievable**。</span><span class="sxs-lookup"><span data-stu-id="0edff-149">Under **Main characteristics**, select **Queryable** and **Retrievable**.</span></span>
    
8. <span data-ttu-id="0edff-150">在**映射到已爬网属性**下\>**添加映射**。</span><span class="sxs-lookup"><span data-stu-id="0edff-150">Under **Mappings to crawled properties** \> **Add a mapping**.</span></span>
    
9. <span data-ttu-id="0edff-151">在**爬网属性选择**对话框\>查找和选择对应的 Windows Server FCI 属性或其他属性将使用 DLP 策略中的已爬网的属性\>**确定**。</span><span class="sxs-lookup"><span data-stu-id="0edff-151">In the **crawled property selection** dialog box \> find and select the crawled property that corresponds to the Windows Server FCI property or other property that you will use in your DLP policy \> **OK**.</span></span>
    
    ![已爬网属性选择对话框](media/aeda1dce-1342-48bf-9594-a8e4f230e8aa.png)
  
10. <span data-ttu-id="0edff-153">在页面底部\>**确定**。</span><span class="sxs-lookup"><span data-stu-id="0edff-153">At the bottom of the page \> **OK**.</span></span>
    
## <a name="create-a-dlp-policy-that-uses-an-fci-property-or-other-property"></a><span data-ttu-id="0edff-154">创建使用 FCI 属性或其他属性的 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="0edff-154">Create a DLP policy that uses an FCI property or other property</span></span>

<span data-ttu-id="0edff-p112">本示例中，组织是 FCI 其基于 Windows Server 的文件在服务器上使用;具体而言，他们正在使用的**高**、**中等**、**低**、**公共**和**不 PII**的可能值以命名**个人身份信息**的 FCI 分类属性。现在他们想要利用其 Office 365 中的 DLP 策略中其现有 FCI 分类。</span><span class="sxs-lookup"><span data-stu-id="0edff-p112">In this example, an organization is using FCI on its Windows Server-based file servers; specifically, they're using the FCI classification property named **Personally Identifiable Information** with possible values of **High**, **Moderate**, **Low**, **Public**, and **Not PII**. Now they want to leverage their existing FCI classification in their DLP policies in Office 365.</span></span>
  
<span data-ttu-id="0edff-157">首先，它们按照上述步骤在 SharePoint Online 中创建托管属性，该属性映射到从 FCI 属性自动创建的已爬网属性。</span><span class="sxs-lookup"><span data-stu-id="0edff-157">First, they follow the steps above to create a managed property in SharePoint Online, which maps to the crawled property created automatically from the FCI property.</span></span>
  
<span data-ttu-id="0edff-158">接下来，他们创建的 DLP 策略与两个规则，同时使用**文档属性包含上述任何值的**条件：</span><span class="sxs-lookup"><span data-stu-id="0edff-158">Next, they create a DLP policy with two rules that both use the condition **Document properties contain any of these values**:</span></span>
  
- <span data-ttu-id="0edff-159">**FCI PII 内容-高、 中等**如果 FCI 分类属性**个人身份信息**等于**高**或**中等**和文档共享与组织外部的人员，第一个规则限制对文档访问。</span><span class="sxs-lookup"><span data-stu-id="0edff-159">**FCI PII content - High, Moderate** The first rule restricts access to the document if the FCI classification property **Personally Identifiable Information** equals **High** or **Moderate** and the document is shared with people outside the organization.</span></span> 
    
- <span data-ttu-id="0edff-160">**FCI PII 内容-低**第二个规则将发送通知给文档所有者如果 FCI 分类属性**个人身份信息**等于**低**和文档共享与组织外部的人员。</span><span class="sxs-lookup"><span data-stu-id="0edff-160">**FCI PII content - Low** The second rule sends a notification to the document owner if the FCI classification property **Personally Identifiable Information** equals **Low** and the document is shared with people outside the organization.</span></span> 
    
### <a name="create-the-dlp-policy-by-using-powershell"></a><span data-ttu-id="0edff-161">使用 PowerShell 创建 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="0edff-161">Create the DLP policy by using PowerShell</span></span>

<span data-ttu-id="0edff-p113">请注意，**文档属性包含上述任何值的**条件都暂时不安全的 UI 中&amp;合规性中心，但您仍可以通过使用 PowerShell 使用这种情况。您可以使用`New\Set\Get-DlpCompliancePolicy`cmdlet 以使用 DLP 策略，并使用`New\Set\Get-DlpComplianceRule`cmdlet 与`ContentPropertyContainsWords`参数可以添加**文档属性包含上述任何值的**条件。</span><span class="sxs-lookup"><span data-stu-id="0edff-p113">Note that the condition **Document properties contain any of these values** is temporarily not available in the UI of the Security &amp; Compliance Center, but you can still use this condition by using PowerShell. You can use the  `New\Set\Get-DlpCompliancePolicy` cmdlets to work with a DLP policy, and use the  `New\Set\Get-DlpComplianceRule` cmdlets with the  `ContentPropertyContainsWords` parameter to add the condition **Document properties contain any of these values**.</span></span>
  
<span data-ttu-id="0edff-164">这些 cmdlet 的详细信息，请参阅[Office 365 安全性&amp;合规性中心 cmdlet](http://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409)。</span><span class="sxs-lookup"><span data-stu-id="0edff-164">For more information on these cmdlets, see [Office 365 Security &amp; Compliance Center cmdlets](http://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409).</span></span>
  
1. [<span data-ttu-id="0edff-165">连接到 Office 365 安全性&amp;合规性中心使用远程 PowerShell</span><span class="sxs-lookup"><span data-stu-id="0edff-165">Connect to the Office 365 Security &amp; Compliance Center using remote PowerShell</span></span>](http://go.microsoft.com/fwlink/?LinkID=799771&amp;clcid=0x409)
    
2. <span data-ttu-id="0edff-166">使用创建策略`New-DlpCompliancePolicy`。</span><span class="sxs-lookup"><span data-stu-id="0edff-166">Create the policy by using  `New-DlpCompliancePolicy`.</span></span>
    
    <span data-ttu-id="0edff-167">下面是创建适用于所有位置的 DLP 策略 PowerShell 示例。</span><span class="sxs-lookup"><span data-stu-id="0edff-167">Here is a PowerShell example that creates a DLP policy that applies to all locations.</span></span>
    
      ```
      New-DlpCompliancePolicy -Name FCI_PII_policy -ExchangeLocation All -SharePointLocation All -OneDriveLocation All -Mode Enable
      ```

3. <span data-ttu-id="0edff-168">创建使用上述两个规则`New-DlpComplianceRule`，其中一个规则为**低**值，而另一个规则为**高**和**中等**值。</span><span class="sxs-lookup"><span data-stu-id="0edff-168">Create the two rules described above by using  `New-DlpComplianceRule`, where one rule is for the **Low** value, and another rule is for the **High** and **Moderate** values.</span></span> 
    
    <span data-ttu-id="0edff-p114">下面是创建这两个规则 PowerShell 示例。请注意，属性名称/值对括在引号内，属性名称可以指定多个值使用不带空格的用逗号隔开，如`"<Property1>:<Value1>,<Value2>","<Property2>:<Value3>,<Value4>"....`</span><span class="sxs-lookup"><span data-stu-id="0edff-p114">Here is a PowerShell example that creates these two rules. Note that the property name/value pairs are enclosed in quotation marks, and a property name may specify multiple values separated by commas with no spaces, like  `"<Property1>:<Value1>,<Value2>","<Property2>:<Value3>,<Value4>"....`</span></span>
    
      ```
      New-DlpComplianceRule -Name FCI_PII_content-High,Moderate -Policy FCI_PII_policy -AccessScope NotInOrganization -BlockAccess $true -ContentPropertyContainsWords "Personally Identifiable Information:High,Moderate" -Disabled $falseNew-DlpComplianceRule -Name FCI_PII_content-Low -Policy FCI_PII_policy -AccessScope NotInOrganization -BlockAccess $false -ContentPropertyContainsWords "Personally Identifiable Information:Low" -Disabled $false -NotifyUser Owner
      ```

    <span data-ttu-id="0edff-p115">请注意，Windows Server FCI 包括许多内置属性，包括在此示例中使用的**个人身份信息**。可能的每个属性值可以是不同的每个组织。**高**、**中等**复杂和此处使用的**低**值是仅示例。为您的组织，您可以在基于 Windows Server 的文件服务器上的文件服务器资源管理器中查看 Windows Server FCI 分类属性的可能值。有关详细信息，请参阅[Create 分类属性](http://go.microsoft.com/fwlink/p/?LinkID=627456)。</span><span class="sxs-lookup"><span data-stu-id="0edff-p115">Note that Windows Server FCI includes many built-in properties, including **Personally Identifiable Information** used in this example. The possible values for each property can be different for every organization. The **High**, **Moderate**, and **Low** values used here are only an example. For your organization, you can view the Windows Server FCI classification properties with their possible values in the file Server Resource Manager on the Windows Server-based file server. For more information, see [Create a classification property](http://go.microsoft.com/fwlink/p/?LinkID=627456).</span></span>
    
<span data-ttu-id="0edff-p116">完成后，您的策略应具有两个新规则，同时使用的**文档属性包含上述任何值的**条件。注意，此条件会不会出现在用户界面，但其他条件、 操作和设置将出现。</span><span class="sxs-lookup"><span data-stu-id="0edff-p116">When you finish, your policy should have two new rules that both use the **Document properties contain any of these values** condition. Note that this condition won't appear in the UI, though the other conditions, actions, and settings will appear.</span></span> 
  
<span data-ttu-id="0edff-p117">一个规则阻止访问内容位置的**个人身份信息**属性等于**高**或**中等**。第二个规则发送关于内容通知，其中的**个人身份信息**属性等于**低**。</span><span class="sxs-lookup"><span data-stu-id="0edff-p117">One rule blocks access to content where the **Personally Identifiable Information** property equals **High** or **Moderate**. A second rule sends a notification about content where the **Personally Identifiable Information** property equals **Low**.</span></span>
  
![显示刚创建的两条规则的“新建 DLP 策略”对话框](media/5c56c13b-62a5-4f25-8eb7-ce83a844bb12.png)
  
## <a name="after-you-create-the-dlp-policy"></a><span data-ttu-id="0edff-181">创建 DLP 策略之后</span><span class="sxs-lookup"><span data-stu-id="0edff-181">After you create the DLP policy</span></span>

<span data-ttu-id="0edff-182">执行前面几节中的步骤将创建快速将检测的 DLP 策略内容与该属性，但仅当 （以便的内容编制索引） 新上载的内容，或如果的内容旧但只需编辑 （以便内容重新编制索引）.</span><span class="sxs-lookup"><span data-stu-id="0edff-182">Doing the steps in the previous sections will create a DLP policy that will quickly detect content with that property, but only if that content is newly uploaded (so that the content's indexed), or if that content is old but just edited (so that the content's re-indexed).</span></span>
  
<span data-ttu-id="0edff-p118">若要在任意位置检测包含该属性的内容，您可能需要手动请求对您的库、网站或网站集重新编制索引，以便 DLP 策略识别包含该属性的所有内容。在 SharePoint Online 中，内容基于已定义的爬网计划进行自动爬网。爬网程序选取自上次爬网以来已更改的内容，并更新索引。如果您需要在下一次计划的爬网之前，让您的 DLP 策略保护内容，您可以执行下列步骤。</span><span class="sxs-lookup"><span data-stu-id="0edff-p118">To detect content with that property everywhere, you may want to manually request that your library, site, or site collection be re-indexed, so that the DLP policy is aware of all the content with that property. In SharePoint Online, content is automatically crawled based on a defined crawl schedule. The crawler picks up content that has changed since the last crawl and updates the index. If you need your DLP policy to protect content before the next scheduled crawl, you can take these steps.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="0edff-p119">重新编制索引网站可能会导致对搜索系统的大规模负载。除非您的方案绝对需要它，不重新编制索引您的网站。</span><span class="sxs-lookup"><span data-stu-id="0edff-p119">Re-indexing a site can cause a massive load on the search system. Don't re-index your site unless your scenario absolutely requires it.</span></span> 
  
<span data-ttu-id="0edff-189">有关详细信息，请参阅[手动请求爬网和的网站，库或列表重新编制索引](http://go.microsoft.com/fwlink/p/?LinkID=627457)。</span><span class="sxs-lookup"><span data-stu-id="0edff-189">For more information, see [Manually request crawling and re-indexing of a site, a library or a list](http://go.microsoft.com/fwlink/p/?LinkID=627457).</span></span>
  
### <a name="re-index-a-site-optional"></a><span data-ttu-id="0edff-190">重新编制网站的索引（可选）</span><span class="sxs-lookup"><span data-stu-id="0edff-190">Re-index a site (optional)</span></span>

1. <span data-ttu-id="0edff-191">在网站上，选择**设置**（齿轮图标右上） \> **网站设置**。</span><span class="sxs-lookup"><span data-stu-id="0edff-191">On the site, choose **Settings** (gear icon in upper right) \> **Site Settings**.</span></span>
    
2. <span data-ttu-id="0edff-192">在**搜索**下选择**搜索和脱机可用性** \> **网站重新编制索引**。</span><span class="sxs-lookup"><span data-stu-id="0edff-192">Under **Search**, choose **Search and offline availability** \> **Reindex site**.</span></span>
    
## <a name="more-information"></a><span data-ttu-id="0edff-193">详细信息</span><span class="sxs-lookup"><span data-stu-id="0edff-193">More information</span></span>

- [<span data-ttu-id="0edff-194">数据丢失防护策略概述</span><span class="sxs-lookup"><span data-stu-id="0edff-194">Overview of data loss prevention policies</span></span>](data-loss-prevention-policies.md)
    
- [<span data-ttu-id="0edff-195">从模板创建 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="0edff-195">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)
    
- [<span data-ttu-id="0edff-196">发送通知并显示 DLP 策略的策略提示</span><span class="sxs-lookup"><span data-stu-id="0edff-196">Send notifications and show policy tips for DLP policies</span></span>](use-notifications-and-policy-tips.md)
    
- [<span data-ttu-id="0edff-197">DLP 策略模板包含的内容</span><span class="sxs-lookup"><span data-stu-id="0edff-197">What the DLP policy templates include</span></span>](what-the-dlp-policy-templates-include.md)
    
- [<span data-ttu-id="0edff-198">敏感信息类型库存</span><span class="sxs-lookup"><span data-stu-id="0edff-198">Sensitive information types inventory</span></span>](what-the-sensitive-information-types-look-for.md)
    

