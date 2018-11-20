---
title: Office 365 中的攻击模拟器
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 11/09/2018
ms.audience: ITPro
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: da5845db-c578-4a41-b2cb-5a09689a551b
description: 作为 Office 365 全局管理员，您可以使用攻击模拟器若要运行您的组织中的实际攻击方案。这可以帮助您确定并查找易受攻击用户前真实攻击点击您的业务。
ms.openlocfilehash: ccef127c4ce4d806ef9af04673b8c68d82ce9ec6
ms.sourcegitcommit: 7c55721b51b2f321537a0cdad6644abf91996710
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/10/2018
ms.locfileid: "26256437"
---
# <a name="attack-simulator-in-office-365"></a>Office 365 中的攻击模拟器

**摘要**如果您是 Office 365 全局管理员和贵组织拥有[Office 365 威胁智能](office-365-ti.md)，您可以使用攻击模拟器运行您的组织中的实际攻击方案。这可以帮助您确定并查找易受攻击用户前真实攻击影响您底线。阅读此文，了解详细信息。
  
## <a name="the-attacks"></a>攻击

目前，三种类型的攻击模拟有：
  
- [显示名称矛网络钓鱼攻击](attack-simulator.md#spearphish)
    
- [密码喷涂攻击](attack-simulator.md#passwordspray)
    
- [强制密码攻击](attack-simulator.md#bruteforce)
    
攻击者要成功启动，您使用多因素身份验证帐户用于运行模拟的攻击。此外，您必须是 Office 365 全局管理员。
  
> [!NOTE]
> 条件访问支持即将提供。 
  
若要访问攻击模拟器，安全中&amp;合规性中心中，选择**威胁管理** \> **攻击模拟器**。
  
## <a name="before-you-begin"></a>开始之前...

请确保您和您的组织满足攻击模拟器的以下要求：
      
- Exchange Online 中位于组织的电子邮件。（攻击模拟器不可用的内部部署电子邮件服务器。）
    
- 您是 Office 365 全局管理员
    
- 您的组织使用[的 Office 365 用户的多因素身份验证](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication&view=o365-worldwide)
 
- 贵组织拥有[Office 365 威胁智能](office-365-ti.md)与安全中可见的攻击模拟器&amp;合规性中心 (转到**威胁管理** \> **攻击模拟器**)<br/>![威胁管理-攻击模拟器](media/ThreatMgmt-AttackSimulator.png)

    
## <a name="display-name-spear-phishing-attack"></a>显示名称矛网络钓鱼攻击

网络钓鱼的攻击 classed 社会工程样式攻击作为一组广泛的通用术语。此类攻击重点矛网络钓鱼，旨在个人或组织的特定组更有针对性的攻击。通常情况下，自定义与使用将生成信任收件人，例如看起来像来自组织内主管电子邮件中的显示名称并执行一些侦测攻击。
  
此类攻击着重于让您通过更改显示名称和源地址源自消息显示的操作。矛网络钓鱼攻击成功后，犯罪访问用户的凭据。
  
### <a name="to-simulate-a-spear-phishing-attack"></a>若要模拟矛网络钓鱼攻击

![撰写电子邮件正文](media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)
  
可以创建定制直接在**电子邮件正文**字段本身中丰富的 HTML 编辑器，也可以使用 HTML 源代码。有两个重要字段以包含在 HTML 中： 
  
1. 安全中&amp;合规性中心中，选择**威胁管理** \> **攻击模拟器**。
    
2. 指定攻击的有意义的市场活动名称，或选择一个模板。 <br/>![网络钓鱼开始页](media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)
  
3. 指定目标收件人。这可以是您的组织内个人或组。每个目标的收件人必须具有 Exchange Online 邮箱为了攻击成功。 <br/>![收件人选择](media/faf8c2e0-6175-4cd7-8265-0c8e727f4d0f.jpg)
  
4. 配置网络钓鱼电子邮件详细信息。 <br/>![配置电子邮件的详细信息](media/f043608f-f8ce-4aae-be28-86e8ecc524a9.jpg)<br/>HTML 格式可以为复杂或基本随着您市场需求。电子邮件格式为 HTML，如可以插入图像和文本以增强 believability。您可以控制上收到的消息中接收电子邮件客户端的类似。
    
5. 指定文本的**从 （名称）** 域。这是接收的电子邮件客户端中的**显示名称**中显示的字段。 
    
6. 指定文本或**从**域。这是显示为接收电子邮件客户端的发件人的电子邮件地址的字段。<br/>您可以输入贵组织中的现有电子邮件命名空间 （执行此操作将导致实际解决接收客户端，从而推动非常高信任模型中的电子邮件地址），也可以输入外部电子邮件地址。您指定不必实际存在的电子邮件地址，但它确实需要为以下的一个有效的 SMTP 地址，例如 user@domainname.extension 格式。 
  
7. 使用下拉选择器，选择一个反映您将拥有您攻击中的内容类型的网络钓鱼登录服务器 URL。您可供选择，如文档传递，技术，工资等提供多种应用了主题的 Url。这是有效目标的用户时要求您单击的 URL。
    
8. 指定自定义登录页 URL。使用此将用户重定向到末尾的成功的攻击指定的 URL。如果您具有内部认知培训，例如，您可以指定的下面。
    
9. 指定**主题**字段的文本。这是显示为接收电子邮件客户端中的**使用者名称**的字段。 
    
10. 撰写**电子邮件正文**将接收目标。 <br/>`${username}`将目标名称插入到电子邮件正文。 <br/>`${loginserverurl}`插入我们希望目标用户单击的 URL 
    
11. 选择**下一步，** 然后**完成**以启动攻击。矛网络钓鱼电子邮件传递到目标收件人的邮箱。 
    
## <a name="password-spray-attack"></a>密码喷涂攻击

不良的 actor 成功获得有效用户从租户的列表后将通常用于针对组织的密码喷涂攻击。不良的 actor 了解常见人员使用的密码。这是广泛使用的攻击中，因为它是运行，且更难比暴力方法检测到便宜攻击。
  
此类攻击着重于让您指定的用户的大型目标基针对公用密码。
  
### <a name="to-simulate-a-password-spray-attack"></a>若要模拟密码喷涂攻击

1. 安全中&amp;合规性中心中，选择**威胁管理** \> **攻击模拟器**。
    
2. 指定攻击的有意义的市场活动名称。
    
3. 指定目标收件人。这可以是您的组织内个人或组。目标的收件人必须具有 Exchange Online 邮箱为了攻击成功。
    
4. 指定要使用的攻击的密码。例如，您可以尝试的一个常见、 相关密码是`Fall2017`。可能有另一个`Spring2018`，或`Password1`。
    
5. 选择**完成**以启动攻击。 
    
## <a name="brute-force-password-attack"></a>强制密码攻击

不良的 actor 成功获得从租户的关键用户列表后，通常使用针对组织的密码强力攻击。此类攻击着重于尝试一组对单个用户的帐户的密码。
  
### <a name="to-simulate-a-brute-force-password-attack"></a>模拟密码强力攻击

1. 安全中&amp;合规性中心中，选择**威胁管理** \> **攻击模拟器**。
    
2. 指定攻击的有意义的市场活动名称。
    
3. 指定目标收件人。目标的收件人必须具有 Exchange Online 邮箱为了攻击成功。
    
4. 指定一组用于攻击的密码。文本文件 (.txt) 可用于您的密码列表。文本文件不能超过 10 MB 文件大小。使用一个密码每行，并确保可在列表中的最后一个密码后包含硬回车。
    
5. 选择**完成**以启动攻击。 
    
## <a name="new-features-in-attack-simulator"></a>在攻击模拟器中的新增功能

新功能添加到攻击模拟器。这些工具包括：
- **报告功能的高级**。您将能够看到数据，例如最快 （或最慢） 时间最快 （或最慢） 时间打开攻击模拟电子邮件，单击中的消息和详细信息的链接。
- **电子邮件模板编辑器**。您可以创建可用于将来攻击模拟的自定义的、 可重用的电子邮件模板。

请访问[Microsoft 365 路线图](https://www.microsoft.com/microsoft-365/roadmap)以查看新增开发中什么推出，和哪些已启动。



