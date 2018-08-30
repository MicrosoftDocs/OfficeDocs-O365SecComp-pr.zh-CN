---
title: 配置组织的监督策略
ms.author: brendonb
author: brendonb
manager: laurawi
ms.date: 5/12/2017
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.SupervisoryReview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MET150
- MOE150
ms.assetid: d14ae7c3-fcb0-4a03-967b-cbed861bb086
description: 设置监督审阅策略来捕获员工通信进行审阅。
ms.openlocfilehash: a919d65f5c0967a44ac12b7e02d477dac2113704
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22526081"
---
# <a name="configure-supervision-policies-for-your-organization"></a>配置组织的监督策略

使用监督策略来捕获员工通信的内部或外部的审阅者的检查。
  
> [!NOTE]
> 使用监督策略要求对您的组织的 Office 365 E5 订阅。如果您不具有该计划，并且想要尝试监督，您还可以[注册试用版的 Office 365 企业 E5](https://go.microsoft.com/fwlink/p/?LinkID=698279)。 
  
请按照下列步骤设置和 Office 365 组织中使用监督： 
  
- [为监督设置组](configure-supervision-policies.md#exampledist)
    
    开始使用监督之前，确定谁将其通信检查以及谁将执行这些 reviews （英文）。如果您想要开始使用几个用户查看监督的工作方式，则可以跳过现在设置组。
    
- [您的组织中公开监督](configure-supervision-policies.md#SRavailable)
    
    将自己添加到监督审阅角色组以便您可以设置策略。已分配该角色的任何人都可以访问下安全中的**数据调控****监督**页&amp;合规性中心。 
    
- [设置监督策略](configure-supervision-policies.md#setupsuper)
    
    您将创建监督策略中安全&amp;合规性中心。这些策略定义的通信将受到组织中查看和指定用户应执行 reviews （英文）。Communications 包括电子邮件，以及第三方平台 communications （如 Facebook、 Twitter 等。）
    
- [使用 Outlook web app 查看 communications 标识监督策略](configure-supervision-policies.md#UseOutlook)
    
    监督外接程序，审阅者访问 Outlook web app 中右监督功能这样他们可以评估并对每个项目进行分类。对桌面的 Outlook 版本支持即将提供。
    
- **运行监督报告**
    
    使用监督报表查看级别的策略和审阅者的查看活动。对于每个策略，您还可以查看活动的当前状态查看 live 统计信息。有关详细信息，请参阅[监督 reports](supervision-reports.md)。
    
## <a name="set-up-groups-for-supervision"></a>为监督设置组
<a name="exampledist"> </a>

 创建监督策略时，您将决定谁将具有检查其通信以及谁将执行这些 reviews （英文）。在策略，您将使用电子邮件地址来标识个人或组的人员。若要简化您的设置，创建组会检查其通信的人员和组将查看这些通信的人员。如果您使用的组，则可能需要几个 — 例如，如果您想要监控的人员，两个不同组之间的通信，或如果您想要指定不打算管理组。有关此工作原理的详细信息，请参阅[示例通讯组](configure-supervision-policies.md#GroupExample)。 
  
监督 communications 之间或在组织中的组中，请在 Exchange 管理中心中设置通讯组 (转到**收件人** \> **组**)。有关设置通讯组的详细信息，请参阅[管理通讯组](http://go.microsoft.com/fwlink/?LinkId=613635)
  
> [!NOTE]
> 您可还用于动态通讯组或安全组监督如果您愿意。为了帮助您决定是否这些更好地满足组织需求，请参阅[管理已启用邮件的安全组](http://go.microsoft.com/fwlink/?LinkId=627033)和[管理动态通讯组](http://go.microsoft.com/fwlink/?LinkId=627058)。 
  
### <a name="example-distribution-groups"></a>示例通讯组
<a name="GroupExample"> </a>

本示例包含已设置名为 Contoso 财务国际财务组织的通讯组。 
  
在 Contoso Financial International 中，必须监督美国经纪人之间的通信抽样。但是，无需监督该组中的合规部主管。对于本例，我们可以创建以下组：
  
|**设置此通讯组**|**组地址（别名）**|**说明**|
|:-----|:-----|:-----|
|所有美国经纪人  <br/> |US_Brokers@Contoso.com  <br/> |此组包括为 Contoso 工作的所有在美国的经纪人的电子邮件地址。  <br/> |
|所有美国合规部主管  <br/> |US_Compliance@Contoso.com  <br/> |此组包括所有美国合规部主管，就职 contoso 电子邮件地址。由于此组的所有美国经纪人子集，因此可以从监督策略到例外合规部主管使用此别名。  <br/> |
   
[设置监督策略](configure-supervision-policies.md#setupsuper)一节描述如何配置策略时使用这些组。 
  
## <a name="make-supervision-available-in-your-organization"></a>您的组织中公开监督
<a name="SRavailable"> </a>

为了使**监督**菜单选项安全&amp;合规性中心，您必须分配监督审阅管理员角色。 
  
若要执行此操作，也可以将自己添加为监督审阅角色组的成员，也可以创建新的角色组。
  
### <a name="add-members-to-the-supervisory-review-role-group"></a>向主管审阅角色组添加成员

1. 登录到[https://protection.office.com](https://protection.office.com)使用 Office 365 组织中的管理帐户的凭据。 
    
2. 安全中&amp;合规性中心中，转到**权限**。
    
3. 选择**监督审阅**角色组，然后单击编辑图标。 
    
4. 在**成员**部分中，添加您要管理您的组织的监督的人员。 
    
### <a name="create-a-new-role-group"></a>创建新的角色组

1. 登录到[https://protection.office.com](https://protection.office.com)使用 Office 365 组织中的管理帐户的凭据。 
    
2. 安全中&amp;合规性中心，转到**权限**，然后单击添加 ( **+**)。
    
3. 在**角色**部分中，单击添加 ( **+**) 和向下的滚动到**监督审阅管理员**。将此角色添加到角色组。
    
4. 在**成员**部分中，添加您要管理您的组织的监督的人员。 
    
有关角色组和权限的详细信息，请参阅[Permissions in Office 365 安全性&amp;合规性中心](permissions-in-the-security-and-compliance-center.md)。
  
## <a name="set-up-a-supervision-policy"></a>设置监督策略
<a name="setupsuper"> </a>

> [!IMPORTANT]
> 创建监督策略之前，必须首先删除任何现有的监督审阅策略。 
  
1. 登录到[https://protection.office.com](https://protection.office.com)使用 Office 365 组织中的管理帐户的凭据。 
    
2. 安全中&amp;合规性中心中，转到单击**数据调控** \> **监督**。
    
    > [!NOTE]
    > 在左侧导航窗格中作为**监督审阅 (retiring 很快)** 可能会显示以前版本的功能。将很快否决此版本，并为其移除。调用**监督**的新版本需要其位置。 
  
3. 单击**创建**，然后按照向导设置策略的以下页面。 
    
### <a name="policy-name-and-description"></a>策略名称和说明

输入名称和您的策略的说明。出于举例目的，我们将命名策略 Contoso 美国经纪人。
  
### <a name="choose-users-to-supervise"></a>选择要管理用户

- 在**Supervise 这些用户或组**框中，选择用户或组监督您希望其通信。为 Contoso 美国经纪人粘滞与我们的示例，我们将选择组 US_Brokers@Contoso.com 此处。 
    
- 如果您选择某个组将监督，您可以使用**来排除这些用户**框中选择不受监督的组的成员。使用的示例，我们将排除组 US_Compliance@Contoso.com 此处。 
    
### <a name="choose-communications-to-review"></a>选择通信查看
<a name="CommsToReview"> </a>

默认情况下，**方向**条件显示，并且无法删除。如果您想要范围 （如仅查看内容，其中包含特定词或短语），进一步查看，请单击**添加条件**。如果需要您可以指定多个条件。
  
您选择的条件 （类似于从 Facebook 或收存箱） 在组织中的电子邮件和第三方源中将适用于通讯。关于导入您的 Office 365 组织的第三方通信的详细信息，请参阅[Office 365 中的存档第三方数据](https://technet.microsoft.com/EN-US/library/mt621583.aspx)。
  
下表详细解释每个条件。
  
|**条件**|**如何使用此条件**|
|:-----|:-----|
|用法说明  <br/> |选择**入站**查看 communications 发送**到**您选择监督**从**人员的人不包含在策略。  <br/> 如果您想要查看的通信选择**出站****发送您选择监督的人员*** * 到 * * 人员不包含在策略。  <br/> 在策略，选择**内部**查看发送通信**之间**标识的人员。  <br/> |
|邮件包含以下任何词语  <br/> 邮件包含无下列单词  <br/> |若要将策略应用时包括或排除在邮件中特定词或短语，输入每个单词或短语单独占一行。将分别应用您输入的单词的每一行 （要应用于邮件的策略必须应用这些行中的只有一个）。关于输入词或短语的详细信息，请参阅下一节[匹配单词和短语针对电子邮件或附件](configure-supervision-policies.md#Matchwords)。<br/> |
|附件包含以下任何词语  <br/> 附件包含无下列单词  <br/> |若要将策略应用时包括或排除在邮件附件 （如 Word 文档） 中特定词或短语，输入每个单词或短语单独占一行。将分别应用您输入的单词的每一行 （只有一个行必须应用于附件的策略）。关于输入词或短语的详细信息，请参阅下一节[匹配单词和短语针对电子邮件或附件](configure-supervision-policies.md#Matchwords)。<br/> |
|附件是任何这些文件类型  <br/> 附件是无这些文件类型  <br/> |监督 communications 包含或排除特定类型的附件，输入 （如.exe 或.pdf） 的文件扩展名。如果您想要包括或排除多个文件扩展名，输入这些在单独的行。只有一个附件扩展需要匹配要应用的策略。  <br/> |
|邮件大小大于  <br/> 不能超过消息大小  <br/> |若要查看基于特定大小的邮件，使用这些条件来指定受到审阅之前，可以是一条消息的最大值或最小大小。例如，如果您指定**邮件大小大于** \> **1.0 MB**，为 1.01 MB 和较大将的所有邮件采用审阅。您可以选择字节、 千字节、 兆字节或此条件千兆字节。<br/> |
|附件大于  <br/> 附件是不大于  <br/> |若要查看邮件及其附件的大小，指定附件的最大值或最小大小可在消息之前和及其附件将受到审阅。例如，如果您指定**附件大于** \> **2.0 MB**，所有邮件的附件 2.01 MB 和转移将采用审阅。您可以选择字节、 千字节、 兆字节或此条件千兆字节。<br/> |
   
#### <a name="matching-words-and-phrases-to-emails-or-attachments"></a>将字词和短语与电子邮件或附件匹配
<a name="Matchwords"> </a>

将分别应用您输入的单词的每一行 （只有一个行必须应用于电子邮件或附件策略条件）。例如，我们使用条件时，**邮件包含以下任何词语**，与关键字"四"和"内幕交易"置于单独的行。该策略将应用到包括"四"单词或短语"内幕交易"任何消息。只有一个这些单词或短语必须进行要应用此策略条件。在邮件或附件的单词必须完全匹配您的输入。
  
#### <a name="entering-multiple-conditions"></a>输入多个条件
<a name="Matchwords"> </a>

如果您输入多个条件，Office 365 使用的所有条件一起确定何时将策略应用于通信项。当您设置了多个条件时，它们必须所有满足策略应用，除非您输入的例外。例如，假设您需要创建的策略，应该应用如果邮件包含单词"贸易"，并且大于 2 MB。不过，如果邮件还包含单词"contoso 财务已批准"，应该不会应用策略。因此，在这种情况下，三个条件将，如下所示： 
  
- **邮件包含以下任何词语**，与"贸易"的关键字
    
- **邮件大小大于**，与值 2 MB
    
- **邮件包含无下列单词**，与关键字"Contoso 财务团队已批准"。
    
### <a name="specify-percentage-to-review"></a>指定要查看的百分比
<a name="CommsToReview"> </a>

如果您希望以减少要查看的内容量，指定百分比。从您选择的条件匹配的总，我们将随机选择的内容量。如果您希望的审阅者的所有项目，输入**100%**。
  
### <a name="choose-reviewers"></a>选择审阅者
<a name="CommsToReview"> </a>

用户和组您选择将用于监督应用程序 Outlook web app 中检查通信返回此策略。您可以包括内部或外部的审阅者的电子邮件地址。 
  
### <a name="review-your-settings"></a>检查您的设置
<a name="CommsToReview"> </a>

您已完成所有节的监督策略后，查看您的设置，然后单击**完成**以保存您的策略。可能需要几个小时要启动捕获通信的策略。监督到的共享文件夹的审阅者可以访问 Outlook web app 中提供了供审阅的所有通信。 
  
## <a name="use-outlook-web-app-to-review-communications-identified-by-a-supervision-policy"></a>使用 Outlook web app 查看 communications 标识监督策略
<a name="UseOutlook"> </a>

审阅者将使用监督外接程序 Outlook web app 查看 communications。外接程序是自动安装 Outlook web app 中的所有策略中指定的审阅者。对桌面的 Outlook 版本支持即将提供。
  
 **查看 Outlook web app 中的通信**
  
1. 在 Outlook web app 中，展开**监督-\<策略名称\>** 文件夹。 
    
2. 在**\<策略名称\>** 子文件夹，审阅者会看到该监督策略被标识的所有通信。 
    
    ![监督外接程序显示所选的监督策略子文件夹的 Outlook web app 中](media/eef329bf-2bd0-477e-a715-76ca19b3347f.jpg)
  
3. 打开一个项目以查看并单击**监督**加载项。 
    
4. 使用外接程序对项目进行分类为**符合**、**不兼容**， **Questionable**或**已解决**。您已分类项目后，它将移到下的相应子文件夹**\<策略名称\>** 文件夹。 
    

