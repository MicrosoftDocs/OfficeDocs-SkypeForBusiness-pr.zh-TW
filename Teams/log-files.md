---
title: 使用記錄檔進行疑難排解Microsoft Teams
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
description: 瞭解由 Microsoft Teams 產生的偵錯、媒體和桌面記錄檔、可找到這些記錄的位置，以及如何協助監控和疑難排解。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4d8e3ab079498ecfca11a7d2ba48736aaf457329
ms.sourcegitcommit: bd05783dfb33a63e0eb083a2135f97d110dc81a3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/26/2022
ms.locfileid: "65059104"
---
# <a name="use-log-files-to-monitor-and-troubleshoot-microsoft-teams"></a>使用記錄檔來監視及疑難排解Microsoft Teams

用戶端會自動產生三種類型的記錄檔，可用於協助監控及疑難排解Teams：

-   [偵錯記錄](#debug-logs)

-   [媒體記錄檔](#media-logs)

-   [桌面記錄檔](#desktop-logs)

本文將說明這些記錄檔及其使用方式。 如需疑難排解特定問題的相關資訊，請參閱：[Teams疑難排解]](/MicrosoftTeams/troubleshoot/teams)。 如需如何連絡客戶支援的相關資訊，請參閱 [取得支援](/microsoft-365/business-video/get-help-support)。 使用Microsoft 支援服務建立支援要求時，支援工程師將需要偵錯記錄檔。 建立支援要求之前，請先備有偵錯記錄檔，可讓 Microsoft 快速開始疑難排解問題。 **只有** 當 Microsoft 要求時，才需要媒體或 **桌面** 記錄。

> [!NOTE]
> 在本文中， **「偵錯記錄」** 一詞是指用於疑難排解的記錄檔。 不過，針對這些記錄所產生的檔案名稱中會包含字詞 **診斷記錄** 檔。  

## <a name="collect-and-enable-logging"></a>收集並啟用記錄

問題發生時，請務必立即收集記錄。 只要按幾下滑鼠，就可以將記錄收集在一起。

- Windows：以滑鼠右鍵按一下系統匣中的Teams圖示，然後選擇 **[收集支援檔案]**。 

- Mac：選取 [說明] 功能表，然後選擇 **[收集支援檔案]**。

偵錯、桌面和媒體記錄會收集在一個資料夾中，名稱為 _MSTeams 診斷記錄檔 \<local date and time\>_。 當您使用Microsoft 支援服務開啟支援要求時，可以壓縮並共用此資料夾。 資料夾會包含桌面、會議 (媒體) 和偵錯 (網頁) 的資料夾。 您可以使用下列鍵盤快速鍵來收集檔案：

- Windows：<kbd>Ctrl</kbd> + <kbd>Alt</kbd> + <kbd>Shift</kbd> + <kbd>1</kbd>

- Mac： <kbd>Option</kbd> + <kbd>Command</kbd> + <kbd>Shift</kbd> + <kbd>1</kbd>


媒體記錄檔中所述，只有部分 CPU 預設會開啟 [媒體記錄](#media-logs)。 否則，預設會關閉。 若要啟用媒體記錄，使用者必須開啟Teams用戶端中的選項。 移至 **設定**  >  **General**，然後選取 [**啟用會議診斷記錄]， (需要重新開機Teams)**。 Teams用戶端必須重新開機，記錄才能開始 (重新開機，方法是以滑鼠右鍵按一下 Dock (Mac) 或工作列中的圖示， (Windows) 並選取 [**結束]**。 結束之後，只要按一下應用程式圖示，) 再開啟一次。

如果特定會議或即時事件發生問題，將 URL 與會議相關聯會很有説明。 這會提供其他資訊，以協助找出記錄檔中確切的會議或即時事件。 您可以從會議的任何參與者或現場活動的簡報者或製作人收集這項資訊。 將游標暫留在聯結 URL 上並選擇 **[複製超連結]**，即可擷取此 URL。

> [!NOTE]
> 如果已啟用媒體記錄，會議資料夾中會包含其他檔案，這是調查音訊和視訊問題的必要檔案。 如果未啟用媒體記錄，則可用的記錄數量有限。
  
> [!NOTE]
> 偵錯記錄檔先前使用下列鍵盤快速鍵收集。 這些功能仍然有效，且會完成與 **[收集支援檔案** ] 選項相同的記錄擷取。
>
> - Windows：<kbd>Crtl</kbd> + <kbd>Alt</kbd> + <kbd>Shift</kbd> + <kbd>1</kbd>
>
> - Mac： <kbd>Option</kbd> + <kbd>Command</kbd> + <kbd>Shift</kbd> + <kbd>1</kbd>


下表概述各種用戶端及其相關聯的記錄。 記錄檔會儲存在用戶端和作業系統的特定位置。


|用戶端 |調試|桌面|媒體|
|---------|---------|---------|---------|
|Web    |X         |-         |-         |
|Windows     |X         |X         |X         |
|Mac OSX     |X         |X         |X         |
|Linux     |X         |X         |X         |
|iOS     |-         |-         |-         |
|Android     |-         |-         |-         |

如需支援的作業系統和瀏覽器的完整清單，請參閱[取得Microsoft Teams版用戶端](get-clients.md)。

## <a name="debug-logs"></a>偵錯記錄

如需Windows和 Mac 的指示，請參閱 _收集和啟用記錄_ 功能一節。 偵錯記錄是由 Windows 和 Mac 桌面用戶端以及瀏覽器型用戶端產生。 記錄檔是以文字為基礎，並從下到上朗讀。 您可以使用任何文字編輯器來讀取記錄，並在登入用戶端時建立新的記錄。

偵錯記錄會顯示下列資料流程：

-   登錄

-   對中介層服務的連線要求

-   通話/交談

若要收集 Linux 的記錄：
- 鍵盤快速鍵：<kbd>CtrlAltShift1</kbd>  +  <kbd> </kbd>  +  <kbd> </kbd>  +  <kbd> </kbd>  
- 檔案可在 `~/Downloads`

若要收集瀏覽器和Windows的記錄：
- 鍵盤快速鍵：<kbd>CtrlAltShift1</kbd>  +  <kbd> </kbd>  +  <kbd> </kbd>  +  <kbd> </kbd>  
- 檔案可在 `%userprofile%\Downloads`

## <a name="media-logs"></a>媒體記錄檔

如需Windows和 Mac 的指示，請參閱 _收集和啟用記錄_ 功能一節。 媒體記錄檔包含Teams會議中音訊、視訊和螢幕共用的診斷資料。 連結到通話相關問題的支援案例是必要的。

如果您的 CPU 為：電腦的媒體記錄功能預設為開啟：
- 任何 Apple M1
- 任何 Intel Xeon
- 任何 Intel i9，U、G7、M 和 MQ 系列除外
- 除了 U、G7、M 和 MQ 系列之外，任何第 6 代及之後的 Intel i7

否則，預設會關閉。 若要記錄Teams會議的診斷資料，使用者必須開啟Teams用戶端中的選項。 移至 **設定**  >  **General**，選取 [啟用 **會議診斷的記錄]， (需要重新開機Teams**) 核取方塊、重新開機Teams，然後重現問題。 

> [!NOTE]
> 當您登出Teams時，媒體記錄會重設為預設值。 

當您傳送記錄檔給 Microsoft 支援服務時，請驗證記錄檔的時間戳記，以確保當您重現問題時，記錄檔涵蓋時間範圍。

若要收集 Linux 的記錄：  
- 這些檔案可在下列位置使用：
  - `~/.config/Microsoft/Microsoft Teams/media-stack/\*\.blog`
  - `~/.config/Microsoft/Microsoft Teams/skylib/\*\.blog`

若要收集Windows記錄：  
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

如需Windows和 Mac 的指示，請參閱 _收集和啟用記錄_ 功能一節。 桌面記錄，也稱為啟動載入器記錄檔，包含會發生在桌面用戶端和瀏覽器之間的記錄資料。 這些記錄檔與媒體記錄一樣，只有在 Microsoft 要求時才需要。 記錄檔是以文字為基礎的，可以使用任何由上而下格式的文字編輯器來朗讀。

若要收集 Linux 的記錄：
- 按一下系統匣中的Microsoft Teams圖示，然後選 **取 [取得記錄檔]**。
- 檔案將在 中取得 `~/.config/Microsoft/Microsoft Teams/logs.txt` 。
  
若要收集Windows記錄：
- 按一下系統匣中的Microsoft Teams圖示，然後選取 **[收集支援檔案]**。
- 檔案 `logs.txt` 會自動以記事本開啟。

在調查登入Teams的問題時，您可能需要手動收集桌面記錄檔。 這些記錄檔位於 Windows 中的 %appdata%\Microsoft\Teams。

## <a name="browser-trace"></a>瀏覽器追蹤

對於某些類型的錯誤，Microsoft 支援服務可能需要您收集瀏覽器追蹤。 這項資訊可以提供有關錯誤發生時Teams用戶端狀態的重要詳細資料。

開始瀏覽器追蹤之前，請確定您已登入Teams。 請務必先執行此動作，再啟動追蹤，讓追蹤不含敏感的登入資訊。

登入之後，請根據您的瀏覽器，選取下列其中一個連結，然後依照提供的步驟進行。 

-   [Chrome & Edge (Chromium) ](/azure/azure-portal/capture-browser-trace#google-chrome-and-microsoft-edge-chromium?preserve-view=true#resolution)

-   [邊緣](/azure/azure-portal/capture-browser-trace#microsoft-edge-edgehtml?preserve-view=true#resolution)

-   [Safari](/azure/azure-portal/capture-browser-trace#apple-safari?preserve-view=true#resolution)

-   [火狐](/azure/azure-portal/capture-browser-trace#firefox?preserve-view=true#resolution)

> [!NOTE]
> 在步驟中，將Azure 入口網站的所有參照取代為Teams用戶端。
  
## <a name="webrtc-logs-in-browsers"></a>瀏覽器中的 WebRTC 記錄
WebRTC 記錄檔可以提供音訊和視訊通話的連線詳細資料，協助Microsoft 支援服務。 依照步驟在 Edge (Chromium) 或 Chrome 中存取 WebRTC 記錄檔： 
  
1.  開啟新索引標籤，然後移至下列其中一個 URL：
    -   Edge (Chromium) ：`edge://webrtc-internals/`
    -   鉻： `chrome://webrtc-internals/`
  
2.  開啟 Teams Web 應用程式並重現問題。
  
3.  返回到步驟 1 中存取的索引標籤，您會看到至少兩個索引標籤：
    -   GetUserMedia 要求
    -   `https://teams.microsoft.com/url`

4.  選擇含有Teams應用程式名稱的索引標籤，然後儲存頁面內容。

## <a name="related-topics"></a>相關主題

[Teams 疑難排解](/MicrosoftTeams/troubleshoot/teams)
