---
title: 使用 Office 365 云应用安全创建应用发现报告
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 1/28/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 3e68e691-1fc4-4d3e-a2c0-d3134eb64055
description: 使用 Office 365 云应用程序安全性，您可以了解在组织中的用户如何使用 Office 365 和其他应用程序创建报告。
ms.openlocfilehash: 543a194ec9d441a4feea97b8ad49022094565d7a
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/11/2019
ms.locfileid: "29603713"
---
# <a name="create-app-discovery-reports-using-office-365-cloud-app-security"></a><span data-ttu-id="e5968-103">使用 Office 365 云应用安全创建应用发现报告</span><span class="sxs-lookup"><span data-stu-id="e5968-103">Create app discovery reports using Office 365 Cloud App Security</span></span>

<span data-ttu-id="e5968-104">Office 365 高级安全管理现在是 Office 365 云应用程序安全性。</span><span class="sxs-lookup"><span data-stu-id="e5968-104">Office 365 Advanced Security Management is now Office 365 Cloud App Security.</span></span>
  
|<span data-ttu-id="e5968-105">评估 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="e5968-105">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="e5968-106">规划 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="e5968-106">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="e5968-107">部署 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="e5968-107">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="e5968-108">使用率 \*\*\*</span><span class="sxs-lookup"><span data-stu-id="e5968-108">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="e5968-109">启动评估</span><span class="sxs-lookup"><span data-stu-id="e5968-109">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="e5968-110">开始规划</span><span class="sxs-lookup"><span data-stu-id="e5968-110">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |[<span data-ttu-id="e5968-111">开始部署</span><span class="sxs-lookup"><span data-stu-id="e5968-111">Start deploying</span></span>](turn-on-office-365-cas.md) <br/> |<span data-ttu-id="e5968-112">在这里 ！</span><span class="sxs-lookup"><span data-stu-id="e5968-112">You are here!</span></span>  <br/> [<span data-ttu-id="e5968-113">后续步骤</span><span class="sxs-lookup"><span data-stu-id="e5968-113">Next steps</span></span>](#next-steps) <br/> |
   
<span data-ttu-id="e5968-p101">Office 365 云应用程序安全性帮助全局管理员、 安全管理员和安全读者深入了解在组织中的人员将云服务。例如，您可以看到用户在其中存储并对文档协作和多少数据上载到应用程序或服务的 Office 365 以外。</span><span class="sxs-lookup"><span data-stu-id="e5968-p101">Office 365 Cloud App Security helps global administrators, security administrators, and security readers gain insight into the cloud services people in an organization are using. For example, you can see where users are storing and collaborating on documents and how much data is being uploaded to apps or services that are outside of Office 365.</span></span>
  
<span data-ttu-id="e5968-116">要生成应用程序发现报告，您手动上载 web 流量日志文件从您的防火墙和代理，然后 Office 365 云应用程序安全性分析并分析报表的那些文件。</span><span class="sxs-lookup"><span data-stu-id="e5968-116">To generate an app discovery report, you manually upload your web traffic log files from your firewalls and proxies, and then Office 365 Cloud App Security parses and analyzes those files for your report.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e5968-p102">您必须是全局管理员、 安全管理员或安全读者才能执行本文中描述的任务。若要了解详细信息，请参阅[Permissions in Office 365 安全性&amp;合规性中心](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="e5968-p102">You must be a global administrator, security administrator, or security reader to perform the tasks described in this article. To learn more, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> 
  
## <a name="create-a-report-with-app-discovery"></a><span data-ttu-id="e5968-119">使用应用程序发现创建报表</span><span class="sxs-lookup"><span data-stu-id="e5968-119">Create a report with app discovery</span></span>

<span data-ttu-id="e5968-120">要创建应用程序发现报告，请确定您想要已经分析，请选择日志文件，然后请求报告的日志文件的供应商数据源。</span><span class="sxs-lookup"><span data-stu-id="e5968-120">To create an app discovery report, you identify the vendor data source for the log files that you want to have analyzed, select the log files, and then request the report.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e5968-121">使用包括高峰流量时段，若要使用的最佳表示获取组织中的 web 流量日志文件。</span><span class="sxs-lookup"><span data-stu-id="e5968-121">Use web traffic log files that include peak traffic periods to get the best representation of usage in your organization.</span></span> 
  
1. <span data-ttu-id="e5968-122">收集您的[web 流量日志和 Office 365 云应用程序安全性的数据源](web-traffic-logs-and-data-sources-for-ocas.md)。</span><span class="sxs-lookup"><span data-stu-id="e5968-122">Collect your [web traffic logs and data sources for Office 365 Cloud App Security](web-traffic-logs-and-data-sources-for-ocas.md).</span></span>
    
2. <span data-ttu-id="e5968-123">转到云应用程序安全性门户 ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) 和登录。</span><span class="sxs-lookup"><span data-stu-id="e5968-123">Go to the Cloud App Security portal ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) and sign in.</span></span> 
       
3. <span data-ttu-id="e5968-124">选择**发现** \> **创建新报表**。</span><span class="sxs-lookup"><span data-stu-id="e5968-124">Choose **Discover** \> **Create new report**.</span></span> <br><span data-ttu-id="e5968-125">![在 Office 365 CAS 门户中，选择发现](media/73b5299f-94b5-49dd-a00f-154d188eb2c5.png)</span><span class="sxs-lookup"><span data-stu-id="e5968-125">![In the Office 365 CAS portal, choose Discover](media/73b5299f-94b5-49dd-a00f-154d188eb2c5.png)</span></span><br>
  
4. <span data-ttu-id="e5968-126">指定的名称和说明为您的报表，然后选择**数据源**列表中的 web 流量日志的数据源。</span><span class="sxs-lookup"><span data-stu-id="e5968-126">Specify a name and description for your report, and then select the data source for your web traffic logs in the **Data source** list.</span></span> <br><span data-ttu-id="e5968-127">![在 O365 CAS 中，选择发现\>创建新报表](media/22e660f0-5eb2-49fa-9fea-f88a5809a07b.png)</span><span class="sxs-lookup"><span data-stu-id="e5968-127">![In O365 CAS, choose Discover \> Create new report](media/22e660f0-5eb2-49fa-9fea-f88a5809a07b.png)</span></span><br><span data-ttu-id="e5968-p103">如果未列出您想要使用的数据源，您可以请求将添加它。选择**其他**的**数据源**，然后键入您要上载的数据源的名称。我们将查看日志，并让您了解是否我们添加对它生成的数据源的支持。</span><span class="sxs-lookup"><span data-stu-id="e5968-p103">If a data source that you'd like to use is not listed, you can request that it be added. Select **Other** for **Data source**, and then type the name of the data source that you're trying to upload. We'll review the log, and let you know if we add support for the data source that generated it.</span></span> 
  
5. <span data-ttu-id="e5968-p104">浏览到您收集的日志文件的位置，然后选择文件。所选报表的数据源必须已生成的日志文件。</span><span class="sxs-lookup"><span data-stu-id="e5968-p104">Browse to the location of the log files you collected and select the files. The log files must have been generated by the data source that you chose for the report.</span></span>
    
6. <span data-ttu-id="e5968-133">单击**创建**以启动报表创建过程。</span><span class="sxs-lookup"><span data-stu-id="e5968-133">Click **Create** to start the report creation process.</span></span> 
    
7. <span data-ttu-id="e5968-p105">若要查看的报表的状态，请单击**管理快照报告**。报表准备就绪后，您将看到**查看报告**选项。</span><span class="sxs-lookup"><span data-stu-id="e5968-p105">To see the status of the report, click **Manage snapshot reports**. When a report is ready, you'll see the **View report** option.</span></span> 
    
## <a name="next-steps"></a><span data-ttu-id="e5968-136">后续步骤</span><span class="sxs-lookup"><span data-stu-id="e5968-136">Next steps</span></span>

- [<span data-ttu-id="e5968-137">查看并通知对其执行操作</span><span class="sxs-lookup"><span data-stu-id="e5968-137">Review and take action on alerts</span></span>](review-office-365-cas-alerts.md)
    
- [<span data-ttu-id="e5968-138">查看 Office 365 云应用安全中的应用发现结果</span><span class="sxs-lookup"><span data-stu-id="e5968-138">Review app discovery findings in Office 365 Cloud App Security</span></span>](review-app-discovery-findings-in-ocas.md)
    
- <span data-ttu-id="e5968-139">查看您[的 Office 365 云应用程序安全性的使用率活动](utilization-activities-for-ocas.md)</span><span class="sxs-lookup"><span data-stu-id="e5968-139">Review your [utilization activities for Office 365 Cloud App Security](utilization-activities-for-ocas.md)</span></span>
    

