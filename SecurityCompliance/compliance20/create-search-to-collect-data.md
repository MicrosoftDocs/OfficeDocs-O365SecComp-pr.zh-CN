---
title: 创建搜索项来收集数据
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 773137cbfc73d449766e04bf7eccc77f8bdd0cca
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/11/2019
ms.locfileid: "29706133"
---
# <a name="create-a-search-to-collect-data"></a><span data-ttu-id="9c119-102">创建搜索项来收集数据</span><span class="sxs-lookup"><span data-stu-id="9c119-102">Create a search to collect data</span></span>

<span data-ttu-id="9c119-103">在您的案例**搜索**选项卡，可以通过单击**新建搜索**并执行向导来创建新的搜索。</span><span class="sxs-lookup"><span data-stu-id="9c119-103">On the **Searches** tab in your case, you can create a new search by clicking **New search** and following the wizard.</span></span>

## <a name="name-your-search-and-give-description"></a><span data-ttu-id="9c119-104">命名您的搜索，并介绍</span><span class="sxs-lookup"><span data-stu-id="9c119-104">Name your search and give description</span></span>

<span data-ttu-id="9c119-p101">每个搜索与用例应具有唯一的名称。（可选），您可以为搜索提供说明。</span><span class="sxs-lookup"><span data-stu-id="9c119-p101">Each search with a case should have a unique name. You can optionally provide a description for your search.</span></span> 

## <a name="define-your-conditions"></a><span data-ttu-id="9c119-107">定义您的条件</span><span class="sxs-lookup"><span data-stu-id="9c119-107">Define your conditions</span></span>

<span data-ttu-id="9c119-p102">您可以定义为搜索使用预建的条件卡或使用关键字查询语言 (KQL) 的条件。有关详细信息，请参阅[生成搜索查询](building-search-queries.md)。</span><span class="sxs-lookup"><span data-stu-id="9c119-p102">You can define the conditions for your search using the pre-built condition cards or using Keyword Query Language (KQL). For more information, see [Build search queries](building-search-queries.md).</span></span>

## <a name="choose-the-custodians-to-search-from"></a><span data-ttu-id="9c119-110">选择要从搜索管理员</span><span class="sxs-lookup"><span data-stu-id="9c119-110">Choose the custodians to search from</span></span>

<span data-ttu-id="9c119-p103">一旦定义您的条件，您需要选择您要搜索的位置。执行此操作的一种方法是通过指定要搜索已添加到用例的管理员。通过选择管理员，您将所有数据源映射到 custodian 针对运行搜索。有关如何将管理员添加到您的案例和管理其数据源的详细信息，请参阅[使用管理员](managing-custodians.md)。</span><span class="sxs-lookup"><span data-stu-id="9c119-p103">Once you have defined your conditions, you need to choose which locations you want to search. One way to do it is by specifying which custodians you have already added to the case you want to search. By selecting a custodian, you will run the search against all data sources mapped to the custodian. See [Work with custodians](managing-custodians.md) for more information on how to add custodians to your case and manage their data sources.</span></span>

## <a name="choose-non-custodial-locations"></a><span data-ttu-id="9c119-115">选择非监控位置</span><span class="sxs-lookup"><span data-stu-id="9c119-115">Choose non-custodial locations</span></span>

<span data-ttu-id="9c119-p104">在某些情况下，您可能希望搜索未映射到管理员的数据源。在这种情况下，您可以指定您希望搜索或选择搜索特定的 Office 365 服务 （如搜索所有 Exchange 邮箱或所有 SharePoint 和 OneDrive for Business 站点） 的所有内容位置的位置。</span><span class="sxs-lookup"><span data-stu-id="9c119-p104">In some cases, you may wish to search data sources that are not mapped to a custodian. In this case, you can specify the locations you would like to search, or choose to search all content locations for a specific Office 365 service (such as searching all Exchange mailboxes or all SharePoint and OneDrive for Business sites).</span></span>