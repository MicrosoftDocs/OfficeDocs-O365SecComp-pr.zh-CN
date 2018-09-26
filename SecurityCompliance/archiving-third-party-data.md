---
title: 在 Office 365 中存档第三方数据
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 9/5/2017
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid: MOE150
ms.assetid: 0ce338d5-3666-4a18-86ab-c6910ff408cc
description: 管理员可以从导入第三方数据社交媒体平台、 即时消息平台，以及文档协作平台到 Office 365 组织中的邮箱。这样可以存档来自 Office 365 中的 Facebook、 Twitter 和数据源的数据。然后您可以对第三方数据 appply Office 365 合规性功能 （如合法保留、 内容搜索和保留策略）。
ms.openlocfilehash: 5e8fe94e0c3e8b39aec479f4755a263438513d35
ms.sourcegitcommit: 7956955cd919f6e00b64e4506605a743c5872549
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/26/2018
ms.locfileid: "25038105"
---
# <a name="archiving-third-party-data-in-office-365"></a>在 Office 365 中存档第三方数据

Office 365 允许管理员导入和存档即时消息平台和文档协作平台，对您的 Office 365 组织中邮箱的从社交媒体平台的第三方数据。可以导入到 Office 365 的第三方数据源的示例包括： 
  
- **社交**-Twitter、 Facebook、 Yammer 和 LinkedIn 
    
- **即时消息**-Yahoo Messenger 和 GoogleTalk，Cisco Jabber 
    
- **文档协作**-框和收存箱 
    
- **纵向行业**-客户关系管理 （如销售队伍争议） 和财务 （如 Thomson Reuters 和彭博美国） 
    
- **SMS/短信服务**的 BlackBerry 
    
导入第三方数据后，您可以应用 Office 365 合规性功能，如诉讼保留、 内容搜索、 就地存档、 审核和 Office 365 的保留策略 — 对此数据。例如，当邮箱置于诉讼保留，将保留第三方的数据。您可以通过使用内容搜索中搜索第三方数据。或可应用存档和保留策略与第三方数据像可用于 Microsoft 数据。简而言之，存档 Office 365 中的第三方数据可帮助组织保持符合政府和法规的策略。
  
下面是第三方数据导入到 Office 365 所需的过程和步骤概述。

[步骤 1：寻找第三方数据合作伙伴](#step-1-find-a-third-party-data-partner)

[步骤 2：在 Office 365 中创建和配置第三方数据邮箱](#step-2-create-and-configure-a-third-party-data-mailbox-in-office-365)

[步骤 3：为第三方数据配置用户邮箱](#step-3-configure-user-mailboxes-for-third-party-data)

[步骤 4：为合作伙伴提供信息](#step-4-provide-your-partner-with-information)

[步骤 5： 在 Azure Active Directory 中注册第三方数据连接器](#step-5-register-the-third-party-data-connector-in-azure-active-directory)

## <a name="how-the-third-party-data-import-process-works"></a>如何第三方数据导入过程适用于 >

下图及说明介绍了第三方数据导入过程的工作原理。
  
![第三方数据导入过程的工作原理](media/5d4cf8e9-b4cc-4547-90c8-d12d04a9f0e7.png)
  
1. 选择要配置连接器，将从第三方数据源提取项目，然后将这些项目导入到 Office 365 其合作伙伴适用于客户。
    
2. 合作伙伴连接器连接到通过第三方 API （基于计划或作为配置） 的第三方数据源，并从数据源提取项目。合作伙伴连接器将项目的内容转换为电子邮件格式。请参阅有关的邮件格式架构的说明[详细信息](#more-information)部分。 
    
3. 合作伙伴连接器连接到 Office 365 中的 Azure 服务使用通过已知的终结点的 Exchange Web 服务 (EWS)。
    
4. 项目便导入到特定用户的邮箱或“catch-all”第三方数据邮箱。无论项目是导入到特定用户邮箱还是第三方数据邮箱，都要基于以下条件：
    
    答：**项目的具有对应于 Office 365 用户帐户的用户 ID** -如果合作伙伴连接器可以将第三方数据源中的项的用户 ID 映射到特定用户在 Office 365 中，项目 ID 被复制到用户的中的**清除**文件夹可恢复项目文件夹。用户无法访问清除文件夹中的项目。但是，您可以使用 Office 365 电子数据展示工具搜索清除文件夹中的项目。
    
    b.**不具有对应于 Office 365 用户帐户的用户 ID 的项**-合作伙伴连接器无法将项目的用户 ID 映射到特定用户在 Office 365 中，项目 ID 被复制到第三方数据邮箱的**收件箱**文件夹。将项目导入到收件箱中登录到要查看和管理这些项，以及是否需要在合作伙伴连接器配置进行任何调整的第三方邮箱贵组织允许您或其他人。
 
## <a name="step-1-find-a-third-party-data-partner"></a>步骤 1：寻找第三方数据合作伙伴

为 Office 365 中的第三方数据存档的关键组件是查找并使用第三方数据源的数据捕获和导入到 Office 365 中的 Microsoft 合作伙伴，专门。导入的数据后，它可以存档和保留与您的组织的其他 Microsoft 数据，如电子邮件从 Exchange 和 SharePoint 和 OneDrive for Business 中的文档。合作伙伴创建从组织的第三方数据源 （如 BlackBerry、 Facebook、 Google +、 Thomson Reuters、 Twitter 和 YouTube） 提取数据，并将该数据传递给将项目导入到 Exchange 邮箱作为 Office 365 API 的连接器将电子邮件。 
  
以下各节列出 Microsoft 合作伙伴 — 和它们支持第三方数据源 — 为 Office 365 中的第三方数据存档程序正在参与。

[17a-4 LLC](#17a-4-llc)
  
[Actiance](#actiance)
  
[ArchiveSocial](#archivesocial)
  
[Globanet](#globanet)
  
[OpenText](#opentext)
  
[Verba](#verba)
  
### <a name="17a-4-llc"></a>17a-4 LLC

17a-4 LLC 支持以下第三方数据源：
  
- BlackBerry
    
- Bloomberg 数据流
    
- Cisco Jabber
    
- FactSet
    
- HipChat
    
- InvestEdge
    
- LivePerson
    
- 
MessageLabs 数据流

    
- OpenText
    
- Oracle/ATG“单击以呼叫”Live 帮助

    
- Pivot IMTRADER

    
- Microsoft SharePoint
    
- MindAlign
    
- Sitrion One (Newsgator)
    
- 
Skype for Business (Lync/OCS)
    
- 
Skype for Business Online (Lync Online)

    
- SQL 数据库
    
- 
Squawker

    
- Thomson Reuters Eikon Messenger

  
### <a name="actiance"></a>Actiance

[Actiance](https://www.actiance.com)支持下列第三方数据源： 
  
- AIM
    
- American Idol
    
- Apple Juice
    
- 
使用 Pivot 客户端的 AOL

    
- Ares
    
- Bazaar Voice
    
- Bear Share
    
- Bit Torrent
    
- BlackBerry 呼叫日志（v5、v10、v12）
    
- BlackBerry Messenger（v5、v10、v12）
    
- BlackBerry PIN（v5、v10、v12）
    
- BlackBerry 短信（v5、v10、v12）
    
- Bloomberg 邮件

    
- CellTrust
    
- Chat Import

    
- 聊天实时日志记录和策略

    
- Chatter

    
- Cisco IM&amp;状态服务器 (v9.0.1、 v9.1，v9.1.1 SU1、 v10，v10.5.1 SU1)
    
- Cisco Unified Presence 服务器（v8.6.3、v8.6.4、v8.6.5）

    
- 协作导入

    
- 协作实时日志记录

    
- Direct Connect
    
- Facebook
    
- FactSet
    
- FastTrack
    
- Gnutella
    
- Google+

    
- GoToMyPC
    
- Hopster
    
- HubConnex
    
- IBM Connections（v3.0.1、v4.0、v4.5、v4.5 CR3、v5）

    
- IBM Connections Chat Cloud

    
- IBM Connections Social Cloud

    
- IBM SameTime Advanced 8.5.2 IFR1

    
- IBM SameTime Communicate 9.0

    
- IBM SameTime Community (v8.0.2、v8.5.1 IFR2、v8.5.2 IFR1、v9.1)

    
- IBM SameTime Complete 9.0

    
- IBM SameTime Conference 9.0

    
- IBM SameTime Meeting 8.5.2 IFR1

    
- ICE/YellowJacket
    
- 即时消息导入

    
- 即时消息实时日志记录和策略

    
- Indii Messenger

    
- 即时 Bloomberg

    
- IRC
    
- Jive

    
- Jive 6 实时日志记录（v6、v7）

    
- Jive 导入
    
- JXTA
    
- LinkedIn
    
- 
Microsoft Lync（2010、2013）

    
- MFTP
    
- Microsoft Lync 2013 语音

    
- Microsoft SharePoint（2010、2013）

    
- Microsoft SharePoint Online
    
- Microsoft UC（统一通信）
    
- MindAlign
    
- Mobile Guard
    
- MSN
    
- My Space
    
- NEONetwork
    
- Office 365 Lync 专用

    
- Office 365 共享即时消息

    
- Pinterest
    
- Pivot
    
- QQ
    
- Skype for Business 2015
    
- SoftEther
    
- Symphony

    
- Thomson Reuters Eikon

    
- Thomson Reuters Messenger

    
- Tor
    
- TTT
    
- Twitter
    
- WinMX
    
- Winny
    
- Yahoo

    
- Yammer
    
- YouTube
    
  
### <a name="archivesocial"></a>ArchiveSocial

[ArchiveSocial](https://www.archivesocial.com)支持下列第三方数据源： 
  
- Facebook
    
- Flickr

    
- Instagram

    
- LinkedIn
    
- Pinterest
    
- Twitter
    
- YouTube
    
- Vimeo
  
### <a name="globanet"></a>Globanet

[Globanet](https://www.globanet.com)支持下列第三方数据源： 
  
- 使用 Pivot 客户端的 AOL 
    
- BlackBerry 呼叫日志（v5、v10、v12）
    
- BlackBerry Messenger（v5、v10、v12）
    
- BlackBerry PIN（v5、v10、v12）
    
- BlackBerry 短信（v5、v10、v12）
    
- Bloomberg 聊天

    
- Bloomberg 邮件

    
- Box

    
- 适用于 Salesforce Chatter 的 CipherCloud
    
- Cisco IM&amp;状态服务器 (v10，v10.5.1 SU1 v11.0，v11.5 SU2)

- Cisco Webex 团队

- Citrix 工作区&amp;ShareFile

- CrowdCompass

- 自定义带分隔符的文本文件

    
- 自定义 XML 文件

    
- Facebook （页）
    
- Factset

    
- FXConnect
    
- ICE Chat/YellowJacket
    
- Jive

    
- Macgregor XIP


- Microsoft Exchange Server
    
- Microsoft OneDrive for Business

- Microsoft Teams
       
- Microsoft Yammer

    
- Mobile Guard
    
- Pivot
    
- Salesforce Chatter

- Skype for Business Online
    
- Skype for Business，版本 2007 R2 - 2016（本地）

    
- Slack Enterprise Grid
    
- Symphony

    
- Thomson Reuters Eikon

    
- Thomson Reuters Messenger

    
- Thomson Reuters Dealings 3000 / FX Trading

    
- Twitter
    
- UBS 聊天

    
- YouTube
  
### <a name="opentext"></a>OpenText

[OpenText](https://www.opentext.com/what-we-do/products/opentext-product-offerings-catalog/rebranded-products/daegis)支持下列第三方数据源： 
  
- Axs Encrypted
    
- Axs Exchange
    
- Axs 本地存档
    
- Axs PlaceHolder
    
- Axs Signed
    
- Bloomberg
    
- Thomson Reuters
  
### <a name="verba"></a>Verba

[Verba](https://www.verba.com)支持下列第三方数据源： 
  
- Avaya Aura 视频

    
- Avaya Aura 语音

    
- Avtec 调频广播

    
- Bosch/Telex 调频广播

    
- BroadSoft 视频

    
- BroadSoft 语音

    
- Centile 语音

    
- Cisco Jabber 即时消息

    
- Cisco UC 视频

    
- Cisco UC 语音

    
- Cisco UCCX/UCCE 视频
    
- Cisco UCCX/UCCE 语音
    
- ESChat 调频广播
    
- Geoman 联络专家
    
- IP Trade 语音

    
- Luware LUCS 联络中心
    
- Microsoft UC（统一通信）
    
- 适用于 Lync 的 Mitel MiContact 中心 (prairieFyre) 

    
- Oracle / Acme 数据包会话边界控制器视频  

    
- Oracle / Acme 数据包会话边界控制器语音

    
- Singtel Mobile 语音

    
- SIPREC 视频
    
-  SIPREC 语音 
    
- Skype for Business/Lync 即时消息

    
- Skype for Business/Lync 视频

    
- Skype for Business/Lync 语音

    
- Speakerbus 语音

    
- 标准 SIP/H.323 视频 

    
- 标准 SIP/H.323 语音 

    
- Truphone 语音

    
- TwistedPair 调频广播

    
- Windows 桌面计算机屏幕 

  
## <a name="step-2-create-and-configure-a-third-party-data-mailbox-in-office-365"></a>步骤 2：在 Office 365 中创建和配置第三方数据邮箱

下面是用于创建和配置数据导入到 Office 365 的第三方数据邮箱的步骤。与以前所述，项目被导入到此邮箱的合作伙伴连接器无法将该项目的用户 ID 映射到 Office 365 用户帐户。
  
 **完成这些任务在 Office 365 管理中心**
  
1. 在 Office 365 中创建新的用户帐户，并将其分配的 Exchange Online 计划 2 许可证;请参阅[添加到 Office 365 的用户](https://go.microsoft.com/fwlink/p/?LinkId=692098)。计划 2 许可证需要将置于诉讼保留状态的邮箱或启用存档邮箱的具有不受限制的存储配额。
    
2. 第三方数据邮箱的用户帐户添加到 Office 365; 中的**Exchange 管理员**管理角色请参阅[Office 365 中的管理角色分配](https://go.microsoft.com/fwlink/p/?LinkId=532393)。
    
    > [!TIP]
    > 写下此用户帐户的凭据。您需要将它们提供给您的合作伙伴，如步骤 4 中所述。 
  
 **完成这些任务在 Exchange 管理中心**
  
1. 第三方数据中隐藏邮箱通讯簿和您的组织; 在其他地址列表请参阅[管理用户邮箱](https://go.microsoft.com/fwlink/p/?LinkId=616058)。此外，还可以运行以下 PowerShell 命令：
    
    ```
    Set-Mailbox -Identity <identity of third-party data mailbox> -HiddenFromAddressListsEnabled $true
    ```

2. 分配给第三方数据邮箱的**FullAccess**权限，以便管理员或合规部主管可以在 Outlook 桌面客户端，则打开第三方数据邮箱请参阅[Manage permissions for 收件人](https://go.microsoft.com/fwlink/p/?LinkId=692104)。
    
3. 启用了以下合规性相关 Office 365 功能的第三方数据邮箱：
    
    - 启用存档邮箱中;请参阅[Office 365 安全性启用存档邮箱&amp;合规性中心](enable-archive-mailboxes.md)和[启用 Office 365 中的无限制存档](enable-unlimited-archiving.md)。这会让您通过设置将第三方数据项目移动到存档邮箱的存档策略的主邮箱中释放存储空间。这将为您提供不受限制的存储的第三方数据。
    
    - 将置于诉讼保留状态的第三方数据邮箱。您还可以应用 Office 365 安全性的 Office 365 保留策略&amp;合规性中心。保持发出此邮箱将保留第三方数据项目 （无限期或指定的持续时间），并防止它们从邮箱被清除。请参阅以下主题之一：
    
      - [将邮箱置于诉讼保留状态](https://go.microsoft.com/fwlink/p/?LinkId=404420)
    
      - [Office 365 中的保留策略概述](retention-policies.md)
    
       
    
    - 启用邮箱审核日志记录所有者、 委派和管理访问的第三方数据邮箱;请参阅[启用邮箱审核 Office 365 中](enable-mailbox-auditing.md)。这将使您能够审核执行的任何用户都有权访问的第三方数据邮箱的所有活动。

## <a name="step-3-configure-user-mailboxes-for-third-party-data"></a>步骤 3：为第三方数据配置用户邮箱

下一步是配置用户邮箱以支持第三方数据。使用 Exchange 管理中心或使用相应的 Windows PowerShell cmdlet，请完成这些任务。
  
1. 启用存档邮箱的每个用户;请参阅[Office 365 安全性启用存档邮箱&amp;合规性中心](enable-archive-mailboxes.md)和[启用 Office 365 中的无限制存档](enable-unlimited-archiving.md)。
    
2. 将用户邮箱置于诉讼保留或应用 Office 365 的保留策略。请参阅以下主题之一： 
    
    - [将邮箱置于诉讼保留状态](https://go.microsoft.com/fwlink/p/?LinkId=404420)
    
    - [Office 365 中的保留策略概述](retention-policies.md)
    
    如前所述，在将邮箱置于保留时，您可以设置保留第三方数据源中项目的时长，或者也可以选择无限期保留这些项目。

## <a name="step-4-provide-your-partner-with-information"></a>步骤 4：为合作伙伴提供信息

最后一步是为您的合作伙伴提供以下信息，这样他们便能够配置连接器以连接到 Office 365 组织，从而将数据导入到用户邮箱和第三方数据邮箱。 
  
- 终结点用于连接到 Office 365 中的 Azure 服务：

    ```
    https://office365ingestionsvc.gble1.protection.outlook.com/service/ThirdPartyIngestionService.svc
    ```

- 您在步骤 2 中创建的第三方数据邮箱 （Office 365 用户 ID 和密码） 凭据登录。这些凭据是必需，以便合作伙伴连接器可以访问和项目导入到用户邮箱和第三方数据邮箱。
 
## <a name="step-5-register-the-third-party-data-connector-in-azure-active-directory"></a>步骤 5： 在 Azure Active Directory 中注册第三方数据连接器

Office 365 中的 Azure 服务启动年 9 月 30 2018年将开始使用现代身份验证在 Exchange Online 进行身份验证尝试连接到 Office 365 组织导入数据的第三方数据连接器。此更改的原因是身份验证的现代提供更多安全比当前方法，基于前面所述的终结点用于连接到 Azure 服务添加到白名单第三方连接器。

若要启用第三方数据连接器以连接到 Office 365 使用的新的现代身份验证方法，您的 Office 365 组织中的管理员必须同意以作为受信任的服务应用程序在 Azure Active Directory 中注册连接器。这是接受权限请求以允许访问您组织的 Azure Active Directory 中的数据的连接器。接受此请求后，第三方数据连接器是添加为 Azure Active Directory 的企业应用程序，表示为服务主体。同意过程的详细信息，请参阅[Consent 租户管理员](https://docs.microsoft.com/en-us/skype-sdk/trusted-application-api/docs/tenantadminconsent)。

下面是访问并接受请求将连接器注册的步骤：

1. 转到[此页](https://login.microsoftonline.com/common/oauth2/authorize?client_id=8dfbc50b-2111-4d03-9b4d-dd0d00aae7a2&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent)并使用的 Office 365 全局管理员凭据登录。<br/><br/>下面的对话框中显示。您可以展开插入符号以查看将分配给连接器的权限。<br/><br/>![显示权限请求对话框](media/O365_ThirdPartyDataConnector_OptIn1.png)
2. 单击**接受**。

接受请求后，将显示在[Azure 门户](https://portal.azure.com)。若要查看为您的组织的应用程序的列表，请单击**Azure Active Directory** > **企业应用程序**。**企业应用程序**刀片上列出 Office 365 第三方数据连接器。

> [!IMPORTANT]
> 年 9 月 30 2018年后第三方将不再将数据导入您的组织中的邮箱如果不在 Azure Active Directory 中注册的第三方数据连接器。步骤 5 中的过程在 Azure Active Directory 中必须还进行注册现有第三方数据连接器 （那些之前 2018 年 9 月 30，创建） 的说明。

### <a name="revoking-consent-for-a-third-party-data-connector"></a>撤消第三方数据连接器的同意

您的组织同意在 Azure Active Directory 中注册的第三方数据连接器的权限请求后，您的组织可以取消随时的许可。但是，撤消连接器同意将意味着第三方数据源中的数据不再将导入 Office 365。

要取消的第三方数据连接器的同意，您可以删除应用程序 （通过删除相应的服务主体） 使用**企业应用程序**刀片，在 Azure 门户中，或通过使用[的 Azure Active Directory删除 MsolServicePrincipal](https://docs.microsoft.com/en-us/powershell/module/msonline/remove-msolserviceprincipal) Office 365 PowerShell 中。您还可以使用 Azure Active Directory PowerShell 中[删除 AzureADServicePrincipal](https://docs.microsoft.com/en-us/powershell/module/azuread/remove-azureadserviceprincipal) cmdlet。
  
## <a name="more-information"></a>更多信息

- 与以前所述，从第三方数据源导入到 Exchange 邮箱作为电子邮件项目。合作伙伴连接器导入使用所需的 Office 365 API 的架构的项。下表说明了第三方数据源中的项目的邮件属性后导入到 Exchange 邮箱作为电子邮件。表还指示是否强制 message 属性。必须填充必需的属性。如果项目缺少必需属性，它不会导入到 Office 365。导入过程将返回解释原因项目未导入和哪个属性是缺少一条错误消息。
    
    |**邮件属性**|**必需？**|**说明**|**示例值**|
    |:-----|:-----|:-----|:-----|
    |**发件人** <br/> |是  <br/> |最初创建或发送第三方数据源中的项目的用户。合作伙伴连接器会尝试将从源项 （例如 Twitter 句柄） 到 Office 365 用户帐户的用户 ID 映射所有参与者 （从和收件人字段中的用户）。邮件的副本将导入到每个参与者的邮箱中。如果无项中的参与者可以映射到 Office 365 用户帐户，该项目将导入到 Office 365 中的第三方存档邮箱。<br/> <br/> 标识项目的发件人为参与者必须具有项目正在导入到 Office 365 组织中的活动邮箱。如果发件人没有活动邮箱，则返回以下错误：<br/><br/>  `One or more messages in the Request failed to be delivered to either From or Sender email address. You will need to resend your entire Request. Error: The request failed. The remote server returned an error: (401) Unauthorized.`  | `bob@contoso.com` <br/> |
    |**收件人** <br/> |是  <br/> |接收项目的用户（如果适用于数据源中的项目）。  <br/> | `bob@contoso.com` <br/> |
    |**主题** <br/> |否  <br/> |源项目中的主题。  <br/> | `"Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/> |
    |**日期** <br/> |是  <br/> |最初在客户数据源中创建或发布项目的日期；例如，发布 Twitter 消息的日期。  <br/> | `01 NOV 2015` <br/> |
    |**正文** <br/> |否  <br/> |Post 消息的内容。对于某些数据源，此属性的内容可能是**SUBJECT**属性的内容相同。在导入过程中，合作伙伴连接器将尝试维护尽可能的内容源的完全保真的。如果可能文件、 图形或其他内容源项目的正文包括在此属性。否则，从源项的内容包含在**附件**属性。此属性的内容将取决于合作伙伴连接器和源平台的功能。<br/> | `Author: bob@contoso.com` <br/>  `Date: 10 DEC 2014` <br/>  `Tweet: "Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/>  `Date: 01 NOV 2015` <br/> |
    |**附件** <br/> |否  <br/> |如果数据源 （如 Twitter 或即时消息对话中 tweet) 中的项都有一个附加的文件，或包含图像，合作伙伴连接将第一次尝试在**BODY**属性中包含附件。如果这不是可能的则会添加到 * * 附件 * * 属性。附件的其他示例包括顶帖 Facebook，从内容源和答复邮件或文章的元数据中。<br/> | `image.gif` <br/> |
    |**邮件类** <br/> |是  <br/> | 这是一个多值属性，其中创建和填充合作伙伴连接器。此属性的格式为`IPM.NOTE.Source.Event`。(此属性必须以`IPM.NOTE`; 此格式是相似的`IPM.NOTE.X`邮件类。)此属性包括以下信息：<br/><br/>`Source`-指示第三方数据源;例如，Twitter、 Facebook 或 BlackBerry。  <br/> <br/>  `Event`-指示执行生成项，则在第三方数据源中的活动的类型例如，tweet Twitter 或的帖子中 Facebook 中。事件是特定于数据源。<br/> <br/>  此属性的一个用途是基于其中项目产生或基于事件的类型的数据源的特定项进行筛选。例如，在电子数据展示搜索中无法创建搜索查询来查找特定的用户发布的所有 tweets。<br/> | `IPM.NOTE.Twitter.Tweet` <br/> |
   
- 当项目被成功导入到 Office 365 中的邮箱中时，作为一部分的 HTTP 响应呼叫者回返回的唯一标识符。此标识符 — 调用`x-IngestionCorrelationID`— 可用于项目的端到端跟踪的伙伴后续疑难解答目的。建议合作伙伴捕获此信息，并相应地登录其末尾。下面是显示此标识符的 HTTP 响应示例：

    ```
    HTTP/1.1 200 OK
    Content-Type: text/xml; charset=utf-8
    Server: Microsoft-IIS/8.5
    x-IngestionCorrelationID: 1ec7667d-f097-47fe-a9a2-bc7ab0a7552b
    X-AspNet-Version: 4.0.30319
    X-Powered-By: ASP.NET
    Date: Tue, 02 Feb 2016 22:55:33 GMT 
    ```
 
- 您可以在 Office 365 安全性使用内容搜索工具&amp;合规性中心搜索已导入到 Office 365 中的邮箱从第三方数据源的项目。若要搜索专门针对这些导入的项，可以在内容搜索关键字框中使用以下邮件属性值对。. 
    
  - **`kind:externaldata`**-使用此属性值对搜索所有第三方数据类型。例如，若要搜索已从第三方数据源导入和导入项目的 Subject 属性中包含的单词"contoso"的项目，需要使用关键字查询`kind:externaldata AND subject:contoso`。
    
  - **`itemclass:ipm.externaldata.<third-party data type>`**-使用此属性值对仅查找指定的第三方数据类型。例如，若要仅搜索包含单词"contoso"的使用者属性中的 Facebook 数据，需要使用关键字查询`itemclass:ipm.externaldata.Facebook* AND subject:contoso`。 

  有关要使用第三方数据类型的值的完整列表`itemclass`属性，请参阅[使用内容搜索第三方数据的已导入到 Office 365](use-content-search-to-search-third-party-data-that-was-imported.md)
    
   有关如何使用内容搜索以及创建关键字搜索查询的详细信息，请参阅：
    
  - [Office 365 中的内容搜索](content-search.md)
    
  - [内容搜索的关键字查询和搜索条件](keyword-queries-and-search-conditions.md)
 
