---
title: 为 Office 365 应用部署条件访问应用控制
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.reviewer: alesibov
ms.audience: Admin
ms.topic: reference
ms.date: 02/27/2019
ms.service: O365-seccomp
localization_priority: Normal
description: 按照以下步骤操作, 将 Azure AD Office 365 应用程序配置为由 Office 365 云应用安全条件访问应用程序控制。
ms.openlocfilehash: 74cc415220282491694bf417a6761fd43a6d3521
ms.sourcegitcommit: e23b84ef4eee9cccec7205826b71ddfe9aaac2f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33402940"
---
# <a name="deploy-conditional-access-app-control-for-office-365-apps"></a>为 Office 365 应用部署条件访问应用控制

|评估 * *\>**|规划 * *\>**|部署 * *\>**|利用率 * * * *|
|:-----|:-----|:-----|:-----|
|[开始评估](office-365-cas-overview.md) <br/> |[开始规划](get-ready-for-office-365-cas.md) <br/> |你在这里!  <br/> [后续步骤](ocas-session-policies.md) <br/> |[开始利用](utilization-activities-for-ocas.md) <br/> |

按照以下步骤操作, 将 Azure AD Office 365 应用程序配置为由 Office 365 云应用安全条件访问应用程序控制。

**步骤 1: [创建 Azure AD 条件访问测试策略](#step-1-create-an-azure-ad-conditional-access-test-policy)**

**步骤 2: [使用范围限定为应用程序中的策略的用户登录](#step-2-sign-in-with-a-user-scoped-to-the-policy-in-the-apps)**

**步骤 3: 如果未在 Azure AD 中选择内置云应用安全策略, 或者如果要将该策略应用于非功能应用程序, 请 [在云应用安全门户中配置高级控件](#step-3-configure-advanced-controls-in-the-cloud-app-security-portal)**

**步骤 4:[测试部署](#step-4-test-the-deployment)**

> [!IMPORTANT]
> 若要为 Office 365 应用程序部署条件访问应用程序控制, 您需要一个适用 [于 Azure AD Premium P1](https://docs.microsoft.com/azure/active-directory/license-users-groups) 的有效许可证以及一个 Office 365 云应用安全许可证。

## <a name="step-1-create-an-azure-ad-conditional-access-test-policy"></a>步骤 1: 创建 Azure AD 条件访问测试策略 

1. 在 Azure Active Directory 中的 " **安全性**" 下, 单击 " **条件访问**"。

2. 单击 " **新建策略** ", 并创建新策略。

3. 在 "测试策略" 中的 " **用户**" 下, 分配可用于初始登录和验证的测试用户或用户。

4. 在测试策略中的 " **云应用**" 下, 使用条件访问应用程序控制分配要控制的应用程序。

5. 在 " **会话**" 下, 将策略设置为使用任一内置策略、" **仅** 监视" 或 " **阻止下载**"。 或选择 " **使用自定义策略** " 在云应用安全门户中设置高级策略。

6. 添加任何适用的 **条件分配** 或 **授予控件** (可选)。

> ![Azure AD 条件访问](media/OCASimage1.png)

## <a name="step-2-sign-in-with-a-user-scoped-to-the-policy-in-the-apps"></a>步骤 2: 使用范围限定为应用程序中的策略的用户登录 

创建策略后, 登录该策略中配置的每个应用。 确保使用在策略中配置的用户进行登录。 请务必先注销现有会话。

云应用安全会将您的策略详细信息同步到其服务器, 以对您登录的每个新应用程序进行同步。 这最多可能需要一分钟。

## <a name="step-3-configure-advanced-controls-in-the-cloud-app-security-portal"></a>步骤 3: 在云应用安全门户中配置高级控件 

上面的说明可帮助您在 Azure AD 中直接为特色应用程序创建内置云应用安全策略。

若要配置高级策略, 请在 Office 365 云应用安全门户中创建 [访问策略](ocas-access-policies.md) 或 [会话策略](ocas-session-policies.md) 。

### <a name="to-identify-devices-using-client-certificates-this-is-optional"></a>使用客户端证书标识设备 (这是可选的):

1. 转到 "设置" "cog", 然后选择 " **设备标识**"。

2. 上载一个或多个根证书或中间证书。

3. 上载证书后, 可以基于 **设备标记**和 **有效的客户端证书**创建访问策略和会话策略。

![条件访问应用程序控制设备 ID](media/OCASimage2.png)

> [!NOTE]
> 仅当会话与使用有效客户端证书筛选器的策略相匹配时, 才会从用户请求证书。
> 
## <a name="step-4-test-the-deployment"></a>步骤 4: 测试部署 

1. 首先注销任何现有会话。 然后, 尝试登录到已成功部署的每个应用。 使用与 Azure AD 中配置的策略相匹配的用户登录。

2. 在云应用安全门户中的 " **调查**" 下, 选择 " **活动日志**", 并确保为每个应用捕获了 "登录" 活动。

3. 您可以通过单击 " **高级**", 然后使用 **Source = Access control**进行筛选来进行筛选。

4. 建议您从托管和非托管设备登录移动和桌面应用。 这样做是为了确保在活动日志中正确地捕获这些活动。 若要验证是否已正确捕获活动, 请单击 "单一登录" 活动上的 "登录" 活动, 以打开活动抽屉。 确保 **用户代理标记** 正确反映设备是本机客户端 (即移动或桌面应用程序), 还是设备是托管设备 (合规、加入域或有效的客户端证书)。

> [!NOTE]
> 部署后, 不能从条件访问应用程序控件页中删除应用程序。 只要您不在应用程序上设置会话或访问策略, 条件访问应用程序控件就不会更改应用程序的任何行为。

## <a name="next-steps"></a>后续步骤

- [了解 Office 365 中的会话策略云应用安全性](ocas-session-policies.md)

- [了解 Office 365 中的访问策略云应用安全](ocas-access-policies.md) 

- [对 IP 地址进行分组以简化 Office 365 云应用安全中的管理](group-your-ip-addresses-in-ocas.md)