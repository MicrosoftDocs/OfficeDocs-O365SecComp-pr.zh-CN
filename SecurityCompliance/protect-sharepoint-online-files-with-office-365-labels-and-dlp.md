---
title: 使用 Office 365 标签和 DLP 保护 SharePoint Online 文件
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/12/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_Solutions
ms.assetid: c9f837af-8d71-4df1-a285-dedb1c5618b3
description: 摘要：为具有各级别信息保护的 SharePoint Online 团队网站应用 Office 365 标签和数据丢失防护 (DLP) 策略。
ms.openlocfilehash: fd2fedf23b4e65bd32642b8528548f8a85533051
ms.sourcegitcommit: 6ff0233b5a1a07595f8b4d55db6b1327bcaa174c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/15/2019
ms.locfileid: "28023431"
---
# <a name="protect-sharepoint-online-files-with-office-365-labels-and-dlp"></a><span data-ttu-id="5557b-103">使用 Office 365 标签和 DLP 保护 SharePoint Online 文件</span><span class="sxs-lookup"><span data-stu-id="5557b-103">Protect SharePoint Online files with Office 365 labels and DLP</span></span>

 <span data-ttu-id="5557b-104">**摘要：** 为具有各级别信息保护的 SharePoint Online 团队网站应用 Office 365 标签和数据丢失防护 (DLP) 策略。</span><span class="sxs-lookup"><span data-stu-id="5557b-104">**Summary:** Apply Office 365 labels and data loss prevention (DLP) policies for SharePoint Online team sites with various levels of information protection.</span></span>
  
<span data-ttu-id="5557b-p101">使用本文中的步骤针对基线、敏感和高度机密的 SharePoint Online 团队网站设计并部署 Office 365 标签和 DLP 策略。有关三层保护的详细信息，请参阅[保护 SharePoint Online 网站和文件](secure-sharepoint-online-sites-and-files.md)。</span><span class="sxs-lookup"><span data-stu-id="5557b-p101">Use the steps in this article to design and deploy Office 365 labels and DLP policies for baseline, sensitive, and highly confidential SharePoint Online team sites. For more information about these three tiers of protection, see [Secure SharePoint Online sites and files](secure-sharepoint-online-sites-and-files.md).</span></span>
  
## <a name="how-this-works"></a><span data-ttu-id="5557b-107">工作原理</span><span class="sxs-lookup"><span data-stu-id="5557b-107">How this works</span></span>
1. <span data-ttu-id="5557b-p102">创建并发布所需标签。最长可能需要 12 小时，才能发布这些标签。</span><span class="sxs-lookup"><span data-stu-id="5557b-p102">Create the desired labels and publish these. It can take up to 12 hours for these to be published.</span></span>
2. <span data-ttu-id="5557b-110">对于所需 SharePoint 网站，将文档库设置编辑为，向库中项应用标签。</span><span class="sxs-lookup"><span data-stu-id="5557b-110">For the desired SharePoint sites, edit the document library settings to apply a label to items in the library.</span></span>
3. <span data-ttu-id="5557b-111">创建根据标签执行操作的 DLP 策略。</span><span class="sxs-lookup"><span data-stu-id="5557b-111">Create DLP policies to take action based on the labels.</span></span>

<span data-ttu-id="5557b-p103">当用户向库中添加某个文档时，默认情况下该文档会收到分配的标签。如果需要的话，用户可以更改标签。当用户在组织外部共享文档时，DLP 将检查是否分配了标签，如果某个 DLP 策略与该标签匹配，则采取行动。DLP 还将查找其他策略匹配，例如保护包含信用卡号的文件（如果配置了这类型的策略）。</span><span class="sxs-lookup"><span data-stu-id="5557b-p103">When users add a document to the library, the document will receive the assigned label by default. Users can change the label, if needed. When a user shares a document outside the organization, DLP will check to see if a label is assigned and take action if a DLP policy matches the label. DLP will look for other policy matches as well, such as protecting files with credit card numbers if this type of policy is configured.</span></span> 

## <a name="office-365-labels-for-your-sharepoint-online-sites"></a><span data-ttu-id="5557b-116">SharePoint Online 网站的 Office 365 标签</span><span class="sxs-lookup"><span data-stu-id="5557b-116">Office 365 labels for your SharePoint Online sites</span></span>

<span data-ttu-id="5557b-117">创建并向 SharePoint Online 团队网站分配 Office 365 标签分以下三个阶段。</span><span class="sxs-lookup"><span data-stu-id="5557b-117">There are three phases to creating and then assigning Office 365 labels to SharePoint Online team sites.</span></span>
  
### <a name="phase-1-determine-the-office-365-label-names"></a><span data-ttu-id="5557b-118">阶段 1：确定 Office 365 标签名称</span><span class="sxs-lookup"><span data-stu-id="5557b-118">Phase 1: Determine the Office 365 label names</span></span>

<span data-ttu-id="5557b-p104">在此阶段，对于应用到 SharePoint Online 团队网站的四个级别的信息保护，确定 Office 365 标签的名称。 下表列出了针对每个级别建议的名称。</span><span class="sxs-lookup"><span data-stu-id="5557b-p104">In this phase, you determine the names of your Office 365 labels for the four levels of information protection applied to SharePoint Online team sites. The following table lists the recommended names for each level.</span></span>
  
|<span data-ttu-id="5557b-121">**SharePoint Online 团队网站保护级别**</span><span class="sxs-lookup"><span data-stu-id="5557b-121">**SharePoint Online team site protection level**</span></span>|<span data-ttu-id="5557b-122">**标签名称**</span><span class="sxs-lookup"><span data-stu-id="5557b-122">**Label name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="5557b-123">基线 - 公用</span><span class="sxs-lookup"><span data-stu-id="5557b-123">Baseline-Public</span></span>  <br/> |<span data-ttu-id="5557b-124">内部公用</span><span class="sxs-lookup"><span data-stu-id="5557b-124">Internal public</span></span>  <br/> |
|<span data-ttu-id="5557b-125">基线 - 专用</span><span class="sxs-lookup"><span data-stu-id="5557b-125">Baseline-Private</span></span>  <br/> |<span data-ttu-id="5557b-126">Private</span><span class="sxs-lookup"><span data-stu-id="5557b-126">Private</span></span>  <br/> |
|<span data-ttu-id="5557b-127">敏感</span><span class="sxs-lookup"><span data-stu-id="5557b-127">Sensitive</span></span>  <br/> |<span data-ttu-id="5557b-128">敏感</span><span class="sxs-lookup"><span data-stu-id="5557b-128">Sensitive</span></span>  <br/> |
|<span data-ttu-id="5557b-129">高度机密</span><span class="sxs-lookup"><span data-stu-id="5557b-129">Highly Confidential</span></span>  <br/> |<span data-ttu-id="5557b-130">高度机密</span><span class="sxs-lookup"><span data-stu-id="5557b-130">Highly Confidential</span></span>  <br/> |
   
### <a name="phase-2-create-the-office-365-labels"></a><span data-ttu-id="5557b-131">阶段 2：创建 Office 365 标签</span><span class="sxs-lookup"><span data-stu-id="5557b-131">Phase 2: Create the Office 365 labels</span></span>

<span data-ttu-id="5557b-132">在此阶段中，针对不同的信息保护级别创建并发布确定的标签。</span><span class="sxs-lookup"><span data-stu-id="5557b-132">In this phase, you create and then publish your determined labels for the different levels of information protection.</span></span>
  
<span data-ttu-id="5557b-133">若要创建标签，可以使用 Office 365 管理中心或 Microsoft PowerShell。</span><span class="sxs-lookup"><span data-stu-id="5557b-133">To create the labels, you can use the Office 365 Admin center or Microsoft PowerShell.</span></span>
  
### <a name="create-office-365-labels-with-the-office-365-admin-center"></a><span data-ttu-id="5557b-134">使用 Office 365 管理中心创建 Office 365 标签</span><span class="sxs-lookup"><span data-stu-id="5557b-134">Create Office 365 labels with the Office 365 Admin center</span></span>

1. <span data-ttu-id="5557b-p105">使用具有安全管理员或公司管理员角色的帐户登录到 Office 365 门户。有关帮助信息，请参阅[在何处登录到 Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4)。</span><span class="sxs-lookup"><span data-stu-id="5557b-p105">Sign in to the Office 365 portal with an account that has the Security Administrator or Company Administrator role. For help, see [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="5557b-137">在“Microsoft Office 主页”\*\*\*\* 标签页中，单击“管理员”磁贴\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5557b-137">From the **Microsoft Office Home** tab, click the **Admin** tile.</span></span>
    
3. <span data-ttu-id="5557b-138">在浏览器的新“Office 管理中心”\*\*\*\* 标签页中，单击“管理中心”>“安全&amp;合规性”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5557b-138">From the new **Office Admin center** tab of your browser, click **Admin centers > Security &amp; Compliance**.</span></span>
    
4. <span data-ttu-id="5557b-139">在浏览器的新“主页 -安全&amp;合规性”\*\*\*\* 标签页中，单击“分类”>“标签”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5557b-139">From the new **Home - Security &amp; Compliance** tab of your browser, click **Classifications > Labels**.</span></span>
    
5. <span data-ttu-id="5557b-140">从“主页”>“标签”\*\*\*\* 窗格中，单击“保留”\*\*\*\*”选项卡，然后再单击“创建标签”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5557b-140">From the **Home > Labels** pane, click the **Retention** tab, and then click **Create a label**.</span></span>
    
6. <span data-ttu-id="5557b-141">在“命名标签”\*\*\*\* 窗格中，键入标签的名称和管理员及用户描述，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5557b-141">On the **Name your label** pane, type the name of the label and a description for admins and users, and then click **Next**.</span></span>

7. <span data-ttu-id="5557b-142">在“标签设置”窗格中，单击“下一步”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5557b-142">On the **Label settings** pane, click **Next**.</span></span>
    
8. <span data-ttu-id="5557b-143">在“查看设置”\*\*\*\* 窗格中，单击“创建”\*\*\*\*，然后单击“关闭”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5557b-143">On the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>
    
9. <span data-ttu-id="5557b-144">对其他标签重复步骤 5-8。</span><span class="sxs-lookup"><span data-stu-id="5557b-144">Repeat steps 5-8 for your additional labels.</span></span>
    
### <a name="create-office-365-labels-with-powershell"></a><span data-ttu-id="5557b-145">使用 PowerShell 创建 Office 365 标签</span><span class="sxs-lookup"><span data-stu-id="5557b-145">Create Office 365 labels with PowerShell</span></span>

1. <span data-ttu-id="5557b-146">[使用远程 PowerShell 连接到 Office 365 安全性&amp;合规性中心](http://go.microsoft.com/fwlink/?LinkID=799771&amp;clcid=0x409)，并指定具有安全管理员或公司管理员角色的帐户凭据。</span><span class="sxs-lookup"><span data-stu-id="5557b-146">[Connect to the Office 365 Security &amp; Compliance Center using remote PowerShell](http://go.microsoft.com/fwlink/?LinkID=799771&amp;clcid=0x409) and specify the credentials of an account that has the Security Administrator or Company Administrator role.</span></span>
    
2. <span data-ttu-id="5557b-147">填写标签名称列表，然后在 PowerShell 命令提示符下运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="5557b-147">Fill out the list of label names, and then run these commands at the PowerShell command prompt:</span></span>
    
  ```
  $labelNames=@(<list of label names, each enclosed in quotes and separated by commas>)
ForEach ($element in $labelNames){ New-ComplianceTag -Name $element }
  ```

### <a name="publish-your-new-labels"></a><span data-ttu-id="5557b-148">发布新标签</span><span class="sxs-lookup"><span data-stu-id="5557b-148">Publish your new labels</span></span>

<span data-ttu-id="5557b-149">接下来，使用以下步骤发布新的 Office 365 标签。</span><span class="sxs-lookup"><span data-stu-id="5557b-149">Next, use these steps to publish the new Office 365 labels.</span></span>
  
1. <span data-ttu-id="5557b-150">在“安全性&amp;合规性”中心的“主页”>“标签”\*\*\*\* 窗格中，单击“保留”\*\*\*\* 选项卡，然后再单击“发布标签”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5557b-150">From the **Home > Labels** pane of the Security &amp; Compliance Center, click the **Retention** tab, and then click **Publish labels**.</span></span>
    
2. <span data-ttu-id="5557b-151">在“选择要发布的标签”\*\*\*\* 窗格中，单击“选择要发布的标签”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5557b-151">On the **Choose labels to publish** pane, click **Choose labels to publish**.</span></span>
    
3. <span data-ttu-id="5557b-152">在“选择标签”窗格中，单击“添加”并选择全部四个标签\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5557b-152">On the **Choose labels** pane, click **Add** and select all four labels.</span></span>
    
4. <span data-ttu-id="5557b-153">单击“完成”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5557b-153">Click **Done**.</span></span>
    
5. <span data-ttu-id="5557b-154">在“选择要发布的标签”窗格中，单击“下一步”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5557b-154">On the **Choose labels to publish** pane, click **Next**.</span></span>
    
6. <span data-ttu-id="5557b-155">在“选择位置”窗格中，单击“下一步”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5557b-155">On the **Choose locations** pane, click **Next**.</span></span>
    
7. <span data-ttu-id="5557b-156">在“命名策略”\*\*\*\* 窗格中，在“名称”\*\*\*\* 中键入标签组的名称，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5557b-156">On the **Name your policy** pane, type a name for your set of labels in **Name**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="5557b-157">在“查看设置”\*\*\*\* 窗格中，单击“发布标签”\*\*\*\*，然后单击“关闭”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5557b-157">On the **Review your settings** pane, click **Publish labels**, and then click **Close**.</span></span>

    
### <a name="phase-3-apply-the-office-365-labels-to-your-sharepoint-online-sites"></a><span data-ttu-id="5557b-158">阶段 3：将 Office 365 标签应用到 SharePoint Online 网站</span><span class="sxs-lookup"><span data-stu-id="5557b-158">Phase 3: Apply the Office 365 labels to your SharePoint Online sites</span></span>

<span data-ttu-id="5557b-159">使用这些步骤将 Office 365 标签应用到 SharePoint Online 团队网站的文档文件夹。</span><span class="sxs-lookup"><span data-stu-id="5557b-159">Use these steps to apply the Office 365 labels to the documents folders of your SharePoint Online team sites.</span></span>
  
1. <span data-ttu-id="5557b-160">在浏览器的“Microsoft Office 主页”标签页中，单击“SharePoint”磁贴\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5557b-160">From the **Microsoft Office Home** tab of your browser, click the **SharePoint** tile.</span></span>
    
2. <span data-ttu-id="5557b-161">在浏览器的新“SharePoint”标签页中，单击需要分配 Office 365 标签的网站\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5557b-161">On the new **SharePoint** tab in your browser, click a site that needs an Office 365 label assigned.</span></span>
    
3. <span data-ttu-id="5557b-162">在浏览器的新“SharePoint 网站”标签页中，单击“文档”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5557b-162">In the new SharePoint site tab of your browser, click **Documents**.</span></span>
    
4. <span data-ttu-id="5557b-163">单击设置图标，然后单击“库设置”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5557b-163">Click the settings icon, and then click **Library settings**.</span></span>
    
5. <span data-ttu-id="5557b-164">在“权限和管理”下，单击“向此库中的项应用标签”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5557b-164">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
    
6. <span data-ttu-id="5557b-165">在“设置-应用标签”\*\*\*\* 中，选择相应的标签，然后单击“保存”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5557b-165">In **Settings-Apply Label**, select the appropriate label, and then click **Save**.</span></span>
    
7. <span data-ttu-id="5557b-166">关闭 SharePoint Online 网站的选项卡。</span><span class="sxs-lookup"><span data-stu-id="5557b-166">Close the tab for the SharePoint Online site.</span></span>
    
8. <span data-ttu-id="5557b-167">重复步骤 3-8，将 Office 365 标签分配给其他 SharePoint Online 网站。</span><span class="sxs-lookup"><span data-stu-id="5557b-167">Repeat steps 3-8 to assign Office 365 labels to your additional SharePoint Online sites.</span></span>
    
<span data-ttu-id="5557b-168">下面是生成的配置。</span><span class="sxs-lookup"><span data-stu-id="5557b-168">Here is your resulting configuration.</span></span>
  
![四种类型的 SharePoint Online 团队网站的 Office 365 标签。](media/e0a4fdd2-1c30-4d93-8af4-a6f0c6c29966.png)
  
## <a name="dlp-policies-for-your-sharepoint-online-sites"></a><span data-ttu-id="5557b-170">适用于 SharePoint Online 网站的 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="5557b-170">DLP policies for your SharePoint Online sites</span></span>

<span data-ttu-id="5557b-171">使用以下步骤配置 DLP 策略，该策略可在用户在组织外共享关于 SharePoint Online 敏感团队网站的文档时进行通知。</span><span class="sxs-lookup"><span data-stu-id="5557b-171">Use these steps to configure a DLP policy that notifies users when they share a document on a SharePoint Online sensitive team site outside the organization.</span></span>

1. <span data-ttu-id="5557b-172">在“Microsoft Office 主页”\*\*\*\* 标签页中，单击“管理员”磁贴\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5557b-172">From the **Microsoft Office Home** tab, click the **Admin** tile.</span></span>
    
2. <span data-ttu-id="5557b-173">在浏览器的新“Office 管理中心”\*\*\*\* 标签页中，单击“管理中心”>“安全&amp;合规性”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5557b-173">From the new **Office Admin center** tab of your browser, click **Admin centers > Security &amp; Compliance**.</span></span>
    
3. <span data-ttu-id="5557b-174">在浏览器的新“安全&amp;合规性”\*\*\*\* 标签页中，单击“数据丢失防护”>“策略”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5557b-174">On the new **Security &amp; Compliance** tab in your browser, click **Data loss prevention > Policy**.</span></span>
    
4. <span data-ttu-id="5557b-175">在“数据丢失防护”窗格中，单击“+ 创建策略”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5557b-175">In the **Data loss prevention** pane, click **+ Create a policy**.</span></span>
    
5. <span data-ttu-id="5557b-176">在“从模板开始或创建自定义策略”\*\*\*\* 窗格中，单击“自定义”\*\*\*\*，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5557b-176">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>
    
5. <span data-ttu-id="5557b-177">在“命名策略”\*\*\*\* 窗格中，在“名称”\*\*\*\* 中键入敏感级别 DLP 策略的名称，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5557b-177">In the **Name your policy** pane, type the name for the sensitive level DLP policy in **Name**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="5557b-178">在“选择位置”窗格中，单击“允许选择特定位置”，然后单击“下一步”\*\*\*\*\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5557b-178">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="5557b-179">在位置列表中，禁用“Exchange 电子邮件”\*\*\*\* 和“OneDrive 帐户位置”\*\*\*\*，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5557b-179">In the list of locations, disable the **Exchange email** and **OneDrive accounts** locations, and then click **Next**.</span></span>
    
8. <span data-ttu-id="5557b-180">在“**自定义要保护的敏感信息类型**”窗格中，单击“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="5557b-180">In the **Customize the types of sensitive info you want to protect** pane, click **Edit**.</span></span>
    
9. <span data-ttu-id="5557b-181">在“选择要保护的内容类型”\*\*\*\* 窗格中，单击下拉框中的“添加”\*\*\*\*，然后单击“标签”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5557b-181">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Labels**.</span></span>
    
10. <span data-ttu-id="5557b-182">在“标签”\*\*\*\* 窗格中，单击“+ 添加”\*\*\*\*，选择“敏感”\*\*\*\* 标签，然后依次单击“添加”\*\*\*\* 和“完成”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5557b-182">In the **Labels** pane, click **+ Add**, select the **Sensitive** label, click **Add**, and then click **Done**.</span></span>
    
11. <span data-ttu-id="5557b-183">在“选择要保护的内容类型”窗格中，单击“保存”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5557b-183">In the **Choose the types of content to protect** pane, click **Save**.</span></span>
    
12. <span data-ttu-id="5557b-184">在“**自定义要保护的敏感信息类型**”窗格中，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="5557b-184">In the **Customize the types of sensitive info you want to protect** pane, click **Next**.</span></span>

13. <span data-ttu-id="5557b-185">在“如果检测到敏感信息，希望采取什么操作?”窗格中，单击“自定义提示和电子邮件”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5557b-185">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>
    
14. <span data-ttu-id="5557b-186">在“自定义策略提示和电子邮件通知”\*\*\*\* 窗格中，单击“自定义策略提示文本”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5557b-186">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>
    
15. <span data-ttu-id="5557b-187">在文本框中，键入或粘贴以下提示之一，具体取决于是否已实现 Azure 信息保护来保护高度机密文件：</span><span class="sxs-lookup"><span data-stu-id="5557b-187">In the text box, type or paste in one of the following tips, depending on if you implemented Azure Information Protection to protect highly confidential files:</span></span>
    
  - <span data-ttu-id="5557b-p106">要与组织外部的用户共享，请下载并打开文件。 依次单击“文件”、“保护文档”、“使用密码加密”，然后指定强密码。 通过单独的电子邮件或其他通信方式发送密码。</span><span class="sxs-lookup"><span data-stu-id="5557b-p106">To share with a user outside the organization, download the file and then open it. Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password. Send the password in a separate email or other means of communication.</span></span>
  - <span data-ttu-id="5557b-p107">高度机密文件已获加密保护。只有 IT 部门向其授予对这些文件的相应权限的外部用户，才能读取这些文件。</span><span class="sxs-lookup"><span data-stu-id="5557b-p107">Highly confidential files are protected with encryption. Only external users who are granted permissions to these files by your IT department can read them.</span></span>
    
    <span data-ttu-id="5557b-193">或键入或粘贴自己的策略提示，指示用户如何在组织外共享文件。</span><span class="sxs-lookup"><span data-stu-id="5557b-193">Alternately, type or paste in your own policy tip that instructs users on how to share a file outside your organization.</span></span>
    
16. <span data-ttu-id="5557b-194">单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5557b-194">Click **OK**.</span></span>
    
17. <span data-ttu-id="5557b-195">在“如果检测到敏感信息，希望采取什么操作?”\*\*\*\* 窗格中，单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5557b-195">In the **What do you want to do if we detect sensitive info?** pane, click **Next**.</span></span>
    
18. <span data-ttu-id="5557b-196">在“是否希望立即启用策略或先进行测试?”\*\*\*\* 窗格中，单击“是，立即启用”\*\*\*\*，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5557b-196">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>
    
19. <span data-ttu-id="5557b-197">在“查看设置”\*\*\*\* 窗格中，单击“创建”\*\*\*\*，然后单击“关闭”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5557b-197">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>
    
<span data-ttu-id="5557b-198">以下为敏感 SharePoint Online 团队网站的配置结果。</span><span class="sxs-lookup"><span data-stu-id="5557b-198">Here is your resulting configuration for sensitive SharePoint Online team sites.</span></span>
  
![使用敏感 Office 365 标签的独立 SharePoint Online 团队网站的 DLP 策略。](media/2ff4cc53-87a8-43e3-b637-3068d88409f3.png)
  
<span data-ttu-id="5557b-200">接下来，使用以下步骤配置 DLP 策略，该策略可在用户在组织外共享关于 SharePoint Online 高度机密团队网站的文档时阻止用户。</span><span class="sxs-lookup"><span data-stu-id="5557b-200">Next, use these steps to configure a DLP policy that blocks users when they share a document on a SharePoint Online highly confidential team site outside the organization.</span></span>
  
1. <span data-ttu-id="5557b-201">在浏览器的“Microsoft Office 主页”\*\*\*\* 标签页中，单击“安全&amp;合规性”\*\*\*\* 磁贴。</span><span class="sxs-lookup"><span data-stu-id="5557b-201">From the **Microsoft Office Home** tab in your browser, click the **Security &amp; Compliance** tile.</span></span>
    
2. <span data-ttu-id="5557b-202">在浏览器的新“安全&amp;合规性”\*\*\*\* 标签页中，单击“数据丢失防护”>“策略”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5557b-202">On the new **Security &amp; Compliance** tab in your browser, click **Data loss prevention > Policy**.</span></span>
    
3. <span data-ttu-id="5557b-203">在“数据丢失防护”窗格中，单击“+ 创建策略”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5557b-203">In the **Data loss prevention** pane, click **+ Create a policy**.</span></span>
    
4. <span data-ttu-id="5557b-204">在“从模板开始或创建自定义策略”\*\*\*\* 窗格中，单击“自定义”\*\*\*\*，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5557b-204">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>
    
5. <span data-ttu-id="5557b-205">在“命名策略”\*\*\*\* 窗格中，在“名称”\*\*\*\* 中键入高度敏感级别 DLP 策略的名称，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5557b-205">In the **Name your policy** pane, type the name for the highly sensitive level DLP policy in **Name**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="5557b-206">在“选择位置”窗格中，单击“允许选择特定位置”，然后单击“下一步”\*\*\*\*\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5557b-206">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="5557b-207">在位置列表中，禁用“Exchange 电子邮件”\*\*\*\* 和“OneDrive 帐户位置”\*\*\*\*，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5557b-207">In the list of locations, disable the **Exchange email** and **OneDrive accounts** locations, and then click **Next**.</span></span>
    
8. <span data-ttu-id="5557b-208">在“自定义要保护的敏感信息类型”窗格中，单击“编辑”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5557b-208">In the **Customize the types of sensitive info you want to protect** pane, click **Edit**.</span></span>
    
9. <span data-ttu-id="5557b-209">在“选择要保护的内容类型”\*\*\*\* 窗格中，单击下拉框中的“添加”\*\*\*\*，然后单击“标签”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5557b-209">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Labels**.</span></span>
    
10. <span data-ttu-id="5557b-210">在“标签”\*\*\*\* 窗格中，单击“+ 添加”\*\*\*\*，选择“高度机密”标签\*\*\*\*，然后依次单击“添加”\*\*\*\* 和“完成”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5557b-210">In the **Labels** pane, click **+ Add**, select the **Highly Confidential** label, click **Add**, and then click **Done**.</span></span>
    
11. <span data-ttu-id="5557b-211">在“选择要保护的内容类型”窗格中，单击“保存”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5557b-211">In the **Choose the types of content to protect** pane, click **Save**.</span></span>
    
12. <span data-ttu-id="5557b-212">在“自定义要保护的敏感信息类型”窗格中，单击“下一步”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5557b-212">In the **Customize the types of sensitive info you want to protect** pane, click **Next**.</span></span>
    
13. <span data-ttu-id="5557b-213">在“如果检测到敏感信息，希望采取什么操作?”窗格中，单击“自定义提示和电子邮件”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5557b-213">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>
    
14. <span data-ttu-id="5557b-214">在“自定义策略提示和电子邮件通知”窗格中，单击“自定义策略提示文本”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5557b-214">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>
    
15. <span data-ttu-id="5557b-215">在文本框中，键入或粘贴以下内容：</span><span class="sxs-lookup"><span data-stu-id="5557b-215">In the text box, type or paste in the following:</span></span>
    
  - <span data-ttu-id="5557b-p108">要与组织外部的用户共享，请下载并打开文件。 依次单击“文件”、“保护文档”、“使用密码加密”，然后指定强密码。 通过单独的电子邮件或其他通信方式发送密码。</span><span class="sxs-lookup"><span data-stu-id="5557b-p108">To share with a user outside the organization, download the file and then open it. Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password. Send the password in a separate email or other means of communication.</span></span>
    
    <span data-ttu-id="5557b-219">或者，键入或粘贴自己的策略提示，指示用户如何在组织外共享文件。</span><span class="sxs-lookup"><span data-stu-id="5557b-219">Alternately, type or paste in your own policy tip that instructs users on how to share a file outside your organization.</span></span>
    
16. <span data-ttu-id="5557b-220">单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5557b-220">Click **OK**.</span></span>
    
17. <span data-ttu-id="5557b-221">在“如果检测到敏感信息，希望采取什么操作?”\*\*\*\* 窗格中，单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5557b-221">In the **What do you want to do if we detect sensitive info?** pane, click **Next**.</span></span>
    
18. <span data-ttu-id="5557b-222">在“是否希望立即启用策略或先进行测试?”\*\*\*\* 窗格中，单击“是，立即启用”\*\*\*\*，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5557b-222">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>
    
19. <span data-ttu-id="5557b-223">在“查看设置”\*\*\*\* 窗格中，单击“创建”\*\*\*\*，然后单击“关闭”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5557b-223">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>
    
<span data-ttu-id="5557b-224">以下为高度机密的 SharePoint Online 团队网站的配置结果。</span><span class="sxs-lookup"><span data-stu-id="5557b-224">Here is your resulting configuration for high confidentiality SharePoint Online team sites.</span></span>
  
![使用高度机密 Office 365 标签的独立 SharePoint Online 团队网站的 DLP 策略。](media/f705d3d0-23c9-4333-8b70-ad3b91f835ea.png)
  
## <a name="next-step"></a><span data-ttu-id="5557b-226">后续步骤</span><span class="sxs-lookup"><span data-stu-id="5557b-226">Next step</span></span>

[<span data-ttu-id="5557b-227">使用 Azure 信息保护来保护 SharePoint Online 文件</span><span class="sxs-lookup"><span data-stu-id="5557b-227">Protect SharePoint Online files with Azure Information Protection</span></span>](protect-sharepoint-online-files-with-azure-information-protection.md)
    
## <a name="see-also"></a><span data-ttu-id="5557b-228">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5557b-228">See Also</span></span>

[<span data-ttu-id="5557b-229">保护 SharePoint Online 网站和文件</span><span class="sxs-lookup"><span data-stu-id="5557b-229">Secure SharePoint Online sites and files</span></span>](secure-sharepoint-online-sites-and-files.md)
  
[<span data-ttu-id="5557b-230">在开发/测试环境中保护 SharePoint Online 网站</span><span class="sxs-lookup"><span data-stu-id="5557b-230">Secure SharePoint Online sites in a dev/test environment</span></span>](secure-sharepoint-online-sites-in-a-dev-test-environment.md)
  
[<span data-ttu-id="5557b-231">Microsoft 针对政治宣传活动、非营利组织和其他敏捷性组织的安全指南</span><span class="sxs-lookup"><span data-stu-id="5557b-231">Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations</span></span>](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)
  
[<span data-ttu-id="5557b-232">云应用和混合解决方案</span><span class="sxs-lookup"><span data-stu-id="5557b-232">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)


