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
# <a name="dealing-with-data-corruption-in-office-365"></a><span data-ttu-id="5062f-103">处理 Office 365 中的数据损坏</span><span class="sxs-lookup"><span data-stu-id="5062f-103">Dealing with Data Corruption in Office 365</span></span>

<span data-ttu-id="5062f-p101">运行大型云服务的具挑战性方面之一是如何处理数据损坏给定大量数据和独立的系统。数据损坏可能是由导致的：</span><span class="sxs-lookup"><span data-stu-id="5062f-p101">One of the challenging aspects of running a large-scale cloud service is how to handle data corruption, given the large volume of data and independent systems. Data corruption can be caused by:</span></span>
- <span data-ttu-id="5062f-106">应用程序或基础结构的 bug，破坏部分或全部应用程序状态</span><span class="sxs-lookup"><span data-stu-id="5062f-106">Application or infrastructure bugs, corrupting some or all of the application state</span></span> 
- <span data-ttu-id="5062f-107">硬件问题导致数据丢失或无法读取数据的结果</span><span class="sxs-lookup"><span data-stu-id="5062f-107">Hardware issues that result in lost data or an inability to read data</span></span> 
- <span data-ttu-id="5062f-108">人工操作错误</span><span class="sxs-lookup"><span data-stu-id="5062f-108">Human operational errors</span></span> 
- <span data-ttu-id="5062f-109">恶意黑客和不满的员工</span><span class="sxs-lookup"><span data-stu-id="5062f-109">Malicious hackers and disgruntled employees</span></span> 
- <span data-ttu-id="5062f-110">导致丢失一些数据的外部服务中的事件</span><span class="sxs-lookup"><span data-stu-id="5062f-110">Incidents in external services that result in some loss of data</span></span> 

<span data-ttu-id="5062f-p102">数据完整性的更高版本恢复能力意味着更少数据损坏事件，因为 Microsoft 具有内置 Office 365 保护机制以防止从发生，以及系统和流程来帮助我们恢复数据，则毁坏。检查和流程存在工程的发布过程，以提高可恢复性防止数据损坏的各个阶段中包括：</span><span class="sxs-lookup"><span data-stu-id="5062f-p102">Because greater resiliency in data integrity means fewer data corruption incidents, Microsoft has built into Office 365 protection mechanisms to prevent corruption from happening, as well as systems and processes that enable us to recover data if it does. Checks and processes exist within the various stages of the engineering release process to increase resiliency against data corruption, including:</span></span>
- <span data-ttu-id="5062f-113">系统设计</span><span class="sxs-lookup"><span data-stu-id="5062f-113">System Design</span></span>
- <span data-ttu-id="5062f-114">代码组织和结构</span><span class="sxs-lookup"><span data-stu-id="5062f-114">Code organization and structure</span></span> 
- <span data-ttu-id="5062f-115">代码评审</span><span class="sxs-lookup"><span data-stu-id="5062f-115">Code review</span></span> 
- <span data-ttu-id="5062f-116">单元测试、 集成测试和系统测试</span><span class="sxs-lookup"><span data-stu-id="5062f-116">Unit tests, integration tests, and system tests</span></span>
- <span data-ttu-id="5062f-117">行程线测试/入口</span><span class="sxs-lookup"><span data-stu-id="5062f-117">Trip wires tests/gates</span></span> 

<span data-ttu-id="5062f-p103">Office 365 生产环境中数据中心之间的对等方复制确保总是有多个 live 副本的任何数据。使用标准图像和脚本以恢复丢失的服务器，并复制的数据用于还原客户数据。由于的内置数据恢复能力检查和流程，Microsoft 维护备份的 Office 365 信息系统文档 （包括与安全相关的文档），仅使用 SharePoint Online 和我们内部的代码中内置的复制库工具，源安装盘。SharePoint Online 中存储系统文档和源安装盘包含系统和应用程序的图像。SharePoint Online 和源安装盘使用版本控制和几乎可以实时复制到中。</span><span class="sxs-lookup"><span data-stu-id="5062f-p103">Within Office 365 production environments, peer replication between datacenters ensures that there are always multiple live copies of any data. Standard images and scripts are used to recover lost servers, and replicated data is used to restore customer data. Because of the built-in data resiliency checks and processes, Microsoft maintains backups only of Office 365 information system documentation (including security-related documentation), using built-in replication in SharePoint Online and our internal code repository tool, Source Depot. System documentation is stored in SharePoint Online, and Source Depot contains system and application images. Both SharePoint Online and Source Depot use versioning and are replicated in near real-time.</span></span> 