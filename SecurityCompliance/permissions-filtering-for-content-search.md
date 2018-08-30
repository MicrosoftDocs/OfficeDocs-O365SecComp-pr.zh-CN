---
title: 配置内容搜索的权限筛选
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 5/14/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 1adffc35-38e5-4f7d-8495-8e0e8721f377
description: 使用筛选以让您的 Office 365 组织中的搜索邮箱和网站的子集电子数据展示管理器的内容搜索权限。
ms.openlocfilehash: 2b6968a097e7abe5943a84b9ceb9b6d126057cc2
ms.sourcegitcommit: c166964fe14eec69139a2d3d9c10d2c40ab33f91
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/28/2018
ms.locfileid: "23258620"
---
# <a name="configure-permissions-filtering-for-content-search"></a>配置内容搜索的权限筛选

您可以使用搜索筛选以让您的 Office 365 组织中的搜索邮箱和网站的子集电子数据展示管理器的权限。您还可以使用筛选以便仅搜索满足特定搜索条件的邮箱或网站内容的同一个电子数据展示管理器的权限。例如，您可能会让的特定位置或部门中的搜索仅的邮箱用户的电子数据展示管理器。通过创建使用受支持的收件人筛选器以限制哪些邮箱可搜索的筛选器来执行此操作。您还可以创建筛选器指定要搜索邮箱内容。这是创建筛选器所使用的可搜索的邮件属性。同样，您可能会让电子数据展示管理器中仅在您的组织中搜索特定的 SharePoint 网站。通过创建限制哪些网站可搜索的筛选器来执行此操作。您还可以创建筛选器指定要搜索网站内容。这是创建筛选器所使用的可搜索网站属性。

您还可以使用搜索权限筛选以创建逻辑边界 （称为*合规性边界*） 中的 Office 365 组织的控制用户 （如邮箱、 SharePoint 网站和 OneDrive 帐户） 的内容位置的特定的电子数据展示管理员可以搜索。有关详细信息，请参阅[设置 Office 365 中的电子数据展示调查的合规性边界](set-up-compliance-boundaries.md)。
  
搜索权限筛选支持 Office 365 安全性内容的搜索功能的&amp;合规性中心。这些四个 cmdlet 可以配置和管理搜索 permisisons 筛选器：
  
[新 ComplianceSecurityFilter](#new-compliancesecurityfilter)

[Get-ComplianceSecurityFilter](#get-compliancesecurityfilter)

[设置 ComplianceSecurityFilter](#set-compliancesecurityfilter)

[删除 ComplianceSecurityFilter](#remove-compliancesecurityfilter)

## <a name="before-you-begin"></a>准备工作

- 若要运行的合规性安全筛选器 cmdlet，您必须是安全中的 Organization Management 角色组的成员&amp;合规性中心。有关详细信息，请参阅[Permissions in Office 365 安全性&amp;合规性中心](permissions-in-the-security-and-compliance-center.md)。
    
- 您必须将 Windows PowerShell 连接到两个安全&amp;合规性中心和 Exchange Online 组织使用合规性安全筛选器 cmdlet。这是必要的因为这些 cmdlet 需要访问邮箱属性，因此，您必须连接到 Exchange Online。请参阅下一节中的步骤。 
    
- 请参阅[More information](#more-information)部分，了解有关搜索权限筛选器的其他信息。 
    
- 适用于非活动邮箱，这意味着您可以使用邮箱和邮箱内容筛选可以搜索非活动邮箱的限制筛选搜索权限。请参阅有关权限筛选和非活动邮箱的其他信息的[详细信息](#more-information)部分。 
    
-  筛选搜索权限不能用于限制用户可以在 Exchange 搜索公用文件夹。 
    
- 可在组织中创建的搜索权限筛选器的数量没有限制。但是，有 100 多个搜索权限筛选器时，将会影响搜索性能。若要保留在组织中的搜索权限筛选器数目尽可能的小，创建单个筛选器尽可能中的 Exchange、 SharePoint 和 OneDrive 合并的规则的筛选器。
    
## <a name="connect-to-the-security-amp-compliance-center-and-exchange-online-in-a-single-remote-powershell-session"></a>连接到安全性&amp;合规性中心和 Exchange Online 中的单个的远程 PowerShell 会话

1. 将以下文本保存到的 Windows PowerShell 脚本文件中，使用.ps1 filename 后缀。例如，您无法将其保存到名为 ConnectEXO CC.ps1 的文件。
    
    ```
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -DisableNameChecking
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -AllowClobber -DisableNameChecking
    $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Exchange Online + Compliance Center)"
    ```

2. 本地计算机上打开 Windows PowerShell，转到您在上一步中创建的脚本所在的文件夹，然后运行脚本。例如：
    
    ```
    .\ConnectEXO-CC.ps1
    ```
 
您如何知道是否这有效？运行脚本，cmdlet 从安全后&amp;合规性中心和 Exchange Online 导入本地 PowerShell 会话。如果未收到任何错误，您将成功连接。快速测试是运行安全&amp;合规性中心 cmdlet — 例如，**安装 UnifiedCompliancePrerequisite** — 和 Exchange Online cmdlet，如**Get-mailbox**。 
  
如果收到错误，则查看以下要求：
  
- 常见问题是密码错误。重新运行上述两个步骤，并仔细查看在步骤 1 中输入的用户名和密码。
    
- 验证您的帐户有权访问安全性&amp;合规性中心。有关详细信息，请参阅[让安全的用户访问&amp;合规性中心](grant-access-to-the-security-and-compliance-center.md)。
    
- 为了帮助防止受到拒绝服务 (DoS) 攻击，您限制为三个 open 远程 PowerShell 连接到安全性&amp;合规性中心。
    
- Windows PowerShell 需要进行相关配置，以运行脚本。只需在计算机上配置一次此设置即可，无需每次连接时都进行配置。为了使 Windows PowerShell 能够运行已签名脚本，请在提升的 Windows PowerShell 窗口（通过选择"以管理员身份运行"打开的 Windows PowerShell 窗口）中运行以下命令。

    ```
    Set-ExecutionPolicy RemoteSigned
    ```
- 需要之间本地计算机和 Office 365 开放 TCP 端口 80 通信。很可能打开，但是这是一个要考虑是否您的组织具有限制 Internet 访问策略。
    

  
## <a name="new-compliancesecurityfilter"></a>新 ComplianceSecurityFilter
<a name="New"> </a>

**新建 ComplianceSecurityFilter**用于创建新的搜索权限筛选器。下表描述此 cmdlet 的参数。创建合规性安全筛选器所需的所有参数。 
  
|**参数**|**说明**|
|:-----|:-----|
| _Action_ <br/> | _Action_参数指定的筛选器应用于的搜索操作的类型。内容搜索操作可以是：<br/><br/> 导出搜索结果时，应用**导出**-筛选器。  <br/> 预览搜索结果时应用**预览**-筛选器。  <br/> 清除搜索结果时，将应用**清除**-筛选器。  <br/> 运行 search 时应用**搜索**-筛选器。  <br/> **所有**的筛选器应用于所有搜索操作。  <br/> |
| _FilterName_ <br/> |_FilterName_参数指定的权限筛选器的名称。此名称用于标识筛选器时使用**Get-ComplianceSecurityFilter**、 **Set-ComplianceSecurityFilter**和**删除 ComplianceSecurityFilter** cmdlet。<br/> |
| _筛选器_ <br/> | _筛选器_参数指定的合规性安全筛选器的搜索条件。您可以创建三种不同的筛选器：<br/><br/> **邮箱筛选**-此类型的筛选器指定分配给的用户 （_用户_参数指定） 可以搜索的邮箱。此类型的筛选器的语法是**Mailbox_** _MailboxPropertyName_，其中_MailboxPropertyName_指定用于确定范围可搜索的邮箱的邮箱属性。例如，邮箱筛选器`"Mailbox_CustomAttribute10 -eq 'OttawaUsers'"`CustomAttribute10 属性中允许的用户分配此筛选器仅搜索邮箱具有值"OttawaUsers"。<br/>  任何支持的可筛选收件人属性可用于_MailboxPropertyName_属性。有关支持的属性列表，请参阅[-RecipientFilter 参数的可筛选属性](https://go.microsoft.com/fwlink/p/?LinkId=784903)。<br/><br/> **邮箱内容筛选**-此类型的筛选器应用上的内容的可搜索。指定已分配的用户可以搜索邮箱内容。此类型的筛选器的语法是**MailboxContent_** _SearchablePropertyName:value_，其中_SearchablePropertyName_指定可以指定在内容搜索的关键字查询语言 (KQL) 属性。例如，邮箱内容筛选器`MailboxContent_recipients:contoso.com`将允许为用户分配此筛选器仅搜索发送到 contoso.com 域中的收件人的邮件。<br/>  可搜索的邮件属性的列表，请参阅[关键字查询和内容搜索的搜索条件](keyword-queries-and-search-conditions.md)。  <br/><br/> **网站和网站内容筛选**-有两种 SharePoint 和 OneDrive for Business 与网站相关的筛选器可用于指定哪些网站或网站内容已分配的用户可以搜索：  <br/><br/> - **Site_**_SearchableSiteProperty_ <br/> - **SiteContent_**_SearchableSiteProperty_ <br/><br/>  以下两个筛选器可互换;例如`"Site_Path -like 'https://contoso.sharepoint.com/sites/doctors*'"`和`"SiteContent_Path -like 'https://contoso.sharepoint.com/sites/doctors*'"`将返回相同的结果。但为了帮助您确定筛选器的用途，您可以使用`Site_`指定与网站相关的属性 （如网站 URL) 和`SiteContent_`指定内容相关的属性 （例如文档类型。例如，筛选器`"Site_Path -like 'https://contoso.sharepoint.com/sites/doctors*'"`将允许为用户分配此筛选器中的内容仅搜索https://contoso.sharepoint.com/sites/doctors网站集。筛选器`"SiteContent_FileExtension -eq 'docx'"`将允许为用户分配此筛选器，以仅搜索的 Word 文档 (Word 2007 和更高版本)。<br/><br/>  可搜索站点属性列表，请参阅[Overview of 爬网和托管 SharePoint 中的属性](https://go.microsoft.com/fwlink/p/?LinkId=331599)。属性标有**是**中 * * 可查询 * * 列可用于创建网站内容筛选器。<br/> <br/> **重要：** 单个搜索筛选器只能有一种类型的筛选器;它不能包含邮箱筛选和网站筛选;同样，它不能包含邮箱筛选器和邮箱内容筛选器。但是，筛选器可以包含同一类型的更复杂的查询。例如，`"Mailbox_CustomAttribute10 -eq 'FTE' -and Mailbox_MemberOfGroup -eq '$($DG.DistinguishedName)'"` <br/><br/> **重要：** 您必须创建一个搜索权限筛选器明确阻止用户在特定的 Office 365 服务 （如防止用户搜索任何 Exchange 邮箱或任何 SharePoint 网站） 中搜索内容的位置。换句话说，创建允许用户搜索组织中的所有 SharePoint 网站的都搜索权限筛选器不阻止用户从搜索邮箱。例如，若要允许 SharePoint 管理员可以仅搜索 SharePoint 网站，您需要创建一个创建防止这些搜索邮箱的筛选器。同样，以允许仅搜索邮箱的 Exchange 管理员，您需要创建一个创建筛选器阻止它们搜索网站。           |
| _用户_ <br/> |_用户_参数指定要获取其内容的搜索应用于此筛选器的用户。标识通过其别名或主 SMTP 地址的用户。您可以指定用逗号分隔的多个值，也可以向所有用户分配筛选器，使用的**所有**值。<br/> 您还可以使用_用户_参数来指定安全&amp;合规性中心角色组。此使您能够创建自定义角色组并将该角色组的搜索权限筛选器。例如，假设您具有多个国家/地区的公司的美国子公司的电子数据展示管理员自定义角色组。您可以使用_用户_参数指定该角色组 （通过使用角色组的名称属性），然后使用_Filter_参数允许仅在美国要搜索的邮箱。<br/> 不能使用此参数指定通讯组。  <br/> |
   

## <a name="examples-of-creating-search-permissions-filters"></a>创建搜索权限筛选器的示例

下面是使用 **New-ComplianceSecurityFilter** cmdlet 创建搜索权限筛选器的示例。 
  
本示例允许用户 annb@contoso.com 只为在加拿大邮箱执行所有内容搜索操作。此筛选器包含从 ISO 3166-1 加拿大的三位数字的国家/地区代码。

```
New-ComplianceSecurityFilter -FilterName CountryFilter  -Users annb@contoso.com -Filters "Mailbox_CountryCode  -eq '124'" -Action All
```

此示例允许用户 donh 和 suzanf 仅搜索 CustomAttribute1 邮箱属性中具有值“Marketing”的邮箱。

```
New-ComplianceSecurityFilter -FilterName MarketingFilter  -Users donh,suzanf -Filters "Mailbox_CustomAttribute1  -eq 'Marketing'" -Action Search
```
   
此示例允许“美国发现管理员”角色组的成员仅对美国的邮箱执行所有内容搜索操作。此筛选器包含 ISO 3166-1 标准的美国三位数字国家/地区代码。
  
```
New-ComplianceSecurityFilter -FilterName USDiscoveryManagers  -Users "US Discovery Managers" -Filters "Mailbox_CountryCode  -eq '840'" -Action All
```

此分配示例将允许电子数据展示管理员角色组的成员仅搜索渥太华用户通讯组成员的邮箱。 
  
```
$DG = Get-DistributionGroup "Ottawa Users"
```

```
New-ComplianceSecurityFilter -FilterName DGFilter  -Users eDiscoveryManager -Filters "Mailbox_MemberOfGroup -eq '$($DG.DistinguishedName)'" -Action Search
```
此示例防止任何用户删除执行团队通讯组成员邮箱中的内容。

```
$DG = Get-DistributionGroup "Executive Team"
```

```
New-ComplianceSecurityFilter -FilterName NoExecutivesPreview  -Users all -Filters "Mailbox_MemberOfGroup -ne '$($DG.DistinguishedName)'" -Action Purge
```
   
本示例允许组织中的业务位置 onedrive 仅搜索内容的 OneDrive 电子数据展示管理员自定义角色组的成员。

```
New-ComplianceSecurityFilter -FilterName OneDriveOnly  -Users "OneDrive eDiscovery Managers" -Filters "Site_Path -like 'https://contoso-my.sharepoint.com/personal*'" -Action Search
```
   
> [!NOTE]
> 若要限制对搜索特定站点的用户，使用筛选器`Site_Path`，在上面的示例所示。使用`Site_Site`不起作用。 
  
此示例将用户限制为仅对 2015 日历年期间发送的电子邮件执行所有内容搜索操作。

```
New-ComplianceSecurityFilter -FilterName EmailDateRestrictionFilter -Users donh@contoso.com -Filters "MailboxContent_Received -ge '01-01-2015' -and MailboxContent_Received -le '12-31-2015'" -Action All
```
   
与上一示例类似，此示例将用户限制为对最近更改时间为 2015 日历年某个时间的文档执行所有内容搜索操作。

```
New-ComplianceSecurityFilter -FilterName DocumentDateRestrictionFilter -Users donh@contoso.com -Filters "SiteContent_LastModifiedTime -ge '01-01-2015' -and SiteContent_LastModifiedTime -le '12-31-2015'" -Action All
```
   
本示例阻止对组织中的任何邮箱执行内容搜索操作"OneDrive 发现管理员"角色组的成员。 

```
New-ComplianceSecurityFilter -FilterName NoEXO -Users "OneDrive Discovery Managers" -Filters "Mailbox_Alias -notlike '*'"  -Action All
```
  
## <a name="get-compliancesecurityfilter"></a>Get-ComplianceSecurityFilter

**Get ComplianceSecurityFilter**用于返回的搜索权限筛选器列表。使用_FilterName_参数返回特定搜索筛选器的信息。 
  
## <a name="set-compliancesecurityfilter"></a>设置 ComplianceSecurityFilter

**设置 ComplianceSecurityFilter**用于修改现有的搜索权限筛选器。所需的唯一参数是_FilterName_。 
  
|**参数**|**说明**|
|:-----|:-----|
| _Action_| _Action_参数指定的筛选器应用于的搜索操作的类型。内容搜索操作可以是：<br/><br/> 导出搜索结果时，应用**导出**-筛选器。  <br/> 预览搜索结果时应用**预览**-筛选器。  <br/> 清除搜索结果时，将应用**清除**-筛选器。  <br/> 运行 search 时应用**搜索**-筛选器。  <br/> **所有**的筛选器应用于所有搜索操作。  <br/> |
| _FilterName_|_FilterName_参数指定的权限筛选器的名称。 |
| _筛选器_| _筛选器_参数指定的合规性安全筛选器的搜索条件。您可以创建两种不同的筛选器：<br/><br/>**邮箱筛选**-此类型的筛选器指定分配给的用户 （_用户_参数指定） 可以搜索的邮箱。此类型的筛选器的语法是**Mailbox_** _MailboxPropertyName_，其中_MailboxPropertyName_指定用于确定范围可搜索的邮箱的邮箱属性。例如，邮箱筛选器`"Mailbox_CustomAttribute10 -eq 'OttawaUsers'"`CustomAttribute10 属性中允许的用户分配此筛选器仅搜索邮箱具有值"OttawaUsers"。 任何支持的可筛选收件人属性可用于_MailboxPropertyName_属性。有关支持的属性列表，请参阅[-RecipientFilter 参数的可筛选属性](https://go.microsoft.com/fwlink/p/?LinkId=784903)。<br/><br/>**邮箱内容筛选**-此类型的筛选器应用上的内容的可搜索。指定已分配的用户可以搜索邮箱内容。此类型的筛选器的语法是**MailboxContent_** _SearchablePropertyName:value_，其中_SearchablePropertyName_指定可以指定在内容搜索的关键字查询语言 (KQL) 属性。例如，邮箱内容筛选器`MailboxContent_recipients:contoso.com`将允许为用户分配此筛选器仅搜索发送到 contoso.com 域中的收件人的邮件。 可搜索的邮件属性的列表，请参阅[内容搜索的关键字查询](keyword-queries-and-search-conditions.md)。<br/><br/>**网站和网站内容筛选**有两种 SharePoint 和 OneDrive for Business 与网站相关的筛选器可用于指定哪些网站或网站内容已分配的用户可以搜索： <br/><br/>- **Site_***SearchableSiteProperty* <br/>- **SiteContent**_*SearchableSiteProperty*<br/><br/>以下两个筛选器可互换;例如`"Site_Path -like 'https://contoso.spoppe.com/sites/doctors*'"`和`"SiteContent_Path -like 'https://contoso.spoppe.com/sites/doctors*'"`将返回相同的结果。但为了帮助您确定筛选器的用途，您可以使用`Site_`指定与网站相关的属性 （如网站 URL) 和`SiteContent_`指定内容相关的属性 （例如文档类型。例如，筛选器`"Site_Path -like 'https://contoso.spoppe.com/sites/doctors*'"`将允许为用户分配此筛选器中的内容仅搜索https://contoso.spoppe.com/sites/doctors网站集。筛选器`"SiteContent_FileExtension -eq 'docx'"`将允许为用户分配此筛选器，以仅搜索的 Word 文档 (Word 2007 和更高版本)。<br/><br/>可搜索站点属性列表，请参阅[Overview of 爬网和托管 SharePoint 中的属性](https://go.microsoft.com/fwlink/p/?LinkId=331599)。标有**是****可查询**列中的属性可用于创建网站内容筛选器。<br/><br/> **重要：** 单个搜索筛选器只能有一种类型的筛选器;它不能包含邮箱筛选和网站筛选;同样，它不能包含邮箱筛选器和邮箱内容筛选器。但是，筛选器可以包含同一类型的更复杂的查询。例如，`"Mailbox_CustomAttribute10 -eq 'FTE' -and Mailbox_MemberOfGroup -eq '$($DG.DistinguishedName)'"`          |
| _用户_|_用户_参数指定要获取其内容的搜索应用于此筛选器的用户。因为这是一个多值属性，该参数指定用户组将覆盖现有的用户列表。请参阅下面的示例添加和删除所选的用户的语法。<br/><br/>您还可以使用_用户_参数来指定安全&amp;合规性中心角色组。此使您能够创建自定义角色组并将该角色组的搜索权限筛选器。例如，假设您具有多个国家/地区的公司的美国子公司的电子数据展示管理员自定义角色组。您可以使用_用户_参数指定该角色组 （通过使用角色组的名称属性），然后使用_Filter_参数允许仅在美国要搜索的邮箱。<br/><br/>不能使用此参数指定通讯组。 |

## <a name="examples-of-changing-search-permissions-filters"></a>更改搜索权限筛选器的示例

这些示例演示如何使用**Get-ComplianceSecurityFilter**和**设置 ComplianceSecurityFilter** cmdlet 来添加或删除现有列表的筛选器分配给用户的用户。当您添加或删除筛选器的用户时，指定的用户使用他们的 SMTP 地址。 
  
此示例是将用户添加到筛选器。

```
$filterusers = Get-ComplianceSecurityFilter -FilterName OttawaUsersFilter
```
```
$filterusers.users.add("pilarp@contoso.com")
```

```
Set-ComplianceSecurityFilter -FilterName OttawaUsersFilter -Users $filterusers.users
```
   
此示例是从筛选器中删除用户。

```
$filterusers = Get-ComplianceSecurityFilter -FilterName OttawaUsersFilter
```

```
$filterusers.users.remove("annb@contoso.com")
```

```
Set-ComplianceSecurityFilter -FilterName OttawaUsersFilter -Users $filterusers.users
```
  
## <a name="remove-compliancesecurityfilter"></a>删除 ComplianceSecurityFilter

**删除 ComplianceSecurityFilter**用于删除的搜索筛选器。使用_FilterName_参数指定要删除的筛选器。 
  
## <a name="more-information"></a>详细信息

- **如何搜索筛选工作的权限？** 内容搜索运行时，将向搜索查询添加权限筛选器。权限筛选器本质上通过**AND**布尔运算符加入向搜索查询。例如，如果您具有允许 Bob 的工作者通讯组的成员邮箱上执行所有搜索操作的权限筛选器。然后 Bob 搜索查询与组织中所有邮箱上运行内容搜索`sender:jerry@adatum.com`。因为由**AND**运算符逻辑组合权限筛选器和搜索查询，搜索将返回由 jerry@adatum.com 发送到任何工作人员通讯组的成员的任何消息。 
    
- **如果您有多个搜索权限筛选器，将会发生什么情况？** 在内容搜索查询中，由**或**布尔运算符组合多个权限筛选器。因此，任何筛选器时，将返回结果。在内容搜索 （通过**或**运算符组合） 的所有筛选器后组合与搜索查询通过**AND**运算符。我们来看上面的示例，其中的搜索筛选器允许 Bob 仅搜索的邮箱的工作者通讯组的成员。然后，我们创建另一个筛选器阻止 Bob 搜索 Phil 的邮箱 ("Mailbox_Alias-ne Phil")。我们还假定 Phil 是工作者组的成员。当 Bob 对组织中的所有邮箱 （从上面的示例中） 上运行内容搜索时，搜索结果将返回 Phil 的邮箱中，即使应用筛选器以阻止 Bob 搜索 Phil 的邮箱。这是因为第一个筛选器，它允许 Bob 搜索人员组中，为 true。和 Bob 由于 Phil 工作者组的成员，可以搜索 Phil 的邮箱。 
    
- **搜索筛选工时非活动邮箱的权限？** 是，您可以使用邮箱和邮箱内容筛选器以限制用户可以搜索您的组织中的非活动邮箱。常规邮箱，如非活动邮箱已用于创建权限筛选器的收件人属性用来配置。如有必要，您可以使用**Get-mailbox InactiveMailboxOnly**命令显示非活动邮箱的属性。有关详细信息，请参阅[创建和管理 Office 365 中的非活动邮箱](create-and-manage-inactive-mailboxes.md)。
    
- **搜索筛选工作为公用文件夹的权限？** 不。与前面所述，搜索筛选的权限不能用于限制用户可以在 Exchange 搜索公用文件夹。例如，不能权限筛选搜索结果中排除公用文件夹位置中的项目。 
    
- **确实会允许用户在特定服务中搜索的所有内容位置还阻止它们在不同的服务中搜索内容的位置？** 不。如前所述，您需要创建一个搜索权限筛选器明确阻止用户在特定的 Office 365 服务 （如防止用户搜索任何 Exchange 邮箱或任何 SharePoint 网站） 中搜索内容的位置。换句话说，创建允许用户搜索组织中的所有 SharePoint 网站的都搜索权限筛选器不阻止用户从搜索邮箱。例如，若要允许 SharePoint 管理员可以仅搜索 SharePoint 网站，您需要创建一个创建防止这些搜索邮箱的筛选器。同样，以允许仅搜索邮箱的 Exchange 管理员，您需要创建一个创建筛选器阻止它们搜索网站。
