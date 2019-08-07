---
title: 部署独立的 SharePoint Online 团队网站
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/30/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_Solutions
ms.assetid: 3033614b-e23b-4f68-9701-f62525eafaab
description: '摘要: 使用这些分步说明部署一个新的独立 SharePoint Online 团队网站。'
ms.openlocfilehash: 06b7fdbc0e387ee2181a850e950537f3fed5ae50
ms.sourcegitcommit: 6122eb026c558a5126c40845e656fbb0c40cb32a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2019
ms.locfileid: "36053099"
---
# <a name="deploy-an-isolated-sharepoint-online-team-site"></a>部署独立的 SharePoint Online 团队网站

 **摘要:** 按照这些分步说明部署一个新的独立 SharePoint Online 团队网站。
  
本文是在 Microsoft Office 365 中创建和配置独立的 SharePoint Online 团队网站的分步部署指南。 这些步骤假定使用三个默认 SharePoint 组和相应的权限级别, 每个级别的访问权限都有一个基于 Azure Active Directory (AD) 的访问组。
  
## <a name="phase-1-create-and-populate-the-team-site-access-groups"></a>第1阶段: 创建和填充团队网站访问组

在此阶段中, 您将为三个默认 SharePoint 组创建三个基于 Azure AD 的访问组, 并使用适当的用户帐户填充它们。
  
> [!NOTE]
> 以下步骤假定所有必需的用户帐户都已存在, 并为其分配了适当的许可证。 如果不是, 请先添加它们并分配许可证, 然后再继续执行步骤1。 
  
### <a name="step-1-list-the-sharepoint-online-admins-for-the-site"></a>步骤 1: 列出网站的 SharePoint Online 管理员

确定对应于独立团队网站的 SharePoint Online 管理员的用户帐户集。
  
如果您通过 Office 365 管理用户帐户和组, 并且想要使用 Windows PowerShell, 请创建其用户主体名称 (upn) 列表 (示例 UPN: belindan@contoso.com)。
  
### <a name="step-2-list-the-members-for-the-site"></a>步骤 2: 列出网站的成员

确定与独立团队网站的成员对应的用户帐户集, 这些用户帐户将对存储在网站中的资源进行协作。
  
如果您通过 Office 365 管理用户帐户和组, 并且想要使用 PowerShell, 请创建其 Upn 的列表。 如果有大量的网站成员, 则可以将 Upn 列表存储在一个文本文件中, 并将它们全部添加到一个 PowerShell 命令中。
  
### <a name="step-3-list-the-viewers-for-the-site"></a>步骤 3: 列出网站的查看者

确定与独立团队网站的查看者相对应的用户帐户集, 这些用户可以查看存储在网站中的资源, 但不能对其内容进行修改, 也不能直接对其内容进行协作。
  
如果您通过 Office 365 管理用户帐户和组, 并且想要使用 PowerShell, 请创建其 Upn 的列表。 如果有大量的网站成员, 则可以将 Upn 列表存储在一个文本文件中, 并将它们全部添加到一个 PowerShell 命令中。
  
网站的查看者可能包括行政管理、法律顾问或部门间利益干系人。
  
### <a name="step-4-create-the-three-access-groups-for-the-site-in-azure-ad"></a>步骤 4: 在 Azure AD 中为网站创建三个访问组

您需要在 Azure AD 中创建以下访问组:
  
- 网站管理员 (将包含步骤1中的列表)
    
- 网站成员 (将包含步骤2中的列表)
    
- 网站查看器 (将包含步骤3中的列表)
    
1. 在浏览器中, 转到 Azure 门户, [https://portal.azure.com](https://portal.azure.com)并使用已分配给用户管理管理员或公司管理员角色的帐户的凭据进行登录。
    
2. 在 Azure 门户中，单击“**Azure Active Directory”>“组**”。
    
3. 在“**组 - 所有组**”边栏选项卡上，单击“**+ 新建组**”。
    
4. 在**新组**边栏上:
    
  - 选择 "**组类型**中的**安全性**"。
    
  - 在 "**名称**" 中键入组名称。
    
  - 在 "**组说明**" 中键入组的说明。
    
  - 在“**成员身份**”类型中，选择“**已分配**”。
    
5. 单击“**创建**”，然后关闭“**组**”边栏选项卡。
    
6. 对其他组重复步骤3-5。
    
> [!NOTE]
> 您需要使用 Azure 门户来创建组, 以便他们启用 Office 功能。 如果后来将 SharePoint Online 独立网站配置为具有 Azure 信息保护标签的高度机密网站来加密文件, 并为特定组分配权限, 则必须已在启用 Office 功能的情况下创建允许的组。 Azure AD 组创建后, 无法更改其 Office 功能设置。 
  
下面是具有三个网站访问组的结果配置。
  
![用于部署独立 SharePoint Online 网站的三个访问组。](media/c2557f61-478b-4494-95e9-d79fe5909e8b.png)
  
### <a name="step-5-add-the-user-accounts-to-the-access-groups"></a>步骤 5. 将用户帐户添加到访问组

在此步骤中, 请执行以下操作:
  
1. 将步骤1中的用户列表添加到网站管理员访问组
    
2. 将步骤2中的用户列表添加到网站成员访问组
    
3. 将步骤3中的用户列表添加到 "网站查看者访问" 组
    
如果通过 Active Directory 域服务 (AD DS) 管理用户帐户和组, 请使用常规 AD DS 用户和组管理程序将用户添加到相应的访问组, 并等待与 Office 365 订阅同步。
  
如果通过 Office 365 管理用户帐户和组, 则可以使用 Microsoft 365 管理中心或 PowerShell。 如果有任何访问组的组名称重复, 则应使用 Microsoft 365 管理中心。
  
对于 Microsoft 365 管理中心, 使用已分配有用户帐户管理员或公司管理员角色的用户帐户登录, 并使用组将相应的用户帐户和组添加到相应的访问组。
  
对于 PowerShell, 首先[与 Azure Active Directory PowerShell For Graph 模块进行连接](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)。
  
接下来, 使用以下命令块将单个用户帐户添加到访问组中:
  
```
$userUPN="<UPN of the user account>"
$grpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

> [!TIP]
> 对于包含所有 PowerShell 命令的文本文件和基于您的组和用户帐户名称生成 PowerShell 命令的 Excel 配置工作表, 请下载[独立的 SharePoint Online 团队网站部署工具包](https://gallery.technet.microsoft.com/Isolated-SharePoint-Online-0b364907)。 
  
如果您为文本文件中的任何访问组存储了用户帐户的 Upn, 则可以使用下面的 PowerShell 命令块一次添加所有这些组:
  
```
$grpName="<display name of the access group>"
$fileName="<path and name of the file containing the list of account UPNs>"
$grpID=(Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
Get-Content $fileName | ForEach { $userUPN=$_; Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID $grpID }
```

对于 PowerShell, 使用以下命令块将单个组添加到访问组中:
  
```
$nestedGrpName="<display name of the group to add to the access group>"
$grpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $nestedGrpName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID

```

结果应如下所示:
  
- 网站管理员 Azure AD 组包含网站管理员用户帐户或组
    
- 网站成员 Azure AD 组包含网站成员用户帐户或组
    
- 网站查看器 Azure AD 组包含仅可查看网站内容的用户帐户或组
    
使用 Microsoft 365 管理中心或以下 PowerShell 命令块验证每个访问组的组成员列表:
  
```
$grpName="<display name of the access group>"
Get-AzureADGroupMember -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID | Sort UserPrincipalName | Select UserPrincipalName,DisplayName,UserType
```

下面是通过使用用户帐户或组填充的三个网站访问组生成的配置。
  
![三个使用用户帐户填充的访问组。](media/2320107c-dad6-4c8f-94e5-f6427c125e71.png)
  
## <a name="phase-2-create-and-configure-the-isolated-team-site"></a>阶段 2: 创建和配置独立的团队网站

在此阶段中, 您将创建独立的 SharePoint Online 网站, 并将默认 SharePoint Online 权限级别的权限配置为使用新的基于 Azure AD 的访问组。
  
首先, 使用这些步骤创建 SharePoint Online 团队网站。
  
1. 使用将同时用于管理 SharePoint Online 团队网站的帐户（即 SharePoint Online 管理员帐户）登录管理中心。 如需帮助，请参阅[如何登录到 Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4)。
    
2. 在磁贴列表中，单击“SharePoint”****。
    
3. 在浏览器的新“SharePoint”标签页中，单击“+ 创建网站”。********
    
4. 在“创建网站”页中，单击“团队网站”********。
    
5. 在 "**网站名称**" 中, 键入团队网站的名称。 
    
6. 在 "**团队网站说明" 中,** 键入网站用途的可选说明。
    
7. 在“隐私设置”中，选择“专用 - 仅成员可以访问此网站”，然后单击“下一步”************。
    
8. 在“希望添加哪些人员?”窗格中，单击“完成”********。
    
接下来, 从新的 SharePoint Online 团队网站配置权限。
  
1. 在工具栏中，依次单击设置图标和“网站权限”****。
    
2. 在“网站权限”窗格中，单击“高级权限设置”********。
    
3. 在浏览器的新“权限”标签页中，单击“访问请求设置”********。
    
4. 在 "**访问请求设置**" 对话框中, 清除 "**允许成员" 以共享网站和各个文件和文件夹**, 并**允许访问请求**(以便清除所有三个复选框), 然后单击 **"确定"**。
    
5. 在浏览器的 "**权限**" 选项卡上, 单击** \<** 列表中的 "网站名称"> 成员。
    
6. 在“人员和组”中，单击“新建”********。
    
7. 在 "**共享**" 对话框中, 键入网站成员访问组的名称, 选择它, 然后单击 "**共享**"。
    
8. 单击浏览器上的后退按钮。
    
9. 单击列表中的 " ** \<网站名称"> 所有者**"。
    
10. 在“人员和组”中，单击“新建”********。
    
11. 在 "**共享**" 对话框中, 键入 "网站管理员" 访问组的名称, 选择它, 然后单击 "**共享**"。
    
12. 单击浏览器上的后退按钮。
    
13. 在列表中单击 " ** \<网站名称"> 访问者**。
    
14. 在“人员和组”中，单击“新建”********。
    
15. 在 "**共享**" 对话框中, 键入 "网站查看者访问" 组的名称, 选择它, 然后单击 "**共享**"。
    
16. 关闭浏览器的“权限”标签页****。
    
以下是这些权限设置的结果：
  
- " ** \<网站名称> 所有者**" SharePoint 组包含 "网站管理员" 访问组, 其中所有成员都具有 "**完全控制**" 权限级别。
    
- " ** \<网站名称> 成员**" SharePoint 组包含 "网站成员" 访问组, 其中所有成员都具有 "**编辑**" 权限级别。
    
- " ** \<网站名称> 访问者**" SharePoint 组包含 "网站查看者" 访问组, 其中所有成员都具有 "**读取**" 权限级别。
    
- 禁用成员邀请其他成员或非成员请求访问的功能已被禁用。
    
下面是配置了三个 SharePoint 组的网站的结果配置, 该网站配置为使用三个访问组, 其中填充了用户帐户或 Azure AD 组。
  
![使用访问组和用户帐户的独立 SharePoint Online 网站的最终配置。](media/e7618971-06ab-447b-90ff-d8be3790fe63.png)
  
您和网站成员 (通过其中一个访问组中的组成员身份) 现在可以使用网站的资源进行协作。
  
## <a name="next-step"></a>后续步骤

如果需要更改网站访问组成员身份或创建具有自定义权限的文档文件夹, 请参阅[管理独立的 SharePoint Online 团队网站](manage-an-isolated-sharepoint-online-team-site.md)。
  
## <a name="see-also"></a>另请参阅

[独立 SharePoint Online 团队网站](isolated-sharepoint-online-team-sites.md)
  
[设计独立 SharePoint Online 团队网站](design-an-isolated-sharepoint-online-team-site.md)
  
[管理独立 SharePoint Online 团队网站](manage-an-isolated-sharepoint-online-team-site.md)
  



