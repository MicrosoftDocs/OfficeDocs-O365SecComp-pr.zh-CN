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
ms.openlocfilehash: 0e185dec44bed7657bed126f70dfc64ffc135611
ms.sourcegitcommit: 9034809b6f308bedc3b8ddcca8242586b5c30f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/15/2019
ms.locfileid: "28015024"
---
# <a name="integrate-your-siem-server-with-office-365-cloud-app-security"></a><span data-ttu-id="df477-104">将 SIEM 服务器与 Office 365 云应用安全集成</span><span class="sxs-lookup"><span data-stu-id="df477-104">Integrate your SIEM server with Office 365 Cloud App Security</span></span>
  
|<span data-ttu-id="df477-105">评估 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="df477-105">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="df477-106">规划 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="df477-106">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="df477-107">部署 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="df477-107">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="df477-108">使用率 \*\*\*</span><span class="sxs-lookup"><span data-stu-id="df477-108">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="df477-109">启动评估</span><span class="sxs-lookup"><span data-stu-id="df477-109">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="df477-110">开始规划</span><span class="sxs-lookup"><span data-stu-id="df477-110">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |<span data-ttu-id="df477-111">在这里 ！</span><span class="sxs-lookup"><span data-stu-id="df477-111">You are here!</span></span>  <br/> [<span data-ttu-id="df477-112">后续步骤</span><span class="sxs-lookup"><span data-stu-id="df477-112">Next step</span></span>](utilization-activities-for-ocas.md) <br/> |[<span data-ttu-id="df477-113">开始利用</span><span class="sxs-lookup"><span data-stu-id="df477-113">Start utilizing</span></span>](utilization-activities-for-ocas.md) <br/> |
   
## <a name="overview-and-prerequisites"></a><span data-ttu-id="df477-114">概述和先决条件</span><span class="sxs-lookup"><span data-stu-id="df477-114">Overview and prerequisites</span></span>

<span data-ttu-id="df477-p102">您可以与要启用的通知的集中监控您安全信息和事件管理 (SIEM) 服务器集成[Office 365 云应用程序安全性](get-ready-for-office-365-cas.md)。这是将云服务的组织特别有用，本地服务器应用程序。将与 SIEM server 集成允许您以更好地保持通过自动化某些安全过程和关联之间的基于云的常规安全工作流，同时保护您的 Office 365 应用程序的安全团队和本地事件。</span><span class="sxs-lookup"><span data-stu-id="df477-p102">You can integrate [Office 365 Cloud App Security](get-ready-for-office-365-cas.md) with your security information and event management (SIEM) server to enable centralized monitoring of alerts. This is especially beneficial for organizations who are using cloud services and on-premises server applications. Integrating with a SIEM server allows your security team to better protect your Office 365 applications while maintaining your usual security workflow, by automating certain security procedures and correlating between cloud-based and on-premises events.</span></span>  
  
<span data-ttu-id="df477-p103">首先集成 SIEM 服务器与 Office 365 云应用程序安全性时, 从最近两天的通知转发到 SIEM 服务器，以及所有通知，然后从上 （基于您选择的任何筛选器）。此外，如果您禁用此功能长时间，当您启用它再次，它会将在过去两天的通知，然后所有通知此后转发。</span><span class="sxs-lookup"><span data-stu-id="df477-p103">When you first integrate your SIEM server with Office 365 Cloud App Security, alerts from the last two days are forwarded to the SIEM server, as well as all alerts from then on (based on any filters you select). Additionally, if you disable this feature for an extended period, when you enable it again, it will forward the past two days of alerts and then all alerts from then on.</span></span>

### <a name="siem-integration-architecture"></a><span data-ttu-id="df477-120">SIEM 集成体系结构</span><span class="sxs-lookup"><span data-stu-id="df477-120">SIEM integration architecture</span></span>

<span data-ttu-id="df477-p104">在贵组织的网络中设置的 SIEM 代理。SIEM 代理配置和部署时, 提取已配置的数据类型 （警报） 使用 Office 365 云应用程序安全 RESTful Api。然后通过端口 443 上加密 HTTPS 通道发送通信。</span><span class="sxs-lookup"><span data-stu-id="df477-p104">A SIEM agent is set up in your organization's network. When deployed and configured, the SIEM agent pulls the data types that were configured (alerts) using Office 365 Cloud App Security RESTful APIs. The traffic is then sent over an encrypted HTTPS channel on port 443.</span></span>
  
<span data-ttu-id="df477-124">时 SIEM 代理从 Office 365 云应用程序安全性检索数据，它将系统日志消息发送到本地 SIEM 服务器使用 （TCP 或与自定义端口的 UDP） 的安装过程中提供的网络配置。</span><span class="sxs-lookup"><span data-stu-id="df477-124">When a SIEM agent retrieves data from Office 365 Cloud App Security, it sends the Syslog messages to your local SIEM server using the network configurations that are provided during setup (TCP or UDP with a custom port).</span></span>

![SIEM 和云应用程序安全体系结构](media/siem-architecture.png)

### <a name="supported-siem-servers"></a><span data-ttu-id="df477-126">支持的 SIEM 服务器</span><span class="sxs-lookup"><span data-stu-id="df477-126">Supported SIEM servers</span></span>

<span data-ttu-id="df477-127">Office 365 云应用程序安全性当前支持以下 SIEM 服务器：</span><span class="sxs-lookup"><span data-stu-id="df477-127">Office 365 Cloud App Security currently supports the following SIEM servers:</span></span>
- <span data-ttu-id="df477-128">微焦点推荐 ArcSight</span><span class="sxs-lookup"><span data-stu-id="df477-128">Micro Focus ArcSight</span></span>
- <span data-ttu-id="df477-129">泛型 CEF</span><span class="sxs-lookup"><span data-stu-id="df477-129">Generic CEF</span></span>

### <a name="prerequisites"></a><span data-ttu-id="df477-130">先决条件</span><span class="sxs-lookup"><span data-stu-id="df477-130">Prerequisites</span></span>

- <span data-ttu-id="df477-p105">您必须是要执行本文中描述的任务的全局管理员或 security 管理员程序。请参阅[Permissions in Office 365 安全性&amp;合规性中心](permissions-in-the-security-and-compliance-center.md)</span><span class="sxs-lookup"><span data-stu-id="df477-p105">You must be a global administrator or security administrator to perform the tasks described in this article. See [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md)</span></span>

- <span data-ttu-id="df477-133">您必须为您的组织中具有[启用 Office 365 云应用程序安全性](turn-on-office-365-cas.md)。</span><span class="sxs-lookup"><span data-stu-id="df477-133">You must have [Office 365 Cloud App Security enabled](turn-on-office-365-cas.md) for your organization.</span></span>

- <span data-ttu-id="df477-134">[审核日志记录](turn-audit-log-search-on-or-off.md)必须打开 Office 365</span><span class="sxs-lookup"><span data-stu-id="df477-134">[Audit logging](turn-audit-log-search-on-or-off.md) must be turned on for Office 365</span></span>

- <span data-ttu-id="df477-135">您必须满足以下要求才能配置 SIEM 服务器集成的标准服务器：</span><span class="sxs-lookup"><span data-stu-id="df477-135">You must have a standard server that meets the following requirements in order to configure SIEM server integration:</span></span>
    - <span data-ttu-id="df477-136">操作系统： Windows 或 Linux （这可以是虚拟机）</span><span class="sxs-lookup"><span data-stu-id="df477-136">OS: Windows or Linux (this can be a virtual machine)</span></span>
    - <span data-ttu-id="df477-137">CPU: 2</span><span class="sxs-lookup"><span data-stu-id="df477-137">CPU: 2</span></span>
    - <span data-ttu-id="df477-138">磁盘空间： 20 GB</span><span class="sxs-lookup"><span data-stu-id="df477-138">Disk space: 20 GB</span></span>
    - <span data-ttu-id="df477-139">RAM: 2 GB</span><span class="sxs-lookup"><span data-stu-id="df477-139">RAM: 2 GB</span></span>
    - <span data-ttu-id="df477-140">安装[oracle Java 8](http://www.oracle.com/technetwork/java/javase/downloads/index.html)</span><span class="sxs-lookup"><span data-stu-id="df477-140">[Oracle Java 8](http://www.oracle.com/technetwork/java/javase/downloads/index.html) installed</span></span>
    - <span data-ttu-id="df477-141">[网络要求](https://docs.microsoft.com/cloud-app-security/network-requirements)中所述配置防火墙</span><span class="sxs-lookup"><span data-stu-id="df477-141">Firewall configured as described in [Network requirements](https://docs.microsoft.com/cloud-app-security/network-requirements)</span></span>

- <span data-ttu-id="df477-p106">您必须具有**远程系统日志主机**和**Syslot 端口号**的详细信息。网络管理员或安全管理员应该能够帮助您找到这些信息。</span><span class="sxs-lookup"><span data-stu-id="df477-p106">You must have details about your **Remote syslog host** and **Syslot port number**. A network administrator or security administrator should be able to help you locate that information.</span></span> 

- <span data-ttu-id="df477-144">您必须同意[软件许可条款](https://go.microsoft.com/fwlink/?linkid=862491)，若要下载[JAR 文件](https://go.microsoft.com/fwlink/?linkid=838596)需要将 SIEM 服务器集成。</span><span class="sxs-lookup"><span data-stu-id="df477-144">You must agree to [software license terms](https://go.microsoft.com/fwlink/?linkid=862491) to download the [JAR file](https://go.microsoft.com/fwlink/?linkid=838596) you'll need to integrate your SIEM server.</span></span>
 
## <a name="step-1-set-it-up-a-siem-agent-in-office-365-cloud-app-security"></a><span data-ttu-id="df477-145">步骤 1： 设置其 Office 365 云应用程序安全性的 SIEM 代理</span><span class="sxs-lookup"><span data-stu-id="df477-145">Step 1: Set it up a SIEM agent in Office 365 Cloud App Security</span></span>

1. <span data-ttu-id="df477-p107">转到[https://protection.office.com](https://protection.office.com)和 Office 365 中使用您的工作或学校帐户登录。(您将转到安全&amp;合规性中心。)</span><span class="sxs-lookup"><span data-stu-id="df477-p107">Go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account for Office 365. (This takes you to the Security &amp; Compliance Center.)</span></span> 
    
2. <span data-ttu-id="df477-148">转到**通知** \> **管理高级通知**。</span><span class="sxs-lookup"><span data-stu-id="df477-148">Go to **Alerts** \> **Manage advanced alerts**.</span></span>
    
3. <span data-ttu-id="df477-p108">选择**转到 Office 365 云应用程序安全性**。</span><span class="sxs-lookup"><span data-stu-id="df477-p108">Choose **Go to Office 365 Cloud App Security**. </span></span><br/>
    <span data-ttu-id="df477-150">![安全中&amp;合规性中心中，选择管理高级通知转到 Office 365 云应用程序安全性](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)</span><span class="sxs-lookup"><span data-stu-id="df477-150">![In the Security &amp; Compliance Center, choose Manage Advanced Alerts to go to Office 365 Cloud App Security](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)</span></span>
  
4. <span data-ttu-id="df477-151">单击**设置** \> **安全扩展**。</span><span class="sxs-lookup"><span data-stu-id="df477-151">Click **Settings** \> **Security extensions**.</span></span><br/>
<span data-ttu-id="df477-152">![选择设置 > 安全扩展](media/Settings-SecurityExtensions.png)</span><span class="sxs-lookup"><span data-stu-id="df477-152">![Choose Settings > Security extensions](media/Settings-SecurityExtensions.png)</span></span>

5. <span data-ttu-id="df477-153">选择**添加 SIEM 代理**。</span><span class="sxs-lookup"><span data-stu-id="df477-153">Choose **Add SIEM agent**.</span></span><br/><span data-ttu-id="df477-154">![选择添加 SIEM 代理。](media/SIEMAgents.png)</span><span class="sxs-lookup"><span data-stu-id="df477-154">![Choose Add SIEM agent.](media/SIEMAgents.png)</span></span>
    
6. <span data-ttu-id="df477-155">选择**启动向导**。</span><span class="sxs-lookup"><span data-stu-id="df477-155">Choose **Start wizard**.</span></span><br/><span data-ttu-id="df477-156">![获取帮助或启动向导](media/HelpOrWizard.png)</span><span class="sxs-lookup"><span data-stu-id="df477-156">![Get help or start the wizard](media/HelpOrWizard.png)</span></span> 
    
7. <span data-ttu-id="df477-p109">在**常规**步骤中，指定名称，并**选择 SIEM 格式**，并设置任何**高级设置**的格式与相关。然后选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="df477-p109">In the **General** step, specify a name, and **Select your SIEM format** and set any **Advanced settings** that are relevant to that format. Then choose **Next**.</span></span><br/><span data-ttu-id="df477-159">![指定名称和类型](media/ChooseAgentTypeAndName.png)</span><span class="sxs-lookup"><span data-stu-id="df477-159">![Specify a name and type](media/ChooseAgentTypeAndName.png)</span></span>
    
8. <span data-ttu-id="df477-p110">在**远程系统日志**步骤中，指定的 IP 地址或**远程 syslog 主机**和**Syslog 端口号**的主机名。选择 TCP 或 UDP 作为远程 Syslog 协议。（您可以使用网络管理员或安全管理员获取这些详细信息，如果您没有这些。）然后选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="df477-p110">In the **Remote Syslog** step, specify the IP address or hostname of the **Remote syslog host** and the **Syslog port number**. Select TCP or UDP as the Remote Syslog protocol. (You can work with your network administrator or security administrator to get these details if you don't have them.) Then choose **Next**.</span></span><br/><span data-ttu-id="df477-163">![指定远程系统日志的详细信息](media/ArcSightS1Syslog.png)</span><span class="sxs-lookup"><span data-stu-id="df477-163">![Specify Remote Syslog details](media/ArcSightS1Syslog.png)</span></span>
  
9. <span data-ttu-id="df477-164">在**数据类型**步骤中，执行以下内容，之一，然后单击**下一步**：</span><span class="sxs-lookup"><span data-stu-id="df477-164">In the **Data Types** step, do one of the following, and then click **Next**:</span></span>
    - <span data-ttu-id="df477-165">保留**所有通知**的默认设置</span><span class="sxs-lookup"><span data-stu-id="df477-165">Keep the default setting of **All Alerts**</span></span><br/><span data-ttu-id="df477-166">或者</span><span class="sxs-lookup"><span data-stu-id="df477-166">OR</span></span>
    - <span data-ttu-id="df477-p111">单击**所有通知**，，然后选择**特定的筛选器**。定义筛选器以选择要向 SIEM 服务器发送的通知的类型。</span><span class="sxs-lookup"><span data-stu-id="df477-p111">Click **All alerts**, and then choose **Specific filters**. Define filters to select the kinds of alerts you want to send to your SIEM server. </span></span><br/><span data-ttu-id="df477-169">![向导的步骤的数据类型](media/ArcSightS1ExportOptions.png)</span><span class="sxs-lookup"><span data-stu-id="df477-169">![Data Types step of the wizard](media/ArcSightS1ExportOptions.png)</span></span>
  
10. <span data-ttu-id="df477-170">在祝贺您屏幕上，复制标记并将其保存为更高版本。</span><span class="sxs-lookup"><span data-stu-id="df477-170">On the Congratulations screen, copy the token and save it for later.</span></span><br/>![SIEM 创建代理屏幕](media/SIEMAgentFinished.png) 

> [!IMPORTANT]
> <span data-ttu-id="df477-p112">此时，您已设置 Office 365 云应用程序安全性，SIEM 代理，但尚未完成您 SIEM 服务器集成。继续执行下一步继续 SIEM server 的集成。</span><span class="sxs-lookup"><span data-stu-id="df477-p112">At this point, you have set up a SIEM agent in Office 365 Cloud App Security, but your SIEM server integration is not yet finished. Proceed to the next step to continue your SIEM server integration.</span></span>

<span data-ttu-id="df477-p113">单击关闭和保留向导，在安全扩展屏幕上之后，您可以看到您在表中添加的 SIEM 代理。它连接更高版本之前，它将显示**创建**的状态。</span><span class="sxs-lookup"><span data-stu-id="df477-p113">After you click Close and leave the wizard, on the Security extensions screen, you can see the SIEM agent you added in the table. It will show a status of **Created** until it's connected later.</span></span>

![创建 SIEM 代理](media/SIEMAgentCreated.png)
    
## <a name="step-2-download-a-jar-file-and-run-it-on-your-siem-server"></a><span data-ttu-id="df477-177">步骤 2: JAR 文件下载并运行 SIEM 服务器上</span><span class="sxs-lookup"><span data-stu-id="df477-177">Step 2: Download a JAR file and run it on your SIEM server</span></span>

1. <span data-ttu-id="df477-p114">下载[Microsoft 云应用程序安全 SIEM 代理](https://go.microsoft.com/fwlink/?linkid=838596)并解压缩文件夹。（必须同意[软件许可条款](https://go.microsoft.com/fwlink/?linkid=862491)才能继续。）</span><span class="sxs-lookup"><span data-stu-id="df477-p114">Download the [Microsoft Cloud App Security SIEM Agent](https://go.microsoft.com/fwlink/?linkid=838596) and unzip the folder. (You must agree to [software license terms](https://go.microsoft.com/fwlink/?linkid=862491) in order to proceed.)</span></span> 
    
2. <span data-ttu-id="df477-180">从压缩文件夹中提取的.jar 文件并 SIEM 服务器上运行它。</span><span class="sxs-lookup"><span data-stu-id="df477-180">Extract the .jar file from the zipped folder and run it on your SIEM server.</span></span>
    
3. <span data-ttu-id="df477-181">在运行该文件之后, 运行以下命令： 命令：</span><span class="sxs-lookup"><span data-stu-id="df477-181">After running the file, run the following: command:</span></span><br/>
  ```
  java -jar mcas-siemagent-0.87.20-signed.jar [--logsDirectory DIRNAME] [--proxy ADDRESS[:PORT]] --token TOKEN
  ```
### <a name="important-notes"></a><span data-ttu-id="df477-182">重要说明</span><span class="sxs-lookup"><span data-stu-id="df477-182">Important notes</span></span>

- <span data-ttu-id="df477-183">文件名可能有所不同具体取决于 SIEM 代理的版本。</span><span class="sxs-lookup"><span data-stu-id="df477-183">The file name may differ depending on the version of the SIEM agent.</span></span> 

- <span data-ttu-id="df477-184">我们建议您在服务器安装过程中运行 SIEM 服务器上的 JAR 文件。</span><span class="sxs-lookup"><span data-stu-id="df477-184">We recommend that you run the JAR file on your SIEM server during server setup.</span></span>

    - <span data-ttu-id="df477-185">**Windows**： 运行作为计划任务，并确保配置任务**运行或不用户是否登录**和清除**如果运行超过停止任务**选项。</span><span class="sxs-lookup"><span data-stu-id="df477-185">**Windows**: Run as a scheduled task, making sure to configure the task to **Run whether the user is logged on or not** and clear the **Stop the task if it runs longer than** option.</span></span>

    - <span data-ttu-id="df477-186">**Linux**： 添加运行的命令与**&** 到`rc.local`文件。</span><span class="sxs-lookup"><span data-stu-id="df477-186">**Linux**: Add the run command with an **&** to the `rc.local` file.</span></span> <br/><span data-ttu-id="df477-187">示例：</span><span class="sxs-lookup"><span data-stu-id="df477-187">Example:</span></span><br/> 
    ```
    java -jar mcas-siemagent-0.87.20-signed.jar [--logsDirectory DIRNAME] [--proxy ADDRESS[:PORT]] --token TOKEN &
    ```

- <span data-ttu-id="df477-p115">中括号 [] 参数是可选的并应仅当相关。使用以下变量：</span><span class="sxs-lookup"><span data-stu-id="df477-p115">Parameters in brackets [] are optional, and should be used only if relevant. Use the following variables:</span></span>

    - <span data-ttu-id="df477-190">**DIRNAME**是您想要使用的本地代理调试日志目录的路径。</span><span class="sxs-lookup"><span data-stu-id="df477-190">**DIRNAME** is the path to the directory you want to use for local agent debug logs.</span></span>

    - <span data-ttu-id="df477-191">**地址 [: 端口]** 是代理服务器地址和服务器用于连接到 Internet 的端口。</span><span class="sxs-lookup"><span data-stu-id="df477-191">**ADDRESS[:PORT]** is the proxy server address and port that the server uses to connect to the Internet.</span></span>

    - <span data-ttu-id="df477-192">**令牌**是您在第一个过程中复制 SIEM 代理标记。</span><span class="sxs-lookup"><span data-stu-id="df477-192">**TOKEN** is the SIEM agent token you copied in the first procedure.</span></span>

    - <span data-ttu-id="df477-193">若要获取帮助，请键入`-h`。</span><span class="sxs-lookup"><span data-stu-id="df477-193">To get help, type `-h`.</span></span> 
  
## <a name="step-3-validate-that-the-siem-agent-is-working"></a><span data-ttu-id="df477-194">步骤 3： 验证 SIEM 代理工作</span><span class="sxs-lookup"><span data-stu-id="df477-194">Step 3: Validate that the SIEM agent is working</span></span>

1. <span data-ttu-id="df477-195">请确保在 Office 365 云应用程序安全性门户 SIEM 代理的状态不显示为**连接错误**或**已断开连接**，并且有任何代理通知。</span><span class="sxs-lookup"><span data-stu-id="df477-195">Make sure the status of the SIEM agent in the Office 365 Cloud App Security portal is not displayed as **Connection error** or **Disconnected** and that there are no agent notifications.</span></span><br/><span data-ttu-id="df477-196">例如，此处我们可以看到 SIEM 服务器连接：</span><span class="sxs-lookup"><span data-stu-id="df477-196">For example, here we can see the SIEM server is connected:</span></span><br/><span data-ttu-id="df477-197">![SIEM 服务器连接](media/siem-connected.png)</span><span class="sxs-lookup"><span data-stu-id="df477-197">![SIEM server connected](media/siem-connected.png)</span></span><br/><span data-ttu-id="df477-198">并在这里，我们可以看到 SIEM 服务器已断开连接：</span><span class="sxs-lookup"><span data-stu-id="df477-198">And here, we can see the SIEM server is disconnected:</span></span><br/><span data-ttu-id="df477-199">![未连接的 SIEM 服务器](media/siem-not-connected.png)</span><span class="sxs-lookup"><span data-stu-id="df477-199">![SIEM server not connected](media/siem-not-connected.png)</span></span> 
  
2. <span data-ttu-id="df477-200">在您的系统日志/SIEM 服务器，请确保您看到通知均已到达从 Office 365 云应用程序安全性。</span><span class="sxs-lookup"><span data-stu-id="df477-200">In your Syslog/SIEM server, make sure you see that alerts have arrived from Office 365 Cloud App Security.</span></span>
  
## <a name="what-the-logfiles-look-like"></a><span data-ttu-id="df477-201">日志文件表现形式是什么</span><span class="sxs-lookup"><span data-stu-id="df477-201">What the logfiles look like</span></span>

<span data-ttu-id="df477-202">下面是可能发送到 SIEM 服务器通知日志文件示例：</span><span class="sxs-lookup"><span data-stu-id="df477-202">Here's an alerts logfile example that might be sent to a SIEM server:</span></span>

```
2017-07-15T20:42:30.531Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|myPolicy|3|externalId=596a7e360c204203a335a3fb start=1500151350531 end=1500151350531 msg=Activity policy ''myPolicy'' was triggered by ''admin@box-contoso.com'' suser=admin@box-contoso.com destinationServiceName=Box cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596a7e360c204203a335a3fb cs2Label=uniqueServiceAppIds cs2=APPID_BOX cs3Label=relatedAudits cs3=1500151288183_acc891bf-33e1-424b-a021-0d4370789660 cs4Label=policyIDs cs4=59f0ab82f797fa0681e9b1c7

2017-07-16T09:36:26.550Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|test-activity-policy|3|externalId=596b339b0c204203a33a51ae start=1500197786550 end=1500197786550 msg=Activity policy ''test-activity-policy'' was triggered by ''user@contoso.com'' suser=user@contoso.com destinationServiceName=Salesforce cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596b339b0c204203a33a51ae cs2Label=uniqueServiceAppIds cs2=APPID_SALESFORCE cs3Label=relatedAudits cs3=1500197720691_b7f6317c-b8de-476a-bc8f-dfa570e00349 cs4Label=policyIDs cs4=

2017-07-16T09:17:03.361Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|test-activity-policy3|3|externalId=596b2fd70c204203a33a3eeb start=1500196623361 end=1500196623361 msg=Activity policy ''test-activity-policy3'' was triggered by ''admin@contoso.com'' suser=admin@contoso.com destinationServiceName=Office 365 cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596b2fd70c204203a33a3eeb cs2Label=uniqueServiceAppIds cs2=APPID_O365 cs3Label=relatedAudits cs3=1500196549157_a0e01f8a-e29a-43ae-8599-783c1c11597d cs4Label=policyIDs cs4=

2017-07-16T09:17:15.426Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|test-activity-policy|3|externalId=596b2fd70c204203a33a3eec start=1500196635426 end=1500196635426 msg=Activity policy ''test-activity-policy'' was triggered by ''admin@contoso.com'' suser=admin@contoso.com destinationServiceName=Microsoft Office 365 admin center cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596b2fd70c204203a33a3eec cs2Label=uniqueServiceAppIds cs2=APPID_O365_PORTAL cs3Label=relatedAudits cs3=1500196557398_3e102b20-d9fa-4f66-b550-8c7a403bb4d8 cs4Label=policyIDs cs4=59f0ab35f797fa9811e9b1c7

2017-07-16T09:17:46.290Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|test-activity-policy4|3|externalId=596b30200c204203a33a4765 start=1500196666290 end=1500196666290 msg=Activity policy ''test-activity-policy4'' was triggered by ''admin@contoso.com'' suser=admin@contoso.com destinationServiceName=Microsoft Exchange Online cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596b30200c204203a33a4765 cs2Label=uniqueServiceAppIds cs2=APPID_OUTLOOK cs3Label=relatedAudits cs3=1500196587034_a8673602-7e95-46d6-a1fe-c156c4709c5d cs4Label=policyIDs cs4=

2017-07-16T09:41:04.369Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|test-activity-policy2|3|externalId=596b34b10c204203a33a5240 start=1500198064369 end=1500198064369 msg=Activity policy ''test-activity-policy2'' was triggered by ''user2@test15-adallom.com'' suser=user2@test15-adallom.com destinationServiceName=Google cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596b34b10c204203a33a5240 cs2Label=uniqueServiceAppIds cs2=APPID_33626 cs3Label=relatedAudits cs3=1500197996117_fd71f265-1e46-4f04-b372-2e32ec874cd3 cs4Label=policyIDs cs4=
```

<span data-ttu-id="df477-203">下面是另一个示例中，这次 CEF 格式：</span><span class="sxs-lookup"><span data-stu-id="df477-203">And here's another sample, this time in CEF format:</span></span>


|<span data-ttu-id="df477-204">CEF 字段名称</span><span class="sxs-lookup"><span data-stu-id="df477-204">CEF field name</span></span>  | <span data-ttu-id="df477-205">说明</span><span class="sxs-lookup"><span data-stu-id="df477-205">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="df477-206">启动</span><span class="sxs-lookup"><span data-stu-id="df477-206">start</span></span>     | <span data-ttu-id="df477-207">通知的时间戳</span><span class="sxs-lookup"><span data-stu-id="df477-207">alert timestamp</span></span>        |
|<span data-ttu-id="df477-208">结束</span><span class="sxs-lookup"><span data-stu-id="df477-208">end</span></span>     | <span data-ttu-id="df477-209">通知的时间戳</span><span class="sxs-lookup"><span data-stu-id="df477-209">alert timestamp</span></span>        |
|<span data-ttu-id="df477-210">rt</span><span class="sxs-lookup"><span data-stu-id="df477-210">rt</span></span>     | <span data-ttu-id="df477-211">通知的时间戳</span><span class="sxs-lookup"><span data-stu-id="df477-211">alert timestamp</span></span>        |
|<span data-ttu-id="df477-212">msg</span><span class="sxs-lookup"><span data-stu-id="df477-212">msg</span></span>     | <span data-ttu-id="df477-213">Office 365 云应用程序安全性门户中所示通知说明</span><span class="sxs-lookup"><span data-stu-id="df477-213">alert description as shown in the Office 365 Cloud App Security portal</span></span>        |
|<span data-ttu-id="df477-214">suser</span><span class="sxs-lookup"><span data-stu-id="df477-214">suser</span></span>     | <span data-ttu-id="df477-215">通知使用者用户</span><span class="sxs-lookup"><span data-stu-id="df477-215">alert subject user</span></span>        |
|<span data-ttu-id="df477-216">destinationServiceName</span><span class="sxs-lookup"><span data-stu-id="df477-216">destinationServiceName</span></span>     | <span data-ttu-id="df477-217">接收应用程序，如 Office 365、 SharePoint、 或 OneDrive 的通知</span><span class="sxs-lookup"><span data-stu-id="df477-217">alert originating app, such as Office 365, SharePoint, or OneDrive</span></span>        |
|<span data-ttu-id="df477-218">csLabel</span><span class="sxs-lookup"><span data-stu-id="df477-218">csLabel</span></span>     | <span data-ttu-id="df477-p116">有所不同 （标签具有不同的含义）。通常，标签是一目了然，如 targetObjects。</span><span class="sxs-lookup"><span data-stu-id="df477-p116">Varies (labels have different meanings). Typically, labels are self-explanatory, like targetObjects.</span></span>        |
|<span data-ttu-id="df477-221">cs</span><span class="sxs-lookup"><span data-stu-id="df477-221">cs</span></span>     | <span data-ttu-id="df477-222">对应于一个标签 （如警报标签示例根据目标用户） 的信息</span><span class="sxs-lookup"><span data-stu-id="df477-222">Information corresponding to a label (such as the target user of an alert as per the label example)</span></span>        |

## <a name="additional-tasks-as-needed"></a><span data-ttu-id="df477-223">其他任务 （根据需要）</span><span class="sxs-lookup"><span data-stu-id="df477-223">Additional tasks (as needed)</span></span>

<span data-ttu-id="df477-p117">您已配置 SIEM 服务器并具有与 Office 365 云应用程序安全性集成后，您可能需要重新生成令牌、 编辑 SIEM 代理，或删除 SIEM 代理。以下各节介绍如何执行这些任务。</span><span class="sxs-lookup"><span data-stu-id="df477-p117">After you have configured your SIEM server and have integrated it with Office 365 Cloud App Security, you might need to regenerate a token, edit a SIEM agent, or delete a SIEM agent. The following sections describe how to perform these tasks.</span></span>

### <a name="regenerate-a-token"></a><span data-ttu-id="df477-226">重新生成令牌</span><span class="sxs-lookup"><span data-stu-id="df477-226">Regenerate a token</span></span>

<span data-ttu-id="df477-227">如果您丢失了您的令牌，您可以重新生成一个。</span><span class="sxs-lookup"><span data-stu-id="df477-227">If you lose your token, you can regenerate one.</span></span> 

1. <span data-ttu-id="df477-228">在 Office 365 云应用程序安全性门户中，选择**设置** > **安全扩展**。</span><span class="sxs-lookup"><span data-stu-id="df477-228">In the Office 365 Cloud App Security portal, choose **Settings** > **Security extensions**.</span></span>

2. <span data-ttu-id="df477-229">在表中，找到所在行的 SIEM 代理。</span><span class="sxs-lookup"><span data-stu-id="df477-229">In the table, locate the row for the SIEM agent.</span></span> 

3. <span data-ttu-id="df477-230">单击省略号，，然后选择**重新生成令牌**。</span><span class="sxs-lookup"><span data-stu-id="df477-230">Click the ellipses, and then choose **Regenerate token**.</span></span><br/><span data-ttu-id="df477-231">![通过单击省略号 SIEM 代理再生令牌](media/04de368a-b88e-4a9c-a830-58025cb98db6.png)</span><span class="sxs-lookup"><span data-stu-id="df477-231">![Regenerate a token by clicking the ellipsis for your SIEM agent](media/04de368a-b88e-4a9c-a830-58025cb98db6.png)</span></span>
  
### <a name="edit-a-siem-agent"></a><span data-ttu-id="df477-232">编辑 SIEM 代理</span><span class="sxs-lookup"><span data-stu-id="df477-232">Edit a SIEM agent</span></span>

1. <span data-ttu-id="df477-233">在 Office 365 云应用程序安全性门户中，选择**设置** > **安全扩展**。</span><span class="sxs-lookup"><span data-stu-id="df477-233">In the Office 365 Cloud App Security portal, choose **Settings** > **Security extensions**.</span></span>

2. <span data-ttu-id="df477-234">SIEM 代理中找到的行。</span><span class="sxs-lookup"><span data-stu-id="df477-234">Locate the row for the SIEM agent.</span></span> 

3. <span data-ttu-id="df477-p118">单击省略号，，，然后选择**编辑**。（如果您编辑 SIEM 代理，不需要重新运行.jar 文件; 它将自动更新。）</span><span class="sxs-lookup"><span data-stu-id="df477-p118">Click the ellipses, and then choose **Edit**. (If you edit the SIEM agent, you do not need to re-run the .jar file; it updates automatically.) </span></span><br/><span data-ttu-id="df477-237">![若要编辑 SIEM 代理，选择省略号，，，然后选择编辑。](media/96d0b362-3e0c-4dff-b2b4-d7af5b1bfb91.png)</span><span class="sxs-lookup"><span data-stu-id="df477-237">![To edit your SIEM agent, choose the ellipses, and then choose Edit.](media/96d0b362-3e0c-4dff-b2b4-d7af5b1bfb91.png)</span></span>
  
### <a name="delete-a-siem-agent"></a><span data-ttu-id="df477-238">删除 SIEM 代理</span><span class="sxs-lookup"><span data-stu-id="df477-238">Delete a SIEM agent</span></span>

1. <span data-ttu-id="df477-239">在 Office 365 云应用程序安全性门户中，选择**设置** > **安全扩展**。</span><span class="sxs-lookup"><span data-stu-id="df477-239">In the Office 365 Cloud App Security portal, choose **Settings** > **Security extensions**.</span></span>

2. <span data-ttu-id="df477-240">SIEM 代理中找到的行。</span><span class="sxs-lookup"><span data-stu-id="df477-240">Locate the row for the SIEM agent.</span></span> 

3. <span data-ttu-id="df477-241">单击省略号，，，然后选择**删除**。</span><span class="sxs-lookup"><span data-stu-id="df477-241">Click the ellipses, and then choose **Delete**.</span></span><br/><span data-ttu-id="df477-242">![若要删除的 SIEM 代理，选择省略号，，，然后选择删除。](media/540b5bdf-5574-4ecc-a7b0-92a499a387d7.png)</span><span class="sxs-lookup"><span data-stu-id="df477-242">![To delete a SIEM agent, choose the ellipses, and then choose Delete.](media/540b5bdf-5574-4ecc-a7b0-92a499a387d7.png)</span></span>

  
## <a name="next-steps"></a><span data-ttu-id="df477-243">后续步骤</span><span class="sxs-lookup"><span data-stu-id="df477-243">Next steps</span></span>

- [<span data-ttu-id="df477-244">推出 Office 365 云应用安全后的利用率活动</span><span class="sxs-lookup"><span data-stu-id="df477-244">Utilization activities after rolling out Office 365 Cloud App Security</span></span>](utilization-activities-for-ocas.md)
    
- [<span data-ttu-id="df477-245">查看并通知对其执行操作</span><span class="sxs-lookup"><span data-stu-id="df477-245">Review and take action on alerts</span></span>](review-office-365-cas-alerts.md)
    
- [<span data-ttu-id="df477-246">若要简化管理您 IP 地址进行分组</span><span class="sxs-lookup"><span data-stu-id="df477-246">Group your IP addresses to simplify management</span></span>](group-your-ip-addresses-in-ocas.md)
    

