---
title: 对 IP 地址进行分组以简化 Office 365 云应用安全中的管理
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 2/22/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: b5e1471c-1ad6-4bc5-9e75-ce791aee283c
description: 可以轻松地识别套将在 Office 365 云应用程序安全性，使用您实际办公室的 IP 地址，如的 IP 地址可以设置组的 IP 地址范围。
ms.openlocfilehash: 76cb9625a46d1f5eceaab696de5dcbb72f4d2b47
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22524825"
---
# <a name="group-your-ip-addresses-to-simplify-management-in-office-365-cloud-app-security"></a><span data-ttu-id="dce5b-103">对 IP 地址进行分组以简化 Office 365 云应用安全中的管理</span><span class="sxs-lookup"><span data-stu-id="dce5b-103">Group your IP addresses to simplify management in Office 365 Cloud App Security</span></span>
  
|<span data-ttu-id="dce5b-104">评估 * *\>**</span><span class="sxs-lookup"><span data-stu-id="dce5b-104">****Evaluation** \>**</span></span>|<span data-ttu-id="dce5b-105">规划 * *\>**</span><span class="sxs-lookup"><span data-stu-id="dce5b-105">****Planning** \>**</span></span>|<span data-ttu-id="dce5b-106">部署 * *\>**</span><span class="sxs-lookup"><span data-stu-id="dce5b-106">****Deployment** \>**</span></span>|<span data-ttu-id="dce5b-107">使用率 \*\*\*</span><span class="sxs-lookup"><span data-stu-id="dce5b-107">****Utilization****</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="dce5b-108">启动评估</span><span class="sxs-lookup"><span data-stu-id="dce5b-108">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="dce5b-109">开始规划</span><span class="sxs-lookup"><span data-stu-id="dce5b-109">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |<span data-ttu-id="dce5b-110">在这里 ！</span><span class="sxs-lookup"><span data-stu-id="dce5b-110">You are here!</span></span>  <br/> [<span data-ttu-id="dce5b-111">后续步骤</span><span class="sxs-lookup"><span data-stu-id="dce5b-111">Next steps</span></span>](#next-steps) <br/> |[<span data-ttu-id="dce5b-112">开始利用</span><span class="sxs-lookup"><span data-stu-id="dce5b-112">Start utilizing</span></span>](utilization-activities-for-ocas.md) <br/> |
   
<span data-ttu-id="dce5b-p101">可以轻松地识别套将在 Office 365 云应用程序安全性，使用您实际办公室的 IP 地址，如的 IP 地址可以设置组的 IP 地址范围。定义这些范围允许标记和分类，然后您可以使用标记和自定义您的活动日志和通知的方式的类别显示和调查。</span><span class="sxs-lookup"><span data-stu-id="dce5b-p101">To easily identify sets of IP addresses that you'll use in Office 365 Cloud App Security, such as your physical office IP addresses, you can set up groups of IP address ranges. Defining these ranges lets you tag and categorize them, and then you can use tags and categories to customize how your activity logs and alerts are displayed and investigated.</span></span>
  
<span data-ttu-id="dce5b-p102">IP 范围的每个组可以标记与的选择，然后将标记可进行分类基于 IP 类别 （例如企业、 管理、 Risky 和 VPN） 的默认列表的标记名称中。支持 IPv4 和 IPv6 地址。</span><span class="sxs-lookup"><span data-stu-id="dce5b-p102">Each group of IP ranges can be tagged with tag names that you choose, and then the tags can be categorized based on a default list of IP categories (such as Corporate, Administrative, Risky, and VPN). Both IPv4 and IPv6 addresses are supported.</span></span>
  
> [!NOTE]
> <span data-ttu-id="dce5b-p103">您必须是全局管理员或安全管理员才能执行本文中的过程。若要了解详细信息，请参阅[Permissions in Office 365 安全性&amp;合规性中心](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="dce5b-p103">You must be a global administrator or security administrator to perform the procedures in this article. To learn more, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> 
  
## <a name="to-set-up-an-ip-address-range-in-office-365-cloud-app-security"></a><span data-ttu-id="dce5b-119">设置 Office 365 云应用程序安全性的 IP 地址范围</span><span class="sxs-lookup"><span data-stu-id="dce5b-119">To set up an IP address range in Office 365 Cloud App Security</span></span>

1. <span data-ttu-id="dce5b-p104">以全局管理员或 security 管理员程序中，转到[https://protection.office.com](https://protection.office.com)和使用工作或学校帐户登录。(您将转到安全&amp;合规性中心。)</span><span class="sxs-lookup"><span data-stu-id="dce5b-p104">As a global administrator or security administrator, go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account. (This takes you to the Security &amp; Compliance Center.)</span></span> 
    
2. <span data-ttu-id="dce5b-122">安全中&amp;合规性中心中，选择**警报** \> **管理高级通知**。</span><span class="sxs-lookup"><span data-stu-id="dce5b-122">In the Security &amp; Compliance Center, choose **Alerts** \> **Manage advanced alerts**.</span></span>
    
3. <span data-ttu-id="dce5b-123">选择**转到 Office 365 云应用程序安全性**。</span><span class="sxs-lookup"><span data-stu-id="dce5b-123">Choose **Go to Office 365 Cloud App Security**.</span></span>
    
    ![安全中&amp;合规性中心中，选择管理高级通知转到 Office 365 云应用程序安全性](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)
  
4. <span data-ttu-id="dce5b-125">在页面右上角右上角，单击**设置** \> **IP 地址范围**。</span><span class="sxs-lookup"><span data-stu-id="dce5b-125">On the upper right of the page, click **Settings** \> **IP address ranges**.</span></span>
    
    ![在 O365 云应用程序安全中，选择设置以访问您的系统和数据设置](media/f6c48ee3-39b4-4b5a-8252-b6493b7bcd3d.png)
  
5. <span data-ttu-id="dce5b-127">单击新建按钮，其类似于一个加号 ( **+**)。</span><span class="sxs-lookup"><span data-stu-id="dce5b-127">Click the new button, which resembles a plus sign ( **+**).</span></span>
    
6. <span data-ttu-id="dce5b-128">在**新的 IP 地址范围**窗口中，指定以下值：</span><span class="sxs-lookup"><span data-stu-id="dce5b-128">In the **New IP address range** window, specify the following values:</span></span> 
    
|<span data-ttu-id="dce5b-129">**字段或列表**</span><span class="sxs-lookup"><span data-stu-id="dce5b-129">**Field or list**</span></span>|<span data-ttu-id="dce5b-130">**需执行的操作**</span><span class="sxs-lookup"><span data-stu-id="dce5b-130">**What to do**</span></span>|
|:-----|:-----|
|<span data-ttu-id="dce5b-131">**名称**</span><span class="sxs-lookup"><span data-stu-id="dce5b-131">**Name**</span></span> <br/> |<span data-ttu-id="dce5b-p105">使用此字段来管理您的 IP 地址范围和设置。（您不会看到此活动日志中的值）。</span><span class="sxs-lookup"><span data-stu-id="dce5b-p105">Use this field to manage your IP address range and settings. (You won't see this value in activities logs.)</span></span>  <br/> |
|<span data-ttu-id="dce5b-134">**IP 地址范围**</span><span class="sxs-lookup"><span data-stu-id="dce5b-134">**IP address ranges**</span></span> <br/> |<span data-ttu-id="dce5b-p106">指定范围，使用网络前缀符号 （也称为 CIDR 格式表示）。例如，192.168.1.0/27 包括 192.168.1.0 通过 192.168.1.31 （含） 的值的范围。</span><span class="sxs-lookup"><span data-stu-id="dce5b-p106">Specify a range, using network prefix notation (also known as CIDR notation). For example, 192.168.1.0/27 includes the range of values 192.168.1.0 through 192.168.1.31 (inclusive).</span></span>  <br/> |
|<span data-ttu-id="dce5b-137">**位置**和**注册 ISP**</span><span class="sxs-lookup"><span data-stu-id="dce5b-137">**Location** and **Registered ISP**</span></span> <br/> |<span data-ttu-id="dce5b-p107">指定的 IP 地址范围的位置和 Internet 服务提供程序 (ISP)。这将覆盖公共字段定义地址，这很有帮助的情况下，如 IP 地址是的被视为公开在爱尔兰但实际上就是在美国</span><span class="sxs-lookup"><span data-stu-id="dce5b-p107">Specify the location and Internet Service Provider (ISP) for the IP address range. This overrides the public fields defined for the addresses, which is helpful for cases, such as an IP address is that is considered publicly to be in Ireland but is actually in the U.S.</span></span>  <br/> |
|<span data-ttu-id="dce5b-140">**Tags**</span><span class="sxs-lookup"><span data-stu-id="dce5b-140">**Tags**</span></span> <br/> |<span data-ttu-id="dce5b-p108">使用标记命名您的 IP 地址的组。（与不同的名称字段中，您将看到标记活动日志中。）键入的字词或短语的您想要使用的标记。您可以添加每个 IP 地址范围任意数量的标记。然后，如果您已设置了标记，并且想要向其中添加此 IP 地址范围，选择从列表中出现，在开始键入内容的当前标记。</span><span class="sxs-lookup"><span data-stu-id="dce5b-p108">Use tags to name your groups of IP addresses. (Unlike the Name field, you will see Tags in activity logs.) Type a word or phrase that you want to use for a tag. You can add as many tags as you like for each IP address range. And if you've already set up a tag and you want to add this IP address range to it, choose it from the list of current tags that appear as you start typing.</span></span>  <br/> |
|<span data-ttu-id="dce5b-145">**Category**</span><span class="sxs-lookup"><span data-stu-id="dce5b-145">**Category**</span></span> <br/> | <span data-ttu-id="dce5b-p109">为您的标记，以使其更易于识别来自特定 IP 地址的活动分配类别。选择以下选项：</span><span class="sxs-lookup"><span data-stu-id="dce5b-p109">Assign categories to your tags to make it easier to recognize activities that come from certain IP addresses. Choose from the following options:  </span></span><br/> <span data-ttu-id="dce5b-148">**管理**所有的 IP 地址的您的管理员。</span><span class="sxs-lookup"><span data-stu-id="dce5b-148">**Administrative** All of the IP addresses of your admins.</span></span>  <br/> <span data-ttu-id="dce5b-149">**云提供程序**您在云中的代理服务器的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="dce5b-149">**Cloud provider** The IP address of your proxy in the cloud.</span></span>  <br/> <span data-ttu-id="dce5b-150">**企业**所有 IP 地址在内部网络、 分支机构和您 Wi-fi 漫游地址。</span><span class="sxs-lookup"><span data-stu-id="dce5b-150">**Corporate** All of the IP addresses in your internal network, your branch offices, and your Wi-Fi roaming addresses.</span></span>  <br/> <span data-ttu-id="dce5b-p110">**Risky**考虑为 risky，如可疑的 IP 地址您任何 IP 地址已看到在过去，竞争对手网络中的 IP 地址等等。默认情况下，risky 类别包含两个 IP 标记：**匿名代理**，**或**</span><span class="sxs-lookup"><span data-stu-id="dce5b-p110">**Risky** Any IP addresses that you consider to be risky, such as suspicious IP addresses you've seen in the past, IP addresses in your competitors' networks, and so on. By default, the Risky categories includes two IP tags: **Anonymous proxy** and **Tor**</span></span> <br/> <span data-ttu-id="dce5b-153">**VPN**您的远程工作者使用任何 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="dce5b-153">**VPN** Any IP addresses that your remote workers use.</span></span>  <br/> |
   
7. <span data-ttu-id="dce5b-154">选择**保存**。</span><span class="sxs-lookup"><span data-stu-id="dce5b-154">Choose **Save**.</span></span>
    
<span data-ttu-id="dce5b-155">设置您的 IP 地址范围后，请注意，这些更改将影响仅未来事件。</span><span class="sxs-lookup"><span data-stu-id="dce5b-155">After you set up your IP address ranges, keep in mind that only future events are affected by these changes.</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="dce5b-156">后续步骤</span><span class="sxs-lookup"><span data-stu-id="dce5b-156">Next steps</span></span>

- [<span data-ttu-id="dce5b-157">活动策略和通知</span><span class="sxs-lookup"><span data-stu-id="dce5b-157">Activity policies and alerts</span></span>](activity-policies-and-alerts.md)
    
- [<span data-ttu-id="dce5b-158">异常检测策略</span><span class="sxs-lookup"><span data-stu-id="dce5b-158">Anomaly detection policies</span></span>](anomaly-detection-policies-in-ocas.md)
    
- [<span data-ttu-id="dce5b-159">将 SIEM 服务器集成</span><span class="sxs-lookup"><span data-stu-id="dce5b-159">Integrate your SIEM server</span></span>](integrate-your-siem-server-with-office-365-cas.md)
    
- [<span data-ttu-id="dce5b-160">查看 Office 365 云应用安全中的警报并执行相应操作</span><span class="sxs-lookup"><span data-stu-id="dce5b-160">Review and take action on alerts in Office 365 Cloud App Security</span></span>](review-office-365-cas-alerts.md)
    

