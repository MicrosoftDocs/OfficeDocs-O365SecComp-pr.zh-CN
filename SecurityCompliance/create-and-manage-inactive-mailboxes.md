---
title: 创建和管理 Office 365 中的非活动邮箱
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 296a02bd-ebde-4022-900e-547acf38ddd7
description: 通过将保持或 Office 365 保留策略应用于邮箱，然后删除相应的 Office 365 用户帐户，您可以在 Office 365 中创建非活动邮箱。非活动邮箱中的项目，将保留其进行非活动状态之前对其应用保留或保留策略的持续时间内。若要永久删除非活动邮箱，只需删除保留或保留策略。
ms.openlocfilehash: de67068ded30f63e46a8a94c1030d45a12b56a2e
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/11/2019
ms.locfileid: "29740834"
---
# <a name="create-and-manage-inactive-mailboxes-in-office-365"></a>创建和管理 Office 365 中的非活动邮箱

Office 365 使您可以保留已删除邮箱的内容。此功能称为[非活动邮箱](inactive-mailboxes-in-office-365.md)。非活动邮箱，您可以在它们离开组织后保留以前员工的电子邮件。诉讼保留或 Office 365 保留策略时，邮箱变为非活动状态 (在 Office 365 安全性中创建&amp;合规性中心) 中删除相应的 Office 365 用户帐户之前应用于邮箱。非活动邮箱的内容将保留在邮箱发出，已处于非活动状态的保留项的持续时间。这允许管理员、 合规部主管和记录管理者中安全使用内容搜索&amp;合规性中心搜索和导出的非活动邮箱内容。非活动邮箱无法接收电子邮件和您的组织共享的通讯簿或其他列表中未显示。
  
> [!NOTE]
> 我们已推迟创建新的就地保留进行非活动邮箱的 2017 年 7 月 1，最后期限。但今年或早期明年，您将无法创建新的就地保留在 Exchange Online。此时，仅诉讼保留和 Office 365 的保留策略可用于创建非活动邮箱。但是，仍会支持现有的非活动邮箱上就地保留的并且您可以继续管理非活动邮箱上就地保留。这包括更改的就地保留持续时间，并通过删除就地保留中永久删除非活动邮箱。 
  
## <a name="before-you-begin"></a>准备工作

- 若要使非活动邮箱，必须将它分配的 Exchange Online 计划 2 许可证，以便诉讼保留或 Office 365 保留策略可应用于邮箱被删除之前。Exchange Online 计划 2 许可证是 Office 365 企业版 E3 和 E5 订阅的一部分。如果邮箱已分配的 Exchange Online 计划 1 许可证 （它是 Office 365 企业版 E1 订阅的一部分），您将需要以便保留可应用于邮箱被删除之前将其分配单独的 Exchange Online Archiving 许可证。有关详细信息，请参阅[Exchange Online Archiving](https://go.microsoft.com/fwlink/p/?LinkId=286153)。
    
- 删除相应的 Office 365 用户帐户后，将可与 Exchange Online 的已删除邮箱关联的许可证。然后可以[将对业务的 Office 365 中的用户的许可证分配](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)给其他用户。 
    
- 如果诉讼保留或 Office 365 保留策略不应用于邮箱被删除之前，邮箱的内容不会保留或可供搜索。但是，可以删除，30 天内恢复已删除的邮箱的邮箱，其内容将被永久删除 30 天后如果它不可恢复。
    
- 有关诉讼保留的详细信息，请参阅[就地保留和诉讼保留](https://go.microsoft.com/fwlink/p/?LinkId=846124)。有关 Office 365 中安全性的保留策略的详细信息&amp;合规性中心，请参阅[Overview of Office 365 中的保留策略](retention-policies.md)。
  
## <a name="create-an-inactive-mailbox"></a>创建非活动邮箱

使非活动邮箱涉及两个步骤： 1） 发出邮箱诉讼保留或将 Office 365 保留策略应用于，和 2） 删除邮箱或相应的 Office 365 用户帐户。邮箱处于非活动状态后，将保留其内容，直到删除保留或保留策略。
  
### <a name="step-1-place-a-mailbox-on-litigation-hold-or-apply-an-office-365-retention-policy"></a>步骤 1： 将邮箱置于诉讼保留或 Office 365 保留策略应用

将邮箱置于诉讼保留或将 Office 365 保留策略应用将被删除之前保留的邮箱中的内容。两种类型的保留将保留所有邮箱内容，包括已删除的项目和已修改的项目的原始版本。为指定的时间段，或者直到取消，永久删除非活动邮箱中删除应用于非活动邮箱的保留或保留策略在非活动邮箱中保留已删除和修改项目。
  
如果保留已置于邮箱，或者已应用于邮箱的 Office 365 保留策略，您只需执行操作是删除相应的 Office 365 用户帐户，如在步骤 2 中所述。
  
有关将邮箱置于诉讼保留或将 Office 365 保留策略应用的分步过程，请参阅：
  
- [将邮箱置于诉讼保留状态](https://go.microsoft.com/fwlink/?linkid=856286)
    
- [Office 365 中的保留策略概述](retention-policies.md)
    
> [!NOTE]
> 诉讼保留和 Office 365 保留策略，您可以创建无限期保留，或基于时间的保留。无限期保留，在非活动邮箱的内容将下去，保留或直到保留被删除或更改保留持续时间。保持或保留策略已 （假定指定邮箱已删除超过 30 天） 后，非活动邮箱将标记为永久删除和保留或可供搜索，将不再是邮箱的内容。在基于时间的保留或 Office 365 保留策略中，您可以指定保留项的持续时间。此持续时间在每项基础和接收或创建邮箱项目从日期计算。保留项过期邮箱项目，并且该项目移动到或非活动邮箱中可恢复邮件文件夹位于后，项目被永久删除 （清除） 从非活动邮箱已删除的邮件保留期过后。 
  
### <a name="step-2-delete-the-mailbox"></a>步骤 2：删除邮箱

邮箱置于保持状态或 Office 365 保留策略应用于其后下, 一步是删除邮箱。删除邮箱的最佳方式是删除 Office 365 管理中心中的相应 Office 365 用户帐户。有关删除 Office 365 用户帐户的信息，请参阅[删除用户从您的组织](https://support.office.com/article/d5155593-3bac-4d8d-9d8b-f4513a81479e)。
  
> [!NOTE]
> 您也可以在 Exchange Online PowerShell 中使用**Remove-mailbox** cmdlet 删除邮箱。有关详细信息，请参阅[删除或还原 Exchange 在 Online 用户邮箱](https://go.microsoft.com/fwlink/?linkid=856287)。 
  

## <a name="view-a-list-of-inactive-mailboxes"></a>查看列表的非活动邮箱


若要查看组织中的非活动邮箱的列表：
  
1. 转到[https://protection.office.com/](https://protection.office.com/)和使用 Office 365 组织中的管理员帐户凭据登录。 
    
2. 在左侧窗格中的安全&amp;合规性中心，单击**数据调控** \> * * 保留 * *。
    
3. 在**保留**页上，单击**更多**![导航栏省略号](media/9723029d-e5cd-4740-b5b1-2806e4f28208.gif)，，然后单击**非活动邮箱**。
    
    ![在保留页上，单击更多，然后单击非活动邮箱显示非活动邮箱的列表](media/761bd90c-3e37-48f9-b1b9-479e90fea267.png)
  
    显示**非活动邮箱**页。请注意显示您的组织中的非活动邮箱总数。 
    
    ![将显示您的组织中的所有非活动邮箱的列表](media/57d9d183-0c6c-4bd8-82e7-115f7b7b6de7.png)
  
此外，还可以运行以下命令在 Exchange Online PowerShell，可以显示非活动邮箱的列表。

```
 Get-Mailbox -InactiveMailboxOnly | FT DisplayName,PrimarySMTPAddress,WhenSoftDeleted
```

您可以单击![导出搜索结果图标](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png)**导出**以查看或下载 CSV 文件包含有关您的组织中的非活动邮箱的其他信息。 
  
您还可以运行以下命令以将非活动邮箱的列表和其他信息导出到 CSV 文件。本示例中，在当前目录中创建 CSV 文件。

```
Get-Mailbox -InactiveMailboxOnly | Select Displayname,PrimarySMTPAddress,DistinguishedName,ExchangeGuid,WhenSoftDeleted | Export-Csv InactiveMailboxes.csv -NoType
```
   
> [!NOTE]
> 则可能非活动邮箱，可能为活动用户邮箱中的相同的 SMTP 地址。在这种情况下，可以使用的**可分辨名称**或**ExchangeGuid**属性的值来唯一地标识非活动邮箱。 
  
## <a name="search-and-export-the-contents-of-an-inactive-mailbox"></a>搜索和导出内容的非活动邮箱

可以通过使用中的安全的内容搜索工具访问的非活动邮箱内容&amp;合规性中心。搜索非活动邮箱时，您可以创建关键字搜索查询来搜索特定项，或者您可以返回非活动邮箱的全部内容。您可以预览搜索结果，或将搜索结果导出到 Outlook 数据 (PST) 文件或作为单个电子邮件。用于搜索邮箱和导出搜索结果的分步过程，请参阅下列主题：
  
- [Office 365 中的内容搜索](content-search.md)
    
- [从 Office 365 安全性导出内容的搜索结果&amp;合规性中心](export-search-results.md)
    
下面是要搜索非活动邮箱时，请记住的几个事项。
  
- 如果内容搜索包含用户邮箱，并且该邮箱由处于非活动状态，内容搜索将继续在它变为非活动状态后重新运行搜索时搜索非活动邮箱。
    
- 在某些情况下，用户可能有活动邮箱和非活动邮箱，具有相同的 SMTP 地址。在这种情况下，将搜索仅特定邮箱的选择作为内容搜索的位置。换句话说，如果您将用户邮箱添加到搜索，您不能假设，将搜索其活动和非活动邮箱;将搜索的明确添加到搜索邮箱。
    
- 我们强烈建议您避免使用活动邮箱和非活动邮箱具有相同的 SMTP 地址。如果您需要重用当前分配给非活动邮箱的 SMTP 地址，我们建议恢复非活动邮箱或非活动邮箱的内容还原到活动邮箱 （或活动邮箱的存档），然后删除非活动邮箱。
    
## <a name="change-the-hold-duration-for-an-inactive-mailbox"></a>更改非活动邮箱的保留期

非活动邮箱后，您可以更改保留或 Office 365 保留策略应用于非活动邮箱的持续时间。有关分步步骤说明，请参阅[更改在 Office 365 中的非活动邮箱的保留持续时间](change-the-hold-duration-for-an-inactive-mailbox.md)。
  
## <a name="recover-an-inactive-mailbox"></a>恢复非活动邮箱

如果以前员工返回给您的组织，或新员工加入才能离开员工职责，您可以恢复非活动邮箱的内容。非活动邮箱恢复时，邮箱转换为新邮箱，将保留内容和非活动邮箱文件夹结构，以及邮箱链接到新的用户帐户。将在恢复之后，非活动邮箱不再存在。分步过程和详细信息发生非活动邮箱恢复时，请参阅[Office 365 中的非活动邮箱恢复](recover-an-inactive-mailbox.md)。
  
## <a name="restore-the-contents-of-an-inactive-mailbox-to-another-mailbox"></a>将非活动邮箱的内容还原到另一个邮箱

如果另一个雇员承担的前员工职责或其他人需要访问非活动邮箱的内容，您可以还原 （或合并） 到现有邮箱的非活动邮箱的内容。非活动邮箱还原时，内容复制到另一个邮箱。非活动邮箱保留，并保持非活动邮箱。仍可使用电子数据展示搜索非活动邮箱，可在其内容还原到另一个邮箱或恢复或删除以后。有关分步步骤说明，请参阅[还原 Office 365 中的非活动邮箱](restore-an-inactive-mailbox.md)。
  
## <a name="delete-an-inactive-mailbox"></a>删除非活动邮箱

如果您不再需要保留的非活动邮箱内容，您可以通过删除保留或移除 Office 365 保留策略应用于非活动邮箱中永久删除非活动邮箱。如果邮箱已删除超过 30 天，邮箱将标记为永久删除后删除保留，并且邮箱将变为不可恢复。如果最近 30 天内已删除邮箱，仍可以恢复后删除保留或保留策略的邮箱。有关删除保留或 Office 365 保留策略永久删除非活动邮箱的分步过程，请参阅[删除非活动邮箱 Office 365 中](delete-an-inactive-mailbox.md)。