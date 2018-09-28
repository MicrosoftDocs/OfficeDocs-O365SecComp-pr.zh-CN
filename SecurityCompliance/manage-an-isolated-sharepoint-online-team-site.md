---
title: 管理独立 SharePoint Online 团队网站
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_Solutions
ms.assetid: 79a61003-4905-4ba8-9e8a-16def7add37c
description: 摘要： 管理您的独立的 SharePoint Online 团队网站使用这些过程。
ms.openlocfilehash: 22b4cbbdd926635286d23570e1f61b64529d0e76
ms.sourcegitcommit: e0f016aca7befc8806233a492ee916cbe646094f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/27/2018
ms.locfileid: "25345934"
---
# <a name="manage-an-isolated-sharepoint-online-team-site"></a>管理独立 SharePoint Online 团队网站

 **摘要：** 管理您的独立的 SharePoint Online 团队网站使用这些过程。
  
本文介绍为独立的 SharePoint Online 团队网站的常见管理操作。
  
## <a name="add-a-new-user"></a>添加新用户

当某个新人加入网站时，您必须决定在网站中的参与其级别：
  
- 管理： 将新的用户帐户添加到网站管理员访问组
    
- 活动的协作： 向网站添加用户帐户成员访问组
    
- 查看： 将用户帐户添加到网站查看器访问组
    
如果您在管理用户帐户和组通过 Windows Server Active Directory (AD)，将相应的用户添加到适当的访问组使用您正常的 Windows Server AD 用户和组管理过程并等待与同步您Office 365 订阅。
  
如果您在管理用户帐户和组通过 Office 365，您可以使用 Office 管理中心或 Microsoft PowerShell:
  
- 对于 Office 管理中心中，使用已分配的用户帐户管理员或公司管理员角色的用户帐户登录，并使用组将相应的用户添加到适当的访问组。
    
- Powershell，第一个[使用 Azure Active Directory V2 PowerShell 模块的连接](https://go.microsoft.com/fwlink/?linkid=842218)。若要向其用户主体名称 (UPN) 与 access 组添加用户帐户，使用以下 PowerShell 命令块：
    
```
$userUPN="<UPN of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

> [!TIP]
> 对于包含所有 PowerShell 命令和 Excel 的文本文件配置工作表中生成 PowerShell 命令的基于您的组和用户帐户名，下载[独立 SharePoint Online 团队网站部署工具包](https://gallery.technet.microsoft.com/Isolated-SharePoint-Online-0b364907)。 

若要向其显示名称与 access 组添加用户帐户，请使用以下 PowerShell 命令块：

```
$userDisplayName="<display name of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userDisplayName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="add-a-new-group"></a>添加新组

若要添加到整个组的访问，必须决定参与组的所有成员的站点中的级别：
  
- 管理： 将组添加到网站管理员访问组
    
- 活动的协作： 将组添加到网站成员访问组
    
- 查看： 将组添加到网站查看器访问组
    
如果您在管理用户帐户和通过 Windows Server AD 的组，将相应的组添加到适当的组使用普通的 Windows Server AD 用户和组管理过程并等待与 Office 365 订阅的同步。
  
如果您在管理用户帐户和组通过 Office 365，您可以使用 Office 管理中心或 PowerShell:
  
- 对于 Office 管理中心中，使用已分配的用户帐户管理员或公司管理员角色的用户帐户登录，并使用组将相应的组添加到适当的访问组。
    
- Powershell，第一个[使用 Azure Active Directory V2 PowerShell 模块的连接](https://go.microsoft.com/fwlink/?linkid=842218)。然后，使用以下 PowerShell 命令：
 
```
$newGroupName="<display name of the new group to add>"
$siteGrpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $newGroupName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $siteGrpName }).ObjectID
```

## <a name="remove-a-user"></a>删除用户

必须从网站删除某人的访问，它们从组中删除访问它们所当前基于其参与网站成员：
  
- 管理： 删除网站管理员访问组中的用户帐户
    
- 活动的协作： 删除网站成员访问组中的用户帐户
    
- 查看： 删除网站的查看者访问组中的用户帐户
    
如果您在管理用户帐户和组通过 Windows Server AD，从使用普通的 Windows Server AD 用户和组管理过程的适当的访问组中删除相应的用户并等待与 Office 365 同步订阅。
  
如果您在管理用户帐户和组通过 Office 365，您可以使用 Office 管理中心或 PowerShell:
  
- 为 Office 管理中心中，使用已分配的用户帐户管理员或公司管理员角色的用户帐户登录并使用组来从适当的访问组中删除相应的用户。
    
- Powershell，第一个[使用 Azure Active Directory V2 PowerShell 模块的连接](https://go.microsoft.com/fwlink/?linkid=842218)。若要从其 UPN 与访问组中删除的用户帐户，请使用以下 PowerShell 命令块：
    
```
$userUPN="<UPN of the user account>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

若要从其显示名称访问组中删除的用户帐户，请使用以下 PowerShell 命令块：
    
```
$userDisplayName="<display name of the user account>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.DisplayName -eq $userDisplayName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="remove-a-group"></a>删除组

删除整个组的访问权限，您可以从它们所当前基于其参与网站成员访问组中删除组：
  
- 管理： 删除从网站管理员访问组的组
    
- 活动的协作： 删除从网站成员访问组的组
    
- 查看： 删除从网站查看器访问组的组
    
如果您在管理用户帐户和通过 Windows Server Active Directory 组，从使用您正常的 Windows Server AD 用户和组管理过程的适当的访问组中删除相应的组并等待与同步您Office 365 订阅。
  
如果您在管理用户帐户和组通过 Office 365，您可以使用 Office 管理中心或 PowerShell:
  
- 为 Office 管理中心中，使用已分配的用户帐户管理员或公司管理员角色的用户帐户登录并使用组来从适当的访问组中删除相应的组。
    
- Powershell，第一个[使用 Azure Active Directory V2 PowerShell 模块的连接](https://go.microsoft.com/fwlink/?linkid=842218)。    
若要从使用其显示名称的访问组中删除组，请使用以下 PowerShell 命令块：
    
```
$groupMemberName="<display name of the group to remove>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="create-a-documents-subfolder-with-custom-permissions"></a>使用自定义权限创建的文档子文件夹

在某些情况下，使用隔离网站内的人员的子集需要进行协作的更多专用位置。对于 SharePoint Online 网站，您可以在网站的文档文件夹中创建子文件夹，并分配自定义权限。那些没有权限将不会看到子文件夹。
  
要创建自定义权限文档子文件夹，请执行以下操作：
  
1. 使用网站的管理员访问组的成员的帐户登录到 Office 365。为了帮助，请参阅[从何处登录到 Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4)。
    
2. 转到独立的工作组网站，并单击**文档**。
    
3. 浏览到的文件夹中文档文件夹，将包含自定义权限的子文件夹，创建文件夹，然后再打开它。
    
4. 单击"共享"。
    
5. 单击**与共享 > 高级**。
    
6. 单击**停止继承权限**，然后单击**确定**。
    
7. 单击"共享"。
    
8. 单击**与共享 > 高级**。
    
9. 单击**授予权限 > 与共享 > 高级**。
    
10. 在权限页上单击**\<网站名称 > 列表中的成员**。
    
11. 在**\<网站名称 > 成员**页上，选择网站成员访问组旁的复选标记，单击**操作**，单击**删除用户组**，然后单击**确定**。
    
12. 若要添加此子文件夹的特定成员，请单击**新建 > 将用户添加**。
    
13. 在**共享**对话框中，键入可以协作处理的子文件夹中的文件，然后单击**共享**的用户帐户的名称。
    
14. 刷新网页以查看新的结果。
    
15. 在左侧导航窗格中的**组**下, 单击**\<网站名称 > 访问者**组并用于指定一组可以查看文件的子文件夹中 （根据需要） 的用户帐户的步骤 11 至 14。
    
16. 在左侧导航窗格中的**组**下, 单击**\<网站名称 > 所有者**组和步骤 11 至 14 用于指定的用户帐户 （根据需要） 可以管理子文件夹中的权限集。
    
17. 关闭浏览器中的**人员和组**选项卡。
    
## <a name="see-also"></a>另请参阅

[独立 SharePoint Online 团队网站](isolated-sharepoint-online-team-sites.md)
  
[设计独立 SharePoint Online 团队网站](design-an-isolated-sharepoint-online-team-site.md)

[部署独立 SharePoint Online 团队网站](deploy-an-isolated-sharepoint-online-team-site.md)



