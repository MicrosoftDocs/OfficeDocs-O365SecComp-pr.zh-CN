---
title: 在 Microsoft 365 安全中监视和报告应用状态
description: 介绍如何能够深入了解组织中的云应用程序使用情况
keywords: security、恶意软件、Microsoft 365、M365、security center、monitor、report、apps
ms.prod: w10
ms.mktglfcycl: deploy
ms.localizationpriority: medium
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 02cc511532f65172aba2c0f98cdf594776f586a5
ms.sourcegitcommit: ef27da3ea5340d6e7a2eaa1288e2e005ef8e4788
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2019
ms.locfileid: "30791576"
---
# <a name="monitor-and-report-app-status-in-microsoft-365-security"></a><span data-ttu-id="51930-104">在 Microsoft 365 安全中监视和报告应用状态</span><span class="sxs-lookup"><span data-stu-id="51930-104">Monitor and report app status in Microsoft 365 security</span></span>

[!include[Prerelease�information](prerelease.md)]

<span data-ttu-id="51930-105">这些报告可更深入地了解如何在组织中使用云应用程序, 包括哪些类型的应用、风险级别和警报。</span><span class="sxs-lookup"><span data-stu-id="51930-105">These reports provide more insight into how cloud apps are being used in your organization, including what kinds of apps, their level of risk, and alerts.</span></span>

## <a name="monitor-email-accounts-at-risk"></a><span data-ttu-id="51930-106">监视电子邮件帐户的风险</span><span class="sxs-lookup"><span data-stu-id="51930-106">Monitor email accounts at risk</span></span>

<span data-ttu-id="51930-107">**电子邮件保护**显示有风险的电子邮件帐户。</span><span class="sxs-lookup"><span data-stu-id="51930-107">**Email protection** shows email accounts at risk.</span></span> <span data-ttu-id="51930-108">您可以单击某个帐户以在 Windows Defender 安全中心中进行进一步调查。</span><span class="sxs-lookup"><span data-stu-id="51930-108">You can click an account to investigate further in Windows Defender Security Center.</span></span>

![电子邮件保护卡](./media/security-docs/email-protection.png)

## <a name="monitor-app-permissions-granted-by-users"></a><span data-ttu-id="51930-110">监视用户授予的应用程序权限</span><span class="sxs-lookup"><span data-stu-id="51930-110">Monitor app permissions granted by users</span></span>

<span data-ttu-id="51930-111">**云应用安全-OAuth 应用**列出由用户授予权限的云应用安全发现的应用程序。</span><span class="sxs-lookup"><span data-stu-id="51930-111">**Cloud App Security - OAuth apps** lists apps discovered by Cloud App Security that have been granted permissions by users.</span></span> <span data-ttu-id="51930-112">云应用安全性风险目录包含16000个以上使用超过70个风险因素评估的应用程序。</span><span class="sxs-lookup"><span data-stu-id="51930-112">Cloud App Security's risk catalog includes over 16,000 apps that are assessed using over 70 risk factors.</span></span>

<span data-ttu-id="51930-113">风险因素从一般信息 (如应用程序发布者) 开始, 到安全措施和控件, 例如应用程序是否支持在 rest 上进行加密或提供用户活动的审核日志。</span><span class="sxs-lookup"><span data-stu-id="51930-113">The risk factors start from general information, such as the app publisher, to security measures and controls, such as whether the app supports for encryption at rest or provides an audit log of user activity.</span></span>

![云应用安全 OAuth 应用程序卡片](./media/security-docs/cloud-app-security-oauth-apps.png)

## <a name="monitor-cloud-app-user-accounts"></a><span data-ttu-id="51930-115">监视云应用程序用户帐户</span><span class="sxs-lookup"><span data-stu-id="51930-115">Monitor cloud app user accounts</span></span>

<span data-ttu-id="51930-116">**适用于审阅的云应用帐户**列表可能需要注意的帐户。</span><span class="sxs-lookup"><span data-stu-id="51930-116">**Cloud app accounts for review** lists accounts that may require attention.</span></span>

![审阅卡片的云应用程序帐户](./media/security-docs/cloud-app-accounts-for-review.png)

## <a name="understand-which-cloud-apps-are-used"></a><span data-ttu-id="51930-118">了解使用的是哪些云应用程序</span><span class="sxs-lookup"><span data-stu-id="51930-118">Understand which cloud apps are used</span></span>

<span data-ttu-id="51930-119">已**发现的云应用程序 (类别)** 显示在您的组织中使用的是哪些类型的应用程序, 以及云发现仪表板在云应用安全中的链接。</span><span class="sxs-lookup"><span data-stu-id="51930-119">**Discovered cloud apps (categories)** show what kinds of apps are being used in your organization and links to the Cloud Discovery dashboard in Cloud App Security.</span></span> <span data-ttu-id="51930-120">有关详细信息, 请参阅[快速入门: 使用已发现的应用](https://docs.microsoft.com/cloud-app-security/discovered-apps)。</span><span class="sxs-lookup"><span data-stu-id="51930-120">For more information, see [Quickstart: Work with discovered apps](https://docs.microsoft.com/cloud-app-security/discovered-apps).</span></span>  

![发现的云应用类别卡片](./media/security-docs/discovered-cloud-apps-categories.png)

## <a name="monitor-where-users-access-cloud-apps"></a><span data-ttu-id="51930-122">监视用户访问云应用程序的位置</span><span class="sxs-lookup"><span data-stu-id="51930-122">Monitor where users access cloud apps</span></span>

<span data-ttu-id="51930-123">**云应用活动位置**显示用户在访问云应用程序的位置。</span><span class="sxs-lookup"><span data-stu-id="51930-123">**Cloud app activity locations** show where users are accessing cloud apps.</span></span>

![云应用活动位置卡片](./media/security-docs/cloud-app-activity-locations.png)

## <a name="monitor-health-for-infrastructure-workloads"></a><span data-ttu-id="51930-125">监视基础架构工作负载的运行状况</span><span class="sxs-lookup"><span data-stu-id="51930-125">Monitor health for infrastructure workloads</span></span>

<span data-ttu-id="51930-126">**基础结构运行状况**在 Azure 安全中心中显示基础结构工作负荷的运行状况状态警报。</span><span class="sxs-lookup"><span data-stu-id="51930-126">**Infrastructure health** shows health status alerts for infrastructure workloads in Azure Security Center.</span></span>

<span data-ttu-id="51930-127">Azure 安全中心在内部部署和云工作负载中提供统一的安全管理和高级威胁保护。</span><span class="sxs-lookup"><span data-stu-id="51930-127">Azure Security Center provides unified security management and advanced threat protection across on-premises and cloud workloads.</span></span> <span data-ttu-id="51930-128">您可以从各种源 (包括防火墙和其他合作伙伴解决方案) 收集、搜索和分析安全数据。</span><span class="sxs-lookup"><span data-stu-id="51930-128">You can collect, search, and analyze security data from a variety of sources, including firewalls and other partner solutions.</span></span>

<span data-ttu-id="51930-129">有关详细信息, 请参阅[Azure 安全中心文档](https://docs.microsoft.com/azure/security-center/)。</span><span class="sxs-lookup"><span data-stu-id="51930-129">For more information, see [Azure Security Center Documentation](https://docs.microsoft.com/azure/security-center/).</span></span>

![基础结构运行状况卡片](./media/security-docs/infrastructure-health.png)
