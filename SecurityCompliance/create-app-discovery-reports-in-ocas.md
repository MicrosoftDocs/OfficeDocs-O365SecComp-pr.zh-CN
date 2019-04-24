---
title: 使用 Office 365 云应用安全创建应用发现报告
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 1/28/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 3e68e691-1fc4-4d3e-a2c0-d3134eb64055
description: 创建具有 office 365 云应用安全性的报告, 使您能够了解组织中的人员如何使用 office 365 和其他应用程序。
ms.openlocfilehash: 23165a52a09e5bcde46ee3ab2110dc17d0faf7f4
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32259632"
---
# <a name="create-app-discovery-reports-using-office-365-cloud-app-security"></a><span data-ttu-id="5a32c-103">使用 Office 365 云应用安全创建应用发现报告</span><span class="sxs-lookup"><span data-stu-id="5a32c-103">Create app discovery reports using Office 365 Cloud App Security</span></span>

|<span data-ttu-id="5a32c-104">评估 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="5a32c-104">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="5a32c-105">规划 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="5a32c-105">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="5a32c-106">部署 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="5a32c-106">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="5a32c-107">利用率 \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="5a32c-107">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="5a32c-108">开始评估</span><span class="sxs-lookup"><span data-stu-id="5a32c-108">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="5a32c-109">开始规划</span><span class="sxs-lookup"><span data-stu-id="5a32c-109">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |[<span data-ttu-id="5a32c-110">开始部署</span><span class="sxs-lookup"><span data-stu-id="5a32c-110">Start deploying</span></span>](turn-on-office-365-cas.md) <br/> |<span data-ttu-id="5a32c-111">你在这里!</span><span class="sxs-lookup"><span data-stu-id="5a32c-111">You are here!</span></span>  <br/> [<span data-ttu-id="5a32c-112">后续步骤</span><span class="sxs-lookup"><span data-stu-id="5a32c-112">Next steps</span></span>](#next-steps) <br/> |
   
<span data-ttu-id="5a32c-113">Office 365 云应用安全帮助全局管理员、安全管理员和安全读者深入了解组织中的云服务人员正在使用。</span><span class="sxs-lookup"><span data-stu-id="5a32c-113">Office 365 Cloud App Security helps global administrators, security administrators, and security readers gain insight into the cloud services people in an organization are using.</span></span> <span data-ttu-id="5a32c-114">例如, 您可以查看用户在何处存储和协作处理文档, 以及将多少数据上载到 Office 365 之外的应用或服务。</span><span class="sxs-lookup"><span data-stu-id="5a32c-114">For example, you can see where users are storing and collaborating on documents and how much data is being uploaded to apps or services that are outside of Office 365.</span></span>
  
<span data-ttu-id="5a32c-115">若要生成应用发现报告, 请从防火墙和代理手动上载 web 流量日志文件, 然后 Office 365 云应用安全性分析并分析这些文件中的报告。</span><span class="sxs-lookup"><span data-stu-id="5a32c-115">To generate an app discovery report, you manually upload your web traffic log files from your firewalls and proxies, and then Office 365 Cloud App Security parses and analyzes those files for your report.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5a32c-116">您必须是全局管理员、安全管理员或安全读者才能执行本文中所述的任务。</span><span class="sxs-lookup"><span data-stu-id="5a32c-116">You must be a global administrator, security administrator, or security reader to perform the tasks described in this article.</span></span> <span data-ttu-id="5a32c-117">若要了解详细信息, 请参阅[Office 365 安全&amp;合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="5a32c-117">To learn more, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> 
  
## <a name="create-a-report-with-app-discovery"></a><span data-ttu-id="5a32c-118">创建包含应用程序发现的报告</span><span class="sxs-lookup"><span data-stu-id="5a32c-118">Create a report with app discovery</span></span>

<span data-ttu-id="5a32c-119">若要创建应用发现报告, 请确定要分析的日志文件的供应商数据源, 选择日志文件, 然后请求报告。</span><span class="sxs-lookup"><span data-stu-id="5a32c-119">To create an app discovery report, you identify the vendor data source for the log files that you want to have analyzed, select the log files, and then request the report.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5a32c-120">使用包含峰值流量周期的 web 流量日志文件, 以获取组织中的使用情况的最佳表示。</span><span class="sxs-lookup"><span data-stu-id="5a32c-120">Use web traffic log files that include peak traffic periods to get the best representation of usage in your organization.</span></span> 
  
1. <span data-ttu-id="5a32c-121">收集[适用于 Office 365 云应用安全的 web 流量日志和数据源](web-traffic-logs-and-data-sources-for-ocas.md)。</span><span class="sxs-lookup"><span data-stu-id="5a32c-121">Collect your [web traffic logs and data sources for Office 365 Cloud App Security](web-traffic-logs-and-data-sources-for-ocas.md).</span></span>
    
2. <span data-ttu-id="5a32c-122">转到云应用安全门户 ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) 并登录。</span><span class="sxs-lookup"><span data-stu-id="5a32c-122">Go to the Cloud App Security portal ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) and sign in.</span></span> 
       
3. <span data-ttu-id="5a32c-123">选择 "**发现** \> **创建新报告**"。</span><span class="sxs-lookup"><span data-stu-id="5a32c-123">Choose **Discover** \> **Create new report**.</span></span> <br><span data-ttu-id="5a32c-124">![在 Office 365 CAS 门户中, 选择 "发现"](media/73b5299f-94b5-49dd-a00f-154d188eb2c5.png)</span><span class="sxs-lookup"><span data-stu-id="5a32c-124">![In the Office 365 CAS portal, choose Discover](media/73b5299f-94b5-49dd-a00f-154d188eb2c5.png)</span></span><br>
  
4. <span data-ttu-id="5a32c-125">为报表指定名称和说明, 然后在 "**数据源**" 列表中选择 web 流量日志的数据源。</span><span class="sxs-lookup"><span data-stu-id="5a32c-125">Specify a name and description for your report, and then select the data source for your web traffic logs in the **Data source** list.</span></span> <br><span data-ttu-id="5a32c-126">![在 O365 CAS 中, 选择\> "发现创建新报告"](media/22e660f0-5eb2-49fa-9fea-f88a5809a07b.png)</span><span class="sxs-lookup"><span data-stu-id="5a32c-126">![In O365 CAS, choose Discover \> Create new report](media/22e660f0-5eb2-49fa-9fea-f88a5809a07b.png)</span></span><br><span data-ttu-id="5a32c-127">如果未列出您想要使用的数据源, 则可以请求添加该数据源。</span><span class="sxs-lookup"><span data-stu-id="5a32c-127">If a data source that you'd like to use is not listed, you can request that it be added.</span></span> <span data-ttu-id="5a32c-128">选择 "**其他**" 作为 "**数据源**", 然后键入要尝试上载的数据源的名称。</span><span class="sxs-lookup"><span data-stu-id="5a32c-128">Select **Other** for **Data source**, and then type the name of the data source that you're trying to upload.</span></span> <span data-ttu-id="5a32c-129">我们将查看日志, 并告知我们是否为生成它的数据源添加支持。</span><span class="sxs-lookup"><span data-stu-id="5a32c-129">We'll review the log, and let you know if we add support for the data source that generated it.</span></span> 
  
5. <span data-ttu-id="5a32c-130">浏览到您收集的日志文件的位置, 并选择这些文件。</span><span class="sxs-lookup"><span data-stu-id="5a32c-130">Browse to the location of the log files you collected and select the files.</span></span> <span data-ttu-id="5a32c-131">日志文件必须由您为报告选择的数据源生成。</span><span class="sxs-lookup"><span data-stu-id="5a32c-131">The log files must have been generated by the data source that you chose for the report.</span></span>
    
6. <span data-ttu-id="5a32c-132">单击 "**创建**" 以启动报告创建过程。</span><span class="sxs-lookup"><span data-stu-id="5a32c-132">Click **Create** to start the report creation process.</span></span> 
    
7. <span data-ttu-id="5a32c-133">若要查看报告的状态, 请单击 "**管理快照报告**"。</span><span class="sxs-lookup"><span data-stu-id="5a32c-133">To see the status of the report, click **Manage snapshot reports**.</span></span> <span data-ttu-id="5a32c-134">报告准备就绪后, 您将看到 "**查看报告**" 选项。</span><span class="sxs-lookup"><span data-stu-id="5a32c-134">When a report is ready, you'll see the **View report** option.</span></span> 
    
## <a name="next-steps"></a><span data-ttu-id="5a32c-135">后续步骤</span><span class="sxs-lookup"><span data-stu-id="5a32c-135">Next steps</span></span>

- [<span data-ttu-id="5a32c-136">查看警报并对其执行操作</span><span class="sxs-lookup"><span data-stu-id="5a32c-136">Review and take action on alerts</span></span>](review-office-365-cas-alerts.md)
    
- [<span data-ttu-id="5a32c-137">查看 Office 365 云应用安全中的应用发现结果</span><span class="sxs-lookup"><span data-stu-id="5a32c-137">Review app discovery findings in Office 365 Cloud App Security</span></span>](review-app-discovery-findings-in-ocas.md)
    
- <span data-ttu-id="5a32c-138">查看[Office 365 云应用安全性的利用率活动](utilization-activities-for-ocas.md)</span><span class="sxs-lookup"><span data-stu-id="5a32c-138">Review your [utilization activities for Office 365 Cloud App Security](utilization-activities-for-ocas.md)</span></span>
    

