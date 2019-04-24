---
title: 在 Office 365 中的电子数据展示事例中创建保留报告
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 9/11/2017
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid: MOE150
ms.assetid: cca08d26-6fbf-4b2c-b102-b226e4cd7381
description: 使用本文中的脚本生成一个报告, 该报告包含有关与 Office 365 或 Microsoft 365 中的符合性中心中的电子数据展示事例相关联的所有保留的信息。
ms.openlocfilehash: db5a462087dd20ed71f87efe2fd83b821654f1b9
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32258762"
---
# <a name="create-a-report-on-holds-in-ediscovery-cases-in-office-365"></a><span data-ttu-id="06646-103">在 Office 365 中的电子数据展示事例中创建保留报告</span><span class="sxs-lookup"><span data-stu-id="06646-103">Create a report on holds in eDiscovery cases in Office 365</span></span>
  
<span data-ttu-id="06646-104">本文中的脚本允许电子数据展示管理员和电子数据展示管理器生成一个报告, 其中包含有关与 Office 365 或 Microsoft 365 中的合规性中心中的电子数据展示事例相关联的所有保留项的信息。</span><span class="sxs-lookup"><span data-stu-id="06646-104">The script in this article lets eDiscovery administrators and eDiscovery managers generate a report that contains information about all holds that are associated with eDiscovery cases in the the compliance center in Office 365 or Microsoft 365.</span></span> <span data-ttu-id="06646-105">报告包含与保留相关联的事例的名称、放置在保留中的内容位置以及保留是否基于查询的信息。</span><span class="sxs-lookup"><span data-stu-id="06646-105">The report contains information such as the name of the case a hold is associated with, the content locations that are placed on hold, and whether the hold is query-based.</span></span> <span data-ttu-id="06646-106">如果存在不包含任何保留的案例, 该脚本将创建另一个报告, 其中包含不含 "保留" 的案例列表。</span><span class="sxs-lookup"><span data-stu-id="06646-106">If there are cases that don't have any holds, the script will create an additional report with a list of cases without holds.</span></span>

<span data-ttu-id="06646-107">有关报告中包含的信息的详细说明, 请参阅[详细信息](#more-information)部分。</span><span class="sxs-lookup"><span data-stu-id="06646-107">See the [More information](#more-information) section for a detailed description of the information included in the report.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="06646-108">准备工作</span><span class="sxs-lookup"><span data-stu-id="06646-108">Before you begin</span></span>

- <span data-ttu-id="06646-109">若要生成组织中所有电子数据展示事例的报告, 您必须是组织中的电子数据展示管理员。</span><span class="sxs-lookup"><span data-stu-id="06646-109">To generate a report on all eDiscovery cases in your organization, you have to be an eDiscovery Administrator in your organization.</span></span> <span data-ttu-id="06646-110">如果您是电子数据展示管理器, 则报告将仅包含有关您可以访问的事例的信息。</span><span class="sxs-lookup"><span data-stu-id="06646-110">If you are an eDiscovery Manager, the report will only include information about the cases that you can access.</span></span> <span data-ttu-id="06646-111">有关电子数据展示权限的详细信息, 请参阅[分配电子数据展示权限](assign-ediscovery-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="06646-111">For more information about eDiscovery permissions, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>
    
- <span data-ttu-id="06646-112">本文中的脚本具有最少的错误处理。</span><span class="sxs-lookup"><span data-stu-id="06646-112">The script in this article has minimal error handling.</span></span> <span data-ttu-id="06646-113">主要目的是快速创建有关与组织中的电子数据展示事例相关联的保留报告。</span><span class="sxs-lookup"><span data-stu-id="06646-113">The primary purpose is to quickly create report about the holds that are associated with the eDiscovery cases in your organization.</span></span>
    
- <span data-ttu-id="06646-p104">本主题中的示例脚本不受任何 Microsoft 标准支持计划或服务支持。示例脚本按原样提供，不提供任何种类的担保。Microsoft 进一步声明，不提供任何默示担保，包括但不限于适销性或特定用途适用性的默示担保。使用或运行示例脚本和文档所产生的任何风险均由你自己承担。对于因使用或无法使用示例脚本或文档而产生的任何损失（包括但不限于商业利润损失、业务中断、业务信息丢失或其他金钱损失），Microsoft、脚本作者或参与创建、生成或交付脚本的任何人都不承担任何责任，即使 Microsoft 已被告知存在这种损失的可能性，也不例外。</span><span class="sxs-lookup"><span data-stu-id="06646-p104">The sample scripts provided in this topic aren't supported under any Microsoft standard support program or service. The sample scripts are provided AS IS without warranty of any kind. Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose. The entire risk arising out of the use or performance of the sample scripts and documentation remains with you. In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>
    
## <a name="step-1-connect-to-the-security--compliance-center-powershell"></a><span data-ttu-id="06646-119">步骤 1: 连接到安全 & 合规中心 PowerShell</span><span class="sxs-lookup"><span data-stu-id="06646-119">Step 1: Connect to the Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="06646-120">第一步是连接到您的组织的安全 & 合规中心。</span><span class="sxs-lookup"><span data-stu-id="06646-120">The first step is to connect to the Security & Compliance Center for your organization.</span></span>
  
1. <span data-ttu-id="06646-121">使用文件名后缀. ps1; 将以下文本保存到 Windows PowerShell 脚本文件中。例如, `ConnectSCC.ps1`。</span><span class="sxs-lookup"><span data-stu-id="06646-121">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `ConnectSCC.ps1`.</span></span> 
    
      ```
      # Get login credentials 
      $UserCredential = Get-Credential 
      $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection 
      Import-PSSession $Session -AllowClobber -DisableNameChecking 
      $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Security & Compliance Center)" 
    ```

2. <span data-ttu-id="06646-122">在本地计算机上, 打开 Windows PowerShell 并转到保存该脚本的文件夹。</span><span class="sxs-lookup"><span data-stu-id="06646-122">On your local computer, open Windows PowerShell and go to the folder where you saved the script.</span></span> 
    
3. <span data-ttu-id="06646-123">运行脚本;例如:</span><span class="sxs-lookup"><span data-stu-id="06646-123">Run the script; for example:</span></span>

    ```
    .\ConnectSCC.ps1
    ```
   
4. <span data-ttu-id="06646-124">当系统提示你输入凭据时, 请输入你的电子邮件地址和密码, 然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="06646-124">When prompted for your credentials, enter your email address and password, and then click **OK**.</span></span> 
  
## <a name="step-2-run-the-script-to-report-on-holds-associated-with-ediscovery-cases"></a><span data-ttu-id="06646-125">步骤 2: 运行脚本以报告与电子数据展示事例相关联的保留</span><span class="sxs-lookup"><span data-stu-id="06646-125">Step 2: Run the script to report on holds associated with eDiscovery cases</span></span>

<span data-ttu-id="06646-126">在连接到安全 & 合规中心 PowerShell 之后, 下一步是创建并运行脚本, 以收集有关您组织中的电子数据展示事例的信息。</span><span class="sxs-lookup"><span data-stu-id="06646-126">After you've connected to Security & Compliance Center PowerShell, the next step is to create and run the script that collects information about the eDiscovery cases in your organization.</span></span> 
  
1. <span data-ttu-id="06646-127">使用文件名后缀. ps1; 将以下文本保存到 Windows PowerShell 脚本文件中。例如, CaseHoldsReport。</span><span class="sxs-lookup"><span data-stu-id="06646-127">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, CaseHoldsReport.ps1.</span></span> 
    
  ```
#script begin
" " 
write-host "***********************************************"
write-host "   Security & Compliance Center   " -foregroundColor yellow -backgroundcolor darkgreen
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

2. <span data-ttu-id="06646-128">在步骤1中打开的 Windows PowerShell 会话中, 转到保存脚本的文件夹。</span><span class="sxs-lookup"><span data-stu-id="06646-128">In the Windows PowerShell session that opened in Step 1, go to the folder where you saved the script.</span></span> 
    
3. <span data-ttu-id="06646-129">运行脚本;例如:</span><span class="sxs-lookup"><span data-stu-id="06646-129">Run the script; for example:</span></span>

    ```
    .\CaseHoldsReport.ps1
    ```

    <span data-ttu-id="06646-130">脚本将提示要将报告保存到的目标文件夹。</span><span class="sxs-lookup"><span data-stu-id="06646-130">The script will prompt for a target folder to save the report to.</span></span> 
    
4. <span data-ttu-id="06646-131">键入要将报告保存到的文件夹的完整路径名称, 然后按**enter**。</span><span class="sxs-lookup"><span data-stu-id="06646-131">Type the full path name of the folder to save the report to, and then press **Enter**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="06646-132">若要将报告保存在脚本所在的同一文件夹中, 请在系统提示输入目标文件夹时键入句点 (".")。</span><span class="sxs-lookup"><span data-stu-id="06646-132">To save the report in the same folder that the script is located in, type a period (".") when prompted for a target folder.</span></span> <span data-ttu-id="06646-133">若要将报告保存在脚本所在的文件夹的子文件夹中, 只需键入子文件夹的名称即可。</span><span class="sxs-lookup"><span data-stu-id="06646-133">To save the report in a subfolder in the folder where the script is located, just type the name of the subfolder.</span></span> 
  
    <span data-ttu-id="06646-134">脚本开始收集组织中所有电子数据展示事例的相关信息。</span><span class="sxs-lookup"><span data-stu-id="06646-134">The script starts to collect information about all the eDiscovery cases in your organization.</span></span> <span data-ttu-id="06646-135">在运行脚本时不访问报告文件。</span><span class="sxs-lookup"><span data-stu-id="06646-135">Don't access the report file while the script is running.</span></span> <span data-ttu-id="06646-136">脚本完成后, 将在 Windows PowerShell 会话中显示一条确认消息。</span><span class="sxs-lookup"><span data-stu-id="06646-136">After the script is complete, a confirmation message is displayed in the Windows PowerShell session.</span></span> <span data-ttu-id="06646-137">显示此消息后, 您可以访问您在步骤4中指定的文件夹中的报告。</span><span class="sxs-lookup"><span data-stu-id="06646-137">After this message is displayed, you can access the report in the folder that you specified in Step 4.</span></span> <span data-ttu-id="06646-138">报告的文件名为`CaseHoldsReport<DateTimeStamp>.csv`。</span><span class="sxs-lookup"><span data-stu-id="06646-138">The file name for the report is `CaseHoldsReport<DateTimeStamp>.csv`.</span></span>

    <span data-ttu-id="06646-139">此外, 该脚本还将创建一个报告, 其中包含不包含任何保留的案例列表。</span><span class="sxs-lookup"><span data-stu-id="06646-139">Addtionally, the script also creates a report with a list of cases that don't have any holds.</span></span> <span data-ttu-id="06646-140">此报告的文件名为`CaseswithNoHolds<DateTimeStamp>.csv`。</span><span class="sxs-lookup"><span data-stu-id="06646-140">The file name for this report is `CaseswithNoHolds<DateTimeStamp>.csv`.</span></span>
    
    <span data-ttu-id="06646-141">下面的示例展示了如何运行 CaseHoldsReport 脚本。</span><span class="sxs-lookup"><span data-stu-id="06646-141">Here's an example of running the CaseHoldsReport.ps1 script.</span></span> 
    
    ![运行 CaseHoldsReport 脚本后的输出](media/7d312ed5-505e-4ec5-8f06-3571e3524a1a.png)
  
## <a name="more-information"></a><span data-ttu-id="06646-143">详细信息</span><span class="sxs-lookup"><span data-stu-id="06646-143">More information</span></span>

<span data-ttu-id="06646-144">事例包含运行本文中的脚本时创建的报告, 其中包含有关每个保留的以下信息。</span><span class="sxs-lookup"><span data-stu-id="06646-144">The case holds report that's created when you run the script in this article contains the following information about each hold.</span></span> <span data-ttu-id="06646-145">如前面所述, 您必须是电子数据展示管理员才能返回组织中所有保留的信息。</span><span class="sxs-lookup"><span data-stu-id="06646-145">As previously explained, you have to be an eDiscovery Administrator to return information for all holds in your organization.</span></span> <span data-ttu-id="06646-146">有关案例保留的详细信息, 请参阅[电子数据展示事例](ediscovery-cases.md)。</span><span class="sxs-lookup"><span data-stu-id="06646-146">For more information about case holds, see [eDiscovery cases](ediscovery-cases.md).</span></span>
  
  - <span data-ttu-id="06646-147">保留的名称和与该保留相关联的电子数据展示事例的名称。</span><span class="sxs-lookup"><span data-stu-id="06646-147">The name of the hold and the name of the eDiscovery case that the hold is associated with.</span></span>
    
  - <span data-ttu-id="06646-148">电子数据展示事例是否处于活动状态或已关闭状态。</span><span class="sxs-lookup"><span data-stu-id="06646-148">Whether or not the eDiscovery case is active or closed.</span></span>
    
  - <span data-ttu-id="06646-149">保留是否已启用或已禁用。</span><span class="sxs-lookup"><span data-stu-id="06646-149">Whether or not the hold is enabled or disabled.</span></span>
    
  - <span data-ttu-id="06646-150">与保留相关联的电子数据展示事例的成员。</span><span class="sxs-lookup"><span data-stu-id="06646-150">The members of the eDiscovery case that the hold is associated with.</span></span> <span data-ttu-id="06646-151">事例成员可以查看或管理事例, 具体取决于他们已分配的电子数据展示权限。</span><span class="sxs-lookup"><span data-stu-id="06646-151">Case members can view or manage a case, depending on the eDiscovery permissions they've been assigned.</span></span>
    
  - <span data-ttu-id="06646-152">案例的创建时间和日期。</span><span class="sxs-lookup"><span data-stu-id="06646-152">The time and date the case was created.</span></span>
    
  - <span data-ttu-id="06646-153">如果案例关闭, 则关闭它以及关闭它的时间和日期。</span><span class="sxs-lookup"><span data-stu-id="06646-153">If a case is closed, the person who closed it and the time and date it was closed.</span></span>
    
  - <span data-ttu-id="06646-154">处于保留状态的 Exchange 邮箱和 SharePoint 网站位置。</span><span class="sxs-lookup"><span data-stu-id="06646-154">The Exchange mailboxes and SharePoint sites locations that are on hold.</span></span>
    
  - <span data-ttu-id="06646-155">如果保留是基于查询的查询语法, 则为。</span><span class="sxs-lookup"><span data-stu-id="06646-155">If the hold is query-based, the query syntax.</span></span>
    
  - <span data-ttu-id="06646-156">创建保留的时间和日期以及创建该保留的人员。</span><span class="sxs-lookup"><span data-stu-id="06646-156">The time and date the hold was created and the person who created it.</span></span>
    
  - <span data-ttu-id="06646-157">上次更改保留的时间和日期以及更改了保留的人员。</span><span class="sxs-lookup"><span data-stu-id="06646-157">The time and date the hold was last changed and the person who changed it.</span></span>
