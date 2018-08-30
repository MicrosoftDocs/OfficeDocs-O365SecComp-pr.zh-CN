---
title: Office 365 处理数据损坏
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: Office 365 和 Microsoft 的保护和恢复工作中的数据损坏的说明。
ms.openlocfilehash: 087be23ce5dad1daf62357cb08e27c0a15962792
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525496"
---
# <a name="dealing-with-data-corruption-in-office-365"></a>处理 Office 365 中的数据损坏

运行大型云服务的具挑战性方面之一是如何处理数据损坏给定大量数据和独立的系统。数据损坏可能是由导致的：
- 应用程序或基础结构的 bug，破坏部分或全部应用程序状态 
- 硬件问题导致数据丢失或无法读取数据的结果 
- 人工操作错误 
- 恶意黑客和不满的员工 
- 导致丢失一些数据的外部服务中的事件 

数据完整性的更高版本恢复能力意味着更少数据损坏事件，因为 Microsoft 具有内置 Office 365 保护机制以防止从发生，以及系统和流程来帮助我们恢复数据，则毁坏。检查和流程存在工程的发布过程，以提高可恢复性防止数据损坏的各个阶段中包括：
- 系统设计
- 代码组织和结构 
- 代码评审 
- 单元测试、 集成测试和系统测试
- 行程线测试/入口 

Office 365 生产环境中数据中心之间的对等方复制确保总是有多个 live 副本的任何数据。使用标准图像和脚本以恢复丢失的服务器，并复制的数据用于还原客户数据。由于的内置数据恢复能力检查和流程，Microsoft 维护备份的 Office 365 信息系统文档 （包括与安全相关的文档），仅使用 SharePoint Online 和我们内部的代码中内置的复制库工具，源安装盘。SharePoint Online 中存储系统文档和源安装盘包含系统和应用程序的图像。SharePoint Online 和源安装盘使用版本控制和几乎可以实时复制到中。 