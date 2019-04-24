---
title: 保护用户和设备访问
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 4/17/2018
ms.audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a6ef28a4-2447-4b43-aae2-f5af6d53c68e
description: 用于保护对 O365 数据和服务的访问权限的登录页
ms.openlocfilehash: e1b529a641d25f82521c40d0df9d091e0ebb5d90
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32265224"
---
# <a name="protect-user-and-device-access"></a><span data-ttu-id="5ae14-103">保护用户和设备访问</span><span class="sxs-lookup"><span data-stu-id="5ae14-103">Protect user and device access</span></span>

<span data-ttu-id="5ae14-104">保护对 Office 365 数据和服务的访问对于防御网络攻击和防止数据丢失至关重要。</span><span class="sxs-lookup"><span data-stu-id="5ae14-104">Protecting access to your Office 365 data and services is crucial to defending against cyber-attacks and guarding against data loss.</span></span> <span data-ttu-id="5ae14-105">可以将相同的保护应用于环境中的其他 SaaS 应用程序, 甚至应用于使用 Azure Active Directory 应用程序代理发布的本地应用程序。</span><span class="sxs-lookup"><span data-stu-id="5ae14-105">The same protections can be applied to other SaaS applications in your environment and even to on-premises applications published with Azure Active Directory Application Proxy.</span></span>
  
## <a name="step-1-review-recommendations"></a><span data-ttu-id="5ae14-106">步骤 1: 查看建议</span><span class="sxs-lookup"><span data-stu-id="5ae14-106">Step 1: Review recommendations</span></span>

<span data-ttu-id="5ae14-107">用于保护访问 Office 365 设备、其他 SaaS 服务以及使用 Azure AD 应用代理发布的本地应用的标识和设备的推荐功能。</span><span class="sxs-lookup"><span data-stu-id="5ae14-107">Recommended capabilities for protecting identities and devices that access Office 365, other SaaS services, and on-premises applications published with Azure AD Application Proxy.</span></span>
  
<span data-ttu-id="5ae14-108">[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [更多语言](https://www.microsoft.com/download/details.aspx?id=55032)</span><span class="sxs-lookup"><span data-stu-id="5ae14-108">[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [More languages](https://www.microsoft.com/download/details.aspx?id=55032)</span></span>
  
## <a name="step-2-protect-administrator-accounts-and-access"></a><span data-ttu-id="5ae14-109">步骤 2: 保护管理员帐户和访问权限</span><span class="sxs-lookup"><span data-stu-id="5ae14-109">Step 2: Protect administrator accounts and access</span></span>
<span data-ttu-id="5ae14-110">用于管理 Office 365 环境的管理帐户包括提升的权限。</span><span class="sxs-lookup"><span data-stu-id="5ae14-110">The administrative accounts you use to administer your Office 365 environment include elevated privileges.</span></span> <span data-ttu-id="5ae14-111">这些是黑客和网络罪犯的有用目标。</span><span class="sxs-lookup"><span data-stu-id="5ae14-111">These are valuable targets for hackers and cyber criminals.</span></span> 

<span data-ttu-id="5ae14-112">首先使用管理员帐户进行管理。</span><span class="sxs-lookup"><span data-stu-id="5ae14-112">Begin by using administrator accounts only for administration.</span></span> <span data-ttu-id="5ae14-113">管理员应使用单独的用户帐户进行常规的非管理, 并且仅在必要时才使用其管理帐户完成与工作职能相关联的任务。</span><span class="sxs-lookup"><span data-stu-id="5ae14-113">Admins should have a separate user account for regular, non-administrative use and only use their administrative account when necessary to complete a task associated with their job function.</span></span>

<span data-ttu-id="5ae14-114">使用多重身份验证和条件访问来保护您的管理员帐户。</span><span class="sxs-lookup"><span data-stu-id="5ae14-114">Protect your administrator accounts with multi-factor authentication and conditional access.</span></span> <span data-ttu-id="5ae14-115">有关详细信息, 请参阅[保护管理员帐户](https://docs.microsoft.com/en-us/microsoft-365/enterprise/identity-access-prerequisites#protecting-administrator-accounts)。</span><span class="sxs-lookup"><span data-stu-id="5ae14-115">For more information, see [Protecting administrator accounts](https://docs.microsoft.com/en-us/microsoft-365/enterprise/identity-access-prerequisites#protecting-administrator-accounts).</span></span> 

<span data-ttu-id="5ae14-116">接下来, 在 Office 365 中配置特权访问管理。</span><span class="sxs-lookup"><span data-stu-id="5ae14-116">Next, configure privileged access management in Office 365.</span></span> <span data-ttu-id="5ae14-117">特权访问管理允许对 Office 365 中的特权管理任务进行精确的访问控制。</span><span class="sxs-lookup"><span data-stu-id="5ae14-117">Privileged access management allows granular access control over privileged admin tasks in Office 365.</span></span> <span data-ttu-id="5ae14-118">它可以帮助保护您的组织免受可能使用现有特权管理员帐户访问敏感数据或访问关键配置设置的访问的危害。</span><span class="sxs-lookup"><span data-stu-id="5ae14-118">It can help protect your organization from breaches that may use existing privileged admin accounts with standing access to sensitive data or access to critical configuration settings.</span></span>

- [<span data-ttu-id="5ae14-119">特权访问管理概述</span><span class="sxs-lookup"><span data-stu-id="5ae14-119">Overview of privileged access management</span></span>](privileged-access-management-overview.md)
- [<span data-ttu-id="5ae14-120">配置特权访问管理</span><span class="sxs-lookup"><span data-stu-id="5ae14-120">Configure privileged access management</span></span>](privileged-access-management-configuration.md)

<span data-ttu-id="5ae14-121">另一个主要建议是使用专为管理工作配置的工作站。</span><span class="sxs-lookup"><span data-stu-id="5ae14-121">Another top recommendation is to use workstations specifically configured for administrative work.</span></span> <span data-ttu-id="5ae14-122">这些是仅用于管理任务的专用设备。</span><span class="sxs-lookup"><span data-stu-id="5ae14-122">These are dedicated devices that are only used for administrative tasks.</span></span> <span data-ttu-id="5ae14-123">请参阅[保护特权访问](https://docs.microsoft.com/en-us/windows-server/identity/securing-privileged-access/securing-privileged-access)。</span><span class="sxs-lookup"><span data-stu-id="5ae14-123">See [Securing privileged access](https://docs.microsoft.com/en-us/windows-server/identity/securing-privileged-access/securing-privileged-access).</span></span>

<span data-ttu-id="5ae14-124">最后, 您可以通过在租户中创建两个或多个紧急访问帐户来缓解无意中缺少管理访问权限造成的影响。</span><span class="sxs-lookup"><span data-stu-id="5ae14-124">Finally, you can mitigate the impact of inadvertent lack of administrative access by creating two or more emergency access accounts in your tenant.</span></span> <span data-ttu-id="5ae14-125">请参阅[管理 Azure AD 中的紧急访问帐户](https://docs.microsoft.com/en-us/azure/active-directory/users-groups-roles/directory-emergency-access)。</span><span class="sxs-lookup"><span data-stu-id="5ae14-125">See [Manage emergency access accounts in Azure AD](https://docs.microsoft.com/en-us/azure/active-directory/users-groups-roles/directory-emergency-access).</span></span> 

## <a name="step-3-configure-recommended-identity-and-device-access-policies"></a><span data-ttu-id="5ae14-126">步骤 3: 配置推荐的标识和设备访问策略</span><span class="sxs-lookup"><span data-stu-id="5ae14-126">Step 3: Configure recommended identity and device access policies</span></span>
<span data-ttu-id="5ae14-127">多重身份验证 (MFA) 和条件访问策略是功能强大的工具, 可缓解受到损坏的帐户和未经授权的访问。</span><span class="sxs-lookup"><span data-stu-id="5ae14-127">Multi-factor authentication (MFA) and conditional access policies are powerful tools for mitigating against compromised accounts and unauthorized access.</span></span> <span data-ttu-id="5ae14-128">我们建议实现一组已经过测试的策略。</span><span class="sxs-lookup"><span data-stu-id="5ae14-128">We recommend implementing a set of policies that have been tested together.</span></span> <span data-ttu-id="5ae14-129">有关详细信息 (包括部署步骤), 请参阅[Identity and device access 配置](https://docs.microsoft.com/en-us/microsoft-365/enterprise/microsoft-365-policies-configurations)。</span><span class="sxs-lookup"><span data-stu-id="5ae14-129">For more information, including deployment steps, see [Identity and device access configurations](https://docs.microsoft.com/en-us/microsoft-365/enterprise/microsoft-365-policies-configurations).</span></span>

 <span data-ttu-id="5ae14-130">这些策略实现以下功能:</span><span class="sxs-lookup"><span data-stu-id="5ae14-130">These policies implement the following capabilities:</span></span>
- <span data-ttu-id="5ae14-131">多身份验证</span><span class="sxs-lookup"><span data-stu-id="5ae14-131">Mult-factor authentication</span></span>
- <span data-ttu-id="5ae14-132">条件访问</span><span class="sxs-lookup"><span data-stu-id="5ae14-132">Conditional access</span></span>
- <span data-ttu-id="5ae14-133">Intune 应用保护 (设备的应用程序和数据保护)</span><span class="sxs-lookup"><span data-stu-id="5ae14-133">Intune app protection (app and data protection for devices)</span></span>
- <span data-ttu-id="5ae14-134">Intune 设备合规性</span><span class="sxs-lookup"><span data-stu-id="5ae14-134">Intune device compliance</span></span>
- <span data-ttu-id="5ae14-135">Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="5ae14-135">Azure AD Identity Protection</span></span>

<span data-ttu-id="5ae14-136">Implemetning Intune 设备合规性需要设备注册。</span><span class="sxs-lookup"><span data-stu-id="5ae14-136">Implemetning Intune device compliance requires device enrollment.</span></span> <span data-ttu-id="5ae14-137">管理设备使您能够在允许用户访问您的环境中的资源之前确保它们的健康和合规性。</span><span class="sxs-lookup"><span data-stu-id="5ae14-137">Managing devices allows you to ensure that they are healthy and compliant before allowing them access to resources in your environment.</span></span> <span data-ttu-id="5ae14-138">请参阅[在 Intune 中注册设备以进行管理](https://docs.microsoft.com/intune-classic/deploy-use/enroll-devices-in-microsoft-intune)</span><span class="sxs-lookup"><span data-stu-id="5ae14-138">See [Enroll devices for management in Intune](https://docs.microsoft.com/intune-classic/deploy-use/enroll-devices-in-microsoft-intune)</span></span>

## <a name="step-4-configure-sharepoint-device-access-policies"></a><span data-ttu-id="5ae14-139">步骤 4: 配置 SharePoint 设备访问策略</span><span class="sxs-lookup"><span data-stu-id="5ae14-139">Step 4: Configure SharePoint device access policies</span></span>

<span data-ttu-id="5ae14-140">Microsoft 建议使用设备访问控制保护 SharePoint 网站中的内容与敏感和高度管控的内容。</span><span class="sxs-lookup"><span data-stu-id="5ae14-140">Microsoft recommends you protect content in SharePoint sites with sensitive and highly-regulated content with device access controls.</span></span> <span data-ttu-id="5ae14-141">有关详细信息, 请参阅[保护 SharePoint 网站和文件的策略建议](https://docs.microsoft.com/en-us/microsoft-365/enterprise/sharepoint-file-access-policies)。</span><span class="sxs-lookup"><span data-stu-id="5ae14-141">For more information, see [Policy recommendations for securing SharePoint sites and files](https://docs.microsoft.com/en-us/microsoft-365/enterprise/sharepoint-file-access-policies).</span></span>



    

