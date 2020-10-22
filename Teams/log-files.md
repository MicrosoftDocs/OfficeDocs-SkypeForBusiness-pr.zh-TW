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
<a name="use-log-files-in-troubleshooting-microsoft-teams"></a><span data-ttu-id="215f7-103">在 Microsoft 團隊的疑難排解中使用記錄檔</span><span class="sxs-lookup"><span data-stu-id="215f7-103">Use log files in troubleshooting Microsoft Teams</span></span>
=================================================

<span data-ttu-id="215f7-104">用戶端自動產生三種類型的記錄檔案，可利用這些檔案來協助您針對 Microsoft 團隊進行疑難排解。</span><span class="sxs-lookup"><span data-stu-id="215f7-104">There are three types of log files automatically produced by the client that can be leveraged to assist in troubleshooting Microsoft Teams.</span></span>

-   <span data-ttu-id="215f7-105">調試記錄</span><span class="sxs-lookup"><span data-stu-id="215f7-105">Debug logs</span></span>

-   <span data-ttu-id="215f7-106">媒體記錄</span><span class="sxs-lookup"><span data-stu-id="215f7-106">Media logs</span></span>

-   <span data-ttu-id="215f7-107">桌面記錄</span><span class="sxs-lookup"><span data-stu-id="215f7-107">Desktop logs</span></span>

<span data-ttu-id="215f7-108">建立含 Microsoft 支援的支援要求時，支援工程師將需要調試記錄。</span><span class="sxs-lookup"><span data-stu-id="215f7-108">When creating a support request with Microsoft Support, the support engineer will require the debug logs.</span></span> <span data-ttu-id="215f7-109">建立支援要求之前，請先將這些記錄放在手邊，讓 Microsoft 能夠快速開始疑難排解問題。</span><span class="sxs-lookup"><span data-stu-id="215f7-109">Having these logs on hand before creating the support request will allow Microsoft to quickly start troubleshooting the problem.</span></span> <span data-ttu-id="215f7-110">媒體或桌面記錄只有 Microsoft 要求時才是必要的。</span><span class="sxs-lookup"><span data-stu-id="215f7-110">Media or desktop logs are only required if requested by Microsoft.</span></span>

<span data-ttu-id="215f7-111">下表列出各種用戶端及其相關記錄。</span><span class="sxs-lookup"><span data-stu-id="215f7-111">The following table outlines the various clients, and their associated logs.</span></span> <span data-ttu-id="215f7-112">記錄檔案會儲存在用戶端與作業系統專用的位置。</span><span class="sxs-lookup"><span data-stu-id="215f7-112">Log files are stored in locations specific to the client and operating system.</span></span>


|<span data-ttu-id="215f7-113">用戶端</span><span class="sxs-lookup"><span data-stu-id="215f7-113">Client</span></span> |<span data-ttu-id="215f7-114">Debug</span><span class="sxs-lookup"><span data-stu-id="215f7-114">Debug</span></span>|<span data-ttu-id="215f7-115">桌面</span><span class="sxs-lookup"><span data-stu-id="215f7-115">Desktop</span></span>|<span data-ttu-id="215f7-116">媒體</span><span class="sxs-lookup"><span data-stu-id="215f7-116">Media</span></span>|
|---------|---------|---------|---------|
|<span data-ttu-id="215f7-117">網站</span><span class="sxs-lookup"><span data-stu-id="215f7-117">Web</span></span>    |<span data-ttu-id="215f7-118">X</span><span class="sxs-lookup"><span data-stu-id="215f7-118">X</span></span>         |-         |-         |
|<span data-ttu-id="215f7-119">Windows</span><span class="sxs-lookup"><span data-stu-id="215f7-119">Windows</span></span>     |<span data-ttu-id="215f7-120">X</span><span class="sxs-lookup"><span data-stu-id="215f7-120">X</span></span>         |<span data-ttu-id="215f7-121">X</span><span class="sxs-lookup"><span data-stu-id="215f7-121">X</span></span>         |<span data-ttu-id="215f7-122">X</span><span class="sxs-lookup"><span data-stu-id="215f7-122">X</span></span>         |
|<span data-ttu-id="215f7-123">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="215f7-123">Mac OSX</span></span>     |<span data-ttu-id="215f7-124">X</span><span class="sxs-lookup"><span data-stu-id="215f7-124">X</span></span>         |<span data-ttu-id="215f7-125">X</span><span class="sxs-lookup"><span data-stu-id="215f7-125">X</span></span>         |<span data-ttu-id="215f7-126">X</span><span class="sxs-lookup"><span data-stu-id="215f7-126">X</span></span>         |
|<span data-ttu-id="215f7-127">Linux</span><span class="sxs-lookup"><span data-stu-id="215f7-127">Linux</span></span>     |<span data-ttu-id="215f7-128">X</span><span class="sxs-lookup"><span data-stu-id="215f7-128">X</span></span>         |<span data-ttu-id="215f7-129">X</span><span class="sxs-lookup"><span data-stu-id="215f7-129">X</span></span>         |<span data-ttu-id="215f7-130">X</span><span class="sxs-lookup"><span data-stu-id="215f7-130">X</span></span>         |
|<span data-ttu-id="215f7-131">iOS</span><span class="sxs-lookup"><span data-stu-id="215f7-131">iOS</span></span>     |-         |-         |-         |
|<span data-ttu-id="215f7-132">Android</span><span class="sxs-lookup"><span data-stu-id="215f7-132">Android</span></span>     |-         |-         |-         |

<span data-ttu-id="215f7-133">如需支援的作業系統和瀏覽器的完整清單，請參閱 [取得 Microsoft 團隊的用戶端](get-clients.md)。</span><span class="sxs-lookup"><span data-stu-id="215f7-133">For a complete list of supported operating systems and browsers, see [Get clients for Microsoft Teams](get-clients.md).</span></span>

<a name="debug-logs"></a><span data-ttu-id="215f7-134">調試記錄</span><span class="sxs-lookup"><span data-stu-id="215f7-134">Debug logs</span></span>
---------------------------

<span data-ttu-id="215f7-135">這些是最常見的記錄，而且對於所有 Microsoft 支援案例都是必要的。</span><span class="sxs-lookup"><span data-stu-id="215f7-135">These are the most common logs and are required for all Microsoft support cases.</span></span> <span data-ttu-id="215f7-136">[調試記錄] 是由 Windows 和 Mac 桌面用戶端以及瀏覽器的用戶端所產生。</span><span class="sxs-lookup"><span data-stu-id="215f7-136">Debug logs are produced by the Windows and Mac desktop clients, as well as browser based clients.</span></span> <span data-ttu-id="215f7-137">這些記錄都是以文字為基礎，並從底部開始閱讀。</span><span class="sxs-lookup"><span data-stu-id="215f7-137">The logs are text based and are read from the bottom up.</span></span> <span data-ttu-id="215f7-138">他們可以使用任何以文字為基礎的編輯器讀取，並在登入用戶端時建立新的記錄。</span><span class="sxs-lookup"><span data-stu-id="215f7-138">They can be read using any text based editor and new logs are created when logging into the client.</span></span>

<span data-ttu-id="215f7-139">[調試記錄] 會顯示下列資料流程程：</span><span class="sxs-lookup"><span data-stu-id="215f7-139">Debug logs show the following data flows:</span></span>

-   <span data-ttu-id="215f7-140">Id</span><span class="sxs-lookup"><span data-stu-id="215f7-140">Login</span></span>

-   <span data-ttu-id="215f7-141">中介層服務的連線要求</span><span class="sxs-lookup"><span data-stu-id="215f7-141">Connection requests to middle tier services</span></span>

-   <span data-ttu-id="215f7-142">通話/交談</span><span class="sxs-lookup"><span data-stu-id="215f7-142">Call/conversation</span></span>

<span data-ttu-id="215f7-143">調試記錄是使用下列 OS 特定方法產生：</span><span class="sxs-lookup"><span data-stu-id="215f7-143">The debug logs are produced using the following OS specific methods:</span></span>

-   <span data-ttu-id="215f7-144">時間</span><span class="sxs-lookup"><span data-stu-id="215f7-144">Windows:</span></span>

      <span data-ttu-id="215f7-145">鍵盤快速鍵： Ctrl + Alt + Shift + 1</span><span class="sxs-lookup"><span data-stu-id="215f7-145">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

-   <span data-ttu-id="215f7-146">Mac OSX：</span><span class="sxs-lookup"><span data-stu-id="215f7-146">Mac OSX:</span></span>

      <span data-ttu-id="215f7-147">鍵盤快速鍵： Option + Command + Shift + 1</span><span class="sxs-lookup"><span data-stu-id="215f7-147">Keyboard shortcut: Option + Command + Shift+1</span></span>

-   <span data-ttu-id="215f7-148">Linux</span><span class="sxs-lookup"><span data-stu-id="215f7-148">Linux:</span></span>

      <span data-ttu-id="215f7-149">鍵盤快速鍵： Ctrl + Alt + Shift + 1</span><span class="sxs-lookup"><span data-stu-id="215f7-149">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

<span data-ttu-id="215f7-150">調試記錄會自動下載到下列資料夾中。</span><span class="sxs-lookup"><span data-stu-id="215f7-150">The debug logs are automatically downloaded to the following folders.</span></span>

-   <span data-ttu-id="215f7-151">Windows：% userprofile% \\ 下載</span><span class="sxs-lookup"><span data-stu-id="215f7-151">Windows: %userprofile%\\Downloads</span></span>

-   <span data-ttu-id="215f7-152">Mac OSX： ~/Downloads</span><span class="sxs-lookup"><span data-stu-id="215f7-152">Mac OSX: ~/Downloads</span></span>

-   <span data-ttu-id="215f7-153">Linux： ~/Downloads</span><span class="sxs-lookup"><span data-stu-id="215f7-153">Linux: ~/Downloads</span></span>

-   <span data-ttu-id="215f7-154">瀏覽器：系統會提示您將調試記錄儲存到預設的儲存位置</span><span class="sxs-lookup"><span data-stu-id="215f7-154">Browser: You will be prompted to save the debug log to default save location</span></span>

<a name="media-logs"></a><span data-ttu-id="215f7-155">媒體記錄</span><span class="sxs-lookup"><span data-stu-id="215f7-155">Media logs</span></span>
---------------------------

<span data-ttu-id="215f7-156">媒體記錄包含有關團隊會議中音訊、影片和螢幕共用的診斷資料。</span><span class="sxs-lookup"><span data-stu-id="215f7-156">Media logs contain diagnostic data about audio, video, and screen sharing in Teams meetings.</span></span> <span data-ttu-id="215f7-157">它們對於連結至通話相關問題的支援案例是必要的。</span><span class="sxs-lookup"><span data-stu-id="215f7-157">They are required for support cases that are linked to call-related issues.</span></span>

<span data-ttu-id="215f7-158">媒體記錄會預設為關閉狀態。</span><span class="sxs-lookup"><span data-stu-id="215f7-158">Media logging is turned off by default.</span></span> <span data-ttu-id="215f7-159">若要記錄團隊會議的診斷資料，使用者必須開啟團隊用戶端中的選項。</span><span class="sxs-lookup"><span data-stu-id="215f7-159">To log diagnostic data for Teams meetings, users must turn on the option in the Teams client.</span></span> <span data-ttu-id="215f7-160">移至**Settings**  >  **[設定一般**]，選取 [**啟用會議診斷記錄] (需要重新開機團隊**) 核取方塊，然後重新開機團隊並再現問題。</span><span class="sxs-lookup"><span data-stu-id="215f7-160">Go to **Settings** > **General**, select the **Enable logging for meeting diagnostics (requires restarting Teams**) check box, and then restart Teams and reproduce the issue.</span></span> 

<span data-ttu-id="215f7-161">下表列出媒體記錄位置。</span><span class="sxs-lookup"><span data-stu-id="215f7-161">The following table outlines the media log locations.</span></span> <span data-ttu-id="215f7-162">當您將記錄檔傳送給 Microsoft 支援時，請確認記錄檔的時間戳記，以確定當您再現問題時，記錄會覆蓋時間範圍。</span><span class="sxs-lookup"><span data-stu-id="215f7-162">When you send the log files to Microsoft support, please verify the timestamp of the log files to make sure the logs cover the time frame when you reproduced the issue.</span></span>

|<span data-ttu-id="215f7-163">用戶端</span><span class="sxs-lookup"><span data-stu-id="215f7-163">Client</span></span> |<span data-ttu-id="215f7-164">位置</span><span class="sxs-lookup"><span data-stu-id="215f7-164">Location</span></span> |
|---------|---------|
|<span data-ttu-id="215f7-165">Windows</span><span class="sxs-lookup"><span data-stu-id="215f7-165">Windows</span></span>     |<span data-ttu-id="215f7-166">%appdata%\Microsoft\Teams\media-stack \\ \*. 博客</span><span class="sxs-lookup"><span data-stu-id="215f7-166">%appdata%\Microsoft\Teams\media-stack\\*.blog</span></span>         |
|            |<span data-ttu-id="215f7-167">%appdata%\Microsoft\Teams\skylib \\ \*. 博客</span><span class="sxs-lookup"><span data-stu-id="215f7-167">%appdata%\Microsoft\Teams\skylib\\*.blog</span></span>
|            |<span data-ttu-id="215f7-168">%appdata%\Microsoft\Teams\media-stack \\ \* .etl</span><span class="sxs-lookup"><span data-stu-id="215f7-168">%appdata%\Microsoft\Teams\media-stack\\*.etl</span></span>         |
|<span data-ttu-id="215f7-169">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="215f7-169">Mac OSX</span></span>     |<span data-ttu-id="215f7-170">~ 路徑/library/application support 支援/Microsoft/團隊/media-stack/\*. 博客</span><span class="sxs-lookup"><span data-stu-id="215f7-170">~/Library/Application Support/Microsoft/Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="215f7-171">~ 路徑/library/application support 支援/Microsoft/團隊/skylib/\*. 博客</span><span class="sxs-lookup"><span data-stu-id="215f7-171">~/Library/Application Support/Microsoft/Teams/skylib/\*.blog</span></span>         |
|<span data-ttu-id="215f7-172">Linux</span><span class="sxs-lookup"><span data-stu-id="215f7-172">Linux</span></span>       |<span data-ttu-id="215f7-173">~/.config/Microsoft/Microsoft 團隊/media-stack/\*. 博客</span><span class="sxs-lookup"><span data-stu-id="215f7-173">~/.config/Microsoft/Microsoft Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="215f7-174">~/.config/Microsoft/Microsoft 團隊/skylib/\*. 博客</span><span class="sxs-lookup"><span data-stu-id="215f7-174">~/.config/Microsoft/Microsoft Teams/skylib/\*.blog</span></span>         |

<span data-ttu-id="215f7-175">以下列出所產生的記錄檔及其包含的資訊。</span><span class="sxs-lookup"><span data-stu-id="215f7-175">Here's a list of the log files that are generated and the information they contain.</span></span>

|<span data-ttu-id="215f7-176">記錄檔案名</span><span class="sxs-lookup"><span data-stu-id="215f7-176">Log file name</span></span>  |<span data-ttu-id="215f7-177">說明</span><span class="sxs-lookup"><span data-stu-id="215f7-177">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="215f7-178">Msrtc-0-s1039525249。</span><span class="sxs-lookup"><span data-stu-id="215f7-178">Teams.msrtc-0-s1039525249.blog</span></span>     | <span data-ttu-id="215f7-179">包含媒體堆疊的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="215f7-179">Contains information related to the media stack.</span></span> <span data-ttu-id="215f7-180">這包括通道狀態（例如解析度、使用的解碼器和編碼器），以及傳送和接收的畫面數，以及攝影機與影片螢幕共用 (VBSS) 會話狀態。</span><span class="sxs-lookup"><span data-stu-id="215f7-180">This includes channel status such as resolution, decoders and encoders used, and the number of frames sent and received, and camera and video-based screen sharing (VBSS) session status.</span></span>         |
|<span data-ttu-id="215f7-181">rtmcontrol msrtc-0-2415069487. 博客</span><span class="sxs-lookup"><span data-stu-id="215f7-181">rtmcontrol.msrtc-0-2415069487.blog</span></span>      |<span data-ttu-id="215f7-182">記錄與遠端控制動作相關的資訊，例如控制權的時間戳記，以及滑鼠指標資訊。</span><span class="sxs-lookup"><span data-stu-id="215f7-182">Records information related to remote control actions, such as the time stamp when control is given, and mouse pointer information.</span></span>          |
|<span data-ttu-id="215f7-183">Teams_MediaStackETW-2-U-xr-U</span><span class="sxs-lookup"><span data-stu-id="215f7-183">Teams_MediaStackETW-2-U-xr-U.etl</span></span>      |<span data-ttu-id="215f7-184">記錄媒體堆疊追蹤事件。</span><span class="sxs-lookup"><span data-stu-id="215f7-184">Records media stack trace events.</span></span>         |
|<span data-ttu-id="215f7-185">調試-0-s2790420889。</span><span class="sxs-lookup"><span data-stu-id="215f7-185">Debug-0-s2790420889.blog</span></span>    | <span data-ttu-id="215f7-186">包含媒體代理程式的相關資訊，包括轉譯品質。</span><span class="sxs-lookup"><span data-stu-id="215f7-186">Contains information related to the media agent, including rendering quality.</span></span>          |
|<span data-ttu-id="215f7-187">tscalling-0-2061129496</span><span class="sxs-lookup"><span data-stu-id="215f7-187">tscalling-0-2061129496.blog</span></span>   |<span data-ttu-id="215f7-188">在 ts 呼叫 API 中記錄事件。</span><span class="sxs-lookup"><span data-stu-id="215f7-188">Records events in the ts-calling API.</span></span>       |

<a name="desktop-logs"></a><span data-ttu-id="215f7-189">桌面記錄</span><span class="sxs-lookup"><span data-stu-id="215f7-189">Desktop logs</span></span>
---------------------

<span data-ttu-id="215f7-190">桌面記錄（也稱為引導程式記錄）包含在桌面用戶端與瀏覽器之間所發生的記錄資料。</span><span class="sxs-lookup"><span data-stu-id="215f7-190">Desktop logs, also known as bootstrapper logs, contains log data that occurs between the desktop client and the browser.</span></span> <span data-ttu-id="215f7-191">就像媒體記錄一樣，只有 Microsoft 要求時才需要這些記錄。</span><span class="sxs-lookup"><span data-stu-id="215f7-191">Like media logs, these logs are only needed if requested by Microsoft.</span></span> <span data-ttu-id="215f7-192">這些記錄是以文字為基礎的，而且可以使用任何以文字為基礎的編輯器，以最高的格式閱讀。</span><span class="sxs-lookup"><span data-stu-id="215f7-192">The logs are text based and can be read using any text based editor in a top down format.</span></span>

<span data-ttu-id="215f7-193">時間</span><span class="sxs-lookup"><span data-stu-id="215f7-193">Windows:</span></span>

1.  <span data-ttu-id="215f7-194">以滑鼠右鍵按一下系統工作列中的 [ **Microsoft 團隊**] 圖示，然後選取 [**取得記錄**]</span><span class="sxs-lookup"><span data-stu-id="215f7-194">Right-click the **Microsoft Teams** icon in your system tray, select **Get Logs**</span></span>

<span data-ttu-id="215f7-195">Mac OsX：</span><span class="sxs-lookup"><span data-stu-id="215f7-195">Mac OsX:</span></span>

1.  <span data-ttu-id="215f7-196">從 **[說明] 下拉式功能表**中選擇 [**取得記錄**]</span><span class="sxs-lookup"><span data-stu-id="215f7-196">Choosing **Get Logs** from the **Help** pull-down menu</span></span>

<span data-ttu-id="215f7-197">Linux</span><span class="sxs-lookup"><span data-stu-id="215f7-197">Linux:</span></span>

1.  <span data-ttu-id="215f7-198">按一下系統託盤中的 [ **Microsoft 團隊**] 圖示，然後選取 [**取得記錄**]</span><span class="sxs-lookup"><span data-stu-id="215f7-198">Click on the **Microsoft Teams** icon in your system tray, select **Get Logs**</span></span>

|<span data-ttu-id="215f7-199">用戶端</span><span class="sxs-lookup"><span data-stu-id="215f7-199">Client</span></span> |<span data-ttu-id="215f7-200">位置</span><span class="sxs-lookup"><span data-stu-id="215f7-200">Location</span></span> |
|---------|---------|
|<span data-ttu-id="215f7-201">Windows</span><span class="sxs-lookup"><span data-stu-id="215f7-201">Windows</span></span>     |<span data-ttu-id="215f7-202">% appdata% \Microsoft\Teams\logs.txt</span><span class="sxs-lookup"><span data-stu-id="215f7-202">%appdata%\Microsoft\Teams\logs.txt</span></span>         |
|<span data-ttu-id="215f7-203">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="215f7-203">Mac OSX</span></span>     |<span data-ttu-id="215f7-204">~ 路徑/library/application support 支援/Microsoft/團隊/logs.txt</span><span class="sxs-lookup"><span data-stu-id="215f7-204">~/Library/Application Support/Microsoft/Teams/logs.txt</span></span>         |
|<span data-ttu-id="215f7-205">Linux</span><span class="sxs-lookup"><span data-stu-id="215f7-205">Linux</span></span>       |<span data-ttu-id="215f7-206">~/.config/Microsoft/Microsoft 小組/logs.txt</span><span class="sxs-lookup"><span data-stu-id="215f7-206">~/.config/Microsoft/Microsoft Teams/logs.txt</span></span>         |


## <a name="related-topics"></a><span data-ttu-id="215f7-207">相關主題</span><span class="sxs-lookup"><span data-stu-id="215f7-207">Related topics</span></span>

[<span data-ttu-id="215f7-208">Teams 疑難排解</span><span class="sxs-lookup"><span data-stu-id="215f7-208">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
