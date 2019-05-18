---
title: 将外部联系人批量导入到 Exchange Online
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/29/2018
audience: End User
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOP150
ms.assetid: bed936bc-0969-4a6d-a7a5-66305c14e958
description: 了解管理员如何使用 Exchange Online PowerShell 和 CSV 文件将外部联系人批量导入到全局地址列表。
ms.openlocfilehash: 08fe7666f03c7fe60555133292be9e27a9ffa413
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2019
ms.locfileid: "34152204"
---
# <a name="bulk-import-external-contacts-to-exchange-online"></a>将外部联系人批量导入到 Exchange Online

**本文适用于管理员。您是否正在尝试将联系人导入您自己的邮箱？请参阅[将联系人导入到 Outlook](https://support.office.com/article/bb796340-b58a-46c1-90c7-b549b8f3c5f8)**
   
您的公司是否有许多您想要在 Exchange Online 中的共享通讯簿 (也称为 "全局地址列表") 中包含的现有业务联系人？ 您是否要将外部联系人添加为通讯组的成员, 就像您可以与公司内部的用户进行操作一样？ 如果是这样, 您可以使用 Exchange Online PowerShell 和 CSV (逗号分隔值) 文件将外部联系人批量导入 Exchange Online。 这是一个包含三个步骤的过程:
  
[步骤 1: 创建包含有关外部联系人的信息的 CSV 文件](#step-1-create-a-csv-file-that-contains-information-about-the-external-contacts)

[步骤 2: 使用 PowerShell 创建外部联系人](#step-2-create-the-external-contacts-with-powershell) 

[步骤 3: 将信息添加到外部联系人的属性中](#step-3-add-information-to-the-properties-of-the-external-contacts)

完成这些步骤以导入联系人后, 可以执行以下其他任务:
  
- [添加更多外部联系人](#add-more-external-contacts)
  
- [隐藏共享通讯簿中的外部联系人](#hide-external-contacts-from-the-shared-address-book)
  
## <a name="step-1-create-a-csv-file-that-contains-information-about-the-external-contacts"></a>步骤 1: 创建包含有关外部联系人的信息的 CSV 文件

第一步是创建一个 CSV 文件, 其中包含有关要导入到 Exchange Online 的每个外部联系人的信息。 
  
1. 将以下文本复制到记事本中的文本文件, 并使用文件名后缀 .csv 将其以 CSV 文件的形式保存到您的桌面。例如, ExternalContacts。
    
    > [!TIP]
    > 如果您的语言包含特殊字符 (例如, **å**、 **ä**和**ö** in 瑞典语), 则在记事本中保存文件时, 请使用 UTF-8 或其他 Unicode 编码保存 CSV 文件。 
  
    ```
    ExternalEmailAddress,Name,FirstName,LastName,StreetAddress,City,StateorProvince,PostalCode,Phone,MobilePhone,Pager,HomePhone,Company,Title,OtherTelephone,Department,CountryOrRegion,Fax,Initials,Notes,Office,Manager
    danp@fabrikam.com,Dan Park,Dan,Park,1234 23rd Ave,Golden,CO,80215,206-111-1234,303-900-1234,555-1212,123-456-7890,Fabrikam,Shipping clerk,555-5555,Shipping,US,123-4567,R.,Good worker,31/1663,Dan Park
    pilar@contoso.com,Pilar Pinilla,Pilar,Pinilla,1234 Main St.,Seattle,WA,98017,206-555-0100,206-555-0101,206-555-0102,206-555-1234,Contoso,HR Manager,206-555-0104,Executive,US,206-555-0105,P.,Technical decision maker,31/1000,Dan Park 
    ```

    CSV 文件的第一行 (即标题行) 列出了在将联系人导入 Exchange Online 时可使用的联系人的属性。 每个属性名称都用逗号分隔。 标题行下的每一行表示用于导入单个外部联系人的属性值。 
    
    > [!NOTE]
    > 此文本包含可删除的示例数据。 但不要删除或更改第一个 (标头) 行。 它包含外部联系人的所有属性。 
  
2. 在 Microsoft Excel 中打开 CSV 文件以编辑 CSV 文件, 因为使用 Excel 编辑 CSV 文件要容易得多。
    
3. 为要导入到 Exchange Online 中的每个联系人创建一行。 填充尽可能多的单元格。 此信息将显示在每个联系人的共享通讯簿中。 
    
    > [!IMPORTANT]
    >  以下属性 (标题行中的前四项) 是创建外部联系人所必需的, 并且必须在 CSV 文件中进行填充: **ExternalEmailAddress**、 **Name**、 **FirstName**和**LastName**。 您在步骤2中运行的 PowerShell 命令将使用这些属性的值来创建联系人。 

## <a name="step-2-create-the-external-contacts-with-powershell"></a>步骤 2: 使用 PowerShell 创建外部联系人

下一步是使用您在步骤1和 PowerShell 中创建的 CSV 文件以批量将 CSV 文件中列出的外部联系人导入到 Exchange Online。 
  
1.  将 PowerShell 连接到您的 Exchange Online 组织。 有关分步说明, 请参阅[连接到 Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554)。 在连接到 Exchange Online PowerShell 时, 请务必使用 Office 365 全局管理员帐户的用户名和密码。 
    
2. 将 PowerShell 连接到 Exchange Online 后, 请转到在步骤1中保存 CSV 文件的桌面文件夹;例如`C:\Users\Administrator\desktop`。
    
3. 运行以下命令以创建外部联系人:

    ```
    Import-Csv .\ExternalContacts.csv|%{New-MailContact -Name $_.Name -DisplayName $_.Name -ExternalEmailAddress $_.ExternalEmailAddress -FirstName $_.FirstName -LastName $_.LastName}
    ```

    创建新联系人可能需要一段时间, 具体取决于您导入的数量。 命令运行完毕后, PowerShell 将显示已创建的新联系人的列表。 
    
4. 若要查看新的外部联系人, 请转到 Exchange 管理中心 (EAC), 然后单击 "**收件人** \> **联系人**"。 
    
    > [!TIP]
    > 有关连接到 EAC 的说明, 请参阅 exchange [Online 中的 exchange 管理中心](https://go.microsoft.com/fwlink/p/?LinkId=328197)。 
  
5. 如有必要, **** ![请单击 "](media/O365-MDM-Policy-RefreshIcon.gif)刷新刷新" 图标更新列表, 并查看导入的外部联系人。 
    
    导入的联系人将显示在 Outlook 和 web 上的 Outlook 中的共享通讯簿中。
    
    > [!NOTE]
    > 您还可以通过转到 "**用户** \> **联系人**" 查看 Microsoft 365 管理中心中的联系人。 

## <a name="step-3-add-information-to-the-properties-of-the-external-contacts"></a>步骤 3: 将信息添加到外部联系人的属性中

在步骤2中运行该命令后, 将创建外部联系人, 但不包含任何联系人或组织信息, 这是来自 CSV 文件中的大多数单元格的信息。 这是因为在创建新的外部联系人时, 仅填充了所需的属性。 如果没有在 CSV 文件中填写所有信息, 请不要担心。 如果没有, 则不会添加。
  
1.  将 PowerShell 连接到您的 Exchange Online 组织。 有关分步说明, 请参阅[连接到 Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554)。
    
2. 转到在步骤1中保存 CSV 文件的 "桌面" 文件夹;例如`C:\Users\Administrator\desktop`。
    
3. 运行以下两个命令, 将其他属性从 CSV 文件添加到您在步骤2中创建的外部联系人。
    
    ```
    $Contacts = Import-CSV .\ExternalContacts.csv
  
    ```

    ```
    $contacts | ForEach {Set-Contact $_.Name -StreetAddress $_.StreetAddress -City $_.City -StateorProvince $_.StateorProvince -PostalCode $_.PostalCode -Phone $_.Phone -MobilePhone $_.MobilePhone -Pager $_.Pager -HomePhone $_.HomePhone -Company $_.Company -Title $_.Title -OtherTelephone $_.OtherTelephone -Department $_.Department -Fax $_.Fax -Initials $_.Initials -Notes  $_.Notes -Office $_.Office -Manager $_.Manager}
    ```

    > [!NOTE]
    > _Manager_参数可能有问题。 如果该单元格在 CSV 文件中为空, 则将收到错误, 并且不会向联系人添加任何属性信息。 如果不需要指定管理器, 则只需从以前` -Manager $_.Manager `的 PowerShell 命令中删除即可。 
  
    同样, 更新联系人可能需要一段时间, 具体取决于您在步骤1中导入的数量。 
    
4. 若要验证是否已将这些属性添加到联系人, 请执行以下操作: 
    
1. 在 EAC 中, 转到 "**收件人** \> " "**联系人**"。
    
2. 单击联系人, 然后单击 "**编辑** ![编辑图标](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) " 以显示联系人的属性。 
    
就是这么简单。 用户可以在通讯簿 Outlook 和 Outlook 网页中查看联系人和其他信息。
  
## <a name="add-more-external-contacts"></a>添加更多外部联系人

您可以重复步骤1到步骤 3, 在 Exchange Online 中添加新的外部联系人。 您或您的公司中的用户只需在 CSV 文件中为新联系人添加新行即可。 然后, 可以从步骤2和步骤3中运行 PowerShell 命令, 以创建新联系人并向其添加信息。
  
> [!NOTE]
> 运行命令以创建新联系人时, 您可能会收到一条错误消息, 指出之前创建的联系人已存在。 但会创建新的添加到 CSV 文件中的联系人。 
  
## <a name="hide-external-contacts-from-the-shared-address-book"></a>隐藏共享地址 book> 中的外部联系人。

某些公司可能仅使用外部联系人, 以便可以将其添加为通讯组的成员。 在这种情况下, 他们可能想要隐藏共享通讯簿中的外部联系人。 操作步骤如下：
  
1.  将 PowerShell 连接到您的 Exchange Online 组织。 有关分步说明, 请参阅[连接到 Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554)。
    
2. 若要隐藏单个外部联系人, 请运行以下命令。
    
    ```
    Set-MailContact <external contact> -HiddenFromAddressListsEnabled $true 
    ```
 
    例如, 若要隐藏共享通讯簿中的 Pilar Pinilla, 请运行以下命令:

    ```
    Set-MailContact "Pilar Pinilla" -HiddenFromAddressListsEnabled $true
    ```
   
3. 若要隐藏共享通讯簿中的所有外部联系人, 请运行以下命令:

    ```
    Get-Contact -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'MailContact')} | Set-MailContact -HiddenFromAddressListsEnabled $true  
    ```

隐藏这些联系人后, 不会在共享通讯簿中显示外部联系人, 但仍可将其添加为通讯组成员。
