---
title: 在 Microsoft 團隊的疑難排解中使用記錄檔
ms.reviewer: tejeshs
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 09/25/2017
audience: admin
ms.topic: troubleshooting
ms.service: msteams
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
search.appverid: MET150
description: 瞭解 Microsoft 團隊所產生的調試、媒體和桌面記錄，以及可在哪裡找到這些記錄，以及如何協助疑難排解。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2ff24ddb8aaf63b539959119138aebf2f5d4e81f
ms.sourcegitcommit: 3a577c07b4f399c81d8650a2bba8cfc00b695b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/21/2020
ms.locfileid: "48650826"
---
<a name="use-log-files-in-troubleshooting-microsoft-teams"></a>在 Microsoft 團隊的疑難排解中使用記錄檔
=================================================

用戶端自動產生三種類型的記錄檔案，可利用這些檔案來協助您針對 Microsoft 團隊進行疑難排解。

-   調試記錄

-   媒體記錄

-   桌面記錄

建立含 Microsoft 支援的支援要求時，支援工程師將需要調試記錄。 建立支援要求之前，請先將這些記錄放在手邊，讓 Microsoft 能夠快速開始疑難排解問題。 媒體或桌面記錄只有 Microsoft 要求時才是必要的。

下表列出各種用戶端及其相關記錄。 記錄檔案會儲存在用戶端與作業系統專用的位置。


|用戶端 |Debug|桌面|媒體|
|---------|---------|---------|---------|
|網站    |X         |-         |-         |
|Windows     |X         |X         |X         |
|Mac OSX     |X         |X         |X         |
|Linux     |X         |X         |X         |
|iOS     |-         |-         |-         |
|Android     |-         |-         |-         |

如需支援的作業系統和瀏覽器的完整清單，請參閱 [取得 Microsoft 團隊的用戶端](get-clients.md)。

<a name="debug-logs"></a>調試記錄
---------------------------

這些是最常見的記錄，而且對於所有 Microsoft 支援案例都是必要的。 [調試記錄] 是由 Windows 和 Mac 桌面用戶端以及瀏覽器的用戶端所產生。 這些記錄都是以文字為基礎，並從底部開始閱讀。 他們可以使用任何以文字為基礎的編輯器讀取，並在登入用戶端時建立新的記錄。

[調試記錄] 會顯示下列資料流程程：

-   Id

-   中介層服務的連線要求

-   通話/交談

調試記錄是使用下列 OS 特定方法產生：

-   時間

      鍵盤快速鍵： Ctrl + Alt + Shift + 1

-   Mac OSX：

      鍵盤快速鍵： Option + Command + Shift + 1

-   Linux

      鍵盤快速鍵： Ctrl + Alt + Shift + 1

調試記錄會自動下載到下列資料夾中。

-   Windows：% userprofile% \\ 下載

-   Mac OSX： ~/Downloads

-   Linux： ~/Downloads

-   瀏覽器：系統會提示您將調試記錄儲存到預設的儲存位置

<a name="media-logs"></a>媒體記錄
---------------------------

媒體記錄包含有關團隊會議中音訊、影片和螢幕共用的診斷資料。 它們對於連結至通話相關問題的支援案例是必要的。

媒體記錄會預設為關閉狀態。 若要記錄團隊會議的診斷資料，使用者必須開啟團隊用戶端中的選項。 移至**Settings**  >  **[設定一般**]，選取 [**啟用會議診斷記錄] (需要重新開機團隊**) 核取方塊，然後重新開機團隊並再現問題。 

下表列出媒體記錄位置。 當您將記錄檔傳送給 Microsoft 支援時，請確認記錄檔的時間戳記，以確定當您再現問題時，記錄會覆蓋時間範圍。

|用戶端 |位置 |
|---------|---------|
|Windows     |%appdata%\Microsoft\Teams\media-stack \\ *. 博客         |
|            |%appdata%\Microsoft\Teams\skylib \\ *. 博客
|            |%appdata%\Microsoft\Teams\media-stack \\ * .etl         |
|Mac OSX     |~ 路徑/library/application support 支援/Microsoft/團隊/media-stack/*. 博客         |
|            |~ 路徑/library/application support 支援/Microsoft/團隊/skylib/*. 博客         |
|Linux       |~/.config/Microsoft/Microsoft 團隊/media-stack/*. 博客         |
|            |~/.config/Microsoft/Microsoft 團隊/skylib/*. 博客         |

以下列出所產生的記錄檔及其包含的資訊。

|記錄檔案名  |說明  |
|---------|---------|
|Msrtc-0-s1039525249。     | 包含媒體堆疊的相關資訊。 這包括通道狀態（例如解析度、使用的解碼器和編碼器），以及傳送和接收的畫面數，以及攝影機與影片螢幕共用 (VBSS) 會話狀態。         |
|rtmcontrol msrtc-0-2415069487. 博客      |記錄與遠端控制動作相關的資訊，例如控制權的時間戳記，以及滑鼠指標資訊。          |
|Teams_MediaStackETW-2-U-xr-U      |記錄媒體堆疊追蹤事件。         |
|調試-0-s2790420889。    | 包含媒體代理程式的相關資訊，包括轉譯品質。          |
|tscalling-0-2061129496   |在 ts 呼叫 API 中記錄事件。       |

<a name="desktop-logs"></a>桌面記錄
---------------------

桌面記錄（也稱為引導程式記錄）包含在桌面用戶端與瀏覽器之間所發生的記錄資料。 就像媒體記錄一樣，只有 Microsoft 要求時才需要這些記錄。 這些記錄是以文字為基礎的，而且可以使用任何以文字為基礎的編輯器，以最高的格式閱讀。

時間

1.  以滑鼠右鍵按一下系統工作列中的 [ **Microsoft 團隊**] 圖示，然後選取 [**取得記錄**]

Mac OsX：

1.  從 **[說明] 下拉式功能表**中選擇 [**取得記錄**]

Linux

1.  按一下系統託盤中的 [ **Microsoft 團隊**] 圖示，然後選取 [**取得記錄**]

|用戶端 |位置 |
|---------|---------|
|Windows     |% appdata% \Microsoft\Teams\logs.txt         |
|Mac OSX     |~ 路徑/library/application support 支援/Microsoft/團隊/logs.txt         |
|Linux       |~/.config/Microsoft/Microsoft 小組/logs.txt         |


## <a name="related-topics"></a>相關主題

[Teams 疑難排解](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
