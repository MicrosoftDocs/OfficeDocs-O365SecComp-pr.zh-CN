---
title: 配置组织的监督策略
ms.author: robmazz
author: robmazz
manager: laurawi
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.SupervisoryReview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
- MOE150
ms.assetid: d14ae7c3-fcb0-4a03-967b-cbed861bb086
description: 设置监管审核策略以捕获员工通信以供审阅。
ms.openlocfilehash: 76a5e7152b609944eeb2fe1390e204e1463a673b
ms.sourcegitcommit: 9a69ea604b415af4fef4964a19a09f3cead5a2ce
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/20/2019
ms.locfileid: "30701287"
---
# <a name="configure-supervision-policies-for-your-organization"></a>配置组织的监督策略

使用监督策略来捕获由内部或外部审阅者进行检查的员工通信。 有关监察策略如何帮助您监视组织中的通信的详细信息, 请参阅[Office 365 中的监察策略](supervision-policies.md)。

> [!NOTE]
> 监督策略监视的用户必须拥有 Microsoft 365 E5 合规性许可证、具有高级合规性加载项的 Office 365 企业版 E3 许可证, 或包含在 office 365 企业版 E5 订阅中。
如果你没有现有的企业版 E5 计划, 并且想要尝试监督, 则可以[注册 Office 365 企业版 e5 的试用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。
  
按照以下步骤在 Office 365 组织中设置和使用监督:
  
- **步骤 1 (可选)** - [为监督设置组](configure-supervision-policies.md#exampledist)

    在开始使用监督之前, 请先确定谁将查看其通信, 以及谁将执行这些审阅。 如果您只想开始几个用户来了解监督工作的工作方式, 则可以跳过 "立即" 设置组。

- **步骤 2 (必需)** - [使监督在您的组织中可用](configure-supervision-policies.md#MakeAvailable)

    将自己添加到监管审核角色组, 以便您可以设置策略。 分配此角色的任何人都可以访问 Security & 合规中心内的**数据管理**下的**监督**页面。 如果要审阅的电子邮件托管在 Exchange online 中, 则每个审阅者还必须具有[对 exchange online 的远程 PowerShell 访问权限](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell)。

- **步骤 3 (可选)** - [配置自定义敏感信息类型或自定义关键字词典/词典](configure-supervision-policies.md#sensitiveinfo)

    如果需要对监督策略使用自定义敏感信息类型或自定义关键字词典, 则需要在启动监督向导之前创建它。

- **步骤 4 (必需)** - [设置监督策略](configure-supervision-policies.md#setupsuper)

    你将在安全 & 合规中心中创建监督策略。 这些策略定义哪些通信将在组织中进行审核, 并指定应执行审阅的用户。 通信包括电子邮件和 Microsoft 团队通信, 以及第三方平台通信 (如 Facebook、Twitter 等)

- **第5步-(可选)**[测试新的监督策略](configure-supervision-policies.md#TestPolicy)

    测试您的监督策略以确保其正常运行是确保合规性策略满足您的标准所需的重要部分。

- **步骤 6-(可选)**[为不希望使用 Office 365 监督仪表板或 web 上的 outlook (以前称为 Outlook web App) 的审阅者配置 Outlook 以查看受监督的通信](configure-supervision-policies.md#UseOutlook)

    outlook 可以配置为使审阅者能够访问 Outlook 客户端中的监督功能, 以便他们能够评估和分类每个项目。

<a name="exampledist"> </a>

## <a name="step-1---set-up-groups-for-supervision-optional"></a>步骤 1-设置监控组 (可选)

 当您创建监督策略时, 您将确定谁将查看其通信, 以及谁将执行这些审阅。 在策略中, 您将使用电子邮件地址来标识个人或用户组。 为简化您的设置, 您可以为要查看其通信的用户创建组, 并为将查看这些通信的用户分组。 如果您使用的是组, 则可能需要多个 (例如, 如果要监视两个不同的人员组之间的通信, 或者如果您想要指定一个不受监督的组)。

使用以下图表可帮助您在组织中配置监督策略的组:

| **Policy 成员** | **支持的组** | **不受支持的组** |
|:-----|:-----|:-----|
|受监督用户 | 通讯组 <br> Office 365 组 | 动态通讯组 |
| Reviewers | 启用邮件功能的安全组  | 通讯组 <br> 动态通讯组 |
  
有关设置组的详细信息, 请参阅:
- [创建和管理通讯组](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups)
- [管理启用邮件的安全组](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups)
- [Office 365 组概述](https://docs.microsoft.com/office365/admin/create-groups/office-365-groups?view=o365-worldwide)

<a name="MakeAvailable"> </a>

## <a name="step-2---make-supervision-available-in-your-organization-required"></a>第2步-使监督在你的组织可用 (必需)

若要在安全 & 合规中心中将**监察**功能作为菜单选项提供, 您必须分配有监管审核管理员角色。
  
若要执行此操作, 您可以将自己添加为监管审核角色组的成员, 也可以创建新的角色组。
  
### <a name="add-members-to-the-supervisory-review-role-group"></a>将成员添加到监管审核角色组

1. 在 Office [https://protection.office.com](https://protection.office.com) 365 组织中使用管理员帐户的凭据进行登录。

2. 在 "安全 & 合规性中心" 中, 转到 "**权限**"。

3. 选择 "**监管审核**" 角色组, 然后单击 "编辑" 图标。

4. 在 "**成员**" 部分, 添加要为组织管理监督的人员。

### <a name="create-a-new-role-group"></a>创建新的角色组

1. 在 Office [https://protection.office.com](https://protection.office.com) 365 组织中使用管理员帐户的凭据进行登录。

2. 在 "安全 & 合规性中心" 中, 转到 "**权限**"**+**, 然后单击 "添加" ()。

3. 在 "**角色**" 部分中, 单击**+**"添加" (), 然后向下滚动到 "**监察审核管理员**"。 将此角色添加到角色组。

4. 在 "**成员**" 部分, 添加要为组织管理监督的人员。

有关角色组和权限的详细信息, 请参阅[Office 365 安全&amp;合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。

### <a name="enable-remote-powershell-access-for-reviewers-if-email-is-hosted-on-exchange-online"></a>为审阅者启用远程 PowerShell 访问 (如果 Exchange Online 上托管电子邮件)

1. 按照[启用或禁用对 Exchange Online PowerShell 的访问](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell)中的指导进行操作。

<a name="sensitiveinfo"> </a>
  
## <a name="step-3---create-custom-sensitive-information-types-and-custom-keyword-dictionaries-optional"></a>步骤 3-创建自定义敏感信息类型和自定义关键字词典 (可选)

若要从监督策略向导中的现有自定义敏感信息类型或自定义关键字词典中进行选择, 需要先创建这些项目。

### <a name="create-custom-keyword-dictionarylexicon-optional"></a>创建自定义关键字词典/词典 (可选)

使用文本编辑器 (如记事本), 创建一个新文件, 其中包含要在监督策略中监视的关键字术语。 确保每个术语都位于单独的行中, 并将该文件保存为**Unicode/utf-16 (小 Endian)** 格式。

### <a name="create-custom-sensitive-information-types"></a>创建自定义敏感信息类型

1. 创建新的敏感信息类型, 并将您的自定义词典添加到 Office 365 Security & 合规中心。 导航到 "**分类** \> " "**敏感信息**类型", 然后按照新的 "**敏感信息类型" 向导**中的步骤操作。 你将在此处执行以下操作:

    - 定义敏感信息类型的名称和说明
    - 定义邻近度、置信度和主要模式元素
    - 将自定义词典作为匹配元素的要求导入
    - 查看您的选择并创建敏感信息类型

    有关更多详细信息, 请参阅[创建自定义敏感信息类型](create-a-custom-sensitive-information-type.md)和[创建关键字词典](create-a-keyword-dictionary.md)

    创建自定义词典/词典之后, 可以使用[DlpKeywordDictionary](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/get-dlpkeyworddictionary) cmdlet 查看配置的关键字, 也可以使用[DlpKeywordDictionary](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/set-dlpkeyworddictionary) cmdlet 添加和删除术语。

<a name="setupsuper"> </a>

## <a name="step-4---set-up-a-supervision-policy-required"></a>步骤 4-设置监督策略 (必需)
  
1. 在 Office [https://protection.office.com](https://protection.office.com) 365 组织中使用管理员帐户的凭据进行登录。

2. 在 "安全 & 合规中心" 中, 选择 "**监督**"。
  
3. 选择 "**创建**", 然后按照向导设置此策略的以下页面。 使用该向导, 您将:

    - 为策略指定名称和说明。
    - 选择要监督的用户或组, 包括选择要排除的用户或组。
    - 定义监督策略条件。
    - 选择是否要包含敏感信息类型。 你可以在此处选择默认和自定义敏感信息类型。
    - 定义要查看的通信百分比。
    - 选择策略的审阅者。 审阅者可以是单个用户, 也可以是[启用邮件的安全组](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups#create-a-mail-enabled-security-group)。
    - 查看策略选择并创建策略。

<a name="TestPolicy"> </a>

## <a name="step-5---test-your-supervision-policy-optional"></a>第5步-测试监察策略 (可选)

创建监督策略后, 最好进行测试以确保策略正确地强制实施了您定义的条件。 如果监督策略中包含敏感信息类型, 您可能还需要[测试数据丢失防护 (DLP) 策略](create-test-tune-dlp-policy.md)。 按照以下步骤测试您的监察策略:

1. 打开以您要测试的策略中定义的监督用户身份登录的电子邮件客户端或 Microsoft 团队。
2. 发送符合您在监督策略中定义的条件的电子邮件或 Microsoft 团队聊天。 它可以是关键字、附件大小、域等。请确保您确定策略中配置的条件设置过于严格或太 lenient。

    > [!Note]
    > 已定义策略的电子邮件将在接近实时的情况中进行处理, 并且可以在配置策略后立即进行测试。 Microsoft 团队中的聊天可能需要长达24小时才能在策略中完全处理。 

3. 以监督策略中指定的审阅者的形式登录到 Office 365 租户。 导航到 "**监控** > "*您的自定义策略* > **打开**以查看该策略的报告。

<a name="UseOutlook"> </a>

## <a name="step-6---configure-outlook-for-reviewers-optional"></a>步骤 6-配置 Outlook for 审阅者 (可选)

要使用 Outlook 而不是使用 Office 365 中的监督仪表板检查通信的审阅者必须配置其 Outlook 客户端。

### <a name="step-1-copy-the-address-for-the-supervision-mailbox"></a>步骤 1: 复制监督邮箱的地址

若要为 outlook 桌面或 outlook for web 配置审阅, 你将需要作为监督策略安装程序的一部分创建的监督邮箱的地址。
  
> [!NOTE]
> 如果其他人创建了该策略, 则需要从这些地址获取该地址以安装加载项。

 **查找监督邮箱地址**
  
1. 使用 Office 365 组织中的管理员帐户的凭据登录到[ &amp;安全合规中心](https://protection.office.com)。

2. 转到 "**监督**"。

3. 单击收集您要查看的通信的监督策略。

4. 在 "策略详细信息" 浮出控件的 "**监督邮箱**" 下, 复制地址。<br/>![监督策略的详细信息浮出控件的 "监督邮箱" 部分, 显示监督邮箱地址突出显示](media/71779d0e-4f01-4dd3-8234-5f9c30eeb067.jpg)
  
### <a name="step-2-configure-the-supervision-mailbox-for-outlook-access"></a>步骤 2: 为 Outlook access 配置监督邮箱

接下来, 审阅者将需要运行几个 Exchange Online PowerShell 命令, 以便他们可以将 Outlook 连接到监督邮箱。
  
1. 连接到 Exchange Online PowerShell。 [我该如何做？](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)

2. 运行以下命令, 其中*SupervisoryReview {GUID}* 是您在上面的步骤1中复制的地址,*用户*是将在步骤3中连接到监管邮箱的审阅者的姓名。

    ```Add-MailboxPermission "SupervisoryReview{GUID}@domain.onmicrosoft.com" -User <alias or email address of the account that has reviewer permissions to the supervision mailbox> -AccessRights FullAccess```

    ```Set-Mailbox "<SupervisoryReview{GUID}@domain.onmicrosoft.com>" -HiddenFromAddressListsEnabled: $false```

3. 请等待至少一小时, 然后再转到下面的步骤3。

### <a name="step-3-create-an-outlook-profile-to-connect-to-the-supervision-mailbox"></a>步骤 3: 创建 Outlook 配置文件以连接到监督邮箱

在最后一步中, 审阅者将需要创建 Outlook 配置文件以连接到监督邮箱。

> [!NOTE]
> 若要创建新的 Outlook 配置文件, 请使用 Windows 控制面板中的 "邮件" 设置。 获取这些设置所需的路径可能取决于所使用的 windows 操作系统 (windows 7、windows 8 或 windows 10) 以及安装了哪个版本的 Outlook。
  
1. 打开 "控制面板", 然后在窗口顶部的 "**搜索**" 框中, 键入**Mail**。<br/>(不确定如何访问控制面板？ 请参阅[控制面板在什么位置？](https://support.microsoft.com/help/13764/windows-where-is-control-panel)
  
2. 打开**邮件**应用程序。

3. 在**邮件安装程序-Outlook**中, 单击 "**显示配置文件**"。<br/>![突出显示 "显示配置文件" 按钮的 "邮件设置-Outlook" 对话框](media/28b5dae9-d10c-4f2b-926a-294c857d555c.jpg)
  
4. 在 "**邮件**" 中, 单击 "**添加**"。 然后, 在 "**新建配置文件**" 中, 输入监督邮箱的名称 (如**监督**)。<br/>!["新建配置文件" 对话框显示 "配置文件名称" 框中的 "监督" 名称](media/d02ae181-b541-4ec6-8f51-698f30033204.jpg)
  
5. 在 "**将 Outlook 连接到 Office 365**" 中, 单击 "**连接到其他帐户**"。<br/>![突出显示了 "连接到不同帐户的 Office 365" 链接的 "将 Outlook 连接到 Office" 的消息](media/fac49ff8-a7f0-4e82-a271-9ec045a95de1.jpg)
  
6. 在 "**自动帐户设置**" 中, 选择 "**手动安装或其他服务器类型**", 然后单击 "**下一步**"。

7. 在 "**选择帐户类型**" 中, 选择 " **Office 365**"。 然后, 在 "**电子邮件地址**" 框中, 输入您之前复制的监督邮箱的地址。<br/>![Outlook 中显示 "电子邮件地址" 框的 "选择帐户类型" 页面中的 "添加帐户" 对话框中突出显示了 "电子邮件地址" 框。](media/4f601236-9f69-4cf6-a58c-0b91204aa8cb.jpg)
  
8. 出现提示时, 请输入 Office 365 凭据。

9. 如果成功, 你将看到 "**监督- \<策略名称\> ** " 文件夹列在 Outlook 的文件夹列表视图中。

## <a name="powershell-reference"></a>PowerShell 参考

如果需要, 可以使用以下 PowerShell cmdlet 创建和管理监督策略:

- [新 SupervisoryReviewPolicyV2](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-supervisoryreviewpolicyv2?view=exchange-ps)
- [SupervisoryReviewPolicyV2](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/get-supervisoryreviewpolicyv2?view=exchange-ps)
- [SupervisoryReviewPolicyV2](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-supervisoryreviewpolicyv2?view=exchange-ps)
- [SupervisoryReviewPolicyV2](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/remove-supervisoryreviewpolicyv2?view=exchange-ps)
- [新 SupervisoryReviewRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-supervisoryreviewrule?view=exchange-ps)
- [SupervisoryReviewRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-supervisoryreviewrule?view=exchange-ps)
- [SupervisoryReviewActivity](https://docs.microsoft.com/powershell/module/exchange/reporting/get-supervisoryreviewactivity)
- [SupervisoryReviewOverallProgressReport](https://docs.microsoft.com/powershell/module/exchange/reporting/get-supervisoryreviewoverallprogressreport)
- [SupervisoryReviewTopCasesReport](https://docs.microsoft.com/powershell/module/exchange/reporting/get-supervisoryreviewtopcasesreport)