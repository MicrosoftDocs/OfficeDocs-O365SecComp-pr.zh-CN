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
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32262998"
---
# <a name="access-policies-in-office-365-cloud-app-security"></a><span data-ttu-id="0ea6e-105">Office 365 云应用安全中的访问策略</span><span class="sxs-lookup"><span data-stu-id="0ea6e-105">Access policies in Office 365 Cloud App Security</span></span>

|<span data-ttu-id="0ea6e-106">评估 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="0ea6e-106">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="0ea6e-107">规划 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="0ea6e-107">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="0ea6e-108">部署 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="0ea6e-108">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="0ea6e-109">利用率 \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="0ea6e-109">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="0ea6e-110">开始评估</span><span class="sxs-lookup"><span data-stu-id="0ea6e-110">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="0ea6e-111">开始规划</span><span class="sxs-lookup"><span data-stu-id="0ea6e-111">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |<span data-ttu-id="0ea6e-112">你在这里!</span><span class="sxs-lookup"><span data-stu-id="0ea6e-112">You are here!</span></span>  <br/> [<span data-ttu-id="0ea6e-113">后续步骤</span><span class="sxs-lookup"><span data-stu-id="0ea6e-113">Next step</span></span>](group-your-ip-addresses-in-ocas.md) <br/> |[<span data-ttu-id="0ea6e-114">开始利用</span><span class="sxs-lookup"><span data-stu-id="0ea6e-114">Start utilizing</span></span>](utilization-activities-for-ocas.md) <br/> |

<span data-ttu-id="0ea6e-115">Office 365 云应用安全访问策略支持实时监视和控制基于用户、位置、设备和应用程序对云应用的访问。</span><span class="sxs-lookup"><span data-stu-id="0ea6e-115">Office 365 Cloud App Security access policies enable real-time monitoring and control over access to cloud apps based on user, location, device, and app.</span></span> <span data-ttu-id="0ea6e-116">您可以为任何设备 (包括未加入域的设备) 创建访问策略, 而不是通过将客户端证书滚动到托管设备或使用现有证书 (如第三方 MDM 证书) 来管理 Windows Intune。</span><span class="sxs-lookup"><span data-stu-id="0ea6e-116">You can create access policies for any device, including devices that aren't domain joined, and not managed by Windows Intune by rolling out client certificates to managed devices or by using existing certificates, such as third-party MDM certificates.</span></span> <span data-ttu-id="0ea6e-117">例如, 可以将客户端证书部署到托管设备, 然后阻止不使用证书的设备的访问。</span><span class="sxs-lookup"><span data-stu-id="0ea6e-117">For example, you can deploy client certificates to managed devices, and then block access from devices without a certificate.</span></span>

<span data-ttu-id="0ea6e-118"> [会话策略](ocas-session-policies.md) 不会完全允许或阻止访问, 而是在监视会话和/或限制特定会话活动时允许访问。</span><span class="sxs-lookup"><span data-stu-id="0ea6e-118">Instead of allowing or blocking access completely, with [session policies](ocas-session-policies.md) you can allow access while monitoring the session and/or limit specific session activities.</span></span>

## <a name="prerequisites-to-using-access-policies"></a><span data-ttu-id="0ea6e-119">使用访问策略的先决条件</span><span class="sxs-lookup"><span data-stu-id="0ea6e-119">Prerequisites to using access policies</span></span>

- <span data-ttu-id="0ea6e-120">Azure AD 高级 P1 许可证</span><span class="sxs-lookup"><span data-stu-id="0ea6e-120">Azure AD Premium P1 license</span></span>

- <span data-ttu-id="0ea6e-121">应 [使用条件访问应用程序控件部署](https://docs.microsoft.com/en-us/cloud-app-security/proxy-deployment-aad)相关应用程序</span><span class="sxs-lookup"><span data-stu-id="0ea6e-121">The relevant apps should be [deployed with Conditional Access App Control](https://docs.microsoft.com/en-us/cloud-app-security/proxy-deployment-aad)</span></span>

- <span data-ttu-id="0ea6e-122">应使用 [Azure AD 条件访问策略](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) 将用户重定向到 Office 365 云应用安全, 如下所述。</span><span class="sxs-lookup"><span data-stu-id="0ea6e-122">An [Azure AD conditional access policy](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) should be in place that redirects users to Office 365 Cloud App Security, as described below.</span></span>

## <a name="create-an-azure-ad-conditional-access-policy"></a><span data-ttu-id="0ea6e-123">创建 Azure AD 条件访问策略</span><span class="sxs-lookup"><span data-stu-id="0ea6e-123">Create an Azure AD conditional access policy</span></span>

<span data-ttu-id="0ea6e-124">Azure Active Directory 条件访问策略和云应用安全会话策略一起运行, 以检查每个用户会话并为每个应用制定策略决策。</span><span class="sxs-lookup"><span data-stu-id="0ea6e-124">Azure Active Directory conditional access policies and Cloud App Security session policies work in tandem to examine each user session and make policy decisions for each app.</span></span> <span data-ttu-id="0ea6e-125">若要在 Azure AD 中设置条件访问策略, 请按照以下过程操作:</span><span class="sxs-lookup"><span data-stu-id="0ea6e-125">To set up a conditional access policy in Azure AD, follow this procedure:</span></span>

1. <span data-ttu-id="0ea6e-126">使用用户或用户组的工作分配以及要使用条件访问应用程序控件控制的应用程序配置 [Azure AD 条件访问策略](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) 。</span><span class="sxs-lookup"><span data-stu-id="0ea6e-126">Configure an [Azure AD conditional access policy](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) with assignments for user or group of users and the app you want to control with Conditional Access App Control.</span></span><br><span data-ttu-id="0ea6e-127">注意: 仅此策略会影响 [使用条件访问应用程序控件](https://docs.microsoft.com/cloud-app-security/proxy-deployment-aad) 部署的应用程序。</span><span class="sxs-lookup"><span data-stu-id="0ea6e-127">NOTE: Only apps that were [deployed with Conditional Access App Control](https://docs.microsoft.com/cloud-app-security/proxy-deployment-aad) will be affected by this policy.</span></span>

2. <span data-ttu-id="0ea6e-128">通过在 **Session**下选择 " **使用条件访问应用程序控制强制限制** " 将用户路由到 Office 365 云应用安全性。</span><span class="sxs-lookup"><span data-stu-id="0ea6e-128">Route users to Office 365 Cloud App Security by selecting the **Use Conditional Access App Control enforced restrictions** under **Session**.</span></span>

## <a name="create-a-cloud-app-security-access-policy"></a><span data-ttu-id="0ea6e-129">创建云应用安全访问策略</span><span class="sxs-lookup"><span data-stu-id="0ea6e-129">Create a Cloud App Security access policy</span></span>

<span data-ttu-id="0ea6e-130">若要创建新的访问策略, 请按照以下过程操作:</span><span class="sxs-lookup"><span data-stu-id="0ea6e-130">To create a new access policy, follow this procedure:</span></span>

1. <span data-ttu-id="0ea6e-131">在门户中, 依次选择 " **控制** " 和 " **策略**"。</span><span class="sxs-lookup"><span data-stu-id="0ea6e-131">In the portal, select **Control** followed by **Policies**.</span></span>

2. <span data-ttu-id="0ea6e-132">在 " **策略** " 页中, 单击 " **创建策略** ", 然后选择 " **访问策略**"。</span><span class="sxs-lookup"><span data-stu-id="0ea6e-132">In the **Policies** page, click **Create policy** and select **Access policy**.</span></span>

3. <span data-ttu-id="0ea6e-133">在 " **访问策略** " 窗口中, 为策略分配一个名称, 例如 " *阻止来自非托管设备的访问*"。</span><span class="sxs-lookup"><span data-stu-id="0ea6e-133">In the **Access policy** window, assign a name for your policy, such as *Block access from unmanaged devices*.</span></span>

4. <span data-ttu-id="0ea6e-134">在 **匹配以下** 所有部分的活动中, 在 " **活动源**" 下, 选择 "要应用于策略的其他活动筛选器"。</span><span class="sxs-lookup"><span data-stu-id="0ea6e-134">In the **Activities matching all of the following** section, Under **Activity source**, select additional activity filters to apply to the policy.</span></span> <span data-ttu-id="0ea6e-135">筛选器包括以下选项:</span><span class="sxs-lookup"><span data-stu-id="0ea6e-135">Filters include the following options:</span></span>
    
    - <span data-ttu-id="0ea6e-136">**设备标记**: 使用此筛选器可标识非托管设备。</span><span class="sxs-lookup"><span data-stu-id="0ea6e-136">**Device tags**: Use this filter to identify unmanaged devices.</span></span>
    
    - <span data-ttu-id="0ea6e-137">**位置**: 使用此筛选器可确定未知 (因而是有风险的) 位置。</span><span class="sxs-lookup"><span data-stu-id="0ea6e-137">**Location**: Use this filter to identify unknown (and therefore risky) locations.</span></span>
    
    - <span data-ttu-id="0ea6e-138">**IP 地址**: 使用此筛选器筛选每个 IP 地址或使用之前分配的 ip 地址标记。</span><span class="sxs-lookup"><span data-stu-id="0ea6e-138">**IP address**: Use this filter to filter per IP addresses or use previously assigned IP address tags.</span></span>
    
    - <span data-ttu-id="0ea6e-139">**用户代理标记**: 使用此筛选器可启用启发, 以确定移动和桌面应用。</span><span class="sxs-lookup"><span data-stu-id="0ea6e-139">**User agent tag**: Use this filter to enable the heuristic to identify mobile and desktop apps.</span></span> <span data-ttu-id="0ea6e-140">此筛选器可设置为等于或不等于。</span><span class="sxs-lookup"><span data-stu-id="0ea6e-140">This filter can be set to equals or does not equal.</span></span> <span data-ttu-id="0ea6e-141">应针对每个云应用对移动和桌面应用程序测试这些值。</span><span class="sxs-lookup"><span data-stu-id="0ea6e-141">The values should be tested against your mobile and desktop apps for each cloud app.</span></span>

5. <span data-ttu-id="0ea6e-142">在 " **操作**" 下, 选择下列选项之一:</span><span class="sxs-lookup"><span data-stu-id="0ea6e-142">Under **Actions**, select one of the following options:</span></span>
    
    - <span data-ttu-id="0ea6e-143">**允许**: 将此操作设置为根据您设置的策略筛选器明确允许访问。</span><span class="sxs-lookup"><span data-stu-id="0ea6e-143">**Allow**: Set this action to explicitly allow access according to the policy filters you set.</span></span>
    
    - <span data-ttu-id="0ea6e-144">**阻止**: 将此操作设置为根据您设置的策略筛选器显式阻止访问。</span><span class="sxs-lookup"><span data-stu-id="0ea6e-144">**Block**: Set this action to explicitly block access according to the policy filters you set.</span></span>

6. <span data-ttu-id="0ea6e-145">您 可以 **为具有策略严重性的每个匹配事件创建一个警报**, 并设置一个警报限制, 并选择是将该警报作为电子邮件、短信还是两者都要。</span><span class="sxs-lookup"><span data-stu-id="0ea6e-145">You can **Create an alert for each matching event with the policy's severity** and set an alert limit and select whether you want the alert as an email, a text message or both.</span></span>

## <a name="next-steps"></a><span data-ttu-id="0ea6e-146">后续步骤</span><span class="sxs-lookup"><span data-stu-id="0ea6e-146">Next steps</span></span>

- [<span data-ttu-id="0ea6e-147">对 IP 地址进行分组以简化 Office 365 云应用安全中的管理</span><span class="sxs-lookup"><span data-stu-id="0ea6e-147">Group your IP addresses to simplify management in Office 365 Cloud App Security</span></span>](group-your-ip-addresses-in-ocas.md)