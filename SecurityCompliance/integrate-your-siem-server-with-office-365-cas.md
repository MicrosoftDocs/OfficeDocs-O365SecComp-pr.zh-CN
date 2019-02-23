---
title: 将 SIEM 服务器与 Office 365 云应用安全集成
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: dd6d2417-49c4-4de6-9294-67fdabbf8532
description: 你可以将 SIEM 服务器与 Office 365 云应用安全集成。阅读本文, 了解其工作方式以及如何进行设置的概述。
ms.openlocfilehash: b4baeda3cb836c0b1aa528d29176bbf4321d1fe2
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30215871"
---
# <a name="integrate-your-siem-server-with-office-365-cloud-app-security"></a><span data-ttu-id="1d72f-104">将 SIEM 服务器与 Office 365 云应用安全集成</span><span class="sxs-lookup"><span data-stu-id="1d72f-104">Integrate your SIEM server with Office 365 Cloud App Security</span></span>
  
|<span data-ttu-id="1d72f-105">评估 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="1d72f-105">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="1d72f-106">规划 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="1d72f-106">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="1d72f-107">部署 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="1d72f-107">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="1d72f-108">利用率 \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="1d72f-108">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="1d72f-109">开始评估</span><span class="sxs-lookup"><span data-stu-id="1d72f-109">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="1d72f-110">开始规划</span><span class="sxs-lookup"><span data-stu-id="1d72f-110">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |<span data-ttu-id="1d72f-111">你在这里!</span><span class="sxs-lookup"><span data-stu-id="1d72f-111">You are here!</span></span>  <br/> [<span data-ttu-id="1d72f-112">后续步骤</span><span class="sxs-lookup"><span data-stu-id="1d72f-112">Next step</span></span>](utilization-activities-for-ocas.md) <br/> |[<span data-ttu-id="1d72f-113">开始利用</span><span class="sxs-lookup"><span data-stu-id="1d72f-113">Start utilizing</span></span>](utilization-activities-for-ocas.md) <br/> |
   
## <a name="overview-and-prerequisites"></a><span data-ttu-id="1d72f-114">概述和先决条件</span><span class="sxs-lookup"><span data-stu-id="1d72f-114">Overview and prerequisites</span></span>

<span data-ttu-id="1d72f-p102">您可以将[Office 365 云应用安全性](get-ready-for-office-365-cas.md)与安全信息和事件管理 (SIEM) 服务器集成, 以启用对警报的集中式监视。对于使用云服务和本地服务器应用程序的组织而言, 这一点尤其有用。通过与 SIEM 服务器集成, 您的安全团队可以在维护常规安全工作流的同时, 通过自动执行某些安全过程以及在基于云的和本地事件之间关联, 从而更好地保护 Office 365 应用程序。</span><span class="sxs-lookup"><span data-stu-id="1d72f-p102">You can integrate [Office 365 Cloud App Security](get-ready-for-office-365-cas.md) with your security information and event management (SIEM) server to enable centralized monitoring of alerts. This is especially beneficial for organizations who are using cloud services and on-premises server applications. Integrating with a SIEM server allows your security team to better protect your Office 365 applications while maintaining your usual security workflow, by automating certain security procedures and correlating between cloud-based and on-premises events.</span></span>  
  
<span data-ttu-id="1d72f-p103">当您首次将 SIEM 服务器与 Office 365 云应用程序集成在一起时, 来自最近两天的警报将被转发到 SIEM 服务器, 以及来自随后的所有警报 (基于您选择的任何筛选器)。此外, 如果您在较长的时间段内禁用此功能, 则再次启用它时, 它会将过去两天的通知转发给过去两天的通知, 然后在上转发所有警报。</span><span class="sxs-lookup"><span data-stu-id="1d72f-p103">When you first integrate your SIEM server with Office 365 Cloud App Security, alerts from the last two days are forwarded to the SIEM server, as well as all alerts from then on (based on any filters you select). Additionally, if you disable this feature for an extended period, when you enable it again, it will forward the past two days of alerts and then all alerts from then on.</span></span>

### <a name="siem-integration-architecture"></a><span data-ttu-id="1d72f-120">SIEM 集成体系结构</span><span class="sxs-lookup"><span data-stu-id="1d72f-120">SIEM integration architecture</span></span>

<span data-ttu-id="1d72f-p104">在组织的网络中设置 SIEM 代理。部署和配置后, SIEM 代理将使用 Office 365 云应用安全 RESTful api 提取已配置 (警报) 的数据类型。然后, 通过端口443上的加密 HTTPS 通道发送流量。</span><span class="sxs-lookup"><span data-stu-id="1d72f-p104">A SIEM agent is set up in your organization's network. When deployed and configured, the SIEM agent pulls the data types that were configured (alerts) using Office 365 Cloud App Security RESTful APIs. The traffic is then sent over an encrypted HTTPS channel on port 443.</span></span>
  
<span data-ttu-id="1d72f-124">当 SIEM 代理从 Office 365 云应用安全中检索数据时, 会使用在安装过程中提供的网络配置 (TCP 或 UDP 具有自定义端口) 将 Syslog 邮件发送到本地 SIEM 服务器。</span><span class="sxs-lookup"><span data-stu-id="1d72f-124">When a SIEM agent retrieves data from Office 365 Cloud App Security, it sends the Syslog messages to your local SIEM server using the network configurations that are provided during setup (TCP or UDP with a custom port).</span></span>

![SIEM 和云应用安全体系结构](media/siem-architecture.png)

### <a name="supported-siem-servers"></a><span data-ttu-id="1d72f-126">支持的 SIEM 服务器</span><span class="sxs-lookup"><span data-stu-id="1d72f-126">Supported SIEM servers</span></span>

<span data-ttu-id="1d72f-127">Office 365 云应用安全目前支持以下 SIEM 服务器:</span><span class="sxs-lookup"><span data-stu-id="1d72f-127">Office 365 Cloud App Security currently supports the following SIEM servers:</span></span>
- <span data-ttu-id="1d72f-128">微焦点 ArcSight</span><span class="sxs-lookup"><span data-stu-id="1d72f-128">Micro Focus ArcSight</span></span>
- <span data-ttu-id="1d72f-129">泛型 CEF</span><span class="sxs-lookup"><span data-stu-id="1d72f-129">Generic CEF</span></span>

### <a name="prerequisites"></a><span data-ttu-id="1d72f-130">先决条件</span><span class="sxs-lookup"><span data-stu-id="1d72f-130">Prerequisites</span></span>

- <span data-ttu-id="1d72f-p105">您必须是全局管理员或安全管理员才能执行本文中所述的任务。查看[Office 365 安全&amp;合规中心中的权限](permissions-in-the-security-and-compliance-center.md)</span><span class="sxs-lookup"><span data-stu-id="1d72f-p105">You must be a global administrator or security administrator to perform the tasks described in this article. See [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md)</span></span>

- <span data-ttu-id="1d72f-133">您必须为您的组织[启用 Office 365 云应用安全性](turn-on-office-365-cas.md)。</span><span class="sxs-lookup"><span data-stu-id="1d72f-133">You must have [Office 365 Cloud App Security enabled](turn-on-office-365-cas.md) for your organization.</span></span>

- <span data-ttu-id="1d72f-134">必须为 Office 365 启用[审核日志记录](turn-audit-log-search-on-or-off.md)</span><span class="sxs-lookup"><span data-stu-id="1d72f-134">[Audit logging](turn-audit-log-search-on-or-off.md) must be turned on for Office 365</span></span>

- <span data-ttu-id="1d72f-135">您必须具有满足以下要求的标准服务器, 才能配置 SIEM 服务器集成:</span><span class="sxs-lookup"><span data-stu-id="1d72f-135">You must have a standard server that meets the following requirements in order to configure SIEM server integration:</span></span>
    - <span data-ttu-id="1d72f-136">操作系统: Windows 或 Linux (这可以是虚拟机)</span><span class="sxs-lookup"><span data-stu-id="1d72f-136">OS: Windows or Linux (this can be a virtual machine)</span></span>
    - <span data-ttu-id="1d72f-137">CPU: 2</span><span class="sxs-lookup"><span data-stu-id="1d72f-137">CPU: 2</span></span>
    - <span data-ttu-id="1d72f-138">磁盘空间:20 GB</span><span class="sxs-lookup"><span data-stu-id="1d72f-138">Disk space: 20 GB</span></span>
    - <span data-ttu-id="1d72f-139">RAM: 2 GB</span><span class="sxs-lookup"><span data-stu-id="1d72f-139">RAM: 2 GB</span></span>
    - <span data-ttu-id="1d72f-140">已安装[Oracle Java 8](http://www.oracle.com/technetwork/java/javase/downloads/index.html)</span><span class="sxs-lookup"><span data-stu-id="1d72f-140">[Oracle Java 8](http://www.oracle.com/technetwork/java/javase/downloads/index.html) installed</span></span>
    - <span data-ttu-id="1d72f-141">按照[网络要求](https://docs.microsoft.com/cloud-app-security/network-requirements)中所述配置的防火墙</span><span class="sxs-lookup"><span data-stu-id="1d72f-141">Firewall configured as described in [Network requirements](https://docs.microsoft.com/cloud-app-security/network-requirements)</span></span>

- <span data-ttu-id="1d72f-p106">您必须具有有关**远程 syslog 主机**和**Syslot 端口号**的详细信息。网络管理员或安全管理员应能够帮助您找到该信息。</span><span class="sxs-lookup"><span data-stu-id="1d72f-p106">You must have details about your **Remote syslog host** and **Syslot port number**. A network administrator or security administrator should be able to help you locate that information.</span></span> 

- <span data-ttu-id="1d72f-144">您必须同意[软件许可条款](https://go.microsoft.com/fwlink/?linkid=862491), 才能下载集成您的 SIEM 服务器所需的[JAR 文件](https://go.microsoft.com/fwlink/?linkid=838596)。</span><span class="sxs-lookup"><span data-stu-id="1d72f-144">You must agree to [software license terms](https://go.microsoft.com/fwlink/?linkid=862491) to download the [JAR file](https://go.microsoft.com/fwlink/?linkid=838596) you'll need to integrate your SIEM server.</span></span>
 
## <a name="step-1-set-it-up-a-siem-agent-in-office-365-cloud-app-security"></a><span data-ttu-id="1d72f-145">步骤 1: 在 Office 365 Cloud App Security 中将其设置为 SIEM 代理</span><span class="sxs-lookup"><span data-stu-id="1d72f-145">Step 1: Set it up a SIEM agent in Office 365 Cloud App Security</span></span>

1. <span data-ttu-id="1d72f-146">转到云应用安全门户 ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) 并登录。</span><span class="sxs-lookup"><span data-stu-id="1d72f-146">Go to the Cloud App Security portal ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) and sign in.</span></span>
  
2. <span data-ttu-id="1d72f-147">单击 "**设置** \> **安全扩展**", 然后选择 "SIEM 代理"。</span><span class="sxs-lookup"><span data-stu-id="1d72f-147">Click **Settings** \> **Security extensions**, and then choose SIEM agents.</span></span><br/>
<span data-ttu-id="1d72f-148">![选择 "设置" > 安全扩展](media/Settings-SecurityExtensions.png)</span><span class="sxs-lookup"><span data-stu-id="1d72f-148">![Choose Settings > Security extensions](media/Settings-SecurityExtensions.png)</span></span>

3. <span data-ttu-id="1d72f-149">选择 "**添加 SIEM 代理**"。</span><span class="sxs-lookup"><span data-stu-id="1d72f-149">Choose **Add SIEM agent**.</span></span><br/><span data-ttu-id="1d72f-150">![选择 "添加 SIEM 代理"。](media/SIEMAgents.png)</span><span class="sxs-lookup"><span data-stu-id="1d72f-150">![Choose Add SIEM agent.](media/SIEMAgents.png)</span></span>
    
4. <span data-ttu-id="1d72f-151">选择 "**启动向导**"。</span><span class="sxs-lookup"><span data-stu-id="1d72f-151">Choose **Start wizard**.</span></span><br/><span data-ttu-id="1d72f-152">![获取帮助或启动向导](media/HelpOrWizard.png)</span><span class="sxs-lookup"><span data-stu-id="1d72f-152">![Get help or start the wizard](media/HelpOrWizard.png)</span></span> 
    
5. <span data-ttu-id="1d72f-p107">在 "**常规**" 步骤中, 指定一个名称, 然后**选择您的 SIEM 格式**并设置与该格式相关的任何**高级设置**。然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="1d72f-p107">In the **General** step, specify a name, and **Select your SIEM format** and set any **Advanced settings** that are relevant to that format. Then choose **Next**.</span></span><br/><span data-ttu-id="1d72f-155">![指定名称和类型](media/ChooseAgentTypeAndName.png)</span><span class="sxs-lookup"><span data-stu-id="1d72f-155">![Specify a name and type](media/ChooseAgentTypeAndName.png)</span></span>
    
6. <span data-ttu-id="1d72f-p108">在**远程 syslog**步骤中, 指定**远程 syslog 主机**的 IP 地址或主机名和**Syslog 端口号**。选择 "TCP" 或 "UDP" 作为远程 Syslog 协议。(如果您没有这些详细信息, 则可以与网络管理员或安全管理员合作获取这些详细信息。)然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="1d72f-p108">In the **Remote Syslog** step, specify the IP address or hostname of the **Remote syslog host** and the **Syslog port number**. Select TCP or UDP as the Remote Syslog protocol. (You can work with your network administrator or security administrator to get these details if you don't have them.) Then choose **Next**.</span></span><br/><span data-ttu-id="1d72f-159">![指定远程 Syslog 详细信息](media/ArcSightS1Syslog.png)</span><span class="sxs-lookup"><span data-stu-id="1d72f-159">![Specify Remote Syslog details](media/ArcSightS1Syslog.png)</span></span>
  
7. <span data-ttu-id="1d72f-160">在 "**数据类型**" 步骤中, 执行下列操作之一, 然后单击 "**下一步**":</span><span class="sxs-lookup"><span data-stu-id="1d72f-160">In the **Data Types** step, do one of the following, and then click **Next**:</span></span>
    - <span data-ttu-id="1d72f-161">保留**所有通知**的默认设置</span><span class="sxs-lookup"><span data-stu-id="1d72f-161">Keep the default setting of **All Alerts**</span></span><br/><span data-ttu-id="1d72f-162">或者</span><span class="sxs-lookup"><span data-stu-id="1d72f-162">OR</span></span>
    - <span data-ttu-id="1d72f-p109">单击 "**所有通知**", 然后选择 "**特定筛选器**"。定义筛选器以选择要发送到 SIEM 服务器的警报类型。</span><span class="sxs-lookup"><span data-stu-id="1d72f-p109">Click **All alerts**, and then choose **Specific filters**. Define filters to select the kinds of alerts you want to send to your SIEM server. </span></span><br/><span data-ttu-id="1d72f-165">![向导的数据类型步骤](media/ArcSightS1ExportOptions.png)</span><span class="sxs-lookup"><span data-stu-id="1d72f-165">![Data Types step of the wizard](media/ArcSightS1ExportOptions.png)</span></span>
  
8. <span data-ttu-id="1d72f-166">在祝贺屏幕上, 复制令牌并将其保存到稍后。</span><span class="sxs-lookup"><span data-stu-id="1d72f-166">On the Congratulations screen, copy the token and save it for later.</span></span><br/>![SIEM 代理创建屏幕](media/SIEMAgentFinished.png) 

> [!IMPORTANT]
> <span data-ttu-id="1d72f-p110">此时, 您已在 Office 365 Cloud App Security 中设置了 SIEM 代理, 但您的 SIEM 服务器集成尚未完成。继续执行下一步, 以继续进行 SIEM 服务器集成。</span><span class="sxs-lookup"><span data-stu-id="1d72f-p110">At this point, you have set up a SIEM agent in Office 365 Cloud App Security, but your SIEM server integration is not yet finished. Proceed to the next step to continue your SIEM server integration.</span></span>

<span data-ttu-id="1d72f-p111">单击 "关闭" 并退出向导后, 在 "安全扩展" 屏幕上, 可以看到您在表中添加的 SIEM 代理。它将显示 "已**创建**" 状态, 直到稍后连接。</span><span class="sxs-lookup"><span data-stu-id="1d72f-p111">After you click Close and leave the wizard, on the Security extensions screen, you can see the SIEM agent you added in the table. It will show a status of **Created** until it's connected later.</span></span>

![创建的 SIEM 代理](media/SIEMAgentCreated.png)
    
## <a name="step-2-download-a-jar-file-and-run-it-on-your-siem-server"></a><span data-ttu-id="1d72f-173">步骤 2: 下载 JAR 文件并在您的 SIEM 服务器上运行它</span><span class="sxs-lookup"><span data-stu-id="1d72f-173">Step 2: Download a JAR file and run it on your SIEM server</span></span>

1. <span data-ttu-id="1d72f-p112">下载[Microsoft 云应用安全 SIEM 代理](https://go.microsoft.com/fwlink/?linkid=838596)并解压缩该文件夹。(您必须同意[软件许可条款](https://go.microsoft.com/fwlink/?linkid=862491)才能继续。)</span><span class="sxs-lookup"><span data-stu-id="1d72f-p112">Download the [Microsoft Cloud App Security SIEM Agent](https://go.microsoft.com/fwlink/?linkid=838596) and unzip the folder. (You must agree to [software license terms](https://go.microsoft.com/fwlink/?linkid=862491) in order to proceed.)</span></span> 
    
2. <span data-ttu-id="1d72f-176">从压缩文件夹中提取 .jar 文件, 并在 SIEM 服务器上运行该文件。</span><span class="sxs-lookup"><span data-stu-id="1d72f-176">Extract the .jar file from the zipped folder and run it on your SIEM server.</span></span>
    
3. <span data-ttu-id="1d72f-177">运行文件后, 运行以下命令:</span><span class="sxs-lookup"><span data-stu-id="1d72f-177">After running the file, run the following: command:</span></span><br/>
  ```
  java -jar mcas-siemagent-0.87.20-signed.jar [--logsDirectory DIRNAME] [--proxy ADDRESS[:PORT]] --token TOKEN
  ```
### <a name="important-notes"></a><span data-ttu-id="1d72f-178">重要说明</span><span class="sxs-lookup"><span data-stu-id="1d72f-178">Important notes</span></span>

- <span data-ttu-id="1d72f-179">文件名可能因 SIEM 代理的版本而异。</span><span class="sxs-lookup"><span data-stu-id="1d72f-179">The file name may differ depending on the version of the SIEM agent.</span></span> 

- <span data-ttu-id="1d72f-180">建议您在服务器安装过程中, 在 SIEM 服务器上运行 JAR 文件。</span><span class="sxs-lookup"><span data-stu-id="1d72f-180">We recommend that you run the JAR file on your SIEM server during server setup.</span></span>

    - <span data-ttu-id="1d72f-181">**Windows**: 作为计划任务运行, 确保将任务配置为**无论用户是否登录都要运行**, 并清除 "**如果运行时间超过以下时间, 则停止任务**" 选项。</span><span class="sxs-lookup"><span data-stu-id="1d72f-181">**Windows**: Run as a scheduled task, making sure to configure the task to **Run whether the user is logged on or not** and clear the **Stop the task if it runs longer than** option.</span></span>

    - <span data-ttu-id="1d72f-182">**Linux**: 将 "运行" 命令添加**&** 到`rc.local`文件中。</span><span class="sxs-lookup"><span data-stu-id="1d72f-182">**Linux**: Add the run command with an **&** to the `rc.local` file.</span></span> <br/><span data-ttu-id="1d72f-183">示例：</span><span class="sxs-lookup"><span data-stu-id="1d72f-183">Example:</span></span><br/> 
    ```
    java -jar mcas-siemagent-0.87.20-signed.jar [--logsDirectory DIRNAME] [--proxy ADDRESS[:PORT]] --token TOKEN &
    ```

- <span data-ttu-id="1d72f-p113">括号 [] 中的参数是可选的, 应仅在相关时使用。使用以下变量:</span><span class="sxs-lookup"><span data-stu-id="1d72f-p113">Parameters in brackets [] are optional, and should be used only if relevant. Use the following variables:</span></span>

    - <span data-ttu-id="1d72f-186">**DIRNAME**是要用于本地代理调试日志的目录的路径。</span><span class="sxs-lookup"><span data-stu-id="1d72f-186">**DIRNAME** is the path to the directory you want to use for local agent debug logs.</span></span>

    - <span data-ttu-id="1d72f-187">**ADDRESS [:P ort]** 是服务器连接到 Internet 时使用的代理服务器地址和端口。</span><span class="sxs-lookup"><span data-stu-id="1d72f-187">**ADDRESS[:PORT]** is the proxy server address and port that the server uses to connect to the Internet.</span></span>

    - <span data-ttu-id="1d72f-188">**令牌**是您在第一个过程中复制的 SIEM 代理令牌。</span><span class="sxs-lookup"><span data-stu-id="1d72f-188">**TOKEN** is the SIEM agent token you copied in the first procedure.</span></span>

    - <span data-ttu-id="1d72f-189">若要获取帮助, `-h`请键入。</span><span class="sxs-lookup"><span data-stu-id="1d72f-189">To get help, type `-h`.</span></span> 
  
## <a name="step-3-validate-that-the-siem-agent-is-working"></a><span data-ttu-id="1d72f-190">步骤 3: 验证 SIEM 代理是否正在运行</span><span class="sxs-lookup"><span data-stu-id="1d72f-190">Step 3: Validate that the SIEM agent is working</span></span>

1. <span data-ttu-id="1d72f-191">请确保 Office 365 云应用安全门户中的 SIEM 代理的状态不显示为 "**连接错误**" 或 "已**断开**连接", 并且没有代理通知。</span><span class="sxs-lookup"><span data-stu-id="1d72f-191">Make sure the status of the SIEM agent in the Office 365 Cloud App Security portal is not displayed as **Connection error** or **Disconnected** and that there are no agent notifications.</span></span><br/><span data-ttu-id="1d72f-192">例如, 在这里, 我们可以看到已连接的 SIEM 服务器:</span><span class="sxs-lookup"><span data-stu-id="1d72f-192">For example, here we can see the SIEM server is connected:</span></span><br/><span data-ttu-id="1d72f-193">![连接的 SIEM 服务器](media/siem-connected.png)</span><span class="sxs-lookup"><span data-stu-id="1d72f-193">![SIEM server connected](media/siem-connected.png)</span></span><br/><span data-ttu-id="1d72f-194">在这里, 我们可以看到已断开的 SIEM 服务器:</span><span class="sxs-lookup"><span data-stu-id="1d72f-194">And here, we can see the SIEM server is disconnected:</span></span><br/><span data-ttu-id="1d72f-195">![未连接的 SIEM 服务器](media/siem-not-connected.png)</span><span class="sxs-lookup"><span data-stu-id="1d72f-195">![SIEM server not connected](media/siem-not-connected.png)</span></span> 
  
2. <span data-ttu-id="1d72f-196">在 Syslog/SIEM 服务器中, 请确保您看到 "Office 365 云应用安全" 已到达通知。</span><span class="sxs-lookup"><span data-stu-id="1d72f-196">In your Syslog/SIEM server, make sure you see that alerts have arrived from Office 365 Cloud App Security.</span></span>
  
## <a name="what-the-logfiles-look-like"></a><span data-ttu-id="1d72f-197">日志的外观</span><span class="sxs-lookup"><span data-stu-id="1d72f-197">What the logfiles look like</span></span>

<span data-ttu-id="1d72f-198">以下是可能发送到 SIEM 服务器的警报日志文件示例:</span><span class="sxs-lookup"><span data-stu-id="1d72f-198">Here's an alerts logfile example that might be sent to a SIEM server:</span></span>

```
2017-07-15T20:42:30.531Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|myPolicy|3|externalId=596a7e360c204203a335a3fb start=1500151350531 end=1500151350531 msg=Activity policy ''myPolicy'' was triggered by ''admin@box-contoso.com'' suser=admin@box-contoso.com destinationServiceName=Box cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596a7e360c204203a335a3fb cs2Label=uniqueServiceAppIds cs2=APPID_BOX cs3Label=relatedAudits cs3=1500151288183_acc891bf-33e1-424b-a021-0d4370789660 cs4Label=policyIDs cs4=59f0ab82f797fa0681e9b1c7

2017-07-16T09:36:26.550Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|test-activity-policy|3|externalId=596b339b0c204203a33a51ae start=1500197786550 end=1500197786550 msg=Activity policy ''test-activity-policy'' was triggered by ''user@contoso.com'' suser=user@contoso.com destinationServiceName=Salesforce cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596b339b0c204203a33a51ae cs2Label=uniqueServiceAppIds cs2=APPID_SALESFORCE cs3Label=relatedAudits cs3=1500197720691_b7f6317c-b8de-476a-bc8f-dfa570e00349 cs4Label=policyIDs cs4=

2017-07-16T09:17:03.361Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|test-activity-policy3|3|externalId=596b2fd70c204203a33a3eeb start=1500196623361 end=1500196623361 msg=Activity policy ''test-activity-policy3'' was triggered by ''admin@contoso.com'' suser=admin@contoso.com destinationServiceName=Office 365 cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596b2fd70c204203a33a3eeb cs2Label=uniqueServiceAppIds cs2=APPID_O365 cs3Label=relatedAudits cs3=1500196549157_a0e01f8a-e29a-43ae-8599-783c1c11597d cs4Label=policyIDs cs4=

2017-07-16T09:17:15.426Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|test-activity-policy|3|externalId=596b2fd70c204203a33a3eec start=1500196635426 end=1500196635426 msg=Activity policy ''test-activity-policy'' was triggered by ''admin@contoso.com'' suser=admin@contoso.com destinationServiceName=Microsoft Office 365 admin center cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596b2fd70c204203a33a3eec cs2Label=uniqueServiceAppIds cs2=APPID_O365_PORTAL cs3Label=relatedAudits cs3=1500196557398_3e102b20-d9fa-4f66-b550-8c7a403bb4d8 cs4Label=policyIDs cs4=59f0ab35f797fa9811e9b1c7

2017-07-16T09:17:46.290Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|test-activity-policy4|3|externalId=596b30200c204203a33a4765 start=1500196666290 end=1500196666290 msg=Activity policy ''test-activity-policy4'' was triggered by ''admin@contoso.com'' suser=admin@contoso.com destinationServiceName=Microsoft Exchange Online cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596b30200c204203a33a4765 cs2Label=uniqueServiceAppIds cs2=APPID_OUTLOOK cs3Label=relatedAudits cs3=1500196587034_a8673602-7e95-46d6-a1fe-c156c4709c5d cs4Label=policyIDs cs4=

2017-07-16T09:41:04.369Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|test-activity-policy2|3|externalId=596b34b10c204203a33a5240 start=1500198064369 end=1500198064369 msg=Activity policy ''test-activity-policy2'' was triggered by ''user2@test15-adallom.com'' suser=user2@test15-adallom.com destinationServiceName=Google cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596b34b10c204203a33a5240 cs2Label=uniqueServiceAppIds cs2=APPID_33626 cs3Label=relatedAudits cs3=1500197996117_fd71f265-1e46-4f04-b372-2e32ec874cd3 cs4Label=policyIDs cs4=
```

<span data-ttu-id="1d72f-199">下面是另一个示例, 这一次采用 CEF 格式:</span><span class="sxs-lookup"><span data-stu-id="1d72f-199">And here's another sample, this time in CEF format:</span></span>


|<span data-ttu-id="1d72f-200">CEF 字段名称</span><span class="sxs-lookup"><span data-stu-id="1d72f-200">CEF field name</span></span>  | <span data-ttu-id="1d72f-201">说明</span><span class="sxs-lookup"><span data-stu-id="1d72f-201">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="1d72f-202">起步</span><span class="sxs-lookup"><span data-stu-id="1d72f-202">start</span></span>     | <span data-ttu-id="1d72f-203">警报时间戳</span><span class="sxs-lookup"><span data-stu-id="1d72f-203">alert timestamp</span></span>        |
|<span data-ttu-id="1d72f-204">停止</span><span class="sxs-lookup"><span data-stu-id="1d72f-204">end</span></span>     | <span data-ttu-id="1d72f-205">警报时间戳</span><span class="sxs-lookup"><span data-stu-id="1d72f-205">alert timestamp</span></span>        |
|<span data-ttu-id="1d72f-206">rt</span><span class="sxs-lookup"><span data-stu-id="1d72f-206">rt</span></span>     | <span data-ttu-id="1d72f-207">警报时间戳</span><span class="sxs-lookup"><span data-stu-id="1d72f-207">alert timestamp</span></span>        |
|<span data-ttu-id="1d72f-208">msg</span><span class="sxs-lookup"><span data-stu-id="1d72f-208">msg</span></span>     | <span data-ttu-id="1d72f-209">Office 365 云应用安全门户中所示的警报说明</span><span class="sxs-lookup"><span data-stu-id="1d72f-209">alert description as shown in the Office 365 Cloud App Security portal</span></span>        |
|<span data-ttu-id="1d72f-210">suser</span><span class="sxs-lookup"><span data-stu-id="1d72f-210">suser</span></span>     | <span data-ttu-id="1d72f-211">通知主题用户</span><span class="sxs-lookup"><span data-stu-id="1d72f-211">alert subject user</span></span>        |
|<span data-ttu-id="1d72f-212">destinationServiceName</span><span class="sxs-lookup"><span data-stu-id="1d72f-212">destinationServiceName</span></span>     | <span data-ttu-id="1d72f-213">通知源应用程序 (如 Office 365、SharePoint 或 OneDrive)</span><span class="sxs-lookup"><span data-stu-id="1d72f-213">alert originating app, such as Office 365, SharePoint, or OneDrive</span></span>        |
|<span data-ttu-id="1d72f-214">csLabel</span><span class="sxs-lookup"><span data-stu-id="1d72f-214">csLabel</span></span>     | <span data-ttu-id="1d72f-p114">变化 (标签具有不同的含义)。通常情况下, 标签是一目了然的, 如 targetObjects。</span><span class="sxs-lookup"><span data-stu-id="1d72f-p114">Varies (labels have different meanings). Typically, labels are self-explanatory, like targetObjects.</span></span>        |
|<span data-ttu-id="1d72f-217">cs</span><span class="sxs-lookup"><span data-stu-id="1d72f-217">cs</span></span>     | <span data-ttu-id="1d72f-218">与标签对应的信息 (如警报的目标用户, 按标签示例)</span><span class="sxs-lookup"><span data-stu-id="1d72f-218">Information corresponding to a label (such as the target user of an alert as per the label example)</span></span>        |

## <a name="additional-tasks-as-needed"></a><span data-ttu-id="1d72f-219">其他任务 (根据需要)</span><span class="sxs-lookup"><span data-stu-id="1d72f-219">Additional tasks (as needed)</span></span>

<span data-ttu-id="1d72f-p115">配置 SIEM 服务器并将其与 Office 365 云应用安全性集成后, 您可能需要重新生成令牌、编辑 SIEM 代理或删除 SIEM 代理。以下各节介绍如何执行这些任务。</span><span class="sxs-lookup"><span data-stu-id="1d72f-p115">After you have configured your SIEM server and have integrated it with Office 365 Cloud App Security, you might need to regenerate a token, edit a SIEM agent, or delete a SIEM agent. The following sections describe how to perform these tasks.</span></span>

### <a name="regenerate-a-token"></a><span data-ttu-id="1d72f-222">重新生成令牌</span><span class="sxs-lookup"><span data-stu-id="1d72f-222">Regenerate a token</span></span>

<span data-ttu-id="1d72f-223">如果你丢失了令牌, 你可以重新生成一个。</span><span class="sxs-lookup"><span data-stu-id="1d72f-223">If you lose your token, you can regenerate one.</span></span> 

1. <span data-ttu-id="1d72f-224">在 Office 365 云应用安全门户[https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)() 中, 选择 "**设置** > **安全扩展**"。</span><span class="sxs-lookup"><span data-stu-id="1d72f-224">In the Office 365 Cloud App Security portal ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)), choose **Settings** > **Security extensions**.</span></span>

2. <span data-ttu-id="1d72f-225">在表中, 找到 SIEM 代理对应的行。</span><span class="sxs-lookup"><span data-stu-id="1d72f-225">In the table, locate the row for the SIEM agent.</span></span> 

3. <span data-ttu-id="1d72f-226">单击省略号, 然后选择 "**重新生成令牌**"。</span><span class="sxs-lookup"><span data-stu-id="1d72f-226">Click the ellipses, and then choose **Regenerate token**.</span></span><br/><span data-ttu-id="1d72f-227">![通过单击 SIEM 代理的省略号重新生成令牌](media/04de368a-b88e-4a9c-a830-58025cb98db6.png)</span><span class="sxs-lookup"><span data-stu-id="1d72f-227">![Regenerate a token by clicking the ellipsis for your SIEM agent](media/04de368a-b88e-4a9c-a830-58025cb98db6.png)</span></span>
  
### <a name="edit-a-siem-agent"></a><span data-ttu-id="1d72f-228">编辑 SIEM 代理</span><span class="sxs-lookup"><span data-stu-id="1d72f-228">Edit a SIEM agent</span></span>

1. <span data-ttu-id="1d72f-229">在 Office 365 云应用安全门户[https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)() 中, 选择 "**设置** > **安全扩展**"。</span><span class="sxs-lookup"><span data-stu-id="1d72f-229">In the Office 365 Cloud App Security portal ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)), choose **Settings** > **Security extensions**.</span></span>

2. <span data-ttu-id="1d72f-230">找到 SIEM 代理的行。</span><span class="sxs-lookup"><span data-stu-id="1d72f-230">Locate the row for the SIEM agent.</span></span> 

3. <span data-ttu-id="1d72f-p116">单击省略号, 然后选择 "**编辑**"。(如果编辑 SIEM 代理, 则无需重新运行 .jar 文件; 它会自动更新。)</span><span class="sxs-lookup"><span data-stu-id="1d72f-p116">Click the ellipses, and then choose **Edit**. (If you edit the SIEM agent, you do not need to re-run the .jar file; it updates automatically.) </span></span><br/><span data-ttu-id="1d72f-233">![若要编辑您的 SIEM 代理, 请选择省略号, 然后选择 "编辑"。](media/96d0b362-3e0c-4dff-b2b4-d7af5b1bfb91.png)</span><span class="sxs-lookup"><span data-stu-id="1d72f-233">![To edit your SIEM agent, choose the ellipses, and then choose Edit.](media/96d0b362-3e0c-4dff-b2b4-d7af5b1bfb91.png)</span></span>
  
### <a name="delete-a-siem-agent"></a><span data-ttu-id="1d72f-234">删除 SIEM 代理</span><span class="sxs-lookup"><span data-stu-id="1d72f-234">Delete a SIEM agent</span></span>

1. <span data-ttu-id="1d72f-235">在 Office 365 云应用安全门户[https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)() 中, 选择 "**设置** > **安全扩展**"。</span><span class="sxs-lookup"><span data-stu-id="1d72f-235">In the Office 365 Cloud App Security portal ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)), choose **Settings** > **Security extensions**.</span></span>

2. <span data-ttu-id="1d72f-236">找到 SIEM 代理的行。</span><span class="sxs-lookup"><span data-stu-id="1d72f-236">Locate the row for the SIEM agent.</span></span> 

3. <span data-ttu-id="1d72f-237">单击省略号, 然后选择 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="1d72f-237">Click the ellipses, and then choose **Delete**.</span></span><br/><span data-ttu-id="1d72f-238">![若要删除 SIEM 代理, 请选择省略号, 然后选择 "删除"。](media/540b5bdf-5574-4ecc-a7b0-92a499a387d7.png)</span><span class="sxs-lookup"><span data-stu-id="1d72f-238">![To delete a SIEM agent, choose the ellipses, and then choose Delete.](media/540b5bdf-5574-4ecc-a7b0-92a499a387d7.png)</span></span>

  
## <a name="next-steps"></a><span data-ttu-id="1d72f-239">后续步骤</span><span class="sxs-lookup"><span data-stu-id="1d72f-239">Next steps</span></span>

- [<span data-ttu-id="1d72f-240">推出 Office 365 云应用安全后的利用率活动</span><span class="sxs-lookup"><span data-stu-id="1d72f-240">Utilization activities after rolling out Office 365 Cloud App Security</span></span>](utilization-activities-for-ocas.md)
    
- [<span data-ttu-id="1d72f-241">查看警报并对其执行操作</span><span class="sxs-lookup"><span data-stu-id="1d72f-241">Review and take action on alerts</span></span>](review-office-365-cas-alerts.md)
    
- [<span data-ttu-id="1d72f-242">将 IP 地址分组以简化管理</span><span class="sxs-lookup"><span data-stu-id="1d72f-242">Group your IP addresses to simplify management</span></span>](group-your-ip-addresses-in-ocas.md)
    

