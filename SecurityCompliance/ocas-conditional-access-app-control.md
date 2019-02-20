---
title: 使用 Office 365 云应用安全条件访问应用程序控件保护应用程序
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.reviewer: alesibov
ms.audience: Admin
ms.topic: reference
ms.date: 02/14/2019
ms.service: o365-administration
localization_priority: Normal
description: 使用 Office 365 云应用安全条件访问应用程序控制实时停止泄露和泄露。
ms.openlocfilehash: 8656bf9d3e028bf6b44731c397b74d9c883db707
ms.sourcegitcommit: 8679937354c1d8870ecd41519a59d2d7468c23c4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2019
ms.locfileid: "30103357"
---
# <a name="protect-apps-with-office-365-cloud-app-security-conditional-access-app-control"></a>使用 Office 365 云应用安全条件访问应用程序控件保护应用程序

|评估 * *\>**|规划 * *\>**|部署 * *\>**|利用率 * * * *|
|:-----|:-----|:-----|:-----|
|[开始评估](office-365-cas-overview.md) <br/> |[开始规划](get-ready-for-office-365-cas.md) <br/> |你在这里!  <br/> [后续步骤](ocas-deploy-conditional-access-app-control.md) <br/> |[开始利用](utilization-activities-for-ocas.md) <br/> |

在今天的工作区中, 通常不能知道事实之后在云环境中发生的情况。您希望在员工有意或无意地将您的数据和您的组织置于风险中之前, 及时阻止泄露和泄露。必须让组织中的用户充分利用云应用中的服务和工具, 并让他们自己的设备能够正常工作, 这一点非常重要。同时, 还需要一些工具来帮助保护您的组织实时数据泄露和数据失窃。通过与 Azure Active Directory 结合使用, Office 365 云应用安全功能通过条件访问应用程序控制提供了全面且集成的体验。

> [!IMPORTANT]
> 若要使用云应用安全条件访问应用程序控制, 您需要一个 [Azure Active Directory P1 许可证](https://azure.microsoft.com/pricing/details/active-directory/) 和一个活动的[Office 365 云应用安全](office-365-cas-overview.md)订阅。

## <a name="how-it-works"></a>工作原理

条件访问应用程序控件使用反向代理体系结构, 并与 Azure AD 条件访问唯一集成。Azure AD 条件访问允许您根据某些条件强制实施对组织的应用程序的访问控制。这些条件定义 ** 了条件访问策略应用于哪些用户 (用户或用户组) 以及 *什么* (哪些云应用) 和 *where* (哪些位置和网络)。确定了条件之后, 您可以将用户路由到 Office 365 云应用安全性, 在此可以通过应用访问和会话控制来使用条件访问应用程序控制来保护数据。

条件访问应用程序控制允许基于访问和会话策略实时监视和控制用户应用程序访问和会话。在云应用安全门户中使用访问和会话策略, 进一步优化筛选器并设置要对用户执行的操作。使用访问和会话策略, 您可以执行以下操作:

- **阻止下载**: 您可以阻止下载敏感文档。例如, 在非托管设备上。

- **在下载**时进行保护: 不是阻止下载敏感文档, 而是需要在下载时通过加密来保护文档。此加密可确保在将数据下载到不受信任设备时对文档进行保护, 并对用户访问进行身份验证。

- **监视低信任用户会话**: 在登录到应用程序时监视有风险的用户, 并在会话中记录其操作。您可以调查和分析用户行为, 以了解将来应如何在哪些条件下应用会话策略。

- **阻止访问**: 您可以完全阻止来自非托管设备或非企业网络中的用户的特定应用程序的访问。

- **创建只读模式**: 通过监视和阻止自定义应用程序内活动, 您可以为特定用户的特定应用程序创建只读模式。

- **限制来自非公司网络的用户会话**: 允许从不属于企业网络的位置访问受保护的应用程序的用户受限制的访问权限。敏感材料的下载被阻止或保护。

### <a name="how-session-control-works"></a>会话控制的工作原理

通过使用条件访问应用程序控件创建会话策略, 可以通过反向代理而不是直接通过反向代理重定向用户来控制用户会话, 而不是直接对应用程序进行重定向。从随后开始, 用户请求和响应将通过 Office 365 云应用安全, 而不是直接转到应用程序。

若要将用户保留在会话中, 应用程序会话中的所有相关 url、Java 脚本和 cookie 都将替换为 Office 365 云应用安全 url。例如, 如果应用返回一个页面以 myapp.com 的域结尾的链接, 则会将该链接替换为以下列内容结尾的域: myapp.com.us.cas.ms

此方法不需要在设备上安装任何内容。当监视来自非托管设备的会话时, 此方法非常理想。

在通过 Office 365 云应用安全性定向会话之后, 可以执行以下操作:

1. 检查用户活动的流量

2. 在 Office 365 云应用安全活动日志中显示已标识的活动

3. 保存流量日志并对其进行分析

4. 使管理员能够导出流量日志

5. 对会话强制实施策略

## <a name="managed-device-identification"></a>托管设备标识

通过条件访问应用程序控件, 您可以创建策略, 以考虑设备是否受管理。若要确定设备是否为托管设备, 该功能使用:

- 合规设备

- 加入域的设备

- 客户端证书部署

### <a name="compliant-and-domain-joined-devices"></a>合规设备和加入域的设备

Azure AD 条件访问支持将合规和加入域的设备信息直接传递到 Office 365 云应用安全。在这里, 可以开发使用设备状态作为筛选器的访问策略或会话策略。有关详细信息, 请参阅 [Azure Active Directory 中的设备管理简介](https://docs.microsoft.com/azure/active-directory/device-management-introduction)。

### <a name="client-certificate-authenticated-devices"></a>客户端证书身份验证设备

设备标识机制可以使用客户端证书请求来自相关设备的身份验证。您可以使用组织中已部署的现有客户端证书, 也可以将新的客户端证书推出给托管设备。然后, 使用这些证书的状态来设置访问和会话策略。有关如何部署客户端证书的信息, 请参阅 [deploy 条件 Access App Control for Office 365 apps](ocas-deploy-conditional-access-app-control.md)。

## <a name="supported-apps-and-clients"></a>支持的应用和客户端

Office 365 的条件访问应用程序控制支持以下特色应用程序:

- Exchange Online (预览)

- OneDrive for business (预览)

- Power BI (预览)

- SharePoint Online (预览)

- Microsoft 团队 (预览)

- Yammer (预览)

其他应用程序正持续 boarded 到会话控制。

## <a name="next-steps"></a>后续步骤

- [为 Office 365 应用程序部署条件访问应用程序控制](ocas-deploy-conditional-access-app-control.md)

- [了解 Office 365 中的会话策略云应用安全性](ocas-session-policies.md)

- [了解 Office 365 中的访问策略云应用安全](ocas-access-policies.md) 