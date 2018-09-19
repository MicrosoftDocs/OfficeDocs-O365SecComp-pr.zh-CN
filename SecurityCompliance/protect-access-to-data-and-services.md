---
title: 保护对 Office 365 数据和服务的访问
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 4/17/2018
ms.audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a6ef28a4-2447-4b43-aae2-f5af6d53c68e
description: 用于保护访问 O365 数据和服务的登录页
ms.openlocfilehash: 6ea617b1a7a7a34492689908d4816a851d58e776
ms.sourcegitcommit: 0ce722533d72fa8dcc1d8a58d3c649cb345b938d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/19/2018
ms.locfileid: "24009098"
---
# <a name="protect-access-to-data-and-services-in-office-365"></a><span data-ttu-id="fad25-103">保护对 Office 365 数据和服务的访问</span><span class="sxs-lookup"><span data-stu-id="fad25-103">Protect access to data and services in Office 365</span></span>

<span data-ttu-id="fad25-p101">保护访问您的 Office 365 数据和服务是至关重要辩护网络攻击和防止数据丢失。相同的保护可以应用于您的环境中其他 saas 与应用程序和偶数的本地应用程序发布与 Azure Active Directory 应用程序代理。</span><span class="sxs-lookup"><span data-stu-id="fad25-p101">Protecting access to your Office 365 data and services is crucial to defending against cyber-attacks and guarding against data loss. The same protections can be applied to other SaaS applications in your environment and even to on-premises applications published with Azure Active Directory Application Proxy.</span></span>
  
## <a name="step-1-review-recommendations"></a><span data-ttu-id="fad25-106">步骤 1： 审核相关建议</span><span class="sxs-lookup"><span data-stu-id="fad25-106">Step 1: Review recommendations</span></span>

<span data-ttu-id="fad25-107">用于保护访问 Office 365 设备、其他 SaaS 服务以及使用 Azure AD 应用代理发布的本地应用的标识和设备的推荐功能。</span><span class="sxs-lookup"><span data-stu-id="fad25-107">Recommended capabilities for protecting identities and devices that access Office 365, other SaaS services, and on-premises applications published with Azure AD Application Proxy.</span></span>
  
<span data-ttu-id="fad25-108">[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [更多语言](https://www.microsoft.com/download/details.aspx?id=55032)</span><span class="sxs-lookup"><span data-stu-id="fad25-108">[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [More languages](https://www.microsoft.com/download/details.aspx?id=55032)</span></span>
  
## <a name="step-2-configure-mfa"></a><span data-ttu-id="fad25-109">步骤 2： 配置 MFA</span><span class="sxs-lookup"><span data-stu-id="fad25-109">Step 2: Configure MFA</span></span>

<span data-ttu-id="fad25-110">使用这些资源自己定向到 MFA，确定哪个版本适合您，然后规划和部署和 MFA 您的环境。</span><span class="sxs-lookup"><span data-stu-id="fad25-110">Use these resources to orient yourself to MFA, decide which version is right for you, and then plan and deploy MFA for your environment.</span></span>
  
- [<span data-ttu-id="fad25-111">Azure 多因素身份验证是什么？</span><span class="sxs-lookup"><span data-stu-id="fad25-111">What is Azure multi-factor authentication?</span></span>](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication)
    
- [<span data-ttu-id="fad25-112">为您选择的 Azure 多因素身份验证解决方案</span><span class="sxs-lookup"><span data-stu-id="fad25-112">Choose the Azure multi-factor authentication solution for you</span></span>](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-get-started)
    
- [<span data-ttu-id="fad25-113">如何获取 Azure 多因素身份验证</span><span class="sxs-lookup"><span data-stu-id="fad25-113">How to get Azure multi-factor authentication</span></span>](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-versions-plans)
    
- [<span data-ttu-id="fad25-114">规划多因素身份验证的 Office 365 部署</span><span class="sxs-lookup"><span data-stu-id="fad25-114">Plan for multi-factor authentication for Office 365 deployments</span></span>](https://support.office.com/article/043807b2-21db-4d5c-b430-c8a6dee0e6ba)
    
- [<span data-ttu-id="fad25-115">设置多因素身份验证的 Office 365 用户</span><span class="sxs-lookup"><span data-stu-id="fad25-115">Set up multi-factor authentication for Office 365 users</span></span>](https://support.office.com/article/8f0454b2-f51a-4d9c-bcde-2c48e41621c6)
    
- [<span data-ttu-id="fad25-116">规划在何处部署 MFA、 云或内部部署</span><span class="sxs-lookup"><span data-stu-id="fad25-116">Plan where to deploy MFA, Cloud or on-premises</span></span>](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-get-started)
    
- [<span data-ttu-id="fad25-117">配置 Azure 多因素身份验证设置</span><span class="sxs-lookup"><span data-stu-id="fad25-117">Configure Azure multi-factor authentication settings</span></span>](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-whats-next)
    
## <a name="step-3-enforce-mfa-with-azure-ad-conditional-access-rules"></a><span data-ttu-id="fad25-118">步骤 3： 强制 MFA 与 Azure AD 条件访问规则</span><span class="sxs-lookup"><span data-stu-id="fad25-118">Step 3: Enforce MFA with Azure AD conditional access rules</span></span>

<span data-ttu-id="fad25-119">如果您使用的 Azure AD MFA，创建要用于访问 Office 365 和您的环境中其他 saas 与应用程序需要 MFA 条件访问规则。</span><span class="sxs-lookup"><span data-stu-id="fad25-119">If you are using Azure AD MFA, create a conditional access rule to require MFA for access to Office 365 and other SaaS apps in your environment.</span></span>
  
- [<span data-ttu-id="fad25-120">Azure Active Directory 中的条件访问</span><span class="sxs-lookup"><span data-stu-id="fad25-120">Conditional access in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal)
    
## <a name="step-4-configure-privileged-access-management"></a><span data-ttu-id="fad25-121">步骤 4： 配置访问权限的管理</span><span class="sxs-lookup"><span data-stu-id="fad25-121">Step 4: Configure privileged access management</span></span>

<span data-ttu-id="fad25-p102">特权访问管理 Office 365 中允许精细的访问控制拥有权限的管理员任务。 它可以帮助保护您的组织可以使用现有拥有权限的管理员帐户所访问敏感数据或关键的配置设置的访问权限的破坏。</span><span class="sxs-lookup"><span data-stu-id="fad25-p102">Privileged access management allows granular access control over privileged admin tasks in Office 365.  It can help protect your organization from breaches that may use existing privileged admin accounts with standing access to sensitive data or access to critical configuration settings.</span></span>

- [<span data-ttu-id="fad25-124">概述特权访问管理</span><span class="sxs-lookup"><span data-stu-id="fad25-124">Overview of privileged access management</span></span>](privileged-access-managment-overview.md)
- [<span data-ttu-id="fad25-125">配置访问权限的管理</span><span class="sxs-lookup"><span data-stu-id="fad25-125">Configure privileged access management</span></span>](privileged-access-management-configuration.md)

## <a name="step-5-configure-sharepoint-device-access-policies"></a><span data-ttu-id="fad25-126">步骤 5： 配置 SharePoint 设备访问策略</span><span class="sxs-lookup"><span data-stu-id="fad25-126">Step 5: Configure SharePoint device access policies</span></span>

<span data-ttu-id="fad25-p103">SharePoint Online 和 OneDrive for Business 的设备访问策略被建议用于保护敏感、 保密，和监管的数据。即将推出是能够将设备访问策略应用于各个团队网站。</span><span class="sxs-lookup"><span data-stu-id="fad25-p103">Device access policies for SharePoint Online and OneDrive for Business are recommended for protecting sensitive, classified, and regulated data. Coming soon is the ability to apply device access policies to individual team sites.</span></span>
  
- [<span data-ttu-id="fad25-129">通过非托管设备控制访问</span><span class="sxs-lookup"><span data-stu-id="fad25-129">Control access from unmanaged devices</span></span>](https://support.office.com/article/Control-access-from-unmanaged-devices-5ae550c4-bd20-4257-847b-5c20fb053622?ui=en-US&amp;rs=en-US&amp;ad=US)
    
## <a name="step-6-configure-app-and-data-protection-for-devices"></a><span data-ttu-id="fad25-130">步骤 6： 配置应用程序和数据保护设备 （英文）</span><span class="sxs-lookup"><span data-stu-id="fad25-130">Step 6: Configure app and data protection for devices</span></span>

<span data-ttu-id="fad25-p104">您可以管理无论是否为移动设备管理注册设备的移动设备上的应用程序。这样可以防止意外泄露的 Office 365，包括邮件和文件中的数据。</span><span class="sxs-lookup"><span data-stu-id="fad25-p104">You can manage applications on mobile devices regardless of whether the devices are enrolled for mobile device management. This protects against accidental leakage of data in Office 365, including mail and files.</span></span>
  
- <span data-ttu-id="fad25-133">IOS 和 Android：[使用应用程序保护策略与 Microsoft Intune 保护应用程序数据](https://docs.microsoft.com/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune)</span><span class="sxs-lookup"><span data-stu-id="fad25-133">For iOS and Android: [Protect app data using app protection policies with Microsoft Intune](https://docs.microsoft.com/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune)</span></span>
    
<span data-ttu-id="fad25-134">Windows 10 的配置 Windows 的信息保护 (WIP) 以防止意外数据泄漏。</span><span class="sxs-lookup"><span data-stu-id="fad25-134">For Windows 10, configure Windows Information Protection (WIP) to prevent accidental data leaks.</span></span>
  
- <span data-ttu-id="fad25-135">托管设备：[创建使用 Microsoft Intune 的 Azure 门户注册策略与 Windows 的信息保护 (WIP)](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/create-wip-policy-using-intune-azure)</span><span class="sxs-lookup"><span data-stu-id="fad25-135">For managed devices: [Create a Windows Information Protection (WIP) with enrollment policy using the Azure portal for Microsoft Intune](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/create-wip-policy-using-intune-azure)</span></span>
    
- <span data-ttu-id="fad25-136">取消托管设备：[创建和部署 Windows 信息保护 (WIP) 应用程序保护策略与 Intune](https://docs.microsoft.com/intune/windows-information-protection-policy-create)</span><span class="sxs-lookup"><span data-stu-id="fad25-136">For un-managed devices: [Create and deploy Windows Information Protection (WIP) app protection policy with Intune](https://docs.microsoft.com/intune/windows-information-protection-policy-create)</span></span>
    
## <a name="step-7-manage-devices-with-intune"></a><span data-ttu-id="fad25-137">步骤 7： 使用管理设备 Intune</span><span class="sxs-lookup"><span data-stu-id="fad25-137">Step 7: Manage devices with Intune</span></span>

<span data-ttu-id="fad25-p105">管理设备可以确保它们正常和合规性之前允许其在您的环境中对资源的访问。基于设备的条件规则帮助确保攻击者不能访问您的资源从非托管设备的访问。</span><span class="sxs-lookup"><span data-stu-id="fad25-p105">Managing devices allows you to ensure that they are healthy and compliant before allowing them access to resources in your environment. Device based conditional access rules help ensure attackers can't gain access to your resources from unmanaged devices.</span></span>
  
- [<span data-ttu-id="fad25-140">注册 Intune 中管理的设备</span><span class="sxs-lookup"><span data-stu-id="fad25-140">Enroll devices for management in Intune</span></span>](https://docs.microsoft.com/intune-classic/deploy-use/enroll-devices-in-microsoft-intune)
    
## <a name="step-8-configure-additional-intune-policies-and-conditional-access-rules-for-your-environment"></a><span data-ttu-id="fad25-141">步骤 8： 配置其他 Intune 策略和针对您的环境的条件访问规则</span><span class="sxs-lookup"><span data-stu-id="fad25-141">Step 8: Configure additional Intune policies and conditional access rules for your environment</span></span>

<span data-ttu-id="fad25-142">使用以下建议企业规模或复杂的访问安全方案的起始点的配置。</span><span class="sxs-lookup"><span data-stu-id="fad25-142">Use these recommended configurations as a starting point for enterprise scale or sophisticated access security scenarios.</span></span>
  
- [<span data-ttu-id="fad25-143">安全电子邮件策略和配置</span><span class="sxs-lookup"><span data-stu-id="fad25-143">Secure email policies and configurations</span></span>](https://docs.microsoft.com/azure/active-directory/secure-email-introduction)
    

