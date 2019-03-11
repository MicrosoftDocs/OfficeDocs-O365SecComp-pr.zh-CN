---
title: Security & 合规性中心中的邮件跟踪
ms.author: chrisda
author: chrisda
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 3e64f99d-ac33-4aba-91c5-9cb4ca476803
description: 管理员可以使用安全 & 合规中心中的邮件跟踪来查明邮件发生了什么情况。
ms.openlocfilehash: 73d4aa6f9a12b8e1bf955dad09e4c4ca7290dae8
ms.sourcegitcommit: 74ad22a5c6c3c9d9324f0f97070909e323a4e9cf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/11/2019
ms.locfileid: "30524086"
---
# <a name="message-trace-in-the-security--compliance-center"></a><span data-ttu-id="48cd8-103">Security & 合规性中心中的邮件跟踪</span><span class="sxs-lookup"><span data-stu-id="48cd8-103">Message trace in the Security & Compliance Center</span></span>

## <a name="overview"></a><span data-ttu-id="48cd8-104">概述</span><span class="sxs-lookup"><span data-stu-id="48cd8-104">Overview</span></span>

<span data-ttu-id="48cd8-105">Security & 合规性中心中的邮件跟踪在电子邮件通过 Exchange Online 组织时遵循这些电子邮件。</span><span class="sxs-lookup"><span data-stu-id="48cd8-105">Message trace in the Security & Compliance Center follows email messages as they travel through your Exchange Online organization.</span></span> <span data-ttu-id="48cd8-106">您可以确定服务是否已接收、拒绝、推迟或发送邮件。</span><span class="sxs-lookup"><span data-stu-id="48cd8-106">You can determine if a message was received, rejected, deferred, or delivered by the service.</span></span> <span data-ttu-id="48cd8-107">它还显示邮件在到达其最终状态之前对邮件执行的操作。</span><span class="sxs-lookup"><span data-stu-id="48cd8-107">It also shows what actions were taken on the message before it reached its final status.</span></span>

<span data-ttu-id="48cd8-108">Security & 合规性中心中的邮件跟踪改进了在 Exchange 管理中心 (EAC) 中可用的邮件跟踪。</span><span class="sxs-lookup"><span data-stu-id="48cd8-108">Message trace in the Security & Compliance Center improves upon message trace that was available in the Exchange admin center (EAC).</span></span> <span data-ttu-id="48cd8-109">您可以使用邮件跟踪中的信息来有效地回答用户对其邮件发生的问题、解决邮件流问题以及验证策略更改的问题。</span><span class="sxs-lookup"><span data-stu-id="48cd8-109">You can use the information from message trace to efficiently answer user questions about what happened to their messages, troubleshoot mail flow issues, and validate policy changes.</span></span>

## <a name="open-message-trace"></a><span data-ttu-id="48cd8-110">打开邮件跟踪</span><span class="sxs-lookup"><span data-stu-id="48cd8-110">Open message trace</span></span>

1. <span data-ttu-id="48cd8-111">使用您的 工作或学校帐户[登录到 Office 365](https://support.office.com/article/e9eb7d51-5430-4929-91ab-6157c5a050b4)。</span><span class="sxs-lookup"><span data-stu-id="48cd8-111">[Sign in to Office 365](https://support.office.com/article/e9eb7d51-5430-4929-91ab-6157c5a050b4) with your work or school account.</span></span>

2. <span data-ttu-id="48cd8-112">在左上角选择应用启动器图标 ![Office 365 应用启动器图标](media/0aaa6945-f9a4-4b13-bf5f-d5c5dbe978fb.png)，然后选择" **管理**"。</span><span class="sxs-lookup"><span data-stu-id="48cd8-112">Select the app launcher icon ![Office 365 app launcher icon](media/0aaa6945-f9a4-4b13-bf5f-d5c5dbe978fb.png) in the upper-left and choose **Admin**.</span></span>

3. <span data-ttu-id="48cd8-113">在左下角导航中, 展开 "**管理中心**", 然后选择 "**安全 & 合规性**"。</span><span class="sxs-lookup"><span data-stu-id="48cd8-113">In the lower-left navigation, expand **Admin centers** and select **Security & Compliance**.</span></span>

4. <span data-ttu-id="48cd8-114">在打开的**安全 & 合规性**页面中, 展开 "**邮件流**", 然后选择 "**邮件跟踪**"。</span><span class="sxs-lookup"><span data-stu-id="48cd8-114">In the **Security & Compliance** page that opens, expand **Mail flow**, and select **Message trace**.</span></span>

## <a name="message-trace-page"></a><span data-ttu-id="48cd8-115">邮件跟踪页</span><span class="sxs-lookup"><span data-stu-id="48cd8-115">Message trace page</span></span>

<span data-ttu-id="48cd8-116">从这里, 可以通过单击 "**启动跟踪**" 按钮来启动新的默认跟踪。</span><span class="sxs-lookup"><span data-stu-id="48cd8-116">From here you can start a new default trace by clicking on the **Start a trace** button.</span></span> <span data-ttu-id="48cd8-117">这将在最近两天内搜索所有发件人和收件人的所有邮件。</span><span class="sxs-lookup"><span data-stu-id="48cd8-117">This will search for all messages for all senders and recipients for the last two days.</span></span> <span data-ttu-id="48cd8-118">或者, 您可以使用可用查询类别中的一个存储查询, 也可以按自己的方式运行这些查询, 也可以将它们用作自己的查询的起始点:</span><span class="sxs-lookup"><span data-stu-id="48cd8-118">Or you can use one of the stored queries from the available query categories and either run them as-is or use them as starting points for your own queries:</span></span>

- <span data-ttu-id="48cd8-119">**默认查询**: Office 365 提供的内置查询。</span><span class="sxs-lookup"><span data-stu-id="48cd8-119">**Default queries**: Built-in queries provided by Office 365.</span></span>

- <span data-ttu-id="48cd8-120">**自定义查询**: 组织在组织中保存以供将来使用的查询。</span><span class="sxs-lookup"><span data-stu-id="48cd8-120">**Custom queries**: Queries saved by admins in your organization for future use.</span></span>

- <span data-ttu-id="48cd8-121">自动**保存的查询**: 最近十个最近运行的查询。</span><span class="sxs-lookup"><span data-stu-id="48cd8-121">**Autosaved queries**: The last ten most recently run queries.</span></span> <span data-ttu-id="48cd8-122">通过此列表, 可以轻松地从中断的位置开始选择。</span><span class="sxs-lookup"><span data-stu-id="48cd8-122">This list makes it simple to pick up where you left off.</span></span>

<span data-ttu-id="48cd8-123">此外, 在此页面上也是一个**可下载的报告**部分, 其中包含已提交的请求以及报告本身 (如果有) 可供下载。</span><span class="sxs-lookup"><span data-stu-id="48cd8-123">Also on this page is a **Downloadable reports** section for the requests you've submitted, as well as the reports themselves when they're are available for download.</span></span>

## <a name="options-for-a-new-message-trace"></a><span data-ttu-id="48cd8-124">新邮件跟踪选项</span><span class="sxs-lookup"><span data-stu-id="48cd8-124">Options for a new message trace</span></span>

### <a name="filter-by-senders-and-recipients"></a><span data-ttu-id="48cd8-125">按发件人和收件人进行筛选</span><span class="sxs-lookup"><span data-stu-id="48cd8-125">Filter by senders and recipients</span></span>

<span data-ttu-id="48cd8-126">默认值为**所有发件人**和**所有收件人**, 但您可以使用下列字段筛选结果:</span><span class="sxs-lookup"><span data-stu-id="48cd8-126">The default values are **All senders** and **All recipients**, but you can use the following fields to filter the results:</span></span>

- <span data-ttu-id="48cd8-127">**由以下人员**: 单击此字段可选择组织中的一个或多个发件人。</span><span class="sxs-lookup"><span data-stu-id="48cd8-127">**By these people**: Click in this field to select one or more senders from your organization.</span></span> <span data-ttu-id="48cd8-128">您还可以开始键入名称, 列表中的项目将按您键入的内容进行筛选, 这与搜索页面的行为方式非常相似。</span><span class="sxs-lookup"><span data-stu-id="48cd8-128">You can also start to type a name and the items in the list will be filtered by what you've typed, much like how a search page behaves.</span></span>

- <span data-ttu-id="48cd8-129">对于**以下人员**: 在此字段中单击以选择组织中的一个或多个收件人。</span><span class="sxs-lookup"><span data-stu-id="48cd8-129">**To these people**: Click in this field to select one or more recipients in your organization.</span></span>

> [!NOTE]<span data-ttu-id="48cd8-130">您还可以键入外部发件人和收件人的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="48cd8-130">You can also type the email addresses of external senders and recipients.</span></span> <span data-ttu-id="48cd8-131">支持通配符 (`*@contoso.com`或`scot?@contoso.com`), 但不能同时在同一字段中使用多个通配符条目。</span><span class="sxs-lookup"><span data-stu-id="48cd8-131">Wildcards are supported (`*@contoso.com` or `scot?@contoso.com`), but you can't use multiple wildcard entries in the same field at the same time.</span></span>
> [!NOTE]<span data-ttu-id="48cd8-132">可以粘贴多个发件人或收件人列表, 用`;`分号 () 分隔。</span><span class="sxs-lookup"><span data-stu-id="48cd8-132"> You can paste multiple senders or recipients list separated with semicolon (`;\`).</span></span> <span data-ttu-id="48cd8-133">允许使用`\s`空格 ()、回车`\r`符 () 或下`\n`一行 () 符号。</span><span class="sxs-lookup"><span data-stu-id="48cd8-133">Spaces (`\s`), carriage return (`\r`) or next lines (`\n`) symbols are allowed.</span></span>

### <a name="time-range"></a><span data-ttu-id="48cd8-134">时间范围</span><span class="sxs-lookup"><span data-stu-id="48cd8-134">Time range</span></span>

<span data-ttu-id="48cd8-135">默认值为**2 天**, 但您可以指定最长为90天的日期/时间范围。</span><span class="sxs-lookup"><span data-stu-id="48cd8-135">The default value is **2 days**, but you can specify date/time ranges of up to 90 days.</span></span> <span data-ttu-id="48cd8-136">使用日期/时间范围时, 请考虑以下问题:</span><span class="sxs-lookup"><span data-stu-id="48cd8-136">When you use date/time ranges, consider these issues:</span></span>

- <span data-ttu-id="48cd8-137">默认情况下, 使用时间行在**滑块**视图中选择时间范围。</span><span class="sxs-lookup"><span data-stu-id="48cd8-137">By default, you select the time range in **Slider** view using a time line.</span></span> <span data-ttu-id="48cd8-138">您只能选择显示的日期或时间设置。</span><span class="sxs-lookup"><span data-stu-id="48cd8-138">You can only select the day or time settings that are displayed.</span></span> <span data-ttu-id="48cd8-139">如果尝试选择 "介于" 值, 则会将 "开始/结束" 气泡对齐到最接近的显示设置。</span><span class="sxs-lookup"><span data-stu-id="48cd8-139">Trying to select an in-between value will snap the start/end bubble to the nearest displayed setting.</span></span>

   ![Security & 合规性中心内的新邮件跟踪中的滑块时间范围](media/55a9e9c1-f7d5-4047-b217-824e8b976bcb.png)

   <span data-ttu-id="48cd8-141">不过, 您还可以切换到**自定义**视图, 在其中可以指定**开始日期**和**结束日期**值 (包括时间), 还可以为日期/时间范围选择**时区**。</span><span class="sxs-lookup"><span data-stu-id="48cd8-141">But, you can also switch to **Custom** view where you can specify the **Start date** and **End date** values (including times), and you can also select the **Time zone** for the date/time range.</span></span> <span data-ttu-id="48cd8-142">请注意,**时区**设置适用于您的查询输入和查询结果。</span><span class="sxs-lookup"><span data-stu-id="48cd8-142">Note that the **Time zone** setting applies to both your query inputs and your query results.</span></span>

   ![Security & 合规性中心的新邮件跟踪中的自定义时间范围](media/ed4c8d50-9ea5-4694-93f9-ee3ab6660b4f.png)

   <span data-ttu-id="48cd8-144">对于10天或更少, 结果将立即作为**摘要**报告提供。</span><span class="sxs-lookup"><span data-stu-id="48cd8-144">For 10 days or less, the results are available instantly as a **Summary** report.</span></span> <span data-ttu-id="48cd8-145">如果指定的时间范围稍微大于10天, 则结果将延迟, 因为它们仅可用作可下载的 CSV 文件 (**增强的摘要**或**扩展**报告)。</span><span class="sxs-lookup"><span data-stu-id="48cd8-145">If you specify a time range that's even slightly greater than 10 days, the results will be delayed as they are only available as a downloadable CSV file ( **Enhanced summary** or **Extended** reports).</span></span>

   <span data-ttu-id="48cd8-146">有关不同报告类型的详细信息, 请参阅本主题中的[选择报告类型](#choose-report-type)部分。</span><span class="sxs-lookup"><span data-stu-id="48cd8-146">For more information about the different report types, see the [Choose report type](#choose-report-type) section in this topic.</span></span>

   <span data-ttu-id="48cd8-147">**注意**: 已使用存档的邮件跟踪数据准备好了增强的摘要和扩展报告, 并且在报告可供下载前最多可能需要几个小时的时间。</span><span class="sxs-lookup"><span data-stu-id="48cd8-147">**Note**: Enhanced summary and Extended reports are prepared using archived message trace data, and it can take up to several hours before your report is available for download.</span></span> <span data-ttu-id="48cd8-148">根据其他管理员同时提交报告请求的数量, 您还可能会注意到, 在处理排队请求之前, 会先延迟一段时间。</span><span class="sxs-lookup"><span data-stu-id="48cd8-148">Depending on how many other admins have also submitted report requests around the same time, you might also notice a delay before processing starts for your queued request.</span></span>

- <span data-ttu-id="48cd8-149">在**滑块**视图中保存查询保存相对时间范围 (例如, 从今天开始3天)。</span><span class="sxs-lookup"><span data-stu-id="48cd8-149">Saving a query in **Slider** view saves the relative time range (for example, 3 days from today).</span></span> <span data-ttu-id="48cd8-150">在**自定义**视图中保存查询会保存绝对日期/时间范围 (例如, 2018-05-06 13:00 到 2018-05-08 18:00)。</span><span class="sxs-lookup"><span data-stu-id="48cd8-150">Saving a query in **Custom** view saves the absolute date/time range (for example, 2018-05-06 13:00 to 2018-05-08 18:00).</span></span>

### <a name="more-search-options"></a><span data-ttu-id="48cd8-151">更多搜索选项</span><span class="sxs-lookup"><span data-stu-id="48cd8-151">More search options</span></span>

#### <a name="delivery-status"></a><span data-ttu-id="48cd8-152">传递状态</span><span class="sxs-lookup"><span data-stu-id="48cd8-152">Delivery status</span></span>

<span data-ttu-id="48cd8-153">您可以保留**所有**选定的默认值, 也可以选择下列值之一来筛选结果:</span><span class="sxs-lookup"><span data-stu-id="48cd8-153">You can leave the default value **All** selected, or you can select one of the following values to filter the results:</span></span>

- <span data-ttu-id="48cd8-154">已**传递**: 邮件已成功传递到预期的目标。</span><span class="sxs-lookup"><span data-stu-id="48cd8-154">**Delivered**: The message was successfully delivered to the intended destination.</span></span>

- <span data-ttu-id="48cd8-155">**挂起**: 正在尝试或重新尝试传递邮件。</span><span class="sxs-lookup"><span data-stu-id="48cd8-155">**Pending**: Delivery of the message is being attempted or re-attempted.</span></span>

- <span data-ttu-id="48cd8-156">已**展开**: 通讯组收件人在传递给组中的单个成员之前展开。</span><span class="sxs-lookup"><span data-stu-id="48cd8-156">**Expanded**: A distribution group recipient was expanded before delivery to the individual members of the group.</span></span>

- <span data-ttu-id="48cd8-157">**失败**: 邮件未送达。</span><span class="sxs-lookup"><span data-stu-id="48cd8-157">**Failed**: The message was not delivered.</span></span>

- <span data-ttu-id="48cd8-158">已**隔离**: 邮件被隔离 (如垃圾邮件、批量邮件或网络钓鱼)。</span><span class="sxs-lookup"><span data-stu-id="48cd8-158">**Quarantined**: The message was quarantined (as spam, bulk mail, or phishing).</span></span> <span data-ttu-id="48cd8-159">有关详细信息, 请参阅[在 Office 365 中隔离电子邮件消息](https://support.office.com/article/4c234874-015e-4768-8495-98fcccfc639b.aspx)。</span><span class="sxs-lookup"><span data-stu-id="48cd8-159">For more information, see [Quarantine email messages in Office 365](https://support.office.com/article/4c234874-015e-4768-8495-98fcccfc639b.aspx).</span></span>

- <span data-ttu-id="48cd8-160">**筛选为垃圾**邮件: 邮件已标识为垃圾邮件, 已被拒绝或阻止 (未隔离)。</span><span class="sxs-lookup"><span data-stu-id="48cd8-160">**Filtered as spam**: The message was identified spam, and was rejected or blocked (not quarantined).</span></span>

- <span data-ttu-id="48cd8-161">**获取状态:** 该邮件最近由 Office 365 接收, 但其他状态数据仍不可用。</span><span class="sxs-lookup"><span data-stu-id="48cd8-161">**Getting status:** The message was recently received by Office 365, but no other status data is yet available.</span></span> <span data-ttu-id="48cd8-162">请在几分钟后回来查看。</span><span class="sxs-lookup"><span data-stu-id="48cd8-162">Check back in a few minutes.</span></span>

<span data-ttu-id="48cd8-163">**注意**:**作为垃圾邮件\*\*\*\*挂起、** **隔离**和筛选的值仅适用于少于10天的搜索。</span><span class="sxs-lookup"><span data-stu-id="48cd8-163">**Note**: The values **Pending,** **Quarantined**, and **Filter as spam** are only available for searches less than 10 days.</span></span> <span data-ttu-id="48cd8-164">此外, 实际和报告的传递状态之间可能有5到10分钟的延迟。</span><span class="sxs-lookup"><span data-stu-id="48cd8-164">Also, there might be a 5 to 10 minute delay between the actual and reported delivery status.</span></span>

#### <a name="message-id"></a><span data-ttu-id="48cd8-165">邮件 ID</span><span class="sxs-lookup"><span data-stu-id="48cd8-165">Message ID</span></span>

<span data-ttu-id="48cd8-166">这是在邮件头的**邮件 id:** 头字段中找到的 internet 邮件 id (也称为客户端 ID)。</span><span class="sxs-lookup"><span data-stu-id="48cd8-166">This is the internet message ID (also known as the Client ID) that's found in the **Message-ID:** header field in the message header.</span></span> <span data-ttu-id="48cd8-167">用户可为您提供此值来调查特定邮件。</span><span class="sxs-lookup"><span data-stu-id="48cd8-167">Users can give you this value to investigate specific messages.</span></span>

<span data-ttu-id="48cd8-168">该值在邮件生存期内是常量。</span><span class="sxs-lookup"><span data-stu-id="48cd8-168">This value is constant for the lifetime of the message.</span></span> <span data-ttu-id="48cd8-169">对于在 Office 365 或 Exchange 中创建的邮件, 值的格式`<GUID@ServerFQDN>`为, 包括尖括号 (\< \>)。</span><span class="sxs-lookup"><span data-stu-id="48cd8-169">For messages created in Office 365 or Exchange, the value is in the format `<GUID@ServerFQDN>`, including the angle brackets (\< \>).</span></span> <span data-ttu-id="48cd8-170">例如，`<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`。</span><span class="sxs-lookup"><span data-stu-id="48cd8-170">For example, `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`.</span></span> <span data-ttu-id="48cd8-171">其他邮件系统可能使用不同的语法或值。</span><span class="sxs-lookup"><span data-stu-id="48cd8-171">Other messaging systems might use different syntax or values.</span></span> <span data-ttu-id="48cd8-172">此值应是唯一的, 但并不是所有的电子邮件系统都严格遵守此要求。</span><span class="sxs-lookup"><span data-stu-id="48cd8-172">This value is supposed to be unique, but not all email systems strictly follow this requirement.</span></span> <span data-ttu-id="48cd8-173">如果**邮件 ID:** 标头字段不存在或对于来自外部源的传入邮件为空, 则分配一个任意值。</span><span class="sxs-lookup"><span data-stu-id="48cd8-173">If the **Message-ID:** header field doesn't exist or is blank for incoming messages from external sources, an arbitrary value is assigned.</span></span>

<span data-ttu-id="48cd8-174">使用**邮件 ID**筛选结果时, 请务必包含完整的字符串, 包括任何尖括号。</span><span class="sxs-lookup"><span data-stu-id="48cd8-174">When you use **Message ID** to filter the results, be sure to include the full string, including any angle brackets.</span></span>

#### <a name="direction"></a><span data-ttu-id="48cd8-175">Direction</span><span class="sxs-lookup"><span data-stu-id="48cd8-175">Direction</span></span>

<span data-ttu-id="48cd8-176">您可以保留**所有**选中的默认值, 也可以选择 "**入站**(发送给组织中的收件人的邮件") 或 "**出站**(从组织中的用户发送的邮件") 来筛选结果。</span><span class="sxs-lookup"><span data-stu-id="48cd8-176">You can leave the default value **All** selected, or you can select **Inbound** (messages sent to recipients in your organization) or **Outbound** (messages sent from users in your organization) to filter the results.</span></span>

#### <a name="original-client-ip-address"></a><span data-ttu-id="48cd8-177">原始客户端 IP 地址</span><span class="sxs-lookup"><span data-stu-id="48cd8-177">Original client IP address</span></span>

<span data-ttu-id="48cd8-178">您可以通过客户端 IP 地址对结果进行文件管理, 以调查发送大量垃圾邮件或恶意软件的受攻击的计算机。</span><span class="sxs-lookup"><span data-stu-id="48cd8-178">You can filer the results by client IP address to investigate hacked computers that are sending large amounts of spam or malware.</span></span> <span data-ttu-id="48cd8-179">虽然邮件可能看起来来自多个发件人, 但很可能是同一台计算机正在生成所有邮件。</span><span class="sxs-lookup"><span data-stu-id="48cd8-179">Although the messages might appear to come from multiple senders, it's likely that the same computer is generating all of the messages.</span></span>

<span data-ttu-id="48cd8-180">**注意**: 客户端 IP 地址信息仅在10天内可用, 并且仅在**增强的摘要**或**扩展**的报告 (可下载的 CSV 文件) 中可用。</span><span class="sxs-lookup"><span data-stu-id="48cd8-180">**Note**: The client IP address information is only available for 10 days, and is only available in the **Enhanced summary** or **Extended** reports (downloadable CSV files).</span></span>

### <a name="choose-report-type"></a><span data-ttu-id="48cd8-181">选择报告类型</span><span class="sxs-lookup"><span data-stu-id="48cd8-181">Choose report type</span></span>

<span data-ttu-id="48cd8-182">可用的报告类型包括:</span><span class="sxs-lookup"><span data-stu-id="48cd8-182">The available report types are:</span></span>

- <span data-ttu-id="48cd8-183">**摘要**: 如果时间范围少于10天, 且不需要其他筛选选项, 则为可用。</span><span class="sxs-lookup"><span data-stu-id="48cd8-183">**Summary**: Available if the time range is less than 10 days, and requires no additional filtering options.</span></span> <span data-ttu-id="48cd8-184">搜索结果几乎会在您单击 "**搜索**" 之后立即可用。</span><span class="sxs-lookup"><span data-stu-id="48cd8-184">The results are available almost immediately after you click **Search**.</span></span>

- <span data-ttu-id="48cd8-185">**增强的摘要**或**扩展**: 这些报告仅可用作可下载的 CSV 文件, 并且需要一个或多个以下筛选选项, 而不考虑时间范围:**由这些人员**、**这些**人员或**邮件 ID**。</span><span class="sxs-lookup"><span data-stu-id="48cd8-185">**Enhanced summary** or **Extended**: These reports are only available as downloadable CSV files, and require one or more of the following filtering options regardless of the time range: **By these people**, **To these people**, or **Message ID**.</span></span> <span data-ttu-id="48cd8-186">您可以对发件人或收件人使用通配符 (例如, \*@contoso .com)。</span><span class="sxs-lookup"><span data-stu-id="48cd8-186">You can use wildcards for the senders or the recipients (for example, \*@contoso.com).</span></span>

<span data-ttu-id="48cd8-187">**注意**：</span><span class="sxs-lookup"><span data-stu-id="48cd8-187">**Notes**:</span></span>

- <span data-ttu-id="48cd8-188">增强的摘要和扩展报告使用存档的邮件跟踪数据进行准备, 并且在报告可供下载前可能需要几个小时的时间。</span><span class="sxs-lookup"><span data-stu-id="48cd8-188">Enhanced summary and Extended reports are prepared using archived message trace data, and it can take up to several hours before your report is available to download.</span></span> <span data-ttu-id="48cd8-189">根据其他管理员同时提交报告请求的数量, 您可能还会注意到, 在开始处理排队的请求之前会有一段延迟时间。</span><span class="sxs-lookup"><span data-stu-id="48cd8-189">Depending on how many other admins have also submitted report requests around the same time, you might also notice a delay before your queued request starts to be processed.</span></span>

- <span data-ttu-id="48cd8-190">虽然可以为任何日期/时间范围选择增强的摘要或扩展报告, 但存档数据的最后四个小时通常对这两种类型的报告都不可用。</span><span class="sxs-lookup"><span data-stu-id="48cd8-190">While you can select an Enhanced summary or Extended report for any date/time range, commonly the last four hours of archived data will not yet be available for these two types of reports.</span></span>

<span data-ttu-id="48cd8-191">单击 "**下一步**" 时, 将显示一个摘要页, 其中列出了所选的筛选选项、报表的唯一的 (可编辑的) 标题以及在邮件跟踪完成时接收通知的电子邮件地址 (也是可编辑的)。, 并且必须位于组织的接受域之一中。</span><span class="sxs-lookup"><span data-stu-id="48cd8-191">When you click **Next**, you're presented with a summary page that lists the filtering options that you selected, a unique (editable) title for the report, and the email address that receives the notification when the message trace completes (also editable, and must be in one of your organization's accepted domains).</span></span> <span data-ttu-id="48cd8-192">单击 "**准备报告**" 以提交邮件跟踪。</span><span class="sxs-lookup"><span data-stu-id="48cd8-192">Click **Prepare report** to submit the message trace.</span></span> <span data-ttu-id="48cd8-193">在 "主**邮件跟踪**" 页面上, 您可以在**可下载报告**部分中看到报告的状态。</span><span class="sxs-lookup"><span data-stu-id="48cd8-193">On the main **Message trace** page, you can see the status of the report in the **Downloadable reports** section.</span></span>

<span data-ttu-id="48cd8-194">有关不同报告类型中返回的信息的详细信息, 请参阅下一节。</span><span class="sxs-lookup"><span data-stu-id="48cd8-194">For more information about the information that's returned in the different report types, see the next section.</span></span>

## <a name="message-trace-results"></a><span data-ttu-id="48cd8-195">邮件跟踪结果</span><span class="sxs-lookup"><span data-stu-id="48cd8-195">Message trace results</span></span>

<span data-ttu-id="48cd8-196">不同的报告类型返回不同级别的信息。</span><span class="sxs-lookup"><span data-stu-id="48cd8-196">The different report types return different levels of information.</span></span> <span data-ttu-id="48cd8-197">以下各节介绍了不同报告中提供的信息。</span><span class="sxs-lookup"><span data-stu-id="48cd8-197">The information that's available in the different reports is described in the following sections.</span></span>

### <a name="summary-report-output"></a><span data-ttu-id="48cd8-198">摘要报告输出</span><span class="sxs-lookup"><span data-stu-id="48cd8-198">Summary report output</span></span>

<span data-ttu-id="48cd8-199">运行邮件跟踪后, 将列出结果, 并按降序的日期/时间 (最新的优先) 进行排序。</span><span class="sxs-lookup"><span data-stu-id="48cd8-199">After running the message trace, the results will be listed, sorted by descending date/time (most recent first).</span></span>

![Security & 合规中心中的邮件跟踪摘要报告结果](media/0664bafe-0b03-477b-b571-0b046ac8c977.png)

<span data-ttu-id="48cd8-201">摘要报告包含以下信息:</span><span class="sxs-lookup"><span data-stu-id="48cd8-201">The summary report contains the following information:</span></span>

- <span data-ttu-id="48cd8-202">**日期**: 服务收到邮件的日期和时间 (使用配置的 UTC 时区)。</span><span class="sxs-lookup"><span data-stu-id="48cd8-202">**Date**: The date and time at which the message was received by the service, using the configured UTC time zone.</span></span>

- <span data-ttu-id="48cd8-203">**发件人**: 发件人的电子邮件地址 (*别名*@*域*)。</span><span class="sxs-lookup"><span data-stu-id="48cd8-203">**Sender**: The email address of the sender (*alias*@*domain*).</span></span>

- <span data-ttu-id="48cd8-204">**收件人**: 收件人或收件人的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="48cd8-204">**Recipient**: The email address of the recipient or recipients.</span></span> <span data-ttu-id="48cd8-205">对于发送给多个收件人的邮件, 每个收件人有一行。</span><span class="sxs-lookup"><span data-stu-id="48cd8-205">For a message sent to multiple recipients, there's one line per recipient.</span></span> <span data-ttu-id="48cd8-206">如果收件人是通讯组、动态通讯组或启用邮件的安全组, 则该组将成为第一个收件人, 然后组中的每个成员都在单独的行中。</span><span class="sxs-lookup"><span data-stu-id="48cd8-206">If the recipient is a distribution group, dynamic distribution group, or mail-enabled security group, the group will be the first recipient, and then each member of the group is on a separate line.</span></span>

- <span data-ttu-id="48cd8-207">**Subject**: 邮件 " **Subject:** " 字段的前256个字符。</span><span class="sxs-lookup"><span data-stu-id="48cd8-207">**Subject**: The first 256 characters of the message's **Subject:** field.</span></span>

- <span data-ttu-id="48cd8-208">**状态**: 这些值将在 "[传递状态](#delivery-status)" 一节中进行介绍。</span><span class="sxs-lookup"><span data-stu-id="48cd8-208">**Status**: These values are described in the [Delivery status](#delivery-status) section.</span></span>

<span data-ttu-id="48cd8-209">默认情况下, 加载第一个250结果并随时可用。</span><span class="sxs-lookup"><span data-stu-id="48cd8-209">By default, the first 250 results are loaded and readily available.</span></span> <span data-ttu-id="48cd8-210">向下滚动时, 将在加载下一批结果时略有暂停。</span><span class="sxs-lookup"><span data-stu-id="48cd8-210">When you scroll down, there's a slight pause as the next batch of results are loaded.</span></span> <span data-ttu-id="48cd8-211">除滚动之外, 您可以单击 "**全部加载**" 以加载最多为10000的所有结果。</span><span class="sxs-lookup"><span data-stu-id="48cd8-211">Instead of scrolling, you can click **Load all** to load all of the results up to a maximum of 10,000.</span></span>

<span data-ttu-id="48cd8-212">您可以单击列标题, 按该列中的值以升序或降序对结果进行排序。</span><span class="sxs-lookup"><span data-stu-id="48cd8-212">You can click on the column headers to sort the results by the values in that column in ascending or descending order.</span></span>

<span data-ttu-id="48cd8-213">您可以单击 "**筛选结果**" 按一个或多个列筛选结果。</span><span class="sxs-lookup"><span data-stu-id="48cd8-213">You can click **Filter results** to filter the results by one or more columns.</span></span>

<span data-ttu-id="48cd8-214">您可以通过单击 "**导出结果**" 选择一个或多个行, 然后选择 "**导出所有结果**"、"**导出加载结果**" 或 "**导出选定**项", 导出结果。</span><span class="sxs-lookup"><span data-stu-id="48cd8-214">You can export the results after you've selected one or more rows by clicking **Export results** and then selecting **Export all results**, **Export loaded results**, or **Export selected**.</span></span>

#### <a name="find-related-records-for-this-message"></a><span data-ttu-id="48cd8-215">查找此邮件的相关记录</span><span class="sxs-lookup"><span data-stu-id="48cd8-215">Find related records for this message</span></span>

<span data-ttu-id="48cd8-216">相关邮件记录是共享同一邮件 ID 的记录。</span><span class="sxs-lookup"><span data-stu-id="48cd8-216">Related message records are records that shared the same Message ID.</span></span> <span data-ttu-id="48cd8-217">请记住, 即使在两个人之间发送的单个邮件也可以生成多个记录。</span><span class="sxs-lookup"><span data-stu-id="48cd8-217">Remember, even a single message sent between two people can generate multiple records.</span></span> <span data-ttu-id="48cd8-218">当邮件受到通讯组展开、转发、邮件流规则 (也称为传输规则) 等的影响时, 将增加记录数。</span><span class="sxs-lookup"><span data-stu-id="48cd8-218">The number of records increases when the message is affected by distribution group expansion, forwarding, mail flow rules (also known as transport rules), etc.</span></span>

<span data-ttu-id="48cd8-219">选中行的复选框后, 可以通过单击显示的 "**查找相关**" 按钮, 或选择 "**更多选项** ![](media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> " 来查找**此邮件的相关记录**, 从而查找邮件的相关记录。</span><span class="sxs-lookup"><span data-stu-id="48cd8-219">After you select a row's check box, you can find related records for the message by clicking the **Find related** button that appears, or by selecting **More options** ![More](media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> **Find related records for this message**).</span></span>

<span data-ttu-id="48cd8-220">有关邮件 id 的详细信息, 请参阅本主题前面的邮件 id 一节。</span><span class="sxs-lookup"><span data-stu-id="48cd8-220">For more information about the Message ID, see the Message ID section earlier in this topic.</span></span>

#### <a name="message-trace-details"></a><span data-ttu-id="48cd8-221">邮件跟踪详细信息</span><span class="sxs-lookup"><span data-stu-id="48cd8-221">Message trace details</span></span>

<span data-ttu-id="48cd8-222">在摘要报告输出中, 可以使用以下任一方法来查看有关邮件的详细信息:</span><span class="sxs-lookup"><span data-stu-id="48cd8-222">In the summary report output, you can view details about a message by using either of the following methods:</span></span>

- <span data-ttu-id="48cd8-223">选择行 (单击除复选框之外的任何位置)。</span><span class="sxs-lookup"><span data-stu-id="48cd8-223">Select the row (click anywhere in the row except the check box).</span></span>

- <span data-ttu-id="48cd8-224">选中该行的复选框, 然后单击 "更多](media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> **选项** !["**查看详细信息**。</span><span class="sxs-lookup"><span data-stu-id="48cd8-224">Select the row's check box and click **More options** ![More](media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> **View message details**.</span></span>

   ![在摘要报告邮件跟踪中双击行后的详细信息将导致安全 & 合规性中心](media/e50ee7cd-810a-4c06-8b58-e56ffd7028d1.png)

<span data-ttu-id="48cd8-226">邮件跟踪详细信息包含摘要报告中不存在的以下附加信息:</span><span class="sxs-lookup"><span data-stu-id="48cd8-226">The message trace details contain the following additional information that's not present in the summary report:</span></span>

- <span data-ttu-id="48cd8-227">**邮件事件**: 本节包含的分类可帮助对邮件所需的操作进行分类。</span><span class="sxs-lookup"><span data-stu-id="48cd8-227">**Message events**: This section contains classifications that help categorize the actions that the service takes on messages.</span></span> <span data-ttu-id="48cd8-228">您可能遇到的一些更有趣的事件是:</span><span class="sxs-lookup"><span data-stu-id="48cd8-228">Some of the more interesting events that you might encounter are:</span></span>

   - <span data-ttu-id="48cd8-229">**接收**: 服务收到邮件。</span><span class="sxs-lookup"><span data-stu-id="48cd8-229">**Receive**: The message was received by the service.</span></span>

   - <span data-ttu-id="48cd8-230">**发送**: 邮件是由服务发送的。</span><span class="sxs-lookup"><span data-stu-id="48cd8-230">**Send**: The message was sent by the service.</span></span>

   - <span data-ttu-id="48cd8-231">**失败**: 邮件传递失败。</span><span class="sxs-lookup"><span data-stu-id="48cd8-231">**Fail**: The message failed to be delivered.</span></span>

   - <span data-ttu-id="48cd8-232">**传递**: 邮件已传递到邮箱。</span><span class="sxs-lookup"><span data-stu-id="48cd8-232">**Deliver**: The message was delivered to a mailbox.</span></span>

   - <span data-ttu-id="48cd8-233">**Expand**: 邮件被发送到展开的通讯组。</span><span class="sxs-lookup"><span data-stu-id="48cd8-233">**Expand**: The message was sent to a distribution group that was expanded.</span></span>

   - <span data-ttu-id="48cd8-234">**传输**: 由于内容转换、邮件收件人限制或代理, 收件人被移动到分支邮件。</span><span class="sxs-lookup"><span data-stu-id="48cd8-234">**Transfer**: Recipients were moved to a bifurcated message because of content conversion, message recipient limits, or agents.</span></span>

   - <span data-ttu-id="48cd8-235">**Defer**: 邮件传递被推迟, 稍后可能重试。</span><span class="sxs-lookup"><span data-stu-id="48cd8-235">**Defer**: The message delivery was postponed and might be re-attempted later.</span></span>

   - <span data-ttu-id="48cd8-236">**已解决**: 邮件已重定向到基于 Active Directory 查找的新收件人地址。</span><span class="sxs-lookup"><span data-stu-id="48cd8-236">**Resolved**: The message was redirected to a new recipient address based on an Active Directory look up.</span></span> <span data-ttu-id="48cd8-237">当发生这种情况时，原始收件人地址会被列在邮件跟踪中的单独一行，包括邮件的最终传递状态。</span><span class="sxs-lookup"><span data-stu-id="48cd8-237">When this happens, the original recipient address is listed in a separate row in the message trace along with the final delivery status for the message.</span></span>

   <span data-ttu-id="48cd8-238">请注意, 即使已成功传递的无事件邮件也会在邮件跟踪中生成多个**事件**条目。</span><span class="sxs-lookup"><span data-stu-id="48cd8-238">Note that even an uneventful message that's successfully delivered will generate multiple **Event** entries in the message trace.</span></span>

- <span data-ttu-id="48cd8-239">**详细信息**: 本节包含以下详细信息:</span><span class="sxs-lookup"><span data-stu-id="48cd8-239">**More information**: This section contains the following details:</span></span>

   - <span data-ttu-id="48cd8-240">**邮件 id**: 此值在本主题前面的[邮件 id](#message-id)部分中进行了描述。</span><span class="sxs-lookup"><span data-stu-id="48cd8-240">**Message ID**: This value is described in the [Message ID](#message-id) section earlier in this topic.</span></span> <span data-ttu-id="48cd8-241">例如，`<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`。</span><span class="sxs-lookup"><span data-stu-id="48cd8-241">For example, `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`.</span></span>

   - <span data-ttu-id="48cd8-242">**邮件大小**</span><span class="sxs-lookup"><span data-stu-id="48cd8-242">**Message size**</span></span>

   - <span data-ttu-id="48cd8-243">**发件人 ip**: 发送邮件的计算机的 ip 地址。</span><span class="sxs-lookup"><span data-stu-id="48cd8-243">**From IP**: The IP address of the computer that sent the message.</span></span> <span data-ttu-id="48cd8-244">对于从 Exchange Online 发送的出站邮件，该值是空值。</span><span class="sxs-lookup"><span data-stu-id="48cd8-244">For outbound messages sent from Exchange Online, this value is blank.</span></span>

   - <span data-ttu-id="48cd8-245">**目标 ip**: 服务尝试传递邮件的 ip 地址或地址。</span><span class="sxs-lookup"><span data-stu-id="48cd8-245">**To IP**: The IP address or addresses where the service attempted to deliver the message.</span></span> <span data-ttu-id="48cd8-246">如果邮件有多个收件人, 则会显示这些收件人。</span><span class="sxs-lookup"><span data-stu-id="48cd8-246">If the message has multiple recipients, these are displayed.</span></span> <span data-ttu-id="48cd8-247">对于发送到 Exchange Online 的入站邮件，该值是空值。</span><span class="sxs-lookup"><span data-stu-id="48cd8-247">For inbound messages sent to Exchange Online, this value is blank.</span></span>

### <a name="enhanced-summary-reports"></a><span data-ttu-id="48cd8-248">增强的摘要报告</span><span class="sxs-lookup"><span data-stu-id="48cd8-248">Enhanced summary reports</span></span>

<span data-ttu-id="48cd8-249">可用 (已完成) 增强的摘要报告可在开始邮件跟踪的**可下载报告**部分中找到。</span><span class="sxs-lookup"><span data-stu-id="48cd8-249">Available (completed) Enhanced summary reports are available in the **Downloadable reports** section at the beginning message trace.</span></span> <span data-ttu-id="48cd8-250">报告中提供了以下信息:</span><span class="sxs-lookup"><span data-stu-id="48cd8-250">The following information is available in the report:</span></span>

- <span data-ttu-id="48cd8-251">**origin_timestamp**<sup>\*</sup>: 服务最初接收邮件时使用配置的 UTC 时区的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="48cd8-251">**origin_timestamp**<sup>\*</sup>: The date and time when the message was initially received by the service, using the configured UTC time zone.</span></span>

- <span data-ttu-id="48cd8-252">**sender_address**: 发件人的电子邮件地址 (*别名*@*域*)。</span><span class="sxs-lookup"><span data-stu-id="48cd8-252">**sender_address**: The sender's email address (*alias*@*domain*).</span></span>

- <span data-ttu-id="48cd8-253">**Recipient_status**: 邮件传递给收件人的状态。</span><span class="sxs-lookup"><span data-stu-id="48cd8-253">**Recipient_status**: The status of the delivery of the message to the recipient.</span></span> <span data-ttu-id="48cd8-254">如果邮件发送给多个收件人, 则它将显示所有收件人以及每个收件人的相应状态, 格式为: \<*电子邮件地址*\>##\<*状态*\>。</span><span class="sxs-lookup"><span data-stu-id="48cd8-254">If the message was sent to multiple recipients, it will show all the recipients and the corresponding status for each, in the format: \<*email address*\>##\<*status*\>.</span></span> <span data-ttu-id="48cd8-255">例如：</span><span class="sxs-lookup"><span data-stu-id="48cd8-255">For example:</span></span>

   - <span data-ttu-id="48cd8-256">**# #Receive, Send**表示该邮件由服务接收, 并发送到预定的目标。</span><span class="sxs-lookup"><span data-stu-id="48cd8-256">**##Receive, Send** means the message was received by the service and was sent to the intended destination.</span></span>

   - <span data-ttu-id="48cd8-257">**# #Receive, Fail**表示邮件已由服务接收, 但传递到目标目标失败。</span><span class="sxs-lookup"><span data-stu-id="48cd8-257">**##Receive, Fail** means the message was received by the service but delivery to the intended destination failed.</span></span>

   - <span data-ttu-id="48cd8-258">**# #Receive, 提供**表示邮件已由服务接收, 并已传递到收件人的邮箱。</span><span class="sxs-lookup"><span data-stu-id="48cd8-258">**##Receive, Deliver** means the message was received by the service and was delivered to the recipient's mailbox.</span></span>

- <span data-ttu-id="48cd8-259">**message_subject**: 邮件的 " **subject** " 字段的前256个字符。</span><span class="sxs-lookup"><span data-stu-id="48cd8-259">**message_subject**: The first 256 characters of the message's **Subject** field.</span></span>

- <span data-ttu-id="48cd8-260">**total_bytes**: 邮件的大小 (以字节为单位), 包括附件。</span><span class="sxs-lookup"><span data-stu-id="48cd8-260">**total_bytes**: The size of the message in bytes, including attachments.</span></span>

- <span data-ttu-id="48cd8-261">**message_id**: 此值在本主题前面的[邮件 id](#message-id)部分中进行了介绍。</span><span class="sxs-lookup"><span data-stu-id="48cd8-261">**message_id**: This value is described in the [Message ID](#message-id) section earlier in this topic.</span></span> <span data-ttu-id="48cd8-262">例如，`<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`。</span><span class="sxs-lookup"><span data-stu-id="48cd8-262">For example, `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`.</span></span>

- <span data-ttu-id="48cd8-263">**network_message_id**: 在可能由于分叉或通讯组扩展而创建的邮件的所有副本中保持的唯一邮件 id 值。</span><span class="sxs-lookup"><span data-stu-id="48cd8-263">**network_message_id**: A unique message ID value that persists across all copies of the message that might be created due to bifurcation or distribution group expansion.</span></span> <span data-ttu-id="48cd8-264">示例值为`1341ac7b13fb42ab4d4408cf7f55890f`。</span><span class="sxs-lookup"><span data-stu-id="48cd8-264">An example value is `1341ac7b13fb42ab4d4408cf7f55890f`.</span></span>

- <span data-ttu-id="48cd8-265">**original_client_ip**: 发件人客户端的 ip 地址。</span><span class="sxs-lookup"><span data-stu-id="48cd8-265">**original_client_ip**: The IP address of the sender's client.</span></span>

- <span data-ttu-id="48cd8-266">**方向**性: 指示是将邮件发送到组织的入站邮件 (1), 还是从您的组织发送出站邮件 (2)。</span><span class="sxs-lookup"><span data-stu-id="48cd8-266">**directionality**: Indicates whether the message was sent inbound (1) to your organization, or whether it was sent outbound (2) from your organization.</span></span>

- <span data-ttu-id="48cd8-267">**connector_id**: 源或目标连接器的名称。</span><span class="sxs-lookup"><span data-stu-id="48cd8-267">**connector_id**: The name of the source or destination connector.</span></span> <span data-ttu-id="48cd8-268">有关 Exchange Online 连接器的详细信息, 请参阅[在 Office 365 中使用连接器配置邮件流](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)。</span><span class="sxs-lookup"><span data-stu-id="48cd8-268">For more information about connectors in Exchange Online, see [Configure mail flow using connectors in Office 365](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).</span></span>

- <span data-ttu-id="48cd8-269">**delivery_priority**<sup>\*</sup>: 邮件是以**高**、**低**还是**普通**优先级发送。</span><span class="sxs-lookup"><span data-stu-id="48cd8-269">**delivery_priority**<sup>\*</sup>: Whether the message was sent with **High**, **Low**, or **Normal** priority.</span></span>

<span data-ttu-id="48cd8-270"><sup>\*</sup>这些属性仅在增强的摘要报告中可用。</span><span class="sxs-lookup"><span data-stu-id="48cd8-270"><sup>\*</sup>These properties are only available in Enhanced summary reports.</span></span>

### <a name="extended-reports"></a><span data-ttu-id="48cd8-271">扩展报告</span><span class="sxs-lookup"><span data-stu-id="48cd8-271">Extended reports</span></span>

<span data-ttu-id="48cd8-272">可用 (已完成) 扩展报告在邮件跟踪开头的**可下载报告**部分中可用。</span><span class="sxs-lookup"><span data-stu-id="48cd8-272">Available (completed) Extended reports are available in the **Downloadable reports** section at the beginning of message trace.</span></span> <span data-ttu-id="48cd8-273">实际上, 来自增强的摘要报告的所有信息均位于扩展报告中 ( **origin_timestamp**和**delivery_priority**除外)。</span><span class="sxs-lookup"><span data-stu-id="48cd8-273">Virtually all of the information from an Enhanced summary report is available in an Extended report (with the exception of **origin_timestamp** and **delivery_priority**).</span></span> <span data-ttu-id="48cd8-274">以下附加信息仅适用于扩展报告:</span><span class="sxs-lookup"><span data-stu-id="48cd8-274">The following additional information is only available in an Extended report:</span></span>

- <span data-ttu-id="48cd8-275">**client_ip**: 提交邮件的电子邮件服务器或邮件客户端的 ip 地址。</span><span class="sxs-lookup"><span data-stu-id="48cd8-275">**client_ip**: The IP address of the email server or messaging client that submitted the message.</span></span>

- <span data-ttu-id="48cd8-276">**client_hostname**: 提交邮件的电子邮件服务器或邮件客户端的主机名或 FQDN。</span><span class="sxs-lookup"><span data-stu-id="48cd8-276">**client_hostname**: The host name or FQDN of the email server or messaging client that submitted the message.</span></span>

- <span data-ttu-id="48cd8-277">**server_ip**: 源或目标服务器的 ip 地址。</span><span class="sxs-lookup"><span data-stu-id="48cd8-277">**server_ip**: The IP address of the source or destination server.</span></span>

- <span data-ttu-id="48cd8-278">**server_hostname**: 目标服务器的主机名或 FQDN。</span><span class="sxs-lookup"><span data-stu-id="48cd8-278">**server_hostname**: The host name or FQDN of the destination server.</span></span>

- <span data-ttu-id="48cd8-279">**source_context**: 与**源**字段关联的额外信息。</span><span class="sxs-lookup"><span data-stu-id="48cd8-279">**source_context**: Extra information associated with the **source** field.</span></span> <span data-ttu-id="48cd8-280">例如：</span><span class="sxs-lookup"><span data-stu-id="48cd8-280">For example:</span></span>

   - `Protocol Filter Agent`

   - `3489061114359050000`

- <span data-ttu-id="48cd8-281">**源**: 负责事件的 Exchange Online 组件。</span><span class="sxs-lookup"><span data-stu-id="48cd8-281">**source**: The Exchange Online component that's responsible for the event.</span></span> <span data-ttu-id="48cd8-282">例如：</span><span class="sxs-lookup"><span data-stu-id="48cd8-282">For example:</span></span>

   - `AGENT`

   - `MAILBOXRULE`

   - `SMTP`

- <span data-ttu-id="48cd8-283">**event_id**: 这些值对应于在 "[查找此邮件的相关记录](#find-related-records-for-this-message)" 部分中介绍的**消息事件**值。</span><span class="sxs-lookup"><span data-stu-id="48cd8-283">**event_id**: These correspond to the **Message event** values that are explained in the [Find related records for this message](#find-related-records-for-this-message) section.</span></span>

- <span data-ttu-id="48cd8-284">**internal_message_id**: 由当前正在处理邮件的 Exchange Online 服务器分配的邮件标识符。</span><span class="sxs-lookup"><span data-stu-id="48cd8-284">**internal_message_id**: A message identifier that's assigned by the Exchange Online server that's currently processing the message.</span></span>

- <span data-ttu-id="48cd8-285">**recipient_address**: 邮件的收件人的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="48cd8-285">**recipient_address**: The email addresses of the message's recipients.</span></span> <span data-ttu-id="48cd8-286">多个电子邮件地址通过分号字符 (;) 分隔。</span><span class="sxs-lookup"><span data-stu-id="48cd8-286">Multiple email addresses are separated by the semicolon character (;).</span></span>

- <span data-ttu-id="48cd8-287">**recipient_count**: 邮件中的收件人总数。</span><span class="sxs-lookup"><span data-stu-id="48cd8-287">**recipient_count**: The total number of recipients in the message.</span></span>

- <span data-ttu-id="48cd8-288">**related_recipient_address**: 与`EXPAND`、 `REDIRECT`和`RESOLVE`事件一起用来显示与邮件相关联的其他收件人电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="48cd8-288">**related_recipient_address**: Used with `EXPAND`, `REDIRECT`, and `RESOLVE` events to display other recipient email addresses that are associated with the message.</span></span>

- <span data-ttu-id="48cd8-289">**参考**: 此字段包含特定事件类型的其他信息。</span><span class="sxs-lookup"><span data-stu-id="48cd8-289">**reference**: This field contains additional information for specific types of events.</span></span> <span data-ttu-id="48cd8-290">例如：</span><span class="sxs-lookup"><span data-stu-id="48cd8-290">For example:</span></span>

   - <span data-ttu-id="48cd8-291">**DSN**: 包含报告链接, 如果此事件后面生成 dsn, 则该链接是关联的传递状态通知 (也称为 DSN、未送达报告、NDR 或退回邮件) 的**message_id**值。</span><span class="sxs-lookup"><span data-stu-id="48cd8-291">**DSN**: Contains the report link, which is the **message_id** value of the associated delivery status notification (also known as a DSN, non-delivery report, NDR, or bounce message) if a DSN is generated subsequent to this event.</span></span> <span data-ttu-id="48cd8-292">如果这是 dsn 邮件, 则此字段包含为其生成 DSN 的原始邮件的**message_id**值。</span><span class="sxs-lookup"><span data-stu-id="48cd8-292">If this is a DSN message, this field contains the **message_id** value of the original message that the DSN was generated for.</span></span>

   - <span data-ttu-id="48cd8-293">**展开**: 包含相关邮件的**related_recipient_address**值。</span><span class="sxs-lookup"><span data-stu-id="48cd8-293">**EXPAND**: Contains the **related_recipient_address** value of the related messages.</span></span>

   - <span data-ttu-id="48cd8-294">**RECEIVE**: 如果邮件是由其他进程生成的 (例如, 收件箱规则), 则可能包含相关邮件的**message_id**值。</span><span class="sxs-lookup"><span data-stu-id="48cd8-294">**RECEIVE**: Might contain the **message_id** value of the related message if the message was generated by other processes (for example, Inbox rules).</span></span>

   - <span data-ttu-id="48cd8-295">**SEND**: 包含任何 DSN 邮件的**internal_message_id**值。</span><span class="sxs-lookup"><span data-stu-id="48cd8-295">**SEND**: Contains the **internal_message_id** value of any DSN messages.</span></span>

   - <span data-ttu-id="48cd8-296">**传输**: 包含正在分叉的邮件的**internal_message_id**值 (例如, 通过内容转换、邮件收件人限制或代理)。</span><span class="sxs-lookup"><span data-stu-id="48cd8-296">**TRANSFER**: Contains the **internal_message_id** value of the message that's being forked (for example, by content conversion, message recipient limits, or agents).</span></span>

   - <span data-ttu-id="48cd8-297">**MAILBOXRULE**: 包含导致收件箱规则生成出站邮件的入站邮件的**internal_message_id**值。</span><span class="sxs-lookup"><span data-stu-id="48cd8-297">**MAILBOXRULE**: Contains the **internal_message_id** value of the inbound message that caused the Inbox rule to generate the outbound message.</span></span>

   <span data-ttu-id="48cd8-298">对于其他类型的事件, 此字段通常为空。</span><span class="sxs-lookup"><span data-stu-id="48cd8-298">For other types of events, this field is usually blank.</span></span>

- <span data-ttu-id="48cd8-299">**return_path**: 发送邮件的**邮件发件**人命令指定的返回电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="48cd8-299">**return_path**: The return email address specified by the **MAIL FROM** command that sent the message.</span></span> <span data-ttu-id="48cd8-300">虽然此字段永远不为空, 但它可以有表示为`<>`的 null 发件人地址值。</span><span class="sxs-lookup"><span data-stu-id="48cd8-300">Although this field is never empty, it can have the null sender address value represented as `<>`.</span></span>

- <span data-ttu-id="48cd8-301">**message_info**: 有关邮件的其他信息。</span><span class="sxs-lookup"><span data-stu-id="48cd8-301">**message_info**: Additional information about the message.</span></span> <span data-ttu-id="48cd8-302">例如：</span><span class="sxs-lookup"><span data-stu-id="48cd8-302">For example:</span></span>

   - <span data-ttu-id="48cd8-303">的消息起始日期-时间 ( `DELIVER` UTC) 和`SEND`事件。</span><span class="sxs-lookup"><span data-stu-id="48cd8-303">The message origination date-time in UTC for `DELIVER` and `SEND` events.</span></span> <span data-ttu-id="48cd8-304">源日期-时间是邮件第一次进入 Exchange Online 组织的时间。</span><span class="sxs-lookup"><span data-stu-id="48cd8-304">The origination date-time is the time when the message first entered the Exchange Online organization.</span></span> <span data-ttu-id="48cd8-305">UTC `yyyy-mm-ddThh:mm:ss.fffZ`日期-时间以 ISO 8601 日期-时间格式表示:, 其中`yyyy` = year, `mm` = month, `dd` = day, `T`表示时间部分的开始时间, `hh` = 小时, `mm` = 分钟, `ss` = 秒, = `fff`秒的小数部分, 并`Z`表示`Zulu`, 这是表示 UTC 的另一种方法。</span><span class="sxs-lookup"><span data-stu-id="48cd8-305">The UTC date-time is represented in the ISO 8601 date-time format: `yyyy-mm-ddThh:mm:ss.fffZ`, where `yyyy` = year, `mm` = month, `dd` = day, `T` indicates the beginning of the time component, `hh` = hour, `mm` = minute, `ss` = second, `fff` = fractions of a second, and `Z` signifies `Zulu`, which is another way to denote UTC.</span></span>

   - <span data-ttu-id="48cd8-306">身份验证错误。</span><span class="sxs-lookup"><span data-stu-id="48cd8-306">Authentication errors.</span></span> <span data-ttu-id="48cd8-307">例如, 您可能会看到值`11a`和身份验证错误发生时使用的身份验证类型。</span><span class="sxs-lookup"><span data-stu-id="48cd8-307">For example, you might see the value `11a` and the type of authentication that was used when the authentication error occurred.</span></span>

- <span data-ttu-id="48cd8-308">**tenant_id**: 一个表示 Exchange Online 组织的 GUID 值 (例如`39238e87-b5ab-4ef6-a559-af54c6b07b42`)。</span><span class="sxs-lookup"><span data-stu-id="48cd8-308">**tenant_id**: A GUID value that represents the Exchange Online organization (for example, `39238e87-b5ab-4ef6-a559-af54c6b07b42`).</span></span>

- <span data-ttu-id="48cd8-309">**original_server_ip**: 原始服务器的 ip 地址。</span><span class="sxs-lookup"><span data-stu-id="48cd8-309">**original_server_ip**: The IP address of the original server.</span></span>

- <span data-ttu-id="48cd8-310">**custom_data**: 包含与特定事件类型相关的数据。</span><span class="sxs-lookup"><span data-stu-id="48cd8-310">**custom_data**: Contains data related to specific event types.</span></span> <span data-ttu-id="48cd8-311">有关详细信息, 请参阅以下各节。</span><span class="sxs-lookup"><span data-stu-id="48cd8-311">For more information, see the following sections.</span></span>

#### <a name="customdata-values"></a><span data-ttu-id="48cd8-312">custom_data 值</span><span class="sxs-lookup"><span data-stu-id="48cd8-312">custom_data values</span></span>

<span data-ttu-id="48cd8-313">各种\*\*\*\* Exchange Online 代理使用`AGENTINFO`事件的 custom_data 字段来记录消息处理详细信息。</span><span class="sxs-lookup"><span data-stu-id="48cd8-313">The **custom_data** field for an `AGENTINFO` event is used by a variety of Exchange Online agents to log message processing details.</span></span> <span data-ttu-id="48cd8-314">以下各节中介绍了一些更有趣的代理。</span><span class="sxs-lookup"><span data-stu-id="48cd8-314">Some of the more interesting agents are described in the following sections.</span></span>

#### <a name="spam-filter-agent"></a><span data-ttu-id="48cd8-315">垃圾邮件筛选器代理</span><span class="sxs-lookup"><span data-stu-id="48cd8-315">Spam filter agent</span></span>

<span data-ttu-id="48cd8-316">以**custom_data**开头`S:SFA`的值来自垃圾邮件筛选器代理。</span><span class="sxs-lookup"><span data-stu-id="48cd8-316">A **custom_data** value that starts with `S:SFA` is from the spam filter agent.</span></span> <span data-ttu-id="48cd8-317">下表介绍了关键详细信息:</span><span class="sxs-lookup"><span data-stu-id="48cd8-317">The key details are described in the following table:</span></span>

|<span data-ttu-id="48cd8-318">**值**</span><span class="sxs-lookup"><span data-stu-id="48cd8-318">**Value**</span></span>|<span data-ttu-id="48cd8-319">**说明**</span><span class="sxs-lookup"><span data-stu-id="48cd8-319">**Description**</span></span>|
|:-----|:-----|
|`SFV=NSPM`|<span data-ttu-id="48cd8-320">邮件被标记为非垃圾邮件并发送给预期发件人。</span><span class="sxs-lookup"><span data-stu-id="48cd8-320">The message was marked as non-spam and was sent to the intended recipients.</span></span>|
|`SFV=SPM`|<span data-ttu-id="48cd8-321">邮件由内容筛选器标记为垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="48cd8-321">The message was marked as spam by the content filter.</span></span>|
|`SFV=BLK`|<span data-ttu-id="48cd8-322">跳过筛选但阻止邮件，因为它是由已阻止发件人发送。</span><span class="sxs-lookup"><span data-stu-id="48cd8-322">Filtering was skipped and the message was blocked because it originated from a blocked sender.</span></span>|
|`SFV=SKS`|<span data-ttu-id="48cd8-p150">邮件在内容筛选器处理之前被标记为垃圾邮件。这包括符合以下传输规则条件的邮件：自动将邮件标记为垃圾邮件并规避其他所有筛选。</span><span class="sxs-lookup"><span data-stu-id="48cd8-p150">The message was marked as spam prior to being processed by the content filter. This includes messages where the message matched a Transport rule to automatically mark it as spam and bypass all additional filtering.</span></span>|
|`SCL=<number>`|<span data-ttu-id="48cd8-325">有关不同的 SCL 值及其含义的详细信息，请参阅[垃圾邮件可信度](https://technet.microsoft.com/library/jj200686.aspx)。</span><span class="sxs-lookup"><span data-stu-id="48cd8-325">For more information about the different SCL values and what they mean, see [Spam confidence levels](https://technet.microsoft.com/library/jj200686.aspx).</span></span>|
|`PCL=<number>`|<span data-ttu-id="48cd8-p151">邮件的仿冒可能性等级 (PCL) 值。可按照[垃圾邮件可信度](https://technet.microsoft.com/library/jj200686.aspx)中介绍 SCL 值的方式对这些值做出解释。  </span><span class="sxs-lookup"><span data-stu-id="48cd8-p151">The Phishing Confidence Level (PCL) value of the message. These can be interpreted the same way as the SCL values documented in [Spam confidence levels](https://technet.microsoft.com/library/jj200686.aspx).</span></span>|
|`DI=SB`|<span data-ttu-id="48cd8-328">已阻止邮件发件人。</span><span class="sxs-lookup"><span data-stu-id="48cd8-328">The sender of the message was blocked.</span></span>|
|`DI=SQ`|<span data-ttu-id="48cd8-329">邮件已隔离。</span><span class="sxs-lookup"><span data-stu-id="48cd8-329">The message was quarantined.</span></span>|
|`DI=SD`|<span data-ttu-id="48cd8-330">邮件已删除。</span><span class="sxs-lookup"><span data-stu-id="48cd8-330">The message was deleted.</span></span>|
|`DI=SJ`|<span data-ttu-id="48cd8-331">邮件已发送至收件人的"垃圾邮件"文件夹。</span><span class="sxs-lookup"><span data-stu-id="48cd8-331">The message was sent to the recipient's Junk Email folder.</span></span>|
|`DI=SN`|<span data-ttu-id="48cd8-332">邮件已通过高风险传送池路由。</span><span class="sxs-lookup"><span data-stu-id="48cd8-332">The message was routed through the higher risk delivery pool.</span></span> <span data-ttu-id="48cd8-333">有关详细信息, 请参阅[出站邮件的高风险传递池](https://technet.microsoft.com/library/jj200746.aspx)。</span><span class="sxs-lookup"><span data-stu-id="48cd8-333">For more information, see [High-risk delivery pool for outbound messages](https://technet.microsoft.com/library/jj200746.aspx).</span></span>|
|`DI=SO`|<span data-ttu-id="48cd8-334">邮件已通过正常出站传送池路由。</span><span class="sxs-lookup"><span data-stu-id="48cd8-334">The message was routed through the normal outbound delivery pool.</span></span>|
|<span data-ttu-id="48cd8-335">"SFS = [a]</span><span class="sxs-lookup"><span data-stu-id="48cd8-335">\`SFS=[a]</span></span>|<span data-ttu-id="48cd8-336">SFS = [b] '</span><span class="sxs-lookup"><span data-stu-id="48cd8-336">SFS=[b]\`</span></span>|<span data-ttu-id="48cd8-337">说明匹配此垃圾邮件规则。</span><span class="sxs-lookup"><span data-stu-id="48cd8-337">This denotes that spam rules were matched.</span></span>|
|`IPV=CAL`|<span data-ttu-id="48cd8-338">邮件已通过垃圾邮件筛选器允许，因为已在连接筛选器中的 IP 允许列表中指定该 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="48cd8-338">The message was allowed through the spam filters because the IP address was specified in an IP Allow list in the connection filter.</span></span>|
|`H=<EHLOstring>`|<span data-ttu-id="48cd8-339">连接电子邮件服务器的 HELO 或 EHLO 字符串。</span><span class="sxs-lookup"><span data-stu-id="48cd8-339">The HELO or EHLO string of the connecting email server.</span></span>|
|`PTR=<ReverseDNS>`|<span data-ttu-id="48cd8-340">发送 IP 地址的 PTR 记录，也被称为反向 DNS 地址。</span><span class="sxs-lookup"><span data-stu-id="48cd8-340">The PTR record of the sending IP address, also known as the reverse DNS address.</span></span>|

<span data-ttu-id="48cd8-341">针对垃圾邮件筛选的邮件的示例**custom_data**值, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="48cd8-341">An example **custom_data** value for a message that's filtered for spam like this:</span></span>

`S:SFA=SUM|SFV=SPM|IPV=CAL|SRV=BULK|SFS=470454002|SFS=349001|SCL=9|SCORE=-1|LIST=0|DI=SN|RD=ftmail.inc.com|H=ftmail.inc.com|CIP=98.129.140.74|SFP=1501|ASF=1|CTRY=US|CLTCTRY=|LANG=en|LAT=287|LAT=260|LAT=18;`

#### <a name="malware-filter-agent"></a><span data-ttu-id="48cd8-342">恶意软件筛选器代理</span><span class="sxs-lookup"><span data-stu-id="48cd8-342">Malware filter agent</span></span>

<span data-ttu-id="48cd8-343">以\*\*\*\* 的开头`S:AMA`的 custom_data 值来自恶意软件筛选器代理。</span><span class="sxs-lookup"><span data-stu-id="48cd8-343">A **custom_data** value that starts with `S:AMA` is from the malware filter agent.</span></span> <span data-ttu-id="48cd8-344">下表介绍了关键详细信息:</span><span class="sxs-lookup"><span data-stu-id="48cd8-344">The key details are described in the following table:</span></span>

|<span data-ttu-id="48cd8-345">**值**</span><span class="sxs-lookup"><span data-stu-id="48cd8-345">**Value**</span></span>|<span data-ttu-id="48cd8-346">**说明**</span><span class="sxs-lookup"><span data-stu-id="48cd8-346">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="48cd8-347">' AMA = SUM</span><span class="sxs-lookup"><span data-stu-id="48cd8-347">\`AMA=SUM</span></span>|<span data-ttu-id="48cd8-348">v=1</span><span class="sxs-lookup"><span data-stu-id="48cd8-348">v=1</span></span>|<span data-ttu-id="48cd8-349">` or `AMA=EV</span><span class="sxs-lookup"><span data-stu-id="48cd8-349">` or `AMA=EV</span></span>|<span data-ttu-id="48cd8-350">v = 1 '</span><span class="sxs-lookup"><span data-stu-id="48cd8-350">v=1\`</span></span>|<span data-ttu-id="48cd8-351">已确定此邮件包含恶意软件。</span><span class="sxs-lookup"><span data-stu-id="48cd8-351">The message was determined to contain malware.</span></span> <span data-ttu-id="48cd8-352">`SUM`指示任意数量的引擎可能检测到恶意软件。</span><span class="sxs-lookup"><span data-stu-id="48cd8-352">`SUM` indicates the malware could've been detected by any number of engines.</span></span> <span data-ttu-id="48cd8-353">`EV`指示特定引擎检测到恶意软件。</span><span class="sxs-lookup"><span data-stu-id="48cd8-353">`EV` indicates the malware was detected by a specific engine.</span></span> <span data-ttu-id="48cd8-354">引擎检测到恶意软件后，将触发后续操作。</span><span class="sxs-lookup"><span data-stu-id="48cd8-354">When malware is detected by an engine this triggers the subsequent actions.</span></span>|
|`Action=r`|<span data-ttu-id="48cd8-355">邮件已被替换。</span><span class="sxs-lookup"><span data-stu-id="48cd8-355">The message was replaced.</span></span>|
|`Action=p`|<span data-ttu-id="48cd8-356">邮件已被忽略。</span><span class="sxs-lookup"><span data-stu-id="48cd8-356">The message was bypassed.</span></span>|
|`Action=d`|<span data-ttu-id="48cd8-357">邮件已被延迟。</span><span class="sxs-lookup"><span data-stu-id="48cd8-357">The message was deferred.</span></span>|
|`Action=s`|<span data-ttu-id="48cd8-358">邮件已删除。</span><span class="sxs-lookup"><span data-stu-id="48cd8-358">The message was deleted.</span></span>|
|`Action=st`|<span data-ttu-id="48cd8-359">邮件已被忽略。</span><span class="sxs-lookup"><span data-stu-id="48cd8-359">The message was bypassed.</span></span>|
|`Action=sy`|<span data-ttu-id="48cd8-360">邮件已被忽略。</span><span class="sxs-lookup"><span data-stu-id="48cd8-360">The message was bypassed.</span></span>|
|`Action=ni`|<span data-ttu-id="48cd8-361">邮件已被拒绝。</span><span class="sxs-lookup"><span data-stu-id="48cd8-361">The message was rejected.</span></span>|
|`Action=ne`|<span data-ttu-id="48cd8-362">邮件已被拒绝。</span><span class="sxs-lookup"><span data-stu-id="48cd8-362">The message was rejected.</span></span>|
|`Action=b`|<span data-ttu-id="48cd8-363">邮件已被阻止。</span><span class="sxs-lookup"><span data-stu-id="48cd8-363">The message was blocked.</span></span>|
|`Name=<malware>`|<span data-ttu-id="48cd8-364">已检测到的恶意软件的名称。</span><span class="sxs-lookup"><span data-stu-id="48cd8-364">The name of the malware that was detected.</span></span>|
|`File=<filename>`|<span data-ttu-id="48cd8-365">恶意软件中包含的文件名称。</span><span class="sxs-lookup"><span data-stu-id="48cd8-365">The name of the file that contained the malware.</span></span>|

<span data-ttu-id="48cd8-366">包含恶意软件的邮件的示例**custom_data**值如下所示:</span><span class="sxs-lookup"><span data-stu-id="48cd8-366">An example **custom_data** value for a message that contains malware looks like this:</span></span>

`S:AMA=SUM|v=1|action=b|error=|atch=1;S:AMA=EV|engine=M|v=1|sig=1.155.974.0|name=DOS/Test_File|file=filename;S:AMA=EV|engine=A|v=1|sig=201707282038|name=Test_File|file=filename`

#### <a name="transport-rule-agent"></a><span data-ttu-id="48cd8-367">传输规则代理</span><span class="sxs-lookup"><span data-stu-id="48cd8-367">Transport Rule agent</span></span>

<span data-ttu-id="48cd8-368">以**custom_data**开头`S:TRA`的值来自邮件流规则的传输规则代理 (也称为传输规则)。</span><span class="sxs-lookup"><span data-stu-id="48cd8-368">A **custom_data** value that starts with`S:TRA` is from the Transport Rule agent for mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="48cd8-369">下表介绍了关键详细信息:</span><span class="sxs-lookup"><span data-stu-id="48cd8-369">The key details are described in the following table:</span></span>

|<span data-ttu-id="48cd8-370">**值**</span><span class="sxs-lookup"><span data-stu-id="48cd8-370">**Value**</span></span>|<span data-ttu-id="48cd8-371">**说明**</span><span class="sxs-lookup"><span data-stu-id="48cd8-371">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="48cd8-372">' ETR</span><span class="sxs-lookup"><span data-stu-id="48cd8-372">\`ETR</span></span>|<span data-ttu-id="48cd8-373">ruleId =<guid>\`</span><span class="sxs-lookup"><span data-stu-id="48cd8-373">ruleId=<guid>\`</span></span>|<span data-ttu-id="48cd8-374">匹配的规则 ID。</span><span class="sxs-lookup"><span data-stu-id="48cd8-374">The rule ID that was matched.</span></span>|
|`St=<datetime>`|<span data-ttu-id="48cd8-375">发生规则匹配时的日期和时间 (以 UTC 为单位)。</span><span class="sxs-lookup"><span data-stu-id="48cd8-375">The date and time in UTC when the rule match occurred.</span></span>|
|`Action=<ActionDefinition>`|<span data-ttu-id="48cd8-376">应用的操作。</span><span class="sxs-lookup"><span data-stu-id="48cd8-376">The action that was applied.</span></span> <span data-ttu-id="48cd8-377">有关可用操作的列表, 请参阅[Exchange Online 中的邮件流规则操作](https://technet.microsoft.com/library/jj919237.aspx)。</span><span class="sxs-lookup"><span data-stu-id="48cd8-377">For a list of available actions, see [Mail flow rule actions in Exchange Online](https://technet.microsoft.com/library/jj919237.aspx).</span></span>|
|`Mode=<Mode>`|<span data-ttu-id="48cd8-378">规则模式。</span><span class="sxs-lookup"><span data-stu-id="48cd8-378">The mode of the rule.</span></span> <span data-ttu-id="48cd8-379">有效值为：</span><span class="sxs-lookup"><span data-stu-id="48cd8-379">Valid values are:</span></span> <br/><span data-ttu-id="48cd8-380">•**强制实施**: 将强制执行对规则的所有操作。</span><span class="sxs-lookup"><span data-stu-id="48cd8-380">• **Enforce**: All actions on the rule will be enforced.</span></span> <br/><span data-ttu-id="48cd8-381">•**使用策略提示进行测试:**: 将发送所有策略提示操作, 但不会对其他强制操作执行操作。</span><span class="sxs-lookup"><span data-stu-id="48cd8-381">• **Test with Policy Tips:**: Any Policy Tip actions will be sent, but other enforcement actions will not be acted on.</span></span> <br/><span data-ttu-id="48cd8-382">•**测试没有策略提示**: 将在日志文件中列出操作, 但不会以任何方式通知发件人, 并且不会对强制性操作进行处理。</span><span class="sxs-lookup"><span data-stu-id="48cd8-382">• **Test without Policy Tips**: Actions will be listed in a log file, but senders will not be notified in any way, and enforcement actions will not be acted on.</span></span>|

<span data-ttu-id="48cd8-383">与邮件流规则的条件相匹配的邮件的示例**custom_data**值如下所示:</span><span class="sxs-lookup"><span data-stu-id="48cd8-383">An example **custom_data** value for a messages that matches the conditions of a mail flow rule looks like this:</span></span>

`S:TRA=ETR|ruleId=19a25eb2-3e43-4896-ad9e-47b6c359779d|st=7/17/2017 12:31:25 AM|action=ApplyHtmlDisclaimer|sev=1|mode=Enforce`
