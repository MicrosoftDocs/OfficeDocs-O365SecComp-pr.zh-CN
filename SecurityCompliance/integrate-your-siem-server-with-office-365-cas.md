---
title: 将 SIEM 服务器与 Office 365 云应用安全集成
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: dd6d2417-49c4-4de6-9294-67fdabbf8532
description: 您可以与 Office 365 云应用程序安全性集成 SIEM 服务器。阅读这篇文章，获取它的工作方式以及如何将其设置的概述。
ms.openlocfilehash: a2bd75e73ddccef9359ace304faa3c8b1dd4a728
ms.sourcegitcommit: 17c7e18d7d00135b1af40cbea117c9a817a41117
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/24/2018
ms.locfileid: "24972324"
---
# <a name="integrate-your-siem-server-with-office-365-cloud-app-security"></a>将 SIEM 服务器与 Office 365 云应用安全集成
  
|评估 * *\>**|规划 * *\>**|部署 * *\>**|使用率 ***|
|:-----|:-----|:-----|:-----|
|[启动评估](office-365-cas-overview.md) <br/> |[开始规划](get-ready-for-office-365-cas.md) <br/> |在这里 ！  <br/> [下一步](utilization-activities-for-ocas.md) <br/> |[开始利用](utilization-activities-for-ocas.md) <br/> |
   
您可以与要启用的通知的集中监控您安全信息和事件管理 (SIEM) 服务器集成[Office 365 云应用程序安全性](get-ready-for-office-365-cas.md)。这是将云服务的组织特别有用，本地服务器应用程序。将与 SIEM server 集成允许您以更好地保持通过自动化某些安全过程和关联之间的基于云的常规安全工作流，同时保护您的 Office 365 应用程序的安全团队和本地事件。  
  
首先集成 SIEM 服务器与 Office 365 云应用程序安全性时, 从最近两天的通知转发到 SIEM 服务器，以及所有通知，然后从上 （基于您选择的任何筛选器）。此外，如果您禁用此功能长时间，当您启用它再次，它会将在过去两天的通知，然后所有通知此后转发。
 
## <a name="siem-integration-architecture"></a>SIEM 集成体系结构

在贵组织的网络中设置的 SIEM 代理。SIEM 代理配置和部署时, 提取已配置的数据类型 （警报） 使用 Office 365 云应用程序安全 RESTful Api。然后通过端口 443 上加密 HTTPS 通道发送通信。
  
时 SIEM 代理从 Office 365 云应用程序安全性检索数据，它将系统日志消息发送到本地 SIEM 服务器使用 （TCP 或与自定义端口的 UDP） 的安装过程中提供的网络配置。

![SIEM 和云应用程序安全体系结构](media/siem-architecture.png)

## <a name="supported-siem-servers"></a>支持的 SIEM 服务器

Office 365 云应用程序安全性当前支持以下 SIEM 服务器：
- 微焦点推荐 ArcSight
- 泛型 CEF

## <a name="prerequisites"></a>先决条件

- 您必须是要执行本文中描述的任务的全局管理员或 security 管理员程序。请参阅[Permissions in Office 365 安全性&amp;合规性中心](permissions-in-the-security-and-compliance-center.md)

- 您必须为您的组织中具有[启用 Office 365 云应用程序安全性](turn-on-office-365-cas.md)。

- [审核日志记录](turn-audit-log-search-on-or-off.md)必须打开 Office 365

- 您必须满足以下要求才能配置 SIEM 服务器集成的标准服务器：
    - 操作系统： Windows 或 Linux （这可以是虚拟机）
    - CPU: 2
    - 磁盘空间： 20 GB
    - RAM: 2 GB
    - 安装[oracle Java 8](http://www.oracle.com/technetwork/java/javase/downloads/index.html)
    - [网络要求](https://docs.microsoft.com/cloud-app-security/network-requirements)中所述配置防火墙

- 您必须具有**远程系统日志主机**和**Syslot 端口号**的详细信息。网络管理员或安全管理员应该能够帮助您找到这些信息。 

- 您必须同意[软件许可条款](https://go.microsoft.com/fwlink/?linkid=862491)，若要下载[JAR 文件](https://go.microsoft.com/fwlink/?linkid=838596)需要将 SIEM 服务器集成。
 
## <a name="integrate-office-365-cloud-app-security"></a>集成 Office 365 云应用程序安全性
    
### <a name="step-1-set-it-up-in-the-office-365-cloud-app-security-portal"></a>步骤 1： 设置其 Office 365 云应用程序安全性门户中

1. 转到[https://protection.office.com](https://protection.office.com)和 Office 365 中使用您的工作或学校帐户登录。(您将转到安全&amp;合规性中心。) 
    
2. 转到**通知** \> **管理高级通知**。
    
3. 选择**转到 Office 365 云应用程序安全性**。<br/>
    ![安全中&amp;合规性中心中，选择管理高级通知转到 Office 365 云应用程序安全性](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)
  
4. 单击**设置** \> **安全扩展**。<br/>
![选择设置 > 安全扩展](media/Settings-SecurityExtensions.png)

5. 选择**添加 SIEM 代理**。<br/>![选择添加 SIEM 代理。](media/SIEMAgents.png)
    
6. 选择**启动向导**。<br/>![获取帮助或启动向导](media/HelpOrWizard.png) 
    
7. 在**常规**步骤中，指定名称，并**选择 SIEM 格式**，并设置任何**高级设置**的格式与相关。然后选择**下一步**。<br/>![指定名称和类型](media/ChooseAgentTypeAndName.png)
    
8. 在**远程系统日志**步骤中，指定的 IP 地址或**远程 syslog 主机**和**Syslog 端口号**的主机名。选择 TCP 或 UDP 作为远程 Syslog 协议。（您可以使用网络管理员或安全管理员获取这些详细信息，如果您没有这些。）然后选择**下一步**。<br/>![指定远程系统日志的详细信息](media/ArcSightS1Syslog.png)
  
9. 在**数据类型**步骤中，执行以下内容，之一，然后单击**下一步**：
    - 保留**所有通知**的默认设置<br/>OR
    - 单击**所有通知**，，然后选择**特定的筛选器**。定义筛选器以选择要向 SIEM 服务器发送的通知的类型。<br/>![向导的步骤的数据类型](media/ArcSightS1ExportOptions.png)
  
10. 在祝贺您屏幕上，复制标记并将其保存为更高版本。<br/>![SIEM 创建代理屏幕](media/SIEMAgentFinished.png) 

> [!IMPORTANT]
> 此时，您已设置 Office 365 云应用程序安全性，SIEM 代理，但尚未完成您 SIEM 服务器集成。继续执行下一步继续 SIEM server 的集成。

单击关闭和保留向导，在安全扩展屏幕上之后，您可以看到您在表中添加的 SIEM 代理。它连接更高版本之前，它将显示**创建**的状态。

![创建 SIEM 代理](media/SIEMAgentCreated.png)
    
### <a name="step-2-download-the-jar-file-and-run-it-on-your-server"></a>步骤 2： 将 JAR 文件下载并运行在服务器上

1. 下载[Microsoft 云应用程序安全 SIEM 代理](https://go.microsoft.com/fwlink/?linkid=838596)并解压缩文件夹。（必须同意[软件许可条款](https://go.microsoft.com/fwlink/?linkid=862491)才能继续。） 
    
2. 从 zip 文件夹中提取的.jar 文件，并在服务器上运行它。
    
3. 在运行该文件之后, 运行以下命令： 命令：<br/>
  ```
  java -jar mcas-siemagent-0.87.20-signed.jar [--logsDirectory DIRNAME] [--proxy ADDRESS[:PORT]] --token TOKEN
  ```
#### <a name="important-notes"></a>重要说明

- 文件名可能有所不同具体取决于 SIEM 代理的版本。 

- 我们建议在服务器安装过程中，您的服务器上运行 JAR 填充。
    - **Windows**： 运行作为计划任务，并确保配置任务**运行或不用户是否登录**和清除**如果运行超过停止任务**选项。

    - **Linux**： 添加运行的命令与**&** 到`rc.local`文件。 <br/>示例：<br/> 
    ```
    java -jar mcas-siemagent-0.87.20-signed.jar [--logsDirectory DIRNAME] [--proxy ADDRESS[:PORT]] --token TOKEN &
    ```

- 中括号 [] 参数是可选的并应仅当相关。使用以下变量：
    - **DIRNAME**是您想要使用的本地代理调试日志目录的路径。
    - **地址 [: 端口]** 是代理服务器地址和服务器用于连接到 Internet 的端口。
    - **令牌**是您在第一个过程中复制 SIEM 代理标记。
    - 若要获取帮助，请键入`-h`。 
  
### <a name="step-3-validate-that-the-siem-agent-is-working"></a>步骤 3： 验证 SIEM 代理工作

1. 请确保在 Office 365 云应用程序安全性门户 SIEM 代理的状态不显示为**连接错误**或**已断开连接**，并且有任何代理通知。<br/>例如，此处我们可以看到 SIEM 服务器连接：<br/>![SIEM 服务器连接](media/siem-connected.png)<br/>并在这里，我们可以看到 SIEM 服务器已断开连接：<br/>![未连接的 SIEM 服务器](media/siem-not-connected.png) 
  
2. 在您的系统日志/SIEM 服务器，请确保您看到通知均已到达从 Office 365 云应用程序安全性。
  
## <a name="regenerating-your-token"></a>重新生成您的令牌

如果您丢失了您的标记，则可以始终重新生成它。在表中，找到所在行的 SIEM 代理。单击省略号，，然后选择**重新生成令牌**。

![通过单击省略号 SIEM 代理再生令牌](media/04de368a-b88e-4a9c-a830-58025cb98db6.png)
  
## <a name="editing-your-siem-agent"></a>编辑 SIEM 代理

若要编辑您 SIEM 代理，在表中，找到 SIEM 代理所在行。单击省略号，，，然后选择**编辑**。如果您编辑 SIEM 代理，不需要重新运行.jar 文件;自动更新。

![若要编辑 SIEM 代理，选择省略号，，，然后选择编辑。](media/96d0b362-3e0c-4dff-b2b4-d7af5b1bfb91.png)
  
## <a name="deleting-your-siem-agent"></a>删除 SIEM 代理

若要删除您 SIEM 代理，在表中，找到 SIEM 代理所在行。单击省略号，，，然后选择**删除**。

![若要删除的 SIEM 代理，选择省略号，，，然后选择删除。](media/540b5bdf-5574-4ecc-a7b0-92a499a387d7.png)

## <a name="sample-logfiles"></a>示例日志文件

下面是可能发送到 SIEM 服务器通知日志文件示例：

```
2017-07-15T20:42:30.531Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|myPolicy|3|externalId=596a7e360c204203a335a3fb start=1500151350531 end=1500151350531 msg=Activity policy ''myPolicy'' was triggered by ''admin@box-contoso.com'' suser=admin@box-contoso.com destinationServiceName=Box cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596a7e360c204203a335a3fb cs2Label=uniqueServiceAppIds cs2=APPID_BOX cs3Label=relatedAudits cs3=1500151288183_acc891bf-33e1-424b-a021-0d4370789660 cs4Label=policyIDs cs4=59f0ab82f797fa0681e9b1c7

2017-07-16T09:36:26.550Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|test-activity-policy|3|externalId=596b339b0c204203a33a51ae start=1500197786550 end=1500197786550 msg=Activity policy ''test-activity-policy'' was triggered by ''user@contoso.com'' suser=user@contoso.com destinationServiceName=Salesforce cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596b339b0c204203a33a51ae cs2Label=uniqueServiceAppIds cs2=APPID_SALESFORCE cs3Label=relatedAudits cs3=1500197720691_b7f6317c-b8de-476a-bc8f-dfa570e00349 cs4Label=policyIDs cs4=

2017-07-16T09:17:03.361Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|test-activity-policy3|3|externalId=596b2fd70c204203a33a3eeb start=1500196623361 end=1500196623361 msg=Activity policy ''test-activity-policy3'' was triggered by ''admin@contoso.com'' suser=admin@contoso.com destinationServiceName=Office 365 cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596b2fd70c204203a33a3eeb cs2Label=uniqueServiceAppIds cs2=APPID_O365 cs3Label=relatedAudits cs3=1500196549157_a0e01f8a-e29a-43ae-8599-783c1c11597d cs4Label=policyIDs cs4=

2017-07-16T09:17:15.426Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|test-activity-policy|3|externalId=596b2fd70c204203a33a3eec start=1500196635426 end=1500196635426 msg=Activity policy ''test-activity-policy'' was triggered by ''admin@contoso.com'' suser=admin@contoso.com destinationServiceName=Microsoft Office 365 admin center cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596b2fd70c204203a33a3eec cs2Label=uniqueServiceAppIds cs2=APPID_O365_PORTAL cs3Label=relatedAudits cs3=1500196557398_3e102b20-d9fa-4f66-b550-8c7a403bb4d8 cs4Label=policyIDs cs4=59f0ab35f797fa9811e9b1c7

2017-07-16T09:17:46.290Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|test-activity-policy4|3|externalId=596b30200c204203a33a4765 start=1500196666290 end=1500196666290 msg=Activity policy ''test-activity-policy4'' was triggered by ''admin@contoso.com'' suser=admin@contoso.com destinationServiceName=Microsoft Exchange Online cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596b30200c204203a33a4765 cs2Label=uniqueServiceAppIds cs2=APPID_OUTLOOK cs3Label=relatedAudits cs3=1500196587034_a8673602-7e95-46d6-a1fe-c156c4709c5d cs4Label=policyIDs cs4=

2017-07-16T09:41:04.369Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|test-activity-policy2|3|externalId=596b34b10c204203a33a5240 start=1500198064369 end=1500198064369 msg=Activity policy ''test-activity-policy2'' was triggered by ''user2@test15-adallom.com'' suser=user2@test15-adallom.com destinationServiceName=Google cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596b34b10c204203a33a5240 cs2Label=uniqueServiceAppIds cs2=APPID_33626 cs3Label=relatedAudits cs3=1500197996117_fd71f265-1e46-4f04-b372-2e32ec874cd3 cs4Label=policyIDs cs4=
```

以下是 CEF 格式的示例


|CEF 字段名称  | 说明  |
|---------|---------|
|启动     | 通知的时间戳        |
|结束     | 通知的时间戳        |
|rt     | 通知的时间戳        |
|msg     | Office 365 云应用程序安全性门户中所示通知说明        |
|suser     | 通知使用者用户        |
|destinationServiceName     | 接收应用程序，如 Office 365、 SharePoint、 或 OneDrive 的通知        |
|csLabel     | 有所不同 （标签具有不同的含义）。通常，标签是一目了然，如 targetObjects。        |
|cs     | 对应于一个标签 （如警报标签示例根据目标用户） 的信息        |
  
## <a name="next-steps"></a>后续步骤

- [推出 Office 365 云应用安全后的利用率活动](utilization-activities-for-ocas.md)
    
- [查看并通知对其执行操作](review-office-365-cas-alerts.md)
    
- [若要简化管理您 IP 地址进行分组](group-your-ip-addresses-in-ocas.md)
    

