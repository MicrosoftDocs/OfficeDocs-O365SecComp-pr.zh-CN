---
title: 将 PST 文件导入到 Office 365 时筛选数据
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/24/2017
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid: MOE150
ms.assetid: 26af16df-34cd-4f4a-b893-bc1d2e74039e
description: '使用 Office 365 导入服务中的新智能导入功能可筛选实际导入到目标邮箱的项目。智能导入使您可以主动决定要导入的数据和留下的内容。智能导入还提供了有关要导入到 Office 365 中的数据的见解。 '
ms.openlocfilehash: 6091f6cca75bffbb05bcd59f70cfae0dbdcb9040
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/26/2019
ms.locfileid: "30297065"
---
# <a name="filter-data-when-importing-pst-files-to-office-365"></a><span data-ttu-id="f9600-105">将 PST 文件导入到 Office 365 时筛选数据</span><span class="sxs-lookup"><span data-stu-id="f9600-105">Filter data when importing PST files to Office 365</span></span>

<span data-ttu-id="f9600-p102">使用 Office 365 导入服务中的新智能导入功能可筛选实际导入到目标邮箱的 PST 文件中的项目。下面介绍了它的工作原理:</span><span class="sxs-lookup"><span data-stu-id="f9600-p102">Use the new Intelligent Import feature in the Office 365 Import service to filter the items in PST files that actually get imported to the target mailboxes. Here's how it works:</span></span>
  
- <span data-ttu-id="f9600-108">在创建并提交 pst 导入作业之后, pst 文件将上载到 Microsoft 云中的 Azure 存储区域。</span><span class="sxs-lookup"><span data-stu-id="f9600-108">After you create and submit a PST import job, PST files are uploaded to an Azure storage area in the Microsoft cloud.</span></span>
    
- <span data-ttu-id="f9600-109">Office 365 通过标识邮箱项目的期限和 pst 文件中包含的不同邮件类型, 以安全和安全的方式分析 pst 文件中的数据。</span><span class="sxs-lookup"><span data-stu-id="f9600-109">Office 365 analyzes the data in the PST files, in a safe and secure manner, by identifying the age of the mailbox items and the different message types included in the PST files.</span></span>
    
- <span data-ttu-id="f9600-p103">分析完成并准备导入数据后, 您可以选择按如下方式导入 PST 文件中的所有数据, 或通过设置筛选器来裁剪导入的数据, 以控制导入的数据。例如, 您可以选择执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="f9600-p103">When the analysis is complete and the data is ready to import, you have the option to import all data in the PST files as is or trim the data that's imported by setting filters that control what data gets imported. For example, you can choose to:</span></span>
    
  - <span data-ttu-id="f9600-112">仅导入特定期限的项目。</span><span class="sxs-lookup"><span data-stu-id="f9600-112">Import only items of a certain age.</span></span>
    
  - <span data-ttu-id="f9600-113">导入所选的邮件类型。</span><span class="sxs-lookup"><span data-stu-id="f9600-113">Import selected message types.</span></span>
    
  - <span data-ttu-id="f9600-114">排除特定人员发送或接收的邮件。</span><span class="sxs-lookup"><span data-stu-id="f9600-114">Exclude messages sent or received by specific people.</span></span>
    
- <span data-ttu-id="f9600-115">配置筛选器设置后, Office 365 仅将满足筛选条件的数据导入到导入作业中指定的目标邮箱。</span><span class="sxs-lookup"><span data-stu-id="f9600-115">After you configure the filter settings, Office 365 imports only the data that meets the filtering criteria to the target mailboxes specified in the import job.</span></span>
    
<span data-ttu-id="f9600-116">下图显示了智能导入过程, 并突出显示了您执行的任务以及 Office 365 执行的任务。</span><span class="sxs-lookup"><span data-stu-id="f9600-116">The following graphic shows the Intelligent Import process, and highlights the tasks you perform and the tasks performed by Office 365.</span></span>
  
![Office 365 中的智能导入过程](media/f2ec309b-11f5-48f2-939c-a6ff72152d14.png)
  
## <a name="before-you-begin"></a><span data-ttu-id="f9600-118">准备工作</span><span class="sxs-lookup"><span data-stu-id="f9600-118">Before you begin</span></span>

- <span data-ttu-id="f9600-p104">本主题中的步骤假定您已使用网络上传或驱动器传送在 Office 365 导入服务中创建了 PST 导入作业。有关分步说明, 请参阅下列主题之一:</span><span class="sxs-lookup"><span data-stu-id="f9600-p104">The steps in this topic assume that you've created a PST import job in the Office 365 Import service by using network upload or drive shipping. For step-by-step instructions, see one of the following topics:</span></span>
    
  - [<span data-ttu-id="f9600-121">使用网络上载将 PST 文件导入到 Office 365</span><span class="sxs-lookup"><span data-stu-id="f9600-121">Use network upload to import PST files to Office 365</span></span>](use-network-upload-to-import-pst-files.md)
    
  - [<span data-ttu-id="f9600-122">使用驱动器寄送，将 PST 文件导入到 Office 365</span><span class="sxs-lookup"><span data-stu-id="f9600-122">Use drive shipping to import PST files to Office 365</span></span>](use-drive-shipping-to-import-pst-files-to-office-365.md)
    
- <span data-ttu-id="f9600-p105">使用网络上载创建导入作业之后, office 365 安全&amp;合规中心中 "导入" 页上的导入作业的状态设置为 "**正在进行分析**", 这意味着 office 365 正在分析您的 PST 文件中的数据, 您已.单击\*\*\*\*!["刷新](media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png)刷新" 以更新导入作业的状态。</span><span class="sxs-lookup"><span data-stu-id="f9600-p105">After you create an import job by using network upload, the status for the import job on the Import page in Office 365 Security &amp; Compliance Center is set to **Analysis in progress**, which means that Office 365 is analyzing the data in the PST files that you uploaded. Click **Refresh**![refresh](media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png) to update the status for the import job.</span></span> 
    
- <span data-ttu-id="f9600-125">对于驱动器运输导入作业, 在 Microsoft 数据中心人员收到你的硬盘并将 PST 文件上传到组织的 Azure 存储区域之后, 将通过 Office 365 对数据进行分析。</span><span class="sxs-lookup"><span data-stu-id="f9600-125">For drive shipping import jobs, the data will be analyzed by Office 365 after Microsoft data center personnel receive your hard drive and upload the PST files to the Azure storage area for your organization.</span></span>
  
## <a name="filter-data-that-gets-imported-to-mailboxes"></a><span data-ttu-id="f9600-126">筛选导入到邮箱的数据</span><span class="sxs-lookup"><span data-stu-id="f9600-126">Filter data that gets imported to mailboxes</span></span>

<span data-ttu-id="f9600-127">创建 PST 导入作业后, 请按照以下步骤在将数据导入到 Office 365 之前对其进行筛选。</span><span class="sxs-lookup"><span data-stu-id="f9600-127">After you've created a PST import job, follow these steps to filter the data before you import it to Office 365.</span></span>
  
1. <span data-ttu-id="f9600-128">转到[https://protection.office.com/](https://protection.office.com/)并使用 Office 365 组织中的管理员帐户凭据登录。</span><span class="sxs-lookup"><span data-stu-id="f9600-128">Go to [https://protection.office.com/](https://protection.office.com/) and sign in using the credentials for an administrator account in your Office 365 organization.</span></span> 
    
2. <span data-ttu-id="f9600-129">在 Office 365 &amp;安全合规中心的左侧窗格中, 单击 "**数据调控** \> **导入**"。</span><span class="sxs-lookup"><span data-stu-id="f9600-129">In the left pane of the Office 365 Security &amp; Compliance Center, click **Data governance** \> **Import**.</span></span>
    
    <span data-ttu-id="f9600-p106">您的组织的导入作业将在 "**导入**" 页上列出。请注意, "**状态**" 列中的 "**分析完成**" 值指示 Office 365 已分析并准备好导入的导入作业。</span><span class="sxs-lookup"><span data-stu-id="f9600-p106">The import jobs for your organization are listed on the **Import** page. Note that the **Analysis completed** value in the **Status** column indicates the import jobs that have been analyzed by Office 365 and are ready for you to import.</span></span> 
    
    ![分析完成状态表示 Office 365 已分析 PST 文件中的数据](media/de5294f4-f0ba-4b92-a48a-a4b32b6da490.png)
  
3. <span data-ttu-id="f9600-133">对于要完成的导入作业, 单击 "已**准备好导入到 Office 365** "。</span><span class="sxs-lookup"><span data-stu-id="f9600-133">Click **Ready to import to Office 365** for the import job that you want to complete.</span></span> 
    
    <span data-ttu-id="f9600-134">将显示一个 "飞出" 页面, 其中包含有关 PST 文件的信息以及有关导入作业的其他信息。</span><span class="sxs-lookup"><span data-stu-id="f9600-134">A fly out page is displayed with information about the PST files and other information about the import job.</span></span>
    
4. <span data-ttu-id="f9600-135">单击 "**导入到 Office 365**"。</span><span class="sxs-lookup"><span data-stu-id="f9600-135">Click **Import to Office 365**.</span></span>
    
    <span data-ttu-id="f9600-p107">将显示 "**筛选数据**" 页。它包含有关导入作业的 PST 文件中的数据的数据见解, 包括有关数据期限的信息。</span><span class="sxs-lookup"><span data-stu-id="f9600-p107">The **Filter your data** page is displayed. It contains data insights about the data in the PST files for the import job, including information about the age of the data.</span></span> 
    
    !["筛选数据" 页面显示导入作业的 PST 文件的数据见解](media/3b537ec0-25a4-45a4-96d5-a429e2a33128.png)
  
5. <span data-ttu-id="f9600-139">根据是否要修整导入到 Office 365 中的数据, 在 "**是否要筛选数据？**" 下, 执行下列操作之一:</span><span class="sxs-lookup"><span data-stu-id="f9600-139">Based on whether or not you want to trim the data that's imported to Office 365, under **Do you want to filter your data?**, do one of the following:</span></span>
    
    <span data-ttu-id="f9600-p108">回答: 单击 **"是, 我想在导入前筛选它**以修整您导入的数据", 然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="f9600-p108">a. Click **Yes, I want to filter it before importing** to trim the data that you import, and then click **Next**.</span></span>
    
    <span data-ttu-id="f9600-142">"将**数据导入到 Office 365 页面**" 页面将显示, 其中包含来自 Office 365 执行的分析的详细数据见解。</span><span class="sxs-lookup"><span data-stu-id="f9600-142">The **Import data to Office 365 page** page is displayed with detailed data insights from the analysis that Office 365 performed.</span></span> 
    
    ![Office 365 显示来自其 PST 文件分析的详细数据见解](media/4881205f-0288-4c32-a440-37e2160295f2.png)
  
    <span data-ttu-id="f9600-p109">此页面上的图显示了将导入的数据量。有关在 PST 文件中找到的每种邮件类型的信息将显示在图形中。您可以将光标悬停在每个条上, 以显示有关该邮件类型的特定信息。还有一个下拉列表, 其中包含不同的年龄值, 基于 PST 文件的分析。当您在下拉列表中选择某个年龄时, 会更新图形以显示所选年龄将导入的数据量。</span><span class="sxs-lookup"><span data-stu-id="f9600-p109">The graph on this page shows the amount of data that will be imported. Information about each message type found in the PST files is displayed in the graph. You can hover the cursor over each bar to display specific information about that message type. There is also a drop-down list with different age values based on the analysis of the PST files. When you select an age in the drop-down list, the graph is updated to show how much data will be imported for the selected age.</span></span> 
    
    <span data-ttu-id="f9600-p110">b. 若要配置附加筛选器以减少导入的数据量, 请单击 "**更多筛选选项**"。</span><span class="sxs-lookup"><span data-stu-id="f9600-p110">b. To configure addition filters to reduce the amount of data that's imported, click **More filtering options**.</span></span>
    
    ![配置 "更多选项" 页上的筛选器以裁切导入的数据](media/3f8d68c3-3fe2-4b4e-9488-b368b98fa9fe.png)
  
    <span data-ttu-id="f9600-152">您可以配置以下筛选器:</span><span class="sxs-lookup"><span data-stu-id="f9600-152">You can configure these filters:</span></span>
    
      - <span data-ttu-id="f9600-p111">**年龄**-选择年龄, 以便只导入比指定年龄更高的项目。有关 Office 365 如何确定**年龄**筛选器的年龄桶的说明, 请参阅[详细信息](filter-data-when-importing-pst-files.md#moreinfo)部分。</span><span class="sxs-lookup"><span data-stu-id="f9600-p111">**Age** - Select an age so only items that are newer than the specified age will be imported. See the [More information](filter-data-when-importing-pst-files.md#moreinfo) section for a description about how Office 365 determines the age buckets for the **Age** filter.</span></span> 
    
      - <span data-ttu-id="f9600-p112">**类型**-此部分显示在导入作业的 PST 文件中找到的所有邮件类型。您可以取消选中要排除的邮件类型旁边的复选框。请注意, 不能排除其他邮件类型。有关其他类别中包含的邮箱项目列表, 请参阅[详细信息](filter-data-when-importing-pst-files.md#moreinfo)部分。</span><span class="sxs-lookup"><span data-stu-id="f9600-p112">**Type** - This section shows all the message types that were found in the PST files for the import job. You can uncheck a box next to a message type that you want to exclude. Note that you can't exclude the Other message type. See the [More information](filter-data-when-importing-pst-files.md#moreinfo) section for a list of mailbox items that are included in the Other category.</span></span> 
    
      - <span data-ttu-id="f9600-p113">**用户**-您可以排除特定人员发送或接收的邮件。若要排除出现在 "发件人:" 字段、"收件人:" 字段或邮件的 "抄送:" 字段中的人员, 请单击该收件人类型旁边的 "**排除用户**"。键入人员的电子邮件地址 (SMTP 地址), 单击 "**添加**![新图标](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) " 以将其添加到该收件人类型的 "已排除的用户" 列表中, 然后单击 "**保存**" 以保存排除的用户列表。</span><span class="sxs-lookup"><span data-stu-id="f9600-p113">**Users** - You can exclude messages that are sent or received by specific people. To exclude people who appear in the From: field, To: field, or the Cc: field of messages, click **Exclude users** next to that recipient type. Type the email address (SMTP address) of the person, click **Add**![New icon](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) to add them to the list of excluded users for that recipient type, and then click **Save** to save the list of excluded users.</span></span> 
    
        > [!NOTE]
        > <span data-ttu-id="f9600-p114">Office 365 不显示通过设置**人员**筛选器得到的数据见解。但是, 如果您设置此筛选器以排除特定人员发送或接收的邮件, 则在实际导入过程中将排除这些邮件。</span><span class="sxs-lookup"><span data-stu-id="f9600-p114">Office 365 doesn't show data insights that result from setting the **People** filter. However, if you set this filter to exclude messages sent or received by specific people, those messages will be excluded during the actual import process.</span></span> 
  
    <span data-ttu-id="f9600-p115">c. 在 "**其他筛选选项**" 弹出页面中单击 "**应用**" 以保存筛选器设置。</span><span class="sxs-lookup"><span data-stu-id="f9600-p115">c. Click **Apply** in the **More filtering options** fly out page to save your filter settings.</span></span> 
    
    <span data-ttu-id="f9600-p116">"将**数据导入到 Office 365** " 页面将根据您的筛选器设置进行更新, 其中包括将根据筛选器设置导入的总数据量。请注意, 还会显示筛选器设置的摘要。您可以单击筛选器旁边的 "**编辑**" 以更改设置 (如有必要)。</span><span class="sxs-lookup"><span data-stu-id="f9600-p116">The data insights on the **Import data to Office 365** page are updated based on your filter settings, including the total amount of data that will be imported based on the filter settings. Note that a summary of the filter settings is also shown. You can click **Edit** next to a filter to change the setting if necessary.</span></span> 
    
    ![数据洞察力根据您的筛选器设置进行更新](media/897e20fb-3b13-44c3-9d56-9f330750f2a3.png)
  
    <span data-ttu-id="f9600-p117">d. 单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="f9600-p117">d. Click **Next**.</span></span>
    
    <span data-ttu-id="f9600-p118">将显示 "状态" 页, 其中显示了筛选器设置。同样, 您可以编辑任何筛选设置。</span><span class="sxs-lookup"><span data-stu-id="f9600-p118">A status page is displayed showing your filter settings. Again, you can edit any of the filter settings.</span></span>
    
    <span data-ttu-id="f9600-p119">e. 单击 "**导入数据**" 以启动导入。请注意, 将显示将导入的总数据量。</span><span class="sxs-lookup"><span data-stu-id="f9600-p119">e. Click **Import data** to start the import . Note that the total amount of data that will be imported is displayed.</span></span> 
    
    <span data-ttu-id="f9600-177">或者</span><span class="sxs-lookup"><span data-stu-id="f9600-177">Or</span></span>
    
    <span data-ttu-id="f9600-p120">一. 单击 "**否, 我想要导**入所有文件以将 PST 文件中的所有数据导入 Office 365", 然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="f9600-p120">a. Click **No, I want to import everything** to import all data in the PST files to Office 365, and then click **Next**.</span></span>
    
    <span data-ttu-id="f9600-p121">b. 在 "将**数据导入到 Office 365** " 页上, 单击 "**导入数据**" 以启动导入。请注意, 将显示将导入的总数据量。</span><span class="sxs-lookup"><span data-stu-id="f9600-p121">b. On the **Import data to Office 365** page, click **Import data** to start the import. Note that the total amount of data that will be imported is displayed.</span></span> 
    
6. <span data-ttu-id="f9600-p122">在 "**导入**" 页\*\*\*\* ![上,](media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png)单击 "刷新刷新"。导入作业的状态将显示在 "**状态**" 列中。</span><span class="sxs-lookup"><span data-stu-id="f9600-p122">On the **Import** page, click **Refresh** ![refresh](media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png). The status for the import job is displayed in the **Status** column.</span></span> 
    
7. <span data-ttu-id="f9600-185">单击 "导入作业" 以显示更多详细信息, 如每个 PST 文件的状态和您配置的筛选器设置。</span><span class="sxs-lookup"><span data-stu-id="f9600-185">Click the import the job to display more detailed information, such as the status for each PST file and the filter settings that you configured.</span></span>

  
## <a name="more-information"></a><span data-ttu-id="f9600-186">更多信息</span><span class="sxs-lookup"><span data-stu-id="f9600-186">More information</span></span>

- <span data-ttu-id="f9600-p123">Office 365 如何确定年龄筛选器的增量？当 Office 365 分析 PST 文件时, 它会查看每个项目的已发送或接收时间戳 (如果某个项目同时具有已发送和已接收的时间戳, 则选择了最早的日期)。然后, Office 365 将查看该时间戳的年份值, 并将其与当前日期进行比较以确定项目的年龄。然后, 将这些年龄用作**年龄**筛选器的下拉列表中的值。例如, 如果 PST 文件包含来自2016、2015和2014的邮件, 则**年龄**筛选器中的值将为**1 年**、 **2 年**和**3 年**。</span><span class="sxs-lookup"><span data-stu-id="f9600-p123">How does Office 365 determine the increments for the age filter? When Office 365 analyzes a PST file, it looks at the sent or received time stamp of each item (if an item has both a sent and received timestamp, the oldest date is selected). Then Office 365 looks at the year value for that timestamp and compares it to the current date to determine the age of the item. These ages are then used as the values in the drop-down list for the **Age** filter. For example, if a PST file has messages from 2016, 2015, and 2014, then values in the **Age** filter would be **1 year**, **2 years**, and **3 years**.</span></span>
    
- <span data-ttu-id="f9600-p124">下表列出了 "**更多选项**" 飞出页面 (请参阅上\*\*\*\* 一过程中的步骤 5b) 的 "**其他**" 类别中包含的邮件类型。当前, 在将 pst 导入到 Office 365 时, 不能排除 "其他" 类别中的项目。</span><span class="sxs-lookup"><span data-stu-id="f9600-p124">The following table lists the message types that are included in the **Other** category in the **Type** filter on the **More options** fly out page (see Step 5b in the previous procedure). Currently, you can't exclude items in the "Other" category when you import PSTs to Office 365.</span></span> 
    
    |<span data-ttu-id="f9600-194">**邮件类别 ID**</span><span class="sxs-lookup"><span data-stu-id="f9600-194">**Message class ID**</span></span>|<span data-ttu-id="f9600-195">**使用此邮件类别的邮箱项目**</span><span class="sxs-lookup"><span data-stu-id="f9600-195">**Mailbox items that use this message class**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="f9600-196">ipm.note.活动</span><span class="sxs-lookup"><span data-stu-id="f9600-196">IPM.Activity</span></span>  <br/> |<span data-ttu-id="f9600-197">日记条目</span><span class="sxs-lookup"><span data-stu-id="f9600-197">Journal entries</span></span>  <br/> |
    |<span data-ttu-id="f9600-198">ipm.note.证明</span><span class="sxs-lookup"><span data-stu-id="f9600-198">IPM.Document</span></span>  <br/> |<span data-ttu-id="f9600-199">文档和文件 (未附加到电子邮件)</span><span class="sxs-lookup"><span data-stu-id="f9600-199">Documents and files (not attached to an email message)</span></span>  <br/> |
    |<span data-ttu-id="f9600-200">ipm.note.文本文件</span><span class="sxs-lookup"><span data-stu-id="f9600-200">IPM.File</span></span>  <br/> |<span data-ttu-id="f9600-201">(与 IPM。证明</span><span class="sxs-lookup"><span data-stu-id="f9600-201">(same as IPM.Document)</span></span>  <br/> |
    |<span data-ttu-id="f9600-202">ipm.note.注意: IMC. 通知</span><span class="sxs-lookup"><span data-stu-id="f9600-202">IPM.Note.IMC.Notification</span></span>  <br/> |<span data-ttu-id="f9600-203">由 internet 邮件连接发送的报告, 即 Exchange Server 到 internet 的网关</span><span class="sxs-lookup"><span data-stu-id="f9600-203">Reports sent by Internet Mail Connect, which is the Exchange Server gateway to the Internet</span></span>  <br/> |
    |<span data-ttu-id="f9600-204">ipm.note.注意: Microsoft. Fax</span><span class="sxs-lookup"><span data-stu-id="f9600-204">IPM.Note.Microsoft.Fax</span></span>  <br/> |<span data-ttu-id="f9600-205">传真邮件</span><span class="sxs-lookup"><span data-stu-id="f9600-205">Fax messages</span></span>  <br/> |
    |<span data-ttu-id="f9600-206">ipm.note.注意: "Rules。</span><span class="sxs-lookup"><span data-stu-id="f9600-206">IPM.Note.Rules.Oof.Template.Microsoft</span></span>  <br/> |<span data-ttu-id="f9600-207">外出自动答复邮件</span><span class="sxs-lookup"><span data-stu-id="f9600-207">Out-of-office auto-reply messages</span></span>  <br/> |
    |<span data-ttu-id="f9600-208">ipm.note.注意: ReplyTemplate</span><span class="sxs-lookup"><span data-stu-id="f9600-208">IPM.Note.Rules.ReplyTemplate.Microsoft</span></span>  <br/> |<span data-ttu-id="f9600-209">收件箱规则发送的答复</span><span class="sxs-lookup"><span data-stu-id="f9600-209">Replies sent by an inbox rule</span></span>  <br/> |
    |<span data-ttu-id="f9600-210">ipm.note.OLE.静态类</span><span class="sxs-lookup"><span data-stu-id="f9600-210">IPM.OLE.Class</span></span>  <br/> |<span data-ttu-id="f9600-211">定期系列的例外</span><span class="sxs-lookup"><span data-stu-id="f9600-211">Exceptions for a recurring series</span></span>  <br/> |
    |<span data-ttu-id="f9600-212">ipm.note.撤回。报告</span><span class="sxs-lookup"><span data-stu-id="f9600-212">IPM.Recall.Report</span></span>  <br/> |<span data-ttu-id="f9600-213">邮件撤回报告</span><span class="sxs-lookup"><span data-stu-id="f9600-213">Message recall reports</span></span>  <br/> |
    |<span data-ttu-id="f9600-214">ipm.note.远端</span><span class="sxs-lookup"><span data-stu-id="f9600-214">IPM.Remote</span></span>  <br/> |<span data-ttu-id="f9600-215">远程邮件</span><span class="sxs-lookup"><span data-stu-id="f9600-215">Remote mail messages</span></span>  <br/> |
    |<span data-ttu-id="f9600-216">ipm.note.完工</span><span class="sxs-lookup"><span data-stu-id="f9600-216">IPM.Report</span></span>  <br/> |<span data-ttu-id="f9600-217">项目状态报告</span><span class="sxs-lookup"><span data-stu-id="f9600-217">Item status reports</span></span>  <br/> |
