---
title: 启用或禁用 Office 365 中的安全提示
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/05/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: f09668bd-fe1a-4c01-89e3-e88c370e66c7
ms.collection:
- M365-security-compliance
description: 通知 Office 365 和 EOP 管理员如何在电子邮件中启用和禁用安全提示。
ms.openlocfilehash: 9be9c4cd7fc8e94208aac2ad8812c93a3465f58b
ms.sourcegitcommit: 0f93b37c39d807dec91f118aa671a3430c47a9ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/20/2019
ms.locfileid: "30693431"
---
# <a name="enable-or-disable-safety-tips-in-office-365"></a><span data-ttu-id="94423-103">启用或禁用 Office 365 中的安全提示</span><span class="sxs-lookup"><span data-stu-id="94423-103">Enable or disable safety tips in Office 365</span></span>

<span data-ttu-id="94423-104">Exchange Online Protection (EOP) 为其传递的电子邮件添加或标记安全提示。</span><span class="sxs-lookup"><span data-stu-id="94423-104">Exchange Online Protection (EOP) adds, or stamps, a safety tip to email messages that it delivers.</span></span> <span data-ttu-id="94423-105">这些安全提示为收件人提供了快速、直观的方法来确定邮件是否来自安全的已验证发件人, 如果邮件已被 Office 365 标记为 "垃圾邮件", 如果邮件中包含可疑内容 (如仿冒欺诈), 或者外部图像具有被阻止。</span><span class="sxs-lookup"><span data-stu-id="94423-105">These safety tips provide recipients with a quick, visual way to determine if a message is from a safe, verified sender, if the message has been marked as spam by Office 365, if the message contains something suspicious such as a phishing scam, or if external images have been blocked.</span></span> <span data-ttu-id="94423-106">Office 365 和 EOP 管理员可以编辑垃圾邮件策略设置, 以启用或禁用在 Outlook 和其他桌面电子邮件客户端的电子邮件中显示的安全提示。</span><span class="sxs-lookup"><span data-stu-id="94423-106">Office 365 and EOP-standalone admins can edit a spam policy setting to enable or disable safety tips from being displayed in email in Outlook and other desktop email clients.</span></span> 
  
<span data-ttu-id="94423-107">Office 365 默认为您的组织启用安全提示, 我们建议您将其保持启用状态, 以帮助抵御垃圾邮件和网络钓鱼攻击。</span><span class="sxs-lookup"><span data-stu-id="94423-107">Office 365 enables safety tips by default for your organization and we recommend that you leave them enabled to help combat spam and phishing attacks.</span></span> <span data-ttu-id="94423-108">无法对 web 上的 Outlook 禁用安全提示。</span><span class="sxs-lookup"><span data-stu-id="94423-108">You can't disable safety tips for Outlook on the web.</span></span>
  
<span data-ttu-id="94423-109">若要查看示例并了解安全提示中显示的信息, 请参阅[Office 365 中的电子邮件中的安全提示。](safety-tips-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="94423-109">To see examples and to learn about the information displayed in safety tips, see [Safety tips in email messages in Office 365.](safety-tips-in-office-365.md)</span></span>
  
<span data-ttu-id="94423-110">本主题内容：</span><span class="sxs-lookup"><span data-stu-id="94423-110">In this topic:</span></span>
  
- [<span data-ttu-id="94423-111">使用 Office 365 安全&amp;合规中心启用或禁用安全提示</span><span class="sxs-lookup"><span data-stu-id="94423-111">To enable or disable safety tips by using the Office 365 Security &amp; Compliance Center</span></span>](enable-or-disable-safety-tips.md#SandCCsafetytip)
    
- [<span data-ttu-id="94423-112">使用 PowerShell 启用或禁用安全提示的具体方法</span><span class="sxs-lookup"><span data-stu-id="94423-112">To enable or disable safety tips by using PowerShell</span></span>](enable-or-disable-safety-tips.md#pshellsafetytip)
    
## <a name="to-enable-or-disable-safety-tips-by-using-the-office-365-security-amp-compliance-center"></a><span data-ttu-id="94423-113">使用 Office 365 安全&amp;合规中心启用或禁用安全提示</span><span class="sxs-lookup"><span data-stu-id="94423-113">To enable or disable safety tips by using the Office 365 Security &amp; Compliance Center</span></span>
<span data-ttu-id="94423-114"><a name="SandCCsafetytip"> </a></span><span class="sxs-lookup"><span data-stu-id="94423-114"></span></span>

1. <span data-ttu-id="94423-115">转到 [https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="94423-115">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="94423-116">使用您的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="94423-116">Sign in to Office 365 with your work or school account.</span></span>
    
3. <span data-ttu-id="94423-117">选择 "**威胁管理** \> **策略**"。</span><span class="sxs-lookup"><span data-stu-id="94423-117">Choose **Threat Management** \> **Policy**.</span></span> 
    
4. <span data-ttu-id="94423-118">在 "**策略**" 页上, 选择 "**反垃圾邮件**"。</span><span class="sxs-lookup"><span data-stu-id="94423-118">On the **Policy** page, choose **Anti-Spam**.</span></span>
    
    ![此屏幕截图显示如何获取安全&amp;合规性中心中的 "反垃圾邮件设置" 页。](media/b8eb2ee3-2eb1-4ea2-b138-f6d7fb2e23de.png)
  
5. <span data-ttu-id="94423-120">在 "**反垃圾邮件设置**" 页上, 选择 "**自定义**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="94423-120">On the **Anti-spam settings** page choose the **Custom** tab.</span></span> 
    
    ![此屏幕截图显示 "安全&amp;合规中心" 的 "反垃圾邮件设置" 页上的 "自定义" 选项卡的位置。](media/1d688d23-e6f3-4de5-84a7-e8ce31786193.png)
  
6. <span data-ttu-id="94423-122">如有必要, 请选择 "**自定义设置**" 开关打开自定义设置。</span><span class="sxs-lookup"><span data-stu-id="94423-122">If necessary, choose the **Custom settings** switch to turn on custom settings.</span></span> <span data-ttu-id="94423-123">如果自定义设置开关设置为 "**关闭**", 则无法修改垃圾邮件筛选器策略。</span><span class="sxs-lookup"><span data-stu-id="94423-123">If the custom settings switch is set to **Off**, you won't be able to modify spam filter policies.</span></span>
    
    ![此屏幕截图显示自定义反垃圾邮件筛选器策略设置处于关闭状态。](media/94f900ad-b556-4a31-a3ac-acfcd72e71b8.png)
  
7. <span data-ttu-id="94423-125">展开要修改的垃圾邮件策略, 然后选择 "**编辑策略**"。</span><span class="sxs-lookup"><span data-stu-id="94423-125">Expand the spam policy you want to modify and then choose **Edit policy**.</span></span> <span data-ttu-id="94423-126">例如, 选择 "**默认垃圾邮件筛选器策略**" 旁边的向下箭头。</span><span class="sxs-lookup"><span data-stu-id="94423-126">For example, choose the down arrow next to **Default spam filter policy**.</span></span> <span data-ttu-id="94423-127">或者, 如果需要, 可以通过选择 "**添加策略**" 来创建新策略。</span><span class="sxs-lookup"><span data-stu-id="94423-127">Or, if you want, you can create a new policy by choosing **Add a policy**.</span></span>
    
8. <span data-ttu-id="94423-128">展开**垃圾邮件和批量**操作。</span><span class="sxs-lookup"><span data-stu-id="94423-128">Expand **Spam and bulk** actions.</span></span> 
    
9. <span data-ttu-id="94423-129">若要启用安全提示, 请在 "**安全提示**" 下选中 "**打开**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="94423-129">To enable safety tips, under **Safety Tips**, check the **On** checkbox.</span></span> <span data-ttu-id="94423-130">若要禁用安全提示, 请清除 "**打开**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="94423-130">To disable safety tips, clear the **On** checkbox.</span></span> 
    
10. <span data-ttu-id="94423-131">选择“保存”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="94423-131">Choose **Save**.</span></span>
    
## <a name="to-enable-or-disable-safety-tips-by-using-powershell"></a><span data-ttu-id="94423-132">使用 PowerShell 启用或禁用安全提示的具体方法</span><span class="sxs-lookup"><span data-stu-id="94423-132">To enable or disable safety tips by using PowerShell</span></span>
<span data-ttu-id="94423-133"><a name="pshellsafetytip"> </a></span><span class="sxs-lookup"><span data-stu-id="94423-133"></span></span>

<span data-ttu-id="94423-134">管理员可以使用 Exchange Online PowerShell 启用或禁用安全提示。</span><span class="sxs-lookup"><span data-stu-id="94423-134">Admins can use Exchange Online PowerShell to enable or disable safety tips.</span></span> <span data-ttu-id="94423-135">使用 set-hostedcontentfilterpolicy cmdlet 可以在垃圾邮件筛选器策略中启用或禁用安全提示。</span><span class="sxs-lookup"><span data-stu-id="94423-135">Use the Set-HostedContentFilterPolicy cmdlet to enable or disable safety tips in a spam filter policy.</span></span>
  
1. <span data-ttu-id="94423-136">连接到 Exchange Online PowerShell。</span><span class="sxs-lookup"><span data-stu-id="94423-136">Connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="94423-137">有关信息, 请参阅[连接到 Exchange Online PowerShell](http://go.microsoft.com/fwlink/p/?LinkId=396554)。</span><span class="sxs-lookup"><span data-stu-id="94423-137">For information, see [Connect to Exchange Online PowerShell](http://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span>
    
2. <span data-ttu-id="94423-138">运行 set-hostedcontentfilterpolicy cmdlet 以启用或禁用安全提示:</span><span class="sxs-lookup"><span data-stu-id="94423-138">Run the Set-HostedContentFilterPolicy cmdlet to enable or disable safety tips:</span></span>
    
  ```
  Set-HostedContentFilterPolicy -Identity "policy name " -InlineSafetyTipsEnabled <$true|$false>
  ```

<span data-ttu-id="94423-139">其中：</span><span class="sxs-lookup"><span data-stu-id="94423-139">Where:</span></span>
    
  -  <span data-ttu-id="94423-140">*策略名称*是要修改的策略的名称, 例如,**默认值**。</span><span class="sxs-lookup"><span data-stu-id="94423-140">*policy name*  is the name of the policy you want to modify, for example **default**.</span></span>
    
  -  <span data-ttu-id="94423-141">`$true`为垃圾邮件筛选器策略启用安全提示。</span><span class="sxs-lookup"><span data-stu-id="94423-141">`$true` enables safety tips for the spam filter policy.</span></span> 
    
  -  <span data-ttu-id="94423-142">`$false`禁用垃圾邮件筛选器策略的安全提示。</span><span class="sxs-lookup"><span data-stu-id="94423-142">`$false` disables safety tips for the spam filter policy.</span></span> 
    
    <span data-ttu-id="94423-143">例如, 若要禁用默认垃圾邮件筛选器策略的安全提示, 请运行以下命令:</span><span class="sxs-lookup"><span data-stu-id="94423-143">For example, to disable safety tips for the default spam filter policy, run the following command:</span></span>
    
  ```
  PS C:\> Set-HostedContentFilterPolicy -Identity "default" -InlineSafetyTipsEnabled $false
  ```

<span data-ttu-id="94423-144">有关此 cmdlet 的详细信息, 请参阅[set-hostedcontentfilterpolicy](https://technet.microsoft.com/library/jj200781.aspx)。</span><span class="sxs-lookup"><span data-stu-id="94423-144">For more information about this cmdlet, see [Set-HostedContentFilterPolicy](https://technet.microsoft.com/library/jj200781.aspx).</span></span>
    
## <a name="still-need-help"></a><span data-ttu-id="94423-145">是否仍需要帮助？</span><span class="sxs-lookup"><span data-stu-id="94423-145">Still need help?</span></span>
<span data-ttu-id="94423-146"><a name="pshellsafetytip"> </a></span><span class="sxs-lookup"><span data-stu-id="94423-146"></span></span>

<span data-ttu-id="94423-147">如果您禁用安全提示, 但仍在电子邮件中看到它们, 请检查以下内容:</span><span class="sxs-lookup"><span data-stu-id="94423-147">If you disabled safety tips but are still seeing them in your email messages, check these things:</span></span>
  
- <span data-ttu-id="94423-148">无法对 web 上的 Outlook 禁用安全提示。</span><span class="sxs-lookup"><span data-stu-id="94423-148">You can't disable safety tips for Outlook on the web.</span></span> <span data-ttu-id="94423-149">请尝试在另一个客户端 (如 Outlook) 中查看相同的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="94423-149">Try viewing the same email in another client, such as Outlook.</span></span>
    
- <span data-ttu-id="94423-150">默认情况下, 每个使用 EOP 的用户都启用安全提示, 其中包括拥有 Office 365 的所有用户。</span><span class="sxs-lookup"><span data-stu-id="94423-150">Safety tips are on by default for every one who uses EOP, this includes everyone who has Office 365.</span></span> <span data-ttu-id="94423-151">若要禁用电子邮件中显示的安全提示, 必须使用垃圾邮件筛选器策略禁用它们, 如本主题中所述。</span><span class="sxs-lookup"><span data-stu-id="94423-151">In order to disable safety tips from showing up in email, you must disable them by using a spam filter policy as described in this topic.</span></span> <span data-ttu-id="94423-152">设置完策略后, 请确保已启用该策略。</span><span class="sxs-lookup"><span data-stu-id="94423-152">Once you've set up the policy, ensure that it is enabled.</span></span> <span data-ttu-id="94423-153">有关启用垃圾邮件筛选器策略的信息, 请参阅[配置垃圾邮件筛选器策略](https://technet.microsoft.com/library/jj200684.aspx)。</span><span class="sxs-lookup"><span data-stu-id="94423-153">For information on enabling spam filter policies, see [Configure your spam filter policies](https://technet.microsoft.com/library/jj200684.aspx).</span></span>
    
<span data-ttu-id="94423-154">有关防御垃圾邮件和网络钓鱼的更多方法, 请参阅[Office 365 电子邮件反垃圾邮件保护](anti-spam-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="94423-154">For more ways to combat spam and phishing, see [Office 365 Email Anti-Spam Protection](anti-spam-protection.md).</span></span>
  

