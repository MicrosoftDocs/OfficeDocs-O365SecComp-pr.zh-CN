---
title: 使用 Office 365 云应用安全管理 OAuth 应用
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 12/26/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 2062c312-b1e4-4ce7-8cb2-ea39bc0dfdad
description: office 365 中的 OAuth 应用程序安全性帮助您管理用户下载的用于 Office 365 数据的应用程序
ms.openlocfilehash: 0d9916414d55abb73fd99eaf30c3b6df0648b191
ms.sourcegitcommit: 1658be51e2c21ed23bc4467a98af74300a45b975
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/26/2019
ms.locfileid: "30862584"
---
# <a name="manage-oauth-apps-using-office-365-cloud-app-security"></a>使用 Office 365 云应用安全管理 OAuth 应用

|评估 * *\>**|规划 * *\>**|部署 * *\>**|利用率 * * * *|
|:-----|:-----|:-----|:-----|
|[开始评估](office-365-cas-overview.md) <br/> |[开始规划](get-ready-for-office-365-cas.md) <br/> |[开始部署](turn-on-office-365-cas.md) <br/> |你在这里!  <br/> [后续步骤](#next-steps)<br/> |
   
人们喜欢应用程序, 并且他们经常下载它们, 尤其是人们认为, 人们可以通过更轻松地获取工作或学校信息, 从而节省时间。 但是, 某些应用可能会对您的组织造成安全风险, 具体取决于他们访问的信息以及它们如何处理这些信息。 使用[Office 365 云应用安全](office-365-cas-overview.md), 如果您是全局管理员或安全管理员, 则可以管理您的组织的 OAuth 应用程序。 您可以查看使用 Office 365 数据的应用程序, 这些应用程序具有哪些权限, 等等。 
  
本文介绍在哪里可以转到管理 OAuth 应用程序、如何批准、禁止或报告应用程序, 以及如何创建应用程序查询。
  
## <a name="how-to-find-the-manage-oauth-apps-page"></a>如何查找 "管理 OAuth 应用程序" 页

> [!NOTE]
> 在 Office 365 云应用安全门户中管理 OAuth 应用程序。 您必须是全局管理员或安全管理员才能执行以下任务。 若要了解详细信息, 请参阅[Office 365 &amp;安全合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。 
  
1. 转到云应用安全门户 ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) 并登录。
  
2. 选择**调查** \> **OAuth 应用程序**。<br/>![在 O365 CAS 门户中, 选择 "调查"。](media/OCAS-OAuthApps.png)<br/>
  
## <a name="what-youll-see-on-the-manage-oauth-apps-page"></a>您将在 "管理 OAuth 应用程序" 页上看到的内容

下表介绍了 "管理 OAuth 应用" 页上可用的控件和选项。
  
|**项**|**说明**|
|:-----|:-----|
|应用程序查询栏中的基本图标  <br/> ![指示查询的基本查询视图的图标](media/a459bc51-e86b-43d5-a0ee-661b9fb4afc9.png)|选择此选项以切换到 "高级" 视图。  <br/> (如果看到的是 "**基本**", 则使用的是 "高级" 视图)  <br/> |
|应用程序查询栏中的高级图标  <br/> ![指示查询的高级查询视图的图标](media/9958d832-2c81-45ed-a642-d926310ba6b6.png)|选择此选项以切换到 "基本" 视图。  <br/> (如果看到 "**高级**", 则使用的是 "基本" 视图。)  <br/> |
|在应用程序列表中打开或关闭所有详细信息图标  <br/> ![单击此图标可打开或关闭所有应用的所有详细信息](media/018fa996-10e8-48ff-986e-55f2b69a5753.png)|选择此图标可查看有关每个应用程序的更多或更少详细信息。  <br/> |
|在应用程序列表中导出图标  <br/> ![单击此图标可导出所有应用程序的 csv 文件](media/98446851-fd96-4d09-9bb0-831db33090c1.png)|选择此图标可导出包含应用程序列表的 CSV 文件、每个应用程序的用户数、与应用程序关联的权限、权限级别、应用程序状态和社区使用级别。  <br/> |
|名称  <br/> |使用此名称可查看应用程序的名称。 选择名称以查看详细信息, 如其说明、发布者、应用程序网站和应用 ID。  <br/> |
|授权人  <br/> |使用此方法可查看有多少用户已授权应用程序访问其 Office 365 帐户。 选择号码以查看详细信息, 如用户帐户列表。  <br/> |
|权限级别  <br/> ![指示应用程序的 permisiions 级别的图标](media/aaebdd29-35b6-4c62-aef1-7c7817bd803d.png)|使用此方法可查看应用对 Office 365 数据的访问量。 权限级别指示 "**低**"、"**中**" 或 "**高**", 其中**低**可能表明应用程序仅访问用户的配置文件和名称。 选择要查看详细信息的级别, 例如授予应用程序的权限、社区使用以及[调控日志](suspend-or-restore-an-account-in-ocas.md)中的相关活动。  <br/> |
|上次授权 <br/> |使用此操作可查看 OAuth 应用上次授权访问组织的 Office 365 数据的日期和时间。 <br/>  |
|操作<br/>![OAuth 应用程序](media/OCAS-OAuthAppApproveBanReport.png)<br/> |使用此方法可查看或将应用程序标记为已批准或禁止, 将 OAuth 应用报告给 Microsoft, 或将其保留为未定。  <br/> |
   
## <a name="mark-an-app-as-approved"></a>将应用程序标记为已批准

在 "**管理 OAuth 应用**程序" 页上, 找到要批准的应用程序, 然后选择 "将**应用标记为已批准**" 图标。 
  
![选择 "将应用标记为已批准" 图标](media/OCAS-MarkOAuthApproved.png)
  
图标将变为绿色, 并且应用程序将针对所有 Office 365 用户进行审批。
  
> [!NOTE]
> 当您将某个应用程序标记为已批准时, 最终用户将不会有任何影响。 以可视方式标记已批准的应用程序有助于将它们与尚未审阅的应用程序分开。 
  
## <a name="ban-an-app"></a>禁止应用

1. 在 "**管理 OAuth 应用**程序" 页上, 找到要禁止的应用程序, 然后选择 "**标记应用" 作为 "禁止**" 图标。<br/>![选择 "标记应用" 作为 "禁止" 图标](media/OCAS-MarkOAuthBanned.png)
  
2. 在通知消息框中, 保留现有文本, 或自定义文本。 选择是否让用户知道他们的应用程序已被禁止。 <br/>![阻止的应用程序的邮件模板](media/6d132700-5f7f-472c-bfb5-a44549e69c16.jpg)<br/>
  
3. 选择 "**禁止应用**"。

## <a name="report-an-oauth-app-to-microsoft"></a>向 Microsoft 报告 OAuth 应用

如果要将 OAuth 应用程序提交到 Microsoft 进行分析, 可以报告该应用程序。

1. 在 "**管理 OAuth 应用**程序" 页上, 找到要提交以供分析的应用程序。

2. 选择垂直省略号, 然后选择 "**报告应用 ...**"。<br/>![报告 OAuth 应用](media/OCAS-MarkOAuthReported.png)<br/>

3. 在 "**报告此应用程序**" 对话框中, 使用下拉列表指示你的关注。 默认情况下, 将选择**此应用程序是恶意**的。 不过, 您可以选择其他可用选项之一。 <br/>![报告 OAuth 应用](media/OCAS-ReportOAuthApp.png)<br/>

4. 适合保留选择 "联系" 选项, 并确认 (或编辑) 列出的电子邮件地址。

5. Choose **Submit**. 
    
## <a name="create-an-app-query"></a>创建应用程序查询

我们建议使用 "高级" 视图, 如下所示: 

![高级视图](media/OCAS-OAuthAppsAdvQueryView.png)

在应用程序查询栏中, 如果您看到 "**高级**", 则使用的是 "基本" 视图。 单击 (或点击) "**高级**" 以转到 "高级" 视图。 

![基本视图](media/OCAS-OAuthAppsBasicQueryView.png)
    
1. 在查询栏中, 使用 "**选择筛选器**" 列表选择一个选项。 
    - **应用**具有特定名称的应用程序
    - **应用程序状态**基于其状态 ("已批准"、"禁止" 或 "不确定") 的应用程序
    - **社区使用**基于社区使用级别的应用程序 (极少、不常见或常见)
    - **权限级别**基于某些权限级别的应用程序 
    - **权限**需要特定权限的应用程序
    - **发布服务器** 来自特定发布者的应用程序
    - **用户**某个用户授权的应用程序
   
2. 选择 "**等于**或**不等于**", 然后为您的筛选器指定值。
    
3. 若要添加更多筛选器, 请选择加号 (![添加用于查询应用程序的筛选器图标](media/771b2958-67cd-4e14-9302-283ef238cae5.jpg)), 然后重复步骤2和3。
    
4. 若要删除筛选器, 请选择 x (![删除用于查询应用程序的筛选器图标](media/5339277f-555d-4749-8dcc-d2574250556e.jpg)) 旁边的筛选器名称。
    
将自动应用筛选器, 并相应地更新 "应用" 列表。
  
## <a name="next-steps"></a>后续步骤

- [查看警报并对其执行操作](review-office-365-cas-alerts.md)
    
- 查看[适用于 Office 365 云应用程序安全性的 Web 流量日志和数据源](web-traffic-logs-and-data-sources-for-ocas.md)
    
- 查看[Office 365 云应用安全性的利用率活动](utilization-activities-for-ocas.md)
    

