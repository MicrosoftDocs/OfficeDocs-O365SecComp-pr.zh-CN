---
title: Office 365 中的攻击模拟器
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 6/19/2018
ms.audience: ITPro
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: da5845db-c578-4a41-b2cb-5a09689a551b
description: 了解关于三种不同类型的网络攻击，您可以使用攻击模拟器运行。
ms.openlocfilehash: 364144c0b2f8109c67fb262ce879414088380ebe
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525139"
---
# <a name="attack-simulator-in-office-365"></a>Office 365 中的攻击模拟器

与攻击模拟器 （包含在[Office 365 威胁智能](office-365-ti.md)），如果您的组织的安全工作组成员可以实际攻击方案中运行您的组织。这可以帮助您确定并查找易受攻击用户前真实攻击影响您底线。
  
## <a name="the-attacks"></a>攻击

在预览版我们提供您可以运行的攻击模拟的三种：
  
- [显示名称矛网络钓鱼攻击](attack-simulator.md#spearphish)
    
- [密码喷涂攻击](attack-simulator.md#passwordspray)
    
- [强制密码攻击](attack-simulator.md#bruteforce)
    
攻击者要成功启动，正在运行攻击和登录的帐户必须使用多因素身份验证。
  
> [!NOTE]
> 条件访问支持即将提供。 
  
若要访问攻击模拟器，安全中&amp;合规性中心中，选择**威胁管理** \> **攻击模拟器**。
  
## <a name="before-you-begin"></a>开始之前...

请确保您和您的组织满足攻击模拟器的以下要求：
  
- 贵组织拥有[Office 365 威胁智能](office-365-ti.md)与安全中可见的攻击模拟器&amp;合规性中心 (转到**威胁管理** \> **攻击模拟器**)
    
- Exchange Online 中位于组织的电子邮件。（攻击模拟器不可用的内部部署电子邮件服务器。）
    
- 您是 Office 365 全局管理员
    
- 您的组织使用[的 Office 365 用户的多因素身份验证](https://support.office.com/article/8f0454b2-f51a-4d9c-bcde-2c48e41621c6)
    
## <a name="display-name-spear-phishing-attack"></a>显示名称矛网络钓鱼攻击

网络钓鱼的攻击 classed 社会工程样式攻击作为一组广泛的通用术语。此类攻击重点矛网络钓鱼，旨在个人或组织的特定组更有针对性的攻击。通常情况下，自定义与使用将生成信任收件人，例如看起来像来自组织内主管电子邮件中的显示名称并执行一些侦测攻击。
  
此类攻击着重于让您通过更改显示名称和源地址源自消息显示的操作。矛网络钓鱼攻击成功后，犯罪访问用户的凭据。
  
### <a name="to-simulate-a-spear-phishing-attack"></a>若要模拟矛网络钓鱼攻击

![撰写电子邮件正文](media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)
  
可以创建定制直接在**电子邮件正文**字段本身中丰富的 HTML 编辑器，也可以使用 HTML 源代码。有两个重要字段以包含在 HTML 中： 
  
1. 安全中&amp;合规性中心中，选择**威胁管理** \> **攻击模拟器**。
    
2. 指定攻击的有意义的市场活动名称，或选择一个模板。
    
    ![网络钓鱼开始页](media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)
  
3. 指定目标收件人。这可以是您的组织内个人或组。目标的收件人必须具有 Exchange Online 邮箱为了攻击成功。
    
    ![收件人选择](media/faf8c2e0-6175-4cd7-8265-0c8e727f4d0f.jpg)
  
4. 配置网络钓鱼电子邮件详细信息。
    
    ![配置电子邮件的详细信息](media/f043608f-f8ce-4aae-be28-86e8ecc524a9.jpg)
  
    HTML 格式可以为复杂或基本随着您市场需求。按原样 HTML，您可以插入图像和文本以增强 believability。您可以控制上收到的消息中接收电子邮件客户端的类似。
    
1. 文本输入**从 （名称）** 域。这是接收的电子邮件客户端中的**显示名称**中显示的字段。 
    
2. 输入文本或**从**域。这是显示为接收电子邮件客户端的发件人的电子邮件地址的字段。 
    
    > [!IMPORTANT]
    > 您可以输入贵组织中的现有电子邮件命名空间 （执行此操作将导致实际解决接收客户端，从而推动非常高信任模型中的电子邮件地址），也可以输入外部电子邮件地址。您指定不必实际存在的电子邮件地址，但它确实需要为以下的一个有效的 SMTP 地址，例如 user@domainname.extension 格式。 
  
3. 使用下拉选择器，选择一个反映您将拥有您攻击中的内容类型的网络钓鱼登录服务器 URL。您可供选择，如文档传递，技术，工资等提供多种应用了主题的 Url。这是有效目标的用户时要求您单击的 URL。
    
4. 输入自定义登录页 URL。使用此将用户重定向到末尾的成功的攻击指定的 URL。如果您具有内部认知培训，例如，您可以指定的下面。
    
5. 为**主题**字段中输入文本。这是显示为接收电子邮件客户端中的**使用者名称**的字段。 
    
5. 撰写**电子邮件正文**将接收目标。 
  
 **${用户名}** 将目标名称插入到电子邮件正文 
  
 **${loginserverurl}** 插入我们希望目标用户单击的 URL 
    
6. 选择**下一步，** 然后**完成**以启动攻击。矛网络钓鱼电子邮件传递到目标收件人的邮箱。 
    
## <a name="password-spray-attack"></a>密码喷涂攻击

不良 actor 成功具有枚举的有效用户从租户，利用不知情的常见所用的密码列表后，通常用于针对组织的密码喷涂攻击。它是利用广泛，它是一种便宜的攻击，若要运行，且更难检测比暴力方法。
  
此类攻击着重于让您指定的用户的大型目标基针对公用密码。
  
### <a name="to-simulate-a-password-spray-attack"></a>若要模拟密码喷涂攻击

1. 安全中&amp;合规性中心中，选择**威胁管理** \> **攻击模拟器**。
    
2. 指定攻击的有意义的市场活动名称。
    
3. 指定目标收件人。这可以是您的组织内个人或组。目标的收件人必须具有 Exchange Online 邮箱为了攻击成功。
    
4. 指定要使用的攻击的密码。例如，您可以尝试的一个常见、 相关密码是`Fall2017`。可能有另一个`Spring2018`，或`Password1`。
    
5. 选择**完成**以启动攻击。 
    
## <a name="brute-force-password-attack"></a>强制密码攻击

针对组织的密码强力攻击通常用于后不良 actor 已成功枚举从租户的关键用户的列表。此类攻击着重于让您指定一组针对单个用户的密码。
  
### <a name="to-simulate-a-brute-force-password-attack"></a>模拟密码强力攻击

1. 安全中&amp;合规性中心中，选择**威胁管理** \> **攻击模拟器**。
    
2. 指定攻击的有意义的市场活动名称。
    
3. 指定目标收件人。目标的收件人必须具有 Exchange Online 邮箱为了攻击成功。
    
4. 指定一组用于攻击的密码。例如，您可以尝试的一个常见、 相关密码是`Fall2017`。可能有另一个`Spring2018`，或`Password1`。
    
5. 选择**完成**以启动攻击。 
    
## <a name="related-topics"></a>相关主题

[Office 365 威胁智能](office-365-ti.md)
  

