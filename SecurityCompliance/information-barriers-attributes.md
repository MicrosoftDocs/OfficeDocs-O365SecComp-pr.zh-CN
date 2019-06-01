---
title: 信息屏障策略的属性
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 05/31/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
description: 使用本文作为对可在信息屏障策略中使用的各种属性的参考。
ms.openlocfilehash: e72e37950442974897de479c7c11f0053a578d1c
ms.sourcegitcommit: 4fedeb06a6e7796096fc6279cfb091c7b89d484d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/31/2019
ms.locfileid: "34668280"
---
# <a name="attributes-for-information-barrier-policies-preview"></a><span data-ttu-id="bffba-103">信息屏障策略的属性 (预览)</span><span class="sxs-lookup"><span data-stu-id="bffba-103">Attributes for information barrier policies (Preview)</span></span>

<span data-ttu-id="bffba-104">Azure Active Directory 中的某些属性可用于分段用户。</span><span class="sxs-lookup"><span data-stu-id="bffba-104">Certain attributes in Azure Active Directory can be used to segment users.</span></span> <span data-ttu-id="bffba-105">然后, 将段用作信息屏障策略的筛选器。</span><span class="sxs-lookup"><span data-stu-id="bffba-105">Segments are then used as filters for information barrier policies.</span></span> <span data-ttu-id="bffba-106">例如, 您可以使用**部门**按组织中的部门定义用户的分段 (假设没有一个员工同时适用于两个部门)。</span><span class="sxs-lookup"><span data-stu-id="bffba-106">For example, you might use **Department** to define segments of users by department within your organization (assuming no single employee works for two departments at the same time).</span></span> 

<span data-ttu-id="bffba-107">本文提供可使用的属性的列表。</span><span class="sxs-lookup"><span data-stu-id="bffba-107">This article provides a list of attributes that can be used.</span></span> <span data-ttu-id="bffba-108">若要了解有关信息障碍的详细信息, 请参阅以下资源:</span><span class="sxs-lookup"><span data-stu-id="bffba-108">To learn more about information barriers, see the following resources:</span></span>
- [<span data-ttu-id="bffba-109">信息障碍 (预览)</span><span class="sxs-lookup"><span data-stu-id="bffba-109">Information barriers (Preview)</span></span>](information-barriers.md)
- [<span data-ttu-id="bffba-110">为 Microsoft 团队中的信息障碍定义策略 (预览)</span><span class="sxs-lookup"><span data-stu-id="bffba-110">Define policies for information barriers in Microsoft Teams (Preview)</span></span>](information-barriers-policies.md)

## <a name="how-to-use-attributes-in-information-barrier-policies"></a><span data-ttu-id="bffba-111">如何在信息屏障策略中使用属性</span><span class="sxs-lookup"><span data-stu-id="bffba-111">How to use attributes in information barrier policies</span></span>

<span data-ttu-id="bffba-112">本文中列出的属性可用于定义 (或编辑) 用户的各个部分。</span><span class="sxs-lookup"><span data-stu-id="bffba-112">The attributes listed in this article can be used to define (or edit) segments of users.</span></span> <span data-ttu-id="bffba-113">在信息屏障策略中, 段用作参数 (UserGroupFilter), 如以下示例所示:</span><span class="sxs-lookup"><span data-stu-id="bffba-113">Segments are used as parameters (UserGroupFilter) in information barrier policies, as shown in the following examples:</span></span>

|<span data-ttu-id="bffba-114">示例</span><span class="sxs-lookup"><span data-stu-id="bffba-114">Example</span></span>  |<span data-ttu-id="bffba-115">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="bffba-115">Cmdlet</span></span>  |
|---------|---------|
|<span data-ttu-id="bffba-116">使用部门属性定义名为 Segment1 的段</span><span class="sxs-lookup"><span data-stu-id="bffba-116">Define a segment called Segment1 using the Department attribute</span></span>     | `New-OrganizationSegment -Name "Segment1" -UserGroupFilter "Department -eq 'Department1'"`        |
|<span data-ttu-id="bffba-117">使用 MemberOf 属性定义名为 SegmentA 的段 (假定此属性包含组名称, 例如 "BlueGroup")</span><span class="sxs-lookup"><span data-stu-id="bffba-117">Define a segment called SegmentA using the MemberOf attribute (suppose this attribute contains group names, such as "BlueGroup")</span></span>     | `New-OrganizationSegment -Name "SegmentA" -UserGroupFilter "MemberOf -eq 'BlueGroup'"`        |
|<span data-ttu-id="bffba-118">使用 ExtensionAttribute1 定义名为 DayTraders 的段 (假设此属性包含职务, 如 "DayTrader")</span><span class="sxs-lookup"><span data-stu-id="bffba-118">Define a segment called DayTraders using ExtensionAttribute1 (suppose this attribute contains job titles, such as "DayTrader")</span></span>|`New-OrganizationSegment -Name "DayTraders" -UserGroupFilter "ExtensionAttribute1 -eq 'DayTrader'"` |

<span data-ttu-id="bffba-119">在定义段时, 请对所有段使用相同的属性。</span><span class="sxs-lookup"><span data-stu-id="bffba-119">When you define segments, use the same attribute for all your segments.</span></span> <span data-ttu-id="bffba-120">例如, 如果使用*部门*定义一些分段, 则使用*部门*定义所有分段。</span><span class="sxs-lookup"><span data-stu-id="bffba-120">For example, if you define some segments using *Department*, define all of the segments using *Department*.</span></span> <span data-ttu-id="bffba-121">请勿使用使用*MemberOf*的*部门*和其他部门定义某些分段。</span><span class="sxs-lookup"><span data-stu-id="bffba-121">Don't define some segments using *Department* and others using *MemberOf*.</span></span> <span data-ttu-id="bffba-122">请确保您的段不重叠;应将每个用户仅分配给一个分段。</span><span class="sxs-lookup"><span data-stu-id="bffba-122">Make sure your segments do not overlap; each user should be assigned to exactly one segment.</span></span> 

<span data-ttu-id="bffba-123">若要了解详细信息, 请参阅[使用 PowerShell 定义分段](information-barriers-policies.md#define-segments-using-powershell)。</span><span class="sxs-lookup"><span data-stu-id="bffba-123">To learn more, see [Define segments using PowerShell](information-barriers-policies.md#define-segments-using-powershell).</span></span>

## <a name="reference"></a><span data-ttu-id="bffba-124">参考</span><span class="sxs-lookup"><span data-stu-id="bffba-124">Reference</span></span>

<span data-ttu-id="bffba-125">下表列出了可用于信息障碍的属性。</span><span class="sxs-lookup"><span data-stu-id="bffba-125">The following table lists the attributes that you can use with information barriers.</span></span>

|<span data-ttu-id="bffba-126">Azure Active Directory 属性名称 (LDAP 显示名称)</span><span class="sxs-lookup"><span data-stu-id="bffba-126">Azure Active Directory property name (LDAP display name)</span></span>  |<span data-ttu-id="bffba-127">Exchange 属性名称</span><span class="sxs-lookup"><span data-stu-id="bffba-127">Exchange property name</span></span>  |
|---------|---------|
|<span data-ttu-id="bffba-128">合著</span><span class="sxs-lookup"><span data-stu-id="bffba-128">Co</span></span>       | <span data-ttu-id="bffba-129">合著</span><span class="sxs-lookup"><span data-stu-id="bffba-129">Co</span></span>        |
|<span data-ttu-id="bffba-130">Company</span><span class="sxs-lookup"><span data-stu-id="bffba-130">Company</span></span>     |<span data-ttu-id="bffba-131">公司</span><span class="sxs-lookup"><span data-stu-id="bffba-131">Company</span></span>         |
|<span data-ttu-id="bffba-132">Department</span><span class="sxs-lookup"><span data-stu-id="bffba-132">Department</span></span>     |<span data-ttu-id="bffba-133">Department</span><span class="sxs-lookup"><span data-stu-id="bffba-133">Department</span></span>         |
|<span data-ttu-id="bffba-134">ExtensionAttribute1</span><span class="sxs-lookup"><span data-stu-id="bffba-134">ExtensionAttribute1</span></span> |<span data-ttu-id="bffba-135">CustomAttribute1</span><span class="sxs-lookup"><span data-stu-id="bffba-135">CustomAttribute1</span></span>  |
|<span data-ttu-id="bffba-136">ExtensionAttribute2</span><span class="sxs-lookup"><span data-stu-id="bffba-136">ExtensionAttribute2</span></span> |<span data-ttu-id="bffba-137">CustomAttribute2</span><span class="sxs-lookup"><span data-stu-id="bffba-137">CustomAttribute2</span></span>  |
|<span data-ttu-id="bffba-138">ExtensionAttribute3</span><span class="sxs-lookup"><span data-stu-id="bffba-138">ExtensionAttribute3</span></span> |<span data-ttu-id="bffba-139">CustomAttribute3</span><span class="sxs-lookup"><span data-stu-id="bffba-139">CustomAttribute3</span></span>  |
|<span data-ttu-id="bffba-140">ExtensionAttribute4</span><span class="sxs-lookup"><span data-stu-id="bffba-140">ExtensionAttribute4</span></span> |<span data-ttu-id="bffba-141">CustomAttribute4</span><span class="sxs-lookup"><span data-stu-id="bffba-141">CustomAttribute4</span></span>  |
|<span data-ttu-id="bffba-142">ExtensionAttribute5</span><span class="sxs-lookup"><span data-stu-id="bffba-142">ExtensionAttribute5</span></span> |<span data-ttu-id="bffba-143">CustomAttribute5</span><span class="sxs-lookup"><span data-stu-id="bffba-143">CustomAttribute5</span></span>  |
|<span data-ttu-id="bffba-144">ExtensionAttribute6</span><span class="sxs-lookup"><span data-stu-id="bffba-144">ExtensionAttribute6</span></span> |<span data-ttu-id="bffba-145">CustomAttribute6</span><span class="sxs-lookup"><span data-stu-id="bffba-145">CustomAttribute6</span></span>  |
|<span data-ttu-id="bffba-146">ExtensionAttribute7</span><span class="sxs-lookup"><span data-stu-id="bffba-146">ExtensionAttribute7</span></span> |<span data-ttu-id="bffba-147">CustomAttribute7</span><span class="sxs-lookup"><span data-stu-id="bffba-147">CustomAttribute7</span></span>  |
|<span data-ttu-id="bffba-148">ExtensionAttribute8</span><span class="sxs-lookup"><span data-stu-id="bffba-148">ExtensionAttribute8</span></span> |<span data-ttu-id="bffba-149">CustomAttribute8</span><span class="sxs-lookup"><span data-stu-id="bffba-149">CustomAttribute8</span></span>  |
|<span data-ttu-id="bffba-150">ExtensionAttribute9</span><span class="sxs-lookup"><span data-stu-id="bffba-150">ExtensionAttribute9</span></span> |<span data-ttu-id="bffba-151">CustomAttribute9</span><span class="sxs-lookup"><span data-stu-id="bffba-151">CustomAttribute9</span></span>  |
|<span data-ttu-id="bffba-152">ExtensionAttribute10</span><span class="sxs-lookup"><span data-stu-id="bffba-152">ExtensionAttribute10</span></span> |<span data-ttu-id="bffba-153">CustomAttribute10</span><span class="sxs-lookup"><span data-stu-id="bffba-153">CustomAttribute10</span></span>  |
|<span data-ttu-id="bffba-154">ExtensionAttribute11</span><span class="sxs-lookup"><span data-stu-id="bffba-154">ExtensionAttribute11</span></span> |<span data-ttu-id="bffba-155">CustomAttribute11</span><span class="sxs-lookup"><span data-stu-id="bffba-155">CustomAttribute11</span></span>  |
|<span data-ttu-id="bffba-156">ExtensionAttribute12</span><span class="sxs-lookup"><span data-stu-id="bffba-156">ExtensionAttribute12</span></span> |<span data-ttu-id="bffba-157">CustomAttribute12</span><span class="sxs-lookup"><span data-stu-id="bffba-157">CustomAttribute12</span></span>  |
|<span data-ttu-id="bffba-158">ExtensionAttribute13</span><span class="sxs-lookup"><span data-stu-id="bffba-158">ExtensionAttribute13</span></span> |<span data-ttu-id="bffba-159">CustomAttribute13</span><span class="sxs-lookup"><span data-stu-id="bffba-159">CustomAttribute13</span></span>  |
|<span data-ttu-id="bffba-160">ExtensionAttribute14</span><span class="sxs-lookup"><span data-stu-id="bffba-160">ExtensionAttribute14</span></span> |<span data-ttu-id="bffba-161">CustomAttribute14</span><span class="sxs-lookup"><span data-stu-id="bffba-161">CustomAttribute14</span></span>  |
|<span data-ttu-id="bffba-162">ExtensionAttribute15</span><span class="sxs-lookup"><span data-stu-id="bffba-162">ExtensionAttribute15</span></span> |<span data-ttu-id="bffba-163">CustomAttribute15</span><span class="sxs-lookup"><span data-stu-id="bffba-163">CustomAttribute15</span></span>  |
|<span data-ttu-id="bffba-164">MSExchExtensionCustomAttribute1</span><span class="sxs-lookup"><span data-stu-id="bffba-164">MSExchExtensionCustomAttribute1</span></span> |<span data-ttu-id="bffba-165">ExtensionCustomAttribute1</span><span class="sxs-lookup"><span data-stu-id="bffba-165">ExtensionCustomAttribute1</span></span> |
|<span data-ttu-id="bffba-166">MSExchExtensionCustomAttribute2</span><span class="sxs-lookup"><span data-stu-id="bffba-166">MSExchExtensionCustomAttribute2</span></span> |<span data-ttu-id="bffba-167">ExtensionCustomAttribute2</span><span class="sxs-lookup"><span data-stu-id="bffba-167">ExtensionCustomAttribute2</span></span> |
|<span data-ttu-id="bffba-168">MSExchExtensionCustomAttribute3</span><span class="sxs-lookup"><span data-stu-id="bffba-168">MSExchExtensionCustomAttribute3</span></span> |<span data-ttu-id="bffba-169">ExtensionCustomAttribute3</span><span class="sxs-lookup"><span data-stu-id="bffba-169">ExtensionCustomAttribute3</span></span> |
|<span data-ttu-id="bffba-170">MSExchExtensionCustomAttribute4</span><span class="sxs-lookup"><span data-stu-id="bffba-170">MSExchExtensionCustomAttribute4</span></span> |<span data-ttu-id="bffba-171">ExtensionCustomAttribute4</span><span class="sxs-lookup"><span data-stu-id="bffba-171">ExtensionCustomAttribute4</span></span> |
|<span data-ttu-id="bffba-172">MSExchExtensionCustomAttribute5</span><span class="sxs-lookup"><span data-stu-id="bffba-172">MSExchExtensionCustomAttribute5</span></span> |<span data-ttu-id="bffba-173">ExtensionCustomAttribute5</span><span class="sxs-lookup"><span data-stu-id="bffba-173">ExtensionCustomAttribute5</span></span> |
|<span data-ttu-id="bffba-174">MailNickname</span><span class="sxs-lookup"><span data-stu-id="bffba-174">MailNickname</span></span> |<span data-ttu-id="bffba-175">别名</span><span class="sxs-lookup"><span data-stu-id="bffba-175">Alias</span></span> |
|<span data-ttu-id="bffba-176">PhysicalDeliveryOfficeName</span><span class="sxs-lookup"><span data-stu-id="bffba-176">PhysicalDeliveryOfficeName</span></span> |<span data-ttu-id="bffba-177">Office</span><span class="sxs-lookup"><span data-stu-id="bffba-177">Office</span></span> |
|<span data-ttu-id="bffba-178">PostalCode</span><span class="sxs-lookup"><span data-stu-id="bffba-178">PostalCode</span></span> |<span data-ttu-id="bffba-179">PostalCode</span><span class="sxs-lookup"><span data-stu-id="bffba-179">PostalCode</span></span> |
|<span data-ttu-id="bffba-180">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="bffba-180">ProxyAddresses</span></span> |<span data-ttu-id="bffba-181">EmailAddresses</span><span class="sxs-lookup"><span data-stu-id="bffba-181">EmailAddresses</span></span> |
|<span data-ttu-id="bffba-182">StreetAddress</span><span class="sxs-lookup"><span data-stu-id="bffba-182">StreetAddress</span></span> |<span data-ttu-id="bffba-183">StreetAddress</span><span class="sxs-lookup"><span data-stu-id="bffba-183">StreetAddress</span></span> |
|<span data-ttu-id="bffba-184">TargetAddress</span><span class="sxs-lookup"><span data-stu-id="bffba-184">TargetAddress</span></span> |<span data-ttu-id="bffba-185">ExternalEmailAddress</span><span class="sxs-lookup"><span data-stu-id="bffba-185">ExternalEmailAddress</span></span> |
|<span data-ttu-id="bffba-186">UsageLocation</span><span class="sxs-lookup"><span data-stu-id="bffba-186">UsageLocation</span></span> |<span data-ttu-id="bffba-187">UsageLocation</span><span class="sxs-lookup"><span data-stu-id="bffba-187">UsageLocation</span></span> |
|<span data-ttu-id="bffba-188">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="bffba-188">UserPrincipalName</span></span>  |<span data-ttu-id="bffba-189">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="bffba-189">UserPrincipalName</span></span>  |
|<span data-ttu-id="bffba-190">邮件</span><span class="sxs-lookup"><span data-stu-id="bffba-190">Mail</span></span>   |<span data-ttu-id="bffba-191">WindowsEmailAddress</span><span class="sxs-lookup"><span data-stu-id="bffba-191">WindowsEmailAddress</span></span>    |
|<span data-ttu-id="bffba-192">说明</span><span class="sxs-lookup"><span data-stu-id="bffba-192">Description</span></span>    |<span data-ttu-id="bffba-193">说明</span><span class="sxs-lookup"><span data-stu-id="bffba-193">Description</span></span>    |
|<span data-ttu-id="bffba-194">MemberOf</span><span class="sxs-lookup"><span data-stu-id="bffba-194">MemberOf</span></span>   |<span data-ttu-id="bffba-195">MemberOfGroup</span><span class="sxs-lookup"><span data-stu-id="bffba-195">MemberOfGroup</span></span>  |

## <a name="related-topics"></a><span data-ttu-id="bffba-196">相关主题</span><span class="sxs-lookup"><span data-stu-id="bffba-196">Related topics</span></span>

[<span data-ttu-id="bffba-197">为 Microsoft 团队中的信息障碍定义策略 (预览)</span><span class="sxs-lookup"><span data-stu-id="bffba-197">Define policies for information barriers in Microsoft Teams (Preview)</span></span>](information-barriers-policies.md)

[<span data-ttu-id="bffba-198">解决信息障碍 (预览)</span><span class="sxs-lookup"><span data-stu-id="bffba-198">Troubleshooting information barriers (Preview)</span></span>](information-barriers-troubleshooting.md)

[<span data-ttu-id="bffba-199">信息障碍 (预览)</span><span class="sxs-lookup"><span data-stu-id="bffba-199">Information barriers (Preview)</span></span>](information-barriers.md)



