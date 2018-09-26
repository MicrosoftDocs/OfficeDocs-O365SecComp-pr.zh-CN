---
title: 在 Office 365 中的电子数据展示事例中保留创建报表
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 9/11/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid: MOE150
ms.assetid: cca08d26-6fbf-4b2c-b102-b226e4cd7381
description: 使用本文中的脚本来生成报告包含有关与 Office 365 安全性的电子数据展示事例关联的所有保留项信息&amp;合规性中心。
ms.openlocfilehash: b6cef2824002d7e45e4f500bc6c1e9bc880cbd41
ms.sourcegitcommit: 7956955cd919f6e00b64e4506605a743c5872549
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/26/2018
ms.locfileid: "25038205"
---
# <a name="create-a-report-on-holds-in-ediscovery-cases-in-office-365"></a><span data-ttu-id="d3076-103">在 Office 365 中的电子数据展示事例中保留创建报表</span><span class="sxs-lookup"><span data-stu-id="d3076-103">Create a report on holds in eDiscovery cases in Office 365</span></span>
  
<span data-ttu-id="d3076-p101">本文中的脚本允许电子数据展示管理员和电子数据展示管理员生成报告包含有关与 Office 365 安全性的电子数据展示事例关联的所有保留的信息的&amp;合规性中心。该报告包含信息，如条件保留名称的相关联的内容位置的置于保持状态，以及是否保留项是基于查询的。如果没有任何保留的情况下，脚本将创建其他报告的情况下，不保留项列表。</span><span class="sxs-lookup"><span data-stu-id="d3076-p101">The script in this article lets eDiscovery administrators and eDiscovery managers generate a report that contains information about all holds that are associated with eDiscovery cases in the Office 365 Security &amp; Compliance Center. The report contains information such as the name of the case a hold is associated with, the content locations that are placed on hold, and whether the hold is query-based. If there are cases that don't have any holds, the script will create an additional report with a list of cases without holds.</span></span>

<span data-ttu-id="d3076-107">请参阅有关的信息包括在报表的详细说明[详细信息](#more-information)部分。</span><span class="sxs-lookup"><span data-stu-id="d3076-107">See the [More information](#more-information) section for a detailed description of the information included in the report.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="d3076-108">准备工作</span><span class="sxs-lookup"><span data-stu-id="d3076-108">Before you begin</span></span>

- <span data-ttu-id="d3076-p102">若要生成您的组织中的所有电子数据展示事例报告，您必须是电子数据展示管理员在组织中。如果您是经理电子数据展示，报告将仅包含有关您可以访问的用例信息。有关电子数据展示权限的详细信息，请参阅[分配 Office 365 安全性的电子数据展示权限&amp;合规性中心](assign-ediscovery-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="d3076-p102">To generate a report on all eDiscovery cases in your organization, you have to be an eDiscovery Administrator in your organization. If you are an eDiscovery Manager, the report will only include information about the cases that you can access. For more information about eDiscovery permissions, see [Assign eDiscovery permissions in the Office‍ 365 Security &amp; Compliance Center](assign-ediscovery-permissions.md).</span></span>
    
- <span data-ttu-id="d3076-p103">本文中的脚本具有最少的错误处理。主要用途是快速创建有关保留与您的组织中的电子数据展示事例关联的报告。</span><span class="sxs-lookup"><span data-stu-id="d3076-p103">The script in this article has minimal error handling. The primary purpose is to quickly create report about the holds that are associated with the eDiscovery cases in your organization.</span></span>
    
- <span data-ttu-id="d3076-p104">本主题中的示例脚本不受任何 Microsoft 标准支持计划或服务支持。示例脚本按原样提供，不提供任何种类的担保。Microsoft 进一步声明，不提供任何默示担保，包括但不限于适销性或特定用途适用性的默示担保。使用或运行示例脚本和文档所产生的任何风险均由你自己承担。对于因使用或无法使用示例脚本或文档而产生的任何损失（包括但不限于商业利润损失、业务中断、业务信息丢失或其他金钱损失），Microsoft、脚本作者或参与创建、生成或交付脚本的任何人都不承担任何责任，即使 Microsoft 已被告知存在这种损失的可能性，也不例外。</span><span class="sxs-lookup"><span data-stu-id="d3076-p104">The sample scripts provided in this topic aren't supported under any Microsoft standard support program or service. The sample scripts are provided AS IS without warranty of any kind. Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose. The entire risk arising out of the use or performance of the sample scripts and documentation remains with you. In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>
    
## <a name="step-1-connect-to-the-security-amp-compliance-center-using-remote-powershell"></a><span data-ttu-id="d3076-119">步骤 1： 连接到安全性&amp;合规性中心使用远程 PowerShell</span><span class="sxs-lookup"><span data-stu-id="d3076-119">Step 1: Connect to the Security &amp; Compliance Center using Remote PowerShell</span></span>

<span data-ttu-id="d3076-120">第一步是将 Windows PowerShell 连接到安全性&amp;的组织的合规性中心。</span><span class="sxs-lookup"><span data-stu-id="d3076-120">The first step is to connect Windows PowerShell to the Security &amp; Compliance Center for your organization.</span></span>
  
1. <span data-ttu-id="d3076-121">使用.ps1; filename 后缀将以下文本保存到的 Windows PowerShell 脚本文件例如， `ConnectSCC.ps1`。</span><span class="sxs-lookup"><span data-stu-id="d3076-121">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `ConnectSCC.ps1`.</span></span> 
    
      ```
      # Get login credentials 
      $UserCredential = Get-Credential 
      $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection 
      Import-PSSession $Session -AllowClobber -DisableNameChecking 
      $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Office 365 Security &amp; Compliance Center)" 
    ```

2. <span data-ttu-id="d3076-122">在本地计算机上打开 Windows PowerShell 并转到保存该脚本的文件夹。</span><span class="sxs-lookup"><span data-stu-id="d3076-122">On your local computer, open Windows PowerShell and go to the folder where you saved the script.</span></span> 
    
3. <span data-ttu-id="d3076-123">运行脚本。例如：</span><span class="sxs-lookup"><span data-stu-id="d3076-123">Run the script; for example:</span></span>

    ```
    .\ConnectSCC.ps1
    ```
   
4. <span data-ttu-id="d3076-124">当提示输入凭据，输入您的电子邮件地址和密码，，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="d3076-124">When prompted for your credentials, enter your email address and password, and then click **OK**.</span></span> 
  
## <a name="step-2-run-the-script-to-report-on-holds-associated-with-ediscovery-cases"></a><span data-ttu-id="d3076-125">步骤 2： 运行脚本，以报告包含与电子数据展示事例</span><span class="sxs-lookup"><span data-stu-id="d3076-125">Step 2: Run the script to report on holds associated with eDiscovery cases</span></span>

<span data-ttu-id="d3076-126">已连接到安全性后&amp;使用远程 PowerShell 的合规性中心下, 一步是创建和运行的脚本收集有关您的组织中的电子数据展示事例的信息。</span><span class="sxs-lookup"><span data-stu-id="d3076-126">After you've connected to the Security &amp; Compliance Center with remote PowerShell, the next step is to create and run the script that collects information about the eDiscovery cases in your organization.</span></span> 
  
1. <span data-ttu-id="d3076-127">使用.ps1; filename 后缀将以下文本保存到的 Windows PowerShell 脚本文件例如，CaseHoldsReport.ps1。</span><span class="sxs-lookup"><span data-stu-id="d3076-127">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, CaseHoldsReport.ps1.</span></span> 
    
  ```
#script begin
" " 
write-host "***********************************************"
write-host "   Office 365 Security & Compliance Center   " -foregroundColor yellow -backgroundcolor darkgreen
write-host "        eDiscovery cases - Holds report         " -foregroundColor yellow -backgroundcolor darkgreen 
write-host "***********************************************"
" " 
#prompt users to specify a path to store the output files
$time=get-date
$Path = Read-Host 'Enter a file path to save the report to a .csv file'
$outputpath=$Path+'\'+'CaseHoldsReport'+' '+$time.day+'-'+$time.month+'-'+$time.year+' '+$time.hour+'.'+$time.minute+'.csv'
$noholdsfilepath=$Path+'\'+'CaseswithNoHolds'+' '+$time.day+'-'+$time.month+'-'+$time.year+' '+$time.hour+'.'+$time.minute+'.csv'
#add case details to the csv file
function add-tocasereport{
Param([string]$casename,
[String]$casestatus,
[datetime]$casecreatedtime,
[string]$casemembers,
[datetime]$caseClosedDateTime,
[string]$caseclosedby,
[string]$holdname,
[String]$Holdenabled,
[string]$holdcreatedby,
[string]$holdlastmodifiedby,
[string]$ExchangeLocation,
[string]$sharePointlocation,
[string]$ContentMatchQuery,
[datetime]$holdcreatedtime,
[datetime]$holdchangedtime
)
$addRow = New-Object PSObject 
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case name" -Value $casename
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case status" -Value $casestatus
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case members" -Value $casemembers
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case created time" -Value $casecreatedtime
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case closed time" -Value $caseClosedDateTime
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case closed by" -Value $caseclosedby
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold name" -Value $holdname
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold enabled" -Value $Holdenabled
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold created by" -Value $holdcreatedby
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold last changed by" -Value $holdlastmodifiedby
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Exchange locations" -Value  $ExchangeLocation
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "SharePoint locations" -Value $sharePointlocation
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold query" -Value $ContentMatchQuery
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold created time (UTC)" -Value $holdcreatedtime
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold changed time (UTC)" -Value $holdchangedtime
$allholdreport = $addRow | Select-Object "Case name","Case status","Hold name","Hold enabled","Case members", "Case created time","Case closed time","Case closed by","Exchange locations","SharePoint locations","Hold query","Hold created by","Hold created time (UTC)","Hold last changed by","Hold changed time (UTC)"
$allholdreport | export-csv -path $outputPath -notypeinfo -append -Encoding ascii 
}
#get information on the cases and pass values to the case report function
" "
write-host "Gathering a list of cases and holds..."
" "
$edc =Get-ComplianceCase -ErrorAction SilentlyContinue
foreach($cc in $edc)
{
write-host "Working on case :" $cc.name
if($cc.status -eq 'Closed')
{
$cmembers = ((Get-ComplianceCaseMember -Case $cc.name).windowsLiveID)-join ';'
add-tocasereport -casename $cc.name -casestatus $cc.Status -caseclosedby $cc.closedby -caseClosedDateTime $cc.ClosedDateTime -casemembers $cmembers 
}
else{
$cmembers = ((Get-ComplianceCaseMember -Case $cc.name).windowsLiveID)-join ';'
$policies = Get-CaseHoldPolicy -Case $cc.Name | %{ Get-CaseHoldPolicy $_.Name -Case $_.CaseId -DistributionDetail}
if ($policies -ne $NULL)
{
foreach ($policy in $policies)
{
$rule=Get-CaseHoldRule -Policy $policy.name
add-tocasereport -casename $cc.name -casemembers $cmembers -casestatus $cc.Status -casecreatedtime $cc.CreatedDateTime -holdname $policy.name -holdenabled $policy.enabled -holdcreatedby $policy.CreatedBy -holdlastmodifiedby $policy.LastModifiedBy -ExchangeLocation (($policy.exchangelocation.name)-join ';') -SharePointLocation (($policy.sharePointlocation.name)-join ';') -ContentMatchQuery $rule.ContentMatchQuery -holdcreatedtime $policy.WhenCreatedUTC -holdchangedtime $policy.WhenChangedUTC
}
}
else{
write-host "No hold policies found in case:" $cc.name -foregroundColor 'Yellow'
" "
[string]$cc.name | out-file -filepath $noholdsfilepath -append 
}
}
}

" "
Write-host "Script complete! Report files saved to this folder: '$Path'"
" "
#script end
  ```

2. <span data-ttu-id="d3076-128">在 Windows PowerShell 会话中打开在步骤 1 中，转到保存该脚本的文件夹。</span><span class="sxs-lookup"><span data-stu-id="d3076-128">In the Windows PowerShell session that opened in Step 1, go to the folder where you saved the script.</span></span> 
    
3. <span data-ttu-id="d3076-129">运行脚本。例如：</span><span class="sxs-lookup"><span data-stu-id="d3076-129">Run the script; for example:</span></span>

    ```
    .\CaseHoldsReport.ps1
    ```

    <span data-ttu-id="d3076-130">该脚本将会进行提示保存报表的目标文件夹。</span><span class="sxs-lookup"><span data-stu-id="d3076-130">The script will prompt for a target folder to save the report to.</span></span> 
    
4. <span data-ttu-id="d3076-131">键入要保存，该报表的文件夹的完整路径名称，然后按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="d3076-131">Type the full path name of the folder to save the report to, and then press **Enter**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="d3076-p105">若要将报告保存该脚本位于同一文件夹中，键入一段 ("。") 时提示您目标文件夹。若要保存该脚本所在的文件夹中的子文件夹中的报告，只需键入子文件夹的名称。</span><span class="sxs-lookup"><span data-stu-id="d3076-p105">To save the report in the same folder that the script is located in, type a period (".") when prompted for a target folder. To save the report in a subfolder in the folder where the script is located, just type the name of the subfolder.</span></span> 
  
    <span data-ttu-id="d3076-p106">脚本开始收集有关您的组织中的所有电子数据展示事例的信息。脚本运行时，不访问报告文件。完成该脚本后，在 Windows PowerShell 会话中显示一条确认消息。显示此消息之后，您可以访问您在步骤 4 中指定的文件夹中的报告。报表的文件名为`CaseHoldsReport<DateTimeStamp>.csv`。</span><span class="sxs-lookup"><span data-stu-id="d3076-p106">The script starts to collect information about all the eDiscovery cases in your organization. Don't access the report file while the script is running. After the script is complete, a confirmation message is displayed in the Windows PowerShell session. After this message is displayed, you can access the report in the folder that you specified in Step 4. The file name for the report is `CaseHoldsReport<DateTimeStamp>.csv`.</span></span>

    <span data-ttu-id="d3076-p107">另外，该脚本还创建报表的情况下没有任何保留项的列表。此报告的文件名为`CaseswithNoHolds<DateTimeStamp>.csv`。</span><span class="sxs-lookup"><span data-stu-id="d3076-p107">Addtionally, the script also creates a report with a list of cases that don't have any holds. The file name for this report is `CaseswithNoHolds<DateTimeStamp>.csv`.</span></span>
    
    <span data-ttu-id="d3076-141">下面是运行 CaseHoldsReport.ps1 脚本的一个示例。</span><span class="sxs-lookup"><span data-stu-id="d3076-141">Here's an example of running the CaseHoldsReport.ps1 script.</span></span> 
    
    ![后运行 CaseHoldsReport.ps1 脚本输出](media/7d312ed5-505e-4ec5-8f06-3571e3524a1a.png)
  
## <a name="more-information"></a><span data-ttu-id="d3076-143">更多信息</span><span class="sxs-lookup"><span data-stu-id="d3076-143">More information</span></span>

<span data-ttu-id="d3076-p108">这种情况，其中包含本文中运行该脚本时创建的报告包含有关每个保留的以下信息。如前所述，您必须是电子数据展示管理员联系，以返回组织中的所有保留项的信息。包含与案例相关的详细信息，请参阅[Office 365 安全性的电子数据展示事例&amp;合规性中心](ediscovery-cases.md)。</span><span class="sxs-lookup"><span data-stu-id="d3076-p108">The case holds report that's created when you run the script in this article contains the following information about each hold. As previously explained, you have to be an eDiscovery Administrator to return information for all holds in your organization. For more information about case holds, see [eDiscovery cases in the Office 365 Security &amp; Compliance Center](ediscovery-cases.md).</span></span>
  
  - <span data-ttu-id="d3076-147">保留和电子数据展示案例保留项关联的名称的名称。</span><span class="sxs-lookup"><span data-stu-id="d3076-147">The name of the hold and the name of the eDiscovery case that the hold is associated with.</span></span>
    
  - <span data-ttu-id="d3076-148">是否电子数据展示事例是活动还是关闭。</span><span class="sxs-lookup"><span data-stu-id="d3076-148">Whether or not the eDiscovery case is active or closed.</span></span>
    
  - <span data-ttu-id="d3076-149">是否启用或禁用保留项。</span><span class="sxs-lookup"><span data-stu-id="d3076-149">Whether or not the hold is enabled or disabled.</span></span>
    
  - <span data-ttu-id="d3076-p109">与关联保留电子数据展示事例的成员。案例成员可以查看或管理的情况下，根据已被分配给他们的电子数据展示权限。</span><span class="sxs-lookup"><span data-stu-id="d3076-p109">The members of the eDiscovery case that the hold is associated with. Case members can view or manage a case, depending on the eDiscovery permissions they've been assigned.</span></span>
    
  - <span data-ttu-id="d3076-152">这种情况的创建的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="d3076-152">The time and date the case was created.</span></span>
    
  - <span data-ttu-id="d3076-153">如果已关闭种情况下，关闭关闭它与时间和日期它的人员。</span><span class="sxs-lookup"><span data-stu-id="d3076-153">If a case is closed, the person who closed it and the time and date it was closed.</span></span>
    
  - <span data-ttu-id="d3076-154">Exchange 邮箱和 SharePoint 网站处于保持状态的位置。</span><span class="sxs-lookup"><span data-stu-id="d3076-154">The Exchange mailboxes and SharePoint sites locations that are on hold.</span></span>
    
  - <span data-ttu-id="d3076-155">如果保留项是基于查询的查询语法。</span><span class="sxs-lookup"><span data-stu-id="d3076-155">If the hold is query-based, the query syntax.</span></span>
    
  - <span data-ttu-id="d3076-156">时间和保留项的创建的日期和创建它的人员。</span><span class="sxs-lookup"><span data-stu-id="d3076-156">The time and date the hold was created and the person who created it.</span></span>
    
  - <span data-ttu-id="d3076-157">时间和日期上次更改保留更改它的人员。</span><span class="sxs-lookup"><span data-stu-id="d3076-157">The time and date the hold was last changed and the person who changed it.</span></span>
