---
title: 启用或禁用 Office 365 中的安全提示
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/05/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: f09668bd-fe1a-4c01-89e3-e88c370e66c7
description: 向 Office 365 和 EOP 管理员介绍如何启用和禁用电子邮件中的安全提示。
ms.openlocfilehash: 8e5d8bf1d2f831b5d74ca3accd8b434519bfeaab
ms.sourcegitcommit: 204fb0269b5c10b63941055824e863d77e3e9b02
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/06/2018
ms.locfileid: "27180852"
---
# <a name="enable-or-disable-safety-tips-in-office-365"></a><span data-ttu-id="73506-103">启用或禁用 Office 365 中的安全提示</span><span class="sxs-lookup"><span data-stu-id="73506-103">Enable or disable safety tips in Office 365</span></span>

<span data-ttu-id="73506-p101">Exchange Online Protection (EOP) 添加，或对它提供的电子邮件的标记安全提示。如果邮件已被标记为垃圾邮件的 Office 365 中，如果邮件包含可疑网络钓鱼诈骗，如内容或外部图像具有这些安全提示提供使用一种快速 visual 的方式来确定邮件是否从安全收件人验证发件人，被阻止。Office 365 和独立 EOP 管理员可以编辑垃圾邮件策略设置启用或禁用 Outlook 和其他桌面电子邮件客户端中的电子邮件中显示的安全提示。</span><span class="sxs-lookup"><span data-stu-id="73506-p101">Exchange Online Protection (EOP) adds, or stamps, a safety tip to email messages that it delivers. These safety tips provide recipients with a quick, visual way to determine if a message is from a safe, verified sender, if the message has been marked as spam by Office 365, if the message contains something suspicious such as a phishing scam, or if external images have been blocked. Office 365 and EOP-standalone admins can edit a spam policy setting to enable or disable safety tips from being displayed in email in Outlook and other desktop email clients.</span></span> 
  
<span data-ttu-id="73506-p102">Office 365 默认情况下，为您的组织中启用安全提示，我们建议您将保留其启用，以帮助防御垃圾邮件和网络钓鱼攻击。您无法在 web 上的 outlook 中禁用安全提示。</span><span class="sxs-lookup"><span data-stu-id="73506-p102">Office 365 enables safety tips by default for your organization and we recommend that you leave them enabled to help combat spam and phishing attacks. You can't disable safety tips for Outlook on the web.</span></span>
  
<span data-ttu-id="73506-109">若要查看示例，以及若要了解有关安全提示中显示的信息，请参阅[安全提示 Office 365 中的电子邮件中。](safety-tips-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="73506-109">To see examples and to learn about the information displayed in safety tips, see [Safety tips in email messages in Office 365.](safety-tips-in-office-365.md)</span></span>
  
<span data-ttu-id="73506-110">本主题内容：</span><span class="sxs-lookup"><span data-stu-id="73506-110">In this topic:</span></span>
  
- [<span data-ttu-id="73506-111">启用或禁用使用 Office 365 安全性安全提示&amp;合规性中心</span><span class="sxs-lookup"><span data-stu-id="73506-111">To enable or disable safety tips by using the Office 365 Security &amp; Compliance Center</span></span>](enable-or-disable-safety-tips.md#SandCCsafetytip)
    
- [<span data-ttu-id="73506-112">启用或禁用使用 PowerShell 安全提示</span><span class="sxs-lookup"><span data-stu-id="73506-112">To enable or disable safety tips by using PowerShell</span></span>](enable-or-disable-safety-tips.md#pshellsafetytip)
    
## <a name="to-enable-or-disable-safety-tips-by-using-the-office-365-security-amp-compliance-center"></a><span data-ttu-id="73506-113">启用或禁用使用 Office 365 安全性安全提示&amp;合规性中心</span><span class="sxs-lookup"><span data-stu-id="73506-113">To enable or disable safety tips by using the Office 365 Security &amp; Compliance Center</span></span>
<span data-ttu-id="73506-114"><a name="SandCCsafetytip"> </a></span><span class="sxs-lookup"><span data-stu-id="73506-114"></span></span>

1. <span data-ttu-id="73506-115">转到 [https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="73506-115">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="73506-116">使用工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="73506-116">Sign in to Office 365 with your work or school account.</span></span>
    
3. <span data-ttu-id="73506-117">选择**威胁管理** \> **策略**。</span><span class="sxs-lookup"><span data-stu-id="73506-117">Choose **Threat Management** \> **Policy**.</span></span> 
    
4. <span data-ttu-id="73506-118">在**策略**页中，选择**反垃圾邮件**。</span><span class="sxs-lookup"><span data-stu-id="73506-118">On the **Policy** page, choose **Anti-Spam**.</span></span>
    
    ![此屏幕截图显示如何获取到安全中的反垃圾邮件设置页&amp;合规性中心。](media/b8eb2ee3-2eb1-4ea2-b138-f6d7fb2e23de.png)
  
5. <span data-ttu-id="73506-120">在**反垃圾邮件设置**页上选择**自定义**选项卡。</span><span class="sxs-lookup"><span data-stu-id="73506-120">On the **Anti-spam settings** page choose the **Custom** tab.</span></span> 
    
    ![此屏幕截图显示在安全中反垃圾邮件设置页上的自定义选项卡的位置&amp;合规性中心。](media/1d688d23-e6f3-4de5-84a7-e8ce31786193.png)
  
6. <span data-ttu-id="73506-p103">如有必要，选择**自定义设置**开关，打开自定义设置。如果自定义设置开关设置为**关闭**，您将无法修改垃圾邮件筛选器策略。</span><span class="sxs-lookup"><span data-stu-id="73506-p103">If necessary, choose the **Custom settings** switch to turn on custom settings. If the custom settings switch is set to **Off**, you won't be able to modify spam filter policies.</span></span>
    
    ![此屏幕截图显示自定义反垃圾邮件筛选器关闭的策略设置。](media/94f900ad-b556-4a31-a3ac-acfcd72e71b8.png)
  
7. <span data-ttu-id="73506-p104">展开您想要修改，然后选择**编辑策略**的垃圾邮件策略。例如，选择**默认垃圾邮件筛选策略**旁边的向下箭头。或者，如果需要，您可以通过选择**添加策略**来创建新策略。</span><span class="sxs-lookup"><span data-stu-id="73506-p104">Expand the spam policy you want to modify and then choose **Edit policy**. For example, choose the down arrow next to **Default spam filter policy**. Or, if you want, you can create a new policy by choosing **Add a policy**.</span></span>
    
8. <span data-ttu-id="73506-128">展开**垃圾邮件和批量**操作。</span><span class="sxs-lookup"><span data-stu-id="73506-128">Expand **Spam and bulk** actions.</span></span> 
    
9. <span data-ttu-id="73506-p105">若要启用安全提示，在**安全提示**下的选中**上**复选框。若要禁用安全提示，请清除**上**复选框。</span><span class="sxs-lookup"><span data-stu-id="73506-p105">To enable safety tips, under **Safety Tips**, check the **On** checkbox. To disable safety tips, clear the **On** checkbox.</span></span> 
    
10. <span data-ttu-id="73506-131">选择" **保存**"。</span><span class="sxs-lookup"><span data-stu-id="73506-131">Choose **Save**.</span></span>
    
## <a name="to-enable-or-disable-safety-tips-by-using-powershell"></a><span data-ttu-id="73506-132">启用或禁用使用 PowerShell 安全提示</span><span class="sxs-lookup"><span data-stu-id="73506-132">To enable or disable safety tips by using PowerShell</span></span>
<span data-ttu-id="73506-133"><a name="pshellsafetytip"> </a></span><span class="sxs-lookup"><span data-stu-id="73506-133"></span></span>

<span data-ttu-id="73506-p106">管理员可以使用 Exchange Online PowerShell 中启用或禁用安全提示。使用 Set-hostedcontentfilterpolicy cmdlet 可以启用或禁用垃圾邮件筛选器策略中的安全提示。</span><span class="sxs-lookup"><span data-stu-id="73506-p106">Admins can use Exchange Online PowerShell to enable or disable safety tips. Use the Set-HostedContentFilterPolicy cmdlet to enable or disable safety tips in a spam filter policy.</span></span>
  
1. <span data-ttu-id="73506-p107">连接到 Exchange Online PowerShell 中。有关信息，请参阅[Connect to Exchange Online PowerShell 中](http://go.microsoft.com/fwlink/p/?LinkId=396554)。</span><span class="sxs-lookup"><span data-stu-id="73506-p107">Connect to Exchange Online PowerShell. For information, see [Connect to Exchange Online PowerShell](http://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span>
    
2. <span data-ttu-id="73506-138">运行 Set-hostedcontentfilterpolicy cmdlet 启用或禁用安全提示：</span><span class="sxs-lookup"><span data-stu-id="73506-138">Run the Set-HostedContentFilterPolicy cmdlet to enable or disable safety tips:</span></span>
    
  ```
  Set-HostedContentFilterPolicy -Identity "policy name " -InlineSafetyTipsEnabled <$true|$false>
  ```

<span data-ttu-id="73506-139">其中：</span><span class="sxs-lookup"><span data-stu-id="73506-139">Where:</span></span>
    
  -  <span data-ttu-id="73506-140">*策略名称*是想要修改，例如**默认**策略的名称。</span><span class="sxs-lookup"><span data-stu-id="73506-140">*policy name*  is the name of the policy you want to modify, for example **default**.</span></span>
    
  -  <span data-ttu-id="73506-141">`$true`启用垃圾邮件筛选器策略的安全提示。</span><span class="sxs-lookup"><span data-stu-id="73506-141">`$true` enables safety tips for the spam filter policy.</span></span> 
    
  -  <span data-ttu-id="73506-142">`$false`禁用垃圾邮件筛选器策略的安全提示。</span><span class="sxs-lookup"><span data-stu-id="73506-142">`$false` disables safety tips for the spam filter policy.</span></span> 
    
    <span data-ttu-id="73506-143">例如，若要禁用默认垃圾邮件筛选器策略的安全提示，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="73506-143">For example, to disable safety tips for the default spam filter policy, run the following command:</span></span>
    
  ```
  PS C:\> Set-HostedContentFilterPolicy -Identity "default" -InlineSafetyTipsEnabled $false
  ```

<span data-ttu-id="73506-144">有关此 cmdlet 的详细信息，请参阅[Set-hostedcontentfilterpolicy](https://technet.microsoft.com/library/jj200781.aspx)。</span><span class="sxs-lookup"><span data-stu-id="73506-144">For more information about this cmdlet, see [Set-HostedContentFilterPolicy](https://technet.microsoft.com/library/jj200781.aspx).</span></span>
    
## <a name="still-need-help"></a><span data-ttu-id="73506-145">是否仍需要帮助？</span><span class="sxs-lookup"><span data-stu-id="73506-145">Still need help?</span></span>
<span data-ttu-id="73506-146"><a name="pshellsafetytip"> </a></span><span class="sxs-lookup"><span data-stu-id="73506-146"></span></span>

<span data-ttu-id="73506-147">如果您禁用安全提示，但仍在您的电子邮件中看到它们，检查以下事项：</span><span class="sxs-lookup"><span data-stu-id="73506-147">If you disabled safety tips but are still seeing them in your email messages, check these things:</span></span>
  
- <span data-ttu-id="73506-p108">您无法在 web 上的 outlook 中禁用安全提示。尝试在另一个客户端，如 Outlook 中查看相同的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="73506-p108">You can't disable safety tips for Outlook on the web. Try viewing the same email in another client, such as Outlook.</span></span>
    
- <span data-ttu-id="73506-p109">安全提示是在默认情况下，使用 EOP 每一个，包括 Office 365 的任何人。若要禁用安全提示中显示电子邮件中，您必须禁用它们通过本主题中所述使用垃圾邮件筛选器策略。一旦您已设置此策略，则确保启用了它。有关启用垃圾邮件筛选器策略的信息，请参阅[配置垃圾邮件筛选器策略](https://technet.microsoft.com/library/jj200684.aspx)。</span><span class="sxs-lookup"><span data-stu-id="73506-p109">Safety tips are on by default for every one who uses EOP, this includes everyone who has Office 365. In order to disable safety tips from showing up in email, you must disable them by using a spam filter policy as described in this topic. Once you've set up the policy, ensure that it is enabled. For information on enabling spam filter policies, see [Configure your spam filter policies](https://technet.microsoft.com/library/jj200684.aspx).</span></span>
    
<span data-ttu-id="73506-154">有关可防止出现垃圾邮件和网络钓鱼的详细方法，请参阅[Office 365 电子邮件防垃圾邮件保护](anti-spam-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="73506-154">For more ways to combat spam and phishing, see [Office 365 Email Anti-Spam Protection](anti-spam-protection.md).</span></span>
  

