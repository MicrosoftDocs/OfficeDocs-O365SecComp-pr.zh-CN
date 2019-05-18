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
# <a name="bulk-import-external-contacts-to-exchange-online"></a><span data-ttu-id="c9a62-103">将外部联系人批量导入到 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="c9a62-103">Bulk import external contacts to Exchange Online</span></span>

<span data-ttu-id="c9a62-104">**本文适用于管理员。您是否正在尝试将联系人导入您自己的邮箱？请参阅[将联系人导入到 Outlook](https://support.office.com/article/bb796340-b58a-46c1-90c7-b549b8f3c5f8)**</span><span class="sxs-lookup"><span data-stu-id="c9a62-104">**This article is for administrators. Are you trying to import contacts to your own mailbox? See [Import contacts to Outlook](https://support.office.com/article/bb796340-b58a-46c1-90c7-b549b8f3c5f8)**</span></span>
   
<span data-ttu-id="c9a62-105">您的公司是否有许多您想要在 Exchange Online 中的共享通讯簿 (也称为 "全局地址列表") 中包含的现有业务联系人？</span><span class="sxs-lookup"><span data-stu-id="c9a62-105">Does your company have lots of existing business contacts that you want to include in the shared address book (also called the global address list) in Exchange Online?</span></span> <span data-ttu-id="c9a62-106">您是否要将外部联系人添加为通讯组的成员, 就像您可以与公司内部的用户进行操作一样？</span><span class="sxs-lookup"><span data-stu-id="c9a62-106">Do you want to add external contacts as members of distribution groups, just like you can with users inside your company?</span></span> <span data-ttu-id="c9a62-107">如果是这样, 您可以使用 Exchange Online PowerShell 和 CSV (逗号分隔值) 文件将外部联系人批量导入 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="c9a62-107">If so, you can use Exchange Online PowerShell and a CSV (Comma Separated Value) file to bulk import external contacts into Exchange Online.</span></span> <span data-ttu-id="c9a62-108">这是一个包含三个步骤的过程:</span><span class="sxs-lookup"><span data-stu-id="c9a62-108">It's a three-step process:</span></span>
  
[<span data-ttu-id="c9a62-109">步骤 1: 创建包含有关外部联系人的信息的 CSV 文件</span><span class="sxs-lookup"><span data-stu-id="c9a62-109">Step 1: Create a CSV file that contains information about the external contacts</span></span>](#step-1-create-a-csv-file-that-contains-information-about-the-external-contacts)

[<span data-ttu-id="c9a62-110">步骤 2: 使用 PowerShell 创建外部联系人</span><span class="sxs-lookup"><span data-stu-id="c9a62-110">Step 2: Create the external contacts with PowerShell</span></span>](#step-2-create-the-external-contacts-with-powershell) 

[<span data-ttu-id="c9a62-111">步骤 3: 将信息添加到外部联系人的属性中</span><span class="sxs-lookup"><span data-stu-id="c9a62-111">Step 3: Add information to the properties of the external contacts</span></span>](#step-3-add-information-to-the-properties-of-the-external-contacts)

<span data-ttu-id="c9a62-112">完成这些步骤以导入联系人后, 可以执行以下其他任务:</span><span class="sxs-lookup"><span data-stu-id="c9a62-112">After you complete these steps to import contacts, you can perform these additional tasks:</span></span>
  
- [<span data-ttu-id="c9a62-113">添加更多外部联系人</span><span class="sxs-lookup"><span data-stu-id="c9a62-113">Add more external contacts</span></span>](#add-more-external-contacts)
  
- [<span data-ttu-id="c9a62-114">隐藏共享通讯簿中的外部联系人</span><span class="sxs-lookup"><span data-stu-id="c9a62-114">Hide external contacts from the shared address book</span></span>](#hide-external-contacts-from-the-shared-address-book)
  
## <a name="step-1-create-a-csv-file-that-contains-information-about-the-external-contacts"></a><span data-ttu-id="c9a62-115">步骤 1: 创建包含有关外部联系人的信息的 CSV 文件</span><span class="sxs-lookup"><span data-stu-id="c9a62-115">Step 1: Create a CSV file that contains information about the external contacts</span></span>

<span data-ttu-id="c9a62-116">第一步是创建一个 CSV 文件, 其中包含有关要导入到 Exchange Online 的每个外部联系人的信息。</span><span class="sxs-lookup"><span data-stu-id="c9a62-116">The first step is to create a CSV file that contains information about each external contact that you want to import to Exchange Online.</span></span> 
  
1. <span data-ttu-id="c9a62-117">将以下文本复制到记事本中的文本文件, 并使用文件名后缀 .csv 将其以 CSV 文件的形式保存到您的桌面。例如, ExternalContacts。</span><span class="sxs-lookup"><span data-stu-id="c9a62-117">Copy the following text to a text file in NotePad, and save it to your desktop as a CSV file by using a filename suffix of .csv; for example, ExternalContacts.csv.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="c9a62-118">如果您的语言包含特殊字符 (例如, **å**、 **ä**和**ö** in 瑞典语), 则在记事本中保存文件时, 请使用 UTF-8 或其他 Unicode 编码保存 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="c9a62-118">If your language contains special characters (such as **å**, **ä**, and **ö** in Swedish) save the CSV file with UTF-8 or other Unicode encoding when you save the file in NotePad.</span></span> 
  
    ```
    ExternalEmailAddress,Name,FirstName,LastName,StreetAddress,City,StateorProvince,PostalCode,Phone,MobilePhone,Pager,HomePhone,Company,Title,OtherTelephone,Department,CountryOrRegion,Fax,Initials,Notes,Office,Manager
    danp@fabrikam.com,Dan Park,Dan,Park,1234 23rd Ave,Golden,CO,80215,206-111-1234,303-900-1234,555-1212,123-456-7890,Fabrikam,Shipping clerk,555-5555,Shipping,US,123-4567,R.,Good worker,31/1663,Dan Park
    pilar@contoso.com,Pilar Pinilla,Pilar,Pinilla,1234 Main St.,Seattle,WA,98017,206-555-0100,206-555-0101,206-555-0102,206-555-1234,Contoso,HR Manager,206-555-0104,Executive,US,206-555-0105,P.,Technical decision maker,31/1000,Dan Park 
    ```

    <span data-ttu-id="c9a62-119">CSV 文件的第一行 (即标题行) 列出了在将联系人导入 Exchange Online 时可使用的联系人的属性。</span><span class="sxs-lookup"><span data-stu-id="c9a62-119">The first row, or header row, of the CSV file lists the properties of contacts that can be used when you import them to Exchange Online.</span></span> <span data-ttu-id="c9a62-120">每个属性名称都用逗号分隔。</span><span class="sxs-lookup"><span data-stu-id="c9a62-120">Each property name is separated by a comma.</span></span> <span data-ttu-id="c9a62-121">标题行下的每一行表示用于导入单个外部联系人的属性值。</span><span class="sxs-lookup"><span data-stu-id="c9a62-121">Each row under the header row represents the property values for importing a single external contact.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="c9a62-122">此文本包含可删除的示例数据。</span><span class="sxs-lookup"><span data-stu-id="c9a62-122">This text includes sample data, which you can delete.</span></span> <span data-ttu-id="c9a62-123">但不要删除或更改第一个 (标头) 行。</span><span class="sxs-lookup"><span data-stu-id="c9a62-123">But don't delete or change the first (header) row.</span></span> <span data-ttu-id="c9a62-124">它包含外部联系人的所有属性。</span><span class="sxs-lookup"><span data-stu-id="c9a62-124">It contains all of the properties for the external contacts.</span></span> 
  
2. <span data-ttu-id="c9a62-125">在 Microsoft Excel 中打开 CSV 文件以编辑 CSV 文件, 因为使用 Excel 编辑 CSV 文件要容易得多。</span><span class="sxs-lookup"><span data-stu-id="c9a62-125">Open the CSV file in Microsoft Excel to edit the CSV file because it's much easier to use Excel to edit the CSV file.</span></span>
    
3. <span data-ttu-id="c9a62-126">为要导入到 Exchange Online 中的每个联系人创建一行。</span><span class="sxs-lookup"><span data-stu-id="c9a62-126">Create a row for each contact that you want to import to Exchange Online.</span></span> <span data-ttu-id="c9a62-127">填充尽可能多的单元格。</span><span class="sxs-lookup"><span data-stu-id="c9a62-127">Populate as many of the cells as possible.</span></span> <span data-ttu-id="c9a62-128">此信息将显示在每个联系人的共享通讯簿中。</span><span class="sxs-lookup"><span data-stu-id="c9a62-128">This information will be displayed in the shared address book for each contact.</span></span> 
    
    > [!IMPORTANT]
    >  <span data-ttu-id="c9a62-129">以下属性 (标题行中的前四项) 是创建外部联系人所必需的, 并且必须在 CSV 文件中进行填充: **ExternalEmailAddress**、 **Name**、 **FirstName**和**LastName**。</span><span class="sxs-lookup"><span data-stu-id="c9a62-129">The following properties (which are the first four items in the header row) are required to create an external contact and must be populated in the CSV file: **ExternalEmailAddress**, **Name**, **FirstName**, **LastName**.</span></span> <span data-ttu-id="c9a62-130">您在步骤2中运行的 PowerShell 命令将使用这些属性的值来创建联系人。</span><span class="sxs-lookup"><span data-stu-id="c9a62-130">The PowerShell command that you run in Step 2 will use the values for these properties to create the contacts.</span></span> 

## <a name="step-2-create-the-external-contacts-with-powershell"></a><span data-ttu-id="c9a62-131">步骤 2: 使用 PowerShell 创建外部联系人</span><span class="sxs-lookup"><span data-stu-id="c9a62-131">Step 2: Create the external contacts with PowerShell</span></span>

<span data-ttu-id="c9a62-132">下一步是使用您在步骤1和 PowerShell 中创建的 CSV 文件以批量将 CSV 文件中列出的外部联系人导入到 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="c9a62-132">The next step is to use the CSV file that you created in Step 1 and PowerShell to bulk import the external contacts listed in the CSV file to Exchange Online.</span></span> 
  
1.  <span data-ttu-id="c9a62-133">将 PowerShell 连接到您的 Exchange Online 组织。</span><span class="sxs-lookup"><span data-stu-id="c9a62-133">Connect PowerShell to your Exchange Online organization.</span></span> <span data-ttu-id="c9a62-134">有关分步说明, 请参阅[连接到 Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554)。</span><span class="sxs-lookup"><span data-stu-id="c9a62-134">For step-by-step instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span> <span data-ttu-id="c9a62-135">在连接到 Exchange Online PowerShell 时, 请务必使用 Office 365 全局管理员帐户的用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="c9a62-135">Be sure to use the user name and password for your Office 365 global administrator account when you connect to Exchange Online PowerShell.</span></span> 
    
2. <span data-ttu-id="c9a62-136">将 PowerShell 连接到 Exchange Online 后, 请转到在步骤1中保存 CSV 文件的桌面文件夹;例如`C:\Users\Administrator\desktop`。</span><span class="sxs-lookup"><span data-stu-id="c9a62-136">After you connect PowerShell to Exchange Online, go to the desktop folder where you saved the CSV file in Step 1; for example `C:\Users\Administrator\desktop`.</span></span>
    
3. <span data-ttu-id="c9a62-137">运行以下命令以创建外部联系人:</span><span class="sxs-lookup"><span data-stu-id="c9a62-137">Run the following command to create the external contacts:</span></span>

    ```
    Import-Csv .\ExternalContacts.csv|%{New-MailContact -Name $_.Name -DisplayName $_.Name -ExternalEmailAddress $_.ExternalEmailAddress -FirstName $_.FirstName -LastName $_.LastName}
    ```

    <span data-ttu-id="c9a62-138">创建新联系人可能需要一段时间, 具体取决于您导入的数量。</span><span class="sxs-lookup"><span data-stu-id="c9a62-138">It might take a while to create the new contacts, depending on how many you're importing.</span></span> <span data-ttu-id="c9a62-139">命令运行完毕后, PowerShell 将显示已创建的新联系人的列表。</span><span class="sxs-lookup"><span data-stu-id="c9a62-139">When the command is finished running, PowerShell displays a list of the new contacts that were created.</span></span> 
    
4. <span data-ttu-id="c9a62-140">若要查看新的外部联系人, 请转到 Exchange 管理中心 (EAC), 然后单击 "**收件人** \> **联系人**"。</span><span class="sxs-lookup"><span data-stu-id="c9a62-140">To view the new external contacts, go to the Exchange admin center (EAC), and then click **Recipients** \> **Contacts**.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="c9a62-141">有关连接到 EAC 的说明, 请参阅 exchange [Online 中的 exchange 管理中心](https://go.microsoft.com/fwlink/p/?LinkId=328197)。</span><span class="sxs-lookup"><span data-stu-id="c9a62-141">For instructions for connecting to the EAC, see [Exchange admin center in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=328197).</span></span> 
  
5. <span data-ttu-id="c9a62-142">如有必要, \*\*\*\* ![请单击 "](media/O365-MDM-Policy-RefreshIcon.gif)刷新刷新" 图标更新列表, 并查看导入的外部联系人。</span><span class="sxs-lookup"><span data-stu-id="c9a62-142">If necessary, click **Refresh** ![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) to update the list and see the external contacts that were imported.</span></span> 
    
    <span data-ttu-id="c9a62-143">导入的联系人将显示在 Outlook 和 web 上的 Outlook 中的共享通讯簿中。</span><span class="sxs-lookup"><span data-stu-id="c9a62-143">The imported contacts will appear in the shared address book in Outlook and Outlook on the web.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c9a62-144">您还可以通过转到 "**用户** \> **联系人**" 查看 Microsoft 365 管理中心中的联系人。</span><span class="sxs-lookup"><span data-stu-id="c9a62-144">You can also view the contacts in the Microsoft 365 admin center by going to **Users** \> **Contacts**.</span></span> 

## <a name="step-3-add-information-to-the-properties-of-the-external-contacts"></a><span data-ttu-id="c9a62-145">步骤 3: 将信息添加到外部联系人的属性中</span><span class="sxs-lookup"><span data-stu-id="c9a62-145">Step 3: Add information to the properties of the external contacts</span></span>

<span data-ttu-id="c9a62-146">在步骤2中运行该命令后, 将创建外部联系人, 但不包含任何联系人或组织信息, 这是来自 CSV 文件中的大多数单元格的信息。</span><span class="sxs-lookup"><span data-stu-id="c9a62-146">After you run the command in Step 2, the external contacts are created, but they don't contain any of the contact or organization information, which is the information from the most of the cells in the CSV file.</span></span> <span data-ttu-id="c9a62-147">这是因为在创建新的外部联系人时, 仅填充了所需的属性。</span><span class="sxs-lookup"><span data-stu-id="c9a62-147">This is because when you create new external contacts, only the required properties are populated.</span></span> <span data-ttu-id="c9a62-148">如果没有在 CSV 文件中填写所有信息, 请不要担心。</span><span class="sxs-lookup"><span data-stu-id="c9a62-148">Don't worry if you don't have all the information populated in the CSV file.</span></span> <span data-ttu-id="c9a62-149">如果没有, 则不会添加。</span><span class="sxs-lookup"><span data-stu-id="c9a62-149">If it's not there, it won't be added.</span></span>
  
1.  <span data-ttu-id="c9a62-150">将 PowerShell 连接到您的 Exchange Online 组织。</span><span class="sxs-lookup"><span data-stu-id="c9a62-150">Connect PowerShell to your Exchange Online organization.</span></span> <span data-ttu-id="c9a62-151">有关分步说明, 请参阅[连接到 Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554)。</span><span class="sxs-lookup"><span data-stu-id="c9a62-151">For step-by-step instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span>
    
2. <span data-ttu-id="c9a62-152">转到在步骤1中保存 CSV 文件的 "桌面" 文件夹;例如`C:\Users\Administrator\desktop`。</span><span class="sxs-lookup"><span data-stu-id="c9a62-152">Go to the desktop folder where you saved the CSV file in Step 1; for example `C:\Users\Administrator\desktop`.</span></span>
    
3. <span data-ttu-id="c9a62-153">运行以下两个命令, 将其他属性从 CSV 文件添加到您在步骤2中创建的外部联系人。</span><span class="sxs-lookup"><span data-stu-id="c9a62-153">Run the following two commands to add the other properties from the CSV file to the external contacts that you created in Step 2.</span></span>
    
    ```
    $Contacts = Import-CSV .\ExternalContacts.csv
  
    ```

    ```
    $contacts | ForEach {Set-Contact $_.Name -StreetAddress $_.StreetAddress -City $_.City -StateorProvince $_.StateorProvince -PostalCode $_.PostalCode -Phone $_.Phone -MobilePhone $_.MobilePhone -Pager $_.Pager -HomePhone $_.HomePhone -Company $_.Company -Title $_.Title -OtherTelephone $_.OtherTelephone -Department $_.Department -Fax $_.Fax -Initials $_.Initials -Notes  $_.Notes -Office $_.Office -Manager $_.Manager}
    ```

    > [!NOTE]
    > <span data-ttu-id="c9a62-154">_Manager_参数可能有问题。</span><span class="sxs-lookup"><span data-stu-id="c9a62-154">The  _Manager_ parameter might be problematic.</span></span> <span data-ttu-id="c9a62-155">如果该单元格在 CSV 文件中为空, 则将收到错误, 并且不会向联系人添加任何属性信息。</span><span class="sxs-lookup"><span data-stu-id="c9a62-155">If the cell is blank in the CSV file, you will get an error and none of the property information will be added to the contact.</span></span> <span data-ttu-id="c9a62-156">如果不需要指定管理器, 则只需从以前` -Manager $_.Manager `的 PowerShell 命令中删除即可。</span><span class="sxs-lookup"><span data-stu-id="c9a62-156">If you don't need to specify a manager, then just delete  ` -Manager $_.Manager ` from the previous PowerShell command.</span></span> 
  
    <span data-ttu-id="c9a62-157">同样, 更新联系人可能需要一段时间, 具体取决于您在步骤1中导入的数量。</span><span class="sxs-lookup"><span data-stu-id="c9a62-157">Again, it might take a while to update the contacts, depending on how many you imported in Step 1.</span></span> 
    
4. <span data-ttu-id="c9a62-158">若要验证是否已将这些属性添加到联系人, 请执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="c9a62-158">To verify that the properties were added to the contacts:</span></span> 
    
1. <span data-ttu-id="c9a62-159">在 EAC 中, 转到 "**收件人** \> " "**联系人**"。</span><span class="sxs-lookup"><span data-stu-id="c9a62-159">In the EAC, go to **Recipients** \> **Contacts**.</span></span>
    
2. <span data-ttu-id="c9a62-160">单击联系人, 然后单击 "**编辑** ![编辑图标](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) " 以显示联系人的属性。</span><span class="sxs-lookup"><span data-stu-id="c9a62-160">Click a contact and then click **Edit** ![Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) to display the contact's properties.</span></span> 
    
<span data-ttu-id="c9a62-161">就是这么简单。</span><span class="sxs-lookup"><span data-stu-id="c9a62-161">That's it!</span></span> <span data-ttu-id="c9a62-162">用户可以在通讯簿 Outlook 和 Outlook 网页中查看联系人和其他信息。</span><span class="sxs-lookup"><span data-stu-id="c9a62-162">Users can see the contacts and the additional information in the address book Outlook and Outlook on the web.</span></span>
  
## <a name="add-more-external-contacts"></a><span data-ttu-id="c9a62-163">添加更多外部联系人</span><span class="sxs-lookup"><span data-stu-id="c9a62-163">Add more external contacts</span></span>

<span data-ttu-id="c9a62-164">您可以重复步骤1到步骤 3, 在 Exchange Online 中添加新的外部联系人。</span><span class="sxs-lookup"><span data-stu-id="c9a62-164">You can repeat Steps 1 through Step 3 to add new external contacts in Exchange Online.</span></span> <span data-ttu-id="c9a62-165">您或您的公司中的用户只需在 CSV 文件中为新联系人添加新行即可。</span><span class="sxs-lookup"><span data-stu-id="c9a62-165">You or users in your company can just add a new row in the CSV file for the new contact.</span></span> <span data-ttu-id="c9a62-166">然后, 可以从步骤2和步骤3中运行 PowerShell 命令, 以创建新联系人并向其添加信息。</span><span class="sxs-lookup"><span data-stu-id="c9a62-166">Then you can run the PowerShell commands from Step 2 and Step 3 to create and add information to the new contacts.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c9a62-167">运行命令以创建新联系人时, 您可能会收到一条错误消息, 指出之前创建的联系人已存在。</span><span class="sxs-lookup"><span data-stu-id="c9a62-167">When you run the command to create new contacts, you might get an error saying that the contacts that were created earlier already exist.</span></span> <span data-ttu-id="c9a62-168">但会创建新的添加到 CSV 文件中的联系人。</span><span class="sxs-lookup"><span data-stu-id="c9a62-168">But any new contact added to the CSV file is created.</span></span> 
  
## <a name="hide-external-contacts-from-the-shared-address-book"></a><span data-ttu-id="c9a62-169">隐藏共享地址 book> 中的外部联系人。</span><span class="sxs-lookup"><span data-stu-id="c9a62-169">Hide external contacts from the shared address book></span></span>

<span data-ttu-id="c9a62-170">某些公司可能仅使用外部联系人, 以便可以将其添加为通讯组的成员。</span><span class="sxs-lookup"><span data-stu-id="c9a62-170">Some companies may use external contacts only so they can be added as members of distribution groups.</span></span> <span data-ttu-id="c9a62-171">在这种情况下, 他们可能想要隐藏共享通讯簿中的外部联系人。</span><span class="sxs-lookup"><span data-stu-id="c9a62-171">In this scenario, they may want to hide external contacts from the shared address book.</span></span> <span data-ttu-id="c9a62-172">操作步骤如下：</span><span class="sxs-lookup"><span data-stu-id="c9a62-172">Here's how:</span></span>
  
1.  <span data-ttu-id="c9a62-173">将 PowerShell 连接到您的 Exchange Online 组织。</span><span class="sxs-lookup"><span data-stu-id="c9a62-173">Connect PowerShell to your Exchange Online organization.</span></span> <span data-ttu-id="c9a62-174">有关分步说明, 请参阅[连接到 Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554)。</span><span class="sxs-lookup"><span data-stu-id="c9a62-174">For step-by-step instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span>
    
2. <span data-ttu-id="c9a62-175">若要隐藏单个外部联系人, 请运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="c9a62-175">To hide a single external contact, run the following command.</span></span>
    
    ```
    Set-MailContact <external contact> -HiddenFromAddressListsEnabled $true 
    ```
 
    <span data-ttu-id="c9a62-176">例如, 若要隐藏共享通讯簿中的 Pilar Pinilla, 请运行以下命令:</span><span class="sxs-lookup"><span data-stu-id="c9a62-176">For example, to hide Pilar Pinilla from the shared address book, run this command:</span></span>

    ```
    Set-MailContact "Pilar Pinilla" -HiddenFromAddressListsEnabled $true
    ```
   
3. <span data-ttu-id="c9a62-177">若要隐藏共享通讯簿中的所有外部联系人, 请运行以下命令:</span><span class="sxs-lookup"><span data-stu-id="c9a62-177">To hide all external contacts from the shared address book, run this command:</span></span>

    ```
    Get-Contact -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'MailContact')} | Set-MailContact -HiddenFromAddressListsEnabled $true  
    ```

<span data-ttu-id="c9a62-178">隐藏这些联系人后, 不会在共享通讯簿中显示外部联系人, 但仍可将其添加为通讯组成员。</span><span class="sxs-lookup"><span data-stu-id="c9a62-178">After you hide them, external contacts aren't displayed in the shared address book, but you can still add them as members of a distribution group.</span></span>
