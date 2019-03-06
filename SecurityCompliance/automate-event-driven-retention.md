---
title: 自动执行事件驱动的保留
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 本主题介绍如何使用 Microsoft 365 REST API 设置业务流程以通过事件自动执行保留。
ms.openlocfilehash: bfd33550eea447fb787ef981f9b0d7a36274b2cc
ms.sourcegitcommit: ed822a776d3419853453583e882f3c61ca26d4b2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "30410857"
---
# <a name="automate-event-based-retention"></a>自动执行基于事件的保留

了解组织中呈爆炸式增长的内容以及它们如何变为 ROT（冗余、过时、无关紧要的）内容是一件头等大事。为了继续应对法律、业务和法规遵从性挑战，企业必须能够保留和保护重要信息，并快速找到相关信息。仅保留重要的相关信息是企业取得成功的关键。

因此，组织可以利用 Office 365 安全与合规中心中的保留解决方案。可以使用[保留标签](labels.md)触发保留。保留标签允许选择[基于特定事件的保留期](event-driven-retention.md)。通常，保留期基于已知日期，如内容的创建日期或上次修改日期。但是，组织还要求根据事件的发生处理内容，例如在员工离开组织 7 年后进行处理。

为了确保内容的合规处理，必须知道事件何时发生。随着内容量的快速增长，以及时且合规的方式保留和处理内容变得更具挑战性。

基于事件的保留可解决这个问题。本主题介绍如何使用 Microsoft 365 REST API 设置业务流程以通过事件自动执行保留。

## <a name="about-event-based-retention"></a>关于基于事件的保留

组织可以分为小型、中型或大型组织。每天创建和管理的业务文档、法律文档、员工文件，合同和产品文档的数量正在急剧增加。

例如，每天都有数十和数百名员工加入和离开组织。人力资源部门需要根据业务需求继续创建、更新或删除与员工相关的文档。此流程受为企业制定的不同保留策略的约束：

- **内容的保留期可以是已知日期**，如内容创建、上次修改或标记的日期。例如，你可以在创建文档后将其保留 7 年，然后将其删除。

- **内容保留期也可以是未知日期**。例如，对于保留标签，你还可以根据特定类型事件的发生时间（如员工离开组织）来确定保留期。

该事件会触发保留期的开始，并且会对已为该事件类型应用标签的所有内容强制执行标签的保留操作。这称为基于事件的保留 - 有关详细信息，请参阅[事件驱动保留概述](event-driven-retention.md)。

## <a name="set-up-event-based-retention"></a>设置基于事件的保留

本节介绍在保留内容之前需要执行的操作。

### <a name="identify-roles"></a>标识角色

确定执行记录管理任务的组织中的不同角色，这些角色将负责有效且高效地保留业务文档。

  | **角色**| **角色**|
  | - | - |
  | 安全与合规中心管理员 | 在 SharePoint 中创建保留事件类型、保留标签和记录存储库 |
  | 记录经理                                  | 提供保留策略和保留计划指南和合规性详细信息   |
  | 系统管理员（企业）                          | 设置和管理外部系统以使用 Microsoft 365                       |
  | 信息工作者                               | 管理业务流程的生命周期（人力资源、财务、IT 等）                 |

### <a name="set-up-the-security--compliance-center"></a>设置安全与合规中心
  
1. 合规性管理员创建事件类型 – 例如，雇佣终止或合同到期或产品制造终止（请参阅[事件保留文章](https://docs.microsoft.com/zh-CN/office365/securitycompliance/event-driven-retention)中的分步流程）
    
1. 合规性管理员根据事件创建保留标签，并将标签与事件类型相关联
    
1. 保留标签具有 4 种类型的触发器：
            
    1. 创建日期
                
    1. 上次修改时间
                
    1. 标签日期（标记内容的时间）
                
    1. 基于事件
    
1. 合规性管理员发布标签

### <a name="set-up-sharepoint"></a>设置 SharePoint
   
若要创建记录存储库，合规性管理员需要：

1. 创建 SharePoint 网站。

1. 执行下列操作之一：
        
    - 创建 SharePoint 库：在库级别设置基于事件的标签。有关详细信息，请参阅[将默认保留标签应用于 SharePoint 库、文件夹或文档集中的所有内容](labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set)。
          
    - 在 SharePoint 中设置文档集。有关详细信息，请参阅[文档集简介](https://support.office.com/zh-CN/article/Introduction-to-Document-Sets-3DBCD93E-0BED-46B7-B1BA-B31DE2BCD234)。
      
1. 为每个员工文档集分配资产 ID（资产 ID 是组织使用的产品名称或代码，例如员工编号可以是资产 ID）。通过将资产 ID 分配给文件夹，该文件夹中的每个项目都会自动继承相同的资产 ID。这意味着所有项目的保留期都可以由同一事件触发。

## <a name="ways-to-trigger-event-based-retention"></a>触发基于事件的保留的方法

可通过两种方法触发基于事件的保留：

- **使用安全与合规中心 UI** 此流程适用于一次保留较少内容或者不经常触发保留的情形，例如每月或每年保留一次。有关此方法的详细信息，请参阅[事件驱动保留概述](event-driven-retention.md)。但是，这种触发保留的方法可能比较耗时且容易出错，这会影响可伸缩性。用于触发保留的自动化无缝解决方案可以增强数据的安全性和合规性。

- **使用 M365 REST API** 当一次保留大量内容和/或触发保留的频率通常是每天或每周时，可以使用此流程。该流程会检测你的业务线系统中何时发生事件，然后在安全与合规中心自动创建相关事件。每次发生事件时，你无需在 UI 中手动创建事件。

使用 REST API 有两种选择：

- **Microsoft Flow 或类似的应用程序**可用于自动触发事件的发生。Microsoft Flow 是用于连接到其他系统的协调程序。使用 Microsoft Flow 不需要自定义解决方案。

- **使用 PowerShell 或 HTTP 客户端调用 REST API **使用 PowerShell（版本 6 或更高版本）调用 Microsoft 365 REST API 以创建事件。 

Rest API 是一个支持多组 HTTP 操作（方法）的服务终结点，提供对服务资源的创建/检索/更新/删除操作权限 - 有关详细信息，请参阅 [REST API 请求/响应组件](https://docs.microsoft.com/zh-CN/rest/api/gettingstarted/#components-of-a-rest-api-requestresponse)。在这种情况下，通过使用 Microsoft 365 REST API，可以使用 POST 和 GET 操作（方法）来创建和检索事件。

## <a name="example-scenarios"></a>示例场景

让我们以如下场景为例。

### <a name="scenario-1-employees-leaving-the-organization"></a>场景 1：员工离开组织 

组织为每个员工创建和存储许多员工相关文档。这些文档在每位员工的雇佣期内进行管理和保留。但是，当员工离开组织或终止雇佣关系时，组织有义务根据法律和业务要求在规定的时间内保留该员工的文档。

现在，如果每天有多名员工离开组织，组织必须在每天触发数百甚至数千个文档的保留期。

除此之外，还需要根据员工记录的类型计算每个员工的保留期，即雇佣终止日期 + 天数、月数或年数。例如，同一员工的职工薪酬档案与福利档案可能需要不同的保留期。

下图显示如何将多个标签与单个事件关联。在此处，员工薪酬标签下的所有文件和员工福利标签下的所有文件都与单个事件相关联，即员工离开组织。每个不同的文件都有不同的保留期。因此，当员工离开组织时，每个标签中的这些文件都会经历不同的保留期。为每个员工的每种文件类型或标签触发所有这些不同的保留期是一项极具挑战的任务。想象一下，为多名员工做这件事将会如何。

![事件类型、事件和标签的关系图](media/automate-event-driven-retention-event-diagram-employee-leaving.png)

为多个员工触发这些不同保留期的自动化流程将节省时间、无错误且极为高效。

**为此场景配置基于事件的自动保留：**

![针对员工离开组织的场景的角色和操作关系图](media/automate-event-driven-retention-employee-termination-diagram.png)

  - 管理员为文档集创建员工文件夹，如 Jane Doe、John Smith。

  - 管理员将员工文件（如福利、工资单、员工薪酬）添加到每个员工文件夹中

  - 管理员为每个员工文件夹分配资产 ID。 

  - SCC 管理员

  - 登录到安全与合规中心

  - SCC 管理员在安全与合规中心创建与员工相关的事件类型，如“雇佣终止”、“员工雇用”事件。

  - SCC 管理员在安全与合规中心创建“员工保留”标签。

  - 此“员工保留”标签将手动或自动发布并应用于 SharePoint 中的员工文件

  - HR 管理系统（如 Workday）可以与 Microsoft Flow 一起定期运行以管理员工文件

  - 如果员工离开组织，Flow 将触发 M365 基于事件的保留 REST API，该 API 将开始特定员工文件的保留期。

#### <a name="using-microsoft-flow"></a>使用 Microsoft Flow

步骤 1 - 使用 Microsoft 365 REST API 创建用于创建事件的流

![使用流创建事件](media/automate-event-driven-retention-flow-1.png)

![使用流调用 REST API](media/automate-event-driven-retention-flow-2.png)

##### <a name="create-an-event"></a>创建事件

用于调用 REST API 的示例代码

<table>
<thead>
<tr class="header">
<th>方法</th>
<th>POST</th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>URL</td>
<td>https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent)</td>
<td></td>
</tr>
<tr class="even">
<td>标头</td>
<td>Content-Type</td>
<td>application/atom+xml</td>
</tr>
<tr class="odd">
<td>正文</td>
<td><p>&lt;?xml version='1.0' encoding='utf-8' standalone='yes'?&gt;</p>
<p>&lt;entry xmlns:d='http://schemas.microsoft.com/ado/2007/08/dataservices'</p>
<p>xmlns:m='http://schemas.microsoft.com/ado/2007/08/dataservices/metadata'</p>
<p>xmlns='http://www.w3.org/2005/Atom'&gt;</p>
<p>&lt;category scheme='http://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' /&gt;</p>
<p>&lt;updated&gt;9/9/2017 10:50:00 PM&lt;/updated&gt;</p>
<p>&lt;content type='application/xml'&gt;</p>
<p>&lt;m:properties&gt;</p>
<p>&lt;d:Name&gt;Employee Termination &lt;/d:Name&gt;</p>
<p>&lt;d:EventType&gt;99e0ae64-a4b8-40bb-82ed-645895610f56&lt;/d:EventType&gt;</p>
<p>&lt;d:SharePointAssetIdQuery&gt;1234&lt;/d:SharePointAssetIdQuery&gt;</p>
<p>&lt;d:EventDateTime&gt;2018-12-01T00:00:00Z &lt;/d:EventDateTime&gt;</p>
<p>&lt;/m:properties&gt;</p>
<p>&lt;/content&gt;</p>
<p>&lt;/entry&gt;</p></td>
<td></td>
</tr>
<tr class="even">
<td>身份验证</td>
<td>基本</td>
<td></td>
</tr>
<tr class="odd">
<td>用户名</td>
<td>“Complianceuser”</td>
<td></td>
</tr>
<tr class="even">
<td>密码</td>
<td>“Compliancepassword”</td>
<td></td>
</tr>
</tbody>
</table>

##### <a name="available-parameters"></a>可用参数

<table>
<thead>
<tr class="header">
<th><strong>参数</strong></th>
<th><strong>说明</strong></th>
<th><strong>注释</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>&lt;d:Name&gt;&lt;/d:Name&gt;</td>
<td>为事件提供唯一的名称，</td>
<td>不能包含尾随空格和以下字符：% * \ &amp; &lt; &gt; | # ? , : ;</td>
</tr>
<tr class="even">
<td>&lt;d:EventType&gt;&lt;/d:EventType&gt;</td>
<td>输入事件类型名称（或 Guid），</td>
<td>示例：“雇佣终止”。事件类型必须与保留标签相关联。</td>
</tr>
<tr class="odd">
<td>&lt;d:SharePointAssetIdQuery&gt;&lt;/d:SharePointAssetIdQuery&gt;</td>
<td>输入“ComplianceAssetId:” + 员工 Id</td>
<td>示例：&quot;ComplianceAssetId:12345&quot;</td>
</tr>
<tr class="even">
<td>&lt;d:EventDateTime&gt;&lt;/d:EventDateTime&gt;</td>
<td>事件日期和时间</td>
<td><p>格式：yyyy-MM-ddTHH:mm:ssZ，示例：</p>
<p>2018-12-01T00:00:00Z</p></td>
</tr>
</tbody>
</table>

##### <a name="response-codes"></a>响应代码

| **响应代码** | **说明**       |
| ----------------- | --------------------- |
| 302               | 重定向              |
| 201               | 已创建               |
| 403               | 授权失败  |
| 401               | 身份验证失败 |

##### <a name="get-events-based-on-time-range"></a>根据时间范围获取事件

<table>
<thead>
<tr class="header">
<th>方法</th>
<th>GET</th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>URL</td>
<td><ol start="4" type="1">
<li><p>https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent?BeginDateTime=2019-01-11&amp;EndDateTime=2019-01-16</p></li>
</ol></td>
<td></td>
</tr>
<tr class="even">
<td>标头</td>
<td>Content-Type</td>
<td>application/atom+xml</td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>身份验证</td>
<td>基本</td>
<td></td>
</tr>
<tr class="odd">
<td>用户名</td>
<td>“Complianceuser”</td>
<td></td>
</tr>
<tr class="even">
<td>密码</td>
<td>“Compliancepassword”</td>
<td></td>
</tr>
</tbody>
</table>

##### <a name="response-codes"></a>响应代码

| **响应代码** | **说明**                   |
| ----------------- | --------------------------------- |
| 200               | 正常，atom+ xml 中的事件列表 |
| 404               | 未找到                         |
| 302               | 重定向                          |
| 401               | 授权失败              |
| 403               | 身份验证失败             |

##### <a name="get-an-event-by-id"></a>按 ID 获取事件。

| 方法         | GET   |                      |
| -------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | -------------------- |
| URL            | [https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent(‘174e9a86-74ff-4450-8666-7c11f7730f66’)](https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent\('174e9a86-74ff-4450-8666-7c11f7730f66'\)) |                      |
| 标头         | Content-Type                                                                                                                                                                                                                                                       | application/atom+xml |
| 身份验证 | 基本                                                                                                                                                                                                                                                              |                      |
| 用户名       | “Complianceuser”                                                                                                                                                                                                                                                   |                      |
| 密码       | “Compliancepassword”                                                                                                                                                                                                                                               |                      |

##### <a name="response-codes"></a>响应代码

| **响应代码** | **说明**                                      |
| ----------------- | ---------------------------------------------------- |
| 200               | 正常，响应正文包含 atom+xml 中的事件 |
| 404               | 未找到                                            |
| 302               | 重定向                                             |
| 401               | 授权失败                                 |
| 403               | 身份验证失败                                |

##### <a name="get-an-event-by-name"></a>按名称获取事件

| 方法         | GET       |                      |
| -------------- | -------------------------------------------------------------------------------------------------------------------------------------------- | -------------------- |
| URL            | <https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent('EventByRESTPost-2226bfebcc2841a8968ba71f9516b763')> |                      |
| 标头        | Content-Type                                                                                                                                 | application/atom+xml |
| 身份验证 | 基本                                                                                                                                        |                      |
| 用户名       | “Complianceuser”                                                                                                                             |                      |
| 密码       | “Compliancepassword”                                                                                                                         |                      |

##### <a name="response-codes"></a>响应代码

| **响应代码** | **说明**                                      |
| ----------------- | ---------------------------------------------------- |
| 200               | 正常，响应正文包含 atom+xml 中的事件 |
| 404               | 未找到                                            |
| 302               | 重定向                                             |
| 401               | 授权失败                                 |
| 403               | 身份验证失败                                |

#### <a name="using-powershell-ver6-or-higher-or-any-http-client"></a>使用 PowerShell（版本 6 或更高版本）或任何 HTTP 客户端

步骤 1：连接到 PowerShell。

步骤 2：运行以下脚本。

<table>
<tbody>
<tr class="odd">
<td><p>param([string]$baseUri)</p>
<p>$userName = &quot;UserName&quot;</p>
<p>$password = &quot;Password&quot;</p>
<p>$securePassword = ConvertTo-SecureString $password -AsPlainText -Force</p>
<p>$credentials = New-Object System.Management.Automation.PSCredential($userName, $securePassword)</p>
<p>$EventName=&quot;EventByRESTPost-$(([Guid]::NewGuid()).ToString('N'))&quot;</p>
<p>Write-Host &quot;Start to create an event with name: $EventName&quot;</p>
<p>$body = &quot;&lt;?xml version='1.0' encoding='utf-8' standalone='yes'?&gt;</p>
<p>&lt;entry xmlns:d='http://schemas.microsoft.com/ado/2007/08/dataservices'</p>
<p>xmlns:m='http://schemas.microsoft.com/ado/2007/08/dataservices/metadata'</p>
<p>xmlns='http://www.w3.org/2005/Atom'&gt;</p>
<p>&lt;category scheme='http://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' /&gt;</p>
<p>&lt;updated&gt;7/14/2017 2:03:36 PM&lt;/updated&gt;</p>
<p>&lt;content type='application/xml'&gt;</p>
<p>&lt;m:properties&gt;</p>
<p>&lt;d:Name&gt;$EventName&lt;/d:Name&gt;</p>
<p>&lt;d:EventType&gt;e823b782-9a07-4e30-8091-034fc01f9347&lt;/d:EventType&gt;</p>
<p>&lt;d:SharePointAssetIdQuery&gt;'ComplianceAssetId:123'&lt;/d:SharePointAssetIdQuery&gt;</p>
<p>&lt;/m:properties&gt;</p>
<p>&lt;/content&gt;</p>
<p>&lt;/entry&gt;&quot;</p>
<p>$event = $null</p>
<p>try</p>
<p>{</p>
<p>$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri &quot;$baseUri/ComplianceRetentionEvent&quot; -ContentType &quot;application/atom+xml&quot; -Authentication Basic -Credential $credentials -MaximumRedirection 0</p>
<p>}</p>
<p>catch</p>
<p>{</p>
<p>$response = $_.Exception.Response</p>
<p>if($response.StatusCode -eq &quot;Redirect&quot;)</p>
<p>{</p>
<p>$url = $response.Headers.Location</p>
<p>Write-Host &quot;redirected to $url&quot;</p>
<p>$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri $url -ContentType &quot;application/atom+xml&quot; -Authentication Basic -Credential $credentials -MaximumRedirection 0</p>
<p>}</p>
<p>}</p>
<p>$event | fl *</p></td>
</tr>
</tbody>
</table>

#### <a name="verify-the-outcome-in-both-options"></a>验证两个选项的结果

步骤 1：转到安全与合规中心

步骤 2：单击“数据治理”下的“事件”

步骤 3：验证已创建事件。

同样，上述用于自动执行基于事件的保留的选项也可用于以下场景。

### <a name="scenario-2-contracts-expiring"></a>场景 2：合同到期

对于与客户、供应商和合作伙伴签订的单份合同，组织可能拥有多条记录。这些文档可以驻留在 SharePoint 等文档库中。合同的终止决定了与合同关联的文档保留期的开始。例如：与合同相关的所有记录都需要在合同到期后保留 5 年。触发 5 年保留期的事件是合同到期。

客户关系管理 (CRM) 系统可以与 Microsoft 365 一起使用，用于触发合同文档的保留。

**为此场景配置基于事件的自动保留：**

![针对合同到期场景的角色和任务关系图](media/automate-event-driven-retention-contract-expiration.png)

  - 管理员为每种合同类型创建一个包含各种文件夹的 SharePoint 库。

  - 管理员将合同文件（如许可合同、开发合同）添加到每个合同文件夹

  - 管理员为每个合同文件夹分配资产 ID

  - SCC 管理员登录到安全与合规中心

  - SCC 管理员在安全与合规性中心创建与合同相关的事件类型，如“合同创建”和“合同到期”事件。

  - SCC 管理员在安全与合规中心创建“合同到期”标签。

  - 此“合同到期”标签将手动或自动发布并应用于 SharePoint 中的合同文件

  - 合同管理系统可以与 Microsoft Flow 或类似的应用程序一起定期运行以管理合同文件

  - 如果合同到期，Microsoft Flow 将触发 M365 基于事件的保留 REST API，该 API 将开始特定合同文件的保留期。

### <a name="scenario-3-end-of-product-manufacturing"></a>场景 3：产品制造终止

一家生产不同产品系列的制造公司创建了许多制造规格和定价文件。当不再生产某款产品时，与该产品相关的所有规格和文件都需要在产品生存期结束后的特定时间内保留。

企业资源规划 (ERP) 系统可以与 Microsoft 365 和 Microsoft Flow 一起使用，用于触发保留。

**为此场景配置基于事件的自动保留：**

![产品生命周期场景的角色和任务关系图](media/automate-event-driven-retention-product-lifecycle-expiration.png)

  - 管理员在文档集中创建产品文件夹，如产品 1、产品 2 等。

  - 管理员将产品文件（如制造规格、产品定价、产品许可）添加到每个产品文件夹中

  - 管理员为每个产品文件夹分配资产 ID。

  - SCC 管理员登录到安全与合规中心

  - SCC 管理员在安全与合规中心创建与员工相关的事件类型，如“产品制造开始”和“产品制造结束”事件。

  - SCC 管理员在安全与合规中心创建“产品制造终止”标签。

  - 此“产品制造终止”标签将手动或自动发布并应用于 SharePoint 中的产品文件

  - ERP 系统可以与 Microsoft Flow 或类似的应用程序一起定期运行以管理产品文件

  - 如果产品制造终止，Microsoft Flow 将触发 M365 基于事件的保留 REST API，该 API 将开始特定产品文件的保留期。

## <a name="appendix"></a>附录

### <a name="using-redirect-302-response-results-to-call-the-rest-api"></a>使用重定向 302 响应结果来调用 REST API

1.  使用 REST API URL <https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent> 调用 POST 保留事件调用（需要全局管理员权限）

2.  检查响应代码。如果是 302，则从响应标头的“位置”属性中获取重定向的 URL

3.  使用重定向的 URL 再次调用 POST 保留事件调用。

## <a name="credits"></a>制作人员

本主题经过以下人员的审阅：

Antonio Maio<br/>Microsoft Office 应用和服务 MVP<br/> Antonio.Maio@Protiviti.com
