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
# <a name="protect-apps-with-office-365-cloud-app-security-conditional-access-app-control"></a><span data-ttu-id="e2422-103">使用 Office 365 云应用安全条件访问应用程序控件保护应用程序</span><span class="sxs-lookup"><span data-stu-id="e2422-103">Protect apps with Office 365 Cloud App Security Conditional Access App Control</span></span>

|<span data-ttu-id="e2422-104">评估 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="e2422-104">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="e2422-105">规划 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="e2422-105">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="e2422-106">部署 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="e2422-106">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="e2422-107">利用率 \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="e2422-107">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="e2422-108">开始评估</span><span class="sxs-lookup"><span data-stu-id="e2422-108">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="e2422-109">开始规划</span><span class="sxs-lookup"><span data-stu-id="e2422-109">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |<span data-ttu-id="e2422-110">你在这里!</span><span class="sxs-lookup"><span data-stu-id="e2422-110">You are here!</span></span>  <br/> [<span data-ttu-id="e2422-111">后续步骤</span><span class="sxs-lookup"><span data-stu-id="e2422-111">Next step</span></span>](ocas-deploy-conditional-access-app-control.md) <br/> |[<span data-ttu-id="e2422-112">开始利用</span><span class="sxs-lookup"><span data-stu-id="e2422-112">Start utilizing</span></span>](utilization-activities-for-ocas.md) <br/> |

<span data-ttu-id="e2422-p101">在今天的工作区中, 通常不能知道事实之后在云环境中发生的情况。您希望在员工有意或无意地将您的数据和您的组织置于风险中之前, 及时阻止泄露和泄露。必须让组织中的用户充分利用云应用中的服务和工具, 并让他们自己的设备能够正常工作, 这一点非常重要。同时, 还需要一些工具来帮助保护您的组织实时数据泄露和数据失窃。通过与 Azure Active Directory 结合使用, Office 365 云应用安全功能通过条件访问应用程序控制提供了全面且集成的体验。</span><span class="sxs-lookup"><span data-stu-id="e2422-p101">In today’s workplace, it’s often not enough to know what’s happening in your cloud environment after the fact. You want to stop breaches and leaks in real time, before employees intentionally or inadvertently put your data and your organization at risk. It's important to enable users in your organization to make the most of the services and tools available to them in cloud apps, and let them bring their own devices to work. At the same time, you need tools to help protect your organization from data leaks, and data theft, in real time. Together with Azure Active Directory, Office 365 Cloud App Security delivers these capabilities in a holistic and integrated experience with Conditional Access App Control.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e2422-118">若要使用云应用安全条件访问应用程序控制, 您需要一个 [Azure Active Directory P1 许可证](https://azure.microsoft.com/pricing/details/active-directory/) 和一个活动的[Office 365 云应用安全](office-365-cas-overview.md)订阅。</span><span class="sxs-lookup"><span data-stu-id="e2422-118">To use Cloud App Security Conditional Access App Control, you need an [Azure Active Directory P1 license](https://azure.microsoft.com/pricing/details/active-directory/) and an active [Office 365 Cloud App Security](office-365-cas-overview.md) subscription.</span></span>

## <a name="how-it-works"></a><span data-ttu-id="e2422-119">工作原理</span><span class="sxs-lookup"><span data-stu-id="e2422-119">How it works</span></span>

<span data-ttu-id="e2422-p102">条件访问应用程序控件使用反向代理体系结构, 并与 Azure AD 条件访问唯一集成。Azure AD 条件访问允许您根据某些条件强制实施对组织的应用程序的访问控制。这些条件定义 \** 了条件访问策略应用于哪些用户 (用户或用户组) 以及 *什么* (哪些云应用) 和 *where\* (哪些位置和网络)。确定了条件之后, 您可以将用户路由到 Office 365 云应用安全性, 在此可以通过应用访问和会话控制来使用条件访问应用程序控制来保护数据。</span><span class="sxs-lookup"><span data-stu-id="e2422-p102">Conditional Access App Control uses a reverse proxy architecture and is uniquely integrated with Azure AD conditional access. Azure AD conditional access allows you to enforce access controls on your organization’s apps based on certain conditions. The conditions define *who* (user or group of users) and *what* (which cloud apps) and *where* (which locations and networks) a conditional access policy is applied to. After you’ve determined the conditions, you can route users to Office 365 Cloud App Security where you can protect data with Conditional Access App Control by applying access and session controls.</span></span>

<span data-ttu-id="e2422-p103">条件访问应用程序控制允许基于访问和会话策略实时监视和控制用户应用程序访问和会话。在云应用安全门户中使用访问和会话策略, 进一步优化筛选器并设置要对用户执行的操作。使用访问和会话策略, 您可以执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="e2422-p103">Conditional Access App Control enables user app access and sessions to be monitored and controlled in real time based on access and session policies. Access and session policies are used within the Cloud App Security portal to further refine filters and set actions to be taken on a user. With the access and session policies, you can:</span></span>

- <span data-ttu-id="e2422-p104">**阻止下载**: 您可以阻止下载敏感文档。例如, 在非托管设备上。</span><span class="sxs-lookup"><span data-stu-id="e2422-p104">**Block on download**: You can block the download of sensitive documents. For example, on unmanaged devices.</span></span>

- <span data-ttu-id="e2422-p105">**在下载**时进行保护: 不是阻止下载敏感文档, 而是需要在下载时通过加密来保护文档。此加密可确保在将数据下载到不受信任设备时对文档进行保护, 并对用户访问进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="e2422-p105">**Protect on download**: Instead of blocking the download of sensitive documents, you can require documents to be protected via encryption on download. This encryption makes sure the document is protected and user access is authenticated if the data is downloaded to an untrusted device.</span></span>

- <span data-ttu-id="e2422-p106">**监视低信任用户会话**: 在登录到应用程序时监视有风险的用户, 并在会话中记录其操作。您可以调查和分析用户行为, 以了解将来应如何在哪些条件下应用会话策略。</span><span class="sxs-lookup"><span data-stu-id="e2422-p106">**Monitor low-trust user sessions**: Risky users are monitored when they sign into apps and their actions are logged from within the session. You can investigate and analyze user behavior to understand where, and under what conditions, session policies should be applied in the future.</span></span>

- <span data-ttu-id="e2422-133">**阻止访问**: 您可以完全阻止来自非托管设备或非企业网络中的用户的特定应用程序的访问。</span><span class="sxs-lookup"><span data-stu-id="e2422-133">**Block access**: You can completely block access to specific apps for users coming from unmanaged devices or from non-corporate networks.</span></span>

- <span data-ttu-id="e2422-134">**创建只读模式**: 通过监视和阻止自定义应用程序内活动, 您可以为特定用户的特定应用程序创建只读模式。</span><span class="sxs-lookup"><span data-stu-id="e2422-134">**Create read-only mode**: By monitoring and blocking custom in-app activities, you can create a read-only mode to specific apps for specific users.</span></span>

- <span data-ttu-id="e2422-p107">**限制来自非公司网络的用户会话**: 允许从不属于企业网络的位置访问受保护的应用程序的用户受限制的访问权限。敏感材料的下载被阻止或保护。</span><span class="sxs-lookup"><span data-stu-id="e2422-p107">**Restrict user sessions from non-corporate networks**: Users accessing a protected app from a location that isn't part of your corporate network are allowed restricted access. The download of sensitive materials is blocked or protected.</span></span>

### <a name="how-session-control-works"></a><span data-ttu-id="e2422-137">会话控制的工作原理</span><span class="sxs-lookup"><span data-stu-id="e2422-137">How session control works</span></span>

<span data-ttu-id="e2422-p108">通过使用条件访问应用程序控件创建会话策略, 可以通过反向代理而不是直接通过反向代理重定向用户来控制用户会话, 而不是直接对应用程序进行重定向。从随后开始, 用户请求和响应将通过 Office 365 云应用安全, 而不是直接转到应用程序。</span><span class="sxs-lookup"><span data-stu-id="e2422-p108">Creating a session policy with Conditional Access App Control enables you to control user sessions by redirecting the user through a reverse proxy instead of directly to the app. From then on, user requests and responses go through Office 365 Cloud App Security rather than directly to the app.</span></span>

<span data-ttu-id="e2422-p109">若要将用户保留在会话中, 应用程序会话中的所有相关 url、Java 脚本和 cookie 都将替换为 Office 365 云应用安全 url。例如, 如果应用返回一个页面以 myapp.com 的域结尾的链接, 则会将该链接替换为以下列内容结尾的域: myapp.com.us.cas.ms</span><span class="sxs-lookup"><span data-stu-id="e2422-p109">To keep the user within the session, all the relevant URLs, Java scripts, and cookies within the app session are replaced with Office 365 Cloud App Security URLs. For example, if the app returns a page with links whose domains end with myapp.com, the link is replaced with domains ending with something like: myapp.com.us.cas.ms</span></span>

<span data-ttu-id="e2422-p110">此方法不需要在设备上安装任何内容。当监视来自非托管设备的会话时, 此方法非常理想。</span><span class="sxs-lookup"><span data-stu-id="e2422-p110">This method doesn't require you to install anything on the device. This method is ideal when monitoring sessions from unmanaged devices.</span></span>

<span data-ttu-id="e2422-144">在通过 Office 365 云应用安全性定向会话之后, 可以执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="e2422-144">After a session is directed through Office 365 Cloud App Security, the following actions can be done:</span></span>

1. <span data-ttu-id="e2422-145">检查用户活动的流量</span><span class="sxs-lookup"><span data-stu-id="e2422-145">Inspect the traffic for user activities</span></span>

2. <span data-ttu-id="e2422-146">在 Office 365 云应用安全活动日志中显示已标识的活动</span><span class="sxs-lookup"><span data-stu-id="e2422-146">Display the identified activities in the Office 365 Cloud App Security Activity log</span></span>

3. <span data-ttu-id="e2422-147">保存流量日志并对其进行分析</span><span class="sxs-lookup"><span data-stu-id="e2422-147">Save the traffic logs and analyze them</span></span>

4. <span data-ttu-id="e2422-148">使管理员能够导出流量日志</span><span class="sxs-lookup"><span data-stu-id="e2422-148">Enable the admin to export the traffic logs</span></span>

5. <span data-ttu-id="e2422-149">对会话强制实施策略</span><span class="sxs-lookup"><span data-stu-id="e2422-149">Enforce policies on the session</span></span>

## <a name="managed-device-identification"></a><span data-ttu-id="e2422-150">托管设备标识</span><span class="sxs-lookup"><span data-stu-id="e2422-150">Managed device identification</span></span>

<span data-ttu-id="e2422-p111">通过条件访问应用程序控件, 您可以创建策略, 以考虑设备是否受管理。若要确定设备是否为托管设备, 该功能使用:</span><span class="sxs-lookup"><span data-stu-id="e2422-p111">Conditional Access App Control enables you to create policies that take into account whether a device is managed or not. To identify whether a device is managed or not, the feature uses:</span></span>

- <span data-ttu-id="e2422-153">合规设备</span><span class="sxs-lookup"><span data-stu-id="e2422-153">Compliant devices</span></span>

- <span data-ttu-id="e2422-154">加入域的设备</span><span class="sxs-lookup"><span data-stu-id="e2422-154">Domain-joined devices</span></span>

- <span data-ttu-id="e2422-155">客户端证书部署</span><span class="sxs-lookup"><span data-stu-id="e2422-155">Client certificates deployment</span></span>

### <a name="compliant-and-domain-joined-devices"></a><span data-ttu-id="e2422-156">合规设备和加入域的设备</span><span class="sxs-lookup"><span data-stu-id="e2422-156">Compliant and domain-joined devices</span></span>

<span data-ttu-id="e2422-p112">Azure AD 条件访问支持将合规和加入域的设备信息直接传递到 Office 365 云应用安全。在这里, 可以开发使用设备状态作为筛选器的访问策略或会话策略。有关详细信息, 请参阅 [Azure Active Directory 中的设备管理简介](https://docs.microsoft.com/azure/active-directory/device-management-introduction)。</span><span class="sxs-lookup"><span data-stu-id="e2422-p112">Azure AD conditional access enables compliant and domain-joined device information to be passed directly to Office 365 Cloud App Security. From there, an access policy or a session policy can be developed that uses device state as a filter. For more information, see the [Introduction to device management in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/device-management-introduction).</span></span>

### <a name="client-certificate-authenticated-devices"></a><span data-ttu-id="e2422-160">客户端证书身份验证设备</span><span class="sxs-lookup"><span data-stu-id="e2422-160">Client-certificate authenticated devices</span></span>

<span data-ttu-id="e2422-p113">设备标识机制可以使用客户端证书请求来自相关设备的身份验证。您可以使用组织中已部署的现有客户端证书, 也可以将新的客户端证书推出给托管设备。然后, 使用这些证书的状态来设置访问和会话策略。有关如何部署客户端证书的信息, 请参阅 [deploy 条件 Access App Control for Office 365 apps](ocas-deploy-conditional-access-app-control.md)。</span><span class="sxs-lookup"><span data-stu-id="e2422-p113">The device identification mechanism can request authentication from relevant devices using client certificates. You can either use existing client certificates already deployed in your organization or roll out new client certificates to managed devices. You then use the presence of those certificates to set access and session policies. For information on how to deploy client certificates see [Deploy Conditional Access App Control for Office 365 apps](ocas-deploy-conditional-access-app-control.md).</span></span>

## <a name="supported-apps-and-clients"></a><span data-ttu-id="e2422-165">支持的应用和客户端</span><span class="sxs-lookup"><span data-stu-id="e2422-165">Supported apps and clients</span></span>

<span data-ttu-id="e2422-166">Office 365 的条件访问应用程序控制支持以下特色应用程序:</span><span class="sxs-lookup"><span data-stu-id="e2422-166">Conditional Access App Control for Office 365 supports the following featured apps:</span></span>

- <span data-ttu-id="e2422-167">Exchange Online (预览)</span><span class="sxs-lookup"><span data-stu-id="e2422-167">Exchange Online (preview)</span></span>

- <span data-ttu-id="e2422-168">OneDrive for business (预览)</span><span class="sxs-lookup"><span data-stu-id="e2422-168">OneDrive for Business (preview)</span></span>

- <span data-ttu-id="e2422-169">Power BI (预览)</span><span class="sxs-lookup"><span data-stu-id="e2422-169">Power BI (preview)</span></span>

- <span data-ttu-id="e2422-170">SharePoint Online (预览)</span><span class="sxs-lookup"><span data-stu-id="e2422-170">SharePoint Online (preview)</span></span>

- <span data-ttu-id="e2422-171">Microsoft 团队 (预览)</span><span class="sxs-lookup"><span data-stu-id="e2422-171">Microsoft Teams (preview)</span></span>

- <span data-ttu-id="e2422-172">Yammer (预览)</span><span class="sxs-lookup"><span data-stu-id="e2422-172">Yammer (preview)</span></span>

<span data-ttu-id="e2422-173">其他应用程序正持续 boarded 到会话控制。</span><span class="sxs-lookup"><span data-stu-id="e2422-173">Additional apps are being continuously on-boarded to session control.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e2422-174">后续步骤</span><span class="sxs-lookup"><span data-stu-id="e2422-174">Next steps</span></span>

- [<span data-ttu-id="e2422-175">为 Office 365 应用程序部署条件访问应用程序控制</span><span class="sxs-lookup"><span data-stu-id="e2422-175">Deploy Conditional Access App Control for Office 365 apps</span></span>](ocas-deploy-conditional-access-app-control.md)

- [<span data-ttu-id="e2422-176">了解 Office 365 中的会话策略云应用安全性</span><span class="sxs-lookup"><span data-stu-id="e2422-176">Learn about session policies in Office 365 Cloud App Security</span></span>](ocas-session-policies.md)

- [<span data-ttu-id="e2422-177">了解 Office 365 中的访问策略云应用安全</span><span class="sxs-lookup"><span data-stu-id="e2422-177">Learn about access policies in Office 365 Cloud App Security</span></span>](ocas-access-policies.md) 