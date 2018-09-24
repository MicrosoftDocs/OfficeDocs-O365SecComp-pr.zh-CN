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
ms.openlocfilehash: 90ee59c5afed1cd260e13134299a7cb4f17dc5bc
ms.sourcegitcommit: 17c7e18d7d00135b1af40cbea117c9a817a41117
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/24/2018
ms.locfileid: "24972314"
---
# <a name="get-details-about-devices-managed-by-mobile-device-management-mdm-for-office-365"></a><span data-ttu-id="9413b-103">获取有关 Office 365 中管理移动设备管理 (MDM) 设备的详细信息</span><span class="sxs-lookup"><span data-stu-id="9413b-103">Get details about devices managed by Mobile Device Management (MDM) for Office 365</span></span>

<span data-ttu-id="9413b-104">本文介绍如何使用 Windows PowerShell for Office 365 设置为移动设备管理您组织中获取有关设备的详细信息。</span><span class="sxs-lookup"><span data-stu-id="9413b-104">This article shows you how to use Windows PowerShell to get details about the devices in your organization that you set up for Mobile Device Management for Office 365.</span></span> 
  
## <a name="what-device-details-can-i-get"></a><span data-ttu-id="9413b-105">可以获得哪些设备详细信息？</span><span class="sxs-lookup"><span data-stu-id="9413b-105">What device details can I get?</span></span>

<span data-ttu-id="9413b-106">下面是细分。</span><span class="sxs-lookup"><span data-stu-id="9413b-106">Here's a breakdown.</span></span>
  
|<span data-ttu-id="9413b-107">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="9413b-107">**Detail**</span></span>|<span data-ttu-id="9413b-108">**在 PowerShell 中查找内容**</span><span class="sxs-lookup"><span data-stu-id="9413b-108">**What to look for in PowerShell**</span></span>|
|:-----|:-----|
|<span data-ttu-id="9413b-109">设备已[注册 Office 365 MDM](enroll-your-mobile-device.md)</span><span class="sxs-lookup"><span data-stu-id="9413b-109">Device is [enrolled in MDM for Office 365](enroll-your-mobile-device.md)</span></span> <br/> |<span data-ttu-id="9413b-110">*IsManaged*参数的值是：</span><span class="sxs-lookup"><span data-stu-id="9413b-110">The value of the  *isManaged*  parameter is:</span></span>  <br/> <span data-ttu-id="9413b-111">**True** = 注册设备。</span><span class="sxs-lookup"><span data-stu-id="9413b-111">**True** = device is enrolled.</span></span>  <br/> <span data-ttu-id="9413b-112">**False** = 不报名设备。</span><span class="sxs-lookup"><span data-stu-id="9413b-112">**False** = device is not enrolled.</span></span>  <br/> |
|<span data-ttu-id="9413b-113">设备符合您的[设备安全策略](https://go.microsoft.com/fwlink/?linkid=615144)</span><span class="sxs-lookup"><span data-stu-id="9413b-113">Device is compliant with your [device security policies](https://go.microsoft.com/fwlink/?linkid=615144)</span></span> <br/> |<span data-ttu-id="9413b-114">*IsCompliant*参数的值是：</span><span class="sxs-lookup"><span data-stu-id="9413b-114">The value of the  *isCompliant*  parameter is:</span></span>  <br/> <span data-ttu-id="9413b-115">**True** = 设备是否符合策略。</span><span class="sxs-lookup"><span data-stu-id="9413b-115">**True** = device is compliant with policies.</span></span>  <br/> <span data-ttu-id="9413b-116">**False** = 设备不符合策略。</span><span class="sxs-lookup"><span data-stu-id="9413b-116">**False** = device is not compliant with policies.</span></span>  <br/> |
   
![显示 AAD 命令行管理程序参数值是否注册设备和投诉流](media/647b70f4-f886-41ef-8bff-04773a1da278.png)
  
> [!NOTE]
> <span data-ttu-id="9413b-118">命令和脚本本文中的也将返回有关由[Microsoft Intune](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune)任何设备的详细信息。</span><span class="sxs-lookup"><span data-stu-id="9413b-118">The commands and scripts in this article will also return details about any devices that are managed by [Microsoft Intune](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune).</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="9413b-119">准备工作</span><span class="sxs-lookup"><span data-stu-id="9413b-119">Before you begin</span></span>

<span data-ttu-id="9413b-120">有几件事，您需要设置设置为在本文中运行的命令和脚本所述。</span><span class="sxs-lookup"><span data-stu-id="9413b-120">There are a few things you'll need to set up to run the commands and scripts described in this article.</span></span>
  
### <a name="step-1-download-and-install-the-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="9413b-121">步骤 1： 下载并安装 Azure Active Directory 的 Windows PowerShell 的模块</span><span class="sxs-lookup"><span data-stu-id="9413b-121">Step 1: Download and install the Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="9413b-122">有关这些步骤的详细信息，请参阅[Connect to Office 365 PowerShell](https://docs.microsoft.com/Office365/enterprise/powershell/connect-to-office-365-powershell)。</span><span class="sxs-lookup"><span data-stu-id="9413b-122">For more info on these steps, see [Connect to Office 365 PowerShell](https://docs.microsoft.com/Office365/enterprise/powershell/connect-to-office-365-powershell).</span></span>
  
1. <span data-ttu-id="9413b-123">转到[Microsoft Online Services 登录助手的 IT 专业人员 RTWl](https://www.microsoft.com/en-us/download/details.aspx?id=41950)并单击**下载**的 Microsoft Online Services 登录助手。</span><span class="sxs-lookup"><span data-stu-id="9413b-123">Go to [Microsoft Online Services Sign-In Assistant for IT Professionals RTWl](https://www.microsoft.com/en-us/download/details.aspx?id=41950) and click **Download** for Microsoft Online Services Sign-in Assistant.</span></span> 
    
2. <span data-ttu-id="9413b-124">安装用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块，具体步骤如下：</span><span class="sxs-lookup"><span data-stu-id="9413b-124">Install the Microsoft Azure Active Directory Module for Windows PowerShell with these steps:</span></span>
    
    1. <span data-ttu-id="9413b-125">打开管理员级 PowerShell 命令提示符。</span><span class="sxs-lookup"><span data-stu-id="9413b-125">Open an administrator-level PowerShell command prompt.</span></span>
        
    2. <span data-ttu-id="9413b-126">运行`Install-Module MSOnline`命令。</span><span class="sxs-lookup"><span data-stu-id="9413b-126">Run the `Install-Module MSOnline` command.</span></span>
        
    3. <span data-ttu-id="9413b-127">如果提示您安装 NuGet 提供程序，请键入`Y`，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="9413b-127">If prompted to install the NuGet provider, type `Y` and press ENTER.</span></span>
        
    4. <span data-ttu-id="9413b-128">如果提示您安装从 PSGallery 模块，请键入`Y`，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="9413b-128">If prompted to install the module from PSGallery, type `Y` and press ENTER.</span></span>
        
    5. <span data-ttu-id="9413b-129">安装完成后，关闭 PowerShell 命令窗口。</span><span class="sxs-lookup"><span data-stu-id="9413b-129">After installation, close the PowerShell command window.</span></span>
    
### <a name="step-2-connect-to-your-office-365-subscription"></a><span data-ttu-id="9413b-130">步骤 2：连接到 Office 365 订阅</span><span class="sxs-lookup"><span data-stu-id="9413b-130">Step 2: Connect to your Office 365 subscription</span></span>

1. <span data-ttu-id="9413b-131">Windows Azure Active Directory 模块的 Windows PowerShell 中，运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="9413b-131">In the Windows Azure Active Directory Module for Windows PowerShell, run the following command.</span></span><br/>  
  `$UserCredential = Get-Credential`

2. <span data-ttu-id="9413b-132">**Windows PowerShell 凭据请求**对话框中，键入用户名和在 Office 365 全局管理员帐户的密码，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="9413b-132">In the **Windows PowerShell Credential Request** dialog box, type the user name and password for your Office 365 global admin account, and then click **OK**.</span></span>
    
3. <span data-ttu-id="9413b-133">运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="9413b-133">Run the following command.</span></span><br/>
    `
  Connect-MsolService -Credential $UserCredential
  `

### <a name="step-3-make-sure-youre-able-to-run-powershell-scripts"></a><span data-ttu-id="9413b-134">步骤 3： 请确保您能够运行 PowerShell 脚本</span><span class="sxs-lookup"><span data-stu-id="9413b-134">Step 3: Make sure you're able to run PowerShell scripts</span></span>

> [!NOTE]
> <span data-ttu-id="9413b-135">如果您已设置为运行 PowerShell 脚本，则可以跳过此步骤。</span><span class="sxs-lookup"><span data-stu-id="9413b-135">You can skip this step if you're already set up to run PowerShell scripts.</span></span> 
  
<span data-ttu-id="9413b-136">若要运行**Get MsolUserDeviceComplianceStatus.ps1**脚本，您需要启用的 PowerShell 脚本运行。</span><span class="sxs-lookup"><span data-stu-id="9413b-136">To run the **Get-MsolUserDeviceComplianceStatus.ps1** script, you need to enable the running of PowerShell scripts.</span></span> 
  
1. <span data-ttu-id="9413b-p101">从 Windows 桌面上，单击**开始**，然后键入 Windows PowerShell。右键单击**Windows PowerShell**中，，然后单击**以管理员身份运行**。</span><span class="sxs-lookup"><span data-stu-id="9413b-p101">From your Windows Desktop, click **Start**, and then type Windows PowerShell. Right click **Windows PowerShell**, and then click **Run as administrator**.</span></span>
    
2. <span data-ttu-id="9413b-139">运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="9413b-139">Run the following command.</span></span><br/>
  `Set-ExecutionPolicy RemoteSigned`

3. <span data-ttu-id="9413b-140">出现提示时，键入`Y`，然后按 Enter。</span><span class="sxs-lookup"><span data-stu-id="9413b-140">When prompted, type `Y` and then press Enter.</span></span> 
    
## <a name="run-the-get-msoldevice-cmdlet-to-display-details-for-all-devices-in-your-organization"></a><span data-ttu-id="9413b-141">运行 Get MsolDevice cmdlet，以显示组织中的所有设备的详细信息</span><span class="sxs-lookup"><span data-stu-id="9413b-141">Run the Get-MsolDevice cmdlet to display details for all devices in your organization</span></span>

1. <span data-ttu-id="9413b-142">打开用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块。</span><span class="sxs-lookup"><span data-stu-id="9413b-142">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>
    
2. <span data-ttu-id="9413b-143">运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="9413b-143">Run the following command.</span></span><br/>
  ```
  Get-MsolDevice -All -ReturnRegisteredOwners | Where-Object {$_.RegisteredOwners.Count -gt 0}
  ```

<span data-ttu-id="9413b-144">有关更多示例，请参阅[Get MsolDevice](https://go.microsoft.com/fwlink/?linkid=841721)。</span><span class="sxs-lookup"><span data-stu-id="9413b-144">For more examples, see [Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=841721).</span></span>
  
## <a name="run-a-script-to-get-device-details"></a><span data-ttu-id="9413b-145">运行脚本以获取设备的详细信息</span><span class="sxs-lookup"><span data-stu-id="9413b-145">Run a script to get device details</span></span>

### <a name="first-save-the-script-to-your-computer"></a><span data-ttu-id="9413b-146">首先，将脚本保存到您的计算机</span><span class="sxs-lookup"><span data-stu-id="9413b-146">First, save the script to your computer</span></span>

1. <span data-ttu-id="9413b-147">复制并粘贴到记事本中的以下文本。</span><span class="sxs-lookup"><span data-stu-id="9413b-147">Copy and paste the following text into Notepad.</span></span><br/> 
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

2. <span data-ttu-id="9413b-148">使用 **.ps1**文件扩展名保存为 Windows PowerShell 脚本文件。</span><span class="sxs-lookup"><span data-stu-id="9413b-148">Save it as a Windows PowerShell script file by using the file extension **.ps1**.</span></span> <br/><span data-ttu-id="9413b-149">示例：</span><span class="sxs-lookup"><span data-stu-id="9413b-149">Example:</span></span><br/> <span data-ttu-id="9413b-150">`Get-MsolUserDeviceComplianceStatus.ps1`.</span><span class="sxs-lookup"><span data-stu-id="9413b-150"></span></span>
    
### <a name="run-the-script-to-get-device-information-for-a-single-user-account"></a><span data-ttu-id="9413b-151">运行该脚本以使单个用户帐户的设备信息</span><span class="sxs-lookup"><span data-stu-id="9413b-151">Run the script to get device information for a single user account</span></span>

1. <span data-ttu-id="9413b-152">打开用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块。</span><span class="sxs-lookup"><span data-stu-id="9413b-152">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>
    
2. <span data-ttu-id="9413b-p102">导航到保存该脚本的文件夹。例如，如果您将其保存到 C:\PS-Scripts，您将运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="9413b-p102">Navigate to the folder where you saved the script. For example, if you saved it to C:\PS-Scripts, you'd run the following command.</span></span><br/>
    `cd C:\PS-Scripts`

3. <span data-ttu-id="9413b-p103">运行以下命令以确定用户想要获取设备的详细信息。此示例获取 bar@example.com 详细信息。</span><span class="sxs-lookup"><span data-stu-id="9413b-p103">Run the following command to identify the user you want to get device details for. This example gets details for bar@example.com.</span></span><br/>
  ```
  $u = Get-MsolUser -UserPrincipalName bar@example.com
  ```

4. <span data-ttu-id="9413b-157">运行以下命令以启动脚本。</span><span class="sxs-lookup"><span data-stu-id="9413b-157">Run the following command to initiate the script.</span></span><br/>
  ```
  .\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export
  ```

<span data-ttu-id="9413b-p104">信息到 Windows 桌面上导出为 CSV 文件。您可以使用其他参数指定的文件名和路径 CSV。</span><span class="sxs-lookup"><span data-stu-id="9413b-p104">The information is exported to your Windows Desktop as a CSV file. You can use additional parameters to specify the file name and path of the CSV.</span></span>
  
### <a name="run-the-script-to-get-device-information-for-a-group-of-users"></a><span data-ttu-id="9413b-160">运行脚本以获取针对一组用户设备信息</span><span class="sxs-lookup"><span data-stu-id="9413b-160">Run the script to get device information for a group of users</span></span>

1. <span data-ttu-id="9413b-161">打开用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块。</span><span class="sxs-lookup"><span data-stu-id="9413b-161">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>
    
2. <span data-ttu-id="9413b-p105">导航到保存该脚本的文件夹。例如，如果您将其保存到 C:\PS-Scripts，您将运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="9413b-p105">Navigate to the folder where you saved the script. For example, if you saved it to C:\PS-Scripts, you'd run the following command.</span></span><br/>
  `cd C:\PS-Scripts`

3. <span data-ttu-id="9413b-p106">运行以下命令以标识组您希望获取设备的详细信息。此示例获取 FinanceStaff 组中的用户详细信息。</span><span class="sxs-lookup"><span data-stu-id="9413b-p106">Run the following command to identify the group you want to get device details for. This example gets details for users in the FinanceStaff group.</span></span><br/>
  ```
  $u = Get-MsolGroupMember -SearchString "FinanceStaff" | % { Get-MsolUser -ObjectId $_.ObjectId }
  ```

4. <span data-ttu-id="9413b-166">运行以下命令以启动脚本。</span><span class="sxs-lookup"><span data-stu-id="9413b-166">Run the following command to initiate the script.</span></span><br/>
  ```
  .\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export
  ```

<span data-ttu-id="9413b-p107">信息到 Windows 桌面上导出为 CSV 文件。您可以使用其他参数指定的文件名和路径 CSV。</span><span class="sxs-lookup"><span data-stu-id="9413b-p107">The information is exported to your Windows Desktop as a CSV file. You can use additional parameters to specify the file name and path of the CSV.</span></span>
  
## <a name="more-info"></a><span data-ttu-id="9413b-169">详细信息</span><span class="sxs-lookup"><span data-stu-id="9413b-169">More info</span></span>

[<span data-ttu-id="9413b-170">Office 365 的 MDM 的概述</span><span class="sxs-lookup"><span data-stu-id="9413b-170">Overview of MDM for Office 365</span></span>](overview-of-mdm.md)
  
[<span data-ttu-id="9413b-171">Get MsolDevice</span><span class="sxs-lookup"><span data-stu-id="9413b-171">Get-MsolDevice</span></span>](https://go.microsoft.com/fwlink/?linkid=841721)
  

