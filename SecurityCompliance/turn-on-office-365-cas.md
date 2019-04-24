---
title: 启用 Office 365 云应用安全
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
ms.assetid: ba919c73-d021-404d-9850-eec57e78678c
description: 阅读本文, 了解如何在 Microsoft Azure 中启用 Office 365 云应用安全性 (受云应用安全性的支持)。
ms.openlocfilehash: 1227545b1e4d1521dc1820342f09aabdf16ec2c6
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32264124"
---
# <a name="turn-on-office-365-cloud-app-security"></a><span data-ttu-id="2c408-103">启用 Office 365 云应用安全</span><span class="sxs-lookup"><span data-stu-id="2c408-103">Turn on Office 365 Cloud App Security</span></span>
  
|<span data-ttu-id="2c408-104">评估 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="2c408-104">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="2c408-105">规划 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="2c408-105">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="2c408-106">部署 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="2c408-106">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="2c408-107">利用率 \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="2c408-107">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="2c408-108">开始评估</span><span class="sxs-lookup"><span data-stu-id="2c408-108">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="2c408-109">开始规划</span><span class="sxs-lookup"><span data-stu-id="2c408-109">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |<span data-ttu-id="2c408-110">你在这里!</span><span class="sxs-lookup"><span data-stu-id="2c408-110">You are here!</span></span>  <br/> [<span data-ttu-id="2c408-111">后续步骤</span><span class="sxs-lookup"><span data-stu-id="2c408-111">Next step</span></span>](activity-policies-and-alerts.md) <br/> |[<span data-ttu-id="2c408-112">开始利用</span><span class="sxs-lookup"><span data-stu-id="2c408-112">Start utilizing</span></span>](utilization-activities-for-ocas.md) <br/> |
  
## <a name="turn-on-office-365-cloud-app-security"></a><span data-ttu-id="2c408-113">启用 Office 365 云应用安全</span><span class="sxs-lookup"><span data-stu-id="2c408-113">Turn on Office 365 Cloud App Security</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2c408-114">您必须是全局管理员或安全管理员才能执行以下任务。</span><span class="sxs-lookup"><span data-stu-id="2c408-114">You must be a global administrator or security administrator to perform the following task.</span></span> <span data-ttu-id="2c408-115">若要了解详细信息, 请参阅[Office 365 安全&amp;合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="2c408-115">To learn more, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> <span data-ttu-id="2c408-116">为了使 office 365 云应用安全正常工作, 必须为你的 Office 365 环境**启用审核日志记录**。</span><span class="sxs-lookup"><span data-stu-id="2c408-116">In order for Office 365 Cloud App Security to work correct, **audit logging must be turned on** for your Office 365 environment.</span></span> <span data-ttu-id="2c408-117">有关详细信息, 请参阅[打开或关闭 Office 365 审核日志搜索](turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="2c408-117">For more information, see [Turn Office 365 audit log search on or off](turn-audit-log-search-on-or-off.md).</span></span> 
  
1. <span data-ttu-id="2c408-118">作为全局管理员或安全管理员, 请转到[https://protection.office.com](https://security.microsoft.com)并使用 Office 365 的工作或学校帐户登录并登录。</span><span class="sxs-lookup"><span data-stu-id="2c408-118">As a global administrator or security administrator, go to [https://protection.office.com](https://security.microsoft.com) and sign in using your work or school account for Office 365.</span></span> <span data-ttu-id="2c408-119">(这会将您带到&amp;安全合规中心。)</span><span class="sxs-lookup"><span data-stu-id="2c408-119">(This takes you to the Security &amp; Compliance Center.)</span></span> 
    
2. <span data-ttu-id="2c408-120">转到 "**通知** \> " "**管理高级警报**"。</span><span class="sxs-lookup"><span data-stu-id="2c408-120">Go to **Alerts** \> **Manage advanced alerts**.</span></span>
    
3. <span data-ttu-id="2c408-121">选择 **"启用 Office 365 云应用安全"**。</span><span class="sxs-lookup"><span data-stu-id="2c408-121">Select **Turn on Office 365 Cloud App Security**.</span></span>
    
4. <span data-ttu-id="2c408-122">选择 "**转到 Office 365 云应用安全性**"。</span><span class="sxs-lookup"><span data-stu-id="2c408-122">Choose **Go to Office 365 Cloud App Security**.</span></span><br/><span data-ttu-id="2c408-123">![在 "安全&amp;合规性中心" 中, 选择 "管理高级警报" 以转到 Office 365 云应用安全](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)</span><span class="sxs-lookup"><span data-stu-id="2c408-123">![In the Security &amp; Compliance Center, choose Manage Advanced Alerts to go to Office 365 Cloud App Security](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)</span></span><br/><span data-ttu-id="2c408-124">这将转到 Office 365 云应用安全门户, 在其中可以查看报告以及创建或编辑策略。</span><span class="sxs-lookup"><span data-stu-id="2c408-124">This takes you to the Office 365 Cloud App Security portal, where you can view reports and create or edit your policies.</span></span>

<span data-ttu-id="2c408-125">在您启用 Office 365 云应用安全性之后, 可以通过访问[https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)并登录来转到云应用安全门户。</span><span class="sxs-lookup"><span data-stu-id="2c408-125">After you have turned on Office 365 Cloud App Security, you can go to the Cloud App Security portal by visiting [https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com) and signing in.</span></span>
    
> [!NOTE]
> <span data-ttu-id="2c408-126">打开 office 365 云应用安全性时, 将会将有关 Office 365 用户帐户和用户活动的审核信息转移到[Microsoft 云应用安全性](https://aka.ms/whatiscas)。</span><span class="sxs-lookup"><span data-stu-id="2c408-126">When you turn on Office 365 Cloud App Security, auditing information about your Office 365 user accounts and user activities is transferred to [Microsoft Cloud App Security](https://aka.ms/whatiscas).</span></span> <span data-ttu-id="2c408-127">这将允许 Office 365 提供高级警报、筛选和其他功能, 以便你可以获取信息并采取有关可疑活动的操作。</span><span class="sxs-lookup"><span data-stu-id="2c408-127">This allows Office 365 to provide advanced alerts, filtering, and other features so you can get information and take action about suspicious activities.</span></span> 
  
## <a name="next-steps"></a><span data-ttu-id="2c408-128">后续步骤</span><span class="sxs-lookup"><span data-stu-id="2c408-128">Next steps</span></span>

- [<span data-ttu-id="2c408-129">活动策略</span><span class="sxs-lookup"><span data-stu-id="2c408-129">Activity policies</span></span>](activity-policies-and-alerts.md)
    
- [<span data-ttu-id="2c408-130">异常情况检测策略</span><span class="sxs-lookup"><span data-stu-id="2c408-130">Anomaly detection policies</span></span>](anomaly-detection-policies-in-ocas.md)
    
- [<span data-ttu-id="2c408-131">集成您的 SIEM 服务器</span><span class="sxs-lookup"><span data-stu-id="2c408-131">Integrate your SIEM server</span></span>](integrate-your-siem-server-with-office-365-cas.md)
    
- [<span data-ttu-id="2c408-132">将 IP 地址分组以简化管理</span><span class="sxs-lookup"><span data-stu-id="2c408-132">Group your IP addresses to simplify management</span></span>](group-your-ip-addresses-in-ocas.md)
    

