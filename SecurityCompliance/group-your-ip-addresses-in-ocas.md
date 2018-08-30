---
title: 对 IP 地址进行分组以简化 Office 365 云应用安全中的管理
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 2/22/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: b5e1471c-1ad6-4bc5-9e75-ce791aee283c
description: 可以轻松地识别套将在 Office 365 云应用程序安全性，使用您实际办公室的 IP 地址，如的 IP 地址可以设置组的 IP 地址范围。
ms.openlocfilehash: 76cb9625a46d1f5eceaab696de5dcbb72f4d2b47
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22524825"
---
# <a name="group-your-ip-addresses-to-simplify-management-in-office-365-cloud-app-security"></a>对 IP 地址进行分组以简化 Office 365 云应用安全中的管理
  
|评估 * *\>**|规划 * *\>**|部署 * *\>**|使用率 ***|
|:-----|:-----|:-----|:-----|
|[启动评估](office-365-cas-overview.md) <br/> |[开始规划](get-ready-for-office-365-cas.md) <br/> |在这里 ！  <br/> [后续步骤](#next-steps) <br/> |[开始利用](utilization-activities-for-ocas.md) <br/> |
   
可以轻松地识别套将在 Office 365 云应用程序安全性，使用您实际办公室的 IP 地址，如的 IP 地址可以设置组的 IP 地址范围。定义这些范围允许标记和分类，然后您可以使用标记和自定义您的活动日志和通知的方式的类别显示和调查。
  
IP 范围的每个组可以标记与的选择，然后将标记可进行分类基于 IP 类别 （例如企业、 管理、 Risky 和 VPN） 的默认列表的标记名称中。支持 IPv4 和 IPv6 地址。
  
> [!NOTE]
> 您必须是全局管理员或安全管理员才能执行本文中的过程。若要了解详细信息，请参阅[Permissions in Office 365 安全性&amp;合规性中心](permissions-in-the-security-and-compliance-center.md)。 
  
## <a name="to-set-up-an-ip-address-range-in-office-365-cloud-app-security"></a>设置 Office 365 云应用程序安全性的 IP 地址范围

1. 以全局管理员或 security 管理员程序中，转到[https://protection.office.com](https://protection.office.com)和使用工作或学校帐户登录。(您将转到安全&amp;合规性中心。) 
    
2. 安全中&amp;合规性中心中，选择**警报** \> **管理高级通知**。
    
3. 选择**转到 Office 365 云应用程序安全性**。
    
    ![安全中&amp;合规性中心中，选择管理高级通知转到 Office 365 云应用程序安全性](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)
  
4. 在页面右上角右上角，单击**设置** \> **IP 地址范围**。
    
    ![在 O365 云应用程序安全中，选择设置以访问您的系统和数据设置](media/f6c48ee3-39b4-4b5a-8252-b6493b7bcd3d.png)
  
5. 单击新建按钮，其类似于一个加号 ( **+**)。
    
6. 在**新的 IP 地址范围**窗口中，指定以下值： 
    
|**字段或列表**|**需执行的操作**|
|:-----|:-----|
|**名称** <br/> |使用此字段来管理您的 IP 地址范围和设置。（您不会看到此活动日志中的值）。  <br/> |
|**IP 地址范围** <br/> |指定范围，使用网络前缀符号 （也称为 CIDR 格式表示）。例如，192.168.1.0/27 包括 192.168.1.0 通过 192.168.1.31 （含） 的值的范围。  <br/> |
|**位置**和**注册 ISP** <br/> |指定的 IP 地址范围的位置和 Internet 服务提供程序 (ISP)。这将覆盖公共字段定义地址，这很有帮助的情况下，如 IP 地址是的被视为公开在爱尔兰但实际上就是在美国  <br/> |
|**Tags** <br/> |使用标记命名您的 IP 地址的组。（与不同的名称字段中，您将看到标记活动日志中。）键入的字词或短语的您想要使用的标记。您可以添加每个 IP 地址范围任意数量的标记。然后，如果您已设置了标记，并且想要向其中添加此 IP 地址范围，选择从列表中出现，在开始键入内容的当前标记。  <br/> |
|**Category** <br/> | 为您的标记，以使其更易于识别来自特定 IP 地址的活动分配类别。选择以下选项：<br/> **管理**所有的 IP 地址的您的管理员。  <br/> **云提供程序**您在云中的代理服务器的 IP 地址。  <br/> **企业**所有 IP 地址在内部网络、 分支机构和您 Wi-fi 漫游地址。  <br/> **Risky**考虑为 risky，如可疑的 IP 地址您任何 IP 地址已看到在过去，竞争对手网络中的 IP 地址等等。默认情况下，risky 类别包含两个 IP 标记：**匿名代理**，**或** <br/> **VPN**您的远程工作者使用任何 IP 地址。  <br/> |
   
7. 选择**保存**。
    
设置您的 IP 地址范围后，请注意，这些更改将影响仅未来事件。
  
## <a name="next-steps"></a>后续步骤

- [活动策略和通知](activity-policies-and-alerts.md)
    
- [异常检测策略](anomaly-detection-policies-in-ocas.md)
    
- [将 SIEM 服务器集成](integrate-your-siem-server-with-office-365-cas.md)
    
- [查看 Office 365 云应用安全中的警报并执行相应操作](review-office-365-cas-alerts.md)
    

