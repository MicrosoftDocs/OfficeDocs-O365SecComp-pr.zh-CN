---
title: 自动执行事件驱动的保留
ms.author: stephow
author: stephow-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 本主题介绍如何使用 Microsoft 365 REST API 设置业务流程以通过事件自动执行保留。
ms.openlocfilehash: c89abc373a6c0a1de6b6528c638dbd34e586b6d7
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2019
ms.locfileid: "34152274"
---
# <a name="automate-event-based-retention"></a><span data-ttu-id="6331e-103">自动执行基于事件的保留</span><span class="sxs-lookup"><span data-stu-id="6331e-103">Automate event-based retention</span></span>

<span data-ttu-id="6331e-p101">了解组织中呈爆炸式增长的内容以及它们如何变为 ROT（冗余、过时、无关紧要的）内容是一件头等大事。为了继续应对法律、业务和法规遵从性挑战，企业必须能够保留和保护重要信息，并快速找到相关信息。仅保留重要的相关信息是企业取得成功的关键。</span><span class="sxs-lookup"><span data-stu-id="6331e-p101">The explosion of content in organizations and how it can become ROT (redundant, obsolete, trivial) is serious business. To continue to meet legal, business, and regulatory compliance challenges, businesses must be able to keep and protect important information and quickly find what’s relevant. Retaining only important, pertinent information is key to a business’s success.</span></span>

<span data-ttu-id="6331e-p102">因此，组织可以利用 Office 365 安全与合规中心中的保留解决方案。可以使用[保留标签](labels.md)触发保留。保留标签允许选择[基于特定事件的保留期](event-driven-retention.md)。通常，保留期基于已知日期，如内容的创建日期或上次修改日期。但是，组织还要求根据事件的发生处理内容，例如在员工离开组织 7 年后进行处理。</span><span class="sxs-lookup"><span data-stu-id="6331e-p102">Hence organizations can take advantage of retention solutions in the Office 365 Security & Compliance Center. Retention can be triggered by using [retention labels](labels.md). A retention label has the option to [base the retention period on a specific event](event-driven-retention.md). Typically, the retention period is based on a known date, such as the creation date or last modified date for the content. However, organizations also have requirements to dispose of content based on the occurrence of an event, such as 7 years after an employee leaves an organization.</span></span>

<span data-ttu-id="6331e-p103">为了确保内容的合规处理，必须知道事件何时发生。随着内容量的快速增长，以及时且合规的方式保留和处理内容变得更具挑战性。</span><span class="sxs-lookup"><span data-stu-id="6331e-p103">In order to ensure compliant disposal of content, it is imperative to know when an event takes place. With the volume of content increasing rapidly, it is becoming challenging to retain and dispose content in a timely and compliant manner.</span></span>

<span data-ttu-id="6331e-p104">基于事件的保留可解决这个问题。本主题介绍如何使用 Microsoft 365 REST API 设置业务流程以通过事件自动执行保留。</span><span class="sxs-lookup"><span data-stu-id="6331e-p104">Event-based retention solves this problem. This topic explains how to set up your business process flows to automate retention through events by using the Microsoft 365 REST API.</span></span>

## <a name="about-event-based-retention"></a><span data-ttu-id="6331e-116">关于基于事件的保留</span><span class="sxs-lookup"><span data-stu-id="6331e-116">About event-based retention</span></span>

<span data-ttu-id="6331e-p105">组织可以分为小型、中型或大型组织。每天创建和管理的业务文档、法律文档、员工文件，合同和产品文档的数量正在急剧增加。</span><span class="sxs-lookup"><span data-stu-id="6331e-p105">An organization can be small, medium, or large. The number of business documents, legal documents, employee files, contracts, and product documents that get created and managed on a day to day basis is increasing dramatically.</span></span>

<span data-ttu-id="6331e-p106">例如，每天都有数十和数百名员工加入和离开组织。人力资源部门需要根据业务需求继续创建、更新或删除与员工相关的文档。此流程受为企业制定的不同保留策略的约束：</span><span class="sxs-lookup"><span data-stu-id="6331e-p106">For example, each day, tens and hundreds of employees are joining and leaving organizations. The HR department continues to create, update, or delete employee-related documents as per business requirements. This process is subject to the different retention policies outlined for the business:</span></span>

- <span data-ttu-id="6331e-p107">**内容的保留期可以是已知日期**，如内容创建、上次修改或标记的日期。例如，你可以在创建文档后将其保留 7 年，然后将其删除。</span><span class="sxs-lookup"><span data-stu-id="6331e-p107">**The period of retention for content can be a known date** such as the date the content was created, last modified or labeled. For example, you might retain documents for seven years after they're created and then delete them.</span></span>

- <span data-ttu-id="6331e-p108">**内容保留期也可以是未知日期**。例如，对于保留标签，你还可以根据特定类型事件的发生时间（如员工离开组织）来确定保留期。</span><span class="sxs-lookup"><span data-stu-id="6331e-p108">**The period of retention of content can also be an unknown date**. For example, with retention labels, you can also base a retention period on when a specific type of event occurs, such as an employee leaving the organization.</span></span>

<span data-ttu-id="6331e-p109">该事件会触发保留期的开始，并且会对已为该事件类型应用标签的所有内容强制执行标签的保留操作。这称为基于事件的保留 - 有关详细信息，请参阅[事件驱动保留概述](event-driven-retention.md)。</span><span class="sxs-lookup"><span data-stu-id="6331e-p109">The event triggers the start of the retention period, and all content with a label applied for that type of event get the label's retention actions enforced on them. This is called event-based retention - to learn more, see [Overview of event-driven retention](event-driven-retention.md).</span></span>

## <a name="set-up-event-based-retention"></a><span data-ttu-id="6331e-128">设置基于事件的保留</span><span class="sxs-lookup"><span data-stu-id="6331e-128">Set up event-based retention</span></span>

<span data-ttu-id="6331e-129">本节介绍在保留内容之前需要执行的操作。</span><span class="sxs-lookup"><span data-stu-id="6331e-129">This section describes what needs to be done prior to retaining content.</span></span>

### <a name="identify-roles"></a><span data-ttu-id="6331e-130">标识角色</span><span class="sxs-lookup"><span data-stu-id="6331e-130">Identify roles</span></span>

<span data-ttu-id="6331e-131">确定执行记录管理任务的组织中的不同角色，这些角色将负责有效且高效地保留业务文档。</span><span class="sxs-lookup"><span data-stu-id="6331e-131">Identify the different roles in an organization that perform Record Management tasks that would be responsible for effective and efficient retention of business documents.</span></span>

  | <span data-ttu-id="6331e-132">**角色**</span><span class="sxs-lookup"><span data-stu-id="6331e-132">**Persona**</span></span>| <span data-ttu-id="6331e-133">**角色**</span><span class="sxs-lookup"><span data-stu-id="6331e-133">**Role**</span></span>|
  | - | - |
  | <span data-ttu-id="6331e-134">管理员</span><span class="sxs-lookup"><span data-stu-id="6331e-134">Admin</span></span> | <span data-ttu-id="6331e-135">在 SharePoint 中创建保留事件类型、保留标签和记录存储库</span><span class="sxs-lookup"><span data-stu-id="6331e-135">Creates Retention Event types, Retention labels and Record repositories in SharePoint</span></span> |
  | <span data-ttu-id="6331e-136">记录经理</span><span class="sxs-lookup"><span data-stu-id="6331e-136">Records Manager</span></span>                                  | <span data-ttu-id="6331e-137">提供保留策略和保留计划指南和合规性详细信息</span><span class="sxs-lookup"><span data-stu-id="6331e-137">Provides Retention Policies and Retention Schedules guidance and compliance details</span></span>   |
  | <span data-ttu-id="6331e-138">系统管理员（企业）</span><span class="sxs-lookup"><span data-stu-id="6331e-138">System Admin (business)</span></span>                          | <span data-ttu-id="6331e-139">设置和管理外部系统以使用 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6331e-139">Sets up and manages external systems to work with Microsoft 365</span></span>                       |
  | <span data-ttu-id="6331e-140">信息工作者</span><span class="sxs-lookup"><span data-stu-id="6331e-140">Information Worker</span></span>                               | <span data-ttu-id="6331e-141">管理业务流程的生命周期（人力资源、财务、IT 等）</span><span class="sxs-lookup"><span data-stu-id="6331e-141">Manages the lifecycle of their business process (HR, Finance, IT etc)</span></span>                 |

### <a name="set-up-the-security--compliance-center"></a><span data-ttu-id="6331e-142">设置安全与合规中心</span><span class="sxs-lookup"><span data-stu-id="6331e-142">Set up the Security & Compliance Center</span></span>
  
1. <span data-ttu-id="6331e-143">合规性管理员可创建事件类型，例如“雇佣终止”、“合同到期”或“产品制造结束”（请在[事件驱动保留](https://docs.microsoft.com/zh-CN/office365/securitycompliance/event-driven-retention)中查看分步流程）。</span><span class="sxs-lookup"><span data-stu-id="6331e-143">Compliance admin creates an event type – for example, Employee Termination or Contract Expiration or End of Product Manufacturing (Please refer to step by step process in [Event-driven retention](https://docs.microsoft.com/en-us/office365/securitycompliance/event-driven-retention).</span></span>
    
1. <span data-ttu-id="6331e-144">合规性管理员根据事件创建保留标签，并将标签与事件类型相关联。</span><span class="sxs-lookup"><span data-stu-id="6331e-144">Compliance admin creates a retention label based on an event and associates the label with an event type.</span></span>
    
1. <span data-ttu-id="6331e-145">保留标签具有 4 种类型的触发器：</span><span class="sxs-lookup"><span data-stu-id="6331e-145">There are 4 types of triggers for retention labels:</span></span>
            
    1. <span data-ttu-id="6331e-146">创建日期</span><span class="sxs-lookup"><span data-stu-id="6331e-146">Create date</span></span>
                
    1. <span data-ttu-id="6331e-147">上次修改时间</span><span class="sxs-lookup"><span data-stu-id="6331e-147">Last modified</span></span>
                
    1. <span data-ttu-id="6331e-148">标签日期（标记内容的时间）</span><span class="sxs-lookup"><span data-stu-id="6331e-148">Label date (when the content was labeled)</span></span>
                
    1. <span data-ttu-id="6331e-149">基于事件</span><span class="sxs-lookup"><span data-stu-id="6331e-149">Event-based</span></span>
    
1. <span data-ttu-id="6331e-150">合规性管理员发布保留标签。</span><span class="sxs-lookup"><span data-stu-id="6331e-150">Compliance admin publishes the retention label.</span></span>

### <a name="set-up-sharepoint"></a><span data-ttu-id="6331e-151">设置 SharePoint</span><span class="sxs-lookup"><span data-stu-id="6331e-151">Set up SharePoint</span></span>
   
<span data-ttu-id="6331e-152">若要创建记录存储库，合规性管理员需要：</span><span class="sxs-lookup"><span data-stu-id="6331e-152">To create a records repository, the compliance admin:</span></span>

1. <span data-ttu-id="6331e-153">创建 SharePoint 网站。</span><span class="sxs-lookup"><span data-stu-id="6331e-153">Creates a SharePoint site.</span></span>

1. <span data-ttu-id="6331e-154">执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="6331e-154">Does one of the following:</span></span>
        
    - <span data-ttu-id="6331e-p110">创建 SharePoint 库：在库级别设置基于事件的标签。有关详细信息，请参阅[将默认保留标签应用于 SharePoint 库、文件夹或文档集中的所有内容](labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set)。</span><span class="sxs-lookup"><span data-stu-id="6331e-p110">Creates a SharePoint library: Set event-based label at the library level. For more information, see [Applying a default retention label to all content in a SharePoint library, folder, or document set](labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set).</span></span>
          
    - <span data-ttu-id="6331e-p111">在 SharePoint 中设置文档集。有关详细信息，请参阅[文档集简介](https://support.office.com/zh-CN/article/Introduction-to-Document-Sets-3DBCD93E-0BED-46B7-B1BA-B31DE2BCD234)。</span><span class="sxs-lookup"><span data-stu-id="6331e-p111">Sets up a Document set in SharePoint. For more information, see [Introduction to document sets](https://support.office.com/en-us/article/Introduction-to-Document-Sets-3DBCD93E-0BED-46B7-B1BA-B31DE2BCD234).</span></span>
      
1. <span data-ttu-id="6331e-p112">为每个员工文档集分配资产 ID（资产 ID 是组织使用的产品名称或代码，例如员工编号可以是资产 ID）。通过将资产 ID 分配给文件夹，该文件夹中的每个项目都会自动继承相同的资产 ID。这意味着所有项目的保留期都可以由同一事件触发。</span><span class="sxs-lookup"><span data-stu-id="6331e-p112">Assigns Asset Id (asset ID is a product name or code used by the organization, for example, Employee number can be an asset id) to each employee document set (By assigning the asset ID to the folder, every item in that folder automatically inherits the same asset ID. This means all the items can have their retention period triggered by the same event.</span></span>

## <a name="ways-to-trigger-event-based-retention"></a><span data-ttu-id="6331e-161">触发基于事件的保留的方法</span><span class="sxs-lookup"><span data-stu-id="6331e-161">Ways to trigger event-based retention</span></span>

<span data-ttu-id="6331e-162">可通过两种方法触发基于事件的保留：</span><span class="sxs-lookup"><span data-stu-id="6331e-162">There are two ways in which event-based retention can be triggered:</span></span>

- <span data-ttu-id="6331e-p113">**使用管理中心 UI** 此流程适用于一次保留较少内容或者不经常触发保留的情形，例如每月或每年保留一次。有关此方法的详细信息，请参阅[事件驱动保留概述](event-driven-retention.md)。但是，这种触发保留的方法可能比较耗时且容易出错，这会影响可伸缩性。用于触发保留的自动化无缝解决方案可以增强数据的安全性和合规性。</span><span class="sxs-lookup"><span data-stu-id="6331e-p113">**Using the admin center UI** This is a process that can be used to retain less content at a time or the frequency to trigger retention is not often, such as monthly or yearly. For more information on this method, see [Overview of event-driven retention](event-driven-retention.md). However, this way to trigger retention can be time-consuming and prone to error, thus stunting scalability. Therefore, an automated, seamless solution to trigger retention can enhance the security and compliance of data.</span></span>

- <span data-ttu-id="6331e-p114">**使用 M365 REST API** 当一次保留大量内容和/或触发保留的频率通常是每天或每周时，可以使用此流程。该流程会检测你的业务线系统中何时发生事件，然后在安全与合规中心自动创建相关事件。每次发生事件时，你无需在 UI 中手动创建事件。</span><span class="sxs-lookup"><span data-stu-id="6331e-p114">**Using a M365 REST API** This process can be used when large amounts of content are to be retained at a time and/or the frequency to trigger retention is often such as daily or weekly. The flow detects when an event occurs in your line-of-business system, and then automatically creates a related event in the Security & Compliance Center. You don't need to manually create an event in the UI each time one occurs.</span></span>

<span data-ttu-id="6331e-170">使用 REST API 有两种选择：</span><span class="sxs-lookup"><span data-stu-id="6331e-170">There are two options for using the REST API:</span></span>

- <span data-ttu-id="6331e-p115">**Microsoft Flow 或类似的应用程序**可用于自动触发事件的发生。Microsoft Flow 是用于连接到其他系统的协调程序。使用 Microsoft Flow 不需要自定义解决方案。</span><span class="sxs-lookup"><span data-stu-id="6331e-p115">**Microsoft Flow or a similar application** can be used to trigger the occurrence of an event automatically. Microsoft Flow is an orchestrator for connecting to other systems. Using Microsoft Flow does not require a custom solution.</span></span>

- <span data-ttu-id="6331e-174">\*\*使用 PowerShell 或 HTTP 客户端调用 REST API \*\*使用 PowerShell（版本 6 或更高版本）调用 Microsoft 365 REST API 以创建事件。</span><span class="sxs-lookup"><span data-stu-id="6331e-174">**PowerShell or an HTTP client to call REST API** Using PowerShell (version 6 or higher) to call Microsoft 365 REST API to create events.</span></span> 

<span data-ttu-id="6331e-p116">Rest API 是一个支持多组 HTTP 操作（方法）的服务终结点，提供对服务资源的创建/检索/更新/删除操作权限 - 有关详细信息，请参阅 [REST API 请求/响应组件](https://docs.microsoft.com/zh-CN/rest/api/gettingstarted/#components-of-a-rest-api-requestresponse)。在这种情况下，通过使用 Microsoft 365 REST API，可以使用 POST 和 GET 操作（方法）来创建和检索事件。</span><span class="sxs-lookup"><span data-stu-id="6331e-p116">A Rest API is a service endpoint that supports sets of HTTP operations (methods), which provide create/retrieve/update/delete access to the service's resources - for more information, see [Components of a REST API request/response](https://docs.microsoft.com/en-us/rest/api/gettingstarted/#components-of-a-rest-api-requestresponse). In this case, by using the Microsoft 365 REST API, events can be created and retrieved using operations (methods) POST and GET.</span></span>

## <a name="example-scenarios"></a><span data-ttu-id="6331e-177">示例场景</span><span class="sxs-lookup"><span data-stu-id="6331e-177">Example scenarios</span></span>

<span data-ttu-id="6331e-178">让我们以如下场景为例。</span><span class="sxs-lookup"><span data-stu-id="6331e-178">Let’s consider the following scenarios.</span></span>

### <a name="scenario-1-employees-leaving-the-organization"></a><span data-ttu-id="6331e-179">场景 1：员工离开组织</span><span class="sxs-lookup"><span data-stu-id="6331e-179">Scenario 1: Employees leaving the organization</span></span> 

<span data-ttu-id="6331e-p117">组织为每个员工创建和存储许多员工相关文档。这些文档在每位员工的雇佣期内进行管理和保留。但是，当员工离开组织或终止雇佣关系时，组织有义务根据法律和业务要求在规定的时间内保留该员工的文档。</span><span class="sxs-lookup"><span data-stu-id="6331e-p117">An organization creates and stores numerous employee related documents per employee. These documents are managed and retained during the employment of each employee. However, when the employee leaves the organization or the employment is terminated, the organization is obligated by legal and business requirements to retain the documents of that employee for a stipulated period.</span></span>

<span data-ttu-id="6331e-183">现在，如果每天有多名员工离开组织，组织必须在每天触发数百甚至数千个文档的保留期。</span><span class="sxs-lookup"><span data-stu-id="6331e-183">Now if multiple employees leave the organization every day, the organization must trigger the retention clock of hundreds if not thousands of documents each day.</span></span>

<span data-ttu-id="6331e-p118">除此之外，还需要根据员工记录的类型计算每个员工的保留期，即雇佣终止日期 + 天数、月数或年数。例如，同一员工的职工薪酬档案与福利档案可能需要不同的保留期。</span><span class="sxs-lookup"><span data-stu-id="6331e-p118">In addition to this, the retention period needs to be calculated for each of these employees as Employee termination date + number of days, months or years based on the type of the employee record. For example, worker’s compensation of the employee vs benefits filings of the same employee may need different retention.</span></span>

<span data-ttu-id="6331e-p119">下图显示如何将多个标签与单个事件关联。在此处，员工薪酬标签下的所有文件和员工福利标签下的所有文件都与单个事件相关联，即员工离开组织。每个不同的文件都有不同的保留期。因此，当员工离开组织时，每个标签中的这些文件都会经历不同的保留期。为每个员工的每种文件类型或标签触发所有这些不同的保留期是一项极具挑战的任务。想象一下，为多名员工做这件事将会如何。</span><span class="sxs-lookup"><span data-stu-id="6331e-p119">The diagram below shows how there can be multiple labels that are associated with a single event. Here all the files under Worker’s compensation label and all the files under Employee benefits label are both associated with a single event which is the employee leaving the organization. Each of these different files have different retention clocks. So, when an employee leaves the organization, these files within each label experience a different retention period. To trigger all these different retention clocks for each file type or label for each employee is a very challenging task. Imagine doing this for multiple employees.</span></span>

![事件类型、事件和标签的关系图](media/automate-event-driven-retention-event-diagram-employee-leaving.png)

<span data-ttu-id="6331e-193">为多个员工触发这些不同保留期的自动化流程将节省时间、无错误且极为高效。</span><span class="sxs-lookup"><span data-stu-id="6331e-193">Hence an automated process to trigger these different retention clocks for multiple employees will be time-saving, error-free and extremely efficient .</span></span>

<span data-ttu-id="6331e-194">**为此场景配置基于事件的自动保留：**</span><span class="sxs-lookup"><span data-stu-id="6331e-194">**Configuring Automated Event Based Retention for this scenario:**</span></span>

![针对员工离开组织的场景的角色和操作关系图](media/automate-event-driven-retention-employee-termination-diagram.png)

  - <span data-ttu-id="6331e-196">管理员为文档集创建员工文件夹，如 Jane Doe、John Smith。</span><span class="sxs-lookup"><span data-stu-id="6331e-196">Admin c reates employee folders to the Document set such as Jane Doe, John Smith.</span></span>

  - <span data-ttu-id="6331e-197">管理员将员工文件（如福利、工资单、员工薪酬）添加到每个员工文件夹中</span><span class="sxs-lookup"><span data-stu-id="6331e-197">Admin adds employee files such as Benefits, Payroll, Worker’s Compensation to each employee folder</span></span>

  - <span data-ttu-id="6331e-198">管理员为每个员工文件夹分配资产 ID。</span><span class="sxs-lookup"><span data-stu-id="6331e-198">Admin assigns Asset Id to each employee folder.</span></span> 

  - <span data-ttu-id="6331e-199">SCC 管理员</span><span class="sxs-lookup"><span data-stu-id="6331e-199">SCC Admin l</span></span>

  - <span data-ttu-id="6331e-200">登录到安全与合规中心</span><span class="sxs-lookup"><span data-stu-id="6331e-200">Logs into the Security & Compliance Center</span></span>

  - <span data-ttu-id="6331e-201">SCC 管理员创建与员工相关的事件类型，例如“雇佣终止”和“员工雇用”事件。</span><span class="sxs-lookup"><span data-stu-id="6331e-201">SCC Admin creates employee related events types such as “Employee Termination”, “Employee Hire” events.</span></span>

  - <span data-ttu-id="6331e-202">SCC 管理员创建“员工留任”标签。</span><span class="sxs-lookup"><span data-stu-id="6331e-202">SCC Admin creates “Employee Retention” label.</span></span>

  - <span data-ttu-id="6331e-203">此“员工保留”标签将手动或自动发布并应用于 SharePoint 中的员工文件</span><span class="sxs-lookup"><span data-stu-id="6331e-203">This “Employee Retention” label is published and applied manually or automatically to the employee files in SharePoint</span></span>

  - <span data-ttu-id="6331e-204">HR 管理系统（如 Workday）可以与 Microsoft Flow 一起定期运行以管理员工文件</span><span class="sxs-lookup"><span data-stu-id="6331e-204">HR Management System like Workday can work with Microsoft Flow to run periodically to manage employee files</span></span>

  - <span data-ttu-id="6331e-205">如果员工离开组织，Flow 将触发 M365 基于事件的保留 REST API，该 API 将开始特定员工文件的保留期。</span><span class="sxs-lookup"><span data-stu-id="6331e-205">If an employee has left the organization, the Flow will trigger the M365 Event Based Retention REST API that will begin the retention clock on the specific employee’s files.</span></span>

#### <a name="using-microsoft-flow"></a><span data-ttu-id="6331e-206">使用 Microsoft Flow</span><span class="sxs-lookup"><span data-stu-id="6331e-206">Using Microsoft Flow</span></span>

<span data-ttu-id="6331e-207">步骤 1 - 使用 Microsoft 365 REST API 创建用于创建事件的流</span><span class="sxs-lookup"><span data-stu-id="6331e-207">Step 1- Create a flow to create an event using the Microsoft 365 REST API</span></span>

![使用流创建事件](media/automate-event-driven-retention-flow-1.png)

![使用流调用 REST API](media/automate-event-driven-retention-flow-2.png)

##### <a name="create-an-event"></a><span data-ttu-id="6331e-210">创建事件</span><span class="sxs-lookup"><span data-stu-id="6331e-210">Create an event</span></span>

<span data-ttu-id="6331e-211">用于调用 REST API 的示例代码</span><span class="sxs-lookup"><span data-stu-id="6331e-211">Sample code to call the REST API</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="6331e-212">方法</span><span class="sxs-lookup"><span data-stu-id="6331e-212">Method</span></span></th>
<th><span data-ttu-id="6331e-213">POST</span><span class="sxs-lookup"><span data-stu-id="6331e-213">POST</span></span></th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="6331e-214">URL</span><span class="sxs-lookup"><span data-stu-id="6331e-214">URL</span></span></td>
<td>https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent)</td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="6331e-215">标头</span><span class="sxs-lookup"><span data-stu-id="6331e-215">Headers</span></span></td>
<td><span data-ttu-id="6331e-216">Content-Type</span><span class="sxs-lookup"><span data-stu-id="6331e-216">Content-Type</span></span></td>
<td><span data-ttu-id="6331e-217">application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="6331e-217">application/atom+xml</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="6331e-218">正文</span><span class="sxs-lookup"><span data-stu-id="6331e-218">Body</span></span></td>
<td><p><span data-ttu-id="6331e-219">&lt;?xml version='1.0' encoding='utf-8' standalone='yes'?&gt;</span><span class="sxs-lookup"><span data-stu-id="6331e-219">&lt;?xml version='1.0' encoding='utf-8' standalone='yes'?&gt;</span></span></p>
<p><span data-ttu-id="6331e-220">&lt;entry xmlns:d='http://schemas.microsoft.com/ado/2007/08/dataservices'</span><span class="sxs-lookup"><span data-stu-id="6331e-220">&lt;entry xmlns:d='http://schemas.microsoft.com/ado/2007/08/dataservices'</span></span></p>
<p><span data-ttu-id="6331e-221">xmlns:m='http://schemas.microsoft.com/ado/2007/08/dataservices/metadata'</span><span class="sxs-lookup"><span data-stu-id="6331e-221">xmlns:m='http://schemas.microsoft.com/ado/2007/08/dataservices/metadata'</span></span></p>
<p><span data-ttu-id="6331e-222">xmlns='http://www.w3.org/2005/Atom'&gt;</span><span class="sxs-lookup"><span data-stu-id="6331e-222">xmlns='http://www.w3.org/2005/Atom'&gt;</span></span></p>
<p><span data-ttu-id="6331e-223">&lt;category scheme='http://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' /&gt;</span><span class="sxs-lookup"><span data-stu-id="6331e-223">&lt;category scheme='http://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' /&gt;</span></span></p>
<p><span data-ttu-id="6331e-224">&lt;updated&gt;9/9/2017 10:50:00 PM&lt;/updated&gt;</span><span class="sxs-lookup"><span data-stu-id="6331e-224">&lt;updated&gt;9/9/2017 10:50:00 PM&lt;/updated&gt;</span></span></p>
<p><span data-ttu-id="6331e-225">&lt;content type='application/xml'&gt;</span><span class="sxs-lookup"><span data-stu-id="6331e-225">&lt;content type='application/xml'&gt;</span></span></p>
<p><span data-ttu-id="6331e-226">&lt;m:properties&gt;</span><span class="sxs-lookup"><span data-stu-id="6331e-226">&lt;m:properties&gt;</span></span></p>
<p><span data-ttu-id="6331e-227">&lt;d:Name&gt;Employee Termination &lt;/d:Name&gt;</span><span class="sxs-lookup"><span data-stu-id="6331e-227">&lt;d:Name&gt;Employee Termination &lt;/d:Name&gt;</span></span></p>
<p><span data-ttu-id="6331e-228">&lt;d:EventType&gt;99e0ae64-a4b8-40bb-82ed-645895610f56&lt;/d:EventType&gt;</span><span class="sxs-lookup"><span data-stu-id="6331e-228">&lt;d:EventType&gt;99e0ae64-a4b8-40bb-82ed-645895610f56&lt;/d:EventType&gt;</span></span></p>
<p><span data-ttu-id="6331e-229">&lt;d:SharePointAssetIdQuery&gt;1234&lt;/d:SharePointAssetIdQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="6331e-229">&lt;d:SharePointAssetIdQuery&gt;1234&lt;/d:SharePointAssetIdQuery&gt;</span></span></p>
<p><span data-ttu-id="6331e-230">&lt;d:EventDateTime&gt;2018-12-01T00:00:00Z &lt;/d:EventDateTime&gt;</span><span class="sxs-lookup"><span data-stu-id="6331e-230">&lt;d:EventDateTime&gt;2018-12-01T00:00:00Z &lt;/d:EventDateTime&gt;</span></span></p>
<p><span data-ttu-id="6331e-231">&lt;/m:properties&gt;</span><span class="sxs-lookup"><span data-stu-id="6331e-231">&lt;/m:properties&gt;</span></span></p>
<p><span data-ttu-id="6331e-232">&lt;/content&gt;</span><span class="sxs-lookup"><span data-stu-id="6331e-232">&lt;/content&gt;</span></span></p>
<p><span data-ttu-id="6331e-233">&lt;/entry&gt;</span><span class="sxs-lookup"><span data-stu-id="6331e-233">&lt;/entry&gt;</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="6331e-234">身份验证</span><span class="sxs-lookup"><span data-stu-id="6331e-234">Authentication</span></span></td>
<td><span data-ttu-id="6331e-235">基本</span><span class="sxs-lookup"><span data-stu-id="6331e-235">Basic</span></span></td>
<td></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="6331e-236">用户名</span><span class="sxs-lookup"><span data-stu-id="6331e-236">Username</span></span></td>
<td><span data-ttu-id="6331e-237">“Complianceuser”</span><span class="sxs-lookup"><span data-stu-id="6331e-237">“Complianceuser”</span></span></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="6331e-238">密码</span><span class="sxs-lookup"><span data-stu-id="6331e-238">Password</span></span></td>
<td><span data-ttu-id="6331e-239">“Compliancepassword”</span><span class="sxs-lookup"><span data-stu-id="6331e-239">“Compliancepassword”</span></span></td>
<td></td>
</tr>
</tbody>
</table>

##### <a name="available-parameters"></a><span data-ttu-id="6331e-240">可用参数</span><span class="sxs-lookup"><span data-stu-id="6331e-240">Available parameters</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="6331e-241"><strong>参数</strong></span><span class="sxs-lookup"><span data-stu-id="6331e-241"><strong>Parameters</strong></span></span></th>
<th><span data-ttu-id="6331e-242"><strong>说明</strong></span><span class="sxs-lookup"><span data-stu-id="6331e-242"><strong>Description</strong></span></span></th>
<th><span data-ttu-id="6331e-243"><strong>注释</strong></span><span class="sxs-lookup"><span data-stu-id="6331e-243"><strong>Notes</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="6331e-244">&lt;d:Name&gt;&lt;/d:Name&gt;</span><span class="sxs-lookup"><span data-stu-id="6331e-244">&lt;d:Name&gt;&lt;/d:Name&gt;</span></span></td>
<td><span data-ttu-id="6331e-245">为事件提供唯一的名称，</span><span class="sxs-lookup"><span data-stu-id="6331e-245">Provide a unique name for the event,</span></span></td>
<td><span data-ttu-id="6331e-p120">不能包含尾随空格和以下字符：% \* \ &amp; &lt; &gt; | # ? , : ;</span><span class="sxs-lookup"><span data-stu-id="6331e-p120">Cannot contain trailing spaces, and the following characters: % \* \ &amp; &lt; &gt; | # ? , : ;</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="6331e-248">&lt;d:EventType&gt;&lt;/d:EventType&gt;</span><span class="sxs-lookup"><span data-stu-id="6331e-248">&lt;d:EventType&gt;&lt;/d:EventType&gt;</span></span></td>
<td><span data-ttu-id="6331e-249">输入事件类型名称（或 Guid），</span><span class="sxs-lookup"><span data-stu-id="6331e-249">Enter event type name (or Guid),</span></span></td>
<td><span data-ttu-id="6331e-p121">示例：“雇佣终止”。事件类型必须与保留标签相关联。</span><span class="sxs-lookup"><span data-stu-id="6331e-p121">Example: “Employee termination”. Event type has to be associated with a retention label.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="6331e-252">&lt;d:SharePointAssetIdQuery&gt;&lt;/d:SharePointAssetIdQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="6331e-252">&lt;d:SharePointAssetIdQuery&gt;&lt;/d:SharePointAssetIdQuery&gt;</span></span></td>
<td><span data-ttu-id="6331e-253">输入“ComplianceAssetId:” + 员工 Id</span><span class="sxs-lookup"><span data-stu-id="6331e-253">Enter “ComplianceAssetId:” + employee Id</span></span></td>
<td><span data-ttu-id="6331e-254">示例：&quot;ComplianceAssetId:12345&quot;</span><span class="sxs-lookup"><span data-stu-id="6331e-254">Example:&quot;ComplianceAssetId:12345&quot;</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="6331e-255">&lt;d:EventDateTime&gt;&lt;/d:EventDateTime&gt;</span><span class="sxs-lookup"><span data-stu-id="6331e-255">&lt;d:EventDateTime&gt;&lt;/d:EventDateTime&gt;</span></span></td>
<td><span data-ttu-id="6331e-256">事件日期和时间</span><span class="sxs-lookup"><span data-stu-id="6331e-256">Event Date and Time</span></span></td>
<td><p><span data-ttu-id="6331e-257">格式：yyyy-MM-ddTHH:mm:ssZ，示例：</span><span class="sxs-lookup"><span data-stu-id="6331e-257">Format: yyyy-MM-ddTHH:mm:ssZ, Example:</span></span></p>
<p><span data-ttu-id="6331e-258">2018-12-01T00:00:00Z</span><span class="sxs-lookup"><span data-stu-id="6331e-258">2018-12-01T00:00:00Z</span></span></p></td>
</tr>
</tbody>
</table>

##### <a name="response-codes"></a><span data-ttu-id="6331e-259">响应代码</span><span class="sxs-lookup"><span data-stu-id="6331e-259">Response codes</span></span>

| <span data-ttu-id="6331e-260">**响应代码**</span><span class="sxs-lookup"><span data-stu-id="6331e-260">**Response Code**</span></span> | <span data-ttu-id="6331e-261">**说明**</span><span class="sxs-lookup"><span data-stu-id="6331e-261">**Description**</span></span>       |
| ----------------- | --------------------- |
| <span data-ttu-id="6331e-262">302</span><span class="sxs-lookup"><span data-stu-id="6331e-262">302</span></span>               | <span data-ttu-id="6331e-263">重定向</span><span class="sxs-lookup"><span data-stu-id="6331e-263">Redirect</span></span>              |
| <span data-ttu-id="6331e-264">201</span><span class="sxs-lookup"><span data-stu-id="6331e-264">201</span></span>               | <span data-ttu-id="6331e-265">已创建</span><span class="sxs-lookup"><span data-stu-id="6331e-265">Created</span></span>               |
| <span data-ttu-id="6331e-266">403</span><span class="sxs-lookup"><span data-stu-id="6331e-266">403</span></span>               | <span data-ttu-id="6331e-267">授权失败</span><span class="sxs-lookup"><span data-stu-id="6331e-267">Authorization Failed</span></span>  |
| <span data-ttu-id="6331e-268">401</span><span class="sxs-lookup"><span data-stu-id="6331e-268">401</span></span>               | <span data-ttu-id="6331e-269">身份验证失败</span><span class="sxs-lookup"><span data-stu-id="6331e-269">Authentication Failed</span></span> |

##### <a name="get-events-based-on-time-range"></a><span data-ttu-id="6331e-270">根据时间范围获取事件</span><span class="sxs-lookup"><span data-stu-id="6331e-270">Get Events based on time range</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="6331e-271">方法</span><span class="sxs-lookup"><span data-stu-id="6331e-271">Method</span></span></th>
<th><span data-ttu-id="6331e-272">GET</span><span class="sxs-lookup"><span data-stu-id="6331e-272">GET</span></span></th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="6331e-273">URL</span><span class="sxs-lookup"><span data-stu-id="6331e-273">URL</span></span></td>
<td><ol start="4" type="1">
<li><p><span data-ttu-id="6331e-274">https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent?BeginDateTime=2019-01-11&amp;EndDateTime=2019-01-16</span><span class="sxs-lookup"><span data-stu-id="6331e-274">https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent?BeginDateTime=2019-01-11&amp;EndDateTime=2019-01-16</span></span></p></li>
</ol></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="6331e-275">标头</span><span class="sxs-lookup"><span data-stu-id="6331e-275">Headers</span></span></td>
<td><span data-ttu-id="6331e-276">Content-Type</span><span class="sxs-lookup"><span data-stu-id="6331e-276">Content-Type</span></span></td>
<td><span data-ttu-id="6331e-277">application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="6331e-277">application/atom+xml</span></span></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="6331e-278">身份验证</span><span class="sxs-lookup"><span data-stu-id="6331e-278">Authentication</span></span></td>
<td><span data-ttu-id="6331e-279">基本</span><span class="sxs-lookup"><span data-stu-id="6331e-279">Basic</span></span></td>
<td></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="6331e-280">用户名</span><span class="sxs-lookup"><span data-stu-id="6331e-280">Username</span></span></td>
<td><span data-ttu-id="6331e-281">“Complianceuser”</span><span class="sxs-lookup"><span data-stu-id="6331e-281">“Complianceuser”</span></span></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="6331e-282">密码</span><span class="sxs-lookup"><span data-stu-id="6331e-282">Password</span></span></td>
<td><span data-ttu-id="6331e-283">“Compliancepassword”</span><span class="sxs-lookup"><span data-stu-id="6331e-283">“Compliancepassword”</span></span></td>
<td></td>
</tr>
</tbody>
</table>

##### <a name="response-codes"></a><span data-ttu-id="6331e-284">响应代码</span><span class="sxs-lookup"><span data-stu-id="6331e-284">Response codes</span></span>

| <span data-ttu-id="6331e-285">**响应代码**</span><span class="sxs-lookup"><span data-stu-id="6331e-285">**Response Code**</span></span> | <span data-ttu-id="6331e-286">**说明**</span><span class="sxs-lookup"><span data-stu-id="6331e-286">**Description**</span></span>                   |
| ----------------- | --------------------------------- |
| <span data-ttu-id="6331e-287">200</span><span class="sxs-lookup"><span data-stu-id="6331e-287">200</span></span>               | <span data-ttu-id="6331e-288">正常，atom+ xml 中的事件列表</span><span class="sxs-lookup"><span data-stu-id="6331e-288">OK, A list of events in atom+ xml</span></span> |
| <span data-ttu-id="6331e-289">404</span><span class="sxs-lookup"><span data-stu-id="6331e-289">404</span></span>               | <span data-ttu-id="6331e-290">未找到</span><span class="sxs-lookup"><span data-stu-id="6331e-290">Not found</span></span>                         |
| <span data-ttu-id="6331e-291">302</span><span class="sxs-lookup"><span data-stu-id="6331e-291">302</span></span>               | <span data-ttu-id="6331e-292">重定向</span><span class="sxs-lookup"><span data-stu-id="6331e-292">Redirect</span></span>                          |
| <span data-ttu-id="6331e-293">401</span><span class="sxs-lookup"><span data-stu-id="6331e-293">401</span></span>               | <span data-ttu-id="6331e-294">授权失败</span><span class="sxs-lookup"><span data-stu-id="6331e-294">Authorization Failed</span></span>              |
| <span data-ttu-id="6331e-295">403</span><span class="sxs-lookup"><span data-stu-id="6331e-295">403</span></span>               | <span data-ttu-id="6331e-296">身份验证失败</span><span class="sxs-lookup"><span data-stu-id="6331e-296">Authentication Failed</span></span>             |

##### <a name="get-an-event-by-id"></a><span data-ttu-id="6331e-297">按 ID 获取事件。</span><span class="sxs-lookup"><span data-stu-id="6331e-297">Get an event by ID</span></span>

| <span data-ttu-id="6331e-298">方法</span><span class="sxs-lookup"><span data-stu-id="6331e-298">Method</span></span>         | <span data-ttu-id="6331e-299">GET</span><span class="sxs-lookup"><span data-stu-id="6331e-299">GET</span></span>   |                      |
| -------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | -------------------- |
| <span data-ttu-id="6331e-300">URL</span><span class="sxs-lookup"><span data-stu-id="6331e-300">URL</span></span>            | <span data-ttu-id="6331e-301">[https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent(‘174e9a86-74ff-4450-8666-7c11f7730f66’)](https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent\('174e9a86-74ff-4450-8666-7c11f7730f66'\))</span><span class="sxs-lookup"><span data-stu-id="6331e-301">[https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent(‘174e9a86-74ff-4450-8666-7c11f7730f66’)](https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent\('174e9a86-74ff-4450-8666-7c11f7730f66'\))</span></span> |                      |
| <span data-ttu-id="6331e-302">标头</span><span class="sxs-lookup"><span data-stu-id="6331e-302">Header</span></span>         | <span data-ttu-id="6331e-303">Content-Type</span><span class="sxs-lookup"><span data-stu-id="6331e-303">Content-Type</span></span>                                                                                                                                                                                                                                                       | <span data-ttu-id="6331e-304">application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="6331e-304">application/atom+xml</span></span> |
| <span data-ttu-id="6331e-305">身份验证</span><span class="sxs-lookup"><span data-stu-id="6331e-305">Authentication</span></span> | <span data-ttu-id="6331e-306">基本</span><span class="sxs-lookup"><span data-stu-id="6331e-306">Basic</span></span>                                                                                                                                                                                                                                                              |                      |
| <span data-ttu-id="6331e-307">用户名</span><span class="sxs-lookup"><span data-stu-id="6331e-307">Username</span></span>       | <span data-ttu-id="6331e-308">“Complianceuser”</span><span class="sxs-lookup"><span data-stu-id="6331e-308">“Complianceuser”</span></span>                                                                                                                                                                                                                                                   |                      |
| <span data-ttu-id="6331e-309">密码</span><span class="sxs-lookup"><span data-stu-id="6331e-309">Password</span></span>       | <span data-ttu-id="6331e-310">“Compliancepassword”</span><span class="sxs-lookup"><span data-stu-id="6331e-310">“Compliancepassword”</span></span>                                                                                                                                                                                                                                               |                      |

##### <a name="response-codes"></a><span data-ttu-id="6331e-311">响应代码</span><span class="sxs-lookup"><span data-stu-id="6331e-311">Response codes</span></span>

| <span data-ttu-id="6331e-312">**响应代码**</span><span class="sxs-lookup"><span data-stu-id="6331e-312">**Response Code**</span></span> | <span data-ttu-id="6331e-313">**说明**</span><span class="sxs-lookup"><span data-stu-id="6331e-313">**Description**</span></span>                                      |
| ----------------- | ---------------------------------------------------- |
| <span data-ttu-id="6331e-314">200</span><span class="sxs-lookup"><span data-stu-id="6331e-314">200</span></span>               | <span data-ttu-id="6331e-315">正常，响应正文包含 atom+xml 中的事件</span><span class="sxs-lookup"><span data-stu-id="6331e-315">OK, The response body contains the event in atom+xml</span></span> |
| <span data-ttu-id="6331e-316">404</span><span class="sxs-lookup"><span data-stu-id="6331e-316">404</span></span>               | <span data-ttu-id="6331e-317">未找到</span><span class="sxs-lookup"><span data-stu-id="6331e-317">Not found</span></span>                                            |
| <span data-ttu-id="6331e-318">302</span><span class="sxs-lookup"><span data-stu-id="6331e-318">302</span></span>               | <span data-ttu-id="6331e-319">重定向</span><span class="sxs-lookup"><span data-stu-id="6331e-319">Redirect</span></span>                                             |
| <span data-ttu-id="6331e-320">401</span><span class="sxs-lookup"><span data-stu-id="6331e-320">401</span></span>               | <span data-ttu-id="6331e-321">授权失败</span><span class="sxs-lookup"><span data-stu-id="6331e-321">Authorization Failed</span></span>                                 |
| <span data-ttu-id="6331e-322">403</span><span class="sxs-lookup"><span data-stu-id="6331e-322">403</span></span>               | <span data-ttu-id="6331e-323">身份验证失败</span><span class="sxs-lookup"><span data-stu-id="6331e-323">Authentication Failed</span></span>                                |

##### <a name="get-an-event-by-name"></a><span data-ttu-id="6331e-324">按名称获取事件</span><span class="sxs-lookup"><span data-stu-id="6331e-324">Get an event by name</span></span>

| <span data-ttu-id="6331e-325">方法</span><span class="sxs-lookup"><span data-stu-id="6331e-325">Method</span></span>         | <span data-ttu-id="6331e-326">GET</span><span class="sxs-lookup"><span data-stu-id="6331e-326">GET</span></span>       |                      |
| -------------- | -------------------------------------------------------------------------------------------------------------------------------------------- | -------------------- |
| <span data-ttu-id="6331e-327">URL</span><span class="sxs-lookup"><span data-stu-id="6331e-327">URL</span></span>            | <https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent('EventByRESTPost-2226bfebcc2841a8968ba71f9516b763')> |                      |
| <span data-ttu-id="6331e-328">标头</span><span class="sxs-lookup"><span data-stu-id="6331e-328">Headers</span></span>        | <span data-ttu-id="6331e-329">Content-Type</span><span class="sxs-lookup"><span data-stu-id="6331e-329">Content-Type</span></span>                                                                                                                                 | <span data-ttu-id="6331e-330">application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="6331e-330">application/atom+xml</span></span> |
| <span data-ttu-id="6331e-331">身份验证</span><span class="sxs-lookup"><span data-stu-id="6331e-331">Authentication</span></span> | <span data-ttu-id="6331e-332">基本</span><span class="sxs-lookup"><span data-stu-id="6331e-332">Basic</span></span>                                                                                                                                        |                      |
| <span data-ttu-id="6331e-333">用户名</span><span class="sxs-lookup"><span data-stu-id="6331e-333">Username</span></span>       | <span data-ttu-id="6331e-334">“Complianceuser”</span><span class="sxs-lookup"><span data-stu-id="6331e-334">“Complianceuser”</span></span>                                                                                                                             |                      |
| <span data-ttu-id="6331e-335">密码</span><span class="sxs-lookup"><span data-stu-id="6331e-335">Password</span></span>       | <span data-ttu-id="6331e-336">“Compliancepassword”</span><span class="sxs-lookup"><span data-stu-id="6331e-336">“Compliancepassword”</span></span>                                                                                                                         |                      |

##### <a name="response-codes"></a><span data-ttu-id="6331e-337">响应代码</span><span class="sxs-lookup"><span data-stu-id="6331e-337">Response codes</span></span>

| <span data-ttu-id="6331e-338">**响应代码**</span><span class="sxs-lookup"><span data-stu-id="6331e-338">**Response Code**</span></span> | <span data-ttu-id="6331e-339">**说明**</span><span class="sxs-lookup"><span data-stu-id="6331e-339">**Description**</span></span>                                      |
| ----------------- | ---------------------------------------------------- |
| <span data-ttu-id="6331e-340">200</span><span class="sxs-lookup"><span data-stu-id="6331e-340">200</span></span>               | <span data-ttu-id="6331e-341">正常，响应正文包含 atom+xml 中的事件</span><span class="sxs-lookup"><span data-stu-id="6331e-341">OK, The response body contains the event in atom+xml</span></span> |
| <span data-ttu-id="6331e-342">404</span><span class="sxs-lookup"><span data-stu-id="6331e-342">404</span></span>               | <span data-ttu-id="6331e-343">未找到</span><span class="sxs-lookup"><span data-stu-id="6331e-343">Not found</span></span>                                            |
| <span data-ttu-id="6331e-344">302</span><span class="sxs-lookup"><span data-stu-id="6331e-344">302</span></span>               | <span data-ttu-id="6331e-345">重定向</span><span class="sxs-lookup"><span data-stu-id="6331e-345">Redirect</span></span>                                             |
| <span data-ttu-id="6331e-346">401</span><span class="sxs-lookup"><span data-stu-id="6331e-346">401</span></span>               | <span data-ttu-id="6331e-347">授权失败</span><span class="sxs-lookup"><span data-stu-id="6331e-347">Authorization Failed</span></span>                                 |
| <span data-ttu-id="6331e-348">403</span><span class="sxs-lookup"><span data-stu-id="6331e-348">403</span></span>               | <span data-ttu-id="6331e-349">身份验证失败</span><span class="sxs-lookup"><span data-stu-id="6331e-349">Authentication Failed</span></span>                                |

#### <a name="using-powershell-ver6-or-higher-or-any-http-client"></a><span data-ttu-id="6331e-350">使用 PowerShell（版本 6 或更高版本）或任何 HTTP 客户端</span><span class="sxs-lookup"><span data-stu-id="6331e-350">Using PowerShell (ver.6 or higher) or any HTTP client</span></span>

<span data-ttu-id="6331e-351">步骤 1：连接到 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="6331e-351">Step 1: Connect to PowerShell.</span></span>

<span data-ttu-id="6331e-352">步骤 2：运行以下脚本。</span><span class="sxs-lookup"><span data-stu-id="6331e-352">Step 2: Run the following script.</span></span>

<table>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6331e-353">param([string]$baseUri)</span><span class="sxs-lookup"><span data-stu-id="6331e-353">param([string]$baseUri)</span></span></p>
<p><span data-ttu-id="6331e-354">$userName = &quot;UserName&quot;</span><span class="sxs-lookup"><span data-stu-id="6331e-354">$userName = &quot;UserName&quot;</span></span></p>
<p><span data-ttu-id="6331e-355">$password = &quot;Password&quot;</span><span class="sxs-lookup"><span data-stu-id="6331e-355">$password = &quot;Password&quot;</span></span></p>
<p><span data-ttu-id="6331e-356">$securePassword = ConvertTo-SecureString $password -AsPlainText -Force</span><span class="sxs-lookup"><span data-stu-id="6331e-356">$securePassword = ConvertTo-SecureString $password -AsPlainText -Force</span></span></p>
<p><span data-ttu-id="6331e-357">$credentials = New-Object System.Management.Automation.PSCredential($userName, $securePassword)</span><span class="sxs-lookup"><span data-stu-id="6331e-357">$credentials = New-Object System.Management.Automation.PSCredential($userName, $securePassword)</span></span></p>
<p><span data-ttu-id="6331e-358">$EventName=&quot;EventByRESTPost-$(([Guid]::NewGuid()).ToString('N'))&quot;</span><span class="sxs-lookup"><span data-stu-id="6331e-358">$EventName=&quot;EventByRESTPost-$(([Guid]::NewGuid()).ToString('N'))&quot;</span></span></p>
<p><span data-ttu-id="6331e-359">Write-Host &quot;Start to create an event with name: $EventName&quot;</span><span class="sxs-lookup"><span data-stu-id="6331e-359">Write-Host &quot;Start to create an event with name: $EventName&quot;</span></span></p>
<p><span data-ttu-id="6331e-360">$body = &quot;&lt;?xml version='1.0' encoding='utf-8' standalone='yes'?&gt;</span><span class="sxs-lookup"><span data-stu-id="6331e-360">$body = &quot;&lt;?xml version='1.0' encoding='utf-8' standalone='yes'?&gt;</span></span></p>
<p><span data-ttu-id="6331e-361">&lt;entry xmlns:d='http://schemas.microsoft.com/ado/2007/08/dataservices'</span><span class="sxs-lookup"><span data-stu-id="6331e-361">&lt;entry xmlns:d='http://schemas.microsoft.com/ado/2007/08/dataservices'</span></span></p>
<p><span data-ttu-id="6331e-362">xmlns:m='http://schemas.microsoft.com/ado/2007/08/dataservices/metadata'</span><span class="sxs-lookup"><span data-stu-id="6331e-362">xmlns:m='http://schemas.microsoft.com/ado/2007/08/dataservices/metadata'</span></span></p>
<p><span data-ttu-id="6331e-363">xmlns='http://www.w3.org/2005/Atom'&gt;</span><span class="sxs-lookup"><span data-stu-id="6331e-363">xmlns='http://www.w3.org/2005/Atom'&gt;</span></span></p>
<p><span data-ttu-id="6331e-364">&lt;category scheme='http://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' /&gt;</span><span class="sxs-lookup"><span data-stu-id="6331e-364">&lt;category scheme='http://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' /&gt;</span></span></p>
<p><span data-ttu-id="6331e-365">&lt;updated&gt;7/14/2017 2:03:36 PM&lt;/updated&gt;</span><span class="sxs-lookup"><span data-stu-id="6331e-365">&lt;updated&gt;7/14/2017 2:03:36 PM&lt;/updated&gt;</span></span></p>
<p><span data-ttu-id="6331e-366">&lt;content type='application/xml'&gt;</span><span class="sxs-lookup"><span data-stu-id="6331e-366">&lt;content type='application/xml'&gt;</span></span></p>
<p><span data-ttu-id="6331e-367">&lt;m:properties&gt;</span><span class="sxs-lookup"><span data-stu-id="6331e-367">&lt;m:properties&gt;</span></span></p>
<p><span data-ttu-id="6331e-368">&lt;d:Name&gt;$EventName&lt;/d:Name&gt;</span><span class="sxs-lookup"><span data-stu-id="6331e-368">&lt;d:Name&gt;$EventName&lt;/d:Name&gt;</span></span></p>
<p><span data-ttu-id="6331e-369">&lt;d:EventType&gt;e823b782-9a07-4e30-8091-034fc01f9347&lt;/d:EventType&gt;</span><span class="sxs-lookup"><span data-stu-id="6331e-369">&lt;d:EventType&gt;e823b782-9a07-4e30-8091-034fc01f9347&lt;/d:EventType&gt;</span></span></p>
<p><span data-ttu-id="6331e-370">&lt;d:SharePointAssetIdQuery&gt;'ComplianceAssetId:123'&lt;/d:SharePointAssetIdQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="6331e-370">&lt;d:SharePointAssetIdQuery&gt;'ComplianceAssetId:123'&lt;/d:SharePointAssetIdQuery&gt;</span></span></p>
<p><span data-ttu-id="6331e-371">&lt;/m:properties&gt;</span><span class="sxs-lookup"><span data-stu-id="6331e-371">&lt;/m:properties&gt;</span></span></p>
<p><span data-ttu-id="6331e-372">&lt;/content&gt;</span><span class="sxs-lookup"><span data-stu-id="6331e-372">&lt;/content&gt;</span></span></p>
<p><span data-ttu-id="6331e-373">&lt;/entry&gt;&quot;</span><span class="sxs-lookup"><span data-stu-id="6331e-373">&lt;/entry&gt;&quot;</span></span></p>
<p><span data-ttu-id="6331e-374">$event = $null</span><span class="sxs-lookup"><span data-stu-id="6331e-374">$event = $null</span></span></p>
<p><span data-ttu-id="6331e-375">try</span><span class="sxs-lookup"><span data-stu-id="6331e-375">try</span></span></p>
<p><span data-ttu-id="6331e-376">{</span><span class="sxs-lookup"><span data-stu-id="6331e-376">{</span></span></p>
<p><span data-ttu-id="6331e-377">$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri &quot;$baseUri/ComplianceRetentionEvent&quot; -ContentType &quot;application/atom+xml&quot; -Authentication Basic -Credential $credentials -MaximumRedirection 0</span><span class="sxs-lookup"><span data-stu-id="6331e-377">$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri &quot;$baseUri/ComplianceRetentionEvent&quot; -ContentType &quot;application/atom+xml&quot; -Authentication Basic -Credential $credentials -MaximumRedirection 0</span></span></p>
<p><span data-ttu-id="6331e-378">}</span><span class="sxs-lookup"><span data-stu-id="6331e-378">}</span></span></p>
<p><span data-ttu-id="6331e-379">catch</span><span class="sxs-lookup"><span data-stu-id="6331e-379">catch</span></span></p>
<p><span data-ttu-id="6331e-380">{</span><span class="sxs-lookup"><span data-stu-id="6331e-380">{</span></span></p>
<p><span data-ttu-id="6331e-381">$response = $_.Exception.Response</span><span class="sxs-lookup"><span data-stu-id="6331e-381">$response = $_.Exception.Response</span></span></p>
<p><span data-ttu-id="6331e-382">if($response.StatusCode -eq &quot;Redirect&quot;)</span><span class="sxs-lookup"><span data-stu-id="6331e-382">if($response.StatusCode -eq &quot;Redirect&quot;)</span></span></p>
<p><span data-ttu-id="6331e-383">{</span><span class="sxs-lookup"><span data-stu-id="6331e-383">{</span></span></p>
<p><span data-ttu-id="6331e-384">$url = $response.Headers.Location</span><span class="sxs-lookup"><span data-stu-id="6331e-384">$url = $response.Headers.Location</span></span></p>
<p><span data-ttu-id="6331e-385">Write-Host &quot;redirected to $url&quot;</span><span class="sxs-lookup"><span data-stu-id="6331e-385">Write-Host &quot;redirected to $url&quot;</span></span></p>
<p><span data-ttu-id="6331e-386">$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri $url -ContentType &quot;application/atom+xml&quot; -Authentication Basic -Credential $credentials -MaximumRedirection 0</span><span class="sxs-lookup"><span data-stu-id="6331e-386">$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri $url -ContentType &quot;application/atom+xml&quot; -Authentication Basic -Credential $credentials -MaximumRedirection 0</span></span></p>
<p><span data-ttu-id="6331e-387">}</span><span class="sxs-lookup"><span data-stu-id="6331e-387">}</span></span></p>
<p><span data-ttu-id="6331e-388">}</span><span class="sxs-lookup"><span data-stu-id="6331e-388">}</span></span></p>
<p><span data-ttu-id="6331e-389">$event | fl \*</span><span class="sxs-lookup"><span data-stu-id="6331e-389">$event | fl \*</span></span></p></td>
</tr>
</tbody>
</table>

#### <a name="verify-the-outcome-in-both-options"></a><span data-ttu-id="6331e-390">验证两个选项的结果</span><span class="sxs-lookup"><span data-stu-id="6331e-390">Verify the outcome in both options</span></span>

<span data-ttu-id="6331e-391">步骤 1：转到安全与合规中心</span><span class="sxs-lookup"><span data-stu-id="6331e-391">Step 1: Go to Security & Compliance Center</span></span>

<span data-ttu-id="6331e-392">步骤 2：单击“数据治理”下的“事件”</span><span class="sxs-lookup"><span data-stu-id="6331e-392">Step 2: Click on Events under Data Governance</span></span>

<span data-ttu-id="6331e-393">步骤 3：验证已创建事件。</span><span class="sxs-lookup"><span data-stu-id="6331e-393">Step 3: Verify Event has been created.</span></span>

<span data-ttu-id="6331e-394">同样，上述用于自动执行基于事件的保留的选项也可用于以下场景。</span><span class="sxs-lookup"><span data-stu-id="6331e-394">Similarly, the above options to automate event based retention can be used for the following scenarios as well.</span></span>

### <a name="scenario-2-contracts-expiring"></a><span data-ttu-id="6331e-395">场景 2：合同到期</span><span class="sxs-lookup"><span data-stu-id="6331e-395">Scenario 2: Contracts Expiring</span></span>

<span data-ttu-id="6331e-p122">对于与客户、供应商和合作伙伴签订的单份合同，组织可能拥有多条记录。这些文档可以驻留在 SharePoint 等文档库中。合同的终止决定了与合同关联的文档保留期的开始。例如：与合同相关的所有记录都需要在合同到期后保留 5 年。触发 5 年保留期的事件是合同到期。</span><span class="sxs-lookup"><span data-stu-id="6331e-p122">An organization can have multiple records for a single contract with customers, vendors and partners. These documents can reside in a document library like SharePoint. The ending of a contract determines the start of the retention period of the documents associated with the contract. For example: all records related to contracts need to be retained for five years from the time the contract expires. The event that triggers the five-year retention period is the expiration of the contract.</span></span>

<span data-ttu-id="6331e-401">客户关系管理 (CRM) 系统可以与 Microsoft 365 一起使用，用于触发合同文档的保留。</span><span class="sxs-lookup"><span data-stu-id="6331e-401">A Customer Relationship Management (CRM) system can work with Microsoft 365 and trigger retention of Contract documents</span></span>

<span data-ttu-id="6331e-402">**为此场景配置基于事件的自动保留：**</span><span class="sxs-lookup"><span data-stu-id="6331e-402">**Configuring Automated Event Based Retention for this scenario:**</span></span>

![针对合同到期场景的角色和任务关系图](media/automate-event-driven-retention-contract-expiration.png)

  - <span data-ttu-id="6331e-404">管理员为每种合同类型创建一个包含各种文件夹的 SharePoint 库。</span><span class="sxs-lookup"><span data-stu-id="6331e-404">Admin creates a SharePoint library with various folders for each contract type.</span></span>

  - <span data-ttu-id="6331e-405">管理员将合同文件（如许可合同、开发合同）添加到每个合同文件夹</span><span class="sxs-lookup"><span data-stu-id="6331e-405">Admin adds contract files such as License Contracts, Development Contracts to each contract folder</span></span>

  - <span data-ttu-id="6331e-406">管理员为每个合同文件夹分配资产 ID</span><span class="sxs-lookup"><span data-stu-id="6331e-406">Admin assigns Asset Id to each contract folder</span></span>

  - <span data-ttu-id="6331e-407">SCC 管理员登录到安全与合规中心</span><span class="sxs-lookup"><span data-stu-id="6331e-407">SCC Admin logs into the Security & Compliance Center</span></span>

  - <span data-ttu-id="6331e-408">SCC 管理员创建与合同相关的事件类型，例如“合同创建”和“合同到期”事件。</span><span class="sxs-lookup"><span data-stu-id="6331e-408">SCC Admin creates contract related events types such as “Contract Creation”, “Contract Expiration” events.</span></span>

  - <span data-ttu-id="6331e-409">SCC 管理员创建“合同到期”标签。</span><span class="sxs-lookup"><span data-stu-id="6331e-409">SCC Admin creates “Contract Expiration” label.</span></span>

  - <span data-ttu-id="6331e-410">此“合同到期”标签将手动或自动发布并应用于 SharePoint 中的合同文件</span><span class="sxs-lookup"><span data-stu-id="6331e-410">This “ Contract Expiration” label is published and applied manually or automatically to the contract files in SharePoint</span></span>

  - <span data-ttu-id="6331e-411">合同管理系统可以与 Microsoft Flow 或类似的应用程序一起定期运行以管理合同文件</span><span class="sxs-lookup"><span data-stu-id="6331e-411">Contract Management System can work with Microsoft Flow or a similar application to run periodically to manage contract files</span></span>

  - <span data-ttu-id="6331e-412">如果合同到期，Microsoft Flow 将触发 M365 基于事件的保留 REST API，该 API 将开始特定合同文件的保留期。</span><span class="sxs-lookup"><span data-stu-id="6331e-412">If a contract expires, Microsoft Flow will trigger the M365 Event Based Retention REST API that will begin the retention clock on the specific contract’s files.</span></span>

### <a name="scenario-3-end-of-product-manufacturing"></a><span data-ttu-id="6331e-413">场景 3：产品制造终止</span><span class="sxs-lookup"><span data-stu-id="6331e-413">Scenario 3: End of Product Manufacturing</span></span>

<span data-ttu-id="6331e-p123">一家生产不同产品系列的制造公司创建了许多制造规格和定价文件。当不再生产某款产品时，与该产品相关的所有规格和文件都需要在产品生存期结束后的特定时间内保留。</span><span class="sxs-lookup"><span data-stu-id="6331e-p123">A manufacturing company that produces different lines of products creates many manufacturing specifications and pricing documents. When the product is no longer manufactured, all specifications and documents linked to this product need to be retained for a specific period after the end of the lifetime of the product.</span></span>

<span data-ttu-id="6331e-416">企业资源规划 (ERP) 系统可以与 Microsoft 365 和 Microsoft Flow 一起使用，用于触发保留。</span><span class="sxs-lookup"><span data-stu-id="6331e-416">An Enterprise Resource Planning (ERP) system can work with Microsoft 365 and Microsoft Flow to trigger retention.</span></span>

<span data-ttu-id="6331e-417">**为此场景配置基于事件的自动保留：**</span><span class="sxs-lookup"><span data-stu-id="6331e-417">**Configuring Automated Event Based Retention for this scenario:**</span></span>

![产品生命周期场景的角色和任务关系图](media/automate-event-driven-retention-product-lifecycle-expiration.png)

  - <span data-ttu-id="6331e-419">管理员在文档集中创建产品文件夹，如产品 1、产品 2 等。</span><span class="sxs-lookup"><span data-stu-id="6331e-419">Admin creates product folders in the Document set such as Product 1, Product 2, etc.</span></span>

  - <span data-ttu-id="6331e-420">管理员将产品文件（如制造规格、产品定价、产品许可）添加到每个产品文件夹中</span><span class="sxs-lookup"><span data-stu-id="6331e-420">Admin adds product files such as Manufacturing Specifications, Product Pricing, Product licensing to each product folder</span></span>

  - <span data-ttu-id="6331e-421">管理员为每个产品文件夹分配资产 ID。</span><span class="sxs-lookup"><span data-stu-id="6331e-421">Admin assigns Asset Id to each productfolder.</span></span>

  - <span data-ttu-id="6331e-422">SCC 管理员登录到安全与合规中心</span><span class="sxs-lookup"><span data-stu-id="6331e-422">SCC Admin logs into the Security & Compliance Center</span></span>

  - <span data-ttu-id="6331e-423">SCC 管理员创建与员工相关的事件类型，例如“产品制造开始”和“产品制造结束”事件。</span><span class="sxs-lookup"><span data-stu-id="6331e-423">SCC Admin creates employee related events types such as “Start of Product Manufacturing”, “End of Product Manufacturing” events.</span></span>

  - <span data-ttu-id="6331e-424">SCC 管理员创建“产品制造结束”标签。</span><span class="sxs-lookup"><span data-stu-id="6331e-424">SCC Admin creates “End of Product Manufacturing” label.</span></span>

  - <span data-ttu-id="6331e-425">此“产品制造终止”标签将手动或自动发布并应用于 SharePoint 中的产品文件</span><span class="sxs-lookup"><span data-stu-id="6331e-425">This “ End of Product Manufacturing” label is published and applied manually or automatically to the product files in SharePoint</span></span>

  - <span data-ttu-id="6331e-426">ERP 系统可以与 Microsoft Flow 或类似的应用程序一起定期运行以管理产品文件</span><span class="sxs-lookup"><span data-stu-id="6331e-426">ERP Systems can work with Microsoft Flow or similar applications to run periodically to manage product files</span></span>

  - <span data-ttu-id="6331e-427">如果产品制造终止，Microsoft Flow 将触发 M365 基于事件的保留 REST API，该 API 将开始特定产品文件的保留期。</span><span class="sxs-lookup"><span data-stu-id="6331e-427">If the manufacturing of a product ends, Microsoft Flow will trigger the M365 Event Based Retention REST API that will begin the retention clock on the specific product’s files.</span></span>

## <a name="appendix"></a><span data-ttu-id="6331e-428">附录</span><span class="sxs-lookup"><span data-stu-id="6331e-428">Appendix</span></span>

### <a name="using-redirect-302-response-results-to-call-the-rest-api"></a><span data-ttu-id="6331e-429">使用重定向 302 响应结果来调用 REST API</span><span class="sxs-lookup"><span data-stu-id="6331e-429">Using Redirect 302 response results to call the REST API</span></span>

1.  <span data-ttu-id="6331e-430">使用 REST API URL <https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent> 调用 POST 保留事件调用（需要全局管理员权限）</span><span class="sxs-lookup"><span data-stu-id="6331e-430">Invoke a POST retention event call using the REST API URL <https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent> (Global Admin permissions are required)</span></span>

2.  <span data-ttu-id="6331e-p124">检查响应代码。如果是 302，则从响应标头的“位置”属性中获取重定向的 URL</span><span class="sxs-lookup"><span data-stu-id="6331e-p124">Check the response code. If it’s 302, then get the redirected URL from Location property of the response header</span></span>

3.  <span data-ttu-id="6331e-433">使用重定向的 URL 再次调用 POST 保留事件调用。</span><span class="sxs-lookup"><span data-stu-id="6331e-433">Invoke the POST retention event call again using the redirected URL.</span></span>

## <a name="credits"></a><span data-ttu-id="6331e-434">制作人员</span><span class="sxs-lookup"><span data-stu-id="6331e-434">Credits</span></span>

<span data-ttu-id="6331e-435">本主题经过以下人员的审阅：</span><span class="sxs-lookup"><span data-stu-id="6331e-435">This topic was reviewed by:</span></span>

<span data-ttu-id="6331e-436">Antonio Maio</span><span class="sxs-lookup"><span data-stu-id="6331e-436">Antonio Maio</span></span><br/><span data-ttu-id="6331e-437">Microsoft Office 应用和服务 MVP</span><span class="sxs-lookup"><span data-stu-id="6331e-437">Microsoft Office Apps and Services MVP</span></span><br/> <span data-ttu-id="6331e-438">Antonio.Maio@Protiviti.com</span><span class="sxs-lookup"><span data-stu-id="6331e-438">Antonio.Maio@Protiviti.com</span></span>
