---
title: 在 Office 365 中的电子数据展示事例中创建保留报告
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 9/11/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid: MOE150
ms.assetid: cca08d26-6fbf-4b2c-b102-b226e4cd7381
description: 使用本文中的脚本生成一个报告, 该报告包含有关与 Office 365 或 Microsoft 365 中的符合性中心中的电子数据展示事例相关联的所有保留的信息。
ms.openlocfilehash: 7118b62dcd42413309e33c45e80516c8822faeff
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2019
ms.locfileid: "34151284"
---
# <a name="create-a-report-on-holds-in-ediscovery-cases-in-office-365"></a>在 Office 365 中的电子数据展示事例中创建保留报告
  
本文中的脚本允许电子数据展示管理员和电子数据展示管理器生成一个报告, 其中包含有关与 Office 365 或 Microsoft 365 中的合规性中心中的电子数据展示事例相关联的所有保留项的信息。 报告包含与保留相关联的事例的名称、放置在保留中的内容位置以及保留是否基于查询的信息。 如果存在不包含任何保留的案例, 该脚本将创建另一个报告, 其中包含不含 "保留" 的案例列表。

有关报告中包含的信息的详细说明, 请参阅[详细信息](#more-information)部分。 
  
## <a name="before-you-begin"></a>开始之前

- 若要生成组织中所有电子数据展示事例的报告, 您必须是组织中的电子数据展示管理员。 如果您是电子数据展示管理器, 则报告将仅包含有关您可以访问的事例的信息。 有关电子数据展示权限的详细信息, 请参阅[分配电子数据展示权限](assign-ediscovery-permissions.md)。
    
- 本文中的脚本具有最少的错误处理。 主要目的是快速创建有关与组织中的电子数据展示事例相关联的保留报告。
    
- 本主题中的示例脚本不受任何 Microsoft 标准支持计划或服务支持。示例脚本按原样提供，不提供任何种类的担保。Microsoft 进一步声明，不提供任何默示担保，包括但不限于适销性或特定用途适用性的默示担保。使用或运行示例脚本和文档所产生的任何风险均由你自己承担。对于因使用或无法使用示例脚本或文档而产生的任何损失（包括但不限于商业利润损失、业务中断、业务信息丢失或其他金钱损失），Microsoft、脚本作者或参与创建、生成或交付脚本的任何人都不承担任何责任，即使 Microsoft 已被告知存在这种损失的可能性，也不例外。
    
## <a name="step-1-connect-to-the-security--compliance-center-powershell"></a>步骤 1: 连接到安全 & 合规中心 PowerShell

第一步是连接到您的组织的安全 & 合规中心。
  
1. 使用文件名后缀. ps1; 将以下文本保存到 Windows PowerShell 脚本文件中。例如, `ConnectSCC.ps1`。 
    
      ```
      # Get login credentials 
      $UserCredential = Get-Credential 
      $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection 
      Import-PSSession $Session -AllowClobber -DisableNameChecking 
      $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Security & Compliance Center)" 
    ```

2. 在本地计算机上, 打开 Windows PowerShell 并转到保存该脚本的文件夹。 
    
3. 运行脚本;例如:

    ```
    .\ConnectSCC.ps1
    ```
   
4. 当系统提示你输入凭据时, 请输入你的电子邮件地址和密码, 然后单击 **"确定"**。 
  
## <a name="step-2-run-the-script-to-report-on-holds-associated-with-ediscovery-cases"></a>步骤 2: 运行脚本以报告与电子数据展示事例相关联的保留

在连接到安全 & 合规中心 PowerShell 之后, 下一步是创建并运行脚本, 以收集有关您组织中的电子数据展示事例的信息。 
  
1. 使用文件名后缀. ps1; 将以下文本保存到 Windows PowerShell 脚本文件中。例如, CaseHoldsReport。 
    
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

2. 在步骤1中打开的 Windows PowerShell 会话中, 转到保存脚本的文件夹。 
    
3. 运行脚本;例如:

    ```
    .\CaseHoldsReport.ps1
    ```

    脚本将提示要将报告保存到的目标文件夹。 
    
4. 键入要将报告保存到的文件夹的完整路径名称, 然后按**enter**。
    
    > [!TIP]
    > 若要将报告保存在脚本所在的同一文件夹中, 请在系统提示输入目标文件夹时键入句点 (".")。 若要将报告保存在脚本所在的文件夹的子文件夹中, 只需键入子文件夹的名称即可。 
  
    脚本开始收集组织中所有电子数据展示事例的相关信息。 在运行脚本时不访问报告文件。 脚本完成后, 将在 Windows PowerShell 会话中显示一条确认消息。 显示此消息后, 您可以访问您在步骤4中指定的文件夹中的报告。 报告的文件名为`CaseHoldsReport<DateTimeStamp>.csv`。

    此外, 该脚本还将创建一个报告, 其中包含不包含任何保留的案例列表。 此报告的文件名为`CaseswithNoHolds<DateTimeStamp>.csv`。
    
    下面的示例展示了如何运行 CaseHoldsReport 脚本。 
    
    ![运行 CaseHoldsReport 脚本后的输出](media/7d312ed5-505e-4ec5-8f06-3571e3524a1a.png)
  
## <a name="more-information"></a>更多信息

事例包含运行本文中的脚本时创建的报告, 其中包含有关每个保留的以下信息。 如前面所述, 您必须是电子数据展示管理员才能返回组织中所有保留的信息。 有关案例保留的详细信息, 请参阅[电子数据展示事例](ediscovery-cases.md)。
  
  - 保留的名称和与该保留相关联的电子数据展示事例的名称。
    
  - 电子数据展示事例是否处于活动状态或已关闭状态。
    
  - 保留是否已启用或已禁用。
    
  - 与保留相关联的电子数据展示事例的成员。 事例成员可以查看或管理事例, 具体取决于他们已分配的电子数据展示权限。
    
  - 案例的创建时间和日期。
    
  - 如果案例关闭, 则关闭它以及关闭它的时间和日期。
    
  - 处于保留状态的 Exchange 邮箱和 SharePoint 网站位置。
    
  - 如果保留是基于查询的查询语法, 则为。
    
  - 创建保留的时间和日期以及创建该保留的人员。
    
  - 上次更改保留的时间和日期以及更改了保留的人员。
