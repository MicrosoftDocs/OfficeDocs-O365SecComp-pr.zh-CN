---
title: 安装 Microsoft Outlook 的垃圾邮件报告外接程序
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/9/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 8dcc752f-e22e-44ce-a104-4cc4d7e439f3
description: 在此 articleSupported 中 LanguagesInstall 垃圾电子邮件报告外接 inUninstall 垃圾电子邮件报告添加-inFor 详细信息
ms.openlocfilehash: 20fb879d3a965a973513a69cf8055f0d96507e9a
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30217022"
---
# <a name="install-the-junk-email-reporting-add-in-for-microsoft-outlook"></a>安装 Microsoft Outlook 的垃圾邮件报告外接程序
  
本主题描述如何在您组织的客户端计算机上安装（和卸载）Outlook 的 Microsoft 垃圾电子邮件报告外接程序。当前版本的外接程序（2016 年 1 月）包括对 Outlook 2016、Outlook 2013、Outlook 2010 和 Outlook 2007 的支持。 
  
该外接程序（针对所有受支持的语言）允许您直接从 Outlook 功能区报告垃圾邮件。该外接程序的英语版本包括直接通过功能区向 Microsoft 报告电子邮件问题的其他选项：
  
-   报告您收到的网页仿冒垃圾电子邮件 
    
- 报告被错误识别为垃圾邮件的电子邮件。
    
## <a name="supported-languages"></a>支持的语言
<a name="sectionSection0"> </a>

垃圾电子邮件报告外接程序支持下列语言： 
  
- 简体中文
    
- 繁体中文
    
- 荷兰语
    
- 英语
    
- 法语
    
- 德语
    
- 意大利语
    
- 日语
    
- 朝鲜语
    
- 葡萄牙语
    
- 葡萄牙语（巴西）
    
- 西班牙语
    
## <a name="install-the-junk-email-reporting-add-in"></a>安装垃圾电子邮件报告外接程序
<a name="sectionSection1"> </a>

您可以安装垃圾电子邮件报告外接程序：
  
- 像运行任何其他 .msi 文件一样运行 Windows Installer 程序包。当安装外接程序时，会打开一个 GUI 界面并通过安装屏幕提示您。有关详细信息，请参阅[使用安装向导安装垃圾电子邮件报告外接程序](install-the-junk-email-reporting-add-in-for-microsoft-outlook.md#BKMK_InstalltheJunkEmailReportingAdd-InUsingtheSetupWizard)。或者
    
- 运行不显示安装用户界面的静默安装。您可以转而指定运行安装脚本的命令行选项。当安装外接程序时，会提供无法通过 GUI 界面提供的其他配置选项。有关详细信息，请参阅[使用静默模式安装垃圾电子邮件报告外接程序](install-the-junk-email-reporting-add-in-for-microsoft-outlook.md#BKMK_InstalltheJunkEmailReportingAdd-IninSilentMode)。
    
### <a name="what-do-you-need-to-know-before-you-begin"></a>在开始之前，您需要知道什么？

安装 Microsoft Outlook 的 Microsoft 垃圾电子邮件报告外接程序需要以下条件：
  
- 下列操作系统之一：Windows 10、Windows 8.1、Windows 8、Windows 7 Service Pack 1、Windows 10 Server、Windows Server 2012 R2、Windows Server 2012 或 Windows Server 2008 R2
    
- Outlook 2016、Outlook 2013、Outlook 2010 或 Outlook 2007（Service Pack 2 或更高版本）
    
- Microsoft Office 主互操作程序集： 
    
  - 若要为 Microsoft Office 2010 或更高版本下载主互操作程序集，请转到 [Microsoft 下载中心](https://go.microsoft.com/fwlink/?LinkID=166026)。
    
  - 若要为 Microsoft Office 2007 下载主互操作程序集，请转到 [Microsoft 下载中心](https://go.microsoft.com/fwlink/?LinkId=72637)。
    
- Microsoft .NET Framework [版本 2.0](https://go.microsoft.com/fwlink/?LinkID=208706)。
    
> [!NOTE]
> 您必须在要安装外接程序的计算机上拥有管理员权限。 
  
### <a name="install-the-junk-email-reporting-add-in-using-the-setup-wizard"></a>使用安装向导安装垃圾电子邮件报告外接程序
<a name="BKMK_InstalltheJunkEmailReportingAdd-InUsingtheSetupWizard"> </a>

1. 在您的计算机上关闭 Outlook。
    
2. 转到 Microsoft 下载中心页面，获取 Microsoft Outlook 的 Microsoft 垃圾电子邮件报告外接程序[https://go.microsoft.com/fwlink/?LinkID=147248](https://go.microsoft.com/fwlink/?LinkID=147248)并下载 .msi 文件。 
    
3. 双击 .msi 文件。 
    
4. 在 "**欢迎使用 Microsoft 垃圾电子邮件报告外接程序安装程序**" 页上, 单击 "**下一步**"。 
    
5. 查看许可协议, 如果您同意安装条款 (必须继续安装), 请单击 "**我接受许可协议中的条款"** 。单击 "**下一步**" 继续。 
    
6. 向导完成后, 单击 "**完成**"。 
    
7. 启动 Outlook。
    
8. 查找 Outlook 功能区上的 "**垃圾邮件**" 按钮。您现在可以通过在收件箱中选择垃圾电子邮件并单击 "**报告垃圾**邮件" 按钮, 将垃圾电子邮件报告给 Microsoft。 
    
9. 如果要向 Microsoft 报告网络钓鱼诈骗电子邮件, 请选择 "**垃圾邮件**" 旁边的向下箭头, 如 "**报告为网络钓鱼**"。在 "垃圾邮件" 文件夹中, 如果电子邮件被错误地标识为垃圾邮件, 则还可以选择 "**不报告垃圾**邮件"。 
    
### <a name="install-the-junk-email-reporting-add-in-using-silent-mode"></a>使用静默模式安装垃圾电子邮件报告外接程序
<a name="BKMK_InstalltheJunkEmailReportingAdd-IninSilentMode"> </a>

1. 在您的计算机上关闭 Outlook。
    
2. 打开命令提示符。
    
3. 如果想要执行不带任何可选参数的外接程序直接安装，请指定下列内容：
    
  - 运行 x86 Outlook 的计算机： `msiexec /qn /i JunkReportingAdd-in.x86-en.msi`
    
  - 运行 x64 Outlook 的计算机： `msiexec /qn /i JunkReportingAdd-in.x64-en.msi`
    
    还可以指定可选 MaxMessageSelection 和 BccEmailAddress 参数：
    
  - MaxMessageSelection 允许管理员定义用户在一次单击中可选择提交的最大邮件数。范围为 1 到 50 封邮件，默认值为 10 封邮件。
    
    示例：如果您希望将用户在一次单击中可选择提交的最大邮件数设置为 16，请使用下列选项作为安装命令的一部分： `MaxMessageSelection=16`
    
  - BccEmailAddress 允许管理员通过设置密件抄送电子邮件地址，将邮箱设置为接收所有用户提交内容的副本。设置邮箱后，所有提交的电子邮件的副本将发送到 BccEmailAddress。否则，默认设置为没有密件抄送电子邮件地址。
    
    示例：如果您希望将 junkReports@contoso.com 用作所有提交内容的密件抄送电子邮件地址，请使用以下命令： `BccEmailAddress="junkReports@contoso.com"`
    
    > [!NOTE]
    > 通过在输入密件抄送电子邮件地址时使用分号分隔符，可以设置多个密件抄送电子邮件地址。示例： `BccEmailAddress="junkReports@contoso.com; hollyd@treyresearch.net"`
  
    要基于上述示例添加全部两个可选参数，需要为运行 x86 Outlook 的计算机指定以下内容： 
    
  ```
  msiexec /qn /i JunkReportingAdd-in.x86-en.msi. MaxMessageSelection=16 BccEmailAddress="junkReports@contoso.com; hollyd@treyresearch.net"
  ```

4. 安装完成后，启动 Outlook。
    
5. 查找 Outlook 功能区上的 "**垃圾邮件**" 按钮。您现在可以通过在收件箱中选择垃圾电子邮件并单击 "**报告垃圾**邮件" 按钮, 将垃圾电子邮件报告给 Microsoft。 
    
6. 如果要向 Microsoft 报告网络钓鱼诈骗电子邮件, 请选择 "**垃圾邮件**" 旁边的向下箭头, 如 "**报告为网络钓鱼**"。在 "垃圾邮件" 文件夹中, 如果电子邮件被错误地标识为垃圾邮件, 则还可以选择 "**不报告垃圾**邮件"。 
    
## <a name="uninstall-the-junk-email-reporting-add-in"></a>卸载垃圾电子邮件报告外接程序
<a name="sectionSection2"> </a>

使用下列选项之一卸载垃圾电子邮件报告外接程序：
  
- 使用 Windows 控制面板删除外接程序。有关详细信息，请参阅[从控制面板卸载垃圾电子邮件报告外接程序](install-the-junk-email-reporting-add-in-for-microsoft-outlook.md#BKMK_UninstalltheJunkEmailReportingAdd-infromControlPanel)。或者
    
- 运行 Windows Installer 程序包并选择卸载选项。有关详细信息，请参阅[通过运行 Windows Installer 程序包卸载垃圾电子邮件报告外接程序](install-the-junk-email-reporting-add-in-for-microsoft-outlook.md#BKMK_UninstalltheJunkEmailReportingAddinbyRunningtheWindowsInstallerPackage)。或者
    
- 使用卸载选项运行静默安装。有关详细信息，请参阅[在静默模式下卸载垃圾电子邮件报告外接程序](install-the-junk-email-reporting-add-in-for-microsoft-outlook.md#MK_UninstalltheJunkEmailReportingAdd-ininSilentMode)。
    
> [!NOTE]
> 您必须在要卸载外接程序的计算机上拥有管理员权限。 
  
### <a name="uninstall-the-junk-email-reporting-add-in-from-control-panel"></a>从控制面板卸载垃圾电子邮件报告外接程序
<a name="BKMK_UninstalltheJunkEmailReportingAdd-infromControlPanel"> </a>

1. 在您的计算机上关闭 Outlook。
    
2. 从计算机上的 "开始" 菜单中, 选择 **"控制面板"**。
    
3. 选择 "**程序和功能**"。
    
4. **为 microsoft Office Outlook 选择 microsoft 垃圾电子邮件报告外接程序**。
    
5. 选择 "**卸载**"。
    
6. 再次启动 Outlook 以确认该外接程序不再显示在 Outlook 功能区中。
    
### <a name="uninstall-the-junk-email-reporting-add-in-by-running-the-windows-installer-package"></a>通过运行 Windows Installer 程序包卸载垃圾电子邮件报告外接程序
<a name="BKMK_UninstalltheJunkEmailReportingAddinbyRunningtheWindowsInstallerPackage"> </a>

1. 在您的计算机上关闭 Outlook。
    
    > [!NOTE]
    > 如果在卸载过程中 Outlook 正在运行，则需要重新启动 Outlook 才能使外接程序完全卸载。 
  
2. 重新运行以前运行的用于安装外接程序的 .msi 文件。 
    
    （转到 Microsoft 下载中心页面，获取 Microsoft Outlook 的 Microsoft 垃圾电子邮件报告外接程序[https://go.microsoft.com/fwlink/?LinkId=147248](https://go.microsoft.com/fwlink/?LinkId=147248)并下载 .msi 文件，然后双击 .msi 文件。） 
    
3. 执行提示以卸载外接程序。
    
4. 再次启动 Outlook 以确认该外接程序不再显示在 Outlook 功能区中。
    
### <a name="uninstall-the-junk-email-reporting-add-in-in-silent-mode"></a>在静默模式下卸载垃圾电子邮件报告外接程序
<a name="MK_UninstalltheJunkEmailReportingAdd-ininSilentMode"> </a>

1. 在您的计算机上关闭 Outlook。
    
    > [!NOTE]
    > 如果在卸载过程中 Outlook 正在运行，则需要重新启动 Outlook 才能使外接程序完全卸载。 
  
2. 打开命令提示符。
    
3. 指定下列命令行参数：
    
    运行 x86 Outlook 的计算机： `msiexec /x JunkReportingAdd-in.x86-en.msi /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"`
    
    运行 x64 Outlook 的计算机： `msiexec /x JunkReportingAdd-in.x64-en.msi /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"`
    
4. 再次启动 Outlook 以确认该外接程序不再显示在 Outlook 功能区中。
    
## <a name="for-more-information"></a>详细信息
<a name="sectionSection3"> </a>

[向 Microsoft 报告垃圾邮件](report-junk-email-messages-to-microsoft.md)
  
[疑难解答信息和支持信息](troubleshooting-and-support-information.md)
  

