---
title: Microsoft Teams 會議室維護與作業
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 請閱讀本主題以瞭解管理Microsoft Teams 會議室。
ms.openlocfilehash: 2238712b269475891074016c1099a33c56004595
ms.sourcegitcommit: d2c76fe7705acf6e53f7673861671b1b018813dd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/13/2022
ms.locfileid: "62015043"
---
# <a name="microsoft-teams-rooms-maintenance-and-operations"></a>Microsoft Teams 會議室維護與作業
 
請閱讀本主題以瞭解管理Microsoft Teams 會議室。
  
Microsoft Teams 會議室是 Microsoft 的會議解決方案，專為將您的會議室轉換成豐富的共同合作體驗所設計。 使用者將享有熟悉的Microsoft Teams或商務用 Skype介面，IT 系統管理員會喜歡輕鬆部署和管理Windows 10 Teams 會議室應用程式。 Microsoft Teams 會議室是設計用來利用現有設備輕鬆安裝，Microsoft Teams或商務用 Skype會議室。
    
## <a name="collecting-logs-on-microsoft-teams-rooms"></a>收集記錄Microsoft Teams 會議室
<a name="Logs"> </a>

若要在系統管理中心Teams記錄，請前往 Teams **上的> Teams 會議室Windows。** 選取您想要記錄之裝置顯示名稱。 在上方面板中，選取 「下載裝置記錄」。 確認之後，記錄就會在幾分鐘後準備好在歷程記錄中下載。

您也可以使用 PowerShell 收集記錄。 您必須調用隨應用程式一起Microsoft Teams 會議室腳本。 在 [系統管理模式中](rooms-operations.md)，啟動提升的命令提示，併發出下列命令：
  
```PowerShell
powershell -ExecutionPolicy unrestricted c:\rigel\x64\scripts\provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
```

記錄會以 ZIP 檔案在 c：\rigel 中輸出。
  
## <a name="front-of-room-display-settings"></a>會議室顯示畫面設定
<a name="Display"> </a>

設定會議室前顯示畫面的設定 (，) 消費者電子 (CEC) 或啟用電腦模式。
  
如果您希望會議室前方的顯示器在從Teams 會議室模式喚醒時自動切換至會議室，則必須符合特定條件。 這項功能為選擇性，但Microsoft Teams 會議室支援，但基礎硬體支援此功能。 作為會議室前顯示器的消費者電視需要支援消費者電子 (CEC) HDMI 功能。  視選取的固定座或主機 (可能不支援 CEC，請參閱製造商支援檔) ，可能需要來自Crsron的 [HD-RX-201-C-E](https://www.crestron.com/Products/Video/HDMI-Solutions/HDMI-Extenders/HD-RX-201-C-E) 或 [Exron HD CTL 100](https://www.extron.com/article/hdctl100ad) 的控制器，才能啟用想要的行為。
  
## <a name="microsoft-teams-rooms-reset-factory-restore"></a>Microsoft Teams 會議室重設 (還原) 
<a name="Reset"> </a>

如果Microsoft Teams 會議室運作不佳，執行出廠重設可能會有所説明。 若要這麼做，請使用 Microsoft Teams[修復工具，](recovery-tool.md)並遵循出廠還原指示。

> [!NOTE]
> 如果 Microsoft Teams 會議室選取了保留我的檔案 - 移除應用程式與設定，但保留您的個人檔案選項，Windows無法使用已知問題。 請勿 *使用此選項* 。
  
## <a name="supported-remote-options"></a>支援的遠端選項
<a name="RemoteOptions"> </a>

下表摘要列出可能的遠端作業，以及您可以用於完成這些作業的方法。
  

|工作組|未加入網域|已加入網域|
|:-----|:-----|:-----|
|重新 啟動  <br/> |Teams系統管理中心  <br/> 遠端桌面  <br/> 遠端 PowerShell  <br/> | <br/>遠端桌面 (需要進一步)   <br/> 遠端 PowerShell (需要進一步)   <br/> Configuration Manager  <br/> |
|更新作業系統  <br/> |Windows更新  <br/> |Windows更新  <br/> WSUS  <br/> |
|應用程式更新  <br/> |Windows市  <br/> |Windows市  <br/> Configuration Manager  <br/> |
|帳戶配置  <br/> |Teams系統管理中心  <br/> |Teams系統管理中心  <br/> |
|存取記錄  <br/> |Teams系統管理中心  <br/> PowerShell  <br/> |Teams系統管理中心 <br/> PowerShell  <br/>  |
   
## <a name="configuring-group-policy-for-microsoft-teams-rooms"></a>為使用者群組原則Microsoft Teams 會議室
<a name="GroupPolicy"> </a>

本節涵蓋系統設定，Microsoft Teams 會議室系統設定以正常運作。 

將Teams 會議室到 Active Directory 網域提供下列優點：

- 網域加入Teams 會議室可讓您授予網域使用者和群組管理許可權。 如此一來，您就不需要記住本機電腦層級系統管理員帳戶密碼。

- 您可以部署Windows服務品質組Teams 會議室。

- 如果使用 商務用 Skype，加入網域Teams 會議室自動輸入貴組織的專用根憑證鏈。

當您將 Teams 會議室 加入網域時，您必須建立個別的組織單位 (OU) ，這樣您才能在所有 Teams 會議室 物件所在的 OU 中提供群組原則物件 (GPO) 排除。 停用所有 GPO 繼承，讓不支援的群組原則設定不會Teams 會議室。 在將使用者加入網域Teams 會議室在 OU 中建立電腦物件，以確保未將群組原則應用程式至預設電腦 OU。

> [!NOTE]
> 即使您建立個別的 OU 和封鎖繼承，某些群組原則如果設定了 No Override，也可能會造成問題。 具有 No Override 集的群組原則會以封鎖策略繼承集比對 OU。

許多組織都有下列 GPO，這會影響Teams 會議室功能。 確保您重寫或封鎖這些繼承：

  - 登入會話的超時 (自動鎖定) 
  - 與電源管理相關的政策
  - 需要其他驗證步驟
  - 拒絕存取本地磁片磁碟機
  - 提示使用者網路連接速度緩慢
  - 登入時啟動特定程式
  - 在所有加入網域的機器上建立另一個網域使用者帳戶。
  - 按 Windows 更新Teams 會議室

當您將Microsoft Teams 會議室網域時，請確保您的群組原則不會重寫下表中的設定。

|設定|允許|
|:-----|:-----|
|HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (REG_SZ) 1  <br/> |啟用Microsoft Teams 會議室啟動  <br/> |
|Power Management - \> 在 AC 上，在 10 分鐘後關閉螢幕  <br/> Power Management - \> 在 AC 上，永不讓系統進入睡眠狀態  <br/> |啟用Microsoft Teams 會議室關閉附加顯示器並自動喚醒  <br/> |
|net accounts /maxpwage：unlimited  <br/> 或是停用本地帳戶密碼到期的相同方式。 若無法這麼做，最終會導致Skype登入時抱怨密碼過期。 請注意，這會影響電腦上所有的本機帳戶，因此無法設定此設定也會造成方塊上的系統管理帳戶最後也會過期。  <br/> |讓Skype帳戶永遠登入  <br/> |

> [!NOTE]
> 當Microsoft Teams 會議室與下一版作業系統相容時，Windows 10更新Teams 會議室自動更新至下一Windows版本。 Microsoft Teams 會議室 不應透過 GPO 手動或啟用 Windows 商務用更新 (WUFB) 群群組原則，將 Windows 10 升級至下一版 Windows 10 Windows。 Teams 會議室啟用這些群組原則時，已知會遇到作業系統更新Windows 10問題。

## <a name="remote-management-using-powershell"></a>使用 PowerShell 進行遠端系統管理
<a name="RemotePS"> </a>

您可以使用 PowerShell 遠端執行下列管理作業 (請參閱下表中的腳本範例) ：
  
- 取得附加裝置
- 取得應用程式狀態
- 取得系統資訊
- 重新開機系統
- 取回記錄
- 傳輸檔案 (需要加入網域Microsoft Teams 會議室) 
    
> [!NOTE]
> 此功能預設為關閉。 您需要為系統上的環境啟用遠端 PowerShell，Microsoft Teams 會議室執行下列操作。 請參閱 **[Enable-PSRemoting 相關](/powershell/module/microsoft.powershell.core/enable-psremoting)** 檔，以瞭解如何啟用遠端 PowerShell。
  
例如，您可以啟用遠端 PowerShell，如下所示：
  
1. 在裝置上以系統管理員Microsoft Teams 會議室登錄。
2. 開啟提升的 PowerShell 命令提示。
3. 輸入下列命令： `Enable-PSRemoting -SkipNetworkProfileCheck -Force`
4. 開啟本地安全性原則，並新增 *系統管理員安全性群組* 至安全性設定  >  **策略**  >  **使用者許可權指派從** 網路存取  >  **此電腦**。

若要執行管理作業：
  
1. 使用擁有在裝置上執行 PowerShell 命令之許可權的帳號憑證，Microsoft Teams 會議室電腦。
2. 在 PC 上開啟一般 PowerShell 命令提示。
3. 從下表複製命令文字，然後貼到提示。
4. 以  `<Device fqdn>` 適合您環境的 FQDN 值取代欄位。
5. 以  *\<path\>*  主控設定檔或主題SkypeSettings.xml或主題 (的檔案名和) 。
    
若要取得附加裝置
  
```PowerShell
invoke-command {Write-Host "VIDEO DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Image"} | Format-Table Name,Status,Present; Write-Host "AUDIO DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Media"} | Format-Table Name,Status,Present; Write-Host "DISPLAY DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Monitor"} | Format-Table Name,Status,Present} -ComputerName <Device fqdn>
```

取得應用程式狀態
  
```PowerShell
invoke-command { $package = get-appxpackage -User Skype -Name Microsoft.SkypeRoomSystem; if ($package -eq $null) {Write-host "SkypeRoomSystems not installed."} else {write-host "SkypeRoomSystem Version : " $package.Version}; $process = Get-Process -Name "Microsoft.SkypeRoomSystem" -ErrorAction SilentlyContinue; if ($process -eq $null) {write-host "App not running."} else {$process | format-list StartTime,Responding}}  -ComputerName <Device fqdn>
```

取得系統資訊
  
```PowerShell
invoke-command {gwmi -Class Win32_ComputerSystem | Format-List PartOfDomain,Domain,Workgroup,Manufacturer,Model
gwmi -Class Win32_Bios | Format-List SerialNumber,SMBIOSBIOSVersion} -ComputerName <Device fqdn>
```

重新開機系統
  
```PowerShell
invoke-command { Shutdown /r /t 0 } -ComputerName <Device fqdn>
```

取回記錄
  
```PowerShell
$targetDevice = "<Device fqdn> "
$logFile = invoke-command {$output = Powershell.exe -ExecutionPolicy Bypass -File C:\Rigel\x64\Scripts\Provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
Get-ChildItem -Path C:\Rigel\*.zip | Sort-Object -Descending -Property LastWriteTime | Select-Object -First 1} -ComputerName $targetDevice
$session = new-pssession -ComputerName $targetDevice
Copy-Item -Path $logFile.FullName -Destination .\ -FromSession $session; invoke-command {remove-item -force C:\Rigel\*.zip} -ComputerName $targetDevice
```

將 XML 組 (或主題圖形) 
  
```XML
$movefile = "<path>";
$targetDevice = "\\<Device fqdn> \Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState\SkypeSettings.xml"; 
Copy-Item $movefile $targetDevice 
```

## <a name="software-updates"></a>軟體更新
<a name="SWupdate"> </a>

根據預設，Microsoft Teams 會議室嘗試連接到 Windows Store 以取得最新版 Microsoft Teams 會議室軟體。 因此，Teams 會議室需要一般網際網路存取。 在與 Microsoft 聯繫支援問題之前，Microsoft Teams 會議室載入最新版本的應用程式。
  
Microsoft Teams 會議室到更新Windows以取回作業系統和周邊裝置固件更新。 Teams會議室已配置為從當地時間上午 2：00 開始安裝。
  
如果您因為存取 Windows store 的限制而必須手動管理更新，因此無法遵循[商務用 Microsoft Store](https://businessstore.microsoft.com/store)發佈離線應用程式的一般程式，您可以從部署套件[ (](https://go.microsoft.com/fwlink/?linkid=851168) [](/microsoft-store/distribute-offline-apps)取得適當的 APPX 檔案和相依性，從設定[Microsoft Teams 會議室主機) ](console.md)與 Configuration Manager 一起使用。 部署套件發行會落在市面發行之後，因此可能無法一直符合最新的可用版本。
  
### <a name="to-update-using-powershell"></a>若要使用 PowerShell 進行更新

1. 從安裝 [MSI](https://go.microsoft.com/fwlink/?linkid=851168) 將套件解壓縮到裝置可以存取的共用。
2. 執行下列腳本，針對Microsoft Teams 會議室，並在適當時 \<share\> 變更為裝置共用：
    
    ```PowerShell
    Add-AppxPackage -Update -ForceApplicationShutdown -Path '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\*.appx' -DependencyPath (Get-ChildItem '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\Dependencies\x64\*.appx' | Foreach-Object {$_.FullName})
    ```

## <a name="admin-mode-and-device-management"></a>系統管理模式與裝置管理
<a name="AdminMode"> </a>

有些管理功能 ，例如手動安裝私人 CA 憑證，需要將Teams 會議室系統管理模式。 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running"></a>切換至系統管理模式，Microsoft Teams 會議室應用程式執行時返回

1. 掛斷任何進行中的通話，然後返回主畫面。
2. 選取齒輪圖示，然後顯示功能表 (**選項設定協助工具** 和重新開機 **裝置**) 。
3. 選取 **設定**。
4. 輸入系統管理員密碼。 系統會顯示設定畫面。  如果裝置未加入網域，系統預設會使用 (使用者名稱「系統管理」) 系統管理帳戶。 此帳戶的預設密碼是'sfb'。 請儘快變更此密碼。 如果電腦已加入網域，您可以使用適當許可權的網域帳戶來登錄。
5. 選取 **Windows 設定** 欄的儲存格。
6. 使用系統管理認證登入桌面。 您將擁有管理裝置的必要許可權。
7. 執行必要的系統管理工作。
8.  完成後，請重新開機電腦。
    
主機現在會回到其一般運作模式。 下列程式要求您在裝置上附加鍵盤 ，如果尚未附加鍵盤。 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-crashes"></a>切換至系統管理模式，當應用程式Microsoft Teams 會議室時返回

1. 連續Windows按五次按鍵。 這會將您帶到登入Windows畫面。 
2. 使用系統管理認證登入桌面。
3. 執行必要的系統管理工作。
4. 完成後，請重新開機電腦。

    > [!NOTE]
    > 這個方法不會將使用者登出Skype或正常終止應用程式，但若應用程式沒有回應，且無法使用其他方法，您還是會使用它。 

   主機會重新開機至其一般運作模式，執行 Microsoft Teams 會議室 App。 如果您附加鍵盤以完成此程式，您可以移除鍵盤。
   ## <a name="troubleshooting-tips"></a>疑難排解秘訣
   <a name="TS"> </a>

- 跨網域邊界時，可能不會顯示會議邀請 (例如兩家公司之間的) 。 在這種情況下，IT 系統管理員應決定是否允許外部使用者排程會議。 請參閱 PowerShell Cmdlet [Set-CalendarProcessing](/powershell/module/exchange/set-calendarprocessing)Exchange，特別是 'ProcessExternalMeetingMessages' 參數的文章。
- Microsoft Teams 會議室不支援透過 Exchange 2010 自動探索Exchange重新導向。
- 一般而言，IT 系統管理員可以停用他們不想使用的任何音訊端點。
- 如果會議室預覽中顯示鏡像影像，IT 系統管理員可以迴圈使用相機電源，或使用相機設定翻轉影像方向來修正問題。
- 已知會遺失主控台觸控螢幕存取權。 在這種情況下，問題有時會重新開機Teams 會議室。
- 已知透過有線輸入將電腦連接到主機時，會遺失當地音訊。 在這種情況下，重新開機電腦可以解決本地音訊播放問題。
