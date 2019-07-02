---
title: Create a search
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 1aa4ce6e406e4b3a3b72b9d93f651416b1fc65f9
ms.sourcegitcommit: 803baca9f99a6691fb41a3308e799752e4d8f20c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/25/2019
ms.locfileid: "35222246"
---
# <a name="create-a-search"></a>Create a search

在您的案例的 "**搜索**" 选项卡上, 您可以通过单击 "**新建搜索**" 并按照向导创建新的搜索。

## <a name="name-your-search-and-give-it-a-description"></a>命名搜索并为其提供说明

每个具有事例的搜索应具有唯一的名称。 您可以选择为搜索提供说明。 

## <a name="define-your-search-query-and-conditions"></a>定义您的搜索查询和条件

您可以使用预建的条件卡或使用关键字查询语言 (KQL) 定义搜索的关键字查询和任何条件。 有关详细信息, 请参阅[构建搜索查询](building-search-queries.md)。

## <a name="choose-the-custodians-to-search-from"></a>选择要从中搜索的保管人

定义条件后, 需要选择要搜索的位置。 执行此操作的一种方法是指定您已添加到您要搜索的事例的保管人。 通过选择管理员, 你将对映射到保管人的所有数据源运行搜索。 有关如何将保管人添加到你的事例并管理其数据源的详细信息, 请参阅[使用保管人](managing-custodians.md)。

## <a name="choose-non-custodial-locations"></a>选择非 custodial 位置

在某些情况下, 您可能希望搜索未映射到保管人的数据源。 在这种情况下, 您可以指定要搜索的位置, 或选择搜索特定 Office 365 服务的所有内容位置 (例如, 搜索所有 Exchange 邮箱或所有 SharePoint 和 OneDrive for business 网站)。