---
title: Office 365 云应用安全中的访问策略
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.reviewer: alesibov
ms.audience: Admin
ms.topic: reference
ms.date: 02/27/2019
ms.service: O365-seccomp
localization_priority: Normal
description: Office 365 云应用安全访问策略支持实时监视和控制基于用户、位置、设备和应用程序对云应用的访问。 您可以为任何设备 (包括未加入域的设备) 创建访问策略, 而不是通过将客户端证书滚动到托管设备或使用现有证书 (如第三方 MDM 证书) 来管理 Windows Intune。 例如, 可以将客户端证书部署到托管设备, 然后阻止不使用证书的设备的访问。
ms.openlocfilehash: 5e8b8fa293420bc9ff3616daf288b8e02a2eb768
ms.sourcegitcommit: 866d8cab6bcfdd124516a8369e47ec797bc7cf8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/27/2019
ms.locfileid: "30312079"
---
# <a name="access-policies-in-office-365-cloud-app-security"></a>Office 365 云应用安全中的访问策略

|评估 * *\>**|规划 * *\>**|部署 * *\>**|利用率 * * * *|
|:-----|:-----|:-----|:-----|
|[开始评估](office-365-cas-overview.md) <br/> |[开始规划](get-ready-for-office-365-cas.md) <br/> |你在这里!  <br/> [后续步骤](group-your-ip-addresses-in-ocas.md) <br/> |[开始利用](utilization-activities-for-ocas.md) <br/> |

Office 365 云应用安全访问策略支持实时监视和控制基于用户、位置、设备和应用程序对云应用的访问。 您可以为任何设备 (包括未加入域的设备) 创建访问策略, 而不是通过将客户端证书滚动到托管设备或使用现有证书 (如第三方 MDM 证书) 来管理 Windows Intune。 例如, 可以将客户端证书部署到托管设备, 然后阻止不使用证书的设备的访问。

 [会话策略](ocas-session-policies.md) 不会完全允许或阻止访问, 而是在监视会话和/或限制特定会话活动时允许访问。

## <a name="prerequisites-to-using-access-policies"></a>使用访问策略的先决条件

- Azure AD 高级 P1 许可证

- 应 [使用条件访问应用程序控件部署](https://docs.microsoft.com/en-us/cloud-app-security/proxy-deployment-aad)相关应用程序

- 应使用 [Azure AD 条件访问策略](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) 将用户重定向到 Office 365 云应用安全, 如下所述。

## <a name="create-an-azure-ad-conditional-access-policy"></a>创建 Azure AD 条件访问策略

Azure Active Directory 条件访问策略和云应用安全会话策略一起运行, 以检查每个用户会话并为每个应用制定策略决策。 若要在 Azure AD 中设置条件访问策略, 请按照以下过程操作:

1. 使用用户或用户组的工作分配以及要使用条件访问应用程序控件控制的应用程序配置 [Azure AD 条件访问策略](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) 。<br>注意: 仅此策略会影响 [使用条件访问应用程序控件](https://docs.microsoft.com/cloud-app-security/proxy-deployment-aad) 部署的应用程序。

2. 通过在 **Session**下选择 " **使用条件访问应用程序控制强制限制** " 将用户路由到 Office 365 云应用安全性。

## <a name="create-a-cloud-app-security-access-policy"></a>创建云应用安全访问策略

若要创建新的访问策略, 请按照以下过程操作:

1. 在门户中, 依次选择 " **控制** " 和 " **策略**"。

2. 在 " **策略** " 页中, 单击 " **创建策略** ", 然后选择 " **访问策略**"。

3. 在 " **访问策略** " 窗口中, 为策略分配一个名称, 例如 " *阻止来自非托管设备的访问*"。

4. 在 **匹配以下** 所有部分的活动中, 在 " **活动源**" 下, 选择 "要应用于策略的其他活动筛选器"。 筛选器包括以下选项:
    
    - **设备标记**: 使用此筛选器可标识非托管设备。
    
    - **位置**: 使用此筛选器可确定未知 (因而是有风险的) 位置。
    
    - **IP 地址**: 使用此筛选器筛选每个 IP 地址或使用之前分配的 ip 地址标记。
    
    - **用户代理标记**: 使用此筛选器可启用启发, 以确定移动和桌面应用。 此筛选器可设置为等于或不等于。 应针对每个云应用对移动和桌面应用程序测试这些值。

5. 在 " **操作**" 下, 选择下列选项之一:
    
    - **允许**: 将此操作设置为根据您设置的策略筛选器明确允许访问。
    
    - **阻止**: 将此操作设置为根据您设置的策略筛选器显式阻止访问。

6. 您 可以 **为具有策略严重性的每个匹配事件创建一个警报**, 并设置一个警报限制, 并选择是将该警报作为电子邮件、短信还是两者都要。

## <a name="next-steps"></a>后续步骤

- [对 IP 地址进行分组以简化 Office 365 云应用安全中的管理](group-your-ip-addresses-in-ocas.md)