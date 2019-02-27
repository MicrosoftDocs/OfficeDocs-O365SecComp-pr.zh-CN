---
title: 将 PST 文件导入到 Office 365 的常见问题解答
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 2fe71b05-f5a2-4182-ade7-4dc5cabdfd51
description: '有关使用 office 365 导入服务将 organizaiton 的 PST 文件导入到 office 365 邮箱的管理员的常见问题。 '
ms.openlocfilehash: bef9c9e80f4f4c8261e9c44ba201a978937e2841
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/26/2019
ms.locfileid: "30296875"
---
# <a name="faq-about-importing-pst-files-to-office-365"></a>将 PST 文件导入到 Office 365 的常见问题解答

**本文适用于管理员。是否要将 PST 文件导入到自己的邮箱？请参阅[从 Outlook .pst 文件导入电子邮件、联系人和日历](https://go.microsoft.com/fwlink/p/?LinkID=785075)**|
   
下面是一些有关使用 office 365 导入服务批量导入 PST 文件到 office 365 邮箱的常见问题。有关如何导入 pst 文件的详细信息, 请参阅[将 pst 文件导入到 Office 365 概述](https://support.office.com/article/ba688e0a-0fcb-4bd7-8e57-2b669564ea84)。
  
## <a name="using-network-upload-to-import-pst-files"></a>使用网络上载导入 PST 文件

有关分步说明, 请参阅[使用网络上载将 PST 文件导入到 Office 365](use-network-upload-to-import-pst-files.md)。
  
 **在 Office 365 导入服务中创建导入作业所需的权限是什么？**
  
您必须在 Exchange Online 中分配 "邮箱导入导出" 角色, 才能将 PST 文件导入到 Office 365 邮箱。默认情况下, 此角色不会分配给 Exchange Online 中的任何角色组。您可以将邮箱导入导出角色添加到 "组织管理" 角色组。或者, 您可以创建新的角色组, 分配邮箱导入导出角色, 然后将自己或其他用户添加为成员。有关详细信息, 请参阅在[Exchange Online 中管理角色组](https://go.microsoft.com/fwlink/p/?LinkId=730688)中的 "将角色添加到角色组" 或 "创建角色组" 部分。
  
此外, 若要在 Office 365 安全&amp;合规中心中创建导入作业, 必须满足以下条件之一:
  
- 您必须在 Exchange Online 中向您分配 "邮件收件人" 角色。默认情况下, 将此角色分配给组织管理和收件人管理角色组。
    
    或者
    
- 您必须是 Office 365 组织中的全局管理员。
    
> [!TIP]
> 请考虑在 Exchange Online 中创建一个专门用于将 PST 文件导入到 Office 365 的新角色组。若要获取导入 PST 文件所需的最低级别权限, 请将 "邮箱导入导出" 和 "邮件收件人" 角色分配给新的角色组, 然后添加成员。 
  
 **网络上传的可用位置是什么？**
  
网络上传目前适用于美国、加拿大、巴西、英国、法国、欧洲、印度、东亚、东南亚、日本、朝鲜共和国和澳大利亚。不久将在更多区域中提供网络上载。
  
 **使用网络上载导入 PST 文件的价格是多少？**
  
使用网络上传来导入 PST 文件是免费的。
  
这也意味着, 在从 Azure 存储区域中删除 PST 文件后, 这些文件将不再显示在 Office 365 管理中心中已完成导入作业的文件列表中。尽管导入作业可能仍在 "**导入数据到 Office 365** " 页上列出, 但在查看较旧的导入作业的详细信息时, PST 文件列表可能为空。 
  
 **导入 Office 365 支持哪种版本的 PST 文件格式？**
  
有两个版本的 PST 文件格式: ANSI 和 Unicode。建议导入使用 Unicode PST 文件格式的文件。但是, 使用 ANSI PST 文件格式的文件 (例如, 使用双字节字符集 (DBCS) 的语言的文件) 也可以导入到 Office 365。有关导入 ANSI PST 文件的详细信息, 请参阅 "[使用网络上载将组织的 PST 文件导入到 Office 365](use-network-upload-to-import-pst-files.md#step-4-create-the-pst-import-mapping-file)" 中的步骤4。
  
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
  
## <a name="using-drive-shipping-to-import-pst-files"></a>使用驱动器发货以导入 PST 文件

有关分步说明, 请参阅[使用驱动器发货将 PST 文件导入到 Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md)。
  
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
  
在 Microsoft 数据中心收到硬盘驱动器后, 需要7到10个工作日才能将 PST 文件上传到组织的 Microsoft Azure 存储区域。PST 文件将被上传到名为**ingestiondata**的 Azure blob 容器中。 
  
 **将 PST 文件导入到邮箱需要多长时间？**
  
将 pst 文件上传到 Azure 存储区域后, Office 365 将分析 pst 文件中的数据 (以安全和安全的方式), 以确定这些项目的年龄以及 pst 文件中包含的不同邮件类型。完成此分析后, 您可以选择导入 PST 文件中的所有数据, 也可以将筛选器设置为, 以控制导入的数据。在您开始导入作业后, PST 文件将以每日至少 24 GB 的速度导入到 Office 365 邮箱中。如果此比率不能满足您的需求, 则可以考虑将电子邮件数据导入到 Office 365 的其他方法。有关详细信息, 请参阅[将多个电子邮件帐户迁移到 Office 365 的方法](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842)。
  
如果将不同的 PST 文件导入到不同的目标邮箱, 则导入过程将并行发生;换言之, 每个 PST/邮箱对同时导入。同样, 如果将多个 PST 文件导入到同一个邮箱, 则会同时导入这些文件。
  
 **Microsoft 将我的 PST 文件上载到 azure 后, 它们在被删除之前在 azure 中保留的时间是多少？**
  
在安全&amp;合规中心的 "**导入**" 页上创建最近的导入作业30天后, 将在您的组织的 Azure 存储位置中的所有 PST 文件 (在 blob 容器中为**ingestiondata** ) 删除。 
  
这也意味着在从 Azure 存储区域中删除 PST 文件后, 这些文件将不再显示在安全&amp;合规性中心中已完成导入作业的文件列表中。尽管安全&amp;合规中心中的**导入**页面仍可能会列出导入作业, 但在查看较旧的导入作业的详细信息时, PST 文件列表可能为空。 
  
 **导入 Office 365 支持哪种版本的 PST 文件格式？**
  
有两个版本的 PST 文件格式: ANSI 和 Unicode。建议导入使用 Unicode PST 文件格式的文件。但是, 使用 ANSI PST 文件格式的文件 (例如, 使用双字节字符集 (DBCS) 的语言的文件) 也可以导入到 Office 365。有关导入 ANSI PST 文件的详细信息, 请参阅 "[使用驱动器传送将 PST 文件导入到 Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md#step-3-create-the-pst-import-mapping-file)" 中的步骤3。
  
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
