---
title: 设置 Office 365 高级电子数据展示中的用户和事例
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 60ffd80b-4376-419d-b6e4-a72029b9907c
description: '了解如何配置用户角色、 创建用例，并为用户分配 Office 365 高级电子数据展示中的情况下。  '
ms.openlocfilehash: 49f76b415d86035cecafc19c23b36c413f7576e5
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525661"
---
# <a name="set-up-users-and-cases-in-office-365-advanced-ediscovery"></a><span data-ttu-id="0adff-103">设置 Office 365 高级电子数据展示中的用户和事例</span><span class="sxs-lookup"><span data-stu-id="0adff-103">Set up users and cases in Office 365 Advanced eDiscovery</span></span>

<span data-ttu-id="0adff-104">本主题介绍如何设置用户和 Office 365 高级电子数据展示案例。</span><span class="sxs-lookup"><span data-stu-id="0adff-104">This topic describes how to set up users and cases for Office 365 Advanced eDiscovery.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0adff-p101">高级电子数据展示需要为您的组织使用的高级合规性加载项或 E5 订阅 Office 365 E3。如果您不具有该计划，并且想要尝试高级电子数据展示，您还可以[注册试用版的 Office 365 企业 E5](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="0adff-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
## <a name="prerequisites"></a><span data-ttu-id="0adff-107">先决条件</span><span class="sxs-lookup"><span data-stu-id="0adff-107">Prerequisites</span></span>

<span data-ttu-id="0adff-108">之前设置用例和高级电子数据展示中的用户，则需要：</span><span class="sxs-lookup"><span data-stu-id="0adff-108">Before setting up cases and users in Advanced eDiscovery, the following is required:</span></span>
  
- <span data-ttu-id="0adff-p102">若要分析使用高级电子数据展示的用户的数据，用户 (数据的 custodian) 必须分配的 Office 365 E5 许可证。此外，可使用 Office 365 E1 或 E3 许可证的用户分配的高级电子数据展示独立许可证。管理员和合规部主管分配给情况下，并使用高级电子数据展示以分析数据不需要 E5 许可证。</span><span class="sxs-lookup"><span data-stu-id="0adff-p102">To analyze a user's data using Advanced eDiscovery, the user (the custodian of the data) must be assigned an Office 365 E5 license. Alternatively, users with an Office 365 E1 or E3 license can be assigned an Advanced eDiscovery standalone license. Administrators and compliance officers who are assigned to cases and use Advanced eDiscovery to analyze data don't need an E5 license.</span></span> 
    
- <span data-ttu-id="0adff-p103">您必须是 Office 365 安全性的电子数据展示管理员角色组的成员&amp;合规性中心创建电子数据展示事例并向其添加成员。若要将自己添加到电子数据展示管理员角色组安全性&amp;合规性中心，您必须是 Office 365 组织中的全局管理员。如果您不是全局管理员，您将需要提出全局管理员才能将您添加到电子数据展示管理员角色组。有关详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="0adff-p103">You have to be a member of the eDiscovery Manager role group in the Office 365 Security &amp; Compliance Center to create an eDiscovery case and add members to it. To add yourself to the eDiscovery Manager role group in Security &amp; Compliance Center, you have to be a global administrator in your Office 365 organization. If you're not a global administrator, you 'll have to ask a global administrator to add you to the eDiscovery Manager role group. For more information, see:</span></span>
    
  - [<span data-ttu-id="0adff-116">Office 365 安全性权限&amp;合规性中心</span><span class="sxs-lookup"><span data-stu-id="0adff-116">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
    
  - [<span data-ttu-id="0adff-117">分配 Office 365 安全性的电子数据展示权限&amp;合规性中心</span><span class="sxs-lookup"><span data-stu-id="0adff-117">Assign eDiscovery permissions in the Office‍ 365 Security &amp; Compliance Center</span></span>](assign-ediscovery-permissions.md)
    
## <a name="step-1-assign-users-ediscovery-permissions"></a><span data-ttu-id="0adff-118">步骤 1： 向用户分配了电子数据展示权限</span><span class="sxs-lookup"><span data-stu-id="0adff-118">Step 1: Assign users eDiscovery permissions</span></span>

<span data-ttu-id="0adff-p104">第一步是向用户分配安全性要求权限&amp;合规性中心，以便他们可以我添加为电子数据展示事例的成员。将用户添加安全中用例的成员身份后&amp;合规性中心，他们将能够访问高级电子数据展示中的情况。</span><span class="sxs-lookup"><span data-stu-id="0adff-p104">The first step is to assign users the requirement permissions in the Security &amp; Compliance Center so that they can me added as a member of an eDiscovery case. After a user is added as a member of a case in the Security &amp; Compliance Center, they'll be able to access the case in Advanced eDiscovery.</span></span>
  
<span data-ttu-id="0adff-121">若要将用户分配所需的权限，以便他们可以添加为电子数据展示事例的成员，请参阅步骤 1 中[Office 365 安全性的电子数据展示事例&amp;合规性中心](ediscovery-cases.md#step-1-assign-ediscovery-permissions-to-potential-case-members)。</span><span class="sxs-lookup"><span data-stu-id="0adff-121">To assign a user the necessary permissions so they can be added as a member of an eDiscovery case, see Step 1 in [eDiscovery cases in the Office 365 Security &amp; Compliance Center](ediscovery-cases.md#step-1-assign-ediscovery-permissions-to-potential-case-members).</span></span>
  
## <a name="step-2-create-an-ediscovery-case-and-add-members"></a><span data-ttu-id="0adff-122">步骤 2： 创建电子数据展示事例并添加成员</span><span class="sxs-lookup"><span data-stu-id="0adff-122">Step 2: Create an eDiscovery case and add members</span></span>

<span data-ttu-id="0adff-p105">下一步是在安全中创建新的电子数据展示事例&amp;合规性中心并添加成员。然后，大小写的成员能够访问高级电子数据展示中的情况。</span><span class="sxs-lookup"><span data-stu-id="0adff-p105">The next step is to create a new eDiscovery case in the Security &amp; Compliance Center and add members. Members of the case will then be able to access the case in Advanced eDiscovery.</span></span>
  
1. <span data-ttu-id="0adff-125">若要创建新的电子数据展示案例，请参阅中的步骤 2 [Office 365 安全性的电子数据展示事例&amp;合规性中心](ediscovery-cases.md#step-2-create-a-new-case)。</span><span class="sxs-lookup"><span data-stu-id="0adff-125">To create a new eDiscovery case, see Step 2 in [eDiscovery cases in the Office 365 Security &amp; Compliance Center](ediscovery-cases.md#step-2-create-a-new-case).</span></span>
    
2. <span data-ttu-id="0adff-126">若要将成员添加到电子数据展示事例，请参阅中的步骤 3 [Office 365 安全性的电子数据展示事例&amp;合规性中心](ediscovery-cases.md#step-3-add-members-to-a-case)</span><span class="sxs-lookup"><span data-stu-id="0adff-126">To add members to an eDiscovery case, see Step 3 in [eDiscovery cases in the Office 365 Security &amp; Compliance Center](ediscovery-cases.md#step-3-add-members-to-a-case)</span></span>
    
## <a name="step-3-go-a-case-in-advanced-ediscovery"></a><span data-ttu-id="0adff-127">步骤 3： 转中高级电子数据展示案例</span><span class="sxs-lookup"><span data-stu-id="0adff-127">Step 3: Go a case in Advanced eDiscovery</span></span>

<span data-ttu-id="0adff-p106">创建电子数据展示事例并添加成员后，您 （或用例的任何成员） 可以访问高级电子数据展示中相应的大小写。若要访问高级电子数据展示中的种情况下，请参阅中的步骤 8 [Office 365 安全性的电子数据展示事例&amp;合规性中心](ediscovery-cases.md#step-8-go-to-the-case-in-advanced-ediscovery)。</span><span class="sxs-lookup"><span data-stu-id="0adff-p106">After you create an eDiscovery case and add members, you (or any member of the case) can access the corresponding case in Advanced eDiscovery. To access a case in Advanced eDiscovery, see Step 8 in [eDiscovery cases in the Office 365 Security &amp; Compliance Center](ediscovery-cases.md#step-8-go-to-the-case-in-advanced-ediscovery).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="0adff-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0adff-130">See also</span></span>

[<span data-ttu-id="0adff-131">Office 365 高级电子数据展示</span><span class="sxs-lookup"><span data-stu-id="0adff-131">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="0adff-132">准备数据</span><span class="sxs-lookup"><span data-stu-id="0adff-132">Preparing data</span></span>](prepare-data-for-advanced-ediscovery.md)
  
[<span data-ttu-id="0adff-133">用户角色和访问</span><span class="sxs-lookup"><span data-stu-id="0adff-133">User roles and access</span></span>](user-roles-and-access-in-advanced-ediscovery.md)

