---
title: 为 Office 365 应用部署条件访问应用控制
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.reviewer: alesibov
ms.audience: Admin
ms.topic: reference
ms.date: 02/14/2019
ms.service: O365-seccomp
localization_priority: Normal
description: 按照以下步骤操作, 将 Azure AD Office 365 应用程序配置为由 Office 365 云应用安全条件访问应用程序控制。
ms.openlocfilehash: cfb3d885fdfaf0e4698b1f8f9a0e13baacf43f66
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30221052"
---
# <a name="deploy-conditional-access-app-control-for-office-365-apps"></a><span data-ttu-id="8b76f-103">为 Office 365 应用部署条件访问应用控制</span><span class="sxs-lookup"><span data-stu-id="8b76f-103">Deploy Conditional Access App Control for Office 365 apps</span></span>

|<span data-ttu-id="8b76f-104">评估 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="8b76f-104">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="8b76f-105">规划 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="8b76f-105">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="8b76f-106">部署 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="8b76f-106">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="8b76f-107">利用率 \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="8b76f-107">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="8b76f-108">开始评估</span><span class="sxs-lookup"><span data-stu-id="8b76f-108">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="8b76f-109">开始规划</span><span class="sxs-lookup"><span data-stu-id="8b76f-109">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |<span data-ttu-id="8b76f-110">你在这里!</span><span class="sxs-lookup"><span data-stu-id="8b76f-110">You are here!</span></span>  <br/> [<span data-ttu-id="8b76f-111">后续步骤</span><span class="sxs-lookup"><span data-stu-id="8b76f-111">Next step</span></span>](ocas-session-policies.md) <br/> |[<span data-ttu-id="8b76f-112">开始利用</span><span class="sxs-lookup"><span data-stu-id="8b76f-112">Start utilizing</span></span>](utilization-activities-for-ocas.md) <br/> |

<span data-ttu-id="8b76f-113">按照以下步骤操作, 将 Azure AD Office 365 应用程序配置为由 Office 365 云应用安全条件访问应用程序控制。</span><span class="sxs-lookup"><span data-stu-id="8b76f-113">Follow these steps to configure Azure AD Office 365 apps to be controlled by Office 365 Cloud App Security Conditional Access App Control.</span></span>

<span data-ttu-id="8b76f-114">**步骤 1: [创建 Azure AD 条件访问测试策略](#step-1-create-an-azure-ad-conditional-access-test-policy)**</span><span class="sxs-lookup"><span data-stu-id="8b76f-114">**Step 1: [Create an Azure AD conditional access test policy](#step-1-create-an-azure-ad-conditional-access-test-policy)**</span></span>

<span data-ttu-id="8b76f-115">**步骤 2: [使用范围限定为应用程序中的策略的用户登录](#step-2-sign-in-with-a-user-scoped-to-the-policy-in-the-apps)**</span><span class="sxs-lookup"><span data-stu-id="8b76f-115">**Step 2: [Sign in with a user scoped to the policy in the apps](#step-2-sign-in-with-a-user-scoped-to-the-policy-in-the-apps)**</span></span>

<span data-ttu-id="8b76f-116">**步骤 3: 如果未在 Azure AD 中选择内置云应用安全策略, 或者如果要将该策略应用于非功能应用程序, 请 [在云应用安全门户中配置高级控件](#step-3-configure-advanced-controls-in-the-cloud-app-security-portal)**</span><span class="sxs-lookup"><span data-stu-id="8b76f-116">**Step 3: If you did not select a built-in Cloud App Security policy in Azure AD or if you want to apply the policy to a non-featured app, [Configure advanced controls in the Cloud App Security portal](#step-3-configure-advanced-controls-in-the-cloud-app-security-portal)**</span></span>

<span data-ttu-id="8b76f-117">**步骤 4:[测试部署](#step-4-test-the-deployment)**</span><span class="sxs-lookup"><span data-stu-id="8b76f-117">**Step 4: [Test the deployment](#step-4-test-the-deployment)**</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8b76f-118">若要为 Office 365 应用程序部署条件访问应用程序控制, 您需要一个适用 [于 Azure AD Premium P1](https://docs.microsoft.com/azure/active-directory/license-users-groups) 的有效许可证以及一个 Office 365 云应用安全许可证。</span><span class="sxs-lookup"><span data-stu-id="8b76f-118">To deploy Conditional Access App Control for Office 365 apps, you need a valid [license for Azure AD Premium P1](https://docs.microsoft.com/azure/active-directory/license-users-groups) as well as a Office 365 Cloud App Security license.</span></span>

## <a name="step-1-create-an-azure-ad-conditional-access-test-policy"></a><span data-ttu-id="8b76f-119">步骤 1: 创建 Azure AD 条件访问测试策略</span><span class="sxs-lookup"><span data-stu-id="8b76f-119">Step 1: Create an Azure AD conditional access test policy</span></span> 

1. <span data-ttu-id="8b76f-120">在 Azure Active Directory 中的 " **安全性**" 下, 单击 " **条件访问**"。</span><span class="sxs-lookup"><span data-stu-id="8b76f-120">In Azure Active Directory, under **Security**, click on **Conditional access**.</span></span>

2. <span data-ttu-id="8b76f-121">单击 " **新建策略** ", 并创建新策略。</span><span class="sxs-lookup"><span data-stu-id="8b76f-121">Click **New policy** and create a new policy.</span></span>

3. <span data-ttu-id="8b76f-122">在 "测试策略" 中的 " **用户**" 下, 分配可用于初始登录和验证的测试用户或用户。</span><span class="sxs-lookup"><span data-stu-id="8b76f-122">In the TEST policy, under **Users**, assign a test user or user that can be used for an initial sign-on and verification.</span></span>

4. <span data-ttu-id="8b76f-123">在测试策略中的 " **云应用**" 下, 使用条件访问应用程序控制分配要控制的应用程序。</span><span class="sxs-lookup"><span data-stu-id="8b76f-123">In the TEST policy, under **Cloud app**, assign the apps you want to control with Conditional Access App Control.</span></span>

5. <span data-ttu-id="8b76f-p101">在 " **会话**" 下, 将策略设置为使用任一内置策略、" **仅** 监视" 或 " **阻止下载**"。或选择 " **使用自定义策略** " 在云应用安全门户中设置高级策略。</span><span class="sxs-lookup"><span data-stu-id="8b76f-p101">Under **Session**, set the policy to use either of the built-in policies, **Monitor only** or **Block downloads**. Or select **Use custom policy** to set an advanced policy in the Cloud App Security portal.</span></span>

6. <span data-ttu-id="8b76f-126">添加任何适用的 **条件分配** 或 **授予控件** (可选)。</span><span class="sxs-lookup"><span data-stu-id="8b76f-126">Add any applicable **Condition assignments** or **Grant controls** (optional).</span></span>

> ![Azure AD 条件访问](media/image1.png)

## <a name="step-2-sign-in-with-a-user-scoped-to-the-policy-in-the-apps"></a><span data-ttu-id="8b76f-128">步骤 2: 使用范围限定为应用程序中的策略的用户登录</span><span class="sxs-lookup"><span data-stu-id="8b76f-128">Step 2: Sign in with a user scoped to the policy in the apps</span></span> 

<span data-ttu-id="8b76f-p102">创建策略后, 登录该策略中配置的每个应用。确保使用在策略中配置的用户进行登录。请务必先注销现有会话。</span><span class="sxs-lookup"><span data-stu-id="8b76f-p102">After you've created the policy, sign in to each app configured in that policy. Make sure you sign in using a user configured in the policy. Make sure to first sign out of existing sessions.</span></span>

<span data-ttu-id="8b76f-p103">云应用安全会将您的策略详细信息同步到其服务器, 以对您登录的每个新应用程序进行同步。这最多可能需要一分钟。</span><span class="sxs-lookup"><span data-stu-id="8b76f-p103">Cloud App Security will sync your policy details to its servers for each new app you log in to. This may take up to one minute.</span></span>

## <a name="step-3-configure-advanced-controls-in-the-cloud-app-security-portal"></a><span data-ttu-id="8b76f-134">步骤 3: 在云应用安全门户中配置高级控件</span><span class="sxs-lookup"><span data-stu-id="8b76f-134">Step 3: Configure advanced controls in the Cloud App Security portal</span></span> 

<span data-ttu-id="8b76f-135">上面的说明可帮助您在 Azure AD 中直接为特色应用程序创建内置云应用安全策略。</span><span class="sxs-lookup"><span data-stu-id="8b76f-135">The instructions above helped you create a built-in Cloud App Security policy for featured apps directly in Azure AD.</span></span>

<span data-ttu-id="8b76f-136">若要配置高级策略, 请在 Office 365 云应用安全门户中创建 [访问策略](ocas-access-policies.md) 或 [会话策略](ocas-session-policies.md) 。</span><span class="sxs-lookup"><span data-stu-id="8b76f-136">To configure an advanced policy, create an [access policy](ocas-access-policies.md) or a [session policy](ocas-session-policies.md) in the Office 365 Cloud App Security portal.</span></span>

### <a name="to-identify-devices-using-client-certificates-this-is-optional"></a><span data-ttu-id="8b76f-137">使用客户端证书标识设备 (这是可选的):</span><span class="sxs-lookup"><span data-stu-id="8b76f-137">To identify devices using client certificates (this is optional):</span></span>

1. <span data-ttu-id="8b76f-138">转到 "设置" "cog", 然后选择 " **设备标识**"。</span><span class="sxs-lookup"><span data-stu-id="8b76f-138">Go to the settings cog and choose **Device identification**.</span></span>

2. <span data-ttu-id="8b76f-139">上载一个或多个根证书或中间证书。</span><span class="sxs-lookup"><span data-stu-id="8b76f-139">Upload one or more root or intermediate certificates.</span></span>

3. <span data-ttu-id="8b76f-140">上载证书后, 可以基于 **设备标记**和 **有效的客户端证书**创建访问策略和会话策略。</span><span class="sxs-lookup"><span data-stu-id="8b76f-140">After the certificate is uploaded, you can create access policies and session policies based on **Device tag** and **Valid client certificate**.</span></span>

![条件访问应用程序控制设备 ID](media/image2.png)

> [!NOTE]
> <span data-ttu-id="8b76f-142">仅当会话与使用有效客户端证书筛选器的策略相匹配时, 才会从用户请求证书。</span><span class="sxs-lookup"><span data-stu-id="8b76f-142">A certificate is only requested from a user if the session matches a policy that uses the valid client certificate filter.</span></span>
> 
## <a name="step-4-test-the-deployment"></a><span data-ttu-id="8b76f-143">步骤 4: 测试部署</span><span class="sxs-lookup"><span data-stu-id="8b76f-143">Step 4: Test the deployment</span></span> 

1. <span data-ttu-id="8b76f-p104">首先注销任何现有会话。然后, 尝试登录到已成功部署的每个应用。使用与 Azure AD 中配置的策略相匹配的用户登录。</span><span class="sxs-lookup"><span data-stu-id="8b76f-p104">First sign out of any existing sessions. Then, try to sign in to each app that was successfully deployed. Sign in using a user that matches the policy configured in Azure AD.</span></span>

2. <span data-ttu-id="8b76f-147">在云应用安全门户中的 " **调查**" 下, 选择 " **活动日志**", 并确保为每个应用捕获了 "登录" 活动。</span><span class="sxs-lookup"><span data-stu-id="8b76f-147">In the Cloud App Security portal, under **Investigate**, select **Activity log**, and make sure the login activities are captured for each app.</span></span>

3. <span data-ttu-id="8b76f-148">您可以通过单击 " **高级**", 然后使用 **Source = Access control**进行筛选来进行筛选。</span><span class="sxs-lookup"><span data-stu-id="8b76f-148">You can filter by clicking on **Advanced**, and then filtering using **Source equals Access control**.</span></span>

4. <span data-ttu-id="8b76f-p105">建议您从托管和非托管设备登录移动和桌面应用。这样做是为了确保在活动日志中正确地捕获这些活动。若要验证是否已正确捕获活动, 请单击 "单一登录" 活动上的 "登录" 活动, 以打开活动抽屉。确保 **用户代理标记** 正确反映设备是本机客户端 (即移动或桌面应用程序), 还是设备是托管设备 (合规、加入域或有效的客户端证书)。</span><span class="sxs-lookup"><span data-stu-id="8b76f-p105">It's recommended that you sign into mobile and desktop apps from managed and unmanaged devices. This is to make sure that the activities are properly captured in the activity log. To verify that the activity is properly captured, click on a single sign-on log on activity so that it opens the activity drawer. Make sure the **User agent tag** properly reflects whether the device is a native client (meaning either a mobile or desktop app) or the device is a managed device (compliant, domain joined, or valid client certificate).</span></span>

> [!NOTE]
> <span data-ttu-id="8b76f-p106">部署后, 不能从条件访问应用程序控件页中删除应用程序。只要您不在应用程序上设置会话或访问策略, 条件访问应用程序控件就不会更改应用程序的任何行为。</span><span class="sxs-lookup"><span data-stu-id="8b76f-p106">After it is deployed, you can't remove an app from the Conditional Access App Control page. As long as you don't set a session or access policy on the app, the Conditional Access App Control won't change any behavior for the app.</span></span>

## <a name="next-steps"></a><span data-ttu-id="8b76f-155">后续步骤</span><span class="sxs-lookup"><span data-stu-id="8b76f-155">Next steps</span></span>

- [<span data-ttu-id="8b76f-156">了解 Office 365 中的会话策略云应用安全性</span><span class="sxs-lookup"><span data-stu-id="8b76f-156">Learn about session policies in Office 365 Cloud App Security</span></span>](ocas-session-policies.md)

- [<span data-ttu-id="8b76f-157">了解 Office 365 中的访问策略云应用安全</span><span class="sxs-lookup"><span data-stu-id="8b76f-157">Learn about access policies in Office 365 Cloud App Security</span></span>](ocas-access-policies.md) 

- [<span data-ttu-id="8b76f-158">对 IP 地址进行分组以简化 Office 365 云应用安全中的管理</span><span class="sxs-lookup"><span data-stu-id="8b76f-158">Group your IP addresses to simplify management in Office 365 Cloud App Security</span></span>](group-your-ip-addresses-in-ocas.md)