---
title: 创建搜索项来收集数据
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 14f90b29cbff9c1a588b816563178039c7af7da6
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/26/2019
ms.locfileid: "30295955"
---
# <a name="create-a-search-to-collect-data"></a><span data-ttu-id="c5b5d-102">创建搜索项来收集数据</span><span class="sxs-lookup"><span data-stu-id="c5b5d-102">Create a search to collect data</span></span>

<span data-ttu-id="c5b5d-103">在您的案例的 "**搜索**" 选项卡上, 您可以通过单击 "**新建搜索**" 并按照向导创建新的搜索。</span><span class="sxs-lookup"><span data-stu-id="c5b5d-103">On the **Searches** tab in your case, you can create a new search by clicking **New search** and following the wizard.</span></span>

## <a name="name-your-search-and-give-description"></a><span data-ttu-id="c5b5d-104">命名您的搜索并提供说明</span><span class="sxs-lookup"><span data-stu-id="c5b5d-104">Name your search and give description</span></span>

<span data-ttu-id="c5b5d-p101">每个具有事例的搜索应具有唯一的名称。您可以选择为搜索提供说明。</span><span class="sxs-lookup"><span data-stu-id="c5b5d-p101">Each search with a case should have a unique name. You can optionally provide a description for your search.</span></span> 

## <a name="define-your-conditions"></a><span data-ttu-id="c5b5d-107">定义条件</span><span class="sxs-lookup"><span data-stu-id="c5b5d-107">Define your conditions</span></span>

<span data-ttu-id="c5b5d-p102">您可以使用预建的条件卡或使用关键字查询语言 (KQL) 定义搜索条件。有关详细信息, 请参阅[构建搜索查询](building-search-queries.md)。</span><span class="sxs-lookup"><span data-stu-id="c5b5d-p102">You can define the conditions for your search using the pre-built condition cards or using Keyword Query Language (KQL). For more information, see [Build search queries](building-search-queries.md).</span></span>

## <a name="choose-the-custodians-to-search-from"></a><span data-ttu-id="c5b5d-110">选择要从中搜索的保管人</span><span class="sxs-lookup"><span data-stu-id="c5b5d-110">Choose the custodians to search from</span></span>

<span data-ttu-id="c5b5d-p103">定义条件后, 需要选择要搜索的位置。执行此操作的一种方法是指定您已添加到您要搜索的事例的保管人。通过选择管理员, 你将对映射到保管人的所有数据源运行搜索。有关如何将保管人添加到你的事例并管理其数据源的详细信息, 请参阅[使用保管人](managing-custodians.md)。</span><span class="sxs-lookup"><span data-stu-id="c5b5d-p103">Once you have defined your conditions, you need to choose which locations you want to search. One way to do it is by specifying which custodians you have already added to the case you want to search. By selecting a custodian, you will run the search against all data sources mapped to the custodian. See [Work with custodians](managing-custodians.md) for more information on how to add custodians to your case and manage their data sources.</span></span>

## <a name="choose-non-custodial-locations"></a><span data-ttu-id="c5b5d-115">选择非 custodial 位置</span><span class="sxs-lookup"><span data-stu-id="c5b5d-115">Choose non-custodial locations</span></span>

<span data-ttu-id="c5b5d-p104">在某些情况下, 您可能希望搜索未映射到保管人的数据源。在这种情况下, 您可以指定要搜索的位置, 或选择搜索特定 Office 365 服务的所有内容位置 (例如, 搜索所有 Exchange 邮箱或所有 SharePoint 和 OneDrive for business 网站)。</span><span class="sxs-lookup"><span data-stu-id="c5b5d-p104">In some cases, you may wish to search data sources that are not mapped to a custodian. In this case, you can specify the locations you would like to search, or choose to search all content locations for a specific Office 365 service (such as searching all Exchange mailboxes or all SharePoint and OneDrive for Business sites).</span></span>