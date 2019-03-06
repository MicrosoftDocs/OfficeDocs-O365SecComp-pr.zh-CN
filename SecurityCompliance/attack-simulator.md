---
title: Office 365 中的攻击模拟器
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 03/05/2019
ms.audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: da5845db-c578-4a41-b2cb-5a09689a551b
ms.collection:
- M365-security-compliance
description: 作为 Office 365 全局管理员, 你可以使用攻击模拟器在你的组织中运行实际的攻击方案。 这可帮助你在真正的攻击击中你的业务之前识别和查找易受攻击的用户。
ms.openlocfilehash: 25686ce194deca8d1ca07fca40f8142492951574
ms.sourcegitcommit: ed822a776d3419853453583e882f3c61ca26d4b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "30410827"
---
# <a name="attack-simulator-in-office-365"></a>Office 365 中的攻击模拟器

**摘要**如果您是 office 365 全局管理员, 并且您的组织拥有[office 365 的威胁智能](office-365-ti.md), 则可以使用攻击模拟器在组织中运行实际的攻击方案。 这可以帮助您识别和查找易受攻击的用户, 在真正的攻击影响你的底线之前。 阅读本文以了解详细信息。

> [!IMPORTANT]
> 从2019年2月起开始, 在接下来的几个月中, office 365 威胁情报将成为 office 365 高级威胁防护计划 2, 其中包含其他威胁防护功能。 若要了解详细信息, 请参阅[office 365 高级威胁防护计划和定价](https://products.office.com/exchange/advance-threat-protection)以及[Office 365 高级威胁防护服务说明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)。
  
## <a name="the-attacks"></a>攻击

目前提供三种攻击模拟:
  
- [显示名称 spear 网络钓鱼攻击](attack-simulator.md#spearphish)
    
- [密码喷涂攻击](attack-simulator.md#passwordspray)
    
- [强力密码攻击](attack-simulator.md#bruteforce)
    
若要成功启动攻击, 请对要使用的帐户使用多重身份验证, 以运行模拟攻击。 此外, 您必须是 Office 365 全局管理员。
  
> [!NOTE]
> 即将推出对条件访问的支持。 
  
若要访问攻击模拟器, 请在&amp; "安全合规性中心" 中, 选择 "**威胁管理** \> **攻击模拟器**"。
  
## <a name="before-you-begin"></a>开始之前 .。。

请确保您和您的组织满足以下攻击模拟器的要求:
      
- **您的组织的电子邮件托管在 Exchange Online 中**。 (攻击模拟器对本地电子邮件服务器不可用。)
    
- **你是 Office 365 全局管理员**
    
- **[多因素身份验证](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication?view=o365-worldwide)(MFA) 已打开, 至少适用于 Office 365 全局管理员帐户**。 (理想情况下, 将为组织中的所有用户启用 MFA。)
 
- **您的组织具有[Office 365 威胁智能](office-365-ti.md)**, 在安全&amp;合规性中心中显示攻击模拟器 (转到**威胁管理** \> **攻击模拟器**)<br/>![威胁管理-攻击模拟器](media/ThreatMgmt-AttackSimulator.png)

    
## <a name="display-name-spear-phishing-attack"></a>显示名称 spear 网络钓鱼攻击

网络钓鱼是一种通用术语, 用于作为社会工程手段攻击的广泛攻击组 classed。 此攻击主要针对 spear 网络钓鱼, 这是一种更有针对性的攻击, 面向一组特定的个人或组织。 通常, 自定义攻击会执行某些侦测, 并使用将在收件人中生成信任的显示名称, 例如看起来像来自组织中的执行者的电子邮件。
  
此攻击的重点在于通过更改显示名称和源地址, 使您能够操纵发件人显示的来源。 如果 spear 攻击成功, 网络罪犯将获得对用户凭据的访问权限。
  
### <a name="to-simulate-a-spear-phishing-attack"></a>模拟 spear 网络钓鱼攻击

![撰写电子邮件正文](media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)
  
您可以直接在**电子邮件正文**字段中手工创建丰富的 HTML 编辑器, 或使用 HTML 源。
  
1. 在 "[安全&amp;合规性中心](https://protection.office.com)" 中, 选择 "**威胁管理** \> **攻击模拟器**"。
    
2. 为攻击指定有意义的市场活动名称或选择一个模板。 <br/>![网络钓鱼起始页](media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)
  
3. 指定目标收件人。 它可以是组织中的个人或组。 每个目标收件人都必须具有 Exchange Online 邮箱, 攻击才会成功。 <br/>![收件人选择](media/faf8c2e0-6175-4cd7-8265-0c8e727f4d0f.jpg)
  
4. 配置网络钓鱼电子邮件详细信息。 <br/>![配置电子邮件详细信息](media/f043608f-f8ce-4aae-be28-86e8ecc524a9.jpg)<br/>HTML 格式可以是复杂的, 也可以是基本的活动需求。 由于电子邮件格式为 HTML, 因此您可以插入图像和文本, 以增强 believability。 您可以控制收到的邮件在接收电子邮件客户端中的显示形式。
    
5. 指定 "**发件人" (名称)** 域的文本。 这是在接收电子邮件客户端的**显示名称**中显示的字段。 
    
6. 指定文本或 "**发件人**" 字段。 这是在接收电子邮件客户端中显示为发件人的电子邮件地址的字段。 <br/>您可以在组织中输入现有的电子邮件命名空间 (这样做将使电子邮件地址在接收客户端中实际解析, 从而便于实现非常高的信任模型), 也可以输入外部电子邮件地址。 您指定的电子邮件地址不一定确实存在, 但需要遵循有效 SMTP 地址的格式, 例如, 用户 @ domainname. 扩展名。 
  
7. 使用下拉选择器, 选择一个网络钓鱼登录服务器 URL, 该 URL 反映你将在攻击中遇到的内容的类型。 提供了多个主题 url 供您选择, 例如文档交付、技术、工资等。实际上, 这是要求目标用户单击的 URL。
    
8. 指定自定义登陆页面 URL。 使用此将会将用户重定向到成功攻击结束时指定的 URL。 例如, 如果您具有内部意识培训, 可以在此处指定。
    
9. 指定 "**主题**" 字段的文本。 这是在接收电子邮件客户端中显示为**主题名称**的字段。 
    
10. 撰写目标将接收的**电子邮件正文**。 <br/>`${username}`将目标名称插入到电子邮件正文中。 <br/>`${loginserverurl}`插入要让目标用户单击的 URL 
    
11. 选择 **"下一步",** 然后单击 "**完成**" 以启动攻击。 将 spear 网络钓鱼电子邮件传递到目标收件人的邮箱。 
    
## <a name="password-spray-attack"></a>密码喷涂攻击

对组织的密码喷涂攻击通常在损坏的主角成功从租户获取有效用户列表之后使用。 错误参与者知道用户使用的常见密码。 这是一种广泛使用的攻击, 因为它是运行的廉价攻击, 并且比强力方法更难检测。
  
此攻击的重点是让您可以为用户的大型目标群体指定一个公用密码。
  
### <a name="to-simulate-a-password-spray-attack"></a>模拟密码喷涂攻击

1. 在 "[安全&amp;合规性中心](https://protection.office.com)" 中, 选择 "**威胁管理** \> **攻击模拟器**"。
    
2. 为攻击指定有意义的市场活动名称。
    
3. 指定目标收件人。 它可以是组织中的个人或组。 目标收件人必须具有 Exchange Online 邮箱, 攻击才会成功。
    
4. 指定用于攻击的密码。 例如, 您可以尝试的`Fall2017`一个常见的相关密码。 另一个可能`Spring2018`是或`Password1`。
    
5. 选择 "**完成**" 以启动攻击。 
    
## <a name="brute-force-password-attack"></a>强力密码攻击

对组织的强力密码攻击通常在已损坏的主角成功从租户获取关键用户列表之后使用。 此攻击主要针对单个用户的帐户尝试使用一组密码。
  
### <a name="to-simulate-a-brute-force-password-attack"></a>模拟强力密码攻击

1. 在 "[安全&amp;合规性中心](https://protection.office.com)" 中, 选择 "**威胁管理** \> **攻击模拟器**"。
    
2. 为攻击指定有意义的市场活动名称。
    
3. 指定目标收件人。 目标收件人必须具有 Exchange Online 邮箱, 攻击才会成功。
    
4. 指定用于攻击的一组密码。 为此, 您可以对密码列表使用文本 (.txt) 文件。 文件大小中的文本文件不能超过 10 MB。 每行使用一个密码, 并确保在列表中的最后一个密码后面包含一个硬回车。
    
5. 选择 "**完成**" 以启动攻击。 
    
## <a name="new-features-in-attack-simulator"></a>攻击模拟器中的新功能

向攻击模拟器添加了新功能。 具体包括：

- **高级报告功能**。 您将能够查看诸如速度最快 (或最慢) 的数据打开攻击模拟电子邮件、最快 (或最慢) 的时间单击邮件中的链接等。

- **电子邮件模板编辑器**。 您可以创建可用于将来的攻击模拟的自定义、可重用电子邮件模板。

请访问[Microsoft 365 路线图](https://www.microsoft.com/microsoft-365/roadmap)以查看正在开发的内容、正在滚动的内容以及已启动的内容。

## <a name="see-also"></a>另请参阅

[Office 365 高级威胁防护服务 Desription](https://docs.microsoft.com/en-us/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)

[Office 365 高级威胁防护](office-365-atp.md)



