---
title: 保护用户和设备的访问权限
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 4/17/2018
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a6ef28a4-2447-4b43-aae2-f5af6d53c68e
description: 用于保护对 O365 数据和服务的访问权限的登录页
ms.openlocfilehash: 0b693d9b259a671f0e2a3e45747f81e1020d7487
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2019
ms.locfileid: "34156864"
---
# <a name="protect-user-and-device-access"></a>保护用户和设备的访问权限

保护对 Office 365 数据和服务的访问对于防御网络攻击和防止数据丢失至关重要。 可以将相同的保护应用于环境中的其他 SaaS 应用程序, 甚至应用于使用 Azure Active Directory 应用程序代理发布的本地应用程序。
  
## <a name="step-1-review-recommendations"></a>步骤 1: 查看建议

用于保护访问 Office 365 设备、其他 SaaS 服务以及使用 Azure AD 应用代理发布的本地应用的标识和设备的推荐功能。
  
[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [更多语言](https://www.microsoft.com/download/details.aspx?id=55032)
  
## <a name="step-2-protect-administrator-accounts-and-access"></a>步骤 2: 保护管理员帐户和访问权限
用于管理 Office 365 环境的管理帐户包括提升的权限。 这些是黑客和网络罪犯的有用目标。 

首先使用管理员帐户进行管理。 管理员应使用单独的用户帐户进行常规的非管理, 并且仅在必要时才使用其管理帐户完成与工作职能相关联的任务。

使用多重身份验证和条件访问来保护您的管理员帐户。 有关详细信息, 请参阅[保护管理员帐户](https://docs.microsoft.com/en-us/microsoft-365/enterprise/identity-access-prerequisites#protecting-administrator-accounts)。 

接下来, 在 Office 365 中配置特权访问管理。 特权访问管理允许对 Office 365 中的特权管理任务进行精确的访问控制。 它可以帮助保护您的组织免受可能使用现有特权管理员帐户访问敏感数据或访问关键配置设置的访问的危害。

- [特权访问管理概述](privileged-access-management-overview.md)
- [配置特权访问管理](privileged-access-management-configuration.md)

另一个主要建议是使用专为管理工作配置的工作站。 这些是仅用于管理任务的专用设备。 请参阅[保护特权访问](https://docs.microsoft.com/en-us/windows-server/identity/securing-privileged-access/securing-privileged-access)。

最后, 您可以通过在租户中创建两个或多个紧急访问帐户来缓解无意中缺少管理访问权限造成的影响。 请参阅[管理 AZURE AD 中的紧急访问帐户](https://docs.microsoft.com/en-us/azure/active-directory/users-groups-roles/directory-emergency-access)。 

## <a name="step-3-configure-recommended-identity-and-device-access-policies"></a>步骤 3: 配置推荐的标识和设备访问策略
多重身份验证 (MFA) 和条件访问策略是功能强大的工具, 可缓解受到损坏的帐户和未经授权的访问。 我们建议实现一组已经过测试的策略。 有关详细信息 (包括部署步骤), 请参阅[Identity and device access 配置](https://docs.microsoft.com/en-us/microsoft-365/enterprise/microsoft-365-policies-configurations)。

 这些策略实现以下功能:
- 多身份验证
- 条件访问
- Intune 应用保护 (设备的应用程序和数据保护)
- Intune 设备合规性
- Azure AD Identity Protection

Implemetning Intune 设备合规性需要设备注册。 管理设备使您能够在允许用户访问您的环境中的资源之前确保它们的健康和合规性。 请参阅[在 Intune 中注册设备以进行管理](https://docs.microsoft.com/intune-classic/deploy-use/enroll-devices-in-microsoft-intune)

## <a name="step-4-configure-sharepoint-device-access-policies"></a>步骤 4: 配置 SharePoint 设备访问策略

Microsoft 建议使用设备访问控制保护 SharePoint 网站中的内容与敏感和高度管控的内容。 有关详细信息, 请参阅[保护 SharePoint 网站和文件的策略建议](https://docs.microsoft.com/en-us/microsoft-365/enterprise/sharepoint-file-access-policies)。



    

