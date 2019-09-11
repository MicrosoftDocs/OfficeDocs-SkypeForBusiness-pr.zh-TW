---
title: Microsoft 團隊會議室維護和作業
ms.author: v-lanac
author: lanachin
ms.reviewer: sohailta
manager: serdars
ms.date: 5/10/2018
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection: M365-voice
localization_priority: Normal
description: 請閱讀本主題，以瞭解 Microsoft 團隊聊天室（即新一代 Skype 房間系統）的管理。
ms.openlocfilehash: f5c4cf2a7b0c5f8fc12d94553d6c0f77216d9487
ms.sourcegitcommit: dc151bf4454ddec20db5cd133a42a67599c08d64
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/11/2019
ms.locfileid: "36838075"
---
# <a name="microsoft-teams-rooms-maintenance-and-operations"></a>Microsoft 團隊會議室維護和作業 
 
請閱讀本主題，以瞭解 Microsoft 團隊聊天室（即新一代 Skype 房間系統）的管理。
  
Microsoft [團隊聊天室] 是 Microsoft 的最新會議解決方案，旨在將您的會議室轉換為豐富且共同合作的體驗。 使用者將享有其熟悉的 Microsoft 團隊或商務用 Skype 介面，IT 系統管理員會欣賞輕鬆部署和管理的 Windows 10 Skype 會議應用程式。 Microsoft [團隊聊天室] 的設計目的是利用 LCD 面板等現有的裝置，輕鬆安裝，讓 Microsoft 團隊或商務用 Skype 融入會議室。
  
有了其他設定，就可以使用 Microsoft Azure 監視器進行遠端系統管理，如在使用[Azure 監視器規劃 Microsoft 團隊聊天室管理](azure-monitor-plan.md)中所述，使用[Azure 監視器部署 microsoft 團隊聊天室](azure-monitor-deploy.md)管理、[管理使用 Azure 監視器的 Microsoft 團隊聊天室裝置](azure-monitor-deploy.md)。 您也可以[使用 XML 設定檔來遠端系統管理 Microsoft 團隊聊天室的主控台設定](xml-config-file.md)，包括套用自訂顯示主題。 
  
## <a name="collecting-logs-on-microsoft-teams-rooms"></a>在 Microsoft 團隊聊天室收集記錄
<a name="Logs"> </a>

若要收集記錄，您必須呼叫由 Microsoft 團隊聊天室應用程式隨附的記錄集合腳本。 在 [系統管理模式] 中，啟動提升許可權的命令提示字元，然後發出下列命令：
  
```
powershell -ExecutionPolicy unrestricted c:\rigel\x64\scripts\provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
```

在 c:\rigel. 中，會將記錄輸出為 ZIP 檔案
  
## <a name="front-of-room-display-settings"></a>房間顯示設定的正面
<a name="Display"> </a>

將會議室的正面顯示設定為 [延伸] 模式。 如此一來，就能確保當您重新開啟電源時，系統不會在該顯示器上複製主控台 UI。
  
> [!NOTE]
> 如果您希望在來源從待機模式喚醒時自動切換到活動影片來源（例如 MTR 主控台），必須符合某些條件。 此功能是選擇性的，但 Microsoft 團隊聊天室軟體支援，提供基礎硬體支援此功能。 在房間顯示中使用的消費者電視需要支援 HDMI 的消費電子產品控制（CEC）功能。  根據所選的 dock 或 console （可能不支援 CEC，請參閱製造商支援檔），您可能需要使用工作區控制器（例如[EXTRON HD CTL 100](https://www.extron.com/article/hdctl100ad) ）來啟用所需的行為。 
  
## <a name="microsoft-teams-rooms-reset-factory-restore"></a>Microsoft 團隊會議室重設（工廠還原）
<a name="Reset"> </a>

如果 Microsoft 團隊聊天室無法正常運作，可能會執行重設回原值。 這可以在 [**恢復**] 索引標籤上的 [設定] app 中完成。在 [**重設此電腦**] 底下，選取 [**開始**使用]，然後**移除所有專案**。 遵循其餘的提示來重設裝置。
  
> [!NOTE]
> 如果 [保留我的檔案] **：移除 app 和設定，但**在 Windows 重設程式期間已選取 [保留您的個人檔案] 選項，則 Microsoft 團隊聊天室可能無法使用的已知問題。 請勿_使用此_選項。
  
## <a name="supported-remote-options"></a>支援的遠端選項
<a name="RemoteOptions"> </a>

下表摘要列出可能的遠端作業，以及您可以用來完成它們的方法。
  

|工作組|未加入網域|已加入網域|
|:-----|:-----|:-----|
|重  <br/> |遠端桌面  <br/> 遠端 Powershell  <br/> |遠端桌面（需要進一步配置）  <br/> 遠端 Powershell （需要進一步配置）  <br/> SCCM  <br/> |
|更新作業系統  <br/> |Windows Update  <br/> |Windows Update  <br/> 結合  <br/> |
|App 更新  <br/> |Windows 網上商店  <br/> |Windows 網上商店  <br/> SCCM  <br/> |
|Skype 帳戶配置  <br/> |目前不支援  <br/> |目前不支援  <br/> |
|Access 記錄  <br/> |目前不支援  <br/> |目前不支援  <br/> |
   
## <a name="configuring-group-policy-for-microsoft-teams-rooms"></a>為 Microsoft 團隊聊天室設定群組原則
<a name="GroupPolicy"> </a>

本節涵蓋 Microsoft 團隊聊天室所依賴的系統設定，以正常運作。 當您將 Microsoft 團隊聊天室加入網域時，請確定您的群組原則不會覆寫下表中的設定。
  

|正在|讓|
|:-----|:-----|
|HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = （REG_SZ）1  <br/> |可讓 Microsoft 團隊聊天室啟動  <br/> |
|電源管理-\>在 AC 上，10分鐘後關閉螢幕  <br/> 電源管理-\>在交流電上，請勿將系統置於睡眠狀態  <br/> |讓 Microsoft 團隊聊天室關閉附加的顯示，並自動喚醒  <br/> |
|淨帳戶/maxpwage：無限制  <br/> 或同等的方式，在本機帳戶上停用密碼過期。 如果不這麼做，最終會導致 Skype 帳戶無法針對過期密碼登入。 請注意，這會影響電腦上的所有本機帳戶，因此無法設定這種情況，也會導致盒上的系統管理帳戶最終過期。  <br/> |讓 Skype 帳戶永遠登入  <br/> |
   
使用群組原則來傳送檔案將在 [[設定檔案專案](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx)] 中討論。

> [!NOTE]
> 當 Microsoft 團隊聊天室裝置與下一版的 Windows 10 OS 相容時，裝置會透過 Windows Update 自動更新至下一個版本。 Microsoft 團隊聊天室裝置不應升級至 Windows 10 的下一次發行，或透過啟用商務用 Windows Update （WUFB）群組原則，選取您想要接收之更新的 Windows 就緒層級，以及 [在預覽組建時選取] 和[透過 GPO 接收功能更新]。 已啟用這些群群組原則的裝置已知會遇到 Microsoft 小組聊天室 app 的 Windows 10 OS 更新問題。

## <a name="remote-management-using-powershell"></a>使用 PowerShell 進行遠端系統管理
<a name="RemotePS"> </a>

您可以使用 PowerShell 遠端執行下列管理作業（請參閱下表以取得腳本範例）：
  
- 取得連接的裝置
- 取得 app 狀態
- 取得系統資訊
- 重新開機系統
- 檢索記錄
- 傳輸檔案（需要加入網域的 Microsoft 團隊會議室）
    
> [!NOTE]
> 此功能預設為關閉。 您必須在 Microsoft 團隊聊天室系統上為您的環境啟用遠端 PowerShell，才能執行下列作業。 如需有關如何啟用遠端 PowerShell 的資訊，請參閱**[啟用-PSRemoting](https://technet.microsoft.com/library/hh849694.aspx)** 的相關檔。
  
例如，您可以啟用遠端 PowerShell，如下所示：
  
1. 以系統管理員身分登入 Microsoft 團隊聊天室裝置。
2. 開啟提升許可權的 PowerShell 命令提示字元。
3. 輸入下列命令： Enable-PSRemoting-force

若要執行管理作業：
  
1. 以具備在 Microsoft 團隊聊天室裝置上執行 PowerShell 命令許可權的帳號憑證登入電腦。
2. 在電腦上開啟一般的 PowerShell 命令提示字元。
3. 從下表複製命令文字，並在出現提示時貼上。
4. 以`<Device fqdn>`適合您環境的 FQDN 值取代欄位。
5. 以主 SkypeSettings 配置檔案（或主題圖像）的檔案名和本機路徑取代* \<路徑\> * 。
    
取得連接的裝置
  
```
invoke-command {Write-Host "VIDEO DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Image"} | Format-Table Name,Status,Present; Write-Host "AUDIO DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Media"} | Format-Table Name,Status,Present; Write-Host "DISPLAY DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Monitor"} | Format-Table Name,Status,Present} -ComputerName <Device fqdn>
```

取得 App 狀態
  
```
invoke-command { $package = get-appxpackage -User Skype -Name Microsoft.SkypeRoomSystem; if ($package -eq $null) {Write-host "SkypeRoomSystems not installed."} else {write-host "SkypeRoomSystem Version : " $package.Version}; $process = Get-Process -Name "Microsoft.SkypeRoomSystem" -ErrorAction SilentlyContinue; if ($process -eq $null) {write-host "App not running."} else {$process | format-list StartTime,Responding}}  -ComputerName <Device fqdn>
```

取得系統資訊
  
```
invoke-command {gwmi -Class Win32_ComputerSystem | Format-List PartOfDomain,Domain,Workgroup,Manufacturer,Model
gwmi -Class Win32_Bios | Format-List SerialNumber,SMBIOSBIOSVersion} -ComputerName <Device fqdn>
```

重新開機系統
  
```
invoke-command { Shutdown /r /t 0 } -ComputerName <Device fqdn>
```

檢索記錄
  
```
$targetDevice = "<Device fqdn> "
$logFile = invoke-command {$output = Powershell.exe -ExecutionPolicy Bypass -File C:\Rigel\x64\Scripts\Provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
Get-ChildItem -Path C:\Rigel\*.zip | Sort-Object -Descending -Property LastWriteTime | Select-Object -First 1} -ComputerName $targetDevice
$session = new-pssession -ComputerName $targetDevice
Copy-Item -Path $logFile.FullName -Destination .\ -FromSession $session; invoke-command {remove-item -force C:\Rigel\*.zip} -ComputerName $targetDevice
```

推入 XML 設定檔（或主題圖形）
  
```
$movefile = "<path>";
$targetDevice = "\\<Device fqdn> \Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState\SkypeSettings.xml"; 
Copy-Item $movefile $targetDevice 
```

## <a name="software-updates"></a>軟體更新
<a name="SWupdate"> </a>

根據預設，Microsoft 團隊聊天室會嘗試連線到 Windows 市集中，以取得最新版本的 Microsoft 團隊聊天室軟體，因此裝置需要進行一般的網際網路存取。 在與 Microsoft 取得支援問題之前，請務必先使用最新版本的 app 載入 Microsoft 團隊聊天室裝置。
  
根據預設，Microsoft 球隊聊天室會連線至 Windows Update，以檢索作業系統和 USB 週邊裝置固件更新，並將其安裝在已設定的商務時間以外。 您可以登入管理員帳戶並執行 [設定] 應用程式，來設定上班時間。
  
如果您想要手動管理更新，且無法遵循[Microsoft Store For Business](https://businessstore.microsoft.com/store) [發佈離線 app](https://docs.microsoft.com/microsoft-store/distribute-offline-apps)的一般程式，您可以從[部署套件](https://go.microsoft.com/fwlink/?linkid=851168)取得適當的 APPX 檔案和相依性（從設定可搭配 SCCM 使用的[Microsoft 團隊聊天室主控台](console.md)的指示。 部署套件版本滯後于商店發行版本本，因此可能不一定會與最新的可用組建相符。
  
### <a name="to-update-using-powershell"></a>使用 Powershell 更新

1. 從安裝[MSI](https://go.microsoft.com/fwlink/?linkid=851168)將套件解壓縮至裝置可以存取的共用。
2. 針對 Microsoft 團隊聊天室裝置執行下列腳本，視需要將\<共用\>變更為裝置共用：
    
```
Add-AppxPackage -Update -ForceApplicationShutdown -Path '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\*.appx' -DependencyPath (Get-ChildItem '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\Dependencies\x64\*.appx' | Foreach-Object {$_.FullName})
```

## <a name="admin-mode-and-device-management"></a>系統管理模式與裝置管理
<a name="AdminMode"> </a>

某些管理功能（例如手動安裝私人 CA 憑證）需要將 Surface Pro 裝置放在系統管理模式中。 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running"></a>當 Microsoft 團隊聊天室 app 執行時，切換到 [管理員模式] 並返回 [返回]

1. 掛斷任何正在進行的通話，然後返回主畫面。
2. 選取齒輪圖示並顯示功能表（選項為 [**設定**]、[**協助工具**] 和 [**重新開機裝置**]）。
3. 選取 [**設定**]。
4. 輸入系統管理員密碼。 [設定] 畫面隨即出現。  如果裝置未加入網域，則預設會使用本機系統管理帳戶（username "Admin"）。 此帳戶的預設密碼是 [sfb]，請儘快變更密碼。 如果電腦已加入網域，您可以使用適當許可權的網域帳戶登入。 
5. 選取左欄中的 [ **Windows 設定**]。
6. 選擇 [**移至系統管理員登入**]。
7. 輸入系統管理員密碼。 這會適當地登出應用程式，並將您帶到 Windows 登入畫面。 
8. 使用您的管理認證登入桌面。 您將擁有管理裝置所需的許可權。
9. 執行必要的管理工作。
10. 從管理員帳戶登出。
11. 選取畫面最左邊的 [使用者帳戶] 圖示，然後選取 [ **Skype**]，回到 Microsoft 團隊聊天室。
    
    如果沒有列出**Skype**使用者，您可能需要選取 [**其他使用者**]，然後輸入 **.\skype**做為使用者名稱，然後登入。
    
現在，主機會回到其正常操作模式。下列程式需要您在裝置上附加鍵盤（如果尚未連接的話）。 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-crashes"></a>當 Microsoft 小組聊天室 app 當機時切換至 [系統管理] 模式並返回回去

1. 快速連續按下 Windows 鍵五次。 這會將您帶到 Windows 登入畫面。 
2. 使用您的管理認證登入桌面。
3. 執行必要的管理工作。
4. 完成後，請重新開機電腦。

    > [!NOTE]
    > 這個方法不會記錄 Skype 使用者，或適當地終止應用程式，但如果應用程式沒有回應且其他方法無法使用，您就可以使用它。 

   主控台會重新開機至正常的操作模式，並執行 Microsoft 團隊聊天室 app。 如果您已附加鍵盤，您就可以移除它，以允許您執行此程式。
   ## <a name="troubleshooting-tips"></a>疑難排解提示
   <a name="TS"> </a>

- 在跨網域邊界傳送時，會議邀請可能不會出現（例如，在兩個公司之間）。 在這種情況下，IT 系統管理員應該決定是否要允許外部使用者排程會議。
- Microsoft 團隊聊天室不支援透過 Exchange 2010 的 Exchange 自動探索重新導向。
- 一般來說，IT 管理員要停用任何不想要使用的音訊端點是一個不錯的做法。
- 如果在會議室預覽中顯示鏡像影像，IT 系統管理員可以使用相機遙控器來重啟相機電源或翻轉影像方向來修正。
- 已已知失去主控台觸控式螢幕的存取權。 在這種情況下，可能會因重新開機 Microsoft 團隊聊天室系統來解決此問題。
- 透過有線攝取將電腦連線到主控台時，會遺失本機音訊。 在這種情況下，重新開機電腦可以解決本機音訊播放問題。
    
