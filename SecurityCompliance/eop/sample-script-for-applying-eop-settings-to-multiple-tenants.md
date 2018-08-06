---
title: 将 EOP 设置应用到多个租户的示例脚本
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: e87e84e1-7be0-44bf-a414-d91d60ed8817
description: 以下示例脚本允许管理多个租户（公司）的 Microsoft Exchange Online Protection (EOP) 管理员使用 Windows PowerShell 将配置设置应用到租户。
ms.openlocfilehash: 899cc51f80230e92b573803301f0e462205af61a
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2018
ms.locfileid: "22028089"
---
# <a name="sample-script-for-applying-eop-settings-to-multiple-tenants"></a>将 EOP 设置应用到多个租户的示例脚本

以下示例脚本允许管理多个租户（公司）的 Microsoft Exchange Online Protection (EOP) 管理员使用 Windows PowerShell 将配置设置应用到租户。
  
### <a name="to-run-a-script-or-cmdlet-on-multiple-tenants"></a>在多个租户上运行脚本或 cmdlet

1. 使用 Excel 等应用程序创建 .csv 文件（例如，c:\scripts\inputfile.csv）：
    
1. 在 .csv 文件中，指定两个列名称：UserName 和 Cmdlet。
    
2. 对于 .csv 文件中的每一行，在 UserName 列中添加租户的管理员名称，在 Cmdlet 列中添加对该租户运行的 cmdlet。例如，使用 admin@contoso.com 和 Get-AcceptedDomain。
    
2. 将 [RunCmdletOnMultipleTenants.ps1](sample-script-for-applying-eop-settings-to-multiple-tenants.md#RunCmdletOnMultipleTenants.ps1) 脚本复制到记事本等编辑器，然后将文件保存到使 .ps1 文件易于查找的位置（如 c:\scripts）。 
    
3. 使用以下语法运行此脚本：
    
     `&amp; "<file path>\RunCmdletOnMultipleTenants.ps1" "<file path>\inputfile.csv"`
    
    下面是一个示例。 
    
  ```
  &amp; "c:\scripts\RunCmdletOnMultipleTenanats.ps1" "c:\scripts\inputfile.csv"
  ```

4. 每个租户都将登录，并将运行该 cmdlet。
    
## <a name="runcmdletonmultipletenantsps1"></a>RunCmdletOnMultipleTenants.ps1
<a name="RunCmdletOnMultipleTenants.ps1"> </a>

```
# This script runs Windows PowerShell cmdlets on multiple tenants.
# Usage: RunCmdletOnMultipleTenants.ps1 inputfile.csv
#  
# .csv input file sample: 
# UserName,Cmdlet
# admin@contoso.com,Get-AcceptedDomain | ft Name
# URI for connecting to remote Windows PowerShell
$URI = "https://ps.protection.outlook.com/powershell-liveid/"
# Get the .csv file name as an argument to this script.
$FilePath = $args[0]
# Import the UserName and Cmdlet values from the .csv file.
$CompanyList = Import-CSV $FilePath
# Loop through each entry from the .csv file.
ForEach ($Company in $CompanyList) {
# Get the current entry's UserName.
$UserName = $Company.UserName
# Get the current entry's Cmdlet.
$Cmdlet = $Company.Cmdlet
# Create a PowerShell credential object by using the current entry's UserName. Prompt for the password.
$UserCredential = Get-Credential -username $UserName
# Log on to a new Windows PowerShell session.
$Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri $URI -Credential $UserCredential -Authentication Basic -AllowRedirection
Import-PSSession $Session
# Here's where the script to be run on the tenant goes.
# In this example, the cmdlet in the .csv file runs.
Invoke-Expression $Cmdlet
# End the current PowerShell session.
remove-pssession -session $Session
}

```


