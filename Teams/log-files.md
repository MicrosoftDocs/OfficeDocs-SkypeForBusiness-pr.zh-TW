---
title: 使用記錄檔案疑難排解 Microsoft Teams
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
description: 瞭解 Microsoft Teams 所製作的 Debug、Media 和桌面記錄，以及這些記錄可以在哪裡找到，以及如何協助進行疑難排解。
appliesto:
- Microsoft Teams
ms.openlocfilehash: e3e2c4d42d511e2a33a797099132ac42c0475d36
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51112189"
---
<a name="use-log-files-in-troubleshooting-microsoft-teams"></a>使用記錄檔案疑難排解 Microsoft Teams
=================================================

用戶端自動產生的記錄檔案類型有三種，可運用這些記錄檔案以協助 Microsoft Teams 進行疑難排解：

-   調試記錄

-   媒體記錄

-   桌面記錄

使用 Microsoft 支援服務建立支援要求時，支援工程師需要調試記錄。 建立支援要求之前，先將調試記錄放在手邊，Microsoft 就會快速開始疑難排解問題。 **媒體** 或 **桌面** 記錄只有在 Microsoft 要求時才能使用。

> [!NOTE]
> 在本文中，" **調試記錄** "一詞是指用於疑難排解的記錄。 不過，這些記錄產生的檔案名稱中會包含診斷 **記錄** 一詞。  

下表概述各種用戶端及其相關聯的記錄。 記錄檔案會儲存在用戶端和作業系統的特定位置。


|用戶端 |調試|桌面|媒體|
|---------|---------|---------|---------|
|Web    |X         |-         |-         |
|Windows     |X         |X         |X         |
|Mac OSX     |X         |X         |X         |
|Linux     |X         |X         |X         |
|iOS     |-         |-         |-         |
|Android     |-         |-         |-         |

有關支援的作業系統和瀏覽器的完整清單，請參閱取得 Microsoft [Teams 的用戶端](get-clients.md)。

<a name="debug-logs"></a>調試記錄
---------------------------

這些是最常見的記錄，且所有 Microsoft 支援案例都需要這些記錄。 調試記錄是由 Windows 和 Mac 桌面用戶端以及瀏覽器型用戶端所產生。 記錄是以文字為基礎，由下而上讀取。 您可以使用任何文字型編輯器來讀取，登入用戶端時會建立新記錄。

調試記錄會顯示下列資料流程：

-   登錄

-   到中介層服務的連接要求

-   通話/交談

使用下列 OS 特定方法產生調試記錄：

-   窗戶：

      鍵盤快速鍵：Ctrl + Alt + Shift + 1

-   Mac OSX：

      鍵盤快速鍵：Option + Command + Shift+1

-   Linux：

      鍵盤快速鍵：Ctrl + Alt + Shift + 1

系統會自動將調試記錄下載到下列資料夾：

-   Windows：%userprofile% \\ 下載

-   Mac OSX：~/Downloads

-   Linux：~/Downloads

-   瀏覽器：系統會提示您將調試記錄儲存到預設儲存位置

<a name="media-logs"></a>媒體記錄
---------------------------

媒體記錄包含 Teams 會議中音訊、視像和螢幕分享的診斷資料。 當支援案例與通話相關問題連結時，這些案例是必填專案。

媒體記錄預設為關閉。 若要記錄 Teams 會議的診斷資料，使用者必須開啟 Teams 用戶端中的選項。 前往設定一般，選取啟用會議診斷記錄 (需要重新開機 Teams) 核取方塊、重新開機  >  **** Teams，然後重現問題。  

下表概述媒體記錄位置。 當您將記錄檔案傳送給 Microsoft 支援人員時，請確認記錄檔案的時間戳記，以確保記錄在您重現問題時涵蓋時間範圍。

|用戶端 |位置 |
|---------|---------|
|Windows     |%appdata%\Microsoft\Teams\media-stack \\ *.blog         |
|            |%appdata%\Microsoft\Teams\skylib \\ *.blog
|            |%appdata%\Microsoft\Teams\media-stack \\ *.etl         |
|Mac OSX     |~/Library/Application Support/Microsoft/Teams/media-stack/*.blog         |
|            |~/Library/Application Support/Microsoft/Teams/skylib/*.blog         |
|Linux       |~/.config/Microsoft/Microsoft Teams/media-stack/*.blog         |
|            |~/.config/Microsoft/Microsoft Teams/skylib/*.blog         |

以下是產生的記錄檔案清單及其包含的資訊。

|記錄檔案名  |說明  |
|---------|---------|
|Teams.msrtc-0-s1039525249.blog     | 包含媒體堆疊相關資訊。 這包括頻道狀態，例如解析度、使用的解碼器及編碼器，以及接收和接收的畫面數量，以及視 (VBSS) 會話狀態。         |
|rtmcontrol.msrtc-0-2415069487.blog      |記錄與遠端控制動作相關的資訊，例如提供控制項時時間戳記，以及滑鼠指標資訊。          |
|Teams_MediaStackETW-2-U-xr-U.etl      |記錄媒體堆疊追蹤事件。         |
|Debug-0-s2790420889.blog    | 包含媒體代理程式相關資訊，包括呈現品質。          |
|tscalling-0-2061129496.blog   |在 ts-calling API 中記錄事件。       |

<a name="desktop-logs"></a>桌面記錄
---------------------

桌面記錄 ，也稱為 bootstrapper 記錄，包含桌面用戶端與瀏覽器之間發生的記錄資料。 與媒體記錄一樣，這些記錄只有在 Microsoft 要求時才能使用。 記錄是以文字為基礎，而且可以使用由上而下格式的任何文字型編輯器來讀取。

窗戶：

 - 以滑鼠右鍵按一下 **系統工作列** 中的 Microsoft Teams 圖示，然後選取 [ **取得記錄記錄**> 。

Mac OsX：

 - 從 **説明下拉式功能表****選擇取得記錄**。

Linux：

 - 按一下系統工作列 **中的 Microsoft Teams** 圖示，然後選取 [ **取得記錄記錄**> 。

|用戶端 |位置 |
|---------|---------|
|Windows     |%appdata%\Microsoft\Teams\logs.txt         |
|Mac OSX     |~/Library/Application Support/Microsoft/Teams/logs.txt         |
|Linux       |~/.config/Microsoft/Microsoft Teams/logs.txt         |


## <a name="related-topics"></a>相關主題

[Teams 疑難排解](/MicrosoftTeams/troubleshoot/teams)