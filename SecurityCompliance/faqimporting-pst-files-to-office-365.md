---
title: 有关将 PST 文件导入到 Office 365 常见问题
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 1/3/2018
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 2fe71b05-f5a2-4182-ade7-4dc5cabdfd51
description: '有关使用 Office 365 导入服务将生成组织的 PST 文件导入到 Office 365 邮箱，常见问题 (英文） 的管理员。 '
ms.openlocfilehash: 35080106f92b38e944ba31f74d5564e65ba1f752
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22526082"
---
# <a name="faq-about-importing-pst-files-to-office-365"></a>有关将 PST 文件导入到 Office 365 常见问题

**本文是针对管理员。是否要将 PST 文件导入到您自己的邮箱？请参阅[导入电子邮件、 联系人和日历从 Outlook.pst 文件](https://go.microsoft.com/fwlink/p/?LinkID=785075)**|
   
以下是一些有关使用 Office 365 导入服务批量导入 PST 文件迁移到 Office 365 邮箱的常见问题。有关如何导入 PST 文件的详细信息，请参阅[Overview of 导入 PST 文件迁移到 Office 365](https://support.office.com/article/ba688e0a-0fcb-4bd7-8e57-2b669564ea84)。
  
## <a name="using-network-upload-to-import-pst-files"></a>使用网络上载以导入 PST 文件

有关分步说明，请参阅[使用网络上载以导入 PST 文件迁移到 Office 365](use-network-upload-to-import-pst-files.md)。
  
 **需要在 Office 365 导入服务中创建导入作业哪些权限？**
  
您必须为其分配导入导出邮箱角色在 Exchange Online 到 Office 365 邮箱导入 PST 文件。默认情况下，此角色不分配给任何角色组在 Exchange Online。您可以向组织管理角色组中添加邮箱导入导出角色。或者，您可以创建新角色组、 分配的邮箱导入导出角色中，然后将自己或其他用户添加为成员。有关详细信息，请参阅"添加角色向角色组"或"创建角色组"部分[管理角色组在 Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=730688)中。
  
此外，若要创建导入作业 Office 365 安全性&amp;必须满足合规中心，下列选项之一：
  
- 您必须分配 Mail Recipients 角色在 Exchange Online。默认情况下，此角色分配给组织管理和 Recipient Management 角色组。
    
    或
    
- 您必须是 Office 365 组织中的全局管理员。
    
> [!TIP]
> 请考虑在 Exchange Online 的专门用于将 PST 文件导入到 Office 365 中创建新的角色组。最小的导入 PST 文件所需的权限级别，将邮箱导入导出和 Mail Recipients 角色分配给新角色组中，，然后添加成员。 
  
 **在哪里网络上载可用**
  
在美国、 加拿大、 巴西、 英国、 欧洲、 印度、 中国、 东南方向亚洲，日本、 韩国、 和澳大利亚是当前可用网络上载。网络上载很快就会提供在多个区域中。
  
 **什么是使用网络上载导入 PST 文件的定价？**
  
使用网络上载以导入 PST 文件是免费的。
  
这还意味着从 Azure 存储区删除 PST 文件后，他们正在不再显示在 Office 365 管理中心中的已完成的导入作业的文件列表中。虽然仍可能会导入作业列出在**导入到 Office 365 的数据**页上，查看旧导入作业的详细信息中可能为空的 PST 文件的列表。 
  
 **导入到 Office 365 支持哪些版本的 PST 文件格式？**
  
有两个版本的 PST 文件格式： ANSI 和 Unicode。我们建议导入使用 Unicode PST 文件格式的文件。但是，使用 ANSI PST 文件格式，如使用双字节字符的语言的文件 (DBCS)，也可以导入到 Office 365。有关导入 ANSI PST 文件的详细信息，请参阅[使用网络上载以导入到 Office 365 组织的 PST 文件](use-network-upload-to-import-pst-files.md#step-4-create-the-pst-import-mapping-file)中的步骤 4。
  
此外，可以到 Office 365 导入 PST 文件从 Outlook 2007 和更高版本。
  
 **我将我的 PST 文件上载到 Azure 存储区后，长它们保存在 Azure 正在删除之前？**
  
如果您使用的网络上载方法来导入 PST 文件，您可以将它们上载到名为**ingestiondata**Azure blob 容器。如果没有导入作业正在进行**导入**页上的安全性&amp;合规性中心)，然后在 Azure 中**ingestiondata**容器中的所有 PST 文件将被都删除 30 天后在安全&amp;合规性中心。这还意味着您必须在安全中创建新的导入作业&amp;到 Azure 文件上载 PST 30 天内的合规性中心 （中所述步骤 5 中的网络上载说明）。 
  
这还意味着从 Azure 存储区删除 PST 文件后，他们正在不再显示在安全中完成导入作业的文件列表中&amp;合规性中心。尽管安全中的**导入**页上，系统可能仍列出导入作业&amp;合规中心的 PST 文件列表可能为空，当您查看旧导入作业的详细信息。 
  
 **导入到邮箱的 PST 文件需要多长时间？**
  
这取决于您的网络的容量，但它通常采用的每个 tb 的数据上载到您的组织的 Azure 存储区的几个小时。PST 文件复制到 Azure 存储区域后，PST 文件导入到 Office 365 邮箱至少 24 GB 每日的速率。如果此速率，不能满足需要，可以考虑将电子邮件数据迁移到 Office 365 的其他方法。有关详细信息，请参阅[方法迁移到 Office 365 的多个电子邮件帐户](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842)。
  
如果不同 PST 文件导入到不同的目标邮箱，导入过程会发生并行;换句话说，每个邮箱 PST 对导入同时。同样，如果多个 PST 文件导入到的同一邮箱，它们将同时导入。
  
 **导入 PST 文件时有邮件大小限制吗？**
  
是的。如果 PST 文件中包含大于 150 MB 邮箱项目，将在导入过程跳过项目。
  
 **邮件属性，例如当邮件已发送或接收，收件人和其他属性，PST 文件导入到 Office 365 邮箱时保留的列表？**
  
是的。在导入过程不会更改原始消息元数据。
  
 **是否有我想要导入到邮箱的 PST 文件的文件夹层次结构中的级别数限制？**
  
是的。无法导入 PST 文件具有 300 或多个级别的嵌套文件夹。
  
 **可以使用网络上载到 Office 365 中的非活动邮箱导入 PST 文件？**
  
是，此功能现已推出的。
  
 **可以使用网络上载到联机存档邮箱的 Exchange 混合部署中导入 PST 文件？**
  
是，此功能现已推出的。
  
 **可以使用网络上载到 Exchange Online 中公用文件夹中导入 PST 文件？**
  
否，您不能 PST 文件导入公用文件夹。
  
## <a name="using-drive-shipping-to-import-pst-files"></a>使用驱动器传送导入 PST 文件

有关分步说明，请参阅[使用传送导入到 Office 365 的 PST 文件的驱动器](use-drive-shipping-to-import-pst-files-to-office-365.md)。
  
 **需要在 Office 365 导入服务中创建导入作业哪些权限？**
  
您必须为其分配到 Office 365 邮箱导入 PST 文件导入导出邮箱角色。默认情况下，此角色不分配给任何角色组在 Exchange Online。您可以向组织管理角色组中添加邮箱导入导出角色。或者，您可以创建新角色组、 分配的邮箱导入导出角色中，然后将自己或其他用户添加为成员。有关详细信息，请参阅"添加角色向角色组"或"创建角色组"部分[管理角色组在 Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=730688)中。
  
此外，若要创建导入作业 Office 365 安全性&amp;必须满足合规中心，下列选项之一：
  
- 您必须分配 Mail Recipients 角色在 Exchange Online。默认情况下，此角色分配给组织管理和 Recipient Management 角色组。
    
    或
    
- 您必须是 Office 365 组织中的全局管理员。
    
> [!TIP]
> 请考虑在 Exchange Online 的专门用于将 PST 文件导入到 Office 365 中创建新的角色组。最小的导入 PST 文件所需的权限级别，将邮箱导入导出和 Mail Recipients 角色分配给新角色组中，，然后添加成员。 
  
 **驱动器发运可用？**
  
在美国、 加拿大、 巴西、 英国、 欧洲、 印度、 中国、 东南方向亚洲，日本、 韩国、 和澳大利亚驱动器传送是当前可用。驱动器传送很快就会提供在多个区域中。
  
 **哪些商业许可协议支持驱动器传送？**
  
可通过 Microsoft 企业协议 (EA) 传送到 Office 365 导入 PST 文件的驱动器。驱动器传送不提供通过 Microsoft 产品和服务协议 (MPSA)。
  
 **什么是使用传送到 Office 365 导入 PST 文件的驱动器的定价？**
  
若要使用驱动器传送到 Office 365 邮箱导入 PST 文件的成本是每 GB 的数据 2 美元。例如，如果附带包含 1,000 GB (1 TB) 的 PST 文件的硬盘驱动器，成本是 2,000 美元。您可以使用导入费用，合作伙伴。有关查找合作伙伴的信息，请参阅[查找您的 Office 365 合作伙伴或经销商](https://go.microsoft.com/fwlink/p/?LinkId=785197)。
  
 **驱动器传送的操作支持哪些类型的硬盘驱动器？**
  
仅为 2.5 英寸固态驱动器 (Ssd) 或 2.5 或 3.5 英寸 SATA II/III 内部硬盘支持与 Office 365 导入服务一起使用。您可以使用硬盘最多 10 TB。导入作业将处理仅第一个数据卷上的硬盘中。必须使用 NTFS 格式化数据量。当数据复制到硬盘上，您可以将其直接使用 2.5 英寸 SSD 附加或 2.5 或 3.5 英寸 SATA II/III 连接器或可以附加外部使用外部 2.5 英寸 SSD 或 2.5 或 3.5 英寸 SATA II/III USB 适配器。
  
> [!IMPORTANT]
> Office 365 导入服务不支持外部硬盘驱动器附带的内置的 USB 适配器。此外，不能使用内外部的硬盘驱动器上的大小写磁盘。请不要附带外部硬盘驱动器。 
  
 **单个导入作业可以提供多少硬盘驱动器？**
  
您可以提供 10 硬盘驱动器单个导入作业的最大值。
  
 **我附带我硬盘后，如何长，转到 Microsoft 数据中心？**
  
这取决于几件事，例如您接近 Microsoft 数据中心，您用于附带硬盘驱动器 （例如下, 一个工作日传递、 两天传递或度数送达） 哪种类型的传送选项。与大多数 shippers，您可以使用跟踪数跟踪您传递的状态。
  
 **我硬盘到达 Microsoft 数据中心后，如何长时间将我的 PST 文件上载到 Azure？**
  
在 Microsoft 数据中心收到您的硬盘后，将花费多之间 7 至 10 个工作日将 PST 文件上载到您的组织的 Microsoft Azure 存储区。PST 文件将上载到名为**ingestiondata**Azure blob 容器。 
  
 **导入到邮箱的 PST 文件需要多长时间？**
  
PST 文件上载到 Azure 存储区后，Office 365 分析 PST 文件中的数据 （以安全方式） 来标识的项目和 PST 文件中包含的其他消息类型的期限。完成此分析后，您必须导入 PST 文件中的所有数据的选项或设置筛选器与控制哪些数据获取导入。开始导入作业后，PST 文件导入到 Office 365 邮箱至少 24 GB 每日的速率。如果此速率，不能满足需要，可以考虑将电子邮件数据导入到 Office 365 的其他方法。有关详细信息，请参阅[方法迁移到 Office 365 的多个电子邮件帐户](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842)。
  
如果不同 PST 文件导入到不同的目标邮箱，导入过程会发生并行;换句话说，每个邮箱 PST 对导入同时。同样，如果多个 PST 文件导入到的同一邮箱，它们将同时导入。
  
 **Microsoft 将我的 PST 文件上载到 Azure 后，长它们保存在 Azure 正在删除之前？**
  
中的 Azure 的存储位置 （在 blob 容器中名为**ingestiondata** ），贵组织的所有 PST 文件将被都删除 30 天后在安全的**导入**页上创建的最新的导入作业&amp;合规性中心。 
  
这还意味着从 Azure 存储区删除 PST 文件后，他们正在不再显示在安全中完成导入作业的文件列表中&amp;合规性中心。尽管安全中的**导入**页上，系统可能仍列出导入作业&amp;合规中心的 PST 文件列表可能为空，当您查看旧导入作业的详细信息。 
  
 **导入到 Office 365 支持哪些版本的 PST 文件格式？**
  
有两个版本的 PST 文件格式： ANSI 和 Unicode。我们建议导入使用 Unicode PST 文件格式的文件。但是，使用 ANSI PST 文件格式，如使用双字节字符的语言的文件 (DBCS)，也可以导入到 Office 365。有关导入 ANSI PST 文件的详细信息，请参阅[使用驱动器传送导入 PST 文件迁移到 Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md#step-3-create-the-pst-import-mapping-file)中的步骤 3。
  
此外，可以到 Office 365 导入 PST 文件从 Outlook 2007 和更高版本。
  
 **导入 PST 文件时有邮件大小限制吗？**
  
是的。如果 PST 文件中包含大于 150 MB 邮箱项目，将在导入过程跳过项目。
  
 **邮件属性，例如当邮件已发送或接收，收件人和其他属性，PST 文件导入到 Office 365 邮箱时保留的列表？**
  
是的。导入过程中未更改的原始消息元数据
  
 **是否有我想要导入到邮箱的 PST 文件的文件夹层次结构中的级别数限制？**
  
是的。无法导入 PST 文件具有 300 或多个级别的嵌套文件夹。
  
 **可以使用驱动器传送到 Office 365 中的非活动邮箱导入 PST 文件？**
  
是，此功能现已推出的。
  
 **可以使用驱动器传送到联机存档邮箱的 Exchange 混合部署中导入 PST 文件？**
  
是，此功能现已推出的。
  
 **可以使用驱动器传送到 Exchange Online 中公用文件夹中导入 PST 文件？**
  
否，您不能 PST 文件导入公用文件夹。
  
 **运回我之前，可以 Microsoft 擦除我硬盘驱动器上？**
  
否，Microsoft 不能擦除之前传送它们返回到客户的硬盘驱动器。硬盘驱动器相同时它们接收由 Microsoft 它们所处的状态返回给您。
  
 **Microsoft 可以清除而不是传送给我我硬盘驱动器上？**
  
否，Microsoft 能销毁硬盘驱动器。硬盘驱动器相同时它们接收由 Microsoft 它们所处的状态返回给您。
  
 **返回传送的操作支持哪些 courier 服务？**
  
如果您在美国或欧洲客户，Microsoft 使用 FedEx 返回硬盘驱动器。对于所有其他区域，Microsoft 使用 DHL。
  
 **返回传送成本是什么？**
  
返回传送成本有所不同，具体取决于您接近 Microsoft 数据中心的传送到硬盘空间。Microsoft 将 bill 返回您的硬盘您 FedEx 或 DHL 的帐户。返回传送的成本是您的责任。
  
 **可以使用自定义 courier 传送服务，如 FedEx 自定义的传送提供给 Microsoft 我硬盘驱动器上？**
  
是。
  
 **如果我必须附带我到另一个国家/地区的硬盘，还有什么我需要做？**
  
向 Microsoft 附带的硬盘可能需要跨国际边框。如果是这样，您负责确保的硬盘和它包含的数据将导入和/或适用法律按照导出。前传送硬盘驱动器，请与您的顾问验证，您的驱动器和数据合法可以传送到指定的 Microsoft 数据中心。这将有助于确保它及时到达 Microsoft。
