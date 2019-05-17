---
title: 使用精确数据匹配创建自定义敏感信息类型
ms.author: deniseb
author: denisebmsft
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: 05/15/2019
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 使用基于精确数据匹配的分类创建自定义敏感信息类型。
ms.openlocfilehash: 3b15bf0197918d6bbc3897f9fa578c40b70d3f4e
ms.sourcegitcommit: 4eb4ca899adcf4d86501530f875eb49af8cdaeb7
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/16/2019
ms.locfileid: "34083185"
---
# <a name="create-custom-sensitive-information-types-with-exact-data-match-based-classification-preview"></a>使用基于精确数据匹配的分类创建自定义敏感信息类型（预览版）

## <a name="overview"></a>概述

[自定义敏感信息类型](custom-sensitive-info-types.md)用于帮助防止无意或不适当的敏感信息共享。 作为管理员，你可以使用[安全与合规中心](create-a-custom-sensitive-information-type.md)或 [PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md)，根据模式、证据（*员工*、*徽章*、*ID* 等关键字）、字符邻近度（特定模式下证据与字符的邻近度）以及可信度来定义自定义敏感信息类型。 此类自定义敏感信息类型可满足许多组织的业务需求。

但是，如果你需要自定义敏感信息类型（它使用精确数据值而不是模式和邻近度），该怎么办？ 通过基于精确数据匹配 (EDM) 的分类，你可以创建专门设计的自定义敏感信息类型：
- 动态并且可刷新；
- 更具可伸缩性；
- 导致更少的误报；
- 处理结构化敏感数据；
- 更安全地处理敏感信息以及
- 与多种 Microsoft 云服务一起使用。

![基于 EDM 的分类](media/EDMClassification.png)

基于 EDM 的分类允许你创建自定义敏感信息类型，它们将引用敏感信息数据库中的精确值。 数据库可以每天或每周刷新一次，最多可包含 1000 万行数据。 因此，当员工、患者或客户往来并且记录发生更改时，你的自定义敏感信息类型仍将保持最新并且适用。 你还可以将基于 EDM 的分类与策略一起使用，例如[数据丢失防护策略](data-loss-prevention-policies.md) (DLP) 或 [Microsoft Cloud App Security 文件策略](https://docs.microsoft.com/cloud-app-security/data-protection-policies)。

## <a name="required-licenses-and-permissions"></a>所需的许可证和权限

- 你必须是全局管理员、合规性管理员或 Exchange Online 管理员才能执行本文中描述的任务。 若要了解有关 DLP 权限的详细信息，请参阅[权限](data-loss-prevention-policies.md#permissions)。

- 当正式发布时，基于 EDM 的分类将包含在以下订阅中：
    - Office 365 E5
    - Microsoft 365 E5
    - Microsoft 365 信息保护与合规性
    - Office 365 高级合规版

> [!NOTE]
> 对于 [Office 365 中的 DLP](data-loss-prevention-policies.md)（具有 Exchange Online 和 Microsoft Teams）和 [Cloud App Security](https://docs.microsoft.com/cloud-app-security)，**基于 EDM 的分类目前处于预览阶段**。 如果你的组织具有 [DLP 功能](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/messaging-policy-and-compliance-servicedesc#data-loss-prevention-dlp)，则可以试用基于 EDM 的分类。 如果你尚未加入预览，请[联系 Microsoft](https://resources.office.com/us-landing-spe-contactus.html?LCID=EN-US) 以开始使用。 

## <a name="the-work-flow-at-a-glance"></a>工作流程概览

|阶段  |所需项  |
|---------|---------|
|[第 1 部分：设置基于 EDM 的分类](#part-1-set-up-edm-based-classification)<br/><br/>（根据需要）<br/>- [编辑数据库架构](#editing-the-schema-for-edm-based-classification) <br/>- [删除架构](#removing-the-schema-for-edm-based-classification) |- 敏感数据的读取权限<br/>- .xml 格式的数据库架构（提供了示例）<br/>- .xml 格式的规则包（提供了示例）<br/>- 安全与合规中心的管理员权限（使用 PowerShell） |
|[第 2 部分：创建索引并上载敏感数据](#part-2-index-and-upload-the-sensitive-data)<br/><br/>（根据需要）<br/>[刷新数据](#refreshing-your-sensitive-information-database) |- 自定义安全组和用户帐户<br/>- 使用 EDM 上载代理对计算机进行本地管理员访问<br/>- 敏感数据的读取权限<br/>- 刷新数据的流程和计划|
|[第 3 部分：将基于 EDM 的分类与 Microsoft 云服务一起使用](#part-3-use-edm-based-classification-with-your-microsoft-cloud-services) |- 包含 DLP 的 Office 365 订阅<br/>- 启用基于 EDM 的分类功能（在预览版中） |

## <a name="part-1-set-up-edm-based-classification"></a>第 1 部分：设置基于 EDM 的分类

设置和配置基于 EDM 的分类涉及以 .csv 格式保存敏感数据、为敏感信息数据库定义架构、创建规则包以及上载架构和规则包。

### <a name="define-the-schema-for-your-database-of-sensitive-information"></a>定义敏感信息数据库的架构

1. 确定要使用的敏感信息。 将数据导出到应用（如 Microsoft Excel），然后以 .csv 格式保存文件。 数据文件可包含：

    - 高达 1000 万行的敏感数据
    - 每个数据源最多 32 列（字段）

2. 在 .csv 文件中构造敏感数据，使第一行包含用于基于 EDM 的分类的字段名称。 在 .csv 文件中，你可能拥有“ssn”、“生日”、“名字”、“姓氏”等字段名称。 例如，我们的 .csv 文件称为 *PatientRecords.csv*，其列包含*患者 ID*、*MRN*、*姓氏*、*名字*、*SSN* 等。

3. 以 .xml 格式定义敏感信息数据库的架构（类似于下面的示例）。 命名此架构文件 `edm.xml` 并对其进行配置，确保对于数据库中的每一列，都有一行使用语法 `<Field name="" unique="" searchable=""/>`。 

    - 将列名称用于*字段名称*值。
    - 对于包含唯一值（社会安全号码、标识号等）的字段，请使用 *unique="true"*；否则，请使用 *unique="false"*。
    - 对于要搜索的字段，请使用 *searchable="true"*。 不要为每个数据库指定超过五个要搜索的字段。 所有其余字段都应具有 *searchable="false"*。  

    例如，以下 .xml 文件定义患者记录数据库的架构，其中五个字段指定为可搜索字段：*患者 ID*、*MRN*、*SSN*、*电话*和 *DOB*。 
    
    （你可以复制、修改和使用我们的示例。）
    
    ```<?xml version="1.0" encoding="utf-8"?> <EdmSchema xmlns="http://schemas.microsoft.com/office/2018/edm">
        <DataStore name="PatientRecords" description="患者记录的架构" version="1">
            <Field name="PatientID" unique="false" searchable="true" /> <Field name="MRN" unique="false" searchable="true" />
            <Field name="FirstName" unique="false" searchable="false" />
            <Field name="LastName" unique="false" searchable="false" />
            <Field name="SSN" unique="false" searchable="true" />
            <Field name="Phone" unique="false" searchable="true" />
            <Field name="DOB" unique="false" searchable="true" />
            <Field name="Gender" unique="false" searchable="false" />
            <Field name="Address" unique="false" searchable="false" />
        </DataStore>
    </EdmSchema>
    ```

4. [Connect to Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).

5. To upload the database schema, run the following cmdlets, one at a time:

    `$edmSchemaXml=Get-Content .\edm.xml -Encoding Byte -ReadCount 0`

    `New-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true`

    You will be prompted to confirm, as follows:

       Confirm
       Are you sure you want to perform this action?
       New EDM Schema for the data store 'patientrecords' will be imported.
       [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [?] Help (default is "Y"):

    > [!TIP]
    > If you want your changes to occur without confirmation, in Step 5, use this cmdlet instead: `New-DlpEdmSchema -FileData $edmSchemaXml`
    
Now that the schema for your database of sensitive information is defined, the next step is to set up a rule package. Proceed to the section [Set up a rule package](#set-up-a-rule-package).

#### Editing the schema for EDM-based classification 

(As needed) If you want to make changes to your edm.xml file, such as changing which fields are used for EDM-based classification, follow these steps:

1. Edit your edm.mxl file (this is the file discussed in the [Define the schema](#define-the-schema-for-your-database-of-sensitive-information) section of this article).

2. [Connect to Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).

3. To update your database schema, run the following cmdlets, one at a time:

    `$edmSchemaXml=Get-Content .\edm.xml -Encoding Byte -ReadCount 0`

    `Set-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true`

    You will be prompted to confirm, as follows:

       Confirm
       Are you sure you want to perform this action?
       EDM Schema for the data store 'patientrecords' will be updated.
       [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [?] Help (default is "Y"):

    > [!TIP]
    > If you want your changes to occur without confirmation, in Step 3, use this cmdlet instead: `Set-DlpEdmSchema -FileData $edmSchemaXml`

#### Removing the schema for EDM-based classification

(As needed) If you want to remove the schema you're using for EDM-based classification, follow these steps:

1. [Connect to Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).

2. Run the following PowerShell cmdlet, substituting the data store name of "patientrecords" with the one you want to remove:

    `Remove-DlpEdmSchema -Identity patientrecords`

     You will be prompted to confirm, as follows:
    
       Confirm
       Are you sure you want to perform this action?
       EDM Schema for the data store 'patientrecords' will be removed.
       [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [?] Help (default is "Y"):
    
    > [!TIP]
    > If you want your changes to occur without confirmation, in Step 2, use this cmdlet instead: `Remove-DlpEdmSchema -Identity patientrecords -Confirm:$false`

### Set up a rule package

1. Create a rule package in .xml format (with Unicode encoding), similar to the following example. (You can copy, modify, and use our example.) 

   Recall from the previous procedure that our PatientRecords schema defines five fields as searchable: *PatientID*, *MRN*, *SSN*, *Phone*, and *DOB*. Our example rule package includes those fields and references the database schema file (edm.xml), with one *ExactMatch* items per searchable field. Consider the following ExactMatch item:

   ```
    <ExactMatch id = "E1CC861E-3FE9-4A58-82DF-4BD259EAB371" patternsProximity = "300" dataStore ="PatientRecords" recommendedConfidence = "65" > <Pattern confidenceLevel="65"> <idMatch matches = "SSN" classification = "U.S. Social Security Number (SSN)" /> </Pattern> </ExactMatch>
   ```

    In this example, note the following:

    - The dataStore name references the .csv file we created earlier: **dataStore = "PatientRecords"**.
    - The idMatch value references a searchable field that is listed in the database schema file: **idMatch matches = "SSN"**.
    - The classification value references an existing or custom sensitive information type: **classification = "U.S. Social Security Number (SSN)"**. (In this case, we use the existing sensitive information type of U.S. Social Security Number.)

    When you set up your rule package, make sure to correctly reference your .csv file and edm.xml file. (You can copy, modify, and use our example.) 

    ```<?xml version="1.0" encoding="utf-8"?>
    <RulePackage xmlns="http://schemas.microsoft.com/office/2018/edm">
      <RulePack id="fd098e03-1796-41a5-8ab6-198c93c62b11">
        <Version build="0" major="2" minor="0" revision="0" />
        <Publisher id="eb553734-8306-44b4-9ad5-c388ad970528" />
        <Details defaultLangCode="en-us">
          <LocalizedDetails langcode="en-us">
            <PublisherName>IP DLP</PublisherName>
            <Name>Health Care EDM Rulepack</Name>
            <Description>This rule package contains the EDM sensitive type for health care sensitive types.</Description>
          </LocalizedDetails>
        </Details>
      </RulePack>
      <Rules>
        <ExactMatch id = "E1CC861E-3FE9-4A58-82DF-4BD259EAB371" patternsProximity = "300" dataStore ="PatientRecords" recommendedConfidence = "65" >
          <Pattern confidenceLevel="65">
            <idMatch matches = "SSN" classification = "U.S. Social Security Number (SSN)" />
          </Pattern>
          <Pattern confidenceLevel="75">
            <idMatch matches = "SSN" classification = "U.S. Social Security Number (SSN)" />
            <Any minMatches ="3" maxMatches ="100">
              <match matches="PatientID" />
              <match matches="MRN"/>
              <match matches="FirstName"/>
              <match matches="LastName"/>
              <match matches="Phone"/>
              <match matches="DOB"/>
            </Any>
          </Pattern>
        </ExactMatch>
        <LocalizedStrings>
          <Resource idRef="E1CC861E-3FE9-4A58-82DF-4BD259EAB371">
            <Name default="true" langcode="en-us">Patient SSN Exact Match.</Name>
            <Description default="true" langcode="en-us">EDM Sensitive type for detecting Patient SSN.</Description>
          </Resource>
        </LocalizedStrings>
      </Rules>
    </RulePackage>
    ```
    
2. 通过运行以下 PowerShell cmdlet 来上载规则包（每次上载一个）：

    `$rulepack=Get-Content .\rulepack.xml -Encoding Byte -ReadCount 0`

    `New-DlpSensitiveInformationTypeRulePackage -FileData $rulepack`

此时，你已设置基于 EDM 的分类。 下一步是为敏感数据创建索引，然后上载索引数据。 

## <a name="part-2-index-and-upload-the-sensitive-data"></a>第 2 部分：创建索引并上载敏感数据

在此阶段，你将设置自定义安全组和用户帐户，并设置 EDM 上载代理工具。 然后，使用该工具为敏感数据创建索引，并上载索引数据。

### <a name="set-up-the-security-group-and-user-account"></a>设置安全组和用户帐户

1. 以全局管理员身份转到管理中心 ([https://admin.microsoft.com](https://admin.microsoft.com)) 并[创建安全组](https://docs.microsoft.com/office365/admin/email/create-edit-or-delete-a-security-group?view=o365-worldwide)（名为 `EDM_DataUploaders`）。 

2. 将一个或多个用户添加到 *EDM_DataUploaders* 安全组。 （这些用户将管理敏感信息的数据库。）

3. 确保负责管理敏感数据的每个用户都是装有 EDM 上载代理的计算机上的本地管理员。

### <a name="set-up-the-edm-upload-agent"></a>设置 EDM 上载代理

> [!NOTE]
> 在开始此过程之前，请确保你是 *EDM_DataUploaders* 安全组的成员和计算机上的本地管理员。

1. 从 [https://go.microsoft.com/fwlink/?linkid=2088639](https://go.microsoft.com/fwlink/?linkid=2088639) 下载并安装 EDM 上载代理。 默认情况下，安装位置应该为 `C:\Program Files\Microsoft\EdmUploadAgent`。 

2. 若要授权 EDM 上载代理，请打开 Windows 命令提示符（以管理员身份），然后运行以下命令：

    `EdmUploadAgent.exe /Authorize`

3. 使用 Office 365 的工作或学校帐户登录。

下一步是使用 EDM 上载代理为敏感数据创建索引，然后上载索引数据。

### <a name="index-and-upload-the-sensitive-data"></a>创建索引并上载敏感数据

1. 将敏感数据文件（注意我们的示例为 *PatientRecords.csv*）保存到计算机上的本地驱动器。 （我们已将示例 *PatientRecords.csv* 文件保存到 `C:\Edm\Data`。）

2. 若要为敏感数据创建索引，请在 Windows 命令提示符中运行以下命令：

    `EdmUploadAgent.exe /CreateHash /DataStoreName <DataStoreName> /DataFile <DataFilePath> /HashLocation <HashedFileLocation>`

    示例：**EdmUploadAgent.exe /CreateHash /DataStoreName PatientRecords /DataFile C:\Edm\Data\PatientRecords.csv /HashLocation C:\Edm\Hash** 

3. 若要上载索引数据，请在 Windows 命令提示符中运行以下命令：

    `EdmUploadAgent.exe /UploadHash /DataStoreName <DataStoreName> /HashFile <HashedSourceFilePath>`

    示例：**EdmUploadAgent.exe /UploadHash /DataStoreName PatientRecords /HashFile C:\Edm\Hash\PatientRecords.EdmHash** 

4. 若要验证是否已上载敏感数据，请在 Windows 命令提示符中运行以下命令：

    `EdmUploadAgent.exe /GetDataStore`

    你将看到数据存储区列表以及上次更新时间，类似于以下内容： <br/>![GetDataStore cmdlet 和结果的示例](media/EDM-GetDataStore-example.png)

5. 继续设置[刷新敏感信息数据库](#refreshing-your-sensitive-information-database)的流程和计划。

此时，你已准备好将基于 EDM 的分类与 Microsoft 云服务一起使用。 例如，你可以[使用基于 EDM 的分类设置 DLP 策略](#to-create-a-dlp-policy-with-edm)。 

### <a name="refreshing-your-sensitive-information-database"></a>刷新敏感信息数据库

你可以每天或每周刷新敏感信息数据库，EDM 上载工具可以重新为敏感数据创建索引，然后重新上载索引数据。 

1. 确定刷新敏感信息数据库的流程和频率（每天或每周）。

2. 将敏感数据重新导出到应用（如 Microsoft Excel），并以 .csv 格式保存文件。 在按照[创建索引并上载敏感数据](#index-and-upload-the-sensitive-data)中所述的步骤执行操作时，让所使用的文件名和位置保持不变。

    > [!NOTE]
    > 如果 .csv 文件的结构（字段名称）未发生更改，则刷新数据时无需对数据库架构文件进行任何更改。 但是，如果必须进行更改，请确保相应地编辑[数据库架构](#editing-the-schema-for-edm-based-classification)和[规则包](#set-up-a-rule-package)。        

3. 使用[任务计划程序](https://docs.microsoft.com/windows/desktop/TaskSchd/task-scheduler-start-page)自动执行[创建索引并上载敏感数据](#index-and-upload-the-sensitive-data)流程中的步骤 2 和 3。 你可以使用多种方法来计划任务：
    
    |方法  |需执行的操作  |
    |---------|---------|
    |Windows PowerShell     |请参阅本文中的[计划任务](https://docs.microsoft.com/powershell/module/scheduledtasks/?view=win10-ps)文档和[示例 PowerShell 脚本](#example-powershell-script-for-task-scheduler)|
    |任务计划程序 API |请参阅[任务计划程序](https://docs.microsoft.com/windows/desktop/TaskSchd/using-the-task-scheduler)文档 |
    |Windows 用户界面     |在 Windows 中，单击“**开始**”，然后键入 `Task Scheduler`。 然后，在结果列表中，右键单击“**任务计划程序**”，然后选择“**以管理员身份运行**”。          |

#### <a name="example-powershell-script-for-task-scheduler"></a>任务计划程序的示例 PowerShell 脚本

此部分包含一个示例 PowerShell 脚本，你可以使用该脚本来计划创建数据索引并上载索引数据的任务：

```powershell
param([string]$dataStoreName,[string]$fileLocation)
# Assuming current user is also the user context to run the task
$user = "$env:USERDOMAIN\$env:USERNAME"
$edminstallpath = 'C:\Program Files\Microsoft\EdmUploadAgent\'
$edmuploader = $edminstallpath + 'EdmUploadAgent.exe'
$csvext = '.csv'
$edmext = '.EdmHash'
# Assuming CSV file name is same as data store name
$dataFile = "$fileLocation\$dataStoreName$csvext"
$hashFile = "$fileLocation\$dataStoreName$edmext"
# Assuming location to store hash file is same as the location of csv file
$hashLocation = $fileLocation
$createHashArgs = '/CreateHash /DataStoreName ' + $dataStoreName + ' /DataFile ' + $dataFile + ' /HashLocation ' + $hashLocation
$uploadHashArgs = '/UploadHash /DataStoreName ' + $dataStoreName + ' /HashFile ' + $hashFile
# Set up actions associated with the task
$actions = @()
$actions += New-ScheduledTaskAction -Execute $edmuploader -Argument $createHashArgs -WorkingDirectory $edminstallpath
$actions += New-ScheduledTaskAction -Execute $edmuploader -Argument $uploadHashArgs -WorkingDirectory $edminstallpath
# Set up trigger for the task
$trigger = New-ScheduledTaskTrigger -Weekly -DaysOfWeek Sunday -At 2am
# Set up task settings
$principal = New-ScheduledTaskPrincipal -UserId $user -LogonType S4U -RunLevel Highest
$settings = New-ScheduledTaskSettingsSet -RunOnlyIfNetworkAvailable -StartWhenAvailable -WakeToRun
# Create the scheduled task
$scheduledTask = New-ScheduledTask -Action $actions -Principal $principal -Trigger $trigger -Settings $settings
# Get credentials to run the task
$creds = Get-Credential -UserName $user -Message "Enter credentials to run the task"
$password=[Runtime.InteropServices.Marshal]::PtrToStringAuto([Runtime.InteropServices.Marshal]::SecureStringToBSTR($creds.Password))
# Register the scheduled task
$taskName = 'EDMUpload_' + $dataStoreName
Register-ScheduledTask -TaskName $taskName -InputObject $scheduledTask -User $user -Password $password
```
## <a name="part-3-use-edm-based-classification-with-your-microsoft-cloud-services"></a>第 3 部分：将基于 EDM 的分类与 Microsoft 云服务一起使用

你可以将基于 EDM 的分类与信息保护功能一起使用，例如 [Office 365 DLP 策略](data-loss-prevention-policies.md)和 [Microsoft Cloud App Security 文件策略](https://docs.microsoft.com/cloud-app-security/data-protection-policies)。 以下过程介绍如何将 EDM 与在 Office 365 安全与合规中心内创建的 DLP 策略一起使用。

### <a name="to-create-a-dlp-policy-with-edm"></a>使用 EDM 创建 DLP 策略

1. 转到“安全与合规中心”([https://protection.office.com](https://protection.office.com))。

2. 单击“**数据丢失防护**” > “**策略**”。

3. 选择“**创建策略**” > “**自定义**” > “**下一步**”。

4. 在“**命名策略**”选项卡上，指定名称和说明，然后选择“**下一步**”。

5. 在“**选择位置**”选项卡上，选择“**允许选择特定位置**”，然后选择“**下一步**”。<br/>![选择位置选项](media/DLP-EDM-newpolicy-chooselocations.png)<br/>

6. 在“**状态**”列中，仅选择“**Exchange 电子邮件**”，然后选择“**下一步**”。 <br/>![仅限 Exchange 的 EDM 策略](media/EDM-DLPpolicy-ExchangeOnly.png)<br/>

7. 在“**策略设置**”选项卡上，选择“**使用高级设置**”，然后选择“**下一步**”。<br/>![使用高级设置](media/edm-dlp-policy-advancedsettings.png)<br/>

8. 选择“**+ 新建规则**”。<br/>![创建规则](media/edm-dlp-newrule.png)<br/>

9. 在“**名称**”部分中，指定规则的名称和说明。<br/>![新建规则字段](media/edm-dlp-newruleform.png)<br/>

10. 在“**条件**”部分的“**+ 添加条件**”列表中，选择“**内容包含敏感类型**”。<br/>![内容包含敏感信息类型](media/edm-dlp-newrule-conditions.png)<br/>

11. 搜索你在设置规则包时创建的敏感信息类型，然后选择“**+ 添加**”。<br/>![查找敏感信息类型](media/edm-dlp-newrulefindsensitiverulepack.png)<br/>然后选择“**完成**”。

12. 完成为规则选择相关选项，例如“**用户通知**”、“**用户覆盖**”、“**事件报告**”等，然后选择“**保存**”。

13. 在“**策略设置**”选项卡上，查看你的规则，然后选择“**下一步**”。

14. 指定是立即打开策略、测试它还是保持关闭。 然后选择“**下一步**”。

15. 在“**查看你的设置**”选项卡上，查看你的策略。 执行任何必要的更改。 准备好后，选择“**创建**”。

    > [!NOTE]
    > 新 DLP 策略大约需要一个小时才能通过你的数据中心。

## <a name="related-articles"></a>相关文章

[内置敏感信息类型以及它们查找的内容](what-the-sensitive-information-types-look-for.md)

[自定义敏感信息类型](custom-sensitive-info-types.md)

[DLP 策略概述](data-loss-prevention-policies.md)

[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security)
