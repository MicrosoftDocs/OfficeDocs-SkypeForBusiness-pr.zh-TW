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
description: 下載、安裝，然後使用 Windows PowerShell 5.1 建立連線至商務用 Skype Online 的遠端 PowerShell 會話。
ms.openlocfilehash: ed719a2df084c968c622a54fe145647b2d7b7aa8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120332"
---
# <a name="download-and-install-windows-powershell-51"></a>下載並安裝 Windows PowerShell 5.1

如果您使用的是 Windows 10 周年紀念更新或 Windows Server 2016，您應該已經擁有 Windows PowerShell 5.1。 這是因為此應用程式預先安裝于這些作業系統中。
  
若要判斷您使用的是哪個版本的 Microsoft PowerShelll，請于 Windows 7 或 Windows Server 2008 R2 或 Windows Server 2012 電腦上執行下列操作：
  
1. 按一下 **[開始**，**按一下所有程式**，按一下 **配件**，按一下 **Windows PowerShell，** 然後按一下 **Windows PowerShell。**
    
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

    如果退回的版本號碼是 5.1，則您正進行 Windows PowerShell 5.1。 如果退回的版本號碼不是 5.1，則您必須安裝 Windows PowerShell 5.1。 您可以從 Microsoft 下載中心下載 Windows 管理架構 5.1 ，包括 [Windows](https://www.microsoft.com/download/details.aspx?id=54616)PowerShell 5.1。
  
確認已安裝 Windows PowerShell 5.1 之後，您必須確定已針對執行遠端腳本已針對 PowerShell 進行配置。 若要這麼做，請以系統管理員的一個角色啟動 PowerShell。 在 Windows 7、Windows Server 2008 R2、Windows Server 2012 或 Windows Server 2012 R2 上執行下列操作：
  
1. 按一下 **[開始**，**按一下所有** 程式，按一下配件，按一下 **Windows PowerShell，** 以滑鼠右鍵按一下 **Windows PowerShell，** 然後按一下 [**以系統管理員的執行**> 。
    
2. 如果出現 **[使用者帳戶控制>** 對話方塊，請按一下 [是」，確認您想要在系統管理員認證下執行 PowerShell。
    
如果您執行 Windows 8，請改為完成此程式：
  
1. 存取 [按鈕欄，按一下 **[搜尋**，然後以滑鼠右 **鍵按一下 Windows PowerShell。** 您可以按住 Windows 鍵並按 C，在任何 Windows 8 電腦上 (觸控式螢幕或非觸控式螢幕) 快速存取圖示列。
    
2. 在畫面底部的工具列中，按一下 [ **以系統管理員的執行**> 。
    
3. 如果出現 **[使用者帳戶控制>** 對話方塊，請按一下 [是」，確認您想要在系統管理員認證下執行 PowerShell。
    
執行 PowerShell 之後，您必須變更執行策略，允許執行遠端腳本。 在 PowerShell 主控台中，輸入下列命令，然後按 ENTER：
```PowerShell
Set-ExecutionPolicy RemoteSigned -Force
```
   
 
> [!NOTE]
> 執行上述命令時，您可能會收到下列錯誤訊息：> *Set-ExecutionPolicy：拒絕對註冊表鍵的存取權HKEY_LOCAL_MACHINE \\ SOFTWARE \\ Microsoft \\ PowerShell \\ 1 \\ ShellIds \\ Micrsoft.PowerShell'* 遭到拒絕。 如果您沒有在系統管理員認證下執行 PowerShell，通常會發生此錯誤訊息。 關閉 PowerShell 會話，然後以系統管理員的一個角色開始新的會話。
 
若要確認執行策略已正確配置，請在 PowerShell 提示符中輸入下列專案，然後按 ENTER：
  
```PowerShell
Get-ExecutionPolicy
```

如果您返回下列值，則所有專案已正確配置：
  
`RemoteSigned`

如果您目前並未執行 Windows PowerShell 5.1，您也需要從 Microsoft 下載中心下載並安裝 Windows 管理架構 5.1。 此安裝套件包含 Windows PowerShell 5.1 和 Windows Remote Management (WinRM) 3.0。 例如，如果您執行 Windows 7 SP1 且尚未更新至 Windows PowerShell 5.1，可能需要此安裝套件。 如果您執行 Windows Server 2016 或 Windows 10 周年紀念更新，則不需要安裝 Windows PowerShell 5.1。 Windows PowerShell 5.1 已預先安裝于這些作業系統上。
  
安裝 Windows 管理架構 5.1 之前：
  
- 請確定您下載的安裝套件版本正確無誤。 如果您正使用 64 位版本的 Windows 7 SP1，請下載Win7AndW2K8R2-KB3191566-x64.ZIP。 如果您正使用 32 位版本的 Windows 7，請下載Win7-KB3191566-x86.ZIP。
    
- 如果您在電腦上進行 Windows 7，請確定已安裝 Windows 7 Service Pack 1。

如果您不確定您目前運行的 Windows 版本，或不確定您是否已安裝 Windows 7 Service Pack 1，請按一下 [開始，以滑鼠按右鍵 **電腦**，然後按一下 [**內容**>。 這項資訊將在 [系統」 對話方塊中報告。
  
若要安裝 Windows 管理架構 5.1，請完成安裝及設定 [WMF 5.1 中的程式](/powershell/scripting/wmf/setup/install-configure)。
  
電腦重新開機之後，請確認 Windows PowerShell 可以啟動，且應用程式可以在系統管理認證下執行。 若要這麼做：
  
1. 按一下 **[開始**，**按一下所有** 程式，按一下配件，按一下 **Windows PowerShell，** 以滑鼠右鍵按一下 **Windows PowerShell，** 然後按一下 [**以系統管理員的執行**> 。
    
2. 如果出現 [使用者帳戶控制> 對話方塊，請按一下 [是」，確認您想要在系統管理員認證下執行 PowerShell。
    
當 PowerShell 主控台出現時，您應該確認 WinRM 服務已執行且已正確配置。 若要確認服務是否執行，請在 PowerShell 提示處輸入下列命令，然後按 ENTER：
  
```PowerShell
Get-Service winrm
```

WinRM 服務相關資訊隨即會顯示在螢幕上：
  
<pre>
Status   Name               DisplayName
------   ----               -----------
Running  winrm              Windows Remote Management (WS-Manag...
</pre>

如果服務狀態不等於 「執行中」，請輸入下列命令，然後按 ENTER 以啟動 WinRM 服務：
  
```PowerShell
Start-Service winrm
```

服務啟動之後，請執行下列命令，確認 WinRM 使用基本驗證：
  
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

如果基本驗證已設定為 True，表示您已準備好使用 PowerShell 連線到商務用 Skype Online。
  
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a>相關主題
[設定 Windows PowerShell 電腦](set-up-your-computer-for-windows-powershell.md) 

  
