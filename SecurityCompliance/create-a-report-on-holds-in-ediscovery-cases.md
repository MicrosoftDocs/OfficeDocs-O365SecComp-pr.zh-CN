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
# <a name="create-a-report-on-holds-in-ediscovery-cases-in-office-365"></a>在 Office 365 中的电子数据展示事例中保留创建报表
  
本文中的脚本允许电子数据展示管理员和电子数据展示管理员生成报告包含有关与 Office 365 安全性的电子数据展示事例关联的所有保留的信息的&amp;合规性中心。该报告包含信息，如条件保留名称的相关联的内容位置的置于保持状态，以及是否保留项是基于查询的。如果没有任何保留的情况下，脚本将创建其他报告的情况下，不保留项列表。

请参阅有关的信息包括在报表的详细说明[详细信息](#more-information)部分。 
  
## <a name="before-you-begin"></a>准备工作

- 若要生成您的组织中的所有电子数据展示事例报告，您必须是电子数据展示管理员在组织中。如果您是经理电子数据展示，报告将仅包含有关您可以访问的用例信息。有关电子数据展示权限的详细信息，请参阅[分配 Office 365 安全性的电子数据展示权限&amp;合规性中心](assign-ediscovery-permissions.md)。
    
- 本文中的脚本具有最少的错误处理。主要用途是快速创建有关保留与您的组织中的电子数据展示事例关联的报告。
    
- 本主题中的示例脚本不受任何 Microsoft 标准支持计划或服务支持。示例脚本按原样提供，不提供任何种类的担保。Microsoft 进一步声明，不提供任何默示担保，包括但不限于适销性或特定用途适用性的默示担保。使用或运行示例脚本和文档所产生的任何风险均由你自己承担。对于因使用或无法使用示例脚本或文档而产生的任何损失（包括但不限于商业利润损失、业务中断、业务信息丢失或其他金钱损失），Microsoft、脚本作者或参与创建、生成或交付脚本的任何人都不承担任何责任，即使 Microsoft 已被告知存在这种损失的可能性，也不例外。
    
## <a name="step-1-connect-to-the-security-amp-compliance-center-using-remote-powershell"></a>步骤 1： 连接到安全性&amp;合规性中心使用远程 PowerShell

第一步是将 Windows PowerShell 连接到安全性&amp;的组织的合规性中心。
  
1. 使用.ps1; filename 后缀将以下文本保存到的 Windows PowerShell 脚本文件例如， `ConnectSCC.ps1`。 
    
      ```
      # Get login credentials 
      $UserCredential = Get-Credential 
      $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection 
      Import-PSSession $Session -AllowClobber -DisableNameChecking 
      $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Office 365 Security &amp; Compliance Center)" 
    ```

2. 在本地计算机上打开 Windows PowerShell 并转到保存该脚本的文件夹。 
    
3. 运行脚本。例如：

    ```
    .\ConnectSCC.ps1
    ```
   
4. 当提示输入凭据，输入您的电子邮件地址和密码，，，然后单击**确定**。 
  
## <a name="step-2-run-the-script-to-report-on-holds-associated-with-ediscovery-cases"></a>步骤 2： 运行脚本，以报告包含与电子数据展示事例

已连接到安全性后&amp;使用远程 PowerShell 的合规性中心下, 一步是创建和运行的脚本收集有关您的组织中的电子数据展示事例的信息。 
  
1. 使用.ps1; filename 后缀将以下文本保存到的 Windows PowerShell 脚本文件例如，CaseHoldsReport.ps1。 
    
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

2. 在 Windows PowerShell 会话中打开在步骤 1 中，转到保存该脚本的文件夹。 
    
3. 运行脚本。例如：

    ```
    .\CaseHoldsReport.ps1
    ```

    该脚本将会进行提示保存报表的目标文件夹。 
    
4. 键入要保存，该报表的文件夹的完整路径名称，然后按**Enter**。
    
    > [!TIP]
    > 若要将报告保存该脚本位于同一文件夹中，键入一段 ("。") 时提示您目标文件夹。若要保存该脚本所在的文件夹中的子文件夹中的报告，只需键入子文件夹的名称。 
  
    脚本开始收集有关您的组织中的所有电子数据展示事例的信息。脚本运行时，不访问报告文件。完成该脚本后，在 Windows PowerShell 会话中显示一条确认消息。显示此消息之后，您可以访问您在步骤 4 中指定的文件夹中的报告。报表的文件名为`CaseHoldsReport<DateTimeStamp>.csv`。

    另外，该脚本还创建报表的情况下没有任何保留项的列表。此报告的文件名为`CaseswithNoHolds<DateTimeStamp>.csv`。
    
    下面是运行 CaseHoldsReport.ps1 脚本的一个示例。 
    
    ![后运行 CaseHoldsReport.ps1 脚本输出](media/7d312ed5-505e-4ec5-8f06-3571e3524a1a.png)
  
## <a name="more-information"></a>更多信息

这种情况，其中包含本文中运行该脚本时创建的报告包含有关每个保留的以下信息。如前所述，您必须是电子数据展示管理员联系，以返回组织中的所有保留项的信息。包含与案例相关的详细信息，请参阅[Office 365 安全性的电子数据展示事例&amp;合规性中心](ediscovery-cases.md)。
  
  - 保留和电子数据展示案例保留项关联的名称的名称。
    
  - 是否电子数据展示事例是活动还是关闭。
    
  - 是否启用或禁用保留项。
    
  - 与关联保留电子数据展示事例的成员。案例成员可以查看或管理的情况下，根据已被分配给他们的电子数据展示权限。
    
  - 这种情况的创建的日期和时间。
    
  - 如果已关闭种情况下，关闭关闭它与时间和日期它的人员。
    
  - Exchange 邮箱和 SharePoint 网站处于保持状态的位置。
    
  - 如果保留项是基于查询的查询语法。
    
  - 时间和保留项的创建的日期和创建它的人员。
    
  - 时间和日期上次更改保留更改它的人员。
