---
title: 安装适用于 Outlook 桌面版的监督加载项
ms.author: robmazz
author: robmazz
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
- ZOL160
ms.assetid: 6c5620e6-aba3-4910-8f3a-b55451656ff7
description: 安装 Office 365 监督外接程序桌面的 Outlook 版本
ms.openlocfilehash: b0cb0d78ab5f8887628528dd53b49fb15de44126
ms.sourcegitcommit: 204fb0269b5c10b63941055824e863d77e3e9b02
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/06/2018
ms.locfileid: "27180862"
---
# <a name="install-the-supervision-add-in-for-outlook-desktop"></a><span data-ttu-id="eea9e-103">安装适用于 Outlook 桌面版的监督加载项</span><span class="sxs-lookup"><span data-stu-id="eea9e-103">Install the Supervision add-in for Outlook desktop</span></span>

<span data-ttu-id="eea9e-p101">若要查看 communications 监督策略的标识，监督外接程序 Outlook 和 Outlook 的审阅者使用的 web 应用程序。外接程序是自动安装 Outlook web app 中的所有策略中指定的审阅者。但是，审阅者必须通过一些步骤将其安装桌面的 Outlook 版本中运行。</span><span class="sxs-lookup"><span data-stu-id="eea9e-p101">To review communications identified by a supervision policy, reviewers use the Supervision add-in for Outlook and Outlook web app. The add-in is installed automatically in Outlook web app for all reviewers you specified in the policy. However, reviewers must run through some steps to install it in the desktop version of Outlook.</span></span>
  
> [!NOTE]
> <span data-ttu-id="eea9e-p102">由监督策略监控的用户必须具有与高级合规性加载项的 Office 365 企业版 E3 许可证或包含在 Office 365 企业 E5 订阅。如果您不具有现有企业 E5 计划，并需要尝试监督，您还可以[注册试用版的 Office 365 企业 E5](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="eea9e-p102">Users monitored by supervision policies must have either an Office 365 Enterprise E3 license with the Advanced Compliance add-on or be included in an Office 365 Enterprise E5 subscription. If you don't have an existing Enterprise E5 plan and want to try supervision, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span>
  
## <a name="step-1-copy-the-address-for-the-supervision-mailbox"></a><span data-ttu-id="eea9e-109">步骤 1： 复制监督邮箱的地址</span><span class="sxs-lookup"><span data-stu-id="eea9e-109">Step 1: Copy the address for the supervision mailbox</span></span>

<span data-ttu-id="eea9e-110">若要安装外接程序 Outlook 桌面程序，您将需要作为监督策略设置的一部分创建的监督邮箱地址。</span><span class="sxs-lookup"><span data-stu-id="eea9e-110">To install the add-in for Outlook desktop, you'll need the address for the supervision mailbox that was created as part of the supervision policy setup.</span></span>
  
> [!NOTE]
> <span data-ttu-id="eea9e-111">如果其他人创建策略，您将需要从原始安装外接程序获得此地址。</span><span class="sxs-lookup"><span data-stu-id="eea9e-111">If someone else created the policy, you'll need to get this address from them to install the add-in.</span></span>
 
 <span data-ttu-id="eea9e-112">**若要查找的监督邮箱地址**</span><span class="sxs-lookup"><span data-stu-id="eea9e-112">**To find the supervision mailbox address**</span></span>
  
1. <span data-ttu-id="eea9e-113">登录到[安全&amp;合规性中心](https://protection.office.com)使用 Office 365 组织中的管理帐户的凭据。</span><span class="sxs-lookup"><span data-stu-id="eea9e-113">Sign into the [Security &amp; Compliance Center](https://protection.office.com) using credentials for an admin account in your Office 365 organization.</span></span>
    
2. <span data-ttu-id="eea9e-114">转到**数据调控** \> **监督**。</span><span class="sxs-lookup"><span data-stu-id="eea9e-114">Go to **Data governance** \> **Supervision**.</span></span>
    
3. <span data-ttu-id="eea9e-115">单击收集的通信您想要查看的监督策略。</span><span class="sxs-lookup"><span data-stu-id="eea9e-115">Click the supervision policy that's gathering the communications you want to review.</span></span>
    
4. <span data-ttu-id="eea9e-116">在策略下详细弹出，\* \* 监督邮箱 \* \*，复制该地址。</span><span class="sxs-lookup"><span data-stu-id="eea9e-116">In the policy details flyout, under \*\* Supervision mailbox \*\*, copy the address.</span></span><br/>![显示突出显示的监督邮箱地址监督策略的详细信息弹出的监督邮箱部分](media/71779d0e-4f01-4dd3-8234-5f9c30eeb067.jpg)
  
## <a name="step-2-configure-the-supervision-mailbox-for-outlook-desktop-access"></a><span data-ttu-id="eea9e-118">步骤 2： 配置 Outlook 桌面访问的监督邮箱</span><span class="sxs-lookup"><span data-stu-id="eea9e-118">Step 2: Configure the supervision mailbox for Outlook desktop access</span></span>

<span data-ttu-id="eea9e-119">接下来，审阅者将需要运行的几 Exchange Online PowerShell 命令，以便他们可以将 Outlook 连接到监督邮箱。</span><span class="sxs-lookup"><span data-stu-id="eea9e-119">Next, reviewers will need to run a couple Exchange Online PowerShell commands so they can connect Outlook to the supervision mailbox.</span></span>
  
1. <span data-ttu-id="eea9e-p103">连接到 Exchange Online PowerShell 中。[我该如何做？](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="eea9e-p103">Connect to Exchange Online PowerShell. [How do I do this?](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)</span></span>
    
2. <span data-ttu-id="eea9e-122">运行以下命令，其中*SupervisoryReview{GUID}@domain.onmicrosoft.com*是您在上面的步骤 1 中复制的地址，*用户*是将连接到步骤 3 中的监督邮箱审核者的名称。</span><span class="sxs-lookup"><span data-stu-id="eea9e-122">Run the following commands, where  *SupervisoryReview{GUID}@domain.onmicrosoft.com*  is the address you copied in Step 1 above, and  *User*  is the name of the reviewer who will be connecting to the supervision mailbox in Step 3.</span></span>
    - ```Add-MailboxPermission "SupervisoryReview{GUID}@domain.onmicrosoft.com" -User <alias or email address of the account that has reviewer permissions to the supervision mailbox> -AccessRights FullAccess```<br/>
    - ```Set-Mailbox "<SupervisoryReview{GUID}@domain.onmicrosoft.com>" -HiddenFromAddressListsEnabled: $false```
    
3. <span data-ttu-id="eea9e-123">等待至少一个小时之后才能接着下面的步骤 3。</span><span class="sxs-lookup"><span data-stu-id="eea9e-123">Wait at least an hour before moving on to Step 3 below.</span></span>
    
## <a name="step-3-create-an-outlook-profile-to-connect-to-the-supervision-mailbox"></a><span data-ttu-id="eea9e-124">步骤 3： 创建 Outlook 配置文件连接到监督邮箱</span><span class="sxs-lookup"><span data-stu-id="eea9e-124">Step 3: Create an Outlook profile to connect to the supervision mailbox</span></span>

<span data-ttu-id="eea9e-125">最后一步，将需要审阅者创建的 Outlook 配置文件连接到监督邮箱。</span><span class="sxs-lookup"><span data-stu-id="eea9e-125">For the final step, reviewers will need to create an Outlook profile to connect to the supervision mailbox.</span></span>
 
> [!NOTE]
> <span data-ttu-id="eea9e-p104">若要创建新的 Outlook 配置文件，您将使用 Windows 控制面板中邮件设置。您需要访问这些设置的路径可能取决于您正在使用的 Windows 操作系统 （Windows 7、 Windows 8 或 Windows 10） 和安装哪个版本的 Outlook。</span><span class="sxs-lookup"><span data-stu-id="eea9e-p104">To create a new Outlook profile, you'll use the Mail settings in the Windows Control Panel. The path you take to get to these settings might depend on which Windows operating system (Windows 7, Windows 8, or Windows 10) you're using and which version of Outlook is installed.</span></span>
  
1. <span data-ttu-id="eea9e-128">打开控制面板，并在窗口顶部的**搜索**框中，键入**邮件**。</span><span class="sxs-lookup"><span data-stu-id="eea9e-128">Open the Control Panel, and in the **Search** box at the top of the window, type **Mail**.</span></span><br/><span data-ttu-id="eea9e-p105">(不确定如何获取控制面板？请参阅[其中是 Control Panel？](https://support.microsoft.com/help/13764/windows-where-is-control-panel))</span><span class="sxs-lookup"><span data-stu-id="eea9e-p105">(Not sure how to get to the Control Panel? See [Where is Control Panel?](https://support.microsoft.com/help/13764/windows-where-is-control-panel))</span></span>
  
2. <span data-ttu-id="eea9e-131">打开**邮件**应用程序。</span><span class="sxs-lookup"><span data-stu-id="eea9e-131">Open the **Mail** app.</span></span>
    
3. <span data-ttu-id="eea9e-132">在**邮件设置-Outlook**中，单击**显示配置文件**。</span><span class="sxs-lookup"><span data-stu-id="eea9e-132">In **Mail Setup - Outlook**, click **Show Profiles**.</span></span><br/><span data-ttu-id="eea9e-133">![邮件设置的 Outlook 与显示配置文件按钮突出显示的对话框](media/28b5dae9-d10c-4f2b-926a-294c857d555c.jpg)</span><span class="sxs-lookup"><span data-stu-id="eea9e-133">![The 'Mail Setup - Outlook' dialog box with the 'Show Profiles' button highlighted](media/28b5dae9-d10c-4f2b-926a-294c857d555c.jpg)</span></span>
  
4. <span data-ttu-id="eea9e-p106">在**邮件**框中，单击**添加**。然后，在**新的配置文件**中，输入监督邮箱 （例如**监督**） 的名称。</span><span class="sxs-lookup"><span data-stu-id="eea9e-p106">In **Mail**, click **Add**. Then, in **New Profile**, enter a name for the supervision mailbox (such as **Supervision**).</span></span><br/><span data-ttu-id="eea9e-136">![在配置文件名称框中显示名称监督' 新配置文件对话框](media/d02ae181-b541-4ec6-8f51-698f30033204.jpg)</span><span class="sxs-lookup"><span data-stu-id="eea9e-136">![The 'New Profile' dialog showing the name 'Supervision' in the 'Profile Name' box](media/d02ae181-b541-4ec6-8f51-698f30033204.jpg)</span></span>
  
5. <span data-ttu-id="eea9e-137">在**将 Outlook 连接到 Office 365**中，单击**连接到不同的帐户**。</span><span class="sxs-lookup"><span data-stu-id="eea9e-137">In **Connect Outlook to Office 365**, click **Connect to a different account**.</span></span><br/><span data-ttu-id="eea9e-138">![突出显示的连接到不同的帐户链接连接到 Office 365 Outlook 邮件](media/fac49ff8-a7f0-4e82-a271-9ec045a95de1.jpg)</span><span class="sxs-lookup"><span data-stu-id="eea9e-138">![The 'Connect Outlook to Office 365' message with the 'Connect to a different account' link highlighted](media/fac49ff8-a7f0-4e82-a271-9ec045a95de1.jpg)</span></span>
  
6. <span data-ttu-id="eea9e-139">在**自动帐户设置**中，选择**手动安装或其他服务器类型**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="eea9e-139">In **Auto Account Setup**, choose **Manual setup or additional server types**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="eea9e-p107">在**选择帐户类型**，选择**Office 365**。然后，在**电子邮件地址**框中，输入之前复制监督邮箱的地址。</span><span class="sxs-lookup"><span data-stu-id="eea9e-p107">In **Choose Your Account Type**, choose **Office 365**. Then, in the **Email Address** box, enter the address of the supervision mailbox you copied previously.</span></span><br/><span data-ttu-id="eea9e-142">![在 Outlook 中显示电子邮件地址框中突出显示添加帐户对话框的选择您的帐户类型页面。](media/4f601236-9f69-4cf6-a58c-0b91204aa8cb.jpg)</span><span class="sxs-lookup"><span data-stu-id="eea9e-142">![The 'Choose Your Account Type' page of the 'Add Account' dialog in Outlook showing the 'Email Address' box highlighted.](media/4f601236-9f69-4cf6-a58c-0b91204aa8cb.jpg)</span></span>
  
8. <span data-ttu-id="eea9e-143">出现提示时，输入您的 Office 365 凭据。</span><span class="sxs-lookup"><span data-stu-id="eea9e-143">When prompted, enter your Office 365 credentials.</span></span>
    
9. <span data-ttu-id="eea9e-144">如果成功，您将看到**监督-\<策略名称\>** 在 Outlook 的文件夹列表视图中列出的文件夹。</span><span class="sxs-lookup"><span data-stu-id="eea9e-144">If successful, you'll see the **Supervision - \<policy name\>** folder listed in the Folder List view in Outlook.</span></span>