---
title: 保护对 Office 365 数据和服务的访问
ms.author: chrfox
author: chrfox
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
ms.openlocfilehash: 95933c5a7bc95f9fd70e8f3470055b57193971d4
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30213532"
---
# <a name="protect-access-to-data-and-services-in-office-365"></a><span data-ttu-id="dc2aa-103">保护对 Office 365 数据和服务的访问</span><span class="sxs-lookup"><span data-stu-id="dc2aa-103">Protect access to data and services in Office 365</span></span>

<span data-ttu-id="dc2aa-p101">保护对 Office 365 数据和服务的访问对于防御网络攻击和防止数据丢失至关重要。可以将相同的保护应用于环境中的其他 SaaS 应用程序, 甚至应用于使用 Azure Active Directory 应用程序代理发布的本地应用程序。</span><span class="sxs-lookup"><span data-stu-id="dc2aa-p101">Protecting access to your Office 365 data and services is crucial to defending against cyber-attacks and guarding against data loss. The same protections can be applied to other SaaS applications in your environment and even to on-premises applications published with Azure Active Directory Application Proxy.</span></span>
  
## <a name="step-1-review-recommendations"></a><span data-ttu-id="dc2aa-106">步骤 1: 查看建议</span><span class="sxs-lookup"><span data-stu-id="dc2aa-106">Step 1: Review recommendations</span></span>

<span data-ttu-id="dc2aa-107">用于保护访问 Office 365 设备、其他 SaaS 服务以及使用 Azure AD 应用代理发布的本地应用的标识和设备的推荐功能。</span><span class="sxs-lookup"><span data-stu-id="dc2aa-107">Recommended capabilities for protecting identities and devices that access Office 365, other SaaS services, and on-premises applications published with Azure AD Application Proxy.</span></span>
  
<span data-ttu-id="dc2aa-108">[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [更多语言](https://www.microsoft.com/download/details.aspx?id=55032)</span><span class="sxs-lookup"><span data-stu-id="dc2aa-108">[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [More languages](https://www.microsoft.com/download/details.aspx?id=55032)</span></span>
  
## <a name="step-2-configure-mfa"></a><span data-ttu-id="dc2aa-109">步骤 2: 配置 MFA</span><span class="sxs-lookup"><span data-stu-id="dc2aa-109">Step 2: Configure MFA</span></span>

<span data-ttu-id="dc2aa-110">使用这些资源向自己定位 MFA, 决定哪种版本适合您, 然后为您的环境规划和部署 MFA。</span><span class="sxs-lookup"><span data-stu-id="dc2aa-110">Use these resources to orient yourself to MFA, decide which version is right for you, and then plan and deploy MFA for your environment.</span></span>
  
- [<span data-ttu-id="dc2aa-111">什么是 Azure 多因素身份验证？</span><span class="sxs-lookup"><span data-stu-id="dc2aa-111">What is Azure multi-factor authentication?</span></span>](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication)
    
- [<span data-ttu-id="dc2aa-112">为你选择 Azure 多因素身份验证解决方案</span><span class="sxs-lookup"><span data-stu-id="dc2aa-112">Choose the Azure multi-factor authentication solution for you</span></span>](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-get-started)
    
- [<span data-ttu-id="dc2aa-113">如何获取 Azure 多因素身份验证</span><span class="sxs-lookup"><span data-stu-id="dc2aa-113">How to get Azure multi-factor authentication</span></span>](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-versions-plans)
    
- [<span data-ttu-id="dc2aa-114">规划 Office 365 部署的多因素身份验证</span><span class="sxs-lookup"><span data-stu-id="dc2aa-114">Plan for multi-factor authentication for Office 365 deployments</span></span>](https://support.office.com/article/043807b2-21db-4d5c-b430-c8a6dee0e6ba)
    
- [<span data-ttu-id="dc2aa-115">为 Office 365 用户设置多重身份验证</span><span class="sxs-lookup"><span data-stu-id="dc2aa-115">Set up multi-factor authentication for Office 365 users</span></span>](https://support.office.com/article/8f0454b2-f51a-4d9c-bcde-2c48e41621c6)
    
- [<span data-ttu-id="dc2aa-116">规划部署 MFA、云或本地的位置</span><span class="sxs-lookup"><span data-stu-id="dc2aa-116">Plan where to deploy MFA, Cloud or on-premises</span></span>](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-get-started)
    
- [<span data-ttu-id="dc2aa-117">配置 Azure 多重身份验证设置</span><span class="sxs-lookup"><span data-stu-id="dc2aa-117">Configure Azure multi-factor authentication settings</span></span>](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-whats-next)
    
## <a name="step-3-enforce-mfa-with-azure-ad-conditional-access-rules"></a><span data-ttu-id="dc2aa-118">步骤 3: 强制与 Azure AD 条件访问规则进行 MFA</span><span class="sxs-lookup"><span data-stu-id="dc2aa-118">Step 3: Enforce MFA with Azure AD conditional access rules</span></span>

<span data-ttu-id="dc2aa-119">如果使用的是 Azure AD MFA, 请创建条件访问规则, 以要求对环境中的 Office 365 和其他 SaaS 应用程序的访问进行 MFA。</span><span class="sxs-lookup"><span data-stu-id="dc2aa-119">If you are using Azure AD MFA, create a conditional access rule to require MFA for access to Office 365 and other SaaS apps in your environment.</span></span>
  
- [<span data-ttu-id="dc2aa-120">Azure Active Directory 中的条件访问</span><span class="sxs-lookup"><span data-stu-id="dc2aa-120">Conditional access in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal)
    
## <a name="step-4-configure-privileged-access-management"></a><span data-ttu-id="dc2aa-121">步骤 4: 配置特权访问管理</span><span class="sxs-lookup"><span data-stu-id="dc2aa-121">Step 4: Configure privileged access management</span></span>

<span data-ttu-id="dc2aa-p102">特权访问管理允许对 Office 365 中的特权管理任务进行精确的访问控制。 它可以帮助保护您的组织免受可能使用现有特权管理员帐户访问敏感数据或访问关键配置设置的访问的危害。</span><span class="sxs-lookup"><span data-stu-id="dc2aa-p102">Privileged access management allows granular access control over privileged admin tasks in Office 365.  It can help protect your organization from breaches that may use existing privileged admin accounts with standing access to sensitive data or access to critical configuration settings.</span></span>

- [<span data-ttu-id="dc2aa-124">特权访问管理概述</span><span class="sxs-lookup"><span data-stu-id="dc2aa-124">Overview of privileged access management</span></span>](privileged-access-management-overview.md)
- [<span data-ttu-id="dc2aa-125">配置特权访问管理</span><span class="sxs-lookup"><span data-stu-id="dc2aa-125">Configure privileged access management</span></span>](privileged-access-management-configuration.md)

## <a name="step-5-configure-sharepoint-device-access-policies"></a><span data-ttu-id="dc2aa-126">步骤 5: 配置 SharePoint 设备访问策略</span><span class="sxs-lookup"><span data-stu-id="dc2aa-126">Step 5: Configure SharePoint device access policies</span></span>

<span data-ttu-id="dc2aa-p103">建议使用适用于 SharePoint Online 和 OneDrive for business 的设备访问策略来保护敏感、分类和受管制的数据。即将推出将设备访问策略应用于各个团队网站的功能。</span><span class="sxs-lookup"><span data-stu-id="dc2aa-p103">Device access policies for SharePoint Online and OneDrive for Business are recommended for protecting sensitive, classified, and regulated data. Coming soon is the ability to apply device access policies to individual team sites.</span></span>
  
- [<span data-ttu-id="dc2aa-129">通过非托管设备控制访问</span><span class="sxs-lookup"><span data-stu-id="dc2aa-129">Control access from unmanaged devices</span></span>](https://support.office.com/article/Control-access-from-unmanaged-devices-5ae550c4-bd20-4257-847b-5c20fb053622?ui=en-US&amp;rs=en-US&amp;ad=US)
    
## <a name="step-6-configure-app-and-data-protection-for-devices"></a><span data-ttu-id="dc2aa-130">步骤 6: 配置设备的应用程序和数据保护</span><span class="sxs-lookup"><span data-stu-id="dc2aa-130">Step 6: Configure app and data protection for devices</span></span>

<span data-ttu-id="dc2aa-p104">您可以管理移动设备上的应用程序, 而无需考虑是否为移动设备管理注册了设备。这样可以防止 Office 365 中数据的意外泄露 (包括邮件和文件)。</span><span class="sxs-lookup"><span data-stu-id="dc2aa-p104">You can manage applications on mobile devices regardless of whether the devices are enrolled for mobile device management. This protects against accidental leakage of data in Office 365, including mail and files.</span></span>
  
- <span data-ttu-id="dc2aa-133">对于 iOS 和 Android:[使用 Microsoft Intune 的应用保护策略保护应用数据](https://docs.microsoft.com/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune)</span><span class="sxs-lookup"><span data-stu-id="dc2aa-133">For iOS and Android: [Protect app data using app protection policies with Microsoft Intune](https://docs.microsoft.com/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune)</span></span>
    
<span data-ttu-id="dc2aa-134">对于 windows 10, 请配置 windows 信息保护 (WIP) 以防止意外的数据泄露。</span><span class="sxs-lookup"><span data-stu-id="dc2aa-134">For Windows 10, configure Windows Information Protection (WIP) to prevent accidental data leaks.</span></span>
  
- <span data-ttu-id="dc2aa-135">对于托管设备:[使用 Microsoft Intune 的 Azure 门户创建带有注册策略的 Windows 信息保护 (WIP)](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/create-wip-policy-using-intune-azure)</span><span class="sxs-lookup"><span data-stu-id="dc2aa-135">For managed devices: [Create a Windows Information Protection (WIP) with enrollment policy using the Azure portal for Microsoft Intune](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/create-wip-policy-using-intune-azure)</span></span>
    
- <span data-ttu-id="dc2aa-136">对于未管理的设备:[使用 Intune 创建和部署 Windows 信息保护 (WIP) 应用保护策略](https://docs.microsoft.com/intune/windows-information-protection-policy-create)</span><span class="sxs-lookup"><span data-stu-id="dc2aa-136">For un-managed devices: [Create and deploy Windows Information Protection (WIP) app protection policy with Intune](https://docs.microsoft.com/intune/windows-information-protection-policy-create)</span></span>
    
## <a name="step-7-manage-devices-with-intune"></a><span data-ttu-id="dc2aa-137">步骤 7: 使用 Intune 管理设备</span><span class="sxs-lookup"><span data-stu-id="dc2aa-137">Step 7: Manage devices with Intune</span></span>

<span data-ttu-id="dc2aa-p105">管理设备使您能够在允许用户访问您的环境中的资源之前确保它们的健康和合规性。基于设备的条件访问规则有助于确保攻击者无法从非托管设备获取对资源的访问权限。</span><span class="sxs-lookup"><span data-stu-id="dc2aa-p105">Managing devices allows you to ensure that they are healthy and compliant before allowing them access to resources in your environment. Device based conditional access rules help ensure attackers can't gain access to your resources from unmanaged devices.</span></span>
  
- [<span data-ttu-id="dc2aa-140">在 Intune 中注册设备以进行管理</span><span class="sxs-lookup"><span data-stu-id="dc2aa-140">Enroll devices for management in Intune</span></span>](https://docs.microsoft.com/intune-classic/deploy-use/enroll-devices-in-microsoft-intune)
    
## <a name="step-8-configure-additional-intune-policies-and-conditional-access-rules-for-your-environment"></a><span data-ttu-id="dc2aa-141">步骤 8: 为环境配置其他 Intune 策略和条件访问规则</span><span class="sxs-lookup"><span data-stu-id="dc2aa-141">Step 8: Configure additional Intune policies and conditional access rules for your environment</span></span>

<span data-ttu-id="dc2aa-142">使用这些建议的配置作为企业级扩展或完善的访问安全方案的起点。</span><span class="sxs-lookup"><span data-stu-id="dc2aa-142">Use these recommended configurations as a starting point for enterprise scale or sophisticated access security scenarios.</span></span>
  
- [<span data-ttu-id="dc2aa-143">安全电子邮件策略和配置</span><span class="sxs-lookup"><span data-stu-id="dc2aa-143">Secure email policies and configurations</span></span>](https://docs.microsoft.com/azure/active-directory/secure-email-introduction)
    

