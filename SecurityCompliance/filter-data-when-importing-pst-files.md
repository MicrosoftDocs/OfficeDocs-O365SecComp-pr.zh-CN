---
title: PST 文件导入到 Office 365 时筛选数据
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/24/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid: MOE150
ms.assetid: 26af16df-34cd-4f4a-b893-bc1d2e74039e
description: '使用 Office 365 导入服务中的新的智能导入功能实际上获取导入到的目标邮箱的项进行筛选。智能导入让您主动决定哪些数据导入和要保留的内容。智能导入的数据，正在导入到 Office 365 还提供见解。 '
ms.openlocfilehash: c90d9df62c7d8c411196b283acec37959fc95e57
ms.sourcegitcommit: 7956955cd919f6e00b64e4506605a743c5872549
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/26/2018
ms.locfileid: "25038195"
---
# <a name="filter-data-when-importing-pst-files-to-office-365"></a><span data-ttu-id="220fd-105">PST 文件导入到 Office 365 时筛选数据</span><span class="sxs-lookup"><span data-stu-id="220fd-105">Filter data when importing PST files to Office 365</span></span>

<span data-ttu-id="220fd-p102">使用 Office 365 导入服务中的新的智能导入功能筛选实际上获取导入到的目标邮箱的 PST 文件中的项目。下面是它的工作原理：</span><span class="sxs-lookup"><span data-stu-id="220fd-p102">Use the new Intelligent Import feature in the Office 365 Import service to filter the items in PST files that actually get imported to the target mailboxes. Here's how it works:</span></span>
  
- <span data-ttu-id="220fd-108">创建和提交 PST 导入作业后，PST 文件上载到云中 Microsoft Azure 存储区。</span><span class="sxs-lookup"><span data-stu-id="220fd-108">After you create and submit a PST import job, PST files are uploaded to an Azure storage area in the Microsoft cloud.</span></span>
    
- <span data-ttu-id="220fd-109">Office 365 标识的邮箱项目和 PST 文件中包含的其他消息类型的年龄，以安全方式，分析 PST 文件中的数据。</span><span class="sxs-lookup"><span data-stu-id="220fd-109">Office 365 analyzes the data in the PST files, in a safe and secure manner, by identifying the age of the mailbox items and the different message types included in the PST files.</span></span>
    
- <span data-ttu-id="220fd-p103">当完成分析，并已准备好导入数据时，您可以选择要导入或修整通过设置控制哪些数据获取导入的筛选器导入的数据的 PST 文件中的所有数据。例如，您可以选择：</span><span class="sxs-lookup"><span data-stu-id="220fd-p103">When the analysis is complete and the data is ready to import, you have the option to import all data in the PST files as is or trim the data that's imported by setting filters that control what data gets imported. For example, you can choose to:</span></span>
    
  - <span data-ttu-id="220fd-112">导入仅存在一定时间的项目。</span><span class="sxs-lookup"><span data-stu-id="220fd-112">Import only items of a certain age.</span></span>
    
  - <span data-ttu-id="220fd-113">导入所选的消息类型。</span><span class="sxs-lookup"><span data-stu-id="220fd-113">Import selected message types.</span></span>
    
  - <span data-ttu-id="220fd-114">排除由特定人员发送或接收的消息。</span><span class="sxs-lookup"><span data-stu-id="220fd-114">Exclude messages sent or received by specific people.</span></span>
    
- <span data-ttu-id="220fd-115">配置筛选设置后，Office 365 导入符合筛选条件在导入作业中指定的目标邮箱数据。</span><span class="sxs-lookup"><span data-stu-id="220fd-115">After you configure the filter settings, Office 365 imports only the data that meets the filtering criteria to the target mailboxes specified in the import job.</span></span>
    
<span data-ttu-id="220fd-116">下图显示了智能导入过程，并突出显示所执行的任务和执行 Office 365 的任务。</span><span class="sxs-lookup"><span data-stu-id="220fd-116">The following graphic shows the Intelligent Import process, and highlights the tasks you perform and the tasks performed by Office 365.</span></span>
  
![Office 365 中的智能导入过程](media/f2ec309b-11f5-48f2-939c-a6ff72152d14.png)
  
## <a name="before-you-begin"></a><span data-ttu-id="220fd-118">准备工作</span><span class="sxs-lookup"><span data-stu-id="220fd-118">Before you begin</span></span>

- <span data-ttu-id="220fd-p104">本主题中的步骤假定您已创建 PST 导入作业导入 Office 365 服务中使用网络上载或驱动器传送。有关分步说明，请参阅以下主题：</span><span class="sxs-lookup"><span data-stu-id="220fd-p104">The steps in this topic assume that you've created a PST import job in the Office 365 Import service by using network upload or drive shipping. For step-by-step instructions, see one of the following topics:</span></span>
    
  - [<span data-ttu-id="220fd-121">使用网络上载将 PST 文件导入到 Office 365</span><span class="sxs-lookup"><span data-stu-id="220fd-121">Use network upload to import PST files to Office 365</span></span>](use-network-upload-to-import-pst-files.md)
    
  - [<span data-ttu-id="220fd-122">使用驱动器寄送，将 PST 文件导入到 Office 365</span><span class="sxs-lookup"><span data-stu-id="220fd-122">Use drive shipping to import PST files to Office 365</span></span>](use-drive-shipping-to-import-pst-files-to-office-365.md)
    
- <span data-ttu-id="220fd-p105">使用网络上载创建导入作业后，Office 365 安全性页面上导入的导入作业的状态&amp;合规性中心设置为**正在进行中的分析**，这意味着 Office 365 正在分析 PST 文件中的数据的上载。单击**刷新**![刷新](media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png)更新导入作业的状态。</span><span class="sxs-lookup"><span data-stu-id="220fd-p105">After you create an import job by using network upload, the status for the import job on the Import page in Office 365 Security &amp; Compliance Center is set to **Analysis in progress**, which means that Office 365 is analyzing the data in the PST files that you uploaded. Click **Refresh**![refresh](media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png) to update the status for the import job.</span></span> 
    
- <span data-ttu-id="220fd-125">对于传送导入作业的驱动器，将进行数据分析 Office 365 后 Microsoft 数据中心人员收到您的硬盘，并将 PST 文件上载到您的组织的 Azure 存储区。</span><span class="sxs-lookup"><span data-stu-id="220fd-125">For drive shipping import jobs, the data will be analyzed by Office 365 after Microsoft data center personnel receive your hard drive and upload the PST files to the Azure storage area for your organization.</span></span>
  
## <a name="filter-data-that-gets-imported-to-mailboxes"></a><span data-ttu-id="220fd-126">筛选获取导入到邮箱的数据</span><span class="sxs-lookup"><span data-stu-id="220fd-126">Filter data that gets imported to mailboxes</span></span>

<span data-ttu-id="220fd-127">您已创建后 PST 导入作业，请按照以下步骤之前将其导入 Office 365 筛选数据。</span><span class="sxs-lookup"><span data-stu-id="220fd-127">After you've created a PST import job, follow these steps to filter the data before you import it to Office 365.</span></span>
  
1. <span data-ttu-id="220fd-128">转到[https://protection.office.com/](https://protection.office.com/)和使用 Office 365 组织中的管理员帐户凭据登录。</span><span class="sxs-lookup"><span data-stu-id="220fd-128">Go to [https://protection.office.com/](https://protection.office.com/) and sign in using the credentials for an administrator account in your Office 365 organization.</span></span> 
    
2. <span data-ttu-id="220fd-129">Office 365 安全性的左窗格中&amp;合规性中心，单击**数据调控** \> **导入**。</span><span class="sxs-lookup"><span data-stu-id="220fd-129">In the left pane of the Office 365 Security &amp; Compliance Center, click **Data governance** \> **Import**.</span></span>
    
    <span data-ttu-id="220fd-p106">在**导入**页列出了您的组织的导入作业。请注意，**状态**列中的**分析已完成**值指示已分析的 Office 365 并且可供您导入的导入作业。</span><span class="sxs-lookup"><span data-stu-id="220fd-p106">The import jobs for your organization are listed on the **Import** page. Note that the **Analysis completed** value in the **Status** column indicates the import jobs that have been analyzed by Office 365 and are ready for you to import.</span></span> 
    
    ![分析完成状态指示 Office 365 具有分析 PST 文件中的数据](media/de5294f4-f0ba-4b92-a48a-a4b32b6da490.png)
  
3. <span data-ttu-id="220fd-133">要完成的导入作业，单击**已准备好到 Office 365 导入**。</span><span class="sxs-lookup"><span data-stu-id="220fd-133">Click **Ready to import to Office 365** for the import job that you want to complete.</span></span> 
    
    <span data-ttu-id="220fd-134">飞出页将显示有关 PST 文件的信息以及其他信息导入作业。</span><span class="sxs-lookup"><span data-stu-id="220fd-134">A fly out page is displayed with information about the PST files and other information about the import job.</span></span>
    
4. <span data-ttu-id="220fd-135">单击**导入到 Office 365**。</span><span class="sxs-lookup"><span data-stu-id="220fd-135">Click **Import to Office 365**.</span></span>
    
    <span data-ttu-id="220fd-p107">显示**筛选数据**页。它包含有关导入作业，包括有关数据的期限的 PST 文件中的数据的数据见解。</span><span class="sxs-lookup"><span data-stu-id="220fd-p107">The **Filter your data** page is displayed. It contains data insights about the data in the PST files for the import job, including information about the age of the data.</span></span> 
    
    ![筛选器数据页显示的 PST 文件导入作业的数据见解](media/3b537ec0-25a4-45a4-96d5-a429e2a33128.png)
  
5. <span data-ttu-id="220fd-139">基于您是否想要裁剪数据导入到 Office 365 中，在**您需要筛选数据？**，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="220fd-139">Based on whether or not you want to trim the data that's imported to Office 365, under **Do you want to filter your data?**, do one of the following:</span></span>
    
    <span data-ttu-id="220fd-p108">答： 单击**是，我希望筛选其导入前**要裁剪您导入的数据，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="220fd-p108">a. Click **Yes, I want to filter it before importing** to trim the data that you import, and then click **Next**.</span></span>
    
    <span data-ttu-id="220fd-142">**Office 365 逐页导入数据**页将显示从 Office 365 执行分析的详细的数据见解。</span><span class="sxs-lookup"><span data-stu-id="220fd-142">The **Import data to Office 365 page** page is displayed with detailed data insights from the analysis that Office 365 performed.</span></span> 
    
    ![Office 365 显示详细的数据洞察力 PST 文件与其分析](media/4881205f-0288-4c32-a440-37e2160295f2.png)
  
    <span data-ttu-id="220fd-p109">此页上的图显示了将导入的数据量。图中显示有关 PST 文件中找到的每个邮件类型的信息。您可以将光标悬停在每个栏以显示有关该消息类型的特定信息。此外，还有不同期限值基于对 PST 文件的分析的下拉列表。当下拉列表中选择年龄时，图表将更新以显示将为所选的年龄导入数据量。</span><span class="sxs-lookup"><span data-stu-id="220fd-p109">The graph on this page shows the amount of data that will be imported. Information about each message type found in the PST files is displayed in the graph. You can hover the cursor over each bar to display specific information about that message type. There is also a drop-down list with different age values based on the analysis of the PST files. When you select an age in the drop-down list, the graph is updated to show how much data will be imported for the selected age.</span></span> 
    
    <span data-ttu-id="220fd-p110">b.若要配置添加筛选器以减少的导入的数据量，请单击**更多的筛选选项**。</span><span class="sxs-lookup"><span data-stu-id="220fd-p110">b. To configure addition filters to reduce the amount of data that's imported, click **More filtering options**.</span></span>
    
    ![在更多选项页，用以调整导入的数据配置筛选器](media/3f8d68c3-3fe2-4b4e-9488-b368b98fa9fe.png)
  
    <span data-ttu-id="220fd-152">您可以配置这些筛选器：</span><span class="sxs-lookup"><span data-stu-id="220fd-152">You can configure these filters:</span></span>
    
      - <span data-ttu-id="220fd-p111">**期限**-年龄，以便更高的指定期限的唯一项都将被导入的选择。请参阅关于 Office 365 如何确定**期限**筛选器的时间跨度说明的[详细信息](filter-data-when-importing-pst-files.md#moreinfo)部分。</span><span class="sxs-lookup"><span data-stu-id="220fd-p111">**Age** - Select an age so only items that are newer than the specified age will be imported. See the [More information](filter-data-when-importing-pst-files.md#moreinfo) section for a description about how Office 365 determines the age buckets for the **Age** filter.</span></span> 
    
      - <span data-ttu-id="220fd-p112">**类型**-此部分显示已导入作业的 PST 文件中找到的所有消息类型。您可以取消选中要排除的消息类型旁边的框。请注意，不能排除的其他消息类型。请参阅其他类别中包括的邮箱项目列表的[详细信息](filter-data-when-importing-pst-files.md#moreinfo)部分。</span><span class="sxs-lookup"><span data-stu-id="220fd-p112">**Type** - This section shows all the message types that were found in the PST files for the import job. You can uncheck a box next to a message type that you want to exclude. Note that you can't exclude the Other message type. See the [More information](filter-data-when-importing-pst-files.md#moreinfo) section for a list of mailbox items that are included in the Other category.</span></span> 
    
      - <span data-ttu-id="220fd-p113">**用户**-可以排除发送或接收的特定的某个人的邮件。要排除 From 中显示的人员： 字段中，为： 字段中，或抄送： 字段的邮件，单击**排除的用户**旁边的收件人类型。键入此人的电子邮件地址 （SMTP 地址），单击**添加**![图标](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif)将其添加到的收件人类型，排除的用户列表，然后单击**保存**以保存排除的用户的列表。</span><span class="sxs-lookup"><span data-stu-id="220fd-p113">**Users** - You can exclude messages that are sent or received by specific people. To exclude people who appear in the From: field, To: field, or the Cc: field of messages, click **Exclude users** next to that recipient type. Type the email address (SMTP address) of the person, click **Add**![New icon](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) to add them to the list of excluded users for that recipient type, and then click **Save** to save the list of excluded users.</span></span> 
    
        > [!NOTE]
        > <span data-ttu-id="220fd-p114">Office 365 不显示数据见解所产生的设置的**人员**筛选器。但是，如果将此筛选器中排除由特定人员发送或接收的消息，这些消息将排除在实际导入过程。</span><span class="sxs-lookup"><span data-stu-id="220fd-p114">Office 365 doesn't show data insights that result from setting the **People** filter. However, if you set this filter to exclude messages sent or received by specific people, those messages will be excluded during the actual import process.</span></span> 
  
    <span data-ttu-id="220fd-p115">c.**更多筛选选项**飞出要保存筛选器设置页中单击**应用**。</span><span class="sxs-lookup"><span data-stu-id="220fd-p115">c. Click **Apply** in the **More filtering options** fly out page to save your filter settings.</span></span> 
    
    <span data-ttu-id="220fd-p116">在**到 Office 365 的导入数据**页上的见解基于筛选器设置进行更新的数据，包括将导入的数据的总量基于筛选器设置。请注意，还显示筛选器设置摘要。可以更改设置，如有必要的筛选器旁边单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="220fd-p116">The data insights on the **Import data to Office 365** page are updated based on your filter settings, including the total amount of data that will be imported based on the filter settings. Note that a summary of the filter settings is also shown. You can click **Edit** next to a filter to change the setting if necessary.</span></span> 
    
    ![基于筛选器设置进行更新数据见解](media/897e20fb-3b13-44c3-9d56-9f330750f2a3.png)
  
    <span data-ttu-id="220fd-p117">d.单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="220fd-p117">d. Click **Next**.</span></span>
    
    <span data-ttu-id="220fd-p118">将显示的状态页，其中显示筛选器设置。同样，您可以编辑的任何筛选器设置。</span><span class="sxs-lookup"><span data-stu-id="220fd-p118">A status page is displayed showing your filter settings. Again, you can edit any of the filter settings.</span></span>
    
    <span data-ttu-id="220fd-p119">e.单击**导入数据**以开始导入。请注意，将显示的总将导入的数据量。</span><span class="sxs-lookup"><span data-stu-id="220fd-p119">e. Click **Import data** to start the import . Note that the total amount of data that will be imported is displayed.</span></span> 
    
    <span data-ttu-id="220fd-177">或者</span><span class="sxs-lookup"><span data-stu-id="220fd-177">Or</span></span>
    
    <span data-ttu-id="220fd-p120">答： 单击**否，我想要导入所有**PST 文件中的所有数据导入到 Office 365，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="220fd-p120">a. Click **No, I want to import everything** to import all data in the PST files to Office 365, and then click **Next**.</span></span>
    
    <span data-ttu-id="220fd-p121">b.在**导入到 Office 365 的数据**页上，单击**导入数据**开始导入。请注意，将显示的总将导入的数据量。</span><span class="sxs-lookup"><span data-stu-id="220fd-p121">b. On the **Import data to Office 365** page, click **Import data** to start the import. Note that the total amount of data that will be imported is displayed.</span></span> 
    
6. <span data-ttu-id="220fd-p122">在**导入**页上，单击**刷新**![刷新](media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png)。导入作业的状态显示在**状态**列中。</span><span class="sxs-lookup"><span data-stu-id="220fd-p122">On the **Import** page, click **Refresh** ![refresh](media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png). The status for the import job is displayed in the **Status** column.</span></span> 
    
7. <span data-ttu-id="220fd-185">单击导入作业以显示更多详细的信息，如针对每个 PST 文件和配置的筛选器设置的状态。</span><span class="sxs-lookup"><span data-stu-id="220fd-185">Click the import the job to display more detailed information, such as the status for each PST file and the filter settings that you configured.</span></span>

  
## <a name="more-information"></a><span data-ttu-id="220fd-186">更多信息</span><span class="sxs-lookup"><span data-stu-id="220fd-186">More information</span></span>

- <span data-ttu-id="220fd-p123">Office 365 是如何确定期限筛选器的增量的？当 Office 365 分析 PST 文件时，它查找在每个项目的已发送或接收的时间戳 （如果项具有两个发送和接收时间戳，处于选中状态的最早日期）。然后 Office 365 的时间戳的年值查看并比较为当前日期确定项目的时间。这些岁然后用作**期限**筛选器下拉列表中的值。例如，如果 PST 文件具有 2016年、 2015，和 2014 年的消息，则**期限**筛选器中的值将为**1 年**、 **2 年**和**3 年**可以。</span><span class="sxs-lookup"><span data-stu-id="220fd-p123">How does Office 365 determine the increments for the age filter? When Office 365 analyzes a PST file, it looks at the sent or received time stamp of each item (if an item has both a sent and received timestamp, the oldest date is selected). Then Office 365 looks at the year value for that timestamp and compares it to the current date to determine the age of the item. These ages are then used as the values in the drop-down list for the **Age** filter. For example, if a PST file has messages from 2016, 2015, and 2014, then values in the **Age** filter would be **1 year**, **2 years**, and **3 years**.</span></span>
    
- <span data-ttu-id="220fd-p124">下表列出的**其他**类别中的**更多选项**飞出页上的**类型**筛选器包含邮件类型 （请参阅上一过程中的步骤 5b）。目前，不能到 Office 365 中导入 Pst 时排除"其他"类别中的项目。</span><span class="sxs-lookup"><span data-stu-id="220fd-p124">The following table lists the message types that are included in the **Other** category in the **Type** filter on the **More options** fly out page (see Step 5b in the previous procedure). Currently, you can't exclude items in the "Other" category when you import PSTs to Office 365.</span></span> 
    
    |<span data-ttu-id="220fd-194">**邮件类标识符**</span><span class="sxs-lookup"><span data-stu-id="220fd-194">**Message class ID**</span></span>|<span data-ttu-id="220fd-195">**使用此邮件类的邮箱项目**</span><span class="sxs-lookup"><span data-stu-id="220fd-195">**Mailbox items that use this message class**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="220fd-196">IPM。活动</span><span class="sxs-lookup"><span data-stu-id="220fd-196">IPM.Activity</span></span>  <br/> |<span data-ttu-id="220fd-197">日记条目</span><span class="sxs-lookup"><span data-stu-id="220fd-197">Journal entries</span></span>  <br/> |
    |<span data-ttu-id="220fd-198">IPM。文档</span><span class="sxs-lookup"><span data-stu-id="220fd-198">IPM.Document</span></span>  <br/> |<span data-ttu-id="220fd-199">文档和文件 （不附加到电子邮件）</span><span class="sxs-lookup"><span data-stu-id="220fd-199">Documents and files (not attached to an email message)</span></span>  <br/> |
    |<span data-ttu-id="220fd-200">IPM。文件</span><span class="sxs-lookup"><span data-stu-id="220fd-200">IPM.File</span></span>  <br/> |<span data-ttu-id="220fd-201">（IPM 相同。文档）</span><span class="sxs-lookup"><span data-stu-id="220fd-201">(same as IPM.Document)</span></span>  <br/> |
    |<span data-ttu-id="220fd-202">IPM。Note.IMC.Notification</span><span class="sxs-lookup"><span data-stu-id="220fd-202">IPM.Note.IMC.Notification</span></span>  <br/> |<span data-ttu-id="220fd-203">通过 Internet Mail 连接，这是到 Internet 的 Exchange Server 网关发送的报告</span><span class="sxs-lookup"><span data-stu-id="220fd-203">Reports sent by Internet Mail Connect, which is the Exchange Server gateway to the Internet</span></span>  <br/> |
    |<span data-ttu-id="220fd-204">IPM。Note.Microsoft.Fax</span><span class="sxs-lookup"><span data-stu-id="220fd-204">IPM.Note.Microsoft.Fax</span></span>  <br/> |<span data-ttu-id="220fd-205">传真消息</span><span class="sxs-lookup"><span data-stu-id="220fd-205">Fax messages</span></span>  <br/> |
    |<span data-ttu-id="220fd-206">IPM。Note.Rules.Oof.Template.Microsoft</span><span class="sxs-lookup"><span data-stu-id="220fd-206">IPM.Note.Rules.Oof.Template.Microsoft</span></span>  <br/> |<span data-ttu-id="220fd-207">外出自动答复邮件</span><span class="sxs-lookup"><span data-stu-id="220fd-207">Out-of-office auto-reply messages</span></span>  <br/> |
    |<span data-ttu-id="220fd-208">IPM。Note.Rules.ReplyTemplate.Microsoft</span><span class="sxs-lookup"><span data-stu-id="220fd-208">IPM.Note.Rules.ReplyTemplate.Microsoft</span></span>  <br/> |<span data-ttu-id="220fd-209">发送的收件箱规则的答复</span><span class="sxs-lookup"><span data-stu-id="220fd-209">Replies sent by an inbox rule</span></span>  <br/> |
    |<span data-ttu-id="220fd-210">IPM。OLE。类</span><span class="sxs-lookup"><span data-stu-id="220fd-210">IPM.OLE.Class</span></span>  <br/> |<span data-ttu-id="220fd-211">定期系列的例外</span><span class="sxs-lookup"><span data-stu-id="220fd-211">Exceptions for a recurring series</span></span>  <br/> |
    |<span data-ttu-id="220fd-212">IPM。Recall.Report</span><span class="sxs-lookup"><span data-stu-id="220fd-212">IPM.Recall.Report</span></span>  <br/> |<span data-ttu-id="220fd-213">邮件撤回报告</span><span class="sxs-lookup"><span data-stu-id="220fd-213">Message recall reports</span></span>  <br/> |
    |<span data-ttu-id="220fd-214">IPM。远程</span><span class="sxs-lookup"><span data-stu-id="220fd-214">IPM.Remote</span></span>  <br/> |<span data-ttu-id="220fd-215">远程邮件</span><span class="sxs-lookup"><span data-stu-id="220fd-215">Remote mail messages</span></span>  <br/> |
    |<span data-ttu-id="220fd-216">IPM。报告</span><span class="sxs-lookup"><span data-stu-id="220fd-216">IPM.Report</span></span>  <br/> |<span data-ttu-id="220fd-217">项目状态报告</span><span class="sxs-lookup"><span data-stu-id="220fd-217">Item status reports</span></span>  <br/> |
