---
title: 使用記錄檔案疑難排解Microsoft Teams
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
description: 瞭解由 Microsoft Teams 產生的 Debug、Media 和桌面記錄，以及這些記錄可以在哪裡找到，以及如何協助監控和疑難排解。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 100d21338cf77642836793ab9cf69d426d1fd463
ms.sourcegitcommit: 38a4d2f41270633479afb3412c749365922554e5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/10/2021
ms.locfileid: "61410684"
---
# <a name="use-log-files-to-monitor-and-troubleshoot-microsoft-teams"></a>使用記錄檔案來監控和疑難排解Microsoft Teams

用戶端自動產生的記錄檔案有三種類型，可運用這些記錄檔案以協助監控和疑難排解Teams：

-   [調試記錄](#debug-logs)

-   [媒體記錄](#media-logs)

-   [桌面記錄](#desktop-logs)

本文將說明這些記錄及其使用方式。 有關疑難排解特定問題的資訊，請參閱：Teams[疑難排解](/MicrosoftTeams/troubleshoot/teams)。 如需如何與支援人員聯繫的資訊，請參閱 [取得支援](/microsoft-365/business-video/get-help-support)。 使用 Microsoft 支援服務建立支援要求時，支援工程師需要調試記錄。 建立支援要求之前，先將調試記錄放在手邊，Microsoft 就會快速開始疑難排解問題。 **媒體** 或 **桌面** 記錄只有在 Microsoft 要求時才能使用。

> [!NOTE]
> 本文中，" **調試** 記錄"一詞是指用於疑難排解的記錄。 不過，這些記錄產生的檔案名稱中會包含診斷 **記錄** 一詞。  

## <a name="collect-and-enable-logging"></a>收集和啟用記錄

發生問題時，收集記錄非常重要。 只要按幾下滑鼠，就能將記錄收集在一起。

- Windows：以滑鼠右鍵按一下系統Teams中的 [檔案備份Teams，然後選擇 [**收集支援檔案**> 。 

- Mac：選取説明功能表，然後選擇收集 **支援檔案**。

Debug、Desktop 和 Media 記錄會收集到一個名稱為 _MSTeams 診斷 \<local date and time\> 記錄的資料夾_。 當您開啟 Microsoft 支援服務的支援要求時，此資料夾可以壓縮並共用。 資料夾會包含桌面、會議 (媒體) 資料夾，以及 (網頁) 。 您可以使用下列鍵盤快速鍵收集檔案：

- <kbd>Windows：Ctrl</kbd> + <kbd>Alt</kbd> + <kbd>Shift</kbd> + <kbd>1</kbd>

- <kbd>Mac：Option</kbd> + <kbd>Command</kbd> + <kbd>Shift</kbd> + <kbd>1</kbd>


媒體記錄預設為關閉。 若要啟用媒體記錄，使用者必須在用戶端中開啟Teams選項。 請前往 **設定** 一般，然後選取啟用會議診斷記錄， ( >  ******重新開機Teams) 。** 您必須Teams用戶端才能開始記錄 (請以滑鼠右鍵按一下 dock (Mac) 或工作列中的圖示，然後選取 (Windows) 。  在您離開之後，只要按一下應用程式圖示，即可再次開啟) 。

如果特定會議或即時活動發生問題，讓 URL 與會議相關聯會很有説明。 這提供額外的資訊，可協助找出記錄中確切的會議或即時事件。 這項資訊可以從會議的任何參與者或即時活動的簡報者或製作人收集。 您可以將游標停留在連接 URL 上，並選擇複製超連結，以 **捕獲此 URL。**

> [!NOTE]
> 如果已啟用媒體記錄功能，會議資料夾中會包含其他檔案，這是調查音訊和視音訊問題的必要檔案。 如果未啟用媒體記錄，則可用的記錄數量會受到限制。
  
> [!NOTE]
> 先前使用下列鍵盤快速鍵收集的調試記錄。 這些仍然會運作，而且會完成與收集支援檔案選項 **相同的記錄** 捕獲。
>
> - <kbd>Windows：Crtl</kbd> + <kbd>Alt</kbd> + <kbd>Shift</kbd> + <kbd>1</kbd>
>
> - <kbd>Mac：Option</kbd> + <kbd>Command</kbd> + <kbd>Shift</kbd> + <kbd>1</kbd>


下表概述各種用戶端及其相關聯的記錄。 記錄檔案會儲存在用戶端和作業系統的特定位置。


|用戶端 |調試|桌面|媒體|
|---------|---------|---------|---------|
|Web    |X         |-         |-         |
|Windows     |X         |X         |X         |
|Mac OSX     |X         |X         |X         |
|Linux     |X         |X         |X         |
|iOS     |-         |-         |-         |
|Android     |-         |-         |-         |

有關支援的作業系統和瀏覽器的完整清單，請參閱取得[用戶端Microsoft Teams。](get-clients.md)

## <a name="debug-logs"></a>調試記錄

請參閱收集和 _啟用記錄_ 一節，Windows Mac 指示。 調試記錄是由 Windows Mac 桌面用戶端，以及瀏覽器型用戶端所產生。 記錄以文字為基礎，由下而上讀取。 您可以使用任何文字型編輯器來讀取，登入用戶端時會建立新記錄。

調試記錄會顯示下列資料流程：

-   登錄

-   到中介層服務的連接要求

-   通話/交談

若要收集 Linux 的記錄：
- 鍵盤快速鍵<kbd>：Ctrl</kbd>  +  <kbd>Alt</kbd>  +  <kbd>Shift</kbd>  +  <kbd>1</kbd>  
- 檔案可在 `~/Downloads`

若要收集瀏覽器和瀏覽器的Windows：
- 鍵盤快速鍵<kbd>：Ctrl</kbd>  +  <kbd>Alt</kbd>  +  <kbd>Shift</kbd>  +  <kbd>1</kbd>  
- 檔案可在 `%userprofile%\Downloads`

## <a name="media-logs"></a>媒體記錄

請參閱收集和 _啟用記錄_ 一節，Windows Mac 指示。 媒體記錄包含有關會議音訊、視Teams資料的診斷資料。 當支援案例與通話相關問題連結時，這些案例是必填專案。

媒體記錄預設為關閉。 若要記錄會議Teams診斷資料，使用者必須在用戶端中開啟Teams選項。 請 **設定** 一般，選取啟用會議診斷記錄 (需要重新開機  >  **** **Teams)** 核取方塊、重新開機 Teams，然後重現問題。 

當您將記錄檔案傳送給 Microsoft 支援人員時，請確認記錄檔案的時間戳記，以確保記錄在您重現問題時涵蓋時間範圍。

若要收集 Linux 的記錄：  
- 檔案可在下列位置使用：
  - `~/.config/Microsoft/Microsoft Teams/media-stack/\*\.blog`
  - `~/.config/Microsoft/Microsoft Teams/skylib/\*\.blog`

若要收集記錄Windows：  
- 檔案可在下列位置使用：
  - `%userprofile%\Downloads\MSTeams Diagnostics Log\meeting\media-stack\\\*\.blog`
  - `%userprofile%\Downloads\MSTeams Diagnostics Log\meeting\skylib\\\*\.blog` 

以下是產生的記錄檔案及其包含的資訊清單。

<br/>

|記錄檔案名  |描述  |
|---------|---------|
|`Teams.msrtc-0-s1039525249.blog`     | 包含媒體堆疊相關資訊。 這包括頻道狀態，例如解析度、使用的解碼和編碼器，以及接收和接收的畫面數量，以及視像攝影機和視 (VBSS) 會話狀態。         |
|`rtmcontrol.msrtc-0-2415069487.blog`      |記錄與遠端控制動作相關的資訊，例如提供控制項時時間戳記，以及滑鼠指標資訊。          |
|`Teams_MediaStackETW-2-U-xr-U.etl`      |記錄媒體堆疊追蹤事件。         |
|`Debug-0-s2790420889.blog`    | 包含與媒體代理程式有關的資訊，包括呈現品質。          |
|`tscalling-0-2061129496.blog`   |在 ts-calling API 中記錄事件。       |

## <a name="desktop-logs"></a>桌面記錄

請參閱收集和 _啟用記錄_ 一節，Windows Mac 指示。 桌面記錄 ，也稱為 bootstrapper 記錄，包含桌面用戶端與瀏覽器之間發生的記錄資料。 與媒體記錄一樣，這些記錄只有在 Microsoft 要求時才能使用。 記錄是以文字為基礎，而且可以使用由上而下格式的任何文字型編輯器來讀取。

若要收集 Linux 的記錄：
- 按一下系統Microsoft Teams中的 [取得記錄記錄>**圖示。**
- 檔案將在 `~/.config/Microsoft/Microsoft Teams/logs.txt` 中提供。
  
若要收集記錄Windows：
- 按一下系統Microsoft Teams中的 [Microsoft Teams圖示，然後選取 [**收集支援檔案**> 。
- 檔案 `logs.txt` 會自動在 記事本中開啟。

在調查登錄Teams時，您可能需要手動收集桌面記錄。 這些記錄檔案位於 %appdata%\Microsoft\Teams Windows。

## <a name="browser-trace"></a>瀏覽器追蹤

針對某些類別的錯誤，Microsoft 支援服務可能會要求您收集瀏覽器追蹤。 這項資訊可提供發生錯誤時Teams用戶端狀態的重要詳細資料。

開始瀏覽器追蹤之前，請確認您已Teams。 在啟動追蹤之前，執行這項工作非常重要，這樣追蹤就不包含敏感性的登錄資訊。

在您登錄後，請選取下列其中一個連結 ，以適合您的瀏覽器使用，然後遵循所提供的步驟。 

-   [Chrome & Edge (Chromium) ](/azure/azure-portal/capture-browser-trace#google-chrome-and-microsoft-edge-chromium?preserve-view=true#resolution)

-   [邊緣](/azure/azure-portal/capture-browser-trace#microsoft-edge-edgehtml?preserve-view=true#resolution)

-   [Safari](/azure/azure-portal/capture-browser-trace#apple-safari?preserve-view=true#resolution)

-   [火狐](/azure/azure-portal/capture-browser-trace#firefox?preserve-view=true#resolution)

> [!NOTE]
> 在步驟中，將 Azure 入口網站的所有參照取代為 Teams用戶端。
  
## <a name="webrtc-logs-in-browsers"></a>網頁RTC 在瀏覽器中記錄
WebRTC 記錄可提供音訊和視音訊通話的連線詳細資料，以協助 Microsoft 支援服務。 請按照步驟在 Edge (Chromium) Chrome 中存取 WebRTC 記錄： 
  
1.  開啟新的定位停駐點，然後前往下列其中一個 URL：
    -   Edge (Chromium) ：`edge://webrtc-internals/`
    -   鉻： `chrome://webrtc-internals/`
  
2.  開啟 Teams Web 應用程式並重現問題。
  
3.  回到步驟 1 中存取的定位停駐點，您至少會看到兩個定位停駐點：
    -   GetUserMedia 要求
    -   `https://teams.microsoft.com/url`

4.  選擇包含應用程式名稱的Teams，然後儲存頁面內容。

## <a name="related-topics"></a>相關主題

[Teams 疑難排解](/MicrosoftTeams/troubleshoot/teams)
