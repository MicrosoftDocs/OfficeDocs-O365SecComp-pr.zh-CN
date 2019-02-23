---
title: 查看 Office 365 云应用安全中的应用发现结果
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: aac65513-e75e-4c82-a668-9a6604dd9f9d
description: 查看 Office 365 中的应用程序发现报告云应用安全可帮助您了解有关组织中的人员如何使用云应用的详细信息。在使用防火墙和代理中的日志文件创建应用程序发现报告之后, 请在应用发现仪表板中查看结果。
ms.openlocfilehash: f50ad372450b2a1404829eeb6f6964c1d954dccd
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30216252"
---
# <a name="review-app-discovery-findings-in-office-365-cloud-app-security"></a><span data-ttu-id="d3f78-104">查看 Office 365 云应用安全中的应用发现结果</span><span class="sxs-lookup"><span data-stu-id="d3f78-104">Review app discovery findings in Office 365 Cloud App Security</span></span>
  
|<span data-ttu-id="d3f78-105">评估 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="d3f78-105">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="d3f78-106">规划 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="d3f78-106">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="d3f78-107">部署 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="d3f78-107">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="d3f78-108">利用率 \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="d3f78-108">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="d3f78-109">开始评估</span><span class="sxs-lookup"><span data-stu-id="d3f78-109">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="d3f78-110">开始规划</span><span class="sxs-lookup"><span data-stu-id="d3f78-110">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |[<span data-ttu-id="d3f78-111">开始部署</span><span class="sxs-lookup"><span data-stu-id="d3f78-111">Start deploying</span></span>](turn-on-office-365-cas.md) <br/> |<span data-ttu-id="d3f78-112">你在这里!</span><span class="sxs-lookup"><span data-stu-id="d3f78-112">You are here!</span></span>  <br/> [<span data-ttu-id="d3f78-113">后续步骤</span><span class="sxs-lookup"><span data-stu-id="d3f78-113">Next steps</span></span>](#next-steps) <br/> |
   
<span data-ttu-id="d3f78-p102">云发现仪表板可与组织的 web 流量日志配合使用, 以提供有关云应用使用情况的详细信息。如果您是全局管理员、安全管理员或安全读者, 并且您的组织已[在 Office 365 Cloud app security 中创建了应用程序发现报告](create-app-discovery-reports-in-ocas.md), 则可以使用云发现仪表板深入了解您的人员如何组织使用的是 Office 365 和其他云应用。(云发现仪表板也称为 "生产应用程序发现"。)</span><span class="sxs-lookup"><span data-stu-id="d3f78-p102">The Cloud Discovery dashboard works with your organization's web traffic logs to provide detailed information about cloud app usage. If you're a global administrator, security administrator, or security reader, and your organization has [created app discovery reports in Office 365 Cloud App Security](create-app-discovery-reports-in-ocas.md), you can use the Cloud Discovery dashboard to gain insight into how people in your organization are using Office 365 and other cloud apps. (The Cloud Discovery dashboard is also known as Productivity App Discovery.)</span></span>
  
 <span data-ttu-id="d3f78-117">通过云发现仪表板, 可以查看有关组织中的人员如何使用 Office 365 和其他应用程序的详细信息。</span><span class="sxs-lookup"><span data-stu-id="d3f78-117">The Cloud Discovery dashboard enables you to view detailed information about how people in your organization are using Office 365 and other apps.</span></span> 
  
![云发现仪表板已更新](media/12712681-c0b3-4cb3-b7fd-2cf2ad4e825f.png)
     
## <a name="go-to-the-cloud-discovery-dashboard"></a><span data-ttu-id="d3f78-119">转到云发现仪表板</span><span class="sxs-lookup"><span data-stu-id="d3f78-119">Go to the Cloud Discovery dashboard</span></span>

1. <span data-ttu-id="d3f78-120">转到云应用安全门户 ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) 并登录。</span><span class="sxs-lookup"><span data-stu-id="d3f78-120">Go to the Cloud App Security portal ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) and sign in.</span></span>
    
2. <span data-ttu-id="d3f78-121">转到 "**发现** \> **云发现" 仪表板**。</span><span class="sxs-lookup"><span data-stu-id="d3f78-121">Go to **Discover** \> **Cloud Discovery dashboard**.</span></span>
    
## <a name="see-your-top-users-ip-addresses-apps-and-risk-levels"></a><span data-ttu-id="d3f78-122">查看您的首要用户、IP 地址、应用程序和风险级别</span><span class="sxs-lookup"><span data-stu-id="d3f78-122">See your top users, IP addresses, apps, and risk levels</span></span>

<span data-ttu-id="d3f78-123">云发现仪表板为您提供了有关在组织中使用 Office 365 的应用、任何打开的警报、顶级用户和风险级别的概览。</span><span class="sxs-lookup"><span data-stu-id="d3f78-123">The Cloud Discovery dashboard gives you an at-a-glance overview of apps that are used with Office 365 in your organization, any open alerts, top users, and risk levels.</span></span>
  
![云 Discovery dashboaard](media/06696946-fbdf-4781-b5b8-2ac074fcb2a1.png)
  
1. <span data-ttu-id="d3f78-125">在 "**仪表板**" 选项卡上, 在屏幕顶部的 "概述" 部分中查看您的组织中的整体云应用程序使用情况。</span><span class="sxs-lookup"><span data-stu-id="d3f78-125">On the **Dashboard** tab, look at the overall cloud app use in your organization in the overview section across the top of the screen.</span></span> 
    
2. <span data-ttu-id="d3f78-126">有关在组织中使用的应用程序, 请参阅**Office 365 类别**。</span><span class="sxs-lookup"><span data-stu-id="d3f78-126">See the **Office 365 categories** for apps that are used in your organization.</span></span> 
    
3. <span data-ttu-id="d3f78-127">查看 "已**发现的应用程序**" 小部件, 以查看此视图中的 Office 365 和其他应用程序的使用情况。</span><span class="sxs-lookup"><span data-stu-id="d3f78-127">Look at the **Discovered apps** widget to see usage of Office 365 and other apps in this view.</span></span> 
    
4. <span data-ttu-id="d3f78-128">查看 "**顶级用户**和**首要 IP 地址**" 小部件, 以确定使用组织中最多的 Office 365 和云应用的用户。</span><span class="sxs-lookup"><span data-stu-id="d3f78-128">Look at the **Top users** and **Top IP addresses** widget to identify those who use Office 365 and cloud apps the most in your organization.</span></span> 
    
5. <span data-ttu-id="d3f78-129">使用**应用总部位置**映射查看用户使用的应用程序的位置。</span><span class="sxs-lookup"><span data-stu-id="d3f78-129">See where the apps people are using are by geographical location by using the **Apps headquarters location** map.</span></span> 
    
6. <span data-ttu-id="d3f78-p103">在 "地图" 区域上方, 查看发现的应用在**风险级别**概述中的风险分数。您可以通过在**发现的应用程序**区域中使用的相同组和类别查看风险。例如, 您可以查看每个分组中的流量来自高、中或低风险的应用程序。</span><span class="sxs-lookup"><span data-stu-id="d3f78-p103">Above the maps area, take a look at the risk score of the discovered apps in the **Risk levels** overview. You can look at risks by the same groups and categories that you used in the **Discovered apps** area. For example, you can see how much traffic in each grouping is from high, medium, or low risk apps.</span></span> 
    
## <a name="dive-deeper-into-the-information"></a><span data-ttu-id="d3f78-133">深入了解信息</span><span class="sxs-lookup"><span data-stu-id="d3f78-133">Dive deeper into the information</span></span>

<span data-ttu-id="d3f78-134">您可以使用云发现深入了解应用、子域、IP 地址和用户。</span><span class="sxs-lookup"><span data-stu-id="d3f78-134">You can use Cloud Discovery to take a deeper look at apps, subdomains, IP addresses, and users.</span></span>
  
1. <span data-ttu-id="d3f78-135">在 "云发现" 仪表板中, 选择 "**发现的应用**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="d3f78-135">In the Cloud Discovery dashboard, choose the **Discovered apps** tab.</span></span> 
    
2. <span data-ttu-id="d3f78-136">使用 "筛选器" 部分按名称、类别、使用级别或上次查看日期查看应用程序。</span><span class="sxs-lookup"><span data-stu-id="d3f78-136">Use the filters section to view apps by name, category, usage level, or last seen date.</span></span>
    
3. <span data-ttu-id="d3f78-137">在结果列表中, 悬停在应用程序名称旁边以显示 "**查看子域**" 链接。</span><span class="sxs-lookup"><span data-stu-id="d3f78-137">In the list of results, hover by an app name to reveal the **View sub-domains** link.</span></span><br/> <span data-ttu-id="d3f78-138">![悬停在某个应用旁边, 以显示用于查看子域详细信息的链接](media/4a212215-8a2c-46fd-9ef9-89e4064658a6.png)</span><span class="sxs-lookup"><span data-stu-id="d3f78-138">![Hover next to an app to reveal a link to view subdomain details](media/4a212215-8a2c-46fd-9ef9-89e4064658a6.png)</span></span><br/><span data-ttu-id="d3f78-139">将显示有关所选应用程序的详细信息。</span><span class="sxs-lookup"><span data-stu-id="d3f78-139">Detailed information about the selected app will appear.</span></span>
    
4. <span data-ttu-id="d3f78-140">若要查看有关 IP 地址的详细信息, 请选择 " **ip 地址**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="d3f78-140">To view details about IP addresses, choose the **IP addresses** tab.</span></span><br/><span data-ttu-id="d3f78-141">![云发现显示有关 IP 地址的详细信息](media/0c742bf6-da9e-4d22-8656-a27a5007d5d5.png)</span><span class="sxs-lookup"><span data-stu-id="d3f78-141">![Cloud Discovery shows detailed information about IP addresses](media/0c742bf6-da9e-4d22-8656-a27a5007d5d5.png)</span></span><br/><span data-ttu-id="d3f78-142">在结果列表中, 选择单个 IP 地址以查看更详细的信息。</span><span class="sxs-lookup"><span data-stu-id="d3f78-142">In the list of results, select an individual IP address to view more detailed information.</span></span>
    
5. <span data-ttu-id="d3f78-143">若要查看组织中的 Office 365 用户的详细信息, 请选择 "**用户**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="d3f78-143">To view details about Office 365 users within your organization, choose the **Users** tab.</span></span><br/><span data-ttu-id="d3f78-144">![云发现-用户信息](media/2d9c2d85-01e6-4057-8020-d9a68f26bbac.png)</span><span class="sxs-lookup"><span data-stu-id="d3f78-144">![Cloud Discovery - users info](media/2d9c2d85-01e6-4057-8020-d9a68f26bbac.png)</span></span>
  
## <a name="exclude-entities"></a><span data-ttu-id="d3f78-145">排除实体</span><span class="sxs-lookup"><span data-stu-id="d3f78-145">Exclude entities</span></span>

<span data-ttu-id="d3f78-146">您可以排除某些系统用户或 IP 地址, 以便重点关注更多特定信息。</span><span class="sxs-lookup"><span data-stu-id="d3f78-146">You can exclude certain system users or IP addresses in order to focus on more specific information.</span></span>
  
1. <span data-ttu-id="d3f78-147">选择 "**设置** \> **云发现设置**"。</span><span class="sxs-lookup"><span data-stu-id="d3f78-147">Choose **Settings** \> **Cloud Discovery settings**.</span></span>
    
2. <span data-ttu-id="d3f78-148">选择 "**排除实体**"。</span><span class="sxs-lookup"><span data-stu-id="d3f78-148">Choose **Exclude entities**.</span></span>
    
3. <span data-ttu-id="d3f78-149">选择 "已**排除的用户**" 或 "已排除的**IP 地址**"。</span><span class="sxs-lookup"><span data-stu-id="d3f78-149">Choose either **Excluded users** or **Excluded IP addresses**.</span></span>
    
4. <span data-ttu-id="d3f78-150">指定用户或 ip 地址, 并在 "**注释**" 框中键入有关排除这些用户或 ip 地址的原因的信息。</span><span class="sxs-lookup"><span data-stu-id="d3f78-150">Specify the users or IP addresses, and in the **Comments** box, type information about why you are excluding those users or IP addresses.</span></span> 
    
5. <span data-ttu-id="d3f78-151">选择" **添加**"。</span><span class="sxs-lookup"><span data-stu-id="d3f78-151">Choose **Add**.</span></span>
    
## <a name="next-steps"></a><span data-ttu-id="d3f78-152">后续步骤</span><span class="sxs-lookup"><span data-stu-id="d3f78-152">Next steps</span></span>

- [<span data-ttu-id="d3f78-153">查看警报并对其执行操作</span><span class="sxs-lookup"><span data-stu-id="d3f78-153">Review and take action on alerts</span></span>](review-office-365-cas-alerts.md)
    
- [<span data-ttu-id="d3f78-154">创建应用发现报告</span><span class="sxs-lookup"><span data-stu-id="d3f78-154">Create app discovery reports</span></span>](create-app-discovery-reports-in-ocas.md)
    
- <span data-ttu-id="d3f78-155">查看[Office 365 云应用安全性的利用率活动](utilization-activities-for-ocas.md)</span><span class="sxs-lookup"><span data-stu-id="d3f78-155">Review your [utilization activities for Office 365 Cloud App Security](utilization-activities-for-ocas.md)</span></span>
    

