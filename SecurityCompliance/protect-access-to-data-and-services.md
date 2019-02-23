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
# <a name="protect-access-to-data-and-services-in-office-365"></a>保护对 Office 365 数据和服务的访问

保护对 Office 365 数据和服务的访问对于防御网络攻击和防止数据丢失至关重要。可以将相同的保护应用于环境中的其他 SaaS 应用程序, 甚至应用于使用 Azure Active Directory 应用程序代理发布的本地应用程序。
  
## <a name="step-1-review-recommendations"></a>步骤 1: 查看建议

用于保护访问 Office 365 设备、其他 SaaS 服务以及使用 Azure AD 应用代理发布的本地应用的标识和设备的推荐功能。
  
[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [更多语言](https://www.microsoft.com/download/details.aspx?id=55032)
  
## <a name="step-2-configure-mfa"></a>步骤 2: 配置 MFA

使用这些资源向自己定位 MFA, 决定哪种版本适合您, 然后为您的环境规划和部署 MFA。
  
- [什么是 Azure 多因素身份验证？](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication)
    
- [为你选择 Azure 多因素身份验证解决方案](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-get-started)
    
- [如何获取 Azure 多因素身份验证](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-versions-plans)
    
- [规划 Office 365 部署的多因素身份验证](https://support.office.com/article/043807b2-21db-4d5c-b430-c8a6dee0e6ba)
    
- [为 Office 365 用户设置多重身份验证](https://support.office.com/article/8f0454b2-f51a-4d9c-bcde-2c48e41621c6)
    
- [规划部署 MFA、云或本地的位置](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-get-started)
    
- [配置 Azure 多重身份验证设置](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-whats-next)
    
## <a name="step-3-enforce-mfa-with-azure-ad-conditional-access-rules"></a>步骤 3: 强制与 Azure AD 条件访问规则进行 MFA

如果使用的是 Azure AD MFA, 请创建条件访问规则, 以要求对环境中的 Office 365 和其他 SaaS 应用程序的访问进行 MFA。
  
- [Azure Active Directory 中的条件访问](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal)
    
## <a name="step-4-configure-privileged-access-management"></a>步骤 4: 配置特权访问管理

特权访问管理允许对 Office 365 中的特权管理任务进行精确的访问控制。 它可以帮助保护您的组织免受可能使用现有特权管理员帐户访问敏感数据或访问关键配置设置的访问的危害。

- [特权访问管理概述](privileged-access-management-overview.md)
- [配置特权访问管理](privileged-access-management-configuration.md)

## <a name="step-5-configure-sharepoint-device-access-policies"></a>步骤 5: 配置 SharePoint 设备访问策略

建议使用适用于 SharePoint Online 和 OneDrive for business 的设备访问策略来保护敏感、分类和受管制的数据。即将推出将设备访问策略应用于各个团队网站的功能。
  
- [通过非托管设备控制访问](https://support.office.com/article/Control-access-from-unmanaged-devices-5ae550c4-bd20-4257-847b-5c20fb053622?ui=en-US&amp;rs=en-US&amp;ad=US)
    
## <a name="step-6-configure-app-and-data-protection-for-devices"></a>步骤 6: 配置设备的应用程序和数据保护

您可以管理移动设备上的应用程序, 而无需考虑是否为移动设备管理注册了设备。这样可以防止 Office 365 中数据的意外泄露 (包括邮件和文件)。
  
- 对于 iOS 和 Android:[使用 Microsoft Intune 的应用保护策略保护应用数据](https://docs.microsoft.com/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune)
    
对于 windows 10, 请配置 windows 信息保护 (WIP) 以防止意外的数据泄露。
  
- 对于托管设备:[使用 Microsoft Intune 的 Azure 门户创建带有注册策略的 Windows 信息保护 (WIP)](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/create-wip-policy-using-intune-azure)
    
- 对于未管理的设备:[使用 Intune 创建和部署 Windows 信息保护 (WIP) 应用保护策略](https://docs.microsoft.com/intune/windows-information-protection-policy-create)
    
## <a name="step-7-manage-devices-with-intune"></a>步骤 7: 使用 Intune 管理设备

管理设备使您能够在允许用户访问您的环境中的资源之前确保它们的健康和合规性。基于设备的条件访问规则有助于确保攻击者无法从非托管设备获取对资源的访问权限。
  
- [在 Intune 中注册设备以进行管理](https://docs.microsoft.com/intune-classic/deploy-use/enroll-devices-in-microsoft-intune)
    
## <a name="step-8-configure-additional-intune-policies-and-conditional-access-rules-for-your-environment"></a>步骤 8: 为环境配置其他 Intune 策略和条件访问规则

使用这些建议的配置作为企业级扩展或完善的访问安全方案的起点。
  
- [安全电子邮件策略和配置](https://docs.microsoft.com/azure/active-directory/secure-email-introduction)
    

