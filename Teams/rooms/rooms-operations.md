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
- Teams_ITAdmin_Rooms
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 瞭解管理Microsoft Teams 會議室。
ms.openlocfilehash: 93a4c2ff7d9c6a1f982a06ec8df6dabf790f8739
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2022
ms.locfileid: "67272218"
---
# <a name="microsoft-teams-rooms-maintenance-and-operations"></a>Microsoft Teams 會議室維護與作業
 
 
Microsoft Teams 會議室是 Microsoft 的會議解決方案，旨在將會議室轉換成豐富的共同作業體驗。 使用者將享有熟悉的 Microsoft Teams 或商務用 Skype介面，而且 IT 系統管理員將會喜歡輕鬆部署和管理Windows 10 Teams 會議室應用程式。 Microsoft Teams 會議室是設計用來利用現有設備輕鬆安裝，將 Microsoft Teams 或商務用 Skype帶入會議室。
    
## <a name="collecting-logs-on-microsoft-teams-rooms"></a>收集 Microsoft Teams 會議室 上的記錄
<a name="Logs"> </a>

若要在 Teams 系統管理中心收集記錄，請移至 **Windows 上的 Teams 裝置> Teams 會議室**。 選取您要記錄檔之裝置的顯示名稱。 在頂端面板中，選取 [下載裝置記錄檔]。 確認之後，記錄檔將在幾分鐘後於 [歷程記錄] 索引標籤中準備下載。

您也可以使用 PowerShell 來收集記錄。 您必須叫用隨附于 Microsoft Teams 會議室 應用程式的記錄收集腳本。 在[管理員模式中](rooms-operations.md)，啟動提升許可權的命令提示字元，併發出下列命令：
  
```PowerShell
powershell -ExecutionPolicy unrestricted c:\rigel\x64\scripts\provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
```

記錄檔會在 c：\rigel 中輸出為 ZIP 檔案。

### <a name="managing-disk-space"></a>管理磁碟空間
<a name="Space"> </a>

裝置上下載的記錄可能會佔用磁碟空間。 如果記錄檔未定期清理，可能會干擾聊天室的一般功能。 Teams 會議室刪除 30 天后下載的記錄。 IT 系統管理員可以使用裝置登錄設定覆寫記錄清理。

|設定|允許|
|:-----|:-----|
|HKLM\SOFTWARE\Microsoft\PPI\SkypeSettings\LogCleanupAgeThreshold  <br/> |在 30 天后清理記錄檔。  <br/> |
  
## <a name="front-of-room-display-settings"></a>[會議室] 前方的顯示設定
<a name="Display"> </a>

設定 [會議室前方] 顯示器的設定 () ，以支援消費者電子產品控制 (CEC) 或啟用電腦模式。
  
如果您想要在會議室前方顯示器從待命模式喚醒時自動切換到Teams 會議室，則必須符合特定條件。 此功能為選用，但Microsoft Teams 會議室軟體支援，但基礎硬體支援此功能。 做為會議室前方顯示器的消費者電視需要支援消費者電子產品控制 (CEC) HDMI 功能。  視選取的擴充座或主機 (可能不支援 CEC 而定，請參閱製造商支援檔) ，可能需要來自 Cres 要的 [HD-RX-201-C-E](https://www.crestron.com/Products/Video/HDMI-Solutions/HDMI-Extenders/HD-RX-201-C-E) 或 [Excelor HD CTL 100](https://www.extron.com/article/hdctl100ad) 等控制器，才能啟用所需的行為。

### <a name="scale-and-resolution"></a>縮放比例和解析度

若要取得Teams 會議室設計體驗，您的 [會議室前方] 顯示器必須符合解析度和縮放比例需求。

若要設定遠端顯示 [會議室前方] 的縮放比例和解析度，請參閱使用[XML 組態檔遠端系統管理Microsoft Teams 會議室主機設定](xml-config-file.md#set-front-of-room-scale-and-resolution)。

若要在 Teams 會議室系統管理設定中手動設定縮放比例和解析度：

1. 在 Teams 會議室中，切換至 [系統管理模式](#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running)

2. 選取 [開始] 圖示。 然後 **[設定] > [系統>顯示器]**

3. 移至 [ **縮放比例與版面配置**]，然後 **變更文字、應用程式及其他專案的大小**，並將縮放比例設為 100%。

4. 將顯示器解析度設定為 1080p。 如果您有雙螢幕，請設定兩個螢幕的縮放比例和解析度。

5. 接下來，選取 [開始] 圖示，然後輸入 **命令提示字元**。 選 **取 [以系統管理員身分執行]**。

6. 執行下列命令：

```cmdlet
 Powershell -ExecutionPolicy Unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentDisplayScaling.ps1 
```

7. 重新開機裝置。
  
## <a name="microsoft-teams-rooms-reset-factory-restore"></a>Microsoft Teams 會議室重設 (原廠還原) 
<a name="Reset"> </a>

如果Microsoft Teams 會議室無法順利執行，執行原廠重設可能會有説明。 若要這麼做，請使用 [Microsoft Teams 會議室復原工具](recovery-tool.md) ，並依照原廠還原指示進行。

> [!NOTE]
> 在已知的問題中，如果 [**保留我的檔案 - 移除應用程式和設定]，但** Windows 重設程式期間選取了 [保留您的個人檔案] 選項，Microsoft Teams 會議室會變得無法使用。 *請勿* 使用此選項。
  
## <a name="supported-remote-options"></a>支援的遠端選項
<a name="RemoteOptions"> </a>

下表摘要列出可能的遠端作業，以及您可以用來完成這些作業的方法。
  

|工作組|未加入網域|加入網域|
|:-----|:-----|:-----|
|重新 啟動  <br/> |Teams 系統管理中心  <br/> 遠端桌面  <br/> 遠端 PowerShell  <br/> | <br/>遠端桌面 (需要進一步的設定)   <br/> 遠端 PowerShell (需要進一步的設定)   <br/> Configuration Manager  <br/> |
|更新作業系統  <br/> |Windows Update  <br/> |Windows Update  <br/> WSUS  <br/> |
|應用程式更新  <br/> |Windows 市集  <br/> |Windows 市集  <br/> Configuration Manager  <br/> |
|帳戶設定  <br/> |Teams 系統管理中心  <br/> |Teams 系統管理中心  <br/> |
|Access 記錄檔  <br/> |Teams 系統管理中心  <br/> PowerShell  <br/> |Teams 系統管理中心 <br/> PowerShell  <br/>  |
   
## <a name="configuring-group-policy-for-microsoft-teams-rooms"></a>設定 Microsoft Teams 會議室 的群組原則
<a name="GroupPolicy"> </a>

本節涵蓋Microsoft Teams 會議室需視情況而定才能正常運作的系統設定。 

加入Teams 會議室至 Active Directory 網域提供下列優點：

- 加入網域Teams 會議室可讓您授與網域使用者和群組系統管理許可權。 如此一來，您就不需要記住本機電腦層級系統管理員帳戶密碼。

- 您可以將 Windows 服務品質設定部署到Teams 會議室。

- 如果使用商務用 Skype，加入Teams 會議室網域會自動匯入貴組織的私人根憑證鏈。

當您加入Teams 會議室至網域時，必須建立個別的組織單位 (OU) ，這樣您才能在所有Teams 會議室物件所在的 OU 中提供群組原則物件 (GPO) 排除專案。 停用所有 GPO 繼承，讓不支援的群組原則設定不會套用至 Teams 會議室。 在加入網域的Teams 會議室之前，先在 OU 中建立機器物件，以確保不套用至預設電腦 OU 的群組原則。

> [!NOTE]
> 即使您建立個別的 OU 並封鎖繼承，某些群組原則若未覆寫設定可能會造成問題。 沒有覆寫集的群組原則會比對封鎖原則繼承集合的 OU。

許多組織都有下列 GPO，這會影響Teams 會議室功能。 請確定您覆寫或封鎖以下專案的繼承：

  - 自動鎖定 (登入會話逾時) 
  - 電源管理相關原則
  - 需要額外的驗證步驟
  - 拒絕存取本機磁片磁碟機
  - 提示使用者網路連線速度變慢
  - 在登入時啟動特定程式
  - 在所有加入網域的電腦上建立另一個網域使用者帳戶。
  - 將Windows Update推送到Teams 會議室

加入Microsoft Teams 會議室至網域時，請確定您的群組原則不會覆寫下表中的設定。

|設定|允許|
|:-----|:-----|
|HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (REG_SZ) 1  <br/> |啟用Microsoft Teams 會議室開機  <br/> |
|電源管理 - \> 在 AC 上，10 分鐘後關閉螢幕  <br/> 電源管理 - \> 在 AC 上，絕不讓系統進入睡眠狀態  <br/> |啟用Microsoft Teams 會議室關閉附加顯示器並自動喚醒  <br/> |
|net accounts /maxpwage：unlimited  <br/> 或是停用本機帳戶密碼到期的同等方式。 若無法執行此動作，最終會導致 Skype 帳戶無法登入抱怨密碼過期。 請注意，這會影響電腦上的所有本機帳戶，因此設定失敗也會造成方塊上的系統管理帳戶最終也會過期。  <br/> |讓 Skype 帳戶永遠都能登入  <br/> |

> [!NOTE]
> 當Microsoft Teams 會議室與下一版的 Windows 10 作業系統相容時，Teams 會議室會透過 Windows Update 自動更新到下一個版本。 Microsoft Teams 會議室不應透過手動升級至下一個Windows 10版本，或透過啟用商務用 Windows Update (WUFB) 群組原則「選取您要接收之更新的 Windows 整備層級」，以及透過 GPO「在收到預覽組建和功能更新時選取」。 Teams 會議室啟用這些群組原則時，已知會遇到作業系統更新Windows 10問題。

## <a name="remote-management-using-powershell"></a>使用 PowerShell 遠端系統管理
<a name="RemotePS"> </a>

您可以使用 PowerShell 遠端執行下列管理作業 (請參閱下表以取得腳本範例) ：
  
- 取得連接的裝置
- 取得應用程式狀態
- 取得系統資訊
- 重新開機系統
- 擷取記錄檔
- 傳輸檔案 (需要加入網域的Microsoft Teams 會議室) 
    
> [!NOTE]
> 此功能預設為關閉。 您必須在Microsoft Teams 會議室系統上為您的環境啟用遠端 PowerShell，才能執行下列作業。 如需如何啟用遠端 PowerShell 的相關資訊，請參閱 **[Enable-PSRemoting](/powershell/module/microsoft.powershell.core/enable-psremoting)** 的相關檔。
  
例如，您可以啟用遠端 PowerShell，如下所示：
  
1. 在Microsoft Teams 會議室裝置上以管理員身分登入。
2. 開啟提升許可權的 PowerShell 命令提示字元。
3. 輸入下列命令： `Enable-PSRemoting -SkipNetworkProfileCheck -Force`
4. 開啟本機安全性原則，並將系統 *管理員* 安全性群組新增至 **安全性設定**  >  **本機原則**  >  **使用者權利指派**  >  **，從網路存取此電腦**。

若要執行管理作業：
  
1. 使用具有許可權可在Microsoft Teams 會議室裝置上執行 PowerShell 命令的帳號憑證登入電腦。
2. 在電腦上開啟一般 PowerShell 命令提示字元。
3. 從下表複製命令文字，並在提示字元中貼上。
4. 以適合您環境的 FQDN 值取代  `<Device fqdn>` 欄位。
5. 以主SkypeSettings.xml組態檔 (或主題影像) 的檔案名和本機路徑取代  *\<path\>*  。
    
取得連接的裝置
  
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

擷取記錄檔
  
```PowerShell
$targetDevice = "<Device fqdn> "
$logFile = invoke-command {$output = Powershell.exe -ExecutionPolicy Bypass -File C:\Rigel\x64\Scripts\Provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
Get-ChildItem -Path C:\Rigel\*.zip | Sort-Object -Descending -Property LastWriteTime | Select-Object -First 1} -ComputerName $targetDevice
$session = new-pssession -ComputerName $targetDevice
Copy-Item -Path $logFile.FullName -Destination .\ -FromSession $session; invoke-command {remove-item -force C:\Rigel\*.zip} -ComputerName $targetDevice
```

將 XML 組態檔推 (或主題圖形) 
  
```XML
$movefile = "<path>";
$targetDevice = "\\<Device fqdn> \Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState\SkypeSettings.xml"; 
Copy-Item $movefile $targetDevice 
```

## <a name="software-updates"></a>軟體更新
<a name="SWupdate"> </a>

根據預設，Microsoft Teams 會議室嘗試連線到 Windows 市集以取得最新版本的Microsoft Teams 會議室軟體。 因此，Teams 會議室需要定期存取網際網路。 在連絡 Microsoft 以解決支援問題之前，請確定Microsoft Teams 會議室已載入最新版本的應用程式。
  
Microsoft Teams 會議室連線至Windows Update以擷取作業系統和周邊裝置韌體更新。 它也會連線到 Microsoft Store 以擷取應用程式更新。

如果您需要手動管理應用程式更新，但無法按照一般程式[商務用 Microsoft Store](https://businessstore.microsoft.com/store)[散佈離線應用程式](/microsoft-store/distribute-offline-apps)，您可以取得Teams 會議室更新套件，以在支援的作業系統上執行應用程式更新。 更新版本可能會跟 Microsoft Store 版本落後，而且可能不一定總是符合最新可用的組建。 若要深入瞭解，請參閱[手動更新Microsoft Teams 會議室裝置](manual-update.md)。

## <a name="admin-mode-and-device-management"></a>管理員模式與裝置管理
<a name="AdminMode"> </a>

有些管理功能，例如手動安裝私人 CA 憑證，需要將Teams 會議室放在管理員模式中。 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running"></a>切換至管理員模式，並在Microsoft Teams 會議室應用程式執行時返回

1. 掛斷任何進行中的通話，然後返回主畫面。
2. 選取齒輪圖示，並顯示功能表 (選項為 **[設定**]、[ **協助工具]** 和 [ **重新開機裝置** ] ) 。
3. 選 **取 [設定]**。
4. 輸入系統管理員密碼。 安裝程式畫面隨即出現。  如果裝置未加入網域，預設會使用本機系統管理帳戶 (使用者名稱「管理員」) 。 此帳戶的預設密碼為 'sfb'。 請儘快變更此密碼。 如果電腦已加入網域，您可以使用適當許可權的網域帳戶登入。
5. 選取左欄中的 **[Windows 設定** ]。
6. 使用您的系統管理認證登入桌面。 您將擁有管理裝置的必要許可權。
7. 執行必要的系統管理工作。
8.  完成後，重新開機電腦。
    
主機現在恢復為正常運作模式。 如果尚未連接鍵盤，下列程式會要求您將鍵盤連接到裝置。 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-crashes"></a>切換至管理員模式，並在Microsoft Teams 會議室應用程式當機時返回

1. 快速連續按下 Windows 鍵五次。 這會將您帶到 Windows 登入畫面。 
2. 使用您的系統管理認證登入桌面。
3. 執行必要的系統管理工作。
4. 完成後，重新開機電腦。

    > [!NOTE]
    > 此方法不會將 Skype 使用者登出或寬限地終止應用程式，但如果應用程式沒有回應且無法使用其他方法，您就會使用此方法。 

   主機會重新開機為正常運作模式，並執行Microsoft Teams 會議室應用程式。 如果您連接鍵盤以完成此程式，您可以移除鍵盤。
   ## <a name="troubleshooting-tips"></a>疑難排解秘訣
   <a name="TS"> </a>

- 會議邀請在跨網域範圍傳送時可能不會出現 (例如，兩家公司之間) 。 在這種情況下，IT 系統管理員應決定是否要允許外部使用者排程會議。 請參閱 Exchange PowerShell Cmdlet [Set-CalendarProcessing](/powershell/module/exchange/set-calendarprocessing)一文，特別是「ProcessExternalMeetingMessages」參數。
- Microsoft Teams 會議室不支援 Exchange 自動探索透過 Exchange 2010 重新導向。
- 一般而言，IT 系統管理員最好停用他們不打算使用的任何音訊端點。
- 如果在會議室預覽中顯示鏡像影像，IT 系統管理員可以使用相機設定來迴圈攝影機電源或翻轉影像方向來更正。
- 已知會遺失主機觸控螢幕存取權。 在這種情況下，有時會重新開機Teams 會議室來解決此問題。
- 已知透過有線摱取將電腦連線到主機時，會遺失本機音訊。 在這種情況下，重新開機電腦可以解決本機音訊播放問題。
