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
ms.openlocfilehash: 69767353a574336351b01fdc42a9c6117c5c31ed
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32255430"
---
# <a name="faq-about-importing-pst-files-to-office-365"></a>将 PST 文件导入到 Office 365 的常见问题解答

**本文适用于管理员。是否要将 PST 文件导入到自己的邮箱？请参阅[从 Outlook .pst 文件导入电子邮件、联系人和日历](https://go.microsoft.com/fwlink/p/?LinkID=785075)**|
   
下面是一些有关使用 office 365 导入服务批量导入 PST 文件到 office 365 邮箱的常见问题。 有关如何导入 pst 文件的详细信息, 请参阅[将 pst 文件导入到 Office 365 概述](https://support.office.com/article/ba688e0a-0fcb-4bd7-8e57-2b669564ea84)。
  
## <a name="using-network-upload-to-import-pst-files"></a>使用网络上载导入 PST 文件

有关分步说明, 请参阅[使用网络上载将 PST 文件导入到 Office 365](use-network-upload-to-import-pst-files.md)。
  
 **在 Office 365 导入服务中创建导入作业所需的权限是什么？**
  
您必须在 Exchange Online 中分配 "邮箱导入导出" 角色, 才能将 PST 文件导入到 Office 365 邮箱。 默认情况下, 此角色不会分配给 Exchange Online 中的任何角色组。 You can add the Mailbox Import Export role to the Organization Management role group. Or you can create a new role group, assign the Mailbox Import Export role, and then add yourself or other users as a member. 有关详细信息, 请参阅在[Exchange Online 中管理角色组](https://go.microsoft.com/fwlink/p/?LinkId=730688)中的 "将角色添加到角色组" 或 "创建角色组" 部分。
  
此外, 若要在 Security & 合规性中心中创建导入作业, 必须满足以下条件之一:
  
- 您必须在 Exchange Online 中向您分配 "邮件收件人" 角色。 By default, this role is assigned to the Organization Management and Recipient Management roles groups.
    
    或
    
- 您必须是 Office 365 组织中的全局管理员。
    
> [!TIP]
> 请考虑在 Exchange Online 中创建一个专门用于将 PST 文件导入到 Office 365 的新角色组。 若要获取导入 PST 文件所需的最低级别权限, 请将 "邮箱导入导出" 和 "邮件收件人" 角色分配给新的角色组, 然后添加成员。 
  
 **网络上传的可用位置是什么？**
  
网络上传目前适用于美国、加拿大、巴西、英国、法国、欧洲、印度、东亚、东南亚、日本、朝鲜共和国和澳大利亚。 Network upload will be available in more regions soon.
  
 **What is the pricing for importing PST files by using network upload?**
  
Using network upload to import PST files is free.
  
这也意味着, 在从 Azure 存储区域中删除 PST 文件后, 这些文件将不再显示在 Microsoft 365 管理中心中已完成导入作业的文件列表中。 尽管导入作业可能仍在 "**导入数据到 Office 365** " 页上列出, 但在查看较旧的导入作业的详细信息时, PST 文件列表可能为空。 
  
 **What version of the PST file format is supported for importing to Office 365?**
  
There are two versions of the PST file format: ANSI and Unicode. We recommend importing files that use the Unicode PST file format. 但是, 使用 ANSI PST 文件格式的文件 (例如, 使用双字节字符集 (DBCS) 的语言的文件) 也可以导入到 Office 365。 有关导入 ANSI PST 文件的详细信息, 请参阅 "[使用网络上载将组织的 PST 文件导入到 Office 365](use-network-upload-to-import-pst-files.md#step-4-create-the-pst-import-mapping-file)" 中的步骤4。
  
Additionally, PST files from Outlook 2007 and later versions can be imported to Office 365.
  
 **将 PST 文件上传到 azure 存储区域后, 它们在被删除之前保留在 azure 中的时间是多少？**
  
使用网络上传方法导入 PST 文件时, 会将这些文件上传到名为**ingestiondata**的 Azure blob 容器中。 如果 security & 合规中心中的 "**导入**" 页面上没有正在进行的导入作业, 则在安全 & 中创建最近的导入作业30天后删除 Azure 中**ingestiondata**容器中的所有 PST 文件。合规性中心。 这也意味着, 您必须在安全 & 合规性中心 (在网络上载说明中的步骤5中介绍) 在将 PST 文件上载到 Azure 的30天内创建新的导入作业。 
  
这也意味着在从 Azure 存储区域中删除 PST 文件后, 这些文件将不再显示在安全 & 合规性中心中已完成导入作业的文件列表中。 虽然 Security & 合规性中心的**导入**页面仍可能会列出导入作业, 但在查看较旧的导入作业的详细信息时, PST 文件列表可能为空。 
  
 **将 PST 文件导入到邮箱需要多长时间？**
  
It depends on the capacity of your network, but it typically takes several hours for each terabyte (TB) of data to be uploaded to the Azure storage area for your organization. 将 pst 文件复制到 Azure 存储区域后, pst 文件将以每日至少 24 GB 的速度导入到 Office 365 邮箱中。 如果此比率不能满足您的需求, 则可以考虑将电子邮件数据迁移到 Office 365 的其他方法。 有关详细信息，请参阅[将多个电子邮件帐户迁移到 Office 365 的方法](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842)。
  
If different PST files are imported to different target mailboxes, the import process occurs in parallel; in other words, each PST/mailbox pair is imported simultaneously. 同样, 如果将多个 PST 文件导入到同一个邮箱, 则会同时导入这些文件。
  
 **Is there a message size limit when importing PST files?**
  
是。 如果 PST 文件包含大于 150 MB 的邮箱项目, 则在导入过程中将跳过该项目。
  
 **是邮件属性, 例如邮件的发送或接收时间、将 PST 文件导入到 Office 365 邮箱时所保留的收件人和其他属性的列表？**
  
是。 在导入过程中不会更改原始的邮件元数据。
  
 **Is there a limit to the number of levels in a folder hierarchy for a PST file that I want to import to a mailbox?**
  
Yes. You can't import a PST file that has 300 or more levels of nested folders.
  
 **Can I use network upload to import PST files to an inactive mailbox in Office 365?**
  
Yes, this capability is now available. 
  
 **Can I use network upload to import PST files to an online archive mailbox in an Exchange hybrid deployment?**
  
Yes, this capability is now available. 
  
 **是否可以使用网络上载将 PST 文件导入到 Exchange Online 中的公用文件夹？**
  
否, 不能将 PST 文件导入到公用文件夹。
  
## <a name="using-drive-shipping-to-import-pst-files"></a>使用驱动器发货以导入 PST 文件

有关分步说明, 请参阅[使用驱动器发货将 PST 文件导入到 Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md)。
  
 **在 Office 365 导入服务中创建导入作业所需的权限是什么？**
  
您必须分配有邮箱导入导出角色, 才能将 PST 文件导入到 Office 365 邮箱。 默认情况下, 此角色不会分配给 Exchange Online 中的任何角色组。 You can add the Mailbox Import Export role to the Organization Management role group. Or you can create a new role group, assign the Mailbox Import Export role, and then add yourself or other users as a member. 有关详细信息, 请参阅在[Exchange Online 中管理角色组](https://go.microsoft.com/fwlink/p/?LinkId=730688)中的 "将角色添加到角色组" 或 "创建角色组" 部分。
  
此外, 若要在 Security & 合规性中心中创建导入作业, 必须满足以下条件之一:
  
- 您必须在 Exchange Online 中向您分配 "邮件收件人" 角色。 By default, this role is assigned to the Organization Management and Recipient Management roles groups.
    
    或
    
- 您必须是 Office 365 组织中的全局管理员。
    
> [!TIP]
> 请考虑在 Exchange Online 中创建一个专门用于将 PST 文件导入到 Office 365 的新角色组。 若要获取导入 PST 文件所需的最低级别权限, 请将 "邮箱导入导出" 和 "邮件收件人" 角色分配给新的角色组, 然后添加成员。 
  
 **驱动器运输在什么位置？**
  
目前, 在美国、加拿大、巴西、英国、欧洲、印度、东亚、东南亚、日本、韩国和澳大利亚都可以使用驱动器运输。 Drive shipping will be available in more regions soon.
  
 **What commercial licensing agreements support drive shipping?**
  
将 PST 文件导入到 Office 365 的驱动器发货通过 Microsoft 企业协议 (EA) 提供。 无法通过 Microsoft 产品和服务协议 (MPSA) 获取驱动器发货。
  
 **使用驱动器发货将 PST 文件导入到 Office 365 的定价是多少？**
  
The cost to use drive shipping to import PST files to Office 365 mailboxes is $2 USD per GB of data. For example, if you ship a hard drive that contains 1,000 GB (1 TB) of PST files, the cost is $2,000 USD. You can work with a partner to pay the import fee. 有关查找合作伙伴的信息, 请参阅[查找 Office 365 合作伙伴或经销商](https://go.microsoft.com/fwlink/p/?LinkId=785197)。
  
 **What kind of hard drives are supported for drive shipping?**
  
仅2.5 英寸固态驱动器 (ssd) 或2.5 或3.5 英寸 SATA II/III 内置硬盘可与 Office 365 导入服务配合使用。 You can use hard drives up to 10 TB. 对于导入作业, 仅会处理硬盘上的第一个数据量。 The data volume must be formatted with NTFS. 将数据复制到硬盘时, 可以使用2.5 英寸 SSD 或2.5 或3.5 英寸 SATA ii/iii 连接器直接附加它, 也可以使用外部的2.5 英寸 ssd 或2.5 或3.5 英寸 sata ii/iii USB 适配器将其连接到外部。
  
> [!IMPORTANT]
> 内置 USB 适配器附带的外部硬盘驱动器不受 Office 365 导入服务的支持。 Additionally, the disk inside the casing of an external hard drive can't be used. Please don't ship external hard drives. 
  
 **How many hard drives can I ship for a single import job?**
  
You can ship a maximum of 10 hard drives for a single import job.
  
 **After I ship my hard drive, how long does it take to get to the Microsoft data center?**
  
That depends on a few things, such as your proximity to the Microsoft data center and what kind of shipping option you used to ship your hard drive (such as, next-day delivery, two-day delivery, or ground-delivery). With most shippers, you can use the tracking number to track the status of your delivery.
  
 **硬盘驱动器到达 Microsoft 数据中心后, 将 PST 文件上传到 Azure 需要多长时间？**
  
在 Microsoft 数据中心收到硬盘驱动器后, 需要7到10个工作日才能将 PST 文件上传到组织的 Microsoft Azure 存储区域。 PST 文件将被上传到名为**ingestiondata**的 Azure blob 容器中。 
  
 **将 PST 文件导入到邮箱需要多长时间？**
  
将 pst 文件上传到 Azure 存储区域后, Office 365 将分析 pst 文件中的数据 (以安全和安全的方式), 以确定这些项目的年龄以及 pst 文件中包含的不同邮件类型。 完成此分析后, 您可以选择导入 PST 文件中的所有数据, 也可以将筛选器设置为, 以控制导入的数据。 在您开始导入作业后, PST 文件将以每日至少 24 GB 的速度导入到 Office 365 邮箱中。 如果此比率不能满足您的需求, 则可以考虑将电子邮件数据导入到 Office 365 的其他方法。 有关详细信息，请参阅[将多个电子邮件帐户迁移到 Office 365 的方法](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842)。
  
If different PST files are imported to different target mailboxes, the import process occurs in parallel; in other words, each PST/mailbox pair is imported simultaneously. 同样, 如果将多个 PST 文件导入到同一个邮箱, 则会同时导入这些文件。
  
 **Microsoft 将我的 PST 文件上载到 azure 后, 它们在被删除之前在 azure 中保留的时间是多少？**
  
在安全 & 合规中心的 "**导入**" 页上创建最近的导入作业30天后, 将在您的组织的 Azure 存储位置中删除所有 PST 文件 (在 blob 容器中名为**ingestiondata** )。 
  
这也意味着在从 Azure 存储区域中删除 PST 文件后, 这些文件将不再显示在安全 & 合规性中心中已完成导入作业的文件列表中。 虽然 Security & 合规性中心的**导入**页面仍可能会列出导入作业, 但在查看较旧的导入作业的详细信息时, PST 文件列表可能为空。 
  
 **What version of the PST file format is supported for importing to Office 365?**
  
There are two versions of the PST file format: ANSI and Unicode. We recommend importing files that use the Unicode PST file format. 但是, 使用 ANSI PST 文件格式的文件 (例如, 使用双字节字符集 (DBCS) 的语言的文件) 也可以导入到 Office 365。 有关导入 ANSI PST 文件的详细信息, 请参阅 "[使用驱动器传送将 PST 文件导入到 Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md#step-3-create-the-pst-import-mapping-file)" 中的步骤3。
  
Additionally, PST files from Outlook 2007 and later versions can be imported to Office 365.
  
 **Is there a message size limit when importing PST files?**
  
是。 如果 PST 文件包含大于 150 MB 的邮箱项目, 则在导入过程中将跳过该项目。
  
 **是邮件属性, 例如邮件的发送或接收时间、将 PST 文件导入到 Office 365 邮箱时所保留的收件人和其他属性的列表？**
  
是。 在导入过程中不更改原始邮件元数据
  
 **Is there a limit to the number of levels in a folder hierarchy for a PST file that I want to import to a mailbox?**
  
Yes. You can't import a PST file that has 300 or more levels of nested folders.
  
 **Can I use drive shipping to import PST files to an inactive mailbox in Office 365?**
  
Yes, this capability is now available.
  
 **Can I use drive shipping to import PST files to an online archive mailbox in an Exchange hybrid deployment?**
  
Yes, this capability is now available. 
  
 **我是否可以使用驱动器发货以将 PST 文件导入到 Exchange Online 中的公用文件夹？**
  
否, 不能将 PST 文件导入到公用文件夹。
  
 **Can Microsoft wipe my hard drive before they ship it back to me?**
  
No, Microsoft can't wipe hard drives before shipping them back to customers. Hard drives are returned to you in the same state they were in when they were received by Microsoft.
  
 **Microsoft 是否可以清除硬盘, 而不是将其传送回我的硬盘？**
  
No, Microsoft can't destroy your hard drive. Hard drives are returned to you in the same state they were in when they were received by Microsoft.
  
 **退货装运支持哪些快递服务？**
  
If you're a customer in the United States or Europe, Microsoft uses FedEx to return your hard drive. For all other regions, Microsoft uses DHL.
  
 **退货的送货费用是多少？**
  
Return shipping costs vary, depending on your proximity to the Microsoft data center that you shipped your hard drive to. Microsoft will bill your FedEx or DHL account to return your hard drive. The cost of return shipping is your responsibility.
  
 **我可以使用自定义的快递发货服务 (如 FedEx 自定义装运) 将我的硬盘发送到 Microsoft 吗？**
  
是。
  
 **If I have to ship my hard drive to another country, is there anything I need to do?**
  
The hard drive that you ship to Microsoft might have to cross international borders. If this is the case, you're responsible for ensuring that the hard drive and the data it contains are imported and/or exported in accordance with the applicable laws. Before shipping a hard drive, check with your advisors to verify that your drive and data can legally be shipped to the specified Microsoft data center. This will help to ensure that it reaches Microsoft in a timely manner.
