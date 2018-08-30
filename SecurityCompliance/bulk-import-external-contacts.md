---
title: 批量导入到 Exchange Online 的外部联系人
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/29/2018
ms.audience: End User
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOP150
ms.assetid: bed936bc-0969-4a6d-a7a5-66305c14e958
description: 了解如何管理员可以使用 Exchange Online PowerShell 和 CSV 文件批量导入全局地址列表的外部联系人。
ms.openlocfilehash: 4bde56d49ccf94dc91993df90e1ae693e25c961a
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22524892"
---
# <a name="bulk-import-external-contacts-to-exchange-online"></a><span data-ttu-id="29cce-103">批量导入到 Exchange Online 的外部联系人</span><span class="sxs-lookup"><span data-stu-id="29cce-103">Bulk import external contacts to Exchange Online</span></span>

<span data-ttu-id="29cce-104">**本文是针对管理员。您试图将联系人导入到您自己的邮箱？请参阅[向 Outlook 导入联系人](https://support.office.com/article/bb796340-b58a-46c1-90c7-b549b8f3c5f8)**</span><span class="sxs-lookup"><span data-stu-id="29cce-104">**This article is for administrators. Are you trying to import contacts to your own mailbox? See [Import contacts to Outlook](https://support.office.com/article/bb796340-b58a-46c1-90c7-b549b8f3c5f8)**</span></span>
   
<span data-ttu-id="29cce-p101">贵公司是否在 Exchange Online 中有大量想要包含在共享的通讯簿 （也称为全局地址列表） 中的现有业务联系人？是否要为通讯组，就像您公司内可以与用户的成员添加外部联系人？如果是，您可以使用 Exchange Online PowerShell 和 CSV （逗号分隔值） 文件批量导入外部联系人 Exchange Online。它是三个步骤的过程：</span><span class="sxs-lookup"><span data-stu-id="29cce-p101">Does your company have lots of existing business contacts that you want to include in the shared address book (also called the global address list) in Exchange Online? Do you want to add external contacts as members of distribution groups, just like you can with users inside your company? If so, you can use Exchange Online PowerShell and a CSV (Comma Separated Value) file to bulk import external contacts into Exchange Online. It's a three-step process:</span></span>
  
[<span data-ttu-id="29cce-109">步骤 1： 创建 CSV 文件包含有关外部的联系人信息</span><span class="sxs-lookup"><span data-stu-id="29cce-109">Step 1: Create a CSV file that contains information about the external contacts</span></span>](#step-1-create-a-csv-file-that-contains-information-about-the-external-contacts)

[<span data-ttu-id="29cce-110">步骤 2： 使用 PowerShell 创建外部联系人</span><span class="sxs-lookup"><span data-stu-id="29cce-110">Step 2: Create the external contacts with PowerShell</span></span>](#step-2-create-the-external-contacts-with-powershell) 

[<span data-ttu-id="29cce-111">步骤 3： 将信息添加到的外部联系人属性</span><span class="sxs-lookup"><span data-stu-id="29cce-111">Step 3: Add information to the properties of the external contacts</span></span>](#step-3-add-information-to-the-properties-of-the-external-contacts)

<span data-ttu-id="29cce-112">完成这些步骤以导入联系人后，您可以执行这些其他任务：</span><span class="sxs-lookup"><span data-stu-id="29cce-112">After you complete these steps to import contacts, you can perform these additional tasks:</span></span>
  
- [<span data-ttu-id="29cce-113">添加多个外部联系人</span><span class="sxs-lookup"><span data-stu-id="29cce-113">Add more external contacts</span></span>](bulk-import-external-contacts.md#AddMore)
  
- [<span data-ttu-id="29cce-114">隐藏共享的通讯簿中的外部联系人</span><span class="sxs-lookup"><span data-stu-id="29cce-114">Hide external contacts from the shared address book</span></span>](bulk-import-external-contacts.md#Hide)
  
## <a name="step-1-create-a-csv-file-that-contains-information-about-the-external-contacts"></a><span data-ttu-id="29cce-115">步骤 1： 创建 CSV 文件包含有关外部的联系人信息</span><span class="sxs-lookup"><span data-stu-id="29cce-115">Step 1: Create a CSV file that contains information about the external contacts</span></span>

<span data-ttu-id="29cce-116">第一步是创建 CSV 文件包含有关您要导入到 Exchange Online 中的每个外部联系人信息。</span><span class="sxs-lookup"><span data-stu-id="29cce-116">The first step is to create a CSV file that contains information about each external contact that you want to import to Exchange Online.</span></span> 
  
1. <span data-ttu-id="29cce-117">将以下文本复制到文本文件在记事本中，并将其保存到您的桌面为 CSV 文件使用.csv; filename 后缀例如，ExternalContacts.csv。</span><span class="sxs-lookup"><span data-stu-id="29cce-117">Copy the following text to a text file in NotePad, and save it to your desktop as a CSV file by using a filename suffix of .csv; for example, ExternalContacts.csv.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="29cce-118">如果您的语言包含特殊字符 （例如**å**、 **ä**和瑞典语的**ö** ） 将该 CSV 文件以 utf-8 或其他 Unicode 编码，在记事本中保存文件时。</span><span class="sxs-lookup"><span data-stu-id="29cce-118">If your language contains special characters (such as **å**, **ä**, and **ö** in Swedish) save the CSV file with UTF-8 or other Unicode encoding when you save the file in NotePad.</span></span> 
  
    ```
    ExternalEmailAddress,Name,FirstName,LastName,StreetAddress,City,StateorProvince,PostalCode,Phone,MobilePhone,Pager,HomePhone,Company,Title,OtherTelephone,Department,CountryOrRegion,Fax,Initials,Notes,Office,Manager
    danp@fabrikam.com,Dan Park,Dan,Park,1234 23rd Ave,Golden,CO,80215,206-111-1234,303-900-1234,555-1212,123-456-7890,Fabrikam,Shipping clerk,555-5555,Shipping,US,123-4567,R.,Good worker,31/1663,Dan Park
    pilar@contoso.com,Pilar Pinilla,Pilar,Pinilla,1234 Main St.,Seattle,WA,98017,206-555-0100,206-555-0101,206-555-0102,206-555-1234,Contoso,HR Manager,206-555-0104,Executive,US,206-555-0105,P.,Technical decision maker,31/1000,Dan Park 
    ```

    <span data-ttu-id="29cce-p102">标题行，CSV 文件的第一行中，列出用于将其导入 Exchange Online 的联系人的属性。每个属性名称并用逗号分隔。在标题行下的每一行代表导入单个外部联系人的属性值。</span><span class="sxs-lookup"><span data-stu-id="29cce-p102">The first row, or header row, of the CSV file lists the properties of contacts that can be used when you import them to Exchange Online. Each property name is separated by a comma. Each row under the header row represents the property values for importing a single external contact.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="29cce-p103">此文本包含示例数据，您可以删除。但不要删除或更改首行 （标题）。它包含的所有外部联系人的属性。</span><span class="sxs-lookup"><span data-stu-id="29cce-p103">This text includes sample data, which you can delete. But don't delete or change the first (header) row. It contains all of the properties for the external contacts.</span></span> 
  
2. <span data-ttu-id="29cce-125">在 Microsoft Excel 编辑 CSV 文件，因为它是更易于使用 Excel 编辑 CSV 文件中打开该 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="29cce-125">Open the CSV file in Microsoft Excel to edit the CSV file because it's much easier to use Excel to edit the CSV file.</span></span>
    
3. <span data-ttu-id="29cce-p104">创建每个联系人，您希望导入到 Exchange Online 的行。填充尽可能多的尽可能的单元格。将每个联系人共享的通讯簿中显示此信息。</span><span class="sxs-lookup"><span data-stu-id="29cce-p104">Create a row for each contact that you want to import to Exchange Online. Populate as many of the cells as possible. This information will be displayed in the shared address book for each contact.</span></span> 
    
    > [!IMPORTANT]
    >  <span data-ttu-id="29cce-p105">下列属性 （即标题行中的前四个项目） 所需创建外部联系人和必须在 CSV 文件中填充： **ExternalEmailAddress**、 **Name**、 **FirstName**、 **LastName**。在步骤 2 中运行的 PowerShell 命令将使用这些属性的值创建联系人。</span><span class="sxs-lookup"><span data-stu-id="29cce-p105">The following properties (which are the first four items in the header row) are required to create an external contact and must be populated in the CSV file: **ExternalEmailAddress**, **Name**, **FirstName**, **LastName**. The PowerShell command that you run in Step 2 will use the values for these properties to create the contacts.</span></span> 

## <a name="step-2-create-the-external-contacts-with-powershell"></a><span data-ttu-id="29cce-131">步骤 2： 使用 PowerShell 创建外部联系人</span><span class="sxs-lookup"><span data-stu-id="29cce-131">Step 2: Create the external contacts with PowerShell</span></span>

<span data-ttu-id="29cce-132">下一步是使用您在步骤 1 中创建 CSV 文件和 PowerShell 批量导入到 Exchange Online 的 CSV 文件中列出的外部联系人。</span><span class="sxs-lookup"><span data-stu-id="29cce-132">The next step is to use the CSV file that you created in Step 1 and PowerShell to bulk import the external contacts listed in the CSV file to Exchange Online.</span></span> 
  
1.  <span data-ttu-id="29cce-p106">将 PowerShell 连接到 Exchange Online 组织。有关分步说明，请参阅[Connect to Exchange Online PowerShell 中](https://go.microsoft.com/fwlink/p/?LinkId=396554)。请务必时连接到 Exchange Online PowerShell 中的 Office 365 全局管理员帐户使用的用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="29cce-p106">Connect PowerShell to your Exchange Online organization. For step-by-step instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554). Be sure to use the user name and password for your Office 365 global administrator account when you connect to Exchange Online PowerShell.</span></span> 
    
2. <span data-ttu-id="29cce-136">将 PowerShell 连接到 Exchange Online 后，转到桌面文件夹在步骤 1; 中保存 CSV 文件的位置例如`C:\Users\Administrator\desktop`。</span><span class="sxs-lookup"><span data-stu-id="29cce-136">After you connect PowerShell to Exchange Online, go to the desktop folder where you saved the CSV file in Step 1; for example `C:\Users\Administrator\desktop`.</span></span>
    
3. <span data-ttu-id="29cce-137">运行以下命令以创建外部联系人：</span><span class="sxs-lookup"><span data-stu-id="29cce-137">Run the following command to create the external contacts:</span></span>

    ```
    Import-Csv .\ExternalContacts.csv|%{New-MailContact -Name $_.Name -DisplayName $_.Name -ExternalEmailAddress $_.ExternalEmailAddress -FirstName $_.FirstName -LastName $_.LastName}
    ```

    <span data-ttu-id="29cce-p107">可能需要一段时间才能创建新的联系人，具体取决于多少您正在导入。该命令完成时运行，PowerShell 显示创建新联系人的列表。</span><span class="sxs-lookup"><span data-stu-id="29cce-p107">It might take a while to create the new contacts, depending on how many you're importing. When the command is finished running, PowerShell displays a list of the new contacts that were created.</span></span> 
    
4. <span data-ttu-id="29cce-140">要查看新的外部联系人，请转到 Exchange 管理员中心 (EAC) 中，，然后单击**收件人** \> **联系人**。</span><span class="sxs-lookup"><span data-stu-id="29cce-140">To view the new external contacts, go to the Exchange admin center (EAC), and then click **Recipients** \> **Contacts**.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="29cce-141">用于连接到 EAC 中的说明，请参阅[Exchange admin center 在 Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=328197)。</span><span class="sxs-lookup"><span data-stu-id="29cce-141">For instructions for connecting to the EAC, see [Exchange admin center in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=328197).</span></span> 
  
5. <span data-ttu-id="29cce-142">如有必要，单击**刷新**![刷新图标](media/O365-MDM-Policy-RefreshIcon.gif)更新列表和查看已导入的外部联系人。</span><span class="sxs-lookup"><span data-stu-id="29cce-142">If necessary, click **Refresh** ![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) to update the list and see the external contacts that were imported.</span></span> 
    
    <span data-ttu-id="29cce-143">导入的联系人将出现在 Outlook 和 Outlook web 上的共享的通讯簿。</span><span class="sxs-lookup"><span data-stu-id="29cce-143">The imported contacts will appear in the shared address book in Outlook and Outlook on the web.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="29cce-144">您还可以查看联系人在 Office 365 管理中心，转到**用户** \> **联系人**。</span><span class="sxs-lookup"><span data-stu-id="29cce-144">You can also view the contacts in the Office 365 admin center by going to **Users** \> **Contacts**.</span></span> 

## <a name="step-3-add-information-to-the-properties-of-the-external-contacts"></a><span data-ttu-id="29cce-145">步骤 3： 将信息添加到的外部联系人属性</span><span class="sxs-lookup"><span data-stu-id="29cce-145">Step 3: Add information to the properties of the external contacts</span></span>

<span data-ttu-id="29cce-p108">在步骤 2 中运行该命令后，创建外部联系人，但它们不包含的任何联系人或组织信息，即从 CSV 文件中的单元格的最多的信息。这是因为创建新外部联系人时，会填充所需的属性。如果您没有填充该 CSV 文件中的所有信息，请不要担心。如果没有，不会将其进行添加。</span><span class="sxs-lookup"><span data-stu-id="29cce-p108">After you run the command in Step 2, the external contacts are created, but they don't contain any of the contact or organization information, which is the information from the most of the cells in the CSV file. This is because when you create new external contacts, only the required properties are populated. Don't worry if you don't have all the information populated in the CSV file. If it's not there, it won't be added.</span></span>
  
1.  <span data-ttu-id="29cce-p109">将 PowerShell 连接到 Exchange Online 组织。有关分步说明，请参阅[Connect to Exchange Online PowerShell 中](https://go.microsoft.com/fwlink/p/?LinkId=396554)。</span><span class="sxs-lookup"><span data-stu-id="29cce-p109">Connect PowerShell to your Exchange Online organization. For step-by-step instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span>
    
2. <span data-ttu-id="29cce-152">转到桌面文件夹在步骤 1; 中保存 CSV 文件的位置例如`C:\Users\Administrator\desktop`。</span><span class="sxs-lookup"><span data-stu-id="29cce-152">Go to the desktop folder where you saved the CSV file in Step 1; for example `C:\Users\Administrator\desktop`.</span></span>
    
3. <span data-ttu-id="29cce-153">运行以下两个命令中的 CSV 文件的其他属性添加到您在步骤 2 中创建的外部联系人。</span><span class="sxs-lookup"><span data-stu-id="29cce-153">Run the following two commands to add the other properties from the CSV file to the external contacts that you created in Step 2.</span></span>
    
    ```
    $Contacts = Import-CSV .\ExternalContacts.csv
  
    ```

    ```
    $contacts | ForEach {Set-Contact $_.Name -StreetAddress $_.StreetAddress -City $_.City -StateorProvince $_.StateorProvince -PostalCode $_.PostalCode -Phone $_.Phone -MobilePhone $_.MobilePhone -Pager $_.Pager -HomePhone $_.HomePhone -Company $_.Company -Title $_.Title -OtherTelephone $_.OtherTelephone -Department $_.Department -Fax $_.Fax -Initials $_.Initials -Notes  $_.Notes -Office $_.Office -Manager $_.Manager}
    ```

    > [!NOTE]
    > <span data-ttu-id="29cce-p110">_Manager_参数可能有问题。如果该 CSV 文件中，单元格为空，则会收到错误和无属性信息将添加到联系人。如果您不需要指定管理器，然后只删除` -Manager $_.Manager `从以前的 PowerShell 命令。</span><span class="sxs-lookup"><span data-stu-id="29cce-p110">The  _Manager_ parameter might be problematic. If the cell is blank in the CSV file, you will get an error and none of the property information will be added to the contact. If you don't need to specify a manager, then just delete  ` -Manager $_.Manager ` from the previous PowerShell command.</span></span> 
  
    <span data-ttu-id="29cce-157">同样，它可能需要一些时间来更新联系人，具体取决于多少导入在步骤 1 中。</span><span class="sxs-lookup"><span data-stu-id="29cce-157">Again, it might take a while to update the contacts, depending on how many you imported in Step 1.</span></span> 
    
4. <span data-ttu-id="29cce-158">若要验证属性已添加到联系人：</span><span class="sxs-lookup"><span data-stu-id="29cce-158">To verify that the properties were added to the contacts:</span></span> 
    
1. <span data-ttu-id="29cce-159">在 EAC 中，转到**收件人** \> **联系人**。</span><span class="sxs-lookup"><span data-stu-id="29cce-159">In the EAC, go to **Recipients** \> **Contacts**.</span></span>
    
2. <span data-ttu-id="29cce-160">单击联系人，然后单击**编辑**![编辑图标](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)显示联系人的属性。</span><span class="sxs-lookup"><span data-stu-id="29cce-160">Click a contact and then click **Edit** ![Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) to display the contact's properties.</span></span> 
    
<span data-ttu-id="29cce-p111">就是这样！用户可以看到联系人的通讯簿 Outlook 中的其他信息和 Outlook web 上。</span><span class="sxs-lookup"><span data-stu-id="29cce-p111">That's it! Users can see the contacts and the additional information in the address book Outlook and Outlook on the web.</span></span>
  
## <a name="add-more-external-contacts"></a><span data-ttu-id="29cce-163">添加多个外部联系人</span><span class="sxs-lookup"><span data-stu-id="29cce-163">Add more external contacts</span></span>

<span data-ttu-id="29cce-p112">您可以重复步骤 1 至步骤 3 中添加新外部联系人在 Exchange Online。您或贵公司内的用户可以只需将新联系人的 CSV 文件中添加新行。然后您可以运行 PowerShell 命令从步骤 2 和步骤 3，创建并将信息添加到新的联系人。</span><span class="sxs-lookup"><span data-stu-id="29cce-p112">You can repeat Steps 1 through Step 3 to add new external contacts in Exchange Online. You or users in your company can just add a new row in the CSV file for the new contact. Then you can run the PowerShell commands from Step 2 and Step 3 to create and add information to the new contacts.</span></span>
  
> [!NOTE]
> <span data-ttu-id="29cce-p113">运行该命令以创建新联系人时，您可能收到指出先前已创建的联系人存在错误。而是创建任何新的联系人添加到 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="29cce-p113">When you run the command to create new contacts, you might get an error saying that the contacts that were created earlier already exist. But any new contact added to the CSV file is created.</span></span> 
  
## <a name="hide-external-contacts-from-the-shared-address-book"></a><span data-ttu-id="29cce-169">隐藏共享的通讯簿中的外部联系人 ></span><span class="sxs-lookup"><span data-stu-id="29cce-169">Hide external contacts from the shared address book></span></span>

<span data-ttu-id="29cce-p114">一些公司可以使用外部联系人仅以便他们可以添加为通讯组的成员。在此方案中，它们可能希望隐藏共享的通讯簿中的外部联系人。下面是如何：</span><span class="sxs-lookup"><span data-stu-id="29cce-p114">Some companies may use external contacts only so they can be added as members of distribution groups. In this scenario, they may want to hide external contacts from the shared address book. Here's how:</span></span>
  
1.  <span data-ttu-id="29cce-p115">将 PowerShell 连接到 Exchange Online 组织。有关分步说明，请参阅[Connect to Exchange Online PowerShell 中](https://go.microsoft.com/fwlink/p/?LinkId=396554)。</span><span class="sxs-lookup"><span data-stu-id="29cce-p115">Connect PowerShell to your Exchange Online organization. For step-by-step instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span>
    
2. <span data-ttu-id="29cce-175">若要隐藏单个外部联系人，请运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="29cce-175">To hide a single external contact, run the following command.</span></span>
    
    ```
    Set-MailContact <external contact> -HiddenFromAddressListsEnabled $true 
    ```
 
    <span data-ttu-id="29cce-176">例如，若要从共享的通讯簿中隐藏 Pilar Pinilla，运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="29cce-176">For example, to hide Pilar Pinilla from the shared address book, run this command:</span></span>

    ```
    Set-MailContact "Pilar Pinilla" -HiddenFromAddressListsEnabled $true
    ```
   
3. <span data-ttu-id="29cce-177">若要隐藏共享的通讯簿中的所有外部联系人，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="29cce-177">To hide all external contacts from the shared address book, run this command:</span></span>

    ```
    Get-Contact -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'MailContact')} | Set-MailContact -HiddenFromAddressListsEnabled $true  
    ```

<span data-ttu-id="29cce-178">隐藏它们后，外部联系人不会显示在共享的通讯簿中，但仍可以将其添加为通讯组的成员。</span><span class="sxs-lookup"><span data-stu-id="29cce-178">After you hide them, external contacts aren't displayed in the shared address book, but you can still add them as members of a distribution group.</span></span>
