---
title: 使用保留标签和 DLP 保护 SharePoint Online 文件
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/29/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_Solutions
ms.assetid: c9f837af-8d71-4df1-a285-dedb1c5618b3
description: 摘要：为具有各种信息保护级别的 SharePoint Online 团队网站应用保留标签和数据丢失防护 (DLP) 策略。
ms.openlocfilehash: 118911f6430c9ae79dec1fa4a32cd0ba8fa536da
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2019
ms.locfileid: "34156894"
---
# <a name="protect-sharepoint-online-files-with-retention-labels-and-dlp"></a><span data-ttu-id="a2737-103">使用保留标签和 DLP 保护 SharePoint Online 文件</span><span class="sxs-lookup"><span data-stu-id="a2737-103">Protect SharePoint Online files with retention labels and DLP</span></span>

 <span data-ttu-id="a2737-104">**摘要：** 为具有各种信息保护级别的 SharePoint Online 团队网站应用保留标签和数据丢失防护 (DLP) 策略。</span><span class="sxs-lookup"><span data-stu-id="a2737-104">**Summary:** Apply retention labels and data loss prevention (DLP) policies for SharePoint Online team sites with various levels of information protection.</span></span>
  
<span data-ttu-id="a2737-105">使用本文中的步骤针对基线、敏感和高度机密的 SharePoint Online 团队网站设计并部署保留标签和 DLP 策略。</span><span class="sxs-lookup"><span data-stu-id="a2737-105">Use the steps in this article to design and deploy retention labels and DLP policies for baseline, sensitive, and highly confidential SharePoint Online team sites.</span></span> <span data-ttu-id="a2737-106">有关三层保护的详细信息，请参阅[保护 SharePoint Online 网站和文件](secure-sharepoint-online-sites-and-files.md)。</span><span class="sxs-lookup"><span data-stu-id="a2737-106">For more information about these three tiers of protection, see [Secure SharePoint Online sites and files](secure-sharepoint-online-sites-and-files.md).</span></span>
  
## <a name="how-this-works"></a><span data-ttu-id="a2737-107">工作原理</span><span class="sxs-lookup"><span data-stu-id="a2737-107">How this works</span></span>
1. <span data-ttu-id="a2737-108">创建所需的保留标签并发布这些标签。</span><span class="sxs-lookup"><span data-stu-id="a2737-108">Create the desired retention labels and publish these.</span></span> <span data-ttu-id="a2737-109">最多可能需要 12 个小时来发布这些标签。</span><span class="sxs-lookup"><span data-stu-id="a2737-109">It can take up to 12 hours for these to be published.</span></span>
2. <span data-ttu-id="a2737-110">对于所需的 SharePoint 网站，将文档库设置编辑为向库中项目应用所需的保留标签。</span><span class="sxs-lookup"><span data-stu-id="a2737-110">For the desired SharePoint sites, edit the document library settings to apply the desired retention labels to items in the library.</span></span>
3. <span data-ttu-id="a2737-111">创建 DLP 策略以根据保留标签执行相关操作。</span><span class="sxs-lookup"><span data-stu-id="a2737-111">Create DLP policies to take action based on the retention labels.</span></span>

<span data-ttu-id="a2737-112">当用户将文档添加到库时，默认情况下该文档将接收分配的保留标签。</span><span class="sxs-lookup"><span data-stu-id="a2737-112">When users add a document to the library, the document will receive the assigned retention label by default.</span></span> <span data-ttu-id="a2737-113">用户可以根据需要更改标签。</span><span class="sxs-lookup"><span data-stu-id="a2737-113">Users can change the label, if needed.</span></span> <span data-ttu-id="a2737-114">当用户在组织外共享文档时，DLP 将检查是否已分配标签，并在 DLP 策略与标签匹配时执行相关操作。</span><span class="sxs-lookup"><span data-stu-id="a2737-114">When a user shares a document outside the organization, DLP will check to see if a label is assigned and take action if a DLP policy matches the label.</span></span> <span data-ttu-id="a2737-115">DLP 还将查找其他策略匹配，例如，如果配置了此类策略，则使用信用卡号保护文件。</span><span class="sxs-lookup"><span data-stu-id="a2737-115">DLP will look for other policy matches as well, such as protecting files with credit card numbers if this type of policy is configured.</span></span> 

## <a name="retention-labels-for-your-sharepoint-online-sites"></a><span data-ttu-id="a2737-116">SharePoint Online 网站的保留标签</span><span class="sxs-lookup"><span data-stu-id="a2737-116">Retention labels for your SharePoint Online sites</span></span>

<span data-ttu-id="a2737-117">创建并为 SharePoint Online 团队网站分配保留标签分为三个阶段。</span><span class="sxs-lookup"><span data-stu-id="a2737-117">There are three phases to creating and then assigning retention labels to SharePoint Online team sites.</span></span>
  
### <a name="phase-1-determine-the-retention-label-names"></a><span data-ttu-id="a2737-118">阶段 1：确定保留标签名称</span><span class="sxs-lookup"><span data-stu-id="a2737-118">Phase 1: Determine the retention label names</span></span>

<span data-ttu-id="a2737-119">在此阶段，对于应用到 SharePoint Online 团队网站的四个级别的信息保护，确定保留标签的名称。</span><span class="sxs-lookup"><span data-stu-id="a2737-119">In this phase, you determine the names of your retention labels for the four levels of information protection applied to SharePoint Online team sites.</span></span> <span data-ttu-id="a2737-120">下表列出了针对每个级别建议的名称。</span><span class="sxs-lookup"><span data-stu-id="a2737-120">The following table lists the recommended names for each level.</span></span>
  
|<span data-ttu-id="a2737-121">**SharePoint Online 团队网站保护级别**</span><span class="sxs-lookup"><span data-stu-id="a2737-121">**SharePoint Online team site protection level**</span></span>|<span data-ttu-id="a2737-122">**标签名称**</span><span class="sxs-lookup"><span data-stu-id="a2737-122">**Label name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a2737-123">基线 - 公用</span><span class="sxs-lookup"><span data-stu-id="a2737-123">Baseline-Public</span></span>  <br/> |<span data-ttu-id="a2737-124">内部公用</span><span class="sxs-lookup"><span data-stu-id="a2737-124">Internal public</span></span>  <br/> |
|<span data-ttu-id="a2737-125">基线 - 专用</span><span class="sxs-lookup"><span data-stu-id="a2737-125">Baseline-Private</span></span>  <br/> |<span data-ttu-id="a2737-126">Private</span><span class="sxs-lookup"><span data-stu-id="a2737-126">Private</span></span>  <br/> |
|<span data-ttu-id="a2737-127">敏感</span><span class="sxs-lookup"><span data-stu-id="a2737-127">Sensitive</span></span>  <br/> |<span data-ttu-id="a2737-128">敏感</span><span class="sxs-lookup"><span data-stu-id="a2737-128">Sensitive</span></span>  <br/> |
|<span data-ttu-id="a2737-129">高度机密</span><span class="sxs-lookup"><span data-stu-id="a2737-129">Highly Confidential</span></span>  <br/> |<span data-ttu-id="a2737-130">高度机密</span><span class="sxs-lookup"><span data-stu-id="a2737-130">Highly Confidential</span></span>  <br/> |
   
### <a name="phase-2-create-the-retention-labels"></a><span data-ttu-id="a2737-131">阶段 2：创建保留标签</span><span class="sxs-lookup"><span data-stu-id="a2737-131">Phase 2: Create the retention labels</span></span>

<span data-ttu-id="a2737-132">在此阶段中，针对不同的信息保护级别创建并发布确定的标签。</span><span class="sxs-lookup"><span data-stu-id="a2737-132">In this phase, you create and then publish your determined labels for the different levels of information protection.</span></span>
  
1. <span data-ttu-id="a2737-133">使用具有安全管理员或公司管理员角色的帐户登录 [Microsoft 365 合规门户](https://compliance.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="a2737-133">Sign in to the [Microsoft 365 compliance portal](https://compliance.microsoft.com) with an account that has the Security Administrator or Company Administrator role.</span></span>
    
2. <span data-ttu-id="a2737-134">在浏览器的“**主页 - Microsoft 365 合规性**”选项卡中，单击“**分类 > 标签**”。</span><span class="sxs-lookup"><span data-stu-id="a2737-134">From the **Home - Microsoft 365 compliance** tab of your browser, click **Classifications > Labels**.</span></span>
    
3. <span data-ttu-id="a2737-135">单击“**保留标签 > 创建标签**”。</span><span class="sxs-lookup"><span data-stu-id="a2737-135">Click **Retention labels > Create a label**.</span></span>
    
4. <span data-ttu-id="a2737-136">在“**命名标签**”窗格中，键入标签的名称和管理员及用户描述，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="a2737-136">On the **Name your label** pane, type the name of the label and a description for admins and users, and then click **Next**.</span></span>

5. <span data-ttu-id="a2737-137">在“**文件计划描述符**”窗格中，根据需要进行填写，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="a2737-137">On the **File plan descriptors** pane, fill in as needed, and then click **Next**.</span></span>
    
6. <span data-ttu-id="a2737-138">在“**标签设置**”窗格中，根据需要将“**保留**”设置为“**开**”并配置保留设置。</span><span class="sxs-lookup"><span data-stu-id="a2737-138">On the **Label settings** pane, if needed, set **Retention** to **On** and configure retention settings.</span></span> <span data-ttu-id="a2737-139">单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="a2737-139">Click **Next**.</span></span>
    
7. <span data-ttu-id="a2737-140">在“**查看设置**”窗格中，单击“**创建标签**”。</span><span class="sxs-lookup"><span data-stu-id="a2737-140">On the **Review your settings** pane, click **Create the label**.</span></span>
    
8. <span data-ttu-id="a2737-141">对于其他标签，请单击“**创建标签**”，然后根据需要重复步骤 3-7。</span><span class="sxs-lookup"><span data-stu-id="a2737-141">For your additional labels, click **Create a label**, and then repeat steps 3-7 as needed.</span></span>
    

### <a name="publish-your-new-labels"></a><span data-ttu-id="a2737-142">发布新标签</span><span class="sxs-lookup"><span data-stu-id="a2737-142">Publish your new labels</span></span>

<span data-ttu-id="a2737-143">接下来，使用这些步骤发布新的保留标签。</span><span class="sxs-lookup"><span data-stu-id="a2737-143">Next, use these steps to publish the new retention labels.</span></span>
  
1. <span data-ttu-id="a2737-144">在“**标签**”窗格中，单击“**保留标签**”选项卡，然后单击“**发布标签**”。</span><span class="sxs-lookup"><span data-stu-id="a2737-144">From the **Labels** pane, click the **Retention labels** tab, and then click **Publish labels**.</span></span>
    
2. <span data-ttu-id="a2737-145">在“**选择要发布的标签**”窗格中，单击“**选择要发布的标签**”。</span><span class="sxs-lookup"><span data-stu-id="a2737-145">On the **Choose labels to publish** pane, click **Choose labels to publish**.</span></span>
    
3. <span data-ttu-id="a2737-146">在“**选择标签**”窗格中，单击“**添加**”并选择全部四个标签，然后单击“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="a2737-146">On the **Choose labels** pane, click **Add**, select all four labels, click **Add**.</span></span>
    
4. <span data-ttu-id="a2737-147">单击“完成”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a2737-147">Click **Done**.</span></span>
    
5. <span data-ttu-id="a2737-148">在“选择要发布的标签”窗格中，单击“下一步”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a2737-148">On the **Choose labels to publish** pane, click **Next**.</span></span>
    
6. <span data-ttu-id="a2737-149">在“选择位置”窗格中，单击“下一步”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a2737-149">On the **Choose locations** pane, click **Next**.</span></span>
    
7. <span data-ttu-id="a2737-150">在“命名策略”\*\*\*\* 窗格中，在“名称”\*\*\*\* 中键入标签组的名称，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a2737-150">On the **Name your policy** pane, type a name for your set of labels in **Name**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="a2737-151">在“查看设置”\*\*\*\* 窗格中，单击“发布标签”\*\*\*\*，然后单击“关闭”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a2737-151">On the **Review your settings** pane, click **Publish labels**, and then click **Close**.</span></span>

    
### <a name="phase-3-apply-the-retention-labels-to-your-sharepoint-online-sites"></a><span data-ttu-id="a2737-152">阶段 3：将保留标签应用到 SharePoint Online 网站</span><span class="sxs-lookup"><span data-stu-id="a2737-152">Phase 3: Apply the retention labels to your SharePoint Online sites</span></span>

<span data-ttu-id="a2737-153">使用这些步骤将保留标签应用到 SharePoint Online 团队网站的文档文件夹。</span><span class="sxs-lookup"><span data-stu-id="a2737-153">Use these steps to apply the retention labels to the documents folders of your SharePoint Online team sites.</span></span>
  
1. <span data-ttu-id="a2737-154">登录到 [Office 365 门户](https://www.office.com)，单击 **SharePoint** 应用。</span><span class="sxs-lookup"><span data-stu-id="a2737-154">Sign in to the [Office 365 portal](https://www.office.com), click the **SharePoint** app.</span></span>
    
2. <span data-ttu-id="a2737-155">在浏览器的新“**SharePoint**”标签页中，单击需要分配保留标签的网站。</span><span class="sxs-lookup"><span data-stu-id="a2737-155">On the new **SharePoint** tab in your browser, click a site that needs a retention label assigned.</span></span>
    
3. <span data-ttu-id="a2737-156">在浏览器的新“SharePoint 网站”标签页中，单击“文档”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a2737-156">In the new SharePoint site tab of your browser, click **Documents**.</span></span>
    
4. <span data-ttu-id="a2737-157">单击设置图标，然后单击“库设置”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a2737-157">Click the settings icon, and then click **Library settings**.</span></span>
    
5. <span data-ttu-id="a2737-158">在“权限和管理”下，单击“向此库中的项应用标签”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a2737-158">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
    
6. <span data-ttu-id="a2737-159">在“**设置-应用标签**”中，选择相应的保留标签，然后单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="a2737-159">In **Settings-Apply Label**, select the appropriate retention label, and then click **Save**.</span></span>
    
7. <span data-ttu-id="a2737-160">关闭 SharePoint Online 网站的选项卡。</span><span class="sxs-lookup"><span data-stu-id="a2737-160">Close the tab for the SharePoint Online site.</span></span>
    
8. <span data-ttu-id="a2737-161">重复步骤 2-8，将保留标签分配给其他 SharePoint Online 网站。</span><span class="sxs-lookup"><span data-stu-id="a2737-161">Repeat steps 2-8 to assign retention labels to your additional SharePoint Online sites.</span></span>
    
<span data-ttu-id="a2737-162">下面是生成的配置。</span><span class="sxs-lookup"><span data-stu-id="a2737-162">Here is your resulting configuration.</span></span>
  
![四种类型的 SharePoint Online 团队网站的保留标签。](media/e0a4fdd2-1c30-4d93-8af4-a6f0c6c29966.png)
  
## <a name="dlp-policies-for-your-sharepoint-online-sites"></a><span data-ttu-id="a2737-164">适用于 SharePoint Online 网站的 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="a2737-164">DLP policies for your SharePoint Online sites</span></span>

<span data-ttu-id="a2737-165">使用以下步骤配置 DLP 策略，该策略可在用户在组织外共享关于 SharePoint Online 敏感团队网站的文档时进行通知。</span><span class="sxs-lookup"><span data-stu-id="a2737-165">Use these steps to configure a DLP policy that notifies users when they share a document on a SharePoint Online sensitive team site outside the organization.</span></span>

1. <span data-ttu-id="a2737-166">使用具有安全管理员或公司管理员角色的帐户登录 [Microsoft 365 合规门户](https://compliance.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="a2737-166">Sign in to the [Microsoft 365 compliance portal](https://compliance.microsoft.com/) with an account that has the Security Administrator or Company Administrator role.</span></span>
    
2. <span data-ttu-id="a2737-167">在浏览器的新“**Microsoft 365 合规**”标签页中，单击“**策略 > 数据丢失防护**”。</span><span class="sxs-lookup"><span data-stu-id="a2737-167">On the new **Microsoft 365 compliance** tab in your browser, click **Policies > Data loss prevention**.</span></span>
    
3. <span data-ttu-id="a2737-168">在“**主页 > 数据丢失防护**”窗格中，单击“**创建策略**”。</span><span class="sxs-lookup"><span data-stu-id="a2737-168">In the **Home > Data loss prevention** pane, click **Create a policy**.</span></span>
    
4. <span data-ttu-id="a2737-169">在“**从模板开始或创建自定义策略**”窗格中，单击“**自定义**”，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="a2737-169">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>
    
5. <span data-ttu-id="a2737-170">在“命名策略”\*\*\*\* 窗格中，在“名称”\*\*\*\* 中键入敏感级别 DLP 策略的名称，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a2737-170">In the **Name your policy** pane, type the name for the sensitive level DLP policy in **Name**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="a2737-171">在“**选择位置**”窗格中，单击“**允许选择特定位置**”，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="a2737-171">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="a2737-172">在位置列表中，禁用“**Exchange 电子邮件**”、“**OneDrive 帐户**”和“**Teams 聊天和频道消息**”，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="a2737-172">In the list of locations, disable the **Exchange email**, **OneDrive accounts**, and **Teams chat and channel messages** locations, and then click **Next**.</span></span>
    
8. <span data-ttu-id="a2737-173">在“**自定义要保护的内容类型**”窗格中，单击“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="a2737-173">In the **Customize the type of content you want to protect** pane, click **Edit**.</span></span>
    
9. <span data-ttu-id="a2737-174">在“**选择要保护的内容类型**”窗格中，单击下拉框中的“**添加**”，然后单击“**保留标签**”。</span><span class="sxs-lookup"><span data-stu-id="a2737-174">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Retention labels**.</span></span>
    
10. <span data-ttu-id="a2737-175">在“**保留标签**”窗格中，单击“**添加**”，选择“**敏感**”标签，然后依次单击“**添加**”和“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="a2737-175">In the **Retention labels** pane, click **Add**, select the **Sensitive** label, click **Add**, and then click **Done**.</span></span>
    
11. <span data-ttu-id="a2737-176">在“选择要保护的内容类型”窗格中，单击“保存”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a2737-176">In the **Choose the types of content to protect** pane, click **Save**.</span></span>
    
12. <span data-ttu-id="a2737-177">在“**自定义要保护的敏感信息类型**”窗格中，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="a2737-177">In the **Customize the type of content you want to protect** pane, click **Next**.</span></span>

13. <span data-ttu-id="a2737-178">在“如果检测到敏感信息，希望采取什么操作?”窗格中，单击“自定义提示和电子邮件”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a2737-178">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>
    
14. <span data-ttu-id="a2737-179">在“自定义策略提示和电子邮件通知”\*\*\*\* 窗格中，单击“自定义策略提示文本”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a2737-179">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>
    
15. <span data-ttu-id="a2737-180">在文本框中，键入或粘贴以下提示之一，具体取决于是否已实现 Azure 信息保护来保护高度机密文件：</span><span class="sxs-lookup"><span data-stu-id="a2737-180">In the text box, type or paste in one of the following tips, depending on if you implemented Azure Information Protection to protect highly confidential files:</span></span>
    
  - <span data-ttu-id="a2737-p106">要与组织外部的用户共享，请下载并打开文件。 依次单击“文件”、“保护文档”、“使用密码加密”，然后指定强密码。 通过单独的电子邮件或其他通信方式发送密码。</span><span class="sxs-lookup"><span data-stu-id="a2737-p106">To share with a user outside the organization, download the file and then open it. Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password. Send the password in a separate email or other means of communication.</span></span>
  - <span data-ttu-id="a2737-p107">高度机密文件已获加密保护。只有 IT 部门向其授予对这些文件的相应权限的外部用户，才能读取这些文件。</span><span class="sxs-lookup"><span data-stu-id="a2737-p107">Highly confidential files are protected with encryption. Only external users who are granted permissions to these files by your IT department can read them.</span></span>
    
    <span data-ttu-id="a2737-186">或键入或粘贴自己的策略提示，指示用户如何在组织外共享文件。</span><span class="sxs-lookup"><span data-stu-id="a2737-186">Alternately, type or paste in your own policy tip that instructs users on how to share a file outside your organization.</span></span>
    
16. <span data-ttu-id="a2737-187">单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a2737-187">Click **OK**.</span></span>
    
17. <span data-ttu-id="a2737-188">在“如果检测到敏感信息，希望采取什么操作?”\*\*\*\* 窗格中，单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a2737-188">In the **What do you want to do if we detect sensitive info?** pane, click **Next**.</span></span>
    
18. <span data-ttu-id="a2737-189">在“是否希望立即启用策略或先进行测试?”\*\*\*\* 窗格中，单击“是，立即启用”\*\*\*\*，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a2737-189">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>
    
19. <span data-ttu-id="a2737-190">在“查看设置”\*\*\*\* 窗格中，单击“创建”\*\*\*\*，然后单击“关闭”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a2737-190">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>
    
<span data-ttu-id="a2737-191">以下为敏感 SharePoint Online 团队网站的配置结果。</span><span class="sxs-lookup"><span data-stu-id="a2737-191">Here is your resulting configuration for sensitive SharePoint Online team sites.</span></span>
  
![使用敏感保留标签的独立 SharePoint Online 团队网站的 DLP 策略。](media/2ff4cc53-87a8-43e3-b637-3068d88409f3.png)
  
<span data-ttu-id="a2737-193">接下来，使用以下步骤配置 DLP 策略，该策略可在用户在组织外共享关于 SharePoint Online 高度机密团队网站的文档时阻止用户。</span><span class="sxs-lookup"><span data-stu-id="a2737-193">Next, use these steps to configure a DLP policy that blocks users when they share a document on a SharePoint Online highly confidential team site outside the organization.</span></span>
  
1. <span data-ttu-id="a2737-194">在浏览器的新“**Microsoft 365 合规**”标签页中，单击“**策略 > 数据丢失防护**”。</span><span class="sxs-lookup"><span data-stu-id="a2737-194">On the new **Microsoft 365 compliance** tab in your browser, click **Policies > Data loss prevention**.</span></span>
    
2. <span data-ttu-id="a2737-195">在“**数据丢失防护**”窗格中，单击“**创建策略**”。</span><span class="sxs-lookup"><span data-stu-id="a2737-195">In the **Data loss prevention** pane, click **Create a policy**.</span></span>
    
3. <span data-ttu-id="a2737-196">在“从模板开始或创建自定义策略”\*\*\*\* 窗格中，单击“自定义”\*\*\*\*，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a2737-196">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>
    
4. <span data-ttu-id="a2737-197">在“命名策略”\*\*\*\* 窗格中，在“名称”\*\*\*\* 中键入高度敏感级别 DLP 策略的名称，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a2737-197">In the **Name your policy** pane, type the name for the highly sensitive level DLP policy in **Name**, and then click **Next**.</span></span>
    
5. <span data-ttu-id="a2737-198">在“选择位置”窗格中，单击“允许选择特定位置”，然后单击“下一步”\*\*\*\*\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a2737-198">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="a2737-199">在位置列表中，禁用“**Exchange 电子邮件**”、“**OneDrive 帐户**”和“**Teams 聊天和频道消息**”，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="a2737-199">In the list of locations, disable the **Exchange email**, **OneDrive accounts**, and **Teams chat and channel messages** locations, and then click **Next**.</span></span>
    
7. <span data-ttu-id="a2737-200">在“**自定义要保护的敏感信息类型**”窗格中，单击“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="a2737-200">In the **Customize the types of sensitive info you want to protect** pane, click **Edit**.</span></span>
    
8. <span data-ttu-id="a2737-201">在“**选择要保护的内容类型**”窗格中，单击下拉框中的“**添加**”，然后单击“**保留标签**”。</span><span class="sxs-lookup"><span data-stu-id="a2737-201">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Retention labels**.</span></span>
    
9. <span data-ttu-id="a2737-202">在“**保留标签**”窗格中，单击“**添加**”，选择“**高度机密**”标签，然后依次单击“**添加**”和“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="a2737-202">In the **Retention labels** pane, click **Add**, select the **Highly Confidential** label, click **Add**, and then click **Done**.</span></span>
    
10. <span data-ttu-id="a2737-203">在“选择要保护的内容类型”窗格中，单击“保存”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a2737-203">In the **Choose the types of content to protect** pane, click **Save**.</span></span>
    
12. <span data-ttu-id="a2737-204">在“自定义要保护的敏感信息类型”窗格中，单击“下一步”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a2737-204">In the **Customize the types of sensitive info you want to protect** pane, click **Next**.</span></span>
    
13. <span data-ttu-id="a2737-205">在“如果检测到敏感信息，希望采取什么操作?”窗格中，单击“自定义提示和电子邮件”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a2737-205">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>
    
14. <span data-ttu-id="a2737-206">在“自定义策略提示和电子邮件通知”窗格中，单击“自定义策略提示文本”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a2737-206">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>
    
15. <span data-ttu-id="a2737-207">在文本框中，键入或粘贴以下内容：</span><span class="sxs-lookup"><span data-stu-id="a2737-207">In the text box, type or paste in the following:</span></span>
    
  - <span data-ttu-id="a2737-p108">要与组织外部的用户共享，请下载并打开文件。 依次单击“文件”、“保护文档”、“使用密码加密”，然后指定强密码。 通过单独的电子邮件或其他通信方式发送密码。</span><span class="sxs-lookup"><span data-stu-id="a2737-p108">To share with a user outside the organization, download the file and then open it. Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password. Send the password in a separate email or other means of communication.</span></span>
    
    <span data-ttu-id="a2737-211">或者，键入或粘贴自己的策略提示，指示用户如何在组织外共享文件。</span><span class="sxs-lookup"><span data-stu-id="a2737-211">Alternately, type or paste in your own policy tip that instructs users on how to share a file outside your organization.</span></span>
    
16. <span data-ttu-id="a2737-212">单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a2737-212">Click **OK**.</span></span>
    
17. <span data-ttu-id="a2737-213">在“如果检测到敏感信息，希望采取什么操作?”\*\*\*\* 窗格中，单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a2737-213">In the **What do you want to do if we detect sensitive info?** pane, click **Next**.</span></span>
    
18. <span data-ttu-id="a2737-214">在“是否希望立即启用策略或先进行测试?”\*\*\*\* 窗格中，单击“是，立即启用”\*\*\*\*，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a2737-214">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>
    
19. <span data-ttu-id="a2737-215">在“查看设置”\*\*\*\* 窗格中，单击“创建”\*\*\*\*，然后单击“关闭”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a2737-215">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>
    
<span data-ttu-id="a2737-216">以下为高度机密的 SharePoint Online 团队网站的配置结果。</span><span class="sxs-lookup"><span data-stu-id="a2737-216">Here is your resulting configuration for high confidentiality SharePoint Online team sites.</span></span>
  
![使用高度机密保留标签的独立 SharePoint Online 团队网站的 DLP 策略。](media/f705d3d0-23c9-4333-8b70-ad3b91f835ea.png)
  
## <a name="next-step"></a><span data-ttu-id="a2737-218">后续步骤</span><span class="sxs-lookup"><span data-stu-id="a2737-218">Next step</span></span>

[<span data-ttu-id="a2737-219">使用 Azure 信息保护来保护 SharePoint Online 文件</span><span class="sxs-lookup"><span data-stu-id="a2737-219">Protect SharePoint Online files with Azure Information Protection</span></span>](protect-sharepoint-online-files-with-azure-information-protection.md)
    
## <a name="see-also"></a><span data-ttu-id="a2737-220">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a2737-220">See Also</span></span>

[<span data-ttu-id="a2737-221">保护 SharePoint Online 网站和文件</span><span class="sxs-lookup"><span data-stu-id="a2737-221">Secure SharePoint Online sites and files</span></span>](secure-sharepoint-online-sites-and-files.md)
  
[<span data-ttu-id="a2737-222">Microsoft 针对政治宣传活动、非营利组织和其他敏捷性组织的安全指南</span><span class="sxs-lookup"><span data-stu-id="a2737-222">Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations</span></span>](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)
  
[<span data-ttu-id="a2737-223">云应用和混合解决方案</span><span class="sxs-lookup"><span data-stu-id="a2737-223">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)


