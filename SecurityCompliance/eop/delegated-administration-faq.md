---
title: 委派管理常见问题解答
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 12/9/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: d6a87ce8-2c22-433a-b430-5eab14f6afdc
description: 本主题为希望执行委派 Office 365 管理任务（包括能够为其他租户（公司）管理 Exchange Online Protection (EOP)）的 Microsoft 合作伙伴和经销商提供常见问题解答。
ms.openlocfilehash: 8d28c8b6e0e85e9cfbe71e5b4b787159cc88ce08
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2019
ms.locfileid: "35599798"
---
# <a name="delegated-administration-faq"></a>委派管理常见问题解答

本主题为希望执行委派 Office 365 管理任务（包括能够为其他租户（公司）管理 Exchange Online Protection (EOP)）的 Microsoft 合作伙伴和经销商提供常见问题解答。
  
 **问：我是经销商，需要管理客户的租户。具体工作原理是什么？**
  
A. 如果你是 Microsoft 合作伙伴或经销商, 并且已注册为 Microsoft advisor, 则可以请求在管理中心内管理其租户的权限。 这称为 "委派管理", 它允许您管理其 Office 365 租户 (包括 EOP 设置), 就像您是组织内的管理员一样。 执行委派管理的步骤如下所示:
  
1. 注册成为 [Microsoft Office 365 顾问](https://aka.ms/cloudbenefits)。
    
2. 注册以执行 Office 365 委派管理。在您开始管理客户帐户之前，客户必须将您授权为委派管理员。要获取此批准，您需首先向其[发送委派管理提议](https://go.microsoft.com/fwlink/?LinkId=396829)。（您也可以稍后向客户提供委派管理。） 
    
3. 使用[添加或删除委派管理员](https://go.microsoft.com/fwlink/?LinkId=396831)中记录的步骤创建委派管理员帐户。
    
访问[合作伙伴：建立您的业务和管理您的 Office 365 合作伙伴帐户](https://go.microsoft.com/fwlink/?LinkId=301485)，了解有关如何设置 Office 365 委派管理的详细信息。 
  
 **问：我是客户，不是经销商，我应该如何为我的子租户设置委派管理员？**
  
答：委派管理目前仅适用于经销商和合作伙伴。但是，我们提供了一个示例 Windows PowerShell 脚本，可帮助您将策略应用到您的子租户（公司）。有关详细信息，请参阅[将 EOP 设置应用到多个租户的示例脚本](sample-script-for-applying-eop-settings-to-multiple-tenants.md)。
  
 **问：能否防止子租户管理员修改我的策略？**
  
答：Office 365 目前不具备此功能。
  
 **问：能否将所有子租户的报告合并在一起？**
  
A. 您管理的公司内的合并报告目前不可用于 Micrsoft 365 管理中心报告。 但是, 可以通过远程 Windows PowerShell 或[报告 web 服务](https://go.microsoft.com/fwlink/?LinkId=279926)执行此操作。 
  

