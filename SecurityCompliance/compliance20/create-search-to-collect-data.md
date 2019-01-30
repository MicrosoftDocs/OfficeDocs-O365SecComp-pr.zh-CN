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
ms.openlocfilehash: 3ebb9a40d3fb055fbb88b32175a4a22df3da44af
ms.sourcegitcommit: ee28ee2b2bdfd049333c2f495d7f7780d13af4a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2019
ms.locfileid: "29607491"
---
# <a name="create-a-search-to-collect-data"></a>创建搜索项来收集数据

在您的案例**搜索**选项卡，可以通过单击**新建搜索**并执行向导来创建新的搜索。

## <a name="name-your-search-and-give-description"></a>命名您的搜索，并介绍

每个搜索与用例应具有唯一的名称。（可选），您可以为搜索提供说明。 

## <a name="define-your-conditions"></a>定义您的条件

您可以定义为搜索使用预建的条件卡或使用关键字查询语言 (KQL) 的条件。有关详细信息，请参阅[生成搜索查询](building-search-queries.md)。

## <a name="choose-the-custodians-to-search-from"></a>选择要从搜索管理员

一旦定义您的条件，您需要选择您要搜索的位置。执行此操作的一种方法是通过指定要搜索已添加到用例的管理员。通过选择管理员，您将所有数据源映射到 custodian 针对运行搜索。有关如何将管理员添加到您的案例和管理其数据源的详细信息，请参见[管理员使用](managing-custodians.md)。

## <a name="choose-non-custodial-locations"></a>选择非监控位置

在某些情况下，您可能希望搜索未映射到管理员的数据源。在这种情况下，您可以指定您希望搜索或选择搜索特定的 Office 365 服务 （如搜索所有 Exchange 邮箱或所有 SharePoint 和 OneDrive for Business 站点） 的所有内容位置的位置。