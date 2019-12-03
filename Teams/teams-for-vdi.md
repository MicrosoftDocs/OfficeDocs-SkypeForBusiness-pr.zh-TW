---
title: 虛擬化桌面基礎結構的團隊
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 04/10/2019
ms.topic: article
ms.service: msteams
ms.reviewer: rafarhi
audience: admin
description: 瞭解如何在虛擬化桌面基礎結構（VDI）環境中執行 Microsoft 團隊。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: bdac909139a225d622098df5d7df44516edac7bd
ms.sourcegitcommit: 74c06b00ff78dc816a59e6c59e9be87181fc0f3e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/03/2019
ms.locfileid: "39669241"
---
# <a name="teams-for-virtualized-desktop-infrastructure"></a>虛擬化桌面基礎結構的團隊

本文將說明在虛擬化環境中使用 Microsoft 團隊的需求與限制。

## <a name="what-is-vdi"></a>什麼是 VDI？

虛擬桌面基礎結構（VDI）是虛擬化技術，可在資料中心的中央伺服器上託管桌面作業系統和應用程式。 這可讓使用者具備完全安全且相容的集中來源，為使用者提供完整的個人化桌面體驗。

目前，虛擬化環境中的團隊可與專用的永久性虛擬化電腦（VM）共同提供共同作業和聊天功能的支援。 若要確保最佳的使用者體驗，請遵循本文中的指導方針。

## <a name="teams-requirements"></a>團隊需求

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality-in-teams"></a>設定原則以關閉小組中的通話與會議功能

小組通話和會議體驗未針對 VDI 環境優化（即將推出）。 我們建議您設定使用者層級原則，以關閉小組中的通話與會議功能。

您仍然可以使用小組桌面應用程式或 web 應用程式，選擇在 VDI 中完全執行團隊。 不過，建議您設定原則，以避免損害使用者體驗。

策略變更可能需要幾個時間（幾個小時）才能傳播。 如果您沒有立即看到特定帳戶的變更，請在幾個小時後再試一次。

> [!NOTE]
> 當團隊通話和會議已針對虛擬桌面環境中的使用進行優化時，您可以復原這些原則，並允許使用者使用小組做為自己的習慣。

#### <a name="calling"></a>通話

使用**CSTeamsCallingPolicy** Cmdlet 來控制是否允許使用者在私人和群組聊天中使用呼叫和呼叫選項。 以下是原則設定及建議值的清單。

|原則名稱  |描述 |建議值  |
|---------|---------|---------|
|AllowCalling|控制交互操作通話功能。 開啟這項功能後，商務用 Skype 使用者就能與團隊使用者進行一對一通話（反之亦然）。|設定為 False，以避免從商務用 Skype 使用者撥打電話給小組。|
|AllowPrivateCalling| 控制呼叫 app 在團隊用戶端左側的應用程式行中是否可用，以及使用者是否在 [私人聊天] 中看到 [通話] 和 [視頻通話] 選項。 |設為 False，即可從小組左側的應用程式行中移除通話應用程式，以及移除 [私人聊天] 中的 [通話] 和 [視頻通話] 選項。|

#### <a name="create-and-assign-a-calling-policy"></a>建立並指派通話原則

1. 以系統管理員身分啟動 Windows PowerShell 會話。
2. 連線至 [Skype Online 連接器]。

      ```powershell
      # Set Office 365 User Name and Password
      $username = "admin email address"
      password = ConvertTo-SecureString "password" -AsPlainText -Force
      $LiveCred = new-object -typename System.Management.Automation.PSCredential -argumentlist $username, $password
      # Connect to Skype Online
      Import-Module SkypeOnlineConnector
      $sfboSession = New-CsOnlineSession -Credential $LiveCred
      Import-PSSession $sfboSession
      ```

3. 查看通話原則選項的清單。

      ```powershell
      Get-CsTeamsCallingPolicy
      ```

4. 尋找已停用所有通話原則的內建原則選項。 它看起來像這樣。

        Identity                        : Tag:DisallowCalling
        AllowCalling                    : False
        AllowPrivateCalling             : False
        AllowVoicemail                  : False
        AllowCallGroups                 : False
        AllowDelegation                 : False
        AllowUserControl                : False
        AllowCallForwardingToUser       : False
        AllowCallForwardingToPhone      : False
        PreventTollBypass               : False

5. 將 DisallowCalling 內建原則選項套用至將在虛擬化環境中使用團隊的所有使用者。

      ```powershell
      Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity "user email id"
      ```

如需團隊通話原則的詳細資訊，請參閱[設定 CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy)。

#### <a name="meetings"></a>舉行

使用**CsTeamsMeetingPolicy** Cmdlet 來控制使用者可以建立的會議類型、在會議中可存取的功能，以及匿名及外部使用者可以使用的會議功能。 以下是原則設定及建議值的清單。

|原則名稱 |描述|建議值                   |
|-------------------|-----------------|-----------------------|
|AllowPrivateMeetingScheduling  | 判斷是否允許使用者排程私人會議。| 設為 False，禁止使用者排程私人會議。 |
|AllowChannelMeetingScheduling  | 判斷是否允許使用者排程頻道會議。 | 設為 False，禁止使用者排程頻道會議。|
|AllowMeetNow |判斷是否允許使用者建立或啟動臨時會議。 | 將此值設定為 False，禁止使用者啟動即席會議。 |
|ScreenSharingMode | 決定允許使用者在通話或會議中共用其螢幕的模式。 | 設為 [停用] 以禁止使用者共用其螢幕。 |
|AllowIPVideo |決定是否在使用者的會議或通話中啟用影片。 | 設為 False，禁止使用者共用影片。 |
| AllowAnonymousUsersToDialOut | 判斷是否允許匿名使用者撥出 PSTN 號碼。 | 設為 False，禁止匿名使用者撥號。 |
| AllowAnonymousUsersToStartMeeting | 判斷匿名使用者是否可以開始會議。 | 設為 False 以禁止使用者開始會議。 |
| AllowOutlookAddIn |決定使用者是否可以在 Outlook 桌面用戶端中排程團隊會議。 | 設定為 False，以禁止使用者在 Outlook 桌面用戶端排程小組會議。 |
| AllowParticipantGiveRequestControl|決定參與者是否可以要求或授與螢幕共用的控制權。| 設為 False，禁止使用者在會議中授與要求控制權。 |
| AllowExternalParticipantGiveRequestControl | 決定外部參與者是否可以要求或授與螢幕共用的控制權。 | 設為 False 可禁止外部使用者授與，要求您在會議中進行控制。 |
| AllowPowerPointSharing |決定是否允許在使用者的會議中共用 PowerPoint。 |設為 False，禁止使用者在會議中共用 PowerPoint 檔案。 |
| AllowWhiteboard | 判斷使用者的會議是否允許使用白板。 | 若要在會議中禁止白板，請將它設為 False。 |
| AllowTranscription |判斷在使用者的會議中是否允許即時及/或會議後的標題和 transcriptions。 | 設為 False，即可禁止會議中的 [文字] 與 [標題]。 |
| AllowSharedNotes | 決定是否允許使用者拍共用筆記。 | 設為 False，禁止使用者記錄共用的筆記。 |
| MediaBitRateKB |決定會議中音訊/視頻/app 共用傳輸的媒體位元速率。 | 建議的值為5000（5 MB）。 您可以根據組織的需求變更它。 |

#### <a name="create-and-assign-a-meeting-policy"></a>建立並指派會議原則

1. 以系統管理員身分啟動 Windows PowerShell 會話。
1. 連線至 [Skype Online 連接器]。

      ```powershell
      # Set Office 365 User Name and Password
      $username = "admin email address"
      password = ConvertTo-SecureString "password" -AsPlainText -Force
      $LiveCred = new-object -typename System.Management.Automation.PSCredential -argumentlist $username, $password
      # Connect to Skype Online
      Import-Module SkypeOnlineConnector
      $sfboSession = New-CsOnlineSession -Credential $LiveCred
      Import-PSSession $sfboSession
      ```

1. 查看會議原則選項的清單。

      ```powershell
      Get-CsTeamsMeetingPolicy
      ```

1. 尋找已停用所有會議原則的內建原則選項。 它看起來像這樣。

        Identity                                    : Tag:AllOff
        Description                                 :
        AllowChannelMeetingScheduling               : False
        AllowMeetNow                                : False
        AllowIPVideo                                : False
        AllowAnonymousUsersToDialOut                : False
        AllowAnonymousUsersToStartMeeting           : False
        AllowPrivateMeetingScheduling               : False
        AutoAdmittedUsers                           : False
        AllowCloudRecording                         : False
        AllowOutlookAddIn                           : False
        AllowPowerPointSharing                      : False
        AllowParticipantGiveRequestControl          : False
        AllowExternalParticipantGiveRequestControl  : False
        AllowSharedNotes                            : False
        AllowWhiteboard                             : False
        AllowTranscription                          : False
        MediaBitRateKb                              : False
        ScreenSharingMode                           : False

1. 將 AllOff 內建原則選項套用至將在虛擬化環境中使用團隊的所有使用者。

      ```powershell
      Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity "user email id"
      ```

 如需團隊會議原則的詳細資訊，請參閱[設定 CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy)。

### <a name="virtualization-provider-requirements"></a>虛擬化提供者需求

團隊 app 已在主要的虛擬化解決方案提供者上驗證。 有了多個市場供應商，請諮詢您的虛擬化解決方案供應商，以確保符合最低需求。

### <a name="virtual-machine-requirements"></a>虛擬機器需求

> [!NOTE]
> 下列要求適用于團隊桌面應用程式和團隊 Web app。

在虛擬化環境中，有各種不同的工作負載和使用者需求，以下是建議的最低 VM 配置。

|參數 |單位 |
|---------|---------|
|vCPU | 2個核心 |
|RAM | 4 GB |
|儲存空間 | 8 GB |

### <a name="virtual-machine-operating-system-requirements"></a>虛擬機器作業系統需求

VM 支援的作業系統如下：

- Windows 10 及更新版本
- Windows Server 2012 R2 及更新版本

## <a name="install-teams-on-vdi"></a>在 VDI 上安裝團隊

以下是部署團隊桌面應用程式的程式和工具。

1. 根據環境，使用下列其中一個連結來下載團隊 MSI 套件。 我們建議使用64位作業系統的 VDI VM 64 位版本。

    - [32位版本](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true)
    - [64位版本](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true&arch=x64)

1. 執行下列命令，將 MSI 安裝到 VDI VM （或完成更新）。

      ```
      msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1
      ```

    這會將小組安裝到程式檔。 此時，黃金影像設定就完成了。

    下次互動式登入會話會啟動團隊並要求認證。 請注意，在 VDI 上使用 ALLUSER 屬性來安裝小組時，不可能停用自動啟動小組。

1. 執行下列命令以從 VDI VM 卸載 MSI （或準備更新）。

      ```
      msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>
      ```

    這會從程式檔案中卸載小組。

## <a name="known-issues-and-limitations"></a>已知問題與限制

下列是 VDI 上小組的已知問題與限制。

- **共用工作階段主機類型部署**：共用工作階段主機類型部署（例如，共用非永久性 VM 設定）不在範圍內。
- **通話與會議**：

  - 通話和會議案例未針對 VDI 進行優化。 這些案例的執行效果不佳。 我們建議使用使用者層級原則，如在 [[團隊中關閉通話和會議功能](#set-policies-to-turn-off-calling-and-meeting-functionality-in-teams)] 區段中所述。  
  - 套用本文所述的原則，會影響使用通話與會議功能（視其他原則而定）可能會影響貴組織中的其他使用者。 如果貴組織中的使用者使用非 VDI 用戶端，您可以選擇不套用原則。  

- **加入由其他使用者所建立的通話與會議**：雖然原則限制使用者建立會議，但如果其他使用者從會議撥出會議，他們仍可加入會議。 在這些會議中，使用者共用影片的能力，使用白板和其他功能，取決於您是否使用 TeamsMeetingPolicy 停用這些功能。

- 快取的**內容**：如果團隊在其中執行的虛擬環境不是持續性（在每個使用者會話結束時都會清除資料），使用者可能會發現內容重新整理導致效能下降，不論使用者是否已在前一個會話中存取相同的內容。

- **用戶端更新**： VDI 上的團隊不會自動更新每電腦 MSI 安裝。 您必須安裝新的 MSI 來更新 VM 影像，如在 VDI 的 [[安裝小組](#install-teams-on-vdi)] 區段中所述。 您必須卸載目前的版本，才能更新為較新的版本。

- **使用者體驗**： vdi 環境中的小組使用者體驗可能與非 VDI 環境不同。 差異可能是因為環境中的原則設定和/或功能支援。

針對與 VDI 無關的小組已知問題，請參閱[Microsoft 團隊已知問題](Known-issues.md)。

## <a name="related-topics"></a>相關主題

- [使用 MSI 安裝 Microsoft 團隊](msi-deployment.md)
