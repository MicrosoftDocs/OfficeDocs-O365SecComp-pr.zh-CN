---
title: Office 365 云应用安全中的异常检测策略
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/28/2019
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 88935b4e-dcb1-47f1-8aca-1bf8fb069db6
description: 'Office 365 云应用程序安全性的异常检测策略使用内置的算法来帮助发现潜在的问题。您应具有至少一个异常检测策略，您可以通过使用筛选器调整 （当您创建它）。 '
ms.openlocfilehash: 7a1cb795531df168f0a5c425e7555ae6b1412d2b
ms.sourcegitcommit: ee28ee2b2bdfd049333c2f495d7f7780d13af4a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2019
ms.locfileid: "29604413"
---
# <a name="anomaly-detection-policies-in-office-365-cloud-app-security"></a>Office 365 云应用安全中的异常检测策略

Office 365 高级安全管理现在是 Office 365 云应用程序安全性。
  
|评估 * *\>**|规划 * *\>**|部署 * *\>**|使用率 ***|
|:-----|:-----|:-----|:-----|
|[启动评估](office-365-cas-overview.md) <br/> |[开始规划](get-ready-for-office-365-cas.md) <br/> |在这里 ！  <br/> [后续步骤](integrate-your-siem-server-with-office-365-cas.md) <br/> |[开始利用](utilization-activities-for-ocas.md) <br/> |
   
Office 365 云应用程序安全性开头[Microsoft 云应用程序安全性释放 116](new-in-office-365-cas-2018.md#office-365-cloud-app-security-release-116-3)，包括多个预定义的异常检测策略 （"开"），包括用户、 实体行为分析 (UEBA) 以及学习 (ML) 的计算机。
  
![若要查看您的异常检测策略，请选择控件\>策略。](media/9663baa5-98bf-45e0-9458-6e572b43ec72.png)
  
这些异常检测策略通过提供即时检测，在您的用户和计算机连接到您的网络设备设定大量行为异常提供即时结果。此外，新策略公开来自云应用程序安全性检测引擎，以帮助您调查处理速度和包含持续威胁的其他数据。
  
为 Office 365 全局管理员或安全管理员，您可以查看，并有必要，修改可用于 Office 365 云应用程序安全性的默认策略。
  
 > [!IMPORTANT]
> 没有七天期间异常行为通知不会触发初始学习期。异常检测算法经过优化，可减少误报警报的数。 
  
## <a name="before-you-begin"></a>准备工作

请确保：
  
- 您的组织具有[Office 365 云应用程序安全性](office-365-cas-overview.md)，并且该服务[开启](turn-on-office-365-cas.md)。
    
- [审核日志记录](turn-audit-log-search-on-or-off.md)处于打开状态的 Office 365 环境。 
    
- 您是全局管理员或 Office 365 安全管理员。
    
## <a name="view-your-anomaly-detection-policies"></a>查看您异常检测策略

1. 以全局管理员或 security 管理员程序中，转到云应用程序安全性门户 ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) 和登录。<br>您将转到 Office 365 云应用程序安全策略页。
    
2. 在**类型**列表中，选择**异常检测策略**。<br>贵组织的默认 （或现有） 显示异常检测策略。<br>![Office 365 云应用安全中的异常检测策略](media/2e0ee770-787a-4d4a-bea8-389dc765d4c6.png)
  
3. 选择要查看或编辑其设置策略。
    
4. 选择**更新**以保存所做的更改。 
    
## <a name="learn-more-about-anomaly-detection-policies"></a>了解有关异常检测策略

将自动启用异常检测策略;但是，Office 365 云应用程序安全性有七天的不是所有异常期间检测警报初始学习期。之后，每个会话进行比较活动，当用户处于活动状态、 IP 地址、 设备、 等通过过去的月和风险评分的这些活动检测。这些检测属于试探性异常检测引擎的配置文件环境并触发警报采用了获知您的组织的活动的基线。这些检测还利用计算机学习算法旨在配置文件的用户和登录模式，以减少误报。
  
通过扫描用户活动检测到异常。通过查看超过 30 不同的风险指标，分为多个风险因素，如 risky IP 地址、 登录失败，管理活动、 非活动帐户、 位置、 意思差旅、 设备和用户代理和活动频率来计算风险。
  
基于策略的结果，触发安全警告。Office 365 云应用程序安全性查找 Office 365 中的每个用户会话，并从您的组织的基线或从用户的常规活动不同发生变化时通知您。
  
下表介绍的默认异常检测策略、 用途，以及它们的工作方式。
  
|**异常检测策略名称**|**如何工作**|
|:-----|:-----|
|意思出差  <br/> |标识两个用户活动 （为一个或多个会话） 源自遥远位置比时间较短的时间段内它可能需要花费用户从第一个位置移动到第二个，指示不同用户使用相同的凭据。此检测利用学习忽略明显"误报"分配给不可能的差旅条件，如 Vpn 和定期由组织中的其他用户的位置的算法的计算机。检测已初始学习期期间其学习新的用户活动模式的七天。  <br/> |
|来自非频繁的国家/地区的活动  <br/> |认为过活动位置确定新和非频繁位置。异常检测引擎存储有关组织中的用户使用的以前位置信息。活动发生从不最近或从不访问由用户或由组织中的任何用户的位置时，将触发一条通知。  <br/> |
|从匿名 IP 地址的活动  <br/> |标识用户处于活动从已被标识为匿名代理 IP 地址的 IP 地址。要隐藏其设备的 IP 地址，并可用于恶意的人员使用这些代理。此检测利用学习减少了"误报"，如设施标记广泛使用组织中的用户的 IP 地址的算法的计算机。  <br/> |
|从可疑 IP 地址的活动  <br/> |标识用户已从一个 IP 地址，由 Microsoft Threat 智能标识为 risky 活动。这些 IP 地址所涉及恶意活动，例如机器人网 C&amp;C，并可能表明受到攻击的帐户。此检测利用学习减少了"误报"，如设施标记广泛使用组织中的用户的 IP 地址的算法的计算机。  <br/> |
|特殊的活动 （由用户）  <br/> | 标识用户执行特殊的活动，例如：  <br/>  -多个文件下载  <br/>  -文件共享活动  <br/>  -文件删除活动  <br/>  -模拟活动  <br/>  -管理活动  <br/>  这些策略查找活动相对于基线教训，单个会话中无法指示违反尝试。这些检测利用学习用户配置文件登录模式的算法的计算机，并减少误报。这些检测属于试探性异常检测引擎的配置文件环境并触发警报采用了获知您的组织的活动的基线。  <br/> |
|多个失败的登录尝试次数  <br/> |标识用户失败单个会话中的多个登录尝试的相对于基线教训，这可能表示违反尝试。  <br/> |
   
## <a name="triage-anomaly-detection-alerts"></a>会审异常检测警报

通知逐渐，您可以快速会审这些通知并确定要将哪些首先处理。具有上下文的通知，可以看到更大的图片，并确定是否有恶意确实情况发生。使用以下过程开始浏览通知：
  
1. 以全局管理员或 security 管理员程序中，转到云应用程序安全性门户 ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) 和登录。 
    
2. 选择**通知**以查看您的通知。 
    
3. 获取通知上下文，请按照以下步骤：
    
4. 选择**调查** \> **活动日志**。
    
5. 选择一个项目，如用户或 IP 地址。这将打开相关见解纸盒。<br>![在活动日志中，您可以调查的 IP 地址。](media/32a727c5-e406-4fe2-9443-c1a7fb6628fc.png)
  
6. 在相关见解银中，单击可用的命令，如**显示类似**部分中的图标。<br> ![单击时钟图标以查看所选活动的 48 小时内执行的活动](media/c6c96aa0-98e5-4205-8873-45f8d6fd0843.png)
  
7. 深入了解有关所选项目通过继续浏览该项目的详细信息。
    
在多个失败登录通知良言可能可疑，并可指示潜在的强力攻击。但是，此类通知也可能是应用程序配置不正确，导致通知为误报，则返回 true 误报。如果您看到其他可疑活动多失败登录警报，则帐户受到威胁的更高的概率。例如，假设，多失败登录通知后跟活动从或 IP 地址和意思差旅活动，这两个强指标的威胁。您甚至可能会看到相同的用户执行大量下载活动，它通常是攻击者执行 exfiltration 的数据的指示符。它的类，您可以了解 Office 365 云应用程序安全性，若要查看和会审通知，并执行操作中操作在需要时。
  
## <a name="next-steps"></a>后续步骤

- [将 SIEM 服务器集成](integrate-your-siem-server-with-office-365-cas.md)
    
- [查看并通知对其执行操作](review-office-365-cas-alerts.md)
    
- [若要简化管理您 IP 地址进行分组](group-your-ip-addresses-in-ocas.md)
    

