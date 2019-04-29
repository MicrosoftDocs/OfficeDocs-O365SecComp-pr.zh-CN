---
title: 检测和修正 Office 365 中的非法授权
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 4/23/2018
ms.audience: ITPro
ms.topic: article
ms.collection:
- o365_security_incident_response
- M365-security-compliance
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
description: 了解如何识别和修正在 Office 365 中的非法许可授予攻击。
ms.openlocfilehash: 658183b3e5a3089425312ee14c6663485e0543ce
ms.sourcegitcommit: e23b84ef4eee9cccec7205826b71ddfe9aaac2f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33402950"
---
# <a name="detect-and-remediate-illicit-consent-grants-in-office-365"></a>检测和修正 Office 365 中的非法授权

**摘要** 了解如何识别和修正在 Office 365 中的非法许可授予攻击。

## <a name="what-is-the-illicit-consent-grant-attack-in-office-365"></a>什么是 Office 365 中的非法同意授权攻击？
在违法许可授予攻击中, 攻击者将创建一个 Azure 注册的应用程序, 该应用程序请求对联系人信息、电子邮件或文档等数据的访问权限。 然后, 攻击者向最终用户授予权限, 允许该应用程序通过网络钓鱼攻击或将非法代码注入到受信任的网站来访问其数据。 在违法应用程序被授予同意后, 它将具有对数据的帐户级别访问权限, 而无需组织帐户。 常规修正步骤 (如重置已违例帐户的密码或要求对帐户进行多重身份验证 (MFA)) 不会对此类型的攻击有效, 因为它们是第三方应用程序, 并且是组织外部的。 这些攻击利用交互模型, 该模型假定调用信息的实体是自动化的, 而不是人工。

## <a name="what-does-an-illicit-consent-grant-attack-look-like-in-office-365"></a>非法同意在 Office 365 中授予攻击外观？
您需要搜索 Office 365**审核日志**, 以查找该攻击的标志 (也称为 "泄露" (IOC) 标记)。 对于具有许多 Azure 注册应用程序和大型用户群的组织, 最佳做法是在每周的基础上查看您的组织同意授予。
### <a name="steps-for-finding-signs-of-this-attack"></a>查找此攻击的迹象的步骤
1. 打开 Office 365 租户中的 "**安全与合规中心**"。
2. 导航到 "**搜索 & 调查**" 节点, 然后选择 "**审核日志**搜索"。
3. 创建搜索 (所有活动和所有用户) 并筛选结果以同意应用程序, 并添加 OAuth2PermissionGrant。
4. 检查扩展属性, 并查看 IsAdminContent 是否设置为 True。

> [!NOTE]
>  
   - 在事件发生后, 将在搜索结果中显示相应的审核日志条目, 最长可能需要30分钟或最长24小时。
   - 审核记录在审核日志中保留和搜索的时间长度取决于您的 Office 365 订阅, 以及分配给特定用户的许可证类型。 有关详细信息, 请参阅[审核日志](search-the-audit-log-in-security-and-compliance.md)。
      
如果此值为 true, 则表示具有全局管理员访问权限的人员可能已授予对数据的广泛访问权限。 如果这是意外情况, 请执行相应的步骤来[确认攻击](detect-and-remediate-illicit-consent-grants.md#confirmattack)。

<a name="confirmattack"> </a>
## <a name="how-to-confirm-an-attack"></a>如何确认攻击
如果您有上面列出的 IOCs 的一个或多个实例, 则需要进行进一步调查以确认攻击是否发生。 您可以使用这三种方法中的任何一种来确认攻击。
- 使用 Azure Active Directory 门户列出应用程序及其权限。 这种方法是彻底的, 但是, 如果您有多个用户要检查, 则一次只能检查一个用户, 这可能会非常耗时。
- 使用 PowerShell 清点应用程序及其权限。 这是最快且最彻底的方法, 最少的开销。
- 让您的用户单独检查其应用和权限, 并将结果报告给管理员进行修正。

## <a name="inventory-apps-with-access-in-your-organization"></a>在您的组织中列出具有访问权限的应用程序
您可以为使用 Azure Active Directory 门户或 PowerShell 的用户执行此操作, 也可以让用户单独枚举其应用程序访问。

### <a name="steps-for-using-the-azure-active-directory-portal"></a>使用 Azure Active Directory 门户的步骤
您可以通过使用[Azure Active Directory 门户](https://portal.azure.com/)来查找任何单个用户已向其授予权限的应用程序。 
1. 使用管理权限登录到 Azure 门户。
2. 选择 "Azure Active Directory" 边栏。
3. 选择 "**用户**"。
4. 选择要查看的用户。
5. 选择 "**应用程序**"。

这将向您显示分配给用户的应用程序以及 applcations 具有的权限。

### <a name="steps-for-having-your-users-enumerate-their-application-access"></a>让用户枚举其应用程序访问权限的步骤
让你的用户转https://myapps.microsoft.com到并查看其自己的应用程序访问权限。 他们应该能够查看具有访问权限的所有应用程序, 查看有关这些应用程序的详细信息 (包括访问范围), 并能够撤销可疑或违法应用程序的权限。

### <a name="steps-for-doing-this-with-powershell"></a>使用 PowerShell 执行此操作的步骤
验证非法同意授予攻击的最简单方法是运行[Get-AzureADPSPermissions](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09), 这会将租赁中所有用户的所有 oauth 同意授权和 oauth 应用转储到一个 .csv 文件中。 

#### <a name="pre-requisites"></a>先决条件
- 安装了 Azure AD PowerShell 库。
- 对将对其运行脚本的租户的全局管理员权限。
- 将运行脚本的计算机上的本地管理员。

> [!IMPORTANT]
> 强烈建议您在管理帐户上要求进行多重身份验证。  此脚本支持 MFA 身份验证。

1. 使用本地管理员权限登录到您将运行脚本的计算机。
2. 将[Get-AzureADPSPermissions](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09)脚本从 GitHub 下载或复制到将从中运行 scruipt 的文件夹。  这将是将写入输出 "权限 .csv" 文件的文件夹。
3. 以管理员身份打开 PowerShell 实例, 并打开将脚本保存到的文件夹。
4. 使用[AzureAD](https://docs.microsoft.com/powershell/module/azuread/connect-azuread?view=azureadps-2.0) cmdlet 连接到您的目录。
5. 运行此 PowerShell 命令行, 如下所示:`Get-AzureADPSPermissions.ps1 | Export-csv -path "Permissions.csv" -NoTypeInformation`

该脚本将生成一个名为 "权限 .csv" 的文件。 按照以下步骤查找违法应用程序权限授予: 
1. 在 ConsentType 列 (列 G) 中搜索值 "AllPrinciples"。 AllPrincipals 权限允许客户端应用程序访问租赁中的所有人的内容。 本机 Office 365 应用程序需要此权限才能正常工作。 应仔细查看具有此权限的每个非 Microsoft 应用程序。
2.  在 "权限" 列 (列 F) 中, 查看每个委派的应用程序对内容所拥有的权限。 查找 "读取" 和 "写入" 权限或 "*"。所有 "权限, 并仔细审查这些权限, 因为它们可能不合适。
3.  查看已授予同意的特定用户。 如果高配置文件或高影响用户授予了不适当的同意, 则应进一步调查。
4.  在 "ClientDisplayName" 列 (列 C) 中, 查找看起来可疑的应用程序。 应仔细查看具有拼写错误名称、超级 bland 名称或以黑客为名字的名称的应用程序。

## <a name="determine-the-scope-of-the-attack"></a>确定攻击的范围
完成对应用程序访问的清点之后, 请查看 Office 365**审核日志**以确定泄露的全部范围。  搜索受影响的用户、违法应用程序有权访问您组织的时间段以及应用程序的权限。 你可以在[Microsoft 365 安全与合规中心](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c)中搜索**审核日志**。 

> [!IMPORTANT]
> 必须先启用[管理员和用户](https://support.office.com/article/turn-office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014)的[邮箱审核](https://support.office.com/article/Enable-mailbox-auditing-in-Office-365-aaca8987-5b62-458b-9882-c28476a66918)和活动审核, 然后才能获取此类信息。

## <a name="how-to-stop-and-remediate-an-illicit-consent-grant--attack"></a>如何停止和修正违法许可授予攻击
在识别出具有非法权限的应用程序之后, 可以通过多种方式删除该访问。
- 您可以通过以下方式在 Azure Active Directory 门户中撤销应用程序的权限:
    - 导航到**Azure Active Directory 用户**边栏中受影响的用户。
    - 选择 "**应用程序**"。
    - 选择违法应用程序。
    - 在深化中单击 "**删除**"。
- 您可以按照[AzureADOAuth2PermissionGrant](https://docs.microsoft.com/powershell/module/azuread/Remove-AzureADOAuth2PermissionGrant?view=azureadps-2.0)中的步骤撤销对 PowerShell 的 OAuth 同意授权。
- 您可以按照[AzureADServiceAppRoleAssignment](https://docs.microsoft.com/powershell/module/azuread/Remove-AzureADServiceAppRoleAssignment?view=azureadps-2.0)中的步骤, 通过 PowerShell 吊销服务应用程序角色分配。
- 您还可以完全禁用受影响帐户的登录, 这将禁用对该帐户中的数据的应用程序访问。 这并不是最终用户的工作效率的理想之处, 但如果您正在努力快速限制影响, 则它可能是一个可行的短期补救措施。
- 您可以为租赁启用集成的应用程序。 这是一项重大步骤, 可禁用最终用户对租户范围授予许可的能力。 这样可以防止您的用户无意中授予对恶意应用程序的访问权限。 强烈建议不要这样做, 因为这会严重削弱用户在第三方应用程序中的工作效率。  为此, 可以按照[启用或禁用集成应用程序](https://support.office.com/article/Turning-Integrated-Apps-on-or-off-7e453a40-66df-44ab-92a1-96786cb7fb34)中的步骤操作。

## <a name="secure-office-365-like-a-cybersecurity-pro"></a>像网络安全专家那样保护 Office 365
你的 Office 365 订阅附带了一组强大的安全功能，可用于保护你的数据和用户。  使用“[Office 365 安全路线图：前 30 天、90 天内以及之后的首要行动](https://support.office.com/article/office-365-security-roadmap-top-priorities-for-the-first-30-days-90-days-and-beyond-28c86a1c-e4dd-4aad-a2a6-c768a21cb352)”，通过实施 Microsoft 建议的最佳做法来保护你的 Office 365 租户。
- 需要在前 30 天完成的任务。  这些任务会对你的用户产生直接影响并且影响很小。
- 需要在 90 天内完成的任务。 这些任务需要花费更多时间来规划和实施，但会显著改善你的安全状况。
- 90 天后。 这些增强功能基于前 90 天的工作构建。

## <a name="see-also"></a>另请参阅：
- [我的应用程序列表中的意外应用程序](https://docs.microsoft.com/azure/active-directory/application-access-unexpected-application)通过在实现时可能需要执行的各种操作来指导管理员。在遇到意外应用程序时, 将对数据进行访问。
- [将应用程序与 Azure Active Directory 集成] (https://docs.microsoft.com/azure/active-directory/active-directory-apps-permissions-consent)是对同意和权限的高级别概述。  请特别注意["同意框架](https://docs.microsoft.com/azure/active-directory/develop/active-directory-integrating-applications#overview-of-the-consent-framework)" 部分的概述。
- [开发应用程序时遇到的问题](https://docs.microsoft.com/azure/active-directory/active-directory-application-dev-development-content-map)提供了指向各种同意相关文章的链接。
- [azure Active Directory (azure AD) 中的应用程序和服务主体对象](https://docs.microsoft.com/azure/active-directory/develop/active-directory-application-objects)概述了应用程序和服务主体对象, 这些对象是应用程序模型的核心。
- "[管理对应用程序的访问](https://docs.microsoft.com/azure/active-directory/active-directory-managing-access-to-apps)" 是管理员管理用户对应用程序的访问权限所需的功能的概述。
