---
title: 与合作伙伴合作, 以在 Office 365 中存档第三方数据
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
description: 您的组织可以与 Microsoft 合作伙伴合作, 设置自定义连接器, 以便从数据源 (如 Salesforce Chatter、Yahoo Messenger 或 Yammer) 导入第三方数据。 这使您可以在 office 365 中存档第三方数据源中的数据, 以便您可以使用 office 365 合规性功能 (如合法保留、内容搜索和保留策略) 来管理组织的第三方数据的管理。
ms.openlocfilehash: dce015438c9764f66e98936df9454cba73fd8472
ms.sourcegitcommit: 63a10dc5ffa9d709fac437d3fc9e554b1bcd826f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/25/2019
ms.locfileid: "33307764"
---
# <a name="work-with-a-partner-to-archive-third-party-data-in-office-365"></a>与合作伙伴合作, 以在 Office 365 中存档第三方数据

您可以与 Microsoft 合作伙伴合作, 将第三方数据源中的数据导入和存档到 Office 365。 合作伙伴可以为您提供一个自定义连接器, 该连接器被配置为从第三方数据源提取项目 (定期), 然后将这些项目导入到 Office 365。 合作伙伴连接器将项目的内容从数据源转换为电子邮件格式, 然后将这些项目存储在 Office 365 中的邮箱中。 导入第三方数据后, 可以将 Office 365 合规性功能 (如诉讼保留、内容搜索、就地存档、审核和 Office 365 保留策略) 应用于此类数据。
  
下面概述了使用 Microsoft 合作伙伴将第三方数据导入 Office 365 时所需的过程和步骤。

[Step 1: Find a third-party data partner](#step-1-find-a-third-party-data-partner)

[Step 2: Create and configure a third-party data mailbox in Office 365](#step-2-create-and-configure-a-third-party-data-mailbox-in-office-365)

[Step 3: Configure user mailboxes for third-party data](#step-3-configure-user-mailboxes-for-third-party-data)

[步骤 4：为合作伙伴提供信息](#step-4-provide-your-partner-with-information)

[步骤 5: 在 Azure Active Directory 中注册第三方数据连接器](#step-5-register-the-third-party-data-connector-in-azure-active-directory)

## <a name="how-the-third-party-data-import-process-works"></a>第三方数据导入过程的工作原理

下图和说明介绍了在使用合作伙伴时第三方数据导入过程的工作原理。
  
![第三方数据导入过程的工作原理](media/5d4cf8e9-b4cc-4547-90c8-d12d04a9f0e7.png)
  
1. 客户可以通过其选择的合作伙伴来配置将从第三方数据源提取项目的连接器, 然后将这些项目导入到 Office 365。
    
2. 合作伙伴连接器通过第三方 API (根据计划或已配置的原则) 连接到第三方数据源, 并从数据源中提取项目。 合作伙伴连接器将项目内容转换为电子邮件格式。 请参阅[More information](#more-information)部分，了解有关邮件格式架构的说明。 
    
3. 合作伙伴连接器通过已知终结点使用 Exchange Web 服务 (EWS) 连接到 Office 365 中的 Azure 服务。
    
4. 项目便导入到特定用户的邮箱或“catch-all”第三方数据邮箱。无论项目是导入到特定用户邮箱还是第三方数据邮箱，都要基于以下条件：
    
    a. **具有与 office 365 用户帐户对应的用户 id 的项目**-如果合作伙伴连接器可以将第三方数据源中项目的用户 id 映射到 office 365 中的特定用户 id, 则会将该项目复制到用户的 Rec 中的 "**清除**" 文件夹中。overable "项目" 文件夹。 用户无法访问“清除”文件夹中的项目。 不过, 您可以使用 Office 365 电子数据展示工具搜索 "清除" 文件夹中的项目。
    
    b. **没有与 office 365 用户帐户对应的用户 id 的项目**-如果合作伙伴连接器无法将项目的用户 id 映射到 office 365 中的特定用户 id, 则会将该项目复制到第三方数据邮箱的 **"收件箱**" 文件夹中。 将项目导入到收件箱允许您或组织中的其他人登录到第三方邮箱来查看和管理这些项目，并查看是否需要在合作伙伴连接器配置中进行任何调整。
 
## <a name="step-1-find-a-third-party-data-partner"></a>步骤 1：寻找第三方数据合作伙伴

在 office 365 中存档第三方数据的关键组件是查找和使用 Microsoft 合作伙伴, 该合作伙伴专门负责捕获第三方数据源中的数据, 并将其导入 Office 365。 导入数据后, 可以对其进行存档和保留, 以及组织的其他 Microsoft 数据 (例如来自 SharePoint 和 OneDrive for business 的 Exchange 和文档的电子邮件)。 合作伙伴创建从组织的第三方数据源 (如 BlackBerry、Facebook、Google +、Thomson Reuters、Twitter 和 YouTube) 提取数据的连接器, 并将该数据传递给将项目导入 Exchange 邮箱的 Office 365 API电子邮件。 
  
以下各节列出了 Microsoft 合作伙伴 (以及他们支持的第三方数据源), 他们参与了在 Office 365 中存档第三方数据的计划。

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
    
- MessageLabs 数据流
    
- OpenText
    
- Oracle/ATG“单击以呼叫”Live 帮助
    
- Pivot IMTRADER
    
- Microsoft SharePoint
    
- MindAlign
    
- Sitrion One (Newsgator)
    
- Skype for Business (Lync/OCS)
    
- Skype for Business Online (Lync Online)
    
- SQL 数据库
    
- Squawker
    
- Thomson Reuters Eikon Messenger
  
### <a name="actiance"></a>Actiance

[Actiance](https://www.actiance.com)支持以下第三方数据源: 
  
- 对准
    
- American Idol
    
- Apple Juice
    
- 使用 Pivot 客户端的 AOL
    
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
    
- Cisco IM &amp;状态服务器 (v 9.0.1、9.1、v 9.1.1 SU1、v10、v v10.5.1 SU1)
    
- Cisco Unified Presence 服务器（v8.6.3、v8.6.4、v8.6.5）
    
- 协作导入
    
- 协作实时日志记录
    
- Direct Connect
    
- Facebook
    
- FactSet
    
- FastTrack
    
- Gnutella
    
- Google +
    
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
    
- 领英
    
- Microsoft Lync（2010、2013）
    
- MFTP
    
- Microsoft Lync 2013 语音
    
- Microsoft SharePoint（2010、2013）
    
- Microsoft SharePoint Online
    
- Microsoft UC（统一通信）
    
- MindAlign
    
- Mobile Guard
    
- 直接
    
- My Space
    
- NEONetwork
    
- Office 365 Lync 专用
    
- Office 365 共享即时消息
    
- Pinterest
    
- 透视
    
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

[ArchiveSocial](https://www.archivesocial.com)支持以下第三方数据源: 
  
- Facebook
    
- Flickr
    
- Instagram
    
- 领英
    
- Pinterest
    
- Twitter
    
- YouTube
    
- Vimeo
  
### <a name="globanet"></a>Globanet

[Globanet](https://www.globanet.com)支持以下第三方数据源: 
  
- 使用 Pivot 客户端的 AOL 
    
- BlackBerry 呼叫日志（v5、v10、v12）
    
- BlackBerry Messenger（v5、v10、v12）
    
- BlackBerry PIN（v5、v10、v12）
    
- BlackBerry 短信（v5、v10、v12）
    
- Bloomberg 聊天
    
- Bloomberg 邮件
    
- Box
    
- 适用于 Salesforce Chatter 的 CipherCloud
    
- Cisco IM &amp;状态服务器 (v10, v v10.5.1 SU1, app-v 11.0, v 11.5 SU2)

- Cisco Webex 团队

- Citrix 工作&amp;区 ShareFile

- CrowdCompass

- 自定义带分隔符的文本文件
    
- 自定义 XML 文件
    
- Facebook (页面)
    
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
    
- 透视
    
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

[OpenText](https://www.opentext.com/what-we-do/products/opentext-product-offerings-catalog/rebranded-products/daegis)支持以下第三方数据源: 
  
- Axs Encrypted
    
- Axs Exchange
    
- Axs 本地存档
    
- Axs PlaceHolder
    
- Axs Signed
    
- Bloomberg
    
- Thomson Reuters
  
### <a name="verba"></a>Verba

[Verba](https://www.verba.com)支持以下第三方数据源: 
  
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

以下是创建和配置将数据导入到 Office 365 的第三方数据邮箱的步骤。 如前所述, 如果合作伙伴连接器无法将项目的用户 ID 映射到 Office 365 用户帐户, 则会将项目导入此邮箱。
  
 **在 Microsoft 365 管理中心完成这些任务**
  
1. 在 Office 365 中创建一个新的用户帐户, 并为其分配 Exchange Online 计划2许可证;请参阅[向 Office 365 添加用户](https://go.microsoft.com/fwlink/p/?LinkId=692098)。 需要 Plan 2 许可证将邮箱置于诉讼保留状态, 或启用具有无限存储配额的存档邮箱。
    
2. 将第三方数据邮箱的用户帐户添加到 Office 365 中的**Exchange 管理员**管理员角色中;请参阅[在 Office 365 中分配管理员角色](https://go.microsoft.com/fwlink/p/?LinkId=532393)。
    
    > [!TIP]
    > 写下此用户帐户的凭据。 您需要将它们提供给您的合作伙伴，如步骤 4 中所述。 
  
 **在 Exchange 管理中心中完成这些任务**
  
1. 从通讯簿和组织中的其他地址列表中隐藏第三方数据邮箱;请参阅[管理用户邮箱](https://go.microsoft.com/fwlink/p/?LinkId=616058)。 或者，可以运行以下 PowerShell 命令：
    
    ```
    Set-Mailbox -Identity <identity of third-party data mailbox> -HiddenFromAddressListsEnabled $true
    ```

2. 为第三方数据邮箱分配**FullAccess**权限, 以便管理员或合规专员可以在 Outlook 桌面客户端中打开第三方数据邮箱;请参阅[管理收件人的权限](https://go.microsoft.com/fwlink/p/?LinkId=692104)。
    
3. 为第三方数据邮箱启用以下与合规性相关的 Office 365 功能:
    
    - 启用存档邮箱;请参阅[启用存档邮箱](enable-archive-mailboxes.md)和[启用无限制存档](enable-unlimited-archiving.md)。 这将允许您通过设置将第三方数据项移动到存档邮箱的存档策略来释放主邮箱中的存储空间。 这将为第三方数据提供无限存储空间。
    
    - 将第三方数据邮箱置于诉讼保留的位置。 您还可以在安全与合规中心中应用 Office 365 保留策略。 将此邮箱置于保留状态时, 将保留第三方数据项 (无限期或指定的持续时间), 并防止从邮箱中清除这些项目。 请参阅下列主题之一:
    
      - [将邮箱置于诉讼保留状态](https://go.microsoft.com/fwlink/p/?LinkId=404420)
    
      - [Office 365 中的保留策略概述](retention-policies.md)
    
       
    
    - 对访问第三方数据邮箱的所有者、委派用户和管理员启用邮箱审核日志记录；请参阅[Enable mailbox auditing in Office 365](enable-mailbox-auditing.md)。 这将允许您审核有权访问第三方数据邮箱的任何用户执行的所有活动。

## <a name="step-3-configure-user-mailboxes-for-third-party-data"></a>步骤 3：为第三方数据配置用户邮箱

下一步是配置用户邮箱以支持第三方数据。 通过使用 Exchange 管理中心或使用相应的 Windows PowerShell cmdlet 完成这些任务。
  
1. 为每个用户启用存档邮箱;请参阅[启用存档邮箱](enable-archive-mailboxes.md)和[启用无限制存档](enable-unlimited-archiving.md)。
    
2. 将用户邮箱置于诉讼保留或应用 Office 365 保留策略;请参阅下列主题之一: 
    
    - [将邮箱置于诉讼保留状态](https://go.microsoft.com/fwlink/p/?LinkId=404420)
    
    - [Office 365 中的保留策略概述](retention-policies.md)
    
    如前所述，在将邮箱置于保留时，您可以设置保留第三方数据源中项目的时长，或者也可以选择无限期保留这些项目。

## <a name="step-4-provide-your-partner-with-information"></a>步骤 4：为合作伙伴提供信息

最后一步是为您的合作伙伴提供以下信息，这样他们便能够配置连接器以连接到 Office 365 组织，从而将数据导入到用户邮箱和第三方数据邮箱。 
  
- 用于连接到 Office 365 中的 Azure 服务的终结点:

    ```
    https://office365ingestionsvc.gble1.protection.outlook.com/service/ThirdPartyIngestionService.svc
    ```

- 您在步骤2中创建的第三方数据邮箱的登录凭据 (Office 365 用户 ID 和密码)。 这些凭据是必需的，以便合作伙伴连接器可以访问并将项目导入用户邮箱和第三方数据邮箱。
 
## <a name="step-5-register-the-third-party-data-connector-in-azure-active-directory"></a>步骤 5: 在 Azure Active Directory 中注册第三方数据连接器

从2018年9月30日起, Office 365 中的 Azure 服务将开始使用 Exchange Online 中的新式验证来验证尝试连接到 Office 365 组织的第三方数据连接器以导入数据。 此更改的原因是新式验证提供的安全性高于当前方法, 后者基于使用前面所述的终结点连接到 Azure 服务的白名单第三方连接器。

若要使第三方数据连接器能够使用新式新式身份验证方法连接到 Office 365, Office 365 组织中的管理员必须同意在 Azure Active Directory 中将连接器注册为受信任的服务应用程序。 这是通过接受允许连接器在 Azure Active Directory 中访问组织数据的权限请求来实现的。 接受此请求后, 第三方数据连接器将作为企业应用程序添加到 Azure Active Directory, 并表示为服务主体。 有关许可过程的详细信息, 请参阅[租户管理员同意](https://docs.microsoft.com/en-us/skype-sdk/trusted-application-api/docs/tenantadminconsent)。

以下是访问和接受注册连接器的请求的步骤:

1. 转到[此页](https://login.microsoftonline.com/common/oauth2/authorize?client_id=8dfbc50b-2111-4d03-9b4d-dd0d00aae7a2&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent), 并使用 Office 365 全局管理员的凭据登录。<br/><br/>将显示以下对话框。 您可以展开 carets 以查看将分配给连接器的权限。<br/><br/>![将显示 "权限请求" 对话框](media/O365_ThirdPartyDataConnector_OptIn1.png)
2. 单击“Accept”****。

接受请求后, 将显示[Azure 门户](https://portal.azure.com)。 若要查看您的组织的应用程序列表, 请单击 " **Azure Active Directory** > **企业应用程序**"。 **企业应用程序**边栏上列出了 Office 365 第三方数据连接器。

> [!IMPORTANT]
> 在2018年9月30日之后, 如果未在 Azure Active Directory 中注册第三方数据连接器, 则将不再将第三方数据导入组织中的邮箱。 注释现有的第三方数据连接器 (在9月30日之前创建的数据连接器) 还必须在 Azure Active Directory 中进行注册, 具体步骤是执行步骤5中的过程。

### <a name="revoking-consent-for-a-third-party-data-connector"></a>撤销第三方数据连接器的同意

在您的组织同意要在 Azure Active Directory 中注册第三方数据连接器的权限请求后, 您的组织可以随时撤销该许可。 但是, 如果吊销连接器的许可, 则将不再将第三方数据源中的数据导入到 Office 365 中。

若要撤销第三方数据连接器的同意, 可以使用 azure 门户中的 "**企业应用程序**" 边栏从 azure Active Directory 中删除应用程序 (通过删除相应的服务主体), 或使用[new-msolserviceprincipal](https://docs.microsoft.com/en-us/powershell/module/msonline/remove-msolserviceprincipal)在 Office 365 PowerShell 中删除。 您还可以在 Azure Active Directory PowerShell 中使用[AzureADServicePrincipal](https://docs.microsoft.com/en-us/powershell/module/azuread/remove-azureadserviceprincipal) cmdlet。
  
## <a name="more-information"></a>更多信息

- 如前所述，第三方数据源中的项目将作为电子邮件导入到 Exchange 邮箱。 合作伙伴连接器使用 Office 365 API 所需的架构导入项目。 下表介绍了第三方数据源中的项目作为电子邮件导入到 Exchange 邮箱之后的邮件属性。 该表还指出该邮件属性是否是强制属性。 必须填充强制属性。 如果某项缺少强制属性, 则不会将其导入 Office 365。 导入过程将返回一条错误消息，解释未导入项目的原因以及缺少了哪些属性。
    
    |**邮件属性**|**强制？**|**说明**|**示例值**|
    |:-----|:-----|:-----|:-----|
    |**FROM** <br/> |是  <br/> |最初创建或发送第三方数据源中的项目的用户。 合作伙伴连接器将尝试将源项目 (例如 Twitter 句柄) 中的用户 ID 映射到所有参与者 ("from" 和 "to" 字段中的用户) 的 Office 365 用户帐户。 邮件的副本将导入到每个参与者的邮箱中。 如果无法将项目中的任何参与者映射到 office 365 用户帐户, 则会将该项目导入 office 365 中的第三方存档邮箱。  <br/> <br/> 标识为项目的发件人的参与者必须在要向其导入项目的 Office 365 组织中具有活动邮箱。 如果发件人没有活动邮箱，则会返回以下错误：<br/><br/>  `One or more messages in the Request failed to be delivered to either From or Sender email address. You will need to resend your entire Request. Error: The request failed. The remote server returned an error: (401) Unauthorized.`  | `bob@contoso.com` <br/> |
    |**TO** <br/> |是  <br/> |接收项目的用户（如果适用于数据源中的项目）。  <br/> | `bob@contoso.com` <br/> |
    |**主题** <br/> |否  <br/> |源项目中的主题。  <br/> | `"Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/> |
    |**结束** <br/> |是  <br/> |最初在客户数据源中创建或发布项目的日期；例如，发布 Twitter 消息的日期。  <br/> | `01 NOV 2015` <br/> |
    |**大量** <br/> |否  <br/> |消息或帖子的内容。 对于某些数据源，此属性的内容可能与****“主题”属性的内容相同。 在导入过程中，合作伙伴连接器将尝试尽可能维护内容源的完全保真度。 如果可能，源项目正文中的文件、图形或其他内容会包含在此属性中。 否则，源项目中的内容会包含在****“附件”属性中。 此属性的内容将取决于合作伙伴连接器和源平台的功能。  <br/> | `Author: bob@contoso.com` <br/>  `Date: 10 DEC 2014` <br/>  `Tweet: "Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/>  `Date: 01 NOV 2015` <br/> |
    |**附着** <br/> |否  <br/> |如果数据源中的项 (如 Twitter 或即时消息对话中的 twitter) 具有附加的文件或包含图像, 则合作伙伴连接将首先尝试在**BODY**属性中包含附件。 如果无法这样做, 则会将其添加到 * * 附件 * * 属性中。 其他附件示例包括 Facebook 中的点赞，内容源中的元数据，以及对消息或帖子的回复。  <br/> | `image.gif` <br/> |
    |**MESSAGECLASS** <br/> |是  <br/> | 这是一个多值属性，由合作伙伴连接器创建和填充。 此属性的格式为`IPM.NOTE.Source.Event`。 (此属性必须以开头`IPM.NOTE`; 这种格式类似于`IPM.NOTE.X`消息类的格式。)此属性包含以下信息:  <br/><br/>`Source`-指示第三方数据源;例如, Twitter、Facebook 或 BlackBerry。  <br/> <br/>  `Event`-指示在生成项目的第三方数据源中执行的活动类型。例如, 在 Twitter 中的 twitter 或 Facebook 中的帖子。 事件是特定于数据源的。  <br/> <br/>  此属性的一个目的是基于项目源自的数据源或基于事件类型筛选特定项目。 例如，在电子数据展示搜索中，您可以创建一个搜索查询来查找特定用户发布的所有微博。  <br/> | `IPM.NOTE.Twitter.Tweet` <br/> |
   
- 将项目成功导入 Office 365 中的邮箱时, 会将唯一标识符作为 HTTP 响应的一部分返回给调用方。 此标识符 (称为`x-IngestionCorrelationID`) 可用于合作伙伴对项目进行端到端跟踪的后续故障排除目的。 建议合作伙伴捕获此信息，并在他们的所在端相应地记录此信息。 下面是显示此标识符的 HTTP 响应的示例：

    ```
    HTTP/1.1 200 OK
    Content-Type: text/xml; charset=utf-8
    Server: Microsoft-IIS/8.5
    x-IngestionCorrelationID: 1ec7667d-f097-47fe-a9a2-bc7ab0a7552b
    X-AspNet-Version: 4.0.30319
    X-Powered-By: ASP.NET
    Date: Tue, 02 Feb 2016 22:55:33 GMT 
    ```
 
- 您可以使用安全与合规中心中的内容搜索工具来搜索从第三方数据源导入到 Office 365 中的邮箱的项目。 若要专门搜索这些导入项, 可以在内容搜索的关键字框中使用以下消息属性-值对。
    
  - **`kind:externaldata`**-使用此属性-值对可搜索所有第三方数据类型。 例如, 若要搜索从第三方数据源导入, 并在导入项目的 Subject 属性中包含 "contoso" 一词的项目, 请使用关键字查询`kind:externaldata AND subject:contoso`。
    
  - **`itemclass:ipm.externaldata.<third-party data type>`**-使用此属性-值对仅搜索第三方数据的指定类型。 例如, 若要在 Subject 属性中仅搜索包含 "contoso" 一词的 Facebook 数据, 则应使用关键字查询`itemclass:ipm.externaldata.Facebook* AND subject:contoso`。 

  有关用于`itemclass`属性的第三方数据类型的值的完整列表, 请参阅[使用内容搜索来搜索导入到 Office 365 的第三方数据](use-content-search-to-search-third-party-data-that-was-imported.md)
    
   有关如何使用内容搜索以及创建关键字搜索查询的详细信息，请参阅：
    
  - [Office 365 中的内容搜索](content-search.md)
    
  - [内容搜索的关键字查询和搜索条件](keyword-queries-and-search-conditions.md)
 
