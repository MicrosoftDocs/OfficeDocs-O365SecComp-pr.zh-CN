---
title: 获取有关 Office 365 中管理移动设备管理 (MDM) 设备的详细信息
ms.author: brendonb
author: brendonb
manager: laurawi
ms.date: 6/12/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MBS150
- MET150
ms.assetid: 5602963c-a1f2-4c21-afb9-f66cd7dca1f0
description: 本文介绍如何使用 Windows PowerShell for Office 365 设置为移动设备管理您组织中获取有关设备的详细信息。
ms.openlocfilehash: 2e406d3583e7892531b7c74bef0db374672956c7
ms.sourcegitcommit: c31424cafbf1953f2864d7e2ceb95b329a694edb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/29/2018
ms.locfileid: "23272527"
---
# <a name="get-details-about-devices-managed-by-mobile-device-management-mdm-for-office-365"></a>获取有关 Office 365 中管理移动设备管理 (MDM) 设备的详细信息

本文介绍如何使用 Windows PowerShell for Office 365 设置为移动设备管理您组织中获取有关设备的详细信息。 
  
## <a name="what-device-details-can-i-get"></a>可以获得哪些设备详细信息？

下面是细分。
  
|**详细信息**|**在 PowerShell 中查找内容**|
|:-----|:-----|
|设备已[注册 Office 365 MDM](enroll-your-mobile-device.md) <br/> |*IsManaged*参数的值是：  <br/> **True** = 注册设备。  <br/> **False** = 不报名设备。  <br/> |
|设备符合您的[设备安全策略](https://go.microsoft.com/fwlink/?linkid=615144) <br/> |*IsCompliant*参数的值是：  <br/> **True** = 设备是否符合策略。  <br/> **False** = 设备不符合策略。  <br/> |
   
![显示 AAD 命令行管理程序参数值是否注册设备和投诉流](media/647b70f4-f886-41ef-8bff-04773a1da278.png)
  
> [!NOTE]
> 命令和脚本本文中的也将返回有关由[Microsoft Intune](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune)任何设备的详细信息。 
  
## <a name="before-you-begin"></a>准备工作

有几件事，您需要设置设置为在本文中运行的命令和脚本所述。
  
### <a name="step-1-download-and-install-the-azure-active-directory-module-for-windows-powershell"></a>步骤 1： 下载并安装 Azure Active Directory 的 Windows PowerShell 的模块

有关这些步骤的详细信息，请参阅[Connect to Office 365 PowerShell](https://docs.microsoft.com/Office365/enterprise/powershell/connect-to-office-365-powershell)。
  
1. 转到[Microsoft Online Services 登录助手的 IT 专业人员 RTWl](https://www.microsoft.com/en-us/download/details.aspx?id=41950)并单击**下载**的 Microsoft Online Services 登录助手。 
    
2. 安装用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块，具体步骤如下：
    
    1. 打开管理员级 PowerShell 命令提示符。
        
    2. 运行`Install-Module MSOnline`命令。
        
    3. 如果提示您安装 NuGet 提供程序，请键入`Y`，然后按 ENTER。
        
    4. 如果提示您安装从 PSGallery 模块，请键入`Y`，然后按 ENTER。
        
    5. 安装完成后，关闭 PowerShell 命令窗口。
    
### <a name="step-2-connect-to-your-office-365-subscription"></a>步骤 2：连接到 Office 365 订阅

1. Windows Azure Active Directory 模块的 Windows PowerShell 中，运行以下命令。</br>  
  `$UserCredential = Get-Credential`

2. **Windows PowerShell 凭据请求**对话框中，键入用户名和在 Office 365 全局管理员帐户的密码，然后单击**确定**。
    
3. 运行以下命令。</br>
    `
  Connect-MsolService -Credential $UserCredential
  `

### <a name="step-3-make-sure-youre-able-to-run-powershell-scripts"></a>步骤 3： 请确保您能够运行 PowerShell 脚本

> [!NOTE]
> 如果您已设置为运行 PowerShell 脚本，则可以跳过此步骤。 
  
若要运行**Get MsolUserDeviceComplianceStatus.ps1**脚本，您需要启用的 PowerShell 脚本运行。 
  
1. 从 Windows 桌面上，单击**开始**，然后键入 Windows PowerShell。右键单击**Windows PowerShell**中，，然后单击**以管理员身份运行**。
    
2. 运行以下命令。</br>
  `Set-ExecutionPolicy RemoteSigned`

3. 出现提示时，键入`Y`，然后按 Enter。 
    
## <a name="run-the-get-msoldevice-cmdlet-to-display-details-for-all-devices-in-your-organization"></a>运行 Get MsolDevice cmdlet，以显示组织中的所有设备的详细信息

1. 打开用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块。
    
2. 运行以下命令。</br>
  ```
  Get-MsolDevice -All -ReturnRegisteredOwners | Where-Object {$_.RegisteredOwners.Count -gt 0}
  ```

有关更多示例，请参阅[Get MsolDevice](https://go.microsoft.com/fwlink/?linkid=841721)。
  
## <a name="run-a-script-to-get-device-details"></a>运行脚本以获取设备的详细信息

### <a name="first-save-the-script-to-your-computer"></a>首先，将脚本保存到您的计算机

1. 复制并粘贴到记事本中的以下文本。</br> 
  ```
  param (
      [PSObject[]]$users = @(),
      [Switch]$export,
      [String]$exportFileName = "UserDeviceComplianceStatus_" + (Get-Date -Format "yyMMdd_HHMMss") + ".csv",
      [String]$exportPath = [Environment]::GetFolderPath("Desktop")
   )
  [System.Collections.IDictionary]$script:schema = @{
      
      DeviceId = ''
      DeviceOSType = ''
      DeviceOSVersion = ''
      DeviceTrustLevel = ''
      DisplayName = ''
      IsCompliant = ''
      IsManaged = ''
      ApproximateLastLogonTimestamp = ''
      DeviceObjectId = ''    
      RegisteredOwnerUpn = ''
      RegisteredOwnerObjectId = ''
      RegisteredOwnerDisplayName = ''
  }
  function createResultObject
  {
      [PSObject]$resultObject = New-Object -TypeName PSObject -Property $script:schema
      return $resultObject
  }
  If ($users.Count -eq 0)
  {
      $users = Get-MsolUser
  }
  [PSObject[]]$result = foreach ($u in $users)
  {
      
      [PSObject]$devices = get-msoldevice -RegisteredOwnerUpn $u.UserPrincipalName
      foreach ($d in $devices)
      {
          [PSObject]$deviceResult = createResultObject
          $deviceResult.DeviceId = $d.DeviceId 
          $deviceResult.DeviceOSType = $d.DeviceOSType 
          $deviceResult.DeviceOSVersion = $d.DeviceOSVersion 
          $deviceResult.DeviceTrustLevel = $d.DeviceTrustLevel
          $deviceResult.DisplayName = $d.DisplayName
          $deviceResult.IsCompliant = $d.GraphDeviceObject.IsCompliant
          $deviceResult.IsManaged = $d.GraphDeviceObject.IsManaged
          $deviceResult.DeviceObjectId = $d.ObjectId
          $deviceResult.RegisteredOwnerUpn = $u.UserPrincipalName
          $deviceResult.RegisteredOwnerObjectId = $u.ObjectId
          $deviceResult.RegisteredOwnerDisplayName = $u.DisplayName
          $deviceResult.ApproximateLastLogonTimestamp = $d.ApproximateLastLogonTimestamp
          $deviceResult
      }
  }
  If ($export)
  {
      $result | Export-Csv -path ($exportPath + "\" + $exportFileName) -NoTypeInformation
  }
  Else
  {
      $result
  }
  
  ```

2. 使用 **.ps1**文件扩展名保存为 Windows PowerShell 脚本文件。 </br>示例：</br> `Get-MsolUserDeviceComplianceStatus.ps1`.
    
### <a name="run-the-script-to-get-device-information-for-a-single-user-account"></a>运行该脚本以使单个用户帐户的设备信息

1. 打开用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块。
    
2. 导航到保存该脚本的文件夹。例如，如果您将其保存到 C:\PS-Scripts，您将运行以下命令。</br>
    `cd C:\PS-Scripts`

3. 运行以下命令以确定用户想要获取设备的详细信息。此示例获取 bar@example.com 详细信息。</br>
  ```
  $u = Get-MsolUser -UserPrincipalName bar@example.com
  ```

4. 运行以下命令以启动脚本。</br>
  ```
  .\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export
  ```

信息到 Windows 桌面上导出为 CSV 文件。您可以使用其他参数指定的文件名和路径 CSV。
  
### <a name="run-the-script-to-get-device-information-for-a-group-of-users"></a>运行脚本以获取针对一组用户设备信息

1. 打开用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块。
    
2. 导航到保存该脚本的文件夹。例如，如果您将其保存到 C:\PS-Scripts，您将运行以下命令。</br>
  `cd C:\PS-Scripts`

3. 运行以下命令以标识组您希望获取设备的详细信息。此示例获取 FinanceStaff 组中的用户详细信息。</br>
  ```
  $u = Get-MsolGroupMember -SearchString "FinanceStaff" | % { Get-MsolUser -ObjectId $_.ObjectId }
  ```

4. 运行以下命令以启动脚本。</br>
  ```
  .\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export
  ```

信息到 Windows 桌面上导出为 CSV 文件。您可以使用其他参数指定的文件名和路径 CSV。
  
## <a name="more-info"></a>详细信息

[Office 365 的 MDM 的概述](overview-of-mdm.md)
  
[Get MsolDevice](https://go.microsoft.com/fwlink/?linkid=841721)
  

