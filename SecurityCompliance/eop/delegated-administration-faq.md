---
title: 委派管理常见问题解答
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/9/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: d6a87ce8-2c22-433a-b430-5eab14f6afdc
description: 本主题为希望执行委派 Office 365 管理任务（包括能够为其他租户（公司）管理 Exchange Online Protection (EOP)）的 Microsoft 合作伙伴和经销商提供常见问题解答。
ms.openlocfilehash: b6096e835f90a0d5f22a39a5df76e52f1a25a79d
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2018
ms.locfileid: "22027489"
---
# <a name="delegated-administration-faq"></a>委派管理常见问题解答

本主题为希望执行委派 Office 365 管理任务（包括能够为其他租户（公司）管理 Exchange Online Protection (EOP)）的 Microsoft 合作伙伴和经销商提供常见问题解答。
  
 **问：我是经销商，需要管理客户的租户。具体工作原理是什么？**
  
答：如果您是 Microsoft 合作伙伴或经销商，且已注册成为 Microsoft 顾问，则可以请求在 Office 365 管理中心中管理其租户的权限。这称为委派管理，它允许您如同其组织中的管理员一样配置其 Office 365 租户（包括 EOP 设置）。执行委派管理的步骤如下所示：
  
1. 注册成为 [Microsoft Office 365 顾问](https://aka.ms/cloudbenefits)。
    
2. 注册以执行 Office 365 委派管理。在您开始管理客户帐户之前，客户必须将您授权为委派管理员。要获取此批准，您需首先向其[发送委派管理提议](https://go.microsoft.com/fwlink/?LinkId=396829)。（您也可以稍后向客户提供委派管理。） 
    
3. 使用[添加或删除委派管理员](https://go.microsoft.com/fwlink/?LinkId=396831)中记录的步骤创建委派管理员帐户。
    
访问[合作伙伴：建立您的业务和管理您的 Office 365 合作伙伴帐户](https://go.microsoft.com/fwlink/?LinkId=301485)，了解有关如何设置 Office 365 委派管理的详细信息。 
  
 **问：我是客户，不是经销商，我应该如何为我的子租户设置委派管理员？**
  
答：委派管理目前仅适用于经销商和合作伙伴。但是，我们提供了一个示例 Windows PowerShell 脚本，可帮助您将策略应用到您的子租户（公司）。有关详细信息，请参阅[将 EOP 设置应用到多个租户的示例脚本](sample-script-for-applying-eop-settings-to-multiple-tenants.md)。
  
 **问：能否防止子租户管理员修改我的策略？**
  
答：Office 365 目前不具备此功能。
  
 **问：能否将所有子租户的报告合并在一起？**
  
答：您管理的公司之间的合并报告目前不适用于 Office 365 管理中心报告。但是，这可以通过远程 Windows PowerShell 或[报告 Web 服务](https://go.microsoft.com/fwlink/?LinkId=279926)实现。 
  

