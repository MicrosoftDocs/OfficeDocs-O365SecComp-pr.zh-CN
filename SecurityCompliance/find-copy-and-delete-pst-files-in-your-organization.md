---
title: 使用 PST 集合工具在您的组织中查找、复制和删除 PST 文件
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: ''
search.appverid: MOE150
ms.assetid: 7a150c84-049c-4a9c-8c91-22355b35f2a7
description: 使用 Microsoft PST 收集工具搜索组织的网络, 以获取分散在整个组织中的 PST 文件的清单。 查找 pst 文件后, 可以使用 pst 集合工具将其复制到一个中心位置, 以便可以将其导入 Office 365。
ms.openlocfilehash: 87e13ec8a4c58f848ac2ff7a430a7532942ece74
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32255334"
---
# <a name="use-the-pst-collection-tool-to-find-copy-and-delete-pst-files-in-your-organization"></a>使用 PST 集合工具在您的组织中查找、复制和删除 PST 文件

> [!IMPORTANT]
> 任何 Microsoft standard 支持计划或服务都不支持本文中介绍的 PST 集合工具。 该工具按原样提供, 无任何种类的担保。 Microsoft 也不提供任何默示担保，包括但不仅限于对适销性或针对特定目的的适用性的默示担保。 由于工具的使用或性能的问题和文档将保留的全部风险。 在任何情况下, Microsoft、其作者或任何其他参与此工具的创建、生产或交付的其他人都不承担任何损害 (包括但不限于业务利润损失、业务中断、丢失损失)。因使用或无法使用该工具或文档而导致的业务信息或其他 pecuniary 丢失, 即使 Microsoft 已被告知可能发生此类损坏的情况也是如此。

您可以使用 Microsoft pst 集合工具在您的组织的网络中搜索 PST 文件。 该工具可帮助你获取分散在整个组织中的 PST 文件的清单。 查找 pst 文件后, 可以使用 pst 集合工具将其复制到一个中心位置。 将 pst 放在一个位置后, 可以将其导入到 exchange online 邮箱 (或单个 exchange online 邮箱) 中, 然后可以在 Office 365 中应用一组丰富的合规性功能。 这包括将 pst 导入到用户的存档邮箱, 使用电子数据展示搜索工具搜索您导入的 PST 文件中的特定邮件, 使用电子数据展示保留和 Office 365 保留策略保留邮件, 并管理生命周期这些邮件的循环使用 Exchange Online 中的邮件记录管理功能。 确信您收集的 PST 文件已成功导入到 Office 365 后, 您可以使用该工具将其从网络上的原始位置删除。 
  
您可以使用 PST 集合工具执行的另一件事是, 阻止用户创建新的 pst 文件, 并更改您在网络上找到的现有 pst 文件。 这些 "阻止" 功能使您能够查找、收集和导入一组已知的 pst 文件到 Office 365, 并防止将来在组织中增加 pst 文件。 
  
## <a name="how-the-pst-collection-tool-works"></a>PST 集合工具的工作原理

以下是使用 PST 收集工具在组织中查找、控制、收集和删除 pst 文件的过程的快速概述。
  
![PST 收集工具流程概述](media/67a29f27-f83c-4f0a-9df4-7ed92d3086fe.png)
  
1. **[步骤 1: 在您的网络上查找 pst 文件](#step-1-find-pst-files-on-your-network)**-当您运行该工具以查找 PST 文件时, 请指定一个位置, 如包含客户端和服务器计算机的 Active Directory 对象的组织单位。 您还可以搜索特定的计算机或网络文件共享。 运行该工具时, 会在目标计算机上安装 "轻型" 集合代理。 此代理在目标计算机上搜索 pst 文件, 然后将信息返回到 pst 收集工具, 以了解找到的任何 PST 文件。 该工具将创建日志文件, 其中包含有关在指定位置找到的 PST 文件的信息。 在后续步骤中运行此工具时, 将使用这些文件。 
    
2. **[(可选) 步骤 2: 控制对 PST 文件的访问](#optional-step-2-control-access-to-pst-files)**-该工具将创建一个组策略对象 (GPO), 其中包含阻止用户创建或更改 PST 文件的设置。 此 GPO 将应用于您的域中的每个用户。 此可选步骤可帮助您 "锁定" 在第1步中找到的 PST 文件, 以便您可以收集、导入和删除这些文件, 而不会创建新的 pst 文件或更改现有的 pst 文件。 
    
3. **[步骤 3: 将 pst 文件复制到收藏位置](#step-3-copy-the-pst-files-to-a-collection-location)**-这使您可以将 pst 文件收集到一个位置, 以便您可以在步骤4中使用 Office 365 导入服务将其导入到 Exchange Online 邮箱中。 当您在 "收集" 模式下运行该工具时, 每个集合代理都会将 PST 文件从安装该代理的目标计算机复制到该集合的位置。 
    
4. **[步骤 4: 将 pst 文件导入到 Office 365](#step-4-import-the-pst-files-to-office-365)** -将 pst 文件复制到一个位置后, 即可将其导入到 Exchange Online 邮箱。 
    
5. **[步骤 5: 删除在网络中找到的 pst 文件](#step-5-delete-the-pst-files-found-on-your-network)**-在您找到和收集的 pst 文件已导入到 Office 365 中的 Exchange Online 邮箱后, 您可以使用 PST 集合工具从原始位置删除 pst 文件在步骤1中找到。 

## <a name="before-you-begin"></a>准备工作

- 按照以下步骤将 PST 集合工具下载到本地计算机。 
    
    1. [下载 "PST 集合" 工具](https://aka.ms/pstcollectiontool)。
    
    2. 在弹出窗口中, 单击 "**保存** \> **另存为**", 将 PSTCollectionTool 文件保存到本地计算机上的文件夹中。 
    
    3. 将 PSTCollectionTool 文件提取到本地计算机上的文件夹中;默认文件夹名称为 PSTCollectionTool。
    
- 若要在任何模式 (查找、阻止、复制或删除) 中运行 PST 集合工具, 您必须是 Active Directory 域中的 Domain Administrators 组的成员。 

## <a name="step-1-find-pst-files-on-your-network"></a>步骤 1: 在网络中查找 PST 文件

第一步是运行 PST 集合工具以在您的组织中查找 pst 文件。 您可以使用此工具搜索以下类型的位置。 
  
- 本地 Active Directory 域中的组织单位 (ou)。 该工具将搜索指定 OU 中包含的所有计算机。 
    
- 客户端和服务器计算机。 该工具将搜索指定的计算机。 
    
- 网络文件共享。 该工具会搜索指定的网络文件共享。 
    
请参阅以下过程中`Locations`对 table 中参数的说明, 以获取用于每个位置类型的语法示例。 
  
> [!IMPORTANT]
> 您必须在 "查找" 模式下运行 "PST 集合" 工具, 然后才能执行其他操作, 例如阻止、收集或删除 PST 文件。 
  
1. 在您的本地计算机上打开命令提示符 (以管理员身份运行)。
    
2. 转到 PSTCollectionTool 文件夹 (或您将 PSTCollectionTool 文件提取到的文件夹)。
    
3. 转到 DataCollectorMaster 目录。
    
4. 运行以下命令, 在指定位置查找 PST 文件。
    
    ```
    DataCollectorMaster.exe -DataSource Pst -Mode Find -JobName <Name> -Locations <Locations to search for PSTs> -LogLocation <Location to store log files> -ConfigurationLocation <Location to store configuration files>
    ```

    下表介绍了运行 DataCollectorMaster 命令查找 PST 文件时的参数及其所需的值。 
    
    |参数 * * * *|****说明****|示例 * * * *|
    |:-----|:-----|:-----|
    | `DataSource` <br/> |指定要搜索的数据的类型。 目前, 您可以使用 "pst 集合" 工具搜索 PST 文件。  <br/> | `-DataSource Pst` <br/> |
    | `Mode` <br/> |指定工具将执行的操作的类型。 使用值`Find`在指定位置查找 PST 文件。 请注意, 该工具可以查找和获取有关在 outlook 中打开的 pst 文件以及连接到 outlook 配置文件的 pst 文件的信息。  <br/> | `-Mode Find` <br/> |
    | `JobName` <br/> |指定 PST 集合作业的名称。 在运行 pst 集合工具以阻止、收集和删除在运行该工具以查找 pst 文件时找到的 pst 文件时, 将使用此相同的作业名称。 此外, 还会将作业名称添加到日志和配置文件名称中。  <br/> | `-JobName PstSearch1` <br/> |
    | `Locations` <br/> | 指定要在其中搜索 PST 文件的一个或多个位置。 如果指定多个位置, 请使用分号 (;)分隔各个位置。 请务必用双引号 ("") 将此参数的各个值括起来。  <br/><br/>   下面是您可以搜索的位置类型所需的标识值格式。  <br/><br/>        **ou** -使用可分辨名称 (DN) 标识 ou;例如:`"OU=NorthAmerica,OU=NWRegion,OU=ITServices,DC=contoso,DC=com"` <br/> > [!IMPORTANT]> 不能指定内置计算机容器 (例如, CN = 计算机, DC = contoso, dc = com), 因为它不是组织单位。<br/> <br/> **计算机**-使用 DN 或完全限定的域名 (FQDN) 来标识网络上的客户端和服务器计算机;例如:  <br/>  DN`"CN=FILESERVER01,CN=Computers,DC=contoso,DC=com"` <br/>  或  <br/>  域名`"FILESERVER01.contoso.com"` <br/><br/>  **网络文件共享**-使用 UNC 名称来标识网络文件共享;例如,`"\\FILESERVER02\Users"` <br/> | `-Locations "CN=FILESERVER01,CN=Computers,DC=contoso,DC=com";"CN=FILESERVER02,CN=Computers,DC=contoso,DC=com"` <br/> |
    | `LogLocation` <br/> |指定要将日志文件复制到的文件夹。 如果该文件夹不存在, 则会在运行该工具时创建该文件夹。  <br/> | `-LogLocation "c:\users\admin\desktop\PSTCollection"` <br/> |
    | `ConfigurationLocation` <br/> |指定将把 .xml 配置文件复制到的文件夹。 此文件包含在运行该工具时找到的每个 PST 文件的相关信息。 当您在步骤3中运行该工具以复制找到的 PST 文件时, 将使用此文件。  <br/> | `-ConfigurationLocation "c:\users\admin\desktop\PSTCollection\Configuration"` <br/> |
    | `ExcludedLocations` <br/> |此可选参数指定在查找操作过程中要跳过的位置。 您可以排除特定 ou、计算机和网络文件共享。 例如, 您可以排除计算机, 如配置为 SQL server 的计算机 (或其他类型的应用程序服务器), 用户无法访问这些计算机。 如果指定要排除的一个或多个位置, 请使用分号 (;)分隔各个位置。 请务必用双引号 ("") 将此参数的各个值括起来。  <br/> | `-ExcludedLocations "SQLSERVER01.contoso.com"` <br/> |
    | `ForceRestart` <br/> |此可选开关允许您在 "查找" 模式下为现有的 PST 集合作业运行该工具。 使用此`ForceRestart`开关时, 将丢弃作业的上一个查找操作的结果, 并且该工具将重新扫描指定的位置并创建新的日志和配置文件。  <br/> | `-ForceRestart` <br/> |
   
    下面的示例展示了使用每个参数的实际值的 DataCollectorMaster 命令的语法:
    
    ```
    DataCollectorMaster.exe -DataSource Pst -Mode Find -JobName PstSearch1 -Locations "CN=FILESERVER01,CN=Computers,DC=contoso,DC=com";"CN=FILESERVER02,CN=Computers,DC=contoso,DC=com" -LogLocation "c:\users\admin\desktop\PSTCollection" -ConfigurationLocation "c:\users\admin\desktop\PSTCollection\Configuration"
    ```

    运行命令后, 将显示详细的状态消息, 显示在指定位置查找 PST 文件的进度。 一段时间后, 最终状态邮件会显示找到的 PST 文件总数、作业是否已完成以及是否有任何错误。 将相同的状态邮件复制到 .log 文件。
    
### <a name="results-of-running-datacollectormasterexe-in-the-find-mode"></a>在 "查找" 模式下运行 DataCollectorMaster 的结果

在成功运行 PST 集合工具的 "查找" 模式后, 将创建以下文件并将其存储在由`LogLocation`和`ConfigurationLocation`参数指定的文件夹中。 
  
- **\>__ JobName Find\<DateTimeStamp\>-日志文件包含显示的状态\<** 消息。 此文件在由`LogLocation`参数指定的文件夹中创建。 
    
- **\>__ JobName 找到\<DateTimeStamp\>-csv 文件中包含每个找到的 PST 文件对应的\<** 行。 每个 pst 的信息包括找到 pst 文件的计算机、pst 文件的完整文件路径位置、pst 文件的所有者以及 pst 文件的大小 (以 kb、kb)。 此文件在由`LogLocation`参数指定的文件夹中创建。 
    
    > [!TIP]
    > 使用 Excel 中的 "自动求和" 工具计算 CSV 文件中列出的所有 PST 文件的总大小 (以 KB 为单位)。 然后, 可以使用转换计算器将总大小转换为兆字节 (MB) 或千兆字节 (gb)。 
  
- **\>__ JobName Find\<DateTimeStamp\>-xml 文件包含在 "查找" 模式下运行该工具时使用的参数值的相关\<** 信息。 此文件还包含有关找到的每个 PST 文件的信息。 当您运行同一作业的工具以阻止、收集或删除找到的 PST 文件时, 将使用此文件中的数据。 此文件在由`ConfigurationLocation`参数指定的文件夹中创建。 
    
    > [!IMPORTANT]
    > 请勿重命名、更改或移动此文件。 当您在相同作业的阻止、复制或删除模式下重新运行该工具时, 它将由 PST 收集工具使用。 

## <a name="optional-step-2-control-access-to-pst-files"></a>Optional步骤 2: 控制对 PST 文件的访问

此可选步骤允许您 "锁定" 在步骤1中找到的 pst 文件, 以便您可以将一组已知的 pst 文件收集并导入到 Office 365。 当您在阻止模式下运行 PST 集合工具时, 会发生以下情况: 
  
- 该工具将创建一个名为 " *PST Usage Controls* " 的组策略对象 (GPO)。 此 GPO 链接到你的域, 并适用于组织中的所有经过身份验证的用户。 
    
- PST 用法控制 GPO 在组织中的计算机上创建注册表设置。 根据您使用的参数, 您可以创建注册表设置, 以阻止用户创建新的 pst 文件和注册表设置, 以防止用户更改现有的 pst 文件。
    
> [!NOTE]
> 如果控制对您的组织的访问 PST 文件的访问过严重, 则可以考虑跳过此步骤, 并执行步骤 3, 将 PST 文件复制到一个中心位置。 然后, 可以为同一作业 (通过使用`ForceRestart`参数) 重复步骤 1, 以查找在将 pst 文件复制到集合位置之后创建的其他 pst 文件。 如果找到了新的 PST 文件, 则可以将其复制到集合位置。 当您在 " `ForceRestart`查找" 模式下重新运行该工具时使用该参数时, 将放弃针对某个作业的以前的查找操作的结果, 并且该工具将重新扫描指定的位置。 

若要阻止对 PST 文件的访问, 请执行以下操作:

1. 在您的本地计算机上打开命令提示符 (以管理员身份运行)。
    
2. 转到您在其中下载了 PST 集合工具的目录。
    
3. 运行以下命令, 以阻止对在步骤1中找到的 PST 文件的访问。

    ```
    DataCollectorMaster.exe -DataSource Pst -Mode Block -JobName <Name of job from Step 1> -ConfigurationLocation <Location of configuration files from Step 1> -BlockChangesToFiles -BlockNewFiles
    ```

    下表介绍了运行 DataCollectorMaster 命令以阻止创建和更改 PST 文件时所需的参数及其所需的值。 
    
    |参数 * * * *|****说明****|示例 * * * *|
    |:-----|:-----|:-----|
    | `DataSource` <br/> |指定要搜索的数据的类型。 目前, 您可以使用 "pst 集合" 工具搜索 PST 文件。  <br/> | `-DataSource Pst` <br/> |
    | `Mode` <br/> |指定工具将执行的操作的类型。 使用此值`Block`可阻止用户创建新的 pst 文件并对现有的 pst 文件进行更改。  <br/> | `-Mode Block` <br/> |
    | `JobName` <br/> |指定现有 PST 集合作业的名称。 您必须使用在第1步中的 "查找" 模式下运行该工具时使用的相同作业名称。 此外, 还会将此作业名称添加到在阻止模式下运行该工具时创建的日志文件的名称。  <br/> | `-JobName PstSearch1` <br/> |
    | `ConfigurationLocation` <br/> |指定文件夹包含在 "查找" 模式下运行该工具时创建的 .xml 配置文件。 使用您在步骤1中用于此参数的相同值。  <br/> | `-ConfigurationLocation "c:\users\admin\desktop\PSTCollection\Configuration"` <br/> |
    | `LogLocation` <br/> |指定将阻止操作的日志文件复制到的文件夹。 这是一个可选参数。 如果不包含此文件, 则会将日志文件复制到您在其中下载 PST 集合工具的文件夹。 考虑在第1步中的 "查找" 模式下运行该工具时使用的相同日志位置, 以便将所有日志文件保存在同一文件夹中。  <br/> | `-LogLocation "c:\users\admin\desktop\PSTCollection"` <br/> |
    | `BlockChangesToFiles` <br/> |使用此开关可阻止用户更改 PST 文件。 使用此开关时, 将创建以下注册表项: `HKEY_CURRENT_USER\Software\Policies\Microsoft\Office\<version>\Outlook\PST\PstDisableGrow`并将数据值设置为1。 在您的组织中的计算机上创建此注册表设置, 该 GPO 在您在阻止模式下运行 PST 集合工具时创建。  <br/> | `-BlockChangesToFiles` <br/> |
    | `BlockNewFiles` <br/> |使用此开关可阻止用户创建新的 pst 文件、打开和导入 pst 文件并将其导入 outlook, 以及从 outlook 导出 pst 文件。 使用此开关时, 将创建以下注册表项: `HKEY_CURRENT_USER\Software\Policies\Microsoft\Office\<version>\Outlook\DisablePst`并将数据值设置为1。 在您的组织中的计算机上创建此注册表设置, 该 GPO 在您在阻止模式下运行 PST 集合工具时创建。  <br/> | `-BlockNewFiles` <br/> |
   
    下面的示例展示了使用每个参数的实际值的 DataCollectorMaster 命令的语法:

    ```
    DataCollectorMaster.exe -DataSource Pst -Mode Block -JobName PstSearch1 -ConfigurationLocation "c:\users\admin\desktop\PSTCollection\Configuration" -LogLocation "c:\users\admin\desktop\PSTCollection" -BlockChangesToFiles -BlockNewFiles
    ```
    
    系统将提示您确认是否要阻止新的 pst 文件或对现有 pst 文件所做的更改。 在您确认要继续运行该命令后, 会显示一条消息, 指出已创建一个名为 "PST Usage Controls" 的新 GPO。
    
## <a name="step-3-copy-the-pst-files-to-a-collection-location"></a>步骤 3: 将 PST 文件复制到集合位置

下一步是复制在 "查找" 模式下运行 pst 集合工具时找到的 pst 文件。 这样, 您可以在一个位置收集 PST 文件, 以便以后将其导入 Office 365。 将 PST 文件复制到集合位置之前, 请考虑确定所需的总存储空间量。 您可以使用在第1步中创建的 CSV 文件来计算所有 PST 文件的总大小。
  
> [!NOTE]
> 将 PST 文件导入到 Office 365 并将其从原始位置删除后, 您可能希望在此步骤中将其从复制它们的集合位置中删除。 
  
1. 在您的本地计算机上打开命令提示符 (以管理员身份运行)。
    
2. 转到您在其中下载了 PST 集合工具的目录。
    
3. 运行以下命令, 将 PST 文件复制到指定位置。
    
    ```
    DataCollectorMaster.exe -DataSource Pst -Mode Collect -JobName <Name of job from Step 1> -Locations <same locations from Step 1> -ConfigurationLocation <Location of configuration files from Step 1> -CopyLocation <Location to copy PST files to>
    ```

    下表介绍了运行 DataCollectorMaster 命令复制 PST 文件时所需的参数及其所需的值。 
    
    |参数 * * * *|****说明****|示例 * * * *|
    |:-----|:-----|:-----|
    | `DataSource` <br/> |指定要搜索的数据的类型。 目前, 您可以使用 "pst 集合" 工具搜索 PST 文件。  <br/> | `-DataSource Pst` <br/> |
    | `Mode` <br/> |指定工具将执行的操作的类型。 使用值`Collect`可复制在 "查找" 模式下运行到该工具时找到的 PST 文件。 请注意, 该工具能够复制在 outlook 中打开的 pst 文件, 并复制连接到 outlook 配置文件的 pst 文件。  <br/> | `-Mode Collect` <br/> |
    | `JobName` <br/> |指定现有 PST 集合作业的名称。 您必须使用在第1步中的 "查找" 模式下运行该工具时使用的相同作业名称。 此外, 还会将此作业名称添加到在收集模式下运行该工具时创建的日志文件的名称。  <br/> | `-JobName PstSearch1` <br/> |
    | `Locations` <br/> |使用您在步骤1中用于`Locations`参数的相同值。 当您在收集模式下运行该工具时, 如果要在步骤5中重新运行该工具以删除其源位置中的 PST 文件, 则必须包含此参数。  <br/> | `-Locations "CN=FILESERVER01,CN=Computers,DC=contoso,DC=com"; "CN=FILESERVER02,CN=Computers,DC=contoso,DC=com"` <br/> |
    | `ConfigurationLocation` <br/> |指定包含在 "查找" 模式下运行该工具时所创建的 .xml 配置文件的文件夹。 使用您在步骤1中用于此参数的相同值。  <br/> | `-ConfigurationLocation "c:\users\admin\desktop \PSTCollection\Configuration"` <br/> |
    | `CopyLocation` <br/> |指定要将 PST 文件复制到的集合位置。 您可以将文件复制到文件服务器、网络文件共享或硬盘。 在收集模式下运行该工具之前, 该位置必须存在。 该工具不会创建位置, 并将返回错误消息, 指出它不存在。  <br/> 此外, 您还必须向此参数指定的集合位置写入权限。  <br/> | `-CopyLocation "\\FILESERVER03\PSTs"` <br/> |
    | `LogLocation` <br/> |指定要将收集模式的日志文件复制到的文件夹。 这是一个可选参数。 如果不包含此文件, 则会将日志文件复制到您在其中下载 PST 集合工具的文件夹。 考虑在第1步中的 "查找" 模式下运行该工具时使用的相同日志位置, 以便将所有日志文件保存在同一文件夹中。  <br/> | `-LogLocation "c:\users\admin\desktop\PSTCollection"` <br/> |
    | `ForceRestart` <br/> |此可选开关允许您在集合模式下为现有的 PST 集合作业重新运行该工具。 如果您以前在收集模式下运行该工具, 但随后在查找模式下`ForceRestart`再次运行该工具以重新扫描 PST 文件的位置, 则可以使用此开关在收集模式下重新运行该工具, 并在您的计算机上重新复制已找到的 pst 文件。重新扫描位置。 在收集模式`ForceRestart`下使用切换时, 该工具将忽略任何以前的集合操作, 并尝试从头开始复制 PST 文件。  <br/> | `-ForceRestart` <br/> |
   
    下面的示例展示了 DataCollectorMaster 工具的语法, 使用每个参数的实际值:
    
    ```
    DataCollectorMaster.exe -DataSource Pst -Mode Collect -JobName PstSearch1 -Locations "CN=FILESERVER01,CN=Computers,DC=contoso,DC=com";"CN=FILESERVER02,CN=Computers,DC=contoso,DC=com" -ConfigurationLocation "c:\users\admin\desktop\PSTCollection\Configuration" -CopyLocation "\\FILESERVER03\PSTs" -LogLocation "c:\users\admin\desktop\PSTCollection"
    ```

    运行命令后, 将显示详细的状态消息, 显示收集在步骤1中找到的 PST 文件的进度。 一段时间后, 最终状态消息将显示是否存在任何错误以及日志复制到的位置。 将相同的状态邮件复制到 .log 文件。
    
### <a name="results-of-running-datacollectormasterexe-in-the-collect-mode"></a>在收集模式下运行 DataCollectorMaster 的结果

在收集模式下成功运行 DataCollectorMaster 后, 将创建以下文件并将其存储在由`LogLocation`和`ConfigurationLocation`参数指定的文件夹中。 
  
- **\>__ JobName 收集\<DateTimeStamp\>-日志文件包含显示的状态\<** 消息。 此文件在由`LogLocation`参数指定的文件夹中创建。 
    
- **\>__ JobName 收集\<DateTimeStamp\>-xml 文件仅包含在收集模式下运行工具所使用的参数值的相关\<** 信息。 当您运行 DataCollectorMaster 工具以删除 PST 文件时, 将使用此文件中的数据;请参阅[第5步](#step-5-delete-the-pst-files-found-on-your-network)。
    

## <a name="step-4-import-the-pst-files-to-office-365"></a>步骤 4: 将 PST 文件导入到 Office 365

在您收集了在第1步中找到的 PST 文件之后, 下一步是将其导入到 Office 365 中的邮箱。 作为部件或导入过程, 您必须创建一个 CSV 映射文件, 其中包含要导入的每个 PST 文件的行。 每行中的信息指定 pst 文件的名称、用户的电子邮件地址以及是否要将 pst 文件导入到用户的主邮箱或存档邮箱。 使用**JobName\>_Find_\<DateTimeStamp**文件 (在步骤中创建) 1 中的信息来帮助您创建 csv 映射文件。 
  
有关将 PST 文件导入到 Office 365 的分步说明, 请参阅下列主题之一:
  
- [使用网络上载将 PST 文件导入到 Office 365](use-network-upload-to-import-pst-files.md)
    
- [使用驱动器寄送，将 PST 文件导入到 Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md)
    

## <a name="step-5-delete-the-pst-files-found-on-your-network"></a>步骤 5: 删除在网络中找到的 PST 文件

在 Office 365 中已将您找到和收集的 PST 文件导入到 Exchange Online 邮箱后, 您可以使用 pst 集合工具从第1步中找到的原始源位置删除 pst 文件。 
  
1. 在您的本地计算机上打开命令提示符 (以管理员身份运行)。
    
2. 转到您在其中下载了 PST 集合工具的目录。
    
3. 运行以下命令以删除 PST 文件。

    ```
    DataCollectorMaster.exe -DataSource Pst -Mode Delete -JobName <Name of job from Step 1> -ConfigurationLocation <Location of configuration files from Step 1> -CopyLocation <Location to copy PST files to>
    ```

    下表介绍了运行 DataCollectorMaster 命令删除 PST 文件时的参数及其所需的值。 
    
    |参数 * * * *|****说明****|示例 * * * *|
    |:-----|:-----|:-----|
    | `DataSource` <br/> |指定要搜索的数据的类型。 目前, 您可以使用 "pst 集合" 工具搜索 PST 文件。 ![定位](media/b078d05c-3aee-4b9f-8805-6a8a9d8970ee.png)           <br/> | `-DataSource Pst` <br/> |
    | `Mode` <br/> |指定工具将执行的操作的类型。 使用此值`Delete`可以删除在 "查找" 模式下运行到该工具时找到的 PST 文件。  <br/> | `-Mode Delete` <br/> |
    | `JobName` <br/> |指定现有 PST 集合作业的名称。 您必须使用在 "查找" 模式下运行该工具时使用的相同作业名称, 以及步骤1和步骤3中的收集模式。 此外, 还会将此作业名称添加到在删除模式下运行该工具时创建的日志文件的名称。  <br/> | `-JobName PstSearch1` <br/> |
    | `ConfigurationLocation` <br/> |指定包含在收集模式下运行该工具时创建的 .xml 配置文件的文件夹。 使用您在步骤3中用于此参数的相同值。  <br/> | `-ConfigurationLocation "c:\users\admin\ desktop\PSTCollection\Configuration"` <br/> |
    | `LogLocation` <br/> |指定要将删除模式的日志文件复制到的文件夹。 这是一个可选参数。 如果不包含此文件, 则会将日志文件复制到您在其中下载 PST 集合工具的文件夹。 考虑在第1步和第3步中的查找和收集模式下运行该工具时使用的相同日志位置, 以便将所有日志文件保存在同一文件夹中。  <br/> | `-LogLocation "c:\users\admin\desktop\PSTCollection"` <br/> |
    | `ForceRestart` <br/> |此可选开关允许您在删除模式下为现有的 PST 集合作业重新运行该工具。 如果您之前在删除模式下运行该工具, 但随后在查找模式下`ForceRestart`再次运行该工具以重新扫描 PST 文件的位置, 则可以使用此开关在删除模式下重新运行该工具, 并删除在重新运行时发现的 pst 文件。nned 位置。 在删除模式`ForceRestart`下使用切换时, 该工具将忽略任何以前的删除操作, 并再次尝试删除 PST 文件。  <br/> | `-ForceRestart` <br/> 

    下面的示例展示了 DataCollectorMaster 工具的语法, 使用每个参数的实际值:
    
    ```
    DataCollectorMaster.exe -DataSource Pst -Mode Delete -JobName PstSearch1 -ConfigurationLocation "c:\users\admin\desktop\PSTCollection\Configuration" -LogLocation "c:\users\admin\desktop\PSTCollection"
    ```
   
    运行命令后, 将显示详细的状态消息, 显示删除在步骤1中找到并在步骤3中收集的 PST 文件的进度。 一段时间后, 最终状态消息将显示是否存在任何错误以及日志复制到的位置。 将相同的状态邮件复制到 .log 文件。
    
### <a name="results-of-running-datacollectormasterexe-in-the-delete-mode"></a>在删除模式下运行 DataCollectorMaster 的结果

在删除模式下成功运行 DataCollectorMaster 后, 将创建以下文件并将其存储在由`LogLocation`和`ConfigurationLocation`参数指定的文件夹中。 
  
- **\>__ JobName 删除\<DateTimeStamp\>-日志文件包含显示的状态\<** 消息。 此文件在由`LogLocation`参数指定的文件夹中创建。 
    
- JobName-xml 文件仅包含在删除模式下运行工具所使用的参数值的相关信息。 **\>__\< \<\>** 它还列出了每个已删除的 PST 文件的名称和文件路径。 此文件在由`ConfigurationLocation`参数指定的文件夹中创建。 
