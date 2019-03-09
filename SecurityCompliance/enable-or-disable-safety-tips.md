---
标题: "启用或禁用 Office 365 中的安全提示" ms. author: krowley author: kccross 管理器: laurawi 毫秒。日期: 12/05/2018 (): Admin ms. 主题: 文章 ms. 服务: o365-管理使用: 正常搜索。 appverid: 
- MET150 assetid: f09668bd-fe1a-4c01-89e3-e88c370e66c7 ms. 集合:
    - M365-安全性合规性说明: "告诉 Office 365 and EOP admins 如何在电子邮件中启用和禁用安全提示。"
---

# <a name="enable-or-disable-safety-tips-in-office-365"></a>启用或禁用 Office 365 中的安全提示

Exchange Online Protection (EOP) 为其传递的电子邮件添加或标记安全提示。 这些安全提示为收件人提供了快速、直观的方法来确定邮件是否来自安全的已验证发件人, 如果邮件已被 Office 365 标记为 "垃圾邮件", 如果邮件中包含可疑内容 (如仿冒欺诈), 或者外部图像具有被阻止。 Office 365 和 EOP 管理员可以编辑垃圾邮件策略设置, 以启用或禁用在 Outlook 和其他桌面电子邮件客户端的电子邮件中显示的安全提示。 
  
Office 365 默认为您的组织启用安全提示, 我们建议您将其保持启用状态, 以帮助抵御垃圾邮件和网络钓鱼攻击。 无法对 web 上的 Outlook 禁用安全提示。
  
若要查看示例并了解安全提示中显示的信息, 请参阅[Office 365 中的电子邮件中的安全提示。](safety-tips-in-office-365.md)
  
本主题内容：
  
- [使用 Office 365 安全&amp;合规中心启用或禁用安全提示](enable-or-disable-safety-tips.md#SandCCsafetytip)
    
- [使用 PowerShell 启用或禁用安全提示的具体方法](enable-or-disable-safety-tips.md#pshellsafetytip)
    
## <a name="to-enable-or-disable-safety-tips-by-using-the-office-365-security-amp-compliance-center"></a>使用 Office 365 安全&amp;合规中心启用或禁用安全提示
<a name="SandCCsafetytip"> </a>

1. 转到 [https://protection.office.com](https://protection.office.com)。
    
2. 使用您的工作或学校帐户登录 Office 365。
    
3. 选择 "**威胁管理** \> **策略**"。 
    
4. 在 "**策略**" 页上, 选择 "**反垃圾邮件**"。
    
    ![此屏幕截图显示如何获取安全&amp;合规性中心中的 "反垃圾邮件设置" 页。](media/b8eb2ee3-2eb1-4ea2-b138-f6d7fb2e23de.png)
  
5. 在 "**反垃圾邮件设置**" 页上, 选择 "**自定义**" 选项卡。 
    
    ![此屏幕截图显示 "安全&amp;合规中心" 的 "反垃圾邮件设置" 页上的 "自定义" 选项卡的位置。](media/1d688d23-e6f3-4de5-84a7-e8ce31786193.png)
  
6. 如有必要, 请选择 "**自定义设置**" 开关打开自定义设置。 如果自定义设置开关设置为 "**关闭**", 则无法修改垃圾邮件筛选器策略。
    
    ![此屏幕截图显示自定义反垃圾邮件筛选器策略设置处于关闭状态。](media/94f900ad-b556-4a31-a3ac-acfcd72e71b8.png)
  
7. 展开要修改的垃圾邮件策略, 然后选择 "**编辑策略**"。 例如, 选择 "**默认垃圾邮件筛选器策略**" 旁边的向下箭头。 或者, 如果需要, 可以通过选择 "**添加策略**" 来创建新策略。
    
8. 展开**垃圾邮件和批量**操作。 
    
9. 若要启用安全提示, 请在 "**安全提示**" 下选中 "**打开**" 复选框。 若要禁用安全提示, 请清除 "**打开**" 复选框。 
    
10. 选择“保存”****。
    
## <a name="to-enable-or-disable-safety-tips-by-using-powershell"></a>使用 PowerShell 启用或禁用安全提示的具体方法
<a name="pshellsafetytip"> </a>

管理员可以使用 Exchange Online PowerShell 启用或禁用安全提示。 使用 set-hostedcontentfilterpolicy cmdlet 可以在垃圾邮件筛选器策略中启用或禁用安全提示。
  
1. 连接到 Exchange Online PowerShell。 有关信息, 请参阅[连接到 Exchange Online PowerShell](http://go.microsoft.com/fwlink/p/?LinkId=396554)。
    
2. 运行 set-hostedcontentfilterpolicy cmdlet 以启用或禁用安全提示:
    
  ```
  Set-HostedContentFilterPolicy -Identity "policy name " -InlineSafetyTipsEnabled <$true|$false>
  ```

其中：
    
  -  *策略名称*是要修改的策略的名称, 例如,**默认值**。
    
  -  `$true`为垃圾邮件筛选器策略启用安全提示。 
    
  -  `$false`禁用垃圾邮件筛选器策略的安全提示。 
    
    例如, 若要禁用默认垃圾邮件筛选器策略的安全提示, 请运行以下命令:
    
  ```
  PS C:\> Set-HostedContentFilterPolicy -Identity "default" -InlineSafetyTipsEnabled $false
  ```

有关此 cmdlet 的详细信息, 请参阅[set-hostedcontentfilterpolicy](https://technet.microsoft.com/library/jj200781.aspx)。
    
## <a name="still-need-help"></a>是否仍需要帮助？
<a name="pshellsafetytip"> </a>

如果您禁用安全提示, 但仍在电子邮件中看到它们, 请检查以下内容:
  
- 无法对 web 上的 Outlook 禁用安全提示。 请尝试在另一个客户端 (如 Outlook) 中查看相同的电子邮件。
    
- 默认情况下, 每个使用 EOP 的用户都启用安全提示, 其中包括拥有 Office 365 的所有用户。 若要禁用电子邮件中显示的安全提示, 必须使用垃圾邮件筛选器策略禁用它们, 如本主题中所述。 设置完策略后, 请确保已启用该策略。 有关启用垃圾邮件筛选器策略的信息, 请参阅[配置垃圾邮件筛选器策略](https://technet.microsoft.com/library/jj200684.aspx)。
    
有关防御垃圾邮件和网络钓鱼的更多方法, 请参阅[Office 365 电子邮件反垃圾邮件保护](anti-spam-protection.md)。
  

