---
title: EOP 中的功能权限
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 1/30/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 34674847-a6b7-4a7e-9eaa-b64f22bc150d
description: 执行管理 Microsoft Exchange Online Protection (EOP) 的任务所需的权限根据正在管理的功能的不同而不同。
ms.openlocfilehash: 08753d537982e49e735a1f81796f4709882c2be9
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32256250"
---
# <a name="feature-permissions-in-eop"></a>EOP 中的功能权限

执行管理 Microsoft Exchange Online Protection (EOP) 的任务所需的权限根据正在管理的功能的不同而不同。 
  
您必须是 Office 365 全局管理员或 Exchange 公司管理员（组织管理角色组），才能设置 EOP。
  
## <a name="exchange-online-protection-permissions"></a>Exchange Online Protection 权限

要找到管理 EOP 功能所需的权限，请参考下表：如果某个功能列出多个角色组，则您只需要被分配到其中一个角色组就可以使用此功能。
  
|**功能**|**所需的权限**|
|:-----|:-----|
|反恶意软件  <br/> |[组织管理](http://technet.microsoft.com/library/0bfd21c1-86ac-4369-86b7-aeba386741c8.aspx) <br/> [清洁管理](http://technet.microsoft.com/library/fc0a9ec2-9c3d-42f6-8442-8603fb29d464.aspx) <br/> |
|反垃圾邮件  <br/> |[组织管理](http://technet.microsoft.com/library/0bfd21c1-86ac-4369-86b7-aeba386741c8.aspx) <br/> [清洁管理](http://technet.microsoft.com/library/fc0a9ec2-9c3d-42f6-8442-8603fb29d464.aspx) <br/> |
|邮件流规则  <br/> |[组织管理](http://technet.microsoft.com/library/0bfd21c1-86ac-4369-86b7-aeba386741c8.aspx) <br/> [Records Management](http://technet.microsoft.com/library/0e0c95ce-6109-4591-b86d-c6cfd44d21f5.aspx) <br/> |
|域  <br/> |[组织管理](http://technet.microsoft.com/library/0bfd21c1-86ac-4369-86b7-aeba386741c8.aspx) <br/> [View-Only Organization Management](http://technet.microsoft.com/library/c514c6d0-0157-4c52-9ec6-441d9a30f3df.aspx) <br/> |
|高级威胁防护 (ATP)  <br/> |[组织管理](http://technet.microsoft.com/library/0bfd21c1-86ac-4369-86b7-aeba386741c8.aspx) <br/> [清洁管理](http://technet.microsoft.com/library/fc0a9ec2-9c3d-42f6-8442-8603fb29d464.aspx) <br/> |
|Office 365 连接器  <br/> |[组织管理](http://technet.microsoft.com/library/0bfd21c1-86ac-4369-86b7-aeba386741c8.aspx) <br/> |
|邮件跟踪  <br/> |[组织管理](http://technet.microsoft.com/library/0bfd21c1-86ac-4369-86b7-aeba386741c8.aspx) <br/> [View-Only Organization Management](http://technet.microsoft.com/library/c514c6d0-0157-4c52-9ec6-441d9a30f3df.aspx) <br/> |
|组织配置  <br/> |[Organization Management](http://technet.microsoft.com/library/0bfd21c1-86ac-4369-86b7-aeba386741c8.aspx) <br/> |
|隔离  <br/> |[组织管理](http://technet.microsoft.com/library/0bfd21c1-86ac-4369-86b7-aeba386741c8.aspx) <br/> [View-Only Organization Management](http://technet.microsoft.com/library/c514c6d0-0157-4c52-9ec6-441d9a30f3df.aspx) <br/> [Hygiene Management](http://technet.microsoft.com/library/fc0a9ec2-9c3d-42f6-8442-8603fb29d464.aspx) <br/> |
|用户、联系人和角色组  <br/> |[组织管理](http://technet.microsoft.com/library/0bfd21c1-86ac-4369-86b7-aeba386741c8.aspx) <br/> [View-Only Organization Management](http://technet.microsoft.com/library/c514c6d0-0157-4c52-9ec6-441d9a30f3df.aspx) <br/> [Hygiene Management](http://technet.microsoft.com/library/fc0a9ec2-9c3d-42f6-8442-8603fb29d464.aspx) <br/> |
|通讯组和安全组  <br/> |[Organization Management](http://technet.microsoft.com/library/0bfd21c1-86ac-4369-86b7-aeba386741c8.aspx) <br/> [View-Only Organization Management](http://technet.microsoft.com/library/c514c6d0-0157-4c52-9ec6-441d9a30f3df.aspx) <br/> [Hygiene Management](http://technet.microsoft.com/library/fc0a9ec2-9c3d-42f6-8442-8603fb29d464.aspx) <br/> |
|查看报告  <br/> |[Organization Management](http://technet.microsoft.com/library/0bfd21c1-86ac-4369-86b7-aeba386741c8.aspx) - 用户有权访问邮件保护报告。  <br/> [View-Only Recipients](http://technet.microsoft.com/library/37e66b92-81d3-412f-b7a9-e1bb8cbeb468.aspx) - 用户有权访问邮件保护报告。  <br/> [Compliance Management](http://technet.microsoft.com/library/b91b23a4-e9c7-4bd0-9ee3-ec5cb498da15.aspx) - 用户有权访问邮件保护报告和数据丢失预防 (DLP) 报告（如果他们的订阅具有 DLP 功能）。  <br/> |
   

