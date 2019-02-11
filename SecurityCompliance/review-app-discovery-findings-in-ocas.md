---
title: 查看 Office 365 云应用安全中的应用发现结果
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: aac65513-e75e-4c82-a668-9a6604dd9f9d
description: 查看高级安全管理中的应用程序发现报告可帮助您了解有关如何在组织中的人员使用云应用程序的详细信息。您已创建应用程序发现报告使用从防火墙和代理日志文件后，查看应用程序发现仪表板中的结果。
ms.openlocfilehash: 6195c9aae7ae5e398ac555cc820de04dee05d4fd
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/11/2019
ms.locfileid: "29603743"
---
# <a name="review-app-discovery-findings-in-office-365-cloud-app-security"></a><span data-ttu-id="79705-104">查看 Office 365 云应用安全中的应用发现结果</span><span class="sxs-lookup"><span data-stu-id="79705-104">Review app discovery findings in Office 365 Cloud App Security</span></span>
  
|<span data-ttu-id="79705-105">评估 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="79705-105">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="79705-106">规划 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="79705-106">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="79705-107">部署 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="79705-107">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="79705-108">使用率 \*\*\*</span><span class="sxs-lookup"><span data-stu-id="79705-108">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="79705-109">启动评估</span><span class="sxs-lookup"><span data-stu-id="79705-109">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="79705-110">开始规划</span><span class="sxs-lookup"><span data-stu-id="79705-110">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |[<span data-ttu-id="79705-111">开始部署</span><span class="sxs-lookup"><span data-stu-id="79705-111">Start deploying</span></span>](turn-on-office-365-cas.md) <br/> |<span data-ttu-id="79705-112">在这里 ！</span><span class="sxs-lookup"><span data-stu-id="79705-112">You are here!</span></span>  <br/> [<span data-ttu-id="79705-113">后续步骤</span><span class="sxs-lookup"><span data-stu-id="79705-113">Next steps</span></span>](#next-steps) <br/> |
   
<span data-ttu-id="79705-p102">云发现仪表板适用于组织的 web 流量日志，以提供有关云应用程序使用率的详细的信息。如果您的全局管理员、 安全管理员或安全读者，并且您的组织已[创建应用程序发现 Office 365 云应用程序安全性的报告](create-app-discovery-reports-in-ocas.md)，您可以使用云发现仪表板深入了解如何在人员您组织使用 Office 365 和其他云应用程序。（云发现仪表板。 也称为工作效率应用程序发现）</span><span class="sxs-lookup"><span data-stu-id="79705-p102">The Cloud Discovery dashboard works with your organization's web traffic logs to provide detailed information about cloud app usage. If you're a global administrator, security administrator, or security reader, and your organization has [created app discovery reports in Office 365 Cloud App Security](create-app-discovery-reports-in-ocas.md), you can use the Cloud Discovery dashboard to gain insight into how people in your organization are using Office 365 and other cloud apps. (The Cloud Discovery dashboard is also known as Productivity App Discovery.)</span></span>
  
 <span data-ttu-id="79705-117">云发现仪表板，可以查看有关您的组织中的用户如何使用 Office 365 和其他应用程序的详细的信息。</span><span class="sxs-lookup"><span data-stu-id="79705-117">The Cloud Discovery dashboard enables you to view detailed information about how people in your organization are using Office 365 and other apps.</span></span> 
  
![已更新，云发现仪表板](media/12712681-c0b3-4cb3-b7fd-2cf2ad4e825f.png)
     
## <a name="go-to-the-cloud-discovery-dashboard"></a><span data-ttu-id="79705-119">转到云发现仪表板</span><span class="sxs-lookup"><span data-stu-id="79705-119">Go to the Cloud Discovery dashboard</span></span>

1. <span data-ttu-id="79705-120">转到云应用程序安全性门户 ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) 和登录。</span><span class="sxs-lookup"><span data-stu-id="79705-120">Go to the Cloud App Security portal ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) and sign in.</span></span>
    
2. <span data-ttu-id="79705-121">转到**发现** \> **云发现仪表板**。</span><span class="sxs-lookup"><span data-stu-id="79705-121">Go to **Discover** \> **Cloud Discovery dashboard**.</span></span>
    
## <a name="see-your-top-users-ip-addresses-apps-and-risk-levels"></a><span data-ttu-id="79705-122">请参阅您最多的用户、 IP 地址、 应用程序，以及风险级别</span><span class="sxs-lookup"><span data-stu-id="79705-122">See your top users, IP addresses, apps, and risk levels</span></span>

<span data-ttu-id="79705-123">云发现仪表板为您提供了一览 overview of apps 中您的组织、 任何打开的警报、 最多的用户和风险级别与 Office 365 一起使用。</span><span class="sxs-lookup"><span data-stu-id="79705-123">The Cloud Discovery dashboard gives you an at-a-glance overview of apps that are used with Office 365 in your organization, any open alerts, top users, and risk levels.</span></span>
  
![云发现 dashboaard](media/06696946-fbdf-4781-b5b8-2ac074fcb2a1.png)
  
1. <span data-ttu-id="79705-125">在**仪表板**选项卡，查看组织中的概述部分中的总体云应用程序使用屏幕的顶部。</span><span class="sxs-lookup"><span data-stu-id="79705-125">On the **Dashboard** tab, look at the overall cloud app use in your organization in the overview section across the top of the screen.</span></span> 
    
2. <span data-ttu-id="79705-126">请参阅**Office 365 类别**组织中使用的应用程序。</span><span class="sxs-lookup"><span data-stu-id="79705-126">See the **Office 365 categories** for apps that are used in your organization.</span></span> 
    
3. <span data-ttu-id="79705-127">查看**Discovered 应用程序**小部件，若要查看用法的 Office 365 和此视图中的其他应用程序。</span><span class="sxs-lookup"><span data-stu-id="79705-127">Look at the **Discovered apps** widget to see usage of Office 365 and other apps in this view.</span></span> 
    
4. <span data-ttu-id="79705-128">查看**最多用户**和**顶部 IP 地址**小部件来标识那些使用 Office 365 和云组织中最多的应用程序。</span><span class="sxs-lookup"><span data-stu-id="79705-128">Look at the **Top users** and **Top IP addresses** widget to identify those who use Office 365 and cloud apps the most in your organization.</span></span> 
    
5. <span data-ttu-id="79705-129">请参阅人正在使用的应用程序在何处按地理位置使用的**应用程序总部位置**映射。</span><span class="sxs-lookup"><span data-stu-id="79705-129">See where the apps people are using are by geographical location by using the **Apps headquarters location** map.</span></span> 
    
6. <span data-ttu-id="79705-p103">上方的映射区域中，看看的**风险级别**overview 中发现的应用程序的风险分数。您可以查看由相同的组和类别的**Discovered 应用程序**区域中使用的风险。例如，您可以看到多少中每个分组的通信是从高、 中型或低风险应用程序。</span><span class="sxs-lookup"><span data-stu-id="79705-p103">Above the maps area, take a look at the risk score of the discovered apps in the **Risk levels** overview. You can look at risks by the same groups and categories that you used in the **Discovered apps** area. For example, you can see how much traffic in each grouping is from high, medium, or low risk apps.</span></span> 
    
## <a name="dive-deeper-into-the-information"></a><span data-ttu-id="79705-133">深入信息</span><span class="sxs-lookup"><span data-stu-id="79705-133">Dive deeper into the information</span></span>

<span data-ttu-id="79705-134">您可以使用云发现更深入地介绍一下在应用程序、 子域、 IP 地址和用户。</span><span class="sxs-lookup"><span data-stu-id="79705-134">You can use Cloud Discovery to take a deeper look at apps, subdomains, IP addresses, and users.</span></span>
  
1. <span data-ttu-id="79705-135">在云发现仪表板，选择**Discovered 应用程序**选项卡。</span><span class="sxs-lookup"><span data-stu-id="79705-135">In the Cloud Discovery dashboard, choose the **Discovered apps** tab.</span></span> 
    
2. <span data-ttu-id="79705-136">使用筛选器部分可以查看按名称、 类别、 使用率级别或上次查看的日期的应用程序。</span><span class="sxs-lookup"><span data-stu-id="79705-136">Use the filters section to view apps by name, category, usage level, or last seen date.</span></span>
    
3. <span data-ttu-id="79705-137">在结果列表中，悬停按应用程序名称以显示**查看子域**链接。</span><span class="sxs-lookup"><span data-stu-id="79705-137">In the list of results, hover by an app name to reveal the **View sub-domains** link.</span></span><br/> <span data-ttu-id="79705-138">![将鼠标悬停旁边显示一个链接，用于查看子域的详细信息的应用程序](media/4a212215-8a2c-46fd-9ef9-89e4064658a6.png)</span><span class="sxs-lookup"><span data-stu-id="79705-138">![Hover next to an app to reveal a link to view subdomain details](media/4a212215-8a2c-46fd-9ef9-89e4064658a6.png)</span></span><br/><span data-ttu-id="79705-139">将显示所选应用程序的详细的信息。</span><span class="sxs-lookup"><span data-stu-id="79705-139">Detailed information about the selected app will appear.</span></span>
    
4. <span data-ttu-id="79705-140">若要查看有关 IP 地址的详细信息，请选择**IP 地址**选项卡。</span><span class="sxs-lookup"><span data-stu-id="79705-140">To view details about IP addresses, choose the **IP addresses** tab.</span></span><br/><span data-ttu-id="79705-141">![云发现显示 IP 地址的详细的信息](media/0c742bf6-da9e-4d22-8656-a27a5007d5d5.png)</span><span class="sxs-lookup"><span data-stu-id="79705-141">![Cloud Discovery shows detailed information about IP addresses](media/0c742bf6-da9e-4d22-8656-a27a5007d5d5.png)</span></span><br/><span data-ttu-id="79705-142">在结果列表中，选择单个 IP 地址以查看更多详细的信息。</span><span class="sxs-lookup"><span data-stu-id="79705-142">In the list of results, select an individual IP address to view more detailed information.</span></span>
    
5. <span data-ttu-id="79705-143">若要查看有关组织内的 Office 365 用户的详细信息，请选择**用户**选项卡。</span><span class="sxs-lookup"><span data-stu-id="79705-143">To view details about Office 365 users within your organization, choose the **Users** tab.</span></span><br/><span data-ttu-id="79705-144">![云发现-用户信息](media/2d9c2d85-01e6-4057-8020-d9a68f26bbac.png)</span><span class="sxs-lookup"><span data-stu-id="79705-144">![Cloud Discovery - users info](media/2d9c2d85-01e6-4057-8020-d9a68f26bbac.png)</span></span>
  
## <a name="exclude-entities"></a><span data-ttu-id="79705-145">排除实体</span><span class="sxs-lookup"><span data-stu-id="79705-145">Exclude entities</span></span>

<span data-ttu-id="79705-146">为了重点关注更具体的信息，您可以排除特定系统用户或 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="79705-146">You can exclude certain system users or IP addresses in order to focus on more specific information.</span></span>
  
1. <span data-ttu-id="79705-147">选择**设置** \> **云发现设置**。</span><span class="sxs-lookup"><span data-stu-id="79705-147">Choose **Settings** \> **Cloud Discovery settings**.</span></span>
    
2. <span data-ttu-id="79705-148">选择**排除实体**。</span><span class="sxs-lookup"><span data-stu-id="79705-148">Choose **Exclude entities**.</span></span>
    
3. <span data-ttu-id="79705-149">选择**排除的用户**或**排除的 IP 地址**。</span><span class="sxs-lookup"><span data-stu-id="79705-149">Choose either **Excluded users** or **Excluded IP addresses**.</span></span>
    
4. <span data-ttu-id="79705-150">指定的用户或 IP 地址，并在**注释**框中，键入有关为什么您不包括这些用户或 IP 地址的信息。</span><span class="sxs-lookup"><span data-stu-id="79705-150">Specify the users or IP addresses, and in the **Comments** box, type information about why you are excluding those users or IP addresses.</span></span> 
    
5. <span data-ttu-id="79705-151">选择" **添加**"。</span><span class="sxs-lookup"><span data-stu-id="79705-151">Choose **Add**.</span></span>
    
## <a name="next-steps"></a><span data-ttu-id="79705-152">后续步骤</span><span class="sxs-lookup"><span data-stu-id="79705-152">Next steps</span></span>

- [<span data-ttu-id="79705-153">查看并通知对其执行操作</span><span class="sxs-lookup"><span data-stu-id="79705-153">Review and take action on alerts</span></span>](review-office-365-cas-alerts.md)
    
- [<span data-ttu-id="79705-154">创建应用程序发现报告</span><span class="sxs-lookup"><span data-stu-id="79705-154">Create app discovery reports</span></span>](create-app-discovery-reports-in-ocas.md)
    
- <span data-ttu-id="79705-155">查看您[的 Office 365 云应用程序安全性的使用率活动](utilization-activities-for-ocas.md)</span><span class="sxs-lookup"><span data-stu-id="79705-155">Review your [utilization activities for Office 365 Cloud App Security](utilization-activities-for-ocas.md)</span></span>
    

