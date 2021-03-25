---
title: Microsoft Teams 會議室的維護與作業
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
localization_priority: Normal
description: 請閱讀本主題以瞭解新一代 Skype 會議室系統 Microsoft Teams 會議室的管理。
ms.openlocfilehash: 52234f72c380c4f5af8f47fff51998fa8c3d1459
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117431"
---
# <a name="microsoft-teams-rooms-maintenance-and-operations"></a>Microsoft Teams 會議室的維護與作業 
 
請閱讀本主題以瞭解新一代 Skype 會議室系統 Microsoft Teams 會議室的管理。
  
Microsoft Teams 會議室是 Microsoft 的最新會議解決方案，專為將您的會議室轉換成豐富、共同合作的體驗所設計。 使用者將享有熟悉的 Microsoft Teams 或商務用 Skype 介面，IT 系統管理員會感謝輕鬆部署和管理的 Windows 10 Skype 會議應用程式。 Microsoft Teams 會議室是設計用來利用現有設備 ，例如LCD 面板，方便安裝，將 Microsoft Teams 或商務用 Skype 帶進您的會議室。
  
有了其他組組，使用 Microsoft Azure 監視器進行遠端系統管理是可能的，如使用 Azure 監視器規劃 [Microsoft Teams](azure-monitor-plan.md)會議室管理、使用 Azure 監視器部署 Microsoft Teams 會議室管理、使用 Azure 監視器管理 Microsoft [Teams](azure-monitor-deploy.md)會議室 [裝置](azure-monitor-deploy.md)中所述。 您也可以使用 [XML](xml-config-file.md)設定檔遠端系統管理 Microsoft Teams 會議室主控台設定，包括使用自訂顯示主題。 
  
## <a name="collecting-logs-on-microsoft-teams-rooms"></a>收集 Microsoft Teams 會議室的記錄
<a name="Logs"> </a>

若要收集記錄，您必須使用 Microsoft Teams 會議室應用程式所提供之記錄集合腳本。 在系統管理模式中，啟動提升的命令提示，併發出下列命令：
  
```PowerShell
powershell -ExecutionPolicy unrestricted c:\rigel\x64\scripts\provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
```

記錄會以 c：\rigel 的 ZIP 檔案輸出。
  
## <a name="front-of-room-display-settings"></a>會議室顯示設定前面
<a name="Display"> </a>

將會議室前方顯示設定為延伸模式。 這麼做可確保當您在顯示器上迴圈使用電源時，主控台 UI 不會重複于該顯示器上。
  
> [!NOTE]
> 如果您希望會議室前方的顯示器自動切換到使用中的視 (例如當來源從待命模式喚醒時) 則必須符合某些條件。 這項功能是選擇性的，但 Microsoft Teams 會議室軟體支援此功能，提供基礎硬體支援此功能。 作為會議室前顯示器的消費者電視需要支援消費者電子 (CEC) HDMI 功能。  視選取的固定座或主機 (可能不支援 CEC，請參閱製造商支援檔) ，可能需要來自Crsron的 [HD-RX-201-C-E](https://www.crestron.com/Products/Video/HDMI-Solutions/HDMI-Extenders/HD-RX-201-C-E) 或 Exron 的 [Exron HD CTL 100](https://www.extron.com/article/hdctl100ad) 控制器，才能啟用想要的行為。 
  
## <a name="microsoft-teams-rooms-reset-factory-restore"></a>Microsoft Teams 會議室重設 (還原) 
<a name="Reset"> </a>

如果 Microsoft Teams 會議室運作不佳，執行出廠重設可能會有所説明。 若要這麼做，請使用 [Microsoft Teams 會議室修復工具，](recovery-tool.md) 並遵循出廠還原指示。

> [!NOTE]
> 如果 Windows 重設程式期間已選取了保留我的檔案 **- 移除** 應用程式與設定，但保留您的個人檔案選項，Microsoft Teams 會議室可能會無法使用的已知問題。 請勿 *使用此選項* 。
  
## <a name="supported-remote-options"></a>支援的遠端選項
<a name="RemoteOptions"> </a>

下表摘要列出可能的遠端作業，以及您可以用於完成這些作業的方法。
  

|工作組|未加入網域|已加入網域|
|:-----|:-----|:-----|
|重新 啟動  <br/> |Teams 系統管理中心  <br/> 遠端桌面  <br/> 遠端 Powershell  <br/> | <br/>遠端桌面 (需要進一步)   <br/> 遠端 Powershell (需要進一步)   <br/> Configuration Manager  <br/> |
|更新作業系統  <br/> |Windows Update  <br/> |Windows Update  <br/> WSUS  <br/> |
|應用程式更新  <br/> |Windows 市  <br/> |Windows 市  <br/> Configuration Manager  <br/> |
|帳戶配置  <br/> |Teams 系統管理中心  <br/> |Teams 系統管理中心  <br/> |
|存取記錄  <br/> |Teams 系統管理中心  <br/> |Teams 系統管理中心 <br/> |
   
## <a name="configuring-group-policy-for-microsoft-teams-rooms"></a>為 Microsoft Teams 會議室群組原則
<a name="GroupPolicy"> </a>

本節涵蓋 Microsoft Teams 會議室要正常運作所依賴的系統設定。 將 Microsoft Teams 會議室加入網域時，請確保您的群組原則不會重寫下表中的設定。
  

|設定|允許|
|:-----|:-----|
|HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (REG_SZ) 1  <br/> |啟用 Microsoft Teams 會議室啟動  <br/> |
|Power Management - \> 在 AC 上，在 10 分鐘後關閉螢幕  <br/> Power Management - \> 在 AC 上，永不讓系統進入睡眠狀態  <br/> |讓 Microsoft Teams 會議室關閉附加的顯示器並自動喚醒  <br/> |
|net accounts /maxpwage：unlimited  <br/> 或是停用本地帳戶密碼到期的相同方式。 如果不這麼做，最終會導致 Skype 帳戶無法登入抱怨密碼過期。 請注意，這會影響電腦上所有的本機帳戶，因此無法設定此設定也會造成方塊上的系統管理帳戶最後也會過期。  <br/> |讓 Skype 帳戶永遠登入  <br/> |
   
使用群組原則傳輸檔案在設定檔案專案 [中會進行討論](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc772536(v=ws.11))。

> [!NOTE]
> 當 Microsoft Teams 會議室裝置與下一版的 Windows 10 作業系統相容時，裝置會透過 Windows Update 自動更新至下一個版本。 Microsoft Teams 會議室裝置不應透過 GPO 手動或啟用商務用 Windows Update (WUFB) 群群組原則「選取您想要接收的更新的 Windows 就緒等級」和「選取何時收到預覽版建立及功能更新」，以升級到 Windows 10 的下一版。 已知啟用這些群組原則的裝置會遇到 Microsoft Teams 會議室應用程式 Windows 10 OS 更新的問題。

## <a name="remote-management-using-powershell"></a>使用 PowerShell 進行遠端系統管理
<a name="RemotePS"> </a>

您可以使用 PowerShell 遠端執行下列管理作業 (請參閱下表中的腳本範例) ：
  
- 取得附加裝置
- 取得應用程式狀態
- 取得系統資訊
- 重新開機系統
- 取回記錄
- 傳輸檔案 (需要加入網域的 Microsoft Teams 會議室) 
    
> [!NOTE]
> 此功能預設為關閉。 您需要在 Microsoft Teams 會議室系統上為環境啟用遠端 PowerShell，才能執行下列操作。 請參閱 **[Enable-PSRemoting 相關](/powershell/module/microsoft.powershell.core/enable-psremoting)** 檔，以瞭解如何啟用遠端 PowerShell。
  
例如，您可以啟用遠端 PowerShell，如下所示：
  
1. 在 Microsoft Teams 會議室裝置上以系統管理員的登錄。
2. 開啟提升的 PowerShell 命令提示。
3. 輸入下列命令： `Enable-PSRemoting -SkipNetworkProfileCheck -Force`
4. 開啟本地安全性原則，並新增 *系統管理員* 安全性組至安全性設定  >  **Local Policy**  >  **User Rights Assignment Access**  >  **此電腦從網路**。

若要執行管理作業：
  
1. 使用帳號憑證，具有在 Microsoft Teams 會議室裝置上執行 PowerShell 命令的許可權，來登錄電腦。
2. 在 PC 上開啟一般 PowerShell 命令提示。
3. 從下表複製命令文字，然後貼到提示。
4. 以  `<Device fqdn>` 適合您環境的 FQDN 值取代欄位。
5. 以  *\<path\>*  主控畫面的檔案名和本地路徑取代SkypeSettings.xml或主題 (圖像) 。
    
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

按 XML 組 (或主題圖形) 
  
```XML
$movefile = "<path>";
$targetDevice = "\\<Device fqdn> \Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState\SkypeSettings.xml"; 
Copy-Item $movefile $targetDevice 
```

## <a name="software-updates"></a>軟體更新
<a name="SWupdate"> </a>

根據預設，Microsoft Teams 會議室會嘗試連接到 Windows Store 以取得最新版的 Microsoft Teams 會議室軟體，因此裝置需要一般網際網路存取。 在與 Microsoft 聯繫支援問題之前，請務必先將 Microsoft Teams 會議室裝置載入最新版本的應用程式。
  
根據預設，Microsoft Teams 會議室會連接到 Windows Update 以取回作業系統和 USB 周邊裝置固件更新，並安裝于已配置的上班時間以外。 您可以登錄系統管理員帳戶並執行設定應用程式來設定上班時間。
  
如果您想要手動管理更新，而且無法遵循商務用 Microsoft Store 發佈離線應用程式的正常程式，可以從部署[](/microsoft-store/distribute-offline-apps)套件[ (](https://go.microsoft.com/fwlink/?linkid=851168)取得適用于 Configuration Manager 的 Microsoft [Teams](https://businessstore.microsoft.com/store)會議室主控台) 的指示中適當的[APPX](console.md)檔案和相依性。 部署套件發行會落在市面發行之後，因此可能無法一直符合最新的可用版本。
  
### <a name="to-update-using-powershell"></a>若要使用 Powershell 進行更新

1. 從安裝 [MSI](https://go.microsoft.com/fwlink/?linkid=851168) 將套件解壓縮到裝置可以存取的共用。
2. 針對 Microsoft Teams 會議室裝置執行下列腳本，視需要變更 \<share\> 為裝置共用：
    
    ```PowerShell
    Add-AppxPackage -Update -ForceApplicationShutdown -Path '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\*.appx' -DependencyPath (Get-ChildItem '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\Dependencies\x64\*.appx' | Foreach-Object {$_.FullName})
    ```

## <a name="admin-mode-and-device-management"></a>系統管理模式與裝置管理
<a name="AdminMode"> </a>

有些管理功能 ，例如手動安裝私人 CA 憑證，需要將 Surface Pro 裝置置於系統管理模式。 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running"></a>當 Microsoft Teams 會議室應用程式執行時切換回系統管理模式

1. 掛斷任何進行中的通話，然後返回主畫面。
2. 選取齒輪圖示，然後顯示功能表 **(選項為** 設定、協助工具和 **重新開機裝置**) 。 
3. 選取 **設定**。
4. 輸入系統管理員密碼。 系統會顯示設定畫面。  如果裝置未加入網域，系統預設會使用 (使用者名稱「系統管理」) 系統管理帳戶。 此帳戶的預設密碼是'sfb'，請儘快變更密碼。 如果電腦已加入網域，您可以使用適當許可權的網域帳戶來登錄。 
5. 選取 **左欄中** 的 Windows 設定。
6. 選擇 **前往系統管理登錄**。
7. 輸入系統管理員密碼。 這會正常登出應用程式，並帶您到 Windows 登入畫面。 
8. 使用系統管理認證登入桌面。 您將擁有管理裝置的必要許可權。
9. 執行必要的系統管理工作。
10. 從系統管理帳戶登出。
11. 選取畫面最左側的使用者帳戶圖示，然後選取 **Skype，** 以返回 Microsoft Teams 會議室。
    
    如果未 **列出 Skype** 使用者，您可能必須選取其他使用者，然後輸入 **.\skype** 做為使用者名稱，然後進行登錄。
    
主機現在會回到其一般運作模式。下列程式要求您在裝置上附加鍵盤 ，如果尚未附加鍵盤。 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-crashes"></a>當 Microsoft Teams 會議室應用程式當機時切換回系統管理模式

1. 連續連續按五次 Windows 鍵。 這會將您帶到 Windows 登入畫面。 
2. 使用系統管理認證登入桌面。
3. 執行必要的系統管理工作。
4. 完成後，請重新開機電腦。

    > [!NOTE]
    > 這個方法不會將 Skype 使用者登出或正常終止應用程式，但若應用程式沒有回應，且無法使用其他方法，您還是會使用它。 

   主機會重新開機至一般運作模式，執行 Microsoft Teams 會議室應用程式。 您可以移除鍵盤 ，如果鍵盤已附加，讓您執行此程式。
   ## <a name="troubleshooting-tips"></a>疑難排解秘訣
   <a name="TS"> </a>

- 跨網域邊界時可能不會顯示會議邀請 (例如，兩家公司之間的) 。 在這種情況下，IT 系統管理員應決定是否允許外部使用者排程會議。
- Microsoft Teams 會議室不支援透過 Exchange 2010 自動探索重新導向。
- 一般而言，IT 系統管理員可以停用他們不想使用的任何音訊端點。
- 如果會議室預覽中顯示鏡像影像，IT 系統管理員可以使用相機遙控器來切換相機電源或翻轉影像方向，以修正問題。
- 已知會遺失主控台觸控螢幕存取權。 在這種情況下，此問題有時會重新開機 Microsoft Teams 會議室系統來解決。
- 已知透過有線輸入將電腦連接到主機時，會遺失當地音訊。 在這種情況下，重新開機電腦可以解決本地音訊播放問題。
