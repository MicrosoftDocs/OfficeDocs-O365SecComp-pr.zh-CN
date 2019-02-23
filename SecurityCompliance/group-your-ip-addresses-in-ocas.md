---
title: 对 IP 地址进行分组以简化 Office 365 云应用安全中的管理
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/28/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: b5e1471c-1ad6-4bc5-9e75-ce791aee283c
description: 若要轻松识别您将在 Office 365 云应用安全性 (如物理 Office IP 地址) 中使用的 ip 地址集, 可以设置 ip 地址范围组。
ms.openlocfilehash: b8f5c1dd46b2e3990d53a65881d12ca8f3961b16
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30220442"
---
# <a name="group-your-ip-addresses-to-simplify-management-in-office-365-cloud-app-security"></a><span data-ttu-id="14d46-103">对 IP 地址进行分组以简化 Office 365 云应用安全中的管理</span><span class="sxs-lookup"><span data-stu-id="14d46-103">Group your IP addresses to simplify management in Office 365 Cloud App Security</span></span>
  
|<span data-ttu-id="14d46-104">评估 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="14d46-104">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="14d46-105">规划 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="14d46-105">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="14d46-106">部署 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="14d46-106">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="14d46-107">利用率 \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="14d46-107">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="14d46-108">开始评估</span><span class="sxs-lookup"><span data-stu-id="14d46-108">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="14d46-109">开始规划</span><span class="sxs-lookup"><span data-stu-id="14d46-109">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |<span data-ttu-id="14d46-110">你在这里!</span><span class="sxs-lookup"><span data-stu-id="14d46-110">You are here!</span></span>  <br/> [<span data-ttu-id="14d46-111">后续步骤</span><span class="sxs-lookup"><span data-stu-id="14d46-111">Next steps</span></span>](#next-steps) <br/> |[<span data-ttu-id="14d46-112">开始利用</span><span class="sxs-lookup"><span data-stu-id="14d46-112">Start utilizing</span></span>](utilization-activities-for-ocas.md) <br/> |
   
<span data-ttu-id="14d46-p101">若要轻松识别您将在 Office 365 云应用安全性 (如物理 Office IP 地址) 中使用的 ip 地址集, 可以设置 ip 地址范围组。通过定义这些范围, 可以对其进行标记和分类, 然后可以使用标记和类别自定义活动日志和通知的显示和调查方式。</span><span class="sxs-lookup"><span data-stu-id="14d46-p101">To easily identify sets of IP addresses that you'll use in Office 365 Cloud App Security, such as your physical office IP addresses, you can set up groups of IP address ranges. Defining these ranges lets you tag and categorize them, and then you can use tags and categories to customize how your activity logs and alerts are displayed and investigated.</span></span>
  
<span data-ttu-id="14d46-p102">每组 IP 范围都可以使用您选择的标记名称进行标记, 然后可以根据 IP 类别的默认列表 (如公司、管理、危险和 VPN) 对这些标记进行分类。IPv4 和 IPv6 地址都受支持。</span><span class="sxs-lookup"><span data-stu-id="14d46-p102">Each group of IP ranges can be tagged with tag names that you choose, and then the tags can be categorized based on a default list of IP categories (such as Corporate, Administrative, Risky, and VPN). Both IPv4 and IPv6 addresses are supported.</span></span>
  
> [!NOTE]
> <span data-ttu-id="14d46-p103">您必须是全局管理员或安全管理员才能执行本文中的过程。若要了解详细信息, 请参阅[Office 365 安全&amp;合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="14d46-p103">You must be a global administrator or security administrator to perform the procedures in this article. To learn more, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> 
  
## <a name="to-set-up-an-ip-address-range-in-office-365-cloud-app-security"></a><span data-ttu-id="14d46-119">在 Office 365 Cloud App Security 中设置 IP 地址范围</span><span class="sxs-lookup"><span data-stu-id="14d46-119">To set up an IP address range in Office 365 Cloud App Security</span></span>

1. <span data-ttu-id="14d46-120">作为全局管理员或安全管理员, 请转到云应用安全门户 ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) 并登录。</span><span class="sxs-lookup"><span data-stu-id="14d46-120">As a global administrator or security administrator, go to the Cloud App Security portal ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) and sign in.</span></span>
    
2. <span data-ttu-id="14d46-121">在页面的右上方, 单击 "**设置** \> **IP 地址范围**"。</span><span class="sxs-lookup"><span data-stu-id="14d46-121">On the upper right of the page, click **Settings** \> **IP address ranges**.</span></span><br><span data-ttu-id="14d46-122">![在 O365 云应用安全性中, 选择 "设置" 以访问系统和数据设置](media/f6c48ee3-39b4-4b5a-8252-b6493b7bcd3d.png)</span><span class="sxs-lookup"><span data-stu-id="14d46-122">![In O365 Cloud App Security, choose Settings to access your system and data settings](media/f6c48ee3-39b4-4b5a-8252-b6493b7bcd3d.png)</span></span><br>
  
3. <span data-ttu-id="14d46-123">单击 "新建" 按钮, 它类似于加号 ( **+**)。</span><span class="sxs-lookup"><span data-stu-id="14d46-123">Click the new button, which resembles a plus sign ( **+**).</span></span>
    
4. <span data-ttu-id="14d46-124">在 "**新 IP 地址范围**" 窗口中, 指定以下值:</span><span class="sxs-lookup"><span data-stu-id="14d46-124">In the **New IP address range** window, specify the following values:</span></span> 
    
|<span data-ttu-id="14d46-125">**字段或列表**</span><span class="sxs-lookup"><span data-stu-id="14d46-125">**Field or list**</span></span>|<span data-ttu-id="14d46-126">**需执行的操作**</span><span class="sxs-lookup"><span data-stu-id="14d46-126">**What to do**</span></span>|
|:-----|:-----|
|<span data-ttu-id="14d46-127">**名称**</span><span class="sxs-lookup"><span data-stu-id="14d46-127">**Name**</span></span> <br/> |<span data-ttu-id="14d46-p104">使用此字段可管理您的 IP 地址范围和设置。(您不会在 "活动日志" 中看到此值。)</span><span class="sxs-lookup"><span data-stu-id="14d46-p104">Use this field to manage your IP address range and settings. (You won't see this value in activities logs.)</span></span>  <br/> |
|<span data-ttu-id="14d46-130">**IP 地址范围**</span><span class="sxs-lookup"><span data-stu-id="14d46-130">**IP address ranges**</span></span> <br/> |<span data-ttu-id="14d46-p105">使用网络前缀表示法指定一个范围 (也称为 CIDR 表示法)。例如, 192.168.1.0/27 包含值192.168.1.0 到 192.168.1.31 (包括这两个值) 的范围。</span><span class="sxs-lookup"><span data-stu-id="14d46-p105">Specify a range, using network prefix notation (also known as CIDR notation). For example, 192.168.1.0/27 includes the range of values 192.168.1.0 through 192.168.1.31 (inclusive).</span></span>  <br/> |
|<span data-ttu-id="14d46-133">**位置**和**注册的 ISP**</span><span class="sxs-lookup"><span data-stu-id="14d46-133">**Location** and **Registered ISP**</span></span> <br/> |<span data-ttu-id="14d46-p106">为 IP 地址范围指定位置和 Internet 服务提供商 (ISP)。这将覆盖为地址定义的公共字段, 这对于事例 (如 IP 地址) 很有用, 例如在爱尔兰中被视为公开, 但实际上是在美国</span><span class="sxs-lookup"><span data-stu-id="14d46-p106">Specify the location and Internet Service Provider (ISP) for the IP address range. This overrides the public fields defined for the addresses, which is helpful for cases, such as an IP address is that is considered publicly to be in Ireland but is actually in the U.S.</span></span>  <br/> |
|<span data-ttu-id="14d46-136">**Tags**</span><span class="sxs-lookup"><span data-stu-id="14d46-136">**Tags**</span></span> <br/> |<span data-ttu-id="14d46-p107">使用标记命名您的 IP 地址组。(与 "名称" 字段不同, 您将在 "活动日志" 中看到标记。)键入要用于标记的单词或短语。您可以根据需要为每个 IP 地址范围添加任意数量的标记。如果您已经设置了一个标记, 并且想要向其添加此 IP 地址范围, 请从开始键入时显示的当前标记列表中进行选择。</span><span class="sxs-lookup"><span data-stu-id="14d46-p107">Use tags to name your groups of IP addresses. (Unlike the Name field, you will see Tags in activity logs.) Type a word or phrase that you want to use for a tag. You can add as many tags as you like for each IP address range. And if you've already set up a tag and you want to add this IP address range to it, choose it from the list of current tags that appear as you start typing.</span></span>  <br/> |
|<span data-ttu-id="14d46-141">**类别**</span><span class="sxs-lookup"><span data-stu-id="14d46-141">**Category**</span></span> <br/> | <span data-ttu-id="14d46-p108">为您的标记分配类别, 以便更轻松地识别来自特定 IP 地址的活动。从以下选项中进行选择:</span><span class="sxs-lookup"><span data-stu-id="14d46-p108">Assign categories to your tags to make it easier to recognize activities that come from certain IP addresses. Choose from the following options:  </span></span><br/> <span data-ttu-id="14d46-144">**管理**管理员的所有 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="14d46-144">**Administrative** All of the IP addresses of your admins.</span></span>  <br/> <span data-ttu-id="14d46-145">**云提供程序**云中代理的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="14d46-145">**Cloud provider** The IP address of your proxy in the cloud.</span></span>  <br/> <span data-ttu-id="14d46-146">**企业**内部网络中的所有 IP 地址、分支机构和 wlan 漫游地址。</span><span class="sxs-lookup"><span data-stu-id="14d46-146">**Corporate** All of the IP addresses in your internal network, your branch offices, and your Wi-Fi roaming addresses.</span></span>  <br/> <span data-ttu-id="14d46-p109">**风险**您认为有风险的任何 IP 地址, 如过去所见到的可疑 ip 地址、竞争对手网络中的 ip 地址等。默认情况下, 有风险的类别包括两个 IP 标记:**匿名代理**和**Tor**</span><span class="sxs-lookup"><span data-stu-id="14d46-p109">**Risky** Any IP addresses that you consider to be risky, such as suspicious IP addresses you've seen in the past, IP addresses in your competitors' networks, and so on. By default, the Risky categories includes two IP tags: **Anonymous proxy** and **Tor**</span></span> <br/> <span data-ttu-id="14d46-149">**VPN**您的远程工作人员使用的任何 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="14d46-149">**VPN** Any IP addresses that your remote workers use.</span></span>  <br/> |
   
7. <span data-ttu-id="14d46-150">选择" **保存**"。</span><span class="sxs-lookup"><span data-stu-id="14d46-150">Choose **Save**.</span></span>
    
<span data-ttu-id="14d46-151">设置 IP 地址范围后, 请记住, 这些更改仅影响将来的事件。</span><span class="sxs-lookup"><span data-stu-id="14d46-151">After you set up your IP address ranges, keep in mind that only future events are affected by these changes.</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="14d46-152">后续步骤</span><span class="sxs-lookup"><span data-stu-id="14d46-152">Next steps</span></span>

- [<span data-ttu-id="14d46-153">活动策略和警报</span><span class="sxs-lookup"><span data-stu-id="14d46-153">Activity policies and alerts</span></span>](activity-policies-and-alerts.md)
    
- [<span data-ttu-id="14d46-154">异常情况检测策略</span><span class="sxs-lookup"><span data-stu-id="14d46-154">Anomaly detection policies</span></span>](anomaly-detection-policies-in-ocas.md)
    
- [<span data-ttu-id="14d46-155">集成您的 SIEM 服务器</span><span class="sxs-lookup"><span data-stu-id="14d46-155">Integrate your SIEM server</span></span>](integrate-your-siem-server-with-office-365-cas.md)
    
- [<span data-ttu-id="14d46-156">查看 Office 365 云应用安全中的警报并执行相应操作</span><span class="sxs-lookup"><span data-stu-id="14d46-156">Review and take action on alerts in Office 365 Cloud App Security</span></span>](review-office-365-cas-alerts.md)
    

