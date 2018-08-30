---
title: 创建和应用信息管理策略
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 5/16/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- SPO160
- OSU150
- OSU160
- MET150
ms.assetid: 8ccac9e4-3a50-49fa-a95b-d186032a6ee3
description: 信息管理策略，组织到多长时间保留内容、 审核人执行操作的内容，以及添加条形码控件或标签文档。策略可以帮助强制实施符合法律和政府法规或内部业务流程。作为管理员，您可以设置策略以控制如何跟踪文档和文档的保留多长时间。
ms.openlocfilehash: cc15b7d830e6c13e00045f7e4b672ac4a755a70e
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525090"
---
# <a name="create-and-apply-information-management-policies"></a><span data-ttu-id="e8853-105">创建和应用信息管理策略</span><span class="sxs-lookup"><span data-stu-id="e8853-105">Create and apply information management policies</span></span>

<span data-ttu-id="e8853-p102">信息管理策略，组织到多长时间保留内容、 审核人执行操作的内容，以及添加条形码控件或标签文档。策略可以帮助强制实施符合法律和政府法规或内部业务流程。作为管理员，您可以设置策略以控制如何跟踪文档和文档的保留多长时间。</span><span class="sxs-lookup"><span data-stu-id="e8853-p102">Information management policies enable your organization to control how long to retain content, to audit what people do with content, and to add barcodes or labels to documents. A policy can help enforce compliance with legal and governmental regulations or internal business processes. As an administrator, you can set up a policy to control how to track documents and how long to retain documents.</span></span>
  
<span data-ttu-id="e8853-109">您可以在网站层次结构，从最全面的三个不同的位置创建信息管理策略可以向最窄：</span><span class="sxs-lookup"><span data-stu-id="e8853-109">You can create an information management policy can at three different locations in the site hierarchy, from the broadest to the narrowest:</span></span>
  
- <span data-ttu-id="e8853-110">创建策略，以使用网站集中的多个内容类型。</span><span class="sxs-lookup"><span data-stu-id="e8853-110">Create a policy to use on multiple content types within a site collection.</span></span>
    
- <span data-ttu-id="e8853-111">创建网站内容类型的策略。</span><span class="sxs-lookup"><span data-stu-id="e8853-111">Create a policy for a site content type.</span></span>
    
- <span data-ttu-id="e8853-112">创建列表或库的策略。</span><span class="sxs-lookup"><span data-stu-id="e8853-112">Create a policy for a list or library.</span></span>
    
<span data-ttu-id="e8853-113">有关详细信息，请参阅[Introduction to 信息管理策略](intro-to-info-mgmt-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="e8853-113">For more information, see [Introduction to information management policies](intro-to-info-mgmt-policies.md).</span></span>
  
## <a name="create-a-policy-for-multiple-content-types-within-a-site-collection"></a><span data-ttu-id="e8853-114">创建网站集内的多个内容类型的策略</span><span class="sxs-lookup"><span data-stu-id="e8853-114">Create a policy for multiple content types within a site collection</span></span>
<span data-ttu-id="e8853-115"><a name="__toc261001590"> </a></span><span class="sxs-lookup"><span data-stu-id="e8853-115"></span></span>

<span data-ttu-id="e8853-p103">以确保信息策略应用于网站集中特定类型的所有文档，请考虑在网站集级别创建策略，然后对内容类型更高版本应用策略。这些称为网站集策略。</span><span class="sxs-lookup"><span data-stu-id="e8853-p103">To ensure that an information policy is applied to all documents of a certain type within a site collection, consider creating the policy at the site collection level and then later apply the policy to content types. These are referred to as site collection policies.</span></span> 
  
1. <span data-ttu-id="e8853-p104">在网站集主页上\>**设置**![标题栏上的 SharePoint 2016 设置按钮。](media/1c22d2d8-39e0-4930-82c6-c3eee44211d3.png) \> **网站设置**。</span><span class="sxs-lookup"><span data-stu-id="e8853-p104">On the site collection home page \> **Settings**![SharePoint 2016 Settings button on title bar.](media/1c22d2d8-39e0-4930-82c6-c3eee44211d3.png) \> **Site Settings**.</span></span>
    
    <span data-ttu-id="e8853-120">中 SharePoint 组连接网站中，单击**设置**，单击**网站内容**，，然后单击**网站设置**。</span><span class="sxs-lookup"><span data-stu-id="e8853-120">In a SharePoint group-connected site, click **Settings**, click **Site Contents**, and then click **Site Settings**.</span></span> 
    
2. <span data-ttu-id="e8853-121">在网站设置页上，在**网站集管理**下\>**内容类型策略模板**。</span><span class="sxs-lookup"><span data-stu-id="e8853-121">On the Site Settings page, under **Site Collection Administration** \> **Content Type Policy Templates**.</span></span> 
  
![在网站设置页的内容类型策略模板链接](media/26d3466a-23ec-443f-88f0-2aaff38e992b.png)
  
3. <span data-ttu-id="e8853-123">在策略页上\>**创建**。</span><span class="sxs-lookup"><span data-stu-id="e8853-123">On the Policies page \> **Create**.</span></span> 
    
4. <span data-ttu-id="e8853-124">输入名称和说明策略，，然后编写简要策略声明到用户策略的用途的说明。</span><span class="sxs-lookup"><span data-stu-id="e8853-124">Enter a name and description for the policy, and then write a brief policy statement that explains to users what the policy is for.</span></span>
    
5. <span data-ttu-id="e8853-125">创建网站内容类型以了解如何设置您想要与该策略关联的功能的策略，请参阅下一节。</span><span class="sxs-lookup"><span data-stu-id="e8853-125">See the next section on creating policies for a site content type to learn how to set up the features you want to associate with the policy.</span></span> 
    
6. <span data-ttu-id="e8853-126">选择"确定"。</span><span class="sxs-lookup"><span data-stu-id="e8853-126">Choose **OK**.</span></span>
    
## <a name="create-a-policy-for-a-site-content-type"></a><span data-ttu-id="e8853-127">创建网站内容类型的策略</span><span class="sxs-lookup"><span data-stu-id="e8853-127">Create a policy for a site content type</span></span>
<span data-ttu-id="e8853-128"><a name="__create_a_policy"> </a></span><span class="sxs-lookup"><span data-stu-id="e8853-128"></span></span>

<span data-ttu-id="e8853-p105">向内容类型添加信息管理策略便于将策略功能与多个列表或库相关联。您可以选择将现有的信息管理策略添加到内容类型或创建一个唯一的策略的特定于单个内容类型。</span><span class="sxs-lookup"><span data-stu-id="e8853-p105">Adding an information management policy to a content type makes it easy to associate policy features with multiple lists or libraries. You can choose to add an existing information management policy to a content type or create a unique policy specific to an individual content type.</span></span>
  
 <span data-ttu-id="e8853-p106">您还可以向特定于列表的内容类型添加信息管理策略。仅对该列表中的项目所使用的内容类型应用策略效果。</span><span class="sxs-lookup"><span data-stu-id="e8853-p106">You can also add an information management policy to a content type that is specific to lists. This has the effect of applying the policy only to items in that list that are using the content type.</span></span> 
  
1. <span data-ttu-id="e8853-p107">在网站集主页上\>**设置**![标题栏上的 SharePoint 2016 设置按钮。](media/1c22d2d8-39e0-4930-82c6-c3eee44211d3.png) \> **网站设置**。</span><span class="sxs-lookup"><span data-stu-id="e8853-p107">On the site collection home page \> **Settings**![SharePoint 2016 Settings button on title bar.](media/1c22d2d8-39e0-4930-82c6-c3eee44211d3.png) \> **Site Settings**.</span></span>
    
    <span data-ttu-id="e8853-135">中 SharePoint 组连接网站中，单击**设置**，单击**网站内容**，，然后单击**网站设置**。</span><span class="sxs-lookup"><span data-stu-id="e8853-135">In a SharePoint group-connected site, click **Settings**, click **Site Contents**, and then click **Site Settings**.</span></span> 
    
2. <span data-ttu-id="e8853-136">在网站设置页上，在**Web 设计器库**下\>**网站内容类型**。</span><span class="sxs-lookup"><span data-stu-id="e8853-136">On the Site Settings page, under **Web Designer Galleries** \> **Site content types**.</span></span>
  
![在网站设置页的网站内容类型链接](media/6f6fa51f-15d7-4782-b06f-a7b36e874cd3.png)
  
3. <span data-ttu-id="e8853-138">在网站内容类型设置页上，选择您想要添加到策略的内容类型。</span><span class="sxs-lookup"><span data-stu-id="e8853-138">On the Site Content Type Settings page, select the content type that you want to add a policy to.</span></span>
    
4. <span data-ttu-id="e8853-139">在网站内容类型页上的在**设置**下， \> **信息管理策略设置**。</span><span class="sxs-lookup"><span data-stu-id="e8853-139">On the Site Content Type page, under **Settings** \> **Information management policy settings**.</span></span>
    
5. <span data-ttu-id="e8853-140">在编辑策略页上输入的名称和说明策略，然后写入到用户策略的用途的说明的简要说明。</span><span class="sxs-lookup"><span data-stu-id="e8853-140">On the Edit Policy page, enter a name and description for the policy, and then write a brief description that explains to users what the policy is for.</span></span>
    
6. <span data-ttu-id="e8853-141">在下一步部分，选择您想要添加到您的信息管理策略的各个策略功能。</span><span class="sxs-lookup"><span data-stu-id="e8853-141">In the next sections, select the individual policy features that you want to add to your information management policy.</span></span> 
  
![类型的内容的策略](media/19fcb8a3-974b-40d3-a13f-b76088d122f8.png)
  
7. <span data-ttu-id="e8853-143">若要指定的文档和项受此策略的保留期，选择**启用保留**，然后指定保持期，以及您想要项目到期时，会发生的操作。</span><span class="sxs-lookup"><span data-stu-id="e8853-143">To specify a retention period for documents and items that are subject to this policy, choose **Enable Retention**, and then specify the retention period and the actions that you want to occur when the items expire.</span></span>
    
    <span data-ttu-id="e8853-144">指定保留期</span><span class="sxs-lookup"><span data-stu-id="e8853-144">To specify a retention period</span></span>
    
||||||<span data-ttu-id="e8853-145">**1。**</span><span class="sxs-lookup"><span data-stu-id="e8853-145">**1.**</span></span>|<span data-ttu-id="e8853-146">\* \* 选择 \* \* 添加记录的保留阶段...\*\*\*</span><span class="sxs-lookup"><span data-stu-id="e8853-146">**Choose **Add a retention stage for records…****</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
||||||<span data-ttu-id="e8853-147">2.</span><span class="sxs-lookup"><span data-stu-id="e8853-147">2.</span></span>  <br/> | <span data-ttu-id="e8853-p108">选择一个保留期选项以指定文档或项设置过期。请执行以下任一操作：</span><span class="sxs-lookup"><span data-stu-id="e8853-p108">Select a retention period option to specify when documents or items are set to expire. Do one of the following:  </span></span><br/>  <span data-ttu-id="e8853-150">若要设置的到期日期，根据日期属性，在**事件** \> **此阶段基于关闭日期属性的项**，然后选择的文档或项目的操作 （例如，创建或修改） 并在此操作 （的时间增量例如的天数、 月数或年数） 当您想要过期的项。</span><span class="sxs-lookup"><span data-stu-id="e8853-150">To set the expiration date based on a date property, under **Event** \> **This stage is based off a date property on the item**, and then select the document or item action (for example, Created or Modified) and the increment of time after this action (for example, the number of days, months, or years) when you want the item to expire.</span></span>  <br/>  <span data-ttu-id="e8853-151">若要使用自定义保留公式来确定有效期限，请选择**此服务器上安装自定义保留公式来设置**。</span><span class="sxs-lookup"><span data-stu-id="e8853-151">To use a custom retention formula to determine expiration, choose **Set by a custom retention formula installed on this server**.</span></span>  <br/> <span data-ttu-id="e8853-152">> [!NOTE]> 此选项才可用，如果您的管理员已设置的自定义公式。</span><span class="sxs-lookup"><span data-stu-id="e8853-152">> [!NOTE]>  This option is only available if a custom formula has been set up by your administrator.</span></span>           |
||||||<span data-ttu-id="e8853-153">3.</span><span class="sxs-lookup"><span data-stu-id="e8853-153">3.</span></span>  <br/> |<span data-ttu-id="e8853-p109">**启动工作流**选项是您要定义列表、 库或已具有与其关联的工作流的内容类型的策略时，才可用。然后是根据选择的工作流可供选择。</span><span class="sxs-lookup"><span data-stu-id="e8853-p109">The **Start a workflow** option is available only if you are defining a policy for a list, library, or content type that already has a workflow associated with it. You will then be given a choice of workflows to choose from.  </span></span><br/> |
||||||<span data-ttu-id="e8853-156">4.</span><span class="sxs-lookup"><span data-stu-id="e8853-156">4.</span></span>  <br/> |<span data-ttu-id="e8853-157">在**重复**部分中，选择**重复此阶段的操作...** 然后输入您希望再次出现的操作的频率。</span><span class="sxs-lookup"><span data-stu-id="e8853-157">In the **Recurrence** section, select **Repeat this stage's action…** and enter how often you want the action to reoccur.</span></span>  <br/> <span data-ttu-id="e8853-p110">> [!NOTE]> 此选项才可用可以重复您选择的操作。例如，不能设置定期**永久删除**操作。</span><span class="sxs-lookup"><span data-stu-id="e8853-p110">> [!NOTE]>  This option is only available if the action you selected can be repeated. For example, you cannot set recurrence for the action **Permanently Delete**.</span></span>           |
||||||<span data-ttu-id="e8853-160">5.</span><span class="sxs-lookup"><span data-stu-id="e8853-160">5.</span></span>  <br/> |<span data-ttu-id="e8853-161">选择**确定**。</span><span class="sxs-lookup"><span data-stu-id="e8853-161">Chose **OK**.</span></span>  <br/> |
   
1. <span data-ttu-id="e8853-162">若要启用审核的文档和受到此策略的项目，选择**启用审核**，并指定您想要审核的事件。</span><span class="sxs-lookup"><span data-stu-id="e8853-162">To enable auditing for the documents and items that are subject to this policy, choose **Enable Auditing**, and then specify the events you want to audit.</span></span>
    
    <span data-ttu-id="e8853-163">若要启用审核</span><span class="sxs-lookup"><span data-stu-id="e8853-163">To enable auditing</span></span>
    
||||||<span data-ttu-id="e8853-164">1.\* \* \*</span><span class="sxs-lookup"><span data-stu-id="e8853-164">****1.****</span></span>|<span data-ttu-id="e8853-165">在编辑策略页上 \* ***下\*\*\*\*审核** **\>** **启用审核*** *，然后选择您想要保留审核的事件旁边的复选框尾 for.* \* \*</span><span class="sxs-lookup"><span data-stu-id="e8853-165">****On the Edit Policy page,** **under** **Auditing** **\>** **Enable auditing** **, and then select the check boxes next to the events you want to keep an audit trail for.****</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
||||||<span data-ttu-id="e8853-166">**2。**</span><span class="sxs-lookup"><span data-stu-id="e8853-166">**2.**</span></span> <br/> |<span data-ttu-id="e8853-167">**若要提示用户插入到文档，这些条码****选择****插入条码保存或打印前的，提示用户****.**</span><span class="sxs-lookup"><span data-stu-id="e8853-167">**To prompt users to insert these barcodes into documents,** **choose** **Prompt users to insert a barcode before saving or printing** **.**</span></span> <br/> |
||||||<span data-ttu-id="e8853-168">**3。**</span><span class="sxs-lookup"><span data-stu-id="e8853-168">**3.**</span></span> <br/> |<span data-ttu-id="e8853-169">**选择****确定*** * 若要将审核功能应用于此策略。</span><span class="sxs-lookup"><span data-stu-id="e8853-169">**Choose** **OK** ** to apply the auditing feature to the policy.</span></span> ** <br/> |
|||||||<span data-ttu-id="e8853-p111">审核策略功能，组织可以创建并分析审核跟踪对文档和列表项，如任务列表、 问题列表、 讨论组和日历。此策略功能提供的审核日志将记录事件，如时查看、 编辑或删除内容。</span><span class="sxs-lookup"><span data-stu-id="e8853-p111">The Auditing Policy feature enables organizations to create and analyze audit trails for documents and to list items such as task lists, issues lists, discussion groups, and calendars. This policy feature provides an audit log that records events, such as when content is viewed, edited, or deleted.</span></span>  <br/> |
|||||||<span data-ttu-id="e8853-p112">启用审核后信息管理策略的一部分，管理员可以查看审核数据的基于 Microsoft Excel 中并的汇总当前使用的策略使用率报告中。管理员可以使用这些报告，以确定信息组织内使用的方式。这些报告还有助于组织验证并记录其法规或研究潜在的问题。</span><span class="sxs-lookup"><span data-stu-id="e8853-p112">When auditing is enabled as part of an information management policy, administrators can view the audit data in policy usage reports that are based in Microsoft Excel and that summarize current usage. Administrators can use these reports to determine how information is being used within the organization. These reports can also help organizations to verify and document their regulatory compliance or to investigate potential concerns.</span></span>  <br/> |
|||||||<span data-ttu-id="e8853-175">审核日志可记录以下信息：事件名称、事件的日期和时间以及执行操作的用户的系统名称。</span><span class="sxs-lookup"><span data-stu-id="e8853-175">The audit log records the following information: event name, date and time of the event, and system name of the user who performed the action.</span></span>  <br/> |
   
1. <span data-ttu-id="e8853-p113">启用条码后的策略的一部分，它们添加到文档属性和条形码应用于文档的页眉区域中显示。标签，如条码可以也是手动删除从文档。您可以指定是否包含条形码打印或保存项目时是否应提示用户或如果应手动插入条码 2010年中使用**插入**选项卡 Office release 程序。</span><span class="sxs-lookup"><span data-stu-id="e8853-p113">When barcodes are enabled as part of a policy, they are added to document properties and displayed in the header area of the document to which the barcode is applied. Like labels, barcodes can also be manually removed from a document. You can specify whether users should be prompted to include the barcode when printing or saving an item or if the barcode should be inserted manually using the **Insert** tab in 2010 Office release programs.</span></span> 
    
    <span data-ttu-id="e8853-179">若要启用条码</span><span class="sxs-lookup"><span data-stu-id="e8853-179">To enable barcodes</span></span>
    
||||||<span data-ttu-id="e8853-180">1.\* \* \*</span><span class="sxs-lookup"><span data-stu-id="e8853-180">****1.****</span></span>|<span data-ttu-id="e8853-181">**在编辑策略页的**条码**\> **启用条码**。**</span><span class="sxs-lookup"><span data-stu-id="e8853-181">**On the Edit Policy page, under **Barcodes**\> **Enable Barcodes**.**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
||||||<span data-ttu-id="e8853-182">**2。**</span><span class="sxs-lookup"><span data-stu-id="e8853-182">**2.**</span></span> <br/> |<span data-ttu-id="e8853-183">提示用户进行这些条码插入到文档中，选择**插入条码保存或打印前的，提示用户**。</span><span class="sxs-lookup"><span data-stu-id="e8853-183">To prompt users to insert these barcodes into documents, choose **Prompt users to insert a barcode before saving or printing**.</span></span>  <br/> |
||||||<span data-ttu-id="e8853-184">**3。**</span><span class="sxs-lookup"><span data-stu-id="e8853-184">**3.**</span></span> <br/> |<span data-ttu-id="e8853-185">选择**确定**以应用于此策略的条码功能。</span><span class="sxs-lookup"><span data-stu-id="e8853-185">Choose **OK** to apply the barcode feature to the policy.</span></span>  <br/> |
|||||||
 <span data-ttu-id="e8853-p114">条码策略会生成代码 39 标准条码。每个条码图像包括下面表示条码值的条形码符号的文字。这样，即使扫描硬件不可用时要使用的条码数据。用户可以手动在搜索框中，若要找到网站上的项目键入条码编号。</span><span class="sxs-lookup"><span data-stu-id="e8853-p114">The barcode policy generates Code 39 standard barcodes. Each barcode image includes text below the barcode symbol that represents the barcode value. This enables the barcode data to be used even when scanning hardware is not available. Users can manually type the barcode number into the search box to locate the item on a site.</span></span>  <br/> |
   
1. <span data-ttu-id="e8853-190">若要要求受此策略制约的文档具有标签、 选择**启用标签**，然后指定所需的标签的设置。</span><span class="sxs-lookup"><span data-stu-id="e8853-190">To require that documents that are subject to this policy have labels, choose **Enable Labels**, and then specify the settings that you want for the labels.</span></span>
    
    <span data-ttu-id="e8853-191">若要启用标签</span><span class="sxs-lookup"><span data-stu-id="e8853-191">To enable labels</span></span>
    
||||||<span data-ttu-id="e8853-192">**1。**</span><span class="sxs-lookup"><span data-stu-id="e8853-192">**1.**</span></span>|<span data-ttu-id="e8853-193">* * 到要求用户添加到文档的标签，请选择**提示用户保存或打印前插入标签**。</span><span class="sxs-lookup"><span data-stu-id="e8853-193">**To require users to add a label to a document, choose **Prompt users to insert a label before saving or printing**.</span></span>  <br/> <span data-ttu-id="e8853-194">> [!NOTE]> 如果您希望标签为可选，不要选中此复选框。</span><span class="sxs-lookup"><span data-stu-id="e8853-194">> [!NOTE]>  If you want labels to be optional, do not select this check box.</span></span>        **|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
||||||<span data-ttu-id="e8853-195">2.</span><span class="sxs-lookup"><span data-stu-id="e8853-195">2.</span></span>  <br/> |<span data-ttu-id="e8853-196">要锁定标签，以便它不能更改其插入后，请选择**标签添加标签后禁止更改标签**。</span><span class="sxs-lookup"><span data-stu-id="e8853-196">To lock a label so that it cannot be changed after it has been inserted, choose **Prevent changes to labels after they are added**.</span></span>  <br/>  <span data-ttu-id="e8853-p115">此设置可防止更新后标签插入如 Word、 Excel 或 PowerPoint 的客户端应用程序内的项目的标签文本。如果您希望更新该文档或项目的属性时要更新的标签，请不选中此复选框。</span><span class="sxs-lookup"><span data-stu-id="e8853-p115">This setting prevents the label text from updating once the label has been inserted into an item within a client application such as Word, Excel, or PowerPoint. If you want the label to be updated when the properties for this document or item are updated, do not select this check box.  </span></span><br/> |
||||||<span data-ttu-id="e8853-199">3.</span><span class="sxs-lookup"><span data-stu-id="e8853-199">3.</span></span>  <br/> |<span data-ttu-id="e8853-p116">在标签格式框中，根据需要对显示，为标签输入的文本。标签可以包含最多 10 个列引用，其中每个可以最多 255 个字符。若要创建的格式为您的标签，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="e8853-p116">In the Label format box, enter the text for the label as you want it to be displayed. Labels can contain up to 10 column references, each of which can be up to 255 characters long. To create the format for your label, do the following:</span></span>  <br/> <span data-ttu-id="e8853-p117">键入您想要在其中您希望其出现的顺序在标签中包括的列的名称。将列名称括在大括号 ({})、 编辑策略页上的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="e8853-p117">Type the names of the columns that you want to include in the label in the order in which you want them to appear. Enclose the column names in curly brackets ({}), as shown in the example on the Edit Policy page.</span></span>  <br/> <span data-ttu-id="e8853-205">在编辑策略页上的示例所示，请键入单词以确定在括号外的列。</span><span class="sxs-lookup"><span data-stu-id="e8853-205">Type words to identify the columns outside the brackets, as shown in the example on the Edit Policy page.</span></span>  <br/> |
||||||<span data-ttu-id="e8853-206">4.</span><span class="sxs-lookup"><span data-stu-id="e8853-206">4.</span></span>  <br/> |<span data-ttu-id="e8853-207">若要添加换行符， **\n**输入您希望出现换行符。</span><span class="sxs-lookup"><span data-stu-id="e8853-207">To add a line break, enter **\n** where you want the line break to appear.</span></span>  <br/> |
||||||<span data-ttu-id="e8853-208">5.</span><span class="sxs-lookup"><span data-stu-id="e8853-208">5.</span></span>  <br/> |<span data-ttu-id="e8853-209">选择的字体大小和型，它指定是否希望标签置于左、 中心，还是文档中的权限。</span><span class="sxs-lookup"><span data-stu-id="e8853-209">Select the font size and style that you want, and specify whether you want the label positioned left, center, or right within the document.</span></span>  <br/>  <span data-ttu-id="e8853-p118">选择字体和用户的计算机可用的样式。字体的大小会影响多少文本可显示标签上。</span><span class="sxs-lookup"><span data-stu-id="e8853-p118">Select a font and style that are available on the users' computers. The size of the font affects how much text can be displayed on the label.</span></span>  <br/> |
||||||<span data-ttu-id="e8853-212">6.</span><span class="sxs-lookup"><span data-stu-id="e8853-212">6.</span></span>  <br/> |<span data-ttu-id="e8853-p119">输入高度和标签的宽度。标签高度为 20 英寸，可以从.25 英寸范围和标签宽度的范围可以从.25 英寸为 20 英寸。标签文本标签 image 内始终垂直居中。</span><span class="sxs-lookup"><span data-stu-id="e8853-p119">Enter the height and width of the label. Label height can range from .25 inches to 20 inches, and label width can range from .25 inches to 20 inches. Label text is always vertically centered within the label image.</span></span>  <br/> |
||||||<span data-ttu-id="e8853-216">7.</span><span class="sxs-lookup"><span data-stu-id="e8853-216">7.</span></span>  <br/> |<span data-ttu-id="e8853-217">选择**刷新**以预览的标签内容。</span><span class="sxs-lookup"><span data-stu-id="e8853-217">Choose **Refresh** to preview the label content.</span></span>  <br/> |
   
1. <span data-ttu-id="e8853-218">选择"确定"。</span><span class="sxs-lookup"><span data-stu-id="e8853-218">Choose **OK**.</span></span>
    
## <a name="create-a-policy-for-a-list-library-or-folder-location-based-retention-policy"></a><span data-ttu-id="e8853-219">为列表、库或文件夹创建策略（基于位置的保留策略）</span><span class="sxs-lookup"><span data-stu-id="e8853-219">Create a policy for a list, library or folder (location-based retention policy)</span></span>
<span data-ttu-id="e8853-220"><a name="__create_a_policy"> </a></span><span class="sxs-lookup"><span data-stu-id="e8853-220"></span></span>

<span data-ttu-id="e8853-p120">您可以定义仅适用于特定列表、 库或文件夹的保留策略。但是，如果这种方式创建保留策略，不能重新使用在其他列表、 库、 文件夹或网站，此策略，并且无法将网站集策略应用于基于位置策略。</span><span class="sxs-lookup"><span data-stu-id="e8853-p120">You can define a retention policy that applies only to a specific list, library or folder. However, if you create a retention policy this way, you cannot reuse this policy on other lists, libraries, folders or sites, and you cannot apply a site collection policy to a location based policy.</span></span>
  
<span data-ttu-id="e8853-p121">如果您想要将单个保留策略应用于所有类型的单个位置中的内容，很可能需要使用基于位置的保留期。在大多数其他情况下，要验证的所有内容类型指定保留策略。</span><span class="sxs-lookup"><span data-stu-id="e8853-p121">If you want to apply a single retention policy to all types of content in a single location, you will most likely want to use location-based retention. In most other cases, you will want to verify that a retention policy is specified for all content types.</span></span>
  
 <span data-ttu-id="e8853-225">每个子文件夹继承其父级的保留策略，除非您选择要断开继承并定义新的保留策略子级别。</span><span class="sxs-lookup"><span data-stu-id="e8853-225">Each subfolder inherits the retention policy of its parent, unless you choose to break inheritance and define a new retention policy at the child level.</span></span> 
  
<span data-ttu-id="e8853-226">如果您想要对列表或库中定义信息管理策略保留之外，您需要定义与列表或库关联的每个单独的列表内容类型的信息管理策略。</span><span class="sxs-lookup"><span data-stu-id="e8853-226">If you want to define an information management policy other than retention to a list or library, you need to define an information management policy for each individual list content type associated with that list or library.</span></span>
  
 <span data-ttu-id="e8853-p122">如果在任何点决定从内容类型切换到基于位置的列表或库的策略，只保留策略将用作基于位置的策略。将从关联的内容类型继承的所有其他管理策略 （审核、 条码，和条码）。</span><span class="sxs-lookup"><span data-stu-id="e8853-p122">If at any point you decide to switch from content type to location-based policies for a list or library, only the retention policy will be used as the location-based policy. All other management policies (audits, barcodes, and barcodes) will be inherited from the associated content types.</span></span> 
  
 <span data-ttu-id="e8853-p123">可以停用的库和文件夹基于保留功能，为网站集禁用基于位置策略。这样，网站集管理员，以确保其内容类型策略不重写的列表管理员基于位置策略。</span><span class="sxs-lookup"><span data-stu-id="e8853-p123">Location based policies can be disabled for a site collection by deactivating the Library and Folder Based Retention feature. This enables site collection administrators to ensure that their content type policies are not overridden by a list administrator's location based policies.</span></span> 
  
<span data-ttu-id="e8853-231">您至少需要管理列表权限若要更改列表或库的信息管理策略设置。</span><span class="sxs-lookup"><span data-stu-id="e8853-231">You need at least the Manage Lists permission to change the information management policy settings for a list or library.</span></span>
  
1. <span data-ttu-id="e8853-232">导航到您要为其指定信息管理策略的列表或库。</span><span class="sxs-lookup"><span data-stu-id="e8853-232">Navigate to the list or library for which you want to specify an information management policy.</span></span> 
    
2. <span data-ttu-id="e8853-233">在功能区中，选择**库**或**列表**选项卡\>**库设置**或**列表设置**。</span><span class="sxs-lookup"><span data-stu-id="e8853-233">On the ribbon, choose the **Library** or **List** tab \> **Library Settings** or **List Settings**.</span></span>
    
    <span data-ttu-id="e8853-234">在 SharePoint Online 中，单击**设置**，然后单击**列表设置**或**库设置**。</span><span class="sxs-lookup"><span data-stu-id="e8853-234">In SharePoint Online, click **Settings** and then click **List settings** or **Library settings**.</span></span> 
    
3. <span data-ttu-id="e8853-235">在**权限和管理**下\>**信息管理策略设置**。</span><span class="sxs-lookup"><span data-stu-id="e8853-235">Under **Permissions and Management**\> **Information management policy settings**.</span></span>
  
![在文档库设置页面上的信息管理策略链接](media/9fa6d366-6aab-49e1-a05c-898ac6f536e6.png)
  
4. <span data-ttu-id="e8853-237">在信息管理策略设置页上，确保保留列表或库的源，设置为库和文件夹。</span><span class="sxs-lookup"><span data-stu-id="e8853-237">On the Information Management Policy Settings page, make sure that the source of retention for the list or library is set to Library and Folders.</span></span> 
  
<span data-ttu-id="e8853-p124">如果**内容类型**显示为源，单击**更改源**，然后单击**库和文件夹**。提醒您将被忽略内容类型保留策略。选择**确定**。</span><span class="sxs-lookup"><span data-stu-id="e8853-p124">If **Content Type** appears as the source, click **Change Source**, and then click **Library and Folders**. You are alerted that content type retention policies will be ignored. Choose **OK**.</span></span> 
    
5. <span data-ttu-id="e8853-241">在编辑策略页上的在**库基于保留计划**，下，输入要创建的策略的简要说明。</span><span class="sxs-lookup"><span data-stu-id="e8853-241">On the Edit Policy page, under **Library Based Retention Schedule**, enter a brief description for the policy you are creating.</span></span> 
    
6. <span data-ttu-id="e8853-242">选择**添加保留阶段...**</span><span class="sxs-lookup"><span data-stu-id="e8853-242">Choose **Add a retention stage…**</span></span>
    
     <span data-ttu-id="e8853-243">请注意，在下记录，您可以选择通过选择记录选项定义不同的保留阶段中定义的记录的不同的保留策略。</span><span class="sxs-lookup"><span data-stu-id="e8853-243">Note that under Records, you can choose to define different retention policies for records by selecting the Define different retention stages for records option.</span></span> 
    
7. <span data-ttu-id="e8853-p125">在容器属性对话框，选择保留期选项，以指定文档或项目都设置为时过期。请执行以下任一操作：</span><span class="sxs-lookup"><span data-stu-id="e8853-p125">In the Stage properties dialog, select a retention period option to specify when documents or items are set to expire. Do one of the following:</span></span>
    
  - <span data-ttu-id="e8853-246">若要设置的到期日期，根据日期属性，在**事件** \> **此阶段基于关闭日期属性的项**，然后选择的文档或项目的操作 （例如，创建或修改） 并在此操作 （的时间增量例如的天数、 月数或年数） 当您想要过期的项。</span><span class="sxs-lookup"><span data-stu-id="e8853-246">To set the expiration date based on a date property, under **Event** \> **This stage is based off a date property on the item**, and then select the document or item action (for example, Created or Modified) and the increment of time after this action (for example, the number of days, months, or years) when you want the item to expire.</span></span> 
    
  - <span data-ttu-id="e8853-247">若要使用自定义保留公式来确定有效期限，请选择**此服务器上安装自定义保留公式来设置**。</span><span class="sxs-lookup"><span data-stu-id="e8853-247">To use a custom retention formula to determine expiration, choose **Set by a custom retention formula installed on this server**.</span></span> 
    
    > [!NOTE]
    >  <span data-ttu-id="e8853-248">此选项才可用，如果您的管理员已设置的自定义公式。</span><span class="sxs-lookup"><span data-stu-id="e8853-248">This option is only available if a custom formula has been set up by your administrator.</span></span> 
  
  - <span data-ttu-id="e8853-p126">在**操作**指定您想要在文档或项过期时执行。若要启用的文档或项目 （例如删除） 的特定操作，请从列表中选择一个操作。</span><span class="sxs-lookup"><span data-stu-id="e8853-p126">Under **Action**, specify what you want to happen when the document or item expires. To enable a specific action to happen to the document or item (such as deletion), select an action from the list.</span></span> 
    
8. <span data-ttu-id="e8853-p127">**启动工作流**选项是您要定义列表、 库或已具有与其关联的工作流的内容类型的策略时，才可用。然后是根据选择的工作流可供选择。</span><span class="sxs-lookup"><span data-stu-id="e8853-p127">The **Start a workflow** option is available only if you are defining a policy for a list, library, or content type that already has a workflow associated with it. You will then be given a choice of workflows to choose from.</span></span> 
    
9. <span data-ttu-id="e8853-253">在**定期**，下选择**重复此阶段的操作...** 然后输入您希望再次出现的操作的频率。</span><span class="sxs-lookup"><span data-stu-id="e8853-253">Under **Recurrence**, choose **Repeat this stage's action…** and enter how often you want the action to reoccur.</span></span> 
    
    > [!NOTE]
    >  <span data-ttu-id="e8853-p128">此选项才可用可以重复您选择的操作。例如，不能设置定期**永久删除**操作。</span><span class="sxs-lookup"><span data-stu-id="e8853-p128">This option is only available if the action you selected can be repeated. For example, you cannot set recurrence for the action **Permanently Delete**.</span></span> 
  
10. <span data-ttu-id="e8853-256">选择"确定"。</span><span class="sxs-lookup"><span data-stu-id="e8853-256">Choose **OK**.</span></span>
    
## <a name="apply-a-site-collection-policy-to-a-content-type"></a><span data-ttu-id="e8853-257">适用于内容类型的网站集策略</span><span class="sxs-lookup"><span data-stu-id="e8853-257">Apply a site collection policy to a content type</span></span>
<span data-ttu-id="e8853-258"><a name="__apply_a_site"> </a></span><span class="sxs-lookup"><span data-stu-id="e8853-258"></span></span>

<span data-ttu-id="e8853-p129">如果信息管理策略已创建网站作为网站集策略，您可以向内容类型应用策略之一。通过执行此操作，您可以将相同的策略应用于多个内容类型在网站集中不共享相同的父内容类型的。</span><span class="sxs-lookup"><span data-stu-id="e8853-p129">If information management policies have already been created for your site as site collection policies, you can apply one of the policies to a content type. By doing this, you can apply the same policy to multiple content types in a site collection that do not share the same parent content type.</span></span>
  
 <span data-ttu-id="e8853-p130">如果您想要将策略应用于网站集中的多个内容类型，并且必须配置 Managed Metadata Service，可以使用内容类型发布出发布信息管理策略到多个网站集。请参阅[应用到跨网站集的内容类型策略](create-info-mgmt-policies.md#__apply_a_policy)的详细信息的部分。</span><span class="sxs-lookup"><span data-stu-id="e8853-p130">If you want to apply policies to multiple content types in a site collection, and you have a Managed Metadata Service configured, you can use Content Type Publishing to publish out information management polices to multiple site collections. See the section [Apply a policy to content types across site collections](create-info-mgmt-policies.md#__apply_a_policy) for more information.</span></span> 
  
1. <span data-ttu-id="e8853-263">导航到列表或库，其中包含您要向其应用策略的内容类型。</span><span class="sxs-lookup"><span data-stu-id="e8853-263">Navigate to the list or library that contains the content type to which you want to apply a policy.</span></span>
    
2. <span data-ttu-id="e8853-264">在功能区中，选择**库**或**列表**选项卡\>**库设置**或**列表设置**。</span><span class="sxs-lookup"><span data-stu-id="e8853-264">On the ribbon, choose the **Library** or **List** tab \> **Library Settings** or **List Settings**.</span></span>
    
    <span data-ttu-id="e8853-265">在 SharePoint Online 中，单击**设置**，然后单击**列表设置**或**库设置**。</span><span class="sxs-lookup"><span data-stu-id="e8853-265">In SharePoint Online, click **Settings** and then click **List settings** or **Library settings**.</span></span> 
    
3. <span data-ttu-id="e8853-266">在**权限和管理**下\>**信息管理策略设置**。</span><span class="sxs-lookup"><span data-stu-id="e8853-266">Under **Permissions and Management** \> **Information management policy settings**.</span></span>
  
![在文档库设置页面上的信息管理策略链接](media/9fa6d366-6aab-49e1-a05c-898ac6f536e6.png)
  
4. <span data-ttu-id="e8853-268">验证策略源设置为**内容类型**，并在**内容类型策略**选择您想要应用该策略的内容类型。</span><span class="sxs-lookup"><span data-stu-id="e8853-268">Verify that the policy source is set to **Content Types**, and under **Content Type Policies** select the content type you want to apply the policy to.</span></span> 
    
5. <span data-ttu-id="e8853-269">在**指定策略**下\>**使用网站集策略**，然后选择要应用列表中的策略。</span><span class="sxs-lookup"><span data-stu-id="e8853-269">Under **Specify the Policy** \> **Use a site collection policy**, and then select the policy that you want to apply from the list.</span></span> 
    
    > [!NOTE]
    >  <span data-ttu-id="e8853-270">如果**使用的网站集策略**选项不可用，任何网站集策略具有已不定义的网站集。</span><span class="sxs-lookup"><span data-stu-id="e8853-270">If the **Use a site collection policy** option is not available, no site collection policies have been defined for the site collection.</span></span> 
  
6. <span data-ttu-id="e8853-271">选择"确定"。</span><span class="sxs-lookup"><span data-stu-id="e8853-271">Choose **OK**.</span></span>
    
     <span data-ttu-id="e8853-p131">如果列表或库您正在使用支持多种内容类型进行管理，在**内容类型**下您可以选择要为其指定信息管理策略的内容类型。这会将您导引直接向上方的步骤 5。</span><span class="sxs-lookup"><span data-stu-id="e8853-p131">If the list or library you are working with supports the management of multiple content types, under **Content Types** you can choose the content type for which you want to specify an information management policy. This will take you directly to Step 5 above.</span></span> 
    
## <a name="apply-a-policy-across-site-collections"></a><span data-ttu-id="e8853-274">将策略应用跨网站集</span><span class="sxs-lookup"><span data-stu-id="e8853-274">Apply a policy across site collections</span></span>
<span data-ttu-id="e8853-275"><a name="__toc260646789"> </a></span><span class="sxs-lookup"><span data-stu-id="e8853-275"></span></span>

<span data-ttu-id="e8853-p132">使用托管元数据服务应用程序设置内容类型发布跨网站集共享内容类型。发布的内容类型可帮助您管理内容和元数据始终在网站之间因为可以创建和集中，更新内容类型，可以将更新出发布到多个订阅的网站集或 Web 应用程序。</span><span class="sxs-lookup"><span data-stu-id="e8853-p132">Share content types across site collections by using a Managed Metadata service application to set up content type publishing. Content type publishing helps you manage content and metadata consistently across your sites because content types can be created and updated centrally, and updates can be published out to multiple subscribing site collections or Web applications.</span></span>
  
## <a name="create-a-template-from-an-existing-policy-to-use-across-site-collections"></a><span data-ttu-id="e8853-278">从现有的策略，以使用跨网站集创建模板</span><span class="sxs-lookup"><span data-stu-id="e8853-278">Create a template from an existing policy to use across site collections</span></span>
<span data-ttu-id="e8853-279"><a name="__toc262125409"> </a></span><span class="sxs-lookup"><span data-stu-id="e8853-279"></span></span>

<span data-ttu-id="e8853-p133">您可以定义信息管理策略，然后从它使用所需跨多个网站集创建模板。如果您想要备份的信息策略，或还可作为的备用方法的内容类型发布使用跨网站集应用一个策略，则可以使用此方法。到另一个网站集从一个网站集中导出策略，然后导入其到保存位置或创建的是模板或策略的备份。</span><span class="sxs-lookup"><span data-stu-id="e8853-p133">You can define an information management policy and then create a template from it to use as needed across multiple site collections. This method can be used if you want to have a backup of your information policies, or it can also be used as an alternate method to using content type publishing for applying one policy across site collections. You create a template or backup of the policy by exporting the policy from one site collection and then importing it to a saved location or to another site collection.</span></span>
  
> [!IMPORTANT]
>  <span data-ttu-id="e8853-p134">如果您使用导出/导入功能作为一种使一组策略模板的方式，请记住，策略.xml 文件中存在的唯一标识符。因此，您无法导入该策略网站多次而不更改此唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="e8853-p134">If you using the export/import feature as a way to make a set of policy templates, keep in mind that a unique identifier exists in the policy .xml file. Because of this, you cannot import that policy into a site more than once without changing this unique identifier.</span></span> 
  
### <a name="export-a-policy"></a><span data-ttu-id="e8853-285">导出策略</span><span class="sxs-lookup"><span data-stu-id="e8853-285">Export a policy</span></span>
<span data-ttu-id="e8853-286"><a name="__toc260646790"> </a></span><span class="sxs-lookup"><span data-stu-id="e8853-286"></span></span>

1. <span data-ttu-id="e8853-287">在网站集主页上，选择**设置**![发生的网站设置的小型设置齿轮。](media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png) \> **网站设置**。</span><span class="sxs-lookup"><span data-stu-id="e8853-287">On the site collection home page, choose **Settings**![Small Settings gear that took the place of Site Settings.](media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png)\> **Site Settings**.</span></span>
    
    <span data-ttu-id="e8853-288">中 SharePoint 组连接网站中，单击**设置**，单击**网站内容**，，然后单击**网站设置**。</span><span class="sxs-lookup"><span data-stu-id="e8853-288">In a SharePoint group-connected site, click **Settings**, click **Site Contents**, and then click **Site Settings**.</span></span> 
    
2. <span data-ttu-id="e8853-289">在网站设置页上，在**网站集管理**下\>**内容类型策略模板**。</span><span class="sxs-lookup"><span data-stu-id="e8853-289">On the Site Settings page, under **Site Collection Administration** \> **Content Type Policy Templates**.</span></span> 
  
![在网站设置页的内容类型策略模板链接](media/26d3466a-23ec-443f-88f0-2aaff38e992b.png)
  
3. <span data-ttu-id="e8853-291">选择您想要导出的策略\>滚动到底部\>**导出**。</span><span class="sxs-lookup"><span data-stu-id="e8853-291">Choose the policy you want to export \> scroll to the bottom \> **Export**.</span></span>
    
4. <span data-ttu-id="e8853-p135">在提示符处保存或打开该文件，选择**保存**，，然后选择保存到文件位置。请务必选择可供导入的策略的网站集的位置。</span><span class="sxs-lookup"><span data-stu-id="e8853-p135">At the prompt to save or open the file, choose **Save**, and then select a location to save the file to. Be sure to select a location that is available to the site collections that are importing the policy.</span></span>
    
5. <span data-ttu-id="e8853-294">显示下载完毕对话框中，选择**关闭**。</span><span class="sxs-lookup"><span data-stu-id="e8853-294">When the Download Complete dialog is displayed, choose **Close**.</span></span>
    
### <a name="import-a-policy-to-a-different-site-collection"></a><span data-ttu-id="e8853-295">导入到不同的网站集的策略</span><span class="sxs-lookup"><span data-stu-id="e8853-295">Import a policy to a different site collection</span></span>
<span data-ttu-id="e8853-296"><a name="__toc260646791"> </a></span><span class="sxs-lookup"><span data-stu-id="e8853-296"></span></span>

<span data-ttu-id="e8853-p136">导入的信息管理策略，可以将其应用于多个内容类型在任何给定的网站集内网站或列表级别。此操作的好处是两种： 您无需重新定义并对每个内容类型应用策略和您可以更轻松地管理策略修改，通过更改只需一个位置中的策略。</span><span class="sxs-lookup"><span data-stu-id="e8853-p136">Importing an information management policy enables you to apply it to multiple content types at the site or list level within any given site collection. The benefits of doing this are twofold: you don't have to re-define and apply the policy on each content type, and you can more easily manage policy modifications by making changes to the policy in just one place.</span></span>
  
1. <span data-ttu-id="e8853-299">在您要向其应用策略的网站集的主页上，选择**设置**![发生的网站设置的小型设置齿轮。](media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png) \> **网站设置**。</span><span class="sxs-lookup"><span data-stu-id="e8853-299">On the home page of the site collection to which you want to apply the policy, choose **Settings**![Small Settings gear that took the place of Site Settings.](media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png)\> **Site Settings**.</span></span>
    
    <span data-ttu-id="e8853-300">中 SharePoint 组连接网站中，单击**设置**，单击**网站内容**，，然后单击**网站设置**。</span><span class="sxs-lookup"><span data-stu-id="e8853-300">In a SharePoint group-connected site, click **Settings**, click **Site Contents**, and then click **Site Settings**.</span></span> 
    
2. <span data-ttu-id="e8853-301">在网站设置页上，在**网站集管理**下\>**内容类型策略模板**。</span><span class="sxs-lookup"><span data-stu-id="e8853-301">On the Site Settings page, under **Site Collection Administration** \> **Content Type Policy Templates**.</span></span>
    
3. <span data-ttu-id="e8853-302">在策略页上\>**导入** \> **浏览**以找到该 XML 文件的策略。</span><span class="sxs-lookup"><span data-stu-id="e8853-302">On the Policies page \> **Import** \> **Browse** to find the XML file for the policy.</span></span> 
    
4. <span data-ttu-id="e8853-303">选择在其中保存策略的 XML 文件\>**打开**。</span><span class="sxs-lookup"><span data-stu-id="e8853-303">Select the XML file in which the policy has been saved \> **Open**.</span></span> 
    
5. <span data-ttu-id="e8853-304">在导入网站集策略页上\>**导入**策略添加到网站集。</span><span class="sxs-lookup"><span data-stu-id="e8853-304">On the Import a Site Collection Policy page \> **Import** to add the policy to the site collection.</span></span> 
    
<span data-ttu-id="e8853-305">现在，您导入的策略都可以应用于网站或列表级别的一个或多个内容类型。</span><span class="sxs-lookup"><span data-stu-id="e8853-305">Your imported policy can now be applied to one or many content types at the site or list level.</span></span> 
  
[<span data-ttu-id="e8853-306">信息管理策略，组织到多长时间保留内容、 审核人执行操作的内容，以及添加条形码控件或标签文档。策略可以帮助强制实施符合法律和政府法规或内部业务流程。作为管理员，您可以设置策略以控制如何跟踪文档和文档的保留多长时间。您可以在网站层次结构，从最全面的三个不同的位置创建信息管理策略可以向最窄： 创建策略，以使用网站集中的多个内容类型。创建网站内容类型的策略。创建列表或库的策略。有关详细信息，请参阅 Introduction to 信息管理策略。</span><span class="sxs-lookup"><span data-stu-id="e8853-306">Information management policies enable your organization to control how long to retain content, to audit what people do with content, and to add barcodes or labels to documents. A policy can help enforce compliance with legal and governmental regulations or internal business processes. As an administrator, you can set up a policy to control how to track documents and how long to retain documents.You can create an information management policy can at three different locations in the site hierarchy, from the broadest to the narrowest:Create a policy to use on multiple content types within a site collection.Create a policy for a site content type.Create a policy for a list or library.For more information, see Introduction to information management policies.</span></span>](create-info-mgmt-policies.md#__top)
  

