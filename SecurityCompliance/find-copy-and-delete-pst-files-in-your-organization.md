---
title: 使用 PST 集合工具查找、 复制和删除组织中的 PST 文件
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid: MOE150
ms.assetid: 7a150c84-049c-4a9c-8c91-22355b35f2a7
description: 使用 Microsoft PST 集合工具搜索贵组织的网络，若要获取分散在您的组织的 PST 文件的清单。查找 PST 文件后，您可以使用 PST 集合工具以将其复制在一个中心位置，以便您可以将其导入 Office 365。
ms.openlocfilehash: 34395eee7776d8bff1ddccb7fed5b683e97c02c7
ms.sourcegitcommit: c59a082dca6593d0e35e58124ee6ba240547bfa5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/05/2018
ms.locfileid: "27154208"
---
# <a name="use-the-pst-collection-tool-to-find-copy-and-delete-pst-files-in-your-organization"></a>使用 PST 集合工具查找、 复制和删除组织中的 PST 文件

> [!IMPORTANT]
> 本文中所述的 PST 集合工具不支持任何 Microsoft 标准支持程序或服务。该工具原样提供，没有任何形式的担保。Microsoft 进一步否认所有默示的担保，包括但不限于，任何暗示对适销性或针对特定用途的适用性的担保。因使用或性能的工具和文档的全部风险您自己承担。在任何情况 Microsoft、 作者，或 else 参与创建、 生产或传递的工具的任何人都概的因任何损害向 （包括但不限于损失业务损失、 业务中断丢失业务信息或其他 pecuniary 丢失） 因使用或不能使用工具或文档，即使 Microsoft 已被告知此类损害的可能性。

Microsoft PST 收集工具可用于搜索的 PST 文件的组织的网络。该工具可帮助您获得分散在您的组织的 PST 文件的清单。查找 PST 文件后，您可以使用 PST 集合工具以将其复制在一个中心位置。无 Pst 在一个位置，然后允许您导入到 Exchange Online 邮箱 （或单个 Exchange Online 邮箱），然后可应用丰富的 Office 365 中的合规性功能。这包括将 Pst 导入到用户的邮箱，搜索特定邮件已导入使用电子数据展示搜索工具，邮件保留使用电子数据展示 PST 文件中包含的存档和 Office 365 保留策略，以及管理生命周期周期的使用消息这些邮件记录管理功能在 Exchange Online。确信您收集的 PST 文件已成功导入到 Office 365 后，您可以使用工具在您的网络从其原始位置删除它们。 
  
用 PST 收集工具能做的另一个事情是阻止用户创建新的 PST 文件和更改查找网络的现有 PST 文件。这些"阻止"功能允许您查找、 收集和一组已知的 PST 文件导入 Office 365 和阻止的组织中的 PST 文件将来扩散打开了。 
  
## <a name="how-the-pst-collection-tool-works"></a>PST 集合工具的工作方式

下面是过程的使用 PST 收集工具查找、 控制、 收集和删除组织中的 PST 文件的快速概述。
  
![PST 集合工具过程概述](media/67a29f27-f83c-4f0a-9df4-7ed92d3086fe.png)
  
1. **[步骤 1： 查找在您的网络的 PST 文件](#step-1-find-pst-files-on-your-network)**-当您运行工具查找 PST 文件，指定一个位置，例如包含客户端和服务器的计算机的 Active Directory 对象的组织单位。您还可以搜索特定计算机或网络文件共享。运行该工具时，在目标计算机上安装"轻型"集合代理。此代理搜索 PST 文件的目标计算机，然后将信息发送回有关发现任何 PST 文件的 PST 集合工具。此工具创建日志文件包含有关在指定位置中找到的 PST 文件的信息。后续步骤中运行该工具时使用这些文件。 
    
2. **[（可选） 步骤 2： 控制对 PST 文件的访问](#optional-step-2-control-access-to-pst-files)**-工具创建组策略对象 (GPO) 具有阻止用户创建或更改 PST 文件的设置。此 GPO 应用于您的域中的每个用户。此可选步骤将帮助您"锁定"，以便可以收集、 导入，并删除这些而无需创建新的 PST 文件在步骤 1 中，找到 PST 文件或更改现有 PST 文件。 
    
3. **[步骤 3： 将 PST 文件复制到集合位置](#step-3-copy-the-pst-files-to-a-collection-location)**-这允许您收集在一个位置的 PST 文件，以便您可以将其导入 Exchange Online 邮箱步骤 4 中使用的导入 Office 365 服务。在"收集"模式下运行该工具时，每个集合代理将安装代理集位置到目标计算机复制 PST 文件。 
    
4. **[步骤 4： 将 PST 文件导入到 Office 365](#step-4-import-the-pst-files-to-office-365)** -已 PST 文件复制到一个位置后，您准备好进行导入到 Exchange Online 邮箱。 
    
5. **[步骤 5： 网络找到的 PST 文件的删除](#step-5-delete-the-pst-files-found-on-your-network)**-PST 文件，找到并收集已导入到 Office 365 中的 Exchange Online 邮箱，您可以使用 PST 收集工具从原始位置删除 PST 文件后，它们步骤 1 中找到。 

## <a name="before-you-begin"></a>准备工作

- 按照以下步骤以下载到本地计算机的 PST 收集工具。 
    
    1. [下载 PST 集合工具](https://aka.ms/pstcollectiontool)。
    
    2. 在弹出窗口中，单击**保存** \> **另存为**本地计算机上将 PSTCollectionTool.zip 文件保存到文件夹。 
    
    3. PSTCollectionTool.zip 将文件提取到一个文件夹在本地计算机。默认文件夹名称是 PSTCollectionTool。
    
- 若要在任何模式 （查找、 阻止、 复制或删除） 中运行 PST 收集工具，您必须是 Active Directory 域中的 Domain Administrators 组的成员。 

## <a name="step-1-find-pst-files-on-your-network"></a>步骤 1： 查找在您的网络的 PST 文件

第一步是运行 PST 集合工具查找组织中的 PST 文件。此工具可用于搜索以下类型的位置。 
  
- 内部部署 Active Directory 域中的组织单位 (Ou)。该工具将搜索指定的 OU 中包含的所有计算机。 
    
- 客户端和服务器的计算机。该工具将搜索指定的计算机。 
    
- 网络文件共享。该工具将搜索指定的网络文件共享。 
    
说明，请参阅`Locations`的语法来使用这些位置类型的每个示例的以下过程中的表中的参数。 
  
> [!IMPORTANT]
> 您具有到运行查找模式的 PST 集合工具才能执行其他操作，如阻止、 收集，或删除 PST 文件。 
  
1. 在本地计算机上打开命令提示符 （以管理员身份运行）。
    
2. 转到 PSTCollectionTool 文件夹 （或提取到的 PSTCollectionTool.zip 文件的文件夹）。
    
3. 转到 DataCollectorMaster 目录。
    
4. 运行以下命令以查找 PST 文件中指定的位置。
    
    ```
    DataCollectorMaster.exe -DataSource Pst -Mode Find -JobName <Name> -Locations <Locations to search for PSTs> -LogLocation <Location to store log files> -ConfigurationLocation <Location to store configuration files>
    ```

    下表介绍参数以及它们所需的值，当您运行 DataCollectorMaster.exe 命令，以查找 PST 文件。 
    
    |参数 ***|****Description****|示例 ***|
    |:-----|:-----|:-----|
    | `DataSource` <br/> |指定要搜索数据的类型。目前，您可以使用 PST 收集工具搜索 PST 文件。  <br/> | `-DataSource Pst` <br/> |
    | `Mode` <br/> |指定该工具将执行的操作的类型。使用值`Find`来查找 PST 文件中指定的位置。请注意该工具可以查找和获取有关连接到 Outlook 配置文件的 Outlook 和 PST 文件中打开的 PST 文件的信息。<br/> | `-Mode Find` <br/> |
    | `JobName` <br/> |指定 PST 集合作业的名称。运行 PST 集合工具，以阻止、 收集和删除位于运行工具查找 PST 文件时的 PST 文件时，您将使用此相同的作业名称。作业名称也将添加到日志和配置文件名称。  <br/> | `-JobName PstSearch1` <br/> |
    | `Locations` <br/> | 指定要搜索的 PST 文件的一个或多个位置。如果您指定多个位置，请使用分号 （;） 分隔各个位置。请务必包围各个值的此参数与双引号 ("")。<br/><br/>   下面是可以搜索的位置的类型的必需的 identity 值格式。  <br/><br/>        **Ou** -使用的可分辨名称 (DN) 来标识 Ou;例如：`"OU=NorthAmerica,OU=NWRegion,OU=ITServices,DC=contoso,DC=com"` <br/> > [!IMPORTANT]> 不能指定内置的计算机容器 (例如，CN = Computers，DC = contoso，DC = com") 因为组织单位。<br/> <br/> **机**-使用 DN 或完全限定的域名 (FQDN) 来确定客户端和服务器网络内计算机上;例如：  <br/>  DN:`"CN=FILESERVER01,CN=Computers,DC=contoso,DC=com"` <br/>  或  <br/>  FQDN:`"FILESERVER01.contoso.com"` <br/><br/>  **网络文件共享**-使用 UNC 名称来标识网络文件共享;例如，`"\\FILESERVER02\Users"` <br/> | `-Locations "CN=FILESERVER01,CN=Computers,DC=contoso,DC=com";"CN=FILESERVER02,CN=Computers,DC=contoso,DC=com"` <br/> |
    | `LogLocation` <br/> |指定日志文件将被复制到的文件夹。如果文件夹不存在，将运行该工具时创建它。  <br/> | `-LogLocation "c:\users\admin\desktop\PSTCollection"` <br/> |
    | `ConfigurationLocation` <br/> |指定.xml 配置文件将被复制到的文件夹。此文件包含有关运行该工具时找到每个 PST 文件的信息。步骤 3 复制找到 PST 文件中运行该工具时，将使用此文件。  <br/> | `-ConfigurationLocation "c:\users\admin\desktop\PSTCollection\Configuration"` <br/> |
    | `ExcludedLocations` <br/> |此可选参数指定要跳过查找操作过程中的位置。您可以排除特定 Ou、 机和网络文件共享。例如，可以排除机，如配置为 SQL server （或其他类型的应用程序服务器） 的计算机，用户不能访问。如果您指定要排除的多个位置，请使用分号 （;） 分隔各个位置。请务必包围各个值的此参数与双引号 ("")。  <br/> | `-ExcludedLocations "SQLSERVER01.contoso.com"` <br/> |
    | `ForceRestart` <br/> |此可选开关，可以在现有 PST 集合作业的查找模式运行该工具。当您使用`ForceRestart`切换，以前的查找操作的结果将丢弃该作业，并在工具将重新扫描的指定的位置和创建新的日志和配置文件。<br/> | `-ForceRestart` <br/> |
   
    下面是语法的使用实际值的每个参数 DataCollectorMaster.exe 命令示例：
    
    ```
    DataCollectorMaster.exe -DataSource Pst -Mode Find -JobName PstSearch1 -Locations "CN=FILESERVER01,CN=Computers,DC=contoso,DC=com";"CN=FILESERVER02,CN=Computers,DC=contoso,DC=com" -LogLocation "c:\users\admin\desktop\PSTCollection" -ConfigurationLocation "c:\users\admin\desktop\PSTCollection\Configuration"
    ```

    运行该命令后，则显示详细的状态消息的显示在指定位置查找 PST 文件的进度。后一段时间，最终状态消息显示找到的 PST 文件的总数、 是否完成该作业后，和如果没有任何错误。相同的状态邮件复制到.log 文件。
    
### <a name="results-of-running-datacollectormasterexe-in-the-find-mode"></a>在查找模式下运行 DataCollectorMaster.exe 的结果

在成功运行 PST 收集工具查找模式后，创建并通过指定的文件夹中存储以下文件`LogLocation`和`ConfigurationLocation`参数。 
  
- **\<JobName\>_查找_\<DateTimeStamp\>.log** -日志文件中包含已显示状态消息。在指定的文件夹中创建此文件`LogLocation`参数。 
    
- **\<JobName\>_查找_\<DateTimeStamp\>.csv** -CSV 文件包含为每个找的 PST 文件的行。每个 PST 的信息包括在其中发现，PST 文件的完整文件路径位置、 PST 文件中，和 PST 文件的大小 （以千字节，知识库） 的所有者的 PST 文件的计算机。在指定的文件夹中创建此文件`LogLocation`参数。 
    
    > [!TIP]
    > 使用 Excel 中的自动求和工具来计算该 CSV 文件中列出的所有 PST 文件的总大小 （以 kb 为单位）。然后您可以使用转换计算器转换的总大小 (mb) 或千兆字节 (GB)。 
  
- **\<JobName\>_查找_\<DateTimeStamp\>.xml** -XML 文件包含何类信息参数值的位置查找模式中运行该工具时使用。此文件还包含有关找到的每个 PST 文件的信息。重新运行相同的工具收集，作业到块中，或删除 PST 文件找到的运行时使用此文件中的数据。在指定的文件夹中创建此文件`ConfigurationLocation`参数。 
    
    > [!IMPORTANT]
    > 不重命名、 更改或移动该文件。它使用 PST 收集工具在块、 复制、 重新运行该工具或删除模式相同的作业时。 

## <a name="optional-step-2-control-access-to-pst-files"></a>（可选）步骤 2： 控制对 PST 文件的访问

此可选步骤，您可以"锁定"，以便您可以收集在步骤 1 中找到的 PST 文件和导入到 Office 365 的一组已知的 PST 文件。阻止模式中运行 PST 收集工具时，会发生以下情况： 
  
- 此工具创建名为*PST 使用率控件*组策略对象 (GPO)。此 GPO 链接到您的域，并且适用于您的组织中的所有经过身份验证的用户。 
    
- PST 使用率控件 GPO 创建您的组织中的计算机上的注册表设置。根据您使用的参数，您可以创建一个注册表设置来阻止用户创建新的 PST 文件和注册表设置，禁止用户更改现有 PST 文件。
    
> [!NOTE]
> 如果您的组织太中断控制对 PST 文件的访问，则可以考虑跳过此步骤中，并执行步骤 3 将 PST 文件复制到一个中心位置。然后您可以重复步骤 1 的相同的作业 (使用`ForceRestart`参数) 来查找其他后 Pst 文件复制到集合位置创建的 Pst 文件。如果找到新的 PST 文件，您可以将其复制到集合位置。当您使用`ForceRestart`参数重新查找模式中运行该工具时，将放弃作业以前的查找操作的结果，该工具将重新扫描的指定的位置。 

若要阻止对 PST 文件的访问：

1. 在本地计算机上打开命令提示符 （以管理员身份运行）。
    
2. 转到下载 PST 集合工具的目录。
    
3. 运行以下命令以阻止对在步骤 1 中找到的 PST 文件的访问。

    ```
    DataCollectorMaster.exe -DataSource Pst -Mode Block -JobName <Name of job from Step 1> -ConfigurationLocation <Location of configuration files from Step 1> -BlockChangesToFiles -BlockNewFiles
    ```

    下表介绍参数以及它们所需的值，当您运行 DataCollectorMaster.exe 命令，以阻止创建和更改的 PST 文件。 
    
    |参数 ***|****Description****|示例 ***|
    |:-----|:-----|:-----|
    | `DataSource` <br/> |指定要搜索数据的类型。目前，您可以使用 PST 收集工具搜索 PST 文件。  <br/> | `-DataSource Pst` <br/> |
    | `Mode` <br/> |指定该工具将执行的操作的类型。使用值`Block`阻止用户创建新的 PST 文件并对现有 PST 文件进行更改。<br/> | `-Mode Block` <br/> |
    | `JobName` <br/> |指定现有的 PST 集合作业的名称。您必须使用此作业的名称相同时在步骤 1 中的查找模式下运行该工具使用。此作业名称添加到阻止模式中运行该工具时，将创建日志文件的名称。  <br/> | `-JobName PstSearch1` <br/> |
    | `ConfigurationLocation` <br/> |指定文件夹中包含.xml 配置文件中查找模式运行工具时创建的。使用用于在步骤 1 中此参数的值相同。  <br/> | `-ConfigurationLocation "c:\users\admin\desktop\PSTCollection\Configuration"` <br/> |
    | `LogLocation` <br/> |指定阻止操作的日志文件将被复制到的文件夹。这是一个可选参数。如果不包括它，日志文件复制到其中下载 PST 集合工具的文件夹。请考虑使用您在步骤 1 中的查找模式下运行该工具时，以便所有日志文件将都保存在同一文件夹时所使用的日志位置相同。  <br/> | `-LogLocation "c:\users\admin\desktop\PSTCollection"` <br/> |
    | `BlockChangesToFiles` <br/> |使用此开关，以防止用户更改 PST 文件。当您使用此开关时，创建以下注册表项： `HKEY_CURRENT_USER\Software\Policies\Microsoft\Office\<version>\Outlook\PST\PstDisableGrow` ，数据值设置为 1。此注册表设置阻止模式中运行 PST 集合工具时创建的 GPO 创建您的组织中的计算机上。<br/> | `-BlockChangesToFiles` <br/> |
    | `BlockNewFiles` <br/> |使用此开关来阻止用户创建新的 PST 文件、 打开和将 PST 文件导入到 Outlook，和从 Outlook 导出 PST 文件。当您使用此开关时，创建以下注册表项： `HKEY_CURRENT_USER\Software\Policies\Microsoft\Office\<version>\Outlook\DisablePst` ，数据值设置为 1。此注册表设置阻止模式中运行 PST 集合工具时创建的 GPO 创建您的组织中的计算机上。<br/> | `-BlockNewFiles` <br/> |
   
    下面是语法的使用实际值的每个参数 DataCollectorMaster.exe 命令示例：

    ```
    DataCollectorMaster.exe -DataSource Pst -Mode Block -JobName PstSearch1 -ConfigurationLocation "c:\users\admin\desktop\PSTCollection\Configuration" -LogLocation "c:\users\admin\desktop\PSTCollection" -BlockChangesToFiles -BlockNewFiles
    ```
    
    系统会提示您确认要阻止新的 PST 文件或更改现有 PST 文件。您确认要继续并成功运行该命令后，将显示一条消息，告知已创建一个新的 GPO，名为"PST 使用率控件"。
    
## <a name="step-3-copy-the-pst-files-to-a-collection-location"></a>步骤 3： 将 PST 文件复制到集合的位置

下一步是复制 PST 文件的在其中找到时则查找模式中运行 PST 集合工具。这样可以收集在一个位置的 PST 文件，以便您可以稍后将其导入 Office 365。PST 文件复制到集合位置之前，请考虑确定的总所需的存储空间量。您可以执行此操作使用来计算所有 PST 文件的总大小的步骤 1 中创建的 CSV 文件。
  
> [!NOTE]
> 已导入到 Office 365 的 PST 文件，并已将其删除从其原始位置后，您可能想要从您在此步骤中复制到这些集合位置将其删除。 
  
1. 在本地计算机上打开命令提示符 （以管理员身份运行）。
    
2. 转到下载 PST 集合工具的目录。
    
3. 运行以下命令以将 PST 文件复制到指定的位置。
    
    ```
    DataCollectorMaster.exe -DataSource Pst -Mode Collect -JobName <Name of job from Step 1> -Locations <same locations from Step 1> -ConfigurationLocation <Location of configuration files from Step 1> -CopyLocation <Location to copy PST files to>
    ```

    下表介绍参数和其所需的值，当您运行 DataCollectorMaster.exe 命令复制 PST 文件。 
    
    |参数 ***|****Description****|示例 ***|
    |:-----|:-----|:-----|
    | `DataSource` <br/> |指定要搜索数据的类型。目前，您可以使用 PST 收集工具搜索 PST 文件。  <br/> | `-DataSource Pst` <br/> |
    | `Mode` <br/> |指定该工具将执行的操作的类型。使用值`Collect`复制 PST 文件的找到您何时运行查找模式中的工具。请注意，此工具可以复制 PST 文件在 Outlook 中打开并将连接到 Outlook 配置文件的 PST 文件复制。<br/> | `-Mode Collect` <br/> |
    | `JobName` <br/> |指定现有的 PST 集合作业的名称。您必须使用此作业的名称相同时在步骤 1 中的查找模式下运行该工具使用。此作业名称添加到在收集模式下运行该工具时，将创建日志文件的名称。  <br/> | `-JobName PstSearch1` <br/> |
    | `Locations` <br/> |使用相同的值用于`Locations`在步骤 1 中的参数。如果您想要重新运行该工具，从源位置在步骤 5 中删除 PST 文件以收集模式运行该工具时，您已包括此参数。<br/> | `-Locations "CN=FILESERVER01,CN=Computers,DC=contoso,DC=com"; "CN=FILESERVER02,CN=Computers,DC=contoso,DC=com"` <br/> |
    | `ConfigurationLocation` <br/> |指定包含.xml 配置文件中查找模式运行工具时创建的文件夹。使用用于在步骤 1 中此参数的值相同。  <br/> | `-ConfigurationLocation "c:\users\admin\desktop \PSTCollection\Configuration"` <br/> |
    | `CopyLocation` <br/> |指定要从中复制到 PST 文件的集合位置。您可以将文件复制到文件服务器、 网络文件共享或硬盘驱动器。在收集模式下运行该工具之前必须存在的位置。该工具不会创建位置，并将返回的错误消息不存在。  <br/> 此外，您需要此参数所指定的集合位置的写入权限。  <br/> | `-CopyLocation "\\FILESERVER03\PSTs"` <br/> |
    | `LogLocation` <br/> |指定收集模式的日志文件将被复制到的文件夹。这是一个可选参数。如果不包括它，日志文件复制到其中下载 PST 集合工具的文件夹。请考虑使用您在步骤 1 中的查找模式下运行该工具时，以便所有日志文件将都保存在同一文件夹时所使用的日志位置相同。  <br/> | `-LogLocation "c:\users\admin\desktop\PSTCollection"` <br/> |
    | `ForceRestart` <br/> |此可选开关，可以重新在现有 PST 集合作业集合模式下运行该工具。如果您之前在收集模式中，运行该工具，但然后在使用查找模式下再次运行该工具`ForceRestart`切换重新扫描 PST 文件的位置，您可以使用此开关重新在集模式运行该工具并没有找到时的 PST 文件重新复制您重新扫描的位置。当使用`ForceRestart`集模式，该工具中的开关将忽略所有以前回收操作并尝试从零开始复制 PST 文件。<br/> | `-ForceRestart` <br/> |
   
    下面是一个示例使用的每个参数的实际值的 DataCollectorMaster.exe 工具的语法：
    
    ```
    DataCollectorMaster.exe -DataSource Pst -Mode Collect -JobName PstSearch1 -Locations "CN=FILESERVER01,CN=Computers,DC=contoso,DC=com";"CN=FILESERVER02,CN=Computers,DC=contoso,DC=com" -ConfigurationLocation "c:\users\admin\desktop\PSTCollection\Configuration" -CopyLocation "\\FILESERVER03\PSTs" -LogLocation "c:\users\admin\desktop\PSTCollection"
    ```

    运行该命令后，则显示显示进度收集在步骤 1 中找到的 PST 文件的详细的状态消息。后一段时间，最终状态消息显示是否存在任何错误和日志复制到的位置。相同的状态邮件复制到.log 文件。
    
### <a name="results-of-running-datacollectormasterexe-in-the-collect-mode"></a>在收集模式下运行 DataCollectorMaster.exe 的结果

成功收集模式中运行 DataCollectorMaster.exe 后，创建并通过指定的文件夹中存储以下文件`LogLocation`和`ConfigurationLocation`参数。 
  
- **\<JobName\>_收集_\<DateTimeStamp\>.log** -日志文件中包含已显示状态消息。在指定的文件夹中创建此文件`LogLocation`参数。 
    
- **\<JobName\>_收集_\<DateTimeStamp\>.xml** -XML 文件仅包含其中使用该工具已收集模式中运行信息参数值。运行时使用此文件中的数据重新运行 DataCollectorMaster.exe 工具删除 PST 文件;请参阅[第 5 步](#step-5-delete-the-pst-files-found-on-your-network)。
    

## <a name="step-4-import-the-pst-files-to-office-365"></a>步骤 4： 将 PST 文件导入到 Office 365

您已收集在步骤 1 中找到的 PST 文件后下, 一步是将其导入 Office 365 中的邮箱。为部件或导入过程中，您将需要创建 CSV 映射文件包含要导入每个 PST 文件中的行。每行中的信息指定 PST 文件，该用户的电子邮件地址的名称，并且您是否要将 PST 文件导入用户的主要或存档邮箱。使用中的信息**JobName\>_查找_\<DateTimeStamp.csv**文件 （在步骤中创建） 可帮助您创建 CSV 映射文件的 1。 
  
到 Office 365 导入 PST 文件的分步说明，请参阅以下主题之一：
  
- [使用网络上载将 PST 文件导入到 Office 365](use-network-upload-to-import-pst-files.md)
    
- [使用驱动器寄送，将 PST 文件导入到 Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md)
    

## <a name="step-5-delete-the-pst-files-found-on-your-network"></a>步骤 5： 删除您的网络上找到的 PST 文件

找到并收集的 PST 文件导入到 Office 365 中的 Exchange Online 邮箱后，您可以使用 PST 收集工具可从其中已找到步骤 1 中的原始源位置删除 PST 文件。 
  
1. 在本地计算机上打开命令提示符 （以管理员身份运行）。
    
2. 转到下载 PST 集合工具的目录。
    
3. 运行以下命令以删除 PST 文件。

    ```
    DataCollectorMaster.exe -DataSource Pst -Mode Delete -JobName <Name of job from Step 1> -ConfigurationLocation <Location of configuration files from Step 1> -CopyLocation <Location to copy PST files to>
    ```

    下表介绍参数以及它们所需的值时运行 DataCollectorMaster.exe 命令以删除 PST 文件。 
    
    |参数 ***|****Description****|示例 ***|
    |:-----|:-----|:-----|
    | `DataSource` <br/> |指定要搜索数据的类型。目前，您可以使用 PST 收集工具搜索 PST 文件。 ![分隔](media/b078d05c-3aee-4b9f-8805-6a8a9d8970ee.png)           <br/> | `-DataSource Pst` <br/> |
    | `Mode` <br/> |指定该工具将执行的操作的类型。使用值`Delete`删除 PST 文件的找到您何时运行查找模式中的工具。<br/> | `-Mode Delete` <br/> |
    | `JobName` <br/> |指定现有的 PST 集合作业的名称。您必须使用此作业的名称相同查找模式和步骤 1 和步骤 3 中的收集模式中运行该工具时使用。此作业名称添加到您在删除模式下运行该工具时，将创建日志文件的名称。  <br/> | `-JobName PstSearch1` <br/> |
    | `ConfigurationLocation` <br/> |指定包含.xml 配置文件时收集模式中运行该工具创建的文件夹。使用相同的值用于此步骤 3 中的参数。  <br/> | `-ConfigurationLocation "c:\users\admin\ desktop\PSTCollection\Configuration"` <br/> |
    | `LogLocation` <br/> |指定删除模式的日志文件将被复制到的文件夹。这是一个可选参数。如果不包括它，日志文件复制到其中下载 PST 集合工具的文件夹。请考虑使用，以便所有日志文件将都保存在同一文件夹中查找和步骤 1 和步骤 3 中的收集模式运行该工具时所使用的日志位置相同。  <br/> | `-LogLocation "c:\users\admin\desktop\PSTCollection"` <br/> |
    | `ForceRestart` <br/> |此可选开关，可以重新在现有 PST 集合作业的删除模式运行该工具。如果您之前在删除模式中，运行该工具，但然后在使用查找模式下再次运行该工具`ForceRestart`切换重新扫描 PST 文件的位置，您可以使用此开关重新在删除模式下运行该工具并删除 PST 文件没有找到时您 re scanned 位置。当使用`ForceRestart`中删除模式，该工具的开关忽略任何以前的删除操作，尝试再次删除 PST 文件。<br/> | `-ForceRestart` <br/> 

    下面是一个示例使用的每个参数的实际值的 DataCollectorMaster.exe 工具的语法：
    
    ```
    DataCollectorMaster.exe -DataSource Pst -Mode Delete -JobName PstSearch1 -ConfigurationLocation "c:\users\admin\desktop\PSTCollection\Configuration" -LogLocation "c:\users\admin\desktop\PSTCollection"
    ```
   
    运行该命令后，则显示显示进度删除在步骤 1 中找到，在步骤 3 中收集的 PST 文件的详细的状态消息。后一段时间，最终状态消息显示是否存在任何错误和日志复制到的位置。相同的状态邮件复制到.log 文件。
    
### <a name="results-of-running-datacollectormasterexe-in-the-delete-mode"></a>在删除模式下运行 DataCollectorMaster.exe 的结果

成功删除模式中运行 DataCollectorMaster.exe 后，创建并在指定的文件夹中存储以下文件`LogLocation`和`ConfigurationLocation`参数。 
  
- **\<JobName\>_删除_\<DateTimeStamp\>.log** -日志文件中包含已显示状态消息。在指定的文件夹中创建此文件`LogLocation`参数。 
    
- **\<JobName\>_删除_\<DateTimeStamp\>.xml** -XML 文件仅包含其中使用该工具已删除模式中运行信息参数值。它还列出了每个已删除的 PST 文件的名称和文件路径。在指定的文件夹中创建此文件`ConfigurationLocation`参数。 
