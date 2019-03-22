---
title: 创建关键字词典
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 标识敏感信息有时需要查找关键字，尤其是在标识通用内容（如与医疗保健相关的通信）或不当/露骨语言时。虽然可以在敏感信息类型中创建关键字列表，但关键字列表的大小受限，且必须修改 XML 才能创建或编辑它们。借助关键字词典，可以更大规模地轻松管理关键字（每个词典最多支持 100,000 个关键字）。
ms.openlocfilehash: 5561f8b11cf7bab8c726da332caca1484d455b35
ms.sourcegitcommit: 9a69ea604b415af4fef4964a19a09f3cead5a2ce
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/20/2019
ms.locfileid: "30701307"
---
# <a name="create-a-keyword-dictionary"></a><span data-ttu-id="2dc11-105">创建关键字词典</span><span class="sxs-lookup"><span data-stu-id="2dc11-105">Create a keyword dictionary</span></span>

<span data-ttu-id="2dc11-p102">Office 365 中的数据丢失防护 (DLP) 可标识、监视和保护敏感信息。标识敏感信息有时需要查找关键字，尤其是在标识通用内容（如与医疗保健相关的通信）或不当/露骨语言时。虽然可以在敏感信息类型中创建关键字列表，但关键字列表的大小受限，且必须修改 XML 才能创建或编辑它们。借助关键字词典，可以更大规模地轻松管理关键字（每个词典最多支持 100,000 个关键字）。</span><span class="sxs-lookup"><span data-stu-id="2dc11-p102">Data loss prevention (DLP) in Office 365 can identify, monitor, and protect your sensitive information. Identifying sensitive information sometimes requires looking for keywords, particularly when identifying generic content (such as healthcare-related communication) or inappropriate or explicit language. While you can create keyword lists in sensitive information types, keyword lists are limited in size and require modifying XML to create or edit them. Keyword dictionaries provide simpler management of keywords and at a much larger scale, supporting up to 100,000 terms per dictionary.</span></span>
  
## <a name="basic-steps-to-creating-a-keyword-dictionary"></a><span data-ttu-id="2dc11-110">创建关键字词典的基本步骤</span><span class="sxs-lookup"><span data-stu-id="2dc11-110">Basic steps to creating a keyword dictionary</span></span>

<span data-ttu-id="2dc11-p103">词典可能有多个关键字来源，最常见的来源是服务或 PowerShell cmdlet 中导入的文件（如 .csv 或 .txt 列表）、你直接在 PowerShell cmdlet 中输入的列表或现有词典。创建关键字词典时，请遵循下面的相同核心步骤：</span><span class="sxs-lookup"><span data-stu-id="2dc11-p103">The keywords for your dictionary could come from a variety of sources, most commonly from a file (such as a .csv or .txt list), from a list you enter directly in the cmdlet, or from an existing dictionary. When you create a keyword dictionary, you follow the same core steps:</span></span>
  
1. <span data-ttu-id="2dc11-113">使用**安全与合规中心**或连接到**安全与合规中心 PowerShell**。</span><span class="sxs-lookup"><span data-stu-id="2dc11-113">Use the **Security & Compliance center** or connect to the **Security &amp; Compliance Center PowerShell**.</span></span>
    
2. <span data-ttu-id="2dc11-114">**定义或加载目标来源中的关键字** - 用于创建自定义关键字词典的向导和 cmdlet 均接受关键字的逗号分隔列表，所以这一步因关键字来源不同而略有差异。</span><span class="sxs-lookup"><span data-stu-id="2dc11-114">**Define or load your keywords from your intended source** - the cmdlet to create a keyword dictionary accepts a comma-separated list of keywords, so this step will vary slightly depending on where your keywords come from.</span></span> <span data-ttu-id="2dc11-115">加载后的关键字会在导入前编码并转换为字节数组。</span><span class="sxs-lookup"><span data-stu-id="2dc11-115">Encode your keywords - once loaded, they're converted to a byte array before they're imported.</span></span>
    
3. <span data-ttu-id="2dc11-116">**创建词典** - 指定名称和说明，并创建词典。</span><span class="sxs-lookup"><span data-stu-id="2dc11-116">**Create your dictionary** - choose a name and description and create your dictionary.</span></span>

## <a name="create-a-keyword-dictionary-using-the-security--compliance-center"></a><span data-ttu-id="2dc11-117">使用安全与合规中心创建关键字词典</span><span class="sxs-lookup"><span data-stu-id="2dc11-117">Create a keyword dictionary using the Security & Compliance center</span></span>

<span data-ttu-id="2dc11-118">使用以下步骤创建和导入自定义词典关键字：</span><span class="sxs-lookup"><span data-stu-id="2dc11-118">Use the following steps to create and import keywords for a custom dictionary:</span></span>

1. <span data-ttu-id="2dc11-119">连接到[安全与合规中心](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="2dc11-119">[Connect to the Office 365 Security & Compliance Center Powershell](https://protection.office.com)</span></span>
2. <span data-ttu-id="2dc11-120">导航到 **“分类”>“敏感信息类型”**。</span><span class="sxs-lookup"><span data-stu-id="2dc11-120">Navigate to **Classifications > Sensitive info types**.</span></span>
3. <span data-ttu-id="2dc11-121">选择“**创建**”并输入敏感信息类型的“**名称**”和“**说明**”，然后选择“**下一步**”</span><span class="sxs-lookup"><span data-stu-id="2dc11-121">Select **Create** and enter a **Name** and **Description** for your sensitive info type, then select **Next**</span></span>
4. <span data-ttu-id="2dc11-122">选择“**添加元素**”，然后选择“**检测内容包含**”下拉列表中的“**词典（大关键字）**”中。</span><span class="sxs-lookup"><span data-stu-id="2dc11-122">Select **Add an element**, then select **Dictionary (Large keywords)** in the **Detect content containing** drop-down list.</span></span>
5. <span data-ttu-id="2dc11-123">选择“**添加词典**”</span><span class="sxs-lookup"><span data-stu-id="2dc11-123">Select **Add a site**.</span></span>
6. <span data-ttu-id="2dc11-124">在“搜索”控件下，选择“**你可以在此处新建关键字词典**”。</span><span class="sxs-lookup"><span data-stu-id="2dc11-124">Under the Search control, select **You can create new keyword dictionaries here**.</span></span>
7. <span data-ttu-id="2dc11-125">输入自定义词典的“**名称**”。</span><span class="sxs-lookup"><span data-stu-id="2dc11-125">Enter a **Name** for your custom dictionary.</span></span>
8. <span data-ttu-id="2dc11-126">选择“**导入**”，并根据关键字文件类型选择“**从文本**”或“**从 csv**”。</span><span class="sxs-lookup"><span data-stu-id="2dc11-126">Select **Import**, and select either **From text** or **From csv** depending on your keyword file type.</span></span>
9. <span data-ttu-id="2dc11-127">在文件对话框中，从本地电脑或网络文件共享中选择关键字文件，然后选择“**打开**”。</span><span class="sxs-lookup"><span data-stu-id="2dc11-127">In the file dialog, select the keyword file from your local PC or network file share, then select **Open**.</span></span>
10. <span data-ttu-id="2dc11-128">选择“**保存**”，然后从“**关键字词典**”列表中选择自定义词典。</span><span class="sxs-lookup"><span data-stu-id="2dc11-128">Select **Save**, then select your custom dictionary from the **Keyword dictionaries** list.</span></span>
11. <span data-ttu-id="2dc11-129">选择“**添加**”，然后选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="2dc11-129">Select **Add**, then select **Next**.</span></span>
12. <span data-ttu-id="2dc11-130">检查并完成敏感信息类型选择，然后选择“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="2dc11-130">Review and finalize your sensitive info type selections, then select **Finish**.</span></span>
    
## <a name="create-a-keyword-dictionary-from-a-file-using-powershell"></a><span data-ttu-id="2dc11-131">使用 PowerShell 通过文件创建关键字词典</span><span class="sxs-lookup"><span data-stu-id="2dc11-131">Create a keyword dictionary from a file</span></span>

<span data-ttu-id="2dc11-p105">如果需要创建大词典，词典通常使用从其他某来源导出的文件或列表中的关键字。本示例将创建关键字词典，其中包含要在外部电子邮件中筛查的不当语言列表。首先，需要[连接到 Office 365 安全与合规中心 PowerShell](https://docs.microsoft.com/zh-CN/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="2dc11-p105">Often when you need to create a large dictionary, it's to use keywords from a file or a list exported from some other source. In this case, you'll create a keyword dictionary containing a list of inappropriate language to screen in external email. You need to first [Connect to Office 365 Security &amp; Compliance Center PowerShell](https://docs.microsoft.com/zh-CN/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>
  
1. <span data-ttu-id="2dc11-135">将关键字复制到文本文件中，并确保每个关键字都单独占一行。</span><span class="sxs-lookup"><span data-stu-id="2dc11-135">Copy the keywords into a text file and make sure that each keyword is on a separate line.</span></span>
    
2. <span data-ttu-id="2dc11-p106">使用 Unicode 编码保存文本文件。在记事本中，依次单击“另存为”\*\*\*\*\>“编码”\*\*\*\*\>“Unicode”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2dc11-p106">Save the text file with Unicode encoding. In Notepad \> **Save As** \> **Encoding** \> **Unicode**.</span></span>
    
3. <span data-ttu-id="2dc11-138">运行下面的 cmdlet，以将文件读入变量中：</span><span class="sxs-lookup"><span data-stu-id="2dc11-138">Read the file into a variable by running this cmdlet:</span></span>
    
  ```
  $fileData = Get-Content <filename> -Encoding Byte -ReadCount 0
  ```

4. <span data-ttu-id="2dc11-139">运行下面的 cmdlet，以创建词典：</span><span class="sxs-lookup"><span data-stu-id="2dc11-139">Create the dictionary by running this cmdlet:</span></span>
    
  ```
  New-DlpKeywordDictionary -Name <name> -Description <description> -FileData $fileData
  ```

## <a name="modifying-an-existing-keyword-dictionary"></a><span data-ttu-id="2dc11-140">修改现有关键字词典</span><span class="sxs-lookup"><span data-stu-id="2dc11-140">Modifying an existing keyword dictionary</span></span>

<span data-ttu-id="2dc11-141">可能需要修改一个关键字词典中的关键字，或修改一个内置词典。</span><span class="sxs-lookup"><span data-stu-id="2dc11-141">You might need to modify keywords in one of your keyword dictionaries, or modify one of the built-in dictionaries.</span></span> <span data-ttu-id="2dc11-142">目前，只能使用 PowerShell 更新自定义关键字词典。</span><span class="sxs-lookup"><span data-stu-id="2dc11-142">Currently, your can only update a custom keyword dictionary using PowerShell.</span></span> 

<span data-ttu-id="2dc11-143">本示例将在 PowerShell 中修改一些术语，在可便于使用编辑器编辑术语的本地位置保存术语，然后就地更新旧术语。</span><span class="sxs-lookup"><span data-stu-id="2dc11-143">You might need to modify keywords in one of your keyword dictionaries, or modify one of the built-in dictionaries. In this example, we'll modify some terms in PowerShell, save the terms locally where you can modify them in an editor, and then update the previous terms in place. First, retrieve the dictionary object:</span></span> <span data-ttu-id="2dc11-144">首先，检索词典对象：</span><span class="sxs-lookup"><span data-stu-id="2dc11-144">First, retrieve the dictionary object:</span></span>
  
```
$dict = Get-DlpKeywordDictionary -Name "Diseases"
```

<span data-ttu-id="2dc11-p109">打印 `$dict` 将显示各种变量。关键字本身存储在后端上的对象中，但 `$dict.KeywordDictionary` 包含它们的字符串表示形式，可用于修改词典。必须先使用 `.split(',')` 方法将关键字字符串转换回数组，然后才能修改词典。然后，使用 `.trim()` 方法清理关键字之间不必要的空格，只留下要使用的关键字。</span><span class="sxs-lookup"><span data-stu-id="2dc11-p109">Printing  `$dict` will show the various variables. The keywords themselves are stored in an object on the backend, but  `$dict.KeywordDictionary` contains a string representation of them, which you'll use to modify the dictionary. Before you modify the dictionary, you need to turn the string of terms back into an array using the  `.split(',')` method. Then you'll clean up the unwanted spaces between the keywords with the  `.trim()` method, leaving just the keywords to work with.</span></span> 
  
```
$terms = $dict.KeywordDictionary.split(',').trim()
```

<span data-ttu-id="2dc11-p110">现在从词典中删除一些关键字。由于示例词典中只有几个关键字，因此你可以很轻松地就跳到导出词典并在记事本中编辑关键字，但词典通常包含大量文本，所以必须先了解如何在 PowerShell 中轻松编辑关键字。</span><span class="sxs-lookup"><span data-stu-id="2dc11-p110">Now you'll remove some terms from the dictionary. Because the example dictionary has only a few keywords, you could just as easily skip to exporting the dictionary and editing it in Notepad, but dictionaries generally contain a large amount of text, so you'll first learn this way to edit them easily in PowerShell.</span></span>
  
<span data-ttu-id="2dc11-p111">你在最后一步中将关键字保存到了数组中。虽然[从数组中删除项](https://go.microsoft.com/fwlink/p/?linkid=852620)的方法有多种，但简单方法是创建要从词典中删除的关键字数组，再只将要删除的关键字列表中没有的词典关键字复制到其中。</span><span class="sxs-lookup"><span data-stu-id="2dc11-p111">In the last step, you saved the keywords to an array. There are several ways to [remove items from an array](https://go.microsoft.com/fwlink/p/?linkid=852620), but as a straightforward approach, you'll create an array of the terms you want to remove from the dictionary, and then copy only the dictionary terms to it that aren't in the list of terms to remove.</span></span>
  
<span data-ttu-id="2dc11-p112">运行命令 `$terms`，以显示当前关键字列表。此命令的输出如下所示：</span><span class="sxs-lookup"><span data-stu-id="2dc11-p112">Run the command  `$terms` to show the current list of terms. The output of the command looks like this:</span></span> 
  
```
aarskog's syndrome
abandonment
abasia
abderhalden-kaufmann-lignac
abdominalgia
abduction contracture
abetalipoproteinemia
abiotrophy
ablatio
ablation
ablepharia
abocclusion
abolition
aborter
abortion
abortus
aboulomania
abrami's disease
```

<span data-ttu-id="2dc11-155">运行下面的命令，以指定要删除的关键字：</span><span class="sxs-lookup"><span data-stu-id="2dc11-155">Run this command to specify the terms that you want to remove:</span></span>
  
```
$termsToRemove = @('abandonment', 'ablatio')
```

<span data-ttu-id="2dc11-156">运行下面的命令，以实际删除列表中的关键字：</span><span class="sxs-lookup"><span data-stu-id="2dc11-156">Run this command to actually remove the terms from the list:</span></span>
  
```
$updatedTerms = $terms | Where-Object{ $_ -notin $termsToRemove }
```

<span data-ttu-id="2dc11-p113">运行命令 `$updatedTerms`，以显示更新后的关键字列表。此命令的输出如下所示（指定关键字已遭删除）：</span><span class="sxs-lookup"><span data-stu-id="2dc11-p113">Run the command  `$updatedTerms` to show the updated list of terms. The output of the command looks like this (the specified terms have been removed):</span></span> 
  
```
aarskog's syndrome
abasia
abderhalden-kaufmann-lignac
abdominalgia
abduction contracture
abetalipo proteinemia
abiotrophy
ablation
ablepharia
abocclusion
abolition
aborter
abortion
abortus
aboulomania
abrami's disease
```

<span data-ttu-id="2dc11-p114">现在，在本地保存词典，并添加其他一些关键字。可直接在 PowerShell 中添加关键字，但仍需要在本地导出文件，以确保它是使用 Unicode 编码进行保存并包含 BOM。</span><span class="sxs-lookup"><span data-stu-id="2dc11-p114">Now save the dictionary locally and add a few more terms. You could add the terms right here in PowerShell, but you'll still need to export the file locally to ensure it's saved with Unicode encoding and contains the BOM.</span></span>
  
<span data-ttu-id="2dc11-161">运行下面的命令，以在本地保存词典：</span><span class="sxs-lookup"><span data-stu-id="2dc11-161">Save the dictionary locally by running the following:</span></span>
  
```
Set-Content $updatedTerms -Path "C:\myPath\terms.txt"
```

<span data-ttu-id="2dc11-p115">现在只需打开文件，添加其他关键字，并使用 Unicode 编码 (UTF-16) 保存文件即可。现在将上传更新后的关键字，并就地更新词典。</span><span class="sxs-lookup"><span data-stu-id="2dc11-p115">Now simply open the file, add your additional terms, and save with Unicode encoding (UTF-16). Now you'll upload the updated terms and update the dictionary in place.</span></span>
  
```
PS> Set-DlpKeywordDictionary -Identity "Diseases" -FileData (Get-Content -Path "C:myPath\terms.txt" -Encoding Byte -ReadCount 0)
```

<span data-ttu-id="2dc11-p116">至此，词典已就地更新。请注意，`Identity` 字段需要使用词典名称。如果还要使用 `set-` cmdlet 更改词典名称，只需将包含新词典名称的 `-Name` 参数添加到上面的命令中即可。</span><span class="sxs-lookup"><span data-stu-id="2dc11-p116">Now the dictionary has been updated in place. Note that the  `Identity` field takes the name of the dictionary. If you wanted to also change the name of your dictionary using the  `set-` cmdlet, you would just need to add the  `-Name` parameter to what's above with your new dictionary name.</span></span> 
  
## <a name="using-keyword-dictionaries-in-custom-sensitive-information-types-and-dlp-policies"></a><span data-ttu-id="2dc11-167">在自定义敏感信息类型和 DLP 策略中使用关键字词典</span><span class="sxs-lookup"><span data-stu-id="2dc11-167">Using keyword dictionaries in custom sensitive information types and DLP policies</span></span>

<span data-ttu-id="2dc11-p117">关键字字典可用作自定义敏感信息类型的匹配要求，也可用作敏感信息类型本身。无论是上述哪种情况，都必须[使用 Office 365 安全与合规中心 PowerShell 创建自定义敏感信息类型](create-a-custom-sensitive-information-type-in-scc-powershell.md)。请按照链接文章中的说明操作，创建敏感信息类型。创建 XML 后，必须有字典的 GUID 标识符才能使用它。</span><span class="sxs-lookup"><span data-stu-id="2dc11-p117">Keyword dictionaries can be used as part of the match requirements for a custom sensitive information type, or as a sensitive information type themselves. Both require [Create a custom sensitive information type in Office 365 Security & Compliance Center PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md). Follow the instructions in the linked article to create a sensitive information type. Once you have the XML, you'll need the GUID identifier for the dictionary to use it.</span></span>
  
```
<Entity id="9e5382d0-1b6a-42fd-820e-44e0d3b15b6e" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef=". . ."/>
    </Pattern>
</Entity>
```

<span data-ttu-id="2dc11-172">若要获得词典标识，请运行下面的命令，并复制 **Identity** 属性值：</span><span class="sxs-lookup"><span data-stu-id="2dc11-172">To get the identity of your dictionary, run this command and copy the **Identity** property value:</span></span> 
  
```
Get-DlpKeywordDictionary -Name "Diseases"
```

<span data-ttu-id="2dc11-173">此命令的输出如下所示：</span><span class="sxs-lookup"><span data-stu-id="2dc11-173">The output of the command looks like this:</span></span>
  
```
RunspaceId        : 138e55e7-ea1e-4f7a-b824-79f2c4252255
Identity          : 8d2d44b0-91f4-41f2-94e0-21c1c5b5fc9f
Name              : Diseases
Description       : Names of diseases and injuries from ICD-10-CM lexicon
KeywordDictionary : aarskog's syndrome, abandonment, abasia, abderhalden-kaufmann-lignac, abdominalgia, abduction contracture, abetalipo
                    proteinemia, abiotrophy, ablatio, ablation, ablepharia, abocclusion, abolition, aborter, abortion, abortus, aboulomania,
                    abrami's disease, abramo
IsValid           : True
ObjectState       : Unchanged
```

<span data-ttu-id="2dc11-p118">将标识粘贴到自定义敏感信息类型的 XML 中，并上传它。此时，词典会出现在敏感信息类型列表中，你可以直接在策略中使用它，同时指定必须匹配多少个关键字。</span><span class="sxs-lookup"><span data-stu-id="2dc11-p118">Paste the identity into your custom sensitive information type's XML and upload it. Now your dictionary will appear in your list of sensitive information types and you can use it right in your policy, specifying how many keywords are required to match.</span></span>
  
```
<Entity id="d333c6c2-5f4c-4131-9433-db3ef72a89e8" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="8d2d44b0-91f4-41f2-94e0-21c1c5b5fc9f" />
      </Pattern>
    </Entity>
    <LocalizedStrings>
      <Resource idRef="d333c6c2-5f4c-4131-9433-db3ef72a89e8">
        <Name default="true" langcode="en-us">Diseases</Name>
        <Description default="true" langcode="en-us">Detects various diseases</Description>
      </Resource>
    </LocalizedStrings>
```


