---
title: 下載並安裝 Windows PowerShell 5.1
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: d739cd71-3c18-42ea-879f-b408bf53b1f4
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- PowerShell
- LIL_Placement
description: 下載、安裝並使用 Windows PowerShell 5.1 來建立連線至商務用 Skype Online 的遠端 PowerShell 會話。
ms.openlocfilehash: 227023d5c86b99a66ecdbdabd3b2973d0383a534
ms.sourcegitcommit: ac922addbc1422b5c41273a2e03196efb2ed7770
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41831147"
---
# <a name="download-and-install-windows-powershell-51"></a>下載並安裝 Windows PowerShell 5.1

如果您使用的是 Windows 10 年度更新版或 Windows Server 2016，您應該已經有 Windows PowerShell 5.1。 這是因為此應用程式是預先預先安裝了這些作業系統。
  
若要判斷您使用的是哪個版本的 Microsoft PowerShelll，請在您的 Windows 7 或 Windows Server 2008 R2 或 windows Server 2012 電腦上執行下列動作：
  
1. 按一下 [**開始**]，按一下 [**所有程式**]，按一下 [**附件**]，按一下 [ **Windows PowerShell**]，然後按一下 [ **windows powershell**]。
    
2. 在 PowerShell 主控台中，輸入下列命令，然後按 ENTER：
    
   ```PowerShell
   Get-Host | Select-Object Version
   ```

3. 類似下列的資訊應該會顯示在主控台視窗中：
    
    <pre>
    Version <BR>
    ------- <BR>
    4.0
    </pre>

    如果傳回的版本號碼是5.1，則您執行的是 Windows PowerShell 5.1。 如果傳回的版本號碼不是5.1，則您必須安裝 Windows PowerShell 5.1。 您可以從[Microsoft 下載中心](https://www.microsoft.com/en-us/download/details.aspx?id=54616)下載 Windows Management Framework 5.1 （包括 windows PowerShell 5.1）。
  
確認已安裝 Windows PowerShell 5.1 之後，您必須確認已針對執行遠端腳本將其設定為執行。 若要這樣做，請以系統管理員的身分啟動 PowerShell。 在 Windows 7、Windows Server 2008 R2、Windows Server 2012 或 Windows Server 2012 R2 上，請執行下列動作：
  
1. 按一下 [**開始**]，按一下 [**所有程式**]，按一下 [**附件**]，按一下 [ **windows powershell**]，以滑鼠右鍵按一下 [ **windows powershell**]，然後按一下 [**以系統管理員**身分
    
2. 如果出現 [**使用者帳戶控制**] 對話方塊，請按一下 [**是]** ，確認您要在 [管理員認證] 下執行 PowerShell。
    
如果您執行的是 Windows 8，請改為完成此程式：
  
1. 存取快速鍵列，按一下 [**搜尋**]，然後以滑鼠右鍵按一下 [ **Windows PowerShell**]。 您可以在任何 Windows 8 電腦（觸控式螢幕或非觸控式螢幕）上快速存取快速鍵列，方法是按住 Windows 鍵，然後按 C。
    
2. 在畫面底部的工具列中，按一下 [**以系統管理員身分執行**]。
    
3. 如果出現 [**使用者帳戶控制**] 對話方塊，請按一下 [**是]** ，確認您要在 [管理員認證] 下執行 PowerShell。
    
PowerShell 執行之後，您必須變更執行原則，以允許執行遠端腳本。 在 PowerShell 主控台中，輸入下列命令，然後按 ENTER：
```PowerShell
Set-ExecutionPolicy RemoteSigned -Force
```
   
 
> [!NOTE]
> 當您執行上述命令時，您可能會收到下列錯誤訊息： >*設定-ExecutionPolicy：無法存取登錄機碼 "HKEY_LOCAL_MACHINE\\軟體\\Microsoft\\PowerShell\\1\\ShellIds\\Micrsoft"。* 如果您不是在 [管理員認證] 下執行 PowerShell，通常會發生此錯誤訊息。 關閉您的 PowerShell 會話，然後以系統管理員的身分開始新的會話。
 
若要確認是否已正確設定執行原則，請在 PowerShell 提示輸入以下內容，然後按 ENTER 鍵：
  
```PowerShell
Get-ExecutionPolicy
```

如果您傳回下列值，所有內容都已正確設定：
  
`RemoteSigned`

如果您目前未執行 Windows PowerShell 5.1，您也需要從 Microsoft 下載中心下載並安裝 Windows Management Framework 5.1。 這是包含 Windows PowerShell 5.1 和 Windows 遠端系統管理（WinRM）3.0 的安裝套件。 例如，如果您執行的是 Windows 7 SP1，且尚未更新為 Windows PowerShell 5.1，可能需要此安裝套件。 如果您執行的是 Windows Server 2016 或 Windows 10 周年紀念更新，就不需要安裝 Windows PowerShell 5.1。 Windows PowerShell 5.1 已預先安裝在這些作業系統上。
  
安裝 Windows Management Framework 5.1 之前：
  
- 請確定您已下載正確版本的安裝套件。 如果您執行的是64位版本的 Windows 7 SP1，請下載檔案 Win7AndW2K8R2-KB3191566-x64。 如果您執行的是32位版本的 Windows 7，請下載檔案 Win7-KB3191566-x86。
    
- 如果您在電腦上執行 Windows 7，請確認您已安裝 Windows 7 Service Pack 1。

如果不確定您執行的是哪個 Windows 版本，或者不確定您是否已安裝 Windows 7 Service Pack 1，請按一下 [**開始**]，以滑鼠右鍵按一下 [**電腦**]，然後按一下 [**屬性**]。 此資訊將會在 [系統] 對話方塊中報告。
  
若要安裝 Windows Management Framework 5.1，請完成[安裝和設定 WMF 5.1](https://docs.microsoft.com/powershell/scripting/wmf/setup/install-configure)中的程式。
  
重新開機電腦之後，請確認 Windows PowerShell 可以啟動，而且該應用程式可以在 [管理認證] 下執行。 若要執行此動作：
  
1. 按一下 [**開始**]，按一下 [**所有程式**]，按一下 [**附件**]，按一下 [ **windows powershell**]，以滑鼠右鍵按一下 [ **windows powershell** ]，然後按一下 [**以系統管理員**
    
2. 如果出現 [使用者帳戶控制] 對話方塊，請按一下 [**是]** ，確認您要在 [管理員認證] 下執行 PowerShell。
    
PowerShell 主控台出現後，您應該確認 WinRM 服務正在執行且已正確設定。 若要確認服務正在執行，請在 PowerShell 提示輸入下列命令，然後按 ENTER：
  
```PowerShell
Get-Service winrm
```

隨後就會在螢幕上顯示 WinRM 服務的相關資訊：
  
<pre>
Status   Name               DisplayName
------   ----               -----------
Running  winrm              Windows Remote Management (WS-Manag...
</pre>

如果服務狀態不等於「正在執行」，請輸入下列命令以啟動 WinRM 服務，然後按 ENTER：
  
```PowerShell
Start-Service winrm
```

在服務啟動後，請執行下列命令，以確認 WinRM 使用的是基本驗證：
  
```PowerShell
winrm set winrm/config/client/auth '@{Basic="True"}'
```

類似下列的資訊將會顯示在螢幕上：
  
<pre>
Auth
    Basic = true
    Digest = true
    Kerberos = true
    Negotiate = true
    Certificate = true
    CredSSP = false
</pre>

如果基本驗證已設定為 true，就表示您已經準備好使用 PowerShell 連線到商務用 Skype Online。
  
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a>相關主題
[設定 Windows PowerShell 電腦](set-up-your-computer-for-windows-powershell.md) 

  
 
