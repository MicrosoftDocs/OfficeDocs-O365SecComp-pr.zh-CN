---
title: 对 IP 地址进行分组以简化 Office 365 云应用安全中的管理
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/28/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: b5e1471c-1ad6-4bc5-9e75-ce791aee283c
description: 若要轻松识别您将在 Office 365 云应用安全性 (如物理 Office IP 地址) 中使用的 ip 地址集, 可以设置 ip 地址范围组。
ms.openlocfilehash: b8f5c1dd46b2e3990d53a65881d12ca8f3961b16
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30220442"
---
# <a name="group-your-ip-addresses-to-simplify-management-in-office-365-cloud-app-security"></a>对 IP 地址进行分组以简化 Office 365 云应用安全中的管理
  
|评估 * *\>**|规划 * *\>**|部署 * *\>**|利用率 * * * *|
|:-----|:-----|:-----|:-----|
|[开始评估](office-365-cas-overview.md) <br/> |[开始规划](get-ready-for-office-365-cas.md) <br/> |你在这里!  <br/> [后续步骤](#next-steps) <br/> |[开始利用](utilization-activities-for-ocas.md) <br/> |
   
若要轻松识别您将在 Office 365 云应用安全性 (如物理 Office IP 地址) 中使用的 ip 地址集, 可以设置 ip 地址范围组。通过定义这些范围, 可以对其进行标记和分类, 然后可以使用标记和类别自定义活动日志和通知的显示和调查方式。
  
每组 IP 范围都可以使用您选择的标记名称进行标记, 然后可以根据 IP 类别的默认列表 (如公司、管理、危险和 VPN) 对这些标记进行分类。IPv4 和 IPv6 地址都受支持。
  
> [!NOTE]
> 您必须是全局管理员或安全管理员才能执行本文中的过程。若要了解详细信息, 请参阅[Office 365 安全&amp;合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。 
  
## <a name="to-set-up-an-ip-address-range-in-office-365-cloud-app-security"></a>在 Office 365 Cloud App Security 中设置 IP 地址范围

1. 作为全局管理员或安全管理员, 请转到云应用安全门户 ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) 并登录。
    
2. 在页面的右上方, 单击 "**设置** \> **IP 地址范围**"。<br>![在 O365 云应用安全性中, 选择 "设置" 以访问系统和数据设置](media/f6c48ee3-39b4-4b5a-8252-b6493b7bcd3d.png)<br>
  
3. 单击 "新建" 按钮, 它类似于加号 ( **+**)。
    
4. 在 "**新 IP 地址范围**" 窗口中, 指定以下值: 
    
|**字段或列表**|**需执行的操作**|
|:-----|:-----|
|**名称** <br/> |使用此字段可管理您的 IP 地址范围和设置。(您不会在 "活动日志" 中看到此值。)  <br/> |
|**IP 地址范围** <br/> |使用网络前缀表示法指定一个范围 (也称为 CIDR 表示法)。例如, 192.168.1.0/27 包含值192.168.1.0 到 192.168.1.31 (包括这两个值) 的范围。  <br/> |
|**位置**和**注册的 ISP** <br/> |为 IP 地址范围指定位置和 Internet 服务提供商 (ISP)。这将覆盖为地址定义的公共字段, 这对于事例 (如 IP 地址) 很有用, 例如在爱尔兰中被视为公开, 但实际上是在美国  <br/> |
|**Tags** <br/> |使用标记命名您的 IP 地址组。(与 "名称" 字段不同, 您将在 "活动日志" 中看到标记。)键入要用于标记的单词或短语。您可以根据需要为每个 IP 地址范围添加任意数量的标记。如果您已经设置了一个标记, 并且想要向其添加此 IP 地址范围, 请从开始键入时显示的当前标记列表中进行选择。  <br/> |
|**类别** <br/> | 为您的标记分配类别, 以便更轻松地识别来自特定 IP 地址的活动。从以下选项中进行选择:<br/> **管理**管理员的所有 IP 地址。  <br/> **云提供程序**云中代理的 IP 地址。  <br/> **企业**内部网络中的所有 IP 地址、分支机构和 wlan 漫游地址。  <br/> **风险**您认为有风险的任何 IP 地址, 如过去所见到的可疑 ip 地址、竞争对手网络中的 ip 地址等。默认情况下, 有风险的类别包括两个 IP 标记:**匿名代理**和**Tor** <br/> **VPN**您的远程工作人员使用的任何 IP 地址。  <br/> |
   
7. 选择" **保存**"。
    
设置 IP 地址范围后, 请记住, 这些更改仅影响将来的事件。
  
## <a name="next-steps"></a>后续步骤

- [活动策略和警报](activity-policies-and-alerts.md)
    
- [异常情况检测策略](anomaly-detection-policies-in-ocas.md)
    
- [集成您的 SIEM 服务器](integrate-your-siem-server-with-office-365-cas.md)
    
- [查看 Office 365 云应用安全中的警报并执行相应操作](review-office-365-cas-alerts.md)
    

