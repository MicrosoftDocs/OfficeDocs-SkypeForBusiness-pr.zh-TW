---
title: 在 Teams 中設定記錄檔以進行監視和疑難排解
ms.reviewer: tejeshs
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 05/06/2021
audience: admin
ms.topic: troubleshooting
ms.service: msteams
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
search.appverid: MET150
description: 瞭解 Microsoft Teams 產生的偵錯、媒體和桌面記錄檔、可找到這些記錄的位置，以及如何協助監控和疑難排解。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2ab00f7a1eedf2b1341819c7ec1c67abeb5f6e38
ms.sourcegitcommit: 6b4dad9cea8fdad74c493ef62b085dbb9957235d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/31/2022
ms.locfileid: "67486888"
---
# <a name="configure-log-files-for-monitoring-and-troubleshooting-in-teams"></a>在 Teams 中設定記錄檔以進行監視和疑難排解

用戶端會自動產生三種類型的記錄檔，可用於協助監控和疑難排解 Teams：

-   [偵錯記錄](#debug-logs)

-   [媒體記錄檔](#media-logs)

-   [桌面記錄檔](#desktop-logs)

本文將說明這些記錄檔及其使用方式。 如需疑難排解特定問題的相關資訊，請參閱： [Teams 疑難排解](/MicrosoftTeams/troubleshoot/teams)。 

如需如何連絡客戶支援的相關資訊，請參閱 [取得支援](/microsoft-365/business-video/get-help-support)。

> [!NOTE]
> 在本文中， **「偵錯記錄」** 一詞是指用於疑難排解的記錄檔。 不過，針對這些記錄所產生的檔案名稱中會包含字詞 **診斷記錄** 檔。  

## <a name="logs-overview"></a>記錄概觀

問題發生時，請務必立即收集記錄。

使用Microsoft 支援服務建立支援要求時，支援工程師將需要偵錯記錄檔。 建立支援要求之前，請先備有偵錯記錄檔，可讓 Microsoft 快速開始疑難排解問題。 **只有** 當 Microsoft 要求時，才需要媒體或 **桌面** 記錄。

偵錯、桌面和媒體記錄會收集在一個資料夾中，名稱為 _MSTeams 診斷記錄檔 \<local date and time\>_。 當您使用Microsoft 支援服務開啟支援要求時，可以壓縮並共用此資料夾。 資料夾會包含桌面、會議 (媒體) 和偵錯 (網頁) 的資料夾。 您可以使用下列鍵盤快速鍵來收集檔案：

- Windows： <kbd>Ctrl</kbd> + <kbd>Alt</kbd> + <kbd>Shift</kbd> + <kbd>1</kbd>

- Mac： <kbd>Option</kbd> + <kbd>Command</kbd> + <kbd>Shift</kbd> + <kbd>1</kbd>


如果特定會議或即時事件發生問題，將 URL 與會議相關聯會很有説明。 URL 會提供其他資訊，以協助找出記錄檔中的確切會議或即時事件。 您可以從會議的任何參與者或現場活動的簡報者或製作人收集這項資訊。 將游標暫留在聯結 URL 上並選擇 **[複製超連結]**，即可擷取此 URL。

> [!NOTE]
> 如果已啟用媒體記錄，會議資料夾中會包含其他檔案，這是調查音訊和視訊問題的必要檔案。 如果未啟用媒體記錄，則可用的記錄數量有限。
  
下表概述各種用戶端及其相關聯的記錄。 記錄檔會儲存在用戶端和作業系統的特定位置。

|用戶端 |調試|桌面|媒體|
|---------|---------|---------|---------|
|Web    |X         |-         |-         |
|Windows     |X         |X         |X         |
|Mac OSX     |X         |X         |X         |
|Linux     |X         |X         |X         |
|iOS     |-         |-         |-         |
|Android     |-         |-         |-         |

如需支援的作業系統和瀏覽器的完整清單，請參閱 [取得 Microsoft Teams 的用戶端](get-clients.md)。

## <a name="debug-logs"></a>偵錯記錄

偵錯記錄檔是由 Windows 和 Mac 桌面用戶端以及瀏覽器型用戶端所產生。 記錄檔是以文字為基礎，並從下到上朗讀。 您可以使用任何文字編輯器來讀取記錄，並在登入用戶端時建立新的記錄。

偵錯記錄會顯示下列資料流程：

-   登錄

-   對中介層服務的連線要求

-   通話/交談

若要收集 Linux 的記錄：
- 鍵盤快速鍵：<kbd>Ctrl</kbd>  +  <kbd>Alt</kbd>  +  <kbd>Shift</kbd>  +  <kbd>1</kbd>  
- 檔案可在 `~/Downloads`

若要收集瀏覽器和 Windows 的記錄：
- 鍵盤快速鍵：<kbd>Ctrl</kbd>  +  <kbd>Alt</kbd>  +  <kbd>Shift</kbd>  +  <kbd>1</kbd>  
- 檔案可在 `%userprofile%\Downloads`

若要收集 Mac 的記錄：
- 鍵盤快速鍵：<kbd>Option</kbd>  +  <kbd>Command</kbd>  +  <kbd>Shift</kbd>  +  <kbd>1</kbd>  
- 檔案可在 `~/Downloads`

## <a name="media-logs"></a>媒體記錄檔

媒體記錄檔包含 Teams 會議中音訊、視訊和螢幕共用的診斷資料。 連結到通話相關問題的支援案例是必要的。

如果您的 CPU 為：電腦的媒體記錄功能預設為開啟：
- 任何 Apple M1
- 任何 Intel Xeon
- 任何 Intel i9，U、G7、M 和 MQ 系列除外
- 除了 U、G7、M 和 MQ 系列之外，任何第 6 代及之後的 Intel i7

否則，預設會關閉。 有兩種方式可以記錄 Teams 會議的診斷資料：

- 管理員設定- 您可以管理使用者的媒體記錄檔
- 使用者設定- 您的使用者可以開啟媒體記錄

### <a name="admin-configuration"></a>管理員設定

管理使用者的媒體記錄提供順暢的疑難排解體驗，尤其是當問題間歇性時。 系統管理員可以使用 TeamsMediaLoggingPolicy Cmdlet 為使用者啟用和管理媒體記錄。

閱讀 [Grant-CsTeamsMediaLoggingPolicy](/powershell/module/teams/grant-csteamsmedialoggingpolicy) for PowerShell Cmdlet 和詳細資訊。

### <a name="end-user-configuration"></a>使用者設定

使用者必須開啟 Teams 用戶端中的選項，才能記錄 Teams 會議的診斷資料。 他們會移至 [一 **般****設定**  >  ]，選 **取 [啟用媒體記錄檔 (音訊、視訊和螢幕共用的診斷資料)** 核取方塊，然後重現問題。

> [!NOTE]
> 當您的使用者登出 Teams 時，媒體記錄會重設為預設值。

### <a name="collecting-and-sending-media-logs"></a>收集和傳送媒體記錄

將記錄檔傳送給 Microsoft 支援服務之前，請先確認記錄檔的時間戳記，以確保當您重現問題時，記錄檔涵蓋時間範圍。

若要收集 Linux 的記錄：  
- 這些檔案可在下列位置使用：
  - `~/.config/Microsoft/Microsoft Teams/media-stack/\*\.blog`
  - `~/.config/Microsoft/Microsoft Teams/skylib/\*\.blog`

若要收集 Windows 的記錄：  
- 這些檔案可在下列位置使用：
  - `%appdata%\Microsoft\Teams\media-stack\\\*\.blog`
  - `%appdata%\Microsoft\Teams\skylib\\\*\.blog` 

若要收集 Mac 的記錄：
- 這些檔案可在下列位置使用：
  - `~/Library/Application Support/Microsoft/Teams/media-stack\\\*\.blog`
  - `~/Library/Application Support/Microsoft/Teams/skylib\\\*\.blog`

以下是所產生的記錄檔及其所含資訊的清單。

<br/>

|記錄檔名稱  |描述  |
|---------|---------|
|`Teams.msrtc-0-s1039525249.blog`     | 包含媒體堆疊的相關資訊。 這包括頻道狀態，例如解析度、使用的解碼器和編碼器，以及傳送和接收的框架數目，以及相機和視訊螢幕共用 (VBSS) 會話狀態。         |
|`rtmcontrol.msrtc-0-2415069487.blog`      |記錄與遠端控制動作相關的資訊，例如授與控制時的時間戳記，以及滑鼠指標資訊。          |
|`Teams_MediaStackETW-2-U-xr-U.etl`      |記錄媒體堆疊追蹤事件。         |
|`Debug-0-s2790420889.blog`    | 包含媒體代理程式的相關資訊，包括轉譯品質。          |
|`tscalling-0-2061129496.blog`   |記錄 TS 通話 API 中的事件。       |

## <a name="desktop-logs"></a>桌面記錄檔

桌面記錄，也稱為啟動載入器記錄檔，包含會發生在桌面用戶端和瀏覽器之間的記錄資料。 這些記錄檔與媒體記錄一樣，只有在 Microsoft 要求時才需要。 記錄檔是以文字為基礎的，可以使用任何由上而下格式的文字編輯器來朗讀。

若要收集 Linux 的記錄：
- 按一下系統匣中的 Microsoft Teams 圖示，然後選取 [ **取得記錄]**。
- 檔案將在 中取得 `~/.config/Microsoft/Microsoft Teams/logs.txt` 。

若要收集 Mac 的記錄：
- 按一下 Microsoft Teams 中的 [說明] 功能表，然後選取 **[收集支援檔案]**。
- 檔案 `logs.txt` 會位於 _MSTeams 診斷記錄 \<local date and time>_ 檔資料夾內的 [桌面] 資料夾中。

若要收集 Windows 的記錄：
- 按一下系統匣中的 Microsoft Teams 圖示，然後選取 **[收集支援檔案]**。
- 檔案 `logs.txt` 會自動在記事本中開啟。

在調查登入 Teams 的問題時，您可能需要手動收集桌面記錄檔。 這些記錄檔位於 Windows 中的 %appdata%\Microsoft\Teams。

## <a name="related-topics"></a>相關主題

[Teams 疑難排解](/MicrosoftTeams/troubleshoot/teams)

[Teams 的瀏覽器記錄和追蹤](/MicrosoftTeams/browser-logs-and-tracing-for-teams)
