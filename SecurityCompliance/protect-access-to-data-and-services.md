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
ms.openlocfilehash: 652a14c5f1f29187aeac51355e7a924c9378806f
ms.sourcegitcommit: 15dfa0c83aa88816c18e30a44a49e36e733d952c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/19/2018
ms.locfileid: "24011274"
---
# <a name="protect-access-to-data-and-services-in-office-365"></a>保护对 Office 365 数据和服务的访问

保护访问您的 Office 365 数据和服务是至关重要辩护网络攻击和防止数据丢失。相同的保护可以应用于您的环境中其他 saas 与应用程序和偶数的本地应用程序发布与 Azure Active Directory 应用程序代理。
  
## <a name="step-1-review-recommendations"></a>步骤 1： 审核相关建议

用于保护访问 Office 365 设备、其他 SaaS 服务以及使用 Azure AD 应用代理发布的本地应用的标识和设备的推荐功能。
  
[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [更多语言](https://www.microsoft.com/download/details.aspx?id=55032)
  
## <a name="step-2-configure-mfa"></a>步骤 2： 配置 MFA

使用这些资源自己定向到 MFA，确定哪个版本适合您，然后规划和部署和 MFA 您的环境。
  
- [Azure 多因素身份验证是什么？](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication)
    
- [为您选择的 Azure 多因素身份验证解决方案](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-get-started)
    
- [如何获取 Azure 多因素身份验证](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-versions-plans)
    
- [规划多因素身份验证的 Office 365 部署](https://support.office.com/article/043807b2-21db-4d5c-b430-c8a6dee0e6ba)
    
- [设置多因素身份验证的 Office 365 用户](https://support.office.com/article/8f0454b2-f51a-4d9c-bcde-2c48e41621c6)
    
- [规划在何处部署 MFA、 云或内部部署](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-get-started)
    
- [配置 Azure 多因素身份验证设置](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-whats-next)
    
## <a name="step-3-enforce-mfa-with-azure-ad-conditional-access-rules"></a>步骤 3： 强制 MFA 与 Azure AD 条件访问规则

如果您使用的 Azure AD MFA，创建要用于访问 Office 365 和您的环境中其他 saas 与应用程序需要 MFA 条件访问规则。
  
- [Azure Active Directory 中的条件访问](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal)
    
## <a name="step-4-configure-privileged-access-management"></a>步骤 4： 配置访问权限的管理

特权访问管理 Office 365 中允许精细的访问控制拥有权限的管理员任务。 它可以帮助保护您的组织可以使用现有拥有权限的管理员帐户所访问敏感数据或关键的配置设置的访问权限的破坏。

- [概述特权访问管理](privileged-access-management-overview.md)
- [配置访问权限的管理](privileged-access-management-configuration.md)

## <a name="step-5-configure-sharepoint-device-access-policies"></a>步骤 5： 配置 SharePoint 设备访问策略

SharePoint Online 和 OneDrive for Business 的设备访问策略被建议用于保护敏感、 保密，和监管的数据。即将推出是能够将设备访问策略应用于各个团队网站。
  
- [通过非托管设备控制访问](https://support.office.com/article/Control-access-from-unmanaged-devices-5ae550c4-bd20-4257-847b-5c20fb053622?ui=en-US&amp;rs=en-US&amp;ad=US)
    
## <a name="step-6-configure-app-and-data-protection-for-devices"></a>步骤 6： 配置应用程序和数据保护设备 （英文）

您可以管理无论是否为移动设备管理注册设备的移动设备上的应用程序。这样可以防止意外泄露的 Office 365，包括邮件和文件中的数据。
  
- IOS 和 Android：[使用应用程序保护策略与 Microsoft Intune 保护应用程序数据](https://docs.microsoft.com/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune)
    
Windows 10 的配置 Windows 的信息保护 (WIP) 以防止意外数据泄漏。
  
- 托管设备：[创建使用 Microsoft Intune 的 Azure 门户注册策略与 Windows 的信息保护 (WIP)](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/create-wip-policy-using-intune-azure)
    
- 取消托管设备：[创建和部署 Windows 信息保护 (WIP) 应用程序保护策略与 Intune](https://docs.microsoft.com/intune/windows-information-protection-policy-create)
    
## <a name="step-7-manage-devices-with-intune"></a>步骤 7： 使用管理设备 Intune

管理设备可以确保它们正常和合规性之前允许其在您的环境中对资源的访问。基于设备的条件规则帮助确保攻击者不能访问您的资源从非托管设备的访问。
  
- [注册 Intune 中管理的设备](https://docs.microsoft.com/intune-classic/deploy-use/enroll-devices-in-microsoft-intune)
    
## <a name="step-8-configure-additional-intune-policies-and-conditional-access-rules-for-your-environment"></a>步骤 8： 配置其他 Intune 策略和针对您的环境的条件访问规则

使用以下建议企业规模或复杂的访问安全方案的起始点的配置。
  
- [安全电子邮件策略和配置](https://docs.microsoft.com/azure/active-directory/secure-email-introduction)
    

