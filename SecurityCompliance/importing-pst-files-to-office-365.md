---
title: Overview of importing your organization PST files to Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: overview
f1_keywords:
- ms.o365.cc.IngestionHelp
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid: MET150
ms.assetid: ba688e0a-0fcb-4bd7-8e57-2b669564ea84
description: '对于管理员: 了解如何使用 Office 365 安全&amp;合规中心中的 "导入服务" 将电子邮件数据 (PST 文件) 批量导入 Exchange Online 中的用户邮箱。本主题提供 faq 并说明 PST 导入过程的工作原理。'
ms.openlocfilehash: 89aa1a351d0a9bcc70819f4b2657d04adc7599e2
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/26/2019
ms.locfileid: "30296775"
---
# <a name="overview-of-importing-your-organization-pst-files-to-office-365"></a>Overview of importing your organization PST files to Office 365

> [!NOTE]
> 本文适用于管理员。您是否尝试将 PST 文件导入到自己的邮箱？请参阅[从 Outlook .pst 文件导入电子邮件、联系人和日历](https://go.microsoft.com/fwlink/p/?LinkID=785075)

您可以使用 office 365 安全&amp;合规中心中的导入服务将 PST 文件快速批量导入到 Office 365 组织中的 Exchange Online 邮箱。可通过以下两种方法将 PST 文件导入到 Office 365:
   
- **网络上传**![云上](media/54ab16ee-3822-4551-abef-3d926f4e1c01.png)传-将 PST 文件通过网络上传到 Microsoft 云中的临时 Azure 存储位置。然后, 使用 office 365 导入服务将 PST 数据导入 office 365 组织中的邮箱。 

- **驱动器运送**![硬盘](media/e72b76f3-1f73-4296-b749-c325d95d9ef6.png) -将 PST 文件复制到 BitLocker 加密的硬驱, 然后将该驱动器物理传送到 Microsoft。当 microsoft 收到硬盘时, 数据中心人员将数据上载到 Microsoft 云中的临时 Azure 存储位置。然后, 使用 office 365 导入服务将数据导入到 Office 365 组织中的邮箱。

## <a name="step-by-step-instructions"></a>分步说明
  
有关将组织的 PST 文件批量导入 Office 365 的详细分步说明, 请参阅以下主题之一。 
   
- [使用网络上载将 PST 文件导入到 Office 365](use-network-upload-to-import-pst-files.md)
- [使用驱动器寄送，将 PST 文件导入到 Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md)

## <a name="how-importing-pst-files-works"></a>导入 PST 文件的工作原理

以下是完整的 PST 导入过程的图示和说明。该图显示了主工作流, 并突出显示了网络上载和驱动器传送方法之间的差异。
  
![PST 导入过程的工作流](media/76997b69-67d7-433a-a0ca-9389f85a36a1.png)
  
1. 将**pst 导入工具和密钥下载到专用 Azure 存储位置**-第一步是下载用于上载 PST 文件或将其复制到硬盘的工具和访问密钥。您可以从 Office 365 安全&amp;合规中心的 "**导入**" 页中获取它们。密钥为你 (或 Microsoft 数据中心人员) 提供将 PST 文件上传到专用和安全 Azure 存储位置所需的权限。此访问密钥对于您的组织是唯一的, 并且有助于防止在将 PST 文件上传到 Microsoft 云后对其进行未经授权的访问。请注意, 将 PST 文件导入到 Office 365 不需要您的组织拥有单独的 Azure 订阅。 
    
2. **上载或复制 PST 文件**-下一步取决于您使用的是网络上传或驱动器传送来导入 PST 文件。在这两种情况下, 都将使用在上一步中获得的工具和安全存储密钥。
    
    - **网络上传**AzCopy 工具 (在第1步中下载) 用于将 PST 文件上载并存储在 Microsoft 云中的 Azure 存储位置中。请注意, 您将 PST 文件上载到的 Azure 存储位置位于 Office 365 组织所在的相同区域 Microsoft 数据中心。 
    
      若要上传它们, 您要导入到 Office 365 的 PST 文件必须位于组织中的文件共享或文件服务器中。
    
    - **驱动器运送**waimportexport.exe 工具 (在第1步中下载) 用于将 PST 文件复制到硬盘驱动器。此工具使用 BitLocker 对硬盘进行加密, 然后将 pst 复制到硬盘驱动器。与网络上传一样, 要复制到硬盘驱动器的 PST 文件必须位于组织中的文件共享或文件服务器中。
    
3. **创建 pst 导入映射文件**-将 pst 文件上载到 Azure 存储位置或复制到硬盘之后, 下一步是创建一个逗号分隔值 (CSV) 文件, 该文件指定 PST 文件将导入到哪些用户邮箱 (可以将 PST 文件导入到用户的主邮箱或存档邮箱中。Office 365 导入服务将使用此信息导入 PST 文件。 
    
4. **创建 pst 导入作业**-下一步是在安全&amp;合规性中心的 "**导入**" 页上创建一个 pst 导入作业, 并提交在上一步中创建的 pst 导入映射文件。对于网络上载 (由于已将 pst 文件上传到 Azure), Office 365 将分析 pst 文件中的数据, 然后为您提供一个设置筛选器的机会, 该筛选器控制实际导入到 PST 导入映射文件中指定的邮箱的数据。 
    
    对于驱动器运输, 在此过程的这一时刻会发生一些其他事情。
    
    - 您将硬盘物理送到 microsoft 数据中心 (创建导入作业时, 将显示 microsoft 数据中心的送货地址)
    
    - 当 Microsoft 收到硬盘时, 数据中心人员会将硬盘驱动器上的 pst 文件上传到您的组织的 Azure 存储位置。如前所述, 将 PST 文件上传到驻留在 Office 365 组织所在的相同区域 Microsoft 数据中心的 Azure 存储位置。
    
      > [!NOTE]
      > 在 Microsoft 收到硬盘后, 硬盘上的 PST 文件将在7至10个工作日内上传到 Azure。 
  
      与网络上载过程一样, Office 365 将分析 PST 文件中的数据, 并使您有机会设置筛选器, 以控制实际导入到 PST 导入映射文件中指定的邮箱的数据。
    
    - Microsoft 将硬盘寄回给你。 
    
5. **筛选将导入到邮箱的 PST 数据**-在创建导入作业之后 (以及将驱动器发货作业中的 pst 文件上载到 Azure 存储位置后), Office 365 将分析 PST 文件中的数据 (安全和安全), 方法是标识 PST 文件中包含的项目的年龄和不同的邮件类型。分析完成并准备导入数据后, 可以选择导入 PST 文件中包含的所有数据, 也可以通过设置用于控制导入数据的筛选器来裁切导入的数据。 
    
6. **启动 pst 导入作业**-在开始导入作业后, Office 365 将使用 pst 导入映射文件中的信息将 pst 文件从其 Azure 存储位置导入到用户邮箱。有关导入作业的状态信息 (包括有关导入的每个 PST 文件的信息) 显示在安全&amp;合规性中心的 "**导入**" 页上。导入作业完成后, 会将作业的状态设置为 "**完成**"。
  
## <a name="why-import-email-data-to-office-365"></a>为什么要将电子邮件数据导入 Office 365？

- 将 PST 文件导入到用户邮箱是将组织的电子邮件迁移到 Office 365 的一种方法。
    
- 您可以使用[智能导入](filter-data-when-importing-pst-files.md)功能筛选出实际导入到目标邮箱的 PST 文件中的项目。这使您可以通过设置用于控制要导入哪些数据的筛选器来裁切导入的数据。 
    
- 将电子邮件数据导入到 Office 365 有助于满足您的组织的合规性需求, 具体方法是让您:
    
  - 启用[存档邮箱](enable-archive-mailboxes.md)和[无限制的存档](unlimited-archiving.md)以向用户提供额外的邮箱存储空间。 
    
  - 将邮箱置于[诉讼保留状态](https://go.microsoft.com/fwlink/?linkid=841243)以保留内容。 
    
  - 使用[内容搜索工具](content-search.md)搜索邮箱内容。 
    
  - 使用[电子数据展示事例](ediscovery-cases.md)管理您的组织的法律调查 
    
  - 使用安全&amp;合规中心中的[保留策略](retention-policies.md)控制邮箱内容保留的时间长度, 然后在保留期到期后删除内容。 
    
- 将数据导入到 Office 365 有助于防止数据丢失。导入到 Office 365 的电子邮件数据继承了 Exchange Online 的高可用性功能。
    
- Office 365 中的电子邮件数据可供所有设备中的用户使用, 因为它存储在云中。
    
## <a name="importing-sharepoint-data-to-office-365"></a>将 SharePoint 数据导入到 Office 365

您还可以将文件和文档导入 Office 365 组织中的 SharePoint 网站和 OneDrive 帐户。有关详细信息, 请参阅以下文章:

- [迁移到 SharePoint Online](https://docs.microsoft.com/sharepointmigration/migrate-to-sharepoint-online)

- [SharePoint 迁移工具简介](https://docs.microsoft.com/sharepointmigration/introducing-the-sharepoint-migration-tool)

- [使用 PowerShell 迁移到 SharePoint Online](https://docs.microsoft.com/sharepointmigration/overview-spmt-ps-cmdlets)

- [使用 Azure 数据框将文件共享内容迁移到 SharePoint Online](https://docs.microsoft.com/sharepointmigration/how-to-migrate-file-share-content-to-spo-using-azuredatabox)


## <a name="frequently-asked-questions-about-importing-pst-files-to-office-365"></a>将 PST 文件导入到 Office 365 的常见问题
  
下面是一些有关使用 office 365 导入服务批量导入 PST 文件到 office 365 邮箱的常见问题。 
  
- [使用网络上载导入 PST 文件](#using-network-upload-to-import-pst-files)
  
- [使用驱动器发货以导入 PST 文件](#using-drive-shipping-to-import-pst-files)
  
### <a name="using-network-upload-to-import-pst-files"></a>使用网络上载导入 PST 文件

 **在 Office 365 导入服务中创建导入作业所需的权限是什么？**
  
您必须在 Exchange Online 中分配 "邮箱导入导出" 角色, 才能将 PST 文件导入到 Office 365 邮箱。默认情况下, 此角色不会分配给 Exchange Online 中的任何角色组。您可以将邮箱导入导出角色添加到 "组织管理" 角色组。或者, 您可以创建新的角色组, 分配邮箱导入导出角色, 然后将自己或其他用户添加为成员。有关详细信息, 请参阅在[Exchange Online 中管理角色组](https://go.microsoft.com/fwlink/p/?LinkId=730688)中的 "将角色添加到角色组" 或 "创建角色组" 部分。
  
此外, 若要在 Office 365 安全&amp;合规中心中创建导入作业, 必须满足以下条件之一:
  
- 您必须在 Exchange Online 中向您分配 "邮件收件人" 角色。默认情况下, 将此角色分配给组织管理和收件人管理角色组。
    
    或者
    
- 您必须是 Office 365 组织中的全局管理员。
    
> [!TIP]
> 请考虑在 Exchange Online 中创建一个专门用于将 PST 文件导入到 Office 365 的新角色组。若要获取导入 PST 文件所需的最低级别权限, 请将 "邮箱导入导出" 和 "邮件收件人" 角色分配给新的角色组, 然后添加成员。 
  
 **网络上传的可用位置是什么？**
  
网络上传目前适用于美国、加拿大、巴西、英国、欧洲、印度、东亚、东南亚、日本、朝鲜共和国和澳大利亚。不久将在更多区域中提供网络上载。
  
 **使用网络上载导入 PST 文件的价格是多少？**
  
使用网络上传来导入 PST 文件是免费的。
  
这也意味着, 在从 Azure 存储区域中删除 PST 文件后, 这些文件将不再显示在 Office 365 管理中心中已完成导入作业的文件列表中。尽管导入作业可能仍在 "**导入数据到 Office 365** " 页上列出, 但在查看较旧的导入作业的详细信息时, PST 文件列表可能为空。 
  
 **导入 Office 365 支持哪种版本的 PST 文件格式？**
  
有两个版本的 PST 文件格式: ANSI 和 Unicode。建议导入使用 Unicode PST 文件格式的文件。但是, 使用 ANSI PST 文件格式的文件 (例如, 使用双字节字符集 (DBCS) 的语言的文件) 也可以导入到 Office 365。有关导入 ANSI PST 文件的详细信息, 请参阅 "[使用网络上载将 PST 文件导入到 Office 365](https://go.microsoft.com/fwlink/p/?LinkId=823074)" 中的步骤4。
  
此外, 还可以将 Outlook 2007 和更高版本中的 PST 文件导入到 Office 365。
  
 **将 PST 文件上传到 azure 存储区域后, 它们在被删除之前保留在 azure 中的时间是多少？**
  
使用网络上传方法导入 PST 文件时, 会将这些文件上传到名为**ingestiondata**的 Azure blob 容器中。如果安全&amp;合规中心中的 "**导入**" 页上没有正在进行的导入作业, 则在安全性**** &amp;合规性中心。这也意味着, 您必须在将 PST 文件上传到 Azure &amp;的30天内, 在安全合规中心 (在网络上载说明中的步骤5中介绍) 中创建新的导入作业。 
  
这也意味着在从 Azure 存储区域中删除 PST 文件后, 这些文件将不再显示在安全&amp;合规性中心中已完成导入作业的文件列表中。尽管安全&amp;合规中心中的**导入**页面仍可能会列出导入作业, 但在查看较旧的导入作业的详细信息时, PST 文件列表可能为空。 
  
 **将 PST 文件导入到邮箱需要多长时间？**
  
这取决于网络的容量, 但通常需要几个小时才能将每 tb 的数据上载到您的组织的 Azure 存储区域。将 pst 文件复制到 Azure 存储区域后, pst 文件将以每日至少 24 GB 的速度导入到 Office 365 邮箱中。如果此比率不能满足您的需求, 则可以考虑将电子邮件数据迁移到 Office 365 的其他方法。有关详细信息, 请参阅[将多个电子邮件帐户迁移到 Office 365 的方法](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842)。
  
如果将不同的 PST 文件导入到不同的目标邮箱, 则导入过程将并行发生;换言之, 每个 PST/邮箱对同时导入。同样, 如果将多个 PST 文件导入到同一个邮箱, 则会同时导入这些文件。
  
 **导入 PST 文件时是否有邮件大小限制？**
  
是的。如果 PST 文件包含大于 150 MB 的邮箱项目, 则在导入过程中将跳过该项目。
  
 **是邮件属性, 例如邮件的发送或接收时间、将 PST 文件导入到 Office 365 邮箱时所保留的收件人和其他属性的列表？**
  
是的。在导入过程中不会更改原始的邮件元数据。
  
 **对于要导入到邮箱中的 PST 文件, 文件夹层次结构中的级别数是否有限制？**
  
是的。您不能导入包含300或更多级别的嵌套文件夹的 PST 文件。
  
 **可以使用网络上载将 PST 文件导入到 Office 365 中的非活动邮箱吗？**
  
是的, 此功能现已推出。
  
 **是否可以使用网络上载将 PST 文件导入到 Exchange 混合部署中的联机存档邮箱？**
  
是的, 此功能现已推出。
  
 **是否可以使用网络上载将 PST 文件导入到 Exchange Online 中的公用文件夹？**
  
否, 不能将 PST 文件导入到公用文件夹。
  
### <a name="using-drive-shipping-to-import-pst-files"></a>使用驱动器发货以导入 PST 文件

 **在 Office 365 导入服务中创建导入作业所需的权限是什么？**
  
您必须分配有邮箱导入导出角色, 才能将 PST 文件导入到 Office 365 邮箱。默认情况下, 此角色不会分配给 Exchange Online 中的任何角色组。您可以将邮箱导入导出角色添加到 "组织管理" 角色组。或者, 您可以创建新的角色组, 分配邮箱导入导出角色, 然后将自己或其他用户添加为成员。有关详细信息, 请参阅在[Exchange Online 中管理角色组](https://go.microsoft.com/fwlink/p/?LinkId=730688)中的 "将角色添加到角色组" 或 "创建角色组" 部分。
  
此外, 若要在 Office 365 安全&amp;合规中心中创建导入作业, 必须满足以下条件之一:
  
- 您必须在 Exchange Online 中向您分配 "邮件收件人" 角色。默认情况下, 将此角色分配给组织管理和收件人管理角色组。
    
    或者
    
- 您必须是 Office 365 组织中的全局管理员。
    
> [!TIP]
> 请考虑在 Exchange Online 中创建一个专门用于将 PST 文件导入到 Office 365 的新角色组。若要获取导入 PST 文件所需的最低级别权限, 请将 "邮箱导入导出" 和 "邮件收件人" 角色分配给新的角色组, 然后添加成员。 
  
 **驱动器运输在什么位置？**
  
目前, 在美国、加拿大、巴西、英国、欧洲、印度、东亚、东南亚、日本、韩国和澳大利亚都可以使用驱动器运输。很快将在更多区域中提供驱动器运输。
  
 **哪些商业许可协议支持驱动器传送？**
  
将 PST 文件导入到 Office 365 的驱动器发货通过 Microsoft 企业协议 (EA) 提供。无法通过 Microsoft 产品和服务协议 (MPSA) 获取驱动器发货。
  
 **使用驱动器发货将 PST 文件导入到 Office 365 的定价是多少？**
  
使用驱动器传送将 PST 文件导入到 Office 365 邮箱的成本为每 GB 数据的 $2 美元。例如, 如果您提供的硬盘驱动器包含 1000 GB (1 TB) 的 PST 文件, 则开销为 $2000 USD。你可以与合作伙伴合作以支付进口费用。有关查找合作伙伴的信息, 请参阅[查找 Office 365 合作伙伴或经销商](https://go.microsoft.com/fwlink/p/?LinkId=785197)。
  
 **驱动器传送支持哪种类型的硬驱？**
  
仅2.5 英寸固态驱动器 (ssd) 或2.5 或3.5 英寸 SATA II/III 内置硬盘可与 Office 365 导入服务配合使用。可以使用最大 10 TB 的硬盘驱动器。对于导入作业, 仅会处理硬盘上的第一个数据量。必须使用 NTFS 格式化数据卷。将数据复制到硬盘时, 可以使用2.5 英寸 SSD 或2.5 或3.5 英寸 SATA ii/iii 连接器直接附加它, 也可以使用外部的2.5 英寸 ssd 或2.5 或3.5 英寸 sata ii/iii USB 适配器将其连接到外部。
  
> [!IMPORTANT]
> 内置 USB 适配器附带的外部硬盘驱动器不受 Office 365 导入服务的支持。此外, 不能使用外部硬盘驱动器大小写中的磁盘。请勿发售外部硬盘驱动器。 
  
 **我可以为一个导入作业发货多少个硬盘驱动器？**
  
最多可以为一个导入作业发货10个硬盘驱动器。
  
 **在我发货硬盘后, 获取 Microsoft 数据中心需要多长时间？**
  
这取决于一些事项, 如您与 Microsoft 数据中心的邻近程度, 以及您用于运输硬盘的运输选项类型 (例如, 下一天交付、两天交付或基础交付)。对于大多数运货商, 您可以使用跟踪号码来跟踪您的交货状态。
  
 **硬盘驱动器到达 Microsoft 数据中心后, 将 PST 文件上传到 Azure 需要多长时间？**
  
在 Microsoft 数据中心收到硬盘驱动器后, 需要7到10个工作日才能将 PST 文件上传到组织的 Microsoft Azure 存储区域。PST 文件将被上载到名为`ingestiondata`的 Azure blob 容器中。 
  
 **将 PST 文件导入到邮箱需要多长时间？**
  
将 pst 文件上传到 Azure 存储区域后, Office 365 将分析 pst 文件中的数据 (以安全和安全的方式), 以确定这些项目的年龄以及 pst 文件中包含的不同邮件类型。完成此分析后, 您可以选择导入 PST 文件中的所有数据, 也可以将筛选器设置为, 以控制导入的数据。在您开始导入作业后, PST 文件将以每日至少 24 GB 的速度导入到 Office 365 邮箱中。如果此比率不能满足您的需求, 则可以考虑将电子邮件数据导入到 Office 365 的其他方法。有关详细信息, 请参阅[将多个电子邮件帐户迁移到 Office 365 的方法](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842)。
  
如果将不同的 PST 文件导入到不同的目标邮箱, 则导入过程将并行发生;换言之, 每个 PST/邮箱对同时导入。同样, 如果将多个 PST 文件导入到同一个邮箱, 则会同时导入这些文件。
  
 **Microsoft 将我的 PST 文件上载到 azure 后, 它们在被删除之前在 azure 中保留的时间是多少？**
  
在安全&amp;合规中心的 "**导入**" 页上创建最近一次导`ingestiondata`入作业后的30天内, 将删除您的组织的 Azure 存储位置中的所有 PST 文件 (在 blob 容器中名为)。 
  
这也意味着在从 Azure 存储区域中删除 PST 文件后, 这些文件将不再显示在安全&amp;合规性中心中已完成导入作业的文件列表中。尽管安全&amp;合规中心中的**导入**页面仍可能会列出导入作业, 但在查看较旧的导入作业的详细信息时, PST 文件列表可能为空。 
  
 **导入 Office 365 支持哪种版本的 PST 文件格式？**
  
有两个版本的 PST 文件格式: ANSI 和 Unicode。建议导入使用 Unicode PST 文件格式的文件。但是, 使用 ANSI PST 文件格式的文件 (例如, 使用双字节字符集 (DBCS) 的语言的文件) 也可以导入到 Office 365。有关导入 ANSI PST 文件的详细信息, 请参阅第3步:[使用驱动器传送将组织中的 pst 文件导入到 Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md#step-3-create-the-pst-import-mapping-file)。
  
此外, 还可以将 Outlook 2007 和更高版本中的 PST 文件导入到 Office 365。
  
 **导入 PST 文件时是否有邮件大小限制？**
  
是的。如果 PST 文件包含大于 150 MB 的邮箱项目, 则在导入过程中将跳过该项目。
  
 **是邮件属性, 例如邮件的发送或接收时间、将 PST 文件导入到 Office 365 邮箱时所保留的收件人和其他属性的列表？**
  
是的。在导入过程中不更改原始邮件元数据
  
 **对于要导入到邮箱中的 PST 文件, 文件夹层次结构中的级别数是否有限制？**
  
是的。您不能导入包含300或更多级别的嵌套文件夹的 PST 文件。
  
 **我是否可以使用驱动器发货将 PST 文件导入 Office 365 中的非活动邮箱？**
  
是的, 此功能现已推出。
  
 **是否可以使用驱动器发货将 PST 文件导入到 Exchange 混合部署中的联机存档邮箱？**
  
是的, 此功能现已推出。
  
 **我是否可以使用驱动器发货以将 PST 文件导入到 Exchange Online 中的公用文件夹？**
  
否, 不能将 PST 文件导入到公用文件夹。
  
 **Microsoft 可以先擦除我的硬盘, 然后再将其传送回我？**
  
否, Microsoft 无法在将硬驱运输回客户之前将其擦除。硬驱将返回到 Microsoft 收到它们时所处的状态。
  
 **Microsoft 是否可以清除硬盘, 而不是将其传送回我的硬盘？**
  
否, Microsoft 无法销毁你的硬驱。硬驱将返回到 Microsoft 收到它们时所处的状态。
  
 **退货装运支持哪些快递服务？**
  
如果你是美国或欧洲的客户, Microsoft 使用 FedEx 返回你的硬盘。对于所有其他地区, Microsoft 使用 DHL。
  
 **退货的送货费用是多少？**
  
根据您与您发送到的 Microsoft 数据中心的邻近程度, 返回发货费用会有所不同。Microsoft 将向你的 FedEx 或 DHL 帐户计费, 以返回你的硬驱。退货交付的成本是您的责任。
  
 **我可以使用自定义的快递发货服务 (如 FedEx 自定义装运) 将我的硬盘发送到 Microsoft 吗？**
  
可以。
  
 **如果我需要将我的硬盘驱动器运送到另一个国家/地区, 是否有我需要执行的操作？**
  
您发布到 Microsoft 的硬盘驱动器可能需要跨国际边框。如果是这种情况, 您将负责确保按照适用的法律导入和/或导出硬盘及其包含的数据。在运送硬盘之前, 请咨询你的顾问以验证你的驱动器和数据是否可以合法发送到指定的 Microsoft 数据中心。这将有助于确保它及时进入 Microsoft。
