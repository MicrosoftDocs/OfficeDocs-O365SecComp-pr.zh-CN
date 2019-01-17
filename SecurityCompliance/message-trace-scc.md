---
title: 安全 & 合规性中心中的邮件跟踪
ms.author: chrisda
author: chrisda
manager: serdars
ms.date: ''
ms.audience: ITPro
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 3e64f99d-ac33-4aba-91c5-9cb4ca476803
description: 管理员可以使用安全 & 合规性中心中邮件跟踪以找出消息发生了什么变化。
ms.openlocfilehash: 9dfdab4adc5caba55664e93b49c8428791670ab3
ms.sourcegitcommit: 25fb33a1f8b2844fde15f6c03db2936c610824e0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28685355"
---
# <a name="message-trace-in-the-security--compliance-center"></a><span data-ttu-id="5b8d0-103">安全 & 合规性中心中的邮件跟踪</span><span class="sxs-lookup"><span data-stu-id="5b8d0-103">Message trace in the Security & Compliance Center</span></span>

<span data-ttu-id="5b8d0-p101">邮件跟踪中安全 & 合规性中心跟随旅行通过 Exchange Online 组织的电子邮件。您可以确定一条消息，是否已收到、 拒绝、 延迟，或由服务发送。它还会显示其达到其最终状态之前，对邮件采取了哪些操作。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-p101">Message trace in the Security & Compliance Center follows email messages as they travel through your Exchange Online organization. You can determine if a message was received, rejected, deferred, or delivered by the service. It also shows what actions were taken on the message before it reached its final status.</span></span>

<span data-ttu-id="5b8d0-p102">Exchange 管理员中心 (EAC) 中可用的邮件跟踪时提高了安全性 & 合规性中心中的邮件跟踪。邮件跟踪的信息可用于高效地用户有关其邮件发生了什么变化、 排查邮件流问题和解答验证策略更改。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-p102">Message trace in the Security & Compliance Center improves upon message trace that was available in the Exchange admin center (EAC). You can use the information from message trace to efficiently answer user questions about what happened to their messages, troubleshoot mail flow issues, and validate policy changes.</span></span>

## <a name="open-message-trace"></a><span data-ttu-id="5b8d0-109">打开的邮件跟踪</span><span class="sxs-lookup"><span data-stu-id="5b8d0-109">Open message trace</span></span>

1. <span data-ttu-id="5b8d0-110">使用您的 工作或学校帐户[登录到 Office 365](https://support.office.com/article/e9eb7d51-5430-4929-91ab-6157c5a050b4)。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-110">[Sign in to Office 365](https://support.office.com/article/e9eb7d51-5430-4929-91ab-6157c5a050b4) with your work or school account.</span></span>

2. <span data-ttu-id="5b8d0-111">在左上角选择应用启动器图标 ![Office 365 应用启动器图标](media/0aaa6945-f9a4-4b13-bf5f-d5c5dbe978fb.png)，然后选择" **管理**"。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-111">Select the app launcher icon ![Office 365 app launcher icon](media/0aaa6945-f9a4-4b13-bf5f-d5c5dbe978fb.png) in the upper-left and choose **Admin**.</span></span>

3. <span data-ttu-id="5b8d0-112">在左导航窗格中，展开**管理中心**，然后选择**安全 & 合规性**。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-112">In the lower-left navigation, expand **Admin centers** and select **Security & Compliance**.</span></span>

4. <span data-ttu-id="5b8d0-113">在**安全 & 合规性**页打开中，展开**邮件流**，并选择**邮件跟踪**。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-113">In the **Security & Compliance** page that opens, expand **Mail flow**, and select **Message trace**.</span></span>

## <a name="message-trace-page"></a><span data-ttu-id="5b8d0-114">邮件跟踪页面</span><span class="sxs-lookup"><span data-stu-id="5b8d0-114">Message trace page</span></span>

<span data-ttu-id="5b8d0-p103">从此处，您可以通过单击**启动跟踪**按钮开始新的默认跟踪。这将搜索所有邮件的所有发件人和收件人最近两天。或您可以使用的可用的查询类别中的存储查询之一，然后运行它们作为-是或将其用作启动您自己的查询的点：</span><span class="sxs-lookup"><span data-stu-id="5b8d0-p103">From here you can start a new default trace by clicking on the **Start a trace** button. This will search for all messages for all senders and recipients for the last two days. Or you can use one of the stored queries from the available query categories and either run them as-is or use them as starting points for your own queries:</span></span>

- <span data-ttu-id="5b8d0-118">**默认查询**： Office 365 提供的内置查询。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-118">**Default queries**: Built-in queries provided by Office 365.</span></span>

- <span data-ttu-id="5b8d0-119">**自定义查询**： 查询保存由以供将来使用组织中的管理员。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-119">**Custom queries**: Queries saved by admins in your organization for future use.</span></span>

- <span data-ttu-id="5b8d0-p104">**自动保存查询**： 在最后一个十最近运行查询。此列表便于拿起您离开的地方。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-p104">**Autosaved queries**: The last ten most recently run queries. This list makes it simple to pick up where you left off.</span></span>

<span data-ttu-id="5b8d0-122">此外在此页是**Downloadable 报告**部分请求已提交，以及他们自己的报告时可供下载。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-122">Also on this page is a **Downloadable reports** section for the requests you've submitted, as well as the reports themselves when they're are available for download.</span></span>

## <a name="options-for-a-new-message-trace"></a><span data-ttu-id="5b8d0-123">新的邮件跟踪的选项</span><span class="sxs-lookup"><span data-stu-id="5b8d0-123">Options for a new message trace</span></span>

### <a name="filter-by-senders-and-recipients"></a><span data-ttu-id="5b8d0-124">按发件人和收件人筛选</span><span class="sxs-lookup"><span data-stu-id="5b8d0-124">Filter by senders and recipients</span></span>

<span data-ttu-id="5b8d0-125">默认值为**所有发件人**和**所有收件人**，但您可以使用以下字段来筛选结果：</span><span class="sxs-lookup"><span data-stu-id="5b8d0-125">The default values are **All senders** and **All recipients**, but you can use the following fields to filter the results:</span></span>

- <span data-ttu-id="5b8d0-p105">**通过这些人员**： 单击此字段以从您的组织选择一个或多个发件人。您还可以开始键入一个名称并将通过已键入的内容，得多类似的搜索页的行为方式筛选列表中的项。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-p105">**By these people**: Click in this field to select one or more senders from your organization. You can also start to type a name and the items in the list will be filtered by what you've typed, much like how a search page behaves.</span></span>

- <span data-ttu-id="5b8d0-128">**向这些人**： 单击此字段以选择您的组织中的一个或多个收件人。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-128">**To these people**: Click in this field to select one or more recipients in your organization.</span></span>

<span data-ttu-id="5b8d0-p106">您还可以键入外部发件人和收件人的电子邮件地址。支持通配符 (`*@contoso.com`或`scot?@contoso.com`)，但不是能在同一时间的同一字段中使用多个通配符条目。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-p106">You can also type the email addresses of external senders and recipients. Wildcards are supported (`*@contoso.com` or `scot?@contoso.com`), but you can't use multiple wildcard entries in the same field at the same time.</span></span>

### <a name="time-range"></a><span data-ttu-id="5b8d0-131">时间范围</span><span class="sxs-lookup"><span data-stu-id="5b8d0-131">Time range</span></span>

<span data-ttu-id="5b8d0-p107">默认值为**2 天**，但您可以指定的最长为 90 天的日期/时间范围。当您使用日期/时间范围时，请考虑下列问题：</span><span class="sxs-lookup"><span data-stu-id="5b8d0-p107">The default value is **2 days**, but you can specify date/time ranges of up to 90 days. When you use date/time ranges, consider these issues:</span></span>

- <span data-ttu-id="5b8d0-p108">默认情况下使用时间线的**滑块**视图中选择的时间范围。您只能选择的日期或时间显示的设置。要选择的中间值尝试将对齐到的开始/结束气泡最近显示设置。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-p108">By default, you select the time range in **Slider** view using a time line. You can only select the day or time settings that are displayed. Trying to select an in-between value will snap the start/end bubble to the nearest displayed setting.</span></span>

   ![在新的邮件跟踪中安全 & 合规性中心中的滑块时间范围](media/55a9e9c1-f7d5-4047-b217-824e8b976bcb.png)

   <span data-ttu-id="5b8d0-p109">但是，您还可以切换到**自定义**视图，其中您可以指定**开始日期**和**结束日期**值 （包括时间），您还可以选择**时区**的日期/时间范围。请注意，**所在的时区**设置应用于查询输入和查询结果。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-p109">But, you can also switch to **Custom** view where you can specify the **Start date** and **End date** values (including times), and you can also select the **Time zone** for the date/time range. Note that the **Time zone** setting applies to both your query inputs and your query results.</span></span>

   ![在新的邮件跟踪中安全 & 合规性中心中的自定义时间范围](media/ed4c8d50-9ea5-4694-93f9-ee3ab6660b4f.png)

   <span data-ttu-id="5b8d0-p110">表示 10 天或更少，结果是可立即用作**摘要**报告。如果指定即使稍大于 10 天时间范围，结果将为它们只是作为可下载的 CSV 文件 （**增强摘要**或**扩展**用于报表） 提供延迟。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-p110">For 10 days or less, the results are available instantly as a **Summary** report. If you specify a time range that's even slightly greater than 10 days, the results will be delayed as they are only available as a downloadable CSV file ( **Enhanced summary** or **Extended** reports).</span></span>

   <span data-ttu-id="5b8d0-143">有关不同的报告类型的详细信息，请参阅本主题中的[选择报表类型](#choose-report-type)部分。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-143">For more information about the different report types, see the [Choose report type](#choose-report-type) section in this topic.</span></span>

   <span data-ttu-id="5b8d0-p111">**注意**： 增强的摘要和扩展报告准备使用存档的邮件跟踪数据，并，可能要花费几个小时之前您的报告可供下载。根据多少其他管理员也已提交时间大致相同的报告请求，您可能还发现您排队的请求处理开始之前延迟。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-p111">**Note**: Enhanced summary and Extended reports are prepared using archived message trace data, and it can take up to several hours before your report is available for download. Depending on how many other admins have also submitted report requests around the same time, you might also notice a delay before processing starts for your queued request.</span></span>

- <span data-ttu-id="5b8d0-p112">**滑块**视图中保存的查询将保存的相对的时间范围 （例如，从今天的 3 天）。**自定义**视图中保存的查询将保存的绝对的日期/时间范围 (例如，是 06 05 2018年 13:00 到 2018年-05-08 18:00)。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-p112">Saving a query in **Slider** view saves the relative time range (for example, 3 days from today). Saving a query in **Custom** view saves the absolute date/time range (for example, 2018-05-06 13:00 to 2018-05-08 18:00).</span></span>

### <a name="more-search-options"></a><span data-ttu-id="5b8d0-148">多个搜索选项</span><span class="sxs-lookup"><span data-stu-id="5b8d0-148">More search options</span></span>

#### <a name="delivery-status"></a><span data-ttu-id="5b8d0-149">传递状态</span><span class="sxs-lookup"><span data-stu-id="5b8d0-149">Delivery status</span></span>

<span data-ttu-id="5b8d0-150">您可以将保留**所有**选择，默认值，或者您可以选择要筛选结果的下列值之一：</span><span class="sxs-lookup"><span data-stu-id="5b8d0-150">You can leave the default value **All** selected, or you can select one of the following values to filter the results:</span></span>

- <span data-ttu-id="5b8d0-151">**传递**： 邮件已成功递送到预定的目标。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-151">**Delivered**: The message was successfully delivered to the intended destination.</span></span>

- <span data-ttu-id="5b8d0-152">**挂起**： 正在邮件传递尝试或重新尝试。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-152">**Pending**: Delivery of the message is being attempted or re-attempted.</span></span>

- <span data-ttu-id="5b8d0-153">**Expanded**： 通讯组收件人已扩展之前传递到单个组的成员。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-153">**Expanded**: A distribution group recipient was expanded before delivery to the individual members of the group.</span></span>

- <span data-ttu-id="5b8d0-154">**失败**： 消息未能送达。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-154">**Failed**: The message was not delivered.</span></span>

- <span data-ttu-id="5b8d0-p113">**隔离**： 邮件已隔离 （作为垃圾邮件、 批量邮件或网络钓鱼邮件）。有关详细信息，请参阅[Office 365 中的隔离电子邮件](https://support.office.com/article/4c234874-015e-4768-8495-98fcccfc639b.aspx)。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-p113">**Quarantined**: The message was quarantined (as spam, bulk mail, or phishing). For more information, see [Quarantine email messages in Office 365](https://support.office.com/article/4c234874-015e-4768-8495-98fcccfc639b.aspx).</span></span>

- <span data-ttu-id="5b8d0-157">**为垃圾邮件筛选**： 该消息标识垃圾邮件和已拒绝或阻止 （不隔离）。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-157">**Filtered as spam**: The message was identified spam, and was rejected or blocked (not quarantined).</span></span>

- <span data-ttu-id="5b8d0-p114">**获取状态：** Office 365 最近收到邮件，但没有其他状态数据尚不可用。签入几分钟后。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-p114">**Getting status:** The message was recently received by Office 365, but no other status data is yet available. Check back in a few minutes.</span></span>

<span data-ttu-id="5b8d0-p115">**注意**：**未决、** **隔离**，并**为垃圾邮件筛选器**的值仅适用于搜索少于 10 天。此外，可能有 5 至 10 分钟的延迟之间的实际和报告的传递状态。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-p115">**Note**: The values **Pending,** **Quarantined**, and **Filter as spam** are only available for searches less than 10 days. Also, there might be a 5 to 10 minute delay between the actual and reported delivery status.</span></span>

#### <a name="message-id"></a><span data-ttu-id="5b8d0-162">Message ID</span><span class="sxs-lookup"><span data-stu-id="5b8d0-162">Message ID</span></span>

<span data-ttu-id="5b8d0-p116">这是中找到的 internet 邮件 ID (也称为客户端 ID)**邮件 ID:** 邮件头中的标头字段。用户可以为您提供此值来进行调查特定的邮件。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-p116">This is the internet message ID (also known as the Client ID) that's found in the **Message-ID:** header field in the message header. Users can give you this value to investigate specific messages.</span></span>

<span data-ttu-id="5b8d0-p117">邮件的生存期内，此值是常量。在 Office 365 或 Exchange 中创建的邮件，则采用以下格式`<GUID@ServerFQDN>`，包括尖括号 (\< \>)。例如， `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`。其他邮件系统可能会使用不同的语法或值。此值应该是唯一的但并非所有电子邮件系统严格遵循此要求。如果**邮件 ID:** 、 标头字段不存在，或为空的传入邮件来自外部源分配一个任意值。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-p117">This value is constant for the lifetime of the message. For messages created in Office 365 or Exchange, the value is in the format `<GUID@ServerFQDN>`, including the angle brackets (\< \>). For example, `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`. Other messaging systems might use different syntax or values. This value is supposed to be unique, but not all email systems strictly follow this requirement. If the **Message-ID:** header field doesn't exist or is blank for incoming messages from external sources, an arbitrary value is assigned.</span></span>

<span data-ttu-id="5b8d0-171">当使用**邮件 ID**来筛选结果时，请务必包括包括任何尖括号的完整字符串。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-171">When you use **Message ID** to filter the results, be sure to include the full string, including any angle brackets.</span></span>

#### <a name="direction"></a><span data-ttu-id="5b8d0-172">方向</span><span class="sxs-lookup"><span data-stu-id="5b8d0-172">Direction</span></span>

<span data-ttu-id="5b8d0-173">您可以将保留**所有**选择，默认值或您可以选择 （邮件发送给组织中的收件人） 的**入站**或**出站**（从您的组织中的用户发送的邮件） 来筛选结果。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-173">You can leave the default value **All** selected, or you can select **Inbound** (messages sent to recipients in your organization) or **Outbound** (messages sent from users in your organization) to filter the results.</span></span>

#### <a name="original-client-ip-address"></a><span data-ttu-id="5b8d0-174">原始客户端 IP 地址</span><span class="sxs-lookup"><span data-stu-id="5b8d0-174">Original client IP address</span></span>

<span data-ttu-id="5b8d0-p118">通过客户端 IP 地址来进行调查发送大量垃圾邮件或恶意软件的黑客攻击的计算机结果可以文件服务器。尽管邮件可能会显示为来自多个发件人，很可能在同一台计算机生成的所有邮件。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-p118">You can filer the results by client IP address to investigate hacked computers that are sending large amounts of spam or malware. Although the messages might appear to come from multiple senders, it's likely that the same computer is generating all of the messages.</span></span>

<span data-ttu-id="5b8d0-177">**注意**： 客户端 IP 地址信息 10 天，是仅可用且仅**增强摘要**或**扩展**报告 （可下载 CSV 文件） 中。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-177">**Note**: The client IP address information is only available for 10 days, and is only available in the **Enhanced summary** or **Extended** reports (downloadable CSV files).</span></span>

### <a name="choose-report-type"></a><span data-ttu-id="5b8d0-178">选择报表类型</span><span class="sxs-lookup"><span data-stu-id="5b8d0-178">Choose report type</span></span>

<span data-ttu-id="5b8d0-179">可用的报告类型包括：</span><span class="sxs-lookup"><span data-stu-id="5b8d0-179">The available report types are:</span></span>

- <span data-ttu-id="5b8d0-p119">**摘要**： 当时间范围是不超过 10 天，并且需要任何其他筛选选项可用。则结果将几乎立即后单击**搜索**。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-p119">**Summary**: Available if the time range is less than 10 days, and requires no additional filtering options. The results are available almost immediately after you click **Search**.</span></span>

- <span data-ttu-id="5b8d0-p120">**增强摘要**或**扩展**： 仅可可下载的 CSV 文件，这些报告，需要一个或多个以下筛选选项而不考虑时间范围：**这些人员通过**、**向这些人**，或**邮件 ID**。发件人或收件人可以使用通配符 (例如， \*@contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-p120">**Enhanced summary** or **Extended**: These reports are only available as downloadable CSV files, and require one or more of the following filtering options regardless of the time range: **By these people**, **To these people**, or **Message ID**. You can use wildcards for the senders or the recipients (for example, \*@contoso.com).</span></span>

<span data-ttu-id="5b8d0-184">**注意：**</span><span class="sxs-lookup"><span data-stu-id="5b8d0-184">**Notes**:</span></span>

- <span data-ttu-id="5b8d0-p121">增强的摘要和扩展报告准备使用存档的邮件跟踪数据，并，可能要花费几个小时才可以下载您的报告。根据多少其他管理员也已提交时间大致相同的报告请求，您可能还发现排队的请求开始处理之前延迟。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-p121">Enhanced summary and Extended reports are prepared using archived message trace data, and it can take up to several hours before your report is available to download. Depending on how many other admins have also submitted report requests around the same time, you might also notice a delay before your queued request starts to be processed.</span></span>

- <span data-ttu-id="5b8d0-187">时可以选择任何增强型摘要或扩展报表日期/时间范围，通常最后四个小时的存档数据将不会尚未可供以下两种类型的报告。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-187">While you can select an Enhanced summary or Extended report for any date/time range, commonly the last four hours of archived data will not yet be available for these two types of reports.</span></span>

<span data-ttu-id="5b8d0-p122">单击**下一步**，时显示与摘要页，其中列出了所选的筛选选项报表和邮件跟踪完成 （还可编辑时, 收到通知的电子邮件地址的唯一 （可编辑） 标题必须在贵组织的接受域之一)。单击**准备报表**提交邮件跟踪。在主**邮件跟踪**页上，您可以看到**Downloadable 报告**部分中的报表的状态。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-p122">When you click **Next**, you're presented with a summary page that lists the filtering options that you selected, a unique (editable) title for the report, and the email address that receives the notification when the message trace completes (also editable, and must be in one of your organization's accepted domains). Click **Prepare report** to submit the message trace. On the main **Message trace** page, you can see the status of the report in the **Downloadable reports** section.</span></span>

<span data-ttu-id="5b8d0-191">有关在不同的报告类型返回的信息的详细信息，请参阅下一节。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-191">For more information about the information that's returned in the different report types, see the next section.</span></span>

## <a name="message-trace-results"></a><span data-ttu-id="5b8d0-192">邮件跟踪结果</span><span class="sxs-lookup"><span data-stu-id="5b8d0-192">Message trace results</span></span>

<span data-ttu-id="5b8d0-p123">不同的报告类型返回不同级别的信息。以下各节介绍了不同的报告中提供的信息。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-p123">The different report types return different levels of information. The information that's available in the different reports is described in the following sections.</span></span>

### <a name="summary-report-output"></a><span data-ttu-id="5b8d0-195">摘要报告输出</span><span class="sxs-lookup"><span data-stu-id="5b8d0-195">Summary report output</span></span>

<span data-ttu-id="5b8d0-196">后运行邮件跟踪，结果将列，按降序日期/时间 （最新的第一个）。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-196">After running the message trace, the results will be listed, sorted by descending date/time (most recent first).</span></span>

![摘要报告中安全 & 合规中心的邮件跟踪结果](media/0664bafe-0b03-477b-b571-0b046ac8c977.png)

<span data-ttu-id="5b8d0-198">摘要报告中包含以下信息：</span><span class="sxs-lookup"><span data-stu-id="5b8d0-198">The summary report contains the following information:</span></span>

- <span data-ttu-id="5b8d0-199">**日期**： 的日期和时间的服务，使用配置的 UTC 时区收到邮件。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-199">**Date**: The date and time at which the message was received by the service, using the configured UTC time zone.</span></span>

- <span data-ttu-id="5b8d0-200">**发件人**： 发件人的电子邮件地址 (*别名*@*域*)。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-200">**Sender**: The email address of the sender (*alias*@*domain*).</span></span>

- <span data-ttu-id="5b8d0-p124">**收件人**： 收件人或收件人的电子邮件地址。向多个收件人发送邮件，没有每个收件人的一行。如果收件人是通讯组、 动态通讯组或已启用邮件的安全组，组将第一个收件人，并且每个组的成员则单独占一行。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-p124">**Recipient**: The email address of the recipient or recipients. For a message sent to multiple recipients, there's one line per recipient. If the recipient is a distribution group, dynamic distribution group, or mail-enabled security group, the group will be the first recipient, and then each member of the group is on a separate line.</span></span>

- <span data-ttu-id="5b8d0-204">**主题**： 邮件的前 256 个字符**主题：** 字段。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-204">**Subject**: The first 256 characters of the message's **Subject:** field.</span></span>

- <span data-ttu-id="5b8d0-205">**状态**:[传递状态](#delivery-status)部分中描述了这些值。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-205">**Status**: These values are described in the [Delivery status](#delivery-status) section.</span></span>

<span data-ttu-id="5b8d0-p125">默认情况下的前 250 结果已加载且随时可用。当您向下滚动时下, 一批结果是加载会少许暂停。而不是滚动，您可以单击**加载所有**加载所有 10,000 最多的结果。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-p125">By default, the first 250 results are loaded and readily available. When you scroll down, there's a slight pause as the next batch of results are loaded. Instead of scrolling, you can click **Load all** to load all of the results up to a maximum of 10,000.</span></span>

<span data-ttu-id="5b8d0-209">您可以单击列标题以按升序或降序顺序中的列中的值对结果进行排序。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-209">You can click on the column headers to sort the results by the values in that column in ascending or descending order.</span></span>

<span data-ttu-id="5b8d0-210">您可以单击**筛选结果**的一个或多个列筛选结果。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-210">You can click **Filter results** to filter the results by one or more columns.</span></span>

<span data-ttu-id="5b8d0-211">您已选择一个或多个行，请单击**导出结果**，然后选择**导出所有结果**、**都导出加载结果**，或**都导出所选**后，您可以都导出结果。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-211">You can export the results after you've selected one or more rows by clicking **Export results** and then selecting **Export all results**, **Export loaded results**, or **Export selected**.</span></span>

#### <a name="find-related-records-for-this-message"></a><span data-ttu-id="5b8d0-212">此消息的查找相关的记录</span><span class="sxs-lookup"><span data-stu-id="5b8d0-212">Find related records for this message</span></span>

<span data-ttu-id="5b8d0-p126">相关的消息记录所记录的共享相同的邮件 id。请记住，即使两人之间发送一条消息可以生成多个记录。记录数增加时邮件受通讯组扩展、 转接、 邮件流规则 （也称作传输规则） 等。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-p126">Related message records are records that shared the same Message ID. Remember, even a single message sent between two people can generate multiple records. The number of records increases when the message is affected by distribution group expansion, forwarding, mail flow rules (also known as transport rules), etc.</span></span>

<span data-ttu-id="5b8d0-216">选择某一行的复选框后，您可以找到相关的记录的邮件通过单击**查找相关**按钮的显示，或选择**更多选项**![详细](media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> **查找相关的记录此消息**)。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-216">After you select a row's check box, you can find related records for the message by clicking the **Find related** button that appears, or by selecting **More options** ![More](media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> **Find related records for this message**).</span></span>

<span data-ttu-id="5b8d0-217">有关邮件 ID 的详细信息，请参阅本主题前面的邮件 ID 部分。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-217">For more information about the Message ID, see the Message ID section earlier in this topic.</span></span>

#### <a name="message-trace-details"></a><span data-ttu-id="5b8d0-218">邮件跟踪详细信息</span><span class="sxs-lookup"><span data-stu-id="5b8d0-218">Message trace details</span></span>

<span data-ttu-id="5b8d0-219">在摘要报告输出中，您可以使用下列方法之一来查看有关一条消息的详细信息：</span><span class="sxs-lookup"><span data-stu-id="5b8d0-219">In the summary report output, you can view details about a message by using either of the following methods:</span></span>

- <span data-ttu-id="5b8d0-220">选择的行 （复选框以外行中的任意位置单击）。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-220">Select the row (click anywhere in the row except the check box).</span></span>

- <span data-ttu-id="5b8d0-221">选择行的复选框，然后单击**更多选项**![详细](media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> **查看邮件详细信息**。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-221">Select the row's check box and click **More options** ![More](media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> **View message details**.</span></span>

   ![双击安全 & 合规性中心中的摘要报告邮件跟踪结果集中的行之后的详细信息](media/e50ee7cd-810a-4c06-8b58-e56ffd7028d1.png)

<span data-ttu-id="5b8d0-223">邮件跟踪详细信息包含不存在的摘要报告中的以下附加信息：</span><span class="sxs-lookup"><span data-stu-id="5b8d0-223">The message trace details contain the following additional information that's not present in the summary report:</span></span>

- <span data-ttu-id="5b8d0-p127">**消息事件**： 此部分包含帮助分类邮件该服务采取的操作的分类。下面是一些您可能遇到的值得事件：</span><span class="sxs-lookup"><span data-stu-id="5b8d0-p127">**Message events**: This section contains classifications that help categorize the actions that the service takes on messages. Some of the more interesting events that you might encounter are:</span></span>

   - <span data-ttu-id="5b8d0-226">**接收**： 服务收到邮件。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-226">**Receive**: The message was received by the service.</span></span>

   - <span data-ttu-id="5b8d0-227">**发送**： 由服务发送邮件。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-227">**Send**: The message was sent by the service.</span></span>

   - <span data-ttu-id="5b8d0-228">**失败**： 消息未能送达。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-228">**Fail**: The message failed to be delivered.</span></span>

   - <span data-ttu-id="5b8d0-229">**提供**： 邮件已传递到邮箱。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-229">**Deliver**: The message was delivered to a mailbox.</span></span>

   - <span data-ttu-id="5b8d0-230">**展开**： 邮件发送给已扩展的通讯组。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-230">**Expand**: The message was sent to a distribution group that was expanded.</span></span>

   - <span data-ttu-id="5b8d0-231">**转接**： 由于内容转换、 邮件收件人限制或代理，收件人被移动到分叉的邮件。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-231">**Transfer**: Recipients were moved to a bifurcated message because of content conversion, message recipient limits, or agents.</span></span>

   - <span data-ttu-id="5b8d0-232">**Defer**： 邮件传递延迟，可能会稍后重新尝试。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-232">**Defer**: The message delivery was postponed and might be re-attempted later.</span></span>

   - <span data-ttu-id="5b8d0-p128">**已解决**： 邮件已被重定向到基于 Active Directory 查找新收件人地址。这种情况下，在原始收件人地址以及邮件的最终的传递状态邮件跟踪中单独行中列出。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-p128">**Resolved**: The message was redirected to a new recipient address based on an Active Directory look up. When this happens, the original recipient address is listed in a separate row in the message trace along with the final delivery status for the message.</span></span>

   <span data-ttu-id="5b8d0-235">请注意，即使成功传递的一般的消息将在邮件跟踪生成多个**事件**条目。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-235">Note that even an uneventful message that's successfully delivered will generate multiple **Event** entries in the message trace.</span></span>

- <span data-ttu-id="5b8d0-236">**详细信息**： 此部分包含以下详细信息：</span><span class="sxs-lookup"><span data-stu-id="5b8d0-236">**More information**: This section contains the following details:</span></span>

   - <span data-ttu-id="5b8d0-p129">**邮件 ID**： 此值在本主题前面的[邮件 ID](#message-id)部分所述。例如， `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-p129">**Message ID**: This value is described in the [Message ID](#message-id) section earlier in this topic. For example, `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`.</span></span>

   - <span data-ttu-id="5b8d0-239">**邮件大小**</span><span class="sxs-lookup"><span data-stu-id="5b8d0-239">**Message size**</span></span>

   - <span data-ttu-id="5b8d0-p130">**从 IP**： 发送邮件的计算机的 IP 地址。从 Exchange Online 发送出站邮件，此值为空。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-p130">**From IP**: The IP address of the computer that sent the message. For outbound messages sent from Exchange Online, this value is blank.</span></span>

   - <span data-ttu-id="5b8d0-p131">**为 IP**： 的 IP 地址或地址服务尝试传递邮件。如果消息有多个收件人，它们显示。发送到 Exchange Online 的入站邮件，此值为空。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-p131">**To IP**: The IP address or addresses where the service attempted to deliver the message. If the message has multiple recipients, these are displayed. For inbound messages sent to Exchange Online, this value is blank.</span></span>

### <a name="enhanced-summary-reports"></a><span data-ttu-id="5b8d0-245">增强的摘要报告</span><span class="sxs-lookup"><span data-stu-id="5b8d0-245">Enhanced summary reports</span></span>

<span data-ttu-id="5b8d0-p132">在开始邮件跟踪**Downloadable 报告**部分提供了可用 （已完成） 的增强型摘要报告。是可用的报告中的以下信息：</span><span class="sxs-lookup"><span data-stu-id="5b8d0-p132">Available (completed) Enhanced summary reports are available in the **Downloadable reports** section at the beginning message trace. The following information is available in the report:</span></span>

- <span data-ttu-id="5b8d0-248">**origin_timestamp**<sup>\*</sup>： 的日期和时间最初由使用配置的 UTC 时区的服务接收邮件。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-248">**origin_timestamp**<sup>\*</sup>: The date and time when the message was initially received by the service, using the configured UTC time zone.</span></span>

- <span data-ttu-id="5b8d0-249">**sender_address 别名**： 发件人的电子邮件地址 (*别名*@*域*)。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-249">**sender_address**: The sender's email address (*alias*@*domain*).</span></span>

- <span data-ttu-id="5b8d0-p133">**Recipient_status**: 邮件的传递给收件人的状态。如果邮件发送给多个收件人，它将为每个格式显示所有收件人和相应的状态： \<*电子邮件地址*\>##\<*状态*\>。例如：</span><span class="sxs-lookup"><span data-stu-id="5b8d0-p133">**Recipient_status**: The status of the delivery of the message to the recipient. If the message was sent to multiple recipients, it will show all the recipients and the corresponding status for each, in the format: \<*email address*\>##\<*status*\>. For example:</span></span>

   - <span data-ttu-id="5b8d0-253">**##Receive，发送**表示服务已接收邮件，并被发送到预定的目标。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-253">**##Receive, Send** means the message was received by the service and was sent to the intended destination.</span></span>

   - <span data-ttu-id="5b8d0-254">**##Receive，失败**，则意味着收到邮件服务，但传递给目标失败。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-254">**##Receive, Fail** means the message was received by the service but delivery to the intended destination failed.</span></span>

   - <span data-ttu-id="5b8d0-255">**##Receive，传递**表示服务已接收邮件，并已传递到收件人的邮箱。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-255">**##Receive, Deliver** means the message was received by the service and was delivered to the recipient's mailbox.</span></span>

- <span data-ttu-id="5b8d0-256">**message_subject**： 邮件的**主题**字段的前 256 个字符。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-256">**message_subject**: The first 256 characters of the message's **Subject** field.</span></span>

- <span data-ttu-id="5b8d0-257">**total_bytes**： 以字节为单位，包括附件在内的邮件的大小。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-257">**total_bytes**: The size of the message in bytes, including attachments.</span></span>

- <span data-ttu-id="5b8d0-p134">**message_id**： 此值在本主题前面的[邮件 ID](#message-id)部分所述。例如， `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-p134">**message_id**: This value is described in the [Message ID](#message-id) section earlier in this topic. For example, `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`.</span></span>

- <span data-ttu-id="5b8d0-p135">**network_message_id**： 可能由于分叉或通讯组扩展中创建的消息的所有副本仍然存在一个唯一的消息 ID 值。示例值是`1341ac7b13fb42ab4d4408cf7f55890f`。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-p135">**network_message_id**: A unique message ID value that persists across all copies of the message that might be created due to bifurcation or distribution group expansion. An example value is `1341ac7b13fb42ab4d4408cf7f55890f`.</span></span>

- <span data-ttu-id="5b8d0-262">**original_client_ip**： 发件人客户端的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-262">**original_client_ip**: The IP address of the sender's client.</span></span>

- <span data-ttu-id="5b8d0-263">**方向性**： 指示是否发送邮件 （1） 向您的组织的入站或是否发送出站 （2） 从您的组织。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-263">**directionality**: Indicates whether the message was sent inbound (1) to your organization, or whether it was sent outbound (2) from your organization.</span></span>

- <span data-ttu-id="5b8d0-p136">**connector_id**： 源或目标连接器的名称。有关 Exchange Online 中的连接器的详细信息，请参阅[配置邮件流，使用 Office 365 中的连接器](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-p136">**connector_id**: The name of the source or destination connector. For more information about connectors in Exchange Online, see [Configure mail flow using connectors in Office 365](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).</span></span>

- <span data-ttu-id="5b8d0-266">**delivery_priority**<sup>\*</sup>： 是否具有**高**、**低**或**普通**优先级发送邮件。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-266">**delivery_priority**<sup>\*</sup>: Whether the message was sent with **High**, **Low**, or **Normal** priority.</span></span>

<span data-ttu-id="5b8d0-267"><sup>\*</sup>这些属性才可用增强型摘要报告中。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-267"><sup>\*</sup>These properties are only available in Enhanced summary reports.</span></span>

### <a name="extended-reports"></a><span data-ttu-id="5b8d0-268">扩展的报告</span><span class="sxs-lookup"><span data-stu-id="5b8d0-268">Extended reports</span></span>

<span data-ttu-id="5b8d0-p137">邮件跟踪的开头**Downloadable 报告**部分提供了可用 （已完成） 扩展报告。（除外**origin_timestamp**和**delivery_priority**） 扩展报告中提供几乎所有增强型摘要报告的信息。仅扩展报告中提供的以下附加信息：</span><span class="sxs-lookup"><span data-stu-id="5b8d0-p137">Available (completed) Extended reports are available in the **Downloadable reports** section at the beginning of message trace. Virtually all of the information from an Enhanced summary report is available in an Extended report (with the exception of **origin_timestamp** and **delivery_priority**). The following additional information is only available in an Extended report:</span></span>

- <span data-ttu-id="5b8d0-272">**client_ip**： 提交邮件的邮件客户端的电子邮件服务器的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-272">**client_ip**: The IP address of the email server or messaging client that submitted the message.</span></span>

- <span data-ttu-id="5b8d0-273">**client_hostname**： 的主机名或电子邮件服务器或提交邮件的邮件客户端的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-273">**client_hostname**: The host name or FQDN of the email server or messaging client that submitted the message.</span></span>

- <span data-ttu-id="5b8d0-274">**server_ip**： 源或目标服务器的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-274">**server_ip**: The IP address of the source or destination server.</span></span>

- <span data-ttu-id="5b8d0-275">**server_hostname**： 的主机名或目标服务器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-275">**server_hostname**: The host name or FQDN of the destination server.</span></span>

- <span data-ttu-id="5b8d0-p138">**source_context**： 与**源**字段的额外信息。例如：</span><span class="sxs-lookup"><span data-stu-id="5b8d0-p138">**source_context**: Extra information associated with the **source** field. For example:</span></span>

   - `Protocol Filter Agent`

   - `3489061114359050000`

- <span data-ttu-id="5b8d0-p139">**源**： Exchange Online 的组件，负责该事件。例如：</span><span class="sxs-lookup"><span data-stu-id="5b8d0-p139">**source**: The Exchange Online component that's responsible for the event. For example:</span></span>

   - `AGENT`

   - `MAILBOXRULE`

   - `SMTP`

- <span data-ttu-id="5b8d0-280">**event_id**： 这些对应于[查找此消息的相关的记录](#find-related-records-for-this-message)部分中所述的**消息事件**值。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-280">**event_id**: These correspond to the **Message event** values that are explained in the [Find related records for this message](#find-related-records-for-this-message) section.</span></span>

- <span data-ttu-id="5b8d0-281">**internal_message_id**： 由当前正在处理邮件的 Exchange Online 服务器分配消息标识符。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-281">**internal_message_id**: A message identifier that's assigned by the Exchange Online server that's currently processing the message.</span></span>

- <span data-ttu-id="5b8d0-p140">**recipient_address**： 邮件的收件人的电子邮件地址。由分号 （;） 分隔多个电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-p140">**recipient_address**: The email addresses of the message's recipients. Multiple email addresses are separated by the semicolon character (;).</span></span>

- <span data-ttu-id="5b8d0-284">**recipient_count**： 的消息中的收件人总数。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-284">**recipient_count**: The total number of recipients in the message.</span></span>

- <span data-ttu-id="5b8d0-285">**related_recipient_address**： 用于`EXPAND`， `REDIRECT`，和`RESOLVE`事件显示其他收件人电子邮件地址与邮件相关联。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-285">**related_recipient_address**: Used with `EXPAND`, `REDIRECT`, and `RESOLVE` events to display other recipient email addresses that are associated with the message.</span></span>

- <span data-ttu-id="5b8d0-p141">**参考**： 此字段包含特定类型的事件的其他信息。例如：</span><span class="sxs-lookup"><span data-stu-id="5b8d0-p141">**reference**: This field contains additional information for specific types of events. For example:</span></span>

   - <span data-ttu-id="5b8d0-p142">**DSN**： 包含报告链接，这是**message_id**值的关联的传递状态通知 （也称为 DSN、 未送达报告、 NDR 或退回邮件），如果 DSN 生成后此事件。如果这是 DSN 邮件时，此字段包含的 DSN 生成的原始邮件**message_id**值。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-p142">**DSN**: Contains the report link, which is the **message_id** value of the associated delivery status notification (also known as a DSN, non-delivery report, NDR, or bounce message) if a DSN is generated subsequent to this event. If this is a DSN message, this field contains the **message_id** value of the original message that the DSN was generated for.</span></span>

   - <span data-ttu-id="5b8d0-290">**展开**： 包含**related_recipient_address**值相关的消息的数目。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-290">**EXPAND**: Contains the **related_recipient_address** value of the related messages.</span></span>

   - <span data-ttu-id="5b8d0-291">**接收**： 可能包含相关的消息的**message_id**值，如果邮件生成的其他进程 （如收件箱规则）。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-291">**RECEIVE**: Might contain the **message_id** value of the related message if the message was generated by other processes (for example, Inbox rules).</span></span>

   - <span data-ttu-id="5b8d0-292">**发送**： 包含的任何 DSN 邮件**internal_message_id**值。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-292">**SEND**: Contains the **internal_message_id** value of any DSN messages.</span></span>

   - <span data-ttu-id="5b8d0-293">**转接**： 包含**internal_message_id**值的邮件的正在 （例如，通过内容转换、 邮件收件人限制或代理） 分为两路。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-293">**TRANSFER**: Contains the **internal_message_id** value of the message that's being forked (for example, by content conversion, message recipient limits, or agents).</span></span>

   - <span data-ttu-id="5b8d0-294">**MAILBOXRULE**： 包含导致生成以下出站消息的收件箱规则的入站邮件**internal_message_id**值。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-294">**MAILBOXRULE**: Contains the **internal_message_id** value of the inbound message that caused the Inbox rule to generate the outbound message.</span></span>

   <span data-ttu-id="5b8d0-295">对于其他类型的事件，此字段通常为空。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-295">For other types of events, this field is usually blank.</span></span>

- <span data-ttu-id="5b8d0-p143">**return_path**： 通过发送邮件的**MAIL FROM**命令指定返回的电子邮件地址。尽管此字段也不为空，但也可以有 null 发件人地址值表示为`<>`。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-p143">**return_path**: The return email address specified by the **MAIL FROM** command that sent the message. Although this field is never empty, it can have the null sender address value represented as `<>`.</span></span>

- <span data-ttu-id="5b8d0-p144">**message_info**： 邮件的其他信息。例如：</span><span class="sxs-lookup"><span data-stu-id="5b8d0-p144">**message_info**: Additional information about the message. For example:</span></span>

   - <span data-ttu-id="5b8d0-p145">消息发起日期-时间为 utc 格式`DELIVER`和`SEND`事件。发起日期-时间是邮件首次输入 Exchange Online 组织的时间。UTC 日期-时间表示 ISO 8601 日期时间格式： `yyyy-mm-ddThh:mm:ss.fffZ`，其中`yyyy`= 年`mm`= 月`dd`= 日，`T`指示的时间组件，开始`hh`= 小时， `mm` = 分钟， `ss` = 第二、 `fff`= 秒，和`Z`表示`Zulu`，这是另一种方法来表示 UTC。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-p145">The message origination date-time in UTC for `DELIVER` and `SEND` events. The origination date-time is the time when the message first entered the Exchange Online organization. The UTC date-time is represented in the ISO 8601 date-time format: `yyyy-mm-ddThh:mm:ss.fffZ`, where `yyyy` = year, `mm` = month, `dd` = day, `T` indicates the beginning of the time component, `hh` = hour, `mm` = minute, `ss` = second, `fff` = fractions of a second, and `Z` signifies `Zulu`, which is another way to denote UTC.</span></span>

   - <span data-ttu-id="5b8d0-p146">身份验证错误。例如，您可能会看到值`11a`和身份验证出错时使用的身份验证类型。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-p146">Authentication errors. For example, you might see the value `11a` and the type of authentication that was used when the authentication error occurred.</span></span>

- <span data-ttu-id="5b8d0-305">**tenant_id**: GUID 值，该值代表 Exchange Online 组织 (例如， `39238e87-b5ab-4ef6-a559-af54c6b07b42`)。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-305">**tenant_id**: A GUID value that represents the Exchange Online organization (for example, `39238e87-b5ab-4ef6-a559-af54c6b07b42`).</span></span>

- <span data-ttu-id="5b8d0-306">**original_server_ip**： 原始服务器的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-306">**original_server_ip**: The IP address of the original server.</span></span>

- <span data-ttu-id="5b8d0-p147">**custom_data**： 包含与特定事件类型的数据。有关详细信息，请参阅以下各节。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-p147">**custom_data**: Contains data related to specific event types. For more information, see the following sections.</span></span>

#### <a name="customdata-values"></a><span data-ttu-id="5b8d0-309">custom_data 值</span><span class="sxs-lookup"><span data-stu-id="5b8d0-309">custom_data values</span></span>

<span data-ttu-id="5b8d0-p148">**Custom_data**字段`AGENTINFO`各种 Exchange Online 代理使用事件日志消息处理的详细信息。以下各节介绍一些值得代理。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-p148">The **custom_data** field for an `AGENTINFO` event is used by a variety of Exchange Online agents to log message processing details. Some of the more interesting agents are described in the following sections.</span></span>

#### <a name="spam-filter-agent"></a><span data-ttu-id="5b8d0-312">垃圾邮件筛选器代理</span><span class="sxs-lookup"><span data-stu-id="5b8d0-312">Spam filter agent</span></span>

<span data-ttu-id="5b8d0-p149">**Custom_data**值开头的`S:SFA`是垃圾邮件筛选器代理。下表中描述的关键详细信息：</span><span class="sxs-lookup"><span data-stu-id="5b8d0-p149">A **custom_data** value that starts with `S:SFA` is from the spam filter agent. The key details are described in the following table:</span></span>

|<span data-ttu-id="5b8d0-315">**值**</span><span class="sxs-lookup"><span data-stu-id="5b8d0-315">**Value**</span></span>|<span data-ttu-id="5b8d0-316">**说明**</span><span class="sxs-lookup"><span data-stu-id="5b8d0-316">**Description**</span></span>|
|:-----|:-----|
|`SFV=NSPM`|<span data-ttu-id="5b8d0-317">邮件被标记为非垃圾邮件并发送给预期收件人。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-317">The message was marked as non-spam and was sent to the intended recipients.</span></span>|
|`SFV=SPM`|<span data-ttu-id="5b8d0-318">邮件由内容筛选器标记为垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-318">The message was marked as spam by the content filter.</span></span>|
|`SFV=BLK`|<span data-ttu-id="5b8d0-319">跳过筛选但阻止邮件，因为它是由已阻止发件人发送。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-319">Filtering was skipped and the message was blocked because it originated from a blocked sender.</span></span>|
|`SFV=SKS`|<span data-ttu-id="5b8d0-p150">在内容筛选器处理之前，邮件被标记为垃圾邮件。这包括符合以下传输规则条件的邮件：自动将邮件标记为垃圾邮件并规避其他所有筛选。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-p150">The message was marked as spam prior to being processed by the content filter. This includes messages where the message matched a Transport rule to automatically mark it as spam and bypass all additional filtering.</span></span>|
|`SCL=<number>`|<span data-ttu-id="5b8d0-322">有关不同的 SCL 值及其含义的详细信息，请参阅[垃圾邮件可信度](https://technet.microsoft.com/library/jj200686.aspx)。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-322">For more information about the different SCL values and what they mean, see [Spam confidence levels](https://technet.microsoft.com/library/jj200686.aspx).</span></span>|
|`PCL=<number>`|<span data-ttu-id="5b8d0-p151">邮件的仿冒可能性等级 (PCL) 值。可按照[垃圾邮件可信度](https://technet.microsoft.com/library/jj200686.aspx)中介绍 SCL 值的方式对这些值做出解释。  </span><span class="sxs-lookup"><span data-stu-id="5b8d0-p151">The Phishing Confidence Level (PCL) value of the message. These can be interpreted the same way as the SCL values documented in [Spam confidence levels](https://technet.microsoft.com/library/jj200686.aspx).</span></span>|
|`DI=SB`|<span data-ttu-id="5b8d0-325">已阻止邮件发件人。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-325">The sender of the message was blocked.</span></span>|
|`DI=SQ`|<span data-ttu-id="5b8d0-326">邮件已隔离。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-326">The message was quarantined.</span></span>|
|`DI=SD`|<span data-ttu-id="5b8d0-327">邮件已删除。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-327">The message was deleted.</span></span>|
|`DI=SJ`|<span data-ttu-id="5b8d0-328">邮件已发送至收件人的"垃圾邮件"文件夹。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-328">The message was sent to the recipient's Junk Email folder.</span></span>|
|`DI=SN`|<span data-ttu-id="5b8d0-p152">邮件已通过高风险传送池路由。有关详细信息，请参阅[高风险传递池用于出站邮件](https://technet.microsoft.com/library/jj200746.aspx)。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-p152">The message was routed through the higher risk delivery pool. For more information, see [High-risk delivery pool for outbound messages](https://technet.microsoft.com/library/jj200746.aspx).</span></span>|
|`DI=SO`|<span data-ttu-id="5b8d0-331">邮件已通过正常出站传送池路由。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-331">The message was routed through the normal outbound delivery pool.</span></span>|
|<span data-ttu-id="5b8d0-332">SFS = [a]</span><span class="sxs-lookup"><span data-stu-id="5b8d0-332">\`SFS=[a]</span></span>|<span data-ttu-id="5b8d0-333">SFS = [b]</span><span class="sxs-lookup"><span data-stu-id="5b8d0-333">SFS=[b]\`</span></span>|<span data-ttu-id="5b8d0-334">说明匹配此垃圾邮件规则。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-334">This denotes that spam rules were matched.</span></span>|
|`IPV=CAL`|<span data-ttu-id="5b8d0-335">邮件已获得垃圾邮件筛选器的允许，因为 IP 地址已在连接筛选器的 IP 允许列表中指定。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-335">The message was allowed through the spam filters because the IP address was specified in an IP Allow list in the connection filter.</span></span>|
|`H=<EHLOstring>`|<span data-ttu-id="5b8d0-336">连接的电子邮件服务器的 HELO 或 EHLO 字符串。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-336">The HELO or EHLO string of the connecting email server.</span></span>|
|`PTR=<ReverseDNS>`|<span data-ttu-id="5b8d0-337">发送 IP 地址的 PTR 记录，也被称为反向 DNS 地址。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-337">The PTR record of the sending IP address, also known as the reverse DNS address.</span></span>|

<span data-ttu-id="5b8d0-338">邮件被过滤为垃圾邮件，如下所示的示例**custom_data**值：</span><span class="sxs-lookup"><span data-stu-id="5b8d0-338">An example **custom_data** value for a message that's filtered for spam like this:</span></span>

`S:SFA=SUM|SFV=SPM|IPV=CAL|SRV=BULK|SFS=470454002|SFS=349001|SCL=9|SCORE=-1|LIST=0|DI=SN|RD=ftmail.inc.com|H=ftmail.inc.com|CIP=98.129.140.74|SFP=1501|ASF=1|CTRY=US|CLTCTRY=|LANG=en|LAT=287|LAT=260|LAT=18;`

#### <a name="malware-filter-agent"></a><span data-ttu-id="5b8d0-339">恶意软件筛选器代理</span><span class="sxs-lookup"><span data-stu-id="5b8d0-339">Malware filter agent</span></span>

<span data-ttu-id="5b8d0-p153">**Custom_data**值开头的`S:AMA`是从恶意软件筛选器代理。下表中描述的关键详细信息：</span><span class="sxs-lookup"><span data-stu-id="5b8d0-p153">A **custom_data** value that starts with `S:AMA` is from the malware filter agent. The key details are described in the following table:</span></span>

|<span data-ttu-id="5b8d0-342">**值**</span><span class="sxs-lookup"><span data-stu-id="5b8d0-342">**Value**</span></span>|<span data-ttu-id="5b8d0-343">**说明**</span><span class="sxs-lookup"><span data-stu-id="5b8d0-343">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="5b8d0-344">AMA = SUM</span><span class="sxs-lookup"><span data-stu-id="5b8d0-344">\`AMA=SUM</span></span>|<span data-ttu-id="5b8d0-345">v=1</span><span class="sxs-lookup"><span data-stu-id="5b8d0-345">v=1</span></span>|<span data-ttu-id="5b8d0-346">` or `AMA=EV</span><span class="sxs-lookup"><span data-stu-id="5b8d0-346">` or `AMA=EV</span></span>|<span data-ttu-id="5b8d0-347">v = 1</span><span class="sxs-lookup"><span data-stu-id="5b8d0-347">v=1\`</span></span>|<span data-ttu-id="5b8d0-p154">邮件已确定包含恶意软件。`SUM`指示恶意软件可能已被检测到任意数量的引擎。`EV`表示特定引擎检测到恶意软件。当恶意软件检测到某个引擎这会触发后续操作。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-p154">The message was determined to contain malware. `SUM` indicates the malware could've been detected by any number of engines. `EV` indicates the malware was detected by a specific engine. When malware is detected by an engine this triggers the subsequent actions.</span></span>|
|`Action=r`|<span data-ttu-id="5b8d0-352">邮件已被替换。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-352">The message was replaced.</span></span>|
|`Action=p`|<span data-ttu-id="5b8d0-353">邮件已被忽略。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-353">The message was bypassed.</span></span>|
|`Action=d`|<span data-ttu-id="5b8d0-354">邮件已被延迟。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-354">The message was deferred.</span></span>|
|`Action=s`|<span data-ttu-id="5b8d0-355">邮件已删除。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-355">The message was deleted.</span></span>|
|`Action=st`|<span data-ttu-id="5b8d0-356">邮件已被忽略。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-356">The message was bypassed.</span></span>|
|`Action=sy`|<span data-ttu-id="5b8d0-357">邮件已被忽略。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-357">The message was bypassed.</span></span>|
|`Action=ni`|<span data-ttu-id="5b8d0-358">邮件已被拒绝。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-358">The message was rejected.</span></span>|
|`Action=ne`|<span data-ttu-id="5b8d0-359">邮件已被拒绝。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-359">The message was rejected.</span></span>|
|`Action=b`|<span data-ttu-id="5b8d0-360">邮件已被阻止。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-360">The message was blocked.</span></span>|
|`Name=<malware>`|<span data-ttu-id="5b8d0-361">已检测到的恶意软件的名称。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-361">The name of the malware that was detected.</span></span>|
|`File=<filename>`|<span data-ttu-id="5b8d0-362">恶意软件中包含的文件名称。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-362">The name of the file that contained the malware.</span></span>|

<span data-ttu-id="5b8d0-363">为包含恶意软件的邮件示例**custom_data**值如下所示：</span><span class="sxs-lookup"><span data-stu-id="5b8d0-363">An example **custom_data** value for a message that contains malware looks like this:</span></span>

`S:AMA=SUM|v=1|action=b|error=|atch=1;S:AMA=EV|engine=M|v=1|sig=1.155.974.0|name=DOS/Test_File|file=filename;S:AMA=EV|engine=A|v=1|sig=201707282038|name=Test_File|file=filename`

#### <a name="transport-rule-agent"></a><span data-ttu-id="5b8d0-364">传输规则代理</span><span class="sxs-lookup"><span data-stu-id="5b8d0-364">Transport rule agent</span></span>

<span data-ttu-id="5b8d0-p155">**Custom_data**值开头的`S:TRA`是传输规则代理的邮件流规则 （也称作传输规则）。下表中描述的关键详细信息：</span><span class="sxs-lookup"><span data-stu-id="5b8d0-p155">A **custom_data** value that starts with`S:TRA` is from the transport rule agent for mail flow rules (also known as transport rules). The key details are described in the following table:</span></span>

|<span data-ttu-id="5b8d0-367">**值**</span><span class="sxs-lookup"><span data-stu-id="5b8d0-367">**Value**</span></span>|<span data-ttu-id="5b8d0-368">**说明**</span><span class="sxs-lookup"><span data-stu-id="5b8d0-368">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="5b8d0-369">ETR</span><span class="sxs-lookup"><span data-stu-id="5b8d0-369">\`ETR</span></span>|<span data-ttu-id="5b8d0-370">ruleId =<guid>\`</span><span class="sxs-lookup"><span data-stu-id="5b8d0-370">ruleId=<guid>\`</span></span>|<span data-ttu-id="5b8d0-371">匹配的规则 ID。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-371">The rule ID that was matched.</span></span>|
|`St=<datetime>`|<span data-ttu-id="5b8d0-372">日期和时间发生规则匹配时的 UTC。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-372">The date and time in UTC when the rule match occurred.</span></span>|
|`Action=<ActionDefinition>`|<span data-ttu-id="5b8d0-p156">应用操作。有关可用操作的列表，请参阅[Mail flow 规则操作在 Exchange Online](https://technet.microsoft.com/library/jj919237.aspx)。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-p156">The action that was applied. For a list of available actions, see [Mail flow rule actions in Exchange Online](https://technet.microsoft.com/library/jj919237.aspx).</span></span>|
|`Mode=<Mode>`|<span data-ttu-id="5b8d0-p157">规则的模式。有效值为：</span><span class="sxs-lookup"><span data-stu-id="5b8d0-p157">The mode of the rule. Valid values are: </span></span><br/><span data-ttu-id="5b8d0-377">•**强制**： 将强制实施规则的所有操作。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-377">• **Enforce**: All actions on the rule will be enforced.</span></span> <br/><span data-ttu-id="5b8d0-378">•**使用策略提示测试：**： 将发送所有策略提示操作，但其他强制实施操作不会作用于。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-378">• **Test with Policy Tips:**: Any Policy Tip actions will be sent, but other enforcement actions will not be acted on.</span></span> <br/><span data-ttu-id="5b8d0-379">•**不使用策略提示的情况下测试**： 日志文件中将列出操作，但不是会以任何方式通知发件人和强制实施操作不会作用于。</span><span class="sxs-lookup"><span data-stu-id="5b8d0-379">• **Test without Policy Tips**: Actions will be listed in a log file, but senders will not be notified in any way, and enforcement actions will not be acted on.</span></span>|

<span data-ttu-id="5b8d0-380">示例**custom_data**值的邮件的邮件流规则的条件相匹配如下所示：</span><span class="sxs-lookup"><span data-stu-id="5b8d0-380">An example **custom_data** value for a messages that matches the conditions of a mail flow rule looks like this:</span></span>

`S:TRA=ETR|ruleId=19a25eb2-3e43-4896-ad9e-47b6c359779d|st=7/17/2017 12:31:25 AM|action=ApplyHtmlDisclaimer|sev=1|mode=Enforce`
